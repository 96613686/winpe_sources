# __security_init_cookie

- ea: `0x180008d74`
- end: `0x180008e51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008540`

## callees

- `0x180008d74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008dad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008dad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008de3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008de3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008dfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008dfe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180008d74  mov     [rsp-8+arg_18], rbx
0x180008d79  push    rbp
0x180008d7a  mov     rbp, rsp
0x180008d7d  sub     rsp, 20h
0x180008d81  xor     eax, eax
0x180008d83  mov     rbx, 2B992DDFA232h
0x180008d8d  mov     [rbp+arg_0], rax
0x180008d91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008d95  mov     qword ptr [rbp+PerformanceCount], rax
0x180008d99  mov     rax, cs:__security_cookie
0x180008da0  cmp     rax, rbx
0x180008da3  jnz     loc_180008E3C
0x180008da9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008dad  call    cs:__imp_GetSystemTimeAsFileTime
0x180008db3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008db7  mov     [rbp+arg_0], rax
0x180008dbb  call    cs:__imp_GetCurrentProcessId
0x180008dc1  mov     eax, eax
0x180008dc3  xor     [rbp+arg_0], rax
0x180008dc7  call    cs:__imp_GetCurrentThreadId
0x180008dcd  mov     eax, eax
0x180008dcf  xor     [rbp+arg_0], rax
0x180008dd3  call    cs:__imp_GetTickCount
0x180008dd9  mov     eax, eax
0x180008ddb  shl     rax, 18h
0x180008ddf  xor     [rbp+arg_0], rax
0x180008de3  call    cs:__imp_GetTickCount
0x180008de9  mov     eax, eax
0x180008deb  lea     rcx, [rbp+arg_0]
0x180008def  xor     rax, [rbp+arg_0]
0x180008df3  xor     rax, rcx
0x180008df6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008dfa  mov     [rbp+arg_0], rax
0x180008dfe  call    cs:__imp_QueryPerformanceCounter
0x180008e04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008e07  mov     rcx, 0FFFFFFFFFFFFh
0x180008e11  shl     rax, 20h
0x180008e15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008e19  xor     rax, [rbp+arg_0]
0x180008e1d  and     rax, rcx
0x180008e20  mov     rcx, rax
0x180008e23  cmp     rax, rbx
0x180008e26  jnz     short loc_180008E35
0x180008e28  mov     rax, 2B992DDFA233h
0x180008e32  mov     rcx, rax
0x180008e35  mov     cs:__security_cookie, rcx
0x180008e3c  mov     rbx, [rsp+20h+arg_18]
0x180008e41  not     rax
0x180008e44  mov     cs:__security_cookie_complement, rax
0x180008e4b  add     rsp, 20h
0x180008e4f  pop     rbp
0x180008e50  retn
```
