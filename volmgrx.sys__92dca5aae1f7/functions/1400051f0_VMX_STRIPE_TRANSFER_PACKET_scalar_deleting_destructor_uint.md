# VMX_STRIPE_TRANSFER_PACKET::`scalar deleting destructor'(uint)

- ea: `0x1400051f0`
- end: `0x1400052fb`
- name: `??_GVMX_STRIPE_TRANSFER_PACKET@@UEAAPEAXI@Z`
- size: `267`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1400051f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ea`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005253`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005281`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400052d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005253`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005281`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400052d4`
- `ntoskrnl!IoFreeMdl` at `0x140005228`
- `ntoskrnl!IoFreeMdl` at `0x140005228`

## pseudocode

```c
PVOID __fastcall VMX_STRIPE_TRANSFER_PACKET::`scalar deleting destructor'(PVOID P, char a2)
{
  bool v2; // zf
  char v5; // al

  v2 = *((_BYTE *)P + 133) == 0;
  *(_QWORD *)P = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
  if ( !v2 )
  {
    ExFreePoolWithTag((PVOID)(*(_QWORD *)(*((_QWORD *)P + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)P + 3) + 44LL)), 0);
    *((_BYTE *)P + 133) = 0;
  }
  if ( *((_BYTE *)P + 132) )
  {
    IoFreeMdl(*((PMDL *)P + 3));
    *((_BYTE *)P + 132) = 0;
  }
  if ( (a2 & 1) == 0 )
    return P;
  v5 = *((_BYTE *)P + 80);
  if ( v5 == 1 )
  {
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)WPP_MAIN_CB.DeviceExtension, P);
    return P;
  }
  if ( v5 != 2 )
  {
    if ( v5 == 3 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceType, P);
    else
      ExFreePoolWithTag(P, 0);
    return P;
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)WPP_MAIN_CB.Queue.ListEntry.Flink, P);
  return P;
}

```

## disassembly

```asm
0x1400051f0  mov     [rsp+arg_0], rbx
0x1400051f5  mov     [rsp+arg_8], rsi
0x1400051fa  push    rdi
0x1400051fb  sub     rsp, 20h
0x1400051ff  cmp     byte ptr [rcx+85h], 0
0x140005206  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x14000520d  mov     [rcx], rax
0x140005210  mov     esi, edx
0x140005212  mov     rbx, rcx
0x140005215  jnz     loc_1400052A1
0x14000521b  cmp     byte ptr [rbx+84h], 0
0x140005222  jz      short loc_14000523B
0x140005224  mov     rcx, [rbx+18h]; Mdl
0x140005228  call    cs:__imp_IoFreeMdl
0x14000522f  nop     dword ptr [rax+rax+00h]
0x140005234  mov     byte ptr [rbx+84h], 0
0x14000523b  test    sil, 1
0x14000523f  jz      short loc_14000525F
0x140005241  movzx   eax, byte ptr [rbx+50h]
0x140005245  cmp     al, 1
0x140005247  jnz     short loc_140005273
0x140005249  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Lookaside
0x140005250  mov     rdx, rbx; Entry
0x140005253  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000525a  nop     dword ptr [rax+rax+00h]
0x14000525f  mov     rax, rbx
0x140005262  mov     rbx, [rsp+28h+arg_0]
0x140005267  mov     rsi, [rsp+28h+arg_8]
0x14000526c  add     rsp, 20h
0x140005270  pop     rdi
0x140005271  retn
0x140005273  cmp     al, 2
0x140005275  jnz     short loc_1400052C6
0x140005277  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x14000527e  mov     rdx, rbx; Entry
0x140005281  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005288  nop     dword ptr [rax+rax+00h]
0x14000528d  mov     rsi, [rsp+28h+arg_8]
0x140005292  mov     rax, rbx
0x140005295  mov     rbx, [rsp+28h+arg_0]
0x14000529a  add     rsp, 20h
0x14000529e  pop     rdi
0x14000529f  retn
0x1400052a1  mov     rax, [rcx+18h]
0x1400052a5  xor     edx, edx; Tag
0x1400052a7  mov     ecx, [rax+2Ch]
0x1400052aa  add     rcx, [rax+20h]; P
0x1400052ae  call    cs:__imp_ExFreePoolWithTag
0x1400052b5  nop     dword ptr [rax+rax+00h]
0x1400052ba  mov     byte ptr [rbx+85h], 0
0x1400052c1  jmp     loc_14000521B
0x1400052c6  cmp     al, 3
0x1400052c8  jnz     short loc_1400052E5
0x1400052ca  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Lookaside
0x1400052d1  mov     rdx, rbx; Entry
0x1400052d4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400052db  nop     dword ptr [rax+rax+00h]
0x1400052e0  jmp     loc_14000525F
0x1400052e5  xor     edx, edx; Tag
0x1400052e7  mov     rcx, rbx; P
0x1400052ea  call    cs:__imp_ExFreePoolWithTag
0x1400052f1  nop     dword ptr [rax+rax+00h]
0x1400052f6  jmp     loc_14000525F
```
