# BfspGetSystemPartition

- ea: `0x1800315c4`
- end: `0x18003185b`
- name: `BfspGetSystemPartition`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180031ac0`
- `0x1800340fc`

## callees

- `0x1800315c4`
- `0x1800366b8`
- `0x180039424`
- `0x18003d86c`
- `0x18007ec82`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800317d3`
- `ntdll!RtlFreeHeap` at `0x1800317d3`
- `ntdll!RtlNtStatusToDosError` at `0x180031838`
- `ntdll!RtlNtStatusToDosError` at `0x180031838`
- `ntdll!RtlAllocateHeap` at `0x1800316f2`
- `ntdll!RtlAllocateHeap` at `0x1800316f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003160c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031809`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003160c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031809`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031822`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003161d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031684`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003161d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031684`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800317b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031817`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800317b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031817`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031830`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031840`
- `bcd!SyspartGetSystemPartition` at `0x18003164c`
- `bcd!SyspartGetSystemPartition` at `0x1800316a0`
- `bcd!SyspartGetSystemPartition` at `0x18003164c`
- `bcd!SyspartGetSystemPartition` at `0x1800316a0`

## pseudocode

```c
wchar_t *BfspGetSystemPartition()
{
  __int64 v0; // rsi
  __int64 v1; // rax
  unsigned int v2; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  int SystemPartition; // eax
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  HANDLE v9; // rax
  wchar_t *v10; // rax
  wchar_t v11; // r12
  __int64 v12; // rax
  size_t v13; // rbx
  wchar_t *Heap; // r14
  HRESULT v15; // eax
  unsigned __int16 v16; // bx
  HRESULT v17; // eax
  HRESULT v18; // eax
  HANDLE v19; // rax
  HANDLE v20; // rax
  ULONG v21; // eax
  DWORD v23; // [rsp+30h] [rbp-10h]
  DWORD v24; // [rsp+30h] [rbp-10h]
  size_t Size; // [rsp+80h] [rbp+40h] BYREF
  size_t cchDest; // [rsp+88h] [rbp+48h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+90h] [rbp+50h] BYREF

  v0 = -1;
  LODWORD(Size) = 0;
  if ( BfspSystemPartitionName )
  {
    v1 = -1;
    do
      ++v1;
    while ( *((_WORD *)BfspSystemPartitionName + v1) );
    LODWORD(Size) = 2 * v1 + 2;
    v2 = Size;
    ProcessHeap = GetProcessHeap();
    v4 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v2);
    v5 = v4;
    if ( !v4 )
    {
LABEL_21:
      v7 = -1073741670;
      goto LABEL_22;
    }
    memcpy_0(v4, BfspSystemPartitionName, (unsigned int)Size);
LABEL_11:
    pszDest = 0;
    cchDest = 0;
    do
      ++v0;
    while ( v5[v0] );
    v11 = *v5;
    v12 = (unsigned int)v0 + (*v5 != 92) + 15;
    v13 = (unsigned int)v12;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v12);
    if ( Heap )
    {
      v15 = StringCchCopyNExW(Heap, v13, L"\\\\?\\GLOBALROOT", 0xEu, &pszDest, &cchDest, v23);
      v16 = v15;
      if ( v15 >= 0 )
      {
        if ( v11 == 92
          || (v17 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v24), v16 = v17, v17 >= 0) )
        {
          v18 = StringCchCopyNW(pszDest, cchDest, v5, (unsigned int)v0);
          v16 = v18;
          if ( v18 >= 0 )
          {
            NtCurrentTeb()->LastErrorValue = 0;
            v19 = GetProcessHeap();
            HeapFree(v19, 0, v5);
            return Heap;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v16;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
    goto LABEL_21;
  }
  SystemPartition = SyspartGetSystemPartition(0, 0, &Size);
  v7 = SystemPartition;
  if ( SystemPartition != -1073741789 )
  {
    v5 = 0;
    if ( SystemPartition >= 0 )
      v7 = -1073741823;
    goto LABEL_22;
  }
  v8 = Size;
  v9 = GetProcessHeap();
  v10 = (wchar_t *)HeapAlloc(v9, 8u, v8);
  v5 = v10;
  if ( !v10 )
    goto LABEL_21;
  v7 = SyspartGetSystemPartition(v10, (unsigned int)Size, &Size);
  if ( v7 >= 0 )
    goto LABEL_11;
LABEL_22:
  BfspLogMessage(4, L"Failed to get partition name. Status = %#x", (unsigned int)v7);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  v21 = RtlNtStatusToDosError(v7);
  SetLastError(v21);
  return 0;
}

```

