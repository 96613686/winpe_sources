# __security_init_cookie

- ea: `0x180026884`
- end: `0x180026959`
- name: `__security_init_cookie`
- size: `213`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800263d0`

## callees

- `0x180026884`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800268db`
- `KERNEL32!GetTickCount` at `0x1800268eb`
- `KERNEL32!GetTickCount` at `0x1800268db`
- `KERNEL32!GetTickCount` at `0x1800268eb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800268b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800268b5`
- `KERNEL32!GetCurrentThreadId` at `0x1800268cf`
- `KERNEL32!GetCurrentThreadId` at `0x1800268cf`
- `KERNEL32!QueryPerformanceCounter` at `0x180026906`
- `KERNEL32!QueryPerformanceCounter` at `0x180026906`
- `KERNEL32!GetCurrentProcessId` at `0x1800268c3`
- `KERNEL32!GetCurrentProcessId` at `0x1800268c3`

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
0x180026884  mov     [rsp-8+arg_18], rbx
0x180026889  push    rbp
0x18002688a  mov     rbp, rsp
0x18002688d  sub     rsp, 20h
0x180026891  xor     eax, eax
0x180026893  mov     rbx, 2B992DDFA232h
0x18002689d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800268a1  mov     rax, cs:__security_cookie
0x1800268a8  cmp     rax, rbx
0x1800268ab  jnz     loc_180026944
0x1800268b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800268b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800268bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800268bf  mov     [rbp+arg_0], rax
0x1800268c3  call    cs:__imp_GetCurrentProcessId
0x1800268c9  mov     eax, eax
0x1800268cb  xor     [rbp+arg_0], rax
0x1800268cf  call    cs:__imp_GetCurrentThreadId
0x1800268d5  mov     eax, eax
0x1800268d7  xor     [rbp+arg_0], rax
0x1800268db  call    cs:__imp_GetTickCount
0x1800268e1  mov     eax, eax
0x1800268e3  shl     rax, 18h
0x1800268e7  xor     [rbp+arg_0], rax
0x1800268eb  call    cs:__imp_GetTickCount
0x1800268f1  mov     eax, eax
0x1800268f3  lea     rcx, [rbp+arg_0]
0x1800268f7  xor     rax, [rbp+arg_0]
0x1800268fb  xor     rax, rcx
0x1800268fe  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026902  mov     [rbp+arg_0], rax
0x180026906  call    cs:__imp_QueryPerformanceCounter
0x18002690c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002690f  mov     rcx, 0FFFFFFFFFFFFh
0x180026919  shl     rax, 20h
0x18002691d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180026921  xor     rax, [rbp+arg_0]
0x180026925  and     rax, rcx
0x180026928  mov     rcx, rax
0x18002692b  cmp     rax, rbx
0x18002692e  jnz     short loc_18002693D
0x180026930  mov     rax, 2B992DDFA233h
0x18002693a  mov     rcx, rax
0x18002693d  mov     cs:__security_cookie, rcx
0x180026944  mov     rbx, [rsp+20h+arg_18]
0x180026949  not     rax
0x18002694c  mov     cs:__security_cookie_complement, rax
0x180026953  add     rsp, 20h
0x180026957  pop     rbp
0x180026958  retn
```
