# Chef kitchen for BEM (alfa)

## Work in VM

<pre>
chef-bem/
  │
  ├── cookbooks/
  ├── project-stub/
  └── <b>Vagrantfile</b>
</pre>

    git clone https://github.com/ilyar/chef-bem.git
    vagrant up
    vagrant ssh
    bem server
    # open http://localhost:3000/desktop.bundles/index/
    cd project-stub # bem coding

## Experiment (not work)

<pre>
project-stub/
  │
  ├── .bem/
  ├── desktop.blocks/
  ├── desktop.bundles/
  ├── .gitignore
  ├── favicon.ico
  ├── package.json
  └── <b>Vagrantfile</b>
</pre>

    git clone https://github.com/ilyar/chef-bem.git
    cd tests
    vagrant up
    vagrant ssh
    bem server
    # open http://localhost:3000/desktop.bundles/index/
    # bem coding
