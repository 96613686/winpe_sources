# __security_init_cookie

- ea: `0x14002717c`
- end: `0x140027231`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140026bf0`

## callees

- `0x14002717c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400271bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400271bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400271cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400271cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400271db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400271db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400271b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400271b1`

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
0x14002717c  mov     [rsp-8+arg_10], rbx
0x140027181  push    rbp
0x140027182  mov     rbp, rsp
0x140027185  sub     rsp, 30h
0x140027189  mov     rax, cs:__security_cookie
0x140027190  mov     rbx, 2B992DDFA232h
0x14002719a  cmp     rax, rbx
0x14002719d  jnz     short loc_14002721C
0x14002719f  xor     eax, eax
0x1400271a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400271a5  mov     [rbp+var_10], rax
0x1400271a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400271ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1400271b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400271b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400271bb  mov     [rbp+var_10], rax
0x1400271bf  call    cs:__imp_GetCurrentThreadId
0x1400271c5  mov     eax, eax
0x1400271c7  xor     [rbp+var_10], rax
0x1400271cb  call    cs:__imp_GetCurrentProcessId
0x1400271d1  mov     eax, eax
0x1400271d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400271d7  xor     [rbp+var_10], rax
0x1400271db  call    cs:__imp_QueryPerformanceCounter
0x1400271e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400271e4  lea     rcx, [rbp+var_10]
0x1400271e8  shl     rax, 20h
0x1400271ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400271f0  xor     rax, [rbp+var_10]
0x1400271f4  xor     rax, rcx
0x1400271f7  mov     rcx, 0FFFFFFFFFFFFh
0x140027201  and     rax, rcx
0x140027204  mov     rcx, 2B992DDFA233h
0x14002720e  cmp     rax, rbx
0x140027211  cmovz   rax, rcx
0x140027215  mov     cs:__security_cookie, rax
0x14002721c  mov     rbx, [rsp+30h+arg_10]
0x140027221  not     rax
0x140027224  mov     cs:__security_cookie_complement, rax
0x14002722b  add     rsp, 30h
0x14002722f  pop     rbp
0x140027230  retn
```
