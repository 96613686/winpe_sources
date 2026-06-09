# SVSThreadPool::PutOnWorkerQueue(ulong (*)(void *),void *,__int64)

- ea: `0x1800074a8`
- end: `0x1800077a3`
- name: `?PutOnWorkerQueue@SVSThreadPool@@IEAAKP6AKPEAX@Z0_J@Z`
- size: `763`
- prototype: `unsigned int __fastcall(SVSThreadPool *__hidden this, unsigned int (*)(void *), void *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180002550`
- `0x180007230`

## callees

- `0x180006168`
- `0x1800074a8`
- `0x1800077ac`
- `0x180026f20`
- `0x18003ae80`
- `0x18004f304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800075c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800075c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007783`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007795`

## pseudocode

```c
__int64 __fastcall SVSThreadPool::PutOnWorkerQueue(
        SVSThreadPool *this,
        unsigned int (*a2)(void *),
        void *a3,
        __int64 a4)
{
  __int64 Fixed; // rax
  __int64 v7; // r15
  __int64 v8; // rbx
  int v9; // esi
  int v10; // ebp
  bool v11; // cc
  int v12; // r9d
  __int64 v13; // r12
  unsigned int v14; // r10d
  __int64 j; // rax
  __int64 v16; // rdx
  __int64 *v17; // r8
  __int64 k; // rax
  __int64 *v19; // rdx
  __int64 v21; // rax
  _QWORD *v22; // r14
  __int64 v23; // rcx
  int v24; // edx
  __int64 v25; // rdx
  void *v26; // rax
  int v27; // r14d
  int i; // edx
  unsigned int v29; // r10d
  unsigned int v30; // r9d
  __int128 v31; // xmm0
  _OWORD *v32; // rax
  int v33; // r10d
  HANDLE Thread; // rax

  Fixed = svsutil_GetFixed(*((_QWORD *)this + 8), a2, a3);
  v7 = Fixed;
  if ( !Fixed )
    return 0;
  *(_QWORD *)(Fixed + 8) = 0;
  *(_QWORD *)Fixed = RemoveUnusedISAPIs;
  *(_DWORD *)(Fixed + 16) = ++*((_DWORD *)this + 26);
  v8 = *((_QWORD *)this + 2);
  if ( !v8 )
    return 0;
  v9 = ((*((_DWORD *)this + 2) + 1) >> 11) + 1;
  if ( v9 >= *(_DWORD *)v8 )
  {
    v10 = (((*((_DWORD *)this + 2) + 1) >> 5) & 0x3F) + 1;
    v11 = v9 <= *(_DWORD *)v8;
    if ( v9 != *(_DWORD *)v8 )
      goto LABEL_5;
    if ( v10 > *(_DWORD *)(v8 + 4) )
    {
      v11 = v9 <= *(_DWORD *)v8;
LABEL_5:
      if ( v11 )
      {
        while ( *(_DWORD *)(v8 + 4) < v10 )
        {
          if ( !(unsigned int)SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(*(_QWORD *)(v8 + 8)) )
            return 0;
          ++*(_DWORD *)(v8 + 4);
        }
      }
      else
      {
        if ( !*(_QWORD *)(v8 + 8) )
          goto LABEL_29;
        while ( *(int *)(v8 + 4) < 64 )
        {
          if ( !(unsigned int)SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(*(_QWORD *)(v8 + 8)) )
            return 0;
          ++*(_DWORD *)(v8 + 4);
        }
LABEL_29:
        while ( *(_DWORD *)v8 < v9 )
        {
          v21 = svsutil_Alloc(24, g_pvAllocData);
          v22 = (_QWORD *)v21;
          if ( !v21 )
            return 0;
          v23 = *(_QWORD *)(v8 + 8);
          v24 = *(_DWORD *)v8 << 11;
          *(_DWORD *)(v21 + 8) = v24;
          *(_DWORD *)(v21 + 12) = v24 | 0x7FF;
          v25 = g_pvAllocData;
          *(_QWORD *)(v21 + 16) = v23;
          *(_QWORD *)v21 = 0;
          v26 = (void *)svsutil_Alloc(512, v25);
          *v22 = v26;
          if ( !v26 )
            return 0;
          memset_0(v26, 0, 0x200u);
          v11 = ++*(_DWORD *)v8 < v9;
          *(_QWORD *)(v8 + 8) = v22;
          v27 = v10;
          if ( v11 )
            v27 = 64;
          *(_DWORD *)(v8 + 4) = 0;
          for ( i = 0; i < v27; i = *(_DWORD *)(v8 + 4) )
          {
            if ( !(unsigned int)SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(*(_QWORD *)(v8 + 8)) )
              return 0;
            ++*(_DWORD *)(v8 + 4);
          }
        }
      }
    }
  }
  v12 = *((_DWORD *)this + 2);
  v13 = ~a4;
  *((_DWORD *)this + 2) = v12 + 1;
  if ( v12 > 0 )
  {
    do
    {
      if ( *(_QWORD *)SVSExpArray<SVSTHeapEntry<__int64>>::operator[](
                        *((_QWORD *)this + 2),
                        (unsigned int)((v12 - 1) / 2)) >= v13 )
        break;
      v31 = *(_OWORD *)SVSExpArray<SVSTHeapEntry<__int64>>::operator[](*((_QWORD *)this + 2), v29);
      v32 = (_OWORD *)SVSExpArray<SVSTHeapEntry<__int64>>::operator[](*((_QWORD *)this + 2), v30);
      v12 = v33;
      *v32 = v31;
    }
    while ( v33 > 0 );
  }
  v14 = v12 & 0xFFFFF800;
  for ( j = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL); j; j = *(_QWORD *)(j + 16) )
  {
    if ( *(_DWORD *)(j + 8) == v14 )
    {
      v16 = v12;
      v17 = (__int64 *)(*(_QWORD *)(*(_QWORD *)j + 8LL * ((v12 >> 5) & 0x3F)) + 16LL * (v12 & 0x1F));
      goto LABEL_12;
    }
  }
  v17 = `SVSExpArray<SVSTHeapEntry<__int64>>::operator[]'::`2'::dummy;
  v16 = v12;
