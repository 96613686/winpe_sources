# CreateNewEventEntry

- ea: `0x140007234`
- end: `0x140007455`
- name: `CreateNewEventEntry`
- size: `545`
- prototype: `__int64 __fastcall(char, __int128 *, __int64, __int64, char, int, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400076a8`

## callees

- `0x140007200`
- `0x140007234`
- `0x140007dc0`
- `0x1400080c0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400072da`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400072da`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(char a1, __int128 *a2, __int64 a3, __int64 a4, char a5, int a6, __int64 *a7)
{
  __int64 v7; // rbp
  __int64 v9; // r11
  __int64 v11; // r8
  unsigned __int8 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rax
  SIZE_T v16; // rdi
  PVOID PoolWithTag; // rax
  PVOID v18; // rbx
  __int64 NextOffset; // r12
  unsigned __int8 v20; // r14
  unsigned __int8 v21; // si
  unsigned int v22; // edx
  void *v23; // rbx
  __int64 v24; // rsi
  unsigned __int8 v25; // r12
  __int128 v26; // xmm0
  __int64 v27; // rbp
  __int64 v28; // rdi
  unsigned int v29; // edx
  void *v30; // rbx
  _QWORD v31[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  *a7 = 0;
  do
  {
    v13 = *(unsigned int *)(a4 + 16LL * v12 + 8);
    if ( v12 >= 2u )
      v11 += v13;
    v14 = v13 + v9;
    if ( v12 >= 2u )
      v14 = v9;
    ++v12;
    v9 = v14;
  }
  while ( v12 < 0xBu );
  if ( (unsigned __int64)(v11 + v14) > 0xFFFF )
    return 3221225621LL;
  v16 = v11 + 222;
  if ( v11 == -222 )
    return 3221225495LL;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), v16, 0x47417254u);
  v18 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memset(PoolWithTag, 0, v16);
  v31[0] = v18;
  v31[1] = v16;
  NextOffset = CBufferGetNextOffset(v31, 176);
  v20 = a5 + 2;
  v21 = 0;
  if ( a5 != -2 )
  {
    do
    {
      if ( v21 >= 2u )
      {
        v23 = (void *)CBufferGetNextOffset(v31, *(unsigned int *)(a4 + 16 * v7 + 8));
        memmove(v23, *(const void **)(a4 + 16 * v7), v22);
        *(_QWORD *)(NextOffset + 16 * v7) = v23;
        *(_DWORD *)(NextOffset + 16 * v7 + 12) = *(_DWORD *)(a4 + 16 * v7 + 12);
        *(_DWORD *)(NextOffset + 16 * v7 + 8) = *(_DWORD *)(a4 + 16 * v7 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v7) = *(_OWORD *)(a4 + 16 * v7);
      }
      ++v21;
      ++v7;
    }
    while ( v21 < v20 );
  }
  v24 = CBufferGetNextOffset(v31, 46);
  *(_QWORD *)(v24 + 16) = NextOffset;
  v25 = a5 + 2;
  v26 = *a2;
  *(_BYTE *)(v24 + 44) = 11;
  *(_BYTE *)(v24 + 45) = a5;
  *(_DWORD *)(v24 + 40) = a6;
  *(_OWORD *)v24 = v26;
  if ( (unsigned __int8)(a5 + 2) < 0xBu )
  {
    v27 = v20;
    do
    {
      v28 = 2 * v27;
      v30 = (void *)CBufferGetNextOffset(v31, *(unsigned int *)(a4 + 16 * v27 + 8));
      memmove(v30, *(const void **)(a4 + 16 * v27), v29);
      ++v25;
      ++v27;
      *(_QWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28) = v30;
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28 + 12) = *(_DWORD *)(a4 + 8 * v28 + 12);
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28 + 8) = *(_DWORD *)(a4 + 8 * v28 + 8);
    }
    while ( v25 < 0xBu );
  }
  *a7 = v24;
  return 0;
}

```

## disassembly

