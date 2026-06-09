# SlbNatCreateExternalAddressForPortFail

- ea: `0x140014c6c`
- end: `0x140014dc4`
- name: `SlbNatCreateExternalAddressForPortFail`
- size: `344`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006f04`

## callees

- `0x140014c6c`
- `0x140015614`
- `0x14001f980`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140014d52`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014d52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d82`
- `ntoskrnl!ExAllocatePool2` at `0x140014cf2`
- `ntoskrnl!ExAllocatePool2` at `0x140014cf2`

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
0x140014c6c  mov     rax, rsp
0x140014c6f  mov     [rax+8], rbx
0x140014c73  mov     [rax+10h], rsi
0x140014c77  push    rdi
0x140014c78  sub     rsp, 0F0h
0x140014c7f  movaps  xmmword ptr [rax-18h], xmm6
0x140014c83  mov     esi, edx
0x140014c85  movaps  xmmword ptr [rax-28h], xmm7
0x140014c89  xor     edx, edx; Val
0x140014c8b  movaps  xmmword ptr [rax-38h], xmm8
0x140014c90  mov     dil, r8b
0x140014c93  mov     rbx, rcx
0x140014c96  movaps  xmmword ptr [rax-48h], xmm9
0x140014c9b  lea     rcx, [rsp+0F8h+var_B8]; void *
0x140014ca0  movaps  xmmword ptr [rax-58h], xmm10
0x140014ca5  lea     r8d, [rdx+54h]; Size
0x140014ca9  call    memset
0x140014cae  movups  xmm6, xmmword ptr [rbx]
0x140014cb1  xor     eax, eax
0x140014cb3  mov     edx, 90h
0x140014cb8  movups  xmm7, xmmword ptr [rbx+10h]
0x140014cbc  mov     [rsp+0F8h+var_C8], rax
0x140014cc1  mov     r8d, 61704E53h
0x140014cc7  mov     eax, [rbx+50h]
0x140014cca  xorps   xmm0, xmm0
0x140014ccd  movups  xmm8, xmmword ptr [rbx+20h]
0x140014cd2  movups  xmm9, xmmword ptr [rbx+30h]
0x140014cd7  movups  xmm10, xmmword ptr [rbx+40h]
0x140014cdc  movups  [rsp+0F8h+var_D8], xmm0
0x140014ce1  mov     dword ptr [rsp+0F8h+var_D8+4], eax
0x140014ce5  mov     eax, 2
0x140014cea  mov     word ptr [rsp+0F8h+var_D8], ax
0x140014cef  lea     ecx, [rax+3Eh]
0x140014cf2  call    cs:__imp_ExAllocatePool2
0x140014cf9  nop     dword ptr [rax+rax+00h]
0x140014cfe  mov     rbx, rax
0x140014d01  test    rax, rax
0x140014d04  jz      loc_140014D8E
0x140014d0a  movups  xmm0, [rsp+0F8h+var_D8]
0x140014d0f  mov     [rbx+80h], dil
0x140014d16  movsd   xmm1, [rsp+0F8h+var_C8]
0x140014d1c  movups  xmmword ptr [rax], xmm6
0x140014d1f  mov     [rbx+84h], esi
0x140014d25  movups  xmmword ptr [rax+10h], xmm7
0x140014d29  movups  xmmword ptr [rax+20h], xmm8
0x140014d2e  movups  xmmword ptr [rax+30h], xmm9
0x140014d33  movups  xmmword ptr [rax+40h], xmm10
0x140014d38  mov     eax, [rsp+0F8h+var_68]
0x140014d3f  movups  xmmword ptr [rbx+54h], xmm0
0x140014d43  mov     [rbx+50h], eax
0x140014d46  movsd   qword ptr [rbx+64h], xmm1
0x140014d4b  mov     rcx, cs:deviceObject; DeviceObject
0x140014d52  call    cs:__imp_IoAllocateWorkItem
0x140014d59  nop     dword ptr [rax+rax+00h]
0x140014d5e  mov     [rbx+70h], rax
0x140014d62  test    rax, rax
0x140014d65  jz      short loc_140014D7D
0x140014d67  xor     edi, edi
0x140014d69  lea     rdx, SlbNatAsyncHandlePortExhaust
0x140014d70  mov     r8, rbx
0x140014d73  mov     rcx, rax
0x140014d76  call    SlbNatQueueWorkItem
0x140014d7b  jmp     short loc_140014D93
0x140014d7d  xor     edx, edx; Tag
0x140014d7f  mov     rcx, rbx; P
0x140014d82  call    cs:__imp_ExFreePoolWithTag
0x140014d89  nop     dword ptr [rax+rax+00h]
0x140014d8e  mov     edi, 0C0000017h
0x140014d93  lea     r11, [rsp+0F8h+var_8]
0x140014d9b  mov     eax, edi
0x140014d9d  mov     rbx, [r11+10h]
0x140014da1  mov     rsi, [r11+18h]
0x140014da5  movaps  xmm6, xmmword ptr [r11-10h]
0x140014daa  movaps  xmm7, xmmword ptr [r11-20h]
0x140014daf  movaps  xmm8, xmmword ptr [r11-30h]
0x140014db4  movaps  xmm9, xmmword ptr [r11-40h]
0x140014db9  movaps  xmm10, xmmword ptr [r11-50h]
0x140014dbe  mov     rsp, r11
0x140014dc1  pop     rdi
0x140014dc2  retn
```
