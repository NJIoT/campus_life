# campus_life

Nanjing Institute of Technology Campus Assistance App

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our 
[online documentation](https://flutter.dev/docs), which offers tutorials, 
samples, guidance on mobile development, and a full API reference.

```java
public interface APIService {

    @Headers({
            "Referer: https://jwjx.njit.casbs.cn/default2.aspx",
            "Host: jwjx.njit.casbs.cn",
            "Content-Type: application/x-www-form-urlencoded",
            "charset: UTF-8"
    })
    @FormUrlEncoded
    @POST("default2.aspx")
    Observable<Response<ResponseBody>> postLogin(
            @Header("Cookie") String cookie,
            @Field("__VIEWSTATE") String viewState,
            @Field("txtUserName") String user,
            @Field("TextBox2") String password,
            @Field("txtSecretCode") String code,
            @Field("RadioButtonList1") String studORTheacher,
            @Field("Button1") String button1,
            @Field("lbLanguage") String lbLanguage
    );

    @GET("xskbcx.aspx")
    Observable<Response<ResponseBody>> getCourseSchedule(
            @Header("Cookie") String cookie,
            @Field("__EVENTTARGET") String eventTarget,
            @Field("__EVENTARGUMENT") String eventArgument,
            @Field("__VIEWSTATE") String viewState,
            @Query("xh") String xh,
            @Query("xm") String name,
            @Query("gnmkdm") String gnmkdm
    );

    @GET("CheckCode.aspx")
    Observable<Response<ResponseBody>> getCodeImage();

    @GET("{path}")
    Observable<Response<ResponseBody>> getLoginViewState(@Path("path") String path);

    @GET("xscjcx_dq.aspx")
    Observable<Response<ResponseBody>> getGrade(
            @Header("Cookie") String cookie,
            @Query("xh") String xh,
            @Query("xm") String xm,
            @Query("gnmkdm") String gnmkdm
    );

    @FormUrlEncoded
    @POST("xscjcx_dq.aspx")
    Observable<Response<ResponseBody>> postGrade(
            @Header("Cookie") String cookie,
            @Field("__EVENTTARGET") String eventTarget,
            @Field("__EVENTARGUMENT") String eventArgument,
            @Field("__VIEWSTATE") String viewState,
            @Field("ddlxn") String ddlxn,
            @Field("ddlxq") String ddlxq,
            @Query("xh") String xh,
            @Query("xm") String xm,
            @Query("gnmkdm") String gnmkdm
    );

    // Referer 必要：如不填写则返回 302 重定向
    @Headers({
            "Referer: https://jwjx.njit.casbs.cn/xs_main.aspx?xh={xh}",
            "Host: jwjx.njit.casbs.cn",
            "Content-Type: application/x-www-form-urlencoded",
            "charset: UTF-8"
    })
    @GET("xsgrxx.aspx")
    Observable<Response<ResponseBody>> getPersonalInfo(
            @Header("Cookie") String cookie,
            @Query("xh") String xh,
            @Query("xm") String xm,
            @Query("gnmkdm") String gnmkdm
    );

}
```
