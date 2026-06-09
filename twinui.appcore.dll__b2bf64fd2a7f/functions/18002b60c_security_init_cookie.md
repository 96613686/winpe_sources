# __security_init_cookie

- ea: `0x18002b60c`
- end: `0x18002b6c1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b160`

## callees

- `0x18002b60c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b64f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b64f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b65b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b66b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b66b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b641`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b641`

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
0x18002b60c  mov     [rsp-8+arg_10], rbx
0x18002b611  push    rbp
0x18002b612  mov     rbp, rsp
0x18002b615  sub     rsp, 30h
0x18002b619  mov     rax, cs:__security_cookie
0x18002b620  mov     rbx, 2B992DDFA232h
0x18002b62a  cmp     rax, rbx
0x18002b62d  jnz     short loc_18002B6AC
0x18002b62f  xor     eax, eax
0x18002b631  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002b635  mov     [rbp+var_10], rax
0x18002b639  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002b63d  mov     qword ptr [rbp+PerformanceCount], rax
0x18002b641  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b647  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002b64b  mov     [rbp+var_10], rax
0x18002b64f  call    cs:__imp_GetCurrentThreadId
0x18002b655  mov     eax, eax
0x18002b657  xor     [rbp+var_10], rax
0x18002b65b  call    cs:__imp_GetCurrentProcessId
0x18002b661  mov     eax, eax
0x18002b663  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002b667  xor     [rbp+var_10], rax
0x18002b66b  call    cs:__imp_QueryPerformanceCounter
0x18002b671  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002b674  lea     rcx, [rbp+var_10]
0x18002b678  shl     rax, 20h
0x18002b67c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002b680  xor     rax, [rbp+var_10]
0x18002b684  xor     rax, rcx
0x18002b687  mov     rcx, 0FFFFFFFFFFFFh
0x18002b691  and     rax, rcx
0x18002b694  mov     rcx, 2B992DDFA233h
0x18002b69e  cmp     rax, rbx
0x18002b6a1  cmovz   rax, rcx
0x18002b6a5  mov     cs:__security_cookie, rax
0x18002b6ac  mov     rbx, [rsp+30h+arg_10]
0x18002b6b1  not     rax
0x18002b6b4  mov     cs:__security_cookie_complement, rax
0x18002b6bb  add     rsp, 30h
0x18002b6bf  pop     rbp
0x18002b6c0  retn
```
