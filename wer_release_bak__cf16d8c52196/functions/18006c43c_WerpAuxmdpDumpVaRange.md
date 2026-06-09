# WerpAuxmdpDumpVaRange

- ea: `0x18006c43c`
- end: `0x18006c622`
- name: `WerpAuxmdpDumpVaRange`
- size: `486`
- prototype: `__int64 __fastcall(__int64, _DWORD *, signed int *, __int64, DWORD NumberOfBytesWritten)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005a84`
- `0x180016c48`

## callees

- `0x18001c650`
- `0x18003bf14`
- `0x18005b8d1`
- `0x18006c43c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c5d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c5d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c57b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c526`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006c4c1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006c4c1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006c502`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006c502`

## pseudocode

```c
__int64 __fastcall WerpAuxmdpDumpVaRange(
        __int64 a1,
        _DWORD *a2,
        signed int *a3,
        __int64 a4,
        DWORD NumberOfBytesWritten)
{
  unsigned int v5; // ebp
  __int64 i; // rdi
  void *v12; // r8
  void *v13; // rcx
  unsigned int v14; // eax
  bool v15; // cf
  __int64 v16; // rdx
  __int64 v17; // rcx
  DWORD v18; // r8d
  signed int LastError; // eax
  SIZE_T v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rdx
  HANDLE v25; // rcx
  void *v26; // r8
  unsigned int v27; // ebx
  SIZE_T NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  v5 = NumberOfBytesWritten;
  *a2 = 0;
  *a3 = 0;
  if ( !v5 )
    return 0;
  for ( i = 0; (unsigned int)i < v5; i = NumberOfBytesWritten + (unsigned int)i )
  {
    v12 = *(void **)(a1 + 32);
    v13 = *(void **)a1;
    v14 = v5 - i;
    NumberOfBytesRead = 0;
    v15 = v5 - (unsigned int)i < *(_DWORD *)(a1 + 40);
    NumberOfBytesWritten = 0;
    if ( !v15 )
      v14 = *(_DWORD *)(a1 + 40);
    if ( !ReadProcessMemory(v13, (LPCVOID)(i + a4), v12, v14, &NumberOfBytesRead) )
      goto LABEL_15;
    v18 = NumberOfBytesRead;
    if ( !NumberOfBytesRead )
    {
      *a3 = -2147024597;
      goto LABEL_21;
    }
    if ( NumberOfBytesRead > 0xFFFFFFFF )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16);
      v18 = NumberOfBytesRead;
    }
    if ( !WriteFile(*(HANDLE *)(a1 + 8), *(LPCVOID *)(a1 + 32), v18, &NumberOfBytesWritten, 0) )
    {
LABEL_15:
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *a3 = LastError;
      goto LABEL_21;
    }
    if ( !NumberOfBytesWritten )
    {
      *a3 = -2147024867;
      goto LABEL_21;
    }
  }
  *a3 = 0;
  if ( (unsigned int)i > v5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
LABEL_21:
  v20 = 24LL * (unsigned int)(*(_DWORD *)(a1 + 48) + 1);
  if ( !is_mul_ok((unsigned int)(*(_DWORD *)(a1 + 48) + 1), 0x18u) )
    v20 = -1;
  v21 = HeapAlloc(g_hWerheap, 0, v20);
  NumberOfBytesRead = (SIZE_T)v21;
  v22 = v21;
  if ( v21 )
  {
    memcpy_0(v21, *(const void **)(a1 + 56), 24LL * *(unsigned int *)(a1 + 48));
    v23 = *(unsigned int *)(a1 + 48);
    *a2 = i;
    v24 = 3 * v23;
    v25 = g_hWerheap;
    v22[v24] = a4;
    LODWORD(v22[v24 + 2]) = i;
    v22[v24 + 1] = *(_QWORD *)(a1 + 16);
    v26 = *(void **)(a1 + 56);
    *(_QWORD *)(a1 + 16) += (unsigned int)i;
    HeapFree(v25, 0, v26);
    ++*(_DWORD *)(a1 + 48);
    *(_QWORD *)(a1 + 56) = v22;
    v27 = 0;
    NumberOfBytesRead = 0;
    if ( !(_DWORD)i )
      v27 = -2147024597;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&NumberOfBytesRead);
    return v27;
  }
  else
  {
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&NumberOfBytesRead);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18006c43c  mov     [rsp+arg_0], rbx
0x18006c441  mov     [rsp+arg_10], rbp
0x18006c446  push    rsi
0x18006c447  push    rdi
0x18006c448  push    r12
0x18006c44a  push    r14
0x18006c44c  push    r15
0x18006c44e  sub     rsp, 30h
0x18006c452  mov     ebp, [rsp+58h+NumberOfBytesWritten]
0x18006c459  mov     r12, r9
0x18006c45c  mov     dword ptr [rdx], 0
0x18006c462  mov     rbx, r8
0x18006c465  mov     dword ptr [r8], 0
0x18006c46c  mov     r14, rdx
0x18006c46f  mov     rsi, rcx
0x18006c472  test    ebp, ebp
0x18006c474  jnz     short loc_18006C47D
0x18006c476  xor     eax, eax
0x18006c478  jmp     loc_18006C60B
0x18006c47d  xor     edi, edi
0x18006c47f  mov     r15d, edi
0x18006c482  cmp     edi, ebp
0x18006c484  jnb     loc_18006C545
0x18006c48a  mov     r8, [rsi+20h]; lpBuffer
0x18006c48e  lea     rdx, [rdi+r12]; lpBaseAddress
0x18006c492  mov     rcx, [rsi]; hProcess
0x18006c495  mov     eax, ebp
0x18006c497  sub     eax, edi
0x18006c499  mov     [rsp+58h+NumberOfBytesRead], 0
0x18006c4a2  cmp     eax, [rsi+28h]
0x18006c4a5  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18006c4b0  cmovnb  eax, [rsi+28h]
0x18006c4b4  mov     r9d, eax; nSize
0x18006c4b7  lea     rax, [rsp+58h+NumberOfBytesRead]
0x18006c4bc  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18006c4c1  call    cs:__imp_ReadProcessMemory
0x18006c4c7  test    eax, eax
0x18006c4c9  jz      short loc_18006C526
0x18006c4cb  mov     r8, [rsp+58h+NumberOfBytesRead]
0x18006c4d0  test    r8, r8
0x18006c4d3  jz      short loc_18006C53C
0x18006c4d5  mov     eax, 0FFFFFFFFh
0x18006c4da  cmp     r8, rax
0x18006c4dd  jbe     short loc_18006C4E9
0x18006c4df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006c4e4  mov     r8, [rsp+58h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18006c4e9  mov     rdx, [rsi+20h]; lpBuffer
0x18006c4ed  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006c4f5  mov     rcx, [rsi+8]; hFile
0x18006c4f9  mov     [rsp+58h+lpNumberOfBytesRead], 0; lpOverlapped
0x18006c502  call    cs:__imp_WriteFile
0x18006c508  test    eax, eax
0x18006c50a  jz      short loc_18006C526
0x18006c50c  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x18006c513  test    eax, eax
0x18006c515  jz      short loc_18006C51E
0x18006c517  add     edi, eax
0x18006c519  jmp     loc_18006C47F
0x18006c51e  mov     dword ptr [rbx], 8007001Dh
0x18006c524  jmp     short loc_18006C552
0x18006c526  call    cs:__imp_GetLastError
0x18006c52c  test    eax, eax
0x18006c52e  jle     short loc_18006C538
0x18006c530  movzx   eax, ax
0x18006c533  or      eax, 80070000h
0x18006c538  mov     [rbx], eax
0x18006c53a  jmp     short loc_18006C552
0x18006c53c  mov     ebp, 8007012Bh
0x18006c541  mov     [rbx], ebp
0x18006c543  jmp     short loc_18006C557
0x18006c545  mov     dword ptr [rbx], 0
0x18006c54b  jbe     short loc_18006C552
0x18006c54d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006c552  mov     ebp, 8007012Bh
0x18006c557  mov     ecx, [rsi+30h]
0x18006c55a  mov     eax, 18h
0x18006c55f  inc     ecx
0x18006c561  mul     rcx
0x18006c564  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006c56b  cmovb   rax, rcx
0x18006c56f  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006c576  mov     r8, rax; dwBytes
0x18006c579  xor     edx, edx; dwFlags
0x18006c57b  call    cs:__imp_HeapAlloc
0x18006c581  mov     [rsp+58h+NumberOfBytesRead], rax
0x18006c586  mov     rbx, rax
0x18006c589  test    rax, rax
0x18006c58c  jz      short loc_18006C5FC
0x18006c58e  mov     ecx, [rsi+30h]
0x18006c591  mov     rdx, [rsi+38h]; Src
0x18006c595  lea     r8, [rcx+rcx*2]
0x18006c599  mov     rcx, rax; void *
0x18006c59c  shl     r8, 3; Size
0x18006c5a0  call    memcpy_0
0x18006c5a5  mov     ecx, [rsi+30h]
0x18006c5a8  mov     [r14], edi
0x18006c5ab  lea     rdx, [rcx+rcx*2]
0x18006c5af  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006c5b6  mov     [rbx+rdx*8], r12
0x18006c5ba  mov     [rbx+rdx*8+10h], edi
0x18006c5be  mov     rax, [rsi+10h]
0x18006c5c2  mov     [rbx+rdx*8+8], rax
0x18006c5c7  xor     edx, edx; dwFlags
0x18006c5c9  mov     r8, [rsi+38h]; lpMem
0x18006c5cd  add     [rsi+10h], r15
0x18006c5d1  call    cs:__imp_HeapFree
0x18006c5d7  inc     dword ptr [rsi+30h]
0x18006c5da  lea     rcx, [rsp+58h+NumberOfBytesRead]; void *
0x18006c5df  mov     [rsi+38h], rbx
0x18006c5e3  xor     ebx, ebx
0x18006c5e5  test    edi, edi
0x18006c5e7  mov     [rsp+58h+NumberOfBytesRead], 0
0x18006c5f0  cmovz   ebx, ebp
0x18006c5f3  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18006c5f8  mov     eax, ebx
0x18006c5fa  jmp     short loc_18006C60B
0x18006c5fc  lea     rcx, [rsp+58h+NumberOfBytesRead]; void *
0x18006c601  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18006c606  mov     eax, 8007000Eh
0x18006c60b  mov     rbx, [rsp+58h+arg_0]
0x18006c610  mov     rbp, [rsp+58h+arg_10]
0x18006c615  add     rsp, 30h
0x18006c619  pop     r15
0x18006c61b  pop     r14
0x18006c61d  pop     r12
0x18006c61f  pop     rdi
0x18006c620  pop     rsi
0x18006c621  retn
```
