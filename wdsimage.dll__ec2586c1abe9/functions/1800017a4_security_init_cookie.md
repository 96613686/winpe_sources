# __security_init_cookie

- ea: `0x1800017a4`
- end: `0x18000187d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001320`

## callees

- `0x1800017a4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000182a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000182a`
- `KERNEL32!GetCurrentThreadId` at `0x1800017f3`
- `KERNEL32!GetCurrentThreadId` at `0x1800017f3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800017d9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800017d9`
- `KERNEL32!GetTickCount` at `0x1800017ff`
- `KERNEL32!GetTickCount` at `0x18000180f`
- `KERNEL32!GetTickCount` at `0x1800017ff`
- `KERNEL32!GetTickCount` at `0x18000180f`
- `KERNEL32!GetCurrentProcessId` at `0x1800017e7`
- `KERNEL32!GetCurrentProcessId` at `0x1800017e7`

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
0x1800017a4  mov     [rsp-8+arg_18], rbx
0x1800017a9  push    rbp
0x1800017aa  mov     rbp, rsp
0x1800017ad  sub     rsp, 20h
0x1800017b1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800017b6  mov     rbx, 2B992DDFA232h
0x1800017c0  and     qword ptr [rbp+PerformanceCount], 0
0x1800017c5  mov     rax, cs:__security_cookie
0x1800017cc  cmp     rax, rbx
0x1800017cf  jnz     loc_180001868
0x1800017d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800017d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800017e3  mov     [rbp+arg_0], rax
0x1800017e7  call    cs:__imp_GetCurrentProcessId
0x1800017ed  mov     eax, eax
0x1800017ef  xor     [rbp+arg_0], rax
0x1800017f3  call    cs:__imp_GetCurrentThreadId
0x1800017f9  mov     eax, eax
0x1800017fb  xor     [rbp+arg_0], rax
0x1800017ff  call    cs:__imp_GetTickCount
0x180001805  mov     eax, eax
0x180001807  shl     rax, 18h
0x18000180b  xor     [rbp+arg_0], rax
0x18000180f  call    cs:__imp_GetTickCount
0x180001815  mov     eax, eax
0x180001817  lea     rcx, [rbp+arg_0]
0x18000181b  xor     rax, [rbp+arg_0]
0x18000181f  xor     rax, rcx
0x180001822  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001826  mov     [rbp+arg_0], rax
0x18000182a  call    cs:__imp_QueryPerformanceCounter
0x180001830  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001833  mov     rcx, 0FFFFFFFFFFFFh
0x18000183d  shl     rax, 20h
0x180001841  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001845  xor     rax, [rbp+arg_0]
0x180001849  and     rax, rcx
0x18000184c  mov     rcx, rax
0x18000184f  cmp     rax, rbx
0x180001852  jnz     short loc_180001861
0x180001854  mov     rax, 2B992DDFA233h
0x18000185e  mov     rcx, rax
0x180001861  mov     cs:__security_cookie, rcx
0x180001868  mov     rbx, [rsp+20h+arg_18]
0x18000186d  not     rax
0x180001870  mov     cs:__security_cookie_complement, rax
0x180001877  add     rsp, 20h
0x18000187b  pop     rbp
0x18000187c  retn
```
