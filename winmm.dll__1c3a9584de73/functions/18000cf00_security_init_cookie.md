# __security_init_cookie

- ea: `0x18000cf00`
- end: `0x18000cfb5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c940`

## callees

- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cf35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cf35`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cf5f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cf5f`

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
0x18000cf00  mov     [rsp-8+arg_10], rbx
0x18000cf05  push    rbp
0x18000cf06  mov     rbp, rsp
0x18000cf09  sub     rsp, 30h
0x18000cf0d  mov     rax, cs:__security_cookie
0x18000cf14  mov     rbx, 2B992DDFA232h
0x18000cf1e  cmp     rax, rbx
0x18000cf21  jnz     short loc_18000CFA0
0x18000cf23  xor     eax, eax
0x18000cf25  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000cf29  mov     [rbp+var_10], rax
0x18000cf2d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000cf31  mov     qword ptr [rbp+PerformanceCount], rax
0x18000cf35  call    cs:__imp_GetSystemTimeAsFileTime
0x18000cf3b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000cf3f  mov     [rbp+var_10], rax
0x18000cf43  call    cs:__imp_GetCurrentThreadId
0x18000cf49  mov     eax, eax
0x18000cf4b  xor     [rbp+var_10], rax
0x18000cf4f  call    cs:__imp_GetCurrentProcessId
0x18000cf55  mov     eax, eax
0x18000cf57  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000cf5b  xor     [rbp+var_10], rax
0x18000cf5f  call    cs:__imp_QueryPerformanceCounter
0x18000cf65  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000cf68  lea     rcx, [rbp+var_10]
0x18000cf6c  shl     rax, 20h
0x18000cf70  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000cf74  xor     rax, [rbp+var_10]
0x18000cf78  xor     rax, rcx
0x18000cf7b  mov     rcx, 0FFFFFFFFFFFFh
0x18000cf85  and     rax, rcx
0x18000cf88  mov     rcx, 2B992DDFA233h
0x18000cf92  cmp     rax, rbx
0x18000cf95  cmovz   rax, rcx
0x18000cf99  mov     cs:__security_cookie, rax
0x18000cfa0  mov     rbx, [rsp+30h+arg_10]
0x18000cfa5  not     rax
0x18000cfa8  mov     cs:__security_cookie_complement, rax
0x18000cfaf  add     rsp, 30h
0x18000cfb3  pop     rbp
0x18000cfb4  retn
```
