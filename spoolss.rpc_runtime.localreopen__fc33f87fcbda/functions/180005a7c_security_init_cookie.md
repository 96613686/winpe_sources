# __security_init_cookie

- ea: `0x180005a7c`
- end: `0x180005b31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005630`

## callees

- `0x180005a7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005abf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005ab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005ab1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005adb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005adb`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180005a7c  mov     [rsp-8+arg_10], rbx
0x180005a81  push    rbp
0x180005a82  mov     rbp, rsp
0x180005a85  sub     rsp, 30h
0x180005a89  mov     rax, cs:__security_cookie
0x180005a90  mov     rbx, 2B992DDFA232h
0x180005a9a  cmp     rax, rbx
0x180005a9d  jnz     short loc_180005B1C
0x180005a9f  xor     eax, eax
0x180005aa1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005aa5  mov     [rbp+var_10], rax
0x180005aa9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005aad  mov     qword ptr [rbp+PerformanceCount], rax
0x180005ab1  call    cs:__imp_GetSystemTimeAsFileTime
0x180005ab7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005abb  mov     [rbp+var_10], rax
0x180005abf  call    cs:__imp_GetCurrentThreadId
0x180005ac5  mov     eax, eax
0x180005ac7  xor     [rbp+var_10], rax
0x180005acb  call    cs:__imp_GetCurrentProcessId
0x180005ad1  mov     eax, eax
0x180005ad3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005ad7  xor     [rbp+var_10], rax
0x180005adb  call    cs:__imp_QueryPerformanceCounter
0x180005ae1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005ae4  lea     rcx, [rbp+var_10]
0x180005ae8  shl     rax, 20h
0x180005aec  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005af0  xor     rax, [rbp+var_10]
0x180005af4  xor     rax, rcx
0x180005af7  mov     rcx, 0FFFFFFFFFFFFh
0x180005b01  and     rax, rcx
0x180005b04  mov     rcx, 2B992DDFA233h
0x180005b0e  cmp     rax, rbx
0x180005b11  cmovz   rax, rcx
0x180005b15  mov     cs:__security_cookie, rax
0x180005b1c  mov     rbx, [rsp+30h+arg_10]
0x180005b21  not     rax
0x180005b24  mov     cs:__security_cookie_complement, rax
0x180005b2b  add     rsp, 30h
0x180005b2f  pop     rbp
0x180005b30  retn
```
