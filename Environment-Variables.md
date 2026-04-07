# ⚙️ Environment Variables (-e)

## Definition
Allows you to pass variables inside the container at runtime. Variables are crucial for settings, passwords, and configurations without hardcoding them into the image.

## Single Variable
```bash
docker run -e MY_NAME=Pawan ubuntu bash

# Inside the container:
echo $MY_NAME
# Output: Pawan
```

## Multiple Variables
```bash
docker run -e APP_ENV=production -e VERSION=1.0 nginx
```
*💡 Real-life Example:* Changing language preference or themes without buying a new phone.

## Professional .env Files
For many variables (e.g., Database config), use an environment file.

**Create `.env`:**
```text
DB_HOST=localhost
DB_USER=root
DB_PASS=123
```

**Run:**
```bash
docker run --env-file .env myapp
```

**🔥 Exam Note:** Variables are temporary! When a container is stopped and removed, any variable data injected is lost unless re-injected on start.
