# __security_init_cookie

- ea: `0x140132d74`
- end: `0x140132e29`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140132930`

## callees

- `0x140132d74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140132dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140132dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140132db7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140132db7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140132da9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140132da9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140132dd3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140132dd3`

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
0x140132d74  mov     [rsp-8+arg_10], rbx
0x140132d79  push    rbp
0x140132d7a  mov     rbp, rsp
0x140132d7d  sub     rsp, 30h
0x140132d81  mov     rax, cs:__security_cookie
0x140132d88  mov     rbx, 2B992DDFA232h
0x140132d92  cmp     rax, rbx
0x140132d95  jnz     short loc_140132E14
0x140132d97  xor     eax, eax
0x140132d99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140132d9d  mov     [rbp+var_10], rax
0x140132da1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140132da5  mov     qword ptr [rbp+PerformanceCount], rax
0x140132da9  call    cs:__imp_GetSystemTimeAsFileTime
0x140132daf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140132db3  mov     [rbp+var_10], rax
0x140132db7  call    cs:__imp_GetCurrentThreadId
0x140132dbd  mov     eax, eax
0x140132dbf  xor     [rbp+var_10], rax
0x140132dc3  call    cs:__imp_GetCurrentProcessId
0x140132dc9  mov     eax, eax
0x140132dcb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140132dcf  xor     [rbp+var_10], rax
0x140132dd3  call    cs:__imp_QueryPerformanceCounter
0x140132dd9  mov     eax, dword ptr [rbp+PerformanceCount]
0x140132ddc  lea     rcx, [rbp+var_10]
0x140132de0  shl     rax, 20h
0x140132de4  xor     rax, qword ptr [rbp+PerformanceCount]
0x140132de8  xor     rax, [rbp+var_10]
0x140132dec  xor     rax, rcx
0x140132def  mov     rcx, 0FFFFFFFFFFFFh
0x140132df9  and     rax, rcx
0x140132dfc  mov     rcx, 2B992DDFA233h
0x140132e06  cmp     rax, rbx
0x140132e09  cmovz   rax, rcx
0x140132e0d  mov     cs:__security_cookie, rax
0x140132e14  mov     rbx, [rsp+30h+arg_10]
0x140132e19  not     rax
0x140132e1c  mov     cs:__security_cookie_complement, rax
0x140132e23  add     rsp, 30h
0x140132e27  pop     rbp
0x140132e28  retn
```