## disassembly

```asm
0x1800315c4  mov     byte ptr [rsp-38h+Size], cl
0x1800315c8  push    rbp
0x1800315c9  push    rbx
0x1800315ca  push    rsi
0x1800315cb  push    rdi
0x1800315cc  push    r12
0x1800315ce  push    r13
0x1800315d0  push    r14
0x1800315d2  mov     rbp, rsp
0x1800315d5  sub     rsp, 40h
0x1800315d9  mov     rcx, cs:BfspSystemPartitionName
0x1800315e0  xor     r13d, r13d
0x1800315e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800315e7  mov     dword ptr [rbp+Size], r13d
0x1800315eb  mov     r14d, r13d
0x1800315ee  test    rcx, rcx
0x1800315f1  jz      short loc_180031644
0x1800315f3  mov     rax, rsi
0x1800315f6  inc     rax
0x1800315f9  cmp     [rcx+rax*2], r13w
0x1800315fe  jnz     short loc_1800315F6
0x180031600  lea     eax, ds:2[rax*2]
0x180031607  mov     dword ptr [rbp+Size], eax
0x18003160a  mov     ebx, eax
0x18003160c  call    cs:__imp_GetProcessHeap
0x180031612  mov     r8d, ebx; dwBytes
0x180031615  mov     edx, 8; dwFlags
0x18003161a  mov     rcx, rax; hHeap
0x18003161d  call    cs:__imp_HeapAlloc
0x180031623  mov     rdi, rax
0x180031626  test    rax, rax
0x180031629  jz      loc_1800317EB
0x18003162f  mov     r8d, dword ptr [rbp+Size]; Size
0x180031633  mov     rcx, rax; void *
0x180031636  mov     rdx, cs:BfspSystemPartitionName; Src
0x18003163d  call    memcpy_0
0x180031642  jmp     short loc_1800316B0
0x180031644  lea     r8, [rbp+Size]
0x180031648  xor     edx, edx
0x18003164a  xor     ecx, ecx
0x18003164c  call    cs:__imp_SyspartGetSystemPartition
0x180031652  mov     ebx, eax
0x180031654  cmp     eax, 0C0000023h
0x180031659  jz      short loc_180031670
0x18003165b  mov     rdi, r13
0x18003165e  test    eax, eax
0x180031660  js      loc_1800317F0
0x180031666  mov     ebx, 0C0000001h
0x18003166b  jmp     loc_1800317F0
0x180031670  mov     ebx, dword ptr [rbp+Size]
0x180031673  call    cs:__imp_GetProcessHeap
0x180031679  mov     r8d, ebx; dwBytes
0x18003167c  mov     edx, 8; dwFlags
0x180031681  mov     rcx, rax; hHeap
0x180031684  call    cs:__imp_HeapAlloc
0x18003168a  mov     rdi, rax
0x18003168d  test    rax, rax
0x180031690  jz      loc_1800317EB
0x180031696  mov     edx, dword ptr [rbp+Size]
0x180031699  lea     r8, [rbp+Size]
0x18003169d  mov     rcx, rax
0x1800316a0  call    cs:__imp_SyspartGetSystemPartition
0x1800316a6  mov     ebx, eax
0x1800316a8  test    eax, eax
0x1800316aa  js      loc_1800317F0
0x1800316b0  mov     [rbp+pszDest], r13
0x1800316b4  mov     [rbp+cchDest], r13
0x1800316b8  inc     rsi
0x1800316bb  cmp     [rdi+rsi*2], r13w
0x1800316c0  jnz     short loc_1800316B8
0x1800316c2  movzx   r12d, word ptr [rdi]
0x1800316c6  mov     eax, r13d
0x1800316c9  mov     ecx, 5Ch ; '\'
0x1800316ce  mov     edx, 8; Flags
0x1800316d3  cmp     cx, r12w
0x1800316d7  mov     rcx, gs:60h
0x1800316e0  setnz   al
0x1800316e3  add     eax, 0Fh
0x1800316e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800316ea  add     eax, esi
0x1800316ec  mov     ebx, eax
0x1800316ee  lea     r8, [rax+rax]; Size
0x1800316f2  call    cs:__imp_RtlAllocateHeap
0x1800316f8  mov     r14, rax
0x1800316fb  test    rax, rax
0x1800316fe  jnz     short loc_180031715
0x180031700  mov     rax, gs:30h
0x180031709  mov     dword ptr [rax+68h], 8
0x180031710  jmp     loc_1800317E8
0x180031715  lea     rax, [rbp+cchDest]
0x180031719  mov     r9d, 0Eh; cchToCopy
0x18003171f  mov     [rsp+40h+pcchRemaining], rax; pcchRemaining
0x180031724  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x18003172b  lea     rax, [rbp+pszDest]
0x18003172f  mov     rdx, rbx; cchDest
0x180031732  mov     rcx, r14; pszDest
0x180031735  mov     [rsp+40h+ppszDestEnd], rax; ppszDestEnd
0x18003173a  call    StringCchCopyNExW
0x18003173f  mov     ebx, eax
0x180031741  test    eax, eax
0x180031743  js      short loc_1800317C1
0x180031745  mov     eax, 5Ch ; '\'
0x18003174a  cmp     ax, r12w
0x18003174e  jz      short loc_180031782
0x180031750  mov     rdx, [rbp+cchDest]; cchDest
0x180031754  lea     rax, [rbp+cchDest]
0x180031758  mov     rcx, [rbp+pszDest]; pszDest
0x18003175c  lea     r8, asc_180084C70; "\\"
0x180031763  mov     [rsp+40h+pcchRemaining], rax; pcchRemaining
0x180031768  mov     r9d, 1; cchToCopy
0x18003176e  lea     rax, [rbp+pszDest]
0x180031772  mov     [rsp+40h+ppszDestEnd], rax; ppszDestEnd
0x180031777  call    StringCchCopyNExW
0x18003177c  mov     ebx, eax
0x18003177e  test    eax, eax
0x180031780  js      short loc_1800317C1
0x180031782  mov     rdx, [rbp+cchDest]; cchDest
0x180031786  mov     r8, rdi; pszSrc
0x180031789  mov     rcx, [rbp+pszDest]; pszDest
0x18003178d  mov     r9d, esi; cchToCopy
0x180031790  call    StringCchCopyNW
0x180031795  mov     ebx, eax
0x180031797  test    eax, eax
0x180031799  js      short loc_1800317C1
0x18003179b  mov     rax, gs:30h
0x1800317a4  mov     [rax+68h], r13d
0x1800317a8  call    cs:__imp_GetProcessHeap
0x1800317ae  mov     r8, rdi; lpMem
0x1800317b1  xor     edx, edx; dwFlags
0x1800317b3  mov     rcx, rax; hHeap
0x1800317b6  call    cs:__imp_HeapFree
0x1800317bc  jmp     loc_180031849
0x1800317c1  mov     rcx, gs:60h
0x1800317ca  mov     r8, r14; P
0x1800317cd  xor     edx, edx; Flags
0x1800317cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800317d3  call    cs:__imp_RtlFreeHeap
0x1800317d9  mov     rax, gs:30h
0x1800317e2  movzx   ecx, bx
0x1800317e5  mov     [rax+68h], ecx
0x1800317e8  mov     r14, r13
0x1800317eb  mov     ebx, 0C000009Ah
0x1800317f0  mov     r8d, ebx
0x1800317f3  lea     rdx, aFailedToGetPar; "Failed to get partition name. Status = "...
0x1800317fa  mov     ecx, 4
0x1800317ff  call    BfspLogMessage
0x180031804  test    r14, r14
0x180031807  jz      short loc_18003181D
0x180031809  call    cs:__imp_GetProcessHeap
0x18003180f  mov     r8, r14; lpMem
0x180031812  xor     edx, edx; dwFlags
0x180031814  mov     rcx, rax; hHeap
0x180031817  call    cs:__imp_HeapFree
0x18003181d  test    rdi, rdi
0x180031820  jz      short loc_180031836
0x180031822  call    cs:__imp_GetProcessHeap
0x180031828  mov     r8, rdi; lpMem
0x18003182b  xor     edx, edx; dwFlags
0x18003182d  mov     rcx, rax; hHeap
0x180031830  call    cs:__imp_HeapFree
0x180031836  mov     ecx, ebx; Status
0x180031838  call    cs:__imp_RtlNtStatusToDosError
0x18003183e  mov     ecx, eax; dwErrCode
0x180031840  call    cs:__imp_SetLastError
0x180031846  mov     r14, r13
0x180031849  mov     rax, r14
0x18003184c  add     rsp, 40h
0x180031850  pop     r14
0x180031852  pop     r13
0x180031854  pop     r12
0x180031856  pop     rdi
0x180031857  pop     rsi
0x180031858  pop     rbx
0x180031859  pop     rbp
0x18003185a  retn
```
