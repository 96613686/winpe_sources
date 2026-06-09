# TMemoryBlockAllocator<0,524288,4194304,4,0,2560>::GetNewActiveBlockFromPartialList(ushort,bool,bool,bool)

- ea: `0x100416c50`
- end: `0x100416d31`
- name: `?GetNewActiveBlockFromPartialList@?$TMemoryBlockAllocator@$0A@$0IAAAA@$0EAAAAA@$03$0A@$0KAA@@@EEAAPEAVSOS_ParentBlockDescriptor@@G_N00@Z`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100416390`
- `0x100416c50`
- `0x100422880`
- `0x100431e70`
- `0x100494e40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004225e7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004935d7`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493818`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493881`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004938f3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004225e7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004935d7`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493818`
- `KERNEL32!InterlockedPushEntrySList` at `0x100493881`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004938f3`
- `KERNEL32!InterlockedPopEntrySList` at `0x100416cf4`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004936e3`
- `KERNEL32!InterlockedPopEntrySList` at `0x100416cf4`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004936e3`
- `KERNEL32!QueryPerformanceCounter` at `0x100493633`
- `KERNEL32!QueryPerformanceCounter` at `0x100493674`
- `KERNEL32!QueryPerformanceCounter` at `0x100493633`
- `KERNEL32!QueryPerformanceCounter` at `0x100493674`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall TMemoryBlockAllocator<0,524288,4194304,4,0,2560>::GetNewActiveBlockFromPartialList(
        __int64 a1,
        unsigned __int16 a2,
        char a3,
        char a4,
        char a5)
{
  __int64 v6; // rdi
  PSLIST_ENTRY v7; // rbx
  __int64 v8; // r13
  signed int v9; // esi
  union _SLIST_HEADER *v10; // rdi
  PSLIST_ENTRY v11; // rax
  PSLIST_ENTRY v12; // r8
  PSLIST_ENTRY v13; // rdx
  struct SOS_ParentBlockDescriptor *v14; // rdx
  LARGE_INTEGER v16; // rbx
  signed __int64 UniqueThread_low; // r14
  int v18; // r15d
  __int64 v19; // r13
  __int64 v20; // r12
  struct SOS_ParentBlockDescriptor **v21; // rbx
  bool v22; // zf
  __int64 v23; // r10
  int v24; // r11d
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r9
  signed int v27; // eax
  unsigned __int64 v28; // r9
  __int64 v29; // r10
  unsigned __int64 v30; // rdx
  signed __int64 v31; // rax
  SOS_MemoryBlockAllocator *v32; // rcx
  __int64 v33; // rax
  struct SOS_ParentBlockDescriptor *v34; // rcx
  __int64 v35; // rax
  struct SOS_ParentBlockDescriptor **v36; // r8
  struct SOS_ParentBlockDescriptor *v37; // r14
  struct SOS_ParentBlockDescriptor **v38; // r10
  int v39; // edi
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r9
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  signed __int64 v44; // rax
  struct SOS_ParentBlockDescriptor *v45; // rcx
  struct SOS_ParentBlockDescriptor *v46; // rax
  __int64 v47; // r11
  struct SOS_ParentBlockDescriptor *v48; // r9
  __int64 v49; // rcx
  SOS_MemoryBlockAllocator *v50; // rcx
  struct _SLIST_ENTRY *Next; // rax
  __int64 v52; // rdx
  SpinlockBase *v53; // rcx
  LARGE_INTEGER v54; // rcx
  LONGLONG v55; // rax
  signed int v56; // esi
  union _SLIST_HEADER *v57; // rdi
  PSLIST_ENTRY v58; // rax
  PSLIST_ENTRY v59; // r8
  __int64 v60; // r10
  int v61; // r11d
  unsigned __int64 v62; // rdx
  unsigned __int64 v63; // r9
  signed int v64; // eax
  unsigned __int64 v65; // r9
  __int64 v66; // r10
  unsigned __int64 v67; // rdx
  signed __int64 v68; // rax
  PSLIST_ENTRY v69; // rdx
  SOS_MemoryBlockAllocator *v70; // rcx
  struct _SLIST_ENTRY *v71; // rax
  PSLIST_ENTRY v72; // [rsp+28h] [rbp-41h]
  __int64 v73; // [rsp+30h] [rbp-39h] BYREF
  struct SOS_ParentBlockDescriptor *v74; // [rsp+38h] [rbp-31h]
  __int64 v75; // [rsp+40h] [rbp-29h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+48h] [rbp-21h]
  __int64 v77; // [rsp+50h] [rbp-19h] BYREF
  PSLIST_ENTRY v78; // [rsp+58h] [rbp-11h]
  __int64 v79; // [rsp+60h] [rbp-9h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-1h] BYREF
  LARGE_INTEGER v81; // [rsp+70h] [rbp+7h] BYREF
  __int64 v82; // [rsp+78h] [rbp+Fh] BYREF
  int v83; // [rsp+80h] [rbp+17h]
  __int64 v84; // [rsp+88h] [rbp+1Fh]

  v84 = -2;
  v6 = 0;
  v7 = 0;
  v72 = 0;
  v74 = (struct SOS_ParentBlockDescriptor *)&v73;
  v73 = (__int64)&v73;
  v8 = a1 + ((unsigned __int64)a2 << 8);
  v79 = v8;
  if ( a4 )
  {
    v9 = 4;
    while ( 1 )
    {
      v72 = 0;
      if ( (unsigned int)v9 >= 8 )
        break;
      ListEntry = (PSLIST_ENTRY)&v75;
      v75 = (__int64)&v75;
      v10 = (union _SLIST_HEADER *)(v8 + 16 * (v9 + 20LL));
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v11 = InterlockedPopEntrySList(v10);
            v12 = v11;
            if ( !v11 )
            {
              v7 = 0;
              goto LABEL_7;
            }
            v22 = ((__int64)v11[6].Next & 7) == 0;
            v23 = (__int64)v11[6].Next & 7;
            v11->Next = 0;
            *((_QWORD *)&v11->Next + 1) = 0;
            if ( !v22 )
              break;
            *((_QWORD *)&v11->Next + 1) = v74;
            *(_QWORD *)v74 = v11;
            v74 = (struct SOS_ParentBlockDescriptor *)v11;
            v11->Next = (struct _SLIST_ENTRY *)&v73;
          }
          v24 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v25) = v24 - 1;
          v26 = (unsigned __int64)v11[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v26 != v11[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v25 = v26 >> *(_WORD *)(a1 + 90);
            }
            else if ( v26 )
            {
              LODWORD(v25) = v26 - 1;
            }
            else
            {
              LODWORD(v25) = 0;
            }
          }
          if ( v26 > *((_QWORD *)&v11[4].Next + 1) )
            LODWORD(v25) = v24 + v25;
          v27 = v25 + 4;
          if ( (unsigned int)v25 >= 4 )
            v27 = v25;
          if ( v27 <= v9 )
            break;
          HIWORD(v12[5].Next) = v27;
          InterlockedPushEntrySList((PSLIST_HEADER)(v8 + 16 * ((unsigned int)(v27 - 4) + 24LL)), v12);
        }
        if ( (_DWORD)v23 != 4 )
        {
          v28 = (unsigned __int64)v12[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
          v29 = 1;
          if ( a5 )
            v29 = 6;
          do
          {
            v30 = v28;
            v31 = _InterlockedCompareExchange64((volatile signed __int64 *)&v12[6], v28 | v29, v28 | 2);
            v28 = v31 & 0xFFFFFFFFFFFFFFF8uLL;
          }
          while ( (v31 & 0xFFFFFFFFFFFFFFF8uLL) != v30 );
          if ( (v31 & 7) == 2 )
            break;
        }
        *((_QWORD *)&v12->Next + 1) = ListEntry;
        ListEntry->Next = v12;
        ListEntry = v12;
        v12->Next = (struct _SLIST_ENTRY *)&v75;
      }
      HIWORD(v12[5].Next) = -1;
      v7 = v12;
