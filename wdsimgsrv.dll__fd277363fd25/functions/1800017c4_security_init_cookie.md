# __security_init_cookie

- ea: `0x1800017c4`
- end: `0x18000189d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001370`

## callees

- `0x1800017c4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001813`
- `KERNEL32!GetCurrentThreadId` at `0x180001813`
- `KERNEL32!QueryPerformanceCounter` at `0x18000184a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000184a`
- `KERNEL32!GetCurrentProcessId` at `0x180001807`
- `KERNEL32!GetCurrentProcessId` at `0x180001807`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800017f9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800017f9`
- `KERNEL32!GetTickCount` at `0x18000181f`
- `KERNEL32!GetTickCount` at `0x18000182f`
- `KERNEL32!GetTickCount` at `0x18000181f`
- `KERNEL32!GetTickCount` at `0x18000182f`

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
0x1800017c4  mov     [rsp-8+arg_18], rbx
0x1800017c9  push    rbp
0x1800017ca  mov     rbp, rsp
0x1800017cd  sub     rsp, 20h
0x1800017d1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800017d6  mov     rbx, 2B992DDFA232h
0x1800017e0  and     qword ptr [rbp+PerformanceCount], 0
0x1800017e5  mov     rax, cs:__security_cookie
0x1800017ec  cmp     rax, rbx
0x1800017ef  jnz     loc_180001888
0x1800017f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800017f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001803  mov     [rbp+arg_0], rax
0x180001807  call    cs:__imp_GetCurrentProcessId
0x18000180d  mov     eax, eax
0x18000180f  xor     [rbp+arg_0], rax
0x180001813  call    cs:__imp_GetCurrentThreadId
0x180001819  mov     eax, eax
0x18000181b  xor     [rbp+arg_0], rax
0x18000181f  call    cs:__imp_GetTickCount
0x180001825  mov     eax, eax
0x180001827  shl     rax, 18h
0x18000182b  xor     [rbp+arg_0], rax
0x18000182f  call    cs:__imp_GetTickCount
0x180001835  mov     eax, eax
0x180001837  lea     rcx, [rbp+arg_0]
0x18000183b  xor     rax, [rbp+arg_0]
0x18000183f  xor     rax, rcx
0x180001842  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001846  mov     [rbp+arg_0], rax
0x18000184a  call    cs:__imp_QueryPerformanceCounter
0x180001850  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001853  mov     rcx, 0FFFFFFFFFFFFh
0x18000185d  shl     rax, 20h
0x180001861  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001865  xor     rax, [rbp+arg_0]
0x180001869  and     rax, rcx
0x18000186c  mov     rcx, rax
0x18000186f  cmp     rax, rbx
0x180001872  jnz     short loc_180001881
0x180001874  mov     rax, 2B992DDFA233h
0x18000187e  mov     rcx, rax
0x180001881  mov     cs:__security_cookie, rcx
0x180001888  mov     rbx, [rsp+20h+arg_18]
0x18000188d  not     rax
0x180001890  mov     cs:__security_cookie_complement, rax
0x180001897  add     rsp, 20h
0x18000189b  pop     rbp
0x18000189c  retn
```
