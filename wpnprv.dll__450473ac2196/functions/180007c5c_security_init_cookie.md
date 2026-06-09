# __security_init_cookie

- ea: `0x180007c5c`
- end: `0x180007d11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800073f0`

## callees

- `0x180007c5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007cab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007cab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007cbb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007cbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007c91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007c91`

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
0x180007c5c  mov     [rsp-8+arg_10], rbx
0x180007c61  push    rbp
0x180007c62  mov     rbp, rsp
0x180007c65  sub     rsp, 30h
0x180007c69  mov     rax, cs:__security_cookie
0x180007c70  mov     rbx, 2B992DDFA232h
0x180007c7a  cmp     rax, rbx
0x180007c7d  jnz     short loc_180007CFC
0x180007c7f  xor     eax, eax
0x180007c81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007c85  mov     [rbp+var_10], rax
0x180007c89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007c8d  mov     qword ptr [rbp+PerformanceCount], rax
0x180007c91  call    cs:__imp_GetSystemTimeAsFileTime
0x180007c97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180007c9b  mov     [rbp+var_10], rax
0x180007c9f  call    cs:__imp_GetCurrentThreadId
0x180007ca5  mov     eax, eax
0x180007ca7  xor     [rbp+var_10], rax
0x180007cab  call    cs:__imp_GetCurrentProcessId
0x180007cb1  mov     eax, eax
0x180007cb3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180007cb7  xor     [rbp+var_10], rax
0x180007cbb  call    cs:__imp_QueryPerformanceCounter
0x180007cc1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180007cc4  lea     rcx, [rbp+var_10]
0x180007cc8  shl     rax, 20h
0x180007ccc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180007cd0  xor     rax, [rbp+var_10]
0x180007cd4  xor     rax, rcx
0x180007cd7  mov     rcx, 0FFFFFFFFFFFFh
0x180007ce1  and     rax, rcx
0x180007ce4  mov     rcx, 2B992DDFA233h
0x180007cee  cmp     rax, rbx
0x180007cf1  cmovz   rax, rcx
0x180007cf5  mov     cs:__security_cookie, rax
0x180007cfc  mov     rbx, [rsp+30h+arg_10]
0x180007d01  not     rax
0x180007d04  mov     cs:__security_cookie_complement, rax
0x180007d0b  add     rsp, 30h
0x180007d0f  pop     rbp
0x180007d10  retn
```
