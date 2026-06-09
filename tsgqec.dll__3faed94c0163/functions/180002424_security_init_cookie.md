# __security_init_cookie

- ea: `0x180002424`
- end: `0x180002501`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f10`

## callees

- `0x180002424`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800024ae`
- `KERNEL32!QueryPerformanceCounter` at `0x1800024ae`
- `KERNEL32!GetCurrentProcessId` at `0x18000246b`
- `KERNEL32!GetCurrentProcessId` at `0x18000246b`
- `KERNEL32!GetCurrentThreadId` at `0x180002477`
- `KERNEL32!GetCurrentThreadId` at `0x180002477`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000245d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000245d`
- `KERNEL32!GetTickCount` at `0x180002483`
- `KERNEL32!GetTickCount` at `0x180002493`
- `KERNEL32!GetTickCount` at `0x180002483`
- `KERNEL32!GetTickCount` at `0x180002493`

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
0x180002424  mov     [rsp-8+arg_18], rbx
0x180002429  push    rbp
0x18000242a  mov     rbp, rsp
0x18000242d  sub     rsp, 20h
0x180002431  xor     eax, eax
0x180002433  mov     rbx, 2B992DDFA232h
0x18000243d  mov     [rbp+arg_0], rax
0x180002441  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002445  mov     qword ptr [rbp+PerformanceCount], rax
0x180002449  mov     rax, cs:__security_cookie
0x180002450  cmp     rax, rbx
0x180002453  jnz     loc_1800024EC
0x180002459  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000245d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002463  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002467  mov     [rbp+arg_0], rax
0x18000246b  call    cs:__imp_GetCurrentProcessId
0x180002471  mov     eax, eax
0x180002473  xor     [rbp+arg_0], rax
0x180002477  call    cs:__imp_GetCurrentThreadId
0x18000247d  mov     eax, eax
0x18000247f  xor     [rbp+arg_0], rax
0x180002483  call    cs:__imp_GetTickCount
0x180002489  mov     eax, eax
0x18000248b  shl     rax, 18h
0x18000248f  xor     [rbp+arg_0], rax
0x180002493  call    cs:__imp_GetTickCount
0x180002499  mov     eax, eax
0x18000249b  lea     rcx, [rbp+arg_0]
0x18000249f  xor     rax, [rbp+arg_0]
0x1800024a3  xor     rax, rcx
0x1800024a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800024aa  mov     [rbp+arg_0], rax
0x1800024ae  call    cs:__imp_QueryPerformanceCounter
0x1800024b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800024b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800024c1  shl     rax, 20h
0x1800024c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800024c9  xor     rax, [rbp+arg_0]
0x1800024cd  and     rax, rcx
0x1800024d0  mov     rcx, rax
0x1800024d3  cmp     rax, rbx
0x1800024d6  jnz     short loc_1800024E5
0x1800024d8  mov     rax, 2B992DDFA233h
0x1800024e2  mov     rcx, rax
0x1800024e5  mov     cs:__security_cookie, rcx
0x1800024ec  mov     rbx, [rsp+20h+arg_18]
0x1800024f1  not     rax
0x1800024f4  mov     cs:__security_cookie_complement, rax
0x1800024fb  add     rsp, 20h
0x1800024ff  pop     rbp
0x180002500  retn
```
