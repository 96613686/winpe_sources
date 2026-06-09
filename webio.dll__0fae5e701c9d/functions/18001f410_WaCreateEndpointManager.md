# WaCreateEndpointManager

- ea: `0x18001f410`
- end: `0x18001f5e5`
- name: `WaCreateEndpointManager`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e5b8`
- `0x1800223bc`

## callees

- `0x180013820`
- `0x18001f410`
- `0x18002e460`
- `0x1800391c0`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001f472`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001f472`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f4ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f4ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f562`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f562`

## pseudocode

```c
__int64 __fastcall WaCreateEndpointManager(__int64 a1, __int64 a2, __int64 a3, __int64 a4, struct _FILETIME *a5)
{
  void *Heap; // rax
  struct _FILETIME v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  DWORD v13; // ebp
  __int64 v14; // rsi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _FILETIME *p_pftDueTime; // rdx
  unsigned int LastError; // edi
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF

  Heap = (void *)WxAllocateHeapEx(a1, 16480);
  v8 = (struct _FILETIME)Heap;
  if ( !Heap )
    return 8;
  memset_0(Heap, 0, 0x4060u);
  InitializeSRWLock((PSRWLOCK)(*(_QWORD *)&v8 + 80LL));
  v9 = 0;
  *(_DWORD *)(*(_QWORD *)&v8 + 28LL) = 1;
  *(_DWORD *)v8.dwLowDateTime = 1380404549;
  *(_DWORD *)(*(_QWORD *)&v8 + 36LL) = 1023;
  *(_DWORD *)(*(_QWORD *)&v8 + 32LL) = 1024;
  *(_DWORD *)(*(_QWORD *)&v8 + 40LL) = 110000;
  *(_DWORD *)(*(_QWORD *)&v8 + 88LL) = 10000;
  *(_BYTE *)(*(_QWORD *)&v8 + 24LL) = 1;
  do
  {
    v10 = 16LL * (unsigned int)v9;
    v11 = v10 + *(_QWORD *)&v8 + 96LL;
    *(_QWORD *)(v10 + *(_QWORD *)&v8 + 104) = v11;
    v12 = 2 * (v9 + 6);
    v9 = (unsigned int)(v9 + 1);
    *(_QWORD *)(*(_QWORD *)&v8 + 8 * v12) = v11;
  }
  while ( (unsigned int)v9 < *(_DWORD *)(*(_QWORD *)&v8 + 32LL) );
  v13 = *(_DWORD *)(*(_QWORD *)&v8 + 88LL);
  v14 = *(unsigned int *)(*(_QWORD *)&v8 + 40LL);
  *(_BYTE *)(*(_QWORD *)&v8 + 44LL) = 1;
  *(_BYTE *)(*(_QWORD *)&v8 + 92LL) = 1;
  *(_OWORD *)(*(_QWORD *)&v8 + 48LL) = 0;
  *(_OWORD *)(*(_QWORD *)&v8 + 64LL) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(WapTimerCallback, (PVOID)(*(_QWORD *)&v8 + 48LL), &WaTimerEnvironment);
  *(_QWORD *)(*(_QWORD *)&v8 + 56LL) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *(struct _FILETIME *)(*(_QWORD *)&v8 + 72LL) = v8;
    *(_QWORD *)(*(_QWORD *)&v8 + 64LL) = WapIdleEpCollectorWorker;
    *(_DWORD *)(*(_QWORD *)&v8 + 48LL) = 1380796756;
    pftDueTime = 0;
    if ( (_DWORD)v14 )
    {
      p_pftDueTime = &pftDueTime;
      pftDueTime = (struct _FILETIME)(-10000 * v14);
    }
    else
    {
      p_pftDueTime = 0;
      LODWORD(v14) = 0;
      v13 = 0;
    }
    SetThreadpoolTimer(ThreadpoolTimer, p_pftDueTime, v14, v13);
    LastError = 0;
    goto LABEL_10;
  }
  LastError = WaGetLastError();
  if ( !LastError )
  {
LABEL_10:
    *(_QWORD *)(*(_QWORD *)&v8 + 8LL) = a1;
    if ( a1 )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    *(_QWORD *)(*(_QWORD *)&v8 + 16LL) = a2;
    *a5 = v8;
    return LastError;
  }
  *(_BYTE *)(*(_QWORD *)&v8 + 44LL) = 0;
  pftDueTime = v8;
  WxFreeHeapEx(&pftDueTime);
  return LastError;
}

