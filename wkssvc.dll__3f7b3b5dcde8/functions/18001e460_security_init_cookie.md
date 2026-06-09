# __security_init_cookie

- ea: `0x18001e460`
- end: `0x18001e515`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e3d0`

## callees

- `0x18001e460`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e495`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e4af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e4af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e4bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e4bf`

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
0x18001e460  mov     [rsp-8+arg_10], rbx
0x18001e465  push    rbp
0x18001e466  mov     rbp, rsp
0x18001e469  sub     rsp, 30h
0x18001e46d  mov     rax, cs:__security_cookie
0x18001e474  mov     rbx, 2B992DDFA232h
0x18001e47e  cmp     rax, rbx
0x18001e481  jnz     short loc_18001E500
0x18001e483  xor     eax, eax
0x18001e485  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001e489  mov     [rbp+var_10], rax
0x18001e48d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001e491  mov     qword ptr [rbp+PerformanceCount], rax
0x18001e495  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e49b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001e49f  mov     [rbp+var_10], rax
0x18001e4a3  call    cs:__imp_GetCurrentThreadId
0x18001e4a9  mov     eax, eax
0x18001e4ab  xor     [rbp+var_10], rax
0x18001e4af  call    cs:__imp_GetCurrentProcessId
0x18001e4b5  mov     eax, eax
0x18001e4b7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001e4bb  xor     [rbp+var_10], rax
0x18001e4bf  call    cs:__imp_QueryPerformanceCounter
0x18001e4c5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001e4c8  lea     rcx, [rbp+var_10]
0x18001e4cc  shl     rax, 20h
0x18001e4d0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001e4d4  xor     rax, [rbp+var_10]
0x18001e4d8  xor     rax, rcx
0x18001e4db  mov     rcx, 0FFFFFFFFFFFFh
0x18001e4e5  and     rax, rcx
0x18001e4e8  mov     rcx, 2B992DDFA233h
0x18001e4f2  cmp     rax, rbx
0x18001e4f5  cmovz   rax, rcx
0x18001e4f9  mov     cs:__security_cookie, rax
0x18001e500  mov     rbx, [rsp+30h+arg_10]
0x18001e505  not     rax
0x18001e508  mov     cs:__security_cookie_complement, rax
0x18001e50f  add     rsp, 30h
0x18001e513  pop     rbp
0x18001e514  retn
```
