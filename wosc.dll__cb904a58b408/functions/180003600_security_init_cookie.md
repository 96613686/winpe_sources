# __security_init_cookie

- ea: `0x180003600`
- end: `0x1800036b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800030c0`

## callees

- `0x180003600`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000365f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000365f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000364f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000364f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003643`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003635`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003635`

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
0x180003600  mov     [rsp-8+arg_10], rbx
0x180003605  push    rbp
0x180003606  mov     rbp, rsp
0x180003609  sub     rsp, 30h
0x18000360d  mov     rax, cs:__security_cookie
0x180003614  mov     rbx, 2B992DDFA232h
0x18000361e  cmp     rax, rbx
0x180003621  jnz     short loc_1800036A0
0x180003623  xor     eax, eax
0x180003625  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003629  mov     [rbp+var_10], rax
0x18000362d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003631  mov     qword ptr [rbp+PerformanceCount], rax
0x180003635  call    cs:__imp_GetSystemTimeAsFileTime
0x18000363b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000363f  mov     [rbp+var_10], rax
0x180003643  call    cs:__imp_GetCurrentThreadId
0x180003649  mov     eax, eax
0x18000364b  xor     [rbp+var_10], rax
0x18000364f  call    cs:__imp_GetCurrentProcessId
0x180003655  mov     eax, eax
0x180003657  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000365b  xor     [rbp+var_10], rax
0x18000365f  call    cs:__imp_QueryPerformanceCounter
0x180003665  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003668  lea     rcx, [rbp+var_10]
0x18000366c  shl     rax, 20h
0x180003670  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003674  xor     rax, [rbp+var_10]
0x180003678  xor     rax, rcx
0x18000367b  mov     rcx, 0FFFFFFFFFFFFh
0x180003685  and     rax, rcx
0x180003688  mov     rcx, 2B992DDFA233h
0x180003692  cmp     rax, rbx
0x180003695  cmovz   rax, rcx
0x180003699  mov     cs:__security_cookie, rax
0x1800036a0  mov     rbx, [rsp+30h+arg_10]
0x1800036a5  not     rax
0x1800036a8  mov     cs:__security_cookie_complement, rax
0x1800036af  add     rsp, 30h
0x1800036b3  pop     rbp
0x1800036b4  retn
```
