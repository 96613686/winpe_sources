# SspTelemetry::LogClientDataForEpaAudit(bool,_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x180034b20`
- end: `0x180034cc9`
- name: `?LogClientDataForEpaAudit@SspTelemetry@@YAX_NPEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `425`
- prototype: `void __fastcall(SspTelemetry *__hidden this, bool, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180034398`

## callees

- `0x18000115c`
- `0x180001338`
- `0x180012880`
- `0x180034654`
- `0x1800348b8`
- `0x1800348e8`
- `0x180034920`
- `0x180034b20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034c1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034c1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SspTelemetry::LogClientDataForEpaAudit(
        SspTelemetry *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2,
        struct _LSA_SECPKG_FUNCTION_TABLE *a3)
{
  int v4; // r12d
  const WCHAR *v5; // rbx
  __int64 SvchostServiceTag; // rax
  const WCHAR *v7; // r15
  const WCHAR *v8; // rsi
  int v9; // r14d
  int v10; // ecx
  int v11; // r8d
  const WCHAR *v12; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+68h] [rbp-98h] BYREF
  int v14; // [rsp+6Ch] [rbp-94h] BYREF
  int v15; // [rsp+70h] [rbp-90h] BYREF
  DWORD CurrentProcessId; // [rsp+74h] [rbp-8Ch] BYREF
  const WCHAR *v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v19; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v20; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v23; // [rsp+C0h] [rbp-40h] BYREF
  char v24; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v25; // [rsp+6C0h] [rbp+5C0h]
  _BYTE v26[8]; // [rsp+6E8h] [rbp+5E8h] BYREF

  v4 = (unsigned __int8)this;
  v5 = 0;
  v17 = 0;
  if ( a2 )
  {
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v22, a2);
    SvchostServiceTag = SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v22, &v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v17,
      SvchostServiceTag);
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v12);
    v7 = (const WCHAR *)&v23;
    v8 = (const WCHAR *)&v24;
    v9 = v25;
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v26);
    v5 = v17;
  }
  else
  {
    v7 = 0;
    v9 = 0;
    v8 = 0;
  }
  if ( (unsigned int)dword_180045108 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180045108, 0x400000000000LL) )
  {
    v18 = 0x1000000;
    v13 = v4;
    if ( a2 )
    {
      v12 = v7;
    }
    else
    {
      v12 = &Class;
      v8 = &Class;
    }
    v19 = v8;
    v14 = v9;
    v15 = v9;
    CurrentProcessId = GetCurrentProcessId();
    if ( !a2 || !v5 )
      v5 = &Class;
    v20 = v5;
    v21 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v10,
      (unsigned int)byte_18003E1FB,
      v11,
      (unsigned int)&v21,
      (__int64)&v20,
      (__int64)&CurrentProcessId,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v19,
      (__int64)&v12,
      (__int64)&v13,
      (__int64)&v18);
  }
  wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(&v17);
}

