# __security_init_cookie

- ea: `0x180008ebc`
- end: `0x180008f71`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180008ebc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008f1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008f1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008ef1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008ef1`

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
0x180008ebc  mov     [rsp-8+arg_10], rbx
0x180008ec1  push    rbp
0x180008ec2  mov     rbp, rsp
0x180008ec5  sub     rsp, 30h
0x180008ec9  mov     rax, cs:__security_cookie
0x180008ed0  mov     rbx, 2B992DDFA232h
0x180008eda  cmp     rax, rbx
0x180008edd  jnz     short loc_180008F5C
0x180008edf  xor     eax, eax
0x180008ee1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008ee5  mov     [rbp+var_10], rax
0x180008ee9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008eed  mov     qword ptr [rbp+PerformanceCount], rax
0x180008ef1  call    cs:__imp_GetSystemTimeAsFileTime
0x180008ef7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008efb  mov     [rbp+var_10], rax
0x180008eff  call    cs:__imp_GetCurrentThreadId
0x180008f05  mov     eax, eax
0x180008f07  xor     [rbp+var_10], rax
0x180008f0b  call    cs:__imp_GetCurrentProcessId
0x180008f11  mov     eax, eax
0x180008f13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008f17  xor     [rbp+var_10], rax
0x180008f1b  call    cs:__imp_QueryPerformanceCounter
0x180008f21  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008f24  lea     rcx, [rbp+var_10]
0x180008f28  shl     rax, 20h
0x180008f2c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008f30  xor     rax, [rbp+var_10]
0x180008f34  xor     rax, rcx
0x180008f37  mov     rcx, 0FFFFFFFFFFFFh
0x180008f41  and     rax, rcx
0x180008f44  mov     rcx, 2B992DDFA233h
0x180008f4e  cmp     rax, rbx
0x180008f51  cmovz   rax, rcx
0x180008f55  mov     cs:__security_cookie, rax
0x180008f5c  mov     rbx, [rsp+30h+arg_10]
0x180008f61  not     rax
0x180008f64  mov     cs:__security_cookie_complement, rax
0x180008f6b  add     rsp, 30h
0x180008f6f  pop     rbp
0x180008f70  retn
```
