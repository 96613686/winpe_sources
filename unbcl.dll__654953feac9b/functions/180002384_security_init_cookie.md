# __security_init_cookie

- ea: `0x180002384`
- end: `0x180002461`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a80`

## callees

- `0x180002384`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800023cb`
- `KERNEL32!GetCurrentProcessId` at `0x1800023cb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000240e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000240e`
- `KERNEL32!GetTickCount` at `0x1800023e3`
- `KERNEL32!GetTickCount` at `0x1800023f3`
- `KERNEL32!GetTickCount` at `0x1800023e3`
- `KERNEL32!GetTickCount` at `0x1800023f3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800023bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800023bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800023d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800023d7`

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
0x180002384  mov     [rsp-8+arg_18], rbx
0x180002389  push    rbp
0x18000238a  mov     rbp, rsp
0x18000238d  sub     rsp, 20h
0x180002391  xor     eax, eax
0x180002393  mov     rbx, 2B992DDFA232h
0x18000239d  mov     [rbp+arg_0], rax
0x1800023a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800023a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800023a9  mov     rax, cs:__security_cookie
0x1800023b0  cmp     rax, rbx
0x1800023b3  jnz     loc_18000244C
0x1800023b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800023c7  mov     [rbp+arg_0], rax
0x1800023cb  call    cs:__imp_GetCurrentProcessId
0x1800023d1  mov     eax, eax
0x1800023d3  xor     [rbp+arg_0], rax
0x1800023d7  call    cs:__imp_GetCurrentThreadId
0x1800023dd  mov     eax, eax
0x1800023df  xor     [rbp+arg_0], rax
0x1800023e3  call    cs:__imp_GetTickCount
0x1800023e9  mov     eax, eax
0x1800023eb  shl     rax, 18h
0x1800023ef  xor     [rbp+arg_0], rax
0x1800023f3  call    cs:__imp_GetTickCount
0x1800023f9  mov     eax, eax
0x1800023fb  lea     rcx, [rbp+arg_0]
0x1800023ff  xor     rax, [rbp+arg_0]
0x180002403  xor     rax, rcx
0x180002406  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000240a  mov     [rbp+arg_0], rax
0x18000240e  call    cs:__imp_QueryPerformanceCounter
0x180002414  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002417  mov     rcx, 0FFFFFFFFFFFFh
0x180002421  shl     rax, 20h
0x180002425  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002429  xor     rax, [rbp+arg_0]
0x18000242d  and     rax, rcx
0x180002430  mov     rcx, rax
0x180002433  cmp     rax, rbx
0x180002436  jnz     short loc_180002445
0x180002438  mov     rax, 2B992DDFA233h
0x180002442  mov     rcx, rax
0x180002445  mov     cs:__security_cookie, rcx
0x18000244c  mov     rbx, [rsp+20h+arg_18]
0x180002451  not     rax
0x180002454  mov     cs:__security_cookie_complement, rax
0x18000245b  add     rsp, 20h
0x18000245f  pop     rbp
0x180002460  retn
```
