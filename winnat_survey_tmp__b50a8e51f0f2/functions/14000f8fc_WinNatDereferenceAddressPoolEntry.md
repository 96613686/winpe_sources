# WinNatDereferenceAddressPoolEntry

- ea: `0x14000f8fc`
- end: `0x14000f944`
- name: `WinNatDereferenceAddressPoolEntry`
- size: `72`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bdf0`
- `0x14000f428`
- `0x14000f5cc`
- `0x14000fc88`
- `0x140010810`
- `0x140010e64`

## callees

- `0x14000f8fc`
- `0x14000f94c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f931`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f931`

## pseudocode

```c
void __fastcall WinNatDereferenceAddressPoolEntry(PVOID P)
{
  signed __int64 v2; // rax
  bool v3; // zf
  bool v4; // sf
  bool v5; // of
  signed __int64 v6; // rax

  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 2, 0xFFFFFFFFFFFFFFFFuLL);
  v5 = __OFSUB__(v2, 1);
  v3 = v2 == 1;
  v4 = v2 - 1 < 0;
  v6 = v2 - 1;
  if ( v4 ^ v5 | v3 )
  {
    if ( v6 )
      __fastfail(0xEu);
    WinNatDereferenceInstance(*((volatile signed __int64 **)P + 8));
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000f8fc  push    rbx
0x14000f8fe  sub     rsp, 20h
0x14000f902  mov     rbx, rcx
0x14000f905  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f909  lock xadd [rcx+10h], rax
0x14000f90f  sub     rax, 1
0x14000f913  jg      short loc_14000F93D
0x14000f915  test    rax, rax
0x14000f918  jz      short loc_14000F923
0x14000f91a  mov     ecx, 0Eh
0x14000f91f  int     29h; Win8: RtlFailFast(ecx)
0x14000f921  jmp     short loc_14000F93D
0x14000f923  mov     rcx, [rcx+40h]; P
0x14000f927  call    WinNatDereferenceInstance
0x14000f92c  xor     edx, edx; Tag
0x14000f92e  mov     rcx, rbx; P
0x14000f931  call    cs:__imp_ExFreePoolWithTag
0x14000f938  nop     dword ptr [rax+rax+00h]
0x14000f93d  add     rsp, 20h
0x14000f941  pop     rbx
0x14000f942  retn
```
