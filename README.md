# VolleyNoApache
Simple Android Application using Google's Volley without Apache library.

```
		if (Build.VERSION.SDK_INT < 9) {
            Log.w(LOG_TAG, "Build.VERSION.SDK_INT < 9 not supported.");
            return;
        }

        // GET REQUEST
        String url = "http://192.16.1.100:24780/testget";
        RequestQueue requestQueue = Volley.newRequestQueue(this);

        JsonArrayRequest jsonArrayRequest = new JsonArrayRequest(url, new Response.Listener<JSONArray>() {
            @Override
            public void onResponse(JSONArray response) {
                Log.i(LOG_TAG, response.toString());
            }
        }, new Response.ErrorListener() {
            @Override
            public void onErrorResponse(VolleyError error) {
                Log.e(LOG_TAG, error.toString());
            }
        });

        if (requestQueue != null) {
            requestQueue.add(jsonArrayRequest);
        }

        // POST REQUEST
//        RequestQueue requestQueue = Volley.newRequestQueue(this);
//        String url = "http://192.16.1.100:24780/testpost";
//        JSONObject requestBody = new JSONObject();
//        try {
//            requestBody.put("key1", "value01");
//            requestBody.put("key2", "value02");
//        } catch (JSONException e) {
//            e.printStackTrace();
//        }
//
//        JsonObjectRequest jsonObjectRequest = new JsonObjectRequest(Request.Method.POST, url, requestBody, new Response.Listener<JSONObject>() {
//            @Override
//            public void onResponse(JSONObject response) {
//                Log.i(LOG_TAG, response.toString());
//            }
//        }, new Response.ErrorListener() {
//            @Override
//            public void onErrorResponse(VolleyError error) {
//                Log.e(LOG_TAG, error.toString());
//            }
//        });
//
//        if (requestQueue != null){
//            requestQueue.add(jsonObjectRequest);
//        }

	     // MULTIPART REQUEST
//        startActivity(new Intent(this, MultipartActivity.class));
```

build.gradle file:

```
apply plugin: 'com.android.application'

android {
    compileSdkVersion 23
    buildToolsVersion "23.0.2"

    defaultConfig {
        applicationId "com.example.volleynoapache"
        minSdkVersion 16
        targetSdkVersion 23
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}

dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    testCompile 'junit:junit:4.12'
    compile 'com.android.support:appcompat-v7:23.1.1'
}
```
