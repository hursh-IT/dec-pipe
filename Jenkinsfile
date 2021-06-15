pipeline{
	
agent any

stages{
	
stage('pull code scm'){
steps{
echo "code pull successfully"
	}
}

stage('Installing the node packages')
steps{

sh '''rsync -vrhze "ssh -o StrictHostKeyChecking=no" --exclude node_modules/ . root@142.93.2.236:/var/www/html/express/

ssh root@142.93.2.236 <<EOF
cd /var/www/html/express/
npm install
EOF'''

}

stage('start server'){
	
steps{
	sh 'pm2 start src/index.js'
	
}
}

}

}
