1. We can use bootstrap by using the CDN version
remeber bootstrap depends on jquery so you need 
to add jquery too.

2. Bootstrap has three things:
  a. containers
  b. rows
  c. columns

3. both fixed container and fluid one has
left and right padding of 15px

4. Fixed container - "container" has a fixed max-width,
 which changes at certain break points, it also has
 margin-left and margin-right auto and width: 100%

5. Fluid container - "container-fluid" has a width: 100%
with margin left and right auto
				max-width
.container	    100%	540px	720px	960px	1140px
.container-sm	    100%	540px	720px	960px	1140px
.container-md	    100%	100%	720px	960px	1140px
.container-lg	    100%	100%	100%	960px	1140px
.container-xl	    100%	100%	100%	100%	1140px
.container-fluid	100%	100%	100%	100%	100%

6. We can use class="row" in a div in container for the element to
make a row

7. Each column has two part (The columns shold be in row):
  col-{size}-{number}
  {size} = the size of the viewport which you are targeting
  {number} = number of columns you want the element to span
  To design start with mobile design(Bootstrap use min-width)
  size: 
    .col- < 576px / .col-sm- > 576px / .col-md- > 768px / .col-lg- > 992px
    .col-xl- > 1200px 

(ATTENTION):
    because bootstrap uses min-width in @media-query when you change the column
    in a specific size in any format(any changes) these changes also applys to 
    any screens bigger than the current one.


8. Use column offsetting to position the child elements
 in different areas:
              bootstrap3: col-{size}-offset-{number}
              bootstrap4: offset-{size}-{number}

9. pushing element to the right / pulling element to left
(we do this to change the position)
      Bootstrap3: col-{size}-push-{number}
                  col-{size}-pull-{number}
      Bootstrap4:
                  order-{size}-{order number}

10. when there are multiple element with different height in the row
it is possible that some element can't come to the right position 
because of the height of top element:
  we can put a <div class="clearfix"></div> or use plain class
  clear: both;

11. Bootstrap uses classes for each tag (h1 h2 p ...) and give them
some styles that overrrides the browser style.
for example you can use class="h1" on span tag
There is also lead class that we can use on p tag or ...

12. The lists in bootstrap also have default styles.
you can give class="list-unstyled"
class="list-inline" (to make it horizontally)
and give class="list-inline-item" on li tags

13. Bootstrap also give the buttons and anchors tag some
default styles.
you can use btn class on another tags like a tag
class="btn {}" btn is somehow global
Bootstrap3: class="btn btn-default"
Bootstrap4: class="btn btn-primary"
      a. There are many btn-{classes}
      b. There are also btn-{sizes}
      c. we can use disable or active class on a tags and 
          disable or active attributes on buttons
[ATTENTION]
btn-{} changes based on themes.

14. we can have responsive img(max-width:100% and height: auto)

    Bootstrap3: class="img-responsive img-circle img-rounded img-thumnail"
    Bootstrap4: class="img-fluid rounded-circle rounded img-thumbnail" 

im-fluid or responsive give the max-width of 100% if the picture size is less than 100%
the imgae take the left position of the block, to centralize the block use:
    Bootstrap3: class="center-block"
    Bootstrap4: class="d-block mx-auto"

15. we can change the visibility of class by using bootstrap classes:

    Bootstrap3: class="hidden-{size}" hidden that class for that size
    Bootstrap4: class="d-none d-sm-{block}"    
          This element is invisible for xs screens block could be different things

16. We can make drop-down menu in bootstrap: (data-toggle="dropdown" is for jquery
and dropdown-header is optional) (We can also use class="disabled")

<div class="dropdown">
  <button class="dropdown-toggle" data-toggle="dropdown"></button>
  <ul class="dropdown-menu">
    <li class="dropdown-header"></li>
  </ul>
</div>

