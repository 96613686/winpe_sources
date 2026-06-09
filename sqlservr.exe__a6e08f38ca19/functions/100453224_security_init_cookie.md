# __security_init_cookie

- ea: `0x100453224`
- end: `0x1004532d0`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100452fa0`

## callees

- `0x100453224`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x100453250`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100453250`
- `KERNEL32!GetCurrentThreadId` at `0x10045325e`
- `KERNEL32!GetCurrentThreadId` at `0x10045325e`
- `KERNEL32!QueryPerformanceCounter` at `0x10045327a`
- `KERNEL32!QueryPerformanceCounter` at `0x10045327a`
- `KERNEL32!GetCurrentProcessId` at `0x10045326a`
- `KERNEL32!GetCurrentProcessId` at `0x10045326a`

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
0x100453224  mov     [rsp-8+arg_18], rbx
0x100453229  push    rbp
0x10045322a  mov     rbp, rsp
0x10045322d  sub     rsp, 20h
0x100453231  mov     rax, cs:__security_cookie
0x100453238  mov     rbx, 2B992DDFA232h
0x100453242  cmp     rax, rbx
0x100453245  jnz     short loc_1004532BB
0x100453247  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x10045324c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100453250  call    cs:__imp_GetSystemTimeAsFileTime
0x100453256  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x10045325a  mov     [rbp+arg_0], rax
0x10045325e  call    cs:__imp_GetCurrentThreadId
0x100453264  mov     eax, eax
0x100453266  xor     [rbp+arg_0], rax
0x10045326a  call    cs:__imp_GetCurrentProcessId
0x100453270  mov     eax, eax
0x100453272  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100453276  xor     [rbp+arg_0], rax
0x10045327a  call    cs:__imp_QueryPerformanceCounter
0x100453280  mov     eax, dword ptr [rbp+PerformanceCount]
0x100453283  lea     rcx, [rbp+arg_0]
0x100453287  shl     rax, 20h
0x10045328b  xor     rax, qword ptr [rbp+PerformanceCount]
0x10045328f  xor     rax, [rbp+arg_0]
0x100453293  xor     rax, rcx
0x100453296  mov     rcx, 0FFFFFFFFFFFFh
0x1004532a0  and     rax, rcx
0x1004532a3  mov     rcx, 2B992DDFA233h
0x1004532ad  cmp     rax, rbx
0x1004532b0  cmovz   rax, rcx
0x1004532b4  mov     cs:__security_cookie, rax
0x1004532bb  mov     rbx, [rsp+20h+arg_18]
0x1004532c0  not     rax
0x1004532c3  mov     cs:__security_cookie_complement, rax
0x1004532ca  add     rsp, 20h
0x1004532ce  pop     rbp
0x1004532cf  retn
```
