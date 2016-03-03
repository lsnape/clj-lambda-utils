# clj-lambda-deploy

A Leiningen plugin to deploy AWS Lambda function.

## Usage

Note! Currently only updating existing function is supported.

Use this for user-level plugins:

Put `[clj-lambda-deploy "0.1.0-SNAPSHOT"]` into the `:plugins` vector of your `:user`
profile.

Use this for project-level plugins:

Put `[clj-lambda-deploy "0.1.0-SNAPSHOT"]` into the `:plugins` vector of your project.clj.

Create S3 bucket and create following configuration into `project.clj`

    :lambda {:s3 {:bucket "your-bucket-name"
                  :object-key "lambda.jar"}
             :environments {"test" {:function-name "my-func-test"
                                    :region "eu-west-1"}
                            "production" {:function-name "my-func-prod"
                                          :region "eu-west-1"}}}

Then run

    $ lein clj-lambda-deploy update test

or

    $ lein clj-lambda-deploy update production

## License

Copyright © 2016 Markus Hjort

Distributed under the Eclipse Public License 1.0.
