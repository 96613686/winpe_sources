# CWallpaperCore::_AddRecentPictureFolder(_ITEMIDLIST_ABSOLUTE *)

- ea: `0x18003f0d8`
- end: `0x18003f235`
- name: `?_AddRecentPictureFolder@CWallpaperCore@@AEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `349`
- prototype: `void __fastcall(CWallpaperCore *__hidden this, struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800423e0`

## callees

- `0x18003f0d8`
- `0x18003f4dc`
- `0x180042ab4`
- `0x18004e78c`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18003f103`
- `SHELL32!SHCreateItemFromIDList` at `0x18003f103`
- `SHELL32!SHGetIDListFromObject` at `0x18003f146`
- `SHELL32!SHGetIDListFromObject` at `0x18003f146`
- `SHELL32!SHGetNameFromIDList` at `0x18003f1ed`
- `SHELL32!SHGetNameFromIDList` at `0x18003f1ed`
- `SHELL32!__imp_ILFree` at `0x18003f1ac`
- `SHELL32!__imp_ILFree` at `0x18003f1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f21b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f21b`

## pseudocode

```c
void __fastcall CWallpaperCore::_AddRecentPictureFolder(CWallpaperCore *this, const ITEMIDLIST *a2)
{
  HRESULT FilteredShellItem; // ebx
  LPVOID pv; // [rsp+20h] [rbp-10h] BYREF
  void *ppv; // [rsp+28h] [rbp-8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp+30h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp+38h] BYREF

  ppv = 0;
  if ( SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) < 0 )
    goto LABEL_9;
  punk = 0;
  FilteredShellItem = GetFilteredShellItem((struct IShellItem *)ppv, (struct IShellItem **)&punk);
  if ( FilteredShellItem >= 0 )
  {
    ppidl = 0;
    FilteredShellItem = SHGetIDListFromObject(punk, &ppidl);
    if ( FilteredShellItem >= 0 )
    {
      pv = 0;
      FilteredShellItem = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPVOID *))punk->lpVtbl[1].Release)(punk, 0, &pv);
      if ( FilteredShellItem >= 0 )
      {
        CWallpaperCore::_AddUserPath(this, (const unsigned __int16 *)pv, ppidl);
        CWallpaperCore::_SelectFromPathCombo(this, (const struct _ITEMIDLIST_ABSOLUTE *)ppidl);
        CoTaskMemFree(pv);
      }
      ILFree(ppidl);
    }
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( FilteredShellItem < 0 )
  {
LABEL_9:
    ppidl = 0;
    if ( SHGetNameFromIDList(a2, SIGDN_NORMALDISPLAY, (PWSTR *)&ppidl) >= 0 )
    {
      CWallpaperCore::_AddUserPath(this, &ppidl->mkid.cb, a2);
      CWallpaperCore::_SelectFromPathCombo(this, (const struct _ITEMIDLIST_ABSOLUTE *)a2);
      CoTaskMemFree(ppidl);
    }
  }
}

```

## disassembly

```asm
0x18003f0d8  mov     [rsp-18h+arg_0], rbx
0x18003f0dd  push    rbp
0x18003f0de  push    rsi
0x18003f0df  push    rdi
0x18003f0e0  mov     rbp, rsp
0x18003f0e3  sub     rsp, 30h
0x18003f0e7  mov     rdi, rdx
0x18003f0ea  mov     [rbp+ppv], 0
0x18003f0f2  mov     rsi, rcx
0x18003f0f5  lea     r8, [rbp+ppv]; ppv
0x18003f0f9  mov     rcx, rdi; pidl
0x18003f0fc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003f103  call    cs:__imp_SHCreateItemFromIDList
0x18003f10a  nop     dword ptr [rax+rax+00h]
0x18003f10f  test    eax, eax
0x18003f111  js      loc_18003F1DC
0x18003f117  mov     rcx, [rbp+ppv]; struct IShellItem *
0x18003f11b  lea     rdx, [rbp+punk]; struct IShellItem **
0x18003f11f  mov     [rbp+punk], 0
0x18003f127  call    ?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z; GetFilteredShellItem(IShellItem *,IShellItem * *)
0x18003f12c  mov     ebx, eax
0x18003f12e  test    eax, eax
0x18003f130  js      loc_18003F1C8
0x18003f136  mov     rcx, [rbp+punk]; punk
0x18003f13a  lea     rdx, [rbp+ppidl]; ppidl
0x18003f13e  mov     [rbp+ppidl], 0
0x18003f146  call    cs:__imp_SHGetIDListFromObject
0x18003f14d  nop     dword ptr [rax+rax+00h]
0x18003f152  mov     ebx, eax
0x18003f154  test    eax, eax
0x18003f156  js      short loc_18003F1B8
0x18003f158  mov     rcx, [rbp+punk]
0x18003f15c  lea     r8, [rbp+pv]
0x18003f160  mov     [rbp+pv], 0
0x18003f168  xor     edx, edx
0x18003f16a  mov     rax, [rcx]
0x18003f16d  mov     rax, [rax+28h]
0x18003f171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f176  mov     ebx, eax
0x18003f178  test    eax, eax
0x18003f17a  js      short loc_18003F1A8
0x18003f17c  mov     r8, [rbp+ppidl]; pidl
0x18003f180  mov     rcx, rsi; this
0x18003f183  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18003f187  call    ?_AddUserPath@CWallpaperCore@@AEAAJPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_AddUserPath(ushort const *,_ITEMIDLIST_ABSOLUTE const *)
0x18003f18c  mov     rdx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x18003f190  mov     rcx, rsi; this
0x18003f193  call    ?_SelectFromPathCombo@CWallpaperCore@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_SelectFromPathCombo(_ITEMIDLIST_ABSOLUTE const *)
0x18003f198  mov     rcx, [rbp+pv]; pv
0x18003f19c  call    cs:__imp_CoTaskMemFree
0x18003f1a3  nop     dword ptr [rax+rax+00h]
0x18003f1a8  mov     rcx, [rbp+ppidl]; pidl
0x18003f1ac  call    cs:__imp_ILFree
0x18003f1b3  nop     dword ptr [rax+rax+00h]
0x18003f1b8  mov     rcx, [rbp+punk]
0x18003f1bc  mov     rax, [rcx]
0x18003f1bf  mov     rax, [rax+10h]
0x18003f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1c8  mov     rcx, [rbp+ppv]
0x18003f1cc  mov     rax, [rcx]
0x18003f1cf  mov     rax, [rax+10h]
0x18003f1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1d8  test    ebx, ebx
0x18003f1da  jns     short loc_18003F227
0x18003f1dc  lea     r8, [rbp+ppidl]; ppszName
0x18003f1e0  mov     [rbp+ppidl], 0
0x18003f1e8  xor     edx, edx; sigdnName
0x18003f1ea  mov     rcx, rdi; pidl
0x18003f1ed  call    cs:__imp_SHGetNameFromIDList
0x18003f1f4  nop     dword ptr [rax+rax+00h]
0x18003f1f9  test    eax, eax
0x18003f1fb  js      short loc_18003F227
0x18003f1fd  mov     rdx, [rbp+ppidl]; unsigned __int16 *
0x18003f201  mov     r8, rdi; pidl
0x18003f204  mov     rcx, rsi; this
0x18003f207  call    ?_AddUserPath@CWallpaperCore@@AEAAJPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_AddUserPath(ushort const *,_ITEMIDLIST_ABSOLUTE const *)
0x18003f20c  mov     rdx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x18003f20f  mov     rcx, rsi; this
0x18003f212  call    ?_SelectFromPathCombo@CWallpaperCore@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_SelectFromPathCombo(_ITEMIDLIST_ABSOLUTE const *)
0x18003f217  mov     rcx, [rbp+ppidl]; pv
0x18003f21b  call    cs:__imp_CoTaskMemFree
0x18003f222  nop     dword ptr [rax+rax+00h]
0x18003f227  mov     rbx, [rsp+30h+arg_0]
0x18003f22c  add     rsp, 30h
0x18003f230  pop     rdi
0x18003f231  pop     rsi
0x18003f232  pop     rbp
0x18003f233  retn
```
