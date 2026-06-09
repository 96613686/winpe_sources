# VmbPacketAllocate

- ea: `0x14000a650`
- end: `0x14000a6c7`
- name: `VmbPacketAllocate`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005a80`
- `0x14000a650`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a660`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a660`

## pseudocode

```c
PVOID __fastcall VmbPacketAllocate(__int64 a1)
{
  PVOID result; // rax
  __int64 v3; // r11

  result = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 320));
  if ( result )
  {
    OutInitializePacket(
      a1,
      result,
      (unsigned int)(*(_DWORD *)(*(_QWORD *)a1 + 1736LL) + 240),
      KmclpFreeCompletionRoutine);
    if ( *(_DWORD *)(*(_QWORD *)a1 + 1752LL) )
      *(_QWORD *)(v3 + 40) = v3 + *(unsigned int *)(v3 + 172) + 240LL;
    *(_BYTE *)(v3 + 62) |= 8u;
    return (PVOID)v3;
  }
  return result;
}

```

## disassembly

```asm
0x14000a650  push    rbx
0x14000a652  sub     rsp, 20h
0x14000a656  mov     rbx, rcx
0x14000a659  add     rcx, 140h; Lookaside
0x14000a660  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000a667  nop     dword ptr [rax+rax+00h]
0x14000a66c  mov     r11, rax
0x14000a66f  test    rax, rax
0x14000a672  jz      short loc_14000A6C0
0x14000a674  mov     rdx, [rbx]
0x14000a677  lea     r9, KmclpFreeCompletionRoutine
0x14000a67e  mov     rcx, rbx
0x14000a681  mov     r8d, [rdx+6C8h]
0x14000a688  mov     rdx, rax
0x14000a68b  add     r8d, 0F0h
0x14000a692  call    OutInitializePacket
0x14000a697  mov     rdx, [rbx]
0x14000a69a  cmp     dword ptr [rdx+6D8h], 0
0x14000a6a1  jz      short loc_14000A6B8
0x14000a6a3  mov     ecx, [r11+0ACh]
0x14000a6aa  add     rcx, 0F0h
0x14000a6b1  add     rcx, r11
0x14000a6b4  mov     [r11+28h], rcx
0x14000a6b8  or      byte ptr [r11+3Eh], 8
0x14000a6bd  mov     rax, r11
0x14000a6c0  add     rsp, 20h
0x14000a6c4  pop     rbx
0x14000a6c5  retn
```
