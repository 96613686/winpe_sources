# __security_init_cookie

- ea: `0x140002898`
- end: `0x14000294d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002610`

## callees

- `0x140002898`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400028e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400028e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400028cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400028cd`

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
0x140002898  mov     [rsp-8+arg_10], rbx
0x14000289d  push    rbp
0x14000289e  mov     rbp, rsp
0x1400028a1  sub     rsp, 30h
0x1400028a5  mov     rax, cs:__security_cookie
0x1400028ac  mov     rbx, 2B992DDFA232h
0x1400028b6  cmp     rax, rbx
0x1400028b9  jnz     short loc_140002938
0x1400028bb  xor     eax, eax
0x1400028bd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400028c1  mov     [rbp+var_10], rax
0x1400028c5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400028c9  mov     qword ptr [rbp+PerformanceCount], rax
0x1400028cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400028d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400028d7  mov     [rbp+var_10], rax
0x1400028db  call    cs:__imp_GetCurrentThreadId
0x1400028e1  mov     eax, eax
0x1400028e3  xor     [rbp+var_10], rax
0x1400028e7  call    cs:__imp_GetCurrentProcessId
0x1400028ed  mov     eax, eax
0x1400028ef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400028f3  xor     [rbp+var_10], rax
0x1400028f7  call    cs:__imp_QueryPerformanceCounter
0x1400028fd  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002900  lea     rcx, [rbp+var_10]
0x140002904  shl     rax, 20h
0x140002908  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000290c  xor     rax, [rbp+var_10]
0x140002910  xor     rax, rcx
0x140002913  mov     rcx, 0FFFFFFFFFFFFh
0x14000291d  and     rax, rcx
0x140002920  mov     rcx, 2B992DDFA233h
0x14000292a  cmp     rax, rbx
0x14000292d  cmovz   rax, rcx
0x140002931  mov     cs:__security_cookie, rax
0x140002938  mov     rbx, [rsp+30h+arg_10]
0x14000293d  not     rax
0x140002940  mov     cs:__security_cookie_complement, rax
0x140002947  add     rsp, 30h
0x14000294b  pop     rbp
0x14000294c  retn
```
