# __security_init_cookie

- ea: `0x1800019b0`
- end: `0x180001a65`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001580`

## callees

- `0x1800019b0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800019e5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800019e5`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a0f`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a0f`
- `KERNEL32!GetCurrentProcessId` at `0x1800019ff`
- `KERNEL32!GetCurrentProcessId` at `0x1800019ff`
- `KERNEL32!GetCurrentThreadId` at `0x1800019f3`
- `KERNEL32!GetCurrentThreadId` at `0x1800019f3`

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
0x1800019b0  mov     [rsp-8+arg_10], rbx
0x1800019b5  push    rbp
0x1800019b6  mov     rbp, rsp
0x1800019b9  sub     rsp, 30h
0x1800019bd  mov     rax, cs:__security_cookie
0x1800019c4  mov     rbx, 2B992DDFA232h
0x1800019ce  cmp     rax, rbx
0x1800019d1  jnz     short loc_180001A50
0x1800019d3  xor     eax, eax
0x1800019d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019d9  mov     [rbp+var_10], rax
0x1800019dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019ef  mov     [rbp+var_10], rax
0x1800019f3  call    cs:__imp_GetCurrentThreadId
0x1800019f9  mov     eax, eax
0x1800019fb  xor     [rbp+var_10], rax
0x1800019ff  call    cs:__imp_GetCurrentProcessId
0x180001a05  mov     eax, eax
0x180001a07  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a0b  xor     [rbp+var_10], rax
0x180001a0f  call    cs:__imp_QueryPerformanceCounter
0x180001a15  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a18  lea     rcx, [rbp+var_10]
0x180001a1c  shl     rax, 20h
0x180001a20  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a24  xor     rax, [rbp+var_10]
0x180001a28  xor     rax, rcx
0x180001a2b  mov     rcx, 0FFFFFFFFFFFFh
0x180001a35  and     rax, rcx
0x180001a38  mov     rcx, 2B992DDFA233h
0x180001a42  cmp     rax, rbx
0x180001a45  cmovz   rax, rcx
0x180001a49  mov     cs:__security_cookie, rax
0x180001a50  mov     rbx, [rsp+30h+arg_10]
0x180001a55  not     rax
0x180001a58  mov     cs:__security_cookie_complement, rax
0x180001a5f  add     rsp, 30h
0x180001a63  pop     rbp
0x180001a64  retn
```
