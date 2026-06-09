# FileProvInitializeCompress

- ea: `0x14003b078`
- end: `0x14003b2da`
- name: `FileProvInitializeCompress`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a4d8`

## callees

- `0x140007a30`
- `0x1400119c0`
- `0x14003b078`
- `0x14003b2e0`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14003b0db`
- `ntoskrnl!KeQueryPriorityThread` at `0x14003b0db`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b098`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b135`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b098`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b135`
- `ntoskrnl!ObfReferenceObject` at `0x14003b101`
- `ntoskrnl!ObfReferenceObject` at `0x14003b117`
- `ntoskrnl!ObfReferenceObject` at `0x14003b101`
- `ntoskrnl!ObfReferenceObject` at `0x14003b117`
- `ntoskrnl!KeInitializeEvent` at `0x14003b207`
- `ntoskrnl!KeInitializeEvent` at `0x14003b207`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b221`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b221`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompress(__int64 a1, __int64 a2, void *a3, void *a4, __int64 *a5)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  KPRIORITY PriorityThread; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  PVOID v14; // rax
  __int64 v15; // rbx
  _DWORD *v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // eax
  PVOID PoolWithTag; // rax
  unsigned int i; // ebx
  __int64 v23; // r10
  __int64 result; // rax
  __int64 v25; // rcx

  v9 = ExAllocateFromNPagedLookasideList(&FileProvCompressContextLookaside);
  v10 = v9;
  *a5 = (__int64)v9;
  if ( !v9 )
    return 3221225626LL;
  memset(v9, 0, 0x130u);
  v10[4] = 4;
  PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
  v12 = *a5;
  *(_DWORD *)(v12 + 56) = PriorityThread;
  *(_DWORD *)(v12 + 52) = FileProvNumberProcessors;
  *(_QWORD *)(v12 + 64) = *(_QWORD *)(a2 + 24);
  ObfReferenceObject(a4);
  *(_QWORD *)(*a5 + 72) = a4;
  ObfReferenceObject(a3);
  v13 = *a5;
  *(_QWORD *)(v13 + 80) = a3;
  *(_QWORD *)(v13 + 88) = a1;
  v14 = ExAllocateFromNPagedLookasideList(&FileProvCompressWorkitemsLookaside);
  v15 = *a5;
  *(_QWORD *)(*a5 + 232) = v14;
  if ( !v14 )
    return 3221225626LL;
  memset(*(void **)(v15 + 232), 0, 136LL * (unsigned int)FileProvNumberProcessors);
  v16 = (_DWORD *)FileProvCompressionScheme(a1);
  *(_QWORD *)(v15 + 8) = v16;
  v17 = ((unsigned int)*v16 + *(_QWORD *)(a1 + 8) - 1LL) / (unsigned int)*v16 - 1;
  *(_DWORD *)(v15 + 20) = v17;
  if ( *(_DWORD *)(a1 + 12) )
    *(_DWORD *)(v15 + 16) = 8;
  v18 = *(_DWORD *)(v15 + 16);
  if ( v17 >= 0xFFDFEFFF / v18 )
    return 3221226535LL;
  v19 = (v17 * v18 + 4095) & 0xFFFFF000;
  *(_DWORD *)(v15 + 108) = v19;
  *(_DWORD *)(v15 + 104) = v19 + 0x200000;
  if ( *(__int64 *)(a1 + 8) < 0x200000 )
  {
    v20 = v19 + (-*v16 & (*v16 + *(_DWORD *)(a1 + 8) - 1));
    if ( v19 + 0x200000 > v20 )
      *(_DWORD *)(v15 + 104) = v20;
  }
  KeInitializeEvent((PRKEVENT)(v15 + 120), SynchronizationEvent, 0);
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, *(unsigned int *)(*a5 + 104), 0x44527066u);
  *(_QWORD *)(*a5 + 96) = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  for ( i = 0; ; ++i )
  {
    v23 = *a5;
    if ( i >= *(_DWORD *)(*a5 + 52) )
      break;
    result = FileProvInitializeCompressWorkItem(
               *(_QWORD *)(v23 + 8),
               *(unsigned int *)(a1 + 4),
               a2,
               *(_QWORD *)(v23 + 232) + 136LL * i);
    if ( (int)result < 0 )
      return result;
  }
  v25 = (unsigned int)(*(_DWORD *)(v23 + 16) * *(_DWORD *)(v23 + 20));
  *(_DWORD *)(v23 + 48) = v25;
  *(_QWORD *)(v23 + 24) = *(_QWORD *)(v23 + 96) + v25;
  *(_QWORD *)(v23 + 32) = 0;
  *(_QWORD *)(v23 + 40) = 0;
  *(_QWORD *)(v23 + 240) = *(_QWORD *)(v23 + 232) + 136LL * *(unsigned int *)(v23 + 248);
  return 0;
}

