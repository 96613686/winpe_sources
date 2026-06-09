# WanpHandleDemandDialCallOutRequest

- ea: `0x1400140e4`
- end: `0x1400142d3`
- name: `WanpHandleDemandDialCallOutRequest`
- size: `495`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400048d0`

## callees

- `0x140001fb0`
- `0x14000488c`
- `0x1400050b0`
- `0x1400051c0`
- `0x1400140e4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001416f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001416f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400142a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400142a6`
- `ntoskrnl!ExQueueWorkItem` at `0x140014280`
- `ntoskrnl!ExQueueWorkItem` at `0x140014280`
- `NDIS!NdisGetDataBuffer` at `0x140014149`
- `NDIS!NdisGetDataBuffer` at `0x140014239`
- `NDIS!NdisGetDataBuffer` at `0x140014149`
- `NDIS!NdisGetDataBuffer` at `0x140014239`

## pseudocode

```c
__int64 __fastcall WanpHandleDemandDialCallOutRequest(__int64 a1, __int64 a2)
{
  struct _NET_BUFFER *v2; // rbp
  __int64 v4; // r15
  char v5; // bl
  char *p_Storage; // r8
  _DWORD *DataBuffer; // rax
  char *v8; // rdi
  _DWORD *v9; // rsi
  char *v10; // rax
  char *v11; // rbx
  unsigned int v12; // r14d
  PVOID v13; // rdi
  char v14; // al
  ULONG DataLength; // esi
  PVOID v16; // rax
  char Storage; // [rsp+30h] [rbp-88h] BYREF
  char v19; // [rsp+48h] [rbp-70h] BYREF

  v2 = *(struct _NET_BUFFER **)(a1 + 8);
  v4 = *(_QWORD *)(a2 + 24);
  v5 = *(_BYTE *)(a2 + 20);
  NetioAdvanceNetBuffer(v2, 14);
  p_Storage = &v19;
  if ( v5 )
    p_Storage = &Storage;
  DataBuffer = NdisGetDataBuffer(v2, v5 != 0 ? 20 : 40, p_Storage, 1u, 0);
  if ( *(_BYTE *)(a2 + 20) )
  {
    v8 = 0;
    v9 = DataBuffer;
  }
  else
  {
    v9 = 0;
    v8 = (char *)DataBuffer;
  }
  v10 = (char *)ExAllocateFromNPagedLookasideList(&g_llNotificationBlocks);
  v11 = v10;
  if ( !v10 )
  {
    NetioRetreatNetBuffer(v2);
    return (unsigned int)-1073741670;
  }
  *((_DWORD *)v10 + 12) = 0;
  *((_DWORD *)v10 + 13) = *(_DWORD *)(a2 + 32);
  *((_DWORD *)v10 + 14) = *(_DWORD *)(v4 + 360);
  if ( *(_BYTE *)(a2 + 20) )
  {
    if ( v9 )
    {
      v13 = v10 + 77;
      *((_DWORD *)v10 + 16) = v9[3];
      *((_DWORD *)v10 + 17) = v9[4];
      *((_DWORD *)v10 + 18) = *((unsigned __int16 *)v9 + 1);
      v10[76] = *((_BYTE *)v9 + 9);
      goto LABEL_13;
    }
LABEL_21:
    NetioRetreatNetBuffer(v2);
    v12 = -1073741811;
    ExFreeToNPagedLookasideList(&g_llNotificationBlocks, v11);
    return v12;
  }
  if ( !v8 )
    goto LABEL_21;
  *((_OWORD *)v10 + 4) = *(_OWORD *)(v8 + 8);
  *((_OWORD *)v10 + 5) = *(_OWORD *)(v8 + 24);
  *((_DWORD *)v10 + 24) = *((unsigned __int16 *)v8 + 2);
  v10[100] = v8[6];
  v14 = v8[7];
  v13 = v11 + 102;
  v11[101] = v14;
LABEL_13:
  if ( !v13 )
    goto LABEL_21;
  DataLength = v2->DataLength;
  v12 = 0;
  if ( DataLength )
  {
    if ( DataLength >= 0x5EA )
      DataLength = 1514;
    v16 = NdisGetDataBuffer(v2, DataLength, v13, 1u, 0);
    if ( v16 && v16 != v13 )
      memmove(v13, v16, DataLength);
  }
  NetioRetreatNetBuffer(v2);
  *((_QWORD *)v11 + 5) = v11;
  *((_QWORD *)v11 + 4) = WanpCompleteIrp;
  *((_QWORD *)v11 + 2) = 0;
  ExQueueWorkItem((PWORK_QUEUE_ITEM)(v11 + 16), DelayedWorkQueue);
  return v12;
}

