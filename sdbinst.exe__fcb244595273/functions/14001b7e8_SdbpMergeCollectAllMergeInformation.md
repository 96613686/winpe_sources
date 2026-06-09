# SdbpMergeCollectAllMergeInformation

- ea: `0x14001b7e8`
- end: `0x14001bf31`
- name: `SdbpMergeCollectAllMergeInformation`
- size: `1865`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400207cc`

## callees

- `0x14000fb80`
- `0x14001008c`
- `0x140014380`
- `0x14001443c`
- `0x14001a24c`
- `0x14001a834`
- `0x14001b7e8`
- `0x14001c290`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x14001ba76`
- `KERNEL32!RtlCompareMemory` at `0x14001ba8d`
- `KERNEL32!RtlCompareMemory` at `0x14001baa5`
- `KERNEL32!RtlCompareMemory` at `0x14001bd1c`
- `KERNEL32!RtlCompareMemory` at `0x14001bd32`
- `KERNEL32!RtlCompareMemory` at `0x14001bd49`
- `KERNEL32!RtlCompareMemory` at `0x14001ba76`
- `KERNEL32!RtlCompareMemory` at `0x14001ba8d`
- `KERNEL32!RtlCompareMemory` at `0x14001baa5`
- `KERNEL32!RtlCompareMemory` at `0x14001bd1c`
- `KERNEL32!RtlCompareMemory` at `0x14001bd32`
- `KERNEL32!RtlCompareMemory` at `0x14001bd49`
- `ntdll!RtlAllocateHeap` at `0x14001b8e2`
- `ntdll!RtlAllocateHeap` at `0x14001bb81`
- `ntdll!RtlAllocateHeap` at `0x14001bde2`
- `ntdll!RtlAllocateHeap` at `0x14001b8e2`
- `ntdll!RtlAllocateHeap` at `0x14001bb81`
- `ntdll!RtlAllocateHeap` at `0x14001bde2`
- `ntdll!RtlReAllocateHeap` at `0x14001b902`
- `ntdll!RtlReAllocateHeap` at `0x14001bba1`
- `ntdll!RtlReAllocateHeap` at `0x14001be02`
- `ntdll!RtlReAllocateHeap` at `0x14001b902`
- `ntdll!RtlReAllocateHeap` at `0x14001bba1`
- `ntdll!RtlReAllocateHeap` at `0x14001be02`

## pseudocode