```

## disassembly

```asm
0x180034b20  push    rbp
0x180034b22  push    rbx
0x180034b23  push    rsi
0x180034b24  push    rdi
0x180034b25  push    r12
0x180034b27  push    r14
0x180034b29  push    r15
0x180034b2b  lea     rbp, [rsp-600h]
0x180034b33  sub     rsp, 700h
0x180034b3a  mov     rax, cs:__security_cookie
0x180034b41  xor     rax, rsp
0x180034b44  mov     [rbp+630h+var_40], rax
0x180034b4b  mov     rdi, rdx
0x180034b4e  movzx   r12d, cl
0x180034b52  xor     ebx, ebx
0x180034b54  mov     [rsp+730h+var_6B8], rbx
0x180034b59  test    rdx, rdx
0x180034b5c  jz      short loc_180034BB2
0x180034b5e  lea     rcx, [rbp+630h+var_690]; this
0x180034b62  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180034b67  nop
0x180034b68  lea     rdx, [rsp+730h+var_6D0]
0x180034b6d  lea     rcx, [rbp+630h+var_690]
0x180034b71  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x180034b76  mov     rdx, rax
0x180034b79  lea     rcx, [rsp+730h+var_6B8]
0x180034b7e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180034b83  lea     rcx, [rsp+730h+var_6D0]
0x180034b88  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034b8d  lea     r15, [rbp+630h+var_670]
0x180034b91  lea     rsi, [rbp+630h+var_470]
0x180034b98  mov     r14d, [rbp+630h+var_70]
0x180034b9f  lea     rcx, [rbp+630h+var_48]
0x180034ba6  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034bab  mov     rbx, [rsp+730h+var_6B8]
0x180034bb0  jmp     short loc_180034BBA
0x180034bb2  xor     r15d, r15d
0x180034bb5  xor     r14d, r14d
0x180034bb8  xor     esi, esi
0x180034bba  mov     eax, cs:dword_180045108
0x180034bc0  cmp     eax, 5
0x180034bc3  jbe     loc_180034C9E
0x180034bc9  mov     rdx, 400000000000h
0x180034bd3  lea     rcx, dword_180045108
0x180034bda  call    _tlgKeywordOn
0x180034bdf  test    al, al
0x180034be1  jz      loc_180034C9E
0x180034be7  mov     [rbp+630h+var_6B0], 1000000h
0x180034bef  mov     [rsp+730h+var_6C8], r12d
0x180034bf4  lea     r12, Class
0x180034bfb  test    rdi, rdi
0x180034bfe  jz      short loc_180034C07
0x180034c00  mov     [rsp+730h+var_6D0], r15
0x180034c05  jmp     short loc_180034C0F
0x180034c07  mov     [rsp+730h+var_6D0], r12
0x180034c0c  mov     rsi, r12
0x180034c0f  mov     [rbp+630h+var_6A8], rsi
0x180034c13  mov     [rsp+730h+var_6C4], r14d
0x180034c18  mov     [rsp+730h+var_6C0], r14d
0x180034c1d  call    cs:__imp_GetCurrentProcessId
0x180034c23  mov     [rsp+730h+var_6BC], eax
0x180034c27  test    rdi, rdi
0x180034c2a  jz      short loc_180034C31
0x180034c2c  test    rbx, rbx
0x180034c2f  jnz     short loc_180034C34
0x180034c31  mov     rbx, r12
0x180034c34  mov     [rbp+630h+var_6A0], rbx
0x180034c38  mov     [rbp+630h+var_698], 1
0x180034c40  lea     rax, [rbp+630h+var_6B0]
0x180034c44  mov     [rsp+730h+var_6D8], rax
0x180034c49  lea     rax, [rsp+730h+var_6C8]
0x180034c4e  mov     [rsp+730h+var_6E0], rax
0x180034c53  lea     rax, [rsp+730h+var_6D0]
0x180034c58  mov     [rsp+730h+var_6E8], rax
0x180034c5d  lea     rax, [rbp+630h+var_6A8]
0x180034c61  mov     [rsp+730h+var_6F0], rax
0x180034c66  lea     rax, [rsp+730h+var_6C4]
0x180034c6b  mov     [rsp+730h+var_6F8], rax
0x180034c70  lea     rax, [rsp+730h+var_6C0]
0x180034c75  mov     [rsp+730h+var_700], rax
0x180034c7a  lea     rax, [rsp+730h+var_6BC]
0x180034c7f  mov     [rsp+730h+var_708], rax
0x180034c84  lea     rax, [rbp+630h+var_6A0]
0x180034c88  mov     [rsp+730h+var_710], rax
0x180034c8d  lea     r9, [rbp+630h+var_698]
0x180034c91  lea     rdx, byte_18003E1FB
0x180034c98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@443342@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180034c9d  nop
0x180034c9e  lea     rcx, [rsp+730h+var_6B8]
0x180034ca3  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180034ca8  mov     rcx, [rbp+630h+var_40]
0x180034caf  xor     rcx, rsp; StackCookie
0x180034cb2  call    __security_check_cookie
0x180034cb7  add     rsp, 700h
0x180034cbe  pop     r15
0x180034cc0  pop     r14
0x180034cc2  pop     r12
0x180034cc4  pop     rdi
0x180034cc5  pop     rsi
0x180034cc6  pop     rbx
0x180034cc7  pop     rbp
0x180034cc8  retn
```
