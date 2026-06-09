# __security_init_cookie

- ea: `0x180045ee4`
- end: `0x180045fc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045750`

## callees

- `0x180045ee4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180045f1d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180045f1d`
- `KERNEL32!GetTickCount` at `0x180045f43`
- `KERNEL32!GetTickCount` at `0x180045f53`
- `KERNEL32!GetTickCount` at `0x180045f43`
- `KERNEL32!GetTickCount` at `0x180045f53`
- `KERNEL32!QueryPerformanceCounter` at `0x180045f6e`
- `KERNEL32!QueryPerformanceCounter` at `0x180045f6e`
- `KERNEL32!GetCurrentProcessId` at `0x180045f2b`
- `KERNEL32!GetCurrentProcessId` at `0x180045f2b`
- `KERNEL32!GetCurrentThreadId` at `0x180045f37`
- `KERNEL32!GetCurrentThreadId` at `0x180045f37`

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
0x180045ee4  mov     [rsp-8+arg_18], rbx
0x180045ee9  push    rbp
0x180045eea  mov     rbp, rsp
0x180045eed  sub     rsp, 20h
0x180045ef1  xor     eax, eax
0x180045ef3  mov     rbx, 2B992DDFA232h
0x180045efd  mov     [rbp+arg_0], rax
0x180045f01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180045f05  mov     qword ptr [rbp+PerformanceCount], rax
0x180045f09  mov     rax, cs:__security_cookie
0x180045f10  cmp     rax, rbx
0x180045f13  jnz     loc_180045FAC
0x180045f19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180045f1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180045f23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180045f27  mov     [rbp+arg_0], rax
0x180045f2b  call    cs:__imp_GetCurrentProcessId
0x180045f31  mov     eax, eax
0x180045f33  xor     [rbp+arg_0], rax
0x180045f37  call    cs:__imp_GetCurrentThreadId
0x180045f3d  mov     eax, eax
0x180045f3f  xor     [rbp+arg_0], rax
0x180045f43  call    cs:__imp_GetTickCount
0x180045f49  mov     eax, eax
0x180045f4b  shl     rax, 18h
0x180045f4f  xor     [rbp+arg_0], rax
0x180045f53  call    cs:__imp_GetTickCount
0x180045f59  mov     eax, eax
0x180045f5b  lea     rcx, [rbp+arg_0]
0x180045f5f  xor     rax, [rbp+arg_0]
0x180045f63  xor     rax, rcx
0x180045f66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180045f6a  mov     [rbp+arg_0], rax
0x180045f6e  call    cs:__imp_QueryPerformanceCounter
0x180045f74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180045f77  mov     rcx, 0FFFFFFFFFFFFh
0x180045f81  shl     rax, 20h
0x180045f85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180045f89  xor     rax, [rbp+arg_0]
0x180045f8d  and     rax, rcx
0x180045f90  mov     rcx, rax
0x180045f93  cmp     rax, rbx
0x180045f96  jnz     short loc_180045FA5
0x180045f98  mov     rax, 2B992DDFA233h
0x180045fa2  mov     rcx, rax
0x180045fa5  mov     cs:__security_cookie, rcx
0x180045fac  mov     rbx, [rsp+20h+arg_18]
0x180045fb1  not     rax
0x180045fb4  mov     cs:__security_cookie_complement, rax
0x180045fbb  add     rsp, 20h
0x180045fbf  pop     rbp
0x180045fc0  retn
```
