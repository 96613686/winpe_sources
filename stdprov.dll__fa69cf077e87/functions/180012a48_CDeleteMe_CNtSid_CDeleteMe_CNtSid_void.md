# CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(void)

- ea: `0x180012a48`
- end: `0x180012a6f`
- name: `??1?$CDeleteMe@VCNtSid@@@@QEAA@XZ`
- size: `39`
- prototype: `int __fastcall(CNtSid **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043c0`
- `0x180015d00`
- `0x180015d20`

## callees

- `0x180012a48`

## import_xrefs

- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180012a59`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180012a59`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012a62`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012a62`

## pseudocode

```c
int __fastcall CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(CNtSid **a1)
{
  CNtSid *v1; // rbx
  int result; // eax

  v1 = *a1;
  if ( *a1 )
  {
    CNtSid::~CNtSid(*a1);
    return CWin32DefaultArena::WbemMemFree(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180012a48  push    rbx
0x180012a4a  sub     rsp, 20h
0x180012a4e  mov     rbx, [rcx]
0x180012a51  test    rbx, rbx
0x180012a54  jz      short loc_180012A69
0x180012a56  mov     rcx, rbx
0x180012a59  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x180012a5f  mov     rcx, rbx
0x180012a62  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180012a68  nop
0x180012a69  add     rsp, 20h
0x180012a6d  pop     rbx
0x180012a6e  retn
```
