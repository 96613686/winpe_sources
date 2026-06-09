# PgmDestroyAddress

- ea: `0x140002550`
- end: `0x1400025ca`
- name: `PgmDestroyAddress`
- size: `122`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a50`
- `0x1400023b8`
- `0x14000702c`

## callees

- `0x140002550`
- `0x1400387d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000259b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000259b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025b7`

## pseudocode

```c
void __fastcall PgmDestroyAddress(PVOID P)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)P + 11);
  if ( v2 )
  {
    CloseAddressHandles(v2, *((PVOID *)P + 12));
    *((_QWORD *)P + 11) = 0;
  }
  v3 = (void *)*((_QWORD *)P + 8);
  if ( v3 )
  {
    CloseAddressHandles(v3, *((PVOID *)P + 9));
    *((_QWORD *)P + 8) = 0;
  }
  v4 = (void *)*((_QWORD *)P + 28);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *((_QWORD *)P + 28) = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140002550  push    rbx
0x140002552  sub     rsp, 20h
0x140002556  mov     rbx, rcx
0x140002559  mov     rcx, [rcx+58h]; Handle
0x14000255d  test    rcx, rcx
0x140002560  jz      short loc_140002573
0x140002562  mov     rdx, [rbx+60h]; Object
0x140002566  call    CloseAddressHandles
0x14000256b  mov     qword ptr [rbx+58h], 0
0x140002573  mov     rcx, [rbx+40h]; Handle
0x140002577  test    rcx, rcx
0x14000257a  jz      short loc_14000258D
0x14000257c  mov     rdx, [rbx+48h]; Object
0x140002580  call    CloseAddressHandles
0x140002585  mov     qword ptr [rbx+40h], 0
0x14000258d  mov     rcx, [rbx+0E0h]; P
0x140002594  test    rcx, rcx
0x140002597  jz      short loc_1400025B2
0x140002599  xor     edx, edx; Tag
0x14000259b  call    cs:__imp_ExFreePoolWithTag
0x1400025a2  nop     dword ptr [rax+rax+00h]
0x1400025a7  mov     qword ptr [rbx+0E0h], 0
0x1400025b2  xor     edx, edx; Tag
0x1400025b4  mov     rcx, rbx; P
0x1400025b7  call    cs:__imp_ExFreePoolWithTag
0x1400025be  nop     dword ptr [rax+rax+00h]
0x1400025c3  add     rsp, 20h
0x1400025c7  pop     rbx
0x1400025c8  retn
```
