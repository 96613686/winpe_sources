# __security_init_cookie

- ea: `0x140001be4`
- end: `0x140001c9b`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400017a0`

## callees

- `0x140001be4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001c35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001c35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001c29`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001c45`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001c45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001c1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001c1b`

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
0x140001be4  mov     [rsp-8+arg_10], rbx
0x140001be9  push    rbp
0x140001bea  mov     rbp, rsp
0x140001bed  sub     rsp, 30h
0x140001bf1  mov     rax, cs:__security_cookie
0x140001bf8  mov     rbx, 2B992DDFA232h
0x140001c02  cmp     rax, rbx
0x140001c05  jnz     short loc_140001C86
0x140001c07  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001c0b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140001c13  mov     qword ptr [rbp+PerformanceCount], 0
0x140001c1b  call    cs:__imp_GetSystemTimeAsFileTime
0x140001c21  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001c25  mov     [rbp+var_10], rax
0x140001c29  call    cs:__imp_GetCurrentThreadId
0x140001c2f  mov     eax, eax
0x140001c31  xor     [rbp+var_10], rax
0x140001c35  call    cs:__imp_GetCurrentProcessId
0x140001c3b  mov     eax, eax
0x140001c3d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001c41  xor     [rbp+var_10], rax
0x140001c45  call    cs:__imp_QueryPerformanceCounter
0x140001c4b  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001c4e  lea     rcx, [rbp+var_10]
0x140001c52  shl     rax, 20h
0x140001c56  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001c5a  xor     rax, [rbp+var_10]
0x140001c5e  xor     rax, rcx
0x140001c61  mov     rcx, 0FFFFFFFFFFFFh
0x140001c6b  and     rax, rcx
0x140001c6e  mov     rcx, 2B992DDFA233h
0x140001c78  cmp     rax, rbx
0x140001c7b  cmovz   rax, rcx
0x140001c7f  mov     cs:__security_cookie, rax
0x140001c86  mov     rbx, [rsp+30h+arg_10]
0x140001c8b  not     rax
0x140001c8e  mov     cs:__security_cookie_complement, rax
0x140001c95  add     rsp, 30h
0x140001c99  pop     rbp
0x140001c9a  retn
```
