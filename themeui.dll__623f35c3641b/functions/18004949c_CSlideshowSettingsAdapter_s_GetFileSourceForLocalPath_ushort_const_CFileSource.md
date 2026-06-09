# CSlideshowSettingsAdapter::s_GetFileSourceForLocalPath(ushort const *,CFileSource * *)

- ea: `0x18004949c`
- end: `0x18004954d`
- name: `?s_GetFileSourceForLocalPath@CSlideshowSettingsAdapter@@CAJPEBGPEAPEAVCFileSource@@@Z`
- size: `177`
- prototype: `static int(const unsigned __int16 *, struct CFileSource **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180049350`
- `0x1800493ac`

## callees

- `0x180005220`
- `0x18004949c`
- `0x1800618d0`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x1800494c6`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800494c6`
- `SHELL32!SHGetIDListFromObject` at `0x1800494fd`
- `SHELL32!SHGetIDListFromObject` at `0x1800494fd`
- `SHELL32!__imp_ILFree` at `0x18004951d`
- `SHELL32!__imp_ILFree` at `0x18004951d`

## pseudocode

```c
__int64 __fastcall CSlideshowSettingsAdapter::s_GetFileSourceForLocalPath(
        const unsigned __int16 *a1,
        struct CFileSource **a2)
{
  HRESULT FilteredShellItem; // ebx
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp+28h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp+30h] BYREF
  void *ppv; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  ppv = 0;
  FilteredShellItem = SHCreateItemFromParsingName(a1, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( FilteredShellItem >= 0 )
  {
    punk = 0;
    FilteredShellItem = GetFilteredShellItem((struct IShellItem *)ppv, (struct IShellItem **)&punk);
    if ( FilteredShellItem >= 0 )
    {
      ppidl = 0;
      FilteredShellItem = SHGetIDListFromObject(punk, &ppidl);
      if ( FilteredShellItem >= 0 )
      {
        FilteredShellItem = CFileSource::s_CreateFromShellItems(ppidl, 0, a2);
        ILFree(ppidl);
      }
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)FilteredShellItem;
}

```

## disassembly

```asm
0x18004949c  push    rbp
0x18004949e  push    rbx
0x18004949f  push    rdi
0x1800494a0  mov     rbp, rsp
0x1800494a3  sub     rsp, 20h
0x1800494a7  mov     rdi, rdx
0x1800494aa  mov     qword ptr [rdx], 0
0x1800494b1  xor     edx, edx; pbc
0x1800494b3  mov     [rbp+ppv], 0
0x1800494bb  lea     r9, [rbp+ppv]; ppv
0x1800494bf  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800494c6  call    cs:__imp_SHCreateItemFromParsingName
0x1800494cc  mov     ebx, eax
0x1800494ce  test    eax, eax
0x1800494d0  js      short loc_180049543
0x1800494d2  mov     rcx, [rbp+ppv]; struct IShellItem *
0x1800494d6  lea     rdx, [rbp+punk]; struct IShellItem **
0x1800494da  mov     [rbp+punk], 0
0x1800494e2  call    ?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z; GetFilteredShellItem(IShellItem *,IShellItem * *)
0x1800494e7  mov     ebx, eax
0x1800494e9  test    eax, eax
0x1800494eb  js      short loc_180049533
0x1800494ed  mov     rcx, [rbp+punk]; punk
0x1800494f1  lea     rdx, [rbp+ppidl]; ppidl
0x1800494f5  mov     [rbp+ppidl], 0
0x1800494fd  call    cs:__imp_SHGetIDListFromObject
0x180049503  mov     ebx, eax
0x180049505  test    eax, eax
0x180049507  js      short loc_180049523
0x180049509  mov     rcx, [rbp+ppidl]; pidl
0x18004950d  mov     r8, rdi; struct CFileSource **
0x180049510  xor     edx, edx; struct IShellItemArray *
0x180049512  call    ?s_CreateFromShellItems@CFileSource@@SAJPEFBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellItemArray@@PEAPEAV1@@Z; CFileSource::s_CreateFromShellItems(_ITEMIDLIST_ABSOLUTE const *,IShellItemArray *,CFileSource * *)
0x180049517  mov     rcx, [rbp+ppidl]; pidl
0x18004951b  mov     ebx, eax
0x18004951d  call    cs:__imp_ILFree
0x180049523  mov     rcx, [rbp+punk]
0x180049527  mov     rax, [rcx]
0x18004952a  mov     rax, [rax+10h]
0x18004952e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049533  mov     rcx, [rbp+ppv]
0x180049537  mov     rax, [rcx]
0x18004953a  mov     rax, [rax+10h]
0x18004953e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049543  mov     eax, ebx
0x180049545  add     rsp, 20h
0x180049549  pop     rdi
0x18004954a  pop     rbx
0x18004954b  pop     rbp
0x18004954c  retn
```
