# CServerTableEntry::WaitForInitCompleted(CServerListEntry *,CClassData *)

- ea: `0x1800f4a64`
- end: `0x1800f4e02`
- name: `?WaitForInitCompleted@CServerTableEntry@@QEAAJPEAVCServerListEntry@@PEAVCClassData@@@Z`
- size: `926`
- prototype: `int(CServerTableEntry *__hidden this, struct CServerListEntry *, struct CClassData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000866c`

## callees

- `0x180005c40`
- `0x18000b428`
- `0x180014870`
- `0x18002effc`
- `0x180034540`
- `0x180043850`
- `0x18005c08c`
- `0x1800a1a38`
- `0x1800f3cd4`
- `0x1800f4a64`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4d3b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800f4c41`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800f4c41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4c4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4c4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4dd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4dd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4bb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4bb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d9d`

## string_xrefs

- `0x1800f4ae1`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800f4bcc`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800f4db8`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800f4bc1`: `CServerTableEntry::WaitForInitCompleted`
- `0x1800f4dad`: `CServerTableEntry::WaitForInitCompleted`
- `0x1800f4bde`: `ClassIdentifier:%ws PID:%x %!HRESULT!`
- `0x1800f4dc4`: `ClassIdentifier:%ws PID:%x %!HRESULT!`
- `0x1800f4af9`: `ClassIdentifier:%ls PID:%x`

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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
0x1800f4a64  mov     [rsp-28h+arg_0], rbx
0x1800f4a69  mov     [rsp-28h+arg_8], rsi
0x1800f4a6e  push    rbp
0x1800f4a6f  push    rdi
0x1800f4a70  push    r12
0x1800f4a72  push    r14
0x1800f4a74  push    r15
0x1800f4a76  mov     rbp, rsp
0x1800f4a79  sub     rsp, 50h
0x1800f4a7d  mov     rdi, r8
0x1800f4a80  mov     r14, rdx
0x1800f4a83  mov     rsi, rcx
0x1800f4a86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800f4a8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800f4a92  xor     r12d, r12d
0x1800f4a95  test    al, al
0x1800f4a97  jz      loc_1800F4B60
0x1800f4a9d  mov     rax, [rsi]
0x1800f4aa0  lea     rcx, [rbp+string]
0x1800f4aa4  xor     edx, edx
0x1800f4aa6  mov     [rbp+string], r12
0x1800f4aaa  mov     rbx, [rax+20h]
0x1800f4aae  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800f4ab3  lea     rdx, [rbp+string]
0x1800f4ab7  mov     rcx, rsi
0x1800f4aba  mov     rax, rbx
0x1800f4abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ac2  mov     rcx, rdi; this
0x1800f4ac5  call    ?IsSystemSurrogateServer@CClassData@@QEBA_NXZ; CClassData::IsSystemSurrogateServer(void)
0x1800f4aca  test    al, al
0x1800f4acc  jnz     short loc_1800F4B1D
0x1800f4ace  mov     rcx, [rbp+string]; string
0x1800f4ad2  xor     edx, edx; length
0x1800f4ad4  mov     ebx, [rsi+10h]
0x1800f4ad7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4add  mov     rcx, [rbp+28h]; this
0x1800f4ae1  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800f4ae8  mov     [rsp+50h+var_20], ebx
0x1800f4aec  mov     edi, 8000402Ah
0x1800f4af1  mov     [rsp+50h+var_28], rax; char *
0x1800f4af6  mov     r9d, edi; char *
0x1800f4af9  lea     rax, aClassidentifie_4; "ClassIdentifier:%ls PID:%x"
0x1800f4b00  mov     edx, 0E29h; void *
0x1800f4b05  mov     qword ptr [rsp+50h+bAlertable], rax; int
0x1800f4b0a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f4b0f  lea     rcx, [rbp+string]
0x1800f4b13  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800f4b18  jmp     loc_1800F4DE7
0x1800f4b1d  lea     rcx, [rbp+string]
0x1800f4b21  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800f4b26  mov     rax, [rdi]
0x1800f4b29  mov     rcx, [rsi]
0x1800f4b2c  mov     rbx, [rax+10h]
0x1800f4b30  mov     rax, [rcx+10h]
0x1800f4b34  mov     rcx, rsi
0x1800f4b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4b3c  mov     rdx, rax
0x1800f4b3f  mov     rcx, rdi
0x1800f4b42  mov     rax, rbx
0x1800f4b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4b4a  mov     r15, rax
0x1800f4b4d  test    rax, rax
0x1800f4b50  jnz     loc_1800F4BFE
0x1800f4b56  mov     eax, 8007000Eh
0x1800f4b5b  jmp     loc_1800F4DE9
0x1800f4b60  test    rdi, rdi
0x1800f4b63  jnz     short loc_1800F4B26
0x1800f4b65  mov     rax, [rsi]
0x1800f4b68  xor     ecx, ecx; string
0x1800f4b6a  mov     [rbp+string], r12
0x1800f4b6e  mov     rbx, [rax+20h]
0x1800f4b72  call    cs:__imp_WindowsDeleteString
0x1800f4b78  lea     rdx, [rbp+string]
0x1800f4b7c  mov     [rbp+string], r12
0x1800f4b80  mov     rcx, rsi
0x1800f4b83  mov     rax, rbx
0x1800f4b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4b8b  mov     eax, cs:dword_18014E4B8
0x1800f4b91  mov     edi, 8000402Ah
0x1800f4b96  test    eax, eax
0x1800f4b98  jnz     short loc_1800F4BAE
0x1800f4b9a  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f4ba1  jz      short loc_1800F4BEF
0x1800f4ba3  xor     ecx, ecx
0x1800f4ba5  call    IsWppLevelEnabled
0x1800f4baa  test    al, al
0x1800f4bac  jz      short loc_1800F4BEF
0x1800f4bae  mov     rcx, [rbp+string]; string
0x1800f4bb2  xor     edx, edx; length
0x1800f4bb4  mov     ebx, [rsi+10h]
0x1800f4bb7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4bbd  mov     [rsp+50h+var_18], edi
0x1800f4bc1  lea     rdx, aCservertableen; "CServerTableEntry::WaitForInitCompleted"
0x1800f4bc8  mov     [rsp+50h+var_20], ebx
0x1800f4bcc  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800f4bd3  mov     [rsp+50h+var_28], rax
0x1800f4bd8  mov     r8d, 0E39h
0x1800f4bde  lea     rax, aClassidentifie_0; "ClassIdentifier:%ws PID:%x %!HRESULT!"
0x1800f4be5  mov     qword ptr [rsp+50h+bAlertable], rax
0x1800f4bea  call    ??$ComTraceMessageT@PEBGKJ@@YAXPEBD0HW4TraceLevel@@PEBG2KJ@Z; ComTraceMessageT<ushort const *,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,long)
0x1800f4bef  mov     rcx, [rbp+string]; string
0x1800f4bf3  call    cs:__imp_WindowsDeleteString
0x1800f4bf9  jmp     loc_1800F4DE7
0x1800f4bfe  mov     rax, [r14+60h]
0x1800f4c02  mov     edi, r12d
0x1800f4c05  mov     ecx, [rax+5Ch]
0x1800f4c08  test    cl, 40h
0x1800f4c0b  jz      loc_1800F4DDF
0x1800f4c11  mov     rcx, [r14+60h]; this
0x1800f4c15  call    ?GetLaunchedProcessHandleUnsafe@CProcess@@QEBAPEAXXZ; CProcess::GetLaunchedProcessHandleUnsafe(void)
0x1800f4c1a  mov     rcx, [r15+18h]; hHandle
0x1800f4c1e  test    rax, rax
0x1800f4c21  jz      short loc_1800F4C49
0x1800f4c23  xor     r8d, r8d; bWaitAll
0x1800f4c26  mov     [rbp+Handles], rcx
0x1800f4c2a  mov     r9d, 15F90h; dwMilliseconds
0x1800f4c30  mov     [rbp+var_8], rax
0x1800f4c34  lea     rdx, [rbp+Handles]; lpHandles
0x1800f4c38  mov     [rsp+50h+bAlertable], r12d; bAlertable
0x1800f4c3d  lea     ecx, [r8+2]; nCount
0x1800f4c41  call    cs:__imp_WaitForMultipleObjectsEx
0x1800f4c47  jmp     short loc_1800F4C54
0x1800f4c49  mov     edx, 15F90h; dwMilliseconds
0x1800f4c4e  call    cs:__imp_WaitForSingleObject
0x1800f4c54  cmp     eax, 102h
0x1800f4c59  jnz     short loc_1800F4CC6
0x1800f4c5b  mov     rax, [rsi]
0x1800f4c5e  xor     ecx, ecx; string
0x1800f4c60  mov     edi, 8000402Ah
0x1800f4c65  mov     [rbp+string], r12
0x1800f4c69  mov     rbx, [rax+20h]
0x1800f4c6d  call    cs:__imp_WindowsDeleteString
0x1800f4c73  lea     rdx, [rbp+string]
0x1800f4c77  mov     [rbp+string], r12
0x1800f4c7b  mov     rcx, rsi
0x1800f4c7e  mov     rax, rbx
0x1800f4c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4c86  mov     eax, cs:dword_18014E4B8
0x1800f4c8c  test    eax, eax
0x1800f4c8e  jnz     short loc_1800F4CAC
0x1800f4c90  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f4c97  jz      loc_1800F4DD5
0x1800f4c9d  xor     ecx, ecx
0x1800f4c9f  call    IsWppLevelEnabled
0x1800f4ca4  test    al, al
0x1800f4ca6  jz      loc_1800F4DD5
0x1800f4cac  mov     rcx, [rbp+string]; string
0x1800f4cb0  xor     edx, edx; length
0x1800f4cb2  mov     ebx, [rsi+10h]
0x1800f4cb5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4cbb  mov     r8d, 0E5Ch
0x1800f4cc1  jmp     loc_1800F4DA9
0x1800f4cc6  test    eax, eax
0x1800f4cc8  jz      loc_1800F4DDF
0x1800f4cce  cmp     eax, 1
0x1800f4cd1  jnz     short loc_1800F4D3B
0x1800f4cd3  mov     rax, [rsi]
0x1800f4cd6  xor     ecx, ecx; string
0x1800f4cd8  mov     edi, 80080008h
0x1800f4cdd  mov     [rbp+string], r12
0x1800f4ce1  mov     rbx, [rax+20h]
0x1800f4ce5  call    cs:__imp_WindowsDeleteString
0x1800f4ceb  lea     rdx, [rbp+string]
0x1800f4cef  mov     [rbp+string], r12
0x1800f4cf3  mov     rcx, rsi
0x1800f4cf6  mov     rax, rbx
0x1800f4cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4cfe  mov     eax, cs:dword_18014E4B8
0x1800f4d04  test    eax, eax
0x1800f4d06  jnz     short loc_1800F4D24
0x1800f4d08  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f4d0f  jz      loc_1800F4DD5
0x1800f4d15  xor     ecx, ecx
0x1800f4d17  call    IsWppLevelEnabled
0x1800f4d1c  test    al, al
0x1800f4d1e  jz      loc_1800F4DD5
0x1800f4d24  mov     rcx, [rbp+string]; string
0x1800f4d28  xor     edx, edx; length
0x1800f4d2a  mov     ebx, [rsi+10h]
0x1800f4d2d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4d33  mov     r8d, 0E6Ah
0x1800f4d39  jmp     short loc_1800F4DA9
0x1800f4d3b  call    cs:__imp_GetLastError
0x1800f4d41  mov     edi, eax
0x1800f4d43  test    eax, eax
0x1800f4d45  jle     short loc_1800F4D50
0x1800f4d47  movzx   edi, ax
0x1800f4d4a  or      edi, 80070000h
0x1800f4d50  mov     rax, [rsi]
0x1800f4d53  xor     ecx, ecx; string
0x1800f4d55  mov     [rbp+string], r12
0x1800f4d59  mov     rbx, [rax+20h]
0x1800f4d5d  call    cs:__imp_WindowsDeleteString
0x1800f4d63  lea     rdx, [rbp+string]
0x1800f4d67  mov     [rbp+string], r12
0x1800f4d6b  mov     rcx, rsi
0x1800f4d6e  mov     rax, rbx
0x1800f4d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4d76  mov     eax, cs:dword_18014E4B8
0x1800f4d7c  test    eax, eax
0x1800f4d7e  jnz     short loc_1800F4D94
0x1800f4d80  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f4d87  jz      short loc_1800F4DD5
0x1800f4d89  xor     ecx, ecx
0x1800f4d8b  call    IsWppLevelEnabled
0x1800f4d90  test    al, al
0x1800f4d92  jz      short loc_1800F4DD5
0x1800f4d94  mov     rcx, [rbp+string]; string
0x1800f4d98  xor     edx, edx; length
0x1800f4d9a  mov     ebx, [rsi+10h]
0x1800f4d9d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4da3  mov     r8d, 0E74h
0x1800f4da9  mov     [rsp+50h+var_18], edi
0x1800f4dad  lea     rdx, aCservertableen; "CServerTableEntry::WaitForInitCompleted"
0x1800f4db4  mov     [rsp+50h+var_20], ebx
0x1800f4db8  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800f4dbf  mov     [rsp+50h+var_28], rax
0x1800f4dc4  lea     rax, aClassidentifie_0; "ClassIdentifier:%ws PID:%x %!HRESULT!"
0x1800f4dcb  mov     qword ptr [rsp+50h+bAlertable], rax
0x1800f4dd0  call    ??$ComTraceMessageT@PEBGKJ@@YAXPEBD0HW4TraceLevel@@PEBG2KJ@Z; ComTraceMessageT<ushort const *,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,long)
0x1800f4dd5  mov     rcx, [rbp+string]; string
0x1800f4dd9  call    cs:__imp_WindowsDeleteString
0x1800f4ddf  mov     rcx, r15; this
0x1800f4de2  call    ?Release@CNamedObject@@UEAAKXZ; CNamedObject::Release(void)
0x1800f4de7  mov     eax, edi
0x1800f4de9  lea     r11, [rsp+50h+var_s0]
0x1800f4dee  mov     rbx, [r11+30h]
0x1800f4df2  mov     rsi, [r11+38h]
0x1800f4df6  mov     rsp, r11
0x1800f4df9  pop     r15
0x1800f4dfb  pop     r14
0x1800f4dfd  pop     r12
0x1800f4dff  pop     rdi
0x1800f4e00  pop     rbp
0x1800f4e01  retn
```
