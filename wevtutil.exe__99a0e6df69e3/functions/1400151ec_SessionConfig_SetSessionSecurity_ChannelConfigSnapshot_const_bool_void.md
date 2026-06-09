# SessionConfig::SetSessionSecurity(ChannelConfigSnapshot const &,bool,void *)

- ea: `0x1400151ec`
- end: `0x140015841`
- name: `?SetSessionSecurity@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z`
- size: `1621`
- prototype: `static void(const struct ChannelConfigSnapshot *, bool, void *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013658`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140006db0`
- `0x140007fd0`
- `0x14000a4d8`
- `0x14000b6d0`
- `0x140014960`
- `0x1400151ec`
- `0x140015878`
- `0x140015898`
- `0x14001b5b4`
- `0x140021b00`
- `0x140022cec`
- `0x14002bc70`
- `0x14002e75c`
- `0x14002ebf0`
- `0x14002f018`
- `0x14002f384`
- `0x14002f6c8`
- `0x14003029c`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015364`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1400155d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1400155eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1400155d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1400155eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001535a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001535a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400156f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400156fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400156f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400156fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001571f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015730`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001571f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015730`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400157c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400157c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SessionConfig::SetSessionSecurity(const struct ChannelConfigSnapshot *a1, __int64 a2, void *a3)
{
  int v5; // eax
  int v6; // edi
  char v7; // bl
  const WCHAR *v8; // rdi
  void **v9; // rax
  void *v10; // r14
  PSECURITY_DESCRIPTOR *v11; // rax
  DWORD LastError; // edi
  const char *v13; // r8
  DWORD cbData; // r14d
  __int64 v15; // rcx
  unsigned int AutoLoggerSecurityRegPath; // eax
  unsigned int v17; // edi
  HKEY *v18; // rax
  unsigned int RegKey; // eax
  unsigned int v20; // edi
  HKEY *v21; // rax
  int v22; // edi
  LPWSTR v23; // r9
  LPWSTR v24; // rax
  signed __int64 v25; // rdx
  WCHAR v26; // cx
  PVOID *v27; // r8
  unsigned int v28; // eax
  unsigned int v29; // edi
  PSECURITY_DESCRIPTOR v30; // [rsp+40h] [rbp-C0h] BYREF
  __int16 *pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  unsigned int v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+64h] [rbp-9Ch]
  char v36; // [rsp+6Ch] [rbp-94h]
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  void *v41[2]; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h]
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v46[4]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v47[4]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v48; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v49[64]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v50; // [rsp+170h] [rbp+70h]

  v42 = (LPWSTR)*((_QWORD *)a1 + 25);
  v43 = (__int64)(*((_QWORD *)a1 + 26) - (_QWORD)v42) >> 1;
  SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
    v49,
    &v42,
    *((unsigned __int8 *)a1 + 249),
    *((unsigned __int8 *)a1 + 248));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpValueName);
  v48 = v50;
  v5 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpValueName, &v48, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        (unsigned int)v5);
    }
    pExceptionObject = word_14003838A;
    v32 = 0;
    v33 = 0;
    v34 = v6;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v42 = (LPWSTR)*((_QWORD *)a1 + 25);
  v43 = (__int64)(*((_QWORD *)a1 + 26) - (_QWORD)v42) >> 1;
  v7 = IsSecurityChannel(&v42);
  v8 = (const WCHAR *)*((_QWORD *)a1 + 21);
  if ( v7 )
    v9 = (void **)tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get();
  else
    v9 = (void **)(tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get()
                 + 16);
  v10 = *v9;
  v41[0] = 0;
  v11 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(v41);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v8, 1u, v11, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, LastError, v13, 1124);
    throw (EvtException *)&pExceptionObject;
  }
  SecurityDescriptor = 0;
  cbData = TransformSDPermissions(
             v41[0],
             (__int64)&GenericMapping,
             (__int64)qword_14003A270,
             v10,
             v7,
             &SecurityDescriptor);
  v30 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
  AutoLoggerSecurityRegPath = RegistryPaths::GetAutoLoggerSecurityRegPath(v15, &v30, v47, v46);
  v17 = AutoLoggerSecurityRegPath;
  if ( AutoLoggerSecurityRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        AutoLoggerSecurityRegPath);
    }
    pExceptionObject = word_14003838A;
    v32 = 0;
    v33 = 0;
    v34 = v17;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  hkey = 0;
  v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  RegKey = CreateRegKey((HKEY)v30, v47[0], 0x20006u, 0, v18, 0, a3);
  v20 = RegKey;
  if ( RegKey )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, RegKey);
    }
    pExceptionObject = word_14003838A;
    v32 = 0;
    v33 = 0;
    v34 = v20;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  hKey = 0;
  v21 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  OpenRegKey((HKEY)v30, v46[0], 0x20019u, v21, a3);
  pcbData = 0;
  v30 = 0;
  RegReadByteArrayValueNoThrow(hkey, 0, lpValueName[0], &pcbData, (__int64)&v30);
  if ( !pcbData )
    goto LABEL_54;
  v22 = -1;
  StringSecurityDescriptor = 0;
  v42 = 0;
  ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 4u, &StringSecurityDescriptor, 0);
  ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 4u, &v42, 0);
  v23 = StringSecurityDescriptor;
  if ( StringSecurityDescriptor && v42 )
  {
    v24 = StringSecurityDescriptor;
    v25 = (char *)v42 - (char *)StringSecurityDescriptor;
    while ( 1 )
    {
      v26 = *v24;
      if ( *v24 != *(LPWSTR)((char *)v24 + v25) )
        break;
      ++v24;
      if ( !v26 )
      {
        v22 = 0;
        goto LABEL_38;
      }
    }
    v22 = v26 < *(LPWSTR)((char *)v24 + v25) ? -1 : 1;
LABEL_38:
    if ( v22 )
    {
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          *(_QWORD *)&v48 = *((_QWORD *)a1 + 25);
          *((_QWORD *)&v48 + 1) = (__int64)(*((_QWORD *)a1 + 26) - v48) >> 1;
          WPP_SF__utlwsv_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpValueName[0], (__int64)v42);
          v27 = (PVOID *)WPP_GLOBAL_Control;
          v23 = StringSecurityDescriptor;
        }
        if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 && *((_BYTE *)v27 + 25) >= 3u )
        {
          *(_QWORD *)&v48 = *((_QWORD *)a1 + 25);
          *((_QWORD *)&v48 + 1) = (__int64)(*((_QWORD *)a1 + 26) - v48) >> 1;
          WPP_SF__utlwsv_SS((TRACEHANDLE)v27[2], (__int64)lpValueName[0], (__int64)v23);
          v23 = StringSecurityDescriptor;
        }
      }
    }
  }
  LocalFree(v23);
  LocalFree(v42);
  if ( v22 )
  {
LABEL_54:
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v30);
    v28 = RegSetValueExW(hkey, lpValueName[0], 0, 3u, (const BYTE *)SecurityDescriptor, cbData);
    v29 = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v28);
      }
      pExceptionObject = word_14003838A;
      v32 = 0;
      v33 = 0;
      v34 = v29;
      v35 = -1;
      v36 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v30);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(v41);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpValueName);
  SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)v49);
}

