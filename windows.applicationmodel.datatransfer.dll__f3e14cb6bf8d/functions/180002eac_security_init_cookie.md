# __security_init_cookie

- ea: `0x180002eac`
- end: `0x180002f61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180002eac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002eef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002eef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ee1`

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
0x180002eac  mov     [rsp-8+arg_10], rbx
0x180002eb1  push    rbp
0x180002eb2  mov     rbp, rsp
0x180002eb5  sub     rsp, 30h
0x180002eb9  mov     rax, cs:__security_cookie
0x180002ec0  mov     rbx, 2B992DDFA232h
0x180002eca  cmp     rax, rbx
0x180002ecd  jnz     short loc_180002F4C
0x180002ecf  xor     eax, eax
0x180002ed1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002ed5  mov     [rbp+var_10], rax
0x180002ed9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002edd  mov     qword ptr [rbp+PerformanceCount], rax
0x180002ee1  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ee7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002eeb  mov     [rbp+var_10], rax
0x180002eef  call    cs:__imp_GetCurrentThreadId
0x180002ef5  mov     eax, eax
0x180002ef7  xor     [rbp+var_10], rax
0x180002efb  call    cs:__imp_GetCurrentProcessId
0x180002f01  mov     eax, eax
0x180002f03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002f07  xor     [rbp+var_10], rax
0x180002f0b  call    cs:__imp_QueryPerformanceCounter
0x180002f11  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002f14  lea     rcx, [rbp+var_10]
0x180002f18  shl     rax, 20h
0x180002f1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002f20  xor     rax, [rbp+var_10]
0x180002f24  xor     rax, rcx
0x180002f27  mov     rcx, 0FFFFFFFFFFFFh
0x180002f31  and     rax, rcx
0x180002f34  mov     rcx, 2B992DDFA233h
0x180002f3e  cmp     rax, rbx
0x180002f41  cmovz   rax, rcx
0x180002f45  mov     cs:__security_cookie, rax
0x180002f4c  mov     rbx, [rsp+30h+arg_10]
0x180002f51  not     rax
0x180002f54  mov     cs:__security_cookie_complement, rax
0x180002f5b  add     rsp, 30h
0x180002f5f  pop     rbp
0x180002f60  retn
```
