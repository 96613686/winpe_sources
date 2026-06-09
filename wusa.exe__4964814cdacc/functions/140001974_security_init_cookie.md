# __security_init_cookie

- ea: `0x140001974`
- end: `0x140001a51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001650`

## callees

- `0x140001974`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400019bb`
- `KERNEL32!GetCurrentProcessId` at `0x1400019bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400019c7`
- `KERNEL32!GetCurrentThreadId` at `0x1400019c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400019fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400019fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400019d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400019e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400019d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400019e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400019ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400019ad`

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
0x140001974  mov     [rsp-8+arg_18], rbx
0x140001979  push    rbp
0x14000197a  mov     rbp, rsp
0x14000197d  sub     rsp, 20h
0x140001981  xor     eax, eax
0x140001983  mov     rbx, 2B992DDFA232h
0x14000198d  mov     [rbp+arg_0], rax
0x140001991  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001995  mov     qword ptr [rbp+PerformanceCount], rax
0x140001999  mov     rax, cs:__security_cookie
0x1400019a0  cmp     rax, rbx
0x1400019a3  jnz     loc_140001A3C
0x1400019a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400019ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1400019b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400019b7  mov     [rbp+arg_0], rax
0x1400019bb  call    cs:__imp_GetCurrentProcessId
0x1400019c1  mov     eax, eax
0x1400019c3  xor     [rbp+arg_0], rax
0x1400019c7  call    cs:__imp_GetCurrentThreadId
0x1400019cd  mov     eax, eax
0x1400019cf  xor     [rbp+arg_0], rax
0x1400019d3  call    cs:__imp_GetTickCount
0x1400019d9  mov     eax, eax
0x1400019db  shl     rax, 18h
0x1400019df  xor     [rbp+arg_0], rax
0x1400019e3  call    cs:__imp_GetTickCount
0x1400019e9  mov     eax, eax
0x1400019eb  lea     rcx, [rbp+arg_0]
0x1400019ef  xor     rax, [rbp+arg_0]
0x1400019f3  xor     rax, rcx
0x1400019f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400019fa  mov     [rbp+arg_0], rax
0x1400019fe  call    cs:__imp_QueryPerformanceCounter
0x140001a04  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001a07  mov     rcx, 0FFFFFFFFFFFFh
0x140001a11  shl     rax, 20h
0x140001a15  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001a19  xor     rax, [rbp+arg_0]
0x140001a1d  and     rax, rcx
0x140001a20  mov     rcx, rax
0x140001a23  cmp     rax, rbx
0x140001a26  jnz     short loc_140001A35
0x140001a28  mov     rax, 2B992DDFA233h
0x140001a32  mov     rcx, rax
0x140001a35  mov     cs:__security_cookie, rcx
0x140001a3c  mov     rbx, [rsp+20h+arg_18]
0x140001a41  not     rax
0x140001a44  mov     cs:__security_cookie_complement, rax
0x140001a4b  add     rsp, 20h
0x140001a4f  pop     rbp
0x140001a50  retn
```
