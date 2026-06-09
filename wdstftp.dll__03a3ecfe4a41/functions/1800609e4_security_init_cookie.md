# __security_init_cookie

- ea: `0x1800609e4`
- end: `0x180060ab8`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060510`

## callees

- `0x1800609e4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180060a3a`
- `KERNEL32!GetTickCount` at `0x180060a4a`
- `KERNEL32!GetTickCount` at `0x180060a3a`
- `KERNEL32!GetTickCount` at `0x180060a4a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180060a14`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180060a14`
- `KERNEL32!GetCurrentProcessId` at `0x180060a22`
- `KERNEL32!GetCurrentProcessId` at `0x180060a22`
- `KERNEL32!QueryPerformanceCounter` at `0x180060a65`
- `KERNEL32!QueryPerformanceCounter` at `0x180060a65`
- `KERNEL32!GetCurrentThreadId` at `0x180060a2e`
- `KERNEL32!GetCurrentThreadId` at `0x180060a2e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
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
0x1800609e4  mov     [rsp-8+arg_18], rbx
0x1800609e9  push    rbp
0x1800609ea  mov     rbp, rsp
0x1800609ed  sub     rsp, 20h
0x1800609f1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800609f6  mov     rbx, 2B992DDFA232h
0x180060a00  mov     rax, cs:__security_cookie
0x180060a07  cmp     rax, rbx
0x180060a0a  jnz     loc_180060AA3
0x180060a10  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180060a14  call    cs:__imp_GetSystemTimeAsFileTime
0x180060a1a  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180060a1e  mov     [rbp+arg_0], rax
0x180060a22  call    cs:__imp_GetCurrentProcessId
0x180060a28  mov     eax, eax
0x180060a2a  xor     [rbp+arg_0], rax
0x180060a2e  call    cs:__imp_GetCurrentThreadId
0x180060a34  mov     eax, eax
0x180060a36  xor     [rbp+arg_0], rax
0x180060a3a  call    cs:__imp_GetTickCount
0x180060a40  mov     eax, eax
0x180060a42  shl     rax, 18h
0x180060a46  xor     [rbp+arg_0], rax
0x180060a4a  call    cs:__imp_GetTickCount
0x180060a50  mov     eax, eax
0x180060a52  lea     rcx, [rbp+arg_0]
0x180060a56  xor     rax, [rbp+arg_0]
0x180060a5a  xor     rax, rcx
0x180060a5d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180060a61  mov     [rbp+arg_0], rax
0x180060a65  call    cs:__imp_QueryPerformanceCounter
0x180060a6b  mov     eax, dword ptr [rbp+PerformanceCount]
0x180060a6e  mov     rcx, 0FFFFFFFFFFFFh
0x180060a78  shl     rax, 20h
0x180060a7c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180060a80  xor     rax, [rbp+arg_0]
0x180060a84  and     rax, rcx
0x180060a87  mov     rcx, rax
0x180060a8a  cmp     rax, rbx
0x180060a8d  jnz     short loc_180060A9C
0x180060a8f  mov     rax, 2B992DDFA233h
0x180060a99  mov     rcx, rax
0x180060a9c  mov     cs:__security_cookie, rcx
0x180060aa3  mov     rbx, [rsp+20h+arg_18]
0x180060aa8  not     rax
0x180060aab  mov     cs:__security_cookie_complement, rax
0x180060ab2  add     rsp, 20h
0x180060ab6  pop     rbp
0x180060ab7  retn
```
