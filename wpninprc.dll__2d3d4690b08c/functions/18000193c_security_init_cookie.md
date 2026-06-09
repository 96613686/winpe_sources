# __security_init_cookie

- ea: `0x18000193c`
- end: `0x1800019f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x18000193c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000198b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000198b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000197f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000197f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000199b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000199b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001971`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001971`

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
0x18000193c  mov     [rsp-8+arg_10], rbx
0x180001941  push    rbp
0x180001942  mov     rbp, rsp
0x180001945  sub     rsp, 30h
0x180001949  mov     rax, cs:__security_cookie
0x180001950  mov     rbx, 2B992DDFA232h
0x18000195a  cmp     rax, rbx
0x18000195d  jnz     short loc_1800019DC
0x18000195f  xor     eax, eax
0x180001961  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001965  mov     [rbp+var_10], rax
0x180001969  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000196d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001971  call    cs:__imp_GetSystemTimeAsFileTime
0x180001977  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000197b  mov     [rbp+var_10], rax
0x18000197f  call    cs:__imp_GetCurrentThreadId
0x180001985  mov     eax, eax
0x180001987  xor     [rbp+var_10], rax
0x18000198b  call    cs:__imp_GetCurrentProcessId
0x180001991  mov     eax, eax
0x180001993  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001997  xor     [rbp+var_10], rax
0x18000199b  call    cs:__imp_QueryPerformanceCounter
0x1800019a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019a4  lea     rcx, [rbp+var_10]
0x1800019a8  shl     rax, 20h
0x1800019ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019b0  xor     rax, [rbp+var_10]
0x1800019b4  xor     rax, rcx
0x1800019b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800019c1  and     rax, rcx
0x1800019c4  mov     rcx, 2B992DDFA233h
0x1800019ce  cmp     rax, rbx
0x1800019d1  cmovz   rax, rcx
0x1800019d5  mov     cs:__security_cookie, rax
0x1800019dc  mov     rbx, [rsp+30h+arg_10]
0x1800019e1  not     rax
0x1800019e4  mov     cs:__security_cookie_complement, rax
0x1800019eb  add     rsp, 30h
0x1800019ef  pop     rbp
0x1800019f0  retn
```
