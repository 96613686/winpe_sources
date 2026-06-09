# __security_init_cookie

- ea: `0x18003aab0`
- end: `0x18003ab65`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a360`

## callees

- `0x18003aab0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003aaff`
- `KERNEL32!GetCurrentProcessId` at `0x18003aaff`
- `KERNEL32!GetCurrentThreadId` at `0x18003aaf3`
- `KERNEL32!GetCurrentThreadId` at `0x18003aaf3`
- `KERNEL32!QueryPerformanceCounter` at `0x18003ab0f`
- `KERNEL32!QueryPerformanceCounter` at `0x18003ab0f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003aae5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003aae5`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x18003aab0  mov     [rsp-8+arg_10], rbx
0x18003aab5  push    rbp
0x18003aab6  mov     rbp, rsp
0x18003aab9  sub     rsp, 30h
0x18003aabd  mov     rax, cs:__security_cookie
0x18003aac4  mov     rbx, 2B992DDFA232h
0x18003aace  cmp     rax, rbx
0x18003aad1  jnz     short loc_18003AB50
0x18003aad3  xor     eax, eax
0x18003aad5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003aad9  mov     [rbp+var_10], rax
0x18003aadd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003aae1  mov     qword ptr [rbp+PerformanceCount], rax
0x18003aae5  call    cs:__imp_GetSystemTimeAsFileTime
0x18003aaeb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003aaef  mov     [rbp+var_10], rax
0x18003aaf3  call    cs:__imp_GetCurrentThreadId
0x18003aaf9  mov     eax, eax
0x18003aafb  xor     [rbp+var_10], rax
0x18003aaff  call    cs:__imp_GetCurrentProcessId
0x18003ab05  mov     eax, eax
0x18003ab07  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003ab0b  xor     [rbp+var_10], rax
0x18003ab0f  call    cs:__imp_QueryPerformanceCounter
0x18003ab15  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003ab18  lea     rcx, [rbp+var_10]
0x18003ab1c  shl     rax, 20h
0x18003ab20  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003ab24  xor     rax, [rbp+var_10]
0x18003ab28  xor     rax, rcx
0x18003ab2b  mov     rcx, 0FFFFFFFFFFFFh
0x18003ab35  and     rax, rcx
0x18003ab38  mov     rcx, 2B992DDFA233h
0x18003ab42  cmp     rax, rbx
0x18003ab45  cmovz   rax, rcx
0x18003ab49  mov     cs:__security_cookie, rax
0x18003ab50  mov     rbx, [rsp+30h+arg_10]
0x18003ab55  not     rax
0x18003ab58  mov     cs:__security_cookie_complement, rax
0x18003ab5f  add     rsp, 30h
0x18003ab63  pop     rbp
0x18003ab64  retn
```
