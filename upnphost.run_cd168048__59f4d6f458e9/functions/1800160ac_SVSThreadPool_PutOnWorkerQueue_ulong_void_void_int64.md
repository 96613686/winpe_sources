# SVSThreadPool::PutOnWorkerQueue(ulong (*)(void *),void *,__int64)

- ea: `0x1800160ac`
- end: `0x1800163be`
- name: `?PutOnWorkerQueue@SVSThreadPool@@IEAAKP6AKPEAX@Z0_J@Z`
- size: `786`
- prototype: `unsigned int __fastcall(SVSThreadPool *__hidden this, unsigned int (*)(void *), void *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180015df0`
- `0x180016fa0`

## callees

- `0x1800160ac`
- `0x1800163c4`
- `0x18001aea8`
- `0x1800274b0`
- `0x18003d4b0`
- `0x1800528a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800161cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800161cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016392`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163aa`

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
0x1800160ac  push    rbx
0x1800160ae  push    rbp
0x1800160af  push    rsi
0x1800160b0  push    rdi
0x1800160b1  push    r12
0x1800160b3  push    r14
0x1800160b5  push    r15
0x1800160b7  sub     rsp, 30h
0x1800160bb  mov     rdi, rcx
0x1800160be  mov     r12, r9
0x1800160c1  mov     rcx, [rcx+40h]
0x1800160c5  call    svsutil_GetFixed
0x1800160ca  mov     r15, rax
0x1800160cd  test    rax, rax
0x1800160d0  jz      loc_1800161FF
0x1800160d6  mov     qword ptr [r15+8], 0
0x1800160de  lea     rax, ?RemoveUnusedISAPIs@@YAKPEAX@Z; RemoveUnusedISAPIs(void *)
0x1800160e5  mov     [r15], rax
0x1800160e8  inc     dword ptr [rdi+68h]
0x1800160eb  mov     eax, [rdi+68h]
0x1800160ee  mov     [r15+10h], eax
0x1800160f2  mov     rbx, [rdi+10h]
0x1800160f6  test    rbx, rbx
0x1800160f9  jz      loc_1800161FF
0x1800160ff  mov     ebp, [rdi+8]
0x180016102  inc     ebp
0x180016104  mov     esi, ebp
0x180016106  sar     esi, 0Bh
0x180016109  inc     esi
0x18001610b  cmp     esi, [rbx]
0x18001610d  jl      short loc_180016130
0x18001610f  sar     ebp, 5
0x180016112  and     ebp, 3Fh
0x180016115  inc     ebp
0x180016117  cmp     esi, [rbx]
0x180016119  jz      loc_1800161EF
0x18001611f  jg      loc_18001622A
0x180016125  mov     edx, [rbx+4]
0x180016128  cmp     edx, ebp
0x18001612a  jl      loc_180016301
0x180016130  mov     r9d, [rdi+8]
0x180016134  not     r12
0x180016137  lea     eax, [r9+1]
0x18001613b  mov     [rdi+8], eax
0x18001613e  test    r9d, r9d
0x180016141  jg      loc_18001631A
0x180016147  mov     rax, [rdi+10h]
0x18001614b  mov     r10d, r9d
0x18001614e  and     r10d, 0FFFFF800h
0x180016155  mov     rax, [rax+8]
0x180016159  test    rax, rax
0x18001615c  jz      loc_180016212
0x180016162  cmp     [rax+8], r10d
0x180016166  jnz     loc_180016203
0x18001616c  mov     rax, [rax]
0x18001616f  movsxd  rdx, r9d
0x180016172  mov     r8, rdx
0x180016175  mov     rcx, rdx
0x180016178  sar     rcx, 5
0x18001617c  and     r8d, 1Fh
0x180016180  and     ecx, 3Fh
0x180016183  shl     r8, 4
0x180016187  add     r8, [rax+rcx*8]
0x18001618b  mov     [r8], r12
0x18001618e  mov     rax, [rdi+10h]
0x180016192  mov     rax, [rax+8]
0x180016196  test    rax, rax
0x180016199  jz      loc_180016221
0x18001619f  cmp     [rax+8], r10d
0x1800161a3  jnz     short loc_18001620C
0x1800161a5  mov     rax, [rax]
0x1800161a8  mov     rcx, rdx
0x1800161ab  sar     rcx, 5
0x1800161af  and     edx, 1Fh
0x1800161b2  and     ecx, 3Fh
0x1800161b5  shl     rdx, 4
0x1800161b9  add     rdx, [rax+rcx*8]
0x1800161bd  mov     [rdx+8], r15
0x1800161c1  cmp     dword ptr [rdi+60h], 0
0x1800161c5  jz      loc_180016369
0x1800161cb  mov     rcx, [rdi+50h]; hEvent
0x1800161cf  call    cs:__imp_SetEvent
0x1800161d6  nop     dword ptr [rax+rax+00h]
0x1800161db  mov     eax, [r15+10h]
0x1800161df  add     rsp, 30h
0x1800161e3  pop     r15
0x1800161e5  pop     r14
0x1800161e7  pop     r12
0x1800161e9  pop     rdi
0x1800161ea  pop     rsi
0x1800161eb  pop     rbp
0x1800161ec  pop     rbx
0x1800161ed  retn
0x1800161ef  cmp     ebp, [rbx+4]
0x1800161f2  jle     loc_180016130
0x1800161f8  cmp     esi, [rbx]
0x1800161fa  jmp     loc_18001611F
0x1800161ff  xor     eax, eax
0x180016201  jmp     short loc_1800161DF
0x180016203  mov     rax, [rax+10h]
0x180016207  jmp     loc_180016159
0x18001620c  mov     rax, [rax+10h]
0x180016210  jmp     short loc_180016196
0x180016212  lea     r8, ?dummy@?1???A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z@4U2@A; SVSTHeapEntry<__int64> `SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)'::`2'::dummy
0x180016219  movsxd  rdx, r9d
0x18001621c  jmp     loc_18001618B
0x180016221  lea     rdx, ?dummy@?1???A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z@4U2@A; SVSTHeapEntry<__int64> `SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)'::`2'::dummy
0x180016228  jmp     short loc_1800161BD
0x18001622a  cmp     qword ptr [rbx+8], 0
0x18001622f  mov     eax, 40h ; '@'
0x180016234  jz      short loc_180016254
0x180016236  mov     edx, [rbx+4]
0x180016239  cmp     edx, eax
0x18001623b  jge     short loc_180016254
0x18001623d  mov     rcx, [rbx+8]
0x180016241  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x180016246  test    eax, eax
0x180016248  jz      short loc_1800161FF
0x18001624a  inc     dword ptr [rbx+4]
0x18001624d  mov     eax, 40h ; '@'
0x180016252  jmp     short loc_180016236
0x180016254  cmp     [rbx], esi
0x180016256  jge     loc_180016130
0x18001625c  mov     rdx, cs:g_pvAllocData
0x180016263  mov     ecx, 18h
0x180016268  call    svsutil_Alloc
0x18001626d  mov     r14, rax
0x180016270  test    rax, rax
0x180016273  jz      short loc_1800161FF
0x180016275  mov     edx, [rbx]
0x180016277  mov     rcx, [rbx+8]
0x18001627b  shl     edx, 0Bh
0x18001627e  mov     [rax+8], edx
0x180016281  or      edx, 7FFh
0x180016287  mov     [rax+0Ch], edx
0x18001628a  mov     rdx, cs:g_pvAllocData
0x180016291  mov     [rax+10h], rcx
0x180016295  mov     ecx, 200h
0x18001629a  mov     qword ptr [rax], 0
0x1800162a1  call    svsutil_Alloc
0x1800162a6  mov     [r14], rax
0x1800162a9  test    rax, rax
0x1800162ac  jz      loc_1800161FF
0x1800162b2  xor     edx, edx; Val
0x1800162b4  mov     r8d, 200h; Size
0x1800162ba  mov     rcx, rax; void *
0x1800162bd  call    memset_0
0x1800162c2  inc     dword ptr [rbx]
0x1800162c4  mov     eax, 40h ; '@'
0x1800162c9  cmp     [rbx], esi
0x1800162cb  mov     [rbx+8], r14
0x1800162cf  mov     r14d, ebp
0x1800162d2  cmovl   r14d, eax
0x1800162d6  mov     dword ptr [rbx+4], 0
0x1800162dd  xor     edx, edx
0x1800162df  cmp     edx, r14d
0x1800162e2  jge     loc_180016254
0x1800162e8  mov     rcx, [rbx+8]
0x1800162ec  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x1800162f1  test    eax, eax
0x1800162f3  jz      loc_1800161FF
0x1800162f9  inc     dword ptr [rbx+4]
0x1800162fc  mov     edx, [rbx+4]
0x1800162ff  jmp     short loc_1800162DF
0x180016301  mov     rcx, [rbx+8]
0x180016305  call    ?AllocateCluster@?$SVSMTABlock@U?$SVSTHeapEntry@_J@@@@QEAAHH@Z; SVSMTABlock<SVSTHeapEntry<__int64>>::AllocateCluster(int)
0x18001630a  test    eax, eax
0x18001630c  jz      loc_1800161FF
0x180016312  inc     dword ptr [rbx+4]
0x180016315  jmp     loc_180016125
0x18001631a  lea     eax, [r9-1]
0x18001631e  mov     ecx, 2
0x180016323  cdq
0x180016324  idiv    ecx
0x180016326  mov     rcx, [rdi+10h]
0x18001632a  mov     edx, eax
0x18001632c  mov     r10d, eax
0x18001632f  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x180016334  cmp     [rax], r12
0x180016337  jge     loc_180016147
0x18001633d  mov     rcx, [rdi+10h]
0x180016341  mov     edx, r10d
0x180016344  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x180016349  mov     rcx, [rdi+10h]
0x18001634d  mov     edx, r9d
0x180016350  movups  xmm0, xmmword ptr [rax]
0x180016353  call    ??A?$SVSExpArray@U?$SVSTHeapEntry@_J@@@@QEAAAEAU?$SVSTHeapEntry@_J@@H@Z; SVSExpArray<SVSTHeapEntry<__int64>>::operator[](int)
0x180016358  mov     r9d, r10d
0x18001635b  movdqu  xmmword ptr [rax], xmm0
0x18001635f  test    r10d, r10d
0x180016362  jg      short loc_18001631A
0x180016364  jmp     loc_180016147
0x180016369  cmp     dword ptr [rdi+64h], 0
0x18001636d  jnz     loc_1800161CB
0x180016373  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18001637c  lea     r8, ?SVSThreadPoolWorkerThread@SVSThreadPool@@KAKPEAX@Z; lpStartAddress
0x180016383  mov     r9, rdi; lpParameter
0x180016386  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18001638e  xor     edx, edx; dwStackSize
0x180016390  xor     ecx, ecx; lpThreadAttributes
0x180016392  call    cs:__imp_CreateThread
0x180016399  nop     dword ptr [rax+rax+00h]
0x18001639e  test    rax, rax
0x1800163a1  jz      loc_1800161CB
0x1800163a7  mov     rcx, rax; hObject
0x1800163aa  call    cs:__imp_CloseHandle
0x1800163b1  nop     dword ptr [rax+rax+00h]
0x1800163b6  inc     dword ptr [rdi+64h]
0x1800163b9  jmp     loc_1800161CB
```
