# __security_init_cookie

- ea: `0x180001424`
- end: `0x1800014d9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013b0`

## callees

- `0x180001424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001467`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001483`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001483`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001459`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001459`

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
0x180001424  mov     [rsp-8+arg_10], rbx
0x180001429  push    rbp
0x18000142a  mov     rbp, rsp
0x18000142d  sub     rsp, 30h
0x180001431  mov     rax, cs:__security_cookie
0x180001438  mov     rbx, 2B992DDFA232h
0x180001442  cmp     rax, rbx
0x180001445  jnz     short loc_1800014C4
0x180001447  xor     eax, eax
0x180001449  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000144d  mov     [rbp+var_10], rax
0x180001451  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001455  mov     qword ptr [rbp+PerformanceCount], rax
0x180001459  call    cs:__imp_GetSystemTimeAsFileTime
0x18000145f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001463  mov     [rbp+var_10], rax
0x180001467  call    cs:__imp_GetCurrentThreadId
0x18000146d  mov     eax, eax
0x18000146f  xor     [rbp+var_10], rax
0x180001473  call    cs:__imp_GetCurrentProcessId
0x180001479  mov     eax, eax
0x18000147b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000147f  xor     [rbp+var_10], rax
0x180001483  call    cs:__imp_QueryPerformanceCounter
0x180001489  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000148c  lea     rcx, [rbp+var_10]
0x180001490  shl     rax, 20h
0x180001494  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001498  xor     rax, [rbp+var_10]
0x18000149c  xor     rax, rcx
0x18000149f  mov     rcx, 0FFFFFFFFFFFFh
0x1800014a9  and     rax, rcx
0x1800014ac  mov     rcx, 2B992DDFA233h
0x1800014b6  cmp     rax, rbx
0x1800014b9  cmovz   rax, rcx
0x1800014bd  mov     cs:__security_cookie, rax
0x1800014c4  mov     rbx, [rsp+30h+arg_10]
0x1800014c9  not     rax
0x1800014cc  mov     cs:__security_cookie_complement, rax
0x1800014d3  add     rsp, 30h
0x1800014d7  pop     rbp
0x1800014d8  retn
```
