# __security_init_cookie

- ea: `0x18000b960`
- end: `0x18000ba15`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b500`

## callees

- `0x18000b960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b9bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b9bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b995`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b995`

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
0x18000b960  mov     [rsp-8+arg_10], rbx
0x18000b965  push    rbp
0x18000b966  mov     rbp, rsp
0x18000b969  sub     rsp, 30h
0x18000b96d  mov     rax, cs:__security_cookie
0x18000b974  mov     rbx, 2B992DDFA232h
0x18000b97e  cmp     rax, rbx
0x18000b981  jnz     short loc_18000BA00
0x18000b983  xor     eax, eax
0x18000b985  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b989  mov     [rbp+var_10], rax
0x18000b98d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000b991  mov     qword ptr [rbp+PerformanceCount], rax
0x18000b995  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b99b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000b99f  mov     [rbp+var_10], rax
0x18000b9a3  call    cs:__imp_GetCurrentThreadId
0x18000b9a9  mov     eax, eax
0x18000b9ab  xor     [rbp+var_10], rax
0x18000b9af  call    cs:__imp_GetCurrentProcessId
0x18000b9b5  mov     eax, eax
0x18000b9b7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000b9bb  xor     [rbp+var_10], rax
0x18000b9bf  call    cs:__imp_QueryPerformanceCounter
0x18000b9c5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000b9c8  lea     rcx, [rbp+var_10]
0x18000b9cc  shl     rax, 20h
0x18000b9d0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000b9d4  xor     rax, [rbp+var_10]
0x18000b9d8  xor     rax, rcx
0x18000b9db  mov     rcx, 0FFFFFFFFFFFFh
0x18000b9e5  and     rax, rcx
0x18000b9e8  mov     rcx, 2B992DDFA233h
0x18000b9f2  cmp     rax, rbx
0x18000b9f5  cmovz   rax, rcx
0x18000b9f9  mov     cs:__security_cookie, rax
0x18000ba00  mov     rbx, [rsp+30h+arg_10]
0x18000ba05  not     rax
0x18000ba08  mov     cs:__security_cookie_complement, rax
0x18000ba0f  add     rsp, 30h
0x18000ba13  pop     rbp
0x18000ba14  retn
```
