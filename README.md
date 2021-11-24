# Final-Project

import { StatusBar } from 'expo-status-bar';
import React from 'react';
import { StyleSheet, Text, View, Image, Button, ScrollView, Alert, Pressable, TextInput} from 'react-native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import { NavigationContainer } from '@react-navigation/native';
import { BrowserRouter as Router, Route, Routes, useNavigate } from 'react-router-dom';



let home_gif = "https://i.pinimg.com/originals/ca/3a/5d/ca3a5da246e7f436f6f17c069a3a292a.gif"
let price_tag = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRcR0a_nnvdUUocj2-wps61RqwBvhdsk4Y8gkP9Jd5AmjmnrQSKRvtmWXNCdIyxbup69io&usqp=CAU"
let del_icon = "https://png.pngtree.com/png-vector/20190429/ourlarge/pngtree-vector-delivery-motorbike-icon-png-image_1002148.jpg"
let card_icon = "https://i.pinimg.com/originals/c0/c6/ff/c0c6ffeb26cebdc2fe976a7dee95830e.jpg"

const addToCart = () => Alert.alert('Added to your cart!')
const placeOrder = () => Alert.alert('Thank you for choosing BOOZE.PH! Drink Responsibly')


let b_gif = "https://i.pinimg.com/originals/8b/24/17/8b2417decfa1cda2deef887c87ff7ae7.gif"
let b1 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Triple_J_Special_1L_Bottles_1024x1024.png?v=1591902285"
let b2 = "https://cdn.shopify.com/s/files/1/2141/9909/products/UltimateShotsPack_1024x1024.png?v=1591902291"
let b3 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/MicrosoftTeams-image_1349_500x.png?v=1632810609"

let w_gif = "https://cdn.dribbble.com/users/1708903/screenshots/6116183/scotch.gif"
let w1 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JimBeamWhite_1024x1024.png?v=1618577895"
let w2 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JW_Red_Label_700ml_1024x1024.png?v=1591901837"
let w3 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JW_Red_Label_1L_1024x1024.png?v=1569202009"
let w4 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Johnnie_Walker_Black_Label_700ml_1024x1024.png?v=1569201809"
let w5 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Jd700ml_1024x1024.png?v=1591901784"
let w6 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JDHoney_1024x1024.png?v=1585905364"
let w7 = "https://cdn.shopify.com/s/files/1/2141/9909/products/jwblacklabel1l_1_1024x1024.png?v=1590569693"
let w8 = "https://cdn.shopify.com/s/files/1/2141/9909/products/ChivasRegal12700ml_1024x1024.png?v=1598612136"
let w9 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Jameson1L_1024x1024.png?v=1614919650"
let w10 = "https://cdn.shopify.com/s/files/1/2141/9909/products/jack_daniel_s_1l_1_1024x1024.png?v=1590569700"
let w11 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-johnnie-walker-double-black_x192@2x.png?v=1622192133"
let w12 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Chivas12yo1L_1024x1024.png?v=1598612162"
let w13 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-johnnie-walker-gold_500x.png?v=1622192219"
let w14 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JOHNNIE_WALKER_DOUBLE_BLACK_1L_1024x1024.png?v=1569089668"
let w15 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Chivas18yo_1024x1024.png?v=1598612190"
let w16 = "https://cdn.shopify.com/s/files/1/2141/9909/products/dalmore-12yo_1024x1024.png?v=1593686584"
let w17 = "https://cdn.shopify.com/s/files/1/2141/9909/products/dalmore-15yo-2_1024x1024.png?v=1593686622"
let w18 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/MicrosoftTeams-image_232_500x.png?v=1617282177"

