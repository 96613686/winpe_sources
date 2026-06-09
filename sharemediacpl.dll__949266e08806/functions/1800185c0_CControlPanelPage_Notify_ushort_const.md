# CControlPanelPage::Notify(ushort const *)

- ea: `0x1800185c0`
- end: `0x180018789`
- name: `?Notify@CControlPanelPage@@UEAAJPEBG@Z`
- size: `457`
- prototype: `int(CControlPanelPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001d60`
- `0x180006ca8`
- `0x1800185c0`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180018695`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180018695`
- `SHLWAPI!__imp_StrCmpCW` at `0x180018606`
- `SHLWAPI!__imp_StrCmpCW` at `0x180018606`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018645`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018707`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018645`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018707`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001861b`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001861b`
- `SHELL32!SHParseDisplayName` at `0x1800186df`
- `SHELL32!SHParseDisplayName` at `0x1800186df`
- `SHELL32!__imp_ILFree` at `0x180018747`
- `SHELL32!__imp_ILFree` at `0x180018747`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001866b`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x18001866b`

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
0x1800185c0  mov     [rsp-8+arg_10], rbx
0x1800185c5  push    rbp
0x1800185c6  push    rsi
0x1800185c7  push    rdi
0x1800185c8  lea     rbp, [rsp-220h]
0x1800185d0  sub     rsp, 320h
0x1800185d7  mov     rax, cs:__security_cookie
0x1800185de  xor     rax, rsp
0x1800185e1  mov     [rbp+230h+var_20], rax
0x1800185e8  xor     esi, esi
0x1800185ea  mov     rax, rdx
0x1800185ed  mov     rdi, rcx
0x1800185f0  cmp     [rcx-8], rsi
0x1800185f4  jz      loc_180018760
0x1800185fa  lea     rdx, propName; "SearchText"
0x180018601  mov     rcx, rax; pszStr1
0x180018604  mov     ebx, esi
0x180018606  call    cs:__imp_StrCmpCW
0x18001860c  test    eax, eax
0x18001860e  jnz     loc_180018765
0x180018614  lea     rcx, POLID_NoControlPanel; "C"
0x18001861b  call    cs:__imp_SHWindowsPolicy
0x180018621  test    eax, eax
0x180018623  jnz     loc_180018765
0x180018629  mov     rcx, [rdi-8]; punk
0x18001862d  lea     r9, [rsp+330h+ppvOut]; ppvOut
0x180018632  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180018639  mov     [rsp+330h+ppvOut], rsi
0x18001863e  lea     rdx, IID_IFrameManager; guidService
0x180018645  call    cs:__imp_IUnknown_QueryService
0x18001864b  mov     ebx, eax
0x18001864d  test    eax, eax
0x18001864f  js      loc_180018765
0x180018655  mov     rcx, [rsp+330h+ppvOut]; propBag
0x18001865a  lea     r8, [rbp+230h+value]; value
0x18001865e  mov     r9d, 104h; characterCount
0x180018664  lea     rdx, propName; "SearchText"
0x18001866b  call    cs:__imp_PSPropertyBag_ReadStr
0x180018671  mov     ebx, eax
0x180018673  test    eax, eax
0x180018675  js      loc_18001874D
0x18001867b  cmp     [rbp+230h+value], si
0x18001867f  jz      loc_18001874D
0x180018685  lea     r8d, [rsi+27h]
0x180018689  lea     rdx, [rsp+330h+var_2E0]
0x18001868e  lea     rcx, CLSID_ControlPanelCategory
0x180018695  call    cs:__imp_SHStringFromGUIDW
0x18001869b  mov     ebx, eax
0x18001869d  test    eax, eax
0x18001869f  js      loc_18001874D
0x1800186a5  lea     r9, [rsp+330h+var_2E0]
0x1800186aa  lea     r8, aS; "::%s"
0x1800186b1  lea     edx, [rsi+29h]; unsigned __int64
0x1800186b4  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x1800186b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800186bd  mov     ebx, eax
0x1800186bf  test    eax, eax
0x1800186c1  js      loc_18001874D
0x1800186c7  xor     r9d, r9d; sfgaoIn
0x1800186ca  mov     [rsp+330h+ppidl], rsi
0x1800186cf  lea     r8, [rsp+330h+ppidl]; ppidl
0x1800186d4  mov     [rsp+330h+psfgaoOut], rsi; psfgaoOut
0x1800186d9  xor     edx, edx; pbc
0x1800186db  lea     rcx, [rbp+230h+pszName]; pszName
0x1800186df  call    cs:__imp_SHParseDisplayName
0x1800186e5  mov     ebx, eax
0x1800186e7  test    eax, eax
0x1800186e9  js      short loc_18001874D
0x1800186eb  mov     rcx, [rdi-8]; punk
0x1800186ef  lea     r9, [rsp+330h+var_300]; ppvOut
0x1800186f4  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x1800186fb  mov     [rsp+330h+var_300], rsi
0x180018700  lea     rdx, SID_STopLevelBrowser; guidService
0x180018707  call    cs:__imp_IUnknown_QueryService
0x18001870d  mov     ebx, eax
0x18001870f  test    eax, eax
0x180018711  js      short loc_180018742
0x180018713  mov     rcx, [rsp+330h+var_300]
0x180018718  mov     r8d, 180001h
0x18001871e  mov     rdx, [rsp+330h+ppidl]
0x180018723  mov     rax, [rcx]
0x180018726  mov     rax, [rax+58h]
0x18001872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001872f  mov     rcx, [rsp+330h+var_300]
0x180018734  mov     ebx, eax
0x180018736  mov     rax, [rcx]
0x180018739  mov     rax, [rax+10h]
0x18001873d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018742  mov     rcx, [rsp+330h+ppidl]; pidl
0x180018747  call    cs:__imp_ILFree
0x18001874d  mov     rcx, [rsp+330h+ppvOut]
0x180018752  mov     rax, [rcx]
0x180018755  mov     rax, [rax+10h]
0x180018759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875e  jmp     short loc_180018765
0x180018760  mov     ebx, 80070057h
0x180018765  mov     eax, ebx
0x180018767  mov     rcx, [rbp+230h+var_20]
0x18001876e  xor     rcx, rsp; StackCookie
0x180018771  call    __security_check_cookie
0x180018776  mov     rbx, [rsp+330h+arg_10]
0x18001877e  add     rsp, 320h
0x180018785  pop     rdi
0x180018786  pop     rsi
0x180018787  pop     rbp
0x180018788  retn
```
