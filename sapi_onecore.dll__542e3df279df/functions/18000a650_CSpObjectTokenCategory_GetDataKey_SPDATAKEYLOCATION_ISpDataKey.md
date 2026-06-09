# CSpObjectTokenCategory::GetDataKey(SPDATAKEYLOCATION,ISpDataKey * *)

- ea: `0x18000a650`
- end: `0x18000aae6`
- name: `?GetDataKey@CSpObjectTokenCategory@@UEAAJW4SPDATAKEYLOCATION@@PEAPEAUISpDataKey@@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CSpObjectTokenCategory *__hidden this, enum SPDATAKEYLOCATION, struct ISpDataKey **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a420`
- `0x18000a650`
- `0x180018d10`
- `0x180026508`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a77a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a77a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000a92c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000a92c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aa44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aa44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a803`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a9a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a803`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a9a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a9ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a9ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aabc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aabc`

## string_xrefs

- `0x18000a73f`: `HKEY_CURRENT_CONFIG\`
- `0x18000a820`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`
- `0x18000a902`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSpObjectTokenCategory::GetDataKey(
        CSpObjectTokenCategory *this,
        enum SPDATAKEYLOCATION a2,
        struct ISpDataKey **a3)
{
  HKEY v4; // rdi
  int InitializedSingleton; // ebx
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  unsigned __int16 *v8; // rdx
  const wchar_t *v9; // r12
  HKEY v10; // r15
  unsigned int v11; // r13d
  HKEY v12; // r14
  int i; // ebx
  __int64 v14; // r8
  int v15; // esi
  unsigned __int16 *v16; // rdx
  unsigned __int64 j; // rax
  int v18; // eax
  bool v19; // sf
  HKEY v20; // rcx
  HKEY v21; // rdx
  unsigned __int64 k; // rax
  LSTATUS v23; // eax
  const WCHAR *v24; // r14
  int dwOptions; // [rsp+20h] [rbp-59h]
  int dwOptionsa; // [rsp+20h] [rbp-59h]
  LPVOID ppv; // [rsp+50h] [rbp-29h] BYREF
  HKEY v29; // [rsp+58h] [rbp-21h] BYREF
  const wchar_t *v30; // [rsp+60h] [rbp-19h]
  _QWORD v31[13]; // [rsp+68h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  HKEY hKey; // [rsp+E0h] [rbp+67h] BYREF
  struct ISpDataKey **v34; // [rsp+F0h] [rbp+77h]
  HKEY phkResult; // [rsp+F8h] [rbp+7Fh] BYREF