let t_gif = "https://cdn.dribbble.com/users/593387/screenshots/1626862/digital-tequila.gif"
let t1 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-el-hombre-white-tequila_500x.png?v=1622107299"
let t2 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-mojitos-silver_500x.png?v=1621330033"
let t3 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-el-hombre-gold-tequila_500x.png?v=1622107277"
let t4 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-mojitos-gold_500x.png?v=1622696996"
let t5 = "https://cdn.shopify.com/s/files/1/2141/9909/products/JoseCuervo375ml_1024x1024.png?v=1619720319"
let t6 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Jose_Cuervo_Especial_Silver_700ml_1024x1024.png?v=1570122747"
let t7 = "http://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-jose-cuervo-especial-gold.png?v=1622193266"
let t8 = "https://cdn.shopify.com/s/files/1/2141/9909/products/PAtronReposado750ml_1024x1024.png?v=1593468081"
let t9 = "https://cdn.shopify.com/s/files/1/2141/9909/products/PatronAnejo750ml_1024x1024.png?v=1593468114"

let v_gif = "https://cdn.dribbble.com/users/1708903/screenshots/6116219/martini.gif"
let v1 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Smirnoff_Red_Vodka_1024x1024.png?v=1570122730"
let v2 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Absolutblue700ml_1024x1024.png?v=1599120661"
let v3 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Absolutblue1Lnew_1024x1024.png?v=1599120702"
let v4 = "https://cdn.shopify.com/s/files/1/2141/9909/products/AbsolutRubyRed700ml_1024x1024.png?v=1599120679"
let v5 = "https://cdn.shopify.com/s/files/1/2141/9909/products/AbsolutApeach700ml_1024x1024.png?v=1616061551"
let v6 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Absolut_Citron_700ml_1024x1024.png?v=1569159660"
let v7 = "https://cdn.shopify.com/s/files/1/2141/9909/products/absolut_mandrin_700ml_a3e1d4b0-5276-401f-808e-533a0999e36a_1024x1024.png?v=1569248630"
let v8 = "https://cdn.shopify.com/s/files/1/2141/9909/products/AbsolutMandrin700mlnew_1024x1024.png?v=1599120657"
let v9 = "https://cdn.shopify.com/s/files/1/0423/6967/9515/products/WEB-42-below-pure-vodka_500x.png?v=1622686589"
let v10 = "https://cdn.shopify.com/s/files/1/2141/9909/products/GreyGoose750ml_1024x1024.png?v=1614602844"

let be_gif = "https://cdn.dribbble.com/users/2172077/screenshots/7111433/media/3b65241a979a1ee3f4c15296ac30ee1a.gif"
let be1 = "https://cdn.shopify.com/s/files/1/2141/9909/products/SmirnoffMuleBottle_1024x1024.png?v=1600767267"
let be2 = "https://cdn.shopify.com/s/files/1/0494/4071/9012/products/Brew-Kettle-330mL-New-Label-Bottle_800x.png?v=1625128967"
let be3 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Heineken_330ml_1024x1024.png?v=1569208126"
let be4 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Budweiser_330ml_Bttl_1_1024x1024.png?v=1626162284"
let be5 = "https://media.danmurphys.com.au/dmo/product/709123-1.png"
let be6 = "http://assets.stickpng.com/images/585e5e47cb11b227491c33ee.png"
let be7 = "https://cdn.shopify.com/s/files/1/2141/9909/products/tiger-black-500ml-bundle-of-4-cans_1024x1024.png?v=1591902267"
let be8 = "https://cdn.shopify.com/s/files/1/2141/9909/products/heineken-330ml-bundle-of-4-cans_1024x1024.png?v=1590580513"
let be9 = "https://cdn.shopify.com/s/files/1/2141/9909/products/SanMigLightBeer330mLCanBundleof24_2_7bb46e1c-f080-4872-919c-b9b69515f51d_1024x1024.png?v=1608042381"
let be10 = "https://cdn.shopify.com/s/files/1/2141/9909/products/RedHorseBeer330mLCanBundleof24_2_1024x1024.png?v=1602490407"
let be11 ="https://cdn.shopify.com/s/files/1/2141/9909/products/SanMiguelPalePilsenBeer330mLCanBundleof24_2_1024x1024.png?v=1602490435"
let be12 = "https://cdn.shopify.com/s/files/1/2141/9909/products/SanMiguelFlavoredBeer-Apple330mLCanBundleof24_2_1024x1024.png?v=1602490454"
let be13 = "https://cdn.shopify.com/s/files/1/2141/9909/products/heineken-keg-2020_1024x1024.png?v=1590527186"
let be14 = "https://cdn.shopify.com/s/files/1/2141/9909/products/Heineken_Case_1024x1024.png?v=1573994970"