```c
__int64 __fastcall SdbpMergeCollectAllMergeInformation(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  int v4; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // rsi
  unsigned __int64 v9; // rsi
  unsigned __int128 v10; // rax
  size_t v11; // r12
  void *v12; // r8
  void *v13; // rcx
  PVOID v14; // rax
  PVOID Heap; // rbx
  _OWORD *v16; // rax
  unsigned int FirstTag; // eax
  unsigned int v19; // eax
  unsigned int v20; // esi
  unsigned int i; // eax
  int v22; // eax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rsi
  _DWORD *v25; // rbx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  int v28; // eax
  unsigned __int64 v29; // r14
  unsigned __int64 v30; // rcx
  __int64 v31; // rsi
  unsigned __int64 v32; // rsi
  unsigned __int128 v33; // rax
  size_t v34; // r12
  void *v35; // r8
  void *v36; // rcx
  PVOID v37; // rax
  PVOID v38; // rbx
  _OWORD *v39; // rax
  unsigned int v40; // r13d
  unsigned int j; // eax
  int v42; // eax
  __int64 v43; // r8
  int v44; // eax
  unsigned __int64 v45; // rsi
  unsigned __int64 v46; // r14
  _DWORD *v47; // rbx
  unsigned __int64 v48; // rax
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  __int64 v51; // r14
  unsigned __int64 v52; // r14
  unsigned __int128 v53; // rax
  size_t v54; // r12
  void *v55; // r8
  void *v56; // rcx
  PVOID v57; // rax
  PVOID v58; // rbx
  _OWORD *v59; // rax
  unsigned int v60; // r13d
  int v61; // eax
  __int64 v62; // [rsp+20h] [rbp-B9h]
  unsigned int v64; // [rsp+40h] [rbp-99h]
  __int128 v65; // [rsp+50h] [rbp-89h] BYREF
  __int128 Source2; // [rsp+60h] [rbp-79h] BYREF
  __int128 v67; // [rsp+70h] [rbp-69h] BYREF
  __int128 v68; // [rsp+80h] [rbp-59h]
  __int128 v69; // [rsp+90h] [rbp-49h]
  wchar_t v70[40]; // [rsp+A0h] [rbp-39h] BYREF

  v3 = a1;
  memset_0(&v65, 0, 0x50u);
  v4 = SdbpMergeCollectPdbInformation(v3, &v65);
  v5 = v4;
  if ( v4 < 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpMergeCollectAllMergeInformation",
      2790,
      "Failed to collect database information from pdb [%x]",
      v4);
    goto LABEL_104;
  }
  v6 = *(_QWORD *)(a2 + 16);
  if ( v6 >= *(_QWORD *)(a2 + 24) )
  {
    v7 = v6 + 1;
    if ( v6 + 1 <= *(_QWORD *)(a2 + 24) )
    {
      v5 = -1073741811;
      goto LABEL_102;
    }
    v8 = *(_QWORD *)(a2 + 32) - 1LL;
    if ( v8 + v7 < v7
      || !is_mul_ok(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 8))
      || (v9 = (v8 + v7) & ~v8,
          v10 = v9 * (unsigned __int128)*(unsigned __int64 *)(a2 + 8),
          v11 = v9 * *(_QWORD *)(a2 + 8),
          !is_mul_ok(v9, *(_QWORD *)(a2 + 8))) )
    {
      v5 = -1073741675;
      goto LABEL_102;
    }
    v12 = *(void **)(a2 + 40);
    v13 = *(void **)a2;
    if ( v12 )
    {
      Heap = RtlReAllocateHeap(v13, DWORD2(v10), v12, v10);
    }
    else
    {
      v14 = RtlAllocateHeap(v13, DWORD2(v10), v10);
      Heap = v14;
      if ( v14 )
        memset_0(v14, 0, v11);
    }
    v3 = a1;
    if ( !Heap )
    {
      v5 = -1073741801;
      goto LABEL_102;
    }
    *(_QWORD *)(a2 + 40) = Heap;
    *(_QWORD *)(a2 + 24) = v9;
  }
  if ( !is_mul_ok(*(_QWORD *)(a2 + 8), v6)
    || (v16 = (_OWORD *)(*(_QWORD *)(a2 + 40) + *(_QWORD *)(a2 + 8) * v6), (unsigned __int64)v16 < *(_QWORD *)(a2 + 40)) )
  {
    v5 = -1073741675;
LABEL_102:
    LODWORD(v62) = v5;
    v43 = 2796;
LABEL_103:
    AslLogCallPrintf(1, "SdbpMergeCollectAllMergeInformation", v43, "Failed to append dbinfo to array [%x]", v62);
    goto LABEL_104;
  }
  *v16 = v65;
  v16[1] = Source2;
  v16[2] = v67;
  v16[3] = v68;
  v16[4] = v69;
  ++*(_QWORD *)(a2 + 16);
  memset_0(&v65, 0, 0x50u);
  FirstTag = SdbFindFirstTag(v3, 0, 28673);
  if ( !FirstTag )
  {
    AslLogCallPrintf(1, "SdbpMergeCollectAllMergeInformation", 2805, "Failed to find TAG_DATABASE for pdb");
    return 3221225700LL;
  }
  v19 = SdbFindFirstTag(v3, FirstTag, 28748);
  v64 = v19;
  v20 = v19;
  if ( v19 )
  {
    for ( i = SdbFindFirstTag(v3, v19, 28749); ; i = SdbFindNextTag(v3, v64, v40) )
    {
      v40 = i;
      if ( !i )
        break;
      v22 = SdbMergeCollectPreviousMergeInfoFromDb(v3, i, &v65);
      v5 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v62) = v22;
        AslLogCallPrintf(
          1,
          "SdbpMergeCollectAllMergeInformation",
          2825,
          "SdbMergeCollectPreviousMergeInfoFromDb failed to get merge info from sdb [%x]",
          v62);
        goto LABEL_104;
      }
      v23 = *(_QWORD *)(a2 + 16);
      if ( v23 )
      {
        v24 = 0;
        while ( 1 )
        {
          v25 = 0;
          if ( v24 < v23 )
          {
            v26 = *(_QWORD *)(a2 + 8) * v24;
            if ( !is_mul_ok(*(_QWORD *)(a2 + 8), v24)
              || (v27 = *(_QWORD *)(a2 + 40), v25 = (_DWORD *)(v27 + v26), v27 + v26 < v27) )
            {
              v25 = 0;
            }
          }
          if ( v25[14] == DWORD2(v68)
            && v25[18] == DWORD2(v69)
            && RtlCompareMemory(v25 + 6, (char *)&Source2 + 8, 0x10u) == 16
            && RtlCompareMemory(v25 + 10, (char *)&v67 + 8, 0x10u) == 16
            && RtlCompareMemory(v25 + 4, &Source2, 8u) == 8 )
          {
            break;
          }
          v23 = *(_QWORD *)(a2 + 16);
          if ( ++v24 >= v23 )
            goto LABEL_40;
        }
        v28 = AslGuidToString(v70, 39, (char *)&Source2 + 8);
        v5 = v28;
        if ( v28 < 0 )
        {
          LODWORD(v62) = v28;
          AslLogCallPrintf(
            1,
            "SdbpMergeCollectAllMergeInformation",
            2847,
            "AslGuidToString failed to convert guid to string [%x]",
            v62);
          goto LABEL_104;
        }
        AslLogCallPrintf(1, "SdbpMergeCollectAllMergeInformation", 2851, "Duplicate database merged '%S'.", v70);
      }
LABEL_40:
      v29 = *(_QWORD *)(a2 + 16);
      if ( v29 >= *(_QWORD *)(a2 + 24) )
      {
        v30 = v29 + 1;
        if ( v29 + 1 <= *(_QWORD *)(a2 + 24) )
        {
          v5 = -1073741811;
          goto LABEL_59;
        }
        v31 = *(_QWORD *)(a2 + 32) - 1LL;
        if ( v30 + v31 < v30
          || !is_mul_ok(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 8))
          || (v32 = (v30 + v31) & ~v31,
              v33 = v32 * (unsigned __int128)*(unsigned __int64 *)(a2 + 8),
              v34 = v32 * *(_QWORD *)(a2 + 8),
              !is_mul_ok(v32, *(_QWORD *)(a2 + 8))) )
        {
          v5 = -1073741675;
LABEL_59:
          v42 = v5;
LABEL_62:
          LODWORD(v62) = v42;
          v43 = 2856;
          goto LABEL_103;
        }
        v35 = *(void **)(a2 + 40);
        v36 = *(void **)a2;
        if ( v35 )
        {
          v38 = RtlReAllocateHeap(v36, DWORD2(v33), v35, v33);
        }
        else
        {
          v37 = RtlAllocateHeap(v36, DWORD2(v33), v33);
          v38 = v37;
          if ( v37 )
            memset_0(v37, 0, v34);
        }
        v3 = a1;
        if ( !v38 )
        {
          v5 = -1073741801;
          goto LABEL_59;
        }
        *(_QWORD *)(a2 + 40) = v38;
        *(_QWORD *)(a2 + 24) = v32;
      }
      if ( !is_mul_ok(*(_QWORD *)(a2 + 8), v29)
        || (v39 = (_OWORD *)(*(_QWORD *)(a2 + 40) + *(_QWORD *)(a2 + 8) * v29),
            (unsigned __int64)v39 < *(_QWORD *)(a2 + 40)) )
      {
        v42 = -1073741675;
        v5 = -1073741675;
        goto LABEL_62;
      }
      *v39 = v65;
      v39[1] = Source2;
      v39[2] = v67;
      v39[3] = v68;
      v39[4] = v69;
      ++*(_QWORD *)(a2 + 16);
      memset_0(&v65, 0, 0x50u);
      v20 = v64;
    }
    for ( j = SdbFindFirstTag(v3, v20, 28750); ; j = SdbFindNextTag(v3, v64, v60) )
    {
      v60 = j;
      if ( !j )
        goto LABEL_22;
      v44 = SdbMergeCollectPreviousMergeInfoFromDb(v3, j, &v65);
      v5 = v44;
      if ( v44 < 0 )
        break;
      v45 = *(_QWORD *)(a2 + 16);
      if ( v45 )
      {
        v46 = 0;
        while ( 1 )
        {
          v47 = 0;
          if ( v46 < v45 )
          {
            v48 = *(_QWORD *)(a2 + 8) * v46;
            if ( !is_mul_ok(*(_QWORD *)(a2 + 8), v46)
              || (v49 = *(_QWORD *)(a2 + 40), v47 = (_DWORD *)(v49 + v48), v49 + v48 < v49) )
            {
              v47 = 0;
            }
          }
          if ( v47[14] == DWORD2(v68)
            && v47[18] == DWORD2(v69)
            && RtlCompareMemory(v47 + 6, (char *)&Source2 + 8, 0x10u) == 16
            && RtlCompareMemory(v47 + 10, (char *)&v67 + 8, 0x10u) == 16
            && RtlCompareMemory(v47 + 4, &Source2, 8u) == 8 )
          {
            break;
          }
          v45 = *(_QWORD *)(a2 + 16);
          if ( ++v46 >= v45 )
            goto LABEL_77;
        }
      }
      else
      {
LABEL_77:
        if ( v45 >= *(_QWORD *)(a2 + 24) )
        {
          v50 = v45 + 1;
          if ( v45 + 1 <= *(_QWORD *)(a2 + 24) )
          {
            v5 = -1073741811;
            goto LABEL_97;
          }
          v51 = *(_QWORD *)(a2 + 32) - 1LL;
          if ( v51 + v50 < v50
            || !is_mul_ok(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 8))
            || (v52 = (v51 + v50) & ~v51,
                v53 = v52 * (unsigned __int128)*(unsigned __int64 *)(a2 + 8),
                v54 = v52 * *(_QWORD *)(a2 + 8),
                !is_mul_ok(v52, *(_QWORD *)(a2 + 8))) )
          {
            v5 = -1073741675;
LABEL_97:
            v61 = v5;
LABEL_99:
            LODWORD(v62) = v61;
            v43 = 2886;
            goto LABEL_103;
          }
          v55 = *(void **)(a2 + 40);
          v56 = *(void **)a2;
          if ( v55 )
          {
            v58 = RtlReAllocateHeap(v56, DWORD2(v53), v55, v53);
          }
          else
          {
            v57 = RtlAllocateHeap(v56, DWORD2(v53), v53);
            v58 = v57;
            if ( v57 )
              memset_0(v57, 0, v54);
          }
          v3 = a1;
          if ( !v58 )
          {
            v5 = -1073741801;
            goto LABEL_97;
          }
          *(_QWORD *)(a2 + 40) = v58;
          *(_QWORD *)(a2 + 24) = v52;
        }
        if ( !is_mul_ok(*(_QWORD *)(a2 + 8), v45)
          || (v59 = (_OWORD *)(*(_QWORD *)(a2 + 40) + *(_QWORD *)(a2 + 8) * v45),
              (unsigned __int64)v59 < *(_QWORD *)(a2 + 40)) )
        {
          v61 = -1073741675;
          v5 = -1073741675;
          goto LABEL_99;
        }
        *v59 = v65;
        v59[1] = Source2;
        v59[2] = v67;
        v59[3] = v68;
        v59[4] = v69;
        ++*(_QWORD *)(a2 + 16);
        memset_0(&v65, 0, 0x50u);
      }
    }
    LODWORD(v62) = v44;
    AslLogCallPrintf(
      1,
      "SdbpMergeCollectAllMergeInformation",
      2869,
      "SdbMergeCollectPreviousMergeInfoFromDb failed to get merge info from sdb [%x]",
      v62);
  }
  else
  {
LABEL_22:
    v5 = 0;
  }
LABEL_104:
  SdbMergeFreePdbInformation(&v65);
  return v5;
}

```

