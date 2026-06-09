# ComTaskMgrBase::`vector deleting destructor'(uint)

- ea: `0x140006f30`
- end: `0x140006f57`
- name: `??_EComTaskMgrBase@@MEAAPEAXI@Z`
- size: `39`
- prototype: `ComTaskMgrBase *__fastcall(ComTaskMgrBase *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140006f30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006f48`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006f48`

## pseudocode

```c
ComTaskMgrBase *__fastcall ComTaskMgrBase::`vector deleting destructor'(ComTaskMgrBase *this, char a2)
{
  *(_QWORD *)this = &ComTaskMgrBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140006f30  push    rbx
0x140006f32  sub     rsp, 20h
0x140006f36  lea     rax, ??_7ComTaskMgrBase@@6B@; const ComTaskMgrBase::`vftable'
0x140006f3d  mov     rbx, rcx
0x140006f40  mov     [rcx], rax
0x140006f43  test    dl, 1
0x140006f46  jz      short loc_140006F4E
0x140006f48  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006f4e  mov     rax, rbx
0x140006f51  add     rsp, 20h
0x140006f55  pop     rbx
0x140006f56  retn
```
