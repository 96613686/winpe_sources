# SHRemoveFolderPathFromLibrary

- ea: `0x180030df0`
- end: `0x180030e80`
- name: `SHRemoveFolderPathFromLibrary`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fc00`

## callees

- `0x180030df0`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e68`
- `SHELL32!SHCreateItemFromIDList` at `0x180030e32`
- `SHELL32!SHCreateItemFromIDList` at `0x180030e32`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x180030e05`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x180030e05`

## pseudocode

```c
__int64 __fastcall SHRemoveFolderPathFromLibrary(__int64 a1, const WCHAR *a2)
{
  const ITEMIDLIST *v3; // rax
  ITEMIDLIST *v4; // rdi
  HRESULT v5; // ebx
  void *ppv; // [rsp+40h] [rbp+18h] BYREF

  v3 = SHSimpleIDListFromPath(a2);
  v4 = (ITEMIDLIST *)v3;
  if ( v3 )
  {
    ppv = 0;
    v5 = SHCreateItemFromIDList(v3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a1 + 48LL))(a1, ppv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoTaskMemFree(v4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030df0  mov     [rsp+arg_0], rbx
0x180030df5  mov     [rsp+arg_8], rsi
0x180030dfa  push    rdi
0x180030dfb  sub     rsp, 20h
0x180030dff  mov     rsi, rcx
0x180030e02  mov     rcx, rdx; pszPath
0x180030e05  call    cs:__imp_SHSimpleIDListFromPath
0x180030e0b  mov     rdi, rax
0x180030e0e  test    rax, rax
0x180030e11  jnz     short loc_180030E1A
0x180030e13  mov     ebx, 80070057h
0x180030e18  jmp     short loc_180030E6E
0x180030e1a  lea     r8, [rsp+28h+ppv]; ppv
0x180030e1f  mov     [rsp+28h+ppv], 0
0x180030e28  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180030e2f  mov     rcx, rdi; pidl
0x180030e32  call    cs:__imp_SHCreateItemFromIDList
0x180030e38  mov     ebx, eax
0x180030e3a  test    eax, eax
0x180030e3c  js      short loc_180030E65
0x180030e3e  mov     rax, [rsi]
0x180030e41  mov     rcx, rsi
0x180030e44  mov     rdx, [rsp+28h+ppv]
0x180030e49  mov     rax, [rax+30h]
0x180030e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e52  mov     rcx, [rsp+28h+ppv]
0x180030e57  mov     ebx, eax
0x180030e59  mov     rax, [rcx]
0x180030e5c  mov     rax, [rax+10h]
0x180030e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e65  mov     rcx, rdi; pv
0x180030e68  call    cs:__imp_CoTaskMemFree
0x180030e6e  mov     rsi, [rsp+28h+arg_8]
0x180030e73  mov     eax, ebx
0x180030e75  mov     rbx, [rsp+28h+arg_0]
0x180030e7a  add     rsp, 20h
0x180030e7e  pop     rdi
0x180030e7f  retn
```
