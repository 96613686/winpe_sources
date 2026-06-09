# CControlPanelPage::Notify(ushort const *)

- ea: `0x180067c20`
- end: `0x180067de9`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800242c0`

## callees

- `0x180006f2c`
- `0x180067c20`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180067d3f`
- `SHELL32!SHParseDisplayName` at `0x180067d3f`
- `SHELL32!__imp_ILFree` at `0x180067da7`
- `SHELL32!__imp_ILFree` at `0x180067da7`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180067cf5`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180067cf5`
- `SHLWAPI!__imp_StrCmpCW` at `0x180067c66`
- `SHLWAPI!__imp_StrCmpCW` at `0x180067c66`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180067ccb`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180067ccb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067ca5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067d67`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067ca5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067d67`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180067c7b`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180067c7b`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::Notify(CControlPanelPage *this, const unsigned __int16 *a2)
{
  HRESULT Str; // ebx
  IUnknown *v4; // rcx
  IUnknown *v5; // rcx
  void *v7; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[48]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR value[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_QWORD *)this - 1) )
  {
    Str = 0;
    if ( !StrCmpCW(a2, L"SearchText") && !(unsigned int)SHWindowsPolicy(POLID_NoControlPanel) )
    {
      v4 = (IUnknown *)*((_QWORD *)this - 1);
      ppvOut = 0;
      Str = IUnknown_QueryService(v4, &IID_IFrameManager, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppvOut);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr((IPropertyBag *)ppvOut, L"SearchText", value, 260);
        if ( Str >= 0 )
        {
          if ( value[0] )
          {
            Str = SHStringFromGUIDW(&CLSID_ControlPanelCategory, v10, 39);
            if ( Str >= 0 )
            {
              Str = StringCchPrintfW(pszName, 0x29u, L"::%s", v10);
              if ( Str >= 0 )
              {
                ppidl = 0;
                Str = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
                if ( Str >= 0 )
                {
                  v5 = (IUnknown *)*((_QWORD *)this - 1);
                  v7 = 0;
                  Str = IUnknown_QueryService(
                          v5,
                          (const GUID *const)&SID_STopLevelBrowser,
                          &GUID_000214e2_0000_0000_c000_000000000046,
                          &v7);
                  if ( Str >= 0 )
                  {
                    Str = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64))(*(_QWORD *)v7 + 88LL))(
                            v7,
                            ppidl,
                            1572865);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
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
0x180067c20  mov     [rsp-8+arg_10], rbx
0x180067c25  push    rbp
0x180067c26  push    rsi
0x180067c27  push    rdi
0x180067c28  lea     rbp, [rsp-220h]
0x180067c30  sub     rsp, 320h
0x180067c37  mov     rax, cs:__security_cookie
0x180067c3e  xor     rax, rsp
0x180067c41  mov     [rbp+230h+var_20], rax
0x180067c48  xor     esi, esi
0x180067c4a  mov     rax, rdx
0x180067c4d  mov     rdi, rcx
0x180067c50  cmp     [rcx-8], rsi
0x180067c54  jz      loc_180067DC0
0x180067c5a  lea     rdx, aSearchtext; "SearchText"
0x180067c61  mov     rcx, rax; pszStr1
0x180067c64  mov     ebx, esi
0x180067c66  call    cs:__imp_StrCmpCW
0x180067c6c  test    eax, eax
0x180067c6e  jnz     loc_180067DC5
0x180067c74  lea     rcx, POLID_NoControlPanel
0x180067c7b  call    cs:__imp_SHWindowsPolicy
0x180067c81  test    eax, eax
0x180067c83  jnz     loc_180067DC5
0x180067c89  mov     rcx, [rdi-8]; punk
0x180067c8d  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x180067c92  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180067c99  mov     [rsp+330h+ppvOut], rsi
0x180067c9e  lea     rdx, IID_IFrameManager; guidService
0x180067ca5  call    cs:__imp_IUnknown_QueryService
0x180067cab  mov     ebx, eax
0x180067cad  test    eax, eax
0x180067caf  js      loc_180067DC5
0x180067cb5  mov     rcx, [rsp+330h+ppvOut]; propBag
0x180067cba  lea     r8, [rbp+230h+value]; value
0x180067cbe  mov     r9d, 104h; characterCount
0x180067cc4  lea     rdx, aSearchtext; "SearchText"
0x180067ccb  call    cs:__imp_PSPropertyBag_ReadStr
0x180067cd1  mov     ebx, eax
0x180067cd3  test    eax, eax
0x180067cd5  js      loc_180067DAD
0x180067cdb  cmp     [rbp+230h+value], si
0x180067cdf  jz      loc_180067DAD
0x180067ce5  lea     r8d, [rsi+27h]
0x180067ce9  lea     rdx, [rsp+330h+var_2E0]
0x180067cee  lea     rcx, CLSID_ControlPanelCategory
0x180067cf5  call    cs:__imp_SHStringFromGUIDW
0x180067cfb  mov     ebx, eax
0x180067cfd  test    eax, eax
0x180067cff  js      loc_180067DAD
0x180067d05  lea     r9, [rsp+330h+var_2E0]
0x180067d0a  lea     r8, aS; "::%s"
0x180067d11  lea     edx, [rsi+29h]; unsigned __int64
0x180067d14  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x180067d18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067d1d  mov     ebx, eax
0x180067d1f  test    eax, eax
0x180067d21  js      loc_180067DAD
0x180067d27  xor     r9d, r9d; sfgaoIn
0x180067d2a  mov     [rsp+330h+ppidl], rsi
0x180067d2f  lea     r8, [rsp+330h+ppidl]; ppidl
0x180067d34  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x180067d39  xor     edx, edx; pbc
0x180067d3b  lea     rcx, [rbp+230h+pszName]; pszName
0x180067d3f  call    cs:__imp_SHParseDisplayName
0x180067d45  mov     ebx, eax
0x180067d47  test    eax, eax
0x180067d49  js      short loc_180067DAD
0x180067d4b  mov     rcx, [rdi-8]; punk
0x180067d4f  lea     r9, [rsp+330h+var_300]; ppvOut
0x180067d54  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180067d5b  mov     [rsp+330h+var_300], rsi
0x180067d60  lea     rdx, SID_STopLevelBrowser; guidService
0x180067d67  call    cs:__imp_IUnknown_QueryService
0x180067d6d  mov     ebx, eax
0x180067d6f  test    eax, eax
0x180067d71  js      short loc_180067DA2
0x180067d73  mov     rcx, [rsp+330h+var_300]
0x180067d78  mov     r8d, 180001h
0x180067d7e  mov     rdx, [rsp+330h+ppidl]
0x180067d83  mov     rax, [rcx]
0x180067d86  mov     rax, [rax+58h]
0x180067d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d8f  mov     rcx, [rsp+330h+var_300]
0x180067d94  mov     ebx, eax
0x180067d96  mov     rax, [rcx]
0x180067d99  mov     rax, [rax+10h]
0x180067d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067da2  mov     rcx, [rsp+330h+ppidl]; pidl
0x180067da7  call    cs:__imp_ILFree
0x180067dad  mov     rcx, [rsp+330h+ppvOut]
0x180067db2  mov     rax, [rcx]
0x180067db5  mov     rax, [rax+10h]
0x180067db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dbe  jmp     short loc_180067DC5
0x180067dc0  mov     ebx, 80070057h
0x180067dc5  mov     eax, ebx
0x180067dc7  mov     rcx, [rbp+230h+var_20]
0x180067dce  xor     rcx, rsp; StackCookie
0x180067dd1  call    __security_check_cookie
0x180067dd6  mov     rbx, [rsp+330h+arg_10]
0x180067dde  add     rsp, 320h
0x180067de5  pop     rdi
0x180067de6  pop     rsi
0x180067de7  pop     rbp
0x180067de8  retn
```
