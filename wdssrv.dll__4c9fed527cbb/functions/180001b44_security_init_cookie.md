# __security_init_cookie

- ea: `0x180001b44`
- end: `0x180001c1d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800016e0`

## callees

- `0x180001b44`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001b93`
- `KERNEL32!GetCurrentThreadId` at `0x180001b93`
- `KERNEL32!GetCurrentProcessId` at `0x180001b87`
- `KERNEL32!GetCurrentProcessId` at `0x180001b87`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bca`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b79`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b79`
- `KERNEL32!GetTickCount` at `0x180001b9f`
- `KERNEL32!GetTickCount` at `0x180001baf`
- `KERNEL32!GetTickCount` at `0x180001b9f`
- `KERNEL32!GetTickCount` at `0x180001baf`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180001b44  mov     [rsp-8+arg_18], rbx
0x180001b49  push    rbp
0x180001b4a  mov     rbp, rsp
0x180001b4d  sub     rsp, 20h
0x180001b51  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001b56  mov     rbx, 2B992DDFA232h
0x180001b60  and     qword ptr [rbp+PerformanceCount], 0
0x180001b65  mov     rax, cs:__security_cookie
0x180001b6c  cmp     rax, rbx
0x180001b6f  jnz     loc_180001C08
0x180001b75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b79  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b83  mov     [rbp+arg_0], rax
0x180001b87  call    cs:__imp_GetCurrentProcessId
0x180001b8d  mov     eax, eax
0x180001b8f  xor     [rbp+arg_0], rax
0x180001b93  call    cs:__imp_GetCurrentThreadId
0x180001b99  mov     eax, eax
0x180001b9b  xor     [rbp+arg_0], rax
0x180001b9f  call    cs:__imp_GetTickCount
0x180001ba5  mov     eax, eax
0x180001ba7  shl     rax, 18h
0x180001bab  xor     [rbp+arg_0], rax
0x180001baf  call    cs:__imp_GetTickCount
0x180001bb5  mov     eax, eax
0x180001bb7  lea     rcx, [rbp+arg_0]
0x180001bbb  xor     rax, [rbp+arg_0]
0x180001bbf  xor     rax, rcx
0x180001bc2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001bc6  mov     [rbp+arg_0], rax
0x180001bca  call    cs:__imp_QueryPerformanceCounter
0x180001bd0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001bd3  mov     rcx, 0FFFFFFFFFFFFh
0x180001bdd  shl     rax, 20h
0x180001be1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001be5  xor     rax, [rbp+arg_0]
0x180001be9  and     rax, rcx
0x180001bec  mov     rcx, rax
0x180001bef  cmp     rax, rbx
0x180001bf2  jnz     short loc_180001C01
0x180001bf4  mov     rax, 2B992DDFA233h
0x180001bfe  mov     rcx, rax
0x180001c01  mov     cs:__security_cookie, rcx
0x180001c08  mov     rbx, [rsp+20h+arg_18]
0x180001c0d  not     rax
0x180001c10  mov     cs:__security_cookie_complement, rax
0x180001c17  add     rsp, 20h
0x180001c1b  pop     rbp
0x180001c1c  retn
```
