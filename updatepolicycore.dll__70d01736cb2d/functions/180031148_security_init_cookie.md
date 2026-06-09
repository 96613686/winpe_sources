# __security_init_cookie

- ea: `0x180031148`
- end: `0x1800311ff`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030c70`

## callees

- `0x180031148`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003118d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003118d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800311a9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800311a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003117f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003117f`

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
0x180031148  mov     [rsp-8+arg_10], rbx
0x18003114d  push    rbp
0x18003114e  mov     rbp, rsp
0x180031151  sub     rsp, 30h
0x180031155  mov     rax, cs:__security_cookie
0x18003115c  mov     rbx, 2B992DDFA232h
0x180031166  cmp     rax, rbx
0x180031169  jnz     short loc_1800311EA
0x18003116b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003116f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180031177  mov     qword ptr [rbp+PerformanceCount], 0
0x18003117f  call    cs:__imp_GetSystemTimeAsFileTime
0x180031185  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180031189  mov     [rbp+var_10], rax
0x18003118d  call    cs:__imp_GetCurrentThreadId
0x180031193  mov     eax, eax
0x180031195  xor     [rbp+var_10], rax
0x180031199  call    cs:__imp_GetCurrentProcessId
0x18003119f  mov     eax, eax
0x1800311a1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800311a5  xor     [rbp+var_10], rax
0x1800311a9  call    cs:__imp_QueryPerformanceCounter
0x1800311af  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800311b2  lea     rcx, [rbp+var_10]
0x1800311b6  shl     rax, 20h
0x1800311ba  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800311be  xor     rax, [rbp+var_10]
0x1800311c2  xor     rax, rcx
0x1800311c5  mov     rcx, 0FFFFFFFFFFFFh
0x1800311cf  and     rax, rcx
0x1800311d2  mov     rcx, 2B992DDFA233h
0x1800311dc  cmp     rax, rbx
0x1800311df  cmovz   rax, rcx
0x1800311e3  mov     cs:__security_cookie, rax
0x1800311ea  mov     rbx, [rsp+30h+arg_10]
0x1800311ef  not     rax
0x1800311f2  mov     cs:__security_cookie_complement, rax
0x1800311f9  add     rsp, 30h
0x1800311fd  pop     rbp
0x1800311fe  retn
```
