

## Prerequisites

- Node Version 22


### 1. For Run This Applications
```bash
# install packages
npm install 

# Testing The Applications
npm run check

# For Run the application
npm start
```


### Deployment Process
1. **Cleanup**: Removes existing process if running
   ```bash
   pm2 delete node-app || true
   ```

2. **Start Application**: Launches with absolute path
   ```bash
   pm2 start "./src/server.js" --name node-app
   ```

3. **Save Process List**: Persists PM2 configuration
   ```bash
   pm2 save
   ```

### About The Applications
1. **Route**: This Application has 2 route
   ```bash
   / # this will show a hello world page
   ```
      ```bash
   /api # this will response a json
   ```

2. **Default Port**: By Default this application will run on port 3000


#Challenges and Outcome
I faced issues running PM2 on a Windows self-hosted runner:
The pm2 command wasn’t recognized even after installing it globally, due to PATH and environment variable issues.
PM2 failed to start its daemon with permission errors (EPERM) and missing environment variables like HOME or HOMEPATH.
Attempts to fix environment variables and permissions didn’t resolve the errors.
Result: I couldn’t find a stable solution to run PM2 successfully in this Windows environment