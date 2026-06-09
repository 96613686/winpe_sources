# EventSession::UpdateProviderFromAutologgerSettings(_GUID)

- ea: `0x180074eb8`
- end: `0x1800752be`
- name: `?UpdateProviderFromAutologgerSettings@EventSession@@QEAAXU_GUID@@@Z`
- size: `1030`
- prototype: `void __fastcall(EventSession *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000349c`
- `0x180074e04`

## callees

- `0x180004a3c`
- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x18002afa8`
- `0x18002ed28`
- `0x18003d394`
- `0x1800587c8`
- `0x18006c0a4`
- `0x180071db8`
- `0x180074eb8`
- `0x18008df50`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074ff5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074f9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007505b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074f9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007505b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EventSession::UpdateProviderFromAutologgerSettings(HKEY *this, struct _GUID *a2)
{
  __int64 v4; // rcx
  int AutoLoggersRegPath; // eax
  int v6; // ebx
  LSTATUS v7; // eax
  HKEY *v8; // rax
  __int64 v9; // r8
  bool v10; // bl
  unsigned __int8 v11; // r14
  ULONGLONG v12; // rax
  ULONGLONG v13; // rcx
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v15; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v18; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+9Ch] [rbp-64h]
  char v26; // [rsp+A4h] [rbp-5Ch]
  wchar_t *v27[4]; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v29; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR v30[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v31; // [rsp+F8h] [rbp-8h] BYREF

  hKey[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v30);
  AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v4, hKey, lpSubKey, v30);
  v6 = AutoLoggersRegPath;
  if ( AutoLoggersRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids,
        (unsigned int)AutoLoggersRegPath);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v23 = 0;
    v24 = v6;
    v25 = -1;
    v26 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  phkResult = 0;
  v7 = RegOpenKeyExW(hKey[0], lpSubKey[0], 0, 0x20019u, &phkResult);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids,
        lpSubKey[0],
        v7);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( (char *)v30[0] != &v31 )
      operator delete((void *)v30[0]);
    if ( (char *)lpSubKey[0] != &v29 )
      operator delete((void *)lpSubKey[0]);
  }
  else
  {
    v15 = 0;
    v8 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v15);
    RegOpenKeyExW(hKey[0], v30[0], 0, 0x20019u, v8);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v27);
    hKey[0] = this[2];
    hKey[1] = (HKEY)(((char *)this[3] - (char *)hKey[0]) >> 1);
    AssignOrThrowOOM(v27, hKey);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v27,
                             92)
      || (v10 = 1,
          LOBYTE(v9) = 1,
          (int)tlx::_AppendGuid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                 v27,
                 a2,
                 v9) < 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids, 14);
      }
      pExceptionObject = 0;
      v23 = 0;
      v24 = 14;
      v25 = 0x191FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v16 = 0;
    RegReadDWORDValueWithFallbackNoThrow(phkResult, v27[0], v15, v27[0], L"Enabled", &v16);
    v11 = v16 == 1;
    v18 = 0;
    RegReadDWORDValueWithFallbackNoThrow(phkResult, v27[0], v15, v27[0], L"EnableLevel", &v18);
    v17 = 0;
    v19 = 0;
    v20 = 0;
    if ( RegReadDWORDValueWithFallbackNoThrow(phkResult, v27[0], v15, v27[0], L"EnableFlags", &v17) )
    {
      v10 = 0;
      v19 = 0;
      RegReadQWORDValueWithFallbackNoThrow(phkResult, v27[0], v15, v27[0], L"MatchAnyKeyword", &v19);
      v20 = 0;
      RegReadQWORDValueWithFallbackNoThrow(phkResult, v27[0], v15, v27[0], L"MatchAllKeyword", &v20);
      v13 = v19;
      v12 = v20;
    }
    else
    {
      v12 = 0;
      v20 = 0;
      v13 = v17;
      v19 = v17;
    }
    *(struct _GUID *)hKey = *a2;
    EventSession::Enable((EventSession *)this, (LPCGUID)hKey, v11, v18, v13, v12, v10);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v27);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v15);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&phkResult);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v30);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  }
}

```

## disassembly

