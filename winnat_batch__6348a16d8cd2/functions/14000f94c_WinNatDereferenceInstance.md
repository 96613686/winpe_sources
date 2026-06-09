# WinNatDereferenceInstance

- ea: `0x14000f94c`
- end: `0x14000f993`
- name: `WinNatDereferenceInstance`
- size: `71`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f6e0`
- `0x14000f8ac`
- `0x14000f8fc`
- `0x14000f99c`
- `0x140010810`
- `0x1400109a0`
- `0x140010e64`
- `0x1400110d0`
- `0x1400113c0`

## callees

- `0x14000c440`
- `0x14000f94c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f980`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f980`

## pseudocode

```c
void __fastcall WinNatDereferenceInstance(volatile signed __int64 *P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax

  v2 = _InterlockedExchangeAdd64(P + 40, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    WinNatDereferenceGlobal();
    ExFreePoolWithTag((PVOID)P, 0);
  }
}

```

## disassembly

```asm
0x14000f94c  push    rbx
0x14000f94e  sub     rsp, 20h
0x14000f952  mov     rbx, rcx
0x14000f955  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f959  lock xadd [rcx+140h], rax
0x14000f962  sub     rax, 1
0x14000f966  jg      short loc_14000F98C
0x14000f968  test    rax, rax
0x14000f96b  jz      short loc_14000F976
0x14000f96d  mov     ecx, 0Eh
0x14000f972  int     29h; Win8: RtlFailFast(ecx)
0x14000f974  jmp     short loc_14000F98C
0x14000f976  call    WinNatDereferenceGlobal
0x14000f97b  xor     edx, edx; Tag
0x14000f97d  mov     rcx, rbx; P
0x14000f980  call    cs:__imp_ExFreePoolWithTag
0x14000f987  nop     dword ptr [rax+rax+00h]
0x14000f98c  add     rsp, 20h
0x14000f990  pop     rbx
0x14000f991  retn
```
