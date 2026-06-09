# TMemoryBlockAllocator<0,16777216,0,1,0,2560>::GetNewActiveBlockFromPartialList(ushort,bool,bool,bool)

- ea: `0x100437560`
- end: `0x1004376e4`
- name: `?GetNewActiveBlockFromPartialList@?$TMemoryBlockAllocator@$0A@$0BAAAAAA@$0A@$00$0A@$0KAA@@@EEAAPEAVSOS_ParentBlockDescriptor@@G_N00@Z`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100416390`
- `0x100422880`
- `0x100431e70`
- `0x100437560`
- `0x100494e40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x100493f66`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493fb7`
- `KERNEL32!InterlockedPushEntrySList` at `0x100494128`
- `KERNEL32!InterlockedPushEntrySList` at `0x100494191`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004943fd`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493f66`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493fb7`
- `KERNEL32!InterlockedPushEntrySList` at `0x100494128`
- `KERNEL32!InterlockedPushEntrySList` at `0x100494191`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004943fd`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437601`
- `KERNEL32!InterlockedPopEntrySList` at `0x100494003`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437601`
- `KERNEL32!InterlockedPopEntrySList` at `0x100494003`
- `KERNEL32!QueryPerformanceCounter` at `0x100494202`
- `KERNEL32!QueryPerformanceCounter` at `0x10049423b`
- `KERNEL32!QueryPerformanceCounter` at `0x100494202`
- `KERNEL32!QueryPerformanceCounter` at `0x10049423b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall TMemoryBlockAllocator<0,16777216,0,1,0,2560>::GetNewActiveBlockFromPartialList(
        __int64 a1,
        unsigned __int16 a2,
        char a3,
        char a4,
        char a5)
{
  __int64 v5; // r15
  __int64 v6; // rdi
  PSLIST_ENTRY v7; // rbx
  __int64 v8; // r13
  char v9; // r14
  signed int v10; // esi
  union _SLIST_HEADER *v11; // rdi
  PSLIST_ENTRY v12; // rax
  PSLIST_ENTRY v13; // r8
  PSLIST_ENTRY v14; // rdx
  LARGE_INTEGER v15; // rbx
  signed __int64 UniqueThread_low; // r14
  int v17; // r15d
  __int64 v18; // r13
  __int64 v19; // r12
  struct SOS_ParentBlockDescriptor **v20; // rbx
  struct SOS_ParentBlockDescriptor *v21; // rdx
  bool v23; // zf
  __int64 v24; // r10
  int v25; // r11d
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r9
  signed int v28; // eax
  unsigned __int64 v29; // r9
  __int64 v30; // r10
  unsigned __int64 v31; // rdx
  signed __int64 v32; // rax
  SOS_MemoryBlockAllocator *v33; // rcx
  struct _SLIST_ENTRY *Next; // rax
  int v35; // edi
  union _SLIST_HEADER *v36; // rsi
  PSLIST_ENTRY v37; // rax
  PSLIST_ENTRY v38; // r8
  __int64 v39; // r10
  int v40; // r11d
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // r9
  int v43; // eax
  unsigned __int64 v44; // r9
  __int64 v45; // r10
  unsigned __int64 v46; // rdx
  signed __int64 v47; // rax
  PSLIST_ENTRY v48; // rdx
  SOS_MemoryBlockAllocator *v49; // rcx
  struct _SLIST_ENTRY *v50; // rax
  __int64 v51; // rdx
  SpinlockBase *v52; // rcx
  LARGE_INTEGER v53; // rcx
  LONGLONG v54; // rax
  int v55; // edi
  unsigned __int64 v56; // rdx
  unsigned __int64 v57; // r9
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rdx
  signed __int64 v60; // rax
  struct SOS_ParentBlockDescriptor *v61; // rcx
  struct SOS_ParentBlockDescriptor *v62; // rax
  __int64 v63; // r11
  struct SOS_ParentBlockDescriptor *v64; // r9
  struct SOS_ParentBlockDescriptor **v65; // r8
  struct SOS_ParentBlockDescriptor *v66; // r14
  struct SOS_ParentBlockDescriptor **v67; // r10
  struct SOS_ParentBlockDescriptor *v68; // rcx
  __int64 v69; // rax
  SOS_MemoryBlockAllocator *v70; // rcx
  __int64 v71; // rax
  PSLIST_ENTRY v72; // [rsp+28h] [rbp-51h]
  __int64 v73; // [rsp+30h] [rbp-49h] BYREF
  struct SOS_ParentBlockDescriptor *v74; // [rsp+38h] [rbp-41h]
  __int64 v75; // [rsp+40h] [rbp-39h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+48h] [rbp-31h]
  __int64 v77; // [rsp+50h] [rbp-29h] BYREF
  PSLIST_ENTRY v78; // [rsp+58h] [rbp-21h]
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-19h] BYREF
  LARGE_INTEGER v80; // [rsp+68h] [rbp-11h] BYREF
  __int64 v81; // [rsp+70h] [rbp-9h]
  __int64 v82; // [rsp+78h] [rbp-1h] BYREF
  int v83; // [rsp+80h] [rbp+7h]
  __int64 v84; // [rsp+88h] [rbp+Fh]

  v84 = -2;
  v5 = a1;
  v6 = 0;
  v7 = 0;
  v72 = 0;
  v74 = (struct SOS_ParentBlockDescriptor *)&v73;
  v73 = (__int64)&v73;
  v8 = a1 + ((a2 + 2LL) << 7);
  v81 = v8;
  v9 = a5;
  if ( a4 )
  {
    v10 = 1;
    while ( 1 )
    {
      v72 = 0;
      if ( (unsigned int)v10 >= 2 )
        break;
      ListEntry = (PSLIST_ENTRY)&v75;
      v75 = (__int64)&v75;
      v11 = (union _SLIST_HEADER *)(v8 + 16 * (v10 + 4LL));
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v12 = InterlockedPopEntrySList(v11);
            v13 = v12;
            if ( !v12 )
            {
              v7 = 0;
              goto LABEL_7;
            }
            v23 = ((__int64)v12[6].Next & 7) == 0;
            v24 = (__int64)v12[6].Next & 7;
            v12->Next = 0;
            *((_QWORD *)&v12->Next + 1) = 0;
            if ( !v23 )
              break;
            *((_QWORD *)&v12->Next + 1) = v74;
            *(_QWORD *)v74 = v12;
            v74 = (struct SOS_ParentBlockDescriptor *)v12;
            v12->Next = (struct _SLIST_ENTRY *)&v73;
          }
          v25 = *(unsigned __int16 *)(v5 + 88);
          LODWORD(v26) = v25 - 1;
          v27 = (unsigned __int64)v12[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v27 != v12[4].Next )
          {
            if ( *(_WORD *)(v5 + 90) )
            {
              v26 = v27 >> *(_WORD *)(v5 + 90);
            }
            else if ( v27 )
            {
              LODWORD(v26) = v27 - 1;
            }
            else
            {
              LODWORD(v26) = 0;
            }
          }
          if ( v27 > *((_QWORD *)&v12[4].Next + 1) )
            LODWORD(v26) = v25 + v26;
          v28 = v26 + 1;
          if ( (_DWORD)v26 )
            v28 = v26;
          if ( v28 <= v10 )
            break;
          HIWORD(v13[5].Next) = v28;
          InterlockedPushEntrySList((PSLIST_HEADER)(v8 + 16 * ((unsigned int)(v28 - 1) + 5LL)), v13);
        }
        if ( (_DWORD)v24 != 4 )
        {
          v29 = (unsigned __int64)v13[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
          v30 = 1;
          if ( a5 )
            v30 = 6;
          do
          {
            v31 = v29;
            v32 = _InterlockedCompareExchange64((volatile signed __int64 *)&v13[6], v29 | v30, v29 | 2);
            v29 = v32 & 0xFFFFFFFFFFFFFFF8uLL;
          }
          while ( (v32 & 0xFFFFFFFFFFFFFFF8uLL) != v31 );
          if ( (v32 & 7) == 2 )
            break;
        }
        *((_QWORD *)&v13->Next + 1) = ListEntry;
        ListEntry->Next = v13;
        ListEntry = v13;
        v13->Next = (struct _SLIST_ENTRY *)&v75;
      }
      HIWORD(v13[5].Next) = -1;
      v7 = v13;
LABEL_7:
      while ( 1 )
      {
        v14 = ListEntry;
        if ( ListEntry == (PSLIST_ENTRY)&v75 || !ListEntry )
          break;
        v33 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&ListEntry->Next + 1);
        Next = ListEntry->Next;
        *((_QWORD *)&Next->Next + 1) = v33;
        *(_QWORD *)v33 = Next;
        *((_QWORD *)&v14->Next + 1) = 0;
        v14->Next = 0;
        if ( ((__int64)v14[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v11, v14);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v33, (struct SOS_ParentBlockDescriptor *)v14);
      }
      ++v10;
      v5 = a1;
      if ( v7 )
        goto LABEL_19;
      v6 = 0;
    }
  }
  else
  {
    v35 = 1;
    while ( v35 )
    {
      v72 = 0;
      v78 = (PSLIST_ENTRY)&v77;
      v77 = (__int64)&v77;
      v36 = (union _SLIST_HEADER *)(v8 + 16 * (v35 + 4LL));
      while ( 1 )
      {
        v37 = InterlockedPopEntrySList(v36);
        v38 = v37;
        if ( !v37 )
          break;
        v23 = ((__int64)v37[6].Next & 7) == 0;
        v39 = (__int64)v37[6].Next & 7;
        v37->Next = 0;
        *((_QWORD *)&v37->Next + 1) = 0;
        if ( v23 )
        {
          *((_QWORD *)&v37->Next + 1) = v74;
          *(_QWORD *)v74 = v37;
          v74 = (struct SOS_ParentBlockDescriptor *)v37;
          v37->Next = (struct _SLIST_ENTRY *)&v73;
        }
        else
        {
          v40 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v41) = v40 - 1;
          v42 = (unsigned __int64)v37[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v42 != v37[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v41 = v42 >> *(_WORD *)(a1 + 90);
            }
            else if ( v42 )
            {
              LODWORD(v41) = v42 - 1;
            }
            else
            {
              LODWORD(v41) = 0;
            }
          }
          if ( v42 > *((_QWORD *)&v37[4].Next + 1) )
            LODWORD(v41) = v40 + v41;
          v43 = v41 + 1;
          if ( (_DWORD)v41 )
            v43 = v41;
          if ( v43 > v35 )
          {
            HIWORD(v38[5].Next) = v43;
            InterlockedPushEntrySList((PSLIST_HEADER)(v8 + 16 * ((unsigned int)(v43 - 1) + 5LL)), v38);
          }
          else
          {
            if ( (_DWORD)v39 != 4 )
            {
              v44 = (unsigned __int64)v38[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
              v45 = 1;
              if ( v9 )
                v45 = 6;
              do
              {
                v46 = v44;
                v47 = _InterlockedCompareExchange64((volatile signed __int64 *)&v38[6], v44 | v45, v44 | 2);
                v44 = v47 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v47 & 0xFFFFFFFFFFFFFFF8uLL) != v46 );
              if ( (v47 & 7) == 2 )
              {
                HIWORD(v38[5].Next) = -1;
                v7 = v38;
                v72 = v38;
                goto LABEL_71;
              }
            }
            *((_QWORD *)&v38->Next + 1) = v78;
            v78->Next = v38;
            v78 = v38;
            v38->Next = (struct _SLIST_ENTRY *)&v77;
          }
        }
      }
      v7 = 0;
LABEL_71:
      while ( 1 )
      {
        v48 = v78;
        if ( v78 == (PSLIST_ENTRY)&v77 || !v78 )
          break;
        v49 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&v78->Next + 1);
        v50 = v78->Next;
        *((_QWORD *)&v50->Next + 1) = v49;
        *(_QWORD *)v49 = v50;
        *((_QWORD *)&v48->Next + 1) = 0;
        v48->Next = 0;
        if ( ((__int64)v48[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v36, v48);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v49, (struct SOS_ParentBlockDescriptor *)v48);
      }
      --v35;
      v9 = a5;
      if ( v7 )
        goto LABEL_19;
    }
    v6 = 0;
  }
  if ( a3 )
  {
    v82 = v8 + 48;
    v83 = 0;
    v15.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v8 + 48)
      || _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 48), UniqueThread_low, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v51 && *(_QWORD *)(v51 + 272) == v51 )
          v6 = *(_QWORD *)(v51 + 256);
        if ( v6 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v15 = PerformanceCount;
          }
          else
          {
            v15.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      v52 = (SpinlockBase *)(v8 + 48);
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<49,1,268435714>::SpinToAcquireWithExponentialBackoff(v52);
      else
        Spinlock<49,1,268435714>::SpinToAcquireOptimistic(v52, v6, UniqueThread_low);
      if ( v6 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v80);
          v53 = v80;
        }
        else
        {
          v53.QuadPart = MEMORY[0x7FFE0008];
        }
        v54 = 0;
        if ( v53.QuadPart >= (unsigned __int64)v15.QuadPart )
          v54 = v53.QuadPart - v15.QuadPart;
        *(_QWORD *)(v6 + 3192) += v54;
      }
    }
    v83 = 1;
    v17 = 0;
    v18 = v8 + 56;
    v19 = v81;
    v7 = v72;
    do
    {
      if ( v17 )
        break;
      v20 = *(struct SOS_ParentBlockDescriptor ***)(v18 + 8);
      if ( v20 != (struct SOS_ParentBlockDescriptor **)v18 )
      {
        while ( v20 )
        {
          v65 = v20;
          v66 = (struct SOS_ParentBlockDescriptor *)v20;
          v67 = v20 + 1;
          v20 = (struct SOS_ParentBlockDescriptor **)v20[1];
          if ( v20 == (struct SOS_ParentBlockDescriptor **)v18 )
            v20 = 0;
          if ( (*((_QWORD *)v66 + 12) & 7) != 0 )
          {
            v55 = *(unsigned __int16 *)(a1 + 88);
            LODWORD(v56) = v55 - 1;
            v57 = (unsigned __int64)v65[12] >> 3;
            if ( (struct SOS_ParentBlockDescriptor *)v57 != v65[8] )
            {
              if ( *(_WORD *)(a1 + 90) )
              {
                v56 = v57 >> *(_WORD *)(a1 + 90);
              }
              else if ( v57 )
              {
                LODWORD(v56) = v57 - 1;
              }
              else
              {
                LODWORD(v56) = 0;
              }
            }
            if ( v57 > (unsigned __int64)v65[9] )
              LODWORD(v56) = v55 + v56;
            if ( (int)v56 > 0 )
            {
              *((_WORD *)v65 + 43) = v56;
              v63 = *(_QWORD *)v66;
              v64 = *v67;
              *(_QWORD *)(v63 + 8) = *v67;
              *(_QWORD *)v64 = v63;
              *v67 = 0;
              *v65 = 0;
              InterlockedPushEntrySList((PSLIST_HEADER)(v19 + 16 * ((unsigned int)(v56 - 1) + 5LL)), (PSLIST_ENTRY)v65);
            }
            else if ( (*((_DWORD *)v66 + 24) & 7) != 4 )
            {
              v58 = (unsigned __int64)v65[12] & 0xFFFFFFFFFFFFFFF8uLL;
              do
              {
                v59 = v58;
                v60 = _InterlockedCompareExchange64((volatile signed __int64 *)v65 + 12, v58 | 1, v58 | 2);
                v58 = v60 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v60 & 0xFFFFFFFFFFFFFFF8uLL) != v59 );
              if ( (v60 & 7) == 2 )
              {
                v61 = v65[1];
                v62 = *v65;
                *((_QWORD *)v62 + 1) = v61;
                *(_QWORD *)v61 = v62;
                v65[1] = 0;
                *v65 = 0;
                *((_WORD *)v65 + 43) = -1;
                v7 = (PSLIST_ENTRY)v65;
                v72 = (PSLIST_ENTRY)v65;
                goto LABEL_17;
              }
            }
          }
          else
          {
            v68 = *v67;
            v69 = *(_QWORD *)v66;
            *(_QWORD *)(v69 + 8) = *v67;
            *(_QWORD *)v68 = v69;
            *v67 = v74;
            *(_QWORD *)v74 = v66;
            v74 = v66;
            *(_QWORD *)v66 = &v73;
          }
        }
      }
      v7 = v72;
LABEL_17:
      v17 = 1;
      v18 += 16;
    }
    while ( !v7 );
    SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(&v82);
  }
LABEL_19:
  while ( 1 )
  {
    v21 = v74;
    if ( v74 == (struct SOS_ParentBlockDescriptor *)&v73 || !v74 )
      break;
    v70 = (SOS_MemoryBlockAllocator *)*((_QWORD *)v74 + 1);
    v71 = *(_QWORD *)v74;
    *(_QWORD *)(v71 + 8) = v70;
    *(_QWORD *)v70 = v71;
    *((_QWORD *)v21 + 1) = 0;
    *(_QWORD *)v21 = 0;
    SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v70, v21);
  }
  return v7;
}

```

