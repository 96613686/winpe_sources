# __security_init_cookie

- ea: `0x180008d48`
- end: `0x180008dfd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800082d0`

## callees

- `0x180008d48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008d7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008d7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008da7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008da7`

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
0x180008d48  mov     [rsp-8+arg_10], rbx
0x180008d4d  push    rbp
0x180008d4e  mov     rbp, rsp
0x180008d51  sub     rsp, 30h
0x180008d55  mov     rax, cs:__security_cookie
0x180008d5c  mov     rbx, 2B992DDFA232h
0x180008d66  cmp     rax, rbx
0x180008d69  jnz     short loc_180008DE8
0x180008d6b  xor     eax, eax
0x180008d6d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008d71  mov     [rbp+var_10], rax
0x180008d75  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008d79  mov     qword ptr [rbp+PerformanceCount], rax
0x180008d7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180008d83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008d87  mov     [rbp+var_10], rax
0x180008d8b  call    cs:__imp_GetCurrentThreadId
0x180008d91  mov     eax, eax
0x180008d93  xor     [rbp+var_10], rax
0x180008d97  call    cs:__imp_GetCurrentProcessId
0x180008d9d  mov     eax, eax
0x180008d9f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008da3  xor     [rbp+var_10], rax
0x180008da7  call    cs:__imp_QueryPerformanceCounter
0x180008dad  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008db0  lea     rcx, [rbp+var_10]
0x180008db4  shl     rax, 20h
0x180008db8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008dbc  xor     rax, [rbp+var_10]
0x180008dc0  xor     rax, rcx
0x180008dc3  mov     rcx, 0FFFFFFFFFFFFh
0x180008dcd  and     rax, rcx
0x180008dd0  mov     rcx, 2B992DDFA233h
0x180008dda  cmp     rax, rbx
0x180008ddd  cmovz   rax, rcx
0x180008de1  mov     cs:__security_cookie, rax
0x180008de8  mov     rbx, [rsp+30h+arg_10]
0x180008ded  not     rax
0x180008df0  mov     cs:__security_cookie_complement, rax
0x180008df7  add     rsp, 30h
0x180008dfb  pop     rbp
0x180008dfc  retn
```
