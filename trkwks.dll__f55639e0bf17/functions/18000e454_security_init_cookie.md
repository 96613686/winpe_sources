# __security_init_cookie

- ea: `0x18000e454`
- end: `0x18000e531`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ddb0`

## callees

- `0x18000e454`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e4de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e4de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e48d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e48d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e4c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e4c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e49b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e49b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e4a7`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18000e454  mov     [rsp-8+arg_18], rbx
0x18000e459  push    rbp
0x18000e45a  mov     rbp, rsp
0x18000e45d  sub     rsp, 20h
0x18000e461  xor     eax, eax
0x18000e463  mov     rbx, 2B992DDFA232h
0x18000e46d  mov     [rbp+arg_0], rax
0x18000e471  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000e475  mov     qword ptr [rbp+PerformanceCount], rax
0x18000e479  mov     rax, cs:__security_cookie
0x18000e480  cmp     rax, rbx
0x18000e483  jnz     loc_18000E51C
0x18000e489  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000e48d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e493  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000e497  mov     [rbp+arg_0], rax
0x18000e49b  call    cs:__imp_GetCurrentProcessId
0x18000e4a1  mov     eax, eax
0x18000e4a3  xor     [rbp+arg_0], rax
0x18000e4a7  call    cs:__imp_GetCurrentThreadId
0x18000e4ad  mov     eax, eax
0x18000e4af  xor     [rbp+arg_0], rax
0x18000e4b3  call    cs:__imp_GetTickCount
0x18000e4b9  mov     eax, eax
0x18000e4bb  shl     rax, 18h
0x18000e4bf  xor     [rbp+arg_0], rax
0x18000e4c3  call    cs:__imp_GetTickCount
0x18000e4c9  mov     eax, eax
0x18000e4cb  lea     rcx, [rbp+arg_0]
0x18000e4cf  xor     rax, [rbp+arg_0]
0x18000e4d3  xor     rax, rcx
0x18000e4d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000e4da  mov     [rbp+arg_0], rax
0x18000e4de  call    cs:__imp_QueryPerformanceCounter
0x18000e4e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000e4e7  mov     rcx, 0FFFFFFFFFFFFh
0x18000e4f1  shl     rax, 20h
0x18000e4f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000e4f9  xor     rax, [rbp+arg_0]
0x18000e4fd  and     rax, rcx
0x18000e500  mov     rcx, rax
0x18000e503  cmp     rax, rbx
0x18000e506  jnz     short loc_18000E515
0x18000e508  mov     rax, 2B992DDFA233h
0x18000e512  mov     rcx, rax
0x18000e515  mov     cs:__security_cookie, rcx
0x18000e51c  mov     rbx, [rsp+20h+arg_18]
0x18000e521  not     rax
0x18000e524  mov     cs:__security_cookie_complement, rax
0x18000e52b  add     rsp, 20h
0x18000e52f  pop     rbp
0x18000e530  retn
```
