# __security_init_cookie

- ea: `0x18009b5a0`
- end: `0x18009b655`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009ae90`

## callees

- `0x18009b5a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009b5d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009b5d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009b5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009b5e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009b5ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009b5ff`

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
0x18009b5a0  mov     [rsp-8+arg_10], rbx
0x18009b5a5  push    rbp
0x18009b5a6  mov     rbp, rsp
0x18009b5a9  sub     rsp, 30h
0x18009b5ad  mov     rax, cs:__security_cookie
0x18009b5b4  mov     rbx, 2B992DDFA232h
0x18009b5be  cmp     rax, rbx
0x18009b5c1  jnz     short loc_18009B640
0x18009b5c3  xor     eax, eax
0x18009b5c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009b5c9  mov     [rbp+var_10], rax
0x18009b5cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18009b5d1  mov     qword ptr [rbp+PerformanceCount], rax
0x18009b5d5  call    cs:__imp_GetSystemTimeAsFileTime
0x18009b5db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18009b5df  mov     [rbp+var_10], rax
0x18009b5e3  call    cs:__imp_GetCurrentThreadId
0x18009b5e9  mov     eax, eax
0x18009b5eb  xor     [rbp+var_10], rax
0x18009b5ef  call    cs:__imp_GetCurrentProcessId
0x18009b5f5  mov     eax, eax
0x18009b5f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18009b5fb  xor     [rbp+var_10], rax
0x18009b5ff  call    cs:__imp_QueryPerformanceCounter
0x18009b605  mov     eax, dword ptr [rbp+PerformanceCount]
0x18009b608  lea     rcx, [rbp+var_10]
0x18009b60c  shl     rax, 20h
0x18009b610  xor     rax, qword ptr [rbp+PerformanceCount]
0x18009b614  xor     rax, [rbp+var_10]
0x18009b618  xor     rax, rcx
0x18009b61b  mov     rcx, 0FFFFFFFFFFFFh
0x18009b625  and     rax, rcx
0x18009b628  mov     rcx, 2B992DDFA233h
0x18009b632  cmp     rax, rbx
0x18009b635  cmovz   rax, rcx
0x18009b639  mov     cs:__security_cookie, rax
0x18009b640  mov     rbx, [rsp+30h+arg_10]
0x18009b645  not     rax
0x18009b648  mov     cs:__security_cookie_complement, rax
0x18009b64f  add     rsp, 30h
0x18009b653  pop     rbp
0x18009b654  retn
```
