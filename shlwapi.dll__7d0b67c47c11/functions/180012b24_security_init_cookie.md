# __security_init_cookie

- ea: `0x180012b24`
- end: `0x180012bd9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012500`

## callees

- `0x180012b24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012b73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012b73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012b59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012b59`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012b83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012b83`

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
0x180012b24  mov     [rsp-8+arg_10], rbx
0x180012b29  push    rbp
0x180012b2a  mov     rbp, rsp
0x180012b2d  sub     rsp, 30h
0x180012b31  mov     rax, cs:__security_cookie
0x180012b38  mov     rbx, 2B992DDFA232h
0x180012b42  cmp     rax, rbx
0x180012b45  jnz     short loc_180012BC4
0x180012b47  xor     eax, eax
0x180012b49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012b4d  mov     [rbp+var_10], rax
0x180012b51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180012b55  mov     qword ptr [rbp+PerformanceCount], rax
0x180012b59  call    cs:__imp_GetSystemTimeAsFileTime
0x180012b5f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180012b63  mov     [rbp+var_10], rax
0x180012b67  call    cs:__imp_GetCurrentThreadId
0x180012b6d  mov     eax, eax
0x180012b6f  xor     [rbp+var_10], rax
0x180012b73  call    cs:__imp_GetCurrentProcessId
0x180012b79  mov     eax, eax
0x180012b7b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012b7f  xor     [rbp+var_10], rax
0x180012b83  call    cs:__imp_QueryPerformanceCounter
0x180012b89  mov     eax, dword ptr [rbp+PerformanceCount]
0x180012b8c  lea     rcx, [rbp+var_10]
0x180012b90  shl     rax, 20h
0x180012b94  xor     rax, qword ptr [rbp+PerformanceCount]
0x180012b98  xor     rax, [rbp+var_10]
0x180012b9c  xor     rax, rcx
0x180012b9f  mov     rcx, 0FFFFFFFFFFFFh
0x180012ba9  and     rax, rcx
0x180012bac  mov     rcx, 2B992DDFA233h
0x180012bb6  cmp     rax, rbx
0x180012bb9  cmovz   rax, rcx
0x180012bbd  mov     cs:__security_cookie, rax
0x180012bc4  mov     rbx, [rsp+30h+arg_10]
0x180012bc9  not     rax
0x180012bcc  mov     cs:__security_cookie_complement, rax
0x180012bd3  add     rsp, 30h
0x180012bd7  pop     rbp
0x180012bd8  retn
```