```asm
0x180074eb8  mov     [rsp-8+arg_10], rbx
0x180074ebd  push    rbp
0x180074ebe  push    rsi
0x180074ebf  push    rdi
0x180074ec0  push    r14
0x180074ec2  push    r15
0x180074ec4  lea     rbp, [rsp-10h]
0x180074ec9  sub     rsp, 110h
0x180074ed0  mov     rdi, rdx
0x180074ed3  mov     rsi, rcx
0x180074ed6  xor     r15d, r15d
0x180074ed9  mov     [rsp+130h+hKey], r15
0x180074ede  lea     rcx, [rbp+30h+lpSubKey]; void *
0x180074ee2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180074ee7  nop
0x180074ee8  lea     rcx, [rbp+30h+var_48]; void *
0x180074eec  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180074ef1  nop
0x180074ef2  lea     r9, [rbp+30h+var_48]
0x180074ef6  lea     r8, [rbp+30h+lpSubKey]
0x180074efa  lea     rdx, [rsp+130h+hKey]
0x180074eff  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180074f04  mov     ebx, eax
0x180074f06  test    eax, eax
0x180074f08  jns     short loc_180074F78
0x180074f0a  lea     rcx, WPP_GLOBAL_Control
0x180074f11  mov     r10, cs:WPP_GLOBAL_Control
0x180074f18  cmp     r10, rcx
0x180074f1b  jz      short loc_180074F45
0x180074f1d  test    dword ptr [r10+1Ch], 4000000h
0x180074f25  jz      short loc_180074F45
0x180074f27  cmp     byte ptr [r10+19h], 2
0x180074f2c  jb      short loc_180074F45
0x180074f2e  lea     edx, [r15+1Dh]
0x180074f32  mov     r9d, eax
0x180074f35  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x180074f3c  mov     rcx, [r10+10h]
0x180074f40  call    WPP_SF_d
0x180074f45  lea     rax, byte_1800EC961
0x180074f4c  mov     qword ptr [rbp+30h+pExceptionObject], rax
0x180074f50  mov     qword ptr [rbp+30h+pExceptionObject+8], r15
0x180074f54  mov     [rbp+30h+var_A0], r15
0x180074f58  mov     [rbp+30h+var_98], ebx
0x180074f5b  mov     [rbp+30h+var_94], 0FFFFFFFFFFFFFFFFh
0x180074f63  mov     [rbp+30h+var_8C], r15b
0x180074f67  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180074f6e  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180074f72  call    _CxxThrowException_0
0x180074f78  mov     [rsp+130h+var_F0], r15
0x180074f7d  lea     rax, [rsp+130h+var_F0]
0x180074f82  mov     [rsp+130h+phkResult], rax; phkResult
0x180074f87  mov     ebx, 20019h
0x180074f8c  mov     r9d, ebx; samDesired
0x180074f8f  xor     r8d, r8d; ulOptions
0x180074f92  mov     rdx, [rbp+30h+lpSubKey]; lpSubKey
0x180074f96  mov     rcx, [rsp+130h+hKey]; hKey
0x180074f9b  call    cs:__imp_RegOpenKeyExW
0x180074fa1  test    eax, eax
0x180074fa3  jz      loc_180075038
0x180074fa9  lea     rcx, WPP_GLOBAL_Control
0x180074fb0  mov     r10, cs:WPP_GLOBAL_Control
0x180074fb7  cmp     r10, rcx
0x180074fba  jz      short loc_180074FEB
0x180074fbc  test    dword ptr [r10+1Ch], 4000000h
0x180074fc4  jz      short loc_180074FEB
0x180074fc6  cmp     byte ptr [r10+19h], 3
0x180074fcb  jb      short loc_180074FEB
0x180074fcd  mov     edx, 1Eh
0x180074fd2  mov     dword ptr [rsp+130h+phkResult], eax
0x180074fd6  mov     r9, [rbp+30h+lpSubKey]
0x180074fda  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x180074fe1  mov     rcx, [r10+10h]
0x180074fe5  call    WPP_SF_Sd
0x180074fea  nop
0x180074feb  mov     rcx, [rsp+130h+var_F0]; hKey
0x180074ff0  test    rcx, rcx
0x180074ff3  jz      short loc_180074FFC
0x180074ff5  call    cs:__imp_RegCloseKey
0x180074ffb  nop
0x180074ffc  lea     rax, [rbp+30h+var_38]
0x180075000  mov     rcx, [rbp+30h+var_48]; void *
0x180075004  cmp     rcx, rax
0x180075007  jz      short loc_18007500F
0x180075009  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007500e  nop
0x18007500f  lea     rax, [rbp+30h+var_58]
0x180075013  mov     rcx, [rbp+30h+lpSubKey]; void *
0x180075017  cmp     rcx, rax
0x18007501a  jz      short loc_180075021
0x18007501c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075021  mov     rbx, [rsp+130h+arg_10]
0x180075029  add     rsp, 110h
0x180075030  pop     r15
0x180075032  pop     r14
0x180075034  pop     rdi
0x180075035  pop     rsi
0x180075036  pop     rbp
0x180075037  retn
0x180075038  mov     [rsp+130h+var_E8], r15
0x18007503d  lea     rcx, [rsp+130h+var_E8]
0x180075042  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180075047  mov     [rsp+130h+phkResult], rax; phkResult
0x18007504c  mov     r9d, ebx; samDesired
0x18007504f  xor     r8d, r8d; ulOptions
0x180075052  mov     rdx, [rbp+30h+var_48]; lpSubKey
0x180075056  mov     rcx, [rsp+130h+hKey]; hKey
0x18007505b  call    cs:__imp_RegOpenKeyExW
0x180075061  lea     rcx, [rbp+30h+var_88]; void *
0x180075065  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007506a  nop
0x18007506b  mov     rax, [rsi+10h]
0x18007506f  mov     [rsp+130h+hKey], rax
0x180075074  mov     rcx, [rsi+18h]
0x180075078  sub     rcx, rax
0x18007507b  sar     rcx, 1
0x18007507e  mov     [rsp+130h+hKey+8], rcx
0x180075083  lea     rdx, [rsp+130h+hKey]
0x180075088  lea     rcx, [rbp+30h+var_88]
0x18007508c  call    ?AssignOrThrowOOM@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; AssignOrThrowOOM(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180075091  mov     edx, 5Ch ; '\'
0x180075096  lea     rcx, [rbp+30h+var_88]
0x18007509a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18007509f  test    al, al
0x1800750a1  jz      loc_180075253
0x1800750a7  mov     ebx, 1
0x1800750ac  mov     r8b, bl
0x1800750af  mov     rdx, rdi
0x1800750b2  lea     rcx, [rbp+30h+var_88]
0x1800750b6  call    ??$_AppendGuid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::_AppendGuid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x1800750bb  test    eax, eax
0x1800750bd  js      loc_180075253
0x1800750c3  mov     [rsp+130h+var_E0], r15d
0x1800750c8  lea     rax, [rsp+130h+var_E0]
0x1800750cd  mov     [rsp+130h+var_108], rax; unsigned int *
0x1800750d2  lea     rax, aEnabled; "Enabled"
0x1800750d9  mov     [rsp+130h+phkResult], rax; wchar_t *
0x1800750de  mov     rdx, [rbp+30h+var_88]; wchar_t *
0x1800750e2  mov     r9, rdx; wchar_t *
0x1800750e5  mov     r8, [rsp+130h+var_E8]; HKEY
0x1800750ea  mov     rcx, [rsp+130h+var_F0]; HKEY
0x1800750ef  call    ?RegReadDWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEAK@Z; RegReadDWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800750f4  cmp     [rsp+130h+var_E0], ebx
0x1800750f8  setz    r14b
0x1800750fc  mov     dword ptr [rsp+130h+var_DC+4], r15d
0x180075101  lea     rax, [rsp+130h+var_DC+4]
0x180075106  mov     [rsp+130h+var_108], rax; unsigned int *
0x18007510b  lea     rax, aEnablelevel; "EnableLevel"
0x180075112  mov     [rsp+130h+phkResult], rax; wchar_t *
0x180075117  mov     rdx, [rbp+30h+var_88]; wchar_t *
0x18007511b  mov     r9, rdx; wchar_t *
0x18007511e  mov     r8, [rsp+130h+var_E8]; HKEY
0x180075123  mov     rcx, [rsp+130h+var_F0]; HKEY
0x180075128  call    ?RegReadDWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEAK@Z; RegReadDWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18007512d  mov     dword ptr [rsp+130h+var_DC], r15d
0x180075132  mov     [rsp+130h+var_D0], r15
0x180075137  mov     [rsp+130h+var_C8], r15
0x18007513c  mov     rdx, [rbp+30h+var_88]; wchar_t *
0x180075140  lea     rax, [rsp+130h+var_DC]
0x180075145  mov     [rsp+130h+var_108], rax; unsigned int *
0x18007514a  lea     rax, aEnableflags; "EnableFlags"
0x180075151  mov     [rsp+130h+phkResult], rax; wchar_t *
0x180075156  mov     r9, rdx; wchar_t *
0x180075159  mov     r8, [rsp+130h+var_E8]; HKEY
0x18007515e  mov     rcx, [rsp+130h+var_F0]; HKEY
0x180075163  call    ?RegReadDWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEAK@Z; RegReadDWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x180075168  test    eax, eax
0x18007516a  jnz     short loc_18007517F
0x18007516c  mov     rax, r15
0x18007516f  mov     [rsp+130h+var_C8], rax
0x180075174  mov     ecx, dword ptr [rsp+130h+var_DC]
0x180075178  mov     [rsp+130h+var_D0], rcx
0x18007517d  jmp     short loc_1800751EE
0x18007517f  mov     bl, r15b
0x180075182  mov     [rsp+130h+var_D0], r15
0x180075187  lea     rax, [rsp+130h+var_D0]
0x18007518c  mov     [rsp+130h+var_108], rax; unsigned __int64 *
0x180075191  lea     rax, aMatchanykeywor; "MatchAnyKeyword"
0x180075198  mov     [rsp+130h+phkResult], rax; wchar_t *
0x18007519d  mov     rdx, [rbp+30h+var_88]; wchar_t *
0x1800751a1  mov     r9, rdx; wchar_t *
0x1800751a4  mov     r8, [rsp+130h+var_E8]; HKEY
0x1800751a9  mov     rcx, [rsp+130h+var_F0]; HKEY
0x1800751ae  call    ?RegReadQWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEA_K@Z; RegReadQWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 &)
0x1800751b3  mov     [rsp+130h+var_C8], r15
0x1800751b8  lea     rax, [rsp+130h+var_C8]
0x1800751bd  mov     [rsp+130h+var_108], rax; unsigned __int64 *
0x1800751c2  lea     rax, aMatchallkeywor; "MatchAllKeyword"
0x1800751c9  mov     [rsp+130h+phkResult], rax; wchar_t *
0x1800751ce  mov     rdx, [rbp+30h+var_88]; wchar_t *
0x1800751d2  mov     r9, rdx; wchar_t *
0x1800751d5  mov     r8, [rsp+130h+var_E8]; HKEY
0x1800751da  mov     rcx, [rsp+130h+var_F0]; HKEY
0x1800751df  call    ?RegReadQWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEA_K@Z; RegReadQWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 &)
0x1800751e4  mov     rcx, [rsp+130h+var_D0]
0x1800751e9  mov     rax, [rsp+130h+var_C8]
0x1800751ee  movaps  xmm0, xmmword ptr [rdi]
0x1800751f1  movdqa  xmmword ptr [rsp+130h+hKey], xmm0
0x1800751f7  mov     [rsp+130h+var_100], bl; bool
0x1800751fb  mov     [rsp+130h+var_108], rax; unsigned __int64
0x180075200  mov     [rsp+130h+phkResult], rcx; ULONGLONG
0x180075205  mov     r9d, dword ptr [rsp+130h+var_DC+4]; unsigned int
0x18007520a  mov     r8b, r14b; bool
0x18007520d  lea     rdx, [rsp+130h+hKey]; ProviderId
0x180075212  mov     rcx, rsi; this
0x180075215  call    ?Enable@EventSession@@QEAAXU_GUID@@_NK_K21@Z; EventSession::Enable(_GUID,bool,ulong,unsigned __int64,unsigned __int64,bool)
0x18007521a  nop
0x18007521b  lea     rcx, [rbp+30h+var_88]; void *
0x18007521f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180075224  nop
0x180075225  lea     rcx, [rsp+130h+var_E8]
0x18007522a  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007522f  nop
0x180075230  lea     rcx, [rsp+130h+var_F0]
0x180075235  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007523a  nop
0x18007523b  lea     rcx, [rbp+30h+var_48]; void *
0x18007523f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180075244  nop
0x180075245  lea     rcx, [rbp+30h+lpSubKey]; void *
0x180075249  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007524e  jmp     loc_180075021
0x180075253  lea     rcx, WPP_GLOBAL_Control
0x18007525a  mov     ebx, 0Eh
0x18007525f  mov     rax, cs:WPP_GLOBAL_Control
0x180075266  cmp     rax, rcx
0x180075269  jz      short loc_180075290
0x18007526b  test    dword ptr [rax+1Ch], 4000000h
0x180075272  jz      short loc_180075290
0x180075274  cmp     byte ptr [rax+19h], 2
0x180075278  jb      short loc_180075290
0x18007527a  lea     edx, [rbx+11h]
0x18007527d  mov     r9d, ebx
0x180075280  lea     r8, WPP_8b676d1c72cc33de7c97defb2afc7016_Traceguids
0x180075287  mov     rcx, [rax+10h]
0x18007528b  call    WPP_SF_d
0x180075290  xorps   xmm0, xmm0
0x180075293  movdqu  [rbp+30h+pExceptionObject], xmm0
0x180075298  mov     [rbp+30h+var_A0], r15
0x18007529c  mov     [rbp+30h+var_98], ebx
0x18007529f  mov     dword ptr [rbp+30h+var_94], 0FFFFFFFFh
0x1800752a6  mov     dword ptr [rbp+30h+var_94+4], 191h
0x1800752ad  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800752b4  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x1800752b8  call    _CxxThrowException_0
```
