# __security_init_cookie

- ea: `0x180010acc`
- end: `0x180010b83`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010460`

## callees

- `0x180010acc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b2d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b2d`

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
0x180010acc  mov     [rsp-8+arg_10], rbx
0x180010ad1  push    rbp
0x180010ad2  mov     rbp, rsp
0x180010ad5  sub     rsp, 30h
0x180010ad9  mov     rax, cs:__security_cookie
0x180010ae0  mov     rbx, 2B992DDFA232h
0x180010aea  cmp     rax, rbx
0x180010aed  jnz     short loc_180010B6E
0x180010aef  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010af3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010afb  mov     qword ptr [rbp+PerformanceCount], 0
0x180010b03  call    cs:__imp_GetSystemTimeAsFileTime
0x180010b09  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010b0d  mov     [rbp+var_10], rax
0x180010b11  call    cs:__imp_GetCurrentThreadId
0x180010b17  mov     eax, eax
0x180010b19  xor     [rbp+var_10], rax
0x180010b1d  call    cs:__imp_GetCurrentProcessId
0x180010b23  mov     eax, eax
0x180010b25  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180010b29  xor     [rbp+var_10], rax
0x180010b2d  call    cs:__imp_QueryPerformanceCounter
0x180010b33  mov     eax, dword ptr [rbp+PerformanceCount]
0x180010b36  lea     rcx, [rbp+var_10]
0x180010b3a  shl     rax, 20h
0x180010b3e  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010b42  xor     rax, [rbp+var_10]
0x180010b46  xor     rax, rcx
0x180010b49  mov     rcx, 0FFFFFFFFFFFFh
0x180010b53  and     rax, rcx
0x180010b56  mov     rcx, 2B992DDFA233h
0x180010b60  cmp     rax, rbx
0x180010b63  cmovz   rax, rcx
0x180010b67  mov     cs:__security_cookie, rax
0x180010b6e  mov     rbx, [rsp+30h+arg_10]
0x180010b73  not     rax
0x180010b76  mov     cs:__security_cookie_complement, rax
0x180010b7d  add     rsp, 30h
0x180010b81  pop     rbp
0x180010b82  retn
```