```

## disassembly

```asm
0x18001f410  push    rbx
0x18001f412  push    r12
0x18001f414  push    r14
0x18001f416  push    r15
0x18001f418  sub     rsp, 38h
0x18001f41c  mov     rax, cs:__security_cookie
0x18001f423  xor     rax, rsp
0x18001f426  mov     [rsp+58h+var_30], rax
0x18001f42b  mov     r12, [rsp+58h+arg_20]
0x18001f433  mov     r15, rdx
0x18001f436  mov     edx, 4060h
0x18001f43b  mov     r14, rcx
0x18001f43e  call    WxAllocateHeapEx
0x18001f443  mov     rbx, rax
0x18001f446  test    rax, rax
0x18001f449  jz      loc_18001F572
0x18001f44f  mov     [rsp+58h+arg_8], rbp
0x18001f454  xor     edx, edx; Val
0x18001f456  mov     [rsp+58h+arg_10], rsi
0x18001f45b  mov     r8d, 4060h; Size
0x18001f461  mov     rcx, rax; void *
0x18001f464  mov     [rsp+58h+var_28], rdi
0x18001f469  call    memset_0
0x18001f46e  lea     rcx, [rbx+50h]; SRWLock
0x18001f472  call    cs:__imp_InitializeSRWLock
0x18001f479  nop     dword ptr [rax+rax+00h]
0x18001f47e  xor     eax, eax
0x18001f480  mov     dword ptr [rbx+1Ch], 1
0x18001f487  mov     dword ptr [rbx], 52474D45h
0x18001f48d  mov     dword ptr [rbx+24h], 3FFh
0x18001f494  mov     dword ptr [rbx+20h], 400h
0x18001f49b  mov     dword ptr [rbx+28h], 1ADB0h
0x18001f4a2  mov     dword ptr [rbx+58h], 2710h
0x18001f4a9  mov     byte ptr [rbx+18h], 1
0x18001f4ad  nop     dword ptr [rax]
0x18001f4b0  mov     ecx, eax
0x18001f4b2  lea     rdx, [rbx+60h]
0x18001f4b6  shl     rcx, 4
0x18001f4ba  add     rdx, rcx
0x18001f4bd  mov     [rcx+rbx+68h], rdx
0x18001f4c2  lea     rcx, [rax+6]
0x18001f4c6  add     rcx, rcx
0x18001f4c9  inc     eax
0x18001f4cb  mov     [rbx+rcx*8], rdx
0x18001f4cf  cmp     eax, [rbx+20h]
0x18001f4d2  jb      short loc_18001F4B0
0x18001f4d4  mov     ebp, [rbx+58h]
0x18001f4d7  lea     r8, WaTimerEnvironment; pcbe
0x18001f4de  mov     esi, [rbx+28h]
0x18001f4e1  lea     rdx, [rbx+30h]; pv
0x18001f4e5  xorps   xmm0, xmm0
0x18001f4e8  mov     byte ptr [rbx+2Ch], 1
0x18001f4ec  mov     byte ptr [rbx+5Ch], 1
0x18001f4f0  lea     rcx, WapTimerCallback; pfnti
0x18001f4f7  movups  xmmword ptr [rbx+30h], xmm0
0x18001f4fb  movups  xmmword ptr [rbx+40h], xmm0
0x18001f4ff  call    cs:__imp_CreateThreadpoolTimer
0x18001f506  nop     dword ptr [rax+rax+00h]
0x18001f50b  mov     [rbx+38h], rax
0x18001f50f  mov     r10, rax
0x18001f512  test    rax, rax
0x18001f515  jz      short loc_18001F579
0x18001f517  mov     [rbx+48h], rbx
0x18001f51b  lea     rax, WapIdleEpCollectorWorker
0x18001f522  mov     [rbx+40h], rax
0x18001f526  mov     dword ptr [rbx+30h], 524D4954h
0x18001f52d  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x18001f536  test    esi, esi
0x18001f538  jz      loc_18001F5DA
0x18001f53e  imul    rax, rsi, 0FFFFFFFFFFFFD8F0h
0x18001f545  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001f54a  mov     rcx, rax
0x18001f54d  mov     [rsp+58h+pftDueTime.dwLowDateTime], eax
0x18001f551  shr     rcx, 20h
0x18001f555  mov     [rsp+58h+pftDueTime.dwHighDateTime], ecx
0x18001f559  mov     r9d, ebp; msWindowLength
0x18001f55c  mov     r8d, esi; msPeriod
0x18001f55f  mov     rcx, r10; pti
0x18001f562  call    cs:__imp_SetThreadpoolTimer
0x18001f569  nop     dword ptr [rax+rax+00h]
0x18001f56e  xor     edi, edi
0x18001f570  jmp     short loc_18001F584
0x18001f572  mov     eax, 8
0x18001f577  jmp     short loc_18001F5AB
0x18001f579  call    WaGetLastError
0x18001f57e  mov     edi, eax
0x18001f580  test    eax, eax
0x18001f582  jnz     short loc_18001F5C5
0x18001f584  mov     [rbx+8], r14
0x18001f588  test    r14, r14
0x18001f58b  jz      short loc_18001F592
0x18001f58d  lock inc dword ptr [r14+4]
0x18001f592  mov     [rbx+10h], r15
0x18001f596  mov     [r12], rbx
0x18001f59a  mov     rsi, [rsp+58h+arg_10]
0x18001f59f  mov     eax, edi
0x18001f5a1  mov     rdi, [rsp+58h+var_28]
0x18001f5a6  mov     rbp, [rsp+58h+arg_8]
0x18001f5ab  mov     rcx, [rsp+58h+var_30]
0x18001f5b0  xor     rcx, rsp; StackCookie
0x18001f5b3  call    __security_check_cookie
0x18001f5b8  add     rsp, 38h
0x18001f5bc  pop     r15
0x18001f5be  pop     r14
0x18001f5c0  pop     r12
0x18001f5c2  pop     rbx
0x18001f5c3  retn
0x18001f5c5  lea     rcx, [rsp+58h+pftDueTime]
0x18001f5ca  mov     byte ptr [rbx+2Ch], 0
0x18001f5ce  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rbx
0x18001f5d3  call    WxFreeHeapEx
0x18001f5d8  jmp     short loc_18001F59A
0x18001f5da  xor     edx, edx
0x18001f5dc  xor     esi, esi
0x18001f5de  xor     ebp, ebp
0x18001f5e0  jmp     loc_18001F559
```
