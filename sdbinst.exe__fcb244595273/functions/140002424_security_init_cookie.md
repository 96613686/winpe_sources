# __security_init_cookie

- ea: `0x140002424`
- end: `0x140002501`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001c50`

## callees

- `0x140002424`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002477`
- `KERNEL32!GetCurrentThreadId` at `0x140002477`
- `KERNEL32!GetCurrentProcessId` at `0x14000246b`
- `KERNEL32!GetCurrentProcessId` at `0x14000246b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000245d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000245d`
- `KERNEL32!GetTickCount` at `0x140002483`
- `KERNEL32!GetTickCount` at `0x140002493`
- `KERNEL32!GetTickCount` at `0x140002483`
- `KERNEL32!GetTickCount` at `0x140002493`
- `KERNEL32!QueryPerformanceCounter` at `0x1400024ae`
- `KERNEL32!QueryPerformanceCounter` at `0x1400024ae`

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
0x140002424  mov     [rsp-8+arg_18], rbx
0x140002429  push    rbp
0x14000242a  mov     rbp, rsp
0x14000242d  sub     rsp, 20h
0x140002431  xor     eax, eax
0x140002433  mov     rbx, 2B992DDFA232h
0x14000243d  mov     [rbp+arg_0], rax
0x140002441  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002445  mov     qword ptr [rbp+PerformanceCount], rax
0x140002449  mov     rax, cs:__security_cookie
0x140002450  cmp     rax, rbx
0x140002453  jnz     loc_1400024EC
0x140002459  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000245d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002463  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002467  mov     [rbp+arg_0], rax
0x14000246b  call    cs:__imp_GetCurrentProcessId
0x140002471  mov     eax, eax
0x140002473  xor     [rbp+arg_0], rax
0x140002477  call    cs:__imp_GetCurrentThreadId
0x14000247d  mov     eax, eax
0x14000247f  xor     [rbp+arg_0], rax
0x140002483  call    cs:__imp_GetTickCount
0x140002489  mov     eax, eax
0x14000248b  shl     rax, 18h
0x14000248f  xor     [rbp+arg_0], rax
0x140002493  call    cs:__imp_GetTickCount
0x140002499  mov     eax, eax
0x14000249b  lea     rcx, [rbp+arg_0]
0x14000249f  xor     rax, [rbp+arg_0]
0x1400024a3  xor     rax, rcx
0x1400024a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400024aa  mov     [rbp+arg_0], rax
0x1400024ae  call    cs:__imp_QueryPerformanceCounter
0x1400024b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400024b7  mov     rcx, 0FFFFFFFFFFFFh
0x1400024c1  shl     rax, 20h
0x1400024c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400024c9  xor     rax, [rbp+arg_0]
0x1400024cd  and     rax, rcx
0x1400024d0  mov     rcx, rax
0x1400024d3  cmp     rax, rbx
0x1400024d6  jnz     short loc_1400024E5
0x1400024d8  mov     rax, 2B992DDFA233h
0x1400024e2  mov     rcx, rax
0x1400024e5  mov     cs:__security_cookie, rcx
0x1400024ec  mov     rbx, [rsp+20h+arg_18]
0x1400024f1  not     rax
0x1400024f4  mov     cs:__security_cookie_complement, rax
0x1400024fb  add     rsp, 20h
0x1400024ff  pop     rbp
0x140002500  retn
```