function HomeScreen({navigation}) {
  return (
    <View style={styles.container}>
      <Image style={styles.gifSize} source={{uri:home_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, fontWeight: 'bold'}}>Welcome to BOOZE.PH!</Text>
      <Text style={{color:"#fff", fontSize: 15, marginBottom: 50}}>Premium Liquor Delivery 24/7</Text>
      <Image style={styles.imageSize} source={{uri:price_tag}} />
      <Text style={{color:"#c70404", fontSize: 15}}>Affordable</Text>
      <Text style={{color:"#fff", fontSize: 12, marginBottom: 10}}>Low prices for a wide range of liquor all within few clicks</Text>
      <Image style={styles.imageSize1} source={{uri:del_icon}} />
      <Text style={{color:"#c70404", fontSize: 15}}>Fast Delivery</Text>
      <Text style={{color:"#fff", fontSize: 12, marginBottom: 10}}>60-90 min delivery to Metro Manila + Nationwide shipping</Text>
      <Image style={styles.imageSize1} source={{uri:card_icon}} />
      <Text style={{color:"#c70404", fontSize: 15}}>Easy Payment</Text>
      <Text style={{color:"#fff", fontSize: 12, marginBottom: 10}}>We accept COD, Credit/Debit Card, GCash, PayMaya</Text>
      <Text style={{color:"#fff", fontSize: 12, padding: 10}}>-Drink Responsibly-</Text>
      <StatusBar style="auto" />
    </View>
  );
}

function BundleScreen({navigation}){
  return (
    <ScrollView>
      <View style={styles.container}>

      <Image style={styles.gifSize1} source={{uri:b_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>BUNDLE PROMO</Text>

      <Image style={styles.productImage} source={{uri:b2}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Ultimate Shots Pack</Text>
      <Text style={{color:"#fff", fontSize: 12}}>2 x Jagermeister 700ml</Text>
      <Text style={{color:"#fff", fontSize: 12}}>2 x Jose Cuervo Gold 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 3,699.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:b1}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Triple J Special</Text>
      <Text style={{color:"#fff", fontSize: 12}}>1 x Jack Daniels 1L</Text>
      <Text style={{color:"#fff", fontSize: 12}}>1 x Johnnie Walker Black Label 1L</Text>
      <Text style={{color:"#fff", fontSize: 12}}>1 x Jose Cuervo Gold 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 3,999.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 
      
      <Image style={styles.productImage} source={{uri:b3}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Deluxe Bundle</Text>
      <Text style={{color:"#fff", fontSize: 12}}>2 x Johnnie Walker Double Black Label 1L</Text>
      <Text style={{color:"#fff", fontSize: 12}}>1 x Johnnie Walker Green Label 700ml</Text>
      <Text style={{color:"#fff", fontSize: 12}}>1 x Johnnie Walker Gold Label 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 6,499.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

        {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
      </View>
      </ScrollView>
  )
}

function WhiskeyScreen({navigation}) {
  return (
    <ScrollView>
    <View style={styles.container}>
      <Image style={styles.gifSize1} source={{uri:w_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>WHISKEY</Text>

      <Image style={styles.productImage} source={{uri:w1}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jim Beam White 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 549.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w2}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Red Label 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 599.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w3}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Red Label 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 799.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w4}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Black Label 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,099.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w5}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jack Daniel's Old No.7 Tennessee Whiskey 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,099.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w6}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jack Daniel's Tennessee Honey 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,099.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w7}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Black Label 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,199.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:w8}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Chivas Regal 12yo 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,199.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w9}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jameson Irish Whiskey 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,399.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w10}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jack Daniel's Old No.7 Tennessee Whiskey 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,649.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w11}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Double Black 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,649.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w12}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Chivas Regal 12yo 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,649.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>


      <Image style={styles.productImage} source={{uri:w13}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Gold Reserve 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,699.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w14}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Double Black 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,899.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w15}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Chivas Regal 18yo 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 2,949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w16}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Dalmore 12yo 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 4,299.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w17}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Dalmore 15yo 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 6,599.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:w18}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Johnnie Walker Blue Label 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 7,999.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>


    </View>
    </ScrollView>
  );
}

