# _lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()

- ea: `0x180087b5c`
- end: `0x180087e29`
- name: `_lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800876b8`

## callees

- `0x180006ac4`
- `0x180081a38`
- `0x180087b5c`
- `0x1800880dc`
- `0x180089cd0`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180087c0d`
- `RPCRT4!UuidFromStringW` at `0x180087c0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180087cf8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180087cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180087cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180087c54`

## string_xrefs

- `0x180087c4d`: `Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(
        const WCHAR **a1,
        JsonUtil *a2,
        const wchar_t *a3)
{
  signed int StringPropertyWithDefault; // ebx
  __int64 v7; // rdx
  RPC_WSTR v8; // rdi
  __int64 v9; // rdx
  RPC_STATUS v10; // eax
  __int64 (__fastcall *v11)(JsonUtil *, HSTRING, __int64 *); // rbx
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // r12d
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, __int64, HSTRING *); // rsi
  __int64 i; // rdx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v21; // r8
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  wchar_t **lpString2; // [rsp+20h] [rbp-60h]
  int lpString2a; // [rsp+20h] [rbp-60h]
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+60h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  if ( !a2 )
  {
    StringPropertyWithDefault = -2147024809;
    v7 = 70;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)StringPropertyWithDefault,
      (int)lpString2);
    return (unsigned int)StringPropertyWithDefault;
  }
  if ( !a3 )
  {
    StringPropertyWithDefault = -2147467261;
    v7 = 71;
    goto LABEL_3;
  }
  StringUuid = 0;
  StringPropertyWithDefault = JsonUtil::GetStringPropertyWithDefault(
                                a2,
                                a2,
                                a3,
                                (const wchar_t *)&StringUuid,
                                lpString2);
  v8 = StringUuid;
  if ( StringPropertyWithDefault >= 0 )
  {
    if ( StringUuid && *StringUuid )
    {
      Uuid = GUID_NULL;
      v10 = UuidFromStringW(StringUuid, &Uuid);
      StringPropertyWithDefault = v10;
      if ( v10 >= 1 )
        StringPropertyWithDefault = (unsigned __int16)v10 | 0x80010000;
      if ( StringPropertyWithDefault >= 0 )
      {
        v11 = *(__int64 (__fastcall **)(JsonUtil *, HSTRING, __int64 *))(*(_QWORD *)a2 + 72LL);
        v32 = 0;
        string = 0;
        v12 = WindowsCreateStringReference(L"Updates", 7u, &hstringHeader, &string);
        if ( v12 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
          JUMPOUT(0x180087E28LL);
        }
        v15 = v11(a2, string, &v32);
        StringPropertyWithDefault = v15;
        if ( v15 >= 0 )
        {
          v16 = 0;
          v31 = 0;
          v17 = v32;
          v18 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v32 + 64LL);
          WindowsDeleteString(0);
          for ( i = 0; ; i = v16 )
          {
            v31 = 0;
            StringPropertyWithDefault = v18(v17, i, &v31);
            if ( StringPropertyWithDefault == -2147483637 )
              goto LABEL_25;
            if ( StringPropertyWithDefault < 0 )
            {
              v23 = (unsigned int)StringPropertyWithDefault;
              v24 = 98;
              goto LABEL_33;
            }
            StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
            v21 = *a1;
            if ( *a1 == StringRawBuffer
              || v21 && StringRawBuffer && CompareStringW(0x7Fu, 1u, v21, -1, StringRawBuffer, -1) == 2 )
            {
              break;
            }
            WindowsDeleteString(v31);
            ++v16;
            v31 = 0;
            v17 = v32;
            v18 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v32 + 64LL);
            WindowsDeleteString(0);
          }
          v22 = (**(__int64 (__fastcall ***)(JsonUtil *, GUID *, const wchar_t *))a2)(
                  a2,
                  &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                  a3);
          StringPropertyWithDefault = v22;
          if ( v22 >= 0 )
          {
LABEL_25:
            WindowsDeleteString(v31);
            StringPropertyWithDefault = 0;
            goto LABEL_26;
          }
          v23 = (unsigned int)v22;
          v24 = 102;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
            (const char *)v23,
            lpString2a);
          WindowsDeleteString(v31);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
            (const char *)(unsigned int)v15,
            lpString2a);
        }
LABEL_26:
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        goto LABEL_36;
      }
      v9 = 83;
    }
    else
    {
      StringPropertyWithDefault = -2147024809;
      v9 = 80;
    }
  }
  else
  {
    v9 = 77;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)StringPropertyWithDefault,
    lpString2a);
LABEL_36:
  if ( v8 )
    SusFree(v8);
  return (unsigned int)StringPropertyWithDefault;
}

