# WaitForNextJobTermination

- ea: `0x180002b40`
- end: `0x180002d7a`
- name: `WaitForNextJobTermination`
- size: `570`
- prototype: `ULONG __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002b40`
- `0x180002f70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002cc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ce6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cf9`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180002b81`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180002b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d41`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c84`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c84`
- `USERENV!UnloadUserProfile` at `0x180002d32`
- `USERENV!UnloadUserProfile` at `0x180002d32`

## pseudocode

```c
ULONG __fastcall WaitForNextJobTermination(PVOID Parameter)
{
  unsigned __int64 v1; // rbx
  void *v2; // rcx
  void *v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  int v8; // ebx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  DWORD NumberOfBytesTransferred; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp+18h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+68h] [rbp+20h] BYREF

  NumberOfBytesTransferred = 0;
  Overlapped = 0;
  CompletionKey = 0;
  while ( GetQueuedCompletionStatus(g_hIOCP, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
  {
    if ( NumberOfBytesTransferred == 4 )
    {
      v1 = CompletionKey;
      EnterCriticalSection(&csForProcessCount);
      if ( *(_QWORD *)v1 )
      {
        CloseHandle(*(HANDLE *)v1);
        *(_QWORD *)v1 = 0;
      }
      v2 = *(void **)(v1 + 8);
      if ( v2 )
      {
        CloseHandle(v2);
        *(_QWORD *)(v1 + 8) = 0;
      }
      v3 = *(void **)(v1 + 24);
      if ( v3 )
      {
        UnloadUserProfile(*(HANDLE *)(v1 + 16), v3);
        *(_QWORD *)(v1 + 24) = 0;
      }
      v4 = *(void **)(v1 + 16);
      if ( v4 )
      {
        CloseHandle(v4);
        *(_QWORD *)(v1 + 16) = 0;
      }
      v5 = *(void **)(v1 + 40);
      if ( v5 )
      {
        Free_SECONDARYLOGONINFOW(v5);
        *(_QWORD *)(v1 + 40) = 0;
      }
      v6 = *(_QWORD *)(v1 + 48);
      if ( *(_QWORD *)(v6 + 8) != v1 + 48 || (v7 = *(_QWORD **)(v1 + 56), *v7 != v1 + 48) )
        __fastfail(3u);
      *v7 = v6;
      *(_QWORD *)(v6 + 8) = v7;
      if ( *(_DWORD *)(v1 + 64) )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)v1);
      }
      if ( (__int128 *)xmmword_1800096E0 == &xmmword_1800096E0 )
      {
        v8 = 1;
      }
      else
      {
        v8 = 0;
        v9 = 1;
        if ( g_fCleanupThreadActive )
          goto LABEL_21;
      }
      v9 = 0;
LABEL_21:
      g_fCleanupThreadActive = v9;
      EnterCriticalSection(&csForProcessCount);
      g_state.dwServiceType = 32;
      g_state.dwCurrentState = 4;
      g_state.dwControlsAccepted = ((_QWORD)xmmword_1800096E0 == (_QWORD)&xmmword_1800096E0) + 130;
      g_state.dwWin32ExitCode = 0;
      *(_QWORD *)&g_state.dwCheckPoint = 0;
      if ( !SetServiceStatus(hServiceStatus, &g_state) )
        GetLastError();
      LeaveCriticalSection(&csForProcessCount);
      LeaveCriticalSection(&csForProcessCount);
      if ( v8 )
        return 0;
    }
  }
  EnterCriticalSection(&csForProcessCount);
  g_fCleanupThreadActive = 0;
  LeaveCriticalSection(&csForProcessCount);
  return GetLastError();
}

```

## disassembly

