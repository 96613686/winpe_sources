# __security_init_cookie

- ea: `0x180001148`
- end: `0x18000121c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001120`

## callees

- `0x180001148`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800011a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800011a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001194`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800011d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800011d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001186`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001186`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001148  mov     [rsp-8+arg_18], rbx
0x18000114d  push    rbp
0x18000114e  mov     rbp, rsp
0x180001151  sub     rsp, 20h
0x180001155  mov     rcx, cs:__security_cookie
0x18000115c  xor     eax, eax
0x18000115e  mov     [rbp+arg_0], rax
0x180001162  mov     rbx, 2B992DDFA232h
0x18000116c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001170  mov     qword ptr [rbp+PerformanceCount], rax
0x180001174  test    rcx, rcx
0x180001177  jz      short loc_180001182
0x180001179  cmp     rcx, rbx
0x18000117c  jnz     loc_180001207
0x180001182  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001186  call    cs:__imp_GetSystemTimeAsFileTime
0x18000118c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001190  mov     [rbp+arg_0], rax
0x180001194  call    cs:__imp_GetCurrentProcessId
0x18000119a  mov     eax, eax
0x18000119c  xor     [rbp+arg_0], rax
0x1800011a0  call    cs:__imp_GetCurrentThreadId
0x1800011a6  mov     eax, eax
0x1800011a8  xor     [rbp+arg_0], rax
0x1800011ac  call    cs:__imp_GetTickCount
0x1800011b2  mov     eax, eax
0x1800011b4  shl     rax, 18h
0x1800011b8  xor     [rbp+arg_0], rax
0x1800011bc  call    cs:__imp_GetTickCount
0x1800011c2  mov     eax, eax
0x1800011c4  lea     rcx, [rbp+arg_0]
0x1800011c8  xor     rax, [rbp+arg_0]
0x1800011cc  xor     rax, rcx
0x1800011cf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800011d3  mov     [rbp+arg_0], rax
0x1800011d7  call    cs:__imp_QueryPerformanceCounter
0x1800011dd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800011e0  mov     rcx, 0FFFFFFFFFFFFh
0x1800011ea  shl     rax, 20h
0x1800011ee  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800011f2  xor     rax, [rbp+arg_0]
0x1800011f6  and     rax, rcx
0x1800011f9  mov     rcx, rbx
0x1800011fc  cmovnz  rcx, rax
0x180001200  mov     cs:__security_cookie, rcx
0x180001207  mov     rbx, [rsp+20h+arg_18]
0x18000120c  not     rcx
0x18000120f  mov     cs:__security_cookie_complement, rcx
0x180001216  add     rsp, 20h
0x18000121a  pop     rbp
0x18000121b  retn
```
