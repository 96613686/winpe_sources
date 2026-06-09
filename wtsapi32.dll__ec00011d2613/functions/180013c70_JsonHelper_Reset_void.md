# JsonHelper::Reset(void)

- ea: `0x180013c70`
- end: `0x180013d28`
- name: `?Reset@JsonHelper@@UEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012290`
- `0x180012640`
- `0x180013c70`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`

## string_xrefs

- `0x180013ce4`: `ActivateInstance: JsonObject`
- `0x180013c98`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall JsonHelper::Reset(JsonHelper *this)
{
  char *v1; // rbx
  __int64 v2; // rdx
  int v3; // ebx
  int ActivityIdPrefix; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+48h] [rbp-20h]

  v7 = 0;
  v1 = (char *)this + 56;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v7, v1);
  if ( v3 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v2);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)"ActivateInstance: JsonObject",
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013c70  push    rbx
0x180013c72  sub     rsp, 60h
0x180013c76  mov     rax, cs:__security_cookie
0x180013c7d  xor     rax, rsp
0x180013c80  mov     [rsp+68h+var_18], rax
0x180013c85  mov     r9d, 1Ch; unsigned int
0x180013c8b  mov     [rsp+68h+var_20], 0
0x180013c94  lea     rbx, [rcx+38h]
0x180013c98  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180013c9f  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180013ca4  lea     r8d, [r9+1]; unsigned int
0x180013ca8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013cad  mov     rcx, [rsp+68h+var_20]
0x180013cb2  mov     rdx, rbx
0x180013cb5  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180013cba  mov     ebx, eax
0x180013cbc  test    eax, eax
0x180013cbe  jns     short loc_180013D13
0x180013cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cc7  lea     rax, WPP_GLOBAL_Control
0x180013cce  cmp     rcx, rax
0x180013cd1  jz      short loc_180013D13
0x180013cd3  test    byte ptr [rcx+1Ch], 8
0x180013cd7  jz      short loc_180013D13
0x180013cd9  cmp     byte ptr [rcx+19h], 2
0x180013cdd  jb      short loc_180013D13
0x180013cdf  call    RdpX_GetActivityIdPrefix
0x180013ce4  lea     rcx, aActivateinstan; "ActivateInstance: JsonObject"
0x180013ceb  mov     [rsp+68h+var_40], ebx
0x180013cef  mov     [rsp+68h+var_48], rcx
0x180013cf4  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d02  mov     edx, 16h
0x180013d07  mov     r9d, eax
0x180013d0a  mov     rcx, [rcx+10h]
0x180013d0e  call    WPP_SF_DsD
0x180013d13  mov     eax, ebx
0x180013d15  mov     rcx, [rsp+68h+var_18]
0x180013d1a  xor     rcx, rsp; StackCookie
0x180013d1d  call    __security_check_cookie
0x180013d22  add     rsp, 60h
0x180013d26  pop     rbx
0x180013d27  retn
```
