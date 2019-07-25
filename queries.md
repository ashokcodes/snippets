# User Table

```
CREATE TABLE user (
`id` INT UNSIGNED NOT NULL AUTO_INCREMENT,
`firstname` VARCHAR(30) NOT NULL,
`lastname` VARCHAR(30) NOT NULL,
`email` VARCHAR(50),
`reg_date` TIMESTAMP
PRIMARY KEY (`id`)
)
```