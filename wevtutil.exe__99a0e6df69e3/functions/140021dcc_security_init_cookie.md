# __security_init_cookie

- ea: `0x140021dcc`
- end: `0x140021e81`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021ad0`

## callees

- `0x140021dcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140021e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140021e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021e0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140021e2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140021e2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140021e01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140021e01`

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
0x140021dcc  mov     [rsp-8+arg_10], rbx
0x140021dd1  push    rbp
0x140021dd2  mov     rbp, rsp
0x140021dd5  sub     rsp, 30h
0x140021dd9  mov     rax, cs:__security_cookie
0x140021de0  mov     rbx, 2B992DDFA232h
0x140021dea  cmp     rax, rbx
0x140021ded  jnz     short loc_140021E6C
0x140021def  xor     eax, eax
0x140021df1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140021df5  mov     [rbp+var_10], rax
0x140021df9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140021dfd  mov     qword ptr [rbp+PerformanceCount], rax
0x140021e01  call    cs:__imp_GetSystemTimeAsFileTime
0x140021e07  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140021e0b  mov     [rbp+var_10], rax
0x140021e0f  call    cs:__imp_GetCurrentThreadId
0x140021e15  mov     eax, eax
0x140021e17  xor     [rbp+var_10], rax
0x140021e1b  call    cs:__imp_GetCurrentProcessId
0x140021e21  mov     eax, eax
0x140021e23  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140021e27  xor     [rbp+var_10], rax
0x140021e2b  call    cs:__imp_QueryPerformanceCounter
0x140021e31  mov     eax, dword ptr [rbp+PerformanceCount]
0x140021e34  lea     rcx, [rbp+var_10]
0x140021e38  shl     rax, 20h
0x140021e3c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140021e40  xor     rax, [rbp+var_10]
0x140021e44  xor     rax, rcx
0x140021e47  mov     rcx, 0FFFFFFFFFFFFh
0x140021e51  and     rax, rcx
0x140021e54  mov     rcx, 2B992DDFA233h
0x140021e5e  cmp     rax, rbx
0x140021e61  cmovz   rax, rcx
0x140021e65  mov     cs:__security_cookie, rax
0x140021e6c  mov     rbx, [rsp+30h+arg_10]
0x140021e71  not     rax
0x140021e74  mov     cs:__security_cookie_complement, rax
0x140021e7b  add     rsp, 30h
0x140021e7f  pop     rbp
0x140021e80  retn
```
