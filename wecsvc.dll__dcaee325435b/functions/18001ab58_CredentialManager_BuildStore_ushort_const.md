# CredentialManager::BuildStore(ushort const *)

- ea: `0x18001ab58`
- end: `0x18001b232`
- name: `?BuildStore@CredentialManager@@QEAAXPEBG@Z`
- size: `1754`
- prototype: `void __fastcall(CredentialManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005ad0`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x180006370`
- `0x1800064e0`
- `0x18000669c`
- `0x1800077e4`
- `0x18000866c`
- `0x180011c24`
- `0x180011d6c`
- `0x180011e68`
- `0x180011f40`
- `0x18001a730`
- `0x18001a864`
- `0x18001aa84`
- `0x18001ab58`
- `0x18001b998`
- `0x18001c648`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001b0f0`
- `msvcrt!_wcsnicmp` at `0x18001b0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001affb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001affb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001abc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001abc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ac08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ac08`
- `ADVAPI32!CredDeleteW` at `0x18001b1aa`
- `ADVAPI32!CredDeleteW` at `0x18001b1aa`
- `ADVAPI32!CredEnumerateW` at `0x18001afdc`
- `ADVAPI32!CredEnumerateW` at `0x18001afdc`
- `ADVAPI32!CredFree` at `0x18001b0b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CredentialManager::BuildStore(CredentialManager *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // edi
  HKEY v6; // rdx
  unsigned int v7; // edi
  __int64 v8; // r13
  __int64 v9; // r15
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned __int64 v13; // r14
  DWORD LastError; // ebx
  PCREDENTIALW *v15; // rcx
  int v16; // r15d
  __int64 v17; // rdx
  __int64 v18; // rcx
  const wchar_t *v19; // rax
  const wchar_t *v20; // rdi
  const wchar_t *v21; // r14
  bool v22; // zf
  bool v23; // di
  __int64 v24; // rdx
  unsigned int v25; // eax
  int phkResult; // [rsp+20h] [rbp-238h]
  DWORD Count; // [rsp+30h] [rbp-228h] BYREF
  PCREDENTIALW *Credential; // [rsp+38h] [rbp-220h] BYREF
  HKEY v29; // [rsp+40h] [rbp-218h] BYREF
  HKEY CurrentSubKey; // [rsp+48h] [rbp-210h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-208h] BYREF
  __int128 v32; // [rsp+60h] [rbp-1F8h] BYREF
  PCREDENTIALW *v33; // [rsp+70h] [rbp-1E8h]
  __int128 v34; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1D0h]
  struct _RTL_CRITICAL_SECTION *v36; // [rsp+90h] [rbp-1C8h]
  void **pExceptionObject; // [rsp+98h] [rbp-1C0h] BYREF
  char v38; // [rsp+A0h] [rbp-1B8h]
  const char *v39; // [rsp+A8h] [rbp-1B0h]
  __int64 v40; // [rsp+B0h] [rbp-1A8h]
  __int64 v41; // [rsp+B8h] [rbp-1A0h]
  unsigned int v42; // [rsp+C0h] [rbp-198h]
  int v43; // [rsp+C4h] [rbp-194h]
  int v44; // [rsp+C8h] [rbp-190h]
  void **v45; // [rsp+D0h] [rbp-188h] BYREF
  char v46; // [rsp+D8h] [rbp-180h]
  const char *v47; // [rsp+E0h] [rbp-178h]
  __int64 v48; // [rsp+E8h] [rbp-170h]
  __int64 v49; // [rsp+F0h] [rbp-168h]
  int v50; // [rsp+F8h] [rbp-160h]
  int v51; // [rsp+FCh] [rbp-15Ch]
  int v52; // [rsp+100h] [rbp-158h]
  void **v53; // [rsp+108h] [rbp-150h] BYREF
  char v54; // [rsp+110h] [rbp-148h]
  const char *v55; // [rsp+118h] [rbp-140h]
  __int64 v56; // [rsp+120h] [rbp-138h]
  __int64 v57; // [rsp+128h] [rbp-130h]
  unsigned int v58; // [rsp+130h] [rbp-128h]
  int v59; // [rsp+134h] [rbp-124h]
  int v60; // [rsp+138h] [rbp-120h]
  void **v61; // [rsp+140h] [rbp-118h] BYREF
  char v62; // [rsp+148h] [rbp-110h]
  const char *v63; // [rsp+150h] [rbp-108h]
  __int64 v64; // [rsp+158h] [rbp-100h]
  __int64 v65; // [rsp+160h] [rbp-F8h]
  DWORD v66; // [rsp+168h] [rbp-F0h]
  int v67; // [rsp+16Ch] [rbp-ECh]
  int v68; // [rsp+170h] [rbp-E8h]
  char v69[8]; // [rsp+178h] [rbp-E0h] BYREF
  wmi::Exception *v70; // [rsp+180h] [rbp-D8h] BYREF
  char v71[8]; // [rsp+188h] [rbp-D0h] BYREF
  int v72; // [rsp+190h] [rbp-C8h]
  char v73[16]; // [rsp+1C0h] [rbp-98h] BYREF
  __int128 v74; // [rsp+1D0h] [rbp-88h] BYREF
  __int64 v75; // [rsp+1E0h] [rbp-78h]
  LPCWSTR lpSubKey[3]; // [rsp+1F0h] [rbp-68h] BYREF
  unsigned __int64 v77; // [rsp+208h] [rbp-50h]

  v77 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  std::wstring::assign((__int64)lpSubKey, (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append((__int64)lpSubKey, (__int64)L"\\Subscriptions");
  v2 = &CriticalSection;
  v36 = &CriticalSection;
  EnterCriticalSection(&CriticalSection);
  v29 = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( v77 >= 8 )
    v3 = lpSubKey[0];
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &v29);
  v5 = v4;
  if ( v4 != 2 )
  {
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v4);
      }
      v38 = 0;
      v39 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
      v40 = 0;
      v41 = 0;
      v42 = v5;
      v43 = -1;
      v44 = 160;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::_Tree_buy<std::wstring>::_Tree_buy<std::wstring>(v31);
    v6 = v29;
    v29 = 0;
    RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v71, v6);
    v72 = 0;
    v7 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v71);
    while ( 1 )
    {
      if ( v7 )
      {
        if ( v7 != 259 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v7);
          }
          v54 = 0;
          v55 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
          v56 = 0;
          v57 = 0;
          v58 = v7;
          v59 = -1;
          v60 = 201;
          v53 = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&v53;
        }
        Count = 0;
        Credential = 0;
        if ( !CredEnumerateW(0, 0, &Count, &Credential) && GetLastError() != 1168 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 1287;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids,
              LastError);
          }
          v62 = 0;
          v63 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
          v64 = 0;
          v65 = 0;
          v66 = LastError;
          v67 = -1;
          v68 = 213;
          v61 = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&v61;
        }
        v15 = Credential;
        LOBYTE(v32) = 0;
        *((_QWORD *)&v32 + 1) = CredFree;
        v33 = Credential;
        v16 = 0;
        if ( Count )
        {
          while ( 1 )
          {
            if ( !_wcsnicmp(v15[v16]->TargetName, L"EC::", 4u) )
            {
              std::wstring::wstring((__int64)&v74, (__int64)Credential[v16]->TargetName);
              v19 = (const wchar_t *)v31[0];
              v20 = *(const wchar_t **)(v31[0] + 8LL);
              v21 = (const wchar_t *)v31[0];
              if ( !*((_BYTE *)v20 + 25) )
              {
                do
                {
                  if ( (unsigned __int8)CaseInsensitiveLess::operator()(v18, (__int64)(v20 + 16), (const wchar_t *)&v74) )
                  {
                    v20 = (const wchar_t *)*((_QWORD *)v20 + 2);
                  }
                  else
                  {
                    v21 = v20;
                    v20 = *(const wchar_t **)v20;
                  }
                }
                while ( !*((_BYTE *)v20 + 25) );
                v19 = (const wchar_t *)v31[0];
              }
              if ( v21 == v19
                || (v22 = (unsigned __int8)CaseInsensitiveLess::operator()(v18, (__int64)&v74, v21 + 16) == 0,
                    v19 = (const wchar_t *)v31[0],
                    !v22) )
              {
                v21 = v19;
              }
              v23 = v21 == v19;
              LOBYTE(v17) = 1;
              std::wstring::_Tidy(&v74, v17, 0);
              if ( v23 )
                CredDeleteW(Credential[v16]->TargetName, 1u, 0);
            }
            if ( ++v16 >= Count )
              break;
            v15 = Credential;
          }
        }
        wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>((__int64)&v32);
        RegistryKeyEnumerator::~RegistryKeyEnumerator((HKEY *)v71);
        std::_Tree<std::_Tset_traits<std::wstring,CredentialManager::wstring_iless,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,CredentialManager::wstring_iless,std::allocator<std::wstring>,0>>(v31);
        break;
      }
      v34 = 0;
      v35 = 0;
      v32 = 0;
      v33 = 0;
      v74 = 0;
      v75 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)v71, 0x20019u);
        CredentialManager::ReadSubscriptionEntries(&v74, CurrentSubKey, &v34, &v32, &v74);
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&CurrentSubKey);
        v13 = 0;
        v8 = v34;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v70) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = (**(__int64 (__fastcall ***)(wmi::Exception *))v70)(v70);
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, v25);
          }
          LODWORD(CurrentSubKey) = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v71);
          __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_18001AEE0);
          std::vector<std::wstring>::_Tidy(&v74);
          std::vector<std::wstring>::_Tidy(&v32);
          std::vector<std::wstring>::_Tidy(&v34);
          v2 = v36;
          v7 = (unsigned int)CurrentSubKey;
          continue;
        }
      }
      while ( v13 < (*((_QWORD *)&v34 + 1) - v8) >> 5 )
      {
        v9 = 32 * v13;
        if ( *(_QWORD *)(32 * v13 + v8 + 16) )
        {
          if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                            v12,
                            v69,
                            32 * v13 + v8) != g_credMgr )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids, 13);
            }
            v46 = 0;
            v47 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
            v48 = 0;
            v49 = 0;
            v50 = 13;
            v51 = -1;
            v52 = 193;
            v45 = &wmi::GenericException::`vftable';
            throw (wmi::GenericException *)&v45;
          }
          v10 = v9 + v74;
          CredentialManager::AddEntry(g_credMgr, 32 * v13 + v8, v9 + v32, v9 + v74);
          LOBYTE(phkResult) = byte_18002F7B9;
          std::_Tree<std::_Tset_traits<std::wstring,CredentialManager::wstring_iless,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring const &,std::_Nil>(
            v31,
            v73,
            v11,
            v10,
            phkResult);
        }
        ++v13;
      }
      v7 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v71);
      std::vector<std::wstring>::_Tidy(&v74);
      std::vector<std::wstring>::_Tidy(&v32);
      std::vector<std::wstring>::_Tidy(&v34);
    }
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v29);
  LeaveCriticalSection(v2);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(lpSubKey, v24, 0);
}

