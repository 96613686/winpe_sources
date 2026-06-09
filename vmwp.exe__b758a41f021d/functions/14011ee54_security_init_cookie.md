# __security_init_cookie

- ea: `0x14011ee54`
- end: `0x14011ef09`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14011ea10`

## callees

- `0x14011ee54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14011ee97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14011ee97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14011eea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14011eea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14011ee89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14011ee89`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14011eeb3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14011eeb3`

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
0x14011ee54  mov     [rsp-8+arg_10], rbx
0x14011ee59  push    rbp
0x14011ee5a  mov     rbp, rsp
0x14011ee5d  sub     rsp, 30h
0x14011ee61  mov     rax, cs:__security_cookie
0x14011ee68  mov     rbx, 2B992DDFA232h
0x14011ee72  cmp     rax, rbx
0x14011ee75  jnz     short loc_14011EEF4
0x14011ee77  xor     eax, eax
0x14011ee79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14011ee7d  mov     [rbp+var_10], rax
0x14011ee81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14011ee85  mov     qword ptr [rbp+PerformanceCount], rax
0x14011ee89  call    cs:__imp_GetSystemTimeAsFileTime
0x14011ee8f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14011ee93  mov     [rbp+var_10], rax
0x14011ee97  call    cs:__imp_GetCurrentThreadId
0x14011ee9d  mov     eax, eax
0x14011ee9f  xor     [rbp+var_10], rax
0x14011eea3  call    cs:__imp_GetCurrentProcessId
0x14011eea9  mov     eax, eax
0x14011eeab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14011eeaf  xor     [rbp+var_10], rax
0x14011eeb3  call    cs:__imp_QueryPerformanceCounter
0x14011eeb9  mov     eax, dword ptr [rbp+PerformanceCount]
0x14011eebc  lea     rcx, [rbp+var_10]
0x14011eec0  shl     rax, 20h
0x14011eec4  xor     rax, qword ptr [rbp+PerformanceCount]
0x14011eec8  xor     rax, [rbp+var_10]
0x14011eecc  xor     rax, rcx
0x14011eecf  mov     rcx, 0FFFFFFFFFFFFh
0x14011eed9  and     rax, rcx
0x14011eedc  mov     rcx, 2B992DDFA233h
0x14011eee6  cmp     rax, rbx
0x14011eee9  cmovz   rax, rcx
0x14011eeed  mov     cs:__security_cookie, rax
0x14011eef4  mov     rbx, [rsp+30h+arg_10]
0x14011eef9  not     rax
0x14011eefc  mov     cs:__security_cookie_complement, rax
0x14011ef03  add     rsp, 30h
0x14011ef07  pop     rbp
0x14011ef08  retn
```
