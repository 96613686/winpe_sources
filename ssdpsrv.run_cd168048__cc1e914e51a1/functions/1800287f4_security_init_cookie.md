# __security_init_cookie

- ea: `0x1800287f4`
- end: `0x1800288a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028780`

## callees

- `0x1800287f4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180028853`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180028853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028843`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028829`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028829`

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
0x1800287f4  mov     [rsp-8+arg_10], rbx
0x1800287f9  push    rbp
0x1800287fa  mov     rbp, rsp
0x1800287fd  sub     rsp, 30h
0x180028801  mov     rax, cs:__security_cookie
0x180028808  mov     rbx, 2B992DDFA232h
0x180028812  cmp     rax, rbx
0x180028815  jnz     short loc_180028894
0x180028817  xor     eax, eax
0x180028819  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002881d  mov     [rbp+var_10], rax
0x180028821  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180028825  mov     qword ptr [rbp+PerformanceCount], rax
0x180028829  call    cs:__imp_GetSystemTimeAsFileTime
0x18002882f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180028833  mov     [rbp+var_10], rax
0x180028837  call    cs:__imp_GetCurrentThreadId
0x18002883d  mov     eax, eax
0x18002883f  xor     [rbp+var_10], rax
0x180028843  call    cs:__imp_GetCurrentProcessId
0x180028849  mov     eax, eax
0x18002884b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002884f  xor     [rbp+var_10], rax
0x180028853  call    cs:__imp_QueryPerformanceCounter
0x180028859  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002885c  lea     rcx, [rbp+var_10]
0x180028860  shl     rax, 20h
0x180028864  xor     rax, qword ptr [rbp+PerformanceCount]
0x180028868  xor     rax, [rbp+var_10]
0x18002886c  xor     rax, rcx
0x18002886f  mov     rcx, 0FFFFFFFFFFFFh
0x180028879  and     rax, rcx
0x18002887c  mov     rcx, 2B992DDFA233h
0x180028886  cmp     rax, rbx
0x180028889  cmovz   rax, rcx
0x18002888d  mov     cs:__security_cookie, rax
0x180028894  mov     rbx, [rsp+30h+arg_10]
0x180028899  not     rax
0x18002889c  mov     cs:__security_cookie_complement, rax
0x1800288a3  add     rsp, 30h
0x1800288a7  pop     rbp
0x1800288a8  retn
```
