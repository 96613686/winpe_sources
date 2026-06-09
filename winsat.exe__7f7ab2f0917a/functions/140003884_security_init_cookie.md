# __security_init_cookie

- ea: `0x140003884`
- end: `0x140003961`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f40`

## callees

- `0x140003884`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400038bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400038bd`
- `KERNEL32!GetTickCount` at `0x1400038e3`
- `KERNEL32!GetTickCount` at `0x1400038f3`
- `KERNEL32!GetTickCount` at `0x1400038e3`
- `KERNEL32!GetTickCount` at `0x1400038f3`
- `KERNEL32!GetCurrentThreadId` at `0x1400038d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400038d7`
- `KERNEL32!GetCurrentProcessId` at `0x1400038cb`
- `KERNEL32!GetCurrentProcessId` at `0x1400038cb`
- `KERNEL32!QueryPerformanceCounter` at `0x14000390e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000390e`

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
0x140003884  mov     [rsp-8+arg_18], rbx
0x140003889  push    rbp
0x14000388a  mov     rbp, rsp
0x14000388d  sub     rsp, 20h
0x140003891  xor     eax, eax
0x140003893  mov     rbx, 2B992DDFA232h
0x14000389d  mov     [rbp+arg_0], rax
0x1400038a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400038a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400038a9  mov     rax, cs:__security_cookie
0x1400038b0  cmp     rax, rbx
0x1400038b3  jnz     loc_14000394C
0x1400038b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400038bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400038c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400038c7  mov     [rbp+arg_0], rax
0x1400038cb  call    cs:__imp_GetCurrentProcessId
0x1400038d1  mov     eax, eax
0x1400038d3  xor     [rbp+arg_0], rax
0x1400038d7  call    cs:__imp_GetCurrentThreadId
0x1400038dd  mov     eax, eax
0x1400038df  xor     [rbp+arg_0], rax
0x1400038e3  call    cs:__imp_GetTickCount
0x1400038e9  mov     eax, eax
0x1400038eb  shl     rax, 18h
0x1400038ef  xor     [rbp+arg_0], rax
0x1400038f3  call    cs:__imp_GetTickCount
0x1400038f9  mov     eax, eax
0x1400038fb  lea     rcx, [rbp+arg_0]
0x1400038ff  xor     rax, [rbp+arg_0]
0x140003903  xor     rax, rcx
0x140003906  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000390a  mov     [rbp+arg_0], rax
0x14000390e  call    cs:__imp_QueryPerformanceCounter
0x140003914  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003917  mov     rcx, 0FFFFFFFFFFFFh
0x140003921  shl     rax, 20h
0x140003925  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003929  xor     rax, [rbp+arg_0]
0x14000392d  and     rax, rcx
0x140003930  mov     rcx, rax
0x140003933  cmp     rax, rbx
0x140003936  jnz     short loc_140003945
0x140003938  mov     rax, 2B992DDFA233h
0x140003942  mov     rcx, rax
0x140003945  mov     cs:__security_cookie, rcx
0x14000394c  mov     rbx, [rsp+20h+arg_18]
0x140003951  not     rax
0x140003954  mov     cs:__security_cookie_complement, rax
0x14000395b  add     rsp, 20h
0x14000395f  pop     rbp
0x140003960  retn
```
