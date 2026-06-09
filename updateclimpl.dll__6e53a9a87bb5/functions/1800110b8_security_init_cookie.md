# __security_init_cookie

- ea: `0x1800110b8`
- end: `0x18001116f`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010a70`

## callees

- `0x1800110b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800110fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800110fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011119`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011119`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800110ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800110ef`

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
0x1800110b8  mov     [rsp-8+arg_10], rbx
0x1800110bd  push    rbp
0x1800110be  mov     rbp, rsp
0x1800110c1  sub     rsp, 30h
0x1800110c5  mov     rax, cs:__security_cookie
0x1800110cc  mov     rbx, 2B992DDFA232h
0x1800110d6  cmp     rax, rbx
0x1800110d9  jnz     short loc_18001115A
0x1800110db  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800110df  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800110e7  mov     qword ptr [rbp+PerformanceCount], 0
0x1800110ef  call    cs:__imp_GetSystemTimeAsFileTime
0x1800110f5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800110f9  mov     [rbp+var_10], rax
0x1800110fd  call    cs:__imp_GetCurrentThreadId
0x180011103  mov     eax, eax
0x180011105  xor     [rbp+var_10], rax
0x180011109  call    cs:__imp_GetCurrentProcessId
0x18001110f  mov     eax, eax
0x180011111  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180011115  xor     [rbp+var_10], rax
0x180011119  call    cs:__imp_QueryPerformanceCounter
0x18001111f  mov     eax, dword ptr [rbp+PerformanceCount]
0x180011122  lea     rcx, [rbp+var_10]
0x180011126  shl     rax, 20h
0x18001112a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001112e  xor     rax, [rbp+var_10]
0x180011132  xor     rax, rcx
0x180011135  mov     rcx, 0FFFFFFFFFFFFh
0x18001113f  and     rax, rcx
0x180011142  mov     rcx, 2B992DDFA233h
0x18001114c  cmp     rax, rbx
0x18001114f  cmovz   rax, rcx
0x180011153  mov     cs:__security_cookie, rax
0x18001115a  mov     rbx, [rsp+30h+arg_10]
0x18001115f  not     rax
0x180011162  mov     cs:__security_cookie_complement, rax
0x180011169  add     rsp, 30h
0x18001116d  pop     rbp
0x18001116e  retn
```