```

## disassembly

```asm
0x180087b5c  mov     [rsp-38h+arg_18], rbx
0x180087b61  push    rbp
0x180087b62  push    rsi
0x180087b63  push    rdi
0x180087b64  push    r12
0x180087b66  push    r13
0x180087b68  push    r14
0x180087b6a  push    r15
0x180087b6c  mov     rbp, rsp
0x180087b6f  sub     rsp, 80h
0x180087b76  mov     rax, cs:__security_cookie
0x180087b7d  xor     rax, rsp
0x180087b80  mov     [rbp+var_8], rax
0x180087b84  mov     r15, r8
0x180087b87  mov     r14, rdx
0x180087b8a  mov     r13, rcx
0x180087b8d  xor     esi, esi
0x180087b8f  test    rdx, rdx
0x180087b92  jnz     short loc_180087BB4
0x180087b94  mov     ebx, 80070057h
0x180087b99  lea     edx, [rsi+46h]; void *
0x180087b9c  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087ba3  mov     r9d, ebx; char *
0x180087ba6  mov     rcx, [rbp+38h]; this
0x180087baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087baf  jmp     loc_180087DF8
0x180087bb4  test    r15, r15
0x180087bb7  jnz     short loc_180087BC4
0x180087bb9  mov     ebx, 80004003h
0x180087bbe  lea     edx, [r15+47h]; struct ABI::Windows::Data::Json::IJsonObject *
0x180087bc2  jmp     short loc_180087B9C
0x180087bc4  mov     [rbp+StringUuid], rsi
0x180087bc8  lea     r9, [rbp+StringUuid]; wchar_t *
0x180087bcc  mov     rcx, r14; this
0x180087bcf  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180087bd4  mov     ebx, eax
0x180087bd6  mov     rdi, [rbp+StringUuid]
0x180087bda  test    eax, eax
0x180087bdc  jns     short loc_180087BE8
0x180087bde  mov     edx, 4Dh ; 'M'
0x180087be3  jmp     loc_180087DD7
0x180087be8  test    rdi, rdi
0x180087beb  jz      loc_180087DCD
0x180087bf1  cmp     [rdi], si
0x180087bf4  jz      loc_180087DCD
0x180087bfa  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180087c01  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180087c06  lea     rdx, [rbp+Uuid]; Uuid
0x180087c0a  mov     rcx, rdi; StringUuid
0x180087c0d  call    cs:__imp_UuidFromStringW
0x180087c13  mov     ebx, eax
0x180087c15  cmp     eax, 1
0x180087c18  jl      short loc_180087C23
0x180087c1a  movzx   ebx, ax
0x180087c1d  or      ebx, 80010000h
0x180087c23  test    ebx, ebx
0x180087c25  jns     short loc_180087C31
0x180087c27  mov     edx, 53h ; 'S'
0x180087c2c  jmp     loc_180087DD7
0x180087c31  mov     rax, [r14]
0x180087c34  mov     rbx, [rax+48h]
0x180087c38  mov     [rbp+var_20], rsi
0x180087c3c  mov     [rbp+string], rsi
0x180087c40  lea     r9, [rbp+string]; string
0x180087c44  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180087c48  mov     edx, 7; length
0x180087c4d  lea     rcx, aUpdates; "Updates"
0x180087c54  call    cs:__imp_WindowsCreateStringReference
0x180087c5a  test    eax, eax
0x180087c5c  js      loc_180087E21
0x180087c62  lea     r8, [rbp+var_20]
0x180087c66  mov     rdx, [rbp+string]
0x180087c6a  mov     rcx, r14
0x180087c6d  mov     rax, rbx
0x180087c70  call    _guard_dispatch_icall
0x180087c75  mov     ebx, eax
0x180087c77  test    eax, eax
0x180087c79  jns     short loc_180087C98
0x180087c7b  mov     rcx, [rbp+38h]; this
0x180087c7f  mov     r9d, eax; char *
0x180087c82  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087c89  mov     edx, 56h ; 'V'; void *
0x180087c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087c93  jmp     loc_180087D5C
0x180087c98  mov     r12d, esi
0x180087c9b  mov     [rbp+var_28], rsi
0x180087c9f  mov     rbx, [rbp+var_20]
0x180087ca3  mov     rax, [rbx]
0x180087ca6  mov     rsi, [rax+40h]
0x180087caa  xor     ecx, ecx; string
0x180087cac  call    cs:__imp_WindowsDeleteString
0x180087cb2  xor     edx, edx
0x180087cb4  jmp     short loc_180087D2A
0x180087cb6  xor     esi, esi
0x180087cb8  test    ebx, ebx
0x180087cba  js      loc_180087DA8
0x180087cc0  xor     edx, edx; length
0x180087cc2  mov     rcx, [rbp+var_28]; string
0x180087cc6  call    cs:__imp_WindowsGetStringRawBuffer
0x180087ccc  mov     r8, [r13+0]; lpString1
0x180087cd0  cmp     r8, rax
0x180087cd3  jz      loc_180087D74
0x180087cd9  test    r8, r8
0x180087cdc  jz      short loc_180087D03
0x180087cde  test    rax, rax
0x180087ce1  jz      short loc_180087D03
0x180087ce3  or      ecx, 0FFFFFFFFh
0x180087ce6  mov     [rsp+80h+cchCount2], ecx; cchCount2
0x180087cea  mov     [rsp+80h+lpString2], rax; int
0x180087cef  mov     r9d, ecx; cchCount1
0x180087cf2  lea     edx, [rsi+1]; dwCmpFlags
0x180087cf5  lea     ecx, [rsi+7Fh]; Locale
0x180087cf8  call    cs:__imp_CompareStringW
0x180087cfe  cmp     eax, 2
0x180087d01  jz      short loc_180087D74
0x180087d03  mov     rcx, [rbp+var_28]; string
0x180087d07  call    cs:__imp_WindowsDeleteString
0x180087d0d  inc     r12d
0x180087d10  mov     [rbp+var_28], rsi
0x180087d14  mov     rbx, [rbp+var_20]
0x180087d18  mov     rax, [rbx]
0x180087d1b  mov     rsi, [rax+40h]
0x180087d1f  xor     ecx, ecx; string
0x180087d21  call    cs:__imp_WindowsDeleteString
0x180087d27  mov     edx, r12d
0x180087d2a  mov     [rbp+var_28], 0
0x180087d32  lea     r8, [rbp+var_28]
0x180087d36  mov     rcx, rbx
0x180087d39  mov     rax, rsi
0x180087d3c  call    _guard_dispatch_icall
0x180087d41  cmp     eax, 8000000Bh
0x180087d46  mov     ebx, eax
0x180087d48  jnz     loc_180087CB6
0x180087d4e  mov     rcx, [rbp+var_28]; string
0x180087d52  call    cs:__imp_WindowsDeleteString
0x180087d58  xor     esi, esi
0x180087d5a  mov     ebx, esi
0x180087d5c  mov     rcx, [rbp+var_20]
0x180087d60  test    rcx, rcx
0x180087d63  jz      short loc_180087D72
0x180087d65  mov     rax, [rcx]
0x180087d68  mov     rax, [rax+10h]
0x180087d6c  call    _guard_dispatch_icall
0x180087d71  nop
0x180087d72  jmp     short loc_180087DEB
0x180087d74  mov     rax, [r14]
0x180087d77  mov     r8, r15
0x180087d7a  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180087d81  mov     rcx, r14
0x180087d84  mov     rax, [rax]
0x180087d87  call    _guard_dispatch_icall
0x180087d8c  mov     ebx, eax
0x180087d8e  test    eax, eax
0x180087d90  jns     short loc_180087D9C
0x180087d92  mov     r9d, eax
0x180087d95  mov     edx, 66h ; 'f'
0x180087d9a  jmp     short loc_180087DB0
0x180087d9c  mov     rcx, [rbp+var_28]; string
0x180087da0  call    cs:__imp_WindowsDeleteString
0x180087da6  jmp     short loc_180087D5A
0x180087da8  mov     r9d, ebx; char *
0x180087dab  mov     edx, 62h ; 'b'; void *
0x180087db0  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087db7  mov     rcx, [rbp+38h]; this
0x180087dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087dc0  nop
0x180087dc1  mov     rcx, [rbp+var_28]; string
0x180087dc5  call    cs:__imp_WindowsDeleteString
0x180087dcb  jmp     short loc_180087D5C
0x180087dcd  mov     ebx, 80070057h
0x180087dd2  mov     edx, 50h ; 'P'; void *
0x180087dd7  mov     rcx, [rbp+38h]; this
0x180087ddb  mov     r9d, ebx; char *
0x180087dde  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180087de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087dea  nop
0x180087deb  test    rdi, rdi
0x180087dee  jz      short loc_180087DF8
0x180087df0  mov     rcx, rdi; lpMem
0x180087df3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180087df8  mov     eax, ebx
0x180087dfa  mov     rcx, [rbp+var_8]
0x180087dfe  xor     rcx, rsp; StackCookie
0x180087e01  call    __security_check_cookie
0x180087e06  mov     rbx, [rsp+80h+arg_18]
0x180087e0e  add     rsp, 80h
0x180087e15  pop     r15
0x180087e17  pop     r14
0x180087e19  pop     r13
0x180087e1b  pop     r12
0x180087e1d  pop     rdi
0x180087e1e  pop     rsi
0x180087e1f  pop     rbp
0x180087e20  retn
0x180087e21  mov     ecx, eax; this
0x180087e23  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
