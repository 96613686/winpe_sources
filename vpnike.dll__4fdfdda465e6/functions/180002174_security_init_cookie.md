# __security_init_cookie

- ea: `0x180002174`
- end: `0x180002251`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018a0`

## callees

- `0x180002174`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800021bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800021bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800021d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800021e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800021d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800021e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021fe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180002174  mov     [rsp-8+arg_18], rbx
0x180002179  push    rbp
0x18000217a  mov     rbp, rsp
0x18000217d  sub     rsp, 20h
0x180002181  xor     eax, eax
0x180002183  mov     rbx, 2B992DDFA232h
0x18000218d  mov     [rbp+arg_0], rax
0x180002191  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002195  mov     qword ptr [rbp+PerformanceCount], rax
0x180002199  mov     rax, cs:__security_cookie
0x1800021a0  cmp     rax, rbx
0x1800021a3  jnz     loc_18000223C
0x1800021a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800021ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800021b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800021b7  mov     [rbp+arg_0], rax
0x1800021bb  call    cs:__imp_GetCurrentProcessId
0x1800021c1  mov     eax, eax
0x1800021c3  xor     [rbp+arg_0], rax
0x1800021c7  call    cs:__imp_GetCurrentThreadId
0x1800021cd  mov     eax, eax
0x1800021cf  xor     [rbp+arg_0], rax
0x1800021d3  call    cs:__imp_GetTickCount
0x1800021d9  mov     eax, eax
0x1800021db  shl     rax, 18h
0x1800021df  xor     [rbp+arg_0], rax
0x1800021e3  call    cs:__imp_GetTickCount
0x1800021e9  mov     eax, eax
0x1800021eb  lea     rcx, [rbp+arg_0]
0x1800021ef  xor     rax, [rbp+arg_0]
0x1800021f3  xor     rax, rcx
0x1800021f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800021fa  mov     [rbp+arg_0], rax
0x1800021fe  call    cs:__imp_QueryPerformanceCounter
0x180002204  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002207  mov     rcx, 0FFFFFFFFFFFFh
0x180002211  shl     rax, 20h
0x180002215  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002219  xor     rax, [rbp+arg_0]
0x18000221d  and     rax, rcx
0x180002220  mov     rcx, rax
0x180002223  cmp     rax, rbx
0x180002226  jnz     short loc_180002235
0x180002228  mov     rax, 2B992DDFA233h
0x180002232  mov     rcx, rax
0x180002235  mov     cs:__security_cookie, rcx
0x18000223c  mov     rbx, [rsp+20h+arg_18]
0x180002241  not     rax
0x180002244  mov     cs:__security_cookie_complement, rax
0x18000224b  add     rsp, 20h
0x18000224f  pop     rbp
0x180002250  retn
```
