// Provision an EC2 instance
const AWS = require('aws-sdk');

const ec2 = new AWS.EC2({
  region: 'us-east-1',
});

const params = {
  ImageId: 'ami-0b33d91d',
  InstanceType: 't2.micro',
  MinCount: 1,
  MaxCount: 1,
};

ec2.runInstances(params, (err, data) => {
  if (err) {
    console.log('Error', err);
  } else {
    console.log('Success', data);
  }
});
