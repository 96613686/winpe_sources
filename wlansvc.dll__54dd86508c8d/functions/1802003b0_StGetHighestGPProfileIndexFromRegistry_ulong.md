# StGetHighestGPProfileIndexFromRegistry(ulong *)

- ea: `0x1802003b0`
- end: `0x180200773`
- name: `?StGetHighestGPProfileIndexFromRegistry@@YAKPEAK@Z`
- size: `963`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180200d34`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18007018c`
- `0x180106340`
- `0x180107330`
- `0x1802003b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18020060b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18020060b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020050f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802005cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020050f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802005cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18020061d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18020061d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200702`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802005a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802005a3`

## pseudocode

```c
__int64 __fastcall StGetHighestGPProfileIndexFromRegistry(unsigned int *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  unsigned int RegistryRoot; // eax
  unsigned int v5; // eax
  unsigned int v6; // edi
  DWORD i; // esi
  unsigned int v8; // eax
  unsigned int v9; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(Name, 0, 0x4Eu);
  cchName = 39;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 94, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = 87;
    goto LABEL_49;
  }
  *a1 = 0;
  memset_0(SubKey, 0, 0x208u);
  RegistryRoot = StpGetRegistryRoot(
                   (unsigned int)SubKey,
                   260,
                   (unsigned int)L"Software\\Microsoft\\Wlansvc",
                   (unsigned int)L"GroupPolicy\\Profiles",
                   0);
  v3 = RegistryRoot;
  if ( !RegistryRoot )
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 9u, &hKey);
    v3 = v5;
    if ( v5 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 96, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v5);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 == 2 )
        v3 = 0;
      goto LABEL_49;
    }
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 39;
      v8 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v3 = v8;
      if ( v8 )
        break;
      v9 = RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult);
      v3 = v9;
      if ( v9 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 98, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v9);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_44;
      }
      cbData = 4;
      v3 = RegQueryValueExW(phkResult, L"ProfileIndex", 0, 0, Data, &cbData);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v3 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 99, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v3);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 != 2 )
          goto LABEL_44;
      }
      else if ( *(_DWORD *)Data > v6 )
      {
        v6 = *(_DWORD *)Data;
      }
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 97, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v8);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 == 259 )
      v3 = 0;
LABEL_44:
    if ( hKey )
    {
      RegCloseKey(hKey);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 )
      goto LABEL_49;
    *a1 = v6;
    goto LABEL_48;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 95, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, RegistryRoot);
