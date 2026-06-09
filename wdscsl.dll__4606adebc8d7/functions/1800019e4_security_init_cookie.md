# __security_init_cookie

- ea: `0x1800019e4`
- end: `0x180001abd`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001570`

## callees

- `0x1800019e4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001a3f`
- `KERNEL32!GetTickCount` at `0x180001a4f`
- `KERNEL32!GetTickCount` at `0x180001a3f`
- `KERNEL32!GetTickCount` at `0x180001a4f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a19`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a19`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a6a`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a6a`
- `KERNEL32!GetCurrentThreadId` at `0x180001a33`
- `KERNEL32!GetCurrentThreadId` at `0x180001a33`
- `KERNEL32!GetCurrentProcessId` at `0x180001a27`
- `KERNEL32!GetCurrentProcessId` at `0x180001a27`

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
0x1800019e4  mov     [rsp-8+arg_18], rbx
0x1800019e9  push    rbp
0x1800019ea  mov     rbp, rsp
0x1800019ed  sub     rsp, 20h
0x1800019f1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800019f6  mov     rbx, 2B992DDFA232h
0x180001a00  and     qword ptr [rbp+PerformanceCount], 0
0x180001a05  mov     rax, cs:__security_cookie
0x180001a0c  cmp     rax, rbx
0x180001a0f  jnz     loc_180001AA8
0x180001a15  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a19  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a1f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a23  mov     [rbp+arg_0], rax
0x180001a27  call    cs:__imp_GetCurrentProcessId
0x180001a2d  mov     eax, eax
0x180001a2f  xor     [rbp+arg_0], rax
0x180001a33  call    cs:__imp_GetCurrentThreadId
0x180001a39  mov     eax, eax
0x180001a3b  xor     [rbp+arg_0], rax
0x180001a3f  call    cs:__imp_GetTickCount
0x180001a45  mov     eax, eax
0x180001a47  shl     rax, 18h
0x180001a4b  xor     [rbp+arg_0], rax
0x180001a4f  call    cs:__imp_GetTickCount
0x180001a55  mov     eax, eax
0x180001a57  lea     rcx, [rbp+arg_0]
0x180001a5b  xor     rax, [rbp+arg_0]
0x180001a5f  xor     rax, rcx
0x180001a62  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a66  mov     [rbp+arg_0], rax
0x180001a6a  call    cs:__imp_QueryPerformanceCounter
0x180001a70  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a73  mov     rcx, 0FFFFFFFFFFFFh
0x180001a7d  shl     rax, 20h
0x180001a81  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a85  xor     rax, [rbp+arg_0]
0x180001a89  and     rax, rcx
0x180001a8c  mov     rcx, rax
0x180001a8f  cmp     rax, rbx
0x180001a92  jnz     short loc_180001AA1
0x180001a94  mov     rax, 2B992DDFA233h
0x180001a9e  mov     rcx, rax
0x180001aa1  mov     cs:__security_cookie, rcx
0x180001aa8  mov     rbx, [rsp+20h+arg_18]
0x180001aad  not     rax
0x180001ab0  mov     cs:__security_cookie_complement, rax
0x180001ab7  add     rsp, 20h
0x180001abb  pop     rbp
0x180001abc  retn
```
