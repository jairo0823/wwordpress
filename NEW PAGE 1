<?php get_header(); ?>

<?php
while (have_posts()) {
  the_post();


  $parentID = wp_get_post_parent_id(get_the_ID());
?>

<div class="page-banner">
  <div class="page-banner__bg-image" style="background-image: url(<?= get_theme_file_uri('images/ocean.jpg'); ?>)"></div>
  <div class="page-banner__content container container--narrow">
    <h1 class="page-banner__title"><?php the_title(); ?></h1>
    <div class="page-banner__intro">
      <p>Learn how the school of your dreams got started.</p>
    </div>
  </div>
</div>

<div class="container container--narrow page-section">

  <?php if ($parentID) { ?>
    <div class="metabox metabox--position-up metabox--with-home-link">
      <p>
        <a class="metabox__blog-home-link" href="<?= get_permalink($parentID); ?>">
          <i class="fa fa-home" aria-hidden="true"></i> Back to <?= get_the_title($parentID); ?>
        </a>
        <span class="metabox__main"><?php the_title(); ?></span>
      </p>
    </div>
  <?php } ?>

  <?php
  
    $children = get_pages(array(
      'child_of' => get_the_ID()
    ));


    if ($parentID || $children) {
      $findChildrenOf = $parentID ? $parentID : get_the_ID();
  ?>
    <div class="page-links">
      <h2 class="page-links__title">
        <a href="<?= get_permalink($findChildrenOf); ?>">
          <?= get_the_title($findChildrenOf); ?>
        </a>
      </h2>
      <ul class="min-list">
        <?php
          wp_list_pages(array(
            'title_li' => null,
            'child_of' => $findChildrenOf,
            'sort_column' => 'menu_order'
          ));
        ?>
      </ul>
    </div>
  <?php } ?>

  <div class="generic-content">
    <?php the_content(); ?>
  </div>
</div>

<div class="page-section page-section--beige">
  <div class="container container--narrow generic-content">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia voluptates vero vel temporibus aliquid possimus, facere accusamus modi...</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos molestiae, tempora alias atque vero officiis sit commodi ipsa vitae...</p>
  </div>
</div>

<div class="page-section page-section--white">
  <div class="container container--narrow">
    <h2 class="headline headline--medium">Biology Professors:</h2>
    <ul class="professor-cards">
      <li class="professor-card__list-item">
        <a href="#" class="professor-card">
          <img class="professor-card__image" src="<?= get_theme_file_uri('images/barksalot.jpg'); ?>" />
          <span class="professor-card__name">Dr. Barksalot</span>
        </a>
      </li>
      <li class="professor-card__list-item">
        <a href="#" class="professor-card">
          <img class="professor-card__image" src="<?= get_theme_file_uri('images/meowsalot.jpg'); ?>" />
          <span class="professor-card__name">Dr. Meowsalot</span>
        </a>
      </li>
    </ul>

    <hr class="section-break" />

    <div class="row group generic-content">
      <div class="one-third">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      </div>
      <div class="one-third">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      </div>
      <div class="one-third">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      </div>
    </div>
  </div>
</div>

<?php }    ?>

<?php get_footer(); ?>
