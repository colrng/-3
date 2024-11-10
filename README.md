# cve-2023-25813 tast site

이 사이트는 cve-2023-25813 연습을 위해 만들어진 사이트입니다.

사이트를 실행하기 위해 사전에 필요한

npm install mysql2

npm install express

npm install sequelize

그리고 node.js와 mysql이 필요합니다.

그리고 sql은 

'''
CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,       
    username VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE, 
    createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS sessions (
    id INT AUTO_INCREMENT PRIMARY KEY,  
    user_id INT NOT NULL,                   
    session_token VARCHAR(255) NOT NULL,      
    createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP, 
    expiredAt TIMESTAMP NOT NULL,            
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
'''

이렇게 구성 하시면 됩니다.
