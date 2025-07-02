## 主な要素
* ルーティング（URL＝スラッグとPATH情報）
* ディレクトリ構造
* Composer(PHPのパッケージ管理ツール、ライブラリの導入などが簡単)
* Controller
* Models
* Views
* config
* database
* includes
* public
* assets/css,js,images
* vendor(vendor/bin)
* composer
* PHP Mailer（ライブラリ）
* Ubuntu

## ポイント
phpファイルのスタイルシートの読み込みパス情報、各ページへのリンク（ルーティング）、URLの階層構造とファイル名の組み合わせ（スラッグ名）がページの階層構造ごとに代わってしまう。

```php
<?= BASE_URL ?>app/views/recruit/requirement/index.php

<?php include BASE_PATH .'includes/footer.php' ?>

<?php
include BASE_PATH . 'includes/header.php';
?>

<?php
include_once dirname(__DIR__, 4) . '/config/config.php'; 
?>

```
## include
includeとは。。。
### ($_SERVER['DOCUMENT_ROOT']
## Ubuntu
## Docker
```
vender/bin/sail
```
Laravel Sail
## pdo
データベースへの接続
```
C:.
│  composer.json
│  composer.lock
│  htaccess
│  memo
│  README.md
│  tree.txt
│  ディレクトリ構造.text
│  
├─.vscode
│      settings.json
│      
├─admin
├─app
│  ├─controllers
│  │      contactController
│  │      
│  ├─models
│  │      contact.php
│  │      
│  └─views
│      ├─business
│      │      21253_color.svg
│      │      3137_color.svg
│      │      3208_color.svg
│      │      9539_color.svg
│      │      index.php
│      │      
│      ├─company
│      │  │  index.php
│      │  │  
│      │  ├─daihyou
│      │  │      index.php
│      │  │      
│      │  ├─ennkaku
│      │  │      index.php
│      │  │      
│      │  ├─gaiyou
│      │  │      index.php
│      │  │      
│      │  └─rinenn
│      │          index.php
│      │          
│      ├─contact
│      │      confirm.php
│      │      error.php
│      │      form.php
│      │      send.php
│      │      thank_you.php
│      │      
│      ├─news
│      │      index.php
│      │      news_detail.php
│      │      
│      ├─others
│      │  ├─privacy
│      │  │      index.php
│      │  │      
│      │  └─sitePolicy
│      │          index.php
│      │          
│      └─recruit
│          │  index.php
│          │  
│          └─requirement
│              │  index.php
│              │  
│              ├─callCenter
│              │      index.php
│              │      
│              └─mobileShop
│                      index.php
│                      
├─config
│      config.php
│      database.php
│      
├─database
│      db.php
│      init.php
│      
├─includes
│      footer.php
│      functions.php
│      header.php
│      top_news.php
│      
├─public
│  │  index.php
│  │  
│  └─assets
│      ├─css
│      │      business.css
│      │      color.css
│      │      company.css
│      │      contact.css
│      │      daihyou.css
│      │      default.css
│      │      element.css
│      │      ennkaku.css
│      │      footer.css
│      │      form.css
│      │      gaiyou.css
│      │      header.css
│      │      index.css
│      │      news.css
│      │      news_detail.css
│      │      recruit.css
│      │      requirement.css
│      │      resetting.css
│      │      rinenn.css
│      │      scrollTop.css
│      │      subpage.css
│      │      table.css
│      │      
│      ├─images
│      │  │  logo.png
│      │  │  
│      │  └─other_images
│      │      │  business_call_center_unsplash.avif
│      │      │  business_education_unsplash.jpg
│      │      │  business_mobile_unsplash.avif
│      │      │  company-building-unsplash.jpg
│      │      │  company-meeting-unsplash.jpg
│      │      │  company-philosophy-unslash.jpg
│      │      │  company-philosophy-wall-unslash.jpg
│      │      │  company_sign-unsplash.jpg
│      │      │  hunters-race-MYbhN8KaaEc-unsplash.jpg
│      │      │  internet_2unific240629.JPG
│      │      │  nara-Hase-m_find47.jpg
│      │      │  nara-Okuasuka_Sky_Observatory_find47.jpg
│      │      │  recruit_woman_unsplash.avif
│      │      │  wifi_5G1449_TP_V.jpg
│      │      │  
│      │      ├─business
│      │      │      business_education_unsplash.jpg
│      │      │      business_unsplash.jpg
│      │      │      callcenter-img.jpg
│      │      │      smartphone-img.jpg
│      │      │      
│      │      ├─contact
│      │      │      hunters-race-MYbhN8KaaEc-unsplash.jpg
│      │      │      
│      │      ├─news
│      │      │      news_img.jpg
│      │      │      
│      │      ├─post
│      │      │      post-books-unsplash.jpg
│      │      │      
│      │      ├─recruit
│      │      │      hunters-race-MYbhN8KaaEc-unsplash.jpg
│      │      │      recriut_page_img.avif
│      │      │      
│      │      └─top_page
│      │              arlington-research-kN_kViDchA0-unsplash.jpg
│      │              kyoto-Kenninji-temple_Chouontei_Garden-s.jpg
│      │              nara-Autumnal_leaves_in_Nara_Park-m.jpg
│      │              nara-miwa_somen-m.jpg
│      │              nara-Nara_Nara_City__Sarusawaike_-m.jpg
│      │              nara-Okuasuka_Sky_Observatory-m.jpg
│      │              nara-Omine_and_angel's_ladder-m.jpg
│      │              osaka-Night_Lights-m.jpg
│      │              osaka-Poppy_and_Nemophila-m.jpg
│      │              osaka-Sunset_at_Osaka_Port_Diamond_Point-m.jpg
│      │              premium_photo-1675526112779-9181f2559894.avif
│      │              recruit_woman_unsplash.avif
│      │              
│      └─js
│              main.js
│              scrollTop.js
│              slick.js
│              
└─vendor
    │  autoload.php
    │  
    ├─composer
    │      autoload_classmap.php
    │      autoload_namespaces.php
    │      autoload_psr4.php
    │      autoload_real.php
    │      autoload_static.php
    │      ClassLoader.php
    │      installed.json
    │      installed.php
    │      InstalledVersions.php
    │      LICENSE
    │      platform_check.php
    │      
    └─phpmailer
        └─phpmailer
            │  .codecov.yml
            │  .editorconfig
            │  .gitattributes
            │  .gitignore
            │  changelog.md
            │  COMMITMENT
            │  composer.json
            │  get_oauth_token.php
            │  LICENSE
            │  phpcs.xml.dist
            │  phpdoc.dist.xml
            │  phpunit.xml.dist
            │  README.md
            │  SECURITY.md
            │  UPGRADING.md
            │  VERSION
            │  
            ├─.github
            │  │  dependabot.yml
            │  │  FUNDING.yml
            │  │  
            │  ├─actions
            │  │  └─build-docs
            │  │          Dockerfile
            │  │          entrypoint.sh
            │  │          
            │  ├─ISSUE_TEMPLATE
            │  │      bug_report.md
            │  │      
            │  └─workflows
            │          docs.yaml
            │          scorecards.yml
            │          tests.yml
            │          
            ├─.phan
            │      config.php
            │      
            ├─docs
            │      README.md
            │      
            ├─examples
            │  │  azure_xoauth2.phps
            │  │  callback.phps
            │  │  contactform-ajax.phps
            │  │  contactform.phps
            │  │  contents.html
            │  │  contentsutf8.html
            │  │  DKIM_gen_keys.phps
            │  │  DKIM_sign.phps
            │  │  exceptions.phps
            │  │  extending.phps
            │  │  gmail.phps
            │  │  gmail_xoauth.phps
            │  │  mail.phps
            │  │  mailing_list.phps
            │  │  pop_before_smtp.phps
            │  │  README.md
            │  │  sendmail.phps
            │  │  sendoauth2.phps
            │  │  send_file_upload.phps
            │  │  send_multiple_file_upload.phps
            │  │  simple_contact_form.phps
            │  │  smime_signed_mail.phps
            │  │  smtp.phps
            │  │  smtp_check.phps
            │  │  smtp_low_memory.phps
            │  │  smtp_no_auth.phps
            │  │  ssl_options.phps
            │  │  
            │  └─images
            │          PHPMailer card logo.afdesign
            │          PHPMailer card logo.png
            │          PHPMailer card logo.svg
            │          phpmailer.png
            │          phpmailer_mini.png
            │          
            ├─language
            │      phpmailer.lang-af.php
            │      phpmailer.lang-ar.php
            │      phpmailer.lang-as.php
            │      phpmailer.lang-az.php
            │      phpmailer.lang-ba.php
            │      phpmailer.lang-be.php
            │      phpmailer.lang-bg.php
            │      phpmailer.lang-bn.php
            │      phpmailer.lang-ca.php
            │      phpmailer.lang-cs.php
            │      phpmailer.lang-da.php
            │      phpmailer.lang-de.php
            │      phpmailer.lang-el.php
            │      phpmailer.lang-eo.php
            │      phpmailer.lang-es.php
            │      phpmailer.lang-et.php
            │      phpmailer.lang-fa.php
            │      phpmailer.lang-fi.php
            │      phpmailer.lang-fo.php
            │      phpmailer.lang-fr.php
            │      phpmailer.lang-gl.php
            │      phpmailer.lang-he.php
            │      phpmailer.lang-hi.php
            │      phpmailer.lang-hr.php
            │      phpmailer.lang-hu.php
            │      phpmailer.lang-hy.php
            │      phpmailer.lang-id.php
            │      phpmailer.lang-it.php
            │      phpmailer.lang-ja.php
            │      phpmailer.lang-ka.php
            │      phpmailer.lang-ko.php
            │      phpmailer.lang-ku.php
            │      phpmailer.lang-lt.php
            │      phpmailer.lang-lv.php
            │      phpmailer.lang-mg.php
            │      phpmailer.lang-mn.php
            │      phpmailer.lang-ms.php
            │      phpmailer.lang-nb.php
            │      phpmailer.lang-nl.php
            │      phpmailer.lang-pl.php
            │      phpmailer.lang-pt.php
            │      phpmailer.lang-pt_br.php
            │      phpmailer.lang-ro.php
            │      phpmailer.lang-ru.php
            │      phpmailer.lang-si.php
            │      phpmailer.lang-sk.php
            │      phpmailer.lang-sl.php
            │      phpmailer.lang-sr.php
            │      phpmailer.lang-sr_latn.php
            │      phpmailer.lang-sv.php
            │      phpmailer.lang-tl.php
            │      phpmailer.lang-tr.php
            │      phpmailer.lang-uk.php
            │      phpmailer.lang-ur.php
            │      phpmailer.lang-vi.php
            │      phpmailer.lang-zh.php
            │      phpmailer.lang-zh_cn.php
            │      
            ├─src
            │      DSNConfigurator.php
            │      Exception.php
            │      OAuth.php
            │      OAuthTokenProvider.php
            │      PHPMailer.php
            │      POP3.php
            │      SMTP.php
            │      
            └─test
                │  DebugLogTestListener.php
                │  fakepopserver.sh
                │  fakesendmail.sh
                │  PreSendTestCase.php
                │  runfakepopserver.sh
                │  SendTestCase.php
                │  testbootstrap-dist.php
                │  TestCase.php
                │  validators.php
                │  
                ├─Fixtures
                │  ├─FileIsAccessibleTest
                │  │      accessible.txt
                │  │      inaccessible.txt
                │  │      
                │  └─LocalizationTest
                │          phpmailer.lang-fr.php
                │          phpmailer.lang-nl.php
                │          phpmailer.lang-xa_scri_cc.php
                │          phpmailer.lang-xb_scri.php
                │          phpmailer.lang-xc_cc.php
                │          phpmailer.lang-xd_cc.php
                │          phpmailer.lang-xd_scri.php
                │          phpmailer.lang-xe.php
                │          phpmailer.lang-xx.php
                │          phpmailer.lang-yy.php
                │          phpmailer.lang-zz.php
                │          
                ├─Language
                │      TranslationCompletenessTest.php
                │      
                ├─OAuth
                │      OAuthTest.php
                │      
                ├─PHPMailer
                │      AddEmbeddedImageTest.php
                │      AddrFormatTest.php
                │      AddStringAttachmentTest.php
                │      AddStringEmbeddedImageTest.php
                │      AuthCRAMMD5Test.php
                │      CustomHeaderTest.php
                │      DKIMTest.php
                │      DKIMWithoutExceptionsTest.php
                │      DSNConfiguratorTest.php
                │      EncodeQTest.php
                │      EncodeStringTest.php
                │      FileIsAccessibleTest.php
                │      FilenameToTypeTest.php
                │      GenerateIdTest.php
                │      GetLastMessageIDTest.php
                │      HasLineLongerThanMaxTest.php
                │      Html2TextTest.php
                │      ICalTest.php
                │      IsPermittedPathTest.php
                │      IsValidHostTest.php
                │      LocalizationTest.php
                │      MailTransportTest.php
                │      MbPathinfoTest.php
                │      MimeTypesTest.php
                │      NormalizeBreaksTest.php
                │      ParseAddressesTest.php
                │      PHPMailerTest.php
                │      PunyencodeAddressTest.php
                │      QuotedStringTest.php
                │      ReplyToGetSetClearTest.php
                │      SetErrorTest.php
                │      SetFromTest.php
                │      SetTest.php
                │      SetWordWrapTest.php
                │      Utf8CharBoundaryTest.php
                │      ValidateAddressCustomValidatorTest.php
                │      ValidateAddressTest.php
                │      WrapTextTest.php
                │      XMailerTest.php
                │      
                ├─POP3
                │      PopBeforeSmtpTest.php
                │      
                └─Security
                        DenialOfServiceVectorsTest.php
                        

```