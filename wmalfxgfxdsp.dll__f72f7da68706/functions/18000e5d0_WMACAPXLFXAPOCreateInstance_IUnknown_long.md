# WMACAPXLFXAPOCreateInstance(IUnknown *,long *)

- ea: `0x18000e5d0`
- end: `0x18000e61a`
- name: `?WMACAPXLFXAPOCreateInstance@@YAPEAVCWMDSPComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `74`
- prototype: `struct CWMDSPComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e5d0`
- `0x18000e620`
- `0x1800150c4`

## pseudocode

```c
struct CWMDSPComBase *__fastcall WMACAPXLFXAPOCreateInstance(struct IUnknown *a1, int *a2)
{
  CCorrAPO_CapX *v4; // rax

  v4 = (CCorrAPO_CapX *)operator new(0x1D8u);
  if ( v4 )
    v4 = CCorrAPO_CapX::CCorrAPO_CapX(v4, a1, a2, 0);
  return (struct CWMDSPComBase *)(((unsigned __int64)v4 + 88) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18000e5d0  mov     [rsp+arg_0], rbx
0x18000e5d5  push    rdi
0x18000e5d6  sub     rsp, 20h
0x18000e5da  mov     rdi, rcx
0x18000e5dd  mov     rbx, rdx
0x18000e5e0  mov     ecx, 1D8h; Size
0x18000e5e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e5ea  test    rax, rax
0x18000e5ed  jz      short loc_18000E618
0x18000e5ef  xor     r9d, r9d; int
0x18000e5f2  mov     r8, rbx; int *
0x18000e5f5  mov     rdx, rdi; struct IUnknown *
0x18000e5f8  mov     rcx, rax; this
0x18000e5fb  call    ??0CCorrAPO_CapX@@QEAA@PEAUIUnknown@@PEAJH@Z; CCorrAPO_CapX::CCorrAPO_CapX(IUnknown *,long *,int)
0x18000e600  mov     rbx, [rsp+28h+arg_0]
0x18000e605  lea     rcx, [rax+58h]
0x18000e609  neg     rax
0x18000e60c  sbb     rax, rax
0x18000e60f  and     rax, rcx
0x18000e612  add     rsp, 20h
0x18000e616  pop     rdi
0x18000e617  retn
0x18000e618  jmp     short loc_18000E600
```
