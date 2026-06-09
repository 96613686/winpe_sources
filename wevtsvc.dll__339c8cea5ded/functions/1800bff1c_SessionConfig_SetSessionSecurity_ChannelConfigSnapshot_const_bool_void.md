# SessionConfig::SetSessionSecurity(ChannelConfigSnapshot const &,bool,void *)

- ea: `0x1800bff1c`
- end: `0x1800c058b`
- name: `?SetSessionSecurity@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z`
- size: `1647`
- prototype: `void __fastcall(const struct ChannelConfigSnapshot *, bool, void *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059508`

## callees

- `0x180006600`
- `0x180006770`
- `0x180006fb0`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x180017e28`
- `0x18003a2c8`
- `0x18003e14c`
- `0x18003ee78`
- `0x180047fd8`
- `0x18005c2d4`
- `0x18005c600`
- `0x18006ea98`
- `0x180078b74`
- `0x180088720`
- `0x180092008`
- `0x18009aee0`
- `0x1800be1ec`
- `0x1800bff1c`
- `0x1800c07e0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c050e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c050e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0092`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0449`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0453`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0449`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0453`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c0088`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c0088`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c0324`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c0341`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c0324`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800c0341`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SessionConfig::SetSessionSecurity(const struct ChannelConfigSnapshot *a1, __int64 a2, void *a3)
{
  int v4; // eax
  int v5; // edi
  char v6; // bl
  const WCHAR *v7; // rdi
  void **v8; // rax
  void *v9; // rsi
  PSECURITY_DESCRIPTOR *v10; // rax
  DWORD LastError; // edi
  DWORD cbData; // r15d
  __int64 v13; // rcx
  DWORD AutoLoggerSecurityRegPath; // eax
  DWORD v15; // edi
  HKEY *v16; // rax
  struct _SECURITY_ATTRIBUTES *const v17; // r9
  unsigned int RegKey; // eax
  unsigned int v19; // esi
  HKEY *v20; // rax
  __int64 v21; // rdx
  int v22; // esi
  LPWSTR v23; // r9
  LPWSTR v24; // rax
  signed __int64 v25; // rdx
  WCHAR v26; // cx
  PVOID *v27; // r8
  unsigned int v28; // eax
  unsigned int v29; // esi
  PSECURITY_DESCRIPTOR v30; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h]
  DWORD v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  int v35; // [rsp+68h] [rbp-98h]
  char v36; // [rsp+6Ch] [rbp-94h]
  int v37; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  HKEY v41; // [rsp+90h] [rbp-70h] BYREF
  void *v42; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpValueName[4]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v46[4]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *v47[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v48; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v49[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v50; // [rsp+160h] [rbp+60h]

  v43 = (LPWSTR)*((_QWORD *)a1 + 25);
  v44 = (__int64)(*((_QWORD *)a1 + 26) - (_QWORD)v43) >> 1;
  SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
    v49,
    &v43,
    *((unsigned __int8 *)a1 + 249),
    *((unsigned __int8 *)a1 + 248));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpValueName);
  v48 = v50;
  v4 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpValueName, &v48, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        (unsigned int)v4);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v32 = 0;
    v33 = v5;
    v34 = -1;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v43 = (LPWSTR)*((_QWORD *)a1 + 25);
  v44 = (__int64)(*((_QWORD *)a1 + 26) - (_QWORD)v43) >> 1;
  v6 = IsSecurityChannel(&v43);
  v7 = (const WCHAR *)*((_QWORD *)a1 + 21);
  if ( v6 )
    v8 = (void **)tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get();
  else
    v8 = (void **)(tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get()
                 + 16);
  v9 = *v8;
  v42 = 0;
  v10 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>((__int64)&v42);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, v10, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v32 = 0;
    v33 = LastError;
    v34 = -1;
    v35 = 1124;
    throw (EvtException *)&pExceptionObject;
  }
  SecurityDescriptor = 0;
  cbData = TransformSDPermissions(
             v42,
             (struct _GENERIC_MAPPING *)qword_18010F698,
             (__int64)qword_1800F41F0,
             v9,
             v6,
             &SecurityDescriptor);
  v30 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
  AutoLoggerSecurityRegPath = RegistryPaths::GetAutoLoggerSecurityRegPath(v13, &v30, v47, v46);
  v15 = AutoLoggerSecurityRegPath;
  if ( AutoLoggerSecurityRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        AutoLoggerSecurityRegPath);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v32 = 0;
    v33 = v15;
    v34 = -1;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  hKey = 0;
  v16 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  RegKey = CreateRegKey((HKEY)v30, v47[0], 0x20006u, v17, v16, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
  v19 = RegKey;
  if ( RegKey )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, RegKey);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v32 = 0;
    v33 = v19;
    v34 = -1;
    v35 = -1;
    v36 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v41 = 0;
  v20 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v41);
  OpenRegKey((HKEY)v30, v46[0], 0x20019u, v20, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v37 = 0;
  v30 = 0;
  RegReadByteArrayValueWithFallbackNoThrow(hKey, v21, v41);
  if ( !v37 )
    goto LABEL_50;
  v22 = -1;
  StringSecurityDescriptor = 0;
  v43 = 0;
  ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 4u, &StringSecurityDescriptor, 0);
  ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 4u, &v43, 0);
  v23 = StringSecurityDescriptor;
  if ( StringSecurityDescriptor && v43 )
  {
    v24 = StringSecurityDescriptor;
    v25 = (char *)v43 - (char *)StringSecurityDescriptor;
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
          WPP_SF__utlwsv_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)lpValueName[0], (__int64)v43);
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
  LocalFree(v43);
  if ( v22 )
  {
LABEL_50:
    utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v30);
    v28 = RegSetValueExW(hKey, lpValueName[0], 0, 3u, (const BYTE *)SecurityDescriptor, cbData);
    v29 = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v28);
      }
      *(_QWORD *)&pExceptionObject = &byte_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v32 = 0;
      v33 = v29;
      v34 = -1;
      v35 = -1;
      v36 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v30);
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v41);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v42);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpValueName);
  utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v49);
}

```

