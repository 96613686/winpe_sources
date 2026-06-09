# __security_init_cookie

- ea: `0x180001de4`
- end: `0x180001ec1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001780`

## callees

- `0x180001de4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e1d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e1d`
- `KERNEL32!GetTickCount` at `0x180001e43`
- `KERNEL32!GetTickCount` at `0x180001e53`
- `KERNEL32!GetTickCount` at `0x180001e43`
- `KERNEL32!GetTickCount` at `0x180001e53`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e6e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e6e`
- `KERNEL32!GetCurrentThreadId` at `0x180001e37`
- `KERNEL32!GetCurrentThreadId` at `0x180001e37`
- `KERNEL32!GetCurrentProcessId` at `0x180001e2b`
- `KERNEL32!GetCurrentProcessId` at `0x180001e2b`

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
0x180001de4  mov     [rsp-8+arg_18], rbx
0x180001de9  push    rbp
0x180001dea  mov     rbp, rsp
0x180001ded  sub     rsp, 20h
0x180001df1  xor     eax, eax
0x180001df3  mov     rbx, 2B992DDFA232h
0x180001dfd  mov     [rbp+arg_0], rax
0x180001e01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e05  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e09  mov     rax, cs:__security_cookie
0x180001e10  cmp     rax, rbx
0x180001e13  jnz     loc_180001EAC
0x180001e19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e27  mov     [rbp+arg_0], rax
0x180001e2b  call    cs:__imp_GetCurrentProcessId
0x180001e31  mov     eax, eax
0x180001e33  xor     [rbp+arg_0], rax
0x180001e37  call    cs:__imp_GetCurrentThreadId
0x180001e3d  mov     eax, eax
0x180001e3f  xor     [rbp+arg_0], rax
0x180001e43  call    cs:__imp_GetTickCount
0x180001e49  mov     eax, eax
0x180001e4b  shl     rax, 18h
0x180001e4f  xor     [rbp+arg_0], rax
0x180001e53  call    cs:__imp_GetTickCount
0x180001e59  mov     eax, eax
0x180001e5b  lea     rcx, [rbp+arg_0]
0x180001e5f  xor     rax, [rbp+arg_0]
0x180001e63  xor     rax, rcx
0x180001e66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001e6a  mov     [rbp+arg_0], rax
0x180001e6e  call    cs:__imp_QueryPerformanceCounter
0x180001e74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001e77  mov     rcx, 0FFFFFFFFFFFFh
0x180001e81  shl     rax, 20h
0x180001e85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001e89  xor     rax, [rbp+arg_0]
0x180001e8d  and     rax, rcx
0x180001e90  mov     rcx, rax
0x180001e93  cmp     rax, rbx
0x180001e96  jnz     short loc_180001EA5
0x180001e98  mov     rax, 2B992DDFA233h
0x180001ea2  mov     rcx, rax
0x180001ea5  mov     cs:__security_cookie, rcx
0x180001eac  mov     rbx, [rsp+20h+arg_18]
0x180001eb1  not     rax
0x180001eb4  mov     cs:__security_cookie_complement, rax
0x180001ebb  add     rsp, 20h
0x180001ebf  pop     rbp
0x180001ec0  retn
```
