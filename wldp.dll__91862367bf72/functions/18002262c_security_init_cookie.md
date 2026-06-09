# __security_init_cookie

- ea: `0x18002262c`
- end: `0x1800226e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021e70`

## callees

- `0x18002262c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002266f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002266f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002267b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002267b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022661`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022661`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002268b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002268b`

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
0x18002262c  mov     [rsp-8+arg_10], rbx
0x180022631  push    rbp
0x180022632  mov     rbp, rsp
0x180022635  sub     rsp, 30h
0x180022639  mov     rax, cs:__security_cookie
0x180022640  mov     rbx, 2B992DDFA232h
0x18002264a  cmp     rax, rbx
0x18002264d  jnz     short loc_1800226CC
0x18002264f  xor     eax, eax
0x180022651  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022655  mov     [rbp+var_10], rax
0x180022659  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002265d  mov     qword ptr [rbp+PerformanceCount], rax
0x180022661  call    cs:__imp_GetSystemTimeAsFileTime
0x180022667  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002266b  mov     [rbp+var_10], rax
0x18002266f  call    cs:__imp_GetCurrentThreadId
0x180022675  mov     eax, eax
0x180022677  xor     [rbp+var_10], rax
0x18002267b  call    cs:__imp_GetCurrentProcessId
0x180022681  mov     eax, eax
0x180022683  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180022687  xor     [rbp+var_10], rax
0x18002268b  call    cs:__imp_QueryPerformanceCounter
0x180022691  mov     eax, dword ptr [rbp+PerformanceCount]
0x180022694  lea     rcx, [rbp+var_10]
0x180022698  shl     rax, 20h
0x18002269c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800226a0  xor     rax, [rbp+var_10]
0x1800226a4  xor     rax, rcx
0x1800226a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800226b1  and     rax, rcx
0x1800226b4  mov     rcx, 2B992DDFA233h
0x1800226be  cmp     rax, rbx
0x1800226c1  cmovz   rax, rcx
0x1800226c5  mov     cs:__security_cookie, rax
0x1800226cc  mov     rbx, [rsp+30h+arg_10]
0x1800226d1  not     rax
0x1800226d4  mov     cs:__security_cookie_complement, rax
0x1800226db  add     rsp, 30h
0x1800226df  pop     rbp
0x1800226e0  retn
```
