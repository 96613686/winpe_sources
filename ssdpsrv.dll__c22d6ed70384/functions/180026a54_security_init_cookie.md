# __security_init_cookie

- ea: `0x180026a54`
- end: `0x180026b09`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800269e0`

## callees

- `0x180026a54`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026ab3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026aa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026a89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026a89`

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
0x180026a54  mov     [rsp-8+arg_10], rbx
0x180026a59  push    rbp
0x180026a5a  mov     rbp, rsp
0x180026a5d  sub     rsp, 30h
0x180026a61  mov     rax, cs:__security_cookie
0x180026a68  mov     rbx, 2B992DDFA232h
0x180026a72  cmp     rax, rbx
0x180026a75  jnz     short loc_180026AF4
0x180026a77  xor     eax, eax
0x180026a79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026a7d  mov     [rbp+var_10], rax
0x180026a81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180026a85  mov     qword ptr [rbp+PerformanceCount], rax
0x180026a89  call    cs:__imp_GetSystemTimeAsFileTime
0x180026a8f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180026a93  mov     [rbp+var_10], rax
0x180026a97  call    cs:__imp_GetCurrentThreadId
0x180026a9d  mov     eax, eax
0x180026a9f  xor     [rbp+var_10], rax
0x180026aa3  call    cs:__imp_GetCurrentProcessId
0x180026aa9  mov     eax, eax
0x180026aab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026aaf  xor     [rbp+var_10], rax
0x180026ab3  call    cs:__imp_QueryPerformanceCounter
0x180026ab9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180026abc  lea     rcx, [rbp+var_10]
0x180026ac0  shl     rax, 20h
0x180026ac4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180026ac8  xor     rax, [rbp+var_10]
0x180026acc  xor     rax, rcx
0x180026acf  mov     rcx, 0FFFFFFFFFFFFh
0x180026ad9  and     rax, rcx
0x180026adc  mov     rcx, 2B992DDFA233h
0x180026ae6  cmp     rax, rbx
0x180026ae9  cmovz   rax, rcx
0x180026aed  mov     cs:__security_cookie, rax
0x180026af4  mov     rbx, [rsp+30h+arg_10]
0x180026af9  not     rax
0x180026afc  mov     cs:__security_cookie_complement, rax
0x180026b03  add     rsp, 30h
0x180026b07  pop     rbp
0x180026b08  retn
```
