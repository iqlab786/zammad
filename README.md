# Zammad Docker Compose Setup

Zammad will be available at: **http://localhost:8082**

```bash
# 1. Create data directories
mkdir -p data/storage data/backup data/elasticsearch data/postgres data/redis

# 2. (Linux only) fix Elasticsearch data dir permissions
sudo chown -R 1000:1000 data/elasticsearch

# 3. (Linux only) required by Elasticsearch
sudo sysctl -w vm.max_map_count=262144

# 4. Start the stack
docker compose up -d

# 5. Watch startup logs
docker compose logs -f zammad-init zammad-railsserver
```

Then open **http://localhost:8082** in your browser.
