# Security policy

Please do not report security vulnerabilities in public issues or discussions.

Report them privately through GitHub: go to the [Security tab](https://github.com/minhacademi/cademi-cli/security) of this repository and choose **Report a vulnerability**. Include the CLI version (`cademi version`), your platform, and the steps to reproduce.

If a credential may have been exposed, revoke it in your Cademí dashboard right away. Revoking a credential ends every session that uses it.

Every CLI release is signed. `cademi update` verifies the signature before it installs a new version.
