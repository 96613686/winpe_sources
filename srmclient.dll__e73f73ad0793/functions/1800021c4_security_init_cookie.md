# __security_init_cookie

- ea: `0x1800021c4`
- end: `0x1800022a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800016e0`

## callees

- `0x1800021c4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000224e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000224e`
- `KERNEL32!GetCurrentProcessId` at `0x18000220b`
- `KERNEL32!GetCurrentProcessId` at `0x18000220b`
- `KERNEL32!GetCurrentThreadId` at `0x180002217`
- `KERNEL32!GetCurrentThreadId` at `0x180002217`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800021fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800021fd`
- `KERNEL32!GetTickCount` at `0x180002223`
- `KERNEL32!GetTickCount` at `0x180002233`
- `KERNEL32!GetTickCount` at `0x180002223`
- `KERNEL32!GetTickCount` at `0x180002233`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x1800021c4  mov     [rsp-8+arg_18], rbx
0x1800021c9  push    rbp
0x1800021ca  mov     rbp, rsp
0x1800021cd  sub     rsp, 20h
0x1800021d1  xor     eax, eax
0x1800021d3  mov     rbx, 2B992DDFA232h
0x1800021dd  mov     [rbp+arg_0], rax
0x1800021e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800021e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800021e9  mov     rax, cs:__security_cookie
0x1800021f0  cmp     rax, rbx
0x1800021f3  jnz     loc_18000228C
0x1800021f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800021fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002203  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002207  mov     [rbp+arg_0], rax
0x18000220b  call    cs:__imp_GetCurrentProcessId
0x180002211  mov     eax, eax
0x180002213  xor     [rbp+arg_0], rax
0x180002217  call    cs:__imp_GetCurrentThreadId
0x18000221d  mov     eax, eax
0x18000221f  xor     [rbp+arg_0], rax
0x180002223  call    cs:__imp_GetTickCount
0x180002229  mov     eax, eax
0x18000222b  shl     rax, 18h
0x18000222f  xor     [rbp+arg_0], rax
0x180002233  call    cs:__imp_GetTickCount
0x180002239  mov     eax, eax
0x18000223b  lea     rcx, [rbp+arg_0]
0x18000223f  xor     rax, [rbp+arg_0]
0x180002243  xor     rax, rcx
0x180002246  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000224a  mov     [rbp+arg_0], rax
0x18000224e  call    cs:__imp_QueryPerformanceCounter
0x180002254  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002257  mov     rcx, 0FFFFFFFFFFFFh
0x180002261  shl     rax, 20h
0x180002265  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002269  xor     rax, [rbp+arg_0]
0x18000226d  and     rax, rcx
0x180002270  mov     rcx, rax
0x180002273  cmp     rax, rbx
0x180002276  jnz     short loc_180002285
0x180002278  mov     rax, 2B992DDFA233h
0x180002282  mov     rcx, rax
0x180002285  mov     cs:__security_cookie, rcx
0x18000228c  mov     rbx, [rsp+20h+arg_18]
0x180002291  not     rax
0x180002294  mov     cs:__security_cookie_complement, rax
0x18000229b  add     rsp, 20h
0x18000229f  pop     rbp
0x1800022a0  retn
```
