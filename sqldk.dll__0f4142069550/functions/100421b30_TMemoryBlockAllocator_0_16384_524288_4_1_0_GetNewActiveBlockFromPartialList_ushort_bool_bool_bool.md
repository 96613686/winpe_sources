# TMemoryBlockAllocator<0,16384,524288,4,1,0>::GetNewActiveBlockFromPartialList(ushort,bool,bool,bool)

- ea: `0x100421b30`
- end: `0x100421c22`
- name: `?GetNewActiveBlockFromPartialList@?$TMemoryBlockAllocator@$0A@$0EAAA@$0IAAAA@$03$00$0A@@@EEAAPEAVSOS_ParentBlockDescriptor@@G_N00@Z`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100416390`
- `0x100421b30`
- `0x100422880`
- `0x100431e70`
- `0x100494e40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x100421e98`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492c7d`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492e49`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492eb1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004930b4`
- `KERNEL32!InterlockedPushEntrySList` at `0x100421e98`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492c7d`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492e49`
- `KERNEL32!InterlockedPushEntrySList` at `0x100492eb1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004930b4`
- `KERNEL32!InterlockedPopEntrySList` at `0x100421bde`
- `KERNEL32!InterlockedPopEntrySList` at `0x100492d13`
- `KERNEL32!InterlockedPopEntrySList` at `0x100421bde`
- `KERNEL32!InterlockedPopEntrySList` at `0x100492d13`
- `KERNEL32!QueryPerformanceCounter` at `0x100492cce`
- `KERNEL32!QueryPerformanceCounter` at `0x100492efe`
- `KERNEL32!QueryPerformanceCounter` at `0x100492cce`
- `KERNEL32!QueryPerformanceCounter` at `0x100492efe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall TMemoryBlockAllocator<0,16384,524288,4,1,0>::GetNewActiveBlockFromPartialList(
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
  LARGE_INTEGER v17; // rbx
  signed __int64 UniqueThread_low; // rsi
  int v19; // r15d
  __int64 v20; // r12
  __int64 v21; // r13
  struct SOS_ParentBlockDescriptor **v22; // rbx
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
  __int64 v34; // rax
  SOS_MemoryBlockAllocator *v35; // rcx
  struct _SLIST_ENTRY *Next; // rax
  __int64 v37; // rdx
  signed int v38; // esi
  union _SLIST_HEADER *v39; // rdi
  PSLIST_ENTRY v40; // rax
  PSLIST_ENTRY v41; // r8
  __int64 v42; // r10
  int v43; // r11d
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // r9
  signed int v46; // eax
  unsigned __int64 v47; // r9
  __int64 v48; // r10
  unsigned __int64 v49; // rdx
  signed __int64 v50; // rax
  PSLIST_ENTRY v51; // rdx
  SOS_MemoryBlockAllocator *v52; // rcx
  struct _SLIST_ENTRY *v53; // rax
  LARGE_INTEGER v54; // rcx
  LONGLONG v55; // rax
  int v56; // edi
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // r9
  unsigned __int64 v59; // rcx
  unsigned __int64 v60; // rdx
  signed __int64 v61; // rax
  struct SOS_ParentBlockDescriptor *v62; // rcx
  struct SOS_ParentBlockDescriptor *v63; // rax
  __int64 v64; // r11
  struct SOS_ParentBlockDescriptor *v65; // r9
  __int64 v66; // rcx
  struct SOS_ParentBlockDescriptor **v67; // r8
  struct SOS_ParentBlockDescriptor *v68; // r14
  struct SOS_ParentBlockDescriptor **v69; // r10
  struct SOS_ParentBlockDescriptor *v70; // rcx
  __int64 v71; // rax
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
  v8 = a1 + 192LL * a2;
  v75 = v8;
  v9 = (SpinlockBase *)(v8 + 256);
  if ( a4 )
  {
    v10 = 4;
    while ( 1 )
    {
      v72 = 0;
      if ( (unsigned int)v10 >= 8 )
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
          v25 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v26) = v25 - 1;
          v27 = (unsigned __int64)v12[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v27 != v12[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v26 = v27 >> *(_WORD *)(a1 + 90);
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
          v28 = v26 + 4;
          if ( (unsigned int)v26 >= 4 )
            v28 = v26;
          if ( v28 <= v10 )
            break;
          HIWORD(v13[5].Next) = v28;
          InterlockedPushEntrySList((PSLIST_HEADER)(v75 + 16 * ((unsigned int)(v28 - 4) + 21LL)), v13);
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
        v35 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&ListEntry->Next + 1);
        Next = ListEntry->Next;
        *((_QWORD *)&Next->Next + 1) = v35;
        *(_QWORD *)v35 = Next;
        *((_QWORD *)&v14->Next + 1) = 0;
        v14->Next = 0;
        if ( ((__int64)v14[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v11, v14);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v35, (struct SOS_ParentBlockDescriptor *)v14);
      }
      ++v10;
      v8 = v75;
      v9 = (SpinlockBase *)(v75 + 256);
      if ( v7 )
        goto LABEL_10;
      v6 = 0;
    }
  }
  else
  {
    v38 = 7;
    while ( (unsigned int)v38 >= 4 )
    {
      v72 = 0;
      v79 = (PSLIST_ENTRY)&v78;
      v78 = (__int64)&v78;
      v39 = (union _SLIST_HEADER *)(v8 + 16 * (v38 + 17LL));
      while ( 1 )
      {
        v40 = InterlockedPopEntrySList(v39);
        v41 = v40;
        if ( !v40 )
          break;
        v23 = ((__int64)v40[6].Next & 7) == 0;
        v42 = (__int64)v40[6].Next & 7;
        v40->Next = 0;
        *((_QWORD *)&v40->Next + 1) = 0;
        if ( v23 )
        {
          *((_QWORD *)&v40->Next + 1) = v74;
          *(_QWORD *)v74 = v40;
          v74 = (struct SOS_ParentBlockDescriptor *)v40;
          v40->Next = (struct _SLIST_ENTRY *)&v73;
        }
        else
        {
          v43 = *(unsigned __int16 *)(a1 + 88);
          LODWORD(v44) = v43 - 1;
          v45 = (unsigned __int64)v40[6].Next >> 3;
          if ( (struct _SLIST_ENTRY *)v45 != v40[4].Next )
          {
            if ( *(_WORD *)(a1 + 90) )
            {
              v44 = v45 >> *(_WORD *)(a1 + 90);
            }
            else if ( v45 )
            {
              LODWORD(v44) = v45 - 1;
            }
            else
            {
              LODWORD(v44) = 0;
            }
          }
          if ( v45 > *((_QWORD *)&v40[4].Next + 1) )
            LODWORD(v44) = v43 + v44;
          v46 = v44 + 4;
          if ( (unsigned int)v44 >= 4 )
            v46 = v44;
          if ( v46 > v38 )
          {
            HIWORD(v41[5].Next) = v46;
            InterlockedPushEntrySList((PSLIST_HEADER)(v75 + 16 * ((unsigned int)(v46 - 4) + 21LL)), v41);
          }
          else
          {
            if ( (_DWORD)v42 != 4 )
            {
              v47 = (unsigned __int64)v41[6].Next & 0xFFFFFFFFFFFFFFF8uLL;
              v48 = 1;
              if ( a5 )
                v48 = 6;
              do
              {
                v49 = v47;
                v50 = _InterlockedCompareExchange64((volatile signed __int64 *)&v41[6], v47 | v48, v47 | 2);
                v47 = v50 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v50 & 0xFFFFFFFFFFFFFFF8uLL) != v49 );
              if ( (v50 & 7) == 2 )
              {
                HIWORD(v41[5].Next) = -1;
                v7 = v41;
                v72 = v41;
                goto LABEL_85;
              }
            }
            *((_QWORD *)&v41->Next + 1) = v79;
            v79->Next = v41;
            v79 = v41;
            v41->Next = (struct _SLIST_ENTRY *)&v78;
          }
        }
      }
      v7 = 0;
LABEL_85:
      while ( 1 )
      {
        v51 = v79;
        if ( v79 == (PSLIST_ENTRY)&v78 || !v79 )
          break;
        v52 = (SOS_MemoryBlockAllocator *)*((_QWORD *)&v79->Next + 1);
        v53 = v79->Next;
        *((_QWORD *)&v53->Next + 1) = v52;
        *(_QWORD *)v52 = v53;
        *((_QWORD *)&v51->Next + 1) = 0;
        v51->Next = 0;
        if ( ((__int64)v51[6].Next & 7) != 0 )
          InterlockedPushEntrySList(v39, v51);
        else
          SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(v52, (struct SOS_ParentBlockDescriptor *)v51);
      }
      --v38;
      v8 = v75;
      v9 = (SpinlockBase *)(v75 + 256);
      if ( v7 )
        goto LABEL_10;
      v6 = 0;
    }
  }
  if ( a3 )
  {
    v82 = v9;
    v83 = 0;
    v17.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v9 || _InterlockedCompareExchange64((volatile signed __int64 *)v9, UniqueThread_low, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v37 && *(_QWORD *)(v37 + 272) == v37 )
          v6 = *(_QWORD *)(v37 + 256);
        if ( v6 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v17 = PerformanceCount;
          }
          else
          {
            v17.QuadPart = MEMORY[0x7FFE0008];
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
          v54 = v81;
        }
        else
        {
          v54.QuadPart = MEMORY[0x7FFE0008];
        }
        v55 = 0;
        if ( v54.QuadPart >= (unsigned __int64)v17.QuadPart )
          v55 = v54.QuadPart - v17.QuadPart;
        *(_QWORD *)(v6 + 3192) += v55;
      }
    }
    v83 = 1;
    v19 = 0;
    v20 = v75;
    v21 = v75 + 264;
    v7 = v72;
    do
    {
      if ( (unsigned int)v19 >= 4 )
        break;
      v22 = *(struct SOS_ParentBlockDescriptor ***)(v21 + 8);
      if ( v22 != (struct SOS_ParentBlockDescriptor **)v21 )
      {
        while ( v22 )
        {
          v67 = v22;
          v68 = (struct SOS_ParentBlockDescriptor *)v22;
          v69 = v22 + 1;
          v22 = (struct SOS_ParentBlockDescriptor **)v22[1];
          if ( v22 == (struct SOS_ParentBlockDescriptor **)v21 )
            v22 = 0;
          if ( (*((_QWORD *)v68 + 12) & 7) != 0 )
          {
            v56 = *(unsigned __int16 *)(a1 + 88);
            LODWORD(v57) = v56 - 1;
            v58 = (unsigned __int64)v67[12] >> 3;
            if ( (struct SOS_ParentBlockDescriptor *)v58 != v67[8] )
            {
              if ( *(_WORD *)(a1 + 90) )
              {
                v57 = v58 >> *(_WORD *)(a1 + 90);
              }
              else if ( v58 )
              {
                LODWORD(v57) = v58 - 1;
              }
              else
              {
                LODWORD(v57) = 0;
              }
            }
            if ( v58 > (unsigned __int64)v67[9] )
              LODWORD(v57) = v56 + v57;
            if ( (int)v57 > v19 )
            {
              *((_WORD *)v67 + 43) = v57;
              v64 = *(_QWORD *)v68;
              v65 = *v69;
              *(_QWORD *)(v64 + 8) = *v69;
              *(_QWORD *)v65 = v64;
              if ( (unsigned int)v57 >= 4 )
              {
                *v69 = 0;
                *v67 = 0;
                InterlockedPushEntrySList(
                  (PSLIST_HEADER)(v20 + 16 * ((unsigned int)(v57 - 4) + 21LL)),
                  (PSLIST_ENTRY)v67);
              }
              else
              {
                v66 = 16LL * (int)v57 + v20 + 264;
                *v69 = *(struct SOS_ParentBlockDescriptor **)(v66 + 8);
                **(_QWORD **)(v66 + 8) = v67;
                *(_QWORD *)(v66 + 8) = v67;
                *v67 = (struct SOS_ParentBlockDescriptor *)v66;
              }
            }
            else if ( (*((_DWORD *)v68 + 24) & 7) != 4 )
            {
              v59 = (unsigned __int64)v67[12] & 0xFFFFFFFFFFFFFFF8uLL;
              do
              {
                v60 = v59;
                v61 = _InterlockedCompareExchange64((volatile signed __int64 *)v67 + 12, v59 | 1, v59 | 2);
                v59 = v61 & 0xFFFFFFFFFFFFFFF8uLL;
              }
              while ( (v61 & 0xFFFFFFFFFFFFFFF8uLL) != v60 );
              if ( (v61 & 7) == 2 )
              {
                v62 = v67[1];
                v63 = *v67;
                *((_QWORD *)v63 + 1) = v62;
                *(_QWORD *)v62 = v63;
                v67[1] = 0;
                *v67 = 0;
                *((_WORD *)v67 + 43) = -1;
                v7 = (PSLIST_ENTRY)v67;
                v72 = (PSLIST_ENTRY)v67;
                goto LABEL_19;
              }
            }
          }
          else
          {
            v70 = *v69;
            v71 = *(_QWORD *)v68;
            *(_QWORD *)(v71 + 8) = *v69;
            *(_QWORD *)v70 = v71;
            *v69 = v74;
            *(_QWORD *)v74 = v68;
            v74 = v68;
            *(_QWORD *)v68 = &v73;
          }
        }
      }
      v7 = v72;
LABEL_19:
      ++v19;
      v21 += 16;
    }
    while ( !v7 );
    SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(&v82);
  }
LABEL_10:
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
0x100421b30  mov     rax, rsp
0x100421b33  mov     [rax+8], rcx
0x100421b37  push    rbp
0x100421b38  push    r12
0x100421b3a  push    r13
0x100421b3c  push    r14
0x100421b3e  push    r15
0x100421b40  lea     rbp, [rax-57h]
0x100421b44  sub     rsp, 90h
0x100421b4b  mov     [rbp+4Fh+var_30], 0FFFFFFFFFFFFFFFEh
0x100421b53  mov     [rax+10h], rbx
0x100421b57  mov     [rax+18h], rsi
0x100421b5b  mov     [rax+20h], rdi
0x100421b5f  movzx   r13d, r8b
0x100421b63  xor     edi, edi
0x100421b65  mov     ebx, edi
0x100421b67  mov     [rbp+4Fh+var_90], rbx
0x100421b6b  lea     rax, [rbp+4Fh+var_88]
0x100421b6f  mov     [rbp+4Fh+var_80], rax
0x100421b73  lea     rax, [rbp+4Fh+var_88]
0x100421b77  mov     [rbp+4Fh+var_88], rax
0x100421b7b  movzx   eax, dx
0x100421b7e  lea     rax, [rax+rax*2]
0x100421b82  shl     rax, 6
0x100421b86  add     rax, rcx
0x100421b89  mov     [rbp+4Fh+var_78], rax
0x100421b8d  lea     r12, [rax+100h]
0x100421b94  lea     r15d, [rdi+6]
0x100421b98  movzx   r14d, [rbp+4Fh+arg_20]
0x100421b9d  test    r9b, r9b
0x100421ba0  jz      loc_100492CDD
0x100421ba6  lea     esi, [rdi+4]
0x100421ba9  jmp     short loc_100421BAC
0x100421bac  mov     [rbp+4Fh+var_90], rbx
0x100421bb0  cmp     esi, 8
0x100421bb3  jnb     loc_100421C65
0x100421bb9  mov     [rbp+4Fh+var_90], rdi
0x100421bbd  lea     rdx, [rbp+4Fh+var_70]
0x100421bc1  mov     [rbp+4Fh+ListEntry], rdx
0x100421bc5  lea     rcx, [rbp+4Fh+var_70]
0x100421bc9  mov     [rbp+4Fh+var_70], rcx
0x100421bcd  movsxd  rdi, esi
0x100421bd0  add     rdi, 11h
0x100421bd4  shl     rdi, 4
0x100421bd8  add     rdi, rax
0x100421bdb  mov     rcx, rdi; ListHead
0x100421bde  call    cs:__imp_InterlockedPopEntrySList
0x100421be4  mov     r8, rax
0x100421be7  test    rax, rax
0x100421bea  jnz     loc_100421DAD
0x100421bf0  mov     rbx, [rbp+4Fh+var_90]
0x100421bf4  xor     r12d, r12d
0x100421bf7  lea     rax, [rbp+4Fh+var_70]
0x100421bfb  mov     rdx, [rbp+4Fh+ListEntry]; struct SOS_ParentBlockDescriptor *
0x100421bff  cmp     rdx, rax
0x100421c02  jnz     loc_100492C4A
0x100421c08  inc     esi
0x100421c0a  test    rbx, rbx
0x100421c0d  mov     rax, [rbp+4Fh+var_78]
0x100421c11  lea     r12, [rax+100h]
0x100421c18  jnz     short loc_100421C1F
0x100421c1a  xor     edi, edi
0x100421c1c  jmp     short loc_100421BAC
0x100421c1f  jmp     short loc_100421C30
0x100421c30  lea     rax, [rbp+4Fh+var_88]
0x100421c34  mov     rdx, [rbp+4Fh+var_80]; struct SOS_ParentBlockDescriptor *
0x100421c38  cmp     rdx, rax
0x100421c3b  jnz     loc_100421EC4
0x100421c41  mov     rax, rbx
0x100421c44  lea     r11, [rsp+0B0h+var_20]
0x100421c4c  mov     rbx, [r11+38h]
0x100421c50  mov     rsi, [r11+40h]
0x100421c54  mov     rdi, [r11+48h]
0x100421c58  mov     rsp, r11
0x100421c5b  pop     r15
0x100421c5d  pop     r14
0x100421c5f  pop     r13
0x100421c61  pop     r12
0x100421c63  pop     rbp
0x100421c64  retn
0x100421c65  test    rbx, rbx
0x100421c68  jnz     short loc_100421C30
0x100421c6a  test    r13b, r13b
0x100421c6d  jz      short loc_100421C30
0x100421c6f  mov     [rbp+4Fh+var_40], r12
0x100421c73  mov     [rbp+4Fh+var_38], edi
0x100421c76  mov     rbx, rdi
0x100421c79  mov     eax, gs:48h
0x100421c81  mov     esi, eax
0x100421c83  mov     eax, [r12]
0x100421c87  test    eax, eax
0x100421c89  jnz     loc_10042DF51
0x100421c8f  xor     eax, eax
0x100421c91  lock cmpxchg [r12], rsi
0x100421c97  mov     eax, edi
0x100421c99  setz    al
0x100421c9c  test    eax, eax
0x100421c9e  jz      loc_10042DF51
0x100421ca4  mov     [rbp+4Fh+var_38], 1
0x100421cab  mov     r15d, edi
0x100421cae  mov     r12, [rbp+4Fh+var_78]
0x100421cb2  lea     r13, [r12+108h]
0x100421cba  mov     rbx, [rbp+4Fh+var_90]
0x100421cbe  xchg    ax, ax
0x100421cc0  cmp     r15d, 4
0x100421cc4  jnb     short loc_100421CE3
0x100421cc6  mov     rbx, [r13+8]
0x100421cca  cmp     rbx, r13
0x100421ccd  jnz     loc_100493047
0x100421cd3  mov     rbx, [rbp+4Fh+var_90]
0x100421cd7  inc     r15d
0x100421cda  add     r13, 10h
0x100421cde  test    rbx, rbx
0x100421ce1  jz      short loc_100421CC0
0x100421ce3  lea     rcx, [rbp+4Fh+var_40]
0x100421ce7  call    ??1?$SpinlockHolder@$0DB@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<49,1,268435714>::~SpinlockHolder<49,1,268435714>(void)
0x100421cec  nop     word ptr [rax+rax]
0x100421cf1  jmp     loc_100421C30
0x100421dad  mov     r10, [rax+60h]
0x100421db1  and     r10d, 7
0x100421db5  mov     eax, 0
0x100421dba  mov     [r8], rax
0x100421dbd  mov     [r8+8], rax
0x100421dc1  jz      loc_100421EA4
0x100421dc7  mov     rcx, [rbp+4Fh+arg_0]
0x100421dcb  movzx   r11d, word ptr [rcx+58h]
0x100421dd0  lea     edx, [r11-1]
0x100421dd4  mov     rax, [r8+40h]
0x100421dd8  movzx   ecx, word ptr [rcx+5Ah]
0x100421ddc  mov     r9, [r8+60h]
0x100421de0  shr     r9, 3
0x100421de4  mov     rbx, [r8+48h]
0x100421de8  cmp     r9, rax
0x100421deb  jz      short loc_100421DFF
0x100421ded  test    rcx, rcx
0x100421df0  jz      loc_100492C12
0x100421df6  mov     rdx, r9
0x100421df9  shr     rdx, cl
0x100421dfc  jmp     short loc_100421DFF
0x100421dff  cmp     r9, rbx
0x100421e02  jbe     short loc_100421E07
0x100421e04  add     edx, r11d
0x100421e07  lea     eax, [rdx+4]
0x100421e0a  cmp     edx, 4
0x100421e0d  cmovnb  eax, edx
0x100421e10  cmp     eax, esi
0x100421e12  jg      short loc_100421E7F
0x100421e14  cmp     r10d, 4
0x100421e18  jz      loc_100492C2A
0x100421e1e  mov     r9, [r8+60h]
0x100421e22  and     r9, 0FFFFFFFFFFFFFFF8h
0x100421e26  mov     r10d, 1
0x100421e2c  test    r14b, r14b
0x100421e2f  cmovnz  r10, r15
0x100421e33  nop     dword ptr [rax+00h]
0x100421e37  nop     word ptr [rax+rax+00000000h]
0x100421e40  mov     rdx, r9
0x100421e43  mov     rax, r9
0x100421e46  or      rax, 2
0x100421e4a  mov     rcx, r10
0x100421e4d  or      rcx, r9
0x100421e50  lock cmpxchg [r8+60h], rcx
0x100421e56  mov     r9, rax
0x100421e59  and     r9, 0FFFFFFFFFFFFFFF8h
0x100421e5d  cmp     r9, rdx
0x100421e60  jnz     short loc_100421E40
0x100421e62  and     al, 7
0x100421e64  cmp     al, 2
0x100421e66  jnz     loc_100492C2A
0x100421e6c  mov     ecx, 0FFFFh
0x100421e71  mov     [r8+56h], cx
0x100421e76  mov     rbx, r8
0x100421e79  jmp     loc_100421BF4
0x100421e7f  mov     [r8+56h], ax
0x100421e84  add     eax, 0FFFFFFFCh
0x100421e87  mov     ecx, eax
0x100421e89  add     rcx, 15h
0x100421e8d  shl     rcx, 4
0x100421e91  add     rcx, [rbp+4Fh+var_78]; ListHead
0x100421e95  mov     rdx, r8; ListEntry
0x100421e98  call    cs:__imp_InterlockedPushEntrySList
0x100421e9e  jmp     loc_100421BDB
0x100421ea4  mov     rax, [rbp+4Fh+var_80]
0x100421ea8  mov     [r8+8], rax
0x100421eac  mov     rax, [rbp+4Fh+var_80]
0x100421eb0  mov     [rax], r8
0x100421eb3  mov     [rbp+4Fh+var_80], r8
0x100421eb7  lea     rax, [rbp+4Fh+var_88]
0x100421ebb  mov     [r8], rax
0x100421ebe  jmp     loc_100421BDB
0x100421ec4  test    rdx, rdx
0x100421ec7  jz      loc_100421C41
0x100421ecd  mov     rcx, [rdx+8]; this
0x100421ed1  mov     rax, [rdx]
0x100421ed4  mov     [rax+8], rcx
0x100421ed8  mov     [rcx], rax
0x100421edb  xor     eax, eax
0x100421edd  mov     [rdx+8], rax
0x100421ee1  mov     [rdx], rax
0x100421ee4  call    ?ReleaseEmptyDescriptor@SOS_MemoryBlockAllocator@@IEAAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(SOS_ParentBlockDescriptor *)
0x100421ee9  jmp     loc_100421C30
0x10042df51  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10042df57  and     eax, 84h
0x10042df5c  cmp     al, 84h
0x10042df5e  jz      loc_100492C89
0x10042df64  mov     rcx, r12; this
0x10042df67  test    byte ptr cs:qword_1007149B5+2, 80h
0x10042df6e  jz      loc_100492EE2
0x10042df74  mov     r8, rsi
0x10042df77  mov     rdx, rdi
0x10042df7a  call    ?SpinToAcquireOptimistic@?$Spinlock@$0DB@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<49,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10042df7f  jmp     short loc_10042DF82
0x10042df82  test    rdi, rdi
0x10042df85  jnz     loc_100492EF1
0x10042df8b  xor     edi, edi
0x10042df8d  jmp     loc_100421CA4
0x100492c12  test    r9, r9
0x100492c15  jz      short loc_100492C20
0x100492c17  lea     edx, [r9-1]
0x100492c1b  jmp     loc_100421DFF
0x100492c20  xor     eax, eax
0x100492c22  mov     edx, eax
0x100492c24  jmp     loc_100421DFF
0x100492c2a  mov     rax, [rbp+4Fh+ListEntry]
0x100492c2e  mov     [r8+8], rax
0x100492c32  mov     rax, [rbp+4Fh+ListEntry]
0x100492c36  mov     [rax], r8
0x100492c39  mov     [rbp+4Fh+ListEntry], r8
0x100492c3d  lea     rax, [rbp+4Fh+var_70]
0x100492c41  mov     [r8], rax
0x100492c44  jmp     loc_100421BDB
0x100492c4a  test    rdx, rdx
0x100492c4d  jz      loc_100421C08
0x100492c53  mov     rcx, [rdx+8]; this
0x100492c57  mov     rax, [rdx]
0x100492c5a  mov     [rax+8], rcx
0x100492c5e  mov     [rcx], rax
0x100492c61  mov     [rdx+8], r12
0x100492c65  mov     [rdx], r12
0x100492c68  mov     rax, [rdx+60h]
0x100492c6c  test    al, 7
0x100492c6e  jnz     short loc_100492C7A
0x100492c70  call    ?ReleaseEmptyDescriptor@SOS_MemoryBlockAllocator@@IEAAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryBlockAllocator::ReleaseEmptyDescriptor(SOS_ParentBlockDescriptor *)
0x100492c75  jmp     loc_100421BF7
0x100492c7a  mov     rcx, rdi; ListHead
0x100492c7d  call    cs:__imp_InterlockedPushEntrySList
0x100492c83  jmp     loc_100421BF7
0x100492c89  mov     rcx, gs:58h
0x100492c92  mov     eax, cs:_tls_index
0x100492c98  mov     edx, cs:SystemThread_TlsOffset
0x100492c9e  add     rdx, [rcx+rax*8]
0x100492ca2  jz      short loc_100492CB4
0x100492ca4  cmp     [rdx+110h], rdx
0x100492cab  jnz     short loc_100492CB4
0x100492cad  mov     rdi, [rdx+100h]
0x100492cb4  test    rdi, rdi
0x100492cb7  jz      loc_10042DF64
0x100492cbd  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100492cc4  jz      loc_100492ED4
0x100492cca  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x100492cce  call    cs:__imp_QueryPerformanceCounter
0x100492cd4  mov     rbx, qword ptr [rbp+4Fh+PerformanceCount]
0x100492cd8  jmp     loc_10042DF64
0x100492cdd  mov     esi, 7
0x100492ce2  jmp     short loc_100492CE5
0x100492ce5  cmp     esi, 4
0x100492ce8  jb      loc_100421C6A
0x100492cee  mov     [rbp+4Fh+var_90], rdi
0x100492cf2  lea     rdx, [rbp+4Fh+var_60]
0x100492cf6  mov     [rbp+4Fh+var_58], rdx
0x100492cfa  lea     rcx, [rbp+4Fh+var_60]
0x100492cfe  mov     [rbp+4Fh+var_60], rcx
0x100492d02  movsxd  rdi, esi
0x100492d05  add     rdi, 11h
0x100492d09  shl     rdi, 4
0x100492d0d  add     rdi, rax
0x100492d10  mov     rcx, rdi; ListHead
0x100492d13  call    cs:__imp_InterlockedPopEntrySList
0x100492d19  mov     r8, rax
0x100492d1c  test    rax, rax
0x100492d1f  jz      loc_100492EA7
0x100492d25  mov     r10, [rax+60h]
0x100492d29  and     r10d, 7
0x100492d2d  mov     eax, 0
0x100492d32  mov     [r8], rax
0x100492d35  mov     [r8+8], rax
0x100492d39  jnz     short loc_100492D65
0x100492d3b  mov     rax, [rbp+4Fh+var_80]
0x100492d3f  mov     [r8+8], rax
0x100492d43  mov     rax, [rbp+4Fh+var_80]
0x100492d47  mov     [rax], r8
0x100492d4a  mov     [rbp+4Fh+var_80], r8
0x100492d4e  lea     rax, [rbp+4Fh+var_88]
0x100492d52  mov     [r8], rax
0x100492d55  jmp     short loc_100492D10
0x100492d60  xor     edi, edi
0x100492d62  jmp     short loc_100492CE5
0x100492d65  mov     rcx, [rbp+4Fh+arg_0]
0x100492d69  movzx   r11d, word ptr [rcx+58h]
0x100492d6e  lea     edx, [r11-1]
  ... truncated ...
```
