resources
=========

Le routeur rails est composé en 3 parties.
------------------------------------------

* **Resources par défaut**
* **Non resourceful**
* **Les routes personnalisées**


Resources par défaut
--------------------

Les resources par défaut crée les actions:

* **index**
* **new**
* **create**
* **edit**
* **update**
* **delete**
* **destroy**

Exemple de façon de générer des resources :
-------------------------------------------

    resources :photos

Possibilité de créer des resources nidifiés
-------------------------------------------
    resources :admin do
    resources :post, :comments
    end

Possibilité de cacher la racine par:
------------------------------------

    scope 'admin' do
    ressources :post, :comments
    end

Le problèmes des "nested routes" est qu'elle ne doivent pas dépasser plus d'une itération pour des raisons de lisibilité.

Le shallow nesting
------------------

    resources :posts do
    resources :comments, only: [:index, :new, :create]
    end
    

    resources :comments, only: [:show, :edit, :update, :destroy]

Routes personnalisées
---------------------
Routes autres
-------------
