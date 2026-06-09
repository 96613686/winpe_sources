# __security_init_cookie

- ea: `0x18004d050`
- end: `0x18004d11b`
- name: `__security_init_cookie`
- size: `203`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800647d0`

## callees

- `0x18004d050`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18004d093`
- `KERNEL32!GetCurrentProcessId` at `0x18004d093`
- `KERNEL32!GetTickCount` at `0x18004d0ab`
- `KERNEL32!GetTickCount` at `0x18004d0bb`
- `KERNEL32!GetTickCount` at `0x18004d0ab`
- `KERNEL32!GetTickCount` at `0x18004d0bb`
- `KERNEL32!GetCurrentThreadId` at `0x18004d09f`
- `KERNEL32!GetCurrentThreadId` at `0x18004d09f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004d085`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004d085`
- `KERNEL32!QueryPerformanceCounter` at `0x18004d0d6`
- `KERNEL32!QueryPerformanceCounter` at `0x18004d0d6`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
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
    if ( ((PerformanceCount.QuadPart
         ^ *(_QWORD *)&v1
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (PerformanceCount.QuadPart
          ^ *(_QWORD *)&v1
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18004d050  mov     [rsp-8+arg_18], rbx
0x18004d055  push    rbp
0x18004d056  mov     rbp, rsp
0x18004d059  sub     rsp, 20h
0x18004d05d  and     qword ptr [rbp+PerformanceCount], 0
0x18004d062  mov     rbx, 2B992DDFA232h
0x18004d06c  mov     rcx, cs:__security_cookie
0x18004d073  test    rcx, rcx
0x18004d076  jz      short loc_18004D081
0x18004d078  cmp     rcx, rbx
0x18004d07b  jnz     loc_18004D106
0x18004d081  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004d085  call    cs:__imp_GetSystemTimeAsFileTime
0x18004d08b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004d08f  mov     [rbp+arg_0], rax
0x18004d093  call    cs:__imp_GetCurrentProcessId
0x18004d099  mov     eax, eax
0x18004d09b  xor     [rbp+arg_0], rax
0x18004d09f  call    cs:__imp_GetCurrentThreadId
0x18004d0a5  mov     eax, eax
0x18004d0a7  xor     [rbp+arg_0], rax
0x18004d0ab  call    cs:__imp_GetTickCount
0x18004d0b1  mov     eax, eax
0x18004d0b3  shl     rax, 18h
0x18004d0b7  xor     [rbp+arg_0], rax
0x18004d0bb  call    cs:__imp_GetTickCount
0x18004d0c1  mov     eax, eax
0x18004d0c3  lea     rcx, [rbp+arg_0]
0x18004d0c7  xor     rax, [rbp+arg_0]
0x18004d0cb  xor     rax, rcx
0x18004d0ce  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004d0d2  mov     [rbp+arg_0], rax
0x18004d0d6  call    cs:__imp_QueryPerformanceCounter
0x18004d0dc  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004d0df  mov     rcx, 0FFFFFFFFFFFFh
0x18004d0e9  shl     rax, 20h
0x18004d0ed  xor     rax, [rbp+arg_0]
0x18004d0f1  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004d0f5  and     rax, rcx
0x18004d0f8  mov     rcx, rbx
0x18004d0fb  cmovnz  rcx, rax
0x18004d0ff  mov     cs:__security_cookie, rcx
0x18004d106  mov     rbx, [rsp+20h+arg_18]
0x18004d10b  not     rcx
0x18004d10e  mov     cs:__security_cookie_complement, rcx
0x18004d115  add     rsp, 20h
0x18004d119  pop     rbp
0x18004d11a  retn
```
