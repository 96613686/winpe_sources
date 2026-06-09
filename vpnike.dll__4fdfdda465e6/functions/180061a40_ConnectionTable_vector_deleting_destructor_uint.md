# ConnectionTable::`vector deleting destructor'(uint)

- ea: `0x180061a40`
- end: `0x180061a81`
- name: `??_EConnectionTable@@MEAAPEAXI@Z`
- size: `65`
- prototype: `ConnectionTable *__fastcall(ConnectionTable *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001564`
- `0x180061a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061a60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061a60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ConnectionTable *__fastcall ConnectionTable::`vector deleting destructor'(ConnectionTable *this, char a2)
{
  *(_QWORD *)this = &ConnectionTable::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24592));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180061a40  mov     [rsp+arg_0], rbx
0x180061a45  push    rdi
0x180061a46  sub     rsp, 20h
0x180061a4a  lea     rax, ??_7ConnectionTable@@6B@; const ConnectionTable::`vftable'
0x180061a51  mov     rdi, rcx
0x180061a54  mov     [rcx], rax
0x180061a57  mov     ebx, edx
0x180061a59  add     rcx, 6010h; lpCriticalSection
0x180061a60  call    cs:__imp_DeleteCriticalSection
0x180061a66  test    bl, 1
0x180061a69  jz      short loc_180061A73
0x180061a6b  mov     rcx, rdi; Block
0x180061a6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061a73  mov     rbx, [rsp+28h+arg_0]
0x180061a78  mov     rax, rdi
0x180061a7b  add     rsp, 20h
0x180061a7f  pop     rdi
0x180061a80  retn
```
