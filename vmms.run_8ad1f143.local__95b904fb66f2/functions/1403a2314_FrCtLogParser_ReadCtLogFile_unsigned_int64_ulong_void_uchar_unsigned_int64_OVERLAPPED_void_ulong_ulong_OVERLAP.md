# FrCtLogParser::ReadCtLogFile(unsigned __int64,ulong,void *,uchar,unsigned __int64,_OVERLAPPED *,void (*)(ulong,ulong,_OVERLAPPED *))

- ea: `0x1403a2314`
- end: `0x1403a2950`
- name: `?ReadCtLogFile@FrCtLogParser@@AEAAJ_KKPEAXE0PEAU_OVERLAPPED@@P6AXKK2@Z@Z`
- size: `1596`
- prototype: `__int64 __usercall@<rax>(FrCtLogParser *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, void *@<r9>, char, unsigned __int64, LPOVERLAPPED lpOverlapped, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1405995bc`
- `0x14059b648`
- `0x14059b9d8`
- `0x14059baac`
- `0x14059be8c`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x1401879a4`
- `0x1403a2314`
- `0x1404828e0`
- `0x140486128`
- `0x140486535`
- `0x140599758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1403a25dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1403a27a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1403a25dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1403a27a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403a26e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403a2899`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403a26e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403a2899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a23f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a25f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a267d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a27b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a2837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a23f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a25f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a267d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a27b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403a2837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403a2914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403a2914`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x1403a23df`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x1403a23df`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1403a266f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1403a2829`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1403a266f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1403a2829`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1403a2709`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1403a28b9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1403a2709`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1403a28b9`

## pseudocode

```c
__int64 __fastcall FrCtLogParser::ReadCtLogFile(
        FrCtLogParser *this,
        unsigned __int64 a2,
        unsigned int a3,
        void *a4,
        char a5,
        unsigned __int64 a6,
        LPOVERLAPPED lpOverlapped,
        void (*a8)(unsigned int, unsigned int, struct _OVERLAPPED *))
{
  DWORD v8; // ebx
  void (__stdcall *v10)(DWORD, DWORD, LPOVERLAPPED); // rdx
  void *v11; // r10
  size_t v13; // r12
  char v14; // di
  signed int v15; // edi
  signed int LastError; // eax
  _QWORD *v17; // rcx
  unsigned __int64 v18; // r15
  size_t v19; // rdi
  void *v20; // rax
  signed int v21; // eax
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // r8
  wchar_t **v25; // rdx
  BOOL v26; // ebx
  DWORD v27; // eax
  __int64 v28; // r8
  __int64 v29; // rcx
  wchar_t **v30; // rdx
  signed int v31; // eax
  int v32; // r15d
  bool v33; // sf
  unsigned int v34; // r15d
  BOOL v35; // ebx
  DWORD v36; // eax
  __int64 v37; // r8
  LPOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+20h] [rbp-71h]
  LPOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutinea; // [rsp+20h] [rbp-71h]
  int v41; // [rsp+40h] [rbp-51h]
  DWORD v43; // [rsp+54h] [rbp-3Dh]
  __int64 v44; // [rsp+58h] [rbp-39h]
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-31h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp-11h] BYREF

  v8 = 0x2000000;
  v43 = HIDWORD(a2);
  v10 = a8;
  v11 = a4;
  v13 = a3;
  NumberOfBytesTransferred = 0;
  v44 = 0x2000000;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( a3 <= 0x2000000 )
  {
    v14 = a5;
  }
  else
  {
    v14 = 0;
    if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      VmlDebugTraceEx(49568, &off_1409173A0, (unsigned int)v13, a4);
    v11 = a4;
    v10 = a8;
  }
  if ( v10 )
  {
    lpOverlapped->Offset = a2;
    lpOverlapped->OffsetHigh = v43;
    v15 = 0;
    if ( !ReadFileEx(*(HANDLE *)(*((_QWORD *)this + 10) + 8 * a6), v11, v13, lpOverlapped, v10) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        VmlDebugTraceEx(49568, &off_140917388, a6, *(_QWORD *)(*((_QWORD *)this + 10) + 8 * a6));
    }
    goto LABEL_76;
  }
  Overlapped.Pointer = (PVOID)__PAIR64__(v43, a2);
  Overlapped.hEvent = 0;
  if ( v14 )
  {
    if ( *((_DWORD *)this + 120) == a6 )
    {
      v17 = (_QWORD *)((char *)this + 224);
    }
    else
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        lpCompletionRoutine = (LPOVERLAPPED_COMPLETION_ROUTINE)(*((_QWORD *)this + 78) >> 20);
        VmlDebugTraceEx(49568, &off_140917370, a6, *(_QWORD *)(*((_QWORD *)this + 10) + 8 * a6));
      }
      v17 = (_QWORD *)((char *)this + 224);
      *((_QWORD *)this + 27) = 0;
      *((_QWORD *)this + 28) = 0;
    }
    v18 = *((_QWORD *)this + 27);
    if ( a2 < v18 || (v19 = v13, v13 + a2 > *v17) )
    {
      if ( !*((_QWORD *)this + 26) )
      {
        v20 = operator new[](0x2000000u, (const struct std::nothrow_t *)std::nothrow);
        *((_QWORD *)this + 26) = v20;
        if ( !v20 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
            VmlDebugTraceEx(16800, &off_140917358, 0x2000000, *(_QWORD *)(*((_QWORD *)this + 10) + 8 * a6));
          v15 = 8;
          goto LABEL_76;
        }
      }
      v18 = -1;
      if ( (unsigned int)v13 < 0x2000000 )
      {
        v8 = FrCtLogParser::GetLengthForLogFileRead(this, a6, a2, (unsigned int)a4, v13);
        v44 = v8;
      }
      if ( *((_DWORD *)this + 145) )
      {
        if ( v13 + a2 <= v8 )
          v18 = 0;
        else
          v18 = a2 + v13 - v8;
        Overlapped.Pointer = (PVOID)v18;
      }
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( !Overlapped.hEvent )
      {
        v21 = (unsigned __int16)GetLastError();
        v15 = v21;
        v41 = (unsigned __int16)v21;
        if ( (_WORD)v21 )
          v21 = (unsigned __int16)v21 | 0x80070000;
        if ( v21 < 0 )
        {
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_76;
          if ( v15 > 0 )
            v23 = v41 | 0x80070000;
          else
            v23 = v15;
          v24 = v23;
          v25 = &off_1408C0C28;
          goto LABEL_41;
        }
      }
      v26 = ReadFile(*(HANDLE *)(*((_QWORD *)this + 10) + 8 * a6), *((LPVOID *)this + 26), v8, 0, &Overlapped);
      v27 = GetLastError();
      v15 = v27;
      if ( !v26 && v27 != 997 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          if ( v15 > 0 )
            v28 = (unsigned __int16)v15 | 0x80070000;
          else
            v28 = (unsigned int)v15;
          VmlDebugTraceWithError(16800, &off_1408C0C58, v28, v44, *(_QWORD *)(*((_QWORD *)this + 10) + 8 * a6));
        }
        goto LABEL_76;
      }
      WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
      GetOverlappedResult(*(HANDLE *)(*((_QWORD *)this + 10) + 8 * a6), &Overlapped, &NumberOfBytesTransferred, 1);
      v29 = NumberOfBytesTransferred;
      if ( !*((_DWORD *)this + 145) )
        v18 = a2;
      *((_DWORD *)this + 120) = a6;
      *((_QWORD *)this + 78) += v29;
      *((_QWORD *)this + 27) = v18;
      *((_QWORD *)this + 28) = v29 + v18;
      if ( NumberOfBytesTransferred < (unsigned int)v13 )
      {
        v15 = 38;
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
          goto LABEL_76;
        v30 = &off_1409174F0;
        goto LABEL_75;
      }
      v19 = v13;
    }
    memcpy_0(a4, (const void *)(a2 + *((_QWORD *)this + 26) - v18), v19);
    *((_QWORD *)this + 79) += v19;
    v15 = 0;
    goto LABEL_76;
  }
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
  {
    v31 = GetLastError();
    v32 = (unsigned __int16)v31;
    v15 = v31;
    v33 = v31 < 0;
    if ( v31 > 0 )
      v33 = 1;
    if ( v33 )
    {
      if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
        goto LABEL_76;
      if ( v15 > 0 )
        v34 = v32 | 0x80070000;
      else
        v34 = v15;
      v24 = v34;
      v25 = &off_1408C0C40;
LABEL_41:
      VmlDebugTraceWithError(16800, v25, v24, v22, lpCompletionRoutine);
      goto LABEL_76;
    }
  }
  v35 = ReadFile(*(HANDLE *)(*((_QWORD *)this + 10) + 8 * a6), a4, v13, 0, &Overlapped);
  v36 = GetLastError();
  v15 = v36;
  if ( v35 || v36 == 997 )
  {
    v15 = 0;
    WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
    GetOverlappedResult(*(HANDLE *)(*((_QWORD *)this + 10) + 8 * a6), &Overlapped, &NumberOfBytesTransferred, 1);
    if ( NumberOfBytesTransferred >= (unsigned int)v13 )
      goto LABEL_76;
    v15 = 38;
    if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
      goto LABEL_76;
    v30 = &off_1409174D8;
LABEL_75:
    LODWORD(lpCompletionRoutinea) = NumberOfBytesTransferred;
    VmlDebugTraceWithError(16800, v30, 2147942438LL, (unsigned int)v13, lpCompletionRoutinea);
    goto LABEL_76;
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
  {
    if ( v15 > 0 )
      v37 = (unsigned __int16)v15 | 0x80070000;
    else
      v37 = (unsigned int)v15;
    VmlDebugTraceWithError(
      16800,
      &off_1408C0C10,
      v37,
      *(_QWORD *)(*((_QWORD *)this + 10) + 8 * a6),
      lpCompletionRoutinea);
  }
LABEL_76:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1403a2314  push    rbp
0x1403a2316  push    rbx
0x1403a2317  push    rsi
0x1403a2318  push    rdi
0x1403a2319  push    r12
0x1403a231b  push    r13
0x1403a231d  push    r14
0x1403a231f  push    r15
0x1403a2321  lea     rbp, [rsp-7]
0x1403a2326  sub     rsp, 98h
0x1403a232d  mov     rax, cs:__security_cookie
0x1403a2334  xor     rax, rsp
0x1403a2337  mov     [rbp+3Fh+var_48], rax
0x1403a233b  mov     r14, [rbp+3Fh+arg_28]
0x1403a233f  mov     ebx, 2000000h
0x1403a2344  mov     r15, [rbp+3Fh+lpOverlapped]
0x1403a2348  xorps   xmm0, xmm0
0x1403a234b  mov     [rbp+3Fh+var_80], rdx
0x1403a234f  mov     r13, rdx
0x1403a2352  mov     rdx, [rbp+3Fh+arg_38]
0x1403a2359  mov     r10, r9
0x1403a235c  mov     [rbp+3Fh+var_90], rdx
0x1403a2360  mov     rsi, rcx
0x1403a2363  mov     [rbp+3Fh+lpBuffer], r9
0x1403a2367  mov     r12d, r8d
0x1403a236a  mov     [rbp+3Fh+NumberOfBytesTransferred], 0
0x1403a2371  mov     [rbp+3Fh+var_78], rbx
0x1403a2375  movups  xmmword ptr [rbp+3Fh+Overlapped.Internal], xmm0
0x1403a2379  movups  xmmword ptr [rbp+3Fh+Overlapped.10h], xmm0
0x1403a237d  cmp     r8d, ebx
0x1403a2380  jbe     loc_1403A2440
0x1403a2386  mov     ecx, 0C1A0h
0x1403a238b  xor     dil, dil
0x1403a238e  call    VmlIsDebugTraceEnabled
0x1403a2393  test    eax, eax
0x1403a2395  jz      short loc_1403A23AB
0x1403a2397  mov     r8d, r12d
0x1403a239a  lea     rdx, off_1409173A0; "Received a large read request of size %"...
0x1403a23a1  mov     ecx, 0C1A0h
0x1403a23a6  call    VmlDebugTraceEx
0x1403a23ab  mov     r10, [rbp+3Fh+lpBuffer]
0x1403a23af  mov     rdx, [rbp+3Fh+var_90]
0x1403a23b3  mov     eax, dword ptr [rbp+3Fh+var_80+4]
0x1403a23b6  test    rdx, rdx
0x1403a23b9  jz      loc_1403A2449
0x1403a23bf  mov     [r15+10h], r13d
0x1403a23c3  mov     r9, r15; lpOverlapped
0x1403a23c6  mov     [r15+14h], eax
0x1403a23ca  mov     r8d, r12d; nNumberOfBytesToRead
0x1403a23cd  mov     rcx, [rsi+50h]
0x1403a23d1  xor     edi, edi
0x1403a23d3  mov     [rsp+0D0h+lpCompletionRoutine], rdx; lpCompletionRoutine
0x1403a23d8  mov     rdx, r10; lpBuffer
0x1403a23db  mov     rcx, [rcx+r14*8]; hFile
0x1403a23df  call    cs:__imp_ReadFileEx
0x1403a23e6  nop     dword ptr [rax+rax+00h]
0x1403a23eb  test    eax, eax
0x1403a23ed  jnz     loc_1403A290B
0x1403a23f3  call    cs:__imp_GetLastError
0x1403a23fa  nop     dword ptr [rax+rax+00h]
0x1403a23ff  mov     edi, eax
0x1403a2401  test    eax, eax
0x1403a2403  jle     short loc_1403A240E
0x1403a2405  movzx   edi, ax
0x1403a2408  or      edi, 80070000h
0x1403a240e  mov     ebx, 0C1A0h
0x1403a2413  mov     ecx, ebx
0x1403a2415  call    VmlIsDebugTraceEnabled
0x1403a241a  test    eax, eax
0x1403a241c  jz      loc_1403A290B
0x1403a2422  mov     r9, [rsi+50h]
0x1403a2426  lea     rdx, off_140917388; "Failed to read the data from file Index"...
0x1403a242d  mov     r8, r14
0x1403a2430  mov     ecx, ebx
0x1403a2432  mov     r9, [r9+r14*8]
0x1403a2436  call    VmlDebugTraceEx
0x1403a243b  jmp     loc_1403A290B
0x1403a2440  mov     dil, [rbp+3Fh+arg_20]
0x1403a2444  jmp     loc_1403A23B3
0x1403a2449  mov     dword ptr [rbp+3Fh+Overlapped.10h], r13d
0x1403a244d  mov     dword ptr [rbp+3Fh+Overlapped.10h+4], eax
0x1403a2450  mov     [rbp+3Fh+Overlapped.hEvent], 0
0x1403a2458  test    dil, dil
0x1403a245b  jz      loc_1403A2798
0x1403a2461  mov     eax, [rsi+1E0h]
0x1403a2467  cmp     rax, r14
0x1403a246a  jz      loc_1403A2501
0x1403a2470  mov     ecx, 0C1A0h
0x1403a2475  call    VmlIsDebugTraceEnabled
0x1403a247a  test    eax, eax
0x1403a247c  jz      short loc_1403A24E6
0x1403a247e  mov     rax, [rsi+98h]
0x1403a2485  mov     rcx, r14
0x1403a2488  mov     r8, [rsi+250h]
0x1403a248f  mov     r9, [rsi+50h]
0x1403a2493  shl     rcx, 0Ch
0x1403a2497  shr     r8, 14h
0x1403a249b  mov     [rsp+0D0h+var_98], r8
0x1403a24a0  mov     r8, r14
0x1403a24a3  mov     r9, [r9+r14*8]
0x1403a24a7  mov     rdx, [rcx+rax+2Ch]
0x1403a24ac  mov     rcx, [rsi+278h]
0x1403a24b3  mov     rax, [rsi+270h]
0x1403a24ba  shr     rdx, 14h
0x1403a24be  mov     [rsp+0D0h+var_A0], rdx
0x1403a24c3  lea     rdx, off_140917370; "Started reading data from new log file."...
0x1403a24ca  shr     rcx, 14h
0x1403a24ce  mov     [rsp+0D0h+var_A8], rcx
0x1403a24d3  mov     ecx, 0C1A0h
0x1403a24d8  shr     rax, 14h
0x1403a24dc  mov     [rsp+0D0h+lpCompletionRoutine], rax
0x1403a24e1  call    VmlDebugTraceEx
0x1403a24e6  lea     rcx, [rsi+0E0h]
0x1403a24ed  mov     qword ptr [rsi+0D8h], 0
0x1403a24f8  mov     qword ptr [rcx], 0
0x1403a24ff  jmp     short loc_1403A2508
0x1403a2501  lea     rcx, [rsi+0E0h]
0x1403a2508  mov     r15, [rsi+0D8h]
0x1403a250f  cmp     r13, r15
0x1403a2512  jb      short loc_1403A2524
0x1403a2514  lea     rax, [r12+r13]
0x1403a2518  mov     rdi, r12
0x1403a251b  cmp     rax, [rcx]
0x1403a251e  jbe     loc_1403A2771
0x1403a2524  cmp     qword ptr [rsi+0D0h], 0
0x1403a252c  jnz     short loc_1403A257F
0x1403a252e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1403a2535  mov     rcx, rbx; unsigned __int64
0x1403a2538  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1403a253d  mov     [rsi+0D0h], rax
0x1403a2544  test    rax, rax
0x1403a2547  jnz     short loc_1403A257F
0x1403a2549  mov     ebx, 41A0h
0x1403a254e  mov     ecx, ebx
0x1403a2550  call    VmlIsDebugTraceEnabled
0x1403a2555  test    eax, eax
0x1403a2557  jz      short loc_1403A2575
0x1403a2559  mov     r9, [rsi+50h]
0x1403a255d  lea     rdx, off_140917358; "Failed to allocate the buffer of size 0"...
0x1403a2564  mov     r8d, 2000000h
0x1403a256a  mov     ecx, ebx
0x1403a256c  mov     r9, [r9+r14*8]
0x1403a2570  call    VmlDebugTraceEx
0x1403a2575  mov     edi, 8
0x1403a257a  jmp     loc_1403A290B
0x1403a257f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1403a2583  cmp     r12d, ebx
0x1403a2586  jnb     short loc_1403A25A1
0x1403a2588  mov     r8, r13; unsigned __int64
0x1403a258b  mov     dword ptr [rsp+0D0h+lpCompletionRoutine], r12d; unsigned int
0x1403a2590  mov     rdx, r14; unsigned __int64
0x1403a2593  mov     rcx, rsi; this
0x1403a2596  call    ?GetLengthForLogFileRead@FrCtLogParser@@AEAAK_K0KK@Z; FrCtLogParser::GetLengthForLogFileRead(unsigned __int64,unsigned __int64,ulong,ulong)
0x1403a259b  mov     ebx, eax
0x1403a259d  mov     [rbp+3Fh+var_78], rbx
0x1403a25a1  cmp     dword ptr [rsi+244h], 0
0x1403a25a8  jz      short loc_1403A25D1
0x1403a25aa  mov     ecx, ebx
0x1403a25ac  lea     rax, [r12+r13]
0x1403a25b0  mov     r15, r12
0x1403a25b3  cmp     rax, rcx
0x1403a25b6  jbe     short loc_1403A25C0
0x1403a25b8  sub     r15, rcx
0x1403a25bb  add     r15, r13
0x1403a25be  jmp     short loc_1403A25C3
0x1403a25c0  xor     r15d, r15d
0x1403a25c3  mov     rax, r15
0x1403a25c6  mov     dword ptr [rbp+3Fh+Overlapped.10h], r15d
0x1403a25ca  shr     rax, 20h
0x1403a25ce  mov     dword ptr [rbp+3Fh+Overlapped.10h+4], eax
0x1403a25d1  xor     r9d, r9d; lpName
0x1403a25d4  xor     r8d, r8d; bInitialState
0x1403a25d7  xor     ecx, ecx; lpEventAttributes
0x1403a25d9  lea     edx, [r9+1]; bManualReset
0x1403a25dd  call    cs:__imp_CreateEventW
0x1403a25e4  nop     dword ptr [rax+rax+00h]
0x1403a25e9  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x1403a25ed  test    rax, rax
0x1403a25f0  jnz     short loc_1403A2651
0x1403a25f2  call    cs:__imp_GetLastError
0x1403a25f9  nop     dword ptr [rax+rax+00h]
0x1403a25fe  mov     edi, eax
0x1403a2600  movzx   eax, ax
0x1403a2603  mov     dword ptr [rbp+3Fh+var_90], eax
0x1403a2606  test    edi, edi
0x1403a2608  jg      short loc_1403A260E
0x1403a260a  mov     eax, edi
0x1403a260c  jmp     short loc_1403A2613
0x1403a260e  or      eax, 80070000h
0x1403a2613  test    eax, eax
0x1403a2615  jns     short loc_1403A2651
0x1403a2617  mov     ebx, 41A0h
0x1403a261c  mov     ecx, ebx
0x1403a261e  call    VmlIsDebugTraceEnabled
0x1403a2623  test    eax, eax
0x1403a2625  jz      loc_1403A290B
0x1403a262b  test    edi, edi
0x1403a262d  jg      short loc_1403A2633
0x1403a262f  mov     eax, edi
0x1403a2631  jmp     short loc_1403A263B
0x1403a2633  mov     eax, dword ptr [rbp+3Fh+var_90]
0x1403a2636  or      eax, 80070000h
0x1403a263b  mov     r8d, eax
0x1403a263e  lea     rdx, off_1408C0C28; "Failed to create read log file overlapp"...
0x1403a2645  mov     ecx, ebx
0x1403a2647  call    VmlDebugTraceWithError
0x1403a264c  jmp     loc_1403A290B
0x1403a2651  mov     rcx, [rsi+50h]
0x1403a2655  lea     rax, [rbp+3Fh+Overlapped]
0x1403a2659  mov     rdx, [rsi+0D0h]; lpBuffer
0x1403a2660  xor     r9d, r9d; lpNumberOfBytesRead
0x1403a2663  mov     r8d, ebx; nNumberOfBytesToRead
0x1403a2666  mov     [rsp+0D0h+lpCompletionRoutine], rax; lpOverlapped
0x1403a266b  mov     rcx, [rcx+r14*8]; hFile
0x1403a266f  call    cs:__imp_ReadFile
0x1403a2676  nop     dword ptr [rax+rax+00h]
0x1403a267b  mov     ebx, eax
0x1403a267d  call    cs:__imp_GetLastError
0x1403a2684  nop     dword ptr [rax+rax+00h]
0x1403a2689  mov     edi, eax
0x1403a268b  test    ebx, ebx
0x1403a268d  jnz     short loc_1403A26E0
0x1403a268f  cmp     eax, 3E5h
0x1403a2694  jz      short loc_1403A26E0
0x1403a2696  mov     ebx, 41A0h
0x1403a269b  mov     ecx, ebx
0x1403a269d  call    VmlIsDebugTraceEnabled
0x1403a26a2  test    eax, eax
0x1403a26a4  jz      loc_1403A290B
0x1403a26aa  mov     rax, [rsi+50h]
0x1403a26ae  mov     rcx, [rax+r14*8]
0x1403a26b2  test    edi, edi
0x1403a26b4  jg      short loc_1403A26BB
0x1403a26b6  mov     r8d, edi
0x1403a26b9  jmp     short loc_1403A26C6
0x1403a26bb  movzx   r8d, di
0x1403a26bf  or      r8d, 80070000h
0x1403a26c6  mov     r9, [rbp+3Fh+var_78]
0x1403a26ca  lea     rdx, off_1408C0C58; "Failed to read the data of size %d ,for"...
0x1403a26d1  mov     [rsp+0D0h+var_A8], r14
0x1403a26d6  mov     [rsp+0D0h+lpCompletionRoutine], rcx
0x1403a26db  jmp     loc_1403A2904
0x1403a26e0  mov     rcx, [rbp+3Fh+Overlapped.hEvent]; hHandle
0x1403a26e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1403a26e7  call    cs:__imp_WaitForSingleObject
0x1403a26ee  nop     dword ptr [rax+rax+00h]
0x1403a26f3  mov     rcx, [rsi+50h]
0x1403a26f7  lea     r8, [rbp+3Fh+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1403a26fb  mov     r9d, 1; bWait
0x1403a2701  lea     rdx, [rbp+3Fh+Overlapped]; lpOverlapped
0x1403a2705  mov     rcx, [rcx+r14*8]; hFile
0x1403a2709  call    cs:__imp_GetOverlappedResult
0x1403a2710  nop     dword ptr [rax+rax+00h]
0x1403a2715  cmp     dword ptr [rsi+244h], 0
0x1403a271c  mov     ecx, [rbp+3Fh+NumberOfBytesTransferred]
0x1403a271f  cmovz   r15, r13
0x1403a2723  mov     [rsi+1E0h], r14d
0x1403a272a  add     [rsi+270h], rcx
0x1403a2731  mov     [rsi+0D8h], r15
0x1403a2738  lea     rax, [rcx+r15]
0x1403a273c  mov     [rsi+0E0h], rax
0x1403a2743  cmp     [rbp+3Fh+NumberOfBytesTransferred], r12d
0x1403a2747  jnb     short loc_1403A276E
0x1403a2749  mov     ebx, 41A0h
0x1403a274e  mov     edi, 26h ; '&'
0x1403a2753  mov     ecx, ebx
0x1403a2755  call    VmlIsDebugTraceEnabled
0x1403a275a  test    eax, eax
0x1403a275c  jz      loc_1403A290B
0x1403a2762  lea     rdx, off_1409174F0; "Failed to read the requested bytesLengt"...
0x1403a2769  jmp     loc_1403A28E7
0x1403a276e  mov     rdi, r12
0x1403a2771  mov     rdx, [rsi+0D0h]
0x1403a2778  mov     r8, rdi; Size
0x1403a277b  mov     rcx, [rbp+3Fh+lpBuffer]; void *
0x1403a277f  sub     rdx, r15
0x1403a2782  add     rdx, r13; Src
0x1403a2785  call    memcpy_0
0x1403a278a  add     [rsi+278h], rdi
0x1403a2791  xor     edi, edi
0x1403a2793  jmp     loc_1403A290B
0x1403a2798  xor     r9d, r9d; lpName
0x1403a279b  xor     r8d, r8d; bInitialState
0x1403a279e  xor     ecx, ecx; lpEventAttributes
0x1403a27a0  lea     edx, [r9+1]; bManualReset
0x1403a27a4  call    cs:__imp_CreateEventW
0x1403a27ab  nop     dword ptr [rax+rax+00h]
0x1403a27b0  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x1403a27b4  test    rax, rax
0x1403a27b7  jnz     short loc_1403A280E
0x1403a27b9  call    cs:__imp_GetLastError
0x1403a27c0  nop     dword ptr [rax+rax+00h]
0x1403a27c5  movzx   r15d, ax
0x1403a27c9  mov     edi, eax
0x1403a27cb  test    eax, eax
0x1403a27cd  jle     short loc_1403A27D9
0x1403a27cf  mov     eax, r15d
0x1403a27d2  or      eax, 80070000h
0x1403a27d7  test    eax, eax
0x1403a27d9  jns     short loc_1403A280E
  ... truncated ...
```
