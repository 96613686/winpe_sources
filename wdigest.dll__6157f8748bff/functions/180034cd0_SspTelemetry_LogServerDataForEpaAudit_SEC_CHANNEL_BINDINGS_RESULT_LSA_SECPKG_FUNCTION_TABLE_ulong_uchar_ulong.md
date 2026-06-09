# SspTelemetry::LogServerDataForEpaAudit(_SEC_CHANNEL_BINDINGS_RESULT *,_LSA_SECPKG_FUNCTION_TABLE *,ulong,uchar,ulong)

- ea: `0x180034cd0`
- end: `0x180034eb3`
- name: `?LogServerDataForEpaAudit@SspTelemetry@@YAXPEAU_SEC_CHANNEL_BINDINGS_RESULT@@PEAU_LSA_SECPKG_FUNCTION_TABLE@@KEK@Z`
- size: `483`
- prototype: `void __fastcall(SspTelemetry *__hidden this, struct _SEC_CHANNEL_BINDINGS_RESULT *, struct _LSA_SECPKG_FUNCTION_TABLE *, unsigned int, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180034434`

## callees

- `0x18000115c`
- `0x180001180`
- `0x180012880`
- `0x180034654`
- `0x1800348b8`
- `0x1800348e8`
- `0x180034920`
- `0x180034cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034de7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034de7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SspTelemetry::LogServerDataForEpaAudit(
        SspTelemetry *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2,
        struct _LSA_SECPKG_FUNCTION_TABLE *a3,
        unsigned __int8 a4,
        int a5)
{
  int v5; // r13d
  const WCHAR *v8; // rbx
  __int64 SvchostServiceTag; // rax
  const WCHAR *v10; // r14
  const WCHAR *v11; // r12
  int v12; // r15d
  int v13; // r9d
  int v14; // eax
  const WCHAR *v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v19; // [rsp+88h] [rbp-78h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+94h] [rbp-6Ch] BYREF
  int v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+9Ch] [rbp-64h] BYREF
  int v24; // [rsp+A0h] [rbp-60h] BYREF
  DWORD CurrentProcessId; // [rsp+A4h] [rbp-5Ch] BYREF
  const WCHAR *v26; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v28; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v29; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v32; // [rsp+F0h] [rbp-10h] BYREF
  char v33; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v34; // [rsp+6F0h] [rbp+5F0h]
  _BYTE v35[8]; // [rsp+718h] [rbp+618h] BYREF

  v5 = a4;
  v18 = (int)a3;
  v8 = 0;
  v26 = 0;
  if ( a2 )
  {
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v31, a2);
    SvchostServiceTag = SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v31, &v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v26,
      SvchostServiceTag);
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v19);
    v10 = (const WCHAR *)&v32;
    v11 = (const WCHAR *)&v33;
    v12 = v34;
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v35);
    v8 = v26;
  }
  else
  {
    v10 = 0;
    v12 = 0;
    v11 = 0;
  }
  if ( (unsigned int)dword_180045108 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180045108, 0x400000000000LL) )
  {
    v27 = 0x1000000;
    v18 = a5;
    if ( this )
      v14 = *(_DWORD *)this;
    else
      v14 = 0;
    v20 = v14;
    v21 = v13;
    v22 = v5;
    v15 = &Class;
    if ( a2 )
      v15 = v11;
    v28 = v15;
    v23 = v12;
    v24 = v12;
    CurrentProcessId = GetCurrentProcessId();
    if ( a2 )
    {
      v19 = v10;
      if ( v8 )
        goto LABEL_16;
    }
    else
    {
      v19 = &Class;
    }
    v8 = &Class;
LABEL_16:
    v29 = v8;
    v30 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v16,
      (unsigned int)&word_18003E2AE,
      v17,
      (unsigned int)&v30,
      (__int64)&v29,
      (__int64)&v19,
      (__int64)&CurrentProcessId,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v28,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v18,
      (__int64)&v27);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v26);
}

```

## disassembly

