# LEARN

1. Aprender CloudFormation 

 - Oque faz?

 CreateStack: Starts the creation of a new stack. The input parameters to the call include the stack name and a file name (or Amazon S3 URL) for the source template. If the process of creating the stack is completed successfully, the stack is in the CREATE_COMPLETE state. If the stack creation fails, AWS CloudFormation deletes previously created resources, unless the user specified a flag to retain these elements for debugging purposes.
 
 ListStacks: Lists all stacks in your account. You can use this to view the set of stacks and their current status, such as whether the stack is being created or updated.
 

ListStackResources: Lists all the AWS resource names and identifiers that were created as part of creating a stack. In addition to providing you information, this call can be used by an AWS CloudFormation-aware application to understand its environment.

DescribeStackEvents: Lists all AWS CloudFormation generated operations and events for a stack so you can see how creation or deletion is progressing.

UpdateStack: Starts the update process for an existing stack. The input parameters to the call include the stack name and a file name (or Amazon S3 URL) for the updated template. If the process of updating the stack is completed successfully, the stack will be in the UPDATE_COMPLETE state. If the stack update fails, AWS CloudFormation rolls back any resource changes that have been made so that the stack is returned to state described in the original template.


 - Oque nao faz?

