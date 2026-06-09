# __security_init_cookie

- ea: `0x180002294`
- end: `0x18000236d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d60`

## callees

- `0x180002294`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800022ef`
- `KERNEL32!GetTickCount` at `0x1800022ff`
- `KERNEL32!GetTickCount` at `0x1800022ef`
- `KERNEL32!GetTickCount` at `0x1800022ff`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800022c9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800022c9`
- `KERNEL32!QueryPerformanceCounter` at `0x18000231a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000231a`
- `KERNEL32!GetCurrentProcessId` at `0x1800022d7`
- `KERNEL32!GetCurrentProcessId` at `0x1800022d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800022e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800022e3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180002294  mov     [rsp-8+arg_18], rbx
0x180002299  push    rbp
0x18000229a  mov     rbp, rsp
0x18000229d  sub     rsp, 20h
0x1800022a1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800022a6  mov     rbx, 2B992DDFA232h
0x1800022b0  and     qword ptr [rbp+PerformanceCount], 0
0x1800022b5  mov     rax, cs:__security_cookie
0x1800022bc  cmp     rax, rbx
0x1800022bf  jnz     loc_180002358
0x1800022c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800022c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800022cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800022d3  mov     [rbp+arg_0], rax
0x1800022d7  call    cs:__imp_GetCurrentProcessId
0x1800022dd  mov     eax, eax
0x1800022df  xor     [rbp+arg_0], rax
0x1800022e3  call    cs:__imp_GetCurrentThreadId
0x1800022e9  mov     eax, eax
0x1800022eb  xor     [rbp+arg_0], rax
0x1800022ef  call    cs:__imp_GetTickCount
0x1800022f5  mov     eax, eax
0x1800022f7  shl     rax, 18h
0x1800022fb  xor     [rbp+arg_0], rax
0x1800022ff  call    cs:__imp_GetTickCount
0x180002305  mov     eax, eax
0x180002307  lea     rcx, [rbp+arg_0]
0x18000230b  xor     rax, [rbp+arg_0]
0x18000230f  xor     rax, rcx
0x180002312  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002316  mov     [rbp+arg_0], rax
0x18000231a  call    cs:__imp_QueryPerformanceCounter
0x180002320  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002323  mov     rcx, 0FFFFFFFFFFFFh
0x18000232d  shl     rax, 20h
0x180002331  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002335  xor     rax, [rbp+arg_0]
0x180002339  and     rax, rcx
0x18000233c  mov     rcx, rax
0x18000233f  cmp     rax, rbx
0x180002342  jnz     short loc_180002351
0x180002344  mov     rax, 2B992DDFA233h
0x18000234e  mov     rcx, rax
0x180002351  mov     cs:__security_cookie, rcx
0x180002358  mov     rbx, [rsp+20h+arg_18]
0x18000235d  not     rax
0x180002360  mov     cs:__security_cookie_complement, rax
0x180002367  add     rsp, 20h
0x18000236b  pop     rbp
0x18000236c  retn
```
