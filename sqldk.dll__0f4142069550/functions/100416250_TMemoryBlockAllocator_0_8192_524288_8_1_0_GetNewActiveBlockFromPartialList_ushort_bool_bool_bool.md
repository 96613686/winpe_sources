# TMemoryBlockAllocator<0,8192,524288,8,1,0>::GetNewActiveBlockFromPartialList(ushort,bool,bool,bool)

- ea: `0x100416250`
- end: `0x100416342`
- name: `?GetNewActiveBlockFromPartialList@?$TMemoryBlockAllocator@$0A@$0CAAA@$0IAAAA@$07$00$0A@@@EEAAPEAVSOS_ParentBlockDescriptor@@G_N00@Z`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100416250`
- `0x100416390`
- `0x100422880`
- `0x100431e70`
- `0x100494e40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x100415589`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049244d`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492619`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492681`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049273b`
- `KERNEL32!InterlockedPushEntrySList` at `0x100415589`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049244d`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492619`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492681`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049273b`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004162fe`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004924e3`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004162fe`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004924e3`
- `KERNEL32!QueryPerformanceCounter` at `0x10049249e`
- `KERNEL32!QueryPerformanceCounter` at `0x1004926ce`
- `KERNEL32!QueryPerformanceCounter` at `0x10049249e`
- `KERNEL32!QueryPerformanceCounter` at `0x1004926ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall TMemoryBlockAllocator<0,8192,524288,8,1,0>::GetNewActiveBlockFromPartialList(
        __int64 a1,
        unsigned __int16 a2,
        char a3,
        char a4,
        char a5)
{
  __int64 v6; // rdi
  PSLIST_ENTRY v7; // rbx
  __int64 v8; // rax
  SpinlockBase *v9; // r12
  signed int v10; // esi
  union _SLIST_HEADER *v11; // rdi
  PSLIST_ENTRY v12; // rax
  PSLIST_ENTRY v13; // r8
  PSLIST_ENTRY v14; // rdx
  struct SOS_ParentBlockDescriptor *v15; // rdx
  bool v17; // zf
  __int64 v18; // r10
  int v19; // r11d
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r9
  signed int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // r10
  unsigned __int64 v25; // rdx
  signed __int64 v26; // rax
  LARGE_INTEGER v27; // rbx
  signed __int64 UniqueThread_low; // rsi
  int v29; // r15d
  __int64 v30; // r12
  __int64 v31; // r13
  struct SOS_ParentBlockDescriptor **v32; // rbx
  SOS_MemoryBlockAllocator *v33; // rcx
  __int64 v34; // rax
  struct SOS_ParentBlockDescriptor *v35; // rcx
  __int64 v36; // rax
  struct SOS_ParentBlockDescriptor **v37; // r8
  struct SOS_ParentBlockDescriptor *v38; // r14
  struct SOS_ParentBlockDescriptor **v39; // r10
  int v40; // edi
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // r9
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  signed __int64 v45; // rax
  struct SOS_ParentBlockDescriptor *v46; // rcx
  struct SOS_ParentBlockDescriptor *v47; // rax
  __int64 v48; // r11
  struct SOS_ParentBlockDescriptor *v49; // r9
  __int64 v50; // rcx
  SOS_MemoryBlockAllocator *v51; // rcx
  struct _SLIST_ENTRY *Next; // rax
  __int64 v53; // rdx
  signed int v54; // esi
  union _SLIST_HEADER *v55; // rdi
  PSLIST_ENTRY v56; // rax
  PSLIST_ENTRY v57; // r8
  __int64 v58; // r10
  int v59; // r11d
  unsigned __int64 v60; // rdx
  unsigned __int64 v61; // r9
  signed int v62; // eax
  unsigned __int64 v63; // r9
  __int64 v64; // r10
  unsigned __int64 v65; // rdx
  signed __int64 v66; // rax
  PSLIST_ENTRY v67; // rdx
  SOS_MemoryBlockAllocator *v68; // rcx
  struct _SLIST_ENTRY *v69; // rax
  LARGE_INTEGER v70; // rcx
  LONGLONG v71; // rax
  PSLIST_ENTRY v72; // [rsp+28h] [rbp-41h]
  __int64 v73; // [rsp+30h] [rbp-39h] BYREF
  struct SOS_ParentBlockDescriptor *v74; // [rsp+38h] [rbp-31h]
  __int64 v75; // [rsp+40h] [rbp-29h]
  __int64 v76; // [rsp+48h] [rbp-21h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+50h] [rbp-19h]
  __int64 v78; // [rsp+58h] [rbp-11h] BYREF
  PSLIST_ENTRY v79; // [rsp+60h] [rbp-9h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-1h] BYREF
  LARGE_INTEGER v81; // [rsp+70h] [rbp+7h] BYREF
  SpinlockBase *v82; // [rsp+78h] [rbp+Fh] BYREF
  int v83; // [rsp+80h] [rbp+17h]
  __int64 v84; // [rsp+88h] [rbp+1Fh]

  v84 = -2;
  v6 = 0;
  v7 = 0;
  v72 = 0;
  v74 = (struct SOS_ParentBlockDescriptor *)&v73;
  v73 = (__int64)&v73;
  v8 = a1 + 320LL * a2;
  v75 = v8;
  v9 = (SpinlockBase *)(v8 + 256);
  if ( a4 )
  {
    v10 = 8;
    while ( 1 )
    {
      v72 = 0;
      if ( (unsigned int)v10 >= 0x10 )
        break;
      ListEntry = (PSLIST_ENTRY)&v76;
      v76 = (__int64)&v76;
      v11 = (union _SLIST_HEADER *)(v8 + 16 * (v10 + 17LL));
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
            v17 = ((__int64)v12[6].Next & 7) == 0;
            v18 = (__int64)v12[6].Next & 7;
            v12->Next = 0;
            *((_QWORD *)&v12->Next + 1) = 0;
            if ( !v17 )
              break;
            *((_QWORD *)&v12->Next + 1) = v74;
            *(_QWORD *)v74 = v12;
            v74 = (struct SOS_ParentBlockDescriptor *)v12;
            v12->Next = (struct _SLIST_ENTRY *)&v73;
          }
          v19 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v20) = v19 - 1;
          v21 = (unsigned __int64)v12[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v21 != v12[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v20 = v21 >> *(_WORD *)(a1 + 90);
            }
            else if ( v21 )
            {
              LODWORD(v20) = v21 - 1;
            }
            else
            {
              LODWORD(v20) = 0;
            }
          }
          if ( v21 > *((_QWORD *)&v12[4].Next + 1) )
            LODWORD(v20) = v19 + v20;
          v22 = v20 + 8;
          if ( (unsigned int)v20 >= 8 )
            v22 = v20;
          if ( v22 <= v10 )
            break;
          HIWORD(v13[5].Next) = v22;
          InterlockedPushEntrySList((PSLIST_HEADER)(v75 + 16 * ((unsigned int)(v22 - 8) + 25LL)), v13);
        }
        if ( (_DWORD)v18 != 4 )
        {
          v23 = (unsigned __int64)v13[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
          v24 = 1;
          if ( a5 )
            v24 = 6;
          do
          {
            v25 = v23;
            v26 = _InterlockedCompareExchange64((volatile signed __int64 *)&v13[6], v23 | v24, v23 | 2);
            v23 = v26 & 0xFFFFFFFFFFFFFFF8uLL;
          }
          while ( (v26 & 0xFFFFFFFFFFFFFFF8uLL) != v25 );
          if ( (v26 & 7) == 2 )
            break;
        }
        *((_QWORD *)&v13->Next + 1) = ListEntry;
        ListEntry->Next = v13;
        ListEntry = v13;
        v13->Next = (struct _SLIST_ENTRY *)&v76;
      }
      HIWORD(v13[5].Next) = -1;
      v7 = v13;
