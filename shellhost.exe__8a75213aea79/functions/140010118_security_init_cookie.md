# __security_init_cookie

- ea: `0x140010118`
- end: `0x1400101cd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f7b0`

## callees

- `0x140010118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001015b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001015b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010167`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010177`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010177`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001014d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001014d`

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
0x140010118  mov     [rsp-8+arg_10], rbx
0x14001011d  push    rbp
0x14001011e  mov     rbp, rsp
0x140010121  sub     rsp, 30h
0x140010125  mov     rax, cs:__security_cookie
0x14001012c  mov     rbx, 2B992DDFA232h
0x140010136  cmp     rax, rbx
0x140010139  jnz     short loc_1400101B8
0x14001013b  xor     eax, eax
0x14001013d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140010141  mov     [rbp+var_10], rax
0x140010145  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140010149  mov     qword ptr [rbp+PerformanceCount], rax
0x14001014d  call    cs:__imp_GetSystemTimeAsFileTime
0x140010153  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140010157  mov     [rbp+var_10], rax
0x14001015b  call    cs:__imp_GetCurrentThreadId
0x140010161  mov     eax, eax
0x140010163  xor     [rbp+var_10], rax
0x140010167  call    cs:__imp_GetCurrentProcessId
0x14001016d  mov     eax, eax
0x14001016f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140010173  xor     [rbp+var_10], rax
0x140010177  call    cs:__imp_QueryPerformanceCounter
0x14001017d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140010180  lea     rcx, [rbp+var_10]
0x140010184  shl     rax, 20h
0x140010188  xor     rax, qword ptr [rbp+PerformanceCount]
0x14001018c  xor     rax, [rbp+var_10]
0x140010190  xor     rax, rcx
0x140010193  mov     rcx, 0FFFFFFFFFFFFh
0x14001019d  and     rax, rcx
0x1400101a0  mov     rcx, 2B992DDFA233h
0x1400101aa  cmp     rax, rbx
0x1400101ad  cmovz   rax, rcx
0x1400101b1  mov     cs:__security_cookie, rax
0x1400101b8  mov     rbx, [rsp+30h+arg_10]
0x1400101bd  not     rax
0x1400101c0  mov     cs:__security_cookie_complement, rax
0x1400101c7  add     rsp, 30h
0x1400101cb  pop     rbp
0x1400101cc  retn
```