```asm
0x140007234  mov     [rsp+arg_0], rbx
0x140007239  mov     byte ptr [rsp+arg_10], r8b
0x14000723e  mov     [rsp+arg_8], rdx
0x140007243  push    rbp
0x140007244  push    rsi
0x140007245  push    rdi
0x140007246  push    r12
0x140007248  push    r13
0x14000724a  push    r14
0x14000724c  push    r15
0x14000724e  sub     rsp, 30h
0x140007252  mov     r13, [rsp+68h+arg_30]
0x14000725a  xor     ebp, ebp
0x14000725c  mov     r15, r9
0x14000725f  mov     r11d, ebp
0x140007262  mov     r9b, cl
0x140007265  mov     r8d, ebp
0x140007268  mov     r10b, bpl
0x14000726b  mov     [r13+0], rbp
0x14000726f  movzx   eax, r10b
0x140007273  add     rax, rax
0x140007276  cmp     r10b, 2
0x14000727a  mov     ecx, [r15+rax*8+8]
0x14000727f  lea     rax, [rcx+r8]
0x140007283  cmovnb  r8, rax
0x140007287  lea     rax, [rcx+r11]
0x14000728b  cmovnb  rax, r11
0x14000728f  inc     r10b
0x140007292  mov     r11, rax
0x140007295  cmp     r10b, 0Bh
0x140007299  jb      short loc_14000726F
0x14000729b  add     rax, r8
0x14000729e  cmp     rax, 0FFFFh
0x1400072a4  jbe     short loc_1400072B0
0x1400072a6  mov     eax, 0C0000095h
0x1400072ab  jmp     loc_14000743F
0x1400072b0  lea     rdi, [r8+0DEh]
0x1400072b7  test    rdi, rdi
0x1400072ba  jz      loc_14000743A
0x1400072c0  neg     r9b
0x1400072c3  mov     r8d, 47417254h; Tag
0x1400072c9  mov     rdx, rdi; NumberOfBytes
0x1400072cc  sbb     ecx, ecx
0x1400072ce  and     ecx, 0FFFFFE01h
0x1400072d4  add     ecx, 200h; PoolType
0x1400072da  call    cs:__imp_ExAllocatePoolWithTag
0x1400072e1  nop     dword ptr [rax+rax+00h]
0x1400072e6  mov     rbx, rax
0x1400072e9  test    rax, rax
0x1400072ec  jz      loc_14000743A
0x1400072f2  mov     r8, rdi; Size
0x1400072f5  xor     edx, edx; Val
0x1400072f7  mov     rcx, rax; void *
0x1400072fa  call    memset
0x1400072ff  mov     edx, 0B0h
0x140007304  mov     [rsp+68h+var_48], rbx
0x140007309  lea     rcx, [rsp+68h+var_48]
0x14000730e  mov     [rsp+68h+var_40], rdi
0x140007313  call    CBufferGetNextOffset
0x140007318  mov     r14b, [rsp+68h+arg_20]
0x140007320  mov     r12, rax
0x140007323  add     r14b, 2
0x140007327  mov     sil, bpl
0x14000732a  mov     byte ptr [rsp+68h+arg_10], r14b
0x140007332  jz      short loc_140007391
0x140007334  mov     rdi, rbp
0x140007337  add     rdi, rdi
0x14000733a  cmp     sil, 2
0x14000733e  jnb     short loc_14000734D
0x140007340  movups  xmm0, xmmword ptr [r15+rdi*8]
0x140007345  movdqu  xmmword ptr [r12+rdi*8], xmm0
0x14000734b  jmp     short loc_140007386
0x14000734d  mov     edx, [r15+rdi*8+8]
0x140007352  lea     rcx, [rsp+68h+var_48]
0x140007357  call    CBufferGetNextOffset
0x14000735c  mov     r8d, edx; Size
0x14000735f  mov     rcx, rax; void *
0x140007362  mov     rdx, [r15+rdi*8]; Src
0x140007366  mov     rbx, rax
0x140007369  call    memmove
0x14000736e  mov     [r12+rdi*8], rbx
0x140007372  mov     eax, [r15+rdi*8+0Ch]
0x140007377  mov     [r12+rdi*8+0Ch], eax
0x14000737c  mov     eax, [r15+rdi*8+8]
0x140007381  mov     [r12+rdi*8+8], eax
0x140007386  inc     sil
0x140007389  inc     rbp
0x14000738c  cmp     sil, r14b
0x14000738f  jb      short loc_140007334
0x140007391  mov     edx, 2Eh ; '.'
0x140007396  lea     rcx, [rsp+68h+var_48]
0x14000739b  call    CBufferGetNextOffset
0x1400073a0  mov     ecx, [rsp+68h+arg_28]
0x1400073a7  mov     rsi, rax
0x1400073aa  mov     [rax+10h], r12
0x1400073ae  mov     rax, [rsp+68h+arg_8]
0x1400073b3  mov     r12d, [rsp+68h+arg_10]
0x1400073bb  movups  xmm0, xmmword ptr [rax]
0x1400073be  mov     al, [rsp+68h+arg_20]
0x1400073c5  mov     byte ptr [rsi+2Ch], 0Bh
0x1400073c9  mov     [rsi+2Dh], al
0x1400073cc  mov     [rsi+28h], ecx
0x1400073cf  movdqu  xmmword ptr [rsi], xmm0
0x1400073d3  cmp     r12b, 0Bh
0x1400073d7  jnb     short loc_140007432
0x1400073d9  movzx   ebp, r14b
0x1400073dd  mov     rdi, rbp
0x1400073e0  lea     rcx, [rsp+68h+var_48]
0x1400073e5  add     rdi, rdi
0x1400073e8  mov     edx, [r15+rdi*8+8]
0x1400073ed  call    CBufferGetNextOffset
0x1400073f2  mov     r8d, edx; Size
0x1400073f5  mov     rcx, rax; void *
0x1400073f8  mov     rdx, [r15+rdi*8]; Src
0x1400073fc  mov     rbx, rax
0x1400073ff  call    memmove
0x140007404  mov     rcx, [rsi+10h]
0x140007408  inc     r12b
0x14000740b  inc     rbp
0x14000740e  mov     [rcx+rdi*8], rbx
0x140007412  mov     rcx, [rsi+10h]
0x140007416  mov     eax, [r15+rdi*8+0Ch]
0x14000741b  mov     [rcx+rdi*8+0Ch], eax
0x14000741f  mov     rcx, [rsi+10h]
0x140007423  mov     eax, [r15+rdi*8+8]
0x140007428  mov     [rcx+rdi*8+8], eax
0x14000742c  cmp     r12b, 0Bh
0x140007430  jb      short loc_1400073DD
0x140007432  mov     [r13+0], rsi
0x140007436  xor     eax, eax
0x140007438  jmp     short loc_14000743F
0x14000743a  mov     eax, 0C0000017h
0x14000743f  mov     rbx, [rsp+68h+arg_0]
0x140007444  add     rsp, 30h
0x140007448  pop     r15
0x14000744a  pop     r14
0x14000744c  pop     r13
0x14000744e  pop     r12
0x140007450  pop     rdi
0x140007451  pop     rsi
0x140007452  pop     rbp
0x140007453  retn
```
