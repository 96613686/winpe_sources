# __security_init_cookie

- ea: `0x1800348ec`
- end: `0x1800349a1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800344c0`

## callees

- `0x1800348ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003493b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003493b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003492f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003492f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034921`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034921`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003494b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003494b`

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
0x1800348ec  mov     [rsp-8+arg_10], rbx
0x1800348f1  push    rbp
0x1800348f2  mov     rbp, rsp
0x1800348f5  sub     rsp, 30h
0x1800348f9  mov     rax, cs:__security_cookie
0x180034900  mov     rbx, 2B992DDFA232h
0x18003490a  cmp     rax, rbx
0x18003490d  jnz     short loc_18003498C
0x18003490f  xor     eax, eax
0x180034911  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034915  mov     [rbp+var_10], rax
0x180034919  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003491d  mov     qword ptr [rbp+PerformanceCount], rax
0x180034921  call    cs:__imp_GetSystemTimeAsFileTime
0x180034927  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003492b  mov     [rbp+var_10], rax
0x18003492f  call    cs:__imp_GetCurrentThreadId
0x180034935  mov     eax, eax
0x180034937  xor     [rbp+var_10], rax
0x18003493b  call    cs:__imp_GetCurrentProcessId
0x180034941  mov     eax, eax
0x180034943  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180034947  xor     [rbp+var_10], rax
0x18003494b  call    cs:__imp_QueryPerformanceCounter
0x180034951  mov     eax, dword ptr [rbp+PerformanceCount]
0x180034954  lea     rcx, [rbp+var_10]
0x180034958  shl     rax, 20h
0x18003495c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180034960  xor     rax, [rbp+var_10]
0x180034964  xor     rax, rcx
0x180034967  mov     rcx, 0FFFFFFFFFFFFh
0x180034971  and     rax, rcx
0x180034974  mov     rcx, 2B992DDFA233h
0x18003497e  cmp     rax, rbx
0x180034981  cmovz   rax, rcx
0x180034985  mov     cs:__security_cookie, rax
0x18003498c  mov     rbx, [rsp+30h+arg_10]
0x180034991  not     rax
0x180034994  mov     cs:__security_cookie_complement, rax
0x18003499b  add     rsp, 30h
0x18003499f  pop     rbp
0x1800349a0  retn
```
