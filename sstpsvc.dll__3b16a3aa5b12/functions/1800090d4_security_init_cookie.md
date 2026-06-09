# __security_init_cookie

- ea: `0x1800090d4`
- end: `0x1800091b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x1800090d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000911b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000911b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000915e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000915e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000910d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000910d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009133`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009133`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009143`

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
0x1800090d4  mov     [rsp-8+arg_18], rbx
0x1800090d9  push    rbp
0x1800090da  mov     rbp, rsp
0x1800090dd  sub     rsp, 20h
0x1800090e1  xor     eax, eax
0x1800090e3  mov     rbx, 2B992DDFA232h
0x1800090ed  mov     [rbp+arg_0], rax
0x1800090f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800090f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800090f9  mov     rax, cs:__security_cookie
0x180009100  cmp     rax, rbx
0x180009103  jnz     loc_18000919C
0x180009109  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000910d  call    cs:__imp_GetSystemTimeAsFileTime
0x180009113  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009117  mov     [rbp+arg_0], rax
0x18000911b  call    cs:__imp_GetCurrentProcessId
0x180009121  mov     eax, eax
0x180009123  xor     [rbp+arg_0], rax
0x180009127  call    cs:__imp_GetCurrentThreadId
0x18000912d  mov     eax, eax
0x18000912f  xor     [rbp+arg_0], rax
0x180009133  call    cs:__imp_GetTickCount
0x180009139  mov     eax, eax
0x18000913b  shl     rax, 18h
0x18000913f  xor     [rbp+arg_0], rax
0x180009143  call    cs:__imp_GetTickCount
0x180009149  mov     eax, eax
0x18000914b  lea     rcx, [rbp+arg_0]
0x18000914f  xor     rax, [rbp+arg_0]
0x180009153  xor     rax, rcx
0x180009156  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000915a  mov     [rbp+arg_0], rax
0x18000915e  call    cs:__imp_QueryPerformanceCounter
0x180009164  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009167  mov     rcx, 0FFFFFFFFFFFFh
0x180009171  shl     rax, 20h
0x180009175  xor     rax, qword ptr [rbp+PerformanceCount]
0x180009179  xor     rax, [rbp+arg_0]
0x18000917d  and     rax, rcx
0x180009180  mov     rcx, rax
0x180009183  cmp     rax, rbx
0x180009186  jnz     short loc_180009195
0x180009188  mov     rax, 2B992DDFA233h
0x180009192  mov     rcx, rax
0x180009195  mov     cs:__security_cookie, rcx
0x18000919c  mov     rbx, [rsp+20h+arg_18]
0x1800091a1  not     rax
0x1800091a4  mov     cs:__security_cookie_complement, rax
0x1800091ab  add     rsp, 20h
0x1800091af  pop     rbp
0x1800091b0  retn
```
