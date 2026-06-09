# __security_init_cookie

- ea: `0x100426bf4`
- end: `0x100426ca0`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004268e8`

## callees

- `0x100426bf4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100426c4a`
- `KERNEL32!QueryPerformanceCounter` at `0x100426c4a`
- `KERNEL32!GetCurrentProcessId` at `0x100426c3a`
- `KERNEL32!GetCurrentProcessId` at `0x100426c3a`
- `KERNEL32!GetCurrentThreadId` at `0x100426c2e`
- `KERNEL32!GetCurrentThreadId` at `0x100426c2e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100426c20`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100426c20`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x100426bf4  mov     [rsp-8+arg_18], rbx
0x100426bf9  push    rbp
0x100426bfa  mov     rbp, rsp
0x100426bfd  sub     rsp, 20h
0x100426c01  mov     rax, cs:__security_cookie
0x100426c08  mov     rbx, 2B992DDFA232h
0x100426c12  cmp     rax, rbx
0x100426c15  jnz     short loc_100426C8B
0x100426c17  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x100426c1c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100426c20  call    cs:__imp_GetSystemTimeAsFileTime
0x100426c26  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100426c2a  mov     [rbp+arg_0], rax
0x100426c2e  call    cs:__imp_GetCurrentThreadId
0x100426c34  mov     eax, eax
0x100426c36  xor     [rbp+arg_0], rax
0x100426c3a  call    cs:__imp_GetCurrentProcessId
0x100426c40  mov     eax, eax
0x100426c42  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100426c46  xor     [rbp+arg_0], rax
0x100426c4a  call    cs:__imp_QueryPerformanceCounter
0x100426c50  mov     eax, dword ptr [rbp+PerformanceCount]
0x100426c53  lea     rcx, [rbp+arg_0]
0x100426c57  shl     rax, 20h
0x100426c5b  xor     rax, qword ptr [rbp+PerformanceCount]
0x100426c5f  xor     rax, [rbp+arg_0]
0x100426c63  xor     rax, rcx
0x100426c66  mov     rcx, 0FFFFFFFFFFFFh
0x100426c70  and     rax, rcx
0x100426c73  mov     rcx, 2B992DDFA233h
0x100426c7d  cmp     rax, rbx
0x100426c80  cmovz   rax, rcx
0x100426c84  mov     cs:__security_cookie, rax
0x100426c8b  mov     rbx, [rsp+20h+arg_18]
0x100426c90  not     rax
0x100426c93  mov     cs:__security_cookie_complement, rax
0x100426c9a  add     rsp, 20h
0x100426c9e  pop     rbp
0x100426c9f  retn
```
