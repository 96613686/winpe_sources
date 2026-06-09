# WMAGFXAPOCreateInstance(IUnknown *,long *)

- ea: `0x18000e570`
- end: `0x18000e5bd`
- name: `?WMAGFXAPOCreateInstance@@YAPEAVCWMDSPComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `77`
- prototype: `struct CWMDSPComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e570`
- `0x18000e720`
- `0x1800150c4`

## pseudocode

```c
struct CWMDSPComBase *__fastcall WMAGFXAPOCreateInstance(struct IUnknown *a1, int *a2)
{
  CCorrAPO *v4; // rax

  v4 = (CCorrAPO *)operator new(0x1D8u);
  if ( v4 )
    v4 = CCorrAPO::CCorrAPO(v4, a1, a2, 1);
  return (struct CWMDSPComBase *)(((unsigned __int64)v4 + 88) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18000e570  mov     [rsp+arg_0], rbx
0x18000e575  push    rdi
0x18000e576  sub     rsp, 20h
0x18000e57a  mov     rdi, rcx
0x18000e57d  mov     rbx, rdx
0x18000e580  mov     ecx, 1D8h; Size
0x18000e585  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e58a  test    rax, rax
0x18000e58d  jz      short loc_18000E5BB
0x18000e58f  mov     r9d, 1; int
0x18000e595  mov     r8, rbx; int *
0x18000e598  mov     rdx, rdi; struct IUnknown *
0x18000e59b  mov     rcx, rax; this
0x18000e59e  call    ??0CCorrAPO@@QEAA@PEAUIUnknown@@PEAJH@Z; CCorrAPO::CCorrAPO(IUnknown *,long *,int)
0x18000e5a3  mov     rbx, [rsp+28h+arg_0]
0x18000e5a8  lea     rcx, [rax+58h]
0x18000e5ac  neg     rax
0x18000e5af  sbb     rax, rax
0x18000e5b2  and     rax, rcx
0x18000e5b5  add     rsp, 20h
0x18000e5b9  pop     rdi
0x18000e5ba  retn
0x18000e5bb  jmp     short loc_18000E5A3
```
