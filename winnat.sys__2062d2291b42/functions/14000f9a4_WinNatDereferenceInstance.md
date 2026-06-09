# WinNatDereferenceInstance

- ea: `0x14000f9a4`
- end: `0x14000f9eb`
- name: `WinNatDereferenceInstance`
- size: `71`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f738`
- `0x14000f904`
- `0x14000f954`
- `0x14000f9f4`
- `0x140010870`
- `0x140010a00`
- `0x140010ec4`
- `0x140011130`
- `0x140011420`

## callees

- `0x14000c440`
- `0x14000f9a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f9d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f9d8`

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
0x14000f9a4  push    rbx
0x14000f9a6  sub     rsp, 20h
0x14000f9aa  mov     rbx, rcx
0x14000f9ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f9b1  lock xadd [rcx+140h], rax
0x14000f9ba  sub     rax, 1
0x14000f9be  jg      short loc_14000F9E4
0x14000f9c0  test    rax, rax
0x14000f9c3  jz      short loc_14000F9CE
0x14000f9c5  mov     ecx, 0Eh
0x14000f9ca  int     29h; Win8: RtlFailFast(ecx)
0x14000f9cc  jmp     short loc_14000F9E4
0x14000f9ce  call    WinNatDereferenceGlobal
0x14000f9d3  xor     edx, edx; Tag
0x14000f9d5  mov     rcx, rbx; P
0x14000f9d8  call    cs:__imp_ExFreePoolWithTag
0x14000f9df  nop     dword ptr [rax+rax+00h]
0x14000f9e4  add     rsp, 20h
0x14000f9e8  pop     rbx
0x14000f9e9  retn
```
