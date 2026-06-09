# UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180009298`
- end: `0x180009585`
- name: `?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009e2c`
- `0x18004e0c4`
- `0x1800914d8`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180008174`
- `0x180009298`
- `0x18001c6d8`
- `0x18002c220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009348`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009555`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009348`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009555`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009564`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009333`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000936a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009333`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000936a`

## string_xrefs

- `0x180009529`: `SystemProductName`

## pseudocode

```c
__int64 __fastcall UtilGetManufacturerInformation(__int64 a1, __int64 a2, __int64 a3)
{
  LSTATUS v7; // eax
  HKEY v8; // rcx
  signed int v9; // esi
  LSTATUS v10; // eax
  signed int v11; // edi
  unsigned int v12; // r14d
  HKEY v13; // rcx
  const WCHAR *v14; // r8
  wchar_t *v15; // rcx
  HKEY v16; // rcx
  const WCHAR *v17; // r8
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY hkey; // [rsp+98h] [rbp+58h] BYREF

  hKey = 0;
  hkey = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    return 2147942487LL;
  }
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Platform\\DeviceTargetingInfo", 0, 1u, &hkey);
  v8 = hKey;
  v9 = v7;
  hKey = 0;
  if ( v8 )
    RegCloseKey(v8);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation", 0, 1u, &hKey);
  v11 = v10;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
    v13 = hkey;
    v14 = L"PhoneManufacturer";
LABEL_25:
    UtilRegGetString(v13, 0, v14, a1, 0, 0);
    if ( a3 )
    {
      if ( v11 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_32;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
      }
      else
      {
        UtilRegGetString(hKey, 0, L"BIOSVersion", a3, 0, 0);
      }
    }
    v15 = WPP_GLOBAL_Control;
LABEL_32:
    if ( a2 )
    {
      if ( v9 )
      {
        if ( v15 != (wchar_t *)&WPP_GLOBAL_Control && (v15[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)v15 + 2), 29, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
        v16 = hKey;
        v17 = L"SystemProductName";
      }
      else
      {
        if ( v15 != (wchar_t *)&WPP_GLOBAL_Control && (v15[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)v15 + 2), 28, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
        v16 = hkey;
        v17 = L"PhoneManufacturerModelName";
      }
      UtilRegGetString(v16, 0, v17, a2, 0, 0);
    }
    v12 = 0;
    goto LABEL_44;
  }
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
    v13 = hKey;
    v14 = L"SystemManufacturer";
    goto LABEL_25;
  }
  v12 = ERROR_HR_FROM_WIN32(v10);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
      (unsigned int)v9,
      v11);
  }
LABEL_44:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x180009298  mov     [rsp-38h+arg_8], rbx
0x18000929d  push    rbp
0x18000929e  push    rsi
0x18000929f  push    rdi
0x1800092a0  push    r12
0x1800092a2  push    r13
0x1800092a4  push    r14
0x1800092a6  push    r15
0x1800092a8  mov     rbp, rsp
0x1800092ab  sub     rsp, 40h
0x1800092af  xor     ebx, ebx
0x1800092b1  mov     r13, r8
0x1800092b4  mov     [rbp+hKey], rbx
0x1800092b8  mov     r12, rdx
0x1800092bb  mov     [rbp+hkey], rbx
0x1800092bf  mov     r15, rcx
0x1800092c2  test    rcx, rcx
0x1800092c5  jnz     short loc_180009310
0x1800092c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092ce  lea     rbx, WPP_GLOBAL_Control
0x1800092d5  cmp     rcx, rbx
0x1800092d8  jz      short loc_1800092F4
0x1800092da  test    byte ptr [rcx+1Ch], 1
0x1800092de  jz      short loc_1800092F4
0x1800092e0  mov     rcx, [rcx+10h]
0x1800092e4  lea     edx, [r15+17h]
0x1800092e8  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800092ef  call    WPP_SF_
0x1800092f4  lea     rcx, [rbp+hkey]
0x1800092f8  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800092fd  lea     rcx, [rbp+hKey]
0x180009301  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180009306  mov     eax, 80070057h
0x18000930b  jmp     loc_18000956D
0x180009310  lea     rax, [rbp+hkey]
0x180009314  mov     rdi, 0FFFFFFFF80000002h
0x18000931b  mov     rcx, rdi; hKey
0x18000931e  mov     [rsp+40h+phkResult], rax; phkResult
0x180009323  mov     r9d, 1; samDesired
0x180009329  lea     rdx, aSystemPlatform; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x180009330  xor     r8d, r8d; ulOptions
0x180009333  call    cs:__imp_RegOpenKeyExW
0x180009339  mov     rcx, [rbp+hKey]; hKey
0x18000933d  mov     esi, eax
0x18000933f  mov     [rbp+hKey], rbx
0x180009343  test    rcx, rcx
0x180009346  jz      short loc_18000934E
0x180009348  call    cs:__imp_RegCloseKey
0x18000934e  lea     rax, [rbp+hKey]
0x180009352  mov     r9d, 1; samDesired
0x180009358  xor     r8d, r8d; ulOptions
0x18000935b  mov     [rsp+40h+phkResult], rax; phkResult
0x180009360  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x180009367  mov     rcx, rdi; hKey
0x18000936a  call    cs:__imp_RegOpenKeyExW
0x180009370  mov     edi, eax
0x180009372  test    esi, esi
0x180009374  jz      loc_18000941F
0x18000937a  test    eax, eax
0x18000937c  jz      short loc_1800093E1
0x18000937e  mov     ecx, eax; unsigned int
0x180009380  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180009385  mov     r14d, eax
0x180009388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000938f  lea     rbx, WPP_GLOBAL_Control
0x180009396  cmp     rcx, rbx
0x180009399  jz      loc_18000954C
0x18000939f  test    byte ptr [rcx+1Ch], 1
0x1800093a3  jz      loc_18000954C
0x1800093a9  mov     eax, 80070000h
0x1800093ae  test    edi, edi
0x1800093b0  jle     short loc_1800093B7
0x1800093b2  movzx   edi, di
0x1800093b5  or      edi, eax
0x1800093b7  test    esi, esi
0x1800093b9  jle     short loc_1800093C0
0x1800093bb  movzx   esi, si
0x1800093be  or      esi, eax
0x1800093c0  mov     rcx, [rcx+10h]
0x1800093c4  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800093cb  mov     edx, 18h
0x1800093d0  mov     dword ptr [rsp+40h+phkResult], edi
0x1800093d4  mov     r9d, esi
0x1800093d7  call    WPP_SF_Dd
0x1800093dc  jmp     loc_18000954C
0x1800093e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093e8  lea     rbx, WPP_GLOBAL_Control
0x1800093ef  mov     r14b, 4
0x1800093f2  cmp     rcx, rbx
0x1800093f5  jz      short loc_180009412
0x1800093f7  test    [rcx+1Ch], r14b
0x1800093fb  jz      short loc_180009412
0x1800093fd  mov     rcx, [rcx+10h]
0x180009401  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x180009408  mov     edx, 1Ah
0x18000940d  call    WPP_SF_
0x180009412  mov     rcx, [rbp+hKey]
0x180009416  lea     r8, aSystemmanufact; "SystemManufacturer"
0x18000941d  jmp     short loc_18000945B
0x18000941f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009426  lea     rbx, WPP_GLOBAL_Control
0x18000942d  mov     r14b, 4
0x180009430  cmp     rcx, rbx
0x180009433  jz      short loc_180009450
0x180009435  test    [rcx+1Ch], r14b
0x180009439  jz      short loc_180009450
0x18000943b  mov     rcx, [rcx+10h]
0x18000943f  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x180009446  mov     edx, 19h
0x18000944b  call    WPP_SF_
0x180009450  mov     rcx, [rbp+hkey]; hkey
0x180009454  lea     r8, aPhonemanufactu; "PhoneManufacturer"
0x18000945b  mov     [rsp+40h+var_10], 0; char
0x180009460  xor     r9d, r9d
0x180009463  mov     [rsp+40h+var_18], 0; char
0x180009468  xor     edx, edx; lpSubKey
0x18000946a  mov     [rsp+40h+phkResult], r15; __int64
0x18000946f  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180009474  test    r13, r13
0x180009477  jz      short loc_1800094CA
0x180009479  test    edi, edi
0x18000947b  jnz     short loc_1800094A3
0x18000947d  mov     rcx, [rbp+hKey]; hkey
0x180009481  lea     r8, aBiosversion; "BIOSVersion"
0x180009488  mov     [rsp+40h+var_10], dil; char
0x18000948d  xor     r9d, r9d
0x180009490  mov     [rsp+40h+var_18], dil; char
0x180009495  xor     edx, edx; lpSubKey
0x180009497  mov     [rsp+40h+phkResult], r13; __int64
0x18000949c  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800094a1  jmp     short loc_1800094CA
0x1800094a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094aa  cmp     rcx, rbx
0x1800094ad  jz      short loc_1800094D1
0x1800094af  test    [rcx+1Ch], r14b
0x1800094b3  jz      short loc_1800094D1
0x1800094b5  mov     rcx, [rcx+10h]
0x1800094b9  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800094c0  mov     edx, 1Bh
0x1800094c5  call    WPP_SF_
0x1800094ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094d1  test    r12, r12
0x1800094d4  jz      short loc_180009549
0x1800094d6  test    esi, esi
0x1800094d8  jnz     short loc_180009505
0x1800094da  cmp     rcx, rbx
0x1800094dd  jz      short loc_1800094F8
0x1800094df  test    [rcx+1Ch], r14b
0x1800094e3  jz      short loc_1800094F8
0x1800094e5  mov     rcx, [rcx+10h]
0x1800094e9  lea     edx, [rsi+1Ch]
0x1800094ec  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800094f3  call    WPP_SF_
0x1800094f8  mov     rcx, [rbp+hkey]
0x1800094fc  lea     r8, aPhonemanufactu_0; "PhoneManufacturerModelName"
0x180009503  jmp     short loc_180009530
0x180009505  cmp     rcx, rbx
0x180009508  jz      short loc_180009525
0x18000950a  test    [rcx+1Ch], r14b
0x18000950e  jz      short loc_180009525
0x180009510  mov     rcx, [rcx+10h]
0x180009514  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000951b  mov     edx, 1Dh
0x180009520  call    WPP_SF_
0x180009525  mov     rcx, [rbp+hKey]; hkey
0x180009529  lea     r8, aSystemproductn; "SystemProductName"
0x180009530  mov     [rsp+40h+var_10], 0; char
0x180009535  xor     r9d, r9d
0x180009538  mov     [rsp+40h+var_18], 0; char
0x18000953d  xor     edx, edx; lpSubKey
0x18000953f  mov     [rsp+40h+phkResult], r12; __int64
0x180009544  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180009549  xor     r14d, r14d
0x18000954c  mov     rcx, [rbp+hkey]; hKey
0x180009550  test    rcx, rcx
0x180009553  jz      short loc_18000955B
0x180009555  call    cs:__imp_RegCloseKey
0x18000955b  mov     rcx, [rbp+hKey]; hKey
0x18000955f  test    rcx, rcx
0x180009562  jz      short loc_18000956A
0x180009564  call    cs:__imp_RegCloseKey
0x18000956a  mov     eax, r14d
0x18000956d  mov     rbx, [rsp+40h+arg_8]
0x180009575  add     rsp, 40h
0x180009579  pop     r15
0x18000957b  pop     r14
0x18000957d  pop     r13
0x18000957f  pop     r12
0x180009581  pop     rdi
0x180009582  pop     rsi
0x180009583  pop     rbp
0x180009584  retn
```
