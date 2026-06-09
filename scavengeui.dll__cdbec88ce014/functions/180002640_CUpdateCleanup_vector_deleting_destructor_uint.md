# CUpdateCleanup::`vector deleting destructor'(uint)

- ea: `0x180002640`
- end: `0x18000266e`
- name: `??_ECUpdateCleanup@@UEAAPEAXI@Z`
- size: `46`
- prototype: `CUpdateCleanup *__fastcall(CUpdateCleanup *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callees

- `0x180002640`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000265f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000265f`

## pseudocode

```c
CUpdateCleanup *__fastcall CUpdateCleanup::`vector deleting destructor'(CUpdateCleanup *this, char a2)
{
  *(_QWORD *)this = &CCleanupBase::`vftable';
  _InterlockedDecrement(&dword_18000A8D4);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002640  push    rbx
0x180002642  sub     rsp, 20h
0x180002646  lea     rax, ??_7CCleanupBase@@6B@; const CCleanupBase::`vftable'
0x18000264d  mov     rbx, rcx
0x180002650  mov     [rcx], rax
0x180002653  lock dec cs:dword_18000A8D4
0x18000265a  test    dl, 1
0x18000265d  jz      short loc_180002665
0x18000265f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002665  mov     rax, rbx
0x180002668  add     rsp, 20h
0x18000266c  pop     rbx
0x18000266d  retn
```