```

## disassembly

```asm
0x1400151ec  mov     [rsp-8+arg_8], rbx
0x1400151f1  mov     [rsp-8+arg_18], rsi
0x1400151f6  push    rbp
0x1400151f7  push    rdi
0x1400151f8  push    r12
0x1400151fa  push    r14
0x1400151fc  push    r15
0x1400151fe  lea     rbp, [rsp-90h]
0x140015206  sub     rsp, 190h
0x14001520d  mov     rax, cs:__security_cookie
0x140015214  xor     rax, rsp
0x140015217  mov     [rbp+0B0h+var_30], rax
0x14001521e  mov     r15, r8
0x140015221  mov     rsi, rcx
0x140015224  mov     rax, [rcx+0C8h]
0x14001522b  mov     [rbp+0B0h+var_110], rax
0x14001522f  mov     rdx, [rcx+0D0h]
0x140015236  sub     rdx, rax
0x140015239  sar     rdx, 1
0x14001523c  mov     [rbp+0B0h+var_108], rdx
0x140015240  movzx   r9d, byte ptr [rcx+0F8h]
0x140015248  movzx   r8d, byte ptr [rcx+0F9h]
0x140015250  lea     rdx, [rbp+0B0h+var_110]
0x140015254  lea     rcx, [rbp+0B0h+var_80]
0x140015258  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x14001525d  nop
0x14001525e  lea     rcx, [rbp+0B0h+lpValueName]
0x140015262  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140015267  nop
0x140015268  movaps  xmm0, [rbp+0B0h+var_40]
0x14001526c  movdqu  [rbp+0B0h+var_98], xmm0
0x140015271  xor     r8d, r8d
0x140015274  lea     rdx, [rbp+0B0h+var_98]
0x140015278  lea     rcx, [rbp+0B0h+lpValueName]
0x14001527c  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x140015281  mov     edi, eax
0x140015283  xor     r12d, r12d
0x140015286  test    eax, eax
0x140015288  jns     short loc_1400152FB
0x14001528a  lea     rbx, WPP_GLOBAL_Control
0x140015291  mov     rcx, cs:WPP_GLOBAL_Control
0x140015298  cmp     rcx, rbx
0x14001529b  jz      short loc_1400152C1
0x14001529d  test    byte ptr [rcx+1Ch], 4
0x1400152a1  jz      short loc_1400152C1
0x1400152a3  cmp     byte ptr [rcx+19h], 2
0x1400152a7  jb      short loc_1400152C1
0x1400152a9  lea     edx, [r12+48h]
0x1400152ae  mov     r9d, eax
0x1400152b1  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x1400152b8  mov     rcx, [rcx+10h]
0x1400152bc  call    WPP_SF_d
0x1400152c1  lea     rax, word_14003838A
0x1400152c8  mov     [rsp+1B0h+pExceptionObject], rax
0x1400152cd  mov     [rsp+1B0h+var_160], r12
0x1400152d2  mov     [rsp+1B0h+var_158], r12
0x1400152d7  mov     [rsp+1B0h+var_150], edi
0x1400152db  mov     [rsp+1B0h+var_14C], 0FFFFFFFFFFFFFFFFh
0x1400152e4  mov     [rsp+1B0h+var_144], r12b
0x1400152e9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400152f0  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x1400152f5  call    _CxxThrowException_0
0x1400152fb  mov     rax, [rsi+0C8h]
0x140015302  mov     [rbp+0B0h+var_110], rax
0x140015306  mov     rcx, [rsi+0D0h]
0x14001530d  sub     rcx, rax
0x140015310  sar     rcx, 1
0x140015313  mov     [rbp+0B0h+var_108], rcx
0x140015317  lea     rcx, [rbp+0B0h+var_110]
0x14001531b  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140015320  mov     bl, al
0x140015322  mov     rdi, [rsi+0A8h]
0x140015329  test    al, al
0x14001532b  jz      short loc_140015334
0x14001532d  call    ?get@?$_LazyImpl@VLazySecurityBases@@V?$lazy_construct@VLazySecurityBases@@@tlx@@V?$static_lazy@VLazySecurityBases@@$0A@V?$lazy_construct@VLazySecurityBases@@@tlx@@@3@@tlx@@QEAAAEAVLazySecurityBases@@XZ; tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(void)
0x140015332  jmp     short loc_14001533D
0x140015334  call    ?get@?$_LazyImpl@VLazySecurityBases@@V?$lazy_construct@VLazySecurityBases@@@tlx@@V?$static_lazy@VLazySecurityBases@@$0A@V?$lazy_construct@VLazySecurityBases@@@tlx@@@3@@tlx@@QEAAAEAVLazySecurityBases@@XZ; tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(void)
0x140015339  add     rax, 10h
0x14001533d  mov     r14, [rax]
0x140015340  mov     [rbp+0B0h+var_120], r12
0x140015344  lea     rcx, [rbp+0B0h+var_120]
0x140015348  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x14001534d  xor     r9d, r9d; SecurityDescriptorSize
0x140015350  mov     r8, rax; SecurityDescriptor
0x140015353  lea     edx, [r9+1]; StringSDRevision
0x140015357  mov     rcx, rdi; StringSecurityDescriptor
0x14001535a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140015360  test    eax, eax
0x140015362  jnz     short loc_1400153D1
0x140015364  call    cs:__imp_GetLastError
0x14001536a  mov     edi, eax
0x14001536c  mov     eax, 507h
0x140015371  test    edi, edi
0x140015373  cmovz   edi, eax
0x140015376  lea     rbx, WPP_GLOBAL_Control
0x14001537d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015384  cmp     rcx, rbx
0x140015387  jz      short loc_1400153AD
0x140015389  test    byte ptr [rcx+1Ch], 4
0x14001538d  jz      short loc_1400153AD
0x14001538f  cmp     byte ptr [rcx+19h], 2
0x140015393  jb      short loc_1400153AD
0x140015395  mov     edx, 49h ; 'I'
0x14001539a  mov     r9d, edi
0x14001539d  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x1400153a4  mov     rcx, [rcx+10h]
0x1400153a8  call    WPP_SF_d
0x1400153ad  mov     r9d, 464h; int
0x1400153b3  mov     edx, edi; unsigned int
0x1400153b5  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x1400153ba  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400153bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400153c6  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x1400153cb  call    _CxxThrowException_0
0x1400153d1  mov     [rbp+0B0h+SecurityDescriptor], r12
0x1400153d5  lea     rax, [rbp+0B0h+SecurityDescriptor]
0x1400153d9  mov     qword ptr [rsp+1B0h+cbData], rax
0x1400153de  mov     byte ptr [rsp+1B0h+StringSecurityDescriptorLen], bl
0x1400153e2  mov     r9, r14
0x1400153e5  lea     r8, qword_14003A270
0x1400153ec  lea     rdx, GenericMapping
0x1400153f3  mov     rcx, [rbp+0B0h+var_120]
0x1400153f7  call    ?TransformSDPermissions@@YAKPEAXPEAU_GENERIC_MAPPING@@QEBK0_NAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; TransformSDPermissions(void *,_GENERIC_MAPPING *,ulong const * const,void *,bool,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1400153fc  mov     r14d, eax
0x1400153ff  mov     [rsp+1B0h+var_170], r12
0x140015404  lea     rcx, [rbp+0B0h+var_B8]
0x140015408  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001540d  nop
0x14001540e  lea     rcx, [rbp+0B0h+var_D8]
0x140015412  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140015417  nop
0x140015418  lea     r9, [rbp+0B0h+var_D8]
0x14001541c  lea     r8, [rbp+0B0h+var_B8]
0x140015420  lea     rdx, [rsp+1B0h+var_170]
0x140015425  call    ?GetAutoLoggerSecurityRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggerSecurityRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001542a  mov     edi, eax
0x14001542c  test    eax, eax
0x14001542e  jz      short loc_1400154A1
0x140015430  lea     rbx, WPP_GLOBAL_Control
0x140015437  mov     rcx, cs:WPP_GLOBAL_Control
0x14001543e  cmp     rcx, rbx
0x140015441  jz      short loc_140015467
0x140015443  test    byte ptr [rcx+1Ch], 4
0x140015447  jz      short loc_140015467
0x140015449  cmp     byte ptr [rcx+19h], 2
0x14001544d  jb      short loc_140015467
0x14001544f  mov     edx, 4Ah ; 'J'
0x140015454  mov     r9d, eax
0x140015457  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001545e  mov     rcx, [rcx+10h]
0x140015462  call    WPP_SF_d
0x140015467  lea     rax, word_14003838A
0x14001546e  mov     [rsp+1B0h+pExceptionObject], rax
0x140015473  mov     [rsp+1B0h+var_160], r12
0x140015478  mov     [rsp+1B0h+var_158], r12
0x14001547d  mov     [rsp+1B0h+var_150], edi
0x140015481  mov     [rsp+1B0h+var_14C], 0FFFFFFFFFFFFFFFFh
0x14001548a  mov     [rsp+1B0h+var_144], r12b
0x14001548f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015496  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x14001549b  call    _CxxThrowException_0
0x1400154a1  mov     [rsp+1B0h+hkey], r12
0x1400154a6  lea     rcx, [rsp+1B0h+hkey]
0x1400154ab  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400154b0  mov     [rsp+1B0h+var_180], r15; void *
0x1400154b5  mov     qword ptr [rsp+1B0h+cbData], r12; unsigned int *
0x1400154ba  mov     [rsp+1B0h+StringSecurityDescriptorLen], rax; HKEY *
0x1400154bf  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x1400154c2  mov     r8d, 20006h; unsigned int
0x1400154c8  mov     rdx, [rbp+0B0h+var_B8]; wchar_t *
0x1400154cc  mov     rcx, [rsp+1B0h+var_170]; HKEY
0x1400154d1  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x1400154d6  mov     edi, eax
0x1400154d8  test    eax, eax
0x1400154da  jz      short loc_14001554D
0x1400154dc  lea     rbx, WPP_GLOBAL_Control
0x1400154e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154ea  cmp     rcx, rbx
0x1400154ed  jz      short loc_140015513
0x1400154ef  test    byte ptr [rcx+1Ch], 4
0x1400154f3  jz      short loc_140015513
0x1400154f5  cmp     byte ptr [rcx+19h], 2
0x1400154f9  jb      short loc_140015513
0x1400154fb  mov     edx, 4Bh ; 'K'
0x140015500  mov     r9d, eax
0x140015503  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001550a  mov     rcx, [rcx+10h]
0x14001550e  call    WPP_SF_d
0x140015513  lea     rax, word_14003838A
0x14001551a  mov     [rsp+1B0h+pExceptionObject], rax
0x14001551f  mov     [rsp+1B0h+var_160], r12
0x140015524  mov     [rsp+1B0h+var_158], r12
0x140015529  mov     [rsp+1B0h+var_150], edi
0x14001552d  mov     [rsp+1B0h+var_14C], 0FFFFFFFFFFFFFFFFh
0x140015536  mov     [rsp+1B0h+var_144], r12b
0x14001553b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140015542  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x140015547  call    _CxxThrowException_0
0x14001554d  mov     [rbp+0B0h+hKey], r12
0x140015551  lea     rcx, [rbp+0B0h+hKey]
0x140015555  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001555a  mov     [rsp+1B0h+StringSecurityDescriptorLen], r15; void *
0x14001555f  mov     r9, rax; HKEY *
0x140015562  mov     r8d, 20019h; unsigned int
0x140015568  mov     rdx, [rbp+0B0h+var_D8]; wchar_t *
0x14001556c  mov     rcx, [rsp+1B0h+var_170]; HKEY
0x140015571  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140015576  mov     [rsp+1B0h+pcbData], r12d
0x14001557b  mov     [rsp+1B0h+var_170], r12
0x140015580  lea     rax, [rsp+1B0h+var_170]
0x140015585  mov     [rsp+1B0h+StringSecurityDescriptorLen], rax; __int64
0x14001558a  lea     r9, [rsp+1B0h+pcbData]; pcbData
0x14001558f  mov     r8, [rbp+0B0h+lpValueName]; lpValue
0x140015593  xor     edx, edx; lpSubKey
0x140015595  mov     rcx, [rsp+1B0h+hkey]; hkey
0x14001559a  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x14001559f  lea     rbx, WPP_GLOBAL_Control
0x1400155a6  cmp     [rsp+1B0h+pcbData], r12d
0x1400155ab  jz      loc_14001579D
0x1400155b1  or      edi, 0FFFFFFFFh
0x1400155b4  mov     [rbp+0B0h+StringSecurityDescriptor], r12
0x1400155b8  mov     [rbp+0B0h+var_110], r12
0x1400155bc  mov     [rsp+1B0h+StringSecurityDescriptorLen], r12; StringSecurityDescriptorLen
0x1400155c1  lea     r9, [rbp+0B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400155c5  lea     edx, [rdi+2]; RequestedStringSDRevision
0x1400155c8  lea     r8d, [rdi+5]; SecurityInformation
0x1400155cc  mov     rcx, [rbp+0B0h+SecurityDescriptor]; SecurityDescriptor
0x1400155d0  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1400155d6  mov     [rsp+1B0h+StringSecurityDescriptorLen], r12; StringSecurityDescriptorLen
0x1400155db  lea     r9, [rbp+0B0h+var_110]; StringSecurityDescriptor
0x1400155df  lea     edx, [rdi+2]; RequestedStringSDRevision
0x1400155e2  lea     r8d, [rdi+5]; SecurityInformation
0x1400155e6  mov     rcx, [rsp+1B0h+var_170]; SecurityDescriptor
0x1400155eb  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1400155f1  mov     r9, [rbp+0B0h+StringSecurityDescriptor]
0x1400155f5  test    r9, r9
0x1400155f8  jz      loc_1400156F0
0x1400155fe  mov     r10, [rbp+0B0h+var_110]
0x140015602  test    r10, r10
0x140015605  jz      loc_1400156F0
0x14001560b  mov     rax, r9
0x14001560e  mov     rdx, r10
0x140015611  sub     rdx, r9
0x140015614  movzx   ecx, word ptr [rax]
0x140015617  cmp     cx, [rax+rdx]
0x14001561b  jnz     short loc_14001562B
0x14001561d  add     rax, 2
0x140015621  test    cx, cx
0x140015624  jnz     short loc_140015614
0x140015626  mov     edi, r12d
0x140015629  jmp     short loc_140015630
0x14001562b  sbb     edi, edi
0x14001562d  or      edi, 1
0x140015630  test    edi, edi
0x140015632  jz      loc_1400156F0
0x140015638  mov     r8, cs:WPP_GLOBAL_Control
0x14001563f  cmp     r8, rbx
0x140015642  jz      loc_1400156F0
0x140015648  test    byte ptr [r8+1Ch], 4
0x14001564d  jz      short loc_14001569D
0x14001564f  cmp     byte ptr [r8+19h], 3
0x140015654  jb      short loc_14001569D
0x140015656  mov     rax, [rsi+0C8h]
0x14001565d  mov     qword ptr [rbp+0B0h+var_98], rax
0x140015661  mov     rdx, [rsi+0D0h]
0x140015668  sub     rdx, rax
0x14001566b  sar     rdx, 1
0x14001566e  mov     qword ptr [rbp+0B0h+var_98+8], rdx
0x140015672  mov     edx, 4Ch ; 'L'
0x140015677  mov     qword ptr [rsp+1B0h+cbData], r10; __int64
0x14001567c  mov     rax, [rbp+0B0h+lpValueName]
0x140015680  mov     [rsp+1B0h+StringSecurityDescriptorLen], rax; __int64
0x140015685  lea     r9, [rbp+0B0h+var_98]
0x140015689  mov     rcx, [r8+10h]; LoggerHandle
0x14001568d  call    WPP_SF__utlwsv_SS
0x140015692  mov     r8, cs:WPP_GLOBAL_Control
0x140015699  mov     r9, [rbp+0B0h+StringSecurityDescriptor]
0x14001569d  cmp     r8, rbx
0x1400156a0  jz      short loc_1400156F0
0x1400156a2  test    byte ptr [r8+1Ch], 4
0x1400156a7  jz      short loc_1400156F0
0x1400156a9  cmp     byte ptr [r8+19h], 3
0x1400156ae  jb      short loc_1400156F0
0x1400156b0  mov     rax, [rsi+0C8h]
0x1400156b7  mov     qword ptr [rbp+0B0h+var_98], rax
0x1400156bb  mov     rcx, [rsi+0D0h]
0x1400156c2  sub     rcx, rax
0x1400156c5  sar     rcx, 1
0x1400156c8  mov     qword ptr [rbp+0B0h+var_98+8], rcx
0x1400156cc  mov     edx, 4Dh ; 'M'
0x1400156d1  mov     qword ptr [rsp+1B0h+cbData], r9; __int64
0x1400156d6  mov     rax, [rbp+0B0h+lpValueName]
0x1400156da  mov     [rsp+1B0h+StringSecurityDescriptorLen], rax; __int64
0x1400156df  lea     r9, [rbp+0B0h+var_98]
0x1400156e3  mov     rcx, [r8+10h]; LoggerHandle
0x1400156e7  call    WPP_SF__utlwsv_SS
0x1400156ec  mov     r9, [rbp+0B0h+StringSecurityDescriptor]
0x1400156f0  mov     rcx, r9; hMem
0x1400156f3  call    cs:__imp_LocalFree
0x1400156f9  mov     rcx, [rbp+0B0h+var_110]; hMem
  ... truncated ...
```
