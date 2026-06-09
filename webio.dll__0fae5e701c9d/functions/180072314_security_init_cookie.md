# __security_init_cookie

- ea: `0x180072314`
- end: `0x1800723c9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800722a0`

## callees

- `0x180072314`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072373`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180072363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180072363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072349`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072349`

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
0x180072314  mov     [rsp-8+arg_10], rbx
0x180072319  push    rbp
0x18007231a  mov     rbp, rsp
0x18007231d  sub     rsp, 30h
0x180072321  mov     rax, cs:__security_cookie
0x180072328  mov     rbx, 2B992DDFA232h
0x180072332  cmp     rax, rbx
0x180072335  jnz     short loc_1800723B4
0x180072337  xor     eax, eax
0x180072339  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007233d  mov     [rbp+var_10], rax
0x180072341  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180072345  mov     qword ptr [rbp+PerformanceCount], rax
0x180072349  call    cs:__imp_GetSystemTimeAsFileTime
0x18007234f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180072353  mov     [rbp+var_10], rax
0x180072357  call    cs:__imp_GetCurrentThreadId
0x18007235d  mov     eax, eax
0x18007235f  xor     [rbp+var_10], rax
0x180072363  call    cs:__imp_GetCurrentProcessId
0x180072369  mov     eax, eax
0x18007236b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18007236f  xor     [rbp+var_10], rax
0x180072373  call    cs:__imp_QueryPerformanceCounter
0x180072379  mov     eax, dword ptr [rbp+PerformanceCount]
0x18007237c  lea     rcx, [rbp+var_10]
0x180072380  shl     rax, 20h
0x180072384  xor     rax, qword ptr [rbp+PerformanceCount]
0x180072388  xor     rax, [rbp+var_10]
0x18007238c  xor     rax, rcx
0x18007238f  mov     rcx, 0FFFFFFFFFFFFh
0x180072399  and     rax, rcx
0x18007239c  mov     rcx, 2B992DDFA233h
0x1800723a6  cmp     rax, rbx
0x1800723a9  cmovz   rax, rcx
0x1800723ad  mov     cs:__security_cookie, rax
0x1800723b4  mov     rbx, [rsp+30h+arg_10]
0x1800723b9  not     rax
0x1800723bc  mov     cs:__security_cookie_complement, rax
0x1800723c3  add     rsp, 30h
0x1800723c7  pop     rbp
0x1800723c8  retn
```
