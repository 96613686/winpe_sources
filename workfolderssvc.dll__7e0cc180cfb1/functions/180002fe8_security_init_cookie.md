# __security_init_cookie

- ea: `0x180002fe8`
- end: `0x18000309d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a50`

## callees

- `0x180002fe8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003037`
- `KERNEL32!GetCurrentProcessId` at `0x180003037`
- `KERNEL32!QueryPerformanceCounter` at `0x180003047`
- `KERNEL32!QueryPerformanceCounter` at `0x180003047`
- `KERNEL32!GetCurrentThreadId` at `0x18000302b`
- `KERNEL32!GetCurrentThreadId` at `0x18000302b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000301d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000301d`

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
0x180002fe8  mov     [rsp-8+arg_10], rbx
0x180002fed  push    rbp
0x180002fee  mov     rbp, rsp
0x180002ff1  sub     rsp, 30h
0x180002ff5  mov     rax, cs:__security_cookie
0x180002ffc  mov     rbx, 2B992DDFA232h
0x180003006  cmp     rax, rbx
0x180003009  jnz     short loc_180003088
0x18000300b  xor     eax, eax
0x18000300d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003011  mov     [rbp+var_10], rax
0x180003015  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003019  mov     qword ptr [rbp+PerformanceCount], rax
0x18000301d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003023  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003027  mov     [rbp+var_10], rax
0x18000302b  call    cs:__imp_GetCurrentThreadId
0x180003031  mov     eax, eax
0x180003033  xor     [rbp+var_10], rax
0x180003037  call    cs:__imp_GetCurrentProcessId
0x18000303d  mov     eax, eax
0x18000303f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003043  xor     [rbp+var_10], rax
0x180003047  call    cs:__imp_QueryPerformanceCounter
0x18000304d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003050  lea     rcx, [rbp+var_10]
0x180003054  shl     rax, 20h
0x180003058  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000305c  xor     rax, [rbp+var_10]
0x180003060  xor     rax, rcx
0x180003063  mov     rcx, 0FFFFFFFFFFFFh
0x18000306d  and     rax, rcx
0x180003070  mov     rcx, 2B992DDFA233h
0x18000307a  cmp     rax, rbx
0x18000307d  cmovz   rax, rcx
0x180003081  mov     cs:__security_cookie, rax
0x180003088  mov     rbx, [rsp+30h+arg_10]
0x18000308d  not     rax
0x180003090  mov     cs:__security_cookie_complement, rax
0x180003097  add     rsp, 30h
0x18000309b  pop     rbp
0x18000309c  retn
```
