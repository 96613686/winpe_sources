# __security_init_cookie

- ea: `0x180001a08`
- end: `0x180001abd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015b0`

## callees

- `0x180001a08`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001a67`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a67`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a3d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a3d`
- `KERNEL32!GetCurrentProcessId` at `0x180001a57`
- `KERNEL32!GetCurrentProcessId` at `0x180001a57`
- `KERNEL32!GetCurrentThreadId` at `0x180001a4b`
- `KERNEL32!GetCurrentThreadId` at `0x180001a4b`

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
0x180001a08  mov     [rsp-8+arg_10], rbx
0x180001a0d  push    rbp
0x180001a0e  mov     rbp, rsp
0x180001a11  sub     rsp, 30h
0x180001a15  mov     rax, cs:__security_cookie
0x180001a1c  mov     rbx, 2B992DDFA232h
0x180001a26  cmp     rax, rbx
0x180001a29  jnz     short loc_180001AA8
0x180001a2b  xor     eax, eax
0x180001a2d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a31  mov     [rbp+var_10], rax
0x180001a35  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a39  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a3d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a43  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a47  mov     [rbp+var_10], rax
0x180001a4b  call    cs:__imp_GetCurrentThreadId
0x180001a51  mov     eax, eax
0x180001a53  xor     [rbp+var_10], rax
0x180001a57  call    cs:__imp_GetCurrentProcessId
0x180001a5d  mov     eax, eax
0x180001a5f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a63  xor     [rbp+var_10], rax
0x180001a67  call    cs:__imp_QueryPerformanceCounter
0x180001a6d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a70  lea     rcx, [rbp+var_10]
0x180001a74  shl     rax, 20h
0x180001a78  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a7c  xor     rax, [rbp+var_10]
0x180001a80  xor     rax, rcx
0x180001a83  mov     rcx, 0FFFFFFFFFFFFh
0x180001a8d  and     rax, rcx
0x180001a90  mov     rcx, 2B992DDFA233h
0x180001a9a  cmp     rax, rbx
0x180001a9d  cmovz   rax, rcx
0x180001aa1  mov     cs:__security_cookie, rax
0x180001aa8  mov     rbx, [rsp+30h+arg_10]
0x180001aad  not     rax
0x180001ab0  mov     cs:__security_cookie_complement, rax
0x180001ab7  add     rsp, 30h
0x180001abb  pop     rbp
0x180001abc  retn
```
