# You are the Hype!

- a
- b
- c

> Meep mEep


``` ruby
def edit
  redirect_to root_path unless current_user.is_a?(Administrator)
  
  @user = Profile.find(params[:id])
  
  @recruiters = []
  @privacy = (@user.privacy.nil?) ? Privacy.new : @user.privacy
  
  render "privacy/show"
end
```   