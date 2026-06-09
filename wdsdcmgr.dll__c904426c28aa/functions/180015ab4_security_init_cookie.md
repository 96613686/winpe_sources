# __security_init_cookie

- ea: `0x180015ab4`
- end: `0x180015b89`
- name: `__security_init_cookie`
- size: `213`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800153c0`

## callees

- `0x180015ab4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180015b36`
- `KERNEL32!QueryPerformanceCounter` at `0x180015b36`
- `KERNEL32!GetCurrentProcessId` at `0x180015af3`
- `KERNEL32!GetCurrentProcessId` at `0x180015af3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015ae5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015ae5`
- `KERNEL32!GetTickCount` at `0x180015b0b`
- `KERNEL32!GetTickCount` at `0x180015b1b`
- `KERNEL32!GetTickCount` at `0x180015b0b`
- `KERNEL32!GetTickCount` at `0x180015b1b`
- `KERNEL32!GetCurrentThreadId` at `0x180015aff`
- `KERNEL32!GetCurrentThreadId` at `0x180015aff`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
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
0x180015ab4  mov     [rsp-8+arg_18], rbx
0x180015ab9  push    rbp
0x180015aba  mov     rbp, rsp
0x180015abd  sub     rsp, 20h
0x180015ac1  xor     eax, eax
0x180015ac3  mov     rbx, 2B992DDFA232h
0x180015acd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180015ad1  mov     rax, cs:__security_cookie
0x180015ad8  cmp     rax, rbx
0x180015adb  jnz     loc_180015B74
0x180015ae1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015ae5  call    cs:__imp_GetSystemTimeAsFileTime
0x180015aeb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180015aef  mov     [rbp+arg_0], rax
0x180015af3  call    cs:__imp_GetCurrentProcessId
0x180015af9  mov     eax, eax
0x180015afb  xor     [rbp+arg_0], rax
0x180015aff  call    cs:__imp_GetCurrentThreadId
0x180015b05  mov     eax, eax
0x180015b07  xor     [rbp+arg_0], rax
0x180015b0b  call    cs:__imp_GetTickCount
0x180015b11  mov     eax, eax
0x180015b13  shl     rax, 18h
0x180015b17  xor     [rbp+arg_0], rax
0x180015b1b  call    cs:__imp_GetTickCount
0x180015b21  mov     eax, eax
0x180015b23  lea     rcx, [rbp+arg_0]
0x180015b27  xor     rax, [rbp+arg_0]
0x180015b2b  xor     rax, rcx
0x180015b2e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180015b32  mov     [rbp+arg_0], rax
0x180015b36  call    cs:__imp_QueryPerformanceCounter
0x180015b3c  mov     eax, dword ptr [rbp+PerformanceCount]
0x180015b3f  mov     rcx, 0FFFFFFFFFFFFh
0x180015b49  shl     rax, 20h
0x180015b4d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180015b51  xor     rax, [rbp+arg_0]
0x180015b55  and     rax, rcx
0x180015b58  mov     rcx, rax
0x180015b5b  cmp     rax, rbx
0x180015b5e  jnz     short loc_180015B6D
0x180015b60  mov     rax, 2B992DDFA233h
0x180015b6a  mov     rcx, rax
0x180015b6d  mov     cs:__security_cookie, rcx
0x180015b74  mov     rbx, [rsp+20h+arg_18]
0x180015b79  not     rax
0x180015b7c  mov     cs:__security_cookie_complement, rax
0x180015b83  add     rsp, 20h
0x180015b87  pop     rbp
0x180015b88  retn
```
