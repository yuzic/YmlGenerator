YmlGenerator
============

Yandex.Market YML generator. An extension for Yii framework.

It supports output to a file or browser and uses XMLWriter as xml engine.

For generating xml data you need to create your own generator class and implement four methods:
  - shopInfo()
  - currencies()
  - categories()
  - offers() 
 
For example:
class MyYmlGenerator extends YmlGenerator {

  protected function shopInfo() {
      return array(
          'name'=>'',
          'company'=>'',
          'url'=>'',
          'platform'=>'',
          'version'=>'',
          'agency'=>'',
          'email'=>''
      );
  }
  
  
  protected function currencies() {
    $currencies = ...;
    foreach($currencies as $currecy) {
      $this->addCurrency($id,$rate);
    }
  }
  
  
  protected function categories() {
    $categories = ...;
    foreach($categories as $category) {
      $this->addCategory($name,$id,$parentId);
    }    
  }
  
  protected function offers() {
    $offers = ...;
    foreach($offers as $offer) {
      $this->addOffer($id,$data, $params, $available, $type, $bid, $cbid);
    }
  }
}

Description of add* methods you can find in YmlGenerator.php
More about YML see: http://help.yandex.ru/partnermarket/yml/about-yml.xml
