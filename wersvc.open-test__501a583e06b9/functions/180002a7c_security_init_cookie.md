# __security_init_cookie

- ea: `0x180002a7c`
- end: `0x180002b31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002980`

## callees

- `0x180002a7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002abf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002adb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002adb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ab1`

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
0x180002a7c  mov     [rsp-8+arg_10], rbx
0x180002a81  push    rbp
0x180002a82  mov     rbp, rsp
0x180002a85  sub     rsp, 30h
0x180002a89  mov     rax, cs:__security_cookie
0x180002a90  mov     rbx, 2B992DDFA232h
0x180002a9a  cmp     rax, rbx
0x180002a9d  jnz     short loc_180002B1C
0x180002a9f  xor     eax, eax
0x180002aa1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002aa5  mov     [rbp+var_10], rax
0x180002aa9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002aad  mov     qword ptr [rbp+PerformanceCount], rax
0x180002ab1  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ab7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002abb  mov     [rbp+var_10], rax
0x180002abf  call    cs:__imp_GetCurrentThreadId
0x180002ac5  mov     eax, eax
0x180002ac7  xor     [rbp+var_10], rax
0x180002acb  call    cs:__imp_GetCurrentProcessId
0x180002ad1  mov     eax, eax
0x180002ad3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002ad7  xor     [rbp+var_10], rax
0x180002adb  call    cs:__imp_QueryPerformanceCounter
0x180002ae1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ae4  lea     rcx, [rbp+var_10]
0x180002ae8  shl     rax, 20h
0x180002aec  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002af0  xor     rax, [rbp+var_10]
0x180002af4  xor     rax, rcx
0x180002af7  mov     rcx, 0FFFFFFFFFFFFh
0x180002b01  and     rax, rcx
0x180002b04  mov     rcx, 2B992DDFA233h
0x180002b0e  cmp     rax, rbx
0x180002b11  cmovz   rax, rcx
0x180002b15  mov     cs:__security_cookie, rax
0x180002b1c  mov     rbx, [rsp+30h+arg_10]
0x180002b21  not     rax
0x180002b24  mov     cs:__security_cookie_complement, rax
0x180002b2b  add     rsp, 30h
0x180002b2f  pop     rbp
0x180002b30  retn
```
