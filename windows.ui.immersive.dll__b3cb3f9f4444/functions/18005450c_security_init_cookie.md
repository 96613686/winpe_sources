# __security_init_cookie

- ea: `0x18005450c`
- end: `0x1800545c1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800540e0`

## callees

- `0x18005450c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005455b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005455b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005454f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005454f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005456b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005456b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054541`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180054541`

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
0x18005450c  mov     [rsp-8+arg_10], rbx
0x180054511  push    rbp
0x180054512  mov     rbp, rsp
0x180054515  sub     rsp, 30h
0x180054519  mov     rax, cs:__security_cookie
0x180054520  mov     rbx, 2B992DDFA232h
0x18005452a  cmp     rax, rbx
0x18005452d  jnz     short loc_1800545AC
0x18005452f  xor     eax, eax
0x180054531  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180054535  mov     [rbp+var_10], rax
0x180054539  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005453d  mov     qword ptr [rbp+PerformanceCount], rax
0x180054541  call    cs:__imp_GetSystemTimeAsFileTime
0x180054547  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005454b  mov     [rbp+var_10], rax
0x18005454f  call    cs:__imp_GetCurrentThreadId
0x180054555  mov     eax, eax
0x180054557  xor     [rbp+var_10], rax
0x18005455b  call    cs:__imp_GetCurrentProcessId
0x180054561  mov     eax, eax
0x180054563  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180054567  xor     [rbp+var_10], rax
0x18005456b  call    cs:__imp_QueryPerformanceCounter
0x180054571  mov     eax, dword ptr [rbp+PerformanceCount]
0x180054574  lea     rcx, [rbp+var_10]
0x180054578  shl     rax, 20h
0x18005457c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180054580  xor     rax, [rbp+var_10]
0x180054584  xor     rax, rcx
0x180054587  mov     rcx, 0FFFFFFFFFFFFh
0x180054591  and     rax, rcx
0x180054594  mov     rcx, 2B992DDFA233h
0x18005459e  cmp     rax, rbx
0x1800545a1  cmovz   rax, rcx
0x1800545a5  mov     cs:__security_cookie, rax
0x1800545ac  mov     rbx, [rsp+30h+arg_10]
0x1800545b1  not     rax
0x1800545b4  mov     cs:__security_cookie_complement, rax
0x1800545bb  add     rsp, 30h
0x1800545bf  pop     rbp
0x1800545c0  retn
```