LABEL_12:
  *v17 = v13;
  for ( k = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL); k; k = *(_QWORD *)(k + 16) )
  {
    if ( *(_DWORD *)(k + 8) == v14 )
    {
      v19 = (__int64 *)(*(_QWORD *)(*(_QWORD *)k + 8 * ((v16 >> 5) & 0x3F)) + 16 * (v16 & 0x1F));
      goto LABEL_16;
    }
  }
  v19 = `SVSExpArray<SVSTHeapEntry<__int64>>::operator[]'::`2'::dummy;
LABEL_16:
  v19[1] = v7;
  if ( !*((_DWORD *)this + 24) && !*((_DWORD *)this + 25) )
  {
    Thread = CreateThread(0, 0, SVSThreadPool::SVSThreadPoolWorkerThread, this, 0, 0);
    if ( Thread )
    {
      CloseHandle(Thread);
      ++*((_DWORD *)this + 25);
    }
  }
  SetEvent(*((HANDLE *)this + 10));
  return *(unsigned int *)(v7 + 16);
}

```

## disassembly

```asm
0x1800074a8  push    rbx
0x1800074aa  push    rbp
0x1800074ab  push    rsi
0x1800074ac  push    rdi
0x1800074ad  push    r12
0x1800074af  push    r14
0x1800074b1  push    r15
0x1800074b3  sub     rsp, 30h
0x1800074b7  mov     rdi, rcx
0x1800074ba  mov     r12, r9
0x1800074bd  mov     rcx, [rcx+40h]
0x1800074c1  call    svsutil_GetFixed
0x1800074c6  mov     r15, rax
0x1800074c9  test    rax, rax
0x1800074cc  jz      loc_1800075F0
0x1800074d2  mov     qword ptr [r15+8], 0
0x1800074da  lea     rax, ?RemoveUnusedISAPIs@@YAKPEAX@Z; RemoveUnusedISAPIs(void *)
0x1800074e1  mov     [r15], rax
0x1800074e4  inc     dword ptr [rdi+68h]
0x1800074e7  mov     eax, [rdi+68h]
0x1800074ea  mov     [r15+10h], eax
0x1800074ee  mov     rbx, [rdi+10h]
0x1800074f2  test    rbx, rbx
0x1800074f5  jz      loc_1800075F0
0x1800074fb  mov     ebp, [rdi+8]
0x1800074fe  inc     ebp
0x180007500  mov     esi, ebp
0x180007502  sar     esi, 0Bh
0x180007505  inc     esi
0x180007507  cmp     esi, [rbx]
0x180007509  jl      short loc_18000752C
0x18000750b  sar     ebp, 5
0x18000750e  and     ebp, 3Fh
0x180007511  inc     ebp
0x180007513  cmp     esi, [rbx]
0x180007515  jz      loc_1800075E0
0x18000751b  jg      loc_18000761B
0x180007521  mov     edx, [rbx+4]
0x180007524  cmp     edx, ebp
0x180007526  jl      loc_1800076F2
0x18000752c  mov     r9d, [rdi+8]
0x180007530  not     r12
0x180007533  lea     eax, [r9+1]
0x180007537  mov     [rdi+8], eax
0x18000753a  test    r9d, r9d
0x18000753d  jg      loc_18000770B
0x180007543  mov     rax, [rdi+10h]
0x180007547  mov     r10d, r9d
0x18000754a  and     r10d, 0FFFFF800h
0x180007551  mov     rax, [rax+8]
0x180007555  test    rax, rax
0x180007558  jz      loc_180007603
0x18000755e  cmp     [rax+8], r10d
0x180007562  jnz     loc_1800075F4
0x180007568  mov     rax, [rax]
0x18000756b  movsxd  rdx, r9d
0x18000756e  mov     r8, rdx
0x180007571  mov     rcx, rdx
0x180007574  sar     rcx, 5
0x180007578  and     r8d, 1Fh
0x18000757c  and     ecx, 3Fh
0x18000757f  shl     r8, 4
0x180007583  add     r8, [rax+rcx*8]
0x180007587  mov     [r8], r12
0x18000758a  mov     rax, [rdi+10h]
0x18000758e  mov     rax, [rax+8]
0x180007592  test    rax, rax
0x180007595  jz      short loc_180007612
0x180007597  cmp     [rax+8], r10d
0x18000759b  jnz     short loc_1800075FD
0x18000759d  mov     rax, [rax]
0x1800075a0  mov     rcx, rdx
0x1800075a3  sar     rcx, 5
0x1800075a7  and     edx, 1Fh
0x1800075aa  and     ecx, 3Fh
0x1800075ad  shl     rdx, 4
0x1800075b1  add     rdx, [rax+rcx*8]
0x1800075b5  mov     [rdx+8], r15
0x1800075b9  cmp     dword ptr [rdi+60h], 0
0x1800075bd  jz      loc_18000775A
0x1800075c3  mov     rcx, [rdi+50h]; hEvent
0x1800075c7  call    cs:__imp_SetEvent
0x1800075cd  mov     eax, [r15+10h]
0x1800075d1  add     rsp, 30h
0x1800075d5  pop     r15
0x1800075d7  pop     r14
0x1800075d9  pop     r12
0x1800075db  pop     rdi
0x1800075dc  pop     rsi
0x1800075dd  pop     rbp
0x1800075de  pop     rbx
0x1800075df  retn
0x1800075e0  cmp     ebp, [rbx+4]
0x1800075e3  jle     loc_18000752C
0x1800075e9  cmp     esi, [rbx]
0x1800075eb  jmp     loc_18000751B
0x1800075f0  xor     eax, eax
0x1800075f2  jmp     short loc_1800075D1
0x1800075f4  mov     rax, [rax+10h]
0x1800075f8  jmp     loc_180007555
0x1800075fd  mov     rax, [rax+10h]
0x180007601  jmp     short loc_180007592
0x180007603  lea     r8, ?dummy@?1???A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z@4U2@A; SVSTHeapEntry<__int64> `SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)'::`2'::dummy
0x18000760a  movsxd  rdx, r9d
0x18000760d  jmp     loc_180007587
0x180007612  lea     rdx, ?dummy@?1???A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z@4U2@A; SVSTHeapEntry<__int64> `SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)'::`2'::dummy
0x180007619  jmp     short loc_1800075B5
0x18000761b  cmp     qword ptr [rbx+8], 0
0x180007620  mov     eax, 40h ; '@'
0x180007625  jz      short loc_180007645
0x180007627  mov     edx, [rbx+4]
0x18000762a  cmp     edx, eax
0x18000762c  jge     short loc_180007645
0x18000762e  mov     rcx, [rbx+8]
0x180007632  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x180007637  test    eax, eax
0x180007639  jz      short loc_1800075F0
0x18000763b  inc     dword ptr [rbx+4]
0x18000763e  mov     eax, 40h ; '@'
0x180007643  jmp     short loc_180007627
0x180007645  cmp     [rbx], esi
0x180007647  jge     loc_18000752C
0x18000764d  mov     rdx, cs:g_pvAllocData
0x180007654  mov     ecx, 18h
0x180007659  call    svsutil_Alloc
0x18000765e  mov     r14, rax
0x180007661  test    rax, rax
0x180007664  jz      short loc_1800075F0
0x180007666  mov     edx, [rbx]
0x180007668  mov     rcx, [rbx+8]
0x18000766c  shl     edx, 0Bh
0x18000766f  mov     [rax+8], edx
0x180007672  or      edx, 7FFh
0x180007678  mov     [rax+0Ch], edx
0x18000767b  mov     rdx, cs:g_pvAllocData
0x180007682  mov     [rax+10h], rcx
0x180007686  mov     ecx, 200h
0x18000768b  mov     qword ptr [rax], 0
0x180007692  call    svsutil_Alloc
0x180007697  mov     [r14], rax
0x18000769a  test    rax, rax
0x18000769d  jz      loc_1800075F0
0x1800076a3  xor     edx, edx; Val
0x1800076a5  mov     r8d, 200h; Size
0x1800076ab  mov     rcx, rax; void *
0x1800076ae  call    memset_0
0x1800076b3  inc     dword ptr [rbx]
0x1800076b5  mov     eax, 40h ; '@'
0x1800076ba  cmp     [rbx], esi
0x1800076bc  mov     [rbx+8], r14
0x1800076c0  mov     r14d, ebp
0x1800076c3  cmovl   r14d, eax
0x1800076c7  mov     dword ptr [rbx+4], 0
0x1800076ce  xor     edx, edx
0x1800076d0  cmp     edx, r14d
0x1800076d3  jge     loc_180007645
0x1800076d9  mov     rcx, [rbx+8]
0x1800076dd  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x1800076e2  test    eax, eax
0x1800076e4  jz      loc_1800075F0
0x1800076ea  inc     dword ptr [rbx+4]
0x1800076ed  mov     edx, [rbx+4]
0x1800076f0  jmp     short loc_1800076D0
0x1800076f2  mov     rcx, [rbx+8]
0x1800076f6  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x1800076fb  test    eax, eax
0x1800076fd  jz      loc_1800075F0
0x180007703  inc     dword ptr [rbx+4]
0x180007706  jmp     loc_180007521
0x18000770b  lea     eax, [r9-1]
0x18000770f  mov     ecx, 2
0x180007714  cdq
0x180007715  idiv    ecx
0x180007717  mov     rcx, [rdi+10h]
0x18000771b  mov     edx, eax
0x18000771d  mov     r10d, eax
0x180007720  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x180007725  cmp     [rax], r12
0x180007728  jge     loc_180007543
0x18000772e  mov     rcx, [rdi+10h]
0x180007732  mov     edx, r10d
0x180007735  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x18000773a  mov     rcx, [rdi+10h]
0x18000773e  mov     edx, r9d
0x180007741  movups  xmm0, xmmword ptr [rax]
0x180007744  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x180007749  mov     r9d, r10d
0x18000774c  movdqu  xmmword ptr [rax], xmm0
0x180007750  test    r10d, r10d
0x180007753  jg      short loc_18000770B
0x180007755  jmp     loc_180007543
0x18000775a  cmp     dword ptr [rdi+64h], 0
0x18000775e  jnz     loc_1800075C3
0x180007764  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18000776d  lea     r8, ?SVSThreadPoolWorkerThread@SVSThreadPool@@KAKPEAX@Z; lpStartAddress
0x180007774  mov     r9, rdi; lpParameter
0x180007777  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000777f  xor     edx, edx; dwStackSize
0x180007781  xor     ecx, ecx; lpThreadAttributes
0x180007783  call    cs:__imp_CreateThread
0x180007789  test    rax, rax
0x18000778c  jz      loc_1800075C3
0x180007792  mov     rcx, rax; hObject
0x180007795  call    cs:__imp_CloseHandle
0x18000779b  inc     dword ptr [rdi+64h]
0x18000779e  jmp     loc_1800075C3
```
