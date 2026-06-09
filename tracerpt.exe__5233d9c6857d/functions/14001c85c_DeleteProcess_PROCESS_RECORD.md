# DeleteProcess(_PROCESS_RECORD *)

- ea: `0x14001c85c`
- end: `0x14001cb68`
- name: `?DeleteProcess@@YAEPEAU_PROCESS_RECORD@@@Z`
- size: `780`
- prototype: `unsigned __int8 __fastcall(struct _PROCESS_RECORD *lpMem)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004778`
- `0x14001bd40`
- `0x14001db34`

## callees

- `0x14001bd40`
- `0x14001c85c`
- `0x14001cb70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c96e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c98b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c9c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ca5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ca77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cae4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c96e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c98b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c9c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ca5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ca77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cae4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001cb54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c97d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c9b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ca50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ca69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cad6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001caf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c97d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c9b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ca50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ca69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cad6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001caf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001cb46`
- `ntdll!RtlEnterCriticalSection` at `0x14001c88b`
- `ntdll!RtlEnterCriticalSection` at `0x14001c88b`
- `ntdll!RtlLeaveCriticalSection` at `0x14001c8b9`
- `ntdll!RtlLeaveCriticalSection` at `0x14001c8b9`

## pseudocode

```c
unsigned __int8 __fastcall DeleteProcess(struct _PROCESS_RECORD *lpMem)
{
  __int64 v3; // rdx
  struct _PROCESS_RECORD **v4; // rax
  struct _PROCESS_RECORD *v5; // rbx
  struct _THREAD_RECORD *v6; // rcx
  __int64 i; // rbp
  struct _THREAD_RECORD **v8; // rbx
  struct _THREAD_RECORD *v9; // rsi
  struct _THREAD_RECORD *v10; // rcx
  struct _PROCESS_RECORD *v11; // rsi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rax
  struct _PROCESS_RECORD **v21; // rcx
  struct _PROCESS_RECORD *v22; // rbx
  HANDLE v23; // rax
  struct _PROCESS_RECORD *v24; // rbx
  struct _PROCESS_RECORD *v25; // rcx
  _QWORD *v26; // rsi
  _QWORD *v27; // rbp
  _QWORD *v28; // rax
  _QWORD *v29; // r14
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  void *v32; // rbx
  HANDLE v33; // rax
  HANDLE v34; // rax
  struct _PROCESS_RECORD *v35; // rbx
  __int64 v36; // rax
  struct _PROCESS_RECORD **v37; // rcx
  struct _PROCESS_RECORD *v38; // rbp
  void *v39; // r14
  HANDLE v40; // rax
  HANDLE v41; // rax
  void *v42; // rbx
  HANDLE v43; // rax
  void *v44; // rbx
  HANDLE v45; // rax
  void *v46; // rbx
  HANDLE v47; // rax
  HANDLE v48; // rax

  if ( !lpMem )
    return 0;
  RtlEnterCriticalSection(&TLCritSect);
  v3 = *(_QWORD *)lpMem;
  if ( *(struct _PROCESS_RECORD **)(*(_QWORD *)lpMem + 8LL) != lpMem
    || (v4 = (struct _PROCESS_RECORD **)*((_QWORD *)lpMem + 1), *v4 != lpMem) )
  {
LABEL_53:
    __fastfail(3u);
  }
  *v4 = (struct _PROCESS_RECORD *)v3;
  *(_QWORD *)(v3 + 8) = v4;
  RtlLeaveCriticalSection(&TLCritSect);
  v5 = (struct _PROCESS_RECORD *)*((_QWORD *)lpMem + 2);
  if ( v5 == (struct _PROCESS_RECORD *)((char *)lpMem + 16) )
  {
    for ( i = 0; i != 29; ++i )
    {
      v8 = (struct _THREAD_RECORD **)(qword_140082128 + 16 * i);
      v9 = *v8;
      while ( v9 != (struct _THREAD_RECORD *)v8 )
      {
        v10 = v9;
        v9 = *(struct _THREAD_RECORD **)v9;
        if ( *((struct _PROCESS_RECORD **)v10 + 11) == lpMem )
          DeleteThread(v10);
      }
    }
  }
  else
  {
    do
    {
      v6 = v5;
      v5 = *(struct _PROCESS_RECORD **)v5;
      DeleteThread(v6);
    }
    while ( v5 != (struct _PROCESS_RECORD *)((char *)lpMem + 16) );
  }
  v11 = (struct _PROCESS_RECORD *)*((_QWORD *)lpMem + 4);
  while ( v11 != (struct _PROCESS_RECORD *)((char *)lpMem + 32) )
  {
    v12 = (void *)*((_QWORD *)v11 + 5);
    if ( v12 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    v14 = (void *)*((_QWORD *)v11 + 6);
    if ( v14 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    v16 = (void *)*((_QWORD *)v11 + 7);
    if ( v16 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v16);
    }
    v18 = (void *)*((_QWORD *)v11 + 8);
    if ( v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    v20 = *(_QWORD *)v11;
    if ( *(struct _PROCESS_RECORD **)(*(_QWORD *)v11 + 8LL) != v11 )
      goto LABEL_53;
    v21 = (struct _PROCESS_RECORD **)*((_QWORD *)v11 + 1);
    if ( *v21 != v11 )
      goto LABEL_53;
    *v21 = (struct _PROCESS_RECORD *)v20;
    v22 = v11;
    v11 = (struct _PROCESS_RECORD *)v20;
    *(_QWORD *)(v20 + 8) = v21;
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  v24 = (struct _PROCESS_RECORD *)*((_QWORD *)lpMem + 6);
  while ( v24 != (struct _PROCESS_RECORD *)((char *)lpMem + 48) )
  {
    v25 = v24;
    v24 = *(struct _PROCESS_RECORD **)v24;
    DeleteDisk(v25);
  }
  v26 = (_QWORD *)*((_QWORD *)lpMem + 10);
  if ( v26 != (_QWORD *)((char *)lpMem + 80) )
  {
    do
    {
      v27 = (_QWORD *)*v26;
      if ( *(_QWORD **)(*v26 + 8LL) != v26 )
        goto LABEL_53;
      v28 = (_QWORD *)v26[1];
      if ( (_QWORD *)*v28 != v26 )
        goto LABEL_53;
      *v28 = v27;
      v27[1] = v28;
      v29 = (_QWORD *)v26[8];
      while ( v29 != v26 + 8 )
      {
        v30 = (_QWORD *)*v29;
        if ( *(_QWORD **)(*v29 + 8LL) != v29 )
          goto LABEL_53;
        v31 = (_QWORD *)v29[1];
        if ( (_QWORD *)*v31 != v29 )
          goto LABEL_53;
        *v31 = v30;
        v32 = v29;
        v29 = v30;
        v30[1] = v31;
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v32);
      }
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v26);
      v26 = v27;
    }
    while ( v27 != (_QWORD *)((char *)lpMem + 80) );
  }
  v35 = (struct _PROCESS_RECORD *)*((_QWORD *)lpMem + 8);
  while ( v35 != (struct _PROCESS_RECORD *)((char *)lpMem + 64) )
  {
    v36 = *(_QWORD *)v35;
    if ( *(struct _PROCESS_RECORD **)(*(_QWORD *)v35 + 8LL) != v35 )
      goto LABEL_53;
    v37 = (struct _PROCESS_RECORD **)*((_QWORD *)v35 + 1);
    if ( *v37 != v35 )
      goto LABEL_53;
    v38 = v35;
    *v37 = (struct _PROCESS_RECORD *)v36;
    *(_QWORD *)(v36 + 8) = v37;
    v35 = (struct _PROCESS_RECORD *)v36;
    v39 = (void *)*((_QWORD *)v38 + 9);
    if ( v39 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v38);
  }
  v42 = (void *)*((_QWORD *)lpMem + 13);
  if ( v42 )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v42);
  }
  v44 = (void *)*((_QWORD *)lpMem + 12);
  if ( v44 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v44);
  }
  v46 = (void *)*((_QWORD *)lpMem + 14);
  if ( v46 )
  {
    v47 = GetProcessHeap();
    HeapFree(v47, 0, v46);
  }
  v48 = GetProcessHeap();
  HeapFree(v48, 0, lpMem);
  return 1;
}

```

