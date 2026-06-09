# CServerTableEntry::WaitForInitCompleted(CServerListEntry *,CClassData *)

- ea: `0x1800fc8a0`
- end: `0x1800fcc96`
- name: `?WaitForInitCompleted@CServerTableEntry@@QEAAJPEAVCServerListEntry@@PEAVCClassData@@@Z`
- size: `1014`
- prototype: `int(CServerTableEntry *__hidden this, struct CServerListEntry *, struct CClassData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009054`

## callees

- `0x1800065a4`
- `0x18000fb8c`
- `0x1800189d0`
- `0x180024fd0`
- `0x180034260`
- `0x1800535d0`
- `0x180060bbc`
- `0x1800a6f50`
- `0x1800fbaa8`
- `0x1800fc8a0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fcbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fcbb6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800fca95`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800fca95`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fcaa8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fcaa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fca41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcbde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcc66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fca41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcbde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcc66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcb1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcc24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcb1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcc24`

## string_xrefs

- `0x1800fc923`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800fca1a`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800fcc45`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800fca0f`: `CServerTableEntry::WaitForInitCompleted`
- `0x1800fcc3a`: `CServerTableEntry::WaitForInitCompleted`
- `0x1800fca2c`: `ClassIdentifier:%ws PID:%x %!HRESULT!`
- `0x1800fcc51`: `ClassIdentifier:%ws PID:%x %!HRESULT!`
- `0x1800fc93b`: `ClassIdentifier:%ls PID:%x`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::WaitForInitCompleted(
        CServerTableEntry *this,
        struct CServerListEntry *a2,
        struct CClassData *a3)
{
  __int64 v6; // rax
  void (__fastcall *v7)(CServerTableEntry *, HSTRING *); // rbx
  int v8; // ebx
  const char *v9; // rax
  unsigned int v10; // edi
  __int64 (__fastcall *v11)(struct CClassData *, __int64); // rbx
  __int64 v12; // rax
  HANDLE *v13; // r15
  __int64 v15; // rax
  void (__fastcall *v16)(CServerTableEntry *, HSTRING *); // rbx
  int v17; // ebx
  PCWSTR StringRawBuffer; // rax
  int v19; // r9d
  void *LaunchedProcessHandleUnsafe; // rax
  DWORD v21; // eax
  __int64 v22; // rax
  void (__fastcall *v23)(CServerTableEntry *, HSTRING *); // rbx
  int v24; // ebx
  PCWSTR v25; // rax
  int v26; // r9d
  int v27; // r8d
  __int64 v28; // rax
  void (__fastcall *v29)(CServerTableEntry *, HSTRING *); // rbx
  signed int LastError; // eax
  __int64 v31; // rax
  void (__fastcall *v32)(CServerTableEntry *, HSTRING *); // rbx
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HSTRING string; // [rsp+98h] [rbp+48h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    if ( !a3 )
    {
      v15 = *(_QWORD *)this;
      string = 0;
      v16 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v15 + 32);
      WindowsDeleteString(0);
      string = 0;
      v16(this, &string);
      v10 = -2147467222;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v17 = *((_DWORD *)this + 4);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        ComTraceMessageT<unsigned short const *,unsigned long,long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (unsigned int)"CServerTableEntry::WaitForInitCompleted",
          3641,
          v19,
          (__int64)L"ClassIdentifier:%ws PID:%x %!HRESULT!",
          StringRawBuffer,
          v17,
          -2147467222);
      }
      WindowsDeleteString(string);
      return v10;
    }
LABEL_5:
    v11 = *(__int64 (__fastcall **)(struct CClassData *, __int64))(*(_QWORD *)a3 + 16LL);
    v12 = (*(__int64 (__fastcall **)(CServerTableEntry *))(*(_QWORD *)this + 16LL))(this);
    v13 = (HANDLE *)v11(a3, v12);
    if ( !v13 )
      return 2147942414LL;
    v10 = 0;
    if ( (*(_DWORD *)(*((_QWORD *)a2 + 12) + 92LL) & 0x40) == 0 )
      goto LABEL_36;
    LaunchedProcessHandleUnsafe = CProcess::GetLaunchedProcessHandleUnsafe(*((CProcess **)a2 + 12));
    if ( LaunchedProcessHandleUnsafe )
    {
      Handles[0] = v13[3];
      Handles[1] = LaunchedProcessHandleUnsafe;
      v21 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x15F90u, 0);
    }
    else
    {
      v21 = WaitForSingleObject(v13[3], 0x15F90u);
    }
    switch ( v21 )
    {
      case 0x102u:
        v22 = *(_QWORD *)this;
        v10 = -2147467222;
        string = 0;
        v23 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v22 + 32);
        WindowsDeleteString(0);
        string = 0;
        v23(this, &string);
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_35;
        v24 = *((_DWORD *)this + 4);
        v25 = WindowsGetStringRawBuffer(string, 0);
        v27 = 3676;
        break;
      case 0u:
LABEL_36:
        CNamedObject::Release((CNamedObject *)v13);
        return v10;
      case 1u:
        v28 = *(_QWORD *)this;
        v10 = -2146959352;
        string = 0;
        v29 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v28 + 32);
        WindowsDeleteString(0);
        string = 0;
        v29(this, &string);
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_35;
        v24 = *((_DWORD *)this + 4);
        v25 = WindowsGetStringRawBuffer(string, 0);
        v27 = 3690;
        break;
      default:
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v31 = *(_QWORD *)this;
        string = 0;
        v32 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v31 + 32);
        WindowsDeleteString(0);
        string = 0;
        v32(this, &string);
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_35;
        v24 = *((_DWORD *)this + 4);
        v25 = WindowsGetStringRawBuffer(string, 0);
        v27 = 3700;
        break;
    }
    ComTraceMessageT<unsigned short const *,unsigned long,long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (unsigned int)"CServerTableEntry::WaitForInitCompleted",
      v27,
      v26,
      (__int64)L"ClassIdentifier:%ws PID:%x %!HRESULT!",
      v25,
      v24,
      v10);
LABEL_35:
    WindowsDeleteString(string);
    goto LABEL_36;
  }
  v6 = *(_QWORD *)this;
  string = 0;
  v7 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v6 + 32);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v7(this, &string);
  if ( CClassData::IsSystemSurrogateServer(a3) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    goto LABEL_5;
  }
  v8 = *((_DWORD *)this + 4);
  v9 = (const char *)WindowsGetStringRawBuffer(string, 0);
  v10 = -2147467222;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xE29,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
    (const char *)0x8000402ALL,
    (int)"ClassIdentifier:%ls PID:%x",
    v9,
    v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
  return v10;
}

```

