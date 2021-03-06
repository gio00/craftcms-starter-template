# craftcms-starter-template

This is a simple CraftCMS template with a few usefull plugins already installed: 
``` 
"craftcms/redactor"
"ether/seo"
"marionnewlevant/picture"
"sebastianlenz/linkfield"    
```

All the styles is done with `tailwindcss` framework and all the configuration is already done with the help of `laravel-mix`. 
When developing your theme you can use `yarn watch` and browsersync is already configured. The `DEFAULT_SITE_URL` will be used as proxy for browsersync to connect to reach the website, but you can edit this behaviour in the `webpack.mix.js`.

```
DEFAULT_SITE_URL="http://url-to-my-site.test"
```

When building for production purgecss will be used. I included the common extensions to the configuration of purgecss, the
files that will be analyzed for classes to keep. You can edit the configuration as you like in the `webpack.mix.js`. 
You can find more information on the official website: https://laravel-mix.com/

# Start

```
git clone https://github.com/giorgiopogliani/craftcms-starter-template.git website
cd website
composer install 
cp .env.example .env
php craft setup/security-key
mysql -uroot -p -e "create database example"
```

or you can also use composer

```
composer create-project giorgiopogliani/craftcms-starter-template --stability=dev website
```

Edit your `.env` to match your configuration.

```
php craft install/craft 
yarn install
yarn watch
```

# Deploy

There is a really simple deploy script in the root of the repo. You will need `lftp` if you use ftp to deploy your website or `rsync`if you use SSH. Add your credentials at the top of the file. There are a few command line options like `--watch=<folder to watch>` or `--build` to build css and js before deploy. 
 
