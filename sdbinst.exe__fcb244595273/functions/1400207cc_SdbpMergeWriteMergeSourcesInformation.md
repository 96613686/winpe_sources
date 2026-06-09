# SdbpMergeWriteMergeSourcesInformation

- ea: `0x1400207cc`
- end: `0x140020a82`
- name: `SdbpMergeWriteMergeSourcesInformation`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140014500`
- `0x140014b64`
- `0x14001a834`
- `0x14001b7e8`
- `0x14001fc0c`
- `0x1400207cc`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!qsort` at `0x1400208af`
- `msvcrt!qsort` at `0x1400208af`
- `ntdll!RtlAllocateHeap` at `0x140020851`
- `ntdll!RtlAllocateHeap` at `0x140020851`
- `ntdll!RtlFreeHeap` at `0x140020a69`
- `ntdll!RtlFreeHeap` at `0x140020a69`

## string_xrefs

- `0x1400208d6`: `SdbpMergeWriteMergeSourcesInformation`
- `0x140020925`: `SdbpMergeWriteMergeSourcesInformation`
- `0x1400209fc`: `SdbpMergeWriteMergeSourcesInformation`
- `0x140020a0f`: `Failed to write open source/merge tag`
- `0x1400208c9`: `Failed to write open SDB_MERGE_INFO tag`
- `0x1400209d9`: `Failed to write end source/merge tag`
- `0x1400209eb`: `SdbpMergeWriteDbInfo failed to write source db info [%x]`
- `0x1400209c7`: `Failed to write end SDB_MERGE_INFO tag`

## pseudocode

```c
__int64 __fastcall SdbpMergeWriteMergeSourcesInformation(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  PVOID ProcessHeap; // r14
  PVOID Heap; // rax
  void *v9; // rbx
  size_t v10; // rsi
  char *v11; // rdi
  unsigned __int128 v12; // rax
  unsigned int v13; // r13d
  unsigned int v14; // ebx
  unsigned __int64 v15; // r14
  __int64 v16; // rbx
  unsigned int v17; // r12d
  int v18; // eax
  unsigned __int64 i; // r14
  char *v20; // rcx
  __int64 v21; // rax
  HANDLE HeapHandle[2]; // [rsp+38h] [rbp-40h] BYREF
  size_t NumOfElements[2]; // [rsp+48h] [rbp-30h]
  void *Base[2]; // [rsp+58h] [rbp-20h]

  HeapHandle[0] = 0;
  Base[0] = (void *)8;
  NumOfElements[0] = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  HeapHandle[0] = ProcessHeap;
  NumOfElements[1] = 0;
  HeapHandle[1] = (HANDLE)80;
  if ( !is_mul_ok(0, 0x50u) || !is_mul_ok(8u, 0x50u) )
  {
    v14 = -1073741675;
    goto LABEL_9;
  }
  Heap = RtlAllocateHeap(ProcessHeap, (8 * (unsigned __int128)0x50u) >> 64, 0x280u);
  v9 = Heap;
  if ( !Heap )
  {
    v14 = -1073741801;
LABEL_9:
    *(_OWORD *)HeapHandle = 0;
    *(_OWORD *)NumOfElements = 0;
    *(_OWORD *)Base = 0;
    AslLogCallPrintf(
      1,
      "SdbpMergeWriteMergeSourcesInformation",
      2934,
      "RtlArrayInitialize failed to init merge info array [%x]",
      v14);
    v11 = 0;
    v10 = 0;
    goto LABEL_25;
  }
  memset_0(Heap, 0, 0x280u);
  Base[1] = v9;
  NumOfElements[1] = 8;
  SdbpMergeCollectAllMergeInformation(a2, (__int64)HeapHandle);
  SdbpMergeCollectAllMergeInformation(a3, (__int64)HeapHandle);
  v10 = NumOfElements[0];
  v11 = (char *)Base[1];
  qsort(Base[1], NumOfElements[0], 0x50u, SdbpMergeCompareDbMergeInfo);
  v13 = SdbBeginWriteListTag(a1, 28748);
  if ( !v13 )
  {
    AslLogCallPrintf(1, "SdbpMergeWriteMergeSourcesInformation", 2948, "Failed to write open SDB_MERGE_INFO tag");
LABEL_6:
    v14 = -1073741595;
    goto LABEL_25;
  }
  v15 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      v16 = 0;
      if ( v15 < v10 )
      {
        v12 = (unsigned __int64)HeapHandle[1] * (unsigned __int128)v15;
        if ( !is_mul_ok((unsigned __int64)HeapHandle[1], v15)
          || (v16 = (__int64)&v11[v12], &v11[(unsigned __int64)v12] < v11) )
        {
          v16 = 0;
        }
      }
      WORD4(v12) = (*(_DWORD *)(v16 + 76) != 0) + 28749;
      v17 = SdbBeginWriteListTag(a1, *((__int64 *)&v12 + 1));
      if ( !v17 )
        break;
      v18 = SdbpMergeWriteDbInfo(a1, v16, a4);
      v14 = v18;
      if ( v18 < 0 )
      {
        AslLogCallPrintf(
          1,
          "SdbpMergeWriteMergeSourcesInformation",
          2965,
          "SdbpMergeWriteDbInfo failed to write source db info [%x]",
          v18);
        goto LABEL_25;
      }
      if ( !(unsigned int)SdbEndWriteListTag(a1, v17) )
      {
        AslLogCallPrintf(1, "SdbpMergeWriteMergeSourcesInformation", 2970, "Failed to write end source/merge tag");
        goto LABEL_6;
      }
      if ( ++v15 >= v10 )
        goto LABEL_19;
    }
    AslLogCallPrintf(1, "SdbpMergeWriteMergeSourcesInformation", 2958, "Failed to write open source/merge tag");
    goto LABEL_6;
  }
LABEL_19:
  if ( !(unsigned int)SdbEndWriteListTag(a1, v13) )
  {
    AslLogCallPrintf(1, "SdbpMergeWriteMergeSourcesInformation", 2977, "Failed to write end SDB_MERGE_INFO tag");
    goto LABEL_6;
  }
  v14 = 0;
LABEL_25:
  if ( v11 )
  {
    for ( i = 0; i < v10; ++i )
    {
      v20 = 0;
      if ( i < v10 )
      {
        v21 = (unsigned __int64)HeapHandle[1] * i;
        if ( !is_mul_ok((unsigned __int64)HeapHandle[1], i) || (v20 = &v11[v21], &v11[v21] < v11) )
          v20 = 0;
      }
      SdbMergeFreePdbInformation(v20);
    }
    RtlFreeHeap(HeapHandle[0], 0, v11);
  }
  return v14;
}

```

