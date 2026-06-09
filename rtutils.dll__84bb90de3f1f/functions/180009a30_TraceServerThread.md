# TraceServerThread

- ea: `0x180009a30`
- end: `0x180009cae`
- name: `TraceServerThread`
- size: `638`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001fa0`
- `0x180002d90`
- `0x180002e90`
- `0x180004456`
- `0x180009694`
- `0x180009810`
- `0x180009838`
- `0x180009a30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009aa9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009aa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009b01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c71`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180009c08`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180009c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180009ca7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180009ca7`

## pseudocode

```c
void __fastcall __noreturn TraceServerThread(volatile __int32 *Parameter)
{
  HANDLE ProcessHeap; // rax
  LPVOID v3; // rax
  HANDLE v4; // rax
  LPVOID v5; // rax
  char *v6; // rbp
  char *v7; // r15
  char *v8; // rbx
  __int64 v9; // rdx
  _QWORD **v10; // r13
  int v11; // r12d
  unsigned int v12; // r14d
  char *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  void *v19; // rcx
  void *v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdx
  _QWORD v24[96]; // [rsp+30h] [rbp-358h] BYREF

  memset_0(v24, 0, 0x200u);
  _InterlockedExchange(Parameter + 14, *((_DWORD *)Parameter + 14) | 0x10);
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x1388u);
  if ( v3 )
    _InterlockedExchange64((volatile __int64 *)&g_FormatBuffer, (__int64)v3);
  v4 = GetProcessHeap();
  v5 = HeapAlloc(v4, 0, 0x1388u);
  if ( v5 )
    _InterlockedExchange64((volatile __int64 *)&g_PrintBuffer, (__int64)v5);
  v6 = (char *)(Parameter + 88);
  v7 = (char *)(Parameter + 208);
  AcquireWriteLock((__int64)Parameter);
  v8 = (char *)(Parameter + 88);
  if ( Parameter + 88 < Parameter + 208 )
  {
    do
    {
      v9 = *(_QWORD *)v8;
      if ( *(_QWORD *)v8 && (*(_BYTE *)(v9 + 56) & 1) == 0 )
        TraceEnableClientA(Parameter, v9, 0);
      v8 += 8;
    }
    while ( v8 < v7 );
  }
  *((_DWORD *)Parameter + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)Parameter);
  v10 = (_QWORD **)(Parameter + 24);
  while ( 1 )
  {
    AcquireReadLock(Parameter);
    if ( (unsigned __int64)(*((_QWORD *)Parameter + 9) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v11 = 1;
      v24[0] = 0;
    }
    else
    {
      v11 = 0;
      v24[0] = *((_QWORD *)Parameter + 9);
    }
    v12 = 3;
    v24[1] = *((_QWORD *)Parameter + 10);
    v13 = (char *)(Parameter + 88);
    v24[2] = *((_QWORD *)Parameter + 11);
    if ( v6 < v7 )
    {
      do
      {
        v14 = *(_QWORD *)v13;
        if ( *(_QWORD *)v13 && (*(_BYTE *)(v14 + 56) & 8) != 0 )
        {
          v15 = v12++;
          *((_DWORD *)&v24[64] + v15) = (v13 - v6) >> 3;
          v24[v15] = *(_QWORD *)(v14 + 1080);
        }
        v13 += 8;
      }
      while ( v13 < v7 );
    }
    v16 = *v10;
    while ( v16 != v10 )
    {
      v17 = (_QWORD *)*v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16 || (v18 = (_QWORD *)v16[1], (_QWORD *)*v18 != v16) )
        __fastfail(3u);
      v19 = (void *)v16[2];
      v20 = v16;
      *v18 = v17;
      v16 = v17;
      v17[1] = v18;
      CloseHandle(v19);
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
    }
    ReleaseReadLock(Parameter);
    v22 = WaitForMultipleObjectsEx(v12 - v11, (const HANDLE *)&v24[v11], 0, 0xFFFFFFFF, 0) + v11;
    if ( !(_DWORD)v22 )
      break;
    if ( (_DWORD)v22 == 1 )
    {
      TraceCleanUpServer((HGLOBAL)Parameter);
      FreeLibraryAndExitThread(g_moduleRef, 0);
    }
    if ( (unsigned int)v22 >= 3 && (unsigned int)v22 <= v12 )
    {
      _mm_lfence();
      AcquireWriteLock((__int64)Parameter);
      v23 = *(_QWORD *)&Parameter[2 * *((unsigned int *)&v24[64] + v22) + 88];
      if ( v23 && (*(_BYTE *)(v23 + 56) & 1) == 0 )
        TraceEnableClientA(Parameter, v23, 0);
LABEL_31:
      *((_DWORD *)Parameter + 10) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)Parameter);
    }
  }
  AcquireWriteLock((__int64)Parameter);
  if ( (unsigned __int64)(*((_QWORD *)Parameter + 9) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    TraceProcessConsoleInput(Parameter);
  goto LABEL_31;
}

```

## disassembly

```asm
0x180009a30  push    rbx
0x180009a32  push    rbp
0x180009a33  push    rsi
0x180009a34  push    rdi
0x180009a35  push    r12
0x180009a37  push    r13
0x180009a39  push    r14
0x180009a3b  push    r15
0x180009a3d  sub     rsp, 348h
0x180009a44  mov     rax, cs:__security_cookie
0x180009a4b  xor     rax, rsp
0x180009a4e  mov     [rsp+388h+var_58], rax
0x180009a56  mov     rdi, rcx
0x180009a59  xor     edx, edx; Val
0x180009a5b  lea     rcx, [rsp+388h+var_358]; void *
0x180009a60  mov     r8d, 200h; Size
0x180009a66  call    memset_0
0x180009a6b  mov     eax, [rdi+38h]
0x180009a6e  or      eax, 10h
0x180009a71  xchg    eax, [rdi+38h]
0x180009a74  call    cs:__imp_GetProcessHeap
0x180009a7a  mov     ebx, 1388h
0x180009a7f  xor     edx, edx; dwFlags
0x180009a81  mov     rcx, rax; hHeap
0x180009a84  mov     r8d, ebx; dwBytes
0x180009a87  call    cs:__imp_HeapAlloc
0x180009a8d  xor     esi, esi
0x180009a8f  test    rax, rax
0x180009a92  jz      short loc_180009A9B
0x180009a94  xchg    rax, cs:g_FormatBuffer
0x180009a9b  call    cs:__imp_GetProcessHeap
0x180009aa1  mov     r8, rbx; dwBytes
0x180009aa4  xor     edx, edx; dwFlags
0x180009aa6  mov     rcx, rax; hHeap
0x180009aa9  call    cs:__imp_HeapAlloc
0x180009aaf  test    rax, rax
0x180009ab2  jz      short loc_180009ABB
0x180009ab4  xchg    rax, cs:g_PrintBuffer
0x180009abb  mov     rcx, rdi
0x180009abe  lea     rbp, [rdi+160h]
0x180009ac5  lea     r15, [rdi+340h]
0x180009acc  call    AcquireWriteLock
0x180009ad1  mov     rbx, rbp
0x180009ad4  cmp     rbp, r15
0x180009ad7  jnb     short loc_180009AFB
0x180009ad9  mov     rdx, [rbx]
0x180009adc  test    rdx, rdx
0x180009adf  jz      short loc_180009AF2
0x180009ae1  test    byte ptr [rdx+38h], 1
0x180009ae5  jnz     short loc_180009AF2
0x180009ae7  xor     r8d, r8d
0x180009aea  mov     rcx, rdi
0x180009aed  call    TraceEnableClientA
0x180009af2  add     rbx, 8
0x180009af6  cmp     rbx, r15
0x180009af9  jb      short loc_180009AD9
0x180009afb  mov     rcx, rdi; lpCriticalSection
0x180009afe  mov     [rdi+28h], esi
0x180009b01  call    cs:__imp_LeaveCriticalSection
0x180009b07  lea     r13, [rdi+60h]
0x180009b0b  mov     rcx, rdi
0x180009b0e  call    AcquireReadLock
0x180009b13  mov     rcx, [rdi+48h]
0x180009b17  lea     rax, [rcx-1]
0x180009b1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009b1f  ja      short loc_180009B2B
0x180009b21  mov     r12d, esi
0x180009b24  mov     [rsp+388h+var_358], rcx
0x180009b29  jmp     short loc_180009B36
0x180009b2b  mov     r12d, 1
0x180009b31  mov     [rsp+388h+var_358], rsi
0x180009b36  mov     rax, [rdi+50h]
0x180009b3a  mov     r14d, 3
0x180009b40  mov     [rsp+388h+var_350], rax
0x180009b45  mov     rdx, rbp
0x180009b48  mov     rax, [rdi+58h]
0x180009b4c  mov     [rsp+388h+var_348], rax
0x180009b51  cmp     rbp, r15
0x180009b54  jnb     short loc_180009B91
0x180009b56  mov     r8, [rdx]
0x180009b59  test    r8, r8
0x180009b5c  jz      short loc_180009B88
0x180009b5e  test    byte ptr [r8+38h], 8
0x180009b63  jz      short loc_180009B88
0x180009b65  mov     ecx, r14d
0x180009b68  mov     rax, rdx
0x180009b6b  sub     rax, rbp
0x180009b6e  sar     rax, 3
0x180009b72  inc     r14d
0x180009b75  mov     [rsp+rcx*4+388h+var_158], eax
0x180009b7c  mov     rax, [r8+438h]
0x180009b83  mov     [rsp+rcx*8+388h+var_358], rax
0x180009b88  add     rdx, 8
0x180009b8c  cmp     rdx, r15
0x180009b8f  jb      short loc_180009B56
0x180009b91  mov     rsi, [r13+0]
0x180009b95  jmp     short loc_180009BDC
0x180009b97  mov     rax, [rsi]
0x180009b9a  cmp     [rax+8], rsi
0x180009b9e  jnz     loc_180009C8F
0x180009ba4  mov     rdx, [rsi+8]
0x180009ba8  cmp     [rdx], rsi
0x180009bab  jnz     loc_180009C8F
0x180009bb1  mov     rcx, [rsi+10h]; hObject
0x180009bb5  mov     rbx, rsi
0x180009bb8  mov     [rdx], rax
0x180009bbb  mov     rsi, rax
0x180009bbe  mov     [rax+8], rdx
0x180009bc2  call    cs:__imp_CloseHandle
0x180009bc8  call    cs:__imp_GetProcessHeap
0x180009bce  mov     r8, rbx; lpMem
0x180009bd1  xor     edx, edx; dwFlags
0x180009bd3  mov     rcx, rax; hHeap
0x180009bd6  call    cs:__imp_HeapFree
0x180009bdc  cmp     rsi, r13
0x180009bdf  jnz     short loc_180009B97
0x180009be1  mov     rcx, rdi
0x180009be4  call    ReleaseReadLock
0x180009be9  mov     eax, r12d
0x180009bec  lea     rdx, [rsp+388h+var_358]
0x180009bf1  mov     ecx, r14d
0x180009bf4  xor     esi, esi
0x180009bf6  sub     ecx, r12d; nCount
0x180009bf9  mov     [rsp+388h+bAlertable], esi; bAlertable
0x180009bfd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180009c01  xor     r8d, r8d; bWaitAll
0x180009c04  lea     rdx, [rdx+rax*8]; lpHandles
0x180009c08  call    cs:__imp_WaitForMultipleObjectsEx
0x180009c0e  lea     ebx, [rax+r12]
0x180009c12  test    ebx, ebx
0x180009c14  jnz     short loc_180009C35
0x180009c16  mov     rcx, rdi
0x180009c19  call    AcquireWriteLock
0x180009c1e  mov     rax, [rdi+48h]
0x180009c22  dec     rax
0x180009c25  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009c29  ja      short loc_180009C6B
0x180009c2b  mov     rcx, rdi
0x180009c2e  call    TraceProcessConsoleInput
0x180009c33  jmp     short loc_180009C6B
0x180009c35  cmp     ebx, 1
0x180009c38  jz      short loc_180009C96
0x180009c3a  cmp     ebx, 3
0x180009c3d  jb      loc_180009B0B
0x180009c43  cmp     ebx, r14d
0x180009c46  ja      loc_180009B0B
0x180009c4c  lfence
0x180009c4f  mov     rcx, rdi
0x180009c52  call    AcquireWriteLock
0x180009c57  mov     ecx, [rsp+rbx*4+388h+var_158]
0x180009c5e  mov     rdx, [rdi+rcx*8+160h]
0x180009c66  test    rdx, rdx
0x180009c69  jnz     short loc_180009C7C
0x180009c6b  mov     rcx, rdi; lpCriticalSection
0x180009c6e  mov     [rdi+28h], esi
0x180009c71  call    cs:__imp_LeaveCriticalSection
0x180009c77  jmp     loc_180009B0B
0x180009c7c  test    byte ptr [rdx+38h], 1
0x180009c80  jnz     short loc_180009C6B
0x180009c82  xor     r8d, r8d
0x180009c85  mov     rcx, rdi
0x180009c88  call    TraceEnableClientA
0x180009c8d  jmp     short loc_180009C6B
0x180009c8f  mov     ecx, 3
0x180009c94  int     29h; Win8: RtlFailFast(ecx)
0x180009c96  mov     rcx, rdi; hMem
0x180009c99  call    TraceCleanUpServer
0x180009c9e  mov     rcx, cs:g_moduleRef; hLibModule
0x180009ca5  xor     edx, edx; dwExitCode
0x180009ca7  call    cs:__imp_FreeLibraryAndExitThread
```
