# WerpAuxmdpDumpVaRange

- ea: `0x18006f600`
- end: `0x18006f805`
- name: `WerpAuxmdpDumpVaRange`
- size: `517`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD NumberOfBytesWritten)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a768`
- `0x18001b6cc`

## callees

- `0x18001e0d0`
- `0x18003de9c`
- `0x18005dd11`
- `0x18006f600`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f7ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f7ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f751`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f6f6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f685`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f685`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006f6cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006f6cc`

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
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, NumberOfBytesRead);
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
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
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
0x18006f600  mov     [rsp+arg_0], rbx
0x18006f605  mov     [rsp+arg_10], rbp
0x18006f60a  push    rsi
0x18006f60b  push    rdi
0x18006f60c  push    r12
0x18006f60e  push    r14
0x18006f610  push    r15
0x18006f612  sub     rsp, 30h
0x18006f616  mov     ebp, [rsp+58h+NumberOfBytesWritten]
0x18006f61d  mov     r12, r9
0x18006f620  mov     dword ptr [rdx], 0
0x18006f626  mov     rbx, r8
0x18006f629  mov     dword ptr [r8], 0
0x18006f630  mov     r14, rdx
0x18006f633  mov     rsi, rcx
0x18006f636  test    ebp, ebp
0x18006f638  jnz     short loc_18006F641
0x18006f63a  xor     eax, eax
0x18006f63c  jmp     loc_18006F7ED
0x18006f641  xor     edi, edi
0x18006f643  mov     r15d, edi
0x18006f646  cmp     edi, ebp
0x18006f648  jnb     loc_18006F71B
0x18006f64e  mov     r8, [rsi+20h]; lpBuffer
0x18006f652  lea     rdx, [rdi+r12]; lpBaseAddress
0x18006f656  mov     rcx, [rsi]; hProcess
0x18006f659  mov     eax, ebp
0x18006f65b  sub     eax, edi
0x18006f65d  mov     [rsp+58h+NumberOfBytesRead], 0
0x18006f666  cmp     eax, [rsi+28h]
0x18006f669  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18006f674  cmovnb  eax, [rsi+28h]
0x18006f678  mov     r9d, eax; nSize
0x18006f67b  lea     rax, [rsp+58h+NumberOfBytesRead]
0x18006f680  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18006f685  call    cs:__imp_ReadProcessMemory
0x18006f68c  nop     dword ptr [rax+rax+00h]
0x18006f691  test    eax, eax
0x18006f693  jz      short loc_18006F6F6
0x18006f695  mov     r8, [rsp+58h+NumberOfBytesRead]
0x18006f69a  test    r8, r8
0x18006f69d  jz      short loc_18006F712
0x18006f69f  mov     eax, 0FFFFFFFFh
0x18006f6a4  cmp     r8, rax
0x18006f6a7  jbe     short loc_18006F6B3
0x18006f6a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006f6ae  mov     r8, [rsp+58h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18006f6b3  mov     rdx, [rsi+20h]; lpBuffer
0x18006f6b7  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006f6bf  mov     rcx, [rsi+8]; hFile
0x18006f6c3  mov     [rsp+58h+lpNumberOfBytesRead], 0; lpOverlapped
0x18006f6cc  call    cs:__imp_WriteFile
0x18006f6d3  nop     dword ptr [rax+rax+00h]
0x18006f6d8  test    eax, eax
0x18006f6da  jz      short loc_18006F6F6
0x18006f6dc  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x18006f6e3  test    eax, eax
0x18006f6e5  jz      short loc_18006F6EE
0x18006f6e7  add     edi, eax
0x18006f6e9  jmp     loc_18006F643
0x18006f6ee  mov     dword ptr [rbx], 8007001Dh
0x18006f6f4  jmp     short loc_18006F728
0x18006f6f6  call    cs:__imp_GetLastError
0x18006f6fd  nop     dword ptr [rax+rax+00h]
0x18006f702  test    eax, eax
0x18006f704  jle     short loc_18006F70E
0x18006f706  movzx   eax, ax
0x18006f709  or      eax, 80070000h
0x18006f70e  mov     [rbx], eax
0x18006f710  jmp     short loc_18006F728
0x18006f712  mov     ebp, 8007012Bh
0x18006f717  mov     [rbx], ebp
0x18006f719  jmp     short loc_18006F72D
0x18006f71b  mov     dword ptr [rbx], 0
0x18006f721  jbe     short loc_18006F728
0x18006f723  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006f728  mov     ebp, 8007012Bh
0x18006f72d  mov     ecx, [rsi+30h]
0x18006f730  mov     eax, 18h
0x18006f735  inc     ecx
0x18006f737  mul     rcx
0x18006f73a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006f741  cmovb   rax, rcx
0x18006f745  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006f74c  mov     r8, rax; dwBytes
0x18006f74f  xor     edx, edx; dwFlags
0x18006f751  call    cs:__imp_HeapAlloc
0x18006f758  nop     dword ptr [rax+rax+00h]
0x18006f75d  mov     [rsp+58h+NumberOfBytesRead], rax
0x18006f762  mov     rbx, rax
0x18006f765  test    rax, rax
0x18006f768  jz      short loc_18006F7DE
0x18006f76a  mov     ecx, [rsi+30h]
0x18006f76d  mov     rdx, [rsi+38h]; Src
0x18006f771  lea     r8, [rcx+rcx*2]
0x18006f775  mov     rcx, rax; void *
0x18006f778  shl     r8, 3; Size
0x18006f77c  call    memcpy_0
0x18006f781  mov     ecx, [rsi+30h]
0x18006f784  mov     [r14], edi
0x18006f787  lea     rdx, [rcx+rcx*2]
0x18006f78b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006f792  mov     [rbx+rdx*8], r12
0x18006f796  mov     [rbx+rdx*8+10h], edi
0x18006f79a  mov     rax, [rsi+10h]
0x18006f79e  mov     [rbx+rdx*8+8], rax
0x18006f7a3  xor     edx, edx; dwFlags
0x18006f7a5  mov     r8, [rsi+38h]; lpMem
0x18006f7a9  add     [rsi+10h], r15
0x18006f7ad  call    cs:__imp_HeapFree
0x18006f7b4  nop     dword ptr [rax+rax+00h]
0x18006f7b9  inc     dword ptr [rsi+30h]
0x18006f7bc  lea     rcx, [rsp+58h+NumberOfBytesRead]; void *
0x18006f7c1  mov     [rsi+38h], rbx
0x18006f7c5  xor     ebx, ebx
0x18006f7c7  test    edi, edi
0x18006f7c9  mov     [rsp+58h+NumberOfBytesRead], 0
0x18006f7d2  cmovz   ebx, ebp
0x18006f7d5  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18006f7da  mov     eax, ebx
0x18006f7dc  jmp     short loc_18006F7ED
0x18006f7de  lea     rcx, [rsp+58h+NumberOfBytesRead]; void *
0x18006f7e3  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18006f7e8  mov     eax, 8007000Eh
0x18006f7ed  mov     rbx, [rsp+58h+arg_0]
0x18006f7f2  mov     rbp, [rsp+58h+arg_10]
0x18006f7f7  add     rsp, 30h
0x18006f7fb  pop     r15
0x18006f7fd  pop     r14
0x18006f7ff  pop     r12
0x18006f801  pop     rdi
0x18006f802  pop     rsi
0x18006f803  retn
```
