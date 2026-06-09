# __security_init_cookie

- ea: `0x1800113b4`
- end: `0x180011491`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010d40`

## callees

- `0x1800113b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800113fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800113fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011407`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011413`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011423`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011413`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011423`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800113ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800113ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001143e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001143e`

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
0x1800113b4  mov     [rsp-8+arg_18], rbx
0x1800113b9  push    rbp
0x1800113ba  mov     rbp, rsp
0x1800113bd  sub     rsp, 20h
0x1800113c1  xor     eax, eax
0x1800113c3  mov     rbx, 2B992DDFA232h
0x1800113cd  mov     [rbp+arg_0], rax
0x1800113d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800113d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800113d9  mov     rax, cs:__security_cookie
0x1800113e0  cmp     rax, rbx
0x1800113e3  jnz     loc_18001147C
0x1800113e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800113ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800113f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800113f7  mov     [rbp+arg_0], rax
0x1800113fb  call    cs:__imp_GetCurrentProcessId
0x180011401  mov     eax, eax
0x180011403  xor     [rbp+arg_0], rax
0x180011407  call    cs:__imp_GetCurrentThreadId
0x18001140d  mov     eax, eax
0x18001140f  xor     [rbp+arg_0], rax
0x180011413  call    cs:__imp_GetTickCount
0x180011419  mov     eax, eax
0x18001141b  shl     rax, 18h
0x18001141f  xor     [rbp+arg_0], rax
0x180011423  call    cs:__imp_GetTickCount
0x180011429  mov     eax, eax
0x18001142b  lea     rcx, [rbp+arg_0]
0x18001142f  xor     rax, [rbp+arg_0]
0x180011433  xor     rax, rcx
0x180011436  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001143a  mov     [rbp+arg_0], rax
0x18001143e  call    cs:__imp_QueryPerformanceCounter
0x180011444  mov     eax, dword ptr [rbp+PerformanceCount]
0x180011447  mov     rcx, 0FFFFFFFFFFFFh
0x180011451  shl     rax, 20h
0x180011455  xor     rax, qword ptr [rbp+PerformanceCount]
0x180011459  xor     rax, [rbp+arg_0]
0x18001145d  and     rax, rcx
0x180011460  mov     rcx, rax
0x180011463  cmp     rax, rbx
0x180011466  jnz     short loc_180011475
0x180011468  mov     rax, 2B992DDFA233h
0x180011472  mov     rcx, rax
0x180011475  mov     cs:__security_cookie, rcx
0x18001147c  mov     rbx, [rsp+20h+arg_18]
0x180011481  not     rax
0x180011484  mov     cs:__security_cookie_complement, rax
0x18001148b  add     rsp, 20h
0x18001148f  pop     rbp
0x180011490  retn
```
