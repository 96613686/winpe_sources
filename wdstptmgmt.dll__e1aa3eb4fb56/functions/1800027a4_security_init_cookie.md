# __security_init_cookie

- ea: `0x1800027a4`
- end: `0x18000287d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001da0`

## callees

- `0x1800027a4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000282a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000282a`
- `KERNEL32!GetCurrentProcessId` at `0x1800027e7`
- `KERNEL32!GetCurrentProcessId` at `0x1800027e7`
- `KERNEL32!GetTickCount` at `0x1800027ff`
- `KERNEL32!GetTickCount` at `0x18000280f`
- `KERNEL32!GetTickCount` at `0x1800027ff`
- `KERNEL32!GetTickCount` at `0x18000280f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800027d9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800027d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800027f3`
- `KERNEL32!GetCurrentThreadId` at `0x1800027f3`

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
0x1800027a4  mov     [rsp-8+arg_18], rbx
0x1800027a9  push    rbp
0x1800027aa  mov     rbp, rsp
0x1800027ad  sub     rsp, 20h
0x1800027b1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800027b6  mov     rbx, 2B992DDFA232h
0x1800027c0  and     qword ptr [rbp+PerformanceCount], 0
0x1800027c5  mov     rax, cs:__security_cookie
0x1800027cc  cmp     rax, rbx
0x1800027cf  jnz     loc_180002868
0x1800027d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800027df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800027e3  mov     [rbp+arg_0], rax
0x1800027e7  call    cs:__imp_GetCurrentProcessId
0x1800027ed  mov     eax, eax
0x1800027ef  xor     [rbp+arg_0], rax
0x1800027f3  call    cs:__imp_GetCurrentThreadId
0x1800027f9  mov     eax, eax
0x1800027fb  xor     [rbp+arg_0], rax
0x1800027ff  call    cs:__imp_GetTickCount
0x180002805  mov     eax, eax
0x180002807  shl     rax, 18h
0x18000280b  xor     [rbp+arg_0], rax
0x18000280f  call    cs:__imp_GetTickCount
0x180002815  mov     eax, eax
0x180002817  lea     rcx, [rbp+arg_0]
0x18000281b  xor     rax, [rbp+arg_0]
0x18000281f  xor     rax, rcx
0x180002822  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002826  mov     [rbp+arg_0], rax
0x18000282a  call    cs:__imp_QueryPerformanceCounter
0x180002830  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002833  mov     rcx, 0FFFFFFFFFFFFh
0x18000283d  shl     rax, 20h
0x180002841  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002845  xor     rax, [rbp+arg_0]
0x180002849  and     rax, rcx
0x18000284c  mov     rcx, rax
0x18000284f  cmp     rax, rbx
0x180002852  jnz     short loc_180002861
0x180002854  mov     rax, 2B992DDFA233h
0x18000285e  mov     rcx, rax
0x180002861  mov     cs:__security_cookie, rcx
0x180002868  mov     rbx, [rsp+20h+arg_18]
0x18000286d  not     rax
0x180002870  mov     cs:__security_cookie_complement, rax
0x180002877  add     rsp, 20h
0x18000287b  pop     rbp
0x18000287c  retn
```