```asm
0x180002b40  push    rsi
0x180002b42  push    rdi
0x180002b43  sub     rsp, 38h
0x180002b47  xor     edi, edi
0x180002b49  mov     [rsp+48h+var_18], rbx
0x180002b4e  mov     [rsp+48h+NumberOfBytesTransferred], edi
0x180002b52  lea     rsi, xmmword_1800096E0
0x180002b59  mov     [rsp+48h+Overlapped], rdi
0x180002b5e  mov     [rsp+48h+CompletionKey], rdi
0x180002b63  mov     rcx, cs:g_hIOCP; CompletionPort
0x180002b6a  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x180002b6f  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x180002b74  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180002b7c  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180002b81  call    cs:__imp_GetQueuedCompletionStatus
0x180002b87  test    eax, eax
0x180002b89  jz      loc_180002CDF
0x180002b8f  cmp     [rsp+48h+NumberOfBytesTransferred], 4
0x180002b94  jnz     short loc_180002B63
0x180002b96  mov     rbx, [rsp+48h+CompletionKey]
0x180002b9b  lea     rcx, csForProcessCount; lpCriticalSection
0x180002ba2  call    cs:__imp_EnterCriticalSection
0x180002ba8  mov     rcx, [rbx]; hObject
0x180002bab  test    rcx, rcx
0x180002bae  jnz     loc_180002D11
0x180002bb4  mov     rcx, [rbx+8]; hObject
0x180002bb8  test    rcx, rcx
0x180002bbb  jnz     loc_180002D1F
0x180002bc1  mov     rdx, [rbx+18h]; hProfile
0x180002bc5  test    rdx, rdx
0x180002bc8  jnz     loc_180002D2E
0x180002bce  mov     rcx, [rbx+10h]; hObject
0x180002bd2  test    rcx, rcx
0x180002bd5  jnz     loc_180002D41
0x180002bdb  mov     rcx, [rbx+28h]; lpMem
0x180002bdf  test    rcx, rcx
0x180002be2  jnz     loc_180002CD1
0x180002be8  mov     rcx, [rbx+30h]
0x180002bec  lea     rax, [rbx+30h]
0x180002bf0  cmp     [rcx+8], rax
0x180002bf4  jnz     loc_180002D73
0x180002bfa  mov     rdx, [rbx+38h]
0x180002bfe  cmp     [rdx], rax
0x180002c01  jnz     loc_180002D73
0x180002c07  mov     [rdx], rcx
0x180002c0a  mov     [rcx+8], rdx
0x180002c0e  cmp     [rbx+40h], edi
0x180002c11  jnz     loc_180002CB8
0x180002c17  cmp     qword ptr cs:xmmword_1800096E0, rsi
0x180002c1e  jnz     loc_180002D50
0x180002c24  mov     ebx, 1
0x180002c29  mov     eax, edi
0x180002c2b  lea     rcx, csForProcessCount; lpCriticalSection
0x180002c32  mov     cs:g_fCleanupThreadActive, eax
0x180002c38  call    cs:__imp_EnterCriticalSection
0x180002c3e  cmp     qword ptr cs:xmmword_1800096E0, rsi
0x180002c45  lea     rdx, g_state; lpServiceStatus
0x180002c4c  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180002c53  mov     eax, edi
0x180002c55  setz    al
0x180002c58  mov     cs:g_state.dwServiceType, 20h ; ' '
0x180002c62  add     eax, 82h
0x180002c67  mov     cs:g_state.dwCurrentState, 4
0x180002c71  mov     cs:g_state.dwControlsAccepted, eax
0x180002c77  mov     cs:g_state.dwWin32ExitCode, edi
0x180002c7d  mov     qword ptr cs:g_state.dwCheckPoint, rdi
0x180002c84  call    cs:__imp_SetServiceStatus
0x180002c8a  test    eax, eax
0x180002c8c  jz      loc_180002D68
0x180002c92  lea     rcx, csForProcessCount; lpCriticalSection
0x180002c99  call    cs:__imp_LeaveCriticalSection
0x180002c9f  lea     rcx, csForProcessCount; lpCriticalSection
0x180002ca6  call    cs:__imp_LeaveCriticalSection
0x180002cac  test    ebx, ebx
0x180002cae  jz      loc_180002B63
0x180002cb4  mov     eax, edi
0x180002cb6  jmp     short loc_180002D05
0x180002cb8  call    cs:__imp_GetProcessHeap
0x180002cbe  mov     r8, rbx; lpMem
0x180002cc1  xor     edx, edx; dwFlags
0x180002cc3  mov     rcx, rax; hHeap
0x180002cc6  call    cs:__imp_HeapFree
0x180002ccc  jmp     loc_180002C17
0x180002cd1  call    Free_SECONDARYLOGONINFOW
0x180002cd6  mov     [rbx+28h], rdi
0x180002cda  jmp     loc_180002BE8
0x180002cdf  lea     rcx, csForProcessCount; lpCriticalSection
0x180002ce6  call    cs:__imp_EnterCriticalSection
0x180002cec  lea     rcx, csForProcessCount; lpCriticalSection
0x180002cf3  mov     cs:g_fCleanupThreadActive, edi
0x180002cf9  call    cs:__imp_LeaveCriticalSection
0x180002cff  call    cs:__imp_GetLastError
0x180002d05  mov     rbx, [rsp+48h+var_18]
0x180002d0a  add     rsp, 38h
0x180002d0e  pop     rdi
0x180002d0f  pop     rsi
0x180002d10  retn
0x180002d11  call    cs:__imp_CloseHandle
0x180002d17  mov     [rbx], rdi
0x180002d1a  jmp     loc_180002BB4
0x180002d1f  call    cs:__imp_CloseHandle
0x180002d25  mov     [rbx+8], rdi
0x180002d29  jmp     loc_180002BC1
0x180002d2e  mov     rcx, [rbx+10h]; hToken
0x180002d32  call    cs:__imp_UnloadUserProfile
0x180002d38  mov     [rbx+18h], rdi
0x180002d3c  jmp     loc_180002BCE
0x180002d41  call    cs:__imp_CloseHandle
0x180002d47  mov     [rbx+10h], rdi
0x180002d4b  jmp     loc_180002BDB
0x180002d50  cmp     cs:g_fCleanupThreadActive, edi
0x180002d56  mov     ebx, edi
0x180002d58  mov     eax, 1
0x180002d5d  jnz     loc_180002C2B
0x180002d63  jmp     loc_180002C29
0x180002d68  call    cs:__imp_GetLastError
0x180002d6e  jmp     loc_180002C92
0x180002d73  mov     ecx, 3
0x180002d78  int     29h; Win8: RtlFailFast(ecx)
```
