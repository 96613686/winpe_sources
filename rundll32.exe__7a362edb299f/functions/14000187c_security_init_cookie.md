# __security_init_cookie

- ea: `0x14000187c`
- end: `0x140001931`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001570`

## callees

- `0x14000187c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400018b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400018b1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018db`

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
0x14000187c  mov     [rsp-8+arg_10], rbx
0x140001881  push    rbp
0x140001882  mov     rbp, rsp
0x140001885  sub     rsp, 30h
0x140001889  mov     rax, cs:__security_cookie
0x140001890  mov     rbx, 2B992DDFA232h
0x14000189a  cmp     rax, rbx
0x14000189d  jnz     short loc_14000191C
0x14000189f  xor     eax, eax
0x1400018a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400018a5  mov     [rbp+var_10], rax
0x1400018a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400018ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1400018b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400018b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400018bb  mov     [rbp+var_10], rax
0x1400018bf  call    cs:__imp_GetCurrentThreadId
0x1400018c5  mov     eax, eax
0x1400018c7  xor     [rbp+var_10], rax
0x1400018cb  call    cs:__imp_GetCurrentProcessId
0x1400018d1  mov     eax, eax
0x1400018d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400018d7  xor     [rbp+var_10], rax
0x1400018db  call    cs:__imp_QueryPerformanceCounter
0x1400018e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400018e4  lea     rcx, [rbp+var_10]
0x1400018e8  shl     rax, 20h
0x1400018ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400018f0  xor     rax, [rbp+var_10]
0x1400018f4  xor     rax, rcx
0x1400018f7  mov     rcx, 0FFFFFFFFFFFFh
0x140001901  and     rax, rcx
0x140001904  mov     rcx, 2B992DDFA233h
0x14000190e  cmp     rax, rbx
0x140001911  cmovz   rax, rcx
0x140001915  mov     cs:__security_cookie, rax
0x14000191c  mov     rbx, [rsp+30h+arg_10]
0x140001921  not     rax
0x140001924  mov     cs:__security_cookie_complement, rax
0x14000192b  add     rsp, 30h
0x14000192f  pop     rbp
0x140001930  retn
```
