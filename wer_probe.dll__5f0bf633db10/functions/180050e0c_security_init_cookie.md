# __security_init_cookie

- ea: `0x180050e0c`
- end: `0x180050ec1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050d60`

## callees

- `0x180050e0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050e5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050e6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050e6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050e41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050e41`

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
0x180050e0c  mov     [rsp-8+arg_10], rbx
0x180050e11  push    rbp
0x180050e12  mov     rbp, rsp
0x180050e15  sub     rsp, 30h
0x180050e19  mov     rax, cs:__security_cookie
0x180050e20  mov     rbx, 2B992DDFA232h
0x180050e2a  cmp     rax, rbx
0x180050e2d  jnz     short loc_180050EAC
0x180050e2f  xor     eax, eax
0x180050e31  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180050e35  mov     [rbp+var_10], rax
0x180050e39  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180050e3d  mov     qword ptr [rbp+PerformanceCount], rax
0x180050e41  call    cs:__imp_GetSystemTimeAsFileTime
0x180050e47  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180050e4b  mov     [rbp+var_10], rax
0x180050e4f  call    cs:__imp_GetCurrentThreadId
0x180050e55  mov     eax, eax
0x180050e57  xor     [rbp+var_10], rax
0x180050e5b  call    cs:__imp_GetCurrentProcessId
0x180050e61  mov     eax, eax
0x180050e63  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180050e67  xor     [rbp+var_10], rax
0x180050e6b  call    cs:__imp_QueryPerformanceCounter
0x180050e71  mov     eax, dword ptr [rbp+PerformanceCount]
0x180050e74  lea     rcx, [rbp+var_10]
0x180050e78  shl     rax, 20h
0x180050e7c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180050e80  xor     rax, [rbp+var_10]
0x180050e84  xor     rax, rcx
0x180050e87  mov     rcx, 0FFFFFFFFFFFFh
0x180050e91  and     rax, rcx
0x180050e94  mov     rcx, 2B992DDFA233h
0x180050e9e  cmp     rax, rbx
0x180050ea1  cmovz   rax, rcx
0x180050ea5  mov     cs:__security_cookie, rax
0x180050eac  mov     rbx, [rsp+30h+arg_10]
0x180050eb1  not     rax
0x180050eb4  mov     cs:__security_cookie_complement, rax
0x180050ebb  add     rsp, 30h
0x180050ebf  pop     rbp
0x180050ec0  retn
```
