# CreateNewEventEntry

- ea: `0x14000f714`
- end: `0x14000f941`
- name: `CreateNewEventEntry`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009d88`

## callees

- `0x14000f6e0`
- `0x14000f714`
- `0x1400116c0`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f7c1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f7c1`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(
        char a1,
        __int128 *a2,
        unsigned __int8 a3,
        __int64 a4,
        char a5,
        int a6,
        __int64 *a7)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  __int64 v11; // r8
  __int64 v12; // r10
  unsigned __int8 v13; // r11
  __int64 v14; // rcx
  __int64 v15; // rax
  SIZE_T v17; // rsi
  PVOID PoolWithTag; // rax
  PVOID v19; // rdi
  __int64 NextOffset; // r13
  unsigned __int8 v21; // r15
  unsigned __int8 v22; // si
  unsigned int v23; // edx
  void *v24; // rbx
  __int64 v25; // rsi
  unsigned __int8 v26; // r13
  __int128 v27; // xmm0
  __int64 v28; // r14
  __int64 v29; // rdi
  unsigned int v30; // edx
  void *v31; // rbx
  _QWORD v32[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = 0;
  v8 = a3;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  *a7 = 0;
  if ( (_BYTE)v8 )
  {
    do
    {
      v14 = *(unsigned int *)(a4 + 16LL * v13 + 8);
      if ( v13 >= 2u )
        v12 += v14;
      v15 = v14 + v11;
      if ( v13 >= 2u )
        v15 = v11;
      ++v13;
      v11 = v15;
    }
    while ( v13 < (unsigned __int8)v8 );
    if ( (unsigned __int64)(v12 + v15) > 0xFFFF )
      return 3221225621LL;
  }
  v17 = v12 + 16 * v8 + 46;
  if ( !v17 )
    return 3221225495LL;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), v17, 0x47417254u);
  v19 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memset(PoolWithTag, 0, v17);
  v32[0] = v19;
  v32[1] = v17;
  NextOffset = CBufferGetNextOffset(v32, 16 * v8);
  v21 = a5 + 2;
  v22 = 0;
  if ( a5 != -2 )
  {
    do
    {
      if ( v22 >= 2u )
      {
        v24 = (void *)CBufferGetNextOffset(v32, *(unsigned int *)(a4 + 16 * v7 + 8));
        memmove(v24, *(const void **)(a4 + 16 * v7), v23);
        *(_QWORD *)(NextOffset + 16 * v7) = v24;
        *(_DWORD *)(NextOffset + 16 * v7 + 12) = *(_DWORD *)(a4 + 16 * v7 + 12);
        *(_DWORD *)(NextOffset + 16 * v7 + 8) = *(_DWORD *)(a4 + 16 * v7 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v7) = *(_OWORD *)(a4 + 16 * v7);
      }
      ++v22;
      ++v7;
    }
    while ( v22 < v21 );
  }
  v25 = CBufferGetNextOffset(v32, 46);
  *(_QWORD *)(v25 + 16) = NextOffset;
  v26 = a5 + 2;
  v27 = *a2;
  *(_BYTE *)(v25 + 44) = v8;
  *(_BYTE *)(v25 + 45) = a5;
  *(_DWORD *)(v25 + 40) = a6;
  *(_OWORD *)v25 = v27;
  if ( (unsigned __int8)(a5 + 2) < (unsigned __int8)v8 )
  {
    v28 = v21;
    do
    {
      v29 = 2 * v28;
      v31 = (void *)CBufferGetNextOffset(v32, *(unsigned int *)(a4 + 16 * v28 + 8));
      memmove(v31, *(const void **)(a4 + 16 * v28), v30);
      ++v26;
      ++v28;
      *(_QWORD *)(*(_QWORD *)(v25 + 16) + 8 * v29) = v31;
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v29 + 12) = *(_DWORD *)(a4 + 8 * v29 + 12);
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v29 + 8) = *(_DWORD *)(a4 + 8 * v29 + 8);
    }
    while ( v26 < (unsigned __int8)v8 );
  }
  *a7 = v25;
  return 0;
}

