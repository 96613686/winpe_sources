# __security_init_cookie

- ea: `0x180066d3c`
- end: `0x180066df1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800668c0`

## callees

- `0x180066d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180066d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180066d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066d7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066d7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180066d9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180066d9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180066d71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180066d71`

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
0x180066d3c  mov     [rsp-8+arg_10], rbx
0x180066d41  push    rbp
0x180066d42  mov     rbp, rsp
0x180066d45  sub     rsp, 30h
0x180066d49  mov     rax, cs:__security_cookie
0x180066d50  mov     rbx, 2B992DDFA232h
0x180066d5a  cmp     rax, rbx
0x180066d5d  jnz     short loc_180066DDC
0x180066d5f  xor     eax, eax
0x180066d61  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180066d65  mov     [rbp+var_10], rax
0x180066d69  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180066d6d  mov     qword ptr [rbp+PerformanceCount], rax
0x180066d71  call    cs:__imp_GetSystemTimeAsFileTime
0x180066d77  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180066d7b  mov     [rbp+var_10], rax
0x180066d7f  call    cs:__imp_GetCurrentThreadId
0x180066d85  mov     eax, eax
0x180066d87  xor     [rbp+var_10], rax
0x180066d8b  call    cs:__imp_GetCurrentProcessId
0x180066d91  mov     eax, eax
0x180066d93  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180066d97  xor     [rbp+var_10], rax
0x180066d9b  call    cs:__imp_QueryPerformanceCounter
0x180066da1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180066da4  lea     rcx, [rbp+var_10]
0x180066da8  shl     rax, 20h
0x180066dac  xor     rax, qword ptr [rbp+PerformanceCount]
0x180066db0  xor     rax, [rbp+var_10]
0x180066db4  xor     rax, rcx
0x180066db7  mov     rcx, 0FFFFFFFFFFFFh
0x180066dc1  and     rax, rcx
0x180066dc4  mov     rcx, 2B992DDFA233h
0x180066dce  cmp     rax, rbx
0x180066dd1  cmovz   rax, rcx
0x180066dd5  mov     cs:__security_cookie, rax
0x180066ddc  mov     rbx, [rsp+30h+arg_10]
0x180066de1  not     rax
0x180066de4  mov     cs:__security_cookie_complement, rax
0x180066deb  add     rsp, 30h
0x180066def  pop     rbp
0x180066df0  retn
```
