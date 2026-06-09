# CWdsTransportServerComObjectRoot::InternalRelease(void)

- ea: `0x180018348`
- end: `0x180018379`
- name: `?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(CWdsTransportServerComObjectRoot *__hidden this)`
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009e50`
- `0x18000a9d0`
- `0x18000b2d0`
- `0x18000bcc0`
- `0x18000cd08`
- `0x18000d920`
- `0x18000f204`
- `0x18000fa40`
- `0x18000ff30`
- `0x180010570`
- `0x1800174c4`
- `0x180017cb0`
- `0x180019750`
- `0x180019c40`

## callees

- `0x180006654`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall CWdsTransportServerComObjectRoot::InternalRelease(CWdsTransportServerComObjectRoot *this)
{
  volatile int v1; // ebx

  if ( !*((_DWORD *)this + 16) )
    return ATL::SafeDecrementReferenceMultiThread((volatile int *)this);
  v1 = *(_DWORD *)this;
  return v1 + (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7));
}

```

## disassembly

```asm
0x180018348  push    rbx
0x18001834a  sub     rsp, 20h
0x18001834e  cmp     dword ptr [rcx+40h], 0
0x180018352  jz      short loc_18001836F
0x180018354  mov     ebx, [rcx]
0x180018356  mov     rcx, [rcx+38h]
0x18001835a  mov     rax, [rcx]
0x18001835d  mov     rax, [rax+10h]
0x180018361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018366  add     eax, ebx
0x180018368  add     rsp, 20h
0x18001836c  pop     rbx
0x18001836d  retn
0x18001836f  add     rsp, 20h
0x180018373  pop     rbx
0x180018374  jmp     ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
```
