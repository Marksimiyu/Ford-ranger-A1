# Ford-ranger-A1
  const { spawnSync } = require('child_process')
  const { existsSync, writeFileSync } = require('fs')
  
  const SESSION_ID = 'updateThis' // Edit this line only, dont remove ' <- this symbol
  
  if (!existsSync('levanter')) {
    spawnSync('git', ['clone', 'https://github.com/lyfe00011/whatsapp-bot-md.git', 'levanter'], {
      stdio: 'inherit',
    })
    const configPath = 'levanter/config.env'
    writeFileSync(configPath, `VPS=true\nSESSION_ID=${SESSION_ID}`)
    spawnSync('yarn', ['install', '--network-concurrency', '3'], { cwd: 'levanter', stdio: 'inherit' })
  }

    spawnSync('yarn', ['start'], { cwd: 'levanter', stdio: 'inherit' })