LABEL_7:
      while ( 1 )
      {
        v14 = ListEntry;
        if ( ListEntry == (PSLIST_ENTRY)&v76 || !ListEntry )
          break;
        v51 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&ListEntry->Next + 1);
        Next = ListEntry->Next;
        *((_QWORD *)&Next->Next + 1) = v51;
        *(_QWORD *)v51 = Next;
        *((_QWORD *)&v14->Next + 1) = 0;
        v14->Next = 0;
        if ( ((__int64)v14[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v11, v14);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v51, (struct SOS_ParentBlockDescriptor *)v14);
      }
      ++v10;
      v8 = v75;
      v9 = (SpinlockBase *)(v75 + 256);
      if ( v7 )
        goto LABEL_12;
      v6 = 0;
    }
  }
  else
  {
    v54 = 15;
    while ( (unsigned int)v54 >= 8 )
    {
      v72 = 0;
      v79 = (PSLIST_ENTRY)&v78;
      v78 = (__int64)&v78;
      v55 = (union _SLIST_HEADER *)(v8 + 16 * (v54 + 17LL));
      while ( 1 )
      {
        v56 = InterlockedPopEntrySList(v55);
        v57 = v56;
        if ( !v56 )
          break;
        v17 = ((__int64)v56[6].Next & 7) == 0;
        v58 = (__int64)v56[6].Next & 7;
        v56->Next = 0;
        *((_QWORD *)&v56->Next + 1) = 0;
        if ( v17 )
        {
          *((_QWORD *)&v56->Next + 1) = v74;
          *(_QWORD *)v74 = v56;
          v74 = (struct SOS_ParentBlockDescriptor *)v56;
          v56->Next = (struct _SLIST_ENTRY *)&v73;
        }
        else
        {
          v59 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v60) = v59 - 1;
          v61 = (unsigned __int64)v56[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v61 != v56[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v60 = v61 >> *(_WORD *)(a1 + 90);
            }
            else if ( v61 )
            {
              LODWORD(v60) = v61 - 1;
            }
            else
            {
              LODWORD(v60) = 0;
            }
          }
          if ( v61 > *((_QWORD *)&v56[4].Next + 1) )
            LODWORD(v60) = v59 + v60;
          v62 = v60 + 8;
          if ( (unsigned int)v60 >= 8 )
            v62 = v60;
          if ( v62 > v54 )
          {
            HIWORD(v57[5].Next) = v62;
            InterlockedPushEntrySList((PSLIST_HEADER)(v75 + 16 * ((unsigned int)(v62 - 8) + 25LL)), v57);
          }
          else
          {
            if ( (_DWORD)v58 != 4 )
            {
              v63 = (unsigned __int64)v57[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
              v64 = 1;
              if ( a5 )
                v64 = 6;
              do
              {
                v65 = v63;
                v66 = _InterlockedCompareExchange64((volatile signed __int64 *)&v57[6], v63 | v64, v63 | 2);
                v63 = v66 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v66 & 0xFFFFFFFFFFFFFFF8uLL) != v65 );
              if ( (v66 & 7) == 2 )
              {
                HIWORD(v57[5].Next) = -1;
                v7 = v57;
                v72 = v57;
                goto LABEL_105;
              }
            }
            *((_QWORD *)&v57->Next + 1) = v79;
            v79->Next = v57;
            v79 = v57;
            v57->Next = (struct _SLIST_ENTRY *)&v78;
          }
        }
      }
      v7 = 0;
LABEL_105:
      while ( 1 )
      {
        v67 = v79;
        if ( v79 == (PSLIST_ENTRY)&v78 || !v79 )
          break;
        v68 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&v79->Next + 1);
        v69 = v79->Next;
        *((_QWORD *)&v69->Next + 1) = v68;
        *(_QWORD *)v68 = v69;
        *((_QWORD *)&v67->Next + 1) = 0;
        v67->Next = 0;
        if ( ((__int64)v67[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v55, v67);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v68, (struct SOS_ParentBlockDescriptor *)v67);
      }
      --v54;
      v8 = v75;
      v9 = (SpinlockBase *)(v75 + 256);
      if ( v7 )
        goto LABEL_12;
      v6 = 0;
    }
  }
  if ( a3 )
  {
    v82 = v9;
    v83 = 0;
    v27.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v9 || _InterlockedCompareExchange64((volatile signed __int64 *)v9, UniqueThread_low, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v53 && *(_QWORD *)(v53 + 272) == v53 )
          v6 = *(_QWORD *)(v53 + 256);
        if ( v6 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v27 = PerformanceCount;
          }
          else
          {
            v27.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<49,1,268435714>::SpinToAcquireWithExponentialBackoff(v9);
      else
        Spinlock<49,1,268435714>::SpinToAcquireOptimistic(v9, v6, UniqueThread_low);
      if ( v6 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v81);
          v70 = v81;
        }
        else
        {
          v70.QuadPart = MEMORY[0x7FFE0008];
        }
        v71 = 0;
        if ( v70.QuadPart >= (unsigned __int64)v27.QuadPart )
          v71 = v70.QuadPart - v27.QuadPart;
        *(_QWORD *)(v6 + 3192) += v71;
      }
    }
    v83 = 1;
    v29 = 0;
    v30 = v75;
    v31 = v75 + 264;
    v7 = v72;
    do
    {
      if ( (unsigned int)v29 >= 8 )
        break;
      v32 = *(struct SOS_ParentBlockDescriptor ***)(v31 + 8);
      if ( v32 != (struct SOS_ParentBlockDescriptor **)v31 )
      {
        while ( v32 )
        {
          v37 = v32;
          v38 = (struct SOS_ParentBlockDescriptor *)v32;
          v39 = v32 + 1;
          v32 = (struct SOS_ParentBlockDescriptor **)v32[1];
          if ( v32 == (struct SOS_ParentBlockDescriptor **)v31 )
            v32 = 0;
          if ( (*((_QWORD *)v38 + 12) & 7) != 0 )
          {
            v40 = *(unsigned __int16 *)(a1 + 88);
            LODWORD(v41) = v40 - 1;
            v42 = (unsigned __int64)v37[12] >> 3;
            if ( (struct SOS_ParentBlockDescriptor *)v42 != v37[8] )
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
            if ( v42 > (unsigned __int64)v37[9] )
              LODWORD(v41) = v40 + v41;
            if ( (int)v41 > v29 )
            {
              *((_WORD *)v37 + 43) = v41;
              v48 = *(_QWORD *)v38;
              v49 = *v39;
              *(_QWORD *)(v48 + 8) = *v39;
              *(_QWORD *)v49 = v48;
              if ( (unsigned int)v41 >= 8 )
              {
                *v39 = 0;
                *v37 = 0;
                InterlockedPushEntrySList(
                  (PSLIST_HEADER)(v30 + 16 * ((unsigned int)(v41 - 8) + 25LL)),
                  (PSLIST_ENTRY)v37);
              }
              else
              {
                v50 = 16LL * (int)v41 + v30 + 264;
                *v39 = *(struct SOS_ParentBlockDescriptor **)(v50 + 8);
                **(_QWORD **)(v50 + 8) = v37;
                *(_QWORD *)(v50 + 8) = v37;
                *v37 = (struct SOS_ParentBlockDescriptor *)v50;
              }
            }
            else if ( (*((_DWORD *)v38 + 24) & 7) != 4 )
            {
              v43 = (unsigned __int64)v37[12] & 0xFFFFFFFFFFFFFFF8uLL;
              do
              {
                v44 = v43;
                v45 = _InterlockedCompareExchange64((volatile signed __int64 *)v37 + 12, v43 | 1, v43 | 2);
                v43 = v45 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v45 & 0xFFFFFFFFFFFFFFF8uLL) != v44 );
              if ( (v45 & 7) == 2 )
              {
                v46 = v37[1];
                v47 = *v37;
                *((_QWORD *)v47 + 1) = v46;
                *(_QWORD *)v46 = v47;
                v37[1] = 0;
                *v37 = 0;
                *((_WORD *)v37 + 43) = -1;
                v7 = (PSLIST_ENTRY)v37;
                v72 = (PSLIST_ENTRY)v37;
                goto LABEL_36;
              }
            }
          }
          else
          {
            v35 = *v39;
            v36 = *(_QWORD *)v38;
            *(_QWORD *)(v36 + 8) = *v39;
            *(_QWORD *)v35 = v36;
            *v39 = v74;
            *(_QWORD *)v74 = v38;
            v74 = v38;
            *(_QWORD *)v38 = &v73;
          }
        }
      }
      v7 = v72;
