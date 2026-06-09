# __security_init_cookie

- ea: `0x18002a864`
- end: `0x18002a941`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a300`

## callees

- `0x18002a864`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a8ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a8ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a89d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a89d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a8ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a8ee`

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
0x18002a864  mov     [rsp-8+arg_18], rbx
0x18002a869  push    rbp
0x18002a86a  mov     rbp, rsp
0x18002a86d  sub     rsp, 20h
0x18002a871  xor     eax, eax
0x18002a873  mov     rbx, 2B992DDFA232h
0x18002a87d  mov     [rbp+arg_0], rax
0x18002a881  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002a885  mov     qword ptr [rbp+PerformanceCount], rax
0x18002a889  mov     rax, cs:__security_cookie
0x18002a890  cmp     rax, rbx
0x18002a893  jnz     loc_18002A92C
0x18002a899  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a89d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a8a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002a8a7  mov     [rbp+arg_0], rax
0x18002a8ab  call    cs:__imp_GetCurrentProcessId
0x18002a8b1  mov     eax, eax
0x18002a8b3  xor     [rbp+arg_0], rax
0x18002a8b7  call    cs:__imp_GetCurrentThreadId
0x18002a8bd  mov     eax, eax
0x18002a8bf  xor     [rbp+arg_0], rax
0x18002a8c3  call    cs:__imp_GetTickCount
0x18002a8c9  mov     eax, eax
0x18002a8cb  shl     rax, 18h
0x18002a8cf  xor     [rbp+arg_0], rax
0x18002a8d3  call    cs:__imp_GetTickCount
0x18002a8d9  mov     eax, eax
0x18002a8db  lea     rcx, [rbp+arg_0]
0x18002a8df  xor     rax, [rbp+arg_0]
0x18002a8e3  xor     rax, rcx
0x18002a8e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002a8ea  mov     [rbp+arg_0], rax
0x18002a8ee  call    cs:__imp_QueryPerformanceCounter
0x18002a8f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002a8f7  mov     rcx, 0FFFFFFFFFFFFh
0x18002a901  shl     rax, 20h
0x18002a905  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002a909  xor     rax, [rbp+arg_0]
0x18002a90d  and     rax, rcx
0x18002a910  mov     rcx, rax
0x18002a913  cmp     rax, rbx
0x18002a916  jnz     short loc_18002A925
0x18002a918  mov     rax, 2B992DDFA233h
0x18002a922  mov     rcx, rax
0x18002a925  mov     cs:__security_cookie, rcx
0x18002a92c  mov     rbx, [rsp+20h+arg_18]
0x18002a931  not     rax
0x18002a934  mov     cs:__security_cookie_complement, rax
0x18002a93b  add     rsp, 20h
0x18002a93f  pop     rbp
0x18002a940  retn
```