  v34 = a3;
  v4 = 0;
  if ( *((_QWORD *)this + 9) )
  {
    if ( a3 )
    {
      v6 = (unsigned int)(a2 - 1);
      if ( (_DWORD)v6 )
      {
        v6 = (unsigned int)(v6 - 1);
        if ( (_DWORD)v6 )
        {
          if ( (_DWORD)v6 == 3 )
            v7 = -2147483643;
          else
            v7 = 0;
        }
        else
        {
          v7 = -2147483646;
        }
      }
      else
      {
        v7 = -2147483647;
      }
      v29 = (HKEY)v7;
      hKey = 0;
      if ( (int)CSpRegistryIsolator::GetInitializedSingleton(
                  (struct CSpRegistryIsolator **)&hKey,
                  (unsigned __int16 *)v6) >= 0
        && hKey
        && CSpRegistryIsolator::ReplaceWithIsolatedKeyIfAvailable((CSpRegistryIsolator *)hKey, (HKEY)v7, &v29) >= 0 )
      {
        v4 = v29;
      }
      else
      {
        v29 = 0;
      }
      v9 = (const wchar_t *)*((_QWORD *)this + 8);
      v10 = 0;
      v11 = 0;
      v30 = L"HKEY_CLASSES_ROOT\\";
      v31[0] = 0xFFFFFFFF80000000uLL;
      v31[1] = L"HKEY_LOCAL_MACHINE\\";
      v31[2] = -2147483646;
      v31[3] = L"HKEY_CURRENT_USER\\";
      v31[4] = -2147483647;
      v31[5] = L"HKEY_CURRENT_CONFIG\\";
      v31[6] = -2147483643;
      hKey = 0;
      v12 = 0;
      for ( i = 0; i < 4; ++i )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v31[2 * i - 1] + 2 * v14) );
        if ( !(unsigned int)_o__wcsnicmp(v9) )
        {
          v12 = (HKEY)v31[2 * i];
          break;
        }
      }
      v15 = 0;
      phkResult = 0;
      if ( (int)CSpRegistryIsolator::GetInitializedSingleton((struct CSpRegistryIsolator **)&phkResult, v8) >= 0
        && phkResult )
      {
        hKey = v12;
        for ( j = 0; j < *((_QWORD *)phkResult + 1); ++j )
        {
          v16 = (unsigned __int16 *)(2 * j);
          if ( v12 == *(HKEY *)(*(_QWORD *)phkResult + 16 * j + 8) )
          {
            v18 = RegCreateKeyExW(
                    *((HKEY *)phkResult + 3),
                    *(LPCWSTR *)(*(_QWORD *)phkResult + 16 * j),
                    0,
                    0,
                    1u,
                    0xF003Fu,
                    0,
                    &hKey,
                    0);
            v19 = v18 < 0;
            if ( v18 > 0 )
            {
              v18 = (unsigned __int16)v18 | 0x80070000;
              v19 = v18 < 0;
            }
            if ( v19 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5F,
                (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
                (const char *)(unsigned int)v18,
                dwOptions);
              hKey = 0;
            }
            break;
          }
        }
      }
      if ( hKey )
      {
        if ( v4 )
        {
          if ( hKey )
            RegCloseKey(hKey);
          hKey = v4;
        }
        phkResult = 0;
        InitializedSingleton = CSpRegistryIsolator::GetInitializedSingleton(
                                 (struct CSpRegistryIsolator **)&phkResult,
                                 v16);
        if ( InitializedSingleton >= 0 )
        {
          v20 = phkResult;
          if ( phkResult )
          {
            v21 = hKey;
            phkResult = hKey;
            for ( k = 0; k < *((_QWORD *)v20 + 1); ++k )
            {
              if ( hKey == *(HKEY *)(*(_QWORD *)v20 + 16 * k + 8) )
              {
                v23 = RegCreateKeyExW(
                        *((HKEY *)v20 + 3),
                        *(LPCWSTR *)(*(_QWORD *)v20 + 16 * k),
                        0,
                        0,
                        1u,
                        0xF003Fu,
                        0,
                        &phkResult,
                        0);
                InitializedSingleton = v23;
                if ( v23 > 0 )
                  InitializedSingleton = (unsigned __int16)v23 | 0x80070000;
                if ( InitializedSingleton < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x5F,
                    (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
                    (const char *)(unsigned int)InitializedSingleton,
                    dwOptionsa);
                  goto LABEL_61;
                }
                v21 = phkResult;
                break;
              }
            }
            hKey = v21;
            phkResult = 0;
            v24 = wcschr(v9, 0x5Cu) + 1;
            if ( !RegCreateKeyExW(hKey, v24, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0) )
              goto LABEL_60;
            v15 = 1;
            InitializedSingleton = RegCreateKeyExW(hKey, v24, 0, 0, 1u, 0x20019u, 0, &phkResult, 0);
            if ( InitializedSingleton == 5 )
              InitializedSingleton = RegOpenKeyExW(hKey, v24, 0, 0x20019u, &phkResult);
            if ( InitializedSingleton )
            {
              if ( InitializedSingleton == 2 || InitializedSingleton == 259 )
              {
                InitializedSingleton = -2147200966;
              }
              else if ( InitializedSingleton > 0 )
              {
                InitializedSingleton = (unsigned __int16)InitializedSingleton | 0x80070000;
              }
            }
            else
            {
LABEL_60:
              v10 = phkResult;
              InitializedSingleton = 0;
              v11 = v15;
            }
          }
          else
          {
            InitializedSingleton = -2147024882;
          }
        }
      }
      else
      {
        InitializedSingleton = -2147200960;
      }
