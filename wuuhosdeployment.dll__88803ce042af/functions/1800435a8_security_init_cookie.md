# __security_init_cookie

- ea: `0x1800435a8`
- end: `0x18004365f`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042d90`

## callees

- `0x1800435a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800435ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800435ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800435f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800435f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800435df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800435df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043609`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043609`

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
0x1800435a8  mov     [rsp-8+arg_10], rbx
0x1800435ad  push    rbp
0x1800435ae  mov     rbp, rsp
0x1800435b1  sub     rsp, 30h
0x1800435b5  mov     rax, cs:__security_cookie
0x1800435bc  mov     rbx, 2B992DDFA232h
0x1800435c6  cmp     rax, rbx
0x1800435c9  jnz     short loc_18004364A
0x1800435cb  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800435cf  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800435d7  mov     qword ptr [rbp+PerformanceCount], 0
0x1800435df  call    cs:__imp_GetSystemTimeAsFileTime
0x1800435e5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800435e9  mov     [rbp+var_10], rax
0x1800435ed  call    cs:__imp_GetCurrentThreadId
0x1800435f3  mov     eax, eax
0x1800435f5  xor     [rbp+var_10], rax
0x1800435f9  call    cs:__imp_GetCurrentProcessId
0x1800435ff  mov     eax, eax
0x180043601  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180043605  xor     [rbp+var_10], rax
0x180043609  call    cs:__imp_QueryPerformanceCounter
0x18004360f  mov     eax, dword ptr [rbp+PerformanceCount]
0x180043612  lea     rcx, [rbp+var_10]
0x180043616  shl     rax, 20h
0x18004361a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004361e  xor     rax, [rbp+var_10]
0x180043622  xor     rax, rcx
0x180043625  mov     rcx, 0FFFFFFFFFFFFh
0x18004362f  and     rax, rcx
0x180043632  mov     rcx, 2B992DDFA233h
0x18004363c  cmp     rax, rbx
0x18004363f  cmovz   rax, rcx
0x180043643  mov     cs:__security_cookie, rax
0x18004364a  mov     rbx, [rsp+30h+arg_10]
0x18004364f  not     rax
0x180043652  mov     cs:__security_cookie_complement, rax
0x180043659  add     rsp, 30h
0x18004365d  pop     rbp
0x18004365e  retn
```