LABEL_36:
      ++v29;
      v31 += 16;
    }
    while ( !v7 );
    SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(&v82);
  }
LABEL_12:
  while ( 1 )
  {
    v15 = v74;
    if ( v74 == (struct SOS_ParentBlockDescriptor *)&v73 || !v74 )
      break;
    v33 = (SOS_MemoryBlockAllocator *)*((_QWORD *)v74 + 1);
    v34 = *(_QWORD *)v74;
    *(_QWORD *)(v34 + 8) = v33;
    *(_QWORD *)v33 = v34;
    *((_QWORD *)v15 + 1) = 0;
    *(_QWORD *)v15 = 0;
    SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v33, v15);
  }
  return v7;
}

```

## disassembly

```asm
0x100416250  mov     rax, rsp
0x100416253  mov     [rax+8], rcx
0x100416257  push    rbp
0x100416258  push    r12
0x10041625a  push    r13
0x10041625c  push    r14
0x10041625e  push    r15
0x100416260  lea     rbp, [rax-57h]
0x100416264  sub     rsp, 90h
0x10041626b  mov     [rbp+4Fh+var_30], 0FFFFFFFFFFFFFFFEh
0x100416273  mov     [rax+10h], rbx
0x100416277  mov     [rax+18h], rsi
0x10041627b  mov     [rax+20h], rdi
0x10041627f  movzx   r13d, r8b
0x100416283  xor     edi, edi
0x100416285  mov     ebx, edi
0x100416287  mov     [rbp+4Fh+var_90], rbx
0x10041628b  lea     rax, [rbp+4Fh+var_88]
0x10041628f  mov     [rbp+4Fh+var_80], rax
0x100416293  lea     rax, [rbp+4Fh+var_88]
0x100416297  mov     [rbp+4Fh+var_88], rax
0x10041629b  movzx   eax, dx
0x10041629e  lea     rax, [rax+rax*4]
0x1004162a2  shl     rax, 6
0x1004162a6  add     rax, rcx
0x1004162a9  mov     [rbp+4Fh+var_78], rax
0x1004162ad  lea     r12, [rax+100h]
0x1004162b4  lea     r15d, [rdi+6]
0x1004162b8  movzx   r14d, [rbp+4Fh+arg_20]
0x1004162bd  test    r9b, r9b
0x1004162c0  jz      loc_1004924AD
0x1004162c6  lea     esi, [rdi+8]
0x1004162c9  jmp     short loc_1004162CC
0x1004162cc  mov     [rbp+4Fh+var_90], rbx
0x1004162d0  cmp     esi, 10h
0x1004162d3  jnb     loc_100416BA9
0x1004162d9  mov     [rbp+4Fh+var_90], rdi
0x1004162dd  lea     rdx, [rbp+4Fh+var_70]
0x1004162e1  mov     [rbp+4Fh+ListEntry], rdx
0x1004162e5  lea     rcx, [rbp+4Fh+var_70]
0x1004162e9  mov     [rbp+4Fh+var_70], rcx
0x1004162ed  movsxd  rdi, esi
0x1004162f0  add     rdi, 11h
0x1004162f4  shl     rdi, 4
0x1004162f8  add     rdi, rax
0x1004162fb  mov     rcx, rdi; ListHead
0x1004162fe  call    cs:__imp_InterlockedPopEntrySList
0x100416304  mov     r8, rax
0x100416307  test    rax, rax
0x10041630a  jnz     loc_1004163F6
0x100416310  mov     rbx, [rbp+4Fh+var_90]
0x100416314  xor     r12d, r12d
0x100416317  lea     rax, [rbp+4Fh+var_70]
0x10041631b  mov     rdx, [rbp+4Fh+ListEntry]; struct SOS_ParentBlockDescriptor *
0x10041631f  cmp     rdx, rax
0x100416322  jnz     loc_10049241A
0x100416328  inc     esi
0x10041632a  test    rbx, rbx
0x10041632d  mov     rax, [rbp+4Fh+var_78]
0x100416331  lea     r12, [rax+100h]
0x100416338  jnz     short loc_10041633F
0x10041633a  xor     edi, edi
0x10041633c  jmp     short loc_1004162CC
0x10041633f  jmp     short loc_100416350
0x100415570  mov     [r8+56h], ax
0x100415575  add     eax, 0FFFFFFF8h
0x100415578  mov     ecx, eax
0x10041557a  add     rcx, 19h
0x10041557e  shl     rcx, 4
0x100415582  add     rcx, [rbp+4Fh+var_78]; ListHead
0x100415586  mov     rdx, r8; ListEntry
0x100415589  call    cs:__imp_InterlockedPushEntrySList
0x10041558f  jmp     loc_1004162FB
0x100416350  lea     rax, [rbp+4Fh+var_88]
0x100416354  mov     rdx, [rbp+4Fh+var_80]; struct SOS_ParentBlockDescriptor *
0x100416358  cmp     rdx, rax
0x10041635b  jnz     loc_100428513
0x100416361  mov     rax, rbx
0x100416364  lea     r11, [rsp+0B0h+var_20]
0x10041636c  mov     rbx, [r11+38h]
0x100416370  mov     rsi, [r11+40h]
0x100416374  mov     rdi, [r11+48h]
0x100416378  mov     rsp, r11
0x10041637b  pop     r15
0x10041637d  pop     r14
0x10041637f  pop     r13
0x100416381  pop     r12
0x100416383  pop     rbp
0x100416384  retn
0x1004163f6  mov     r10, [rax+60h]
0x1004163fa  and     r10d, 7
0x1004163fe  mov     eax, 0
0x100416403  mov     [r8], rax
0x100416406  mov     [r8+8], rax
0x10041640a  jz      loc_10042853E
0x100416410  mov     rcx, [rbp+4Fh+arg_0]
0x100416414  movzx   r11d, word ptr [rcx+58h]
0x100416419  lea     edx, [r11-1]
0x10041641d  mov     rax, [r8+40h]
0x100416421  movzx   ecx, word ptr [rcx+5Ah]
0x100416425  mov     r9, [r8+60h]
0x100416429  shr     r9, 3
0x10041642d  mov     rbx, [r8+48h]
0x100416431  cmp     r9, rax
0x100416434  jz      short loc_100416448
0x100416436  test    rcx, rcx
0x100416439  jz      loc_1004923E2
0x10041643f  mov     rdx, r9
0x100416442  shr     rdx, cl
0x100416445  jmp     short loc_100416448
0x100416448  cmp     r9, rbx
0x10041644b  jbe     short loc_100416450
0x10041644d  add     edx, r11d
0x100416450  lea     eax, [rdx+8]
0x100416453  cmp     edx, 8
0x100416456  cmovnb  eax, edx
0x100416459  cmp     eax, esi
0x10041645b  jg      loc_100415570
0x100416461  cmp     r10d, 4
0x100416465  jz      loc_1004923FA
0x10041646b  mov     r9, [r8+60h]
0x10041646f  and     r9, 0FFFFFFFFFFFFFFF8h
0x100416473  mov     r10d, 1
0x100416479  test    r14b, r14b
0x10041647c  cmovnz  r10, r15
0x100416480  mov     rdx, r9
0x100416483  mov     rax, r9
0x100416486  or      rax, 2
0x10041648a  mov     rcx, r10
0x10041648d  or      rcx, r9
0x100416490  lock cmpxchg [r8+60h], rcx
0x100416496  mov     r9, rax
0x100416499  and     r9, 0FFFFFFFFFFFFFFF8h
0x10041649d  cmp     r9, rdx
0x1004164a0  jnz     short loc_100416480
0x1004164a2  and     al, 7
0x1004164a4  cmp     al, 2
0x1004164a6  jnz     loc_1004923FA
0x1004164ac  mov     ecx, 0FFFFh
0x1004164b1  mov     [r8+56h], cx
0x1004164b6  mov     rbx, r8
0x1004164b9  jmp     loc_100416314
0x100416ba9  test    rbx, rbx
0x100416bac  jnz     loc_100416350
0x100416bb2  test    r13b, r13b
0x100416bb5  jz      loc_100416350
0x100416bbb  mov     [rbp+4Fh+var_40], r12
0x100416bbf  mov     [rbp+4Fh+var_38], edi
0x100416bc2  mov     rbx, rdi
0x100416bc5  mov     eax, gs:48h
0x100416bcd  mov     esi, eax
0x100416bcf  mov     eax, [r12]
0x100416bd3  test    eax, eax
0x100416bd5  jnz     loc_100431FDE
0x100416bdb  xor     eax, eax
0x100416bdd  lock cmpxchg [r12], rsi
0x100416be3  mov     eax, edi
0x100416be5  setz    al
0x100416be8  test    eax, eax
0x100416bea  jz      loc_100431FDE
0x100416bf0  mov     [rbp+4Fh+var_38], 1
0x100416bf7  mov     r15d, edi
0x100416bfa  mov     r12, [rbp+4Fh+var_78]
0x100416bfe  lea     r13, [r12+108h]
0x100416c06  mov     rbx, [rbp+4Fh+var_90]
0x100416c0a  nop     word ptr [rax+rax+00h]
0x100416c10  cmp     r15d, 8
0x100416c14  jnb     short loc_100416C33
0x100416c16  mov     rbx, [r13+8]
0x100416c1a  cmp     rbx, r13
0x100416c1d  jnz     loc_100432BC7
0x100416c23  mov     rbx, [rbp+4Fh+var_90]
0x100416c27  inc     r15d
0x100416c2a  add     r13, 10h
0x100416c2e  test    rbx, rbx
0x100416c31  jz      short loc_100416C10
0x100416c33  lea     rcx, [rbp+4Fh+var_40]
0x100416c37  call    ??1?$SpinlockHolder@$0DB@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(void)
0x100416c3c  nop     word ptr [rax+rax]
0x100416c41  jmp     loc_100416350
0x100428513  test    rdx, rdx
0x100428516  jz      loc_100416361
0x10042851c  mov     rcx, [rdx+8]; this
0x100428520  mov     rax, [rdx]
0x100428523  mov     [rax+8], rcx
0x100428527  mov     [rcx], rax
0x10042852a  xor     eax, eax
0x10042852c  mov     [rdx+8], rax
0x100428530  mov     [rdx], rax
0x100428533  call    ?ReleaseEmptyDescriptor@SOS_MemoryBlockAllocator@@IEAAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(SOS_ParentBlockDescriptor *)
0x100428538  jmp     loc_100416350
0x10042853e  mov     rax, [rbp+4Fh+var_80]
0x100428542  mov     [r8+8], rax
0x100428546  mov     rax, [rbp+4Fh+var_80]
0x10042854a  mov     [rax], r8
0x10042854d  mov     [rbp+4Fh+var_80], r8
0x100428551  lea     rax, [rbp+4Fh+var_88]
0x100428555  mov     [r8], rax
0x100428558  jmp     loc_1004162FB
0x100431fde  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100431fe4  and     eax, 84h
0x100431fe9  cmp     al, 84h
0x100431feb  jz      loc_100492459
0x100431ff1  mov     rcx, r12; this
0x100431ff4  test    byte ptr cs:qword_1007149B5+2, 80h
0x100431ffb  jz      loc_1004926B2
0x100432001  mov     r8, rsi
0x100432004  mov     rdx, rdi
0x100432007  call    ?SpinToAcquireOptimistic@?$Spinlock@$0DB@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<49,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10043200c  jmp     short loc_10043200F
0x10043200f  test    rdi, rdi
0x100432012  jnz     loc_1004926C1
0x100432018  xor     edi, edi
0x10043201a  jmp     loc_100416BF0
0x100432b9e  mov     rcx, [r10]
0x100432ba1  mov     rax, [r14]
0x100432ba4  mov     [rax+8], rcx
0x100432ba8  mov     [rcx], rax
0x100432bab  mov     rax, [rbp+4Fh+var_80]
0x100432baf  mov     [r10], rax
0x100432bb2  mov     rax, [rbp+4Fh+var_80]
0x100432bb6  mov     [rax], r14
0x100432bb9  mov     [rbp+4Fh+var_80], r14
0x100432bbd  lea     rax, [rbp+4Fh+var_88]
0x100432bc1  mov     [r14], rax
0x100432bc4  jmp     short loc_100432BC7
0x100432bc7  test    rbx, rbx
0x100432bca  jz      loc_100416C23
0x100432bd0  mov     r8, rbx
0x100432bd3  mov     r14, rbx
0x100432bd6  lea     r10, [rbx+8]
0x100432bda  mov     rbx, [r10]
0x100432bdd  cmp     rbx, r13
0x100432be0  cmovz   rbx, rdi
0x100432be4  mov     r11, [r14+60h]
0x100432be8  and     r11d, 7
0x100432bec  jz      short loc_100432B9E
0x100432bee  mov     rcx, [rbp+4Fh+arg_0]
0x100432bf2  movzx   edi, word ptr [rcx+58h]
0x100432bf6  lea     edx, [rdi-1]
0x100432bf9  mov     rax, [r8+40h]
0x100432bfd  movzx   ecx, word ptr [rcx+5Ah]
0x100432c01  mov     r9, [r8+60h]
0x100432c05  shr     r9, 3
0x100432c09  mov     rsi, [r8+48h]
0x100432c0d  cmp     r9, rax
0x100432c10  jz      short loc_100432C24
0x100432c12  test    rcx, rcx
0x100432c15  jz      loc_100492702
0x100432c1b  mov     rdx, r9
0x100432c1e  shr     rdx, cl
0x100432c21  jmp     short loc_100432C24
0x100432c24  cmp     r9, rsi
0x100432c27  ja      loc_10049271A
0x100432c2d  cmp     edx, r15d
0x100432c30  jg      short loc_100432CA7
0x100432c32  cmp     r11d, 4
0x100432c36  jz      loc_100432CE9
0x100432c3c  mov     rcx, [r8+60h]
0x100432c40  and     rcx, 0FFFFFFFFFFFFFFF8h
0x100432c44  nop     dword ptr [rax+00h]
0x100432c48  nop     dword ptr [rax+rax+00000000h]
0x100432c50  mov     rdx, rcx
0x100432c53  mov     rax, rcx
0x100432c56  or      rax, 2
0x100432c5a  or      rcx, 1
0x100432c5e  lock cmpxchg [r8+60h], rcx
0x100432c64  mov     rcx, rax
0x100432c67  and     rcx, 0FFFFFFFFFFFFFFF8h
0x100432c6b  cmp     rcx, rdx
0x100432c6e  jnz     short loc_100432C50
0x100432c70  and     al, 7
0x100432c72  xor     edi, edi
0x100432c74  cmp     al, 2
0x100432c76  jnz     loc_100432BC7
0x100432c7c  mov     rcx, [r8+8]
0x100432c80  mov     rax, [r8]
0x100432c83  mov     [rax+8], rcx
0x100432c87  mov     [rcx], rax
0x100432c8a  mov     [r8+8], rdi
0x100432c8e  mov     [r8], rdi
0x100432c91  mov     eax, 0FFFFh
0x100432c96  mov     [r8+56h], ax
0x100432c9b  mov     rbx, r8
0x100432c9e  mov     [rbp+4Fh+var_90], rbx
0x100432ca2  jmp     loc_100416C27
0x100432ca7  mov     [r8+56h], dx
0x100432cac  mov     r11, [r14]
0x100432caf  mov     r9, [r10]
0x100432cb2  mov     [r11+8], r9
0x100432cb6  mov     [r9], r11
0x100432cb9  cmp     edx, 8
0x100432cbc  jnb     loc_100492722
0x100432cc2  movsxd  rax, edx
0x100432cc5  shl     rax, 4
0x100432cc9  lea     rcx, [r12+108h]
0x100432cd1  add     rcx, rax
0x100432cd4  mov     rax, [rcx+8]
0x100432cd8  mov     [r10], rax
0x100432cdb  mov     rax, [rcx+8]
  ... truncated ...
```
