# WinNatDereferenceAddressPoolEntry

- ea: `0x14000f954`
- end: `0x14000f99c`
- name: `WinNatDereferenceAddressPoolEntry`
- size: `72`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bdf0`
- `0x14000f480`
- `0x14000f624`
- `0x14000fce8`
- `0x140010870`
- `0x140010ec4`

## callees

- `0x14000f954`
- `0x14000f9a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f989`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f989`

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
0x14000f954  push    rbx
0x14000f956  sub     rsp, 20h
0x14000f95a  mov     rbx, rcx
0x14000f95d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f961  lock xadd [rcx+10h], rax
0x14000f967  sub     rax, 1
0x14000f96b  jg      short loc_14000F995
0x14000f96d  test    rax, rax
0x14000f970  jz      short loc_14000F97B
0x14000f972  mov     ecx, 0Eh
0x14000f977  int     29h; Win8: RtlFailFast(ecx)
0x14000f979  jmp     short loc_14000F995
0x14000f97b  mov     rcx, [rcx+40h]; P
0x14000f97f  call    WinNatDereferenceInstance
0x14000f984  xor     edx, edx; Tag
0x14000f986  mov     rcx, rbx; P
0x14000f989  call    cs:__imp_ExFreePoolWithTag
0x14000f990  nop     dword ptr [rax+rax+00h]
0x14000f995  add     rsp, 20h
0x14000f999  pop     rbx
0x14000f99a  retn
```
