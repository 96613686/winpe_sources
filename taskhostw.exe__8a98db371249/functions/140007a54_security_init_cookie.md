# __security_init_cookie

- ea: `0x140007a54`
- end: `0x140007b31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007830`

## callees

- `0x140007a54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007a9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140007ade`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140007ade`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140007a8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140007a8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140007ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140007ac3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140007ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140007ac3`

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
0x140007a54  mov     [rsp-8+arg_18], rbx
0x140007a59  push    rbp
0x140007a5a  mov     rbp, rsp
0x140007a5d  sub     rsp, 20h
0x140007a61  xor     eax, eax
0x140007a63  mov     rbx, 2B992DDFA232h
0x140007a6d  mov     [rbp+arg_0], rax
0x140007a71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140007a75  mov     qword ptr [rbp+PerformanceCount], rax
0x140007a79  mov     rax, cs:__security_cookie
0x140007a80  cmp     rax, rbx
0x140007a83  jnz     loc_140007B1C
0x140007a89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140007a8d  call    cs:__imp_GetSystemTimeAsFileTime
0x140007a93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140007a97  mov     [rbp+arg_0], rax
0x140007a9b  call    cs:__imp_GetCurrentProcessId
0x140007aa1  mov     eax, eax
0x140007aa3  xor     [rbp+arg_0], rax
0x140007aa7  call    cs:__imp_GetCurrentThreadId
0x140007aad  mov     eax, eax
0x140007aaf  xor     [rbp+arg_0], rax
0x140007ab3  call    cs:__imp_GetTickCount
0x140007ab9  mov     eax, eax
0x140007abb  shl     rax, 18h
0x140007abf  xor     [rbp+arg_0], rax
0x140007ac3  call    cs:__imp_GetTickCount
0x140007ac9  mov     eax, eax
0x140007acb  lea     rcx, [rbp+arg_0]
0x140007acf  xor     rax, [rbp+arg_0]
0x140007ad3  xor     rax, rcx
0x140007ad6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140007ada  mov     [rbp+arg_0], rax
0x140007ade  call    cs:__imp_QueryPerformanceCounter
0x140007ae4  mov     eax, dword ptr [rbp+PerformanceCount]
0x140007ae7  mov     rcx, 0FFFFFFFFFFFFh
0x140007af1  shl     rax, 20h
0x140007af5  xor     rax, qword ptr [rbp+PerformanceCount]
0x140007af9  xor     rax, [rbp+arg_0]
0x140007afd  and     rax, rcx
0x140007b00  mov     rcx, rax
0x140007b03  cmp     rax, rbx
0x140007b06  jnz     short loc_140007B15
0x140007b08  mov     rax, 2B992DDFA233h
0x140007b12  mov     rcx, rax
0x140007b15  mov     cs:__security_cookie, rcx
0x140007b1c  mov     rbx, [rsp+20h+arg_18]
0x140007b21  not     rax
0x140007b24  mov     cs:__security_cookie_complement, rax
0x140007b2b  add     rsp, 20h
0x140007b2f  pop     rbp
0x140007b30  retn
```
