# __security_init_cookie

- ea: `0x140001600`
- end: `0x1400016b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x140001600`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000165f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000165f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000164f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000164f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001635`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001635`

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
0x140001600  mov     [rsp-8+arg_10], rbx
0x140001605  push    rbp
0x140001606  mov     rbp, rsp
0x140001609  sub     rsp, 30h
0x14000160d  mov     rax, cs:__security_cookie
0x140001614  mov     rbx, 2B992DDFA232h
0x14000161e  cmp     rax, rbx
0x140001621  jnz     short loc_1400016A0
0x140001623  xor     eax, eax
0x140001625  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001629  mov     [rbp+var_10], rax
0x14000162d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001631  mov     qword ptr [rbp+PerformanceCount], rax
0x140001635  call    cs:__imp_GetSystemTimeAsFileTime
0x14000163b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000163f  mov     [rbp+var_10], rax
0x140001643  call    cs:__imp_GetCurrentThreadId
0x140001649  mov     eax, eax
0x14000164b  xor     [rbp+var_10], rax
0x14000164f  call    cs:__imp_GetCurrentProcessId
0x140001655  mov     eax, eax
0x140001657  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000165b  xor     [rbp+var_10], rax
0x14000165f  call    cs:__imp_QueryPerformanceCounter
0x140001665  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001668  lea     rcx, [rbp+var_10]
0x14000166c  shl     rax, 20h
0x140001670  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001674  xor     rax, [rbp+var_10]
0x140001678  xor     rax, rcx
0x14000167b  mov     rcx, 0FFFFFFFFFFFFh
0x140001685  and     rax, rcx
0x140001688  mov     rcx, 2B992DDFA233h
0x140001692  cmp     rax, rbx
0x140001695  cmovz   rax, rcx
0x140001699  mov     cs:__security_cookie, rax
0x1400016a0  mov     rbx, [rsp+30h+arg_10]
0x1400016a5  not     rax
0x1400016a8  mov     cs:__security_cookie_complement, rax
0x1400016af  add     rsp, 30h
0x1400016b3  pop     rbp
0x1400016b4  retn
```
