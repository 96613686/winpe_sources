# UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18000a3ac`
- end: `0x18000a6b8`
- name: `?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z`
- size: `780`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000aed8`
- `0x180050440`
- `0x1800955c0`

## callees

- `0x180004c64`
- `0x180008e38`
- `0x18000a3ac`
- `0x18001c368`
- `0x18001cb20`
- `0x18002dc4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a462`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a67b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a462`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a67b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a690`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a447`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a48a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a447`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a48a`

## string_xrefs

- `0x18000a64f`: `SystemProductName`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
          WPP_SF_(*((_QWORD *)v15 + 2), 29, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
        v16 = hKey;
        v17 = L"SystemProductName";
      }
      else
      {
        if ( v15 != (wchar_t *)&WPP_GLOBAL_Control && (v15[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)v15 + 2), 28, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
      WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
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
0x18000a3ac  mov     [rsp-38h+arg_8], rbx
0x18000a3b1  push    rbp
0x18000a3b2  push    rsi
0x18000a3b3  push    rdi
0x18000a3b4  push    r12
0x18000a3b6  push    r13
0x18000a3b8  push    r14
0x18000a3ba  push    r15
0x18000a3bc  mov     rbp, rsp
0x18000a3bf  sub     rsp, 40h
0x18000a3c3  xor     ebx, ebx
0x18000a3c5  mov     r13, r8
0x18000a3c8  mov     [rbp+hKey], rbx
0x18000a3cc  mov     r12, rdx
0x18000a3cf  mov     [rbp+hkey], rbx
0x18000a3d3  mov     r15, rcx
0x18000a3d6  test    rcx, rcx
0x18000a3d9  jnz     short loc_18000A424
0x18000a3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3e2  lea     rbx, WPP_GLOBAL_Control
0x18000a3e9  cmp     rcx, rbx
0x18000a3ec  jz      short loc_18000A408
0x18000a3ee  test    byte ptr [rcx+1Ch], 1
0x18000a3f2  jz      short loc_18000A408
0x18000a3f4  mov     rcx, [rcx+10h]
0x18000a3f8  lea     edx, [r15+17h]
0x18000a3fc  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a403  call    WPP_SF_
0x18000a408  lea     rcx, [rbp+hkey]
0x18000a40c  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18000a411  lea     rcx, [rbp+hKey]
0x18000a415  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18000a41a  mov     eax, 80070057h
0x18000a41f  jmp     loc_18000A69F
0x18000a424  lea     rax, [rbp+hkey]
0x18000a428  mov     rdi, 0FFFFFFFF80000002h
0x18000a42f  mov     rcx, rdi; hKey
0x18000a432  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a437  mov     r9d, 1; samDesired
0x18000a43d  lea     rdx, SubKey; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x18000a444  xor     r8d, r8d; ulOptions
0x18000a447  call    cs:__imp_RegOpenKeyExW
0x18000a44e  nop     dword ptr [rax+rax+00h]
0x18000a453  mov     rcx, [rbp+hKey]; hKey
0x18000a457  mov     esi, eax
0x18000a459  mov     [rbp+hKey], rbx
0x18000a45d  test    rcx, rcx
0x18000a460  jz      short loc_18000A46E
0x18000a462  call    cs:__imp_RegCloseKey
0x18000a469  nop     dword ptr [rax+rax+00h]
0x18000a46e  lea     rax, [rbp+hKey]
0x18000a472  mov     r9d, 1; samDesired
0x18000a478  xor     r8d, r8d; ulOptions
0x18000a47b  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a480  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x18000a487  mov     rcx, rdi; hKey
0x18000a48a  call    cs:__imp_RegOpenKeyExW
0x18000a491  nop     dword ptr [rax+rax+00h]
0x18000a496  mov     edi, eax
0x18000a498  test    esi, esi
0x18000a49a  jz      loc_18000A545
0x18000a4a0  test    eax, eax
0x18000a4a2  jz      short loc_18000A507
0x18000a4a4  mov     ecx, eax; unsigned int
0x18000a4a6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000a4ab  mov     r14d, eax
0x18000a4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4b5  lea     rbx, WPP_GLOBAL_Control
0x18000a4bc  cmp     rcx, rbx
0x18000a4bf  jz      loc_18000A672
0x18000a4c5  test    byte ptr [rcx+1Ch], 1
0x18000a4c9  jz      loc_18000A672
0x18000a4cf  mov     eax, 80070000h
0x18000a4d4  test    edi, edi
0x18000a4d6  jle     short loc_18000A4DD
0x18000a4d8  movzx   edi, di
0x18000a4db  or      edi, eax
0x18000a4dd  test    esi, esi
0x18000a4df  jle     short loc_18000A4E6
0x18000a4e1  movzx   esi, si
0x18000a4e4  or      esi, eax
0x18000a4e6  mov     rcx, [rcx+10h]
0x18000a4ea  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a4f1  mov     edx, 18h
0x18000a4f6  mov     dword ptr [rsp+40h+phkResult], edi
0x18000a4fa  mov     r9d, esi
0x18000a4fd  call    WPP_SF_Dd
0x18000a502  jmp     loc_18000A672
0x18000a507  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a50e  lea     rbx, WPP_GLOBAL_Control
0x18000a515  mov     r14b, 4
0x18000a518  cmp     rcx, rbx
0x18000a51b  jz      short loc_18000A538
0x18000a51d  test    [rcx+1Ch], r14b
0x18000a521  jz      short loc_18000A538
0x18000a523  mov     rcx, [rcx+10h]
0x18000a527  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a52e  mov     edx, 1Ah
0x18000a533  call    WPP_SF_
0x18000a538  mov     rcx, [rbp+hKey]
0x18000a53c  lea     r8, aSystemmanufact; "SystemManufacturer"
0x18000a543  jmp     short loc_18000A581
0x18000a545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a54c  lea     rbx, WPP_GLOBAL_Control
0x18000a553  mov     r14b, 4
0x18000a556  cmp     rcx, rbx
0x18000a559  jz      short loc_18000A576
0x18000a55b  test    [rcx+1Ch], r14b
0x18000a55f  jz      short loc_18000A576
0x18000a561  mov     rcx, [rcx+10h]
0x18000a565  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a56c  mov     edx, 19h
0x18000a571  call    WPP_SF_
0x18000a576  mov     rcx, [rbp+hkey]; hkey
0x18000a57a  lea     r8, aPhonemanufactu; "PhoneManufacturer"
0x18000a581  mov     [rsp+40h+var_10], 0; char
0x18000a586  xor     r9d, r9d
0x18000a589  mov     [rsp+40h+var_18], 0; char
0x18000a58e  xor     edx, edx; lpSubKey
0x18000a590  mov     [rsp+40h+phkResult], r15; __int64
0x18000a595  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18000a59a  test    r13, r13
0x18000a59d  jz      short loc_18000A5F0
0x18000a59f  test    edi, edi
0x18000a5a1  jnz     short loc_18000A5C9
0x18000a5a3  mov     rcx, [rbp+hKey]; hkey
0x18000a5a7  lea     r8, aBiosversion; "BIOSVersion"
0x18000a5ae  mov     [rsp+40h+var_10], dil; char
0x18000a5b3  xor     r9d, r9d
0x18000a5b6  mov     [rsp+40h+var_18], dil; char
0x18000a5bb  xor     edx, edx; lpSubKey
0x18000a5bd  mov     [rsp+40h+phkResult], r13; __int64
0x18000a5c2  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18000a5c7  jmp     short loc_18000A5F0
0x18000a5c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5d0  cmp     rcx, rbx
0x18000a5d3  jz      short loc_18000A5F7
0x18000a5d5  test    [rcx+1Ch], r14b
0x18000a5d9  jz      short loc_18000A5F7
0x18000a5db  mov     rcx, [rcx+10h]
0x18000a5df  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a5e6  mov     edx, 1Bh
0x18000a5eb  call    WPP_SF_
0x18000a5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5f7  test    r12, r12
0x18000a5fa  jz      short loc_18000A66F
0x18000a5fc  test    esi, esi
0x18000a5fe  jnz     short loc_18000A62B
0x18000a600  cmp     rcx, rbx
0x18000a603  jz      short loc_18000A61E
0x18000a605  test    [rcx+1Ch], r14b
0x18000a609  jz      short loc_18000A61E
0x18000a60b  mov     rcx, [rcx+10h]
0x18000a60f  lea     edx, [rsi+1Ch]
0x18000a612  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a619  call    WPP_SF_
0x18000a61e  mov     rcx, [rbp+hkey]
0x18000a622  lea     r8, aPhonemanufactu_0; "PhoneManufacturerModelName"
0x18000a629  jmp     short loc_18000A656
0x18000a62b  cmp     rcx, rbx
0x18000a62e  jz      short loc_18000A64B
0x18000a630  test    [rcx+1Ch], r14b
0x18000a634  jz      short loc_18000A64B
0x18000a636  mov     rcx, [rcx+10h]
0x18000a63a  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000a641  mov     edx, 1Dh
0x18000a646  call    WPP_SF_
0x18000a64b  mov     rcx, [rbp+hKey]; hkey
0x18000a64f  lea     r8, aSystemproductn; "SystemProductName"
0x18000a656  mov     [rsp+40h+var_10], 0; char
0x18000a65b  xor     r9d, r9d
0x18000a65e  mov     [rsp+40h+var_18], 0; char
0x18000a663  xor     edx, edx; lpSubKey
0x18000a665  mov     [rsp+40h+phkResult], r12; __int64
0x18000a66a  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18000a66f  xor     r14d, r14d
0x18000a672  mov     rcx, [rbp+hkey]; hKey
0x18000a676  test    rcx, rcx
0x18000a679  jz      short loc_18000A687
0x18000a67b  call    cs:__imp_RegCloseKey
0x18000a682  nop     dword ptr [rax+rax+00h]
0x18000a687  mov     rcx, [rbp+hKey]; hKey
0x18000a68b  test    rcx, rcx
0x18000a68e  jz      short loc_18000A69C
0x18000a690  call    cs:__imp_RegCloseKey
0x18000a697  nop     dword ptr [rax+rax+00h]
0x18000a69c  mov     eax, r14d
0x18000a69f  mov     rbx, [rsp+40h+arg_8]
0x18000a6a7  add     rsp, 40h
0x18000a6ab  pop     r15
0x18000a6ad  pop     r14
0x18000a6af  pop     r13
0x18000a6b1  pop     r12
0x18000a6b3  pop     rdi
0x18000a6b4  pop     rsi
0x18000a6b5  pop     rbp
0x18000a6b6  retn
```