```

## disassembly

```asm
0x14003b078  push    rbx
0x14003b07a  push    rbp
0x14003b07b  push    rsi
0x14003b07c  push    rdi
0x14003b07d  push    r14
0x14003b07f  push    r15
0x14003b081  sub     rsp, 28h
0x14003b085  mov     rsi, rcx
0x14003b088  mov     rbp, r9
0x14003b08b  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14003b092  mov     r14, r8
0x14003b095  mov     r15, rdx
0x14003b098  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b09f  nop     dword ptr [rax+rax+00h]
0x14003b0a4  mov     rdi, [rsp+58h+arg_20]
0x14003b0ac  mov     rbx, rax
0x14003b0af  mov     [rdi], rax
0x14003b0b2  test    rax, rax
0x14003b0b5  jz      loc_14003B2C0
0x14003b0bb  xor     edx, edx; Val
0x14003b0bd  mov     r8d, 130h; Size
0x14003b0c3  mov     rcx, rax; void *
0x14003b0c6  call    memset
0x14003b0cb  mov     dword ptr [rbx+10h], 4
0x14003b0d2  mov     rcx, gs:188h; Thread
0x14003b0db  call    cs:__imp_KeQueryPriorityThread
0x14003b0e2  nop     dword ptr [rax+rax+00h]
0x14003b0e7  mov     rcx, [rdi]
0x14003b0ea  mov     [rcx+38h], eax
0x14003b0ed  mov     eax, cs:FileProvNumberProcessors
0x14003b0f3  mov     [rcx+34h], eax
0x14003b0f6  mov     rax, [r15+18h]
0x14003b0fa  mov     [rcx+40h], rax
0x14003b0fe  mov     rcx, rbp; Object
0x14003b101  call    cs:__imp_ObfReferenceObject
0x14003b108  nop     dword ptr [rax+rax+00h]
0x14003b10d  mov     rax, [rdi]
0x14003b110  mov     rcx, r14; Object
0x14003b113  mov     [rax+48h], rbp
0x14003b117  call    cs:__imp_ObfReferenceObject
0x14003b11e  nop     dword ptr [rax+rax+00h]
0x14003b123  mov     rax, [rdi]
0x14003b126  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14003b12d  mov     [rax+50h], r14
0x14003b131  mov     [rax+58h], rsi
0x14003b135  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b13c  nop     dword ptr [rax+rax+00h]
0x14003b141  mov     rbx, [rdi]
0x14003b144  mov     [rbx+0E8h], rax
0x14003b14b  test    rax, rax
0x14003b14e  jz      loc_14003B2C0
0x14003b154  mov     eax, cs:FileProvNumberProcessors
0x14003b15a  xor     edx, edx; Val
0x14003b15c  mov     rcx, [rbx+0E8h]; void *
0x14003b163  imul    r8, rax, 88h; Size
0x14003b16a  call    memset
0x14003b16f  mov     rcx, rsi
0x14003b172  call    FileProvCompressionScheme
0x14003b177  mov     [rbx+8], rax
0x14003b17b  mov     r10, rax
0x14003b17e  mov     r8d, [rax]
0x14003b181  mov     rax, [rsi+8]
0x14003b185  dec     rax
0x14003b188  add     rax, r8
0x14003b18b  cqo
0x14003b18d  idiv    r8
0x14003b190  lea     ecx, [rax-1]
0x14003b193  mov     [rbx+14h], ecx
0x14003b196  cmp     dword ptr [rsi+0Ch], 0
0x14003b19a  jnz     loc_14003B2CE
0x14003b1a0  mov     r8d, [rbx+10h]
0x14003b1a4  xor     edx, edx
0x14003b1a6  mov     eax, 0FFDFEFFFh
0x14003b1ab  div     r8d
0x14003b1ae  cmp     ecx, eax
0x14003b1b0  jnb     loc_14003B2C7
0x14003b1b6  imul    r8d, ecx
0x14003b1ba  add     r8d, 0FFFh
0x14003b1c1  and     r8d, 0FFFFF000h
0x14003b1c8  mov     [rbx+6Ch], r8d
0x14003b1cc  lea     r9d, [r8+200000h]
0x14003b1d3  mov     [rbx+68h], r9d
0x14003b1d7  cmp     qword ptr [rsi+8], 200000h
0x14003b1df  jge     short loc_14003B1FA
0x14003b1e1  mov     edx, [r10]
0x14003b1e4  mov     eax, [rsi+8]
0x14003b1e7  dec     eax
0x14003b1e9  add     eax, edx
0x14003b1eb  neg     edx
0x14003b1ed  and     eax, edx
0x14003b1ef  add     eax, r8d
0x14003b1f2  cmp     r9d, eax
0x14003b1f5  jbe     short loc_14003B1FA
0x14003b1f7  mov     [rbx+68h], eax
0x14003b1fa  xor     r8d, r8d; State
0x14003b1fd  lea     rcx, [rbx+78h]; Event
0x14003b201  lea     ebp, [r8+1]
0x14003b205  mov     edx, ebp; Type
0x14003b207  call    cs:__imp_KeInitializeEvent
0x14003b20e  nop     dword ptr [rax+rax+00h]
0x14003b213  mov     rax, [rdi]
0x14003b216  mov     r8d, 44527066h; Tag
0x14003b21c  mov     ecx, ebp; PoolType
0x14003b21e  mov     edx, [rax+68h]; NumberOfBytes
0x14003b221  call    cs:__imp_ExAllocatePoolWithTag
0x14003b228  nop     dword ptr [rax+rax+00h]
0x14003b22d  mov     rcx, [rdi]
0x14003b230  mov     [rcx+60h], rax
0x14003b234  test    rax, rax
0x14003b237  jz      loc_14003B2C0
0x14003b23d  xor     ebx, ebx
0x14003b23f  mov     r10, [rdi]
0x14003b242  cmp     ebx, [r10+34h]
0x14003b246  jnb     short loc_14003B26F
0x14003b248  mov     edx, [rsi+4]
0x14003b24b  mov     r8, r15
0x14003b24e  mov     rcx, [r10+8]
0x14003b252  mov     eax, ebx
0x14003b254  imul    r9, rax, 88h
0x14003b25b  add     r9, [r10+0E8h]
0x14003b262  call    FileProvInitializeCompressWorkItem
0x14003b267  test    eax, eax
0x14003b269  js      short loc_14003B2B2
0x14003b26b  add     ebx, ebp
0x14003b26d  jmp     short loc_14003B23F
0x14003b26f  mov     ecx, [r10+14h]
0x14003b273  imul    ecx, [r10+10h]
0x14003b278  mov     [r10+30h], ecx
0x14003b27c  add     rcx, [r10+60h]
0x14003b280  mov     [r10+18h], rcx
0x14003b284  mov     qword ptr [r10+20h], 0
0x14003b28c  mov     qword ptr [r10+28h], 0
0x14003b294  mov     eax, [r10+0F8h]
0x14003b29b  imul    rcx, rax, 88h
0x14003b2a2  add     rcx, [r10+0E8h]
0x14003b2a9  mov     [r10+0F0h], rcx
0x14003b2b0  xor     eax, eax
0x14003b2b2  add     rsp, 28h
0x14003b2b6  pop     r15
0x14003b2b8  pop     r14
0x14003b2ba  pop     rdi
0x14003b2bb  pop     rsi
0x14003b2bc  pop     rbp
0x14003b2bd  pop     rbx
0x14003b2be  retn
0x14003b2c0  mov     eax, 0C000009Ah
0x14003b2c5  jmp     short loc_14003B2B2
0x14003b2c7  mov     eax, 0C0000427h
0x14003b2cc  jmp     short loc_14003B2B2
0x14003b2ce  mov     dword ptr [rbx+10h], 8
0x14003b2d5  jmp     loc_14003B1A0
```
