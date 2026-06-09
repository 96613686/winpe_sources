# __security_init_cookie

- ea: `0x100615e08`
- end: `0x100615eb4`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100435e10`

## callees

- `0x100615e08`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x100615e42`
- `KERNEL32!GetCurrentThreadId` at `0x100615e42`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100615e34`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100615e34`
- `KERNEL32!QueryPerformanceCounter` at `0x100615e5e`
- `KERNEL32!QueryPerformanceCounter` at `0x100615e5e`
- `KERNEL32!GetCurrentProcessId` at `0x100615e4e`
- `KERNEL32!GetCurrentProcessId` at `0x100615e4e`

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
0x100615e08  mov     [rsp-8+arg_18], rbx
0x100615e0d  push    rbp
0x100615e0e  mov     rbp, rsp
0x100615e11  sub     rsp, 20h
0x100615e15  mov     rax, cs:__security_cookie
0x100615e1c  mov     rbx, 2B992DDFA232h
0x100615e26  cmp     rax, rbx
0x100615e29  jnz     short loc_100615E9F
0x100615e2b  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x100615e30  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100615e34  call    cs:__imp_GetSystemTimeAsFileTime
0x100615e3a  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100615e3e  mov     [rbp+arg_0], rax
0x100615e42  call    cs:__imp_GetCurrentThreadId
0x100615e48  mov     eax, eax
0x100615e4a  xor     [rbp+arg_0], rax
0x100615e4e  call    cs:__imp_GetCurrentProcessId
0x100615e54  mov     eax, eax
0x100615e56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100615e5a  xor     [rbp+arg_0], rax
0x100615e5e  call    cs:__imp_QueryPerformanceCounter
0x100615e64  mov     eax, dword ptr [rbp+PerformanceCount]
0x100615e67  lea     rcx, [rbp+arg_0]
0x100615e6b  shl     rax, 20h
0x100615e6f  xor     rax, qword ptr [rbp+PerformanceCount]
0x100615e73  xor     rax, [rbp+arg_0]
0x100615e77  xor     rax, rcx
0x100615e7a  mov     rcx, 0FFFFFFFFFFFFh
0x100615e84  and     rax, rcx
0x100615e87  mov     rcx, 2B992DDFA233h
0x100615e91  cmp     rax, rbx
0x100615e94  cmovz   rax, rcx
0x100615e98  mov     cs:__security_cookie, rax
0x100615e9f  mov     rbx, [rsp+20h+arg_18]
0x100615ea4  not     rax
0x100615ea7  mov     cs:__security_cookie_complement, rax
0x100615eae  add     rsp, 20h
0x100615eb2  pop     rbp
0x100615eb3  retn
```
