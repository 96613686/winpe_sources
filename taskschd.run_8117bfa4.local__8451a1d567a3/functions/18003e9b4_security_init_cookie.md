# __security_init_cookie

- ea: `0x18003e9b4`
- end: `0x18003ea91`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e050`

## callees

- `0x18003e9b4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e9ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e9ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ea13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ea23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ea13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ea23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e9fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e9fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ea07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ea07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ea3e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ea3e`

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
0x18003e9b4  mov     [rsp-8+arg_18], rbx
0x18003e9b9  push    rbp
0x18003e9ba  mov     rbp, rsp
0x18003e9bd  sub     rsp, 20h
0x18003e9c1  xor     eax, eax
0x18003e9c3  mov     rbx, 2B992DDFA232h
0x18003e9cd  mov     [rbp+arg_0], rax
0x18003e9d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003e9d5  mov     qword ptr [rbp+PerformanceCount], rax
0x18003e9d9  mov     rax, cs:__security_cookie
0x18003e9e0  cmp     rax, rbx
0x18003e9e3  jnz     loc_18003EA7C
0x18003e9e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003e9ed  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e9f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003e9f7  mov     [rbp+arg_0], rax
0x18003e9fb  call    cs:__imp_GetCurrentProcessId
0x18003ea01  mov     eax, eax
0x18003ea03  xor     [rbp+arg_0], rax
0x18003ea07  call    cs:__imp_GetCurrentThreadId
0x18003ea0d  mov     eax, eax
0x18003ea0f  xor     [rbp+arg_0], rax
0x18003ea13  call    cs:__imp_GetTickCount
0x18003ea19  mov     eax, eax
0x18003ea1b  shl     rax, 18h
0x18003ea1f  xor     [rbp+arg_0], rax
0x18003ea23  call    cs:__imp_GetTickCount
0x18003ea29  mov     eax, eax
0x18003ea2b  lea     rcx, [rbp+arg_0]
0x18003ea2f  xor     rax, [rbp+arg_0]
0x18003ea33  xor     rax, rcx
0x18003ea36  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003ea3a  mov     [rbp+arg_0], rax
0x18003ea3e  call    cs:__imp_QueryPerformanceCounter
0x18003ea44  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003ea47  mov     rcx, 0FFFFFFFFFFFFh
0x18003ea51  shl     rax, 20h
0x18003ea55  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003ea59  xor     rax, [rbp+arg_0]
0x18003ea5d  and     rax, rcx
0x18003ea60  mov     rcx, rax
0x18003ea63  cmp     rax, rbx
0x18003ea66  jnz     short loc_18003EA75
0x18003ea68  mov     rax, 2B992DDFA233h
0x18003ea72  mov     rcx, rax
0x18003ea75  mov     cs:__security_cookie, rcx
0x18003ea7c  mov     rbx, [rsp+20h+arg_18]
0x18003ea81  not     rax
0x18003ea84  mov     cs:__security_cookie_complement, rax
0x18003ea8b  add     rsp, 20h
0x18003ea8f  pop     rbp
0x18003ea90  retn
```
