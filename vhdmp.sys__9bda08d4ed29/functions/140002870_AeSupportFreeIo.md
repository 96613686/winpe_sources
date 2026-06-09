# AeSupportFreeIo

- ea: `0x140002870`
- end: `0x1400028d1`
- name: `AeSupportFreeIo`
- size: `97`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400025c0`
- `0x140002600`
- `0x140002db0`
- `0x140002f4c`
- `0x140009c74`
- `0x14002068c`
- `0x14002425c`
- `0x1400280cc`
- `0x140028854`
- `0x140028ad0`
- `0x1400291d0`
- `0x1400293f0`
- `0x1400573c0`
- `0x140059058`
- `0x140059290`
- `0x14009ec04`
- `0x14009ef4c`
- `0x1400d8eb0`
- `0x1400d970c`
- `0x1400db12c`
- `0x1400ddd9c`
- `0x1400e68c0`
- `0x1400e69c8`

## callees

- `0x140002870`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140002886`
- `ntoskrnl!IoFreeMdl` at `0x140002886`
- `ntoskrnl!IoCleanupIrp` at `0x1400028a4`
- `ntoskrnl!IoCleanupIrp` at `0x1400028a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400028be`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400028be`

## pseudocode

```c
void __fastcall AeSupportFreeIo(__int64 a1)
{
  _QWORD *v1; // rbx
  struct _MDL *v2; // rcx

  v1 = (_QWORD *)(a1 - 112);
  v2 = *(struct _MDL **)(a1 - 112 + 184);
  if ( v2 )
  {
    IoFreeMdl(v2);
    v1[23] = 0;
  }
  IoCleanupIrp(v1 + 28);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v1[21] + 64LL), v1);
}

```

## disassembly

```asm
0x140002870  push    rbx
0x140002872  sub     rsp, 20h
0x140002876  lea     rbx, [rcx-70h]
0x14000287a  mov     rcx, [rbx+0B8h]; Mdl
0x140002881  test    rcx, rcx
0x140002884  jz      short loc_14000289D
0x140002886  call    cs:__imp_IoFreeMdl
0x14000288d  nop     dword ptr [rax+rax+00h]
0x140002892  mov     qword ptr [rbx+0B8h], 0
0x14000289d  lea     rcx, [rbx+0E0h]
0x1400028a4  call    cs:__imp_IoCleanupIrp
0x1400028ab  nop     dword ptr [rax+rax+00h]
0x1400028b0  mov     rcx, [rbx+0A8h]
0x1400028b7  mov     rdx, rbx; Entry
0x1400028ba  add     rcx, 40h ; '@'; Lookaside
0x1400028be  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400028c5  nop     dword ptr [rax+rax+00h]
0x1400028ca  add     rsp, 20h
0x1400028ce  pop     rbx
0x1400028cf  retn
```
