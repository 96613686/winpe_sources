# __security_init_cookie

- ea: `0x1800dead4`
- end: `0x1800deb8b`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800de4a0`

## callees

- `0x1800dead4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800deb19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800deb19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800deb25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800deb25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800deb0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800deb0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800deb35`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800deb35`

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
0x1800dead4  mov     [rsp-8+arg_10], rbx
0x1800dead9  push    rbp
0x1800deada  mov     rbp, rsp
0x1800deadd  sub     rsp, 30h
0x1800deae1  mov     rax, cs:__security_cookie
0x1800deae8  mov     rbx, 2B992DDFA232h
0x1800deaf2  cmp     rax, rbx
0x1800deaf5  jnz     short loc_1800DEB76
0x1800deaf7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800deafb  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800deb03  mov     qword ptr [rbp+PerformanceCount], 0
0x1800deb0b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800deb11  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800deb15  mov     [rbp+var_10], rax
0x1800deb19  call    cs:__imp_GetCurrentThreadId
0x1800deb1f  mov     eax, eax
0x1800deb21  xor     [rbp+var_10], rax
0x1800deb25  call    cs:__imp_GetCurrentProcessId
0x1800deb2b  mov     eax, eax
0x1800deb2d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800deb31  xor     [rbp+var_10], rax
0x1800deb35  call    cs:__imp_QueryPerformanceCounter
0x1800deb3b  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800deb3e  lea     rcx, [rbp+var_10]
0x1800deb42  shl     rax, 20h
0x1800deb46  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800deb4a  xor     rax, [rbp+var_10]
0x1800deb4e  xor     rax, rcx
0x1800deb51  mov     rcx, 0FFFFFFFFFFFFh
0x1800deb5b  and     rax, rcx
0x1800deb5e  mov     rcx, 2B992DDFA233h
0x1800deb68  cmp     rax, rbx
0x1800deb6b  cmovz   rax, rcx
0x1800deb6f  mov     cs:__security_cookie, rax
0x1800deb76  mov     rbx, [rsp+30h+arg_10]
0x1800deb7b  not     rax
0x1800deb7e  mov     cs:__security_cookie_complement, rax
0x1800deb85  add     rsp, 30h
0x1800deb89  pop     rbp
0x1800deb8a  retn
```
