# CWorkspaceFtaAppRegistration::RegisterFileAssociation(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18005228c`
- end: `0x180052694`
- name: `?RegisterFileAssociation@CWorkspaceFtaAppRegistration@@QEAAJPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `1032`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054b64`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18001e41c`
- `0x18001e610`
- `0x180025824`
- `0x18005228c`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x18005246b`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x18005246b`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180052528`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180052528`
- `ADVAPI32!RegCloseKey` at `0x180052630`
- `ADVAPI32!RegCloseKey` at `0x180052649`
- `ADVAPI32!RegCloseKey` at `0x180052630`
- `ADVAPI32!RegCloseKey` at `0x180052649`
- `ADVAPI32!RegSetValueExW` at `0x1800525b4`
- `ADVAPI32!RegSetValueExW` at `0x1800525b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CWorkspaceFtaAppRegistration::RegisterFileAssociation(__int64 a1, void *a2, HKEY a3, HKEY a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // eax
  LSTATUS v17; // edi
  const WCHAR *v18; // rax
  unsigned int v19; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v21; // rdx
  const BYTE *v22; // rbx
  const WCHAR *v23; // rax
  LSTATUS v24; // esi
  unsigned int v25; // edi
  unsigned int v26; // eax
  HKEY v28; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[4]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v33[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v34[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v35[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v36[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v37[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v38[32]; // [rsp+188h] [rbp+88h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[2] = a3;
  hKey[3] = a4;
  hKey[0] = 0;
  v28 = 0;
  v8 = std::wstring::wstring(v38, L"Software\\Microsoft\\Workspaces\\Feeds");
  v9 = std::operator+<unsigned short>(v37, v8, L"\\");
  v10 = std::operator+<unsigned short>(v36, v9, a1 + 112);
  v11 = std::operator+<unsigned short>(v35, v10, L"\\");
  v12 = std::operator+<unsigned short>(v34, v11, L"Resources");
  v13 = std::operator+<unsigned short>(v33, v12, L"\\");
  v14 = std::operator+<unsigned short>(v32, v13, a1 + 48);
  v15 = std::operator+<unsigned short>(v31, v14, L"\\");
  std::operator+<unsigned short>(v30, v15, L"Capabilities");
  std::wstring::~wstring(v31);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(v34);
  std::wstring::~wstring(v35);
  std::wstring::~wstring(v36);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(v38);
  if ( a2 != (void *)-1LL )
  {
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v17 = RegOpenKeyTransactedW(HKEY_CURRENT_USER, v18, 0, 0x20006u, hKey, a2, 0);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      if ( v17 > 0 )
        v19 = (unsigned __int16)v17 | 0x80070000;
      else
        v19 = v17;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 49;
    }
    else
    {
      v17 = RegCreateKeyTransactedW(hKey[0], L"FileAssociations", 0, 0, 0, 0x20006u, 0, &v28, 0, a2, 0);
      if ( !v17 )
      {
        v17 = 0;
        v22 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
        v24 = RegSetValueExW(v28, v23, 0, 1u, v22, 2 * *((_DWORD *)a4 + 4) + 2);
        if ( !v24 )
          goto LABEL_38;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( v24 > 0 )
            v25 = (unsigned __int16)v24 | 0x80070000;
          else
            v25 = v24;
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v26, v25);
        }
        if ( v24 <= 0 )
        {
          v17 = v24;
          goto LABEL_38;
        }
        v17 = (unsigned __int16)v24;
        goto LABEL_37;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_16:
        if ( v17 <= 0 )
          goto LABEL_38;
        v17 = (unsigned __int16)v17;
LABEL_37:
        v17 |= 0x80070000;
        goto LABEL_38;
      }
      if ( v17 > 0 )
        v19 = (unsigned __int16)v17 | 0x80070000;
      else
        v19 = v17;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 50;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
      CurrentThreadActivityIdPrefix,
      v19);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
      v16,
      -2147024809);
  }
  v17 = -2147024809;
LABEL_38:
  if ( v28 )
  {
    RegCloseKey(v28);
    v28 = 0;
  }
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  std::wstring::~wstring(v30);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18005228c  push    rbp
0x18005228e  push    rbx
0x18005228f  push    rsi
0x180052290  push    rdi
0x180052291  push    r14
0x180052293  push    r15
0x180052295  lea     rbp, [rsp-0B8h]
0x18005229d  sub     rsp, 1B8h
0x1800522a4  mov     [rsp+1E0h+var_170], 0FFFFFFFFFFFFFFFEh
0x1800522ad  mov     rax, cs:__security_cookie
0x1800522b4  xor     rax, rsp
0x1800522b7  mov     [rbp+0E0h+var_38], rax
0x1800522be  mov     r14, r9
0x1800522c1  mov     r15, r8
0x1800522c4  mov     rsi, rdx
0x1800522c7  mov     rbx, rcx
0x1800522ca  mov     [rsp+1E0h+var_168], r8
0x1800522cf  mov     [rbp+0E0h+var_160], r9
0x1800522d3  mov     [rsp+1E0h+hKey], 0
0x1800522dc  mov     [rsp+1E0h+var_180], 0
0x1800522e5  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x1800522ec  lea     rcx, [rbp+0E0h+var_58]
0x1800522f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800522f8  nop
0x1800522f9  lea     rdi, SubStr; "\\"
0x180052300  mov     r8, rdi
0x180052303  mov     rdx, rax
0x180052306  lea     rcx, [rbp+0E0h+var_78]
0x18005230a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18005230f  nop
0x180052310  lea     r8, [rbx+70h]
0x180052314  mov     rdx, rax
0x180052317  lea     rcx, [rbp+0E0h+var_98]
0x18005231b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180052320  nop
0x180052321  mov     r8, rdi
0x180052324  mov     rdx, rax
0x180052327  lea     rcx, [rbp+0E0h+var_B8]
0x18005232b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052330  nop
0x180052331  lea     r8, aResources; "Resources"
0x180052338  mov     rdx, rax
0x18005233b  lea     rcx, [rbp+0E0h+var_D8]
0x18005233f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052344  nop
0x180052345  mov     r8, rdi
0x180052348  mov     rdx, rax
0x18005234b  lea     rcx, [rbp+0E0h+var_F8]
0x18005234f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052354  nop
0x180052355  lea     r8, [rbx+30h]
0x180052359  mov     rdx, rax
0x18005235c  lea     rcx, [rbp+0E0h+var_118]
0x180052360  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180052365  nop
0x180052366  mov     r8, rdi
0x180052369  mov     rdx, rax
0x18005236c  lea     rcx, [rbp+0E0h+var_138]
0x180052370  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052375  nop
0x180052376  lea     r8, aCapabilities; "Capabilities"
0x18005237d  mov     rdx, rax
0x180052380  lea     rcx, [rbp+0E0h+var_158]
0x180052384  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052389  nop
0x18005238a  lea     rcx, [rbp+0E0h+var_138]; void *
0x18005238e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052393  nop
0x180052394  lea     rcx, [rbp+0E0h+var_118]; void *
0x180052398  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005239d  nop
0x18005239e  lea     rcx, [rbp+0E0h+var_F8]; void *
0x1800523a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523a7  nop
0x1800523a8  lea     rcx, [rbp+0E0h+var_D8]; void *
0x1800523ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523b1  nop
0x1800523b2  lea     rcx, [rbp+0E0h+var_B8]; void *
0x1800523b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523bb  nop
0x1800523bc  lea     rcx, [rbp+0E0h+var_98]; void *
0x1800523c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523c5  nop
0x1800523c6  lea     rcx, [rbp+0E0h+var_78]; void *
0x1800523ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523cf  nop
0x1800523d0  lea     rcx, [rbp+0E0h+var_58]; void *
0x1800523d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523dc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800523e0  jnz     short loc_180052435
0x1800523e2  lea     rax, WPP_GLOBAL_Control
0x1800523e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523f0  cmp     rcx, rax
0x1800523f3  jz      short loc_18005242B
0x1800523f5  test    byte ptr [rcx+1Ch], 8
0x1800523f9  jz      short loc_18005242B
0x1800523fb  cmp     byte ptr [rcx+19h], 2
0x1800523ff  jb      short loc_18005242B
0x180052401  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052406  lea     edx, [rsi+31h]
0x180052409  mov     dword ptr [rsp+1E0h+phkResult], 80070057h
0x180052411  mov     r9d, eax
0x180052414  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x18005241b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052422  mov     rcx, [rcx+10h]
0x180052426  call    WPP_SF_Dd
0x18005242b  mov     edi, 80070057h
0x180052430  jmp     loc_180052626
0x180052435  lea     rcx, [rbp+0E0h+var_158]
0x180052439  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005243e  mov     rdx, rax; lpSubKey
0x180052441  mov     [rsp+1E0h+pExtendedParemeter], 0; pExtendedParemeter
0x18005244a  mov     [rsp+1E0h+hTransaction], rsi; hTransaction
0x18005244f  lea     rax, [rsp+1E0h+hKey]
0x180052454  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180052459  mov     ebx, 20006h
0x18005245e  mov     r9d, ebx; samDesired
0x180052461  xor     r8d, r8d; ulOptions
0x180052464  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005246b  call    cs:__imp_RegOpenKeyTransactedW
0x180052471  mov     edi, eax
0x180052473  test    eax, eax
0x180052475  jz      short loc_1800524E0
0x180052477  lea     rax, WPP_GLOBAL_Control
0x18005247e  mov     ebx, 80070000h
0x180052483  mov     rcx, cs:WPP_GLOBAL_Control
0x18005248a  cmp     rcx, rax
0x18005248d  jz      short loc_1800524D0
0x18005248f  test    byte ptr [rcx+1Ch], 8
0x180052493  jz      short loc_1800524D0
0x180052495  cmp     byte ptr [rcx+19h], 2
0x180052499  jb      short loc_1800524D0
0x18005249b  test    edi, edi
0x18005249d  jg      short loc_1800524A3
0x18005249f  mov     esi, edi
0x1800524a1  jmp     short loc_1800524A8
0x1800524a3  movzx   esi, di
0x1800524a6  or      esi, ebx
0x1800524a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800524ad  mov     edx, 31h ; '1'
0x1800524b2  mov     dword ptr [rsp+1E0h+phkResult], esi
0x1800524b6  mov     r9d, eax
0x1800524b9  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x1800524c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800524c7  mov     rcx, [rcx+10h]
0x1800524cb  call    WPP_SF_Dd
0x1800524d0  test    edi, edi
0x1800524d2  jle     loc_180052626
0x1800524d8  movzx   edi, di
0x1800524db  jmp     loc_180052624
0x1800524e0  mov     [rsp+1E0h+var_190], 0; pExtendedParemeter
0x1800524e9  mov     [rsp+1E0h+var_198], rsi; hTransaction
0x1800524ee  mov     [rsp+1E0h+lpdwDisposition], 0; lpdwDisposition
0x1800524f7  lea     rax, [rsp+1E0h+var_180]
0x1800524fc  mov     [rsp+1E0h+var_1A8], rax; phkResult
0x180052501  mov     [rsp+1E0h+pExtendedParemeter], 0; lpSecurityAttributes
0x18005250a  mov     dword ptr [rsp+1E0h+hTransaction], ebx; samDesired
0x18005250e  mov     dword ptr [rsp+1E0h+phkResult], 0; dwOptions
0x180052516  xor     r9d, r9d; lpClass
0x180052519  xor     r8d, r8d; Reserved
0x18005251c  lea     rdx, aFileassociatio; "FileAssociations"
0x180052523  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180052528  call    cs:__imp_RegCreateKeyTransactedW
0x18005252e  mov     edi, eax
0x180052530  test    eax, eax
0x180052532  jz      short loc_18005257C
0x180052534  lea     rax, WPP_GLOBAL_Control
0x18005253b  mov     ebx, 80070000h
0x180052540  mov     rcx, cs:WPP_GLOBAL_Control
0x180052547  cmp     rcx, rax
0x18005254a  jz      short loc_1800524D0
0x18005254c  test    byte ptr [rcx+1Ch], 8
0x180052550  jz      loc_1800524D0
0x180052556  cmp     byte ptr [rcx+19h], 2
0x18005255a  jb      loc_1800524D0
0x180052560  test    edi, edi
0x180052562  jg      short loc_180052568
0x180052564  mov     esi, edi
0x180052566  jmp     short loc_18005256D
0x180052568  movzx   esi, di
0x18005256b  or      esi, ebx
0x18005256d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052572  mov     edx, 32h ; '2'
0x180052577  jmp     loc_1800524B2
0x18005257c  xor     edi, edi
0x18005257e  mov     rcx, r14
0x180052581  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052586  mov     rbx, rax
0x180052589  mov     rcx, r15
0x18005258c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052591  mov     edx, [r14+10h]
0x180052595  lea     edx, ds:2[rdx*2]
0x18005259c  mov     dword ptr [rsp+1E0h+hTransaction], edx; cbData
0x1800525a0  mov     [rsp+1E0h+phkResult], rbx; lpData
0x1800525a5  lea     r9d, [rdi+1]; dwType
0x1800525a9  xor     r8d, r8d; Reserved
0x1800525ac  mov     rdx, rax; lpValueName
0x1800525af  mov     rcx, [rsp+1E0h+var_180]; hKey
0x1800525b4  call    cs:__imp_RegSetValueExW
0x1800525ba  mov     esi, eax
0x1800525bc  test    eax, eax
0x1800525be  jz      short loc_180052626
0x1800525c0  lea     rax, WPP_GLOBAL_Control
0x1800525c7  mov     ebx, 80070000h
0x1800525cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525d3  cmp     rcx, rax
0x1800525d6  jz      short loc_180052619
0x1800525d8  test    byte ptr [rcx+1Ch], 8
0x1800525dc  jz      short loc_180052619
0x1800525de  cmp     byte ptr [rcx+19h], 2
0x1800525e2  jb      short loc_180052619
0x1800525e4  test    esi, esi
0x1800525e6  jg      short loc_1800525EC
0x1800525e8  mov     edi, esi
0x1800525ea  jmp     short loc_1800525F1
0x1800525ec  movzx   edi, si
0x1800525ef  or      edi, ebx
0x1800525f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800525f6  mov     edx, 33h ; '3'
0x1800525fb  mov     dword ptr [rsp+1E0h+phkResult], edi
0x1800525ff  mov     r9d, eax
0x180052602  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052609  mov     rcx, cs:WPP_GLOBAL_Control
0x180052610  mov     rcx, [rcx+10h]
0x180052614  call    WPP_SF_Dd
0x180052619  test    esi, esi
0x18005261b  jg      short loc_180052621
0x18005261d  mov     edi, esi
0x18005261f  jmp     short loc_180052626
0x180052621  movzx   edi, si
0x180052624  or      edi, ebx
0x180052626  mov     rcx, [rsp+1E0h+var_180]; hKey
0x18005262b  test    rcx, rcx
0x18005262e  jz      short loc_18005263F
0x180052630  call    cs:__imp_RegCloseKey
0x180052636  mov     [rsp+1E0h+var_180], 0
0x18005263f  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180052644  test    rcx, rcx
0x180052647  jz      short loc_180052658
0x180052649  call    cs:__imp_RegCloseKey
0x18005264f  mov     [rsp+1E0h+hKey], 0
0x180052658  lea     rcx, [rbp+0E0h+var_158]; void *
0x18005265c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052661  nop
0x180052662  mov     rcx, r15; void *
0x180052665  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005266a  nop
0x18005266b  mov     rcx, r14; void *
0x18005266e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052673  mov     eax, edi
0x180052675  mov     rcx, [rbp+0E0h+var_38]
0x18005267c  xor     rcx, rsp; StackCookie
0x18005267f  call    __security_check_cookie
0x180052684  add     rsp, 1B8h
0x18005268b  pop     r15
0x18005268d  pop     r14
0x18005268f  pop     rdi
0x180052690  pop     rsi
0x180052691  pop     rbx
0x180052692  pop     rbp
0x180052693  retn
```
