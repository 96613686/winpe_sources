# SlbNatCreateExternalAddressForPortFail

- ea: `0x14001432c`
- end: `0x140014484`
- name: `SlbNatCreateExternalAddressForPortFail`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006f04`

## callees

- `0x14001432c`
- `0x140014cd4`
- `0x14001f440`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140014412`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014412`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014442`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014442`
- `ntoskrnl!ExAllocatePool2` at `0x1400143b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400143b2`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddressForPortFail(__int128 *a1, int a2, char a3)
{
  __int128 v6; // xmm6
  __int128 v7; // xmm7
  __int128 v8; // xmm8
  __int128 v9; // xmm9
  __int128 v10; // xmm10
  __int64 Pool2; // rax
  __int64 v12; // rbx
  int v13; // eax
  PIO_WORKITEM WorkItem; // rax
  unsigned int v15; // edi
  __int128 v17; // [rsp+20h] [rbp-D8h]
  _DWORD v18[21]; // [rsp+40h] [rbp-B8h] BYREF

  memset(v18, 0, sizeof(v18));
  v6 = *a1;
  v7 = a1[1];
  v8 = a1[2];
  v9 = a1[3];
  v10 = a1[4];
  v17 = 0;
  DWORD1(v17) = *((_DWORD *)a1 + 20);
  LOWORD(v17) = 2;
  Pool2 = ExAllocatePool2(64, 144, 1634750035);
  v12 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  *(_BYTE *)(Pool2 + 128) = a3;
  *(_OWORD *)Pool2 = v6;
  *(_DWORD *)(Pool2 + 132) = a2;
  *(_OWORD *)(Pool2 + 16) = v7;
  *(_OWORD *)(Pool2 + 32) = v8;
  *(_OWORD *)(Pool2 + 48) = v9;
  *(_OWORD *)(Pool2 + 64) = v10;
  v13 = v18[20];
  *(_OWORD *)(v12 + 84) = v17;
  *(_DWORD *)(v12 + 80) = v13;
  *(_QWORD *)(v12 + 100) = 0;
  WorkItem = IoAllocateWorkItem(deviceObject);
  *(_QWORD *)(v12 + 112) = WorkItem;
  if ( !WorkItem )
  {
    ExFreePoolWithTag((PVOID)v12, 0);
    return (unsigned int)-1073741801;
  }
  v15 = 0;
  SlbNatQueueWorkItem(WorkItem, &SlbNatAsyncHandlePortExhaust, v12);
  return v15;
}

```

## disassembly

```asm
0x14001432c  mov     rax, rsp
0x14001432f  mov     [rax+8], rbx
0x140014333  mov     [rax+10h], rsi
0x140014337  push    rdi
0x140014338  sub     rsp, 0F0h
0x14001433f  movaps  xmmword ptr [rax-18h], xmm6
0x140014343  mov     esi, edx
0x140014345  movaps  xmmword ptr [rax-28h], xmm7
0x140014349  xor     edx, edx; Val
0x14001434b  movaps  xmmword ptr [rax-38h], xmm8
0x140014350  mov     dil, r8b
0x140014353  mov     rbx, rcx
0x140014356  movaps  xmmword ptr [rax-48h], xmm9
0x14001435b  lea     rcx, [rsp+0F8h+var_B8]; void *
0x140014360  movaps  xmmword ptr [rax-58h], xmm10
0x140014365  lea     r8d, [rdx+54h]; Size
0x140014369  call    memset
0x14001436e  movups  xmm6, xmmword ptr [rbx]
0x140014371  xor     eax, eax
0x140014373  mov     edx, 90h
0x140014378  movups  xmm7, xmmword ptr [rbx+10h]
0x14001437c  mov     [rsp+0F8h+var_C8], rax
0x140014381  mov     r8d, 61704E53h
0x140014387  mov     eax, [rbx+50h]
0x14001438a  xorps   xmm0, xmm0
0x14001438d  movups  xmm8, xmmword ptr [rbx+20h]
0x140014392  movups  xmm9, xmmword ptr [rbx+30h]
0x140014397  movups  xmm10, xmmword ptr [rbx+40h]
0x14001439c  movups  [rsp+0F8h+var_D8], xmm0
0x1400143a1  mov     dword ptr [rsp+0F8h+var_D8+4], eax
0x1400143a5  mov     eax, 2
0x1400143aa  mov     word ptr [rsp+0F8h+var_D8], ax
0x1400143af  lea     ecx, [rax+3Eh]
0x1400143b2  call    cs:__imp_ExAllocatePool2
0x1400143b9  nop     dword ptr [rax+rax+00h]
0x1400143be  mov     rbx, rax
0x1400143c1  test    rax, rax
0x1400143c4  jz      loc_14001444E
0x1400143ca  movups  xmm0, [rsp+0F8h+var_D8]
0x1400143cf  mov     [rbx+80h], dil
0x1400143d6  movsd   xmm1, [rsp+0F8h+var_C8]
0x1400143dc  movups  xmmword ptr [rax], xmm6
0x1400143df  mov     [rbx+84h], esi
0x1400143e5  movups  xmmword ptr [rax+10h], xmm7
0x1400143e9  movups  xmmword ptr [rax+20h], xmm8
0x1400143ee  movups  xmmword ptr [rax+30h], xmm9
0x1400143f3  movups  xmmword ptr [rax+40h], xmm10
0x1400143f8  mov     eax, [rsp+0F8h+var_68]
0x1400143ff  movups  xmmword ptr [rbx+54h], xmm0
0x140014403  mov     [rbx+50h], eax
0x140014406  movsd   qword ptr [rbx+64h], xmm1
0x14001440b  mov     rcx, cs:deviceObject; DeviceObject
0x140014412  call    cs:__imp_IoAllocateWorkItem
0x140014419  nop     dword ptr [rax+rax+00h]
0x14001441e  mov     [rbx+70h], rax
0x140014422  test    rax, rax
0x140014425  jz      short loc_14001443D
0x140014427  xor     edi, edi
0x140014429  lea     rdx, SlbNatAsyncHandlePortExhaust
0x140014430  mov     r8, rbx
0x140014433  mov     rcx, rax
0x140014436  call    SlbNatQueueWorkItem
0x14001443b  jmp     short loc_140014453
0x14001443d  xor     edx, edx; Tag
0x14001443f  mov     rcx, rbx; P
0x140014442  call    cs:__imp_ExFreePoolWithTag
0x140014449  nop     dword ptr [rax+rax+00h]
0x14001444e  mov     edi, 0C0000017h
0x140014453  lea     r11, [rsp+0F8h+var_8]
0x14001445b  mov     eax, edi
0x14001445d  mov     rbx, [r11+10h]
0x140014461  mov     rsi, [r11+18h]
0x140014465  movaps  xmm6, xmmword ptr [r11-10h]
0x14001446a  movaps  xmm7, xmmword ptr [r11-20h]
0x14001446f  movaps  xmm8, xmmword ptr [r11-30h]
0x140014474  movaps  xmm9, xmmword ptr [r11-40h]
0x140014479  movaps  xmm10, xmmword ptr [r11-50h]
0x14001447e  mov     rsp, r11
0x140014481  pop     rdi
0x140014482  retn
```
