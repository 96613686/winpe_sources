# __security_init_cookie

- ea: `0x18002efa4`
- end: `0x18002f081`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e640`

## callees

- `0x18002efa4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002efdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002efdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f003`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f013`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f003`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f013`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002efeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002efeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eff7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f02e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f02e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18002efa4  mov     [rsp-8+arg_18], rbx
0x18002efa9  push    rbp
0x18002efaa  mov     rbp, rsp
0x18002efad  sub     rsp, 20h
0x18002efb1  xor     eax, eax
0x18002efb3  mov     rbx, 2B992DDFA232h
0x18002efbd  mov     [rbp+arg_0], rax
0x18002efc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002efc5  mov     qword ptr [rbp+PerformanceCount], rax
0x18002efc9  mov     rax, cs:__security_cookie
0x18002efd0  cmp     rax, rbx
0x18002efd3  jnz     loc_18002F06C
0x18002efd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002efdd  call    cs:__imp_GetSystemTimeAsFileTime
0x18002efe3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002efe7  mov     [rbp+arg_0], rax
0x18002efeb  call    cs:__imp_GetCurrentProcessId
0x18002eff1  mov     eax, eax
0x18002eff3  xor     [rbp+arg_0], rax
0x18002eff7  call    cs:__imp_GetCurrentThreadId
0x18002effd  mov     eax, eax
0x18002efff  xor     [rbp+arg_0], rax
0x18002f003  call    cs:__imp_GetTickCount
0x18002f009  mov     eax, eax
0x18002f00b  shl     rax, 18h
0x18002f00f  xor     [rbp+arg_0], rax
0x18002f013  call    cs:__imp_GetTickCount
0x18002f019  mov     eax, eax
0x18002f01b  lea     rcx, [rbp+arg_0]
0x18002f01f  xor     rax, [rbp+arg_0]
0x18002f023  xor     rax, rcx
0x18002f026  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002f02a  mov     [rbp+arg_0], rax
0x18002f02e  call    cs:__imp_QueryPerformanceCounter
0x18002f034  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002f037  mov     rcx, 0FFFFFFFFFFFFh
0x18002f041  shl     rax, 20h
0x18002f045  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002f049  xor     rax, [rbp+arg_0]
0x18002f04d  and     rax, rcx
0x18002f050  mov     rcx, rax
0x18002f053  cmp     rax, rbx
0x18002f056  jnz     short loc_18002F065
0x18002f058  mov     rax, 2B992DDFA233h
0x18002f062  mov     rcx, rax
0x18002f065  mov     cs:__security_cookie, rcx
0x18002f06c  mov     rbx, [rsp+20h+arg_18]
0x18002f071  not     rax
0x18002f074  mov     cs:__security_cookie_complement, rax
0x18002f07b  add     rsp, 20h
0x18002f07f  pop     rbp
0x18002f080  retn
```
