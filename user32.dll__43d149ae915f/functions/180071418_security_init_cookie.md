# __security_init_cookie

- ea: `0x180071418`
- end: `0x1800714ec`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800713f8`

## callees

- `0x180071418`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180071464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180071464`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007147c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007148c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007147c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007148c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071456`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071456`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800714a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800714a7`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180071418  mov     [rsp-8+arg_18], rbx
0x18007141d  push    rbp
0x18007141e  mov     rbp, rsp
0x180071421  sub     rsp, 20h
0x180071425  mov     rcx, cs:__security_cookie
0x18007142c  xor     eax, eax
0x18007142e  mov     [rbp+arg_0], rax
0x180071432  mov     rbx, 2B992DDFA232h
0x18007143c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180071440  mov     qword ptr [rbp+PerformanceCount], rax
0x180071444  test    rcx, rcx
0x180071447  jz      short loc_180071452
0x180071449  cmp     rcx, rbx
0x18007144c  jnz     loc_1800714D7
0x180071452  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180071456  call    cs:__imp_GetSystemTimeAsFileTime
0x18007145c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180071460  mov     [rbp+arg_0], rax
0x180071464  call    cs:__imp_GetCurrentProcessId
0x18007146a  mov     eax, eax
0x18007146c  xor     [rbp+arg_0], rax
0x180071470  call    cs:__imp_GetCurrentThreadId
0x180071476  mov     eax, eax
0x180071478  xor     [rbp+arg_0], rax
0x18007147c  call    cs:__imp_GetTickCount
0x180071482  mov     eax, eax
0x180071484  shl     rax, 18h
0x180071488  xor     [rbp+arg_0], rax
0x18007148c  call    cs:__imp_GetTickCount
0x180071492  mov     eax, eax
0x180071494  lea     rcx, [rbp+arg_0]
0x180071498  xor     rax, [rbp+arg_0]
0x18007149c  xor     rax, rcx
0x18007149f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800714a3  mov     [rbp+arg_0], rax
0x1800714a7  call    cs:__imp_QueryPerformanceCounter
0x1800714ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800714b0  mov     rcx, 0FFFFFFFFFFFFh
0x1800714ba  shl     rax, 20h
0x1800714be  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800714c2  xor     rax, [rbp+arg_0]
0x1800714c6  and     rax, rcx
0x1800714c9  mov     rcx, rbx
0x1800714cc  cmovnz  rcx, rax
0x1800714d0  mov     cs:__security_cookie, rcx
0x1800714d7  mov     rbx, [rsp+20h+arg_18]
0x1800714dc  not     rcx
0x1800714df  mov     cs:__security_cookie_complement, rcx
0x1800714e6  add     rsp, 20h
0x1800714ea  pop     rbp
0x1800714eb  retn
```
