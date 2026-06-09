# __security_init_cookie

- ea: `0x1800018a4`
- end: `0x180001981`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001550`

## callees

- `0x1800018a4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000192e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000192e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001903`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001913`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001903`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001913`

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
0x1800018a4  mov     [rsp-8+arg_18], rbx
0x1800018a9  push    rbp
0x1800018aa  mov     rbp, rsp
0x1800018ad  sub     rsp, 20h
0x1800018b1  xor     eax, eax
0x1800018b3  mov     rbx, 2B992DDFA232h
0x1800018bd  mov     [rbp+arg_0], rax
0x1800018c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800018c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800018c9  mov     rax, cs:__security_cookie
0x1800018d0  cmp     rax, rbx
0x1800018d3  jnz     loc_18000196C
0x1800018d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800018e7  mov     [rbp+arg_0], rax
0x1800018eb  call    cs:__imp_GetCurrentProcessId
0x1800018f1  mov     eax, eax
0x1800018f3  xor     [rbp+arg_0], rax
0x1800018f7  call    cs:__imp_GetCurrentThreadId
0x1800018fd  mov     eax, eax
0x1800018ff  xor     [rbp+arg_0], rax
0x180001903  call    cs:__imp_GetTickCount
0x180001909  mov     eax, eax
0x18000190b  shl     rax, 18h
0x18000190f  xor     [rbp+arg_0], rax
0x180001913  call    cs:__imp_GetTickCount
0x180001919  mov     eax, eax
0x18000191b  lea     rcx, [rbp+arg_0]
0x18000191f  xor     rax, [rbp+arg_0]
0x180001923  xor     rax, rcx
0x180001926  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000192a  mov     [rbp+arg_0], rax
0x18000192e  call    cs:__imp_QueryPerformanceCounter
0x180001934  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001937  mov     rcx, 0FFFFFFFFFFFFh
0x180001941  shl     rax, 20h
0x180001945  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001949  xor     rax, [rbp+arg_0]
0x18000194d  and     rax, rcx
0x180001950  mov     rcx, rax
0x180001953  cmp     rax, rbx
0x180001956  jnz     short loc_180001965
0x180001958  mov     rax, 2B992DDFA233h
0x180001962  mov     rcx, rax
0x180001965  mov     cs:__security_cookie, rcx
0x18000196c  mov     rbx, [rsp+20h+arg_18]
0x180001971  not     rax
0x180001974  mov     cs:__security_cookie_complement, rax
0x18000197b  add     rsp, 20h
0x18000197f  pop     rbp
0x180001980  retn
```
