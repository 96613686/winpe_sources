# CControlPanelPage::Notify(ushort const *)

- ea: `0x1800531c0`
- end: `0x1800533ba`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `506`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002280`
- `0x180008110`
- `0x1800531c0`
- `0x180057010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadStr` at `0x18005327d`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18005327d`
- `SHELL32!SHParseDisplayName` at `0x1800532fd`
- `SHELL32!SHParseDisplayName` at `0x1800532fd`
- `SHELL32!__imp_ILFree` at `0x180053371`
- `SHELL32!__imp_ILFree` at `0x180053371`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800532ad`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800532ad`
- `SHLWAPI!__imp_StrCmpCW` at `0x180053206`
- `SHLWAPI!__imp_StrCmpCW` at `0x180053206`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180053251`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005332b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180053251`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005332b`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180053221`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180053221`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::Notify(CControlPanelPage *this, const unsigned __int16 *a2)
{
  HRESULT Str; // ebx
  const CHAR *v4; // rdx
  IUnknown *v5; // rcx
  IUnknown *v6; // rcx
  void *v8; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[48]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR value[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_QWORD *)this - 1) )
  {
    Str = 0;
    if ( !StrCmpCW(a2, L"SearchText") && !SHWindowsPolicy(POLID_NoControlPanel, v4) )
    {
      v5 = (IUnknown *)*((_QWORD *)this - 1);
      ppvOut = 0;
      Str = IUnknown_QueryService(v5, &IID_IFrameManager, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppvOut);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr((IPropertyBag *)ppvOut, L"SearchText", value, 260);
        if ( Str >= 0 )
        {
          if ( value[0] )
          {
            Str = SHStringFromGUIDW(&CLSID_ControlPanelCategory, v11, 39);
            if ( Str >= 0 )
            {
              Str = StringCchPrintfW(pszName, 0x29u, L"::%s", v11);
              if ( Str >= 0 )
              {
                ppidl = 0;
                Str = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
                if ( Str >= 0 )
                {
                  v6 = (IUnknown *)*((_QWORD *)this - 1);
                  v8 = 0;
                  Str = IUnknown_QueryService(
                          v6,
                          (const GUID *const)&SID_STopLevelBrowser,
                          &GUID_000214e2_0000_0000_c000_000000000046,
                          &v8);
                  if ( Str >= 0 )
                  {
                    Str = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)v8 + 88LL))(
                            v8,
                            ppidl,
                            1572865);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
                  }
                  ILFree(ppidl);
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x1800531c0  mov     [rsp-8+arg_10], rbx
0x1800531c5  push    rbp
0x1800531c6  push    rsi
0x1800531c7  push    rdi
0x1800531c8  lea     rbp, [rsp-220h]
0x1800531d0  sub     rsp, 320h
0x1800531d7  mov     rax, cs:__security_cookie
0x1800531de  xor     rax, rsp
0x1800531e1  mov     [rbp+230h+var_20], rax
0x1800531e8  xor     esi, esi
0x1800531ea  mov     rax, rdx
0x1800531ed  mov     rdi, rcx
0x1800531f0  cmp     [rcx-8], rsi
0x1800531f4  jz      loc_180053390
0x1800531fa  lea     rdx, aSearchtext; "SearchText"
0x180053201  mov     rcx, rax; pszStr1
0x180053204  mov     ebx, esi
0x180053206  call    cs:__imp_StrCmpCW
0x18005320d  nop     dword ptr [rax+rax+00h]
0x180053212  test    eax, eax
0x180053214  jnz     loc_180053395
0x18005321a  lea     rcx, POLID_NoControlPanel; "C"
0x180053221  call    cs:__imp_SHWindowsPolicy
0x180053228  nop     dword ptr [rax+rax+00h]
0x18005322d  test    eax, eax
0x18005322f  jnz     loc_180053395
0x180053235  mov     rcx, [rdi-8]; punk
0x180053239  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x18005323e  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180053245  mov     [rsp+330h+ppvOut], rsi
0x18005324a  lea     rdx, IID_IFrameManager; guidService
0x180053251  call    cs:__imp_IUnknown_QueryService
0x180053258  nop     dword ptr [rax+rax+00h]
0x18005325d  mov     ebx, eax
0x18005325f  test    eax, eax
0x180053261  js      loc_180053395
0x180053267  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18005326c  lea     r8, [rbp+230h+value]; value
0x180053270  mov     r9d, 104h; characterCount
0x180053276  lea     rdx, aSearchtext; "SearchText"
0x18005327d  call    cs:__imp_PSPropertyBag_ReadStr
0x180053284  nop     dword ptr [rax+rax+00h]
0x180053289  mov     ebx, eax
0x18005328b  test    eax, eax
0x18005328d  js      loc_18005337D
0x180053293  cmp     [rbp+230h+value], si
0x180053297  jz      loc_18005337D
0x18005329d  lea     r8d, [rsi+27h]
0x1800532a1  lea     rdx, [rsp+330h+var_2E0]
0x1800532a6  lea     rcx, CLSID_ControlPanelCategory
0x1800532ad  call    cs:__imp_SHStringFromGUIDW
0x1800532b4  nop     dword ptr [rax+rax+00h]
0x1800532b9  mov     ebx, eax
0x1800532bb  test    eax, eax
0x1800532bd  js      loc_18005337D
0x1800532c3  lea     r9, [rsp+330h+var_2E0]
0x1800532c8  lea     r8, aS; "::%s"
0x1800532cf  lea     edx, [rsi+29h]; unsigned __int64
0x1800532d2  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x1800532d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800532db  mov     ebx, eax
0x1800532dd  test    eax, eax
0x1800532df  js      loc_18005337D
0x1800532e5  xor     r9d, r9d; sfgaoIn
0x1800532e8  mov     [rsp+330h+ppidl], rsi
0x1800532ed  lea     r8, [rsp+330h+ppidl]; ppidl
0x1800532f2  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x1800532f7  xor     edx, edx; pbc
0x1800532f9  lea     rcx, [rbp+230h+pszName]; pszName
0x1800532fd  call    cs:__imp_SHParseDisplayName
0x180053304  nop     dword ptr [rax+rax+00h]
0x180053309  mov     ebx, eax
0x18005330b  test    eax, eax
0x18005330d  js      short loc_18005337D
0x18005330f  mov     rcx, [rdi-8]; punk
0x180053313  lea     r9, [rsp+330h+var_300]; ppvOut
0x180053318  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18005331f  mov     [rsp+330h+var_300], rsi
0x180053324  lea     rdx, SID_STopLevelBrowser; guidService
0x18005332b  call    cs:__imp_IUnknown_QueryService
0x180053332  nop     dword ptr [rax+rax+00h]
0x180053337  mov     ebx, eax
0x180053339  test    eax, eax
0x18005333b  js      short loc_18005336C
0x18005333d  mov     rcx, [rsp+330h+var_300]
0x180053342  mov     r8d, 180001h
0x180053348  mov     rdx, [rsp+330h+ppidl]
0x18005334d  mov     rax, [rcx]
0x180053350  mov     rax, [rax+58h]
0x180053354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053359  mov     rcx, [rsp+330h+var_300]
0x18005335e  mov     ebx, eax
0x180053360  mov     rax, [rcx]
0x180053363  mov     rax, [rax+10h]
0x180053367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005336c  mov     rcx, [rsp+330h+ppidl]; pidl
0x180053371  call    cs:__imp_ILFree
0x180053378  nop     dword ptr [rax+rax+00h]
0x18005337d  mov     rcx, [rsp+330h+ppvOut]
0x180053382  mov     rax, [rcx]
0x180053385  mov     rax, [rax+10h]
0x180053389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005338e  jmp     short loc_180053395
0x180053390  mov     ebx, 80070057h
0x180053395  mov     eax, ebx
0x180053397  mov     rcx, [rbp+230h+var_20]
0x18005339e  xor     rcx, rsp; StackCookie
0x1800533a1  call    __security_check_cookie
0x1800533a6  mov     rbx, [rsp+330h+arg_10]
0x1800533ae  add     rsp, 320h
0x1800533b5  pop     rdi
0x1800533b6  pop     rsi
0x1800533b7  pop     rbp
0x1800533b8  retn
```
