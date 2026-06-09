# __security_init_cookie

- ea: `0x18001fc10`
- end: `0x18001fcc5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fb80`

## callees

- `0x18001fc10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001fc45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001fc45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fc5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fc5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc53`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc6f`

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
0x18001fc10  mov     [rsp-8+arg_10], rbx
0x18001fc15  push    rbp
0x18001fc16  mov     rbp, rsp
0x18001fc19  sub     rsp, 30h
0x18001fc1d  mov     rax, cs:__security_cookie
0x18001fc24  mov     rbx, 2B992DDFA232h
0x18001fc2e  cmp     rax, rbx
0x18001fc31  jnz     short loc_18001FCB0
0x18001fc33  xor     eax, eax
0x18001fc35  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001fc39  mov     [rbp+var_10], rax
0x18001fc3d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001fc41  mov     qword ptr [rbp+PerformanceCount], rax
0x18001fc45  call    cs:__imp_GetSystemTimeAsFileTime
0x18001fc4b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001fc4f  mov     [rbp+var_10], rax
0x18001fc53  call    cs:__imp_GetCurrentThreadId
0x18001fc59  mov     eax, eax
0x18001fc5b  xor     [rbp+var_10], rax
0x18001fc5f  call    cs:__imp_GetCurrentProcessId
0x18001fc65  mov     eax, eax
0x18001fc67  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001fc6b  xor     [rbp+var_10], rax
0x18001fc6f  call    cs:__imp_QueryPerformanceCounter
0x18001fc75  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001fc78  lea     rcx, [rbp+var_10]
0x18001fc7c  shl     rax, 20h
0x18001fc80  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001fc84  xor     rax, [rbp+var_10]
0x18001fc88  xor     rax, rcx
0x18001fc8b  mov     rcx, 0FFFFFFFFFFFFh
0x18001fc95  and     rax, rcx
0x18001fc98  mov     rcx, 2B992DDFA233h
0x18001fca2  cmp     rax, rbx
0x18001fca5  cmovz   rax, rcx
0x18001fca9  mov     cs:__security_cookie, rax
0x18001fcb0  mov     rbx, [rsp+30h+arg_10]
0x18001fcb5  not     rax
0x18001fcb8  mov     cs:__security_cookie_complement, rax
0x18001fcbf  add     rsp, 30h
0x18001fcc3  pop     rbp
0x18001fcc4  retn
```
