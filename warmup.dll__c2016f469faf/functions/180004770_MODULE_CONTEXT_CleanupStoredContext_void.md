# MODULE_CONTEXT::CleanupStoredContext(void)

- ea: `0x180004770`
- end: `0x1800047b5`
- name: `?CleanupStoredContext@MODULE_CONTEXT@@UEAAXXZ`
- size: `69`
- prototype: `void __fastcall(MODULE_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180004770`
- `0x180006010`

## pseudocode

```c
void __fastcall MODULE_CONTEXT::CleanupStoredContext(MODULE_CONTEXT *this)
{
  __int64 v2; // rcx

  if ( this )
  {
    *(_QWORD *)this = &MODULE_CONTEXT::`vftable';
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 256LL))(v2);
      *((_QWORD *)this + 1) = 0;
    }
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180004770  test    rcx, rcx
0x180004773  jz      short locret_1800047B4
0x180004775  push    rbx
0x180004776  sub     rsp, 20h
0x18000477a  lea     rax, ??_7MODULE_CONTEXT@@6B@; const MODULE_CONTEXT::`vftable'
0x180004781  mov     rbx, rcx
0x180004784  mov     [rcx], rax
0x180004787  mov     rcx, [rcx+8]
0x18000478b  test    rcx, rcx
0x18000478e  jz      short loc_1800047A7
0x180004790  mov     rax, [rcx]
0x180004793  mov     rax, [rax+100h]
0x18000479a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000479f  mov     qword ptr [rbx+8], 0
0x1800047a7  mov     rcx, rbx; Block
0x1800047aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047af  add     rsp, 20h
0x1800047b3  pop     rbx
0x1800047b4  retn
```
