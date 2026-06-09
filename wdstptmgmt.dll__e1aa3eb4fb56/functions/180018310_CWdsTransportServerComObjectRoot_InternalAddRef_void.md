# CWdsTransportServerComObjectRoot::InternalAddRef(void)

- ea: `0x180018310`
- end: `0x180018342`
- name: `?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ`
- size: `50`
- prototype: `unsigned int __fastcall(CWdsTransportServerComObjectRoot *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009e10`
- `0x180009e50`
- `0x18000b2d0`
- `0x18000cd08`
- `0x18000f204`
- `0x18000ff30`
- `0x1800174c4`
- `0x180019750`

## callees

- `0x180006680`
- `0x180018310`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall CWdsTransportServerComObjectRoot::InternalAddRef(CWdsTransportServerComObjectRoot *this)
{
  if ( *((_DWORD *)this + 16) )
    return *(_DWORD *)this
         + (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
  else
    return ATL::SafeIncrementReferenceMultiThread((volatile int *)this);
}

```

## disassembly

```asm
0x180018310  push    rbx
0x180018312  sub     rsp, 20h
0x180018316  cmp     dword ptr [rcx+40h], 0
0x18001831a  mov     rbx, rcx
0x18001831d  jz      short loc_180018338
0x18001831f  mov     rcx, [rcx+38h]
0x180018323  mov     rax, [rcx]
0x180018326  mov     rax, [rax+8]
0x18001832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001832f  add     eax, [rbx]
0x180018331  add     rsp, 20h
0x180018335  pop     rbx
0x180018336  retn
0x180018338  add     rsp, 20h
0x18001833c  pop     rbx
0x18001833d  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
