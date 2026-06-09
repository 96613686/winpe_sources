# CWMPRichPreviewRemoteService::GetShellItemFromPath(ushort const *,IShellItem * *)

- ea: `0x140004f40`
- end: `0x140004fdb`
- name: `?GetShellItemFromPath@CWMPRichPreviewRemoteService@@EEAAJPEBGPEAPEAUIShellItem@@@Z`
- size: `155`
- prototype: `int(CWMPRichPreviewRemoteService *__hidden this, const unsigned __int16 *, struct IShellItem **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140004f40`
- `0x14000f010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x140004f73`
- `SHELL32!SHParseDisplayName` at `0x140004f73`
- `SHELL32!SHCreateItemFromIDList` at `0x140004f90`
- `SHELL32!SHCreateItemFromIDList` at `0x140004f90`
- `SHELL32!__imp_ILFree` at `0x140004fb2`
- `SHELL32!__imp_ILFree` at `0x140004fb2`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::GetShellItemFromPath(
        CWMPRichPreviewRemoteService *this,
        const unsigned __int16 *a2,
        struct IShellItem **a3)
{
  HRESULT v4; // ebx
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-18h] BYREF
  void *ppv; // [rsp+68h] [rbp+20h] BYREF

  ppv = 0;
  pidl = 0;
  v4 = SHParseDisplayName(a2, 0, (LPITEMIDLIST *)&pidl, 0, 0);
  if ( v4 >= 0 )
  {
    v4 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v4 >= 0 )
    {
      *a3 = (struct IShellItem *)ppv;
      ppv = 0;
    }
    ILFree((LPITEMIDLIST)pidl);
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140004f40  mov     rax, rsp
0x140004f43  mov     [rax+8], rbx
0x140004f47  push    rdi
0x140004f48  sub     rsp, 40h
0x140004f4c  mov     rdi, r8
0x140004f4f  mov     qword ptr [rax+20h], 0
0x140004f57  mov     rcx, rdx; pszName
0x140004f5a  mov     qword ptr [rax-18h], 0
0x140004f62  lea     r8, [rax-18h]; ppidl
0x140004f66  mov     qword ptr [rax-28h], 0
0x140004f6e  xor     edx, edx; pbc
0x140004f70  xor     r9d, r9d; sfgaoIn
0x140004f73  call    cs:__imp_SHParseDisplayName
0x140004f79  mov     ebx, eax
0x140004f7b  test    eax, eax
0x140004f7d  js      short loc_140004FB8
0x140004f7f  mov     rcx, [rsp+48h+pidl]; pidl
0x140004f84  lea     r8, [rsp+48h+ppv]; ppv
0x140004f89  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x140004f90  call    cs:__imp_SHCreateItemFromIDList
0x140004f96  mov     ebx, eax
0x140004f98  test    eax, eax
0x140004f9a  js      short loc_140004FAD
0x140004f9c  mov     rax, [rsp+48h+ppv]
0x140004fa1  mov     [rdi], rax
0x140004fa4  mov     [rsp+48h+ppv], 0
0x140004fad  mov     rcx, [rsp+48h+pidl]; pidl
0x140004fb2  call    cs:__imp_ILFree
0x140004fb8  mov     rcx, [rsp+48h+ppv]
0x140004fbd  test    rcx, rcx
0x140004fc0  jz      short loc_140004FCE
0x140004fc2  mov     rax, [rcx]
0x140004fc5  mov     rax, [rax+10h]
0x140004fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fce  mov     eax, ebx
0x140004fd0  mov     rbx, [rsp+48h+arg_0]
0x140004fd5  add     rsp, 40h
0x140004fd9  pop     rdi
0x140004fda  retn
```
