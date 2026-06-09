# __security_init_cookie

- ea: `0x1400024c0`
- end: `0x140002575`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400020f0`

## callees

- `0x1400024c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000250f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000250f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002503`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000251f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000251f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400024f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400024f5`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1400024c0  mov     [rsp-8+arg_10], rbx
0x1400024c5  push    rbp
0x1400024c6  mov     rbp, rsp
0x1400024c9  sub     rsp, 30h
0x1400024cd  mov     rax, cs:__security_cookie
0x1400024d4  mov     rbx, 2B992DDFA232h
0x1400024de  cmp     rax, rbx
0x1400024e1  jnz     short loc_140002560
0x1400024e3  xor     eax, eax
0x1400024e5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400024e9  mov     [rbp+var_10], rax
0x1400024ed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400024f1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400024f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400024fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400024ff  mov     [rbp+var_10], rax
0x140002503  call    cs:__imp_GetCurrentThreadId
0x140002509  mov     eax, eax
0x14000250b  xor     [rbp+var_10], rax
0x14000250f  call    cs:__imp_GetCurrentProcessId
0x140002515  mov     eax, eax
0x140002517  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000251b  xor     [rbp+var_10], rax
0x14000251f  call    cs:__imp_QueryPerformanceCounter
0x140002525  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002528  lea     rcx, [rbp+var_10]
0x14000252c  shl     rax, 20h
0x140002530  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002534  xor     rax, [rbp+var_10]
0x140002538  xor     rax, rcx
0x14000253b  mov     rcx, 0FFFFFFFFFFFFh
0x140002545  and     rax, rcx
0x140002548  mov     rcx, 2B992DDFA233h
0x140002552  cmp     rax, rbx
0x140002555  cmovz   rax, rcx
0x140002559  mov     cs:__security_cookie, rax
0x140002560  mov     rbx, [rsp+30h+arg_10]
0x140002565  not     rax
0x140002568  mov     cs:__security_cookie_complement, rax
0x14000256f  add     rsp, 30h
0x140002573  pop     rbp
0x140002574  retn
```
