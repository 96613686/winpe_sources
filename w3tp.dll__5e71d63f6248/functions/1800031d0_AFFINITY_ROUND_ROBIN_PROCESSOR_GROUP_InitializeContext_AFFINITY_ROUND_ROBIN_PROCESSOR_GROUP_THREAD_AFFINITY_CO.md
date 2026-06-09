# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)

- ea: `0x1800031d0`
- end: `0x180003306`
- name: `?InitializeContext@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJPEAUTHREAD_AFFINITY_CONTEXT@1@@Z`
- size: `310`
- prototype: `__int64 __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this, struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002ddc`

## callees

- `0x1800031d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800032b1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800032b1`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800032d3`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800032d3`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800031fc`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180003266`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800031fc`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180003266`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000323f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000323f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000324d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000324d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032bb`

## pseudocode

```c
__int64 __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *this,
        struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rdi
  signed int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF

  dwBytes = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &dwBytes) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 122 )
    {
LABEL_3:
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v4;
    }
  }
  v5 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v7 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 8u, v5);
  v8 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    v4 = LastError;
    goto LABEL_3;
  }
  if ( InitializeProcThreadAttributeList(v7, 1u, 0, &dwBytes) )
  {
    if ( UpdateProcThreadAttribute(v8, 0, 0x30003u, (char *)a2 + 8, 0x10u, 0, 0) )
    {
      v4 = 0;
      *(_QWORD *)a2 = v8;
      return v4;
    }
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    DeleteProcThreadAttributeList(v8);
  }
  else
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
  }
  v11 = GetProcessHeap();
  HeapFree(v11, 0, v8);
  return v4;
}

```

## disassembly

```asm
0x1800031d0  mov     rax, rsp
0x1800031d3  mov     [rax+10h], rbx
0x1800031d7  mov     [rax+18h], rsi
0x1800031db  mov     [rax+8], rcx
0x1800031df  push    rdi
0x1800031e0  sub     rsp, 40h
0x1800031e4  xor     r8d, r8d; dwFlags
0x1800031e7  mov     qword ptr [rax+8], 0
0x1800031ef  mov     rsi, rdx
0x1800031f2  lea     r9, [rax+8]; lpSize
0x1800031f6  xor     ecx, ecx; lpAttributeList
0x1800031f8  lea     edx, [r8+1]; dwAttributeCount
0x1800031fc  call    cs:__imp_InitializeProcThreadAttributeList
0x180003202  test    eax, eax
0x180003204  jnz     short loc_180003229
0x180003206  call    cs:__imp_GetLastError
0x18000320c  mov     ebx, eax
0x18000320e  cmp     eax, 7Ah ; 'z'
0x180003211  jz      short loc_180003229
0x180003213  test    eax, eax
0x180003215  jle     loc_1800032F4
0x18000321b  movzx   ebx, ax
0x18000321e  or      ebx, 80070000h
0x180003224  jmp     loc_1800032F4
0x180003229  mov     rbx, [rsp+48h+dwBytes]
0x18000322e  call    cs:__imp_GetProcessHeap
0x180003234  mov     r8, rbx; dwBytes
0x180003237  mov     edx, 8; dwFlags
0x18000323c  mov     rcx, rax; hHeap
0x18000323f  call    cs:__imp_HeapAlloc
0x180003245  mov     rdi, rax
0x180003248  test    rax, rax
0x18000324b  jnz     short loc_180003257
0x18000324d  call    cs:__imp_GetLastError
0x180003253  mov     ebx, eax
0x180003255  jmp     short loc_180003213
0x180003257  xor     r8d, r8d; dwFlags
0x18000325a  lea     r9, [rsp+48h+dwBytes]; lpSize
0x18000325f  mov     rcx, rdi; lpAttributeList
0x180003262  lea     edx, [r8+1]; dwAttributeCount
0x180003266  call    cs:__imp_InitializeProcThreadAttributeList
0x18000326c  test    eax, eax
0x18000326e  jnz     short loc_180003287
0x180003270  call    cs:__imp_GetLastError
0x180003276  mov     ebx, eax
0x180003278  test    eax, eax
0x18000327a  jle     short loc_1800032D9
0x18000327c  movzx   ebx, ax
0x18000327f  or      ebx, 80070000h
0x180003285  jmp     short loc_1800032D9
0x180003287  mov     [rsp+48h+lpReturnSize], 0; lpReturnSize
0x180003290  lea     r9, [rsi+8]; lpValue
0x180003294  mov     [rsp+48h+lpPreviousValue], 0; lpPreviousValue
0x18000329d  xor     edx, edx; dwFlags
0x18000329f  mov     r8d, 30003h; Attribute
0x1800032a5  mov     [rsp+48h+cbSize], 10h; cbSize
0x1800032ae  mov     rcx, rdi; lpAttributeList
0x1800032b1  call    cs:__imp_UpdateProcThreadAttribute
0x1800032b7  test    eax, eax
0x1800032b9  jnz     short loc_1800032EF
0x1800032bb  call    cs:__imp_GetLastError
0x1800032c1  mov     ebx, eax
0x1800032c3  test    eax, eax
0x1800032c5  jle     short loc_1800032D0
0x1800032c7  movzx   ebx, ax
0x1800032ca  or      ebx, 80070000h
0x1800032d0  mov     rcx, rdi; lpAttributeList
0x1800032d3  call    cs:__imp_DeleteProcThreadAttributeList
0x1800032d9  call    cs:__imp_GetProcessHeap
0x1800032df  mov     r8, rdi; lpMem
0x1800032e2  xor     edx, edx; dwFlags
0x1800032e4  mov     rcx, rax; hHeap
0x1800032e7  call    cs:__imp_HeapFree
0x1800032ed  jmp     short loc_1800032F4
0x1800032ef  xor     ebx, ebx
0x1800032f1  mov     [rsi], rdi
0x1800032f4  mov     rsi, [rsp+48h+arg_10]
0x1800032f9  mov     eax, ebx
0x1800032fb  mov     rbx, [rsp+48h+arg_8]
0x180003300  add     rsp, 40h
0x180003304  pop     rdi
0x180003305  retn
```