## disassembly

```asm
0x1800bff1c  mov     [rsp-8+arg_8], rbx
0x1800bff21  mov     [rsp-8+arg_10], rsi
0x1800bff26  push    rbp
0x1800bff27  push    rdi
0x1800bff28  push    r12
0x1800bff2a  push    r14
0x1800bff2c  push    r15
0x1800bff2e  lea     rbp, [rsp-80h]
0x1800bff33  sub     rsp, 180h
0x1800bff3a  mov     rax, cs:__security_cookie
0x1800bff41  xor     rax, rsp
0x1800bff44  mov     [rbp+0A0h+var_30], rax
0x1800bff48  mov     r14, rcx
0x1800bff4b  mov     rax, [rcx+0C8h]
0x1800bff52  mov     [rbp+0A0h+var_100], rax
0x1800bff56  mov     rdx, [rcx+0D0h]
0x1800bff5d  sub     rdx, rax
0x1800bff60  sar     rdx, 1
0x1800bff63  mov     [rbp+0A0h+var_F8], rdx
0x1800bff67  movzx   r9d, byte ptr [rcx+0F8h]
0x1800bff6f  movzx   r8d, byte ptr [rcx+0F9h]
0x1800bff77  lea     rdx, [rbp+0A0h+var_100]
0x1800bff7b  lea     rcx, [rbp+0A0h+var_80]
0x1800bff7f  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x1800bff84  nop
0x1800bff85  lea     rcx, [rbp+0A0h+lpValueName]; void *
0x1800bff89  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bff8e  nop
0x1800bff8f  movaps  xmm0, [rbp+0A0h+var_40]
0x1800bff93  movdqu  [rbp+0A0h+var_90], xmm0
0x1800bff98  xor     r8d, r8d
0x1800bff9b  lea     rdx, [rbp+0A0h+var_90]
0x1800bff9f  lea     rcx, [rbp+0A0h+lpValueName]
0x1800bffa3  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x1800bffa8  mov     edi, eax
0x1800bffaa  xor     r12d, r12d
0x1800bffad  test    eax, eax
0x1800bffaf  jns     short loc_1800C0029
0x1800bffb1  lea     rbx, WPP_GLOBAL_Control
0x1800bffb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bffbf  cmp     rcx, rbx
0x1800bffc2  jz      short loc_1800BFFE8
0x1800bffc4  test    byte ptr [rcx+1Ch], 4
0x1800bffc8  jz      short loc_1800BFFE8
0x1800bffca  cmp     byte ptr [rcx+19h], 2
0x1800bffce  jb      short loc_1800BFFE8
0x1800bffd0  lea     edx, [r12+48h]
0x1800bffd5  mov     r9d, eax
0x1800bffd8  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800bffdf  mov     rcx, [rcx+10h]
0x1800bffe3  call    WPP_SF_d
0x1800bffe8  lea     rax, byte_1800EC961
0x1800bffef  mov     qword ptr [rsp+1A0h+pExceptionObject], rax
0x1800bfff4  mov     qword ptr [rsp+1A0h+pExceptionObject+8], r12
0x1800bfff9  mov     [rsp+1A0h+var_148], r12
0x1800bfffe  mov     [rsp+1A0h+var_140], edi
0x1800c0002  mov     [rsp+1A0h+var_13C], 0FFFFFFFFh
0x1800c000a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c000e  mov     [rsp+1A0h+var_138], edi
0x1800c0012  mov     [rsp+1A0h+var_134], r12b
0x1800c0017  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800c001e  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800c0023  call    _CxxThrowException_0
0x1800c0029  mov     rax, [r14+0C8h]
0x1800c0030  mov     [rbp+0A0h+var_100], rax
0x1800c0034  mov     rcx, [r14+0D0h]
0x1800c003b  sub     rcx, rax
0x1800c003e  sar     rcx, 1
0x1800c0041  mov     [rbp+0A0h+var_F8], rcx
0x1800c0045  lea     rcx, [rbp+0A0h+var_100]
0x1800c0049  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800c004e  mov     bl, al
0x1800c0050  mov     rdi, [r14+0A8h]
0x1800c0057  test    al, al
0x1800c0059  jz      short loc_1800C0062
0x1800c005b  call    ?get@?$_LazyImpl@VLazySecurityBases@@V?$lazy_construct@VLazySecurityBases@@@tlx@@V?$static_lazy@VLazySecurityBases@@$0A@V?$lazy_construct@VLazySecurityBases@@@tlx@@@3@@tlx@@QEAAAEAVLazySecurityBases@@XZ; tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(void)
0x1800c0060  jmp     short loc_1800C006B
0x1800c0062  call    ?get@?$_LazyImpl@VLazySecurityBases@@V?$lazy_construct@VLazySecurityBases@@@tlx@@V?$static_lazy@VLazySecurityBases@@$0A@V?$lazy_construct@VLazySecurityBases@@@tlx@@@3@@tlx@@QEAAAEAVLazySecurityBases@@XZ; tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(void)
0x1800c0067  add     rax, 10h
0x1800c006b  mov     rsi, [rax]
0x1800c006e  mov     [rbp+0A0h+var_108], r12
0x1800c0072  lea     rcx, [rbp+0A0h+var_108]
0x1800c0076  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1800c007b  xor     r9d, r9d; SecurityDescriptorSize
0x1800c007e  mov     r8, rax; SecurityDescriptor
0x1800c0081  lea     edx, [r9+1]; StringSDRevision
0x1800c0085  mov     rcx, rdi; StringSecurityDescriptor
0x1800c0088  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800c008e  test    eax, eax
0x1800c0090  jnz     short loc_1800C010F
0x1800c0092  call    cs:__imp_GetLastError
0x1800c0098  mov     edi, eax
0x1800c009a  mov     eax, 507h
0x1800c009f  test    edi, edi
0x1800c00a1  cmovz   edi, eax
0x1800c00a4  lea     rbx, WPP_GLOBAL_Control
0x1800c00ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c00b2  cmp     rcx, rbx
0x1800c00b5  jz      short loc_1800C00DB
0x1800c00b7  test    byte ptr [rcx+1Ch], 4
0x1800c00bb  jz      short loc_1800C00DB
0x1800c00bd  cmp     byte ptr [rcx+19h], 2
0x1800c00c1  jb      short loc_1800C00DB
0x1800c00c3  mov     edx, 49h ; 'I'
0x1800c00c8  mov     r9d, edi
0x1800c00cb  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800c00d2  mov     rcx, [rcx+10h]
0x1800c00d6  call    WPP_SF_d
0x1800c00db  xorps   xmm0, xmm0
0x1800c00de  movdqu  [rsp+1A0h+pExceptionObject], xmm0
0x1800c00e4  mov     [rsp+1A0h+var_148], r12
0x1800c00e9  mov     [rsp+1A0h+var_140], edi
0x1800c00ed  mov     [rsp+1A0h+var_13C], 0FFFFFFFFh
0x1800c00f5  mov     [rsp+1A0h+var_138], 464h
0x1800c00fd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800c0104  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800c0109  call    _CxxThrowException_0
0x1800c010f  mov     [rbp+0A0h+SecurityDescriptor], r12
0x1800c0113  lea     rax, [rbp+0A0h+SecurityDescriptor]
0x1800c0117  mov     qword ptr [rsp+1A0h+cbData], rax
0x1800c011c  mov     byte ptr [rsp+1A0h+StringSecurityDescriptorLen], bl
0x1800c0120  mov     r9, rsi
0x1800c0123  lea     r8, qword_1800F41F0
0x1800c012a  lea     rdx, qword_18010F698
0x1800c0131  mov     rcx, [rbp+0A0h+var_108]
0x1800c0135  call    ?TransformSDPermissions@@YAKPEAXPEAU_GENERIC_MAPPING@@QEBK0_NAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; TransformSDPermissions(void *,_GENERIC_MAPPING *,ulong const * const,void *,bool,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1800c013a  mov     r15d, eax
0x1800c013d  mov     [rsp+1A0h+var_160], r12
0x1800c0142  lea     rcx, [rbp+0A0h+var_B0]; void *
0x1800c0146  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c014b  nop
0x1800c014c  lea     rcx, [rbp+0A0h+var_D0]; void *
0x1800c0150  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c0155  nop
0x1800c0156  lea     r9, [rbp+0A0h+var_D0]
0x1800c015a  lea     r8, [rbp+0A0h+var_B0]
0x1800c015e  lea     rdx, [rsp+1A0h+var_160]
0x1800c0163  call    ?GetAutoLoggerSecurityRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggerSecurityRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800c0168  mov     edi, eax
0x1800c016a  test    eax, eax
0x1800c016c  jz      short loc_1800C01E6
0x1800c016e  lea     rbx, WPP_GLOBAL_Control
0x1800c0175  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c017c  cmp     rcx, rbx
0x1800c017f  jz      short loc_1800C01A5
0x1800c0181  test    byte ptr [rcx+1Ch], 4
0x1800c0185  jz      short loc_1800C01A5
0x1800c0187  cmp     byte ptr [rcx+19h], 2
0x1800c018b  jb      short loc_1800C01A5
0x1800c018d  mov     edx, 4Ah ; 'J'
0x1800c0192  mov     r9d, eax
0x1800c0195  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800c019c  mov     rcx, [rcx+10h]
0x1800c01a0  call    WPP_SF_d
0x1800c01a5  lea     rax, byte_1800EC961
0x1800c01ac  mov     qword ptr [rsp+1A0h+pExceptionObject], rax
0x1800c01b1  mov     qword ptr [rsp+1A0h+pExceptionObject+8], r12
0x1800c01b6  mov     [rsp+1A0h+var_148], r12
0x1800c01bb  mov     [rsp+1A0h+var_140], edi
0x1800c01bf  mov     [rsp+1A0h+var_13C], 0FFFFFFFFh
0x1800c01c7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c01cb  mov     [rsp+1A0h+var_138], edi
0x1800c01cf  mov     [rsp+1A0h+var_134], r12b
0x1800c01d4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800c01db  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800c01e0  call    _CxxThrowException_0
0x1800c01e6  mov     [rsp+1A0h+hKey], r12
0x1800c01eb  lea     rcx, [rsp+1A0h+hKey]
0x1800c01f0  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c01f5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c01f9  mov     [rsp+1A0h+var_170], rdi; void *
0x1800c01fe  mov     qword ptr [rsp+1A0h+cbData], r12; unsigned int *
0x1800c0203  mov     [rsp+1A0h+StringSecurityDescriptorLen], rax; HKEY *
0x1800c0208  mov     r8d, 20006h; unsigned int
0x1800c020e  mov     rdx, [rbp+0A0h+var_B0]; wchar_t *
0x1800c0212  mov     rcx, [rsp+1A0h+var_160]; HKEY
0x1800c0217  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x1800c021c  mov     esi, eax
0x1800c021e  test    eax, eax
0x1800c0220  jz      short loc_1800C0294
0x1800c0222  lea     rbx, WPP_GLOBAL_Control
0x1800c0229  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0230  cmp     rcx, rbx
0x1800c0233  jz      short loc_1800C0257
0x1800c0235  test    byte ptr [rcx+1Ch], 4
0x1800c0239  jz      short loc_1800C0257
0x1800c023b  cmp     byte ptr [rcx+19h], 2
0x1800c023f  jb      short loc_1800C0257
0x1800c0241  lea     edx, [rdi+4Ch]
0x1800c0244  mov     r9d, eax
0x1800c0247  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800c024e  mov     rcx, [rcx+10h]
0x1800c0252  call    WPP_SF_d
0x1800c0257  lea     rax, byte_1800EC961
0x1800c025e  mov     qword ptr [rsp+1A0h+pExceptionObject], rax
0x1800c0263  mov     qword ptr [rsp+1A0h+pExceptionObject+8], r12
0x1800c0268  mov     [rsp+1A0h+var_148], r12
0x1800c026d  mov     [rsp+1A0h+var_140], esi
0x1800c0271  mov     [rsp+1A0h+var_13C], 0FFFFFFFFh
0x1800c0279  mov     [rsp+1A0h+var_138], edi
0x1800c027d  mov     [rsp+1A0h+var_134], r12b
0x1800c0282  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800c0289  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800c028e  call    _CxxThrowException_0
0x1800c0294  mov     [rbp+0A0h+var_110], r12
0x1800c0298  lea     rcx, [rbp+0A0h+var_110]
0x1800c029c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c02a1  mov     [rsp+1A0h+StringSecurityDescriptorLen], rdi; void *
0x1800c02a6  mov     r9, rax; HKEY *
0x1800c02a9  mov     r8d, 20019h; unsigned int
0x1800c02af  mov     rdx, [rbp+0A0h+var_D0]; wchar_t *
0x1800c02b3  mov     rcx, [rsp+1A0h+var_160]; HKEY
0x1800c02b8  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1800c02bd  mov     [rsp+1A0h+var_130], r12d
0x1800c02c2  mov     [rsp+1A0h+var_160], r12
0x1800c02c7  lea     rax, [rsp+1A0h+var_160]
0x1800c02cc  mov     [rsp+1A0h+var_170], rax
0x1800c02d1  lea     rax, [rsp+1A0h+var_130]
0x1800c02d6  mov     qword ptr [rsp+1A0h+cbData], rax
0x1800c02db  mov     rax, [rbp+0A0h+lpValueName]
0x1800c02df  mov     [rsp+1A0h+StringSecurityDescriptorLen], rax
0x1800c02e4  mov     r8, [rbp+0A0h+var_110]
0x1800c02e8  mov     rcx, [rsp+1A0h+hKey]
0x1800c02ed  call    ?RegReadByteArrayValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x1800c02f2  lea     rbx, WPP_GLOBAL_Control
0x1800c02f9  cmp     [rsp+1A0h+var_130], r12d
0x1800c02fe  jz      loc_1800C04E4
0x1800c0304  mov     esi, edi
0x1800c0306  mov     [rbp+0A0h+StringSecurityDescriptor], r12
0x1800c030a  mov     [rbp+0A0h+var_100], r12
0x1800c030e  mov     [rsp+1A0h+StringSecurityDescriptorLen], r12; StringSecurityDescriptorLen
0x1800c0313  lea     r9, [rbp+0A0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800c0317  mov     edx, 1; RequestedStringSDRevision
0x1800c031c  lea     r8d, [rdx+3]; SecurityInformation
0x1800c0320  mov     rcx, [rbp+0A0h+SecurityDescriptor]; SecurityDescriptor
0x1800c0324  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800c032a  mov     [rsp+1A0h+StringSecurityDescriptorLen], r12; StringSecurityDescriptorLen
0x1800c032f  lea     r9, [rbp+0A0h+var_100]; StringSecurityDescriptor
0x1800c0333  mov     edx, 1; RequestedStringSDRevision
0x1800c0338  lea     r8d, [rdx+3]; SecurityInformation
0x1800c033c  mov     rcx, [rsp+1A0h+var_160]; SecurityDescriptor
0x1800c0341  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800c0347  mov     r9, [rbp+0A0h+StringSecurityDescriptor]
0x1800c034b  test    r9, r9
0x1800c034e  jz      loc_1800C0446
0x1800c0354  mov     r10, [rbp+0A0h+var_100]
0x1800c0358  test    r10, r10
0x1800c035b  jz      loc_1800C0446
0x1800c0361  mov     rax, r9
0x1800c0364  mov     rdx, r10
0x1800c0367  sub     rdx, r9
0x1800c036a  movzx   ecx, word ptr [rax]
0x1800c036d  cmp     cx, [rax+rdx]
0x1800c0371  jnz     short loc_1800C0381
0x1800c0373  add     rax, 2
0x1800c0377  test    cx, cx
0x1800c037a  jnz     short loc_1800C036A
0x1800c037c  mov     esi, r12d
0x1800c037f  jmp     short loc_1800C0386
0x1800c0381  sbb     esi, esi
0x1800c0383  or      esi, 1
0x1800c0386  test    esi, esi
0x1800c0388  jz      loc_1800C0446
0x1800c038e  mov     r8, cs:WPP_GLOBAL_Control
0x1800c0395  cmp     r8, rbx
0x1800c0398  jz      loc_1800C0446
0x1800c039e  test    byte ptr [r8+1Ch], 4
0x1800c03a3  jz      short loc_1800C03F3
0x1800c03a5  cmp     byte ptr [r8+19h], 3
0x1800c03aa  jb      short loc_1800C03F3
0x1800c03ac  mov     rax, [r14+0C8h]
0x1800c03b3  mov     qword ptr [rbp+0A0h+var_90], rax
0x1800c03b7  mov     rdx, [r14+0D0h]
0x1800c03be  sub     rdx, rax
0x1800c03c1  sar     rdx, 1
0x1800c03c4  mov     qword ptr [rbp+0A0h+var_90+8], rdx
0x1800c03c8  mov     edx, 4Ch ; 'L'
0x1800c03cd  mov     qword ptr [rsp+1A0h+cbData], r10; __int64
0x1800c03d2  mov     rax, [rbp+0A0h+lpValueName]
0x1800c03d6  mov     [rsp+1A0h+StringSecurityDescriptorLen], rax; __int64
0x1800c03db  lea     r9, [rbp+0A0h+var_90]
0x1800c03df  mov     rcx, [r8+10h]; LoggerHandle
0x1800c03e3  call    WPP_SF__utlwsv_SS
0x1800c03e8  mov     r8, cs:WPP_GLOBAL_Control
0x1800c03ef  mov     r9, [rbp+0A0h+StringSecurityDescriptor]
0x1800c03f3  cmp     r8, rbx
0x1800c03f6  jz      short loc_1800C0446
0x1800c03f8  test    byte ptr [r8+1Ch], 4
0x1800c03fd  jz      short loc_1800C0446
0x1800c03ff  cmp     byte ptr [r8+19h], 3
0x1800c0404  jb      short loc_1800C0446
0x1800c0406  mov     rax, [r14+0C8h]
0x1800c040d  mov     qword ptr [rbp+0A0h+var_90], rax
0x1800c0411  mov     rcx, [r14+0D0h]
0x1800c0418  sub     rcx, rax
0x1800c041b  sar     rcx, 1
0x1800c041e  mov     qword ptr [rbp+0A0h+var_90+8], rcx
0x1800c0422  mov     edx, 4Dh ; 'M'
0x1800c0427  mov     qword ptr [rsp+1A0h+cbData], r9; __int64
0x1800c042c  mov     rax, [rbp+0A0h+lpValueName]
  ... truncated ...
```
