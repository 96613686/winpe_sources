# __security_init_cookie

- ea: `0x140005224`
- end: `0x1400052d9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004f60`

## callees

- `0x140005224`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005283`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005267`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005259`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005259`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x140005224  mov     [rsp-8+arg_10], rbx
0x140005229  push    rbp
0x14000522a  mov     rbp, rsp
0x14000522d  sub     rsp, 30h
0x140005231  mov     rax, cs:__security_cookie
0x140005238  mov     rbx, 2B992DDFA232h
0x140005242  cmp     rax, rbx
0x140005245  jnz     short loc_1400052C4
0x140005247  xor     eax, eax
0x140005249  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000524d  mov     [rbp+var_10], rax
0x140005251  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140005255  mov     qword ptr [rbp+PerformanceCount], rax
0x140005259  call    cs:__imp_GetSystemTimeAsFileTime
0x14000525f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140005263  mov     [rbp+var_10], rax
0x140005267  call    cs:__imp_GetCurrentThreadId
0x14000526d  mov     eax, eax
0x14000526f  xor     [rbp+var_10], rax
0x140005273  call    cs:__imp_GetCurrentProcessId
0x140005279  mov     eax, eax
0x14000527b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000527f  xor     [rbp+var_10], rax
0x140005283  call    cs:__imp_QueryPerformanceCounter
0x140005289  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000528c  lea     rcx, [rbp+var_10]
0x140005290  shl     rax, 20h
0x140005294  xor     rax, qword ptr [rbp+PerformanceCount]
0x140005298  xor     rax, [rbp+var_10]
0x14000529c  xor     rax, rcx
0x14000529f  mov     rcx, 0FFFFFFFFFFFFh
0x1400052a9  and     rax, rcx
0x1400052ac  mov     rcx, 2B992DDFA233h
0x1400052b6  cmp     rax, rbx
0x1400052b9  cmovz   rax, rcx
0x1400052bd  mov     cs:__security_cookie, rax
0x1400052c4  mov     rbx, [rsp+30h+arg_10]
0x1400052c9  not     rax
0x1400052cc  mov     cs:__security_cookie_complement, rax
0x1400052d3  add     rsp, 30h
0x1400052d7  pop     rbp
0x1400052d8  retn
```