LABEL_7:
      while ( 1 )
      {
        v13 = ListEntry;
        if ( ListEntry == (PSLIST_ENTRY)&v75 || !ListEntry )
          break;
        v50 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&ListEntry->Next + 1);
        Next = ListEntry->Next;
        *((_QWORD *)&Next->Next + 1) = v50;
        *(_QWORD *)v50 = Next;
        *((_QWORD *)&v13->Next + 1) = 0;
        v13->Next = 0;
        if ( ((__int64)v13[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v10, v13);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v50, (struct SOS_ParentBlockDescriptor *)v13);
      }
      ++v9;
      v8 = v79;
      if ( v7 )
        goto LABEL_10;
      v6 = 0;
    }
  }
  else
  {
    v56 = 7;
    while ( (unsigned int)v56 >= 4 )
    {
      v72 = 0;
      v78 = (PSLIST_ENTRY)&v77;
      v77 = (__int64)&v77;
      v57 = (union _SLIST_HEADER *)(v8 + 16 * (v56 + 20LL));
      while ( 1 )
      {
        v58 = InterlockedPopEntrySList(v57);
        v59 = v58;
        if ( !v58 )
          break;
        v22 = ((__int64)v58[6].Next & 7) == 0;
        v60 = (__int64)v58[6].Next & 7;
        v58->Next = 0;
        *((_QWORD *)&v58->Next + 1) = 0;
        if ( v22 )
        {
          *((_QWORD *)&v58->Next + 1) = v74;
          *(_QWORD *)v74 = v58;
          v74 = (struct SOS_ParentBlockDescriptor *)v58;
          v58->Next = (struct _SLIST_ENTRY *)&v73;
        }
        else
        {
          v61 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v62) = v61 - 1;
          v63 = (unsigned __int64)v58[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v63 != v58[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v62 = v63 >> *(_WORD *)(a1 + 90);
            }
            else if ( v63 )
            {
              LODWORD(v62) = v63 - 1;
            }
            else
            {
              LODWORD(v62) = 0;
            }
          }
          if ( v63 > *((_QWORD *)&v58[4].Next + 1) )
            LODWORD(v62) = v61 + v62;
          v64 = v62 + 4;
          if ( (unsigned int)v62 >= 4 )
            v64 = v62;
          if ( v64 > v56 )
          {
            HIWORD(v59[5].Next) = v64;
            InterlockedPushEntrySList((PSLIST_HEADER)(v8 + 16 * ((unsigned int)(v64 - 4) + 24LL)), v59);
          }
          else
          {
            if ( (_DWORD)v60 != 4 )
            {
              v65 = (unsigned __int64)v59[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
              v66 = 1;
              if ( a5 )
                v66 = 6;
              do
              {
                v67 = v65;
                v68 = _InterlockedCompareExchange64((volatile signed __int64 *)&v59[6], v65 | v66, v65 | 2);
                v65 = v68 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v68 & 0xFFFFFFFFFFFFFFF8uLL) != v67 );
              if ( (v68 & 7) == 2 )
              {
                HIWORD(v59[5].Next) = -1;
                v7 = v59;
                v72 = v59;
                goto LABEL_111;
              }
            }
            *((_QWORD *)&v59->Next + 1) = v78;
            v78->Next = v59;
            v78 = v59;
            v59->Next = (struct _SLIST_ENTRY *)&v77;
          }
        }
      }
      v7 = 0;
LABEL_111:
      while ( 1 )
      {
        v69 = v78;
        if ( v78 == (PSLIST_ENTRY)&v77 || !v78 )
          break;
        v70 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&v78->Next + 1);
        v71 = v78->Next;
        *((_QWORD *)&v71->Next + 1) = v70;
        *(_QWORD *)v70 = v71;
        *((_QWORD *)&v69->Next + 1) = 0;
        v69->Next = 0;
        if ( ((__int64)v69[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v57, v69);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v70, (struct SOS_ParentBlockDescriptor *)v69);
      }
      --v56;
      v8 = v79;
      if ( v7 )
        goto LABEL_10;
      v6 = 0;
    }
  }
  if ( a3 )
  {
    v82 = v8 + 304;
    v83 = 0;
    v16.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v8 + 304)
      || _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 304), UniqueThread_low, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v52 && *(_QWORD *)(v52 + 272) == v52 )
          v6 = *(_QWORD *)(v52 + 256);
        if ( v6 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v16 = PerformanceCount;
          }
          else
          {
            v16.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      v53 = (SpinlockBase *)(v8 + 304);
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<49,1,268435714>::SpinToAcquireWithExponentialBackoff(v53);
      else
        Spinlock<49,1,268435714>::SpinToAcquireOptimistic(v53, v6, UniqueThread_low);
      if ( v6 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v81);
          v54 = v81;
        }
        else
        {
          v54.QuadPart = MEMORY[0x7FFE0008];
        }
        v55 = 0;
        if ( v54.QuadPart >= (unsigned __int64)v16.QuadPart )
          v55 = v54.QuadPart - v16.QuadPart;
        *(_QWORD *)(v6 + 3192) += v55;
      }
    }
    v83 = 1;
    v18 = 0;
    v19 = v8 + 312;
    v20 = v79;
    v7 = v72;
    do
    {
      if ( (unsigned int)v18 >= 4 )
        break;
      v21 = *(struct SOS_ParentBlockDescriptor ***)(v19 + 8);
      if ( v21 != (struct SOS_ParentBlockDescriptor **)v19 )
      {
        while ( v21 )
        {
          v36 = v21;
          v37 = (struct SOS_ParentBlockDescriptor *)v21;
          v38 = v21 + 1;
          v21 = (struct SOS_ParentBlockDescriptor **)v21[1];
          if ( v21 == (struct SOS_ParentBlockDescriptor **)v19 )
            v21 = 0;
          if ( (*((_QWORD *)v37 + 12) & 7) != 0 )
          {
            v39 = *(unsigned __int16 *)(a1 + 88);
            LODWORD(v40) = v39 - 1;
            v41 = (unsigned __int64)v36[12] >> 3;
            if ( (struct SOS_ParentBlockDescriptor *)v41 != v36[8] )
            {
              if ( *(_WORD *)(a1 + 90) )
              {
                v40 = v41 >> *(_WORD *)(a1 + 90);
              }
              else if ( v41 )
              {
                LODWORD(v40) = v41 - 1;
              }
              else
              {
                LODWORD(v40) = 0;
              }
            }
            if ( v41 > (unsigned __int64)v36[9] )
              LODWORD(v40) = v39 + v40;
            if ( (int)v40 > v18 )
            {
              *((_WORD *)v36 + 43) = v40;
              v47 = *(_QWORD *)v37;
              v48 = *v38;
              *(_QWORD *)(v47 + 8) = *v38;
              *(_QWORD *)v48 = v47;
              if ( (unsigned int)v40 >= 4 )
              {
                *v38 = 0;
                *v36 = 0;
                InterlockedPushEntrySList(
                  (PSLIST_HEADER)(v20 + 16 * ((unsigned int)(v40 - 4) + 24LL)),
                  (PSLIST_ENTRY)v36);
              }
              else
              {
                v49 = 16LL * (int)v40 + v20 + 312;
                *v38 = *(struct SOS_ParentBlockDescriptor **)(v49 + 8);
                **(_QWORD **)(v49 + 8) = v36;
                *(_QWORD *)(v49 + 8) = v36;
                *v36 = (struct SOS_ParentBlockDescriptor *)v49;
              }
            }
            else if ( (*((_DWORD *)v37 + 24) & 7) != 4 )
            {
              v42 = (unsigned __int64)v36[12] & 0xFFFFFFFFFFFFFFF8uLL;
              do
              {
                v43 = v42;
                v44 = _InterlockedCompareExchange64((volatile signed __int64 *)v36 + 12, v42 | 1, v42 | 2);
                v42 = v44 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v44 & 0xFFFFFFFFFFFFFFF8uLL) != v43 );
              if ( (v44 & 7) == 2 )
              {
                v45 = v36[1];
                v46 = *v36;
                *((_QWORD *)v46 + 1) = v45;
                *(_QWORD *)v45 = v46;
                v36[1] = 0;
                *v36 = 0;
                *((_WORD *)v36 + 43) = -1;
                v7 = (PSLIST_ENTRY)v36;
                v72 = (PSLIST_ENTRY)v36;
                goto LABEL_19;
              }
            }
          }
          else
          {
            v34 = *v38;
            v35 = *(_QWORD *)v37;
            *(_QWORD *)(v35 + 8) = *v38;
            *(_QWORD *)v34 = v35;
            *v38 = v74;
            *(_QWORD *)v74 = v37;
            v74 = v37;
            *(_QWORD *)v37 = &v73;
          }
        }
      }
      v7 = v72;