## disassembly

```asm
0x100437560  mov     rax, rsp
0x100437563  mov     [rax+18h], r8b
0x100437567  mov     [rax+8], rcx
0x10043756b  push    rbp
0x10043756c  push    rsi
0x10043756d  push    rdi
0x10043756e  push    r12
0x100437570  push    r13
0x100437572  push    r14
0x100437574  push    r15
0x100437576  lea     rbp, [rax-57h]
0x10043757a  sub     rsp, 90h
0x100437581  mov     [rbp+4Fh+var_40], 0FFFFFFFFFFFFFFFEh
0x100437589  mov     [rax+10h], rbx
0x10043758d  mov     r15, rcx
0x100437590  xor     edi, edi
0x100437592  mov     ebx, edi
0x100437594  mov     [rbp+4Fh+var_A0], rbx
0x100437598  lea     rax, [rbp+4Fh+var_98]
0x10043759c  mov     [rbp+4Fh+var_90], rax
0x1004375a0  lea     rax, [rbp+4Fh+var_98]
0x1004375a4  mov     [rbp+4Fh+var_98], rax
0x1004375a8  movzx   r13d, dx
0x1004375ac  add     r13, 2
0x1004375b0  shl     r13, 7
0x1004375b4  add     r13, rcx
0x1004375b7  mov     [rbp+4Fh+var_58], r13
0x1004375bb  lea     r12d, [rdi+6]
0x1004375bf  movzx   r14d, [rbp+4Fh+arg_20]
0x1004375c4  test    r9b, r9b
0x1004375c7  jz      loc_100493FC3
0x1004375cd  lea     esi, [rdi+1]
0x1004375d0  jmp     short loc_1004375D3
0x1004375d3  mov     [rbp+4Fh+var_A0], rbx
0x1004375d7  cmp     esi, 2
0x1004375da  jnb     short loc_100437645
0x1004375dc  mov     [rbp+4Fh+var_A0], rdi
0x1004375e0  lea     rcx, [rbp+4Fh+var_88]
0x1004375e4  mov     [rbp+4Fh+ListEntry], rcx
0x1004375e8  lea     rax, [rbp+4Fh+var_88]
0x1004375ec  mov     [rbp+4Fh+var_88], rax
0x1004375f0  movsxd  rdi, esi
0x1004375f3  add     rdi, 4
0x1004375f7  shl     rdi, 4
0x1004375fb  add     rdi, r13
0x1004375fe  mov     rcx, rdi; ListHead
0x100437601  call    cs:__imp_InterlockedPopEntrySList
0x100437607  mov     r8, rax
0x10043760a  test    rax, rax
0x10043760d  jnz     loc_100493E49
0x100437613  mov     rbx, [rbp+4Fh+var_A0]
0x100437617  xor     r15d, r15d
0x10043761a  nop     word ptr [rax+rax+00h]
0x100437620  lea     rax, [rbp+4Fh+var_88]
0x100437624  mov     rdx, [rbp+4Fh+ListEntry]; struct SOS_ParentBlockDescriptor *
0x100437628  cmp     rdx, rax
0x10043762b  jnz     loc_100493F84
0x100437631  inc     esi
0x100437633  test    rbx, rbx
0x100437636  mov     r15, [rbp+4Fh+arg_0]
0x10043763a  jnz     loc_1004376E1
0x100437640  xor     edi, edi
0x100437642  jmp     short loc_1004375D3
0x100437645  test    rbx, rbx
0x100437648  jnz     loc_1004376F0
0x10043764e  jmp     short loc_100437651
0x100437651  cmp     [rbp+4Fh+arg_10], 0
0x100437655  jz      loc_1004376F0
0x10043765b  lea     rsi, [r13+30h]
0x10043765f  mov     [rbp+4Fh+var_50], rsi
0x100437663  mov     [rbp+4Fh+var_48], edi
0x100437666  mov     rbx, rdi
0x100437669  mov     eax, gs:48h
0x100437671  mov     r14d, eax
0x100437674  mov     eax, [rsi]
0x100437676  test    eax, eax
0x100437678  jnz     loc_1004941B6
0x10043767e  xor     eax, eax
0x100437680  lock cmpxchg [rsi], r14
0x100437685  mov     eax, edi
0x100437687  setz    al
0x10043768a  test    eax, eax
0x10043768c  jz      loc_1004941B6
0x100437692  mov     [rbp+4Fh+var_48], 1
0x100437699  mov     r15d, edi
0x10043769c  add     r13, 38h ; '8'
0x1004376a0  mov     r12, [rbp+4Fh+var_58]
0x1004376a4  mov     rbx, [rbp+4Fh+var_A0]
0x1004376a8  nop     dword ptr [rax+rax+00000000h]
0x1004376b0  cmp     r15d, 1
0x1004376b4  jnb     short loc_1004376D3
0x1004376b6  mov     rbx, [r13+8]
0x1004376ba  cmp     rbx, r13
0x1004376bd  jnz     loc_100494390
0x1004376c3  mov     rbx, [rbp+4Fh+var_A0]
0x1004376c7  inc     r15d
0x1004376ca  add     r13, 10h
0x1004376ce  test    rbx, rbx
0x1004376d1  jz      short loc_1004376B0
0x1004376d3  lea     rcx, [rbp+4Fh+var_50]
0x1004376d7  call    ??1?$SpinlockHolder@$0DB@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(void)
0x1004376dc  nop     word ptr [rax+rax]
0x1004376e1  jmp     short loc_1004376F0
0x1004376f0  lea     rax, [rbp+4Fh+var_98]
0x1004376f4  mov     rdx, [rbp+4Fh+var_90]; struct SOS_ParentBlockDescriptor *
0x1004376f8  cmp     rdx, rax
0x1004376fb  jnz     loc_100494406
0x100437701  mov     rax, rbx
0x100437704  mov     rbx, [rsp+0C0h+arg_8]
0x10043770c  add     rsp, 90h
0x100437713  pop     r15
0x100437715  pop     r14
0x100437717  pop     r13
0x100437719  pop     r12
0x10043771b  pop     rdi
0x10043771c  pop     rsi
0x10043771d  pop     rbp
0x10043771e  retn
0x100493e49  mov     r10, [rax+60h]
0x100493e4d  and     r10d, 7
0x100493e51  mov     eax, 0
0x100493e56  mov     [r8], rax
0x100493e59  mov     [r8+8], rax
0x100493e5d  jnz     short loc_100493E7E
0x100493e5f  mov     rax, [rbp+4Fh+var_90]
0x100493e63  mov     [r8+8], rax
0x100493e67  mov     rax, [rbp+4Fh+var_90]
0x100493e6b  mov     [rax], r8
0x100493e6e  mov     [rbp+4Fh+var_90], r8
0x100493e72  lea     rax, [rbp+4Fh+var_98]
0x100493e76  mov     [r8], rax
0x100493e79  jmp     loc_1004375FE
0x100493e7e  movzx   r11d, word ptr [r15+58h]
0x100493e83  lea     edx, [r11-1]
0x100493e87  mov     rax, [r8+40h]
0x100493e8b  movzx   ecx, word ptr [r15+5Ah]
0x100493e90  mov     r9, [r8+60h]
0x100493e94  shr     r9, 3
0x100493e98  mov     rbx, [r8+48h]
0x100493e9c  cmp     r9, rax
0x100493e9f  jz      short loc_100493EB3
0x100493ea1  test    rcx, rcx
0x100493ea4  jz      loc_100493F38
0x100493eaa  mov     rdx, r9
0x100493ead  shr     rdx, cl
0x100493eb0  jmp     short loc_100493EB3
0x100493eb3  cmp     r9, rbx
0x100493eb6  jbe     short loc_100493EBB
0x100493eb8  add     edx, r11d
0x100493ebb  lea     eax, [rdx+1]
0x100493ebe  cmp     edx, 1
0x100493ec1  cmovnb  eax, edx
0x100493ec4  cmp     eax, esi
0x100493ec6  jg      loc_100493F50
0x100493ecc  cmp     r10d, 4
0x100493ed0  jz      short loc_100493F18
0x100493ed2  mov     r9, [r8+60h]
0x100493ed6  and     r9, 0FFFFFFFFFFFFFFF8h
0x100493eda  mov     r10d, 1
0x100493ee0  test    r14b, r14b
0x100493ee3  cmovnz  r10, r12
0x100493ee7  nop     word ptr [rax+rax+00000000h]
0x100493ef0  mov     rdx, r9
0x100493ef3  mov     rax, r9
0x100493ef6  or      rax, 2
0x100493efa  mov     rcx, r10
0x100493efd  or      rcx, r9
0x100493f00  lock cmpxchg [r8+60h], rcx
0x100493f06  mov     r9, rax
0x100493f09  and     r9, 0FFFFFFFFFFFFFFF8h
0x100493f0d  cmp     r9, rdx
0x100493f10  jnz     short loc_100493EF0
0x100493f12  and     al, 7
0x100493f14  cmp     al, 2
0x100493f16  jz      short loc_100493F71
0x100493f18  mov     rax, [rbp+4Fh+ListEntry]
0x100493f1c  mov     [r8+8], rax
0x100493f20  mov     rax, [rbp+4Fh+ListEntry]
0x100493f24  mov     [rax], r8
0x100493f27  mov     [rbp+4Fh+ListEntry], r8
0x100493f2b  lea     rax, [rbp+4Fh+var_88]
0x100493f2f  mov     [r8], rax
0x100493f32  jmp     loc_1004375FE
0x100493f38  test    r9, r9
0x100493f3b  jz      short loc_100493F46
0x100493f3d  lea     edx, [r9-1]
0x100493f41  jmp     loc_100493EB3
0x100493f46  xor     eax, eax
0x100493f48  mov     edx, eax
0x100493f4a  jmp     loc_100493EB3
0x100493f50  mov     [r8+56h], ax
0x100493f55  lea     ecx, [rax-1]
0x100493f58  add     rcx, 5
0x100493f5c  shl     rcx, 4
0x100493f60  add     rcx, r13; ListHead
0x100493f63  mov     rdx, r8; ListEntry
0x100493f66  call    cs:__imp_InterlockedPushEntrySList
0x100493f6c  jmp     loc_1004375FE
0x100493f71  mov     eax, 0FFFFh
0x100493f76  mov     [r8+56h], ax
0x100493f7b  mov     rbx, r8
0x100493f7e  jmp     loc_100437617
0x100493f84  test    rdx, rdx
0x100493f87  jz      loc_100437631
0x100493f8d  mov     rcx, [rdx+8]; this
0x100493f91  mov     rax, [rdx]
0x100493f94  mov     [rax+8], rcx
0x100493f98  mov     [rcx], rax
0x100493f9b  mov     [rdx+8], r15
0x100493f9f  mov     [rdx], r15
0x100493fa2  mov     rax, [rdx+60h]
0x100493fa6  test    al, 7
0x100493fa8  jnz     short loc_100493FB4
0x100493faa  call    ?ReleaseEmptyDescriptor@SOS_MemoryBlockAllocator@@IEAAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(SOS_ParentBlockDescriptor *)
0x100493faf  jmp     loc_100437620
0x100493fb4  mov     rcx, rdi; ListHead
0x100493fb7  call    cs:__imp_InterlockedPushEntrySList
0x100493fbd  jmp     loc_100437620
0x100493fc3  mov     edi, 1
0x100493fc8  nop     dword ptr [rax+rax+00000000h]
0x100493fd0  cmp     edi, 1
0x100493fd3  jb      loc_1004941AE
0x100493fd9  xor     ebx, ebx
0x100493fdb  mov     [rbp+4Fh+var_A0], rbx
0x100493fdf  lea     rcx, [rbp+4Fh+var_78]
0x100493fe3  mov     [rbp+4Fh+var_70], rcx
0x100493fe7  lea     rax, [rbp+4Fh+var_78]
0x100493feb  mov     [rbp+4Fh+var_78], rax
0x100493fef  movsxd  rsi, edi
0x100493ff2  add     rsi, 4
0x100493ff6  shl     rsi, 4
0x100493ffa  add     rsi, r13
0x100493ffd  nop     dword ptr [rax]
0x100494000  mov     rcx, rsi; ListHead
0x100494003  call    cs:__imp_InterlockedPopEntrySList
0x100494009  mov     r8, rax
0x10049400c  test    rax, rax
0x10049400f  jz      loc_100494187
0x100494015  mov     r10, [rax+60h]
0x100494019  and     r10d, 7
0x10049401d  mov     [rax], rbx
0x100494020  mov     [rax+8], rbx
0x100494024  jnz     short loc_100494042
0x100494026  mov     rax, [rbp+4Fh+var_90]
0x10049402a  mov     [r8+8], rax
0x10049402e  mov     rax, [rbp+4Fh+var_90]
0x100494032  mov     [rax], r8
0x100494035  mov     [rbp+4Fh+var_90], r8
0x100494039  lea     rax, [rbp+4Fh+var_98]
0x10049403d  mov     [r8], rax
0x100494040  jmp     short loc_100494000
0x100494042  mov     rcx, [rbp+4Fh+arg_0]
0x100494046  movzx   r11d, word ptr [rcx+58h]
0x10049404b  lea     edx, [r11-1]
0x10049404f  mov     rax, [rax+40h]
0x100494053  movzx   ecx, word ptr [rcx+5Ah]
0x100494057  mov     r9, [r8+60h]
0x10049405b  shr     r9, 3
0x10049405f  mov     rbx, [r8+48h]
0x100494063  cmp     r9, rax
0x100494066  jz      short loc_10049407A
0x100494068  test    rcx, rcx
0x10049406b  jz      loc_1004940FA
0x100494071  mov     rdx, r9
0x100494074  shr     rdx, cl
0x100494077  jmp     short loc_10049407A
0x10049407a  cmp     r9, rbx
0x10049407d  jbe     short loc_100494082
0x10049407f  add     edx, r11d
0x100494082  lea     eax, [rdx+1]
0x100494085  cmp     edx, 1
0x100494088  cmovnb  eax, edx
0x10049408b  cmp     eax, edi
0x10049408d  jg      loc_100494112
0x100494093  cmp     r10d, 4
0x100494097  jz      short loc_1004940D8
0x100494099  mov     r9, [r8+60h]
0x10049409d  and     r9, 0FFFFFFFFFFFFFFF8h
0x1004940a1  mov     r10d, 1
0x1004940a7  test    r14b, r14b
0x1004940aa  cmovnz  r10, r12
0x1004940ae  xchg    ax, ax
0x1004940b0  mov     rdx, r9
0x1004940b3  mov     rax, r9
0x1004940b6  or      rax, 2
0x1004940ba  mov     rcx, r10
0x1004940bd  or      rcx, r9
0x1004940c0  lock cmpxchg [r8+60h], rcx
0x1004940c6  mov     r9, rax
0x1004940c9  and     r9, 0FFFFFFFFFFFFFFF8h
0x1004940cd  cmp     r9, rdx
0x1004940d0  jnz     short loc_1004940B0
0x1004940d2  and     al, 7
0x1004940d4  cmp     al, 2
0x1004940d6  jz      short loc_100494135
0x1004940d8  mov     rax, [rbp+4Fh+var_70]
0x1004940dc  mov     [r8+8], rax
0x1004940e0  mov     rax, [rbp+4Fh+var_70]
0x1004940e4  mov     [rax], r8
0x1004940e7  mov     [rbp+4Fh+var_70], r8
  ... truncated ...
```
