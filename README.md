# Mapas
MapBox
1. Adicionando dependências e configurações no projeto:
 Adicione a dependência do MapBox ao seu arquivo “build.gradle” :

implementation 'com.mapbox.mapboxsdk:mapbox-android-sdk:10.3.1'

No arquivo “AndroidManifest.xml”, adicione as permissões necessárias para
acesso ao GPS:

<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>

2. Obtendo a localização pelo GPS:
Para acessar a localização pelo GPS, você pode usar a classe “LocationManager” ou as
APIs de localização do Google Play Services.
3. Simulando a localização no emulador:
No Android Studio, você pode simular a localização do dispositivo usando o &quot;Simulador
de Localização&quot; na barra de ferramentas.
4. Adicionando uma marcação no mapa:

// Obtendo a referência do mapa
val mapView = findViewById<MapView>(R.id.mapView)
mapView.getMapAsync { mapboxMap ->
    // Adicionando marcador na localização atual
    val markerOptions = MarkerOptions()
        .position(LatLng(latitude, longitude))
        .title("Minha Localização")
    mapboxMap.addMarker(markerOptions)
}





Google Maps API
1. Adicionando dependências e configurações no projeto:
 Adicione a dependência da Google Maps API no seu arquivo “build.gradle”:

implementation 'com.google.android.gms:play-services-maps:18.0.0'


No arquivo “AndroidManifest.xml”, adicione a chave da API e as permissões de
localização:

<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.INTERNET"/>

<meta-data
android:name="com.google.android.geo.API_KEY"
android:value="SUA_CHAVE_DA_API_GOOGLE_MAPS"/>

2. Obtendo a localização pelo GPS:
Você pode usar as classes “FusedLocationProviderClient” ou “LocationManager” para
obter a localização atual do dispositivo.
3. Simulando a localização no emulador:
Acesse as configurações do emulador, vá para &quot;Emulated Device&quot; e insira as
coordenadas de latitude e longitude para simular a localização.
4. Adicionando uma marcação no mapa:

// Obtendo a referência do mapa
val mapFragment = supportFragmentManager.findFragmentById(R.id.map) as SupportMapFragment
mapFragment.getMapAsync { googleMap ->
    // Adicionando marcador na localização atual
    val markerOptions = MarkerOptions()
        .position(LatLng(latitude, longitude))
        title("Minha Localização")
    googleMap.addMarker(markerOptions)
}




