# __security_init_cookie

- ea: `0x18002f044`
- end: `0x18002f121`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e860`

## callees

- `0x18002f044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f08b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f08b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f07d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002f07d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f0a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f0b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f0a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f0b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f0ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f0ce`

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
0x18002f044  mov     [rsp-8+arg_18], rbx
0x18002f049  push    rbp
0x18002f04a  mov     rbp, rsp
0x18002f04d  sub     rsp, 20h
0x18002f051  xor     eax, eax
0x18002f053  mov     rbx, 2B992DDFA232h
0x18002f05d  mov     [rbp+arg_0], rax
0x18002f061  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002f065  mov     qword ptr [rbp+PerformanceCount], rax
0x18002f069  mov     rax, cs:__security_cookie
0x18002f070  cmp     rax, rbx
0x18002f073  jnz     loc_18002F10C
0x18002f079  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002f07d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002f083  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002f087  mov     [rbp+arg_0], rax
0x18002f08b  call    cs:__imp_GetCurrentProcessId
0x18002f091  mov     eax, eax
0x18002f093  xor     [rbp+arg_0], rax
0x18002f097  call    cs:__imp_GetCurrentThreadId
0x18002f09d  mov     eax, eax
0x18002f09f  xor     [rbp+arg_0], rax
0x18002f0a3  call    cs:__imp_GetTickCount
0x18002f0a9  mov     eax, eax
0x18002f0ab  shl     rax, 18h
0x18002f0af  xor     [rbp+arg_0], rax
0x18002f0b3  call    cs:__imp_GetTickCount
0x18002f0b9  mov     eax, eax
0x18002f0bb  lea     rcx, [rbp+arg_0]
0x18002f0bf  xor     rax, [rbp+arg_0]
0x18002f0c3  xor     rax, rcx
0x18002f0c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002f0ca  mov     [rbp+arg_0], rax
0x18002f0ce  call    cs:__imp_QueryPerformanceCounter
0x18002f0d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002f0d7  mov     rcx, 0FFFFFFFFFFFFh
0x18002f0e1  shl     rax, 20h
0x18002f0e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002f0e9  xor     rax, [rbp+arg_0]
0x18002f0ed  and     rax, rcx
0x18002f0f0  mov     rcx, rax
0x18002f0f3  cmp     rax, rbx
0x18002f0f6  jnz     short loc_18002F105
0x18002f0f8  mov     rax, 2B992DDFA233h
0x18002f102  mov     rcx, rax
0x18002f105  mov     cs:__security_cookie, rcx
0x18002f10c  mov     rbx, [rsp+20h+arg_18]
0x18002f111  not     rax
0x18002f114  mov     cs:__security_cookie_complement, rax
0x18002f11b  add     rsp, 20h
0x18002f11f  pop     rbp
0x18002f120  retn
```