function TequilaScreen({navigation}){
  return (
    <ScrollView>
      <View style={styles.container}>

      <Image style={styles.gifSize1} source={{uri:t_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>TEQUILA</Text>

      <Image style={styles.productImage} source={{uri:t1}} />
      <Text style={{color:"#c70404", fontSize: 20}}>El Hombre White Tequila 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 249.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:t2}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Mojitos Silver 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 249.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:t3}} />
      <Text style={{color:"#c70404", fontSize: 20}}>El Hombre Gold Tequila 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 349.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:t4}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Mojitos Gold 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 349.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:t5}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jose Cuervo 375ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 699.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:t6}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jose Cuervo Silver 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 849.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:t7}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jose Cuervo Gold 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 849.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:t7}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Jose Cuervo Gold 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,099.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:t8}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Patron Reposado 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 3,199.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>

      <Image style={styles.productImage} source={{uri:t9}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Patron Añejo 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 3,449.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable>


        {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
      </View>
      </ScrollView>
  )
}

function VodkaScreen({navigation}){
  return (
    <ScrollView>
      <View style={styles.container}>

      <Image style={styles.gifSize1} source={{uri:v_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>VODKA</Text>

      <Image style={styles.productImage} source={{uri:v1}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Smirnoff Red 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 599.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v2}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Blue 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 749.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v3}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Blue 1L</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 899.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v4}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Ruby Red 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 899.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v5}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Apeach 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v6}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Citron 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v7}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Kurant 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v8}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Absolut Mandrin 700ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v9}} />
      <Text style={{color:"#c70404", fontSize: 20}}>42 Below Vodka 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 999.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:v10}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Grey Goose Vodka 750ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,949.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

        {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
      </View>
      </ScrollView>
  )
}

function BeerScreen({navigation}){
  return (
    <ScrollView>
      <View style={styles.container}>

      <Image style={styles.gifSize1} source={{uri:be_gif}} />
      <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>BEER</Text>

      <Image style={styles.productImage} source={{uri:be1}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Smirnoff Mule 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 49.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be2}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Brew Kettle Beer 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 69.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be3}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Heineken 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 79.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be4}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Budweiser 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 79.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be5}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Sapporo 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 99.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be6}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Corona 330ml</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 119.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be7}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Tiger Black 500ml Bundle of 4 Cans</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 279.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be8}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Heineken 330ml Bundle of 4 Cans</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 319.00</Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be9}} />
      <Text style={{color:"#c70404", fontSize: 20}}>San Mig Light 330 mL Can Case of 24</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,349.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be10}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Red Horse Beer 330 mL Can Case of 24</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,349.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be11}} />
      <Text style={{color:"#c70404", fontSize: 20}}>San Miguel Pale Pilsen 330 mL Can Case of 24</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,349.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be12}} />
      <Text style={{color:"#c70404", fontSize: 20}}>San Miguel Flavored Beer Apple 330 mL Can Case of 24</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,349.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be13}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Heineken 5L DraughtKeg</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 1,399.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 

      <Image style={styles.productImage} source={{uri:be14}} />
      <Text style={{color:"#c70404", fontSize: 20}}>Heineken 500ml Can Case of 24</Text>
      <Text style={{color:"#fff", fontSize: 20, padding: 10}}>Php 2,599.00 </Text>
      <Pressable onPress={addToCart} style={styles.customButton}>
        <Text style={{color:"#fff", fontSize: 15}}>Add to cart</Text>
      </Pressable> 



        {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
      </View>
      </ScrollView>
  )
}