## disassembly

```asm
0x14001b7e8  mov     [rsp-8+arg_10], rbx
0x14001b7ed  push    rbp
0x14001b7ee  push    rsi
0x14001b7ef  push    rdi
0x14001b7f0  push    r12
0x14001b7f2  push    r13
0x14001b7f4  push    r14
0x14001b7f6  push    r15
0x14001b7f8  lea     rbp, [rsp-27h]
0x14001b7fd  sub     rsp, 100h
0x14001b804  mov     rax, cs:__security_cookie
0x14001b80b  xor     rax, rsp
0x14001b80e  mov     [rbp+57h+var_40], rax
0x14001b812  mov     rdi, rdx
0x14001b815  mov     [rsp+130h+var_100], rcx
0x14001b81a  xor     edx, edx; Val
0x14001b81c  mov     r12, rcx
0x14001b81f  lea     rcx, [rsp+130h+var_E0]; void *
0x14001b824  lea     r8d, [rdx+50h]; Size
0x14001b828  call    memset_0
0x14001b82d  lea     rdx, [rsp+130h+var_E0]
0x14001b832  mov     rcx, r12
0x14001b835  call    SdbpMergeCollectPdbInformation
0x14001b83a  xor     r13d, r13d
0x14001b83d  mov     ebx, eax
0x14001b83f  test    eax, eax
0x14001b841  jns     short loc_14001B85D
0x14001b843  mov     dword ptr [rsp+130h+var_110], eax
0x14001b847  lea     r9, aFailedToCollec; "Failed to collect database information "...
0x14001b84e  mov     r8d, 0AE6h
0x14001b854  lea     ecx, [r13+1]
0x14001b858  jmp     loc_14001BEF2
0x14001b85d  mov     r14, [rdi+10h]
0x14001b861  mov     r15d, 1
0x14001b867  mov     r9d, 0C0000095h
0x14001b86d  cmp     r14, [rdi+18h]
0x14001b871  jb      loc_14001B92D
0x14001b877  lea     rcx, [r14+1]
0x14001b87b  cmp     rcx, [rdi+18h]
0x14001b87f  ja      short loc_14001B88B
0x14001b881  mov     ebx, 0C000000Dh
0x14001b886  jmp     loc_14001B9CE
0x14001b88b  mov     rsi, [rdi+20h]
0x14001b88f  dec     rsi
0x14001b892  lea     r8, [rsi+rcx]
0x14001b896  cmp     r8, rcx
0x14001b899  jb      loc_14001B9CB
0x14001b89f  mov     rax, [rdi+8]
0x14001b8a3  mul     qword ptr [rdi+18h]
0x14001b8a7  mov     qword ptr [rsp+130h+var_F0], r13
0x14001b8ac  test    rdx, rdx
0x14001b8af  jnz     loc_14001B9CB
0x14001b8b5  mov     rax, [rdi+8]
0x14001b8b9  not     rsi
0x14001b8bc  and     rsi, r8
0x14001b8bf  mov     qword ptr [rsp+130h+var_F0], r13
0x14001b8c4  mul     rsi
0x14001b8c7  mov     r12, rax
0x14001b8ca  test    rdx, rdx
0x14001b8cd  jnz     loc_14001B9C6
0x14001b8d3  mov     r8, [rdi+28h]; Ptr
0x14001b8d7  mov     rcx, [rdi]; Heap
0x14001b8da  test    r8, r8
0x14001b8dd  jnz     short loc_14001B8FF
0x14001b8df  mov     r8, rax; Size
0x14001b8e2  call    cs:__imp_RtlAllocateHeap
0x14001b8e8  mov     rbx, rax
0x14001b8eb  test    rax, rax
0x14001b8ee  jz      short loc_14001B90B
0x14001b8f0  mov     r8, r12; Size
0x14001b8f3  xor     edx, edx; Val
0x14001b8f5  mov     rcx, rax; void *
0x14001b8f8  call    memset_0
0x14001b8fd  jmp     short loc_14001B90B
0x14001b8ff  mov     r9, r12; Size
0x14001b902  call    cs:__imp_RtlReAllocateHeap
0x14001b908  mov     rbx, rax
0x14001b90b  mov     r12, [rsp+130h+var_100]
0x14001b910  test    rbx, rbx
0x14001b913  jnz     short loc_14001B91F
0x14001b915  mov     ebx, 0C0000017h
0x14001b91a  jmp     loc_14001B9CE
0x14001b91f  mov     [rdi+28h], rbx
0x14001b923  mov     r9d, 0C0000095h
0x14001b929  mov     [rdi+18h], rsi
0x14001b92d  mov     rax, r14
0x14001b930  mov     qword ptr [rsp+130h+var_F0], r13
0x14001b935  mul     qword ptr [rdi+8]
0x14001b939  test    rdx, rdx
0x14001b93c  jnz     loc_14001BEDB
0x14001b942  add     rax, [rdi+28h]
0x14001b946  cmp     rax, [rdi+28h]
0x14001b94a  jb      loc_14001BEDB
0x14001b950  movaps  xmm0, [rsp+130h+var_E0]
0x14001b955  movups  xmmword ptr [rax], xmm0
0x14001b958  movaps  xmm1, [rbp+57h+Source2]
0x14001b95c  movups  xmmword ptr [rax+10h], xmm1
0x14001b960  movaps  xmm0, [rbp+57h+var_C0]
0x14001b964  movups  xmmword ptr [rax+20h], xmm0
0x14001b968  movaps  xmm1, [rbp+57h+var_B0]
0x14001b96c  movups  xmmword ptr [rax+30h], xmm1
0x14001b970  movaps  xmm0, [rbp+57h+var_A0]
0x14001b974  movups  xmmword ptr [rax+40h], xmm0
0x14001b978  add     [rdi+10h], r15
0x14001b97c  xor     edx, edx; Val
0x14001b97e  lea     rcx, [rsp+130h+var_E0]; void *
0x14001b983  lea     r8d, [rdx+50h]; Size
0x14001b987  call    memset_0
0x14001b98c  xor     edx, edx
0x14001b98e  mov     r8d, 7001h
0x14001b994  mov     rcx, r12
0x14001b997  call    SdbFindFirstTag
0x14001b99c  test    eax, eax
0x14001b99e  jnz     short loc_14001B9D7
0x14001b9a0  lea     r9, aFailedToFindTa_10; "Failed to find TAG_DATABASE for pdb"
0x14001b9a7  mov     r8d, 0AF5h
0x14001b9ad  lea     rdx, aSdbpmergecolle_1; "SdbpMergeCollectAllMergeInformation"
0x14001b9b4  mov     ecx, r15d
0x14001b9b7  call    AslLogCallPrintf
0x14001b9bc  mov     eax, 0C00000E4h
0x14001b9c1  jmp     loc_14001BF0A
0x14001b9c6  mov     r12, [rsp+130h+var_100]
0x14001b9cb  mov     ebx, r9d
0x14001b9ce  test    ebx, ebx
0x14001b9d0  jns     short loc_14001B97C
0x14001b9d2  jmp     loc_14001BEDE
0x14001b9d7  mov     r8d, 704Ch
0x14001b9dd  mov     edx, eax
0x14001b9df  mov     rcx, r12
0x14001b9e2  call    SdbFindFirstTag
0x14001b9e7  mov     [rsp+130h+var_F0], eax
0x14001b9eb  mov     esi, eax
0x14001b9ed  test    eax, eax
0x14001b9ef  jnz     short loc_14001B9F8
0x14001b9f1  xor     ebx, ebx
0x14001b9f3  jmp     loc_14001BEFE
0x14001b9f8  mov     r8d, 704Dh
0x14001b9fe  mov     edx, eax
0x14001ba00  mov     rcx, r12
0x14001ba03  call    SdbFindFirstTag
0x14001ba08  jmp     loc_14001BC3A
0x14001ba0d  lea     r8, [rsp+130h+var_E0]
0x14001ba12  mov     edx, r13d
0x14001ba15  mov     rcx, r12
0x14001ba18  call    SdbMergeCollectPreviousMergeInfoFromDb
0x14001ba1d  mov     ebx, eax
0x14001ba1f  test    eax, eax
0x14001ba21  js      loc_14001BC9A
0x14001ba27  mov     rax, [rdi+10h]
0x14001ba2b  test    rax, rax
0x14001ba2e  jz      loc_14001BB04
0x14001ba34  xor     esi, esi
0x14001ba36  xor     ebx, ebx
0x14001ba38  cmp     rsi, rax
0x14001ba3b  jnb     short loc_14001BA58
0x14001ba3d  mov     rax, rsi
0x14001ba40  mul     qword ptr [rdi+8]
0x14001ba44  test    rdx, rdx
0x14001ba47  jnz     short loc_14001BA56
0x14001ba49  mov     rcx, [rdi+28h]
0x14001ba4d  lea     rbx, [rcx+rax]
0x14001ba51  cmp     rbx, rcx
0x14001ba54  jnb     short loc_14001BA58
0x14001ba56  xor     ebx, ebx
0x14001ba58  mov     eax, dword ptr [rbp+57h+var_B0+8]
0x14001ba5b  cmp     [rbx+38h], eax
0x14001ba5e  jnz     short loc_14001BAB1
0x14001ba60  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x14001ba63  cmp     [rbx+48h], eax
0x14001ba66  jnz     short loc_14001BAB1
0x14001ba68  lea     rcx, [rbx+18h]; Source1
0x14001ba6c  mov     r8d, 10h; Length
0x14001ba72  lea     rdx, [rbp+57h+Source2+8]; Source2
0x14001ba76  call    cs:__imp_RtlCompareMemory
0x14001ba7c  cmp     rax, 10h
0x14001ba80  jnz     short loc_14001BAB1
0x14001ba82  lea     rcx, [rbx+28h]; Source1
0x14001ba86  mov     r8, rax; Length
0x14001ba89  lea     rdx, [rbp+57h+var_C0+8]; Source2
0x14001ba8d  call    cs:__imp_RtlCompareMemory
0x14001ba93  cmp     rax, 10h
0x14001ba97  jnz     short loc_14001BAB1
0x14001ba99  lea     rcx, [rbx+10h]; Source1
0x14001ba9d  lea     r8d, [rax-8]; Length
0x14001baa1  lea     rdx, [rbp+57h+Source2]; Source2
0x14001baa5  call    cs:__imp_RtlCompareMemory
0x14001baab  cmp     rax, 8
0x14001baaf  jz      short loc_14001BAC3
0x14001bab1  mov     rax, [rdi+10h]
0x14001bab5  add     rsi, r15
0x14001bab8  cmp     rsi, rax
0x14001babb  jb      loc_14001BA36
0x14001bac1  jmp     short loc_14001BB04
0x14001bac3  lea     r8, [rbp+57h+Source2+8]
0x14001bac7  mov     edx, 27h ; '''
0x14001bacc  lea     rcx, [rbp+57h+var_90]
0x14001bad0  call    AslGuidToString
0x14001bad5  lea     rdx, aSdbpmergecolle_1; "SdbpMergeCollectAllMergeInformation"
0x14001badc  mov     ebx, eax
0x14001bade  mov     ecx, r15d
0x14001bae1  test    eax, eax
0x14001bae3  js      loc_14001BC6C
0x14001bae9  lea     rax, [rbp+57h+var_90]
0x14001baed  mov     r8d, 0B23h
0x14001baf3  lea     r9, aDuplicateDatab; "Duplicate database merged '%S'."
0x14001bafa  mov     [rsp+130h+var_110], rax
0x14001baff  call    AslLogCallPrintf
0x14001bb04  mov     r14, [rdi+10h]
0x14001bb08  cmp     r14, [rdi+18h]
0x14001bb0c  jb      loc_14001BBC6
0x14001bb12  lea     rcx, [r14+1]
0x14001bb16  cmp     rcx, [rdi+18h]
0x14001bb1a  ja      short loc_14001BB26
0x14001bb1c  mov     ebx, 0C000000Dh
0x14001bb21  jmp     loc_14001BC64
0x14001bb26  mov     rsi, [rdi+20h]
0x14001bb2a  dec     rsi
0x14001bb2d  lea     r8, [rcx+rsi]
0x14001bb31  cmp     r8, rcx
0x14001bb34  jb      loc_14001BC5F
0x14001bb3a  mov     rax, [rdi+8]
0x14001bb3e  mul     qword ptr [rdi+18h]
0x14001bb42  mov     [rsp+130h+var_F8], 0
0x14001bb4b  test    rdx, rdx
0x14001bb4e  jnz     loc_14001BC5F
0x14001bb54  mov     rax, [rdi+8]
0x14001bb58  not     rsi
0x14001bb5b  and     rsi, r8
0x14001bb5e  mov     [rsp+130h+var_F8], rdx
0x14001bb63  mul     rsi
0x14001bb66  mov     r12, rax
0x14001bb69  test    rdx, rdx
0x14001bb6c  jnz     loc_14001BC5A
0x14001bb72  mov     r8, [rdi+28h]; Ptr
0x14001bb76  mov     rcx, [rdi]; Heap
0x14001bb79  test    r8, r8
0x14001bb7c  jnz     short loc_14001BB9E
0x14001bb7e  mov     r8, rax; Size
0x14001bb81  call    cs:__imp_RtlAllocateHeap
0x14001bb87  mov     rbx, rax
0x14001bb8a  test    rax, rax
0x14001bb8d  jz      short loc_14001BBAA
0x14001bb8f  mov     r8, r12; Size
0x14001bb92  xor     edx, edx; Val
0x14001bb94  mov     rcx, rax; void *
0x14001bb97  call    memset_0
0x14001bb9c  jmp     short loc_14001BBAA
0x14001bb9e  mov     r9, r12; Size
0x14001bba1  call    cs:__imp_RtlReAllocateHeap
0x14001bba7  mov     rbx, rax
0x14001bbaa  mov     r12, [rsp+130h+var_100]
0x14001bbaf  test    rbx, rbx
0x14001bbb2  jnz     short loc_14001BBBE
0x14001bbb4  mov     ebx, 0C0000017h
0x14001bbb9  jmp     loc_14001BC64
0x14001bbbe  mov     [rdi+28h], rbx
0x14001bbc2  mov     [rdi+18h], rsi
0x14001bbc6  mov     rax, r14
0x14001bbc9  mov     [rsp+130h+var_F8], 0
0x14001bbd2  mul     qword ptr [rdi+8]
0x14001bbd6  test    rdx, rdx
0x14001bbd9  jnz     loc_14001BC82
0x14001bbdf  add     rax, [rdi+28h]
0x14001bbe3  cmp     rax, [rdi+28h]
0x14001bbe7  jb      loc_14001BC82
0x14001bbed  movaps  xmm0, [rsp+130h+var_E0]
0x14001bbf2  movups  xmmword ptr [rax], xmm0
0x14001bbf5  movaps  xmm1, [rbp+57h+Source2]
0x14001bbf9  movups  xmmword ptr [rax+10h], xmm1
0x14001bbfd  movaps  xmm0, [rbp+57h+var_C0]
0x14001bc01  movups  xmmword ptr [rax+20h], xmm0
0x14001bc05  movaps  xmm1, [rbp+57h+var_B0]
0x14001bc09  movups  xmmword ptr [rax+30h], xmm1
0x14001bc0d  movaps  xmm0, [rbp+57h+var_A0]
0x14001bc11  movups  xmmword ptr [rax+40h], xmm0
0x14001bc15  add     [rdi+10h], r15
0x14001bc19  xor     edx, edx; Val
0x14001bc1b  lea     rcx, [rsp+130h+var_E0]; void *
0x14001bc20  lea     r8d, [rdx+50h]; Size
0x14001bc24  call    memset_0
0x14001bc29  mov     esi, [rsp+130h+var_F0]
0x14001bc2d  mov     r8d, r13d
0x14001bc30  mov     edx, esi
0x14001bc32  mov     rcx, r12
0x14001bc35  call    SdbFindNextTag
0x14001bc3a  mov     r13d, eax
0x14001bc3d  test    eax, eax
0x14001bc3f  jnz     loc_14001BA0D
0x14001bc45  mov     r8d, 704Eh
0x14001bc4b  mov     edx, esi
0x14001bc4d  mov     rcx, r12
0x14001bc50  call    SdbFindFirstTag
0x14001bc55  jmp     loc_14001BE91
0x14001bc5a  mov     r12, [rsp+130h+var_100]
0x14001bc5f  mov     ebx, 0C0000095h
0x14001bc64  mov     eax, ebx
0x14001bc66  test    ebx, ebx
0x14001bc68  js      short loc_14001BC8B
0x14001bc6a  jmp     short loc_14001BC19
0x14001bc6c  mov     dword ptr [rsp+130h+var_110], eax
  ... truncated ...
```
