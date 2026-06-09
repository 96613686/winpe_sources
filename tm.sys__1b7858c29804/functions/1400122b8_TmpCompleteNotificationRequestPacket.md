# TmpCompleteNotificationRequestPacket

- ea: `0x1400122b8`
- end: `0x140012378`
- name: `TmpCompleteNotificationRequestPacket`
- size: `192`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012260`
- `0x140012c1c`
- `0x14001c010`

## callees

- `0x140002510`
- `0x14000d198`
- `0x1400122b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012360`
- `ntoskrnl!IoSetIoCompletion` at `0x14001232f`
- `ntoskrnl!IoSetIoCompletion` at `0x14001232f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001233f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001234f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001233f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001234f`

## pseudocode

```c
void __fastcall TmpCompleteNotificationRequestPacket(char *P, __int64 a2)
{
  unsigned int *v3; // rdi
  void *v4; // rcx
  unsigned int v5; // eax
  void *v6; // rdx
  char v7; // [rsp+28h] [rbp-10h]

  v3 = (unsigned int *)(P + 32);
  if ( !*((_DWORD *)P + 8) )
  {
    v4 = (void *)*((_QWORD *)P + 2);
    v5 = *(_DWORD *)(a2 + 48) + 32;
    v6 = (void *)(a2 + 24);
    if ( P[28] )
      RtlCopyToUser(v4, v6, v5);
    else
      RtlCopyVolatileMemory(v4, v6, v5);
  }
  v7 = 1;
  IoSetIoCompletion(*((_QWORD *)P + 7), *((_QWORD *)P + 21), *((_QWORD *)P + 20), *v3, *((unsigned int *)P + 9), v7);
  ObDereferenceObjectDeferDelete(*((PVOID *)P + 7));
  ObDereferenceObjectDeferDelete(*((PVOID *)P + 6));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400122b8  mov     [rsp+arg_8], rbx
0x1400122bd  mov     [rsp+arg_0], rcx
0x1400122c2  push    rdi
0x1400122c3  sub     rsp, 30h
0x1400122c7  mov     rbx, rcx
0x1400122ca  lea     rdi, [rcx+20h]
0x1400122ce  mov     [rsp+38h+arg_10], rdi
0x1400122d3  cmp     dword ptr [rdi], 0
0x1400122d6  jnz     short loc_14001230D
0x1400122d8  mov     rcx, [rcx+10h]; void *
0x1400122dc  mov     r9b, [rbx+1Ch]
0x1400122e0  mov     eax, [rdx+30h]
0x1400122e3  add     eax, 20h ; ' '
0x1400122e6  add     rdx, 18h; Src
0x1400122ea  mov     r8d, eax; Size
0x1400122ed  test    r9b, r9b
0x1400122f0  jz      short loc_1400122F9
0x1400122f2  call    RtlCopyToUser
0x1400122f7  jmp     short loc_1400122FE
0x1400122f9  call    RtlCopyVolatileMemory
0x1400122fe  jmp     short loc_14001230D
0x140012300  mov     rbx, [rsp+38h+arg_0]
0x140012305  mov     [rbx+20h], eax
0x140012308  mov     rdi, [rsp+38h+arg_10]
0x14001230d  mov     eax, [rbx+24h]
0x140012310  mov     [rsp+38h+var_10], 1
0x140012315  mov     [rsp+38h+var_18], rax
0x14001231a  mov     r9d, [rdi]
0x14001231d  mov     r8, [rbx+0A0h]
0x140012324  mov     rdx, [rbx+0A8h]
0x14001232b  mov     rcx, [rbx+38h]
0x14001232f  call    cs:__imp_IoSetIoCompletion
0x140012336  nop     dword ptr [rax+rax+00h]
0x14001233b  mov     rcx, [rbx+38h]; Object
0x14001233f  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140012346  nop     dword ptr [rax+rax+00h]
0x14001234b  mov     rcx, [rbx+30h]; Object
0x14001234f  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140012356  nop     dword ptr [rax+rax+00h]
0x14001235b  xor     edx, edx; Tag
0x14001235d  mov     rcx, rbx; P
0x140012360  call    cs:__imp_ExFreePoolWithTag
0x140012367  nop     dword ptr [rax+rax+00h]
0x14001236c  mov     rbx, [rsp+38h+arg_8]
0x140012371  add     rsp, 30h
0x140012375  pop     rdi
0x140012376  retn
0x140022033  push    rbp
0x140022035  sub     rsp, 30h
0x140022039  mov     rbp, rdx
0x14002203c  call    cs:__imp_ExSystemExceptionFilter
0x140022043  nop     dword ptr [rax+rax+00h]
0x140022048  nop
0x140022049  add     rsp, 30h
0x14002204d  pop     rbp
0x14002204e  retn
```
