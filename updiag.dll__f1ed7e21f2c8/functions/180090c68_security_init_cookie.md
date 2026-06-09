# __security_init_cookie

- ea: `0x180090c68`
- end: `0x180090d1f`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800907e0`

## callees

- `0x180090c68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180090cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180090cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090cad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180090cc9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180090cc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090c9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090c9f`

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
0x180090c68  mov     [rsp-8+arg_10], rbx
0x180090c6d  push    rbp
0x180090c6e  mov     rbp, rsp
0x180090c71  sub     rsp, 30h
0x180090c75  mov     rax, cs:__security_cookie
0x180090c7c  mov     rbx, 2B992DDFA232h
0x180090c86  cmp     rax, rbx
0x180090c89  jnz     short loc_180090D0A
0x180090c8b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180090c8f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180090c97  mov     qword ptr [rbp+PerformanceCount], 0
0x180090c9f  call    cs:__imp_GetSystemTimeAsFileTime
0x180090ca5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180090ca9  mov     [rbp+var_10], rax
0x180090cad  call    cs:__imp_GetCurrentThreadId
0x180090cb3  mov     eax, eax
0x180090cb5  xor     [rbp+var_10], rax
0x180090cb9  call    cs:__imp_GetCurrentProcessId
0x180090cbf  mov     eax, eax
0x180090cc1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180090cc5  xor     [rbp+var_10], rax
0x180090cc9  call    cs:__imp_QueryPerformanceCounter
0x180090ccf  mov     eax, dword ptr [rbp+PerformanceCount]
0x180090cd2  lea     rcx, [rbp+var_10]
0x180090cd6  shl     rax, 20h
0x180090cda  xor     rax, qword ptr [rbp+PerformanceCount]
0x180090cde  xor     rax, [rbp+var_10]
0x180090ce2  xor     rax, rcx
0x180090ce5  mov     rcx, 0FFFFFFFFFFFFh
0x180090cef  and     rax, rcx
0x180090cf2  mov     rcx, 2B992DDFA233h
0x180090cfc  cmp     rax, rbx
0x180090cff  cmovz   rax, rcx
0x180090d03  mov     cs:__security_cookie, rax
0x180090d0a  mov     rbx, [rsp+30h+arg_10]
0x180090d0f  not     rax
0x180090d12  mov     cs:__security_cookie_complement, rax
0x180090d19  add     rsp, 30h
0x180090d1d  pop     rbp
0x180090d1e  retn
```
