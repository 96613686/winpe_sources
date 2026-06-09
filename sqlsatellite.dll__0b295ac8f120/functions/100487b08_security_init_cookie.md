# __security_init_cookie

- ea: `0x100487b08`
- end: `0x100487bb4`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100487380`

## callees

- `0x100487b08`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100487b5e`
- `KERNEL32!QueryPerformanceCounter` at `0x100487b5e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100487b34`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100487b34`
- `KERNEL32!GetCurrentThreadId` at `0x100487b42`
- `KERNEL32!GetCurrentThreadId` at `0x100487b42`
- `KERNEL32!GetCurrentProcessId` at `0x100487b4e`
- `KERNEL32!GetCurrentProcessId` at `0x100487b4e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x100487b08  mov     [rsp-8+arg_18], rbx
0x100487b0d  push    rbp
0x100487b0e  mov     rbp, rsp
0x100487b11  sub     rsp, 20h
0x100487b15  mov     rax, cs:__security_cookie
0x100487b1c  mov     rbx, 2B992DDFA232h
0x100487b26  cmp     rax, rbx
0x100487b29  jnz     short loc_100487B9F
0x100487b2b  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x100487b30  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100487b34  call    cs:__imp_GetSystemTimeAsFileTime
0x100487b3a  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100487b3e  mov     [rbp+arg_0], rax
0x100487b42  call    cs:__imp_GetCurrentThreadId
0x100487b48  mov     eax, eax
0x100487b4a  xor     [rbp+arg_0], rax
0x100487b4e  call    cs:__imp_GetCurrentProcessId
0x100487b54  mov     eax, eax
0x100487b56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100487b5a  xor     [rbp+arg_0], rax
0x100487b5e  call    cs:__imp_QueryPerformanceCounter
0x100487b64  mov     eax, dword ptr [rbp+PerformanceCount]
0x100487b67  lea     rcx, [rbp+arg_0]
0x100487b6b  shl     rax, 20h
0x100487b6f  xor     rax, qword ptr [rbp+PerformanceCount]
0x100487b73  xor     rax, [rbp+arg_0]
0x100487b77  xor     rax, rcx
0x100487b7a  mov     rcx, 0FFFFFFFFFFFFh
0x100487b84  and     rax, rcx
0x100487b87  mov     rcx, 2B992DDFA233h
0x100487b91  cmp     rax, rbx
0x100487b94  cmovz   rax, rcx
0x100487b98  mov     cs:__security_cookie, rax
0x100487b9f  mov     rbx, [rsp+20h+arg_18]
0x100487ba4  not     rax
0x100487ba7  mov     cs:__security_cookie_complement, rax
0x100487bae  add     rsp, 20h
0x100487bb2  pop     rbp
0x100487bb3  retn
```