function CartScreen({navigation}){
    return (
    <ScrollView>
    <View style={styles.container}>

    <Image style={styles.gifSize} source={{uri:home_gif}} />
    <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>YOUR CART</Text>



    <Text style={{color:"#fff", fontSize: 25, }}>Delivery Address</Text>
    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 15, }}>House No. and Street Name*</Text>
    </View>
    <TextInput maxLength={20} style={styles.inputDesignAdd} />
    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 15, }}>Barangay or Village*</Text>
    </View>
    <TextInput maxLength={20} style={styles.inputDesignAdd} />
    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 15, }}>City or Municipality*</Text>
    </View>
    <TextInput maxLength={20} style={styles.inputDesignAdd} />
    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 15, }}>Province*</Text>
    </View>
    <TextInput maxLength={20} style={styles.inputDesignAdd} />
    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 15, }}>(Optional) Nearest Landmark</Text>
    </View>
    <TextInput maxLength={20} style={styles.inputDesignAdd} />
    <Text style={{color:"#fff", fontSize: 10, }}>*Required</Text>


    <View style={{borderWidth: 20, alignSelf: 'baseline'}}>
    <Text style={{color:"#fff", fontSize: 20, }}>Order Notes:</Text>
    </View>
    <TextInput multiline numberOfLines={3} maxLength={80} style={styles.inputDesign} />

    <Pressable onPress={placeOrder} style={styles.customButton}>
      <Text style={{color:"#fff", fontSize: 15}}>PLACE ORDER</Text>
    </Pressable> 

      {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
    </View>
    </ScrollView>
  )
}

// function DetailsScreen({}){
//   return (
//   <ScrollView>
//   <View style={styles.container}>

//   <Image style={styles.gifSize} source={{uri:home_gif}} />
//   <Text style={{color:"#c70404", fontSize: 30, padding: 30}}>YOUR CART</Text>

//     {/* <Button onPress={() => navigation.goBack()} title="Go back home" /> */}
//   </View>
//   </ScrollView>
// )
// }

const Drawer = createDrawerNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Drawer.Navigator initialRouteName="Home">
        <Drawer.Screen name="Home" component={HomeScreen} />
        <Drawer.Screen name="Bundles" component={BundleScreen} />
        <Drawer.Screen name="Whiskey" component={WhiskeyScreen} />
        <Drawer.Screen name="Tequila" component={TequilaScreen} />
        <Drawer.Screen name="Vodka" component={VodkaScreen} />
        <Drawer.Screen name="Beer" component={BeerScreen} />
        <Drawer.Screen name="Cart" component={CartScreen} />
      </Drawer.Navigator>

      </NavigationContainer>
  )
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#000000',
    alignItems: 'center',
    justifyContent: 'center',
  },

  gifSize: {
    width: 170,
    height: 170,

  },
  gifSize1: {
    width: "100%",
    height: 165,

  },

  imageSize: {
    width: 30,
    height: 30,

  },
  imageSize1: {
    width: 60,
    height: 60,

  },
  productImage: {
    width: 200,
    height: 200,
  },

  customButton: {
    width: 120,
    height:30,
    backgroundColor: "#c70404",
    padding: 5,
    alignItems: "center",
    marginBottom: 25
  },

  inputDesign: {
    width:"60%",
    height: 80,
    padding:5,
    backgroundColor: '#fff',
    marginBottom:10

  },
  inputDesignAdd: {
    width:"80%",
    height: 40,
    padding:5,
    backgroundColor: '#fff',
    marginBottom:10

  },
});