```asm
0x180034cd0  push    rbp
0x180034cd2  push    rbx
0x180034cd3  push    rsi
0x180034cd4  push    rdi
0x180034cd5  push    r12
0x180034cd7  push    r13
0x180034cd9  push    r14
0x180034cdb  push    r15
0x180034cdd  lea     rbp, [rsp-638h]
0x180034ce5  sub     rsp, 738h
0x180034cec  mov     rax, cs:__security_cookie
0x180034cf3  xor     rax, rsp
0x180034cf6  mov     [rbp+670h+var_50], rax
0x180034cfd  movzx   r13d, r9b
0x180034d01  mov     r9d, r8d
0x180034d04  mov     [rbp+670h+var_6F0], r8d
0x180034d08  mov     rdi, rdx
0x180034d0b  mov     rsi, rcx
0x180034d0e  xor     ebx, ebx
0x180034d10  mov     [rbp+670h+var_6C8], rbx
0x180034d14  test    rdx, rdx
0x180034d17  jz      short loc_180034D6D
0x180034d19  lea     rcx, [rbp+670h+var_6A0]; this
0x180034d1d  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180034d22  nop
0x180034d23  lea     rdx, [rbp+670h+var_6E8]
0x180034d27  lea     rcx, [rbp+670h+var_6A0]
0x180034d2b  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x180034d30  mov     rdx, rax
0x180034d33  lea     rcx, [rbp+670h+var_6C8]
0x180034d37  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180034d3c  lea     rcx, [rbp+670h+var_6E8]
0x180034d40  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034d45  lea     r14, [rbp+670h+var_680]
0x180034d49  lea     r12, [rbp+670h+var_480]
0x180034d50  mov     r15d, [rbp+670h+var_80]
0x180034d57  lea     rcx, [rbp+670h+var_58]
0x180034d5e  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034d63  mov     rbx, [rbp+670h+var_6C8]
0x180034d67  mov     r9d, [rbp+670h+var_6F0]
0x180034d6b  jmp     short loc_180034D76
0x180034d6d  xor     r14d, r14d
0x180034d70  xor     r15d, r15d
0x180034d73  xor     r12d, r12d
0x180034d76  mov     eax, cs:dword_180045108
0x180034d7c  cmp     eax, 5
0x180034d7f  jbe     loc_180034E87
0x180034d85  mov     rdx, 400000000000h
0x180034d8f  lea     rcx, dword_180045108
0x180034d96  call    _tlgKeywordOn
0x180034d9b  test    al, al
0x180034d9d  jz      loc_180034E87
0x180034da3  mov     [rbp+670h+var_6C0], 1000000h
0x180034dab  mov     eax, dword ptr [rbp+670h+arg_20]
0x180034db1  mov     [rbp+670h+var_6F0], eax
0x180034db4  test    rsi, rsi
0x180034db7  jz      short loc_180034DBD
0x180034db9  mov     eax, [rsi]
0x180034dbb  jmp     short loc_180034DBF
0x180034dbd  xor     eax, eax
0x180034dbf  mov     [rbp+670h+var_6E0], eax
0x180034dc2  mov     [rbp+670h+var_6DC], r9d
0x180034dc6  mov     [rbp+670h+var_6D8], r13d
0x180034dca  lea     rsi, Class
0x180034dd1  mov     rax, rsi
0x180034dd4  test    rdi, rdi
0x180034dd7  cmovnz  rax, r12
0x180034ddb  mov     [rbp+670h+var_6B8], rax
0x180034ddf  mov     [rbp+670h+var_6D4], r15d
0x180034de3  mov     [rbp+670h+var_6D0], r15d
0x180034de7  call    cs:__imp_GetCurrentProcessId
0x180034ded  mov     [rbp+670h+var_6CC], eax
0x180034df0  test    rdi, rdi
0x180034df3  jz      short loc_180034E00
0x180034df5  mov     [rbp+670h+var_6E8], r14
0x180034df9  test    rbx, rbx
0x180034dfc  jz      short loc_180034E04
0x180034dfe  jmp     short loc_180034E07
0x180034e00  mov     [rbp+670h+var_6E8], rsi
0x180034e04  mov     rbx, rsi
0x180034e07  mov     [rbp+670h+var_6B0], rbx
0x180034e0b  mov     [rbp+670h+var_6A8], 1
0x180034e13  lea     rax, [rbp+670h+var_6C0]
0x180034e17  mov     [rsp+770h+var_700], rax
0x180034e1c  lea     rax, [rbp+670h+var_6F0]
0x180034e20  mov     [rsp+770h+var_708], rax
0x180034e25  lea     rax, [rbp+670h+var_6E0]
0x180034e29  mov     [rsp+770h+var_710], rax
0x180034e2e  lea     rax, [rbp+670h+var_6DC]
0x180034e32  mov     [rsp+770h+var_718], rax
0x180034e37  lea     rax, [rbp+670h+var_6D8]
0x180034e3b  mov     [rsp+770h+var_720], rax
0x180034e40  lea     rax, [rbp+670h+var_6B8]
0x180034e44  mov     [rsp+770h+var_728], rax
0x180034e49  lea     rax, [rbp+670h+var_6D4]
0x180034e4d  mov     [rsp+770h+var_730], rax
0x180034e52  lea     rax, [rbp+670h+var_6D0]
0x180034e56  mov     [rsp+770h+var_738], rax
0x180034e5b  lea     rax, [rbp+670h+var_6CC]
0x180034e5f  mov     [rsp+770h+var_740], rax
0x180034e64  lea     rax, [rbp+670h+var_6E8]
0x180034e68  mov     [rsp+770h+var_748], rax
0x180034e6d  lea     rax, [rbp+670h+var_6B0]
0x180034e71  mov     [rsp+770h+var_750], rax
0x180034e76  lea     r9, [rbp+670h+var_6A8]
0x180034e7a  lea     rdx, word_18003E2AE
0x180034e81  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U3@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@44344442@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180034e86  nop
0x180034e87  lea     rcx, [rbp+670h+var_6C8]
0x180034e8b  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034e90  mov     rcx, [rbp+670h+var_50]
0x180034e97  xor     rcx, rsp; StackCookie
0x180034e9a  call    __security_check_cookie
0x180034e9f  add     rsp, 738h
0x180034ea6  pop     r15
0x180034ea8  pop     r14
0x180034eaa  pop     r13
0x180034eac  pop     r12
0x180034eae  pop     rdi
0x180034eaf  pop     rsi
0x180034eb0  pop     rbx
0x180034eb1  pop     rbp
0x180034eb2  retn
```