## disassembly

```asm
0x1800fc8a0  mov     [rsp-28h+arg_0], rbx
0x1800fc8a5  mov     [rsp-28h+arg_8], rsi
0x1800fc8aa  push    rbp
0x1800fc8ab  push    rdi
0x1800fc8ac  push    r12
0x1800fc8ae  push    r14
0x1800fc8b0  push    r15
0x1800fc8b2  mov     rbp, rsp
0x1800fc8b5  sub     rsp, 50h
0x1800fc8b9  mov     rdi, r8
0x1800fc8bc  mov     r14, rdx
0x1800fc8bf  mov     rsi, rcx
0x1800fc8c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800fc8c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800fc8ce  xor     r12d, r12d
0x1800fc8d1  test    al, al
0x1800fc8d3  jz      loc_1800FC9A2
0x1800fc8d9  mov     rax, [rsi]
0x1800fc8dc  lea     rcx, [rbp+string]
0x1800fc8e0  xor     edx, edx
0x1800fc8e2  mov     [rbp+string], r12
0x1800fc8e6  mov     rbx, [rax+20h]
0x1800fc8ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800fc8ef  lea     rdx, [rbp+string]
0x1800fc8f3  mov     rcx, rsi
0x1800fc8f6  mov     rax, rbx
0x1800fc8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc8fe  mov     rcx, rdi; this
0x1800fc901  call    ?IsSystemSurrogateServer@CClassData@@QEBA_NXZ; CClassData::IsSystemSurrogateServer(void)
0x1800fc906  test    al, al
0x1800fc908  jnz     short loc_1800FC95F
0x1800fc90a  mov     rcx, [rbp+string]; string
0x1800fc90e  xor     edx, edx; length
0x1800fc910  mov     ebx, [rsi+10h]
0x1800fc913  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc91a  nop     dword ptr [rax+rax+00h]
0x1800fc91f  mov     rcx, [rbp+28h]; this
0x1800fc923  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800fc92a  mov     [rsp+50h+var_20], ebx
0x1800fc92e  mov     edi, 8000402Ah
0x1800fc933  mov     [rsp+50h+var_28], rax; char *
0x1800fc938  mov     r9d, edi; char *
0x1800fc93b  lea     rax, aClassidentifie_4; "ClassIdentifier:%ls PID:%x"
0x1800fc942  mov     edx, 0E29h; void *
0x1800fc947  mov     qword ptr [rsp+50h+bAlertable], rax; int
0x1800fc94c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fc951  lea     rcx, [rbp+string]
0x1800fc955  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800fc95a  jmp     loc_1800FCC7A
0x1800fc95f  lea     rcx, [rbp+string]
0x1800fc963  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800fc968  mov     rax, [rdi]
0x1800fc96b  mov     rcx, [rsi]
0x1800fc96e  mov     rbx, [rax+10h]
0x1800fc972  mov     rax, [rcx+10h]
0x1800fc976  mov     rcx, rsi
0x1800fc979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc97e  mov     rdx, rax
0x1800fc981  mov     rcx, rdi
0x1800fc984  mov     rax, rbx
0x1800fc987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc98c  mov     r15, rax
0x1800fc98f  test    rax, rax
0x1800fc992  jnz     loc_1800FCA52
0x1800fc998  mov     eax, 8007000Eh
0x1800fc99d  jmp     loc_1800FCC7C
0x1800fc9a2  test    rdi, rdi
0x1800fc9a5  jnz     short loc_1800FC968
0x1800fc9a7  mov     rax, [rsi]
0x1800fc9aa  xor     ecx, ecx; string
0x1800fc9ac  mov     [rbp+string], r12
0x1800fc9b0  mov     rbx, [rax+20h]
0x1800fc9b4  call    cs:__imp_WindowsDeleteString
0x1800fc9bb  nop     dword ptr [rax+rax+00h]
0x1800fc9c0  lea     rdx, [rbp+string]
0x1800fc9c4  mov     [rbp+string], r12
0x1800fc9c8  mov     rcx, rsi
0x1800fc9cb  mov     rax, rbx
0x1800fc9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc9d3  mov     eax, cs:dword_1801574B8
0x1800fc9d9  mov     edi, 8000402Ah
0x1800fc9de  test    eax, eax
0x1800fc9e0  jnz     short loc_1800FC9F6
0x1800fc9e2  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800fc9e9  jz      short loc_1800FCA3D
0x1800fc9eb  xor     ecx, ecx
0x1800fc9ed  call    IsWppLevelEnabled
0x1800fc9f2  test    al, al
0x1800fc9f4  jz      short loc_1800FCA3D
0x1800fc9f6  mov     rcx, [rbp+string]; string
0x1800fc9fa  xor     edx, edx; length
0x1800fc9fc  mov     ebx, [rsi+10h]
0x1800fc9ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fca06  nop     dword ptr [rax+rax+00h]
0x1800fca0b  mov     [rsp+50h+var_18], edi
0x1800fca0f  lea     rdx, aCservertableen; "CServerTableEntry::WaitForInitCompleted"
0x1800fca16  mov     [rsp+50h+var_20], ebx
0x1800fca1a  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800fca21  mov     [rsp+50h+var_28], rax
0x1800fca26  mov     r8d, 0E39h
0x1800fca2c  lea     rax, aClassidentifie_0; "ClassIdentifier:%ws PID:%x %!HRESULT!"
0x1800fca33  mov     qword ptr [rsp+50h+bAlertable], rax
0x1800fca38  call    ??$ComTraceMessageT@PEBGKJ@@YAXPEBD0HW4TraceLevel@@PEBG2KJ@Z; ComTraceMessageT<ushort const *,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,long)
0x1800fca3d  mov     rcx, [rbp+string]; string
0x1800fca41  call    cs:__imp_WindowsDeleteString
0x1800fca48  nop     dword ptr [rax+rax+00h]
0x1800fca4d  jmp     loc_1800FCC7A
0x1800fca52  mov     rax, [r14+60h]
0x1800fca56  mov     edi, r12d
0x1800fca59  mov     ecx, [rax+5Ch]
0x1800fca5c  test    cl, 40h
0x1800fca5f  jz      loc_1800FCC72
0x1800fca65  mov     rcx, [r14+60h]; this
0x1800fca69  call    ?GetLaunchedProcessHandleUnsafe@CProcess@@QEBAPEAXXZ; CProcess::GetLaunchedProcessHandleUnsafe(void)
0x1800fca6e  mov     rcx, [r15+18h]; hHandle
0x1800fca72  test    rax, rax
0x1800fca75  jz      short loc_1800FCAA3
0x1800fca77  xor     r8d, r8d; bWaitAll
0x1800fca7a  mov     [rbp+Handles], rcx
0x1800fca7e  mov     r9d, 15F90h; dwMilliseconds
0x1800fca84  mov     [rbp+var_8], rax
0x1800fca88  lea     rdx, [rbp+Handles]; lpHandles
0x1800fca8c  mov     [rsp+50h+bAlertable], r12d; bAlertable
0x1800fca91  lea     ecx, [r8+2]; nCount
0x1800fca95  call    cs:__imp_WaitForMultipleObjectsEx
0x1800fca9c  nop     dword ptr [rax+rax+00h]
0x1800fcaa1  jmp     short loc_1800FCAB4
0x1800fcaa3  mov     edx, 15F90h; dwMilliseconds
0x1800fcaa8  call    cs:__imp_WaitForSingleObject
0x1800fcaaf  nop     dword ptr [rax+rax+00h]
0x1800fcab4  cmp     eax, 102h
0x1800fcab9  jnz     short loc_1800FCB32
0x1800fcabb  mov     rax, [rsi]
0x1800fcabe  xor     ecx, ecx; string
0x1800fcac0  mov     edi, 8000402Ah
0x1800fcac5  mov     [rbp+string], r12
0x1800fcac9  mov     rbx, [rax+20h]
0x1800fcacd  call    cs:__imp_WindowsDeleteString
0x1800fcad4  nop     dword ptr [rax+rax+00h]
0x1800fcad9  lea     rdx, [rbp+string]
0x1800fcadd  mov     [rbp+string], r12
0x1800fcae1  mov     rcx, rsi
0x1800fcae4  mov     rax, rbx
0x1800fcae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcaec  mov     eax, cs:dword_1801574B8
0x1800fcaf2  test    eax, eax
0x1800fcaf4  jnz     short loc_1800FCB12
0x1800fcaf6  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800fcafd  jz      loc_1800FCC62
0x1800fcb03  xor     ecx, ecx
0x1800fcb05  call    IsWppLevelEnabled
0x1800fcb0a  test    al, al
0x1800fcb0c  jz      loc_1800FCC62
0x1800fcb12  mov     rcx, [rbp+string]; string
0x1800fcb16  xor     edx, edx; length
0x1800fcb18  mov     ebx, [rsi+10h]
0x1800fcb1b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fcb22  nop     dword ptr [rax+rax+00h]
0x1800fcb27  mov     r8d, 0E5Ch
0x1800fcb2d  jmp     loc_1800FCC36
0x1800fcb32  test    eax, eax
0x1800fcb34  jz      loc_1800FCC72
0x1800fcb3a  cmp     eax, 1
0x1800fcb3d  jnz     short loc_1800FCBB6
0x1800fcb3f  mov     rax, [rsi]
0x1800fcb42  xor     ecx, ecx; string
0x1800fcb44  mov     edi, 80080008h
0x1800fcb49  mov     [rbp+string], r12
0x1800fcb4d  mov     rbx, [rax+20h]
0x1800fcb51  call    cs:__imp_WindowsDeleteString
0x1800fcb58  nop     dword ptr [rax+rax+00h]
0x1800fcb5d  lea     rdx, [rbp+string]
0x1800fcb61  mov     [rbp+string], r12
0x1800fcb65  mov     rcx, rsi
0x1800fcb68  mov     rax, rbx
0x1800fcb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcb70  mov     eax, cs:dword_1801574B8
0x1800fcb76  test    eax, eax
0x1800fcb78  jnz     short loc_1800FCB96
0x1800fcb7a  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800fcb81  jz      loc_1800FCC62
0x1800fcb87  xor     ecx, ecx
0x1800fcb89  call    IsWppLevelEnabled
0x1800fcb8e  test    al, al
0x1800fcb90  jz      loc_1800FCC62
0x1800fcb96  mov     rcx, [rbp+string]; string
0x1800fcb9a  xor     edx, edx; length
0x1800fcb9c  mov     ebx, [rsi+10h]
0x1800fcb9f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fcba6  nop     dword ptr [rax+rax+00h]
0x1800fcbab  mov     r8d, 0E6Ah
0x1800fcbb1  jmp     loc_1800FCC36
0x1800fcbb6  call    cs:__imp_GetLastError
0x1800fcbbd  nop     dword ptr [rax+rax+00h]
0x1800fcbc2  mov     edi, eax
0x1800fcbc4  test    eax, eax
0x1800fcbc6  jle     short loc_1800FCBD1
0x1800fcbc8  movzx   edi, ax
0x1800fcbcb  or      edi, 80070000h
0x1800fcbd1  mov     rax, [rsi]
0x1800fcbd4  xor     ecx, ecx; string
0x1800fcbd6  mov     [rbp+string], r12
0x1800fcbda  mov     rbx, [rax+20h]
0x1800fcbde  call    cs:__imp_WindowsDeleteString
0x1800fcbe5  nop     dword ptr [rax+rax+00h]
0x1800fcbea  lea     rdx, [rbp+string]
0x1800fcbee  mov     [rbp+string], r12
0x1800fcbf2  mov     rcx, rsi
0x1800fcbf5  mov     rax, rbx
0x1800fcbf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcbfd  mov     eax, cs:dword_1801574B8
0x1800fcc03  test    eax, eax
0x1800fcc05  jnz     short loc_1800FCC1B
0x1800fcc07  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800fcc0e  jz      short loc_1800FCC62
0x1800fcc10  xor     ecx, ecx
0x1800fcc12  call    IsWppLevelEnabled
0x1800fcc17  test    al, al
0x1800fcc19  jz      short loc_1800FCC62
0x1800fcc1b  mov     rcx, [rbp+string]; string
0x1800fcc1f  xor     edx, edx; length
0x1800fcc21  mov     ebx, [rsi+10h]
0x1800fcc24  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fcc2b  nop     dword ptr [rax+rax+00h]
0x1800fcc30  mov     r8d, 0E74h
0x1800fcc36  mov     [rsp+50h+var_18], edi
0x1800fcc3a  lea     rdx, aCservertableen; "CServerTableEntry::WaitForInitCompleted"
0x1800fcc41  mov     [rsp+50h+var_20], ebx
0x1800fcc45  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800fcc4c  mov     [rsp+50h+var_28], rax
0x1800fcc51  lea     rax, aClassidentifie_0; "ClassIdentifier:%ws PID:%x %!HRESULT!"
0x1800fcc58  mov     qword ptr [rsp+50h+bAlertable], rax
0x1800fcc5d  call    ??$ComTraceMessageT@PEBGKJ@@YAXPEBD0HW4TraceLevel@@PEBG2KJ@Z; ComTraceMessageT<ushort const *,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,long)
0x1800fcc62  mov     rcx, [rbp+string]; string
0x1800fcc66  call    cs:__imp_WindowsDeleteString
0x1800fcc6d  nop     dword ptr [rax+rax+00h]
0x1800fcc72  mov     rcx, r15; this
0x1800fcc75  call    ?Release@CNamedObject@@UEAAKXZ; CNamedObject::Release(void)
0x1800fcc7a  mov     eax, edi
0x1800fcc7c  lea     r11, [rsp+50h+var_s0]
0x1800fcc81  mov     rbx, [r11+30h]
0x1800fcc85  mov     rsi, [r11+38h]
0x1800fcc89  mov     rsp, r11
0x1800fcc8c  pop     r15
0x1800fcc8e  pop     r14
0x1800fcc90  pop     r12
0x1800fcc92  pop     rdi
0x1800fcc93  pop     rbp
0x1800fcc94  retn
```
