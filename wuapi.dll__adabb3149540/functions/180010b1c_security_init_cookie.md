# __security_init_cookie

- ea: `0x180010b1c`
- end: `0x180010bd3`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x180010b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b53`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b7d`

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
0x180010b1c  mov     [rsp-8+arg_10], rbx
0x180010b21  push    rbp
0x180010b22  mov     rbp, rsp
0x180010b25  sub     rsp, 30h
0x180010b29  mov     rax, cs:__security_cookie
0x180010b30  mov     rbx, 2B992DDFA232h
0x180010b3a  cmp     rax, rbx
0x180010b3d  jnz     short loc_180010BBE
0x180010b3f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010b43  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010b4b  mov     qword ptr [rbp+PerformanceCount], 0
0x180010b53  call    cs:__imp_GetSystemTimeAsFileTime
0x180010b59  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010b5d  mov     [rbp+var_10], rax
0x180010b61  call    cs:__imp_GetCurrentThreadId
0x180010b67  mov     eax, eax
0x180010b69  xor     [rbp+var_10], rax
0x180010b6d  call    cs:__imp_GetCurrentProcessId
0x180010b73  mov     eax, eax
0x180010b75  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180010b79  xor     [rbp+var_10], rax
0x180010b7d  call    cs:__imp_QueryPerformanceCounter
0x180010b83  mov     eax, dword ptr [rbp+PerformanceCount]
0x180010b86  lea     rcx, [rbp+var_10]
0x180010b8a  shl     rax, 20h
0x180010b8e  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010b92  xor     rax, [rbp+var_10]
0x180010b96  xor     rax, rcx
0x180010b99  mov     rcx, 0FFFFFFFFFFFFh
0x180010ba3  and     rax, rcx
0x180010ba6  mov     rcx, 2B992DDFA233h
0x180010bb0  cmp     rax, rbx
0x180010bb3  cmovz   rax, rcx
0x180010bb7  mov     cs:__security_cookie, rax
0x180010bbe  mov     rbx, [rsp+30h+arg_10]
0x180010bc3  not     rax
0x180010bc6  mov     cs:__security_cookie_complement, rax
0x180010bcd  add     rsp, 30h
0x180010bd1  pop     rbp
0x180010bd2  retn
```
