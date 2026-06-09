# __security_init_cookie

- ea: `0x180001d14`
- end: `0x180001df1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001410`

## callees

- `0x180001d14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001d73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001d83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001d73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001d83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d4d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d9e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180001d14  mov     [rsp-8+arg_18], rbx
0x180001d19  push    rbp
0x180001d1a  mov     rbp, rsp
0x180001d1d  sub     rsp, 20h
0x180001d21  xor     eax, eax
0x180001d23  mov     rbx, 2B992DDFA232h
0x180001d2d  mov     [rbp+arg_0], rax
0x180001d31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d35  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d39  mov     rax, cs:__security_cookie
0x180001d40  cmp     rax, rbx
0x180001d43  jnz     loc_180001DDC
0x180001d49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d57  mov     [rbp+arg_0], rax
0x180001d5b  call    cs:__imp_GetCurrentProcessId
0x180001d61  mov     eax, eax
0x180001d63  xor     [rbp+arg_0], rax
0x180001d67  call    cs:__imp_GetCurrentThreadId
0x180001d6d  mov     eax, eax
0x180001d6f  xor     [rbp+arg_0], rax
0x180001d73  call    cs:__imp_GetTickCount
0x180001d79  mov     eax, eax
0x180001d7b  shl     rax, 18h
0x180001d7f  xor     [rbp+arg_0], rax
0x180001d83  call    cs:__imp_GetTickCount
0x180001d89  mov     eax, eax
0x180001d8b  lea     rcx, [rbp+arg_0]
0x180001d8f  xor     rax, [rbp+arg_0]
0x180001d93  xor     rax, rcx
0x180001d96  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d9a  mov     [rbp+arg_0], rax
0x180001d9e  call    cs:__imp_QueryPerformanceCounter
0x180001da4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001da7  mov     rcx, 0FFFFFFFFFFFFh
0x180001db1  shl     rax, 20h
0x180001db5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001db9  xor     rax, [rbp+arg_0]
0x180001dbd  and     rax, rcx
0x180001dc0  mov     rcx, rax
0x180001dc3  cmp     rax, rbx
0x180001dc6  jnz     short loc_180001DD5
0x180001dc8  mov     rax, 2B992DDFA233h
0x180001dd2  mov     rcx, rax
0x180001dd5  mov     cs:__security_cookie, rcx
0x180001ddc  mov     rbx, [rsp+20h+arg_18]
0x180001de1  not     rax
0x180001de4  mov     cs:__security_cookie_complement, rax
0x180001deb  add     rsp, 20h
0x180001def  pop     rbp
0x180001df0  retn
```
