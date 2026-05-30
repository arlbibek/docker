# Fixing n8n Docker Permission Error (EACCES)

If you are deploying **n8n** using Docker Compose, you might encounter the following error when checking logs:

```bash
docker compose logs
```

Example output:

```
n8n  | Error: EACCES: permission denied, open '/home/node/.n8n/config'
```

This happens because the container does not have permission to write to the `.n8n` directory on the host.

## Step 1: Update Folder Permissions

Run the following command to give the container’s `node` user ownership of the n8n data directory:

```bash
sudo chown -R 1000:1000 ./n8n_data/
```

* `./n8n_data/` is the folder you mapped as a volume for n8n (`/home/node/.n8n`).
* `1000:1000` is the UID and GID of the `node` user inside the container.

---

## Step 2: Recreate the Container

After fixing permissions, force Docker Compose to recreate the container:

```bash
docker compose up -d --force-recreate
```

This ensures the container starts fresh with the correct permissions.

---

## Step 3: Verify

Check the logs again to confirm that the error is resolved:

```bash
docker compose logs
```

✅ You should see n8n starting normally without any `EACCES` errors.
