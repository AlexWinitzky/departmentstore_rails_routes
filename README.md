Department Store : Rails Routes / Controllers / Views

Instructions:

rails new department_store -d postgresql

cd department_store

git add .

git commit -m ‘initial commit’

(Create a git repo, copy in git remote add origin url)

(Clean up/modify Gemfile)

bundle

rails g model department name

rails g controller departments index show new edit --skip-routes

rails g controller items index show new edit --skip-routes

rails g model item name description:text department:belongs_to

(Inside /app/models/department.rb, add “has_many :items” to the department class)

(In config/routes.rb, add:

root ‘departments#index

resources :departments do
	resources :items
end
)

bundle exec db:create db:migrate

(Fill out controller methods, pay attention to how id’s are referenced when you nest routes, i.e. when should you use “id” vs “department_id”?)

(Finally fill out your views)

—————————————
Good work, now continue on with the bonus objectives!