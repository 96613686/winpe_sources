# __security_init_cookie

- ea: `0x1800027c4`
- end: `0x1800028a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f60`

## callees

- `0x1800027c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000280b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000280b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002817`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002833`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002833`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000284e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000284e`

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
0x1800027c4  mov     [rsp-8+arg_18], rbx
0x1800027c9  push    rbp
0x1800027ca  mov     rbp, rsp
0x1800027cd  sub     rsp, 20h
0x1800027d1  xor     eax, eax
0x1800027d3  mov     rbx, 2B992DDFA232h
0x1800027dd  mov     [rbp+arg_0], rax
0x1800027e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800027e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800027e9  mov     rax, cs:__security_cookie
0x1800027f0  cmp     rax, rbx
0x1800027f3  jnz     loc_18000288C
0x1800027f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002803  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002807  mov     [rbp+arg_0], rax
0x18000280b  call    cs:__imp_GetCurrentProcessId
0x180002811  mov     eax, eax
0x180002813  xor     [rbp+arg_0], rax
0x180002817  call    cs:__imp_GetCurrentThreadId
0x18000281d  mov     eax, eax
0x18000281f  xor     [rbp+arg_0], rax
0x180002823  call    cs:__imp_GetTickCount
0x180002829  mov     eax, eax
0x18000282b  shl     rax, 18h
0x18000282f  xor     [rbp+arg_0], rax
0x180002833  call    cs:__imp_GetTickCount
0x180002839  mov     eax, eax
0x18000283b  lea     rcx, [rbp+arg_0]
0x18000283f  xor     rax, [rbp+arg_0]
0x180002843  xor     rax, rcx
0x180002846  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000284a  mov     [rbp+arg_0], rax
0x18000284e  call    cs:__imp_QueryPerformanceCounter
0x180002854  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002857  mov     rcx, 0FFFFFFFFFFFFh
0x180002861  shl     rax, 20h
0x180002865  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002869  xor     rax, [rbp+arg_0]
0x18000286d  and     rax, rcx
0x180002870  mov     rcx, rax
0x180002873  cmp     rax, rbx
0x180002876  jnz     short loc_180002885
0x180002878  mov     rax, 2B992DDFA233h
0x180002882  mov     rcx, rax
0x180002885  mov     cs:__security_cookie, rcx
0x18000288c  mov     rbx, [rsp+20h+arg_18]
0x180002891  not     rax
0x180002894  mov     cs:__security_cookie_complement, rax
0x18000289b  add     rsp, 20h
0x18000289f  pop     rbp
0x1800028a0  retn
```
