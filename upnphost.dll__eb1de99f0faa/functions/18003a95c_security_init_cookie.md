# __security_init_cookie

- ea: `0x18003a95c`
- end: `0x18003aa11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a510`

## callees

- `0x18003a95c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a9ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a9ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003a9bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003a9bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a991`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a991`

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
0x18003a95c  mov     [rsp-8+arg_10], rbx
0x18003a961  push    rbp
0x18003a962  mov     rbp, rsp
0x18003a965  sub     rsp, 30h
0x18003a969  mov     rax, cs:__security_cookie
0x18003a970  mov     rbx, 2B992DDFA232h
0x18003a97a  cmp     rax, rbx
0x18003a97d  jnz     short loc_18003A9FC
0x18003a97f  xor     eax, eax
0x18003a981  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003a985  mov     [rbp+var_10], rax
0x18003a989  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003a98d  mov     qword ptr [rbp+PerformanceCount], rax
0x18003a991  call    cs:__imp_GetSystemTimeAsFileTime
0x18003a997  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003a99b  mov     [rbp+var_10], rax
0x18003a99f  call    cs:__imp_GetCurrentThreadId
0x18003a9a5  mov     eax, eax
0x18003a9a7  xor     [rbp+var_10], rax
0x18003a9ab  call    cs:__imp_GetCurrentProcessId
0x18003a9b1  mov     eax, eax
0x18003a9b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003a9b7  xor     [rbp+var_10], rax
0x18003a9bb  call    cs:__imp_QueryPerformanceCounter
0x18003a9c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003a9c4  lea     rcx, [rbp+var_10]
0x18003a9c8  shl     rax, 20h
0x18003a9cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003a9d0  xor     rax, [rbp+var_10]
0x18003a9d4  xor     rax, rcx
0x18003a9d7  mov     rcx, 0FFFFFFFFFFFFh
0x18003a9e1  and     rax, rcx
0x18003a9e4  mov     rcx, 2B992DDFA233h
0x18003a9ee  cmp     rax, rbx
0x18003a9f1  cmovz   rax, rcx
0x18003a9f5  mov     cs:__security_cookie, rax
0x18003a9fc  mov     rbx, [rsp+30h+arg_10]
0x18003aa01  not     rax
0x18003aa04  mov     cs:__security_cookie_complement, rax
0x18003aa0b  add     rsp, 30h
0x18003aa0f  pop     rbp
0x18003aa10  retn
```
