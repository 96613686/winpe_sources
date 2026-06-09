# CColorCplPage::_OnChangeTheme(int)

- ea: `0x18000e4b4`
- end: `0x18000e5c7`
- name: `?_OnChangeTheme@CColorCplPage@@AEAAXH@Z`
- size: `275`
- prototype: `void __fastcall(CColorCplPage *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000e010`

## callees

- `0x180002280`
- `0x18000e4b4`
- `0x18000eaf0`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000e4ff`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000e4ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e53a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e53a`

## pseudocode

```c
void __fastcall CColorCplPage::_OnChangeTheme(CColorCplPage *this, int a2)
{
  LPVOID ppv; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v4[528]; // [rsp+40h] [rbp-228h] BYREF

  if ( a2 >= 0 && (unsigned int)a2 < 5 )
  {
    if ( (unsigned int)SHExpandEnvironmentStringsW(*((_QWORD *)&CColorCplPage::cs_rgComboboxThemes + 3 * a2), v4, 260) )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_ThemeManager2, 0, 1u, &GUID_c1e8c83e_845d_4d95_81db_e283fdffc000, &ppv) >= 0 )
      {
        if ( (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0) >= 0
          && (*(int (__fastcall **)(LPVOID, _QWORD, _BYTE *, _QWORD, _DWORD))(*(_QWORD *)ppv + 160LL))(ppv, 0, v4, 0, 0) >= 0 )
        {
          *((_BYTE *)this + 260) = 1;
          CColorCplPage::_Setup(this, 0);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
}

```

## disassembly

```asm
0x18000e4b4  test    edx, edx
0x18000e4b6  js      locret_18000E5C5
0x18000e4bc  push    rbx
0x18000e4bd  sub     rsp, 260h
0x18000e4c4  mov     rax, cs:__security_cookie
0x18000e4cb  xor     rax, rsp
0x18000e4ce  mov     [rsp+268h+var_18], rax
0x18000e4d6  mov     rbx, rcx
0x18000e4d9  cmp     edx, 5
0x18000e4dc  jnb     loc_18000E5AD
0x18000e4e2  movsxd  rax, edx
0x18000e4e5  mov     r8d, 104h
0x18000e4eb  lea     rdx, [rsp+268h+var_228]
0x18000e4f0  lea     rcx, [rax+rax*2]
0x18000e4f4  lea     rax, ?cs_rgComboboxThemes@CColorCplPage@@0QBUCOMBOBOX_THEMES@@B; COMBOBOX_THEMES const near * const CColorCplPage::cs_rgComboboxThemes
0x18000e4fb  mov     rcx, [rax+rcx*8]
0x18000e4ff  call    cs:__imp_SHExpandEnvironmentStringsW
0x18000e506  nop     dword ptr [rax+rax+00h]
0x18000e50b  test    eax, eax
0x18000e50d  jz      loc_18000E5AD
0x18000e513  xor     edx, edx; pUnkOuter
0x18000e515  mov     [rsp+268h+var_238], 0
0x18000e51e  lea     rax, [rsp+268h+var_238]
0x18000e523  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x18000e52a  mov     [rsp+268h+ppv], rax; ppv
0x18000e52f  lea     rcx, CLSID_ThemeManager2; rclsid
0x18000e536  lea     r8d, [rdx+1]; dwClsContext
0x18000e53a  call    cs:__imp_CoCreateInstance
0x18000e541  nop     dword ptr [rax+rax+00h]
0x18000e546  test    eax, eax
0x18000e548  js      short loc_18000E5AD
0x18000e54a  mov     rcx, [rsp+268h+var_238]
0x18000e54f  xor     edx, edx
0x18000e551  mov     rax, [rcx]
0x18000e554  mov     rax, [rax+18h]
0x18000e558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e55d  test    eax, eax
0x18000e55f  js      short loc_18000E59C
0x18000e561  mov     rcx, [rsp+268h+var_238]
0x18000e566  lea     r8, [rsp+268h+var_228]
0x18000e56b  xor     r9d, r9d
0x18000e56e  mov     dword ptr [rsp+268h+ppv], 0
0x18000e576  xor     edx, edx
0x18000e578  mov     rax, [rcx]
0x18000e57b  mov     rax, [rax+0A0h]
0x18000e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e587  test    eax, eax
0x18000e589  js      short loc_18000E59C
0x18000e58b  xor     edx, edx; bool
0x18000e58d  mov     byte ptr [rbx+104h], 1
0x18000e594  mov     rcx, rbx; this
0x18000e597  call    ?_Setup@CColorCplPage@@AEAAJ_N@Z; CColorCplPage::_Setup(bool)
0x18000e59c  mov     rcx, [rsp+268h+var_238]
0x18000e5a1  mov     rax, [rcx]
0x18000e5a4  mov     rax, [rax+10h]
0x18000e5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5ad  mov     rcx, [rsp+268h+var_18]
0x18000e5b5  xor     rcx, rsp; StackCookie
0x18000e5b8  call    __security_check_cookie
0x18000e5bd  add     rsp, 260h
0x18000e5c4  pop     rbx
0x18000e5c5  retn
```
