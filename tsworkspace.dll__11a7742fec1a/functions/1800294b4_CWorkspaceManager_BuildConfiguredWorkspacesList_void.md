# CWorkspaceManager::BuildConfiguredWorkspacesList(void)

- ea: `0x1800294b4`
- end: `0x1800298a4`
- name: `?BuildConfiguredWorkspacesList@CWorkspaceManager@@IEAAXXZ`
- size: `1008`
- prototype: `void __fastcall(CWorkspaceManager *__hidden this)`
- caller_count: `8`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800307f4`
- `0x180033330`
- `0x18003f6d4`
- `0x180070ec0`
- `0x180071190`
- `0x180071280`
- `0x1800714a0`
- `0x180074bb8`

## callees

- `0x180004970`
- `0x180005500`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000fed8`
- `0x180019fb0`
- `0x1800294b4`
- `0x180029f78`
- `0x180030dc4`
- `0x1800335a0`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800295b0`
- `ADVAPI32!RegCloseKey` at `0x1800295b0`
- `ADVAPI32!RegEnumKeyExW` at `0x1800296fd`
- `ADVAPI32!RegEnumKeyExW` at `0x1800296fd`
- `ADVAPI32!RegCreateKeyExW` at `0x180029640`
- `ADVAPI32!RegCreateKeyExW` at `0x180029640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002951e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002951e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297b3`
- `KERNEL32!CompareStringOrdinal` at `0x18002978e`
- `KERNEL32!CompareStringOrdinal` at `0x18002978e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWorkspaceManager::BuildConfiguredWorkspacesList(CWorkspaceManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  char *v3; // r15
  int DefaultWorkspaceGUID; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  DWORD v7; // esi
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  unsigned int v10; // eax
  const WCHAR *v11; // rax
  int v12; // r14d
  DWORD LastError; // ebx
  unsigned int v14; // eax
  BOOL v15; // ebx
  int v16; // r14d
  unsigned int v17; // eax
  int v18; // ebx
  unsigned int v19; // eax
  struct CWorkspace *v20; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cchName[2]; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v23[32]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+98h] [rbp-70h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  cchName[0] = 260;
  v20 = 0;
  std::wstring::wstring(v23);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (char *)this + 64;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 8) + 24LL))((char *)this + 64);
  DefaultWorkspaceGUID = CWorkspaceManager::ReadDefaultWorkspaceGUID(v23);
  if ( (int)(DefaultWorkspaceGUID + 0x80000000) < 0 || DefaultWorkspaceGUID == -2147024894 )
  {
    DefaultWorkspaceGUID = RegCreateKeyExW(
                             HKEY_CURRENT_USER,
                             L"Software\\Microsoft\\Workspaces\\Feeds",
                             0,
                             0,
                             0,
                             0x20019u,
                             0,
                             hKey,
                             0);
    if ( DefaultWorkspaceGUID )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( DefaultWorkspaceGUID > 0 )
          DefaultWorkspaceGUID = (unsigned __int16)DefaultWorkspaceGUID | 0x80070000;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 20;
        goto LABEL_7;
      }
    }
    else
    {
      v7 = 0;
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v20 )
            {
              TCntPtr<CConfigManager>::SafeRelease(&v20);
              v20 = 0;
              TCntPtr<CConfigManager>::SafeAddRef(&v20);
            }
            cchName[0] = 260;
            v8 = RegEnumKeyExW(hKey[0], v7, Name, cchName, 0, 0, 0, 0);
            v9 = v8;
            if ( v8 )
              break;
            v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
            v12 = CompareStringOrdinal(Name, -1, v11, -1, 1);
            if ( !v12
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v14,
                LastError);
            }
            v15 = v12 == 2;
            v16 = CWorkspace::CreateInstance(&v20);
            if ( v16 >= 0 )
            {
              *((_DWORD *)v20 + 24) = v15;
              v18 = CWorkspace::InitializeFromRegistry((GUID *)v20, hKey[0], Name);
              if ( v18 >= 0 )
              {
                (*(void (__fastcall **)(char *, struct CWorkspace *))(*(_QWORD *)v3 + 8LL))(v3, v20);
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v19 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                  v19,
                  v18);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
                v17,
                v16);
            }
            ++v7;
          }
          if ( v8 == 259
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            break;
          }
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DLD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            v10,
            v7++,
            v9);
        }
        ++v7;
      }
      while ( v8 != 259 );
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 19;
LABEL_7:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix,
      DefaultWorkspaceGUID);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  LeaveCriticalSection(v2);
  std::wstring::~wstring(v23);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v20);
}