```

## disassembly

```asm
0x14000f714  mov     [rsp+arg_0], rbx
0x14000f719  mov     [rsp+arg_8], rdx
0x14000f71e  push    rbp
0x14000f71f  push    rsi
0x14000f720  push    rdi
0x14000f721  push    r12
0x14000f723  push    r13
0x14000f725  push    r14
0x14000f727  push    r15
0x14000f729  sub     rsp, 30h
0x14000f72d  mov     rax, [rsp+68h+arg_30]
0x14000f735  xor     r14d, r14d
0x14000f738  movzx   ebp, r8b
0x14000f73c  mov     r12, r9
0x14000f73f  mov     r9b, cl
0x14000f742  mov     r8d, r14d
0x14000f745  mov     r10d, r14d
0x14000f748  mov     r11b, r14b
0x14000f74b  mov     [rax], r14
0x14000f74e  test    bpl, bpl
0x14000f751  jz      short loc_14000F793
0x14000f753  movzx   eax, r11b
0x14000f757  add     rax, rax
0x14000f75a  cmp     r11b, 2
0x14000f75e  mov     ecx, [r12+rax*8+8]
0x14000f763  lea     rax, [rcx+r10]
0x14000f767  cmovnb  r10, rax
0x14000f76b  lea     rax, [rcx+r8]
0x14000f76f  cmovnb  rax, r8
0x14000f773  inc     r11b
0x14000f776  mov     r8, rax
0x14000f779  cmp     r11b, bpl
0x14000f77c  jb      short loc_14000F753
0x14000f77e  add     rax, r10
0x14000f781  cmp     rax, 0FFFFh
0x14000f787  jbe     short loc_14000F793
0x14000f789  mov     eax, 0C0000095h
0x14000f78e  jmp     loc_14000F92B
0x14000f793  mov     rbx, rbp
0x14000f796  shl     rbx, 4
0x14000f79a  lea     rsi, [rbx+2Eh]
0x14000f79e  add     rsi, r10
0x14000f7a1  jz      loc_14000F926
0x14000f7a7  neg     r9b
0x14000f7aa  mov     r8d, 47417254h; Tag
0x14000f7b0  mov     rdx, rsi; NumberOfBytes
0x14000f7b3  sbb     ecx, ecx
0x14000f7b5  and     ecx, 0FFFFFE01h
0x14000f7bb  add     ecx, 200h; PoolType
0x14000f7c1  call    cs:__imp_ExAllocatePoolWithTag
0x14000f7c8  nop     dword ptr [rax+rax+00h]
0x14000f7cd  mov     rdi, rax
0x14000f7d0  test    rax, rax
0x14000f7d3  jz      loc_14000F926
0x14000f7d9  mov     r8, rsi; Size
0x14000f7dc  xor     edx, edx; Val
0x14000f7de  mov     rcx, rax; void *
0x14000f7e1  call    memset
0x14000f7e6  mov     rdx, rbx
0x14000f7e9  mov     [rsp+68h+var_48], rdi
0x14000f7ee  lea     rcx, [rsp+68h+var_48]
0x14000f7f3  mov     [rsp+68h+var_40], rsi
0x14000f7f8  call    CBufferGetNextOffset
0x14000f7fd  mov     r15b, [rsp+68h+arg_20]
0x14000f805  mov     r13, rax
0x14000f808  add     r15b, 2
0x14000f80c  mov     sil, r14b
0x14000f80f  mov     byte ptr [rsp+68h+arg_10], r15b
0x14000f817  jz      short loc_14000F878
0x14000f819  mov     rdi, r14
0x14000f81c  add     rdi, rdi
0x14000f81f  cmp     sil, 2
0x14000f823  jnb     short loc_14000F833
0x14000f825  movups  xmm0, xmmword ptr [r12+rdi*8]
0x14000f82a  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x14000f831  jmp     short loc_14000F86D
0x14000f833  mov     edx, [r12+rdi*8+8]
0x14000f838  lea     rcx, [rsp+68h+var_48]
0x14000f83d  call    CBufferGetNextOffset
0x14000f842  mov     r8d, edx; Size
0x14000f845  mov     rcx, rax; void *
0x14000f848  mov     rdx, [r12+rdi*8]; Src
0x14000f84c  mov     rbx, rax
0x14000f84f  call    memmove
0x14000f854  mov     [r13+rdi*8+0], rbx
0x14000f859  mov     eax, [r12+rdi*8+0Ch]
0x14000f85e  mov     [r13+rdi*8+0Ch], eax
0x14000f863  mov     eax, [r12+rdi*8+8]
0x14000f868  mov     [r13+rdi*8+8], eax
0x14000f86d  inc     sil
0x14000f870  inc     r14
0x14000f873  cmp     sil, r15b
0x14000f876  jb      short loc_14000F819
0x14000f878  mov     edx, 2Eh ; '.'
0x14000f87d  lea     rcx, [rsp+68h+var_48]
0x14000f882  call    CBufferGetNextOffset
0x14000f887  mov     ecx, [rsp+68h+arg_28]
0x14000f88e  mov     rsi, rax
0x14000f891  mov     [rax+10h], r13
0x14000f895  mov     rax, [rsp+68h+arg_8]
0x14000f89a  mov     r13d, [rsp+68h+arg_10]
0x14000f8a2  movups  xmm0, xmmword ptr [rax]
0x14000f8a5  mov     al, [rsp+68h+arg_20]
0x14000f8ac  mov     [rsi+2Ch], bpl
0x14000f8b0  mov     [rsi+2Dh], al
0x14000f8b3  mov     [rsi+28h], ecx
0x14000f8b6  movdqu  xmmword ptr [rsi], xmm0
0x14000f8ba  cmp     r13b, bpl
0x14000f8bd  jnb     short loc_14000F917
0x14000f8bf  movzx   r14d, r15b
0x14000f8c3  mov     rdi, r14
0x14000f8c6  lea     rcx, [rsp+68h+var_48]
0x14000f8cb  add     rdi, rdi
0x14000f8ce  mov     edx, [r12+rdi*8+8]
0x14000f8d3  call    CBufferGetNextOffset
0x14000f8d8  mov     r8d, edx; Size
0x14000f8db  mov     rcx, rax; void *
0x14000f8de  mov     rdx, [r12+rdi*8]; Src
0x14000f8e2  mov     rbx, rax
0x14000f8e5  call    memmove
0x14000f8ea  mov     rcx, [rsi+10h]
0x14000f8ee  inc     r13b
0x14000f8f1  inc     r14
0x14000f8f4  mov     [rcx+rdi*8], rbx
0x14000f8f8  mov     rcx, [rsi+10h]
0x14000f8fc  mov     eax, [r12+rdi*8+0Ch]
0x14000f901  mov     [rcx+rdi*8+0Ch], eax
0x14000f905  mov     rcx, [rsi+10h]
0x14000f909  mov     eax, [r12+rdi*8+8]
0x14000f90e  mov     [rcx+rdi*8+8], eax
0x14000f912  cmp     r13b, bpl
0x14000f915  jb      short loc_14000F8C3
0x14000f917  mov     rax, [rsp+68h+arg_30]
0x14000f91f  mov     [rax], rsi
0x14000f922  xor     eax, eax
0x14000f924  jmp     short loc_14000F92B
0x14000f926  mov     eax, 0C0000017h
0x14000f92b  mov     rbx, [rsp+68h+arg_0]
0x14000f930  add     rsp, 30h
0x14000f934  pop     r15
0x14000f936  pop     r14
0x14000f938  pop     r13
0x14000f93a  pop     r12
0x14000f93c  pop     rdi
0x14000f93d  pop     rsi
0x14000f93e  pop     rbp
0x14000f93f  retn
```
