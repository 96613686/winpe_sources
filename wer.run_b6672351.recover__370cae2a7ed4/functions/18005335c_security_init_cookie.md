# __security_init_cookie

- ea: `0x18005335c`
- end: `0x180053411`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800532b0`

## callees

- `0x18005335c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005339f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005339f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800533ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800533ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800533bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800533bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180053391`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180053391`

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
0x18005335c  mov     [rsp-8+arg_10], rbx
0x180053361  push    rbp
0x180053362  mov     rbp, rsp
0x180053365  sub     rsp, 30h
0x180053369  mov     rax, cs:__security_cookie
0x180053370  mov     rbx, 2B992DDFA232h
0x18005337a  cmp     rax, rbx
0x18005337d  jnz     short loc_1800533FC
0x18005337f  xor     eax, eax
0x180053381  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180053385  mov     [rbp+var_10], rax
0x180053389  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005338d  mov     qword ptr [rbp+PerformanceCount], rax
0x180053391  call    cs:__imp_GetSystemTimeAsFileTime
0x180053397  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005339b  mov     [rbp+var_10], rax
0x18005339f  call    cs:__imp_GetCurrentThreadId
0x1800533a5  mov     eax, eax
0x1800533a7  xor     [rbp+var_10], rax
0x1800533ab  call    cs:__imp_GetCurrentProcessId
0x1800533b1  mov     eax, eax
0x1800533b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800533b7  xor     [rbp+var_10], rax
0x1800533bb  call    cs:__imp_QueryPerformanceCounter
0x1800533c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800533c4  lea     rcx, [rbp+var_10]
0x1800533c8  shl     rax, 20h
0x1800533cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800533d0  xor     rax, [rbp+var_10]
0x1800533d4  xor     rax, rcx
0x1800533d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800533e1  and     rax, rcx
0x1800533e4  mov     rcx, 2B992DDFA233h
0x1800533ee  cmp     rax, rbx
0x1800533f1  cmovz   rax, rcx
0x1800533f5  mov     cs:__security_cookie, rax
0x1800533fc  mov     rbx, [rsp+30h+arg_10]
0x180053401  not     rax
0x180053404  mov     cs:__security_cookie_complement, rax
0x18005340b  add     rsp, 30h
0x18005340f  pop     rbp
0x180053410  retn
```