```

## disassembly

```asm
0x1800294b4  mov     rax, rsp
0x1800294b7  push    rbp
0x1800294b8  push    rdi
0x1800294b9  push    r12
0x1800294bb  push    r14
0x1800294bd  push    r15
0x1800294bf  lea     rbp, [rax-1D8h]
0x1800294c6  sub     rsp, 2B0h
0x1800294cd  mov     qword ptr [rsp+2D0h+var_268], 0FFFFFFFFFFFFFFFEh
0x1800294d6  mov     [rax+10h], rbx
0x1800294da  mov     [rax+18h], rsi
0x1800294de  mov     rax, cs:__security_cookie
0x1800294e5  xor     rax, rsp
0x1800294e8  mov     [rbp+1D0h+var_30], rax
0x1800294ef  mov     rbx, rcx
0x1800294f2  mov     [rsp+2D0h+hKey], 0
0x1800294fb  mov     [rsp+2D0h+cchName], 104h
0x180029503  mov     [rsp+2D0h+var_280], 0
0x18002950c  lea     rcx, [rsp+2D0h+var_260]
0x180029511  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180029516  nop
0x180029517  lea     r12, [rbx+18h]
0x18002951b  mov     rcx, r12; lpCriticalSection
0x18002951e  call    cs:__imp_EnterCriticalSection
0x180029524  lea     r15, [rbx+40h]
0x180029528  mov     rax, [r15]
0x18002952b  mov     rcx, r15
0x18002952e  mov     rax, [rax+18h]
0x180029532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029537  lea     rcx, [rsp+2D0h+var_260]
0x18002953c  call    ?ReadDefaultWorkspaceGUID@CWorkspaceManager@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWorkspaceManager::ReadDefaultWorkspaceGUID(std::wstring &)
0x180029541  mov     ebx, eax
0x180029543  mov     eax, 80000000h
0x180029548  lea     ecx, [rbx+rax]
0x18002954b  test    eax, ecx
0x18002954d  jnz     loc_180029600
0x180029553  cmp     ebx, 80070002h
0x180029559  jz      loc_180029600
0x18002955f  lea     rdi, WPP_GLOBAL_Control
0x180029566  mov     rcx, cs:WPP_GLOBAL_Control
0x18002956d  cmp     rcx, rdi
0x180029570  jz      short loc_1800295A6
0x180029572  test    byte ptr [rcx+1Ch], 8
0x180029576  jz      short loc_1800295A6
0x180029578  cmp     byte ptr [rcx+19h], 2
0x18002957c  jb      short loc_1800295A6
0x18002957e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029583  mov     edx, 13h
0x180029588  mov     [rsp+2D0h+dwOptions], ebx
0x18002958c  mov     r9d, eax
0x18002958f  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180029596  mov     rcx, cs:WPP_GLOBAL_Control
0x18002959d  mov     rcx, [rcx+10h]
0x1800295a1  call    WPP_SF_Dd
0x1800295a6  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800295ab  test    rcx, rcx
0x1800295ae  jz      short loc_1800295B6
0x1800295b0  call    cs:__imp_RegCloseKey
0x1800295b6  mov     rcx, r12; lpCriticalSection
0x1800295b9  call    cs:__imp_LeaveCriticalSection
0x1800295bf  nop
0x1800295c0  lea     rcx, [rsp+2D0h+var_260]; void *
0x1800295c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800295ca  nop
0x1800295cb  lea     rcx, [rsp+2D0h+var_280]
0x1800295d0  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x1800295d5  mov     rcx, [rbp+1D0h+var_30]
0x1800295dc  xor     rcx, rsp; StackCookie
0x1800295df  call    __security_check_cookie
0x1800295e4  lea     r11, [rsp+2D0h+var_20]
0x1800295ec  mov     rbx, [r11+38h]
0x1800295f0  mov     rsi, [r11+40h]
0x1800295f4  mov     rsp, r11
0x1800295f7  pop     r15
0x1800295f9  pop     r14
0x1800295fb  pop     r12
0x1800295fd  pop     rdi
0x1800295fe  pop     rbp
0x1800295ff  retn
0x180029600  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x180029609  lea     rax, [rsp+2D0h+hKey]
0x18002960e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180029613  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002961c  mov     [rsp+2D0h+samDesired], 20019h; samDesired
0x180029624  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x18002962c  xor     r9d, r9d; lpClass
0x18002962f  xor     r8d, r8d; Reserved
0x180029632  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x180029639  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180029640  call    cs:__imp_RegCreateKeyExW
0x180029646  mov     ebx, eax
0x180029648  test    eax, eax
0x18002964a  jz      short loc_180029693
0x18002964c  lea     rdi, WPP_GLOBAL_Control
0x180029653  mov     rax, cs:WPP_GLOBAL_Control
0x18002965a  cmp     rax, rdi
0x18002965d  jz      loc_1800295A6
0x180029663  test    byte ptr [rax+1Ch], 8
0x180029667  jz      loc_1800295A6
0x18002966d  cmp     byte ptr [rax+19h], 2
0x180029671  jb      loc_1800295A6
0x180029677  test    ebx, ebx
0x180029679  jle     short loc_180029684
0x18002967b  movzx   ebx, bx
0x18002967e  or      ebx, 80070000h
0x180029684  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029689  mov     edx, 14h
0x18002968e  jmp     loc_180029588
0x180029693  xor     esi, esi
0x180029695  lea     rdi, WPP_GLOBAL_Control
0x18002969c  cmp     [rsp+2D0h+var_280], 0
0x1800296a2  jz      short loc_1800296C1
0x1800296a4  lea     rcx, [rsp+2D0h+var_280]
0x1800296a9  call    ?SafeRelease@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeRelease(void)
0x1800296ae  mov     [rsp+2D0h+var_280], 0
0x1800296b7  lea     rcx, [rsp+2D0h+var_280]
0x1800296bc  call    ?SafeAddRef@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeAddRef(void)
0x1800296c1  mov     [rsp+2D0h+cchName], 104h
0x1800296c9  mov     [rsp+2D0h+phkResult], 0; lpftLastWriteTime
0x1800296d2  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpcchClass
0x1800296db  mov     qword ptr [rsp+2D0h+samDesired], 0; lpClass
0x1800296e4  mov     qword ptr [rsp+2D0h+dwOptions], 0; lpReserved
0x1800296ed  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800296f2  lea     r8, [rbp+1D0h+Name]; lpName
0x1800296f6  mov     edx, esi; dwIndex
0x1800296f8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800296fd  call    cs:__imp_RegEnumKeyExW
0x180029703  mov     ebx, eax
0x180029705  test    eax, eax
0x180029707  jz      short loc_18002976E
0x180029709  cmp     eax, 103h
0x18002970e  jz      short loc_18002975B
0x180029710  mov     rcx, cs:WPP_GLOBAL_Control
0x180029717  cmp     rcx, rdi
0x18002971a  jz      short loc_18002975B
0x18002971c  test    byte ptr [rcx+1Ch], 1
0x180029720  jz      short loc_18002975B
0x180029722  cmp     byte ptr [rcx+19h], 2
0x180029726  jb      short loc_18002975B
0x180029728  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002972d  mov     edx, 15h
0x180029732  mov     [rsp+2D0h+samDesired], ebx
0x180029736  mov     [rsp+2D0h+dwOptions], esi
0x18002973a  mov     r9d, eax
0x18002973d  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180029744  mov     rcx, cs:WPP_GLOBAL_Control
0x18002974b  mov     rcx, [rcx+10h]
0x18002974f  call    WPP_SF_DLD
0x180029754  inc     esi
0x180029756  jmp     loc_18002969C
0x18002975b  inc     esi
0x18002975d  cmp     ebx, 103h
0x180029763  jnz     loc_18002969C
0x180029769  jmp     loc_1800295A6
0x18002976e  lea     rcx, [rsp+2D0h+var_260]
0x180029773  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029778  mov     r8, rax; lpString2
0x18002977b  mov     [rsp+2D0h+dwOptions], 1; bIgnoreCase
0x180029783  or      r9d, 0FFFFFFFFh; cchCount2
0x180029787  or      edx, r9d; cchCount1
0x18002978a  lea     rcx, [rbp+1D0h+Name]; lpString1
0x18002978e  call    cs:__imp_CompareStringOrdinal
0x180029794  mov     r14d, eax
0x180029797  test    eax, eax
0x180029799  jnz     short loc_1800297E2
0x18002979b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297a2  cmp     rcx, rdi
0x1800297a5  jz      short loc_1800297E2
0x1800297a7  test    byte ptr [rcx+1Ch], 1
0x1800297ab  jz      short loc_1800297E2
0x1800297ad  cmp     byte ptr [rcx+19h], 2
0x1800297b1  jb      short loc_1800297E2
0x1800297b3  call    cs:__imp_GetLastError
0x1800297b9  mov     ebx, eax
0x1800297bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800297c0  lea     edx, [r14+16h]
0x1800297c4  mov     [rsp+2D0h+dwOptions], ebx
0x1800297c8  mov     r9d, eax
0x1800297cb  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800297d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297d9  mov     rcx, [rcx+10h]
0x1800297dd  call    WPP_SF_Dd
0x1800297e2  xor     ebx, ebx
0x1800297e4  cmp     r14d, 2
0x1800297e8  setz    bl
0x1800297eb  lea     rcx, [rsp+2D0h+var_280]; struct CWorkspace **
0x1800297f0  call    ?CreateInstance@CWorkspace@@SAJPEAPEAV1@@Z; CWorkspace::CreateInstance(CWorkspace * *)
0x1800297f5  mov     r14d, eax
0x1800297f8  test    eax, eax
0x1800297fa  jns     short loc_180029844
0x1800297fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029803  cmp     rcx, rdi
0x180029806  jz      short loc_18002983D
0x180029808  test    byte ptr [rcx+1Ch], 1
0x18002980c  jz      short loc_18002983D
0x18002980e  cmp     byte ptr [rcx+19h], 2
0x180029812  jb      short loc_18002983D
0x180029814  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029819  mov     edx, 17h
0x18002981e  mov     [rsp+2D0h+dwOptions], r14d
0x180029823  mov     r9d, eax
0x180029826  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002982d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029834  mov     rcx, [rcx+10h]
0x180029838  call    WPP_SF_Dd
0x18002983d  inc     esi
0x18002983f  jmp     loc_18002969C
0x180029844  mov     rax, [rsp+2D0h+var_280]
0x180029849  mov     [rax+60h], ebx
0x18002984c  lea     r8, [rbp+1D0h+Name]; unsigned __int16 *
0x180029850  mov     rdx, [rsp+2D0h+hKey]; HKEY
0x180029855  mov     rcx, [rsp+2D0h+var_280]; this
0x18002985a  call    ?InitializeFromRegistry@CWorkspace@@QEAAJPEAUHKEY__@@PEAG@Z; CWorkspace::InitializeFromRegistry(HKEY__ *,ushort *)
0x18002985f  mov     ebx, eax
0x180029861  test    eax, eax
0x180029863  jns     short loc_18002988D
0x180029865  mov     rcx, cs:WPP_GLOBAL_Control
0x18002986c  cmp     rcx, rdi
0x18002986f  jz      short loc_18002983D
0x180029871  test    byte ptr [rcx+1Ch], 1
0x180029875  jz      short loc_18002983D
0x180029877  cmp     byte ptr [rcx+19h], 2
0x18002987b  jb      short loc_18002983D
0x18002987d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180029882  mov     edx, 18h
0x180029887  mov     [rsp+2D0h+dwOptions], ebx
0x18002988b  jmp     short loc_180029823
0x18002988d  mov     rax, [r15]
0x180029890  mov     rdx, [rsp+2D0h+var_280]
0x180029895  mov     rcx, r15
0x180029898  mov     rax, [rax+8]
0x18002989c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a1  jmp     short loc_18002983D
```