LABEL_61:
      if ( hKey != v4 && hKey )
        RegCloseKey(hKey);
      ppv = 0;
      if ( InitializedSingleton < 0
        || (InitializedSingleton = CoCreateInstance(
                                     &CLSID_SpDataKey,
                                     0,
                                     0x17u,
                                     &GUID_92a66e2b_c830_4149_83df_6fc2ba1e7a5b,
                                     &ppv),
            InitializedSingleton < 0)
        || (InitializedSingleton = (*(__int64 (__fastcall **)(LPVOID, HKEY, _QWORD))(*(_QWORD *)ppv + 120LL))(
                                     ppv,
                                     v10,
                                     v11),
            InitializedSingleton < 0)
        || (v10 = 0,
            InitializedSingleton = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISpDataKey **))ppv)(
                                     ppv,
                                     &GUID_14056581_e16c_11d2_bb90_00c04f8ee6c0,
                                     v34),
            InitializedSingleton < 0) )
      {
        if ( v10 )
          RegCloseKey(v10);
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v4 )
        RegCloseKey(v4);
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147201023;
  }
  return (unsigned int)InitializedSingleton;
}

```

## disassembly

```asm
0x18000a650  mov     [rsp-8+arg_8], rbx
0x18000a655  mov     [rsp-8+arg_10], r8
0x18000a65a  push    rbp
0x18000a65b  push    rsi
0x18000a65c  push    rdi
0x18000a65d  push    r12
0x18000a65f  push    r13
0x18000a661  push    r14
0x18000a663  push    r15
0x18000a665  lea     rbp, [rsp-27h]
0x18000a66a  sub     rsp, 0A0h
0x18000a671  mov     rax, r8
0x18000a674  mov     rsi, rcx
0x18000a677  xor     edi, edi
0x18000a679  cmp     [rcx+48h], rdi
0x18000a67d  jnz     short loc_18000A689
0x18000a67f  mov     ebx, 80045001h
0x18000a684  jmp     loc_18000AAC9
0x18000a689  test    rax, rax
0x18000a68c  jz      loc_18000AAC4
0x18000a692  mov     r14, 0FFFFFFFF80000005h
0x18000a699  sub     edx, 1; unsigned __int16 *
0x18000a69c  jz      short loc_18000A6BB
0x18000a69e  sub     edx, 1
0x18000a6a1  jz      short loc_18000A6B2
0x18000a6a3  cmp     edx, 3
0x18000a6a6  jz      short loc_18000A6AD
0x18000a6a8  mov     rbx, rdi
0x18000a6ab  jmp     short loc_18000A6C2
0x18000a6ad  mov     rbx, r14
0x18000a6b0  jmp     short loc_18000A6C2
0x18000a6b2  mov     rbx, 0FFFFFFFF80000002h
0x18000a6b9  jmp     short loc_18000A6C2
0x18000a6bb  mov     rbx, 0FFFFFFFF80000001h
0x18000a6c2  mov     [rbp+57h+var_78], rbx
0x18000a6c6  mov     [rbp+57h+hKey], rdi
0x18000a6ca  lea     rcx, [rbp+57h+hKey]; struct CSpRegistryIsolator **
0x18000a6ce  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000a6d3  test    eax, eax
0x18000a6d5  js      short loc_18000A6F6
0x18000a6d7  mov     rcx, [rbp+57h+hKey]; this
0x18000a6db  test    rcx, rcx
0x18000a6de  jz      short loc_18000A6F6
0x18000a6e0  lea     r8, [rbp+57h+var_78]; HKEY *
0x18000a6e4  mov     rdx, rbx; HKEY
0x18000a6e7  call    ?ReplaceWithIsolatedKeyIfAvailable@CSpRegistryIsolator@@QEAAJPEAUHKEY__@@PEAPEAU2@@Z; CSpRegistryIsolator::ReplaceWithIsolatedKeyIfAvailable(HKEY__ *,HKEY__ * *)
0x18000a6ec  test    eax, eax
0x18000a6ee  js      short loc_18000A6F6
0x18000a6f0  mov     rdi, [rbp+57h+var_78]
0x18000a6f4  jmp     short loc_18000A6FA
0x18000a6f6  mov     [rbp+57h+var_78], rdi
0x18000a6fa  mov     r12, [rsi+40h]
0x18000a6fe  xor     esi, esi
0x18000a700  mov     r15d, esi
0x18000a703  mov     r13d, esi
0x18000a706  lea     rax, aHkeyClassesRoo; "HKEY_CLASSES_ROOT\\"
0x18000a70d  mov     [rbp+57h+var_70], rax
0x18000a711  mov     [rbp+57h+var_68], 0FFFFFFFF80000000h
0x18000a719  lea     rax, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\"
0x18000a720  mov     [rbp+57h+var_60], rax
0x18000a724  mov     [rbp+57h+var_58], 0FFFFFFFF80000002h
0x18000a72c  lea     rax, aHkeyCurrentUse_4; "HKEY_CURRENT_USER\\"
0x18000a733  mov     [rbp+57h+var_50], rax
0x18000a737  mov     [rbp+57h+var_48], 0FFFFFFFF80000001h
0x18000a73f  lea     rax, aHkeyCurrentCon; "HKEY_CURRENT_CONFIG\\"
0x18000a746  mov     [rbp+57h+var_40], rax
0x18000a74a  mov     [rbp+57h+var_38], r14
0x18000a74e  mov     [rbp+57h+hKey], rsi
0x18000a752  mov     r14d, esi
0x18000a755  mov     ebx, esi
0x18000a757  cmp     ebx, 4
0x18000a75a  jge     short loc_18000A78D
0x18000a75c  movsxd  rsi, ebx
0x18000a75f  add     rsi, rsi
0x18000a762  mov     rdx, [rbp+rsi*8+57h+var_70]
0x18000a767  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a76b  xor     eax, eax
0x18000a76d  inc     r8
0x18000a770  cmp     [rdx+r8*2], ax
0x18000a775  jnz     short loc_18000A76D
0x18000a777  mov     rcx, r12
0x18000a77a  call    cs:__imp__o__wcsnicmp
0x18000a780  test    eax, eax
0x18000a782  jz      short loc_18000A788
0x18000a784  inc     ebx
0x18000a786  jmp     short loc_18000A757
0x18000a788  mov     r14, [rbp+rsi*8+57h+var_68]
0x18000a78d  xor     esi, esi
0x18000a78f  mov     [rbp+57h+arg_18], rsi
0x18000a793  lea     rcx, [rbp+57h+arg_18]; struct CSpRegistryIsolator **
0x18000a797  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000a79c  test    eax, eax
0x18000a79e  js      loc_18000A835
0x18000a7a4  mov     rcx, [rbp+57h+arg_18]
0x18000a7a8  test    rcx, rcx
0x18000a7ab  jz      loc_18000A835
0x18000a7b1  mov     [rbp+57h+hKey], r14
0x18000a7b5  mov     eax, esi
0x18000a7b7  cmp     rax, [rcx+8]
0x18000a7bb  jnb     short loc_18000A835
0x18000a7bd  mov     rdx, rax
0x18000a7c0  add     rdx, rdx
0x18000a7c3  mov     r10, [rcx]
0x18000a7c6  cmp     r14, [r10+rdx*8+8]
0x18000a7cb  jz      short loc_18000A7D2
0x18000a7cd  inc     rax
0x18000a7d0  jmp     short loc_18000A7B7
0x18000a7d2  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x18000a7d7  lea     rax, [rbp+57h+hKey]
0x18000a7db  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000a7e0  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a7e5  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18000a7ed  mov     [rsp+0D0h+dwOptions], 1; int
0x18000a7f5  xor     r9d, r9d; lpClass
0x18000a7f8  xor     r8d, r8d; Reserved
0x18000a7fb  mov     rdx, [r10+rdx*8]; lpSubKey
0x18000a7ff  mov     rcx, [rcx+18h]; hKey
0x18000a803  call    cs:__imp_RegCreateKeyExW
0x18000a809  test    eax, eax
0x18000a80b  jle     short loc_18000A817
0x18000a80d  movzx   eax, ax
0x18000a810  or      eax, 80070000h
0x18000a815  test    eax, eax
0x18000a817  jns     short loc_18000A835
0x18000a819  mov     rcx, [rbp+5Fh]; this
0x18000a81d  mov     r9d, eax; char *
0x18000a820  lea     r8, aOnecoreuapEndu_348; "onecoreuap\\enduser\\NUI\\OneCore\\sapi"...
0x18000a827  mov     edx, 5Fh ; '_'; void *
0x18000a82c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a831  mov     [rbp+57h+hKey], rsi
0x18000a835  cmp     [rbp+57h+hKey], rsi
0x18000a839  jnz     short loc_18000A845
0x18000a83b  mov     ebx, 80045040h
0x18000a840  jmp     loc_18000AA0B
0x18000a845  test    rdi, rdi
0x18000a848  jz      short loc_18000A85D
0x18000a84a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a84e  test    rcx, rcx
0x18000a851  jz      short loc_18000A859
0x18000a853  call    cs:__imp_RegCloseKey
0x18000a859  mov     [rbp+57h+hKey], rdi
0x18000a85d  mov     [rbp+57h+arg_18], rsi
0x18000a861  lea     rcx, [rbp+57h+arg_18]; struct CSpRegistryIsolator **
0x18000a865  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x18000a86a  mov     ebx, eax
0x18000a86c  test    eax, eax
0x18000a86e  js      loc_18000AA0B
0x18000a874  mov     rcx, [rbp+57h+arg_18]
0x18000a878  test    rcx, rcx
0x18000a87b  jnz     short loc_18000A887
0x18000a87d  mov     ebx, 8007000Eh
0x18000a882  jmp     loc_18000AA0B
0x18000a887  mov     rdx, [rbp+57h+hKey]
0x18000a88b  mov     [rbp+57h+arg_18], rdx
0x18000a88f  mov     rax, rsi
0x18000a892  cmp     rax, [rcx+8]
0x18000a896  jnb     loc_18000A91C
0x18000a89c  mov     r10, rax
0x18000a89f  add     r10, r10
0x18000a8a2  mov     r11, [rcx]
0x18000a8a5  cmp     rdx, [r11+r10*8+8]
0x18000a8aa  jz      short loc_18000A8B1
0x18000a8ac  inc     rax
0x18000a8af  jmp     short loc_18000A892
0x18000a8b1  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x18000a8b6  lea     rax, [rbp+57h+arg_18]
0x18000a8ba  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000a8bf  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a8c4  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18000a8cc  mov     [rsp+0D0h+dwOptions], 1; int
0x18000a8d4  xor     r9d, r9d; lpClass
0x18000a8d7  xor     r8d, r8d; Reserved
0x18000a8da  mov     rdx, [r11+r10*8]; lpSubKey
0x18000a8de  mov     rcx, [rcx+18h]; hKey
0x18000a8e2  call    cs:__imp_RegCreateKeyExW
0x18000a8e8  mov     ebx, eax
0x18000a8ea  test    eax, eax
0x18000a8ec  jle     short loc_18000A8F7
0x18000a8ee  movzx   ebx, ax
0x18000a8f1  or      ebx, 80070000h
0x18000a8f7  test    ebx, ebx
0x18000a8f9  jns     short loc_18000A918
0x18000a8fb  mov     rcx, [rbp+5Fh]; this
0x18000a8ff  mov     r9d, ebx; char *
0x18000a902  lea     r8, aOnecoreuapEndu_348; "onecoreuap\\enduser\\NUI\\OneCore\\sapi"...
0x18000a909  mov     edx, 5Fh ; '_'; void *
0x18000a90e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a913  jmp     loc_18000AA0B
0x18000a918  mov     rdx, [rbp+57h+arg_18]
0x18000a91c  mov     [rbp+57h+hKey], rdx
0x18000a920  mov     [rbp+57h+arg_18], rsi
0x18000a924  mov     edx, 5Ch ; '\'; Ch
0x18000a929  mov     rcx, r12; Str
0x18000a92c  call    cs:__imp_wcschr
0x18000a932  lea     r14, [rax+2]
0x18000a936  xor     r12d, r12d
0x18000a939  mov     [rsp+0D0h+lpdwDisposition], r12; lpdwDisposition
0x18000a93e  lea     rax, [rbp+57h+arg_18]
0x18000a942  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000a947  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000a94c  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18000a954  mov     [rsp+0D0h+dwOptions], 1; dwOptions
0x18000a95c  xor     r9d, r9d; lpClass
0x18000a95f  xor     r8d, r8d; Reserved
0x18000a962  mov     rdx, r14; lpSubKey
0x18000a965  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a969  call    cs:__imp_RegCreateKeyExW
0x18000a96f  test    eax, eax
0x18000a971  jz      loc_18000A9FF
0x18000a977  lea     esi, [r12+1]
0x18000a97c  mov     [rsp+0D0h+lpdwDisposition], r12; lpdwDisposition
0x18000a981  lea     rax, [rbp+57h+arg_18]
0x18000a985  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000a98a  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000a98f  mov     [rsp+0D0h+samDesired], 20019h; samDesired
0x18000a997  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x18000a99b  xor     r9d, r9d; lpClass
0x18000a99e  xor     r8d, r8d; Reserved
0x18000a9a1  mov     rdx, r14; lpSubKey
0x18000a9a4  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a9a8  call    cs:__imp_RegCreateKeyExW
0x18000a9ae  mov     ebx, eax
0x18000a9b0  cmp     eax, 5
0x18000a9b3  jnz     short loc_18000A9D6
0x18000a9b5  lea     rax, [rbp+57h+arg_18]
0x18000a9b9  mov     qword ptr [rsp+0D0h+dwOptions], rax; phkResult
0x18000a9be  mov     r9d, 20019h; samDesired
0x18000a9c4  xor     r8d, r8d; ulOptions
0x18000a9c7  mov     rdx, r14; lpSubKey
0x18000a9ca  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a9ce  call    cs:__imp_RegOpenKeyExW
0x18000a9d4  mov     ebx, eax
0x18000a9d6  test    ebx, ebx
0x18000a9d8  jz      short loc_18000A9FF
0x18000a9da  cmp     ebx, 2
0x18000a9dd  jz      short loc_18000A9F8
0x18000a9df  cmp     ebx, 103h
0x18000a9e5  jz      short loc_18000A9F8
0x18000a9e7  xor     esi, esi
0x18000a9e9  test    ebx, ebx
0x18000a9eb  jle     short loc_18000AA0B
0x18000a9ed  movzx   ebx, bx
0x18000a9f0  or      ebx, 80070000h
0x18000a9f6  jmp     short loc_18000AA0B
0x18000a9f8  mov     ebx, 8004503Ah
0x18000a9fd  jmp     short loc_18000AA09
0x18000a9ff  mov     r15, [rbp+57h+arg_18]
0x18000aa03  mov     ebx, r12d
0x18000aa06  mov     r13d, esi
0x18000aa09  xor     esi, esi
0x18000aa0b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000aa0f  cmp     rcx, rdi
0x18000aa12  jz      short loc_18000AA1F
0x18000aa14  test    rcx, rcx
0x18000aa17  jz      short loc_18000AA1F
0x18000aa19  call    cs:__imp_RegCloseKey
0x18000aa1f  mov     [rbp+57h+ppv], rsi
0x18000aa23  test    ebx, ebx
0x18000aa25  js      short loc_18000AA8F
0x18000aa27  lea     rax, [rbp+57h+ppv]
0x18000aa2b  mov     qword ptr [rsp+0D0h+dwOptions], rax; ppv
0x18000aa30  lea     r9, _GUID_92a66e2b_c830_4149_83df_6fc2ba1e7a5b; riid
0x18000aa37  xor     edx, edx; pUnkOuter
0x18000aa39  lea     r8d, [rdx+17h]; dwClsContext
0x18000aa3d  lea     rcx, CLSID_SpDataKey; rclsid
0x18000aa44  call    cs:__imp_CoCreateInstance
0x18000aa4a  mov     ebx, eax
0x18000aa4c  test    eax, eax
0x18000aa4e  js      short loc_18000AA8F
0x18000aa50  mov     rcx, [rbp+57h+ppv]
0x18000aa54  mov     rax, [rcx]
0x18000aa57  mov     r8d, r13d
0x18000aa5a  mov     rdx, r15
0x18000aa5d  mov     rax, [rax+78h]
0x18000aa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa66  mov     ebx, eax
0x18000aa68  test    eax, eax
0x18000aa6a  js      short loc_18000AA8F
0x18000aa6c  mov     r15, rsi
0x18000aa6f  mov     rcx, [rbp+57h+ppv]
0x18000aa73  mov     rax, [rcx]
0x18000aa76  mov     r8, [rbp+57h+arg_10]
0x18000aa7a  lea     rdx, _GUID_14056581_e16c_11d2_bb90_00c04f8ee6c0
0x18000aa81  mov     rax, [rax]
0x18000aa84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa89  mov     ebx, eax
0x18000aa8b  test    eax, eax
0x18000aa8d  jns     short loc_18000AA9E
0x18000aa8f  test    r15, r15
0x18000aa92  jz      short loc_18000AA9E
0x18000aa94  mov     rcx, r15; hKey
0x18000aa97  call    cs:__imp_RegCloseKey
0x18000aa9d  nop
0x18000aa9e  mov     rcx, [rbp+57h+ppv]
0x18000aaa2  test    rcx, rcx
0x18000aaa5  jz      short loc_18000AAB4
0x18000aaa7  mov     rax, [rcx]
0x18000aaaa  mov     rax, [rax+10h]
0x18000aaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab3  nop
  ... truncated ...
```
