# PolicyManager::Update(utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800abd88`
- end: `0x1800ac194`
- name: `?Update@PolicyManager@@AEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `1036`
- prototype: `void __fastcall(_BYTE *, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800775e0`
- `0x1800aab70`
- `0x1800ab458`

## callees

- `0x180006770`
- `0x18000bc0c`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18002d6dc`
- `0x18006c144`
- `0x180083b84`
- `0x180092008`
- `0x180092ee4`
- `0x180095464`
- `0x1800a6ac0`
- `0x1800a9f14`
- `0x1800abd88`
- `0x1800ac724`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abe2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abf64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abe2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abf64`
- `USERENV!LeaveCriticalPolicySection` at `0x1800ac114`
- `USERENV!LeaveCriticalPolicySection` at `0x1800ac114`
- `USERENV!EnterCriticalPolicySection` at `0x1800abdf8`
- `USERENV!EnterCriticalPolicySection` at `0x1800abdf8`

## string_xrefs

- `0x1800abf80`: `EnableRemoteRpcAccessRestrictions`
- `0x1800abfb1`: `RpcAccess_Remote_Setting`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PolicyManager::Update(_BYTE *a1, __int64 a2)
{
  HANDLE v4; // rsi
  HKEY *v5; // rax
  __int64 v6; // rcx
  unsigned int WinevtRegPath; // eax
  int v8; // edi
  HKEY *v9; // rax
  char v10; // di
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  PVOID *v14; // rcx
  char v15; // al
  int phkResult; // [rsp+20h] [rbp-69h]
  HKEY v17; // [rsp+30h] [rbp-59h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-51h] BYREF
  __int64 v19; // [rsp+48h] [rbp-41h]
  int v20; // [rsp+50h] [rbp-39h]
  __int64 v21; // [rsp+54h] [rbp-35h]
  char v22; // [rsp+5Ch] [rbp-2Dh]
  HANDLE v23; // [rsp+60h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v25[88]; // [rsp+88h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v27; // [rsp+100h] [rbp+77h] BYREF
  HKEY v28; // [rsp+108h] [rbp+7Fh] BYREF

  if ( a1[132] )
    return;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids);
  }
  v4 = EnterCriticalPolicySection(1);
  v23 = v4;
  v28 = 0;
  v5 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\EventLog", 0, 0x20019u, v5);
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
  WinevtRegPath = RegistryPaths::GetWinevtRegPath(v6, &hKey, lpSubKey, v25);
  v8 = WinevtRegPath;
  if ( WinevtRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, WinevtRegPath);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v19 = 0;
    v20 = v8;
    v21 = -1;
    v22 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, 14);
    }
    pExceptionObject = 0;
    v19 = 0;
    v20 = 14;
    v21 = 0x181FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v17 = 0;
  v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v17);
  RegOpenKeyExW(hKey, lpSubKey[0], 0, 0x20019u, v9);
  v10 = a1[128];
  a1[128] = 0;
  LODWORD(hKey) = 0;
  if ( (unsigned int)RegReadDWORDValueNoThrow(
                       v28,
                       &pszFormat,
                       L"EnableRemoteRpcAccessRestrictions",
                       (unsigned int *)&hKey)
    || !(_DWORD)hKey )
  {
    goto LABEL_34;
  }
  v27 = 0;
  v13 = RegReadDWORDValueNoThrow(v28, &pszFormat, L"RpcAccess_Remote_Setting", &v27);
  if ( v13 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v13);
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
  v11 = (unsigned __int8)v27;
  if ( !(_BYTE)v27 )
  {
LABEL_33:
    a1[128] = 0;
    goto LABEL_34;
  }
  v11 = (unsigned int)(unsigned __int8)v27 - 1;
  if ( (unsigned __int8)v27 == 1 )
  {
    a1[128] = 1;
  }
  else
  {
    if ( (unsigned __int8)v27 != 2 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x2000) != 0 && *((_BYTE *)v14 + 25) >= 2u )
        WPP_SF_d(v14[2], 36, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v27);
      goto LABEL_33;
    }
    a1[128] = 2;
  }
LABEL_34:
  if ( a1[128] != v10
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids,
      (unsigned __int8)a1[128]);
  }
  v15 = a1[130];
  a1[131] = v15;
  a1[130] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(phkResult) = v15;
    WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, 0, phkResult);
  }
  if ( PolicyManager::ChannelPolicyCache::Update((PolicyManager::ChannelPolicyCache *)(a1 + 56), v28, v17)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids);
  }
  v23 = 0;
  if ( v4 )
    LeaveCriticalPolicySection(v4);
  utl::unique_lock<utl::shared_mutex>::unlock(a2);
  EventService::UpdatePolicy(g_service);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v17);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v25);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int LeaveCriticalPolicySection(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int LeaveCriticalPolicySection(void *),0>>(&v23);
}

```

## disassembly

```asm
0x1800abd88  mov     [rsp-8+arg_8], rbx
0x1800abd8d  push    rbp
0x1800abd8e  push    rsi
0x1800abd8f  push    rdi
0x1800abd90  push    r12
0x1800abd92  push    r13
0x1800abd94  push    r14
0x1800abd96  push    r15
0x1800abd98  lea     rbp, [rsp-27h]
0x1800abd9d  sub     rsp, 0B0h
0x1800abda4  mov     r14, rdx
0x1800abda7  mov     rbx, rcx
0x1800abdaa  xor     r15d, r15d
0x1800abdad  cmp     [rcx+84h], r15b
0x1800abdb4  jnz     loc_1800AC160
0x1800abdba  lea     r13, WPP_GLOBAL_Control
0x1800abdc1  mov     r12d, 2000h
0x1800abdc7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abdce  cmp     rcx, r13
0x1800abdd1  jz      short loc_1800ABDF3
0x1800abdd3  test    [rcx+1Ch], r12d
0x1800abdd7  jz      short loc_1800ABDF3
0x1800abdd9  cmp     byte ptr [rcx+19h], 5
0x1800abddd  jb      short loc_1800ABDF3
0x1800abddf  lea     edx, [r15+20h]
0x1800abde3  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800abdea  mov     rcx, [rcx+10h]
0x1800abdee  call    WPP_SF_
0x1800abdf3  mov     ecx, 1; bMachine
0x1800abdf8  call    cs:__imp_EnterCriticalPolicySection
0x1800abdfe  mov     rsi, rax
0x1800abe01  mov     [rbp+57h+var_80], rax
0x1800abe05  mov     [rbp+57h+arg_18], r15
0x1800abe09  lea     rcx, [rbp+57h+arg_18]
0x1800abe0d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800abe12  mov     qword ptr [rsp+0E0h+phkResult], rax; phkResult
0x1800abe17  mov     r9d, 20019h; samDesired
0x1800abe1d  xor     r8d, r8d; ulOptions
0x1800abe20  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800abe27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800abe2e  call    cs:__imp_RegOpenKeyExW
0x1800abe34  mov     [rbp+57h+hKey], r15
0x1800abe38  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800abe3c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800abe41  nop
0x1800abe42  lea     rcx, [rbp+57h+var_58]; void *
0x1800abe46  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800abe4b  nop
0x1800abe4c  lea     r9, [rbp+57h+var_58]
0x1800abe50  lea     r8, [rbp+57h+lpSubKey]
0x1800abe54  lea     rdx, [rbp+57h+hKey]
0x1800abe58  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800abe5d  mov     edi, eax
0x1800abe5f  test    eax, eax
0x1800abe61  jz      short loc_1800ABEC6
0x1800abe63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abe6a  cmp     rcx, r13
0x1800abe6d  jz      short loc_1800ABE93
0x1800abe6f  test    [rcx+1Ch], r12d
0x1800abe73  jz      short loc_1800ABE93
0x1800abe75  cmp     byte ptr [rcx+19h], 2
0x1800abe79  jb      short loc_1800ABE93
0x1800abe7b  mov     edx, 21h ; '!'
0x1800abe80  mov     r9d, eax
0x1800abe83  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800abe8a  mov     rcx, [rcx+10h]
0x1800abe8e  call    WPP_SF_d
0x1800abe93  lea     rax, byte_1800EC961
0x1800abe9a  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800abe9e  mov     qword ptr [rbp+57h+pExceptionObject+8], r15
0x1800abea2  mov     [rbp+57h+var_98], r15
0x1800abea6  mov     [rbp+57h+var_90], edi
0x1800abea9  mov     [rbp+57h+var_8C], 0FFFFFFFFFFFFFFFFh
0x1800abeb1  mov     [rbp+57h+var_84], r15b
0x1800abeb5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800abebc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800abec0  call    _CxxThrowException_0
0x1800abec6  mov     r8d, 9
0x1800abecc  lea     rdx, aPolicies; "\\Policies"
0x1800abed3  lea     rcx, [rbp+57h+lpSubKey]
0x1800abed7  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800abedc  test    al, al
0x1800abede  jnz     short loc_1800ABF41
0x1800abee0  mov     ebx, 0Eh
0x1800abee5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abeec  cmp     rcx, r13
0x1800abeef  jz      short loc_1800ABF13
0x1800abef1  test    [rcx+1Ch], r12d
0x1800abef5  jz      short loc_1800ABF13
0x1800abef7  cmp     byte ptr [rcx+19h], 2
0x1800abefb  jb      short loc_1800ABF13
0x1800abefd  lea     edx, [rbx+14h]
0x1800abf00  mov     r9d, ebx
0x1800abf03  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800abf0a  mov     rcx, [rcx+10h]
0x1800abf0e  call    WPP_SF_d
0x1800abf13  xorps   xmm0, xmm0
0x1800abf16  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800abf1b  mov     [rbp+57h+var_98], r15
0x1800abf1f  mov     [rbp+57h+var_90], ebx
0x1800abf22  mov     dword ptr [rbp+57h+var_8C], 0FFFFFFFFh
0x1800abf29  mov     dword ptr [rbp+57h+var_8C+4], 181h
0x1800abf30  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800abf37  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800abf3b  call    _CxxThrowException_0
0x1800abf41  mov     [rbp+57h+var_B0], r15
0x1800abf45  lea     rcx, [rbp+57h+var_B0]
0x1800abf49  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800abf4e  mov     qword ptr [rsp+0E0h+phkResult], rax; phkResult
0x1800abf53  mov     r9d, 20019h; samDesired
0x1800abf59  xor     r8d, r8d; ulOptions
0x1800abf5c  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800abf60  mov     rcx, [rbp+57h+hKey]; hKey
0x1800abf64  call    cs:__imp_RegOpenKeyExW
0x1800abf6a  mov     dil, [rbx+80h]
0x1800abf71  mov     [rbx+80h], r15b
0x1800abf78  mov     dword ptr [rbp+57h+hKey], r15d
0x1800abf7c  lea     r9, [rbp+57h+hKey]; unsigned int *
0x1800abf80  lea     r8, aEnableremoterp; "EnableRemoteRpcAccessRestrictions"
0x1800abf87  lea     rdx, pszFormat; wchar_t *
0x1800abf8e  mov     rcx, [rbp+57h+arg_18]; HKEY
0x1800abf92  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800abf97  test    eax, eax
0x1800abf99  jnz     loc_1800AC04F
0x1800abf9f  cmp     dword ptr [rbp+57h+hKey], r15d
0x1800abfa3  jz      loc_1800AC04F
0x1800abfa9  mov     [rbp+57h+arg_10], r15d
0x1800abfad  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x1800abfb1  lea     r8, aRpcaccessRemot; "RpcAccess_Remote_Setting"
0x1800abfb8  lea     rdx, pszFormat; wchar_t *
0x1800abfbf  mov     rcx, [rbp+57h+arg_18]; HKEY
0x1800abfc3  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800abfc8  test    eax, eax
0x1800abfca  jz      short loc_1800ABFFC
0x1800abfcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abfd3  cmp     rcx, r13
0x1800abfd6  jz      short loc_1800AC003
0x1800abfd8  test    [rcx+1Ch], r12d
0x1800abfdc  jz      short loc_1800AC003
0x1800abfde  cmp     byte ptr [rcx+19h], 2
0x1800abfe2  jb      short loc_1800AC003
0x1800abfe4  mov     edx, 23h ; '#'
0x1800abfe9  mov     r9d, eax
0x1800abfec  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800abff3  mov     rcx, [rcx+10h]
0x1800abff7  call    WPP_SF_d
0x1800abffc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac003  mov     r9d, [rbp+57h+arg_10]
0x1800ac007  movzx   edx, r9b
0x1800ac00b  test    r9b, r9b
0x1800ac00e  jz      short loc_1800AC048
0x1800ac010  sub     edx, 1
0x1800ac013  jz      loc_1800AC187
0x1800ac019  cmp     edx, 1
0x1800ac01c  jz      loc_1800AC17B
0x1800ac022  cmp     rcx, r13
0x1800ac025  jz      short loc_1800AC048
0x1800ac027  test    [rcx+1Ch], r12d
0x1800ac02b  jz      short loc_1800AC048
0x1800ac02d  cmp     byte ptr [rcx+19h], 2
0x1800ac031  jb      short loc_1800AC048
0x1800ac033  mov     edx, 24h ; '$'
0x1800ac038  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800ac03f  mov     rcx, [rcx+10h]
0x1800ac043  call    WPP_SF_d
0x1800ac048  mov     [rbx+80h], r15b
0x1800ac04f  movzx   eax, byte ptr [rbx+80h]
0x1800ac056  cmp     al, dil
0x1800ac059  jz      short loc_1800AC08B
0x1800ac05b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac062  cmp     rcx, r13
0x1800ac065  jz      short loc_1800AC08B
0x1800ac067  test    [rcx+1Ch], r12d
0x1800ac06b  jz      short loc_1800AC08B
0x1800ac06d  cmp     byte ptr [rcx+19h], 4
0x1800ac071  jb      short loc_1800AC08B
0x1800ac073  mov     r9d, eax
0x1800ac076  mov     edx, 25h ; '%'
0x1800ac07b  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800ac082  mov     rcx, [rcx+10h]
0x1800ac086  call    WPP_SF_d
0x1800ac08b  mov     al, [rbx+82h]
0x1800ac091  mov     [rbx+83h], al
0x1800ac097  mov     [rbx+82h], r15b
0x1800ac09e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac0a5  cmp     rcx, r13
0x1800ac0a8  jz      short loc_1800AC0C6
0x1800ac0aa  test    [rcx+1Ch], r12d
0x1800ac0ae  jz      short loc_1800AC0C6
0x1800ac0b0  cmp     byte ptr [rcx+19h], 5
0x1800ac0b4  jb      short loc_1800AC0C6
0x1800ac0b6  mov     byte ptr [rsp+0E0h+phkResult], al
0x1800ac0ba  xor     r9d, r9d
0x1800ac0bd  mov     rcx, [rcx+10h]
0x1800ac0c1  call    WPP_SF_cc
0x1800ac0c6  lea     rcx, [rbx+38h]; this
0x1800ac0ca  mov     r8, [rbp+57h+var_B0]; HKEY
0x1800ac0ce  mov     rdx, [rbp+57h+arg_18]; HKEY
0x1800ac0d2  call    ?Update@ChannelPolicyCache@PolicyManager@@QEAA_NPEAUHKEY__@@0@Z; PolicyManager::ChannelPolicyCache::Update(HKEY__ *,HKEY__ *)
0x1800ac0d7  test    al, al
0x1800ac0d9  jz      short loc_1800AC108
0x1800ac0db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac0e2  cmp     rcx, r13
0x1800ac0e5  jz      short loc_1800AC108
0x1800ac0e7  test    [rcx+1Ch], r12d
0x1800ac0eb  jz      short loc_1800AC108
0x1800ac0ed  cmp     byte ptr [rcx+19h], 5
0x1800ac0f1  jb      short loc_1800AC108
0x1800ac0f3  mov     edx, 27h ; '''
0x1800ac0f8  lea     r8, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800ac0ff  mov     rcx, [rcx+10h]
0x1800ac103  call    WPP_SF_
0x1800ac108  mov     [rbp+57h+var_80], r15
0x1800ac10c  test    rsi, rsi
0x1800ac10f  jz      short loc_1800AC11A
0x1800ac111  mov     rcx, rsi; hSection
0x1800ac114  call    cs:__imp_LeaveCriticalPolicySection
0x1800ac11a  mov     rcx, r14
0x1800ac11d  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x1800ac122  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; this
0x1800ac129  call    ?UpdatePolicy@EventService@@QEAAXXZ; EventService::UpdatePolicy(void)
0x1800ac12e  nop
0x1800ac12f  lea     rcx, [rbp+57h+var_B0]
0x1800ac133  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800ac138  nop
0x1800ac139  lea     rcx, [rbp+57h+var_58]; void *
0x1800ac13d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ac142  nop
0x1800ac143  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800ac147  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ac14c  nop
0x1800ac14d  lea     rcx, [rbp+57h+arg_18]
0x1800ac151  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800ac156  nop
0x1800ac157  lea     rcx, [rbp+57h+var_80]
0x1800ac15b  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?LeaveCriticalPolicySection@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&LeaveCriticalPolicySection(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&LeaveCriticalPolicySection(void *),0>>(void)
0x1800ac160  mov     rbx, [rsp+0E0h+arg_8]
0x1800ac168  add     rsp, 0B0h
0x1800ac16f  pop     r15
0x1800ac171  pop     r14
0x1800ac173  pop     r13
0x1800ac175  pop     r12
0x1800ac177  pop     rdi
0x1800ac178  pop     rsi
0x1800ac179  pop     rbp
0x1800ac17a  retn
0x1800ac17b  mov     byte ptr [rbx+80h], 2
0x1800ac182  jmp     loc_1800AC04F
0x1800ac187  mov     byte ptr [rbx+80h], 1
0x1800ac18e  jmp     loc_1800AC04F
```
