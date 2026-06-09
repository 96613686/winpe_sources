# __security_init_cookie

- ea: `0x180022198`
- end: `0x18002224d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022154`

## callees

- `0x180022198`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800221db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800221db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800221e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800221e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800221f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800221f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800221cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800221cd`

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
0x180022198  mov     [rsp-8+arg_10], rbx
0x18002219d  push    rbp
0x18002219e  mov     rbp, rsp
0x1800221a1  sub     rsp, 30h
0x1800221a5  mov     rax, cs:__security_cookie
0x1800221ac  mov     rbx, 2B992DDFA232h
0x1800221b6  cmp     rax, rbx
0x1800221b9  jnz     short loc_180022238
0x1800221bb  xor     eax, eax
0x1800221bd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800221c1  mov     [rbp+var_10], rax
0x1800221c5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800221c9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800221cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800221d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800221d7  mov     [rbp+var_10], rax
0x1800221db  call    cs:__imp_GetCurrentThreadId
0x1800221e1  mov     eax, eax
0x1800221e3  xor     [rbp+var_10], rax
0x1800221e7  call    cs:__imp_GetCurrentProcessId
0x1800221ed  mov     eax, eax
0x1800221ef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800221f3  xor     [rbp+var_10], rax
0x1800221f7  call    cs:__imp_QueryPerformanceCounter
0x1800221fd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180022200  lea     rcx, [rbp+var_10]
0x180022204  shl     rax, 20h
0x180022208  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002220c  xor     rax, [rbp+var_10]
0x180022210  xor     rax, rcx
0x180022213  mov     rcx, 0FFFFFFFFFFFFh
0x18002221d  and     rax, rcx
0x180022220  mov     rcx, 2B992DDFA233h
0x18002222a  cmp     rax, rbx
0x18002222d  cmovz   rax, rcx
0x180022231  mov     cs:__security_cookie, rax
0x180022238  mov     rbx, [rsp+30h+arg_10]
0x18002223d  not     rax
0x180022240  mov     cs:__security_cookie_complement, rax
0x180022247  add     rsp, 30h
0x18002224b  pop     rbp
0x18002224c  retn
```