## disassembly

```asm
0x14001c85c  push    rbx
0x14001c85e  push    rbp
0x14001c85f  push    rsi
0x14001c860  push    rdi
0x14001c861  push    r12
0x14001c863  push    r14
0x14001c865  push    r15
0x14001c867  sub     rsp, 20h
0x14001c86b  mov     rdi, rcx
0x14001c86e  test    rcx, rcx
0x14001c871  jnz     short loc_14001C884
0x14001c873  xor     al, al
0x14001c875  add     rsp, 20h
0x14001c879  pop     r15
0x14001c87b  pop     r14
0x14001c87d  pop     r12
0x14001c87f  pop     rdi
0x14001c880  pop     rsi
0x14001c881  pop     rbp
0x14001c882  pop     rbx
0x14001c883  retn
0x14001c884  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001c88b  call    cs:__imp_RtlEnterCriticalSection
0x14001c891  mov     rdx, [rdi]
0x14001c894  cmp     [rdx+8], rdi
0x14001c898  jnz     loc_14001CB61
0x14001c89e  mov     rax, [rdi+8]
0x14001c8a2  cmp     [rax], rdi
0x14001c8a5  jnz     loc_14001CB61
0x14001c8ab  mov     [rax], rdx
0x14001c8ae  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001c8b5  mov     [rdx+8], rax
0x14001c8b9  call    cs:__imp_RtlLeaveCriticalSection
0x14001c8bf  lea     rsi, [rdi+10h]
0x14001c8c3  mov     rbx, [rsi]
0x14001c8c6  cmp     rbx, rsi
0x14001c8c9  jz      short loc_14001C8DD
0x14001c8cb  mov     rcx, rbx; lpMem
0x14001c8ce  mov     rbx, [rbx]
0x14001c8d1  call    ?DeleteThread@@YAEPEAU_THREAD_RECORD@@@Z; DeleteThread(_THREAD_RECORD *)
0x14001c8d6  cmp     rbx, rsi
0x14001c8d9  jnz     short loc_14001C8CB
0x14001c8db  jmp     short loc_14001C911
0x14001c8dd  xor     ebp, ebp
0x14001c8df  mov     rbx, rbp
0x14001c8e2  shl     rbx, 4
0x14001c8e6  add     rbx, cs:qword_140082128
0x14001c8ed  mov     rsi, [rbx]
0x14001c8f0  jmp     short loc_14001C903
0x14001c8f2  mov     rcx, rsi; lpMem
0x14001c8f5  mov     rsi, [rsi]
0x14001c8f8  cmp     [rcx+58h], rdi
0x14001c8fc  jnz     short loc_14001C903
0x14001c8fe  call    ?DeleteThread@@YAEPEAU_THREAD_RECORD@@@Z; DeleteThread(_THREAD_RECORD *)
0x14001c903  cmp     rsi, rbx
0x14001c906  jnz     short loc_14001C8F2
0x14001c908  inc     rbp
0x14001c90b  cmp     rbp, 1Dh
0x14001c90f  jnz     short loc_14001C8DF
0x14001c911  lea     r14, [rdi+20h]
0x14001c915  mov     rsi, [r14]
0x14001c918  jmp     loc_14001C9CC
0x14001c91d  mov     rbx, [rsi+28h]
0x14001c921  test    rbx, rbx
0x14001c924  jz      short loc_14001C93A
0x14001c926  call    cs:__imp_GetProcessHeap
0x14001c92c  mov     r8, rbx; lpMem
0x14001c92f  xor     edx, edx; dwFlags
0x14001c931  mov     rcx, rax; hHeap
0x14001c934  call    cs:__imp_HeapFree
0x14001c93a  mov     rbx, [rsi+30h]
0x14001c93e  test    rbx, rbx
0x14001c941  jz      short loc_14001C957
0x14001c943  call    cs:__imp_GetProcessHeap
0x14001c949  mov     r8, rbx; lpMem
0x14001c94c  xor     edx, edx; dwFlags
0x14001c94e  mov     rcx, rax; hHeap
0x14001c951  call    cs:__imp_HeapFree
0x14001c957  mov     rbx, [rsi+38h]
0x14001c95b  test    rbx, rbx
0x14001c95e  jz      short loc_14001C974
0x14001c960  call    cs:__imp_GetProcessHeap
0x14001c966  mov     r8, rbx; lpMem
0x14001c969  xor     edx, edx; dwFlags
0x14001c96b  mov     rcx, rax; hHeap
0x14001c96e  call    cs:__imp_HeapFree
0x14001c974  mov     rbx, [rsi+40h]
0x14001c978  test    rbx, rbx
0x14001c97b  jz      short loc_14001C991
0x14001c97d  call    cs:__imp_GetProcessHeap
0x14001c983  mov     r8, rbx; lpMem
0x14001c986  xor     edx, edx; dwFlags
0x14001c988  mov     rcx, rax; hHeap
0x14001c98b  call    cs:__imp_HeapFree
0x14001c991  mov     rax, [rsi]
0x14001c994  cmp     [rax+8], rsi
0x14001c998  jnz     loc_14001CB61
0x14001c99e  mov     rcx, [rsi+8]
0x14001c9a2  cmp     [rcx], rsi
0x14001c9a5  jnz     loc_14001CB61
0x14001c9ab  mov     [rcx], rax
0x14001c9ae  mov     rbx, rsi
0x14001c9b1  mov     rsi, rax
0x14001c9b4  mov     [rax+8], rcx
0x14001c9b8  call    cs:__imp_GetProcessHeap
0x14001c9be  mov     r8, rbx; lpMem
0x14001c9c1  xor     edx, edx; dwFlags
0x14001c9c3  mov     rcx, rax; hHeap
0x14001c9c6  call    cs:__imp_HeapFree
0x14001c9cc  cmp     rsi, r14
0x14001c9cf  jnz     loc_14001C91D
0x14001c9d5  lea     rsi, [rdi+30h]
0x14001c9d9  mov     rbx, [rsi]
0x14001c9dc  jmp     short loc_14001C9E9
0x14001c9de  mov     rcx, rbx; lpMem
0x14001c9e1  mov     rbx, [rbx]
0x14001c9e4  call    DeleteDisk
0x14001c9e9  cmp     rbx, rsi
0x14001c9ec  jnz     short loc_14001C9DE
0x14001c9ee  lea     r15, [rdi+50h]
0x14001c9f2  mov     rsi, [r15]
0x14001c9f5  cmp     rsi, r15
0x14001c9f8  jz      loc_14001CA89
0x14001c9fe  mov     rbp, [rsi]
0x14001ca01  cmp     [rbp+8], rsi
0x14001ca05  jnz     loc_14001CB61
0x14001ca0b  mov     rax, [rsi+8]
0x14001ca0f  cmp     [rax], rsi
0x14001ca12  jnz     loc_14001CB61
0x14001ca18  mov     [rax], rbp
0x14001ca1b  lea     r12, [rsi+40h]
0x14001ca1f  mov     [rbp+8], rax
0x14001ca23  mov     r14, [r12]
0x14001ca27  jmp     short loc_14001CA64
0x14001ca29  mov     rax, [r14]
0x14001ca2c  cmp     [rax+8], r14
0x14001ca30  jnz     loc_14001CB61
0x14001ca36  mov     rcx, [r14+8]
0x14001ca3a  cmp     [rcx], r14
0x14001ca3d  jnz     loc_14001CB61
0x14001ca43  mov     [rcx], rax
0x14001ca46  mov     rbx, r14
0x14001ca49  mov     r14, rax
0x14001ca4c  mov     [rax+8], rcx
0x14001ca50  call    cs:__imp_GetProcessHeap
0x14001ca56  mov     r8, rbx; lpMem
0x14001ca59  xor     edx, edx; dwFlags
0x14001ca5b  mov     rcx, rax; hHeap
0x14001ca5e  call    cs:__imp_HeapFree
0x14001ca64  cmp     r14, r12
0x14001ca67  jnz     short loc_14001CA29
0x14001ca69  call    cs:__imp_GetProcessHeap
0x14001ca6f  mov     r8, rsi; lpMem
0x14001ca72  xor     edx, edx; dwFlags
0x14001ca74  mov     rcx, rax; hHeap
0x14001ca77  call    cs:__imp_HeapFree
0x14001ca7d  mov     rsi, rbp
0x14001ca80  cmp     rbp, r15
0x14001ca83  jnz     loc_14001C9FE
0x14001ca89  lea     rsi, [rdi+40h]
0x14001ca8d  mov     rbx, [rsi]
0x14001ca90  jmp     short loc_14001CAEA
0x14001ca92  mov     rax, [rbx]
0x14001ca95  cmp     [rax+8], rbx
0x14001ca99  jnz     loc_14001CB61
0x14001ca9f  mov     rcx, [rbx+8]
0x14001caa3  cmp     [rcx], rbx
0x14001caa6  jnz     loc_14001CB61
0x14001caac  mov     rbp, rbx
0x14001caaf  mov     [rcx], rax
0x14001cab2  mov     [rax+8], rcx
0x14001cab6  mov     rbx, rax
0x14001cab9  mov     r14, [rbp+48h]
0x14001cabd  test    r14, r14
0x14001cac0  jz      short loc_14001CAD6
0x14001cac2  call    cs:__imp_GetProcessHeap
0x14001cac8  mov     r8, r14; lpMem
0x14001cacb  xor     edx, edx; dwFlags
0x14001cacd  mov     rcx, rax; hHeap
0x14001cad0  call    cs:__imp_HeapFree
0x14001cad6  call    cs:__imp_GetProcessHeap
0x14001cadc  mov     r8, rbp; lpMem
0x14001cadf  xor     edx, edx; dwFlags
0x14001cae1  mov     rcx, rax; hHeap
0x14001cae4  call    cs:__imp_HeapFree
0x14001caea  cmp     rbx, rsi
0x14001caed  jnz     short loc_14001CA92
0x14001caef  mov     rbx, [rdi+68h]
0x14001caf3  test    rbx, rbx
0x14001caf6  jz      short loc_14001CB0C
0x14001caf8  call    cs:__imp_GetProcessHeap
0x14001cafe  mov     r8, rbx; lpMem
0x14001cb01  xor     edx, edx; dwFlags
0x14001cb03  mov     rcx, rax; hHeap
0x14001cb06  call    cs:__imp_HeapFree
0x14001cb0c  mov     rbx, [rdi+60h]
0x14001cb10  test    rbx, rbx
0x14001cb13  jz      short loc_14001CB29
0x14001cb15  call    cs:__imp_GetProcessHeap
0x14001cb1b  mov     r8, rbx; lpMem
0x14001cb1e  xor     edx, edx; dwFlags
0x14001cb20  mov     rcx, rax; hHeap
0x14001cb23  call    cs:__imp_HeapFree
0x14001cb29  mov     rbx, [rdi+70h]
0x14001cb2d  test    rbx, rbx
0x14001cb30  jz      short loc_14001CB46
0x14001cb32  call    cs:__imp_GetProcessHeap
0x14001cb38  mov     r8, rbx; lpMem
0x14001cb3b  xor     edx, edx; dwFlags
0x14001cb3d  mov     rcx, rax; hHeap
0x14001cb40  call    cs:__imp_HeapFree
0x14001cb46  call    cs:__imp_GetProcessHeap
0x14001cb4c  mov     r8, rdi; lpMem
0x14001cb4f  xor     edx, edx; dwFlags
0x14001cb51  mov     rcx, rax; hHeap
0x14001cb54  call    cs:__imp_HeapFree
0x14001cb5a  mov     al, 1
0x14001cb5c  jmp     loc_14001C875
0x14001cb61  mov     ecx, 3
0x14001cb66  int     29h; Win8: RtlFailFast(ecx)
```
