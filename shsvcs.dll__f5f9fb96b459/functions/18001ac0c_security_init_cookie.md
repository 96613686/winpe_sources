# __security_init_cookie

- ea: `0x18001ac0c`
- end: `0x18001ace9`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a8b0`

## callees

- `0x18001ac0c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ac96`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ac96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ac53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ac53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ac6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ac7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ac6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ac7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ac45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ac45`

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
0x18001ac0c  mov     [rsp-8+arg_18], rbx
0x18001ac11  push    rbp
0x18001ac12  mov     rbp, rsp
0x18001ac15  sub     rsp, 20h
0x18001ac19  xor     eax, eax
0x18001ac1b  mov     rbx, 2B992DDFA232h
0x18001ac25  mov     [rbp+arg_0], rax
0x18001ac29  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001ac2d  mov     qword ptr [rbp+PerformanceCount], rax
0x18001ac31  mov     rax, cs:__security_cookie
0x18001ac38  cmp     rax, rbx
0x18001ac3b  jnz     loc_18001ACD4
0x18001ac41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ac45  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ac4b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ac4f  mov     [rbp+arg_0], rax
0x18001ac53  call    cs:__imp_GetCurrentProcessId
0x18001ac59  mov     eax, eax
0x18001ac5b  xor     [rbp+arg_0], rax
0x18001ac5f  call    cs:__imp_GetCurrentThreadId
0x18001ac65  mov     eax, eax
0x18001ac67  xor     [rbp+arg_0], rax
0x18001ac6b  call    cs:__imp_GetTickCount
0x18001ac71  mov     eax, eax
0x18001ac73  shl     rax, 18h
0x18001ac77  xor     [rbp+arg_0], rax
0x18001ac7b  call    cs:__imp_GetTickCount
0x18001ac81  mov     eax, eax
0x18001ac83  lea     rcx, [rbp+arg_0]
0x18001ac87  xor     rax, [rbp+arg_0]
0x18001ac8b  xor     rax, rcx
0x18001ac8e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ac92  mov     [rbp+arg_0], rax
0x18001ac96  call    cs:__imp_QueryPerformanceCounter
0x18001ac9c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001ac9f  mov     rcx, 0FFFFFFFFFFFFh
0x18001aca9  shl     rax, 20h
0x18001acad  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001acb1  xor     rax, [rbp+arg_0]
0x18001acb5  and     rax, rcx
0x18001acb8  mov     rcx, rax
0x18001acbb  cmp     rax, rbx
0x18001acbe  jnz     short loc_18001ACCD
0x18001acc0  mov     rax, 2B992DDFA233h
0x18001acca  mov     rcx, rax
0x18001accd  mov     cs:__security_cookie, rcx
0x18001acd4  mov     rbx, [rsp+20h+arg_18]
0x18001acd9  not     rax
0x18001acdc  mov     cs:__security_cookie_complement, rax
0x18001ace3  add     rsp, 20h
0x18001ace7  pop     rbp
0x18001ace8  retn
```
