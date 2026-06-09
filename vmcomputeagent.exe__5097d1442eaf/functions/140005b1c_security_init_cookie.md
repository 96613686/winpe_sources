# __security_init_cookie

- ea: `0x140005b1c`
- end: `0x140005bd1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005330`

## callees

- `0x140005b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005b51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005b7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005b7b`

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
0x140005b1c  mov     [rsp-8+arg_10], rbx
0x140005b21  push    rbp
0x140005b22  mov     rbp, rsp
0x140005b25  sub     rsp, 30h
0x140005b29  mov     rax, cs:__security_cookie
0x140005b30  mov     rbx, 2B992DDFA232h
0x140005b3a  cmp     rax, rbx
0x140005b3d  jnz     short loc_140005BBC
0x140005b3f  xor     eax, eax
0x140005b41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140005b45  mov     [rbp+var_10], rax
0x140005b49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140005b4d  mov     qword ptr [rbp+PerformanceCount], rax
0x140005b51  call    cs:__imp_GetSystemTimeAsFileTime
0x140005b57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140005b5b  mov     [rbp+var_10], rax
0x140005b5f  call    cs:__imp_GetCurrentThreadId
0x140005b65  mov     eax, eax
0x140005b67  xor     [rbp+var_10], rax
0x140005b6b  call    cs:__imp_GetCurrentProcessId
0x140005b71  mov     eax, eax
0x140005b73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140005b77  xor     [rbp+var_10], rax
0x140005b7b  call    cs:__imp_QueryPerformanceCounter
0x140005b81  mov     eax, dword ptr [rbp+PerformanceCount]
0x140005b84  lea     rcx, [rbp+var_10]
0x140005b88  shl     rax, 20h
0x140005b8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140005b90  xor     rax, [rbp+var_10]
0x140005b94  xor     rax, rcx
0x140005b97  mov     rcx, 0FFFFFFFFFFFFh
0x140005ba1  and     rax, rcx
0x140005ba4  mov     rcx, 2B992DDFA233h
0x140005bae  cmp     rax, rbx
0x140005bb1  cmovz   rax, rcx
0x140005bb5  mov     cs:__security_cookie, rax
0x140005bbc  mov     rbx, [rsp+30h+arg_10]
0x140005bc1  not     rax
0x140005bc4  mov     cs:__security_cookie_complement, rax
0x140005bcb  add     rsp, 30h
0x140005bcf  pop     rbp
0x140005bd0  retn
```
