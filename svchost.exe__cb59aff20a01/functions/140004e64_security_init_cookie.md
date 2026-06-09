# __security_init_cookie

- ea: `0x140004e64`
- end: `0x140004f19`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004ba0`

## callees

- `0x140004e64`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004ec3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004ec3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004eb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004eb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ea7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140004e99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140004e99`

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
0x140004e64  mov     [rsp-8+arg_10], rbx
0x140004e69  push    rbp
0x140004e6a  mov     rbp, rsp
0x140004e6d  sub     rsp, 30h
0x140004e71  mov     rax, cs:__security_cookie
0x140004e78  mov     rbx, 2B992DDFA232h
0x140004e82  cmp     rax, rbx
0x140004e85  jnz     short loc_140004F04
0x140004e87  xor     eax, eax
0x140004e89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140004e8d  mov     [rbp+var_10], rax
0x140004e91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140004e95  mov     qword ptr [rbp+PerformanceCount], rax
0x140004e99  call    cs:__imp_GetSystemTimeAsFileTime
0x140004e9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140004ea3  mov     [rbp+var_10], rax
0x140004ea7  call    cs:__imp_GetCurrentThreadId
0x140004ead  mov     eax, eax
0x140004eaf  xor     [rbp+var_10], rax
0x140004eb3  call    cs:__imp_GetCurrentProcessId
0x140004eb9  mov     eax, eax
0x140004ebb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140004ebf  xor     [rbp+var_10], rax
0x140004ec3  call    cs:__imp_QueryPerformanceCounter
0x140004ec9  mov     eax, dword ptr [rbp+PerformanceCount]
0x140004ecc  lea     rcx, [rbp+var_10]
0x140004ed0  shl     rax, 20h
0x140004ed4  xor     rax, qword ptr [rbp+PerformanceCount]
0x140004ed8  xor     rax, [rbp+var_10]
0x140004edc  xor     rax, rcx
0x140004edf  mov     rcx, 0FFFFFFFFFFFFh
0x140004ee9  and     rax, rcx
0x140004eec  mov     rcx, 2B992DDFA233h
0x140004ef6  cmp     rax, rbx
0x140004ef9  cmovz   rax, rcx
0x140004efd  mov     cs:__security_cookie, rax
0x140004f04  mov     rbx, [rsp+30h+arg_10]
0x140004f09  not     rax
0x140004f0c  mov     cs:__security_cookie_complement, rax
0x140004f13  add     rsp, 30h
0x140004f17  pop     rbp
0x140004f18  retn
```
