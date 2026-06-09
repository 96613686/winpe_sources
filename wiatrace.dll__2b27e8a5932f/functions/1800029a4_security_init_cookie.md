# __security_init_cookie

- ea: `0x1800029a4`
- end: `0x180002a59`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002930`

## callees

- `0x1800029a4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180002a03`
- `KERNEL32!QueryPerformanceCounter` at `0x180002a03`
- `KERNEL32!GetCurrentProcessId` at `0x1800029f3`
- `KERNEL32!GetCurrentProcessId` at `0x1800029f3`
- `KERNEL32!GetCurrentThreadId` at `0x1800029e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800029e7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800029d9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800029d9`

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
0x1800029a4  mov     [rsp-8+arg_10], rbx
0x1800029a9  push    rbp
0x1800029aa  mov     rbp, rsp
0x1800029ad  sub     rsp, 30h
0x1800029b1  mov     rax, cs:__security_cookie
0x1800029b8  mov     rbx, 2B992DDFA232h
0x1800029c2  cmp     rax, rbx
0x1800029c5  jnz     short loc_180002A44
0x1800029c7  xor     eax, eax
0x1800029c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029cd  mov     [rbp+var_10], rax
0x1800029d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800029d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800029d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800029df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800029e3  mov     [rbp+var_10], rax
0x1800029e7  call    cs:__imp_GetCurrentThreadId
0x1800029ed  mov     eax, eax
0x1800029ef  xor     [rbp+var_10], rax
0x1800029f3  call    cs:__imp_GetCurrentProcessId
0x1800029f9  mov     eax, eax
0x1800029fb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800029ff  xor     [rbp+var_10], rax
0x180002a03  call    cs:__imp_QueryPerformanceCounter
0x180002a09  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a0c  lea     rcx, [rbp+var_10]
0x180002a10  shl     rax, 20h
0x180002a14  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a18  xor     rax, [rbp+var_10]
0x180002a1c  xor     rax, rcx
0x180002a1f  mov     rcx, 0FFFFFFFFFFFFh
0x180002a29  and     rax, rcx
0x180002a2c  mov     rcx, 2B992DDFA233h
0x180002a36  cmp     rax, rbx
0x180002a39  cmovz   rax, rcx
0x180002a3d  mov     cs:__security_cookie, rax
0x180002a44  mov     rbx, [rsp+30h+arg_10]
0x180002a49  not     rax
0x180002a4c  mov     cs:__security_cookie_complement, rax
0x180002a53  add     rsp, 30h
0x180002a57  pop     rbp
0x180002a58  retn
```
