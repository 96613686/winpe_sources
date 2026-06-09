# __security_init_cookie

- ea: `0x18000ea48`
- end: `0x18000eafd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e5f0`

## callees

- `0x18000ea48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea97`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000eaa7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000eaa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ea7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ea7d`

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
0x18000ea48  mov     [rsp-8+arg_10], rbx
0x18000ea4d  push    rbp
0x18000ea4e  mov     rbp, rsp
0x18000ea51  sub     rsp, 30h
0x18000ea55  mov     rax, cs:__security_cookie
0x18000ea5c  mov     rbx, 2B992DDFA232h
0x18000ea66  cmp     rax, rbx
0x18000ea69  jnz     short loc_18000EAE8
0x18000ea6b  xor     eax, eax
0x18000ea6d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ea71  mov     [rbp+var_10], rax
0x18000ea75  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000ea79  mov     qword ptr [rbp+PerformanceCount], rax
0x18000ea7d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ea83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000ea87  mov     [rbp+var_10], rax
0x18000ea8b  call    cs:__imp_GetCurrentThreadId
0x18000ea91  mov     eax, eax
0x18000ea93  xor     [rbp+var_10], rax
0x18000ea97  call    cs:__imp_GetCurrentProcessId
0x18000ea9d  mov     eax, eax
0x18000ea9f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000eaa3  xor     [rbp+var_10], rax
0x18000eaa7  call    cs:__imp_QueryPerformanceCounter
0x18000eaad  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000eab0  lea     rcx, [rbp+var_10]
0x18000eab4  shl     rax, 20h
0x18000eab8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000eabc  xor     rax, [rbp+var_10]
0x18000eac0  xor     rax, rcx
0x18000eac3  mov     rcx, 0FFFFFFFFFFFFh
0x18000eacd  and     rax, rcx
0x18000ead0  mov     rcx, 2B992DDFA233h
0x18000eada  cmp     rax, rbx
0x18000eadd  cmovz   rax, rcx
0x18000eae1  mov     cs:__security_cookie, rax
0x18000eae8  mov     rbx, [rsp+30h+arg_10]
0x18000eaed  not     rax
0x18000eaf0  mov     cs:__security_cookie_complement, rax
0x18000eaf7  add     rsp, 30h
0x18000eafb  pop     rbp
0x18000eafc  retn
```