17. nav tabs and pill:
      Bootstrap3: you can just give nav class and nav-tabs(pills) to ul
      Bootstrap4: you have to give nav-items to li tags and nav-links 
                  to <a> tags as well

      Bootstrap3: in bootstrap3 you have to give class="active" with li tags
      Bootstrap4: in bootstrap4 you have to give class="active" to <a> tags

      using class="nav-justified" to make the each tab similar size.

18. Nav bars in bootstrap4:
      a. Navbars require a wrapping .navbar with .navbar-expand{-sm|-md|-lg|-xl}
       for responsive collapsing and color scheme classes.
       b. Navbars come with built-in support for a handful of sub-components:
       c. using class="fixed-{top}" on nav to make it fixed position
       d. using class="bg-{light, danger, warning, primary ...}"
       <nav class="navbar navbar-expand-md navbar-light fixed-top">
        <ul class="nav navbar-nav">
          <li class="nav-item"><a class="nav-link active" href="#">Ninja training</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Wizard training</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Psychic training</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Coding training</a></li>
        </ul>
      </nav>

19. We can use <div class="jumbotron"></div>

20. We can use class="form-control" for input tags to give them
some styles.

  we can also use form-inline for form tag

  also we can use <div class=form-group></div> to group some
  elements together.

We can use this style for checkbox and radio buttons
  <div class="form group form-check{-inline}">
    <label class="form-check-label" for="">
      <input class="form-check-input" type="checkbox">
      Ninja training
    </label>
  </div>

21. We can use badge class for a span (like notification)
  <button>
    Notification<span class="badge badge-secondary">20</span>
  </button>
  badge-pill for rounded one

22. labels are somehow like badge

  <button>
    Notification<span class="label label-danger">20</span>
  </button>

  23. You can make panels in bootstrap 3 (panel-title make heading smaller)
       (you can use card in bootstrap4)
  <div class="col-12">
    <div class="panel panel-danger">
      <div class="panel-heading">
        <h1>Ninja</h1>
      </div>
      <div class="panel-body">
        <p></p>
      </div>

      <div class="panel-footer">
        <a>More info</a>
      </div>
    </div>
  <div>
//////////////////////
  24. You can use tooltips on any elements:
      (remember to use js)

  <div class="card-footer">
    <a href="#" data-toggle="tooltip"
    data-placement="top" title="how to become a game designer">More info...</a>
  </div>
  $(function(e){
      $('[data-toggle="tooltip"]').tooltip();
    });
///////////////////////

25. You can use carousels for slidebars:
  (remember to use js for options)

  <div class="carousel slide" id="my-slider" data-ride="carousel">
      <ol class="carousel-indicators">
        <li data-target="#my-slider" data-slide-to="0" class="active"></li>
        <li data-target="#my-slider" data-slide-to="1"></li>
        <li data-target="#my-slider" data-slide-to="2"></li>
      </ol>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img class="d-block w-100" src="img/background-for-banner-png.png" alt="">
          <div class="carousel-caption">
            <h2>This is game designing</h2>
          </div>
        </div>
        <div class="carousel-item">
          <img class="d-block w-100" src="img/HGFNfP.jpg" alt="">
        </div>
        <div class="carousel-item">
          <img class="d-block w-100" src="img/version-banner-image.jpg" alt="">
        </div>
      </div>
      <a class="carousel-control-prev" href="#my-slider" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        
      </a>
      <a class="carousel-control-next" href="#my-slider" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
      </a>
    </div>

/////////////////

    26. We can use modal in bootstrap very easily:
    <div class="modal" id="my-modal">
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <button class="close" type="button" data-dismiss="modal"></button>
              <h2 class="modal-title">How to be a better ninja</h2>
            </div>
            <div class="modal-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis
            aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
            occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
          </div>
        </div> <!-- end modal-dialog-->
      </div> <!--end .modal-->


      <div class="card-footer">
        <a href="#" data-toggle="modal" data-target="#my-modal" class="card-link">More info...</a>
      </div>

///////////////////

27. Accordion is a group of panels that bound together
