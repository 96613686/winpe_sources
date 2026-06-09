# __security_init_cookie

- ea: `0x1800017b4`
- end: `0x180001891`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001280`

## callees

- `0x1800017b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001807`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000183e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000183e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001823`

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
0x1800017b4  mov     [rsp-8+arg_18], rbx
0x1800017b9  push    rbp
0x1800017ba  mov     rbp, rsp
0x1800017bd  sub     rsp, 20h
0x1800017c1  xor     eax, eax
0x1800017c3  mov     rbx, 2B992DDFA232h
0x1800017cd  mov     [rbp+arg_0], rax
0x1800017d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800017d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800017d9  mov     rax, cs:__security_cookie
0x1800017e0  cmp     rax, rbx
0x1800017e3  jnz     loc_18000187C
0x1800017e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800017ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800017f7  mov     [rbp+arg_0], rax
0x1800017fb  call    cs:__imp_GetCurrentProcessId
0x180001801  mov     eax, eax
0x180001803  xor     [rbp+arg_0], rax
0x180001807  call    cs:__imp_GetCurrentThreadId
0x18000180d  mov     eax, eax
0x18000180f  xor     [rbp+arg_0], rax
0x180001813  call    cs:__imp_GetTickCount
0x180001819  mov     eax, eax
0x18000181b  shl     rax, 18h
0x18000181f  xor     [rbp+arg_0], rax
0x180001823  call    cs:__imp_GetTickCount
0x180001829  mov     eax, eax
0x18000182b  lea     rcx, [rbp+arg_0]
0x18000182f  xor     rax, [rbp+arg_0]
0x180001833  xor     rax, rcx
0x180001836  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000183a  mov     [rbp+arg_0], rax
0x18000183e  call    cs:__imp_QueryPerformanceCounter
0x180001844  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001847  mov     rcx, 0FFFFFFFFFFFFh
0x180001851  shl     rax, 20h
0x180001855  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001859  xor     rax, [rbp+arg_0]
0x18000185d  and     rax, rcx
0x180001860  mov     rcx, rax
0x180001863  cmp     rax, rbx
0x180001866  jnz     short loc_180001875
0x180001868  mov     rax, 2B992DDFA233h
0x180001872  mov     rcx, rax
0x180001875  mov     cs:__security_cookie, rcx
0x18000187c  mov     rbx, [rsp+20h+arg_18]
0x180001881  not     rax
0x180001884  mov     cs:__security_cookie_complement, rax
0x18000188b  add     rsp, 20h
0x18000188f  pop     rbp
0x180001890  retn
```
