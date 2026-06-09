# __security_init_cookie

- ea: `0x18000ddb8`
- end: `0x18000de6d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d960`

## callees

- `0x18000ddb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000de17`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000de17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dded`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dded`

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
0x18000ddb8  mov     [rsp-8+arg_10], rbx
0x18000ddbd  push    rbp
0x18000ddbe  mov     rbp, rsp
0x18000ddc1  sub     rsp, 30h
0x18000ddc5  mov     rax, cs:__security_cookie
0x18000ddcc  mov     rbx, 2B992DDFA232h
0x18000ddd6  cmp     rax, rbx
0x18000ddd9  jnz     short loc_18000DE58
0x18000dddb  xor     eax, eax
0x18000dddd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000dde1  mov     [rbp+var_10], rax
0x18000dde5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000dde9  mov     qword ptr [rbp+PerformanceCount], rax
0x18000dded  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ddf3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000ddf7  mov     [rbp+var_10], rax
0x18000ddfb  call    cs:__imp_GetCurrentThreadId
0x18000de01  mov     eax, eax
0x18000de03  xor     [rbp+var_10], rax
0x18000de07  call    cs:__imp_GetCurrentProcessId
0x18000de0d  mov     eax, eax
0x18000de0f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000de13  xor     [rbp+var_10], rax
0x18000de17  call    cs:__imp_QueryPerformanceCounter
0x18000de1d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000de20  lea     rcx, [rbp+var_10]
0x18000de24  shl     rax, 20h
0x18000de28  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000de2c  xor     rax, [rbp+var_10]
0x18000de30  xor     rax, rcx
0x18000de33  mov     rcx, 0FFFFFFFFFFFFh
0x18000de3d  and     rax, rcx
0x18000de40  mov     rcx, 2B992DDFA233h
0x18000de4a  cmp     rax, rbx
0x18000de4d  cmovz   rax, rcx
0x18000de51  mov     cs:__security_cookie, rax
0x18000de58  mov     rbx, [rsp+30h+arg_10]
0x18000de5d  not     rax
0x18000de60  mov     cs:__security_cookie_complement, rax
0x18000de67  add     rsp, 30h
0x18000de6b  pop     rbp
0x18000de6c  retn
```
