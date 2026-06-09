# CWorkspaceFtaAppRegistration::Uninstall(void *)

- ea: `0x180052af8`
- end: `0x180052f20`
- name: `?Uninstall@CWorkspaceFtaAppRegistration@@QEAAJPEAX@Z`
- size: `1064`
- prototype: `int(CWorkspaceFtaAppRegistration *__hidden this, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800396d4`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x18001e5d8`
- `0x18001e610`
- `0x180025824`
- `0x180025950`
- `0x18003ce1c`
- `0x1800526f0`
- `0x180052af8`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180052d46`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180052d46`
- `ADVAPI32!RegCloseKey` at `0x180052ed8`
- `ADVAPI32!RegCloseKey` at `0x180052ed8`
- `KERNEL32!RegDeleteTreeW` at `0x180052e60`
- `KERNEL32!RegDeleteTreeW` at `0x180052e60`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CWorkspaceFtaAppRegistration::Uninstall(CWorkspaceFtaAppRegistration *this, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  char *v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v13; // esi
  __int64 v14; // rax
  unsigned int v15; // eax
  const WCHAR *v16; // rax
  LSTATUS v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 v23; // rbx
  const WCHAR *v24; // rax
  HKEY hKey[3]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v27[24]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v32[32]; // [rsp+100h] [rbp-8h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  v4 = std::wstring::wstring(v27, L"Software\\Microsoft\\Workspaces\\Feeds");
  v5 = std::operator+<unsigned short>(v30, v4, L"\\");
  v6 = std::operator+<unsigned short>(v29, v5, (char *)this + 112);
  v7 = std::operator+<unsigned short>(v32, v6, L"\\");
  std::operator+<unsigned short>(v28, v7, L"Resources");
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v29);
  std::wstring::~wstring(v30);
  std::wstring::~wstring(v27);
  v8 = std::operator+<unsigned short>(v29, v28, L"\\");
  v9 = (char *)this + 48;
  v10 = std::operator+<unsigned short>(v30, v8, (char *)this + 48);
  v11 = std::operator+<unsigned short>(v27, v10, L"\\");
  std::operator+<unsigned short>(v31, v11, L"Capabilities");
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v30);
  std::wstring::~wstring(v29);
  if ( a2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    v13 = -2147024809;
    goto LABEL_42;
  }
  hKey[2] = (HKEY)v27;
  v14 = std::wstring::wstring(v27, v31);
  v13 = CWorkspaceFtaAppRegistration::UnRegisterCapabilitiesKey(this, a2, v14);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        v15,
        (__int64)"UnRegisterCapabilitiesKey failed",
        v13);
    }
    goto LABEL_42;
  }
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  v17 = RegOpenKeyTransactedW(HKEY_CURRENT_USER, v16, 0, 0x20006u, hKey, a2, 0);
  if ( v17 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v18);
    }
    v13 = 0;
    goto LABEL_42;
  }
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    if ( v17 > 0 )
      v19 = (unsigned __int16)v17 | 0x80070000;
    else
      v19 = v17;
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 36;
LABEL_38:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v20, v19);
LABEL_39:
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    else
      v13 = v17;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v22);
  }
  v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
  v17 = RegDeleteTreeW(hKey[0], v24);
  if ( (v17 & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    if ( v17 > 0 )
      v19 = (unsigned __int16)v17 | 0x80070000;
    else
      v19 = v17;
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 38;
    goto LABEL_38;
  }
LABEL_42:
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  std::wstring::~wstring(v31);
  std::wstring::~wstring(v28);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180052af8  mov     rax, rsp
0x180052afb  push    rbp
0x180052afc  push    rsi
0x180052afd  push    rdi
0x180052afe  push    r14
0x180052b00  push    r15
0x180052b02  lea     rbp, [rax-48h]
0x180052b06  sub     rsp, 120h
0x180052b0d  mov     [rsp+140h+var_F8], 0FFFFFFFFFFFFFFFEh
0x180052b16  mov     [rax+18h], rbx
0x180052b1a  mov     rax, cs:__security_cookie
0x180052b21  xor     rax, rsp
0x180052b24  mov     [rbp+40h+var_28], rax
0x180052b28  mov     rbx, rdx
0x180052b2b  mov     rdi, rcx
0x180052b2e  mov     [rsp+140h+hKey], 0
0x180052b37  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x180052b3e  lea     rcx, [rsp+140h+var_E8]
0x180052b43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180052b48  nop
0x180052b49  lea     rsi, SubStr; "\\"
0x180052b50  mov     r8, rsi
0x180052b53  mov     rdx, rax
0x180052b56  lea     rcx, [rbp+40h+var_88]
0x180052b5a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052b5f  nop
0x180052b60  lea     r8, [rdi+70h]
0x180052b64  mov     rdx, rax
0x180052b67  lea     rcx, [rbp+40h+var_A8]
0x180052b6b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180052b70  nop
0x180052b71  mov     r8, rsi
0x180052b74  mov     rdx, rax
0x180052b77  lea     rcx, [rbp+40h+var_48]
0x180052b7b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052b80  nop
0x180052b81  lea     r8, aResources; "Resources"
0x180052b88  mov     rdx, rax
0x180052b8b  lea     rcx, [rsp+140h+var_C8]
0x180052b90  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052b95  nop
0x180052b96  lea     rcx, [rbp+40h+var_48]; void *
0x180052b9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052b9f  nop
0x180052ba0  lea     rcx, [rbp+40h+var_A8]; void *
0x180052ba4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052ba9  nop
0x180052baa  lea     rcx, [rbp+40h+var_88]; void *
0x180052bae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052bb3  nop
0x180052bb4  lea     rcx, [rsp+140h+var_E8]; void *
0x180052bb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052bbe  mov     r8, rsi
0x180052bc1  lea     rdx, [rsp+140h+var_C8]
0x180052bc6  lea     rcx, [rbp+40h+var_A8]
0x180052bca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180052bcf  nop
0x180052bd0  lea     r15, [rdi+30h]
0x180052bd4  mov     r8, r15
0x180052bd7  mov     rdx, rax
0x180052bda  lea     rcx, [rbp+40h+var_88]
0x180052bde  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180052be3  nop
0x180052be4  mov     r8, rsi
0x180052be7  mov     rdx, rax
0x180052bea  lea     rcx, [rsp+140h+var_E8]
0x180052bef  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052bf4  nop
0x180052bf5  lea     r8, aCapabilities; "Capabilities"
0x180052bfc  mov     rdx, rax
0x180052bff  lea     rcx, [rbp+40h+var_68]
0x180052c03  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180052c08  nop
0x180052c09  lea     rcx, [rsp+140h+var_E8]; void *
0x180052c0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052c13  nop
0x180052c14  lea     rcx, [rbp+40h+var_88]; void *
0x180052c18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052c1d  nop
0x180052c1e  lea     rcx, [rbp+40h+var_A8]; void *
0x180052c22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052c27  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180052c2b  jnz     short loc_180052C80
0x180052c2d  lea     r14, WPP_GLOBAL_Control
0x180052c34  mov     rax, cs:WPP_GLOBAL_Control
0x180052c3b  cmp     rax, r14
0x180052c3e  jz      short loc_180052C76
0x180052c40  test    byte ptr [rax+1Ch], 8
0x180052c44  jz      short loc_180052C76
0x180052c46  cmp     byte ptr [rax+19h], 2
0x180052c4a  jb      short loc_180052C76
0x180052c4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052c51  lea     edx, [rbx+22h]
0x180052c54  mov     dword ptr [rsp+140h+phkResult], 80070057h
0x180052c5c  mov     r9d, eax
0x180052c5f  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c6d  mov     rcx, [rcx+10h]
0x180052c71  call    WPP_SF_Dd
0x180052c76  mov     esi, 80070057h
0x180052c7b  jmp     loc_180052ECE
0x180052c80  lea     rax, [rsp+140h+var_E8]
0x180052c85  mov     qword ptr [rsp+140h+var_F0], rax
0x180052c8a  lea     rdx, [rbp+40h+var_68]
0x180052c8e  lea     rcx, [rsp+140h+var_E8]
0x180052c93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180052c98  nop
0x180052c99  mov     r8, rax
0x180052c9c  mov     rdx, rbx
0x180052c9f  mov     rcx, rdi
0x180052ca2  call    ?UnRegisterCapabilitiesKey@CWorkspaceFtaAppRegistration@@IEAAJPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWorkspaceFtaAppRegistration::UnRegisterCapabilitiesKey(void *,std::wstring)
0x180052ca7  mov     esi, eax
0x180052ca9  test    eax, eax
0x180052cab  jns     short loc_180052D11
0x180052cad  lea     r14, WPP_GLOBAL_Control
0x180052cb4  mov     rax, cs:WPP_GLOBAL_Control
0x180052cbb  cmp     rax, r14
0x180052cbe  jz      loc_180052ECE
0x180052cc4  test    byte ptr [rax+1Ch], 8
0x180052cc8  jz      loc_180052ECE
0x180052cce  cmp     byte ptr [rax+19h], 2
0x180052cd2  jb      loc_180052ECE
0x180052cd8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052cdd  mov     edx, 22h ; '"'
0x180052ce2  mov     dword ptr [rsp+140h+hTransaction], esi
0x180052ce6  lea     rcx, aUnregistercapa; "UnRegisterCapabilitiesKey failed"
0x180052ced  mov     [rsp+140h+phkResult], rcx
0x180052cf2  mov     r9d, eax
0x180052cf5  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d03  mov     rcx, [rcx+10h]
0x180052d07  call    WPP_SF_DsD
0x180052d0c  jmp     loc_180052ECE
0x180052d11  lea     rcx, [rsp+140h+var_C8]
0x180052d16  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052d1b  mov     rdx, rax; lpSubKey
0x180052d1e  mov     qword ptr [rsp+30h], 0; pExtendedParemeter
0x180052d27  mov     [rsp+140h+hTransaction], rbx; hTransaction
0x180052d2c  lea     rax, [rsp+140h+hKey]
0x180052d31  mov     [rsp+140h+phkResult], rax; phkResult
0x180052d36  mov     r9d, 20006h; samDesired
0x180052d3c  xor     r8d, r8d; ulOptions
0x180052d3f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180052d46  call    cs:__imp_RegOpenKeyTransactedW
0x180052d4c  mov     ebx, eax
0x180052d4e  cmp     eax, 2
0x180052d51  jnz     short loc_180052D9B
0x180052d53  lea     r14, WPP_GLOBAL_Control
0x180052d5a  mov     rax, cs:WPP_GLOBAL_Control
0x180052d61  cmp     rax, r14
0x180052d64  jz      short loc_180052D94
0x180052d66  test    byte ptr [rax+1Ch], 1
0x180052d6a  jz      short loc_180052D94
0x180052d6c  cmp     byte ptr [rax+19h], 4
0x180052d70  jb      short loc_180052D94
0x180052d72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052d77  lea     edx, [rbx+21h]
0x180052d7a  mov     r9d, eax
0x180052d7d  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d8b  mov     rcx, [rcx+10h]
0x180052d8f  call    WPP_SF_D
0x180052d94  xor     esi, esi
0x180052d96  jmp     loc_180052ECE
0x180052d9b  test    ebx, ebx
0x180052d9d  jz      short loc_180052DEB
0x180052d9f  lea     r14, WPP_GLOBAL_Control
0x180052da6  mov     edi, 80070000h
0x180052dab  mov     rax, cs:WPP_GLOBAL_Control
0x180052db2  cmp     rax, r14
0x180052db5  jz      loc_180052EC1
0x180052dbb  test    byte ptr [rax+1Ch], 8
0x180052dbf  jz      loc_180052EC1
0x180052dc5  cmp     byte ptr [rax+19h], 2
0x180052dc9  jb      loc_180052EC1
0x180052dcf  test    ebx, ebx
0x180052dd1  jg      short loc_180052DD7
0x180052dd3  mov     esi, ebx
0x180052dd5  jmp     short loc_180052DDC
0x180052dd7  movzx   esi, bx
0x180052dda  or      esi, edi
0x180052ddc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052de1  mov     edx, 24h ; '$'
0x180052de6  jmp     loc_180052EA3
0x180052deb  lea     r14, WPP_GLOBAL_Control
0x180052df2  mov     rax, cs:WPP_GLOBAL_Control
0x180052df9  cmp     rax, r14
0x180052dfc  jz      short loc_180052E50
0x180052dfe  test    byte ptr [rax+1Ch], 1
0x180052e02  jz      short loc_180052E50
0x180052e04  cmp     byte ptr [rax+19h], 4
0x180052e08  jb      short loc_180052E50
0x180052e0a  mov     rcx, r15
0x180052e0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052e12  mov     rdi, rax
0x180052e15  lea     rcx, [rsp+140h+var_C8]
0x180052e1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052e1f  mov     rbx, rax
0x180052e22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052e27  mov     edx, 25h ; '%'
0x180052e2c  mov     [rsp+140h+hTransaction], rdi; __int64
0x180052e31  mov     [rsp+140h+phkResult], rbx; __int64
0x180052e36  mov     r9d, eax
0x180052e39  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e47  mov     rcx, [rcx+10h]; LoggerHandle
0x180052e4b  call    WPP_SF_DSS
0x180052e50  mov     rcx, r15
0x180052e53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052e58  mov     rdx, rax; lpSubKey
0x180052e5b  mov     rcx, [rsp+140h+hKey]; hKey
0x180052e60  call    cs:__imp_RegDeleteTreeW
0x180052e66  mov     ebx, eax
0x180052e68  test    eax, 0FFFFFFFDh
0x180052e6d  jz      short loc_180052ECE
0x180052e6f  mov     edi, 80070000h
0x180052e74  mov     rax, cs:WPP_GLOBAL_Control
0x180052e7b  cmp     rax, r14
0x180052e7e  jz      short loc_180052EC1
0x180052e80  test    byte ptr [rax+1Ch], 8
0x180052e84  jz      short loc_180052EC1
0x180052e86  cmp     byte ptr [rax+19h], 2
0x180052e8a  jb      short loc_180052EC1
0x180052e8c  test    ebx, ebx
0x180052e8e  jg      short loc_180052E94
0x180052e90  mov     esi, ebx
0x180052e92  jmp     short loc_180052E99
0x180052e94  movzx   esi, bx
0x180052e97  or      esi, edi
0x180052e99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052e9e  mov     edx, 26h ; '&'
0x180052ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180052eaa  mov     dword ptr [rsp+140h+phkResult], esi
0x180052eae  mov     r9d, eax
0x180052eb1  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052eb8  mov     rcx, [rcx+10h]
0x180052ebc  call    WPP_SF_Dd
0x180052ec1  test    ebx, ebx
0x180052ec3  jg      short loc_180052EC9
0x180052ec5  mov     esi, ebx
0x180052ec7  jmp     short loc_180052ECE
0x180052ec9  movzx   esi, bx
0x180052ecc  or      esi, edi
0x180052ece  mov     rcx, [rsp+140h+hKey]; hKey
0x180052ed3  test    rcx, rcx
0x180052ed6  jz      short loc_180052EE7
0x180052ed8  call    cs:__imp_RegCloseKey
0x180052ede  mov     [rsp+140h+hKey], 0
0x180052ee7  lea     rcx, [rbp+40h+var_68]; void *
0x180052eeb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052ef0  nop
0x180052ef1  lea     rcx, [rsp+140h+var_C8]; void *
0x180052ef6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052efb  mov     eax, esi
0x180052efd  mov     rcx, [rbp+40h+var_28]
0x180052f01  xor     rcx, rsp; StackCookie
0x180052f04  call    __security_check_cookie
0x180052f09  mov     rbx, [rsp+140h+arg_10]
0x180052f11  add     rsp, 120h
0x180052f18  pop     r15
0x180052f1a  pop     r14
0x180052f1c  pop     rdi
0x180052f1d  pop     rsi
0x180052f1e  pop     rbp
0x180052f1f  retn
```
