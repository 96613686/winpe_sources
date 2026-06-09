# WuTrace::RetryAttemptsData::ToJsonBlob(wchar_t * *)

- ea: `0x18011f77c`
- end: `0x18011fac7`
- name: `?ToJsonBlob@RetryAttemptsData@WuTrace@@QEBAJPEAPEA_W@Z`
- size: `843`
- prototype: `__int64 __fastcall(WuTrace::RetryAttemptsData *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801e64d0`
- `0x1801e6764`

## callees

- `0x18000def4`
- `0x18007b8a4`
- `0x180110914`
- `0x18011d098`
- `0x18011f77c`
- `0x180120124`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011f7dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011f836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011f7dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011f836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f9ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011f9ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011f9b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011f9b7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011f870`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011f870`

## string_xrefs

- `0x18011f7d5`: `Windows.Data.Json.JsonArray`
- `0x18011f82f`: `Windows.Data.Json.JsonValue`
- `0x18011f804`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011f883`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011f91c`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011f9da`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x18011fa7c`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall WuTrace::RetryAttemptsData::ToJsonBlob(WuTrace::RetryAttemptsData *this, wchar_t **a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // eax
  int i; // ebx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HSTRING v12; // rbx
  __int64 v13; // rcx
  int ActivationFactory; // eax
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD); // rcx
  int v30; // eax
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // [rsp+20h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v35; // [rsp+48h] [rbp-38h] BYREF
  __int64 v36; // [rsp+50h] [rbp-30h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-28h] BYREF
  __int64 v38; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, _QWORD); // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( *(_QWORD *)this && *(_DWORD *)(*(_QWORD *)this + 24LL) )
  {
    v39 = 0;
    string = 0;
    v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
    if ( v4 >= 0 )
    {
      v7 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>(
             string,
             &v39);
      i = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
          (const char *)(unsigned int)v7,
          (int)v32);
LABEL_39:
        v29 = v39;
        if ( v39 )
        {
          v39 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v29)[2])(v29);
        }
        return (unsigned int)i;
      }
      v38 = 0;
      string = 0;
      v9 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v9 >= 0 )
      {
        v12 = string;
        v13 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        ActivationFactory = RoGetActivationFactory(v12, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v38);
        i = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF0,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
            (const char *)(unsigned int)ActivationFactory,
            (int)v32);
LABEL_37:
          v28 = v38;
          if ( v38 )
          {
            v38 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          goto LABEL_39;
        }
        v36 = 0;
        v37 = 0;
        v15 = (**v39)(v39, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v37);
        i = v15;
        if ( v15 < 0 )
        {
          v16 = (unsigned int)v15;
          v17 = 244;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
            (const char *)v16,
            (int)v32);
LABEL_33:
          v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
          if ( v37 )
          {
            v37 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
          }
          v27 = v36;
          if ( v36 )
          {
            v36 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          goto LABEL_37;
        }
        v18 = *(_QWORD *)this;
        if ( v18 )
        {
          for ( i = 0; i >= 0; i = anonymous_namespace_::AppendRetryAttemptDataToJsonVector(v18, &v32) )
          {
            v18 = *(_QWORD *)(v18 + 8);
            if ( !v18 )
              break;
            v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
            if ( v37 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v37)[1])(v37);
          }
          if ( i < 0 )
          {
            v16 = (unsigned int)i;
            v17 = 252;
            goto LABEL_21;
          }
        }
        v35 = 0;
        v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
        v20 = **v37;
        v21 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        i = v20(v19, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v36);
        if ( i >= 0 )
        {
          v23 = v36;
          v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 56LL);
          WindowsDeleteString(v35);
          v35 = 0;
          i = v24(v23, &v35);
          if ( i >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
            i = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a2);
            if ( i >= 0 )
            {
              i = 0;
              goto LABEL_32;
            }
            v22 = 260;
          }
          else
          {
            v22 = 259;
          }
        }
        else
        {
          v22 = 258;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
          (const char *)(unsigned int)i,
          (int)v32);