LABEL_48:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_49:
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_d(v2[12], 100, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1802003b0  mov     [rsp-8+arg_8], rbx
0x1802003b5  mov     [rsp-8+arg_10], rsi
0x1802003ba  push    rbp
0x1802003bb  push    rdi
0x1802003bc  push    r12
0x1802003be  push    r13
0x1802003c0  push    r14
0x1802003c2  lea     rbp, [rsp-1D0h]
0x1802003ca  sub     rsp, 2D0h
0x1802003d1  mov     rax, cs:__security_cookie
0x1802003d8  xor     rax, rsp
0x1802003db  mov     [rbp+1F0h+var_30], rax
0x1802003e2  xor     edx, edx; Val
0x1802003e4  mov     [rsp+2F0h+hKey], 0
0x1802003ed  mov     r14, rcx
0x1802003f0  mov     [rsp+2F0h+var_298], 0
0x1802003f9  lea     rcx, [rsp+2F0h+Name]; void *
0x1802003fe  lea     r8d, [rdx+4Eh]; Size
0x180200402  call    memset_0
0x180200407  mov     [rsp+2F0h+cchName], 27h ; '''
0x18020040f  mov     dword ptr [rsp+2F0h+Data], 0
0x180200417  mov     [rsp+2F0h+cbData], 4
0x18020041f  mov     rcx, cs:WPP_GLOBAL_Control
0x180200426  lea     r13, WPP_GLOBAL_Control
0x18020042d  mov     r12d, 1
0x180200433  cmp     rcx, r13
0x180200436  jz      short loc_180200460
0x180200438  cmp     byte ptr [rcx+69h], 4
0x18020043c  jb      short loc_180200460
0x18020043e  test    [rcx+6Ch], r12b
0x180200442  jz      short loc_180200460
0x180200444  mov     rcx, [rcx+60h]
0x180200448  lea     edx, [r12+5Dh]
0x18020044d  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200454  call    WPP_SF_
0x180200459  mov     rcx, cs:WPP_GLOBAL_Control
0x180200460  test    r14, r14
0x180200463  jnz     short loc_18020046E
0x180200465  lea     ebx, [r14+57h]
0x180200469  jmp     loc_18020071D
0x18020046e  xor     edx, edx; Val
0x180200470  mov     dword ptr [r14], 0
0x180200477  mov     r8d, 208h; Size
0x18020047d  lea     rcx, [rbp+1F0h+SubKey]; void *
0x180200481  call    memset_0
0x180200486  lea     r9, aGrouppolicyPro; "GroupPolicy\\Profiles"
0x18020048d  mov     dword ptr [rsp+2F0h+phkResult], 0
0x180200495  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x18020049c  mov     edx, 104h
0x1802004a1  lea     rcx, [rbp+1F0h+SubKey]
0x1802004a5  call    _StpGetRegistryRoot
0x1802004aa  mov     ebx, eax
0x1802004ac  test    eax, eax
0x1802004ae  jz      short loc_1802004F1
0x1802004b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1802004b7  cmp     rcx, r13
0x1802004ba  jz      loc_180200746
0x1802004c0  cmp     [rcx+69h], r12b
0x1802004c4  jb      loc_18020071D
0x1802004ca  test    [rcx+6Ch], r12b
0x1802004ce  jz      loc_18020071D
0x1802004d4  mov     rcx, [rcx+60h]
0x1802004d8  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1802004df  mov     edx, 5Fh ; '_'
0x1802004e4  mov     r9d, eax
0x1802004e7  call    WPP_SF_d
0x1802004ec  jmp     loc_180200716
0x1802004f1  lea     rax, [rsp+2F0h+hKey]
0x1802004f6  mov     r9d, 9; samDesired
0x1802004fc  xor     r8d, r8d; ulOptions
0x1802004ff  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180200504  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180200508  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18020050f  call    cs:__imp_RegOpenKeyExW
0x180200515  mov     ebx, eax
0x180200517  test    eax, eax
0x180200519  jz      short loc_180200562
0x18020051b  mov     rcx, cs:WPP_GLOBAL_Control
0x180200522  cmp     rcx, r13
0x180200525  jz      short loc_180200552
0x180200527  cmp     [rcx+69h], r12b
0x18020052b  jb      short loc_180200552
0x18020052d  test    [rcx+6Ch], r12b
0x180200531  jz      short loc_180200552
0x180200533  mov     rcx, [rcx+60h]
0x180200537  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18020053e  mov     edx, 60h ; '`'
0x180200543  mov     r9d, eax
0x180200546  call    WPP_SF_d
0x18020054b  mov     rcx, cs:WPP_GLOBAL_Control
0x180200552  cmp     ebx, 2
0x180200555  jnz     loc_18020071D
0x18020055b  xor     ebx, ebx
0x18020055d  jmp     loc_18020071D
0x180200562  xor     edi, edi
0x180200564  xor     esi, esi
0x180200566  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18020056b  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x180200570  mov     [rsp+2F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180200579  lea     r8, [rsp+2F0h+Name]; lpName
0x18020057e  mov     [rsp+2F0h+lpcchClass], 0; lpcchClass
0x180200587  mov     edx, esi; dwIndex
0x180200589  mov     [rsp+2F0h+lpClass], 0; lpClass
0x180200592  mov     [rsp+2F0h+phkResult], 0; lpReserved
0x18020059b  mov     [rsp+2F0h+cchName], 27h ; '''
0x1802005a3  call    cs:__imp_RegEnumKeyExW
0x1802005a9  mov     ebx, eax
0x1802005ab  test    eax, eax
0x1802005ad  jnz     loc_1802006B3
0x1802005b3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1802005b8  lea     rax, [rsp+2F0h+var_298]
0x1802005bd  mov     r9d, r12d; samDesired
0x1802005c0  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1802005c5  xor     r8d, r8d; ulOptions
0x1802005c8  lea     rdx, [rsp+2F0h+Name]; lpSubKey
0x1802005cd  call    cs:__imp_RegOpenKeyExW
0x1802005d3  mov     ebx, eax
0x1802005d5  test    eax, eax
0x1802005d7  jnz     loc_18020067A
0x1802005dd  mov     rcx, [rsp+2F0h+var_298]; hKey
0x1802005e2  lea     rax, [rsp+2F0h+cbData]
0x1802005e7  mov     [rsp+2F0h+lpClass], rax; lpcbData
0x1802005ec  lea     rdx, ValueName; "ProfileIndex"
0x1802005f3  lea     rax, [rsp+2F0h+Data]
0x1802005f8  mov     [rsp+2F0h+cbData], 4
0x180200600  xor     r9d, r9d; lpType
0x180200603  mov     [rsp+2F0h+phkResult], rax; lpData
0x180200608  xor     r8d, r8d; lpReserved
0x18020060b  call    cs:__imp_RegQueryValueExW
0x180200611  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180200616  mov     ebx, eax
0x180200618  test    rcx, rcx
0x18020061b  jz      short loc_180200623
0x18020061d  call    cs:__imp_RegCloseKey
0x180200623  test    ebx, ebx
0x180200625  jz      short loc_180200669
0x180200627  mov     rcx, cs:WPP_GLOBAL_Control
0x18020062e  cmp     rcx, r13
0x180200631  jz      short loc_18020065E
0x180200633  cmp     [rcx+69h], r12b
0x180200637  jb      short loc_18020065E
0x180200639  test    [rcx+6Ch], r12b
0x18020063d  jz      short loc_18020065E
0x18020063f  mov     rcx, [rcx+60h]
0x180200643  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18020064a  mov     edx, 63h ; 'c'
0x18020064f  mov     r9d, ebx
0x180200652  call    WPP_SF_d
0x180200657  mov     rcx, cs:WPP_GLOBAL_Control
0x18020065e  cmp     ebx, 2
0x180200661  jnz     loc_1802006F5
0x180200667  jmp     short loc_180200672
0x180200669  cmp     dword ptr [rsp+2F0h+Data], edi
0x18020066d  cmova   edi, dword ptr [rsp+2F0h+Data]
0x180200672  add     esi, r12d
0x180200675  jmp     loc_180200566
0x18020067a  mov     rcx, cs:WPP_GLOBAL_Control
0x180200681  cmp     rcx, r13
0x180200684  jz      short loc_1802006F5
0x180200686  cmp     [rcx+69h], r12b
0x18020068a  jb      short loc_1802006F5
0x18020068c  test    [rcx+6Ch], r12b
0x180200690  jz      short loc_1802006F5
0x180200692  mov     rcx, [rcx+60h]
0x180200696  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18020069d  mov     edx, 62h ; 'b'
0x1802006a2  mov     r9d, eax
0x1802006a5  call    WPP_SF_d
0x1802006aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1802006b1  jmp     short loc_1802006F5
0x1802006b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1802006ba  cmp     rcx, r13
0x1802006bd  jz      short loc_1802006EA
0x1802006bf  cmp     [rcx+69h], r12b
0x1802006c3  jb      short loc_1802006EA
0x1802006c5  test    [rcx+6Ch], r12b
0x1802006c9  jz      short loc_1802006EA
0x1802006cb  mov     rcx, [rcx+60h]
0x1802006cf  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1802006d6  mov     edx, 61h ; 'a'
0x1802006db  mov     r9d, ebx
0x1802006de  call    WPP_SF_d
0x1802006e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1802006ea  xor     eax, eax
0x1802006ec  cmp     ebx, 103h
0x1802006f2  cmovz   ebx, eax
0x1802006f5  mov     rax, [rsp+2F0h+hKey]
0x1802006fa  test    rax, rax
0x1802006fd  jz      short loc_18020070F
0x1802006ff  mov     rcx, rax; hKey
0x180200702  call    cs:__imp_RegCloseKey
0x180200708  mov     rcx, cs:WPP_GLOBAL_Control
0x18020070f  test    ebx, ebx
0x180200711  jnz     short loc_18020071D
0x180200713  mov     [r14], edi
0x180200716  mov     rcx, cs:WPP_GLOBAL_Control
0x18020071d  cmp     rcx, r13
0x180200720  jz      short loc_180200746
0x180200722  cmp     byte ptr [rcx+69h], 4
0x180200726  jb      short loc_180200746
0x180200728  test    [rcx+6Ch], r12b
0x18020072c  jz      short loc_180200746
0x18020072e  mov     rcx, [rcx+60h]
0x180200732  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200739  mov     edx, 64h ; 'd'
0x18020073e  mov     r9d, ebx
0x180200741  call    WPP_SF_d
0x180200746  mov     eax, ebx
0x180200748  mov     rcx, [rbp+1F0h+var_30]
0x18020074f  xor     rcx, rsp; StackCookie
0x180200752  call    __security_check_cookie
0x180200757  lea     r11, [rsp+2F0h+var_20]
0x18020075f  mov     rbx, [r11+38h]
0x180200763  mov     rsi, [r11+40h]
0x180200767  mov     rsp, r11
0x18020076a  pop     r14
0x18020076c  pop     r13
0x18020076e  pop     r12
0x180200770  pop     rdi
0x180200771  pop     rbp
0x180200772  retn
```
