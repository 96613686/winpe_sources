# __security_init_cookie

- ea: `0x18015d33c`
- end: `0x18015d3f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18015cab0`

## callees

- `0x18015d33c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18015d38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18015d38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015d37f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015d37f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18015d39b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18015d39b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18015d371`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18015d371`

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
0x18015d33c  mov     [rsp-8+arg_10], rbx
0x18015d341  push    rbp
0x18015d342  mov     rbp, rsp
0x18015d345  sub     rsp, 30h
0x18015d349  mov     rax, cs:__security_cookie
0x18015d350  mov     rbx, 2B992DDFA232h
0x18015d35a  cmp     rax, rbx
0x18015d35d  jnz     short loc_18015D3DC
0x18015d35f  xor     eax, eax
0x18015d361  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18015d365  mov     [rbp+var_10], rax
0x18015d369  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18015d36d  mov     qword ptr [rbp+PerformanceCount], rax
0x18015d371  call    cs:__imp_GetSystemTimeAsFileTime
0x18015d377  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18015d37b  mov     [rbp+var_10], rax
0x18015d37f  call    cs:__imp_GetCurrentThreadId
0x18015d385  mov     eax, eax
0x18015d387  xor     [rbp+var_10], rax
0x18015d38b  call    cs:__imp_GetCurrentProcessId
0x18015d391  mov     eax, eax
0x18015d393  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18015d397  xor     [rbp+var_10], rax
0x18015d39b  call    cs:__imp_QueryPerformanceCounter
0x18015d3a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18015d3a4  lea     rcx, [rbp+var_10]
0x18015d3a8  shl     rax, 20h
0x18015d3ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x18015d3b0  xor     rax, [rbp+var_10]
0x18015d3b4  xor     rax, rcx
0x18015d3b7  mov     rcx, 0FFFFFFFFFFFFh
0x18015d3c1  and     rax, rcx
0x18015d3c4  mov     rcx, 2B992DDFA233h
0x18015d3ce  cmp     rax, rbx
0x18015d3d1  cmovz   rax, rcx
0x18015d3d5  mov     cs:__security_cookie, rax
0x18015d3dc  mov     rbx, [rsp+30h+arg_10]
0x18015d3e1  not     rax
0x18015d3e4  mov     cs:__security_cookie_complement, rax
0x18015d3eb  add     rsp, 30h
0x18015d3ef  pop     rbp
0x18015d3f0  retn
```
