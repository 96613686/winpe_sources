# JsonHelper::GetJsonStringAsByteArray(uchar * *,ulong *)

- ea: `0x180012e70`
- end: `0x180013011`
- name: `?GetJsonStringAsByteArray@JsonHelper@@UEAAJPEAPEAEPEAK@Z`
- size: `417`
- prototype: `int(JsonHelper *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012330`
- `0x180012e70`
- `0x180013880`
- `0x180014898`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012fe5`

## string_xrefs

- `0x180012eea`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x180012f5d`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonStringAsByteArray(JsonHelper *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  __int64 v12; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[2]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 length; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v17[0] = 0;
  string = 0;
  length = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         v17);
  if ( v6 >= 0 )
  {
    v10 = v17[0];
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17[0] + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v6 = v11(v10, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v6 = JsonHelper::WideCharToUTF8AsByteArray(v14, StringRawBuffer, length, a2, a3);
      if ( v6 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15);
        v8 = 29;
        v9 = "WideCharToUTF8AsByteArray  failed!";
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
      v8 = 28;
      v9 = "spJsonValue->Stringify  failed!";
      goto LABEL_16;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5);
    v8 = 27;
    v9 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_16:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v9,
      v6);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012e70  mov     [rsp-18h+arg_8], rbx
0x180012e75  mov     [rsp-18h+arg_10], rsi
0x180012e7a  push    rbp
0x180012e7b  push    rdi
0x180012e7c  push    r14
0x180012e7e  mov     rbp, rsp
0x180012e81  sub     rsp, 40h
0x180012e85  mov     r14, rdx
0x180012e88  mov     [rbp+var_10], 0
0x180012e90  lea     rdx, [rbp+var_10]
0x180012e94  mov     [rbp+string], 0
0x180012e9c  add     rcx, 38h ; '8'
0x180012ea0  mov     [rbp+length], 0
0x180012ea7  mov     rsi, r8
0x180012eaa  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180012eaf  mov     ebx, eax
0x180012eb1  test    eax, eax
0x180012eb3  jns     short loc_180012EF6
0x180012eb5  mov     rax, cs:WPP_GLOBAL_Control
0x180012ebc  lea     rcx, WPP_GLOBAL_Control
0x180012ec3  cmp     rax, rcx
0x180012ec6  jz      loc_180012FE1
0x180012ecc  test    byte ptr [rax+1Ch], 8
0x180012ed0  jz      loc_180012FE1
0x180012ed6  cmp     byte ptr [rax+19h], 2
0x180012eda  jb      loc_180012FE1
0x180012ee0  call    RdpX_GetActivityIdPrefix
0x180012ee5  mov     edx, 1Bh
0x180012eea  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x180012ef1  jmp     loc_180012FBE
0x180012ef6  mov     rdi, [rbp+var_10]
0x180012efa  mov     rcx, [rbp+string]; string
0x180012efe  mov     rax, [rdi]
0x180012f01  mov     rbx, [rax+38h]
0x180012f05  call    cs:__imp_WindowsDeleteString
0x180012f0b  lea     rdx, [rbp+string]
0x180012f0f  mov     [rbp+string], 0
0x180012f17  mov     rcx, rdi
0x180012f1a  mov     rax, rbx
0x180012f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f22  mov     ebx, eax
0x180012f24  test    eax, eax
0x180012f26  jns     short loc_180012F66
0x180012f28  mov     rax, cs:WPP_GLOBAL_Control
0x180012f2f  lea     rcx, WPP_GLOBAL_Control
0x180012f36  cmp     rax, rcx
0x180012f39  jz      loc_180012FE1
0x180012f3f  test    byte ptr [rax+1Ch], 8
0x180012f43  jz      loc_180012FE1
0x180012f49  cmp     byte ptr [rax+19h], 2
0x180012f4d  jb      loc_180012FE1
0x180012f53  call    RdpX_GetActivityIdPrefix
0x180012f58  mov     edx, 1Ch
0x180012f5d  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x180012f64  jmp     short loc_180012FBE
0x180012f66  mov     rcx, [rbp+string]; string
0x180012f6a  lea     rdx, [rbp+length]; length
0x180012f6e  call    cs:__imp_WindowsGetStringRawBuffer
0x180012f74  mov     r8d, [rbp+length]; int
0x180012f78  mov     r9, r14; unsigned __int8 **
0x180012f7b  mov     rdx, rax; unsigned __int16 *
0x180012f7e  mov     [rsp+40h+var_20], rsi; unsigned int *
0x180012f83  call    ?WideCharToUTF8AsByteArray@JsonHelper@@AEAAJPEBGHPEAPEAEPEAK@Z; JsonHelper::WideCharToUTF8AsByteArray(ushort const *,int,uchar * *,ulong *)
0x180012f88  mov     ebx, eax
0x180012f8a  test    eax, eax
0x180012f8c  jns     short loc_180012FE1
0x180012f8e  mov     rax, cs:WPP_GLOBAL_Control
0x180012f95  lea     rcx, WPP_GLOBAL_Control
0x180012f9c  cmp     rax, rcx
0x180012f9f  jz      short loc_180012FE1
0x180012fa1  test    byte ptr [rax+1Ch], 8
0x180012fa5  jz      short loc_180012FE1
0x180012fa7  cmp     byte ptr [rax+19h], 2
0x180012fab  jb      short loc_180012FE1
0x180012fad  call    RdpX_GetActivityIdPrefix
0x180012fb2  mov     edx, 1Dh
0x180012fb7  lea     rcx, aWidechartoutf8; "WideCharToUTF8AsByteArray  failed!"
0x180012fbe  mov     [rsp+40h+var_18], ebx
0x180012fc2  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012fc9  mov     [rsp+40h+var_20], rcx
0x180012fce  mov     r9d, eax
0x180012fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fd8  mov     rcx, [rcx+10h]
0x180012fdc  call    WPP_SF_DsD
0x180012fe1  mov     rcx, [rbp+string]; string
0x180012fe5  call    cs:__imp_WindowsDeleteString
0x180012feb  lea     rcx, [rbp+var_10]
0x180012fef  mov     [rbp+string], 0
0x180012ff7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180012ffc  mov     rsi, [rsp+40h+arg_10]
0x180013001  mov     eax, ebx
0x180013003  mov     rbx, [rsp+40h+arg_8]
0x180013008  add     rsp, 40h
0x18001300c  pop     r14
0x18001300e  pop     rdi
0x18001300f  pop     rbp
0x180013010  retn
```