## disassembly

```asm
0x1400207cc  mov     [rsp-40h+arg_18], r9d
0x1400207d1  push    rbp
0x1400207d2  push    rbx
0x1400207d3  push    rsi
0x1400207d4  push    rdi
0x1400207d5  push    r12
0x1400207d7  push    r13
0x1400207d9  push    r14
0x1400207db  push    r15
0x1400207dd  mov     rbp, rsp
0x1400207e0  sub     rsp, 78h
0x1400207e4  mov     rax, gs:60h
0x1400207ed  mov     r12, r8
0x1400207f0  mov     r8d, 8
0x1400207f6  mov     [rbp+HeapHandle], 0
0x1400207fe  mov     r15, rcx
0x140020801  mov     [rbp+Base], r8
0x140020805  xor     ecx, ecx
0x140020807  mov     [rbp+NumOfElements], 0
0x14002080f  mov     r14, [rax+30h]
0x140020813  mov     r13, rdx
0x140020816  lea     r9d, [r8+48h]
0x14002081a  mov     [rbp+HeapHandle], r14
0x14002081e  mov     eax, r9d
0x140020821  mov     [rbp+NumOfElements+8], 0
0x140020829  mul     rcx
0x14002082c  mov     [rbp+HeapHandle+8], r9
0x140020830  test    rdx, rdx
0x140020833  jnz     loc_1400208F8
0x140020839  mov     eax, r9d
0x14002083c  mul     r8
0x14002083f  mov     rdi, rax
0x140020842  test    rdx, rdx
0x140020845  jnz     loc_1400208F8
0x14002084b  mov     r8, rax; Size
0x14002084e  mov     rcx, r14; HeapHandle
0x140020851  call    cs:__imp_RtlAllocateHeap
0x140020857  mov     rbx, rax
0x14002085a  test    rax, rax
0x14002085d  jz      loc_1400208F1
0x140020863  mov     r8, rdi; Size
0x140020866  xor     edx, edx; Val
0x140020868  mov     rcx, rax; void *
0x14002086b  call    memset_0
0x140020870  mov     [rbp+Base+8], rbx
0x140020874  mov     [rbp+NumOfElements+8], 8
0x14002087c  lea     rdx, [rbp+HeapHandle]
0x140020880  mov     rcx, r13
0x140020883  call    SdbpMergeCollectAllMergeInformation
0x140020888  lea     rdx, [rbp+HeapHandle]
0x14002088c  mov     rcx, r12
0x14002088f  call    SdbpMergeCollectAllMergeInformation
0x140020894  mov     rsi, [rbp+NumOfElements]
0x140020898  lea     r9, SdbpMergeCompareDbMergeInfo; CompareFunction
0x14002089f  mov     rdi, [rbp+Base+8]
0x1400208a3  mov     rdx, rsi; NumOfElements
0x1400208a6  mov     rcx, rdi; Base
0x1400208a9  mov     r8d, 50h ; 'P'; SizeOfElements
0x1400208af  call    cs:__imp_qsort
0x1400208b5  mov     edx, 704Ch
0x1400208ba  mov     rcx, r15
0x1400208bd  call    SdbBeginWriteListTag
0x1400208c2  mov     r13d, eax
0x1400208c5  test    eax, eax
0x1400208c7  jnz     short loc_140020943
0x1400208c9  lea     r9, aFailedToWriteO_0; "Failed to write open SDB_MERGE_INFO tag"
0x1400208d0  mov     r8d, 0B84h
0x1400208d6  lea     rdx, aSdbpmergewrite_4; "SdbpMergeWriteMergeSourcesInformation"
0x1400208dd  mov     ecx, 1
0x1400208e2  call    AslLogCallPrintf
0x1400208e7  mov     ebx, 0C00000E5h
0x1400208ec  jmp     loc_140020A23
0x1400208f1  mov     ebx, 0C0000017h
0x1400208f6  jmp     short loc_1400208FD
0x1400208f8  mov     ebx, 0C0000095h
0x1400208fd  xorps   xmm0, xmm0
0x140020900  movups  xmmword ptr [rbp+HeapHandle], xmm0
0x140020904  movups  xmmword ptr [rbp+NumOfElements], xmm0
0x140020908  movups  xmmword ptr [rbp+Base], xmm0
0x14002090c  test    ebx, ebx
0x14002090e  jns     loc_14002087C
0x140020914  lea     r9, aRtlarrayinitia_6; "RtlArrayInitialize failed to init merge"...
0x14002091b  mov     [rsp+78h+var_58], ebx
0x14002091f  mov     r8d, 0B76h
0x140020925  lea     rdx, aSdbpmergewrite_4; "SdbpMergeWriteMergeSourcesInformation"
0x14002092c  mov     ecx, 1
0x140020931  call    AslLogCallPrintf
0x140020936  mov     rdi, [rbp+Base+8]
0x14002093a  mov     rsi, [rbp+NumOfElements]
0x14002093e  jmp     loc_140020A23
0x140020943  xor     r14d, r14d
0x140020946  test    rsi, rsi
0x140020949  jz      short loc_1400209B8
0x14002094b  xor     ebx, ebx
0x14002094d  cmp     r14, rsi
0x140020950  jnb     short loc_140020969
0x140020952  mov     rax, r14
0x140020955  mul     [rbp+HeapHandle+8]
0x140020959  test    rdx, rdx
0x14002095c  jnz     short loc_140020967
0x14002095e  lea     rbx, [rdi+rax]
0x140020962  cmp     rbx, rdi
0x140020965  jnb     short loc_140020969
0x140020967  xor     ebx, ebx
0x140020969  mov     eax, [rbx+4Ch]
0x14002096c  mov     rcx, r15
0x14002096f  neg     eax
0x140020971  sbb     dx, dx
0x140020974  neg     dx
0x140020977  add     dx, 704Dh
0x14002097c  call    SdbBeginWriteListTag
0x140020981  mov     r12d, eax
0x140020984  test    eax, eax
0x140020986  jz      loc_140020A0F
0x14002098c  mov     r8d, [rbp+arg_18]
0x140020990  mov     rdx, rbx
0x140020993  mov     rcx, r15
0x140020996  call    SdbpMergeWriteDbInfo
0x14002099b  mov     ebx, eax
0x14002099d  test    eax, eax
0x14002099f  js      short loc_1400209EB
0x1400209a1  mov     edx, r12d
0x1400209a4  mov     rcx, r15
0x1400209a7  call    SdbEndWriteListTag
0x1400209ac  test    eax, eax
0x1400209ae  jz      short loc_1400209D9
0x1400209b0  inc     r14
0x1400209b3  cmp     r14, rsi
0x1400209b6  jb      short loc_14002094B
0x1400209b8  mov     edx, r13d
0x1400209bb  mov     rcx, r15
0x1400209be  call    SdbEndWriteListTag
0x1400209c3  test    eax, eax
0x1400209c5  jnz     short loc_140020A21
0x1400209c7  lea     r9, aFailedToWriteE_0; "Failed to write end SDB_MERGE_INFO tag"
0x1400209ce  mov     r8d, 0BA1h
0x1400209d4  jmp     loc_1400208D6
0x1400209d9  lea     r9, aFailedToWriteE; "Failed to write end source/merge tag"
0x1400209e0  mov     r8d, 0B9Ah
0x1400209e6  jmp     loc_1400208D6
0x1400209eb  lea     r9, aSdbpmergewrite_0; "SdbpMergeWriteDbInfo failed to write so"...
0x1400209f2  mov     [rsp+78h+var_58], eax
0x1400209f6  mov     r8d, 0B95h
0x1400209fc  lea     rdx, aSdbpmergewrite_4; "SdbpMergeWriteMergeSourcesInformation"
0x140020a03  mov     ecx, 1
0x140020a08  call    AslLogCallPrintf
0x140020a0d  jmp     short loc_140020A23
0x140020a0f  lea     r9, aFailedToWriteO; "Failed to write open source/merge tag"
0x140020a16  mov     r8d, 0B8Eh
0x140020a1c  jmp     loc_1400208D6
0x140020a21  xor     ebx, ebx
0x140020a23  test    rdi, rdi
0x140020a26  jz      short loc_140020A6F
0x140020a28  xor     r14d, r14d
0x140020a2b  test    rsi, rsi
0x140020a2e  jz      short loc_140020A5B
0x140020a30  xor     ecx, ecx
0x140020a32  cmp     r14, rsi
0x140020a35  jnb     short loc_140020A4E
0x140020a37  mov     rax, r14
0x140020a3a  mul     [rbp+HeapHandle+8]
0x140020a3e  test    rdx, rdx
0x140020a41  jnz     short loc_140020A4C
0x140020a43  lea     rcx, [rdi+rax]
0x140020a47  cmp     rcx, rdi
0x140020a4a  jnb     short loc_140020A4E
0x140020a4c  xor     ecx, ecx; void *
0x140020a4e  call    SdbMergeFreePdbInformation
0x140020a53  inc     r14
0x140020a56  cmp     r14, rsi
0x140020a59  jb      short loc_140020A30
0x140020a5b  test    rdi, rdi
0x140020a5e  jz      short loc_140020A6F
0x140020a60  mov     rcx, [rbp+HeapHandle]; HeapHandle
0x140020a64  mov     r8, rdi; P
0x140020a67  xor     edx, edx; Flags
0x140020a69  call    cs:__imp_RtlFreeHeap
0x140020a6f  mov     eax, ebx
0x140020a71  add     rsp, 78h
0x140020a75  pop     r15
0x140020a77  pop     r14
0x140020a79  pop     r13
0x140020a7b  pop     r12
0x140020a7d  pop     rdi
0x140020a7e  pop     rsi
0x140020a7f  pop     rbx
0x140020a80  pop     rbp
0x140020a81  retn
```