LABEL_32:
        WindowsDeleteString(v35);
        v35 = 0;
        goto LABEL_33;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18011FAC6LL);
  }
  v30 = DuplicateString<wchar_t const *,wchar_t *>(&OutputString, a2);
  i = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v30,
      (int)v32);
    return (unsigned int)i;
  }
  return 0;
}

```

## disassembly

```asm
0x18011f77c  mov     [rsp-18h+arg_10], rbx
0x18011f781  mov     [rsp-18h+arg_18], rsi
0x18011f786  push    rbp
0x18011f787  push    rdi
0x18011f788  push    r14
0x18011f78a  mov     rbp, rsp
0x18011f78d  sub     rsp, 80h
0x18011f794  mov     rax, cs:__security_cookie
0x18011f79b  xor     rax, rsp
0x18011f79e  mov     [rbp+var_8], rax
0x18011f7a2  mov     rsi, rdx
0x18011f7a5  mov     rdi, rcx
0x18011f7a8  mov     rax, [rcx]
0x18011f7ab  xor     r14d, r14d
0x18011f7ae  test    rax, rax
0x18011f7b1  jz      loc_18011FA63
0x18011f7b7  cmp     [rax+18h], r14d
0x18011f7bb  jz      loc_18011FA63
0x18011f7c1  mov     [rbp+var_18], r14
0x18011f7c5  mov     [rbp+string], r14
0x18011f7c9  lea     r9, [rbp+string]; string
0x18011f7cd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18011f7d1  lea     edx, [r14+1Bh]; length
0x18011f7d5  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QB_WB; "Windows.Data.Json.JsonArray"
0x18011f7dc  call    cs:__imp_WindowsCreateStringReference
0x18011f7e2  test    eax, eax
0x18011f7e4  js      loc_18011FABF
0x18011f7ea  lea     rdx, [rbp+var_18]
0x18011f7ee  mov     rcx, [rbp+string]
0x18011f7f2  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>)
0x18011f7f7  mov     ebx, eax
0x18011f7f9  test    eax, eax
0x18011f7fb  jns     short loc_18011F81A
0x18011f7fd  mov     rcx, [rbp+18h]; this
0x18011f801  mov     r9d, eax; char *
0x18011f804  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011f80b  mov     edx, 0ECh; void *
0x18011f810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f815  jmp     loc_18011FA47
0x18011f81a  mov     [rbp+var_20], r14
0x18011f81e  mov     [rbp+string], r14
0x18011f822  lea     r9, [rbp+string]; string
0x18011f826  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18011f82a  mov     edx, 1Bh; length
0x18011f82f  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18011f836  call    cs:__imp_WindowsCreateStringReference
0x18011f83c  test    eax, eax
0x18011f83e  js      loc_18011FAB7
0x18011f844  mov     rbx, [rbp+string]
0x18011f848  mov     rcx, [rbp+var_20]
0x18011f84c  test    rcx, rcx
0x18011f84f  jz      short loc_18011F862
0x18011f851  mov     [rbp+var_20], r14
0x18011f855  mov     rax, [rcx]
0x18011f858  mov     rax, [rax+10h]
0x18011f85c  call    _guard_dispatch_icall
0x18011f861  nop
0x18011f862  lea     r8, [rbp+var_20]
0x18011f866  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18011f86d  mov     rcx, rbx
0x18011f870  call    cs:__imp_RoGetActivationFactory
0x18011f876  mov     ebx, eax
0x18011f878  test    eax, eax
0x18011f87a  jns     short loc_18011F899
0x18011f87c  mov     rcx, [rbp+18h]; this
0x18011f880  mov     r9d, eax; char *
0x18011f883  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011f88a  mov     edx, 0F0h; void *
0x18011f88f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f894  jmp     loc_18011FA2D
0x18011f899  mov     [rbp+var_30], r14
0x18011f89d  mov     [rbp+var_28], r14
0x18011f8a1  mov     rcx, [rbp+var_18]
0x18011f8a5  mov     rax, [rcx]
0x18011f8a8  lea     r8, [rbp+var_28]
0x18011f8ac  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x18011f8b3  mov     rax, [rax]
0x18011f8b6  call    _guard_dispatch_icall
0x18011f8bb  mov     ebx, eax
0x18011f8bd  test    eax, eax
0x18011f8bf  jns     short loc_18011F8CB
0x18011f8c1  mov     r9d, eax
0x18011f8c4  mov     edx, 0F4h
0x18011f8c9  jmp     short loc_18011F91C
0x18011f8cb  mov     rdi, [rdi]
0x18011f8ce  test    rdi, rdi
0x18011f8d1  jz      short loc_18011F931
0x18011f8d3  mov     ebx, r14d
0x18011f8d6  jmp     short loc_18011F907
0x18011f8d8  mov     rcx, [rbp+var_28]
0x18011f8dc  mov     [rbp+var_60], rcx
0x18011f8e0  test    rcx, rcx
0x18011f8e3  jz      short loc_18011F8F2
0x18011f8e5  mov     rax, [rcx]
0x18011f8e8  mov     rax, [rax+8]
0x18011f8ec  call    _guard_dispatch_icall
0x18011f8f1  nop
0x18011f8f2  lea     rdx, [rbp+var_60]
0x18011f8f6  mov     rcx, rdi
0x18011f8f9  call    _anonymous_namespace___AppendRetryAttemptDataToJsonVector
0x18011f8fe  mov     ebx, eax
0x18011f900  shr     eax, 1Fh
0x18011f903  test    al, al
0x18011f905  jnz     short loc_18011F910
0x18011f907  mov     rdi, [rdi+8]
0x18011f90b  test    rdi, rdi
0x18011f90e  jnz     short loc_18011F8D8
0x18011f910  test    ebx, ebx
0x18011f912  jns     short loc_18011F931
0x18011f914  mov     r9d, ebx; char *
0x18011f917  mov     edx, 0FCh; void *
0x18011f91c  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011f923  mov     rcx, [rbp+18h]; this
0x18011f927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f92c  jmp     loc_18011F9F9
0x18011f931  mov     [rbp+var_38], r14
0x18011f935  mov     rbx, [rbp+var_28]
0x18011f939  mov     rax, [rbx]
0x18011f93c  mov     rdi, [rax]
0x18011f93f  mov     rcx, [rbp+var_30]
0x18011f943  test    rcx, rcx
0x18011f946  jz      short loc_18011F959
0x18011f948  mov     [rbp+var_30], r14
0x18011f94c  mov     rdx, [rcx]
0x18011f94f  mov     rax, [rdx+10h]
0x18011f953  call    _guard_dispatch_icall
0x18011f958  nop
0x18011f959  lea     r8, [rbp+var_30]
0x18011f95d  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18011f964  mov     rcx, rbx
0x18011f967  mov     rax, rdi
0x18011f96a  call    _guard_dispatch_icall
0x18011f96f  mov     ebx, eax
0x18011f971  test    eax, eax
0x18011f973  jns     short loc_18011F97C
0x18011f975  mov     edx, 102h
0x18011f97a  jmp     short loc_18011F9D3
0x18011f97c  mov     rbx, [rbp+var_30]
0x18011f980  mov     rax, [rbx]
0x18011f983  mov     rdi, [rax+38h]
0x18011f987  mov     rcx, [rbp+var_38]; string
0x18011f98b  call    cs:__imp_WindowsDeleteString
0x18011f991  mov     [rbp+var_38], r14
0x18011f995  lea     rdx, [rbp+var_38]
0x18011f999  mov     rcx, rbx
0x18011f99c  mov     rax, rdi
0x18011f99f  call    _guard_dispatch_icall
0x18011f9a4  mov     ebx, eax
0x18011f9a6  test    eax, eax
0x18011f9a8  jns     short loc_18011F9B1
0x18011f9aa  mov     edx, 103h
0x18011f9af  jmp     short loc_18011F9D3
0x18011f9b1  xor     edx, edx; length
0x18011f9b3  mov     rcx, [rbp+var_38]; string
0x18011f9b7  call    cs:__imp_WindowsGetStringRawBuffer
0x18011f9bd  mov     rdx, rsi
0x18011f9c0  mov     rcx, rax
0x18011f9c3  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18011f9c8  mov     ebx, eax
0x18011f9ca  test    eax, eax
0x18011f9cc  jns     short loc_18011F9E8
0x18011f9ce  mov     edx, 104h; void *
0x18011f9d3  mov     rcx, [rbp+18h]; this
0x18011f9d7  mov     r9d, ebx; char *
0x18011f9da  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011f9e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f9e6  jmp     short loc_18011F9EB
0x18011f9e8  mov     ebx, r14d
0x18011f9eb  mov     rcx, [rbp+var_38]; string
0x18011f9ef  call    cs:__imp_WindowsDeleteString
0x18011f9f5  mov     [rbp+var_38], r14
0x18011f9f9  mov     rcx, [rbp+var_28]
0x18011f9fd  test    rcx, rcx
0x18011fa00  jz      short loc_18011FA13
0x18011fa02  mov     [rbp+var_28], r14
0x18011fa06  mov     rax, [rcx]
0x18011fa09  mov     rax, [rax+10h]
0x18011fa0d  call    _guard_dispatch_icall
0x18011fa12  nop
0x18011fa13  mov     rcx, [rbp+var_30]
0x18011fa17  test    rcx, rcx
0x18011fa1a  jz      short loc_18011FA2D
0x18011fa1c  mov     [rbp+var_30], r14
0x18011fa20  mov     rax, [rcx]
0x18011fa23  mov     rax, [rax+10h]
0x18011fa27  call    _guard_dispatch_icall
0x18011fa2c  nop
0x18011fa2d  mov     rcx, [rbp+var_20]
0x18011fa31  test    rcx, rcx
0x18011fa34  jz      short loc_18011FA47
0x18011fa36  mov     [rbp+var_20], r14
0x18011fa3a  mov     rax, [rcx]
0x18011fa3d  mov     rax, [rax+10h]
0x18011fa41  call    _guard_dispatch_icall
0x18011fa46  nop
0x18011fa47  mov     rcx, [rbp+var_18]
0x18011fa4b  test    rcx, rcx
0x18011fa4e  jz      short loc_18011FA61
0x18011fa50  mov     [rbp+var_18], r14
0x18011fa54  mov     rdx, [rcx]
0x18011fa57  mov     rax, [rdx+10h]
0x18011fa5b  call    _guard_dispatch_icall
0x18011fa60  nop
0x18011fa61  jmp     short loc_18011FA8D
0x18011fa63  lea     rcx, OutputString
0x18011fa6a  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18011fa6f  mov     ebx, eax
0x18011fa71  test    eax, eax
0x18011fa73  jns     short loc_18011FA91
0x18011fa75  mov     rcx, [rbp+18h]; this
0x18011fa79  mov     r9d, eax; char *
0x18011fa7c  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011fa83  mov     edx, 0E6h; void *
0x18011fa88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011fa8d  mov     eax, ebx
0x18011fa8f  jmp     short loc_18011FA93
0x18011fa91  xor     eax, eax
0x18011fa93  mov     rcx, [rbp+var_8]
0x18011fa97  xor     rcx, rsp; StackCookie
0x18011fa9a  call    __security_check_cookie
0x18011fa9f  lea     r11, [rsp+80h+var_s0]
0x18011faa7  mov     rbx, [r11+30h]
0x18011faab  mov     rsi, [r11+38h]
0x18011faaf  mov     rsp, r11
0x18011fab2  pop     r14
0x18011fab4  pop     rdi
0x18011fab5  pop     rbp
0x18011fab6  retn
0x18011fab7  mov     ecx, eax; this
0x18011fab9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18011fabe  nop
0x18011fabf  mov     ecx, eax; this
0x18011fac1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
