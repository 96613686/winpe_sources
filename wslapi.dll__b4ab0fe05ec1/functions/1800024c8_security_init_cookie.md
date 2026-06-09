# __security_init_cookie

- ea: `0x1800024c8`
- end: `0x18000257d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x1800024c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000250b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000250b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002527`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002527`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800024c8  mov     [rsp-8+arg_10], rbx
0x1800024cd  push    rbp
0x1800024ce  mov     rbp, rsp
0x1800024d1  sub     rsp, 30h
0x1800024d5  mov     rax, cs:__security_cookie
0x1800024dc  mov     rbx, 2B992DDFA232h
0x1800024e6  cmp     rax, rbx
0x1800024e9  jnz     short loc_180002568
0x1800024eb  xor     eax, eax
0x1800024ed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024f1  mov     [rbp+var_10], rax
0x1800024f5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024f9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002503  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002507  mov     [rbp+var_10], rax
0x18000250b  call    cs:__imp_GetCurrentThreadId
0x180002511  mov     eax, eax
0x180002513  xor     [rbp+var_10], rax
0x180002517  call    cs:__imp_GetCurrentProcessId
0x18000251d  mov     eax, eax
0x18000251f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002523  xor     [rbp+var_10], rax
0x180002527  call    cs:__imp_QueryPerformanceCounter
0x18000252d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002530  lea     rcx, [rbp+var_10]
0x180002534  shl     rax, 20h
0x180002538  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000253c  xor     rax, [rbp+var_10]
0x180002540  xor     rax, rcx
0x180002543  mov     rcx, 0FFFFFFFFFFFFh
0x18000254d  and     rax, rcx
0x180002550  mov     rcx, 2B992DDFA233h
0x18000255a  cmp     rax, rbx
0x18000255d  cmovz   rax, rcx
0x180002561  mov     cs:__security_cookie, rax
0x180002568  mov     rbx, [rsp+30h+arg_10]
0x18000256d  not     rax
0x180002570  mov     cs:__security_cookie_complement, rax
0x180002577  add     rsp, 30h
0x18000257b  pop     rbp
0x18000257c  retn
```