```

## disassembly

```asm
0x1400140e4  push    rbx
0x1400140e6  push    rbp
0x1400140e7  push    rsi
0x1400140e8  push    rdi
0x1400140e9  push    r14
0x1400140eb  push    r15
0x1400140ed  sub     rsp, 88h
0x1400140f4  mov     rax, cs:__security_cookie
0x1400140fb  xor     rax, rsp
0x1400140fe  mov     [rsp+0B8h+var_48], rax
0x140014103  mov     rbp, [rcx+8]
0x140014107  mov     r14, rdx
0x14001410a  mov     r15, [rdx+18h]
0x14001410e  mov     rcx, rbp
0x140014111  mov     bl, [rdx+14h]
0x140014114  mov     edx, 0Eh
0x140014119  call    NetioAdvanceNetBuffer
0x14001411e  test    bl, bl
0x140014120  mov     [rsp+0B8h+AlignOffset], 0; AlignOffset
0x140014128  lea     rax, [rsp+0B8h+Storage]
0x14001412d  mov     r9d, 1; AlignMultiple
0x140014133  lea     r8, [rsp+0B8h+var_70]
0x140014138  mov     rcx, rbp; NetBuffer
0x14001413b  cmovnz  r8, rax; Storage
0x14001413f  neg     bl
0x140014141  sbb     edx, edx
0x140014143  and     edx, 0FFFFFFECh
0x140014146  add     edx, 28h ; '('; BytesNeeded
0x140014149  call    cs:__imp_NdisGetDataBuffer
0x140014150  nop     dword ptr [rax+rax+00h]
0x140014155  cmp     byte ptr [r14+14h], 0
0x14001415a  jz      short loc_140014163
0x14001415c  xor     edi, edi
0x14001415e  mov     rsi, rax
0x140014161  jmp     short loc_140014168
0x140014163  xor     esi, esi
0x140014165  mov     rdi, rax
0x140014168  lea     rcx, g_llNotificationBlocks; Lookaside
0x14001416f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140014176  nop     dword ptr [rax+rax+00h]
0x14001417b  mov     rbx, rax
0x14001417e  test    rax, rax
0x140014181  jnz     short loc_140014196
0x140014183  mov     rcx, rbp
0x140014186  call    NetioRetreatNetBuffer
0x14001418b  mov     r14d, 0C000009Ah
0x140014191  jmp     loc_1400142B2
0x140014196  mov     dword ptr [rax+30h], 0
0x14001419d  mov     eax, [r14+20h]
0x1400141a1  mov     [rbx+34h], eax
0x1400141a4  mov     eax, [r15+168h]
0x1400141ab  mov     [rbx+38h], eax
0x1400141ae  cmp     byte ptr [r14+14h], 0
0x1400141b3  jz      short loc_1400141DD
0x1400141b5  test    rsi, rsi
0x1400141b8  jz      loc_14001428E
0x1400141be  mov     eax, [rsi+0Ch]
0x1400141c1  lea     rdi, [rbx+4Dh]
0x1400141c5  mov     [rbx+40h], eax
0x1400141c8  mov     eax, [rsi+10h]
0x1400141cb  mov     [rbx+44h], eax
0x1400141ce  movzx   eax, word ptr [rsi+2]
0x1400141d2  mov     [rbx+48h], eax
0x1400141d5  mov     al, [rsi+9]
0x1400141d8  mov     [rbx+4Ch], al
0x1400141db  jmp     short loc_14001420F
0x1400141dd  test    rdi, rdi
0x1400141e0  jz      loc_14001428E
0x1400141e6  movups  xmm0, xmmword ptr [rdi+8]
0x1400141ea  movdqu  xmmword ptr [rbx+40h], xmm0
0x1400141ef  movups  xmm1, xmmword ptr [rdi+18h]
0x1400141f3  movdqu  xmmword ptr [rbx+50h], xmm1
0x1400141f8  movzx   eax, word ptr [rdi+4]
0x1400141fc  mov     [rbx+60h], eax
0x1400141ff  mov     al, [rdi+6]
0x140014202  mov     [rbx+64h], al
0x140014205  mov     al, [rdi+7]
0x140014208  lea     rdi, [rbx+66h]
0x14001420c  mov     [rbx+65h], al
0x14001420f  test    rdi, rdi
0x140014212  jz      short loc_14001428E
0x140014214  mov     esi, [rbp+18h]
0x140014217  xor     r14d, r14d
0x14001421a  test    esi, esi
0x14001421c  jz      short loc_14001425D
0x14001421e  mov     eax, 5EAh
0x140014223  mov     [rsp+0B8h+AlignOffset], r14d; AlignOffset
0x140014228  cmp     esi, eax
0x14001422a  lea     r9d, [r14+1]; AlignMultiple
0x14001422e  mov     r8, rdi; Storage
0x140014231  mov     rcx, rbp; NetBuffer
0x140014234  cmovnb  esi, eax
0x140014237  mov     edx, esi; BytesNeeded
0x140014239  call    cs:__imp_NdisGetDataBuffer
0x140014240  nop     dword ptr [rax+rax+00h]
0x140014245  test    rax, rax
0x140014248  jz      short loc_14001425D
0x14001424a  cmp     rax, rdi
0x14001424d  jz      short loc_14001425D
0x14001424f  mov     r8d, esi; Size
0x140014252  mov     rdx, rax; Src
0x140014255  mov     rcx, rdi; void *
0x140014258  call    memmove
0x14001425d  mov     rcx, rbp
0x140014260  call    NetioRetreatNetBuffer
0x140014265  lea     rcx, [rbx+10h]; WorkItem
0x140014269  mov     edx, 1; QueueType
0x14001426e  lea     rax, WanpCompleteIrp
0x140014275  mov     [rcx+18h], rbx
0x140014279  mov     [rcx+10h], rax
0x14001427d  mov     [rcx], r14
0x140014280  call    cs:__imp_ExQueueWorkItem
0x140014287  nop     dword ptr [rax+rax+00h]
0x14001428c  jmp     short loc_1400142B2
0x14001428e  mov     rcx, rbp
0x140014291  call    NetioRetreatNetBuffer
0x140014296  mov     rdx, rbx; Entry
0x140014299  lea     rcx, g_llNotificationBlocks; Lookaside
0x1400142a0  mov     r14d, 0C000000Dh
0x1400142a6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400142ad  nop     dword ptr [rax+rax+00h]
0x1400142b2  mov     eax, r14d
0x1400142b5  mov     rcx, [rsp+0B8h+var_48]
0x1400142ba  xor     rcx, rsp; StackCookie
0x1400142bd  call    __security_check_cookie
0x1400142c2  add     rsp, 88h
0x1400142c9  pop     r15
0x1400142cb  pop     r14
0x1400142cd  pop     rdi
0x1400142ce  pop     rsi
0x1400142cf  pop     rbp
0x1400142d0  pop     rbx
0x1400142d1  retn
```
