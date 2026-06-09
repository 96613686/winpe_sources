# _lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()

- ea: `0x18003ecf4`
- end: `0x18003efcb`
- name: `_lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003e850`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18002e000`
- `0x18003ecf4`
- `0x180041970`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18003edaf`
- `RPCRT4!UuidFromStringW` at `0x18003edaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ee4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ee4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003eef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ef67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ee68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ee68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003edf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003edf6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee9a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ee9a`

## string_xrefs

- `0x18003edef`: `Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_a4c2085267137ef4ce0642cdecb305f9_::operator()(const WCHAR **a1, JsonUtil *a2, __int64 a3)
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
                                (struct ABI::Windows::Data::Json::IJsonObject *)L"SessionID",
                                0,
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
          JUMPOUT(0x18003EFCALL);
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
          v22 = (**(__int64 (__fastcall ***)(JsonUtil *, GUID *, __int64))a2)(
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
    CSusBaseAllocTag<942762101>::operator delete(v8);
  return (unsigned int)StringPropertyWithDefault;
}

```

## disassembly

```asm
0x18003ecf4  mov     [rsp-38h+arg_18], rbx
0x18003ecf9  push    rbp
0x18003ecfa  push    rsi
0x18003ecfb  push    rdi
0x18003ecfc  push    r12
0x18003ecfe  push    r13
0x18003ed00  push    r14
0x18003ed02  push    r15
0x18003ed04  mov     rbp, rsp
0x18003ed07  sub     rsp, 80h
0x18003ed0e  mov     rax, cs:__security_cookie
0x18003ed15  xor     rax, rsp
0x18003ed18  mov     [rbp+var_8], rax
0x18003ed1c  mov     r15, r8
0x18003ed1f  mov     r14, rdx
0x18003ed22  mov     r13, rcx
0x18003ed25  xor     esi, esi
0x18003ed27  test    rdx, rdx
0x18003ed2a  jnz     short loc_18003ED4C
0x18003ed2c  mov     ebx, 80070057h
0x18003ed31  lea     edx, [rsi+46h]; void *
0x18003ed34  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ed3b  mov     r9d, ebx; char *
0x18003ed3e  mov     rcx, [rbp+38h]; this
0x18003ed42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ed47  jmp     loc_18003EF9A
0x18003ed4c  test    r15, r15
0x18003ed4f  jnz     short loc_18003ED5C
0x18003ed51  mov     ebx, 80004003h
0x18003ed56  lea     edx, [r15+47h]
0x18003ed5a  jmp     short loc_18003ED34
0x18003ed5c  mov     [rbp+StringUuid], rsi
0x18003ed60  lea     r9, [rbp+StringUuid]; wchar_t *
0x18003ed64  xor     r8d, r8d; wchar_t *
0x18003ed67  lea     rdx, aSessionid; "SessionID"
0x18003ed6e  mov     rcx, r14; this
0x18003ed71  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003ed76  mov     ebx, eax
0x18003ed78  mov     rdi, [rbp+StringUuid]
0x18003ed7c  test    eax, eax
0x18003ed7e  jns     short loc_18003ED8A
0x18003ed80  mov     edx, 4Dh ; 'M'
0x18003ed85  jmp     loc_18003EF79
0x18003ed8a  test    rdi, rdi
0x18003ed8d  jz      loc_18003EF6F
0x18003ed93  cmp     [rdi], si
0x18003ed96  jz      loc_18003EF6F
0x18003ed9c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003eda3  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18003eda8  lea     rdx, [rbp+Uuid]; Uuid
0x18003edac  mov     rcx, rdi; StringUuid
0x18003edaf  call    cs:__imp_UuidFromStringW
0x18003edb5  mov     ebx, eax
0x18003edb7  cmp     eax, 1
0x18003edba  jl      short loc_18003EDC5
0x18003edbc  movzx   ebx, ax
0x18003edbf  or      ebx, 80010000h
0x18003edc5  test    ebx, ebx
0x18003edc7  jns     short loc_18003EDD3
0x18003edc9  mov     edx, 53h ; 'S'
0x18003edce  jmp     loc_18003EF79
0x18003edd3  mov     rax, [r14]
0x18003edd6  mov     rbx, [rax+48h]
0x18003edda  mov     [rbp+var_20], rsi
0x18003edde  mov     [rbp+string], rsi
0x18003ede2  lea     r9, [rbp+string]; string
0x18003ede6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003edea  mov     edx, 7; length
0x18003edef  lea     rcx, aUpdates; "Updates"
0x18003edf6  call    cs:__imp_WindowsCreateStringReference
0x18003edfc  test    eax, eax
0x18003edfe  js      loc_18003EFC3
0x18003ee04  lea     r8, [rbp+var_20]
0x18003ee08  mov     rdx, [rbp+string]
0x18003ee0c  mov     rcx, r14
0x18003ee0f  mov     rax, rbx
0x18003ee12  call    _guard_dispatch_icall
0x18003ee17  mov     ebx, eax
0x18003ee19  test    eax, eax
0x18003ee1b  jns     short loc_18003EE3A
0x18003ee1d  mov     rcx, [rbp+38h]; this
0x18003ee21  mov     r9d, eax; char *
0x18003ee24  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ee2b  mov     edx, 56h ; 'V'; void *
0x18003ee30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee35  jmp     loc_18003EEFE
0x18003ee3a  mov     r12d, esi
0x18003ee3d  mov     [rbp+var_28], rsi
0x18003ee41  mov     rbx, [rbp+var_20]
0x18003ee45  mov     rax, [rbx]
0x18003ee48  mov     rsi, [rax+40h]
0x18003ee4c  xor     ecx, ecx; string
0x18003ee4e  call    cs:__imp_WindowsDeleteString
0x18003ee54  xor     edx, edx
0x18003ee56  jmp     short loc_18003EECC
0x18003ee58  xor     esi, esi
0x18003ee5a  test    ebx, ebx
0x18003ee5c  js      loc_18003EF4A
0x18003ee62  xor     edx, edx; length
0x18003ee64  mov     rcx, [rbp+var_28]; string
0x18003ee68  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ee6e  mov     r8, [r13+0]; lpString1
0x18003ee72  cmp     r8, rax
0x18003ee75  jz      loc_18003EF16
0x18003ee7b  test    r8, r8
0x18003ee7e  jz      short loc_18003EEA5
0x18003ee80  test    rax, rax
0x18003ee83  jz      short loc_18003EEA5
0x18003ee85  or      ecx, 0FFFFFFFFh
0x18003ee88  mov     [rsp+80h+cchCount2], ecx; cchCount2
0x18003ee8c  mov     [rsp+80h+lpString2], rax; int
0x18003ee91  mov     r9d, ecx; cchCount1
0x18003ee94  lea     edx, [rsi+1]; dwCmpFlags
0x18003ee97  lea     ecx, [rsi+7Fh]; Locale
0x18003ee9a  call    cs:__imp_CompareStringW
0x18003eea0  cmp     eax, 2
0x18003eea3  jz      short loc_18003EF16
0x18003eea5  mov     rcx, [rbp+var_28]; string
0x18003eea9  call    cs:__imp_WindowsDeleteString
0x18003eeaf  inc     r12d
0x18003eeb2  mov     [rbp+var_28], rsi
0x18003eeb6  mov     rbx, [rbp+var_20]
0x18003eeba  mov     rax, [rbx]
0x18003eebd  mov     rsi, [rax+40h]
0x18003eec1  xor     ecx, ecx; string
0x18003eec3  call    cs:__imp_WindowsDeleteString
0x18003eec9  mov     edx, r12d
0x18003eecc  mov     [rbp+var_28], 0
0x18003eed4  lea     r8, [rbp+var_28]
0x18003eed8  mov     rcx, rbx
0x18003eedb  mov     rax, rsi
0x18003eede  call    _guard_dispatch_icall
0x18003eee3  cmp     eax, 8000000Bh
0x18003eee8  mov     ebx, eax
0x18003eeea  jnz     loc_18003EE58
0x18003eef0  mov     rcx, [rbp+var_28]; string
0x18003eef4  call    cs:__imp_WindowsDeleteString
0x18003eefa  xor     esi, esi
0x18003eefc  mov     ebx, esi
0x18003eefe  mov     rcx, [rbp+var_20]
0x18003ef02  test    rcx, rcx
0x18003ef05  jz      short loc_18003EF14
0x18003ef07  mov     rax, [rcx]
0x18003ef0a  mov     rax, [rax+10h]
0x18003ef0e  call    _guard_dispatch_icall
0x18003ef13  nop
0x18003ef14  jmp     short loc_18003EF8D
0x18003ef16  mov     rax, [r14]
0x18003ef19  mov     r8, r15
0x18003ef1c  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18003ef23  mov     rcx, r14
0x18003ef26  mov     rax, [rax]
0x18003ef29  call    _guard_dispatch_icall
0x18003ef2e  mov     ebx, eax
0x18003ef30  test    eax, eax
0x18003ef32  jns     short loc_18003EF3E
0x18003ef34  mov     r9d, eax
0x18003ef37  mov     edx, 66h ; 'f'
0x18003ef3c  jmp     short loc_18003EF52
0x18003ef3e  mov     rcx, [rbp+var_28]; string
0x18003ef42  call    cs:__imp_WindowsDeleteString
0x18003ef48  jmp     short loc_18003EEFC
0x18003ef4a  mov     r9d, ebx; char *
0x18003ef4d  mov     edx, 62h ; 'b'; void *
0x18003ef52  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ef59  mov     rcx, [rbp+38h]; this
0x18003ef5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef62  nop
0x18003ef63  mov     rcx, [rbp+var_28]; string
0x18003ef67  call    cs:__imp_WindowsDeleteString
0x18003ef6d  jmp     short loc_18003EEFE
0x18003ef6f  mov     ebx, 80070057h
0x18003ef74  mov     edx, 50h ; 'P'; void *
0x18003ef79  mov     rcx, [rbp+38h]; this
0x18003ef7d  mov     r9d, ebx; char *
0x18003ef80  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003ef87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef8c  nop
0x18003ef8d  test    rdi, rdi
0x18003ef90  jz      short loc_18003EF9A
0x18003ef92  mov     rcx, rdi; lpMem
0x18003ef95  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18003ef9a  mov     eax, ebx
0x18003ef9c  mov     rcx, [rbp+var_8]
0x18003efa0  xor     rcx, rsp; StackCookie
0x18003efa3  call    __security_check_cookie
0x18003efa8  mov     rbx, [rsp+80h+arg_18]
0x18003efb0  add     rsp, 80h
0x18003efb7  pop     r15
0x18003efb9  pop     r14
0x18003efbb  pop     r13
0x18003efbd  pop     r12
0x18003efbf  pop     rdi
0x18003efc0  pop     rsi
0x18003efc1  pop     rbp
0x18003efc2  retn
0x18003efc3  mov     ecx, eax; this
0x18003efc5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
