# __security_init_cookie

- ea: `0x180002de4`
- end: `0x180002ec1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800027d0`

## callees

- `0x180002de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002e43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002e53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002e43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002e53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e1d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e6e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180002de4  mov     [rsp-8+arg_18], rbx
0x180002de9  push    rbp
0x180002dea  mov     rbp, rsp
0x180002ded  sub     rsp, 20h
0x180002df1  xor     eax, eax
0x180002df3  mov     rbx, 2B992DDFA232h
0x180002dfd  mov     [rbp+arg_0], rax
0x180002e01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002e05  mov     qword ptr [rbp+PerformanceCount], rax
0x180002e09  mov     rax, cs:__security_cookie
0x180002e10  cmp     rax, rbx
0x180002e13  jnz     loc_180002EAC
0x180002e19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002e1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002e23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002e27  mov     [rbp+arg_0], rax
0x180002e2b  call    cs:__imp_GetCurrentProcessId
0x180002e31  mov     eax, eax
0x180002e33  xor     [rbp+arg_0], rax
0x180002e37  call    cs:__imp_GetCurrentThreadId
0x180002e3d  mov     eax, eax
0x180002e3f  xor     [rbp+arg_0], rax
0x180002e43  call    cs:__imp_GetTickCount
0x180002e49  mov     eax, eax
0x180002e4b  shl     rax, 18h
0x180002e4f  xor     [rbp+arg_0], rax
0x180002e53  call    cs:__imp_GetTickCount
0x180002e59  mov     eax, eax
0x180002e5b  lea     rcx, [rbp+arg_0]
0x180002e5f  xor     rax, [rbp+arg_0]
0x180002e63  xor     rax, rcx
0x180002e66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002e6a  mov     [rbp+arg_0], rax
0x180002e6e  call    cs:__imp_QueryPerformanceCounter
0x180002e74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002e77  mov     rcx, 0FFFFFFFFFFFFh
0x180002e81  shl     rax, 20h
0x180002e85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002e89  xor     rax, [rbp+arg_0]
0x180002e8d  and     rax, rcx
0x180002e90  mov     rcx, rax
0x180002e93  cmp     rax, rbx
0x180002e96  jnz     short loc_180002EA5
0x180002e98  mov     rax, 2B992DDFA233h
0x180002ea2  mov     rcx, rax
0x180002ea5  mov     cs:__security_cookie, rcx
0x180002eac  mov     rbx, [rsp+20h+arg_18]
0x180002eb1  not     rax
0x180002eb4  mov     cs:__security_cookie_complement, rax
0x180002ebb  add     rsp, 20h
0x180002ebf  pop     rbp
0x180002ec0  retn
```
