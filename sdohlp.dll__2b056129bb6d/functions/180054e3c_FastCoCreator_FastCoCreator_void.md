# FastCoCreator::~FastCoCreator(void)

- ea: `0x180054e3c`
- end: `0x180054e6a`
- name: `??1FastCoCreator@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(FastCoCreator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180057540`

## callees

- `0x180054e3c`
- `0x180058010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180054e63`

## pseudocode

```c
void __fastcall FastCoCreator::~FastCoCreator(FastCoCreator *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180054e3c  push    rbx
0x180054e3e  sub     rsp, 20h
0x180054e42  mov     rbx, rcx
0x180054e45  mov     rcx, [rcx+40h]
0x180054e49  test    rcx, rcx
0x180054e4c  jz      short loc_180054E5A
0x180054e4e  mov     rax, [rcx]
0x180054e51  mov     rax, [rax+10h]
0x180054e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e5a  lea     rcx, [rbx+10h]
0x180054e5e  add     rsp, 20h
0x180054e62  pop     rbx
0x180054e63  jmp     cs:__imp_DeleteCriticalSection
```
