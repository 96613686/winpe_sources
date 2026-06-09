# __security_init_cookie

- ea: `0x18003b644`
- end: `0x18003b721`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ace0`

## callees

- `0x18003b644`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b67d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b67d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b6a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b6b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b6a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b6b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b697`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b6ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b6ce`

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
0x18003b644  mov     [rsp-8+arg_18], rbx
0x18003b649  push    rbp
0x18003b64a  mov     rbp, rsp
0x18003b64d  sub     rsp, 20h
0x18003b651  xor     eax, eax
0x18003b653  mov     rbx, 2B992DDFA232h
0x18003b65d  mov     [rbp+arg_0], rax
0x18003b661  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003b665  mov     qword ptr [rbp+PerformanceCount], rax
0x18003b669  mov     rax, cs:__security_cookie
0x18003b670  cmp     rax, rbx
0x18003b673  jnz     loc_18003B70C
0x18003b679  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b67d  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b683  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003b687  mov     [rbp+arg_0], rax
0x18003b68b  call    cs:__imp_GetCurrentProcessId
0x18003b691  mov     eax, eax
0x18003b693  xor     [rbp+arg_0], rax
0x18003b697  call    cs:__imp_GetCurrentThreadId
0x18003b69d  mov     eax, eax
0x18003b69f  xor     [rbp+arg_0], rax
0x18003b6a3  call    cs:__imp_GetTickCount
0x18003b6a9  mov     eax, eax
0x18003b6ab  shl     rax, 18h
0x18003b6af  xor     [rbp+arg_0], rax
0x18003b6b3  call    cs:__imp_GetTickCount
0x18003b6b9  mov     eax, eax
0x18003b6bb  lea     rcx, [rbp+arg_0]
0x18003b6bf  xor     rax, [rbp+arg_0]
0x18003b6c3  xor     rax, rcx
0x18003b6c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003b6ca  mov     [rbp+arg_0], rax
0x18003b6ce  call    cs:__imp_QueryPerformanceCounter
0x18003b6d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003b6d7  mov     rcx, 0FFFFFFFFFFFFh
0x18003b6e1  shl     rax, 20h
0x18003b6e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003b6e9  xor     rax, [rbp+arg_0]
0x18003b6ed  and     rax, rcx
0x18003b6f0  mov     rcx, rax
0x18003b6f3  cmp     rax, rbx
0x18003b6f6  jnz     short loc_18003B705
0x18003b6f8  mov     rax, 2B992DDFA233h
0x18003b702  mov     rcx, rax
0x18003b705  mov     cs:__security_cookie, rcx
0x18003b70c  mov     rbx, [rsp+20h+arg_18]
0x18003b711  not     rax
0x18003b714  mov     cs:__security_cookie_complement, rax
0x18003b71b  add     rsp, 20h
0x18003b71f  pop     rbp
0x18003b720  retn
```
