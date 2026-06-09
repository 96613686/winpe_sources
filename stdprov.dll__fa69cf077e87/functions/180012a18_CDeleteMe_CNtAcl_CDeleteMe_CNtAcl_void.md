# CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)

- ea: `0x180012a18`
- end: `0x180012a3f`
- name: `??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ`
- size: `39`
- prototype: `int __fastcall(CNtAcl **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043c0`
- `0x180015d40`
- `0x180015d60`

## callees

- `0x180012a18`

## import_xrefs

- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180012a29`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180012a29`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012a32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012a32`

## pseudocode

```c
int __fastcall CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(CNtAcl **a1)
{
  CNtAcl *v1; // rbx
  int result; // eax

  v1 = *a1;
  if ( *a1 )
  {
    CNtAcl::~CNtAcl(*a1);
    return CWin32DefaultArena::WbemMemFree(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180012a18  push    rbx
0x180012a1a  sub     rsp, 20h
0x180012a1e  mov     rbx, [rcx]
0x180012a21  test    rbx, rbx
0x180012a24  jz      short loc_180012A39
0x180012a26  mov     rcx, rbx
0x180012a29  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x180012a2f  mov     rcx, rbx
0x180012a32  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180012a38  nop
0x180012a39  add     rsp, 20h
0x180012a3d  pop     rbx
0x180012a3e  retn
```
