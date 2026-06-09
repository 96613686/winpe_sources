# JsonHelper::GetJsonString(ushort * *)

- ea: `0x180012c20`
- end: `0x180012e63`
- name: `?GetJsonString@JsonHelper@@UEAAJPEAPEAG@Z`
- size: `579`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006734`
- `0x180007a64`
- `0x18000e2e8`
- `0x180012330`
- `0x180012c20`
- `0x180013880`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012e3d`

## string_xrefs

- `0x180012dfd`: `StringCchCopy failed!`
- `0x180012c91`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x180012d27`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonString(JsonHelper *this, unsigned __int16 **a2)
{
  int v3; // ebx
  int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // eax
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+68h] [rbp+38h] BYREF

  v17 = 0;
  string = 0;
  length = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         &v17);
  if ( v3 >= 0 )
  {
    v7 = v17;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v3 = v8(v7, &string);
    if ( v3 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v10 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v11 = v10;
      if ( v10 )
      {
        v3 = StringCchCopyW(v10, length, StringRawBuffer);
        if ( v3 >= 0 )
        {
          *a2 = v11;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v3);
          }
          operator delete(v11);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpX_GetActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v12,
            (__int64)"WCHAR[]");
        }
        v3 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpX_GetActivityIdPrefix();
      v5 = 24;
      v6 = "spJsonValue->Stringify  failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpX_GetActivityIdPrefix();
    v5 = 23;
    v6 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v4,
      (__int64)v6,
      v3);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012c20  mov     [rsp-18h+arg_8], rbx
0x180012c25  push    rbp
0x180012c26  push    rsi
0x180012c27  push    rdi
0x180012c28  mov     rbp, rsp
0x180012c2b  sub     rsp, 30h
0x180012c2f  mov     rsi, rdx
0x180012c32  mov     [rbp+arg_18], 0
0x180012c3a  lea     rdx, [rbp+arg_18]
0x180012c3e  mov     [rbp+string], 0
0x180012c46  add     rcx, 38h ; '8'
0x180012c4a  mov     [rbp+length], 0
0x180012c51  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180012c56  mov     ebx, eax
0x180012c58  test    eax, eax
0x180012c5a  jns     short loc_180012CC0
0x180012c5c  mov     rax, cs:WPP_GLOBAL_Control
0x180012c63  lea     rcx, WPP_GLOBAL_Control
0x180012c6a  cmp     rax, rcx
0x180012c6d  jz      loc_180012E39
0x180012c73  test    byte ptr [rax+1Ch], 8
0x180012c77  jz      loc_180012E39
0x180012c7d  cmp     byte ptr [rax+19h], 2
0x180012c81  jb      loc_180012E39
0x180012c87  call    RdpX_GetActivityIdPrefix
0x180012c8c  mov     edx, 17h
0x180012c91  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x180012c98  mov     [rsp+30h+var_8], ebx
0x180012c9c  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012ca3  mov     [rsp+30h+var_10], rcx
0x180012ca8  mov     r9d, eax
0x180012cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cb2  mov     rcx, [rcx+10h]
0x180012cb6  call    WPP_SF_DsD
0x180012cbb  jmp     loc_180012E39
0x180012cc0  mov     rdi, [rbp+arg_18]
0x180012cc4  mov     rcx, [rbp+string]; string
0x180012cc8  mov     rax, [rdi]
0x180012ccb  mov     rbx, [rax+38h]
0x180012ccf  call    cs:__imp_WindowsDeleteString
0x180012cd5  lea     rdx, [rbp+string]
0x180012cd9  mov     [rbp+string], 0
0x180012ce1  mov     rcx, rdi
0x180012ce4  mov     rax, rbx
0x180012ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cec  mov     ebx, eax
0x180012cee  test    eax, eax
0x180012cf0  jns     short loc_180012D33
0x180012cf2  mov     rax, cs:WPP_GLOBAL_Control
0x180012cf9  lea     rcx, WPP_GLOBAL_Control
0x180012d00  cmp     rax, rcx
0x180012d03  jz      loc_180012E39
0x180012d09  test    byte ptr [rax+1Ch], 8
0x180012d0d  jz      loc_180012E39
0x180012d13  cmp     byte ptr [rax+19h], 2
0x180012d17  jb      loc_180012E39
0x180012d1d  call    RdpX_GetActivityIdPrefix
0x180012d22  mov     edx, 18h
0x180012d27  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x180012d2e  jmp     loc_180012C98
0x180012d33  mov     rcx, [rbp+string]; string
0x180012d37  lea     rdx, [rbp+length]; length
0x180012d3b  call    cs:__imp_WindowsGetStringRawBuffer
0x180012d41  mov     ecx, [rbp+length]
0x180012d44  mov     rbx, rax
0x180012d47  inc     ecx
0x180012d49  mov     eax, 2
0x180012d4e  mov     edx, ecx
0x180012d50  mov     [rbp+length], ecx
0x180012d53  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012d5a  mul     rdx
0x180012d5d  cmovb   rax, rcx
0x180012d61  mov     rcx, rax; Size
0x180012d64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012d69  mov     rdi, rax
0x180012d6c  test    rax, rax
0x180012d6f  jnz     short loc_180012DC5
0x180012d71  mov     rax, cs:WPP_GLOBAL_Control
0x180012d78  lea     rcx, WPP_GLOBAL_Control
0x180012d7f  cmp     rax, rcx
0x180012d82  jz      short loc_180012DBE
0x180012d84  test    byte ptr [rax+1Ch], 8
0x180012d88  jz      short loc_180012DBE
0x180012d8a  cmp     byte ptr [rax+19h], 2
0x180012d8e  jb      short loc_180012DBE
0x180012d90  call    RdpX_GetActivityIdPrefix
0x180012d95  lea     rcx, aWchar; "WCHAR[]"
0x180012d9c  mov     r9d, eax
0x180012d9f  mov     [rsp+30h+var_10], rcx
0x180012da4  lea     edx, [rdi+19h]
0x180012da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dae  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012db5  mov     rcx, [rcx+10h]
0x180012db9  call    WPP_SF_Ds
0x180012dbe  mov     ebx, 8007000Eh
0x180012dc3  jmp     short loc_180012E39
0x180012dc5  mov     edx, [rbp+length]; unsigned __int64
0x180012dc8  mov     r8, rbx; unsigned __int16 *
0x180012dcb  mov     rcx, rdi; unsigned __int16 *
0x180012dce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012dd3  mov     ebx, eax
0x180012dd5  test    eax, eax
0x180012dd7  jns     short loc_180012E36
0x180012dd9  mov     rax, cs:WPP_GLOBAL_Control
0x180012de0  lea     rcx, WPP_GLOBAL_Control
0x180012de7  cmp     rax, rcx
0x180012dea  jz      short loc_180012E2C
0x180012dec  test    byte ptr [rax+1Ch], 8
0x180012df0  jz      short loc_180012E2C
0x180012df2  cmp     byte ptr [rax+19h], 2
0x180012df6  jb      short loc_180012E2C
0x180012df8  call    RdpX_GetActivityIdPrefix
0x180012dfd  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x180012e04  mov     [rsp+30h+var_8], ebx
0x180012e08  mov     [rsp+30h+var_10], rcx
0x180012e0d  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012e14  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e1b  mov     edx, 1Ah
0x180012e20  mov     r9d, eax
0x180012e23  mov     rcx, [rcx+10h]
0x180012e27  call    WPP_SF_DsD
0x180012e2c  mov     rcx, rdi; Block
0x180012e2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012e34  jmp     short loc_180012E39
0x180012e36  mov     [rsi], rdi
0x180012e39  mov     rcx, [rbp+string]; string
0x180012e3d  call    cs:__imp_WindowsDeleteString
0x180012e43  lea     rcx, [rbp+arg_18]
0x180012e47  mov     [rbp+string], 0
0x180012e4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180012e54  mov     eax, ebx
0x180012e56  mov     rbx, [rsp+30h+arg_8]
0x180012e5b  add     rsp, 30h
0x180012e5f  pop     rdi
0x180012e60  pop     rsi
0x180012e61  pop     rbp
0x180012e62  retn
```