```

## disassembly

```asm
0x18001ab58  mov     r11, rsp
0x18001ab5b  push    rbx
0x18001ab5c  push    rsi
0x18001ab5d  push    rdi
0x18001ab5e  push    r12
0x18001ab60  push    r13
0x18001ab62  push    r14
0x18001ab64  push    r15
0x18001ab66  sub     rsp, 220h
0x18001ab6d  mov     rax, cs:__security_cookie
0x18001ab74  xor     rax, rsp
0x18001ab77  mov     [rsp+258h+var_48], rax
0x18001ab7f  mov     qword ptr [r11-50h], 7
0x18001ab87  xor     esi, esi
0x18001ab89  mov     [r11-58h], rsi
0x18001ab8d  mov     [r11-68h], si
0x18001ab92  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ab99  lea     rcx, [r11-68h]
0x18001ab9d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001aba2  lea     rdx, aSubscriptions; "\\Subscriptions"
0x18001aba9  lea     rcx, [rsp+258h+lpSubKey]
0x18001abb1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001abb6  lea     rbx, CriticalSection
0x18001abbd  mov     [rsp+258h+var_1C8], rbx
0x18001abc5  mov     rcx, rbx; lpCriticalSection
0x18001abc8  call    cs:__imp_EnterCriticalSection
0x18001abce  nop
0x18001abcf  mov     [rsp+258h+var_218], rsi
0x18001abd4  lea     rdx, [rsp+258h+lpSubKey]
0x18001abdc  cmp     [rsp+258h+var_50], 8
0x18001abe5  cmovnb  rdx, [rsp+258h+lpSubKey]; lpSubKey
0x18001abee  lea     rax, [rsp+258h+var_218]
0x18001abf3  mov     qword ptr [rsp+258h+phkResult], rax; phkResult
0x18001abf8  mov     r9d, 20019h; samDesired
0x18001abfe  xor     r8d, r8d; ulOptions
0x18001ac01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ac08  call    cs:__imp_RegOpenKeyExW
0x18001ac0e  mov     edi, eax
0x18001ac10  cmp     eax, 2
0x18001ac13  jz      loc_18001B1E8
0x18001ac19  test    eax, eax
0x18001ac1b  jz      loc_18001ACBE
0x18001ac21  lea     rax, WPP_GLOBAL_Control
0x18001ac28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac2f  cmp     rcx, rax
0x18001ac32  jz      short loc_18001AC56
0x18001ac34  test    byte ptr [rcx+1Ch], 40h
0x18001ac38  jz      short loc_18001AC56
0x18001ac3a  cmp     byte ptr [rcx+19h], 2
0x18001ac3e  jb      short loc_18001AC56
0x18001ac40  lea     edx, [rsi+0Fh]
0x18001ac43  mov     r9d, edi
0x18001ac46  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001ac4d  mov     rcx, [rcx+10h]
0x18001ac51  call    WPP_SF_D
0x18001ac56  mov     [rsp+258h+var_1B8], sil
0x18001ac5e  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ac65  mov     [rsp+258h+var_1B0], rax
0x18001ac6d  mov     [rsp+258h+var_1A8], rsi
0x18001ac75  mov     [rsp+258h+var_1A0], rsi
0x18001ac7d  mov     [rsp+258h+var_198], edi
0x18001ac84  mov     [rsp+258h+var_194], 0FFFFFFFFh
0x18001ac8f  mov     [rsp+258h+var_190], 0A0h
0x18001ac9a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001aca1  mov     [rsp+258h+pExceptionObject], rax
0x18001aca9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001acb0  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x18001acb8  call    _CxxThrowException_0
0x18001acbe  lea     rcx, [rsp+258h+var_208]
0x18001acc3  call    ??0?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree_buy<std::wstring>::_Tree_buy<std::wstring>(std::allocator<std::wstring> const &)
0x18001acc8  nop
0x18001acc9  mov     rdx, [rsp+258h+var_218]; HKEY
0x18001acce  mov     [rsp+258h+var_218], rsi
0x18001acd3  lea     rcx, [rsp+258h+var_D0]; this
0x18001acdb  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x18001ace0  nop
0x18001ace1  mov     [rsp+258h+var_C8], esi
0x18001ace8  lea     rcx, [rsp+258h+var_D0]; this
0x18001acf0  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18001acf5  mov     edi, eax
0x18001acf7  test    edi, edi
0x18001acf9  jnz     loc_18001AF16
0x18001acff  xorps   xmm0, xmm0
0x18001ad02  movdqu  [rsp+258h+var_1E0], xmm0
0x18001ad08  mov     [rsp+258h+var_1D0], rsi
0x18001ad10  movdqu  [rsp+258h+var_1F8], xmm0
0x18001ad16  mov     [rsp+258h+var_1E8], rsi
0x18001ad1b  movdqu  [rsp+258h+var_88], xmm0
0x18001ad24  mov     [rsp+258h+var_78], rsi
0x18001ad2c  mov     edx, 20019h; unsigned int
0x18001ad31  lea     rcx, [rsp+258h+var_D0]; this
0x18001ad39  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x18001ad3e  mov     [rsp+258h+var_210], rax
0x18001ad43  lea     rcx, [rsp+258h+var_88]
0x18001ad4b  mov     qword ptr [rsp+258h+phkResult], rcx
0x18001ad50  lea     r9, [rsp+258h+var_1F8]
0x18001ad55  lea     r8, [rsp+258h+var_1E0]
0x18001ad5a  mov     rdx, rax
0x18001ad5d  call    ?ReadSubscriptionEntries@CredentialManager@@AEAAXPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@11@Z; CredentialManager::ReadSubscriptionEntries(HKEY__ *,std::vector<std::wstring> &,std::vector<std::wstring> &,std::vector<std::wstring> &)
0x18001ad62  nop
0x18001ad63  lea     rcx, [rsp+258h+var_210]; this
0x18001ad68  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001ad6d  nop
0x18001ad6e  mov     r14, rsi
0x18001ad71  mov     r13, qword ptr [rsp+258h+var_1E0]
0x18001ad76  mov     rax, qword ptr [rsp+258h+var_1E0+8]
0x18001ad7e  sub     rax, r13
0x18001ad81  sar     rax, 5
0x18001ad85  cmp     r14, rax
0x18001ad88  jnb     loc_18001AEA9
0x18001ad8e  mov     r15, r14
0x18001ad91  shl     r15, 5
0x18001ad95  lea     r12, [r15+r13]
0x18001ad99  cmp     [r12+10h], rsi
0x18001ad9e  jz      short loc_18001ADF9
0x18001ada0  mov     r8, r12
0x18001ada3  lea     rdx, [rsp+258h+var_E0]
0x18001adab  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001adb0  mov     rcx, cs:?g_credMgr@@3VCredentialManager@@A; CredentialManager g_credMgr
0x18001adb7  cmp     [rax], rcx
0x18001adba  jnz     short loc_18001AE01
0x18001adbc  mov     rdi, qword ptr [rsp+258h+var_88]
0x18001adc4  add     rdi, r15
0x18001adc7  mov     r8, qword ptr [rsp+258h+var_1F8]
0x18001adcc  add     r8, r15
0x18001adcf  mov     r9, rdi
0x18001add2  mov     rdx, r12
0x18001add5  call    ?AddEntry@CredentialManager@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; CredentialManager::AddEntry(std::wstring const &,std::wstring const &,std::wstring const &)
0x18001adda  mov     al, cs:byte_18002F7B9
0x18001ade0  mov     byte ptr [rsp+258h+phkResult], al
0x18001ade4  mov     r9, rdi
0x18001ade7  lea     rdx, [rsp+258h+var_98]
0x18001adef  lea     rcx, [rsp+258h+var_208]
0x18001adf4  call    ??$_Insert_nohint@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_iless@CredentialManager@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,CredentialManager::wstring_iless,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring const &,std::_Nil>(bool,std::wstring const &,std::_Nil)
0x18001adf9  inc     r14
0x18001adfc  jmp     loc_18001AD76
0x18001ae01  lea     rax, WPP_GLOBAL_Control
0x18001ae08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae0f  cmp     rcx, rax
0x18001ae12  jz      short loc_18001AE39
0x18001ae14  test    byte ptr [rcx+1Ch], 40h
0x18001ae18  jz      short loc_18001AE39
0x18001ae1a  cmp     byte ptr [rcx+19h], 2
0x18001ae1e  jb      short loc_18001AE39
0x18001ae20  mov     edx, 11h
0x18001ae25  lea     r9d, [rdx-4]
0x18001ae29  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001ae30  mov     rcx, [rcx+10h]
0x18001ae34  call    WPP_SF_D
0x18001ae39  mov     [rsp+258h+var_180], sil
0x18001ae41  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ae48  mov     [rsp+258h+var_178], rax
0x18001ae50  mov     [rsp+258h+var_170], rsi
0x18001ae58  mov     [rsp+258h+var_168], 0
0x18001ae64  mov     [rsp+258h+var_160], 0Dh
0x18001ae6f  mov     [rsp+258h+var_15C], 0FFFFFFFFh
0x18001ae7a  mov     [rsp+258h+var_158], 0C1h
0x18001ae85  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ae8c  mov     [rsp+258h+var_188], rax
0x18001ae94  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ae9b  lea     rcx, [rsp+258h+var_188]; pExceptionObject
0x18001aea3  call    _CxxThrowException_0
0x18001aea9  lea     rcx, [rsp+258h+var_D0]; this
0x18001aeb1  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18001aeb6  mov     edi, eax
0x18001aeb8  lea     rcx, [rsp+258h+var_88]
0x18001aec0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001aec5  nop
0x18001aec6  lea     rcx, [rsp+258h+var_1F8]
0x18001aecb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001aed0  nop
0x18001aed1  lea     rcx, [rsp+258h+var_1E0]
0x18001aed6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001aedb  jmp     loc_18001ACF7
0x18001aee0  lea     rcx, [rsp+258h+var_88]
0x18001aee8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001aeed  nop
0x18001aeee  lea     rcx, [rsp+258h+var_1F8]
0x18001aef3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001aef8  nop
0x18001aef9  lea     rcx, [rsp+258h+var_1E0]
0x18001aefe  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001af03  xor     esi, esi
0x18001af05  mov     rbx, [rsp+258h+var_1C8]
0x18001af0d  mov     edi, dword ptr [rsp+258h+var_210]
0x18001af11  jmp     loc_18001ACF7
0x18001af16  cmp     edi, 103h
0x18001af1c  jz      loc_18001AFC5
0x18001af22  lea     rax, WPP_GLOBAL_Control
0x18001af29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af30  cmp     rcx, rax
0x18001af33  jz      short loc_18001AF59
0x18001af35  test    byte ptr [rcx+1Ch], 40h
0x18001af39  jz      short loc_18001AF59
0x18001af3b  cmp     byte ptr [rcx+19h], 2
0x18001af3f  jb      short loc_18001AF59
0x18001af41  mov     edx, 12h
0x18001af46  mov     r9d, edi
0x18001af49  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001af50  mov     rcx, [rcx+10h]
0x18001af54  call    WPP_SF_D
0x18001af59  mov     [rsp+258h+var_148], sil
0x18001af61  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001af68  mov     [rsp+258h+var_140], rax
0x18001af70  mov     [rsp+258h+var_138], rsi
0x18001af78  mov     [rsp+258h+var_130], 0
0x18001af84  mov     [rsp+258h+var_128], edi
0x18001af8b  mov     [rsp+258h+var_124], 0FFFFFFFFh
0x18001af96  mov     [rsp+258h+var_120], 0C9h
0x18001afa1  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001afa8  mov     [rsp+258h+var_150], rax
0x18001afb0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001afb7  lea     rcx, [rsp+258h+var_150]; pExceptionObject
0x18001afbf  call    _CxxThrowException_0
0x18001afc5  mov     [rsp+258h+Count], esi
0x18001afc9  mov     [rsp+258h+Credential], rsi
0x18001afce  lea     r9, [rsp+258h+Credential]; Credential
0x18001afd3  lea     r8, [rsp+258h+Count]; Count
0x18001afd8  xor     edx, edx; Flags
0x18001afda  xor     ecx, ecx; Filter
0x18001afdc  call    cs:__imp_CredEnumerateW
0x18001afe2  test    eax, eax
0x18001afe4  jnz     loc_18001B0B0
0x18001afea  call    cs:__imp_GetLastError
0x18001aff0  cmp     eax, 490h
0x18001aff5  jz      loc_18001B0B0
0x18001affb  call    cs:__imp_GetLastError
0x18001b001  mov     ebx, eax
0x18001b003  mov     eax, 507h
0x18001b008  test    ebx, ebx
0x18001b00a  cmovz   ebx, eax
0x18001b00d  lea     rax, WPP_GLOBAL_Control
0x18001b014  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b01b  cmp     rcx, rax
0x18001b01e  jz      short loc_18001B044
0x18001b020  test    byte ptr [rcx+1Ch], 40h
0x18001b024  jz      short loc_18001B044
0x18001b026  cmp     byte ptr [rcx+19h], 2
0x18001b02a  jb      short loc_18001B044
0x18001b02c  mov     edx, 13h
0x18001b031  mov     r9d, ebx
0x18001b034  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b03b  mov     rcx, [rcx+10h]
0x18001b03f  call    WPP_SF_D
0x18001b044  mov     [rsp+258h+var_110], sil
0x18001b04c  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b053  mov     [rsp+258h+var_108], rax
0x18001b05b  mov     [rsp+258h+var_100], rsi
0x18001b063  mov     [rsp+258h+var_F8], 0
0x18001b06f  mov     [rsp+258h+var_F0], ebx
0x18001b076  mov     [rsp+258h+var_EC], 0FFFFFFFFh
0x18001b081  mov     [rsp+258h+var_E8], 0D5h
0x18001b08c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b093  mov     [rsp+258h+var_118], rax
0x18001b09b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b0a2  lea     rcx, [rsp+258h+var_118]; pExceptionObject
0x18001b0aa  call    _CxxThrowException_0
0x18001b0b0  mov     rcx, [rsp+258h+Credential]
0x18001b0b5  mov     rax, cs:__imp_CredFree
0x18001b0bc  mov     byte ptr [rsp+258h+var_1F8], sil
0x18001b0c1  mov     qword ptr [rsp+258h+var_1F8+8], rax
0x18001b0c6  mov     [rsp+258h+var_1E8], rcx
0x18001b0cb  mov     r15d, esi
0x18001b0ce  cmp     [rsp+258h+Count], esi
0x18001b0d2  jbe     loc_18001B1C4
0x18001b0d8  mov     r12d, r15d
0x18001b0db  mov     rcx, [rcx+r12*8]
0x18001b0df  mov     r8d, 4; MaxCount
0x18001b0e5  lea     rdx, aEc; "EC::"
0x18001b0ec  mov     rcx, [rcx+8]; String1
0x18001b0f0  call    cs:__imp__wcsnicmp
0x18001b0f6  test    eax, eax
0x18001b0f8  jnz     loc_18001B1B0
0x18001b0fe  mov     rax, [rsp+258h+Credential]
0x18001b103  mov     rdx, [rax+r12*8]
0x18001b107  mov     rdx, [rdx+8]
0x18001b10b  lea     rcx, [rsp+258h+var_88]
0x18001b113  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001b118  mov     rax, [rsp+258h+var_208]
0x18001b11d  mov     rdi, [rax+8]
0x18001b121  mov     r14, rax
0x18001b124  cmp     [rdi+19h], sil
0x18001b128  jnz     short loc_18001B156
0x18001b12a  lea     rdx, [rdi+20h]
0x18001b12e  lea     r8, [rsp+258h+var_88]
0x18001b136  call    ??RCaseInsensitiveLess@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CaseInsensitiveLess::operator()(std::wstring const &,std::wstring const &)
0x18001b13b  test    al, al
0x18001b13d  jz      short loc_18001B145
0x18001b13f  mov     rdi, [rdi+10h]
0x18001b143  jmp     short loc_18001B14B
0x18001b145  mov     r14, rdi
0x18001b148  mov     rdi, [rdi]
0x18001b14b  cmp     [rdi+19h], sil
0x18001b14f  jz      short loc_18001B12A
0x18001b151  mov     rax, [rsp+258h+var_208]
0x18001b156  cmp     r14, rax
0x18001b159  jz      short loc_18001B175
0x18001b15b  lea     r8, [r14+20h]
0x18001b15f  lea     rdx, [rsp+258h+var_88]
0x18001b167  call    ??RCaseInsensitiveLess@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CaseInsensitiveLess::operator()(std::wstring const &,std::wstring const &)
  ... truncated ...
```