LABEL_19:
      ++v18;
      v19 += 16;
    }
    while ( !v7 );
    SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(&v82);
  }
LABEL_10:
  while ( 1 )
  {
    v14 = v74;
    if ( v74 == (struct SOS_ParentBlockDescriptor *)&v73 || !v74 )
      break;
    v32 = (SOS_MemoryBlockAllocator *)*((_QWORD *)v74 + 1);
    v33 = *(_QWORD *)v74;
    *(_QWORD *)(v33 + 8) = v32;
    *(_QWORD *)v32 = v33;
    *((_QWORD *)v14 + 1) = 0;
    *(_QWORD *)v14 = 0;
    SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v32, v14);
  }
  return v7;
}

```

## disassembly

```asm
0x100416c50  mov     rax, rsp
0x100416c53  mov     [rax+8], rcx
0x100416c57  push    rbp
0x100416c58  push    r12
0x100416c5a  push    r13
0x100416c5c  push    r14
0x100416c5e  push    r15
0x100416c60  lea     rbp, [rax-57h]
0x100416c64  sub     rsp, 90h
0x100416c6b  mov     [rbp+4Fh+var_30], 0FFFFFFFFFFFFFFFEh
0x100416c73  mov     [rax+10h], rbx
0x100416c77  mov     [rax+18h], rsi
0x100416c7b  mov     [rax+20h], rdi
0x100416c7f  movzx   r12d, r8b
0x100416c83  xor     edi, edi
0x100416c85  mov     ebx, edi
0x100416c87  mov     [rbp+4Fh+var_90], rbx
0x100416c8b  lea     rax, [rbp+4Fh+var_88]
0x100416c8f  mov     [rbp+4Fh+var_80], rax
0x100416c93  lea     rax, [rbp+4Fh+var_88]
0x100416c97  mov     [rbp+4Fh+var_88], rax
0x100416c9b  movzx   r13d, dx
0x100416c9f  shl     r13, 8
0x100416ca3  add     r13, rcx
0x100416ca6  mov     [rbp+4Fh+var_58], r13
0x100416caa  lea     r15d, [rdi+6]
0x100416cae  movzx   r14d, [rbp+4Fh+arg_20]
0x100416cb3  test    r9b, r9b
0x100416cb6  jz      loc_10049369F
0x100416cbc  lea     esi, [rdi+4]
0x100416cbf  jmp     short loc_100416CC2
0x100416cc2  mov     [rbp+4Fh+var_90], rbx
0x100416cc6  cmp     esi, 8
0x100416cc9  jnb     loc_100416D75
0x100416ccf  mov     [rbp+4Fh+var_90], rdi
0x100416cd3  lea     rcx, [rbp+4Fh+var_78]
0x100416cd7  mov     [rbp+4Fh+ListEntry], rcx
0x100416cdb  lea     rax, [rbp+4Fh+var_78]
0x100416cdf  mov     [rbp+4Fh+var_78], rax
0x100416ce3  movsxd  rdi, esi
0x100416ce6  add     rdi, 14h
0x100416cea  shl     rdi, 4
0x100416cee  add     rdi, r13
0x100416cf1  mov     rcx, rdi; ListHead
0x100416cf4  call    cs:__imp_InterlockedPopEntrySList
0x100416cfa  mov     r8, rax
0x100416cfd  test    rax, rax
0x100416d00  jnz     loc_100422502
0x100416d06  mov     rbx, [rbp+4Fh+var_90]
0x100416d0a  xor     r13d, r13d
0x100416d0d  lea     rax, [rbp+4Fh+var_78]
0x100416d11  mov     rdx, [rbp+4Fh+ListEntry]; struct SOS_ParentBlockDescriptor *
0x100416d15  cmp     rdx, rax
0x100416d18  jnz     loc_1004935A4
0x100416d1e  inc     esi
0x100416d20  test    rbx, rbx
0x100416d23  mov     r13, [rbp+4Fh+var_58]
0x100416d27  jnz     short loc_100416D2E
0x100416d29  xor     edi, edi
0x100416d2b  jmp     short loc_100416CC2
0x100416d2e  jmp     short loc_100416D40
0x100416d40  lea     rax, [rbp+4Fh+var_88]
0x100416d44  mov     rdx, [rbp+4Fh+var_80]; struct SOS_ParentBlockDescriptor *
0x100416d48  cmp     rdx, rax
0x100416d4b  jnz     loc_1004286D3
0x100416d51  mov     rax, rbx
0x100416d54  lea     r11, [rsp+0B0h+var_20]
0x100416d5c  mov     rbx, [r11+38h]
0x100416d60  mov     rsi, [r11+40h]
0x100416d64  mov     rdi, [r11+48h]
0x100416d68  mov     rsp, r11
0x100416d6b  pop     r15
0x100416d6d  pop     r14
0x100416d6f  pop     r13
0x100416d71  pop     r12
0x100416d73  pop     rbp
0x100416d74  retn
0x100416d75  test    rbx, rbx
0x100416d78  jnz     short loc_100416D40
0x100416d7a  test    r12b, r12b
0x100416d7d  jz      short loc_100416D40
0x100416d7f  lea     rsi, [r13+130h]
0x100416d86  mov     [rbp+4Fh+var_40], rsi
0x100416d8a  mov     [rbp+4Fh+var_38], edi
0x100416d8d  mov     rbx, rdi
0x100416d90  mov     eax, gs:48h
0x100416d98  mov     r14d, eax
0x100416d9b  mov     eax, [rsi]
0x100416d9d  test    eax, eax
0x100416d9f  jnz     loc_1004935E3
0x100416da5  xor     eax, eax
0x100416da7  lock cmpxchg [rsi], r14
0x100416dac  mov     eax, edi
0x100416dae  setz    al
0x100416db1  test    eax, eax
0x100416db3  jz      loc_1004935E3
0x100416db9  mov     [rbp+4Fh+var_38], 1
0x100416dc0  mov     r15d, edi
0x100416dc3  add     r13, 138h
0x100416dca  mov     r12, [rbp+4Fh+var_58]
0x100416dce  mov     rbx, [rbp+4Fh+var_90]
0x100416dd2  cmp     r15d, 4
0x100416dd6  jnb     short loc_100416DF5
0x100416dd8  mov     rbx, [r13+8]
0x100416ddc  cmp     rbx, r13
0x100416ddf  jnz     loc_10042DE25
0x100416de5  mov     rbx, [rbp+4Fh+var_90]
0x100416de9  inc     r15d
0x100416dec  add     r13, 10h
0x100416df0  test    rbx, rbx
0x100416df3  jz      short loc_100416DD2
0x100416df5  lea     rcx, [rbp+4Fh+var_40]
0x100416df9  call    ??1?$SpinlockHolder@$0DB@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(void)
0x100416dfe  nop     word ptr [rax+rax]
0x100416e03  jmp     loc_100416D40
0x100422502  mov     r10, [rax+60h]
0x100422506  and     r10d, 7
0x10042250a  mov     eax, 0
0x10042250f  mov     [r8], rax
0x100422512  mov     [r8+8], rax
0x100422516  jz      loc_1004286B3
0x10042251c  mov     rcx, [rbp+4Fh+arg_0]
0x100422520  movzx   r11d, word ptr [rcx+58h]
0x100422525  lea     edx, [r11-1]
0x100422529  mov     rax, [r8+40h]
0x10042252d  movzx   ecx, word ptr [rcx+5Ah]
0x100422531  mov     r9, [r8+60h]
0x100422535  shr     r9, 3
0x100422539  mov     rbx, [r8+48h]
0x10042253d  cmp     r9, rax
0x100422540  jz      short loc_100422554
0x100422542  test    rcx, rcx
0x100422545  jz      loc_100422F9C
0x10042254b  mov     rdx, r9
0x10042254e  shr     rdx, cl
0x100422551  jmp     short loc_100422554
0x100422554  cmp     r9, rbx
0x100422557  jbe     short loc_10042255C
0x100422559  add     edx, r11d
0x10042255c  lea     eax, [rdx+4]
0x10042255f  cmp     edx, 4
0x100422562  cmovnb  eax, edx
0x100422565  cmp     eax, esi
0x100422567  jg      short loc_1004225CF
0x100422569  cmp     r10d, 4
0x10042256d  jz      loc_100493584
0x100422573  mov     r9, [r8+60h]
0x100422577  and     r9, 0FFFFFFFFFFFFFFF8h
0x10042257b  mov     r10d, 1
0x100422581  test    r14b, r14b
0x100422584  cmovnz  r10, r15
0x100422588  nop     dword ptr [rax+rax+00000000h]
0x100422590  mov     rdx, r9
0x100422593  mov     rax, r9
0x100422596  or      rax, 2
0x10042259a  mov     rcx, r10
0x10042259d  or      rcx, r9
0x1004225a0  lock cmpxchg [r8+60h], rcx
0x1004225a6  mov     r9, rax
0x1004225a9  and     r9, 0FFFFFFFFFFFFFFF8h
0x1004225ad  cmp     r9, rdx
0x1004225b0  jnz     short loc_100422590
0x1004225b2  and     al, 7
0x1004225b4  cmp     al, 2
0x1004225b6  jnz     loc_100493584
0x1004225bc  mov     eax, 0FFFFh
0x1004225c1  mov     [r8+56h], ax
0x1004225c6  mov     rbx, r8
0x1004225c9  jmp     loc_100416D0A
0x1004225cf  mov     [r8+56h], ax
0x1004225d4  add     eax, 0FFFFFFFCh
0x1004225d7  mov     ecx, eax
0x1004225d9  add     rcx, 18h
0x1004225dd  shl     rcx, 4
0x1004225e1  add     rcx, r13; ListHead
0x1004225e4  mov     rdx, r8; ListEntry
0x1004225e7  call    cs:__imp_InterlockedPushEntrySList
0x1004225ed  jmp     loc_100416CF1
0x100422f9c  test    r9, r9
0x100422f9f  jz      loc_10049357A
0x100422fa5  lea     edx, [r9-1]
0x100422fa9  jmp     loc_100422554
0x1004286b3  mov     rax, [rbp+4Fh+var_80]
0x1004286b7  mov     [r8+8], rax
0x1004286bb  mov     rax, [rbp+4Fh+var_80]
0x1004286bf  mov     [rax], r8
0x1004286c2  mov     [rbp+4Fh+var_80], r8
0x1004286c6  lea     rax, [rbp+4Fh+var_88]
0x1004286ca  mov     [r8], rax
0x1004286cd  jmp     loc_100416CF1
0x1004286d3  test    rdx, rdx
0x1004286d6  jz      loc_100416D51
0x1004286dc  mov     rcx, [rdx+8]; this
0x1004286e0  mov     rax, [rdx]
0x1004286e3  mov     [rax+8], rcx
0x1004286e7  mov     [rcx], rax
0x1004286ea  xor     eax, eax
0x1004286ec  mov     [rdx+8], rax
0x1004286f0  mov     [rdx], rax
0x1004286f3  call    ?ReleaseEmptyDescriptor@SOS_MemoryBlockAllocator@@IEAAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(SOS_ParentBlockDescriptor *)
0x1004286f8  jmp     loc_100416D40
0x10042ddfc  mov     rcx, [r10]
0x10042ddff  mov     rax, [r14]
0x10042de02  mov     [rax+8], rcx
0x10042de06  mov     [rcx], rax
0x10042de09  mov     rax, [rbp+4Fh+var_80]
0x10042de0d  mov     [r10], rax
0x10042de10  mov     rax, [rbp+4Fh+var_80]
0x10042de14  mov     [rax], r14
0x10042de17  mov     [rbp+4Fh+var_80], r14
0x10042de1b  lea     rax, [rbp+4Fh+var_88]
0x10042de1f  mov     [r14], rax
0x10042de22  jmp     short loc_10042DE25
0x10042de25  test    rbx, rbx
0x10042de28  jz      loc_100416DE5
0x10042de2e  mov     r8, rbx
0x10042de31  mov     r14, rbx
0x10042de34  lea     r10, [rbx+8]
0x10042de38  mov     rbx, [r10]
0x10042de3b  cmp     rbx, r13
0x10042de3e  cmovz   rbx, rdi
0x10042de42  mov     r11, [r14+60h]
0x10042de46  and     r11d, 7
0x10042de4a  jz      short loc_10042DDFC
0x10042de4c  mov     rcx, [rbp+4Fh+arg_0]
0x10042de50  movzx   edi, word ptr [rcx+58h]
0x10042de54  lea     edx, [rdi-1]
0x10042de57  mov     rax, [r8+40h]
0x10042de5b  movzx   ecx, word ptr [rcx+5Ah]
0x10042de5f  mov     r9, [r8+60h]
0x10042de63  shr     r9, 3
0x10042de67  mov     rsi, [r8+48h]
0x10042de6b  cmp     r9, rax
0x10042de6e  jz      short loc_10042DE82
0x10042de70  test    rcx, rcx
0x10042de73  jz      loc_10042E5D7
0x10042de79  mov     rdx, r9
0x10042de7c  shr     rdx, cl
0x10042de7f  jmp     short loc_10042DE82
0x10042de82  cmp     r9, rsi
0x10042de85  ja      loc_1004938D2
0x10042de8b  cmp     edx, r15d
0x10042de8e  jg      short loc_10042DF07
0x10042de90  cmp     r11d, 4
0x10042de94  jz      loc_10042DF49
0x10042de9a  mov     rcx, [r8+60h]
0x10042de9e  and     rcx, 0FFFFFFFFFFFFFFF8h
0x10042dea2  nop     dword ptr [rax+00h]
0x10042dea6  nop     word ptr [rax+rax+00000000h]
0x10042deb0  mov     rdx, rcx
0x10042deb3  mov     rax, rcx
0x10042deb6  or      rax, 2
0x10042deba  or      rcx, 1
0x10042debe  lock cmpxchg [r8+60h], rcx
0x10042dec4  mov     rcx, rax
0x10042dec7  and     rcx, 0FFFFFFFFFFFFFFF8h
0x10042decb  cmp     rcx, rdx
0x10042dece  jnz     short loc_10042DEB0
0x10042ded0  and     al, 7
0x10042ded2  xor     edi, edi
0x10042ded4  cmp     al, 2
0x10042ded6  jnz     loc_10042DE25
0x10042dedc  mov     rcx, [r8+8]
0x10042dee0  mov     rax, [r8]
0x10042dee3  mov     [rax+8], rcx
0x10042dee7  mov     [rcx], rax
0x10042deea  mov     [r8+8], rdi
0x10042deee  mov     [r8], rdi
0x10042def1  mov     eax, 0FFFFh
0x10042def6  mov     [r8+56h], ax
0x10042defb  mov     rbx, r8
0x10042defe  mov     [rbp+4Fh+var_90], rbx
0x10042df02  jmp     loc_100416DE9
0x10042df07  mov     [r8+56h], dx
0x10042df0c  mov     r11, [r14]
0x10042df0f  mov     r9, [r10]
0x10042df12  mov     [r11+8], r9
0x10042df16  mov     [r9], r11
0x10042df19  cmp     edx, 4
0x10042df1c  jnb     loc_1004938DA
0x10042df22  movsxd  rax, edx
0x10042df25  shl     rax, 4
0x10042df29  lea     rcx, [r12+138h]
0x10042df31  add     rcx, rax
0x10042df34  mov     rax, [rcx+8]
0x10042df38  mov     [r10], rax
0x10042df3b  mov     rax, [rcx+8]
0x10042df3f  mov     [rax], r8
0x10042df42  mov     [rcx+8], r8
0x10042df46  mov     [r8], rcx
0x10042df49  xor     edi, edi
0x10042df4b  jmp     loc_10042DE25
0x10042e5d7  test    r9, r9
0x10042e5da  jz      loc_1004938C8
0x10042e5e0  lea     edx, [r9-1]
0x10042e5e4  jmp     loc_10042DE82
0x10049357a  xor     eax, eax
0x10049357c  mov     edx, eax
0x10049357e  jmp     loc_100422554
0x100493584  mov     rax, [rbp+4Fh+ListEntry]
  ... truncated ...
```
