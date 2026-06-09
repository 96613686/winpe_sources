# __security_init_cookie

- ea: `0x180006574`
- end: `0x180006629`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005c70`

## callees

- `0x180006574`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800065a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800065a9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800065d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800065d3`

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
0x180006574  mov     [rsp-8+arg_10], rbx
0x180006579  push    rbp
0x18000657a  mov     rbp, rsp
0x18000657d  sub     rsp, 30h
0x180006581  mov     rax, cs:__security_cookie
0x180006588  mov     rbx, 2B992DDFA232h
0x180006592  cmp     rax, rbx
0x180006595  jnz     short loc_180006614
0x180006597  xor     eax, eax
0x180006599  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000659d  mov     [rbp+var_10], rax
0x1800065a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800065a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800065a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800065af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800065b3  mov     [rbp+var_10], rax
0x1800065b7  call    cs:__imp_GetCurrentThreadId
0x1800065bd  mov     eax, eax
0x1800065bf  xor     [rbp+var_10], rax
0x1800065c3  call    cs:__imp_GetCurrentProcessId
0x1800065c9  mov     eax, eax
0x1800065cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800065cf  xor     [rbp+var_10], rax
0x1800065d3  call    cs:__imp_QueryPerformanceCounter
0x1800065d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800065dc  lea     rcx, [rbp+var_10]
0x1800065e0  shl     rax, 20h
0x1800065e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800065e8  xor     rax, [rbp+var_10]
0x1800065ec  xor     rax, rcx
0x1800065ef  mov     rcx, 0FFFFFFFFFFFFh
0x1800065f9  and     rax, rcx
0x1800065fc  mov     rcx, 2B992DDFA233h
0x180006606  cmp     rax, rbx
0x180006609  cmovz   rax, rcx
0x18000660d  mov     cs:__security_cookie, rax
0x180006614  mov     rbx, [rsp+30h+arg_10]
0x180006619  not     rax
0x18000661c  mov     cs:__security_cookie_complement, rax
0x180006623  add     rsp, 30h
0x180006627  pop     rbp
0x180006628  retn
```
