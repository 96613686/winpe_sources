# __security_init_cookie

- ea: `0x180001614`
- end: `0x1800016c9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015a0`

## callees

- `0x180001614`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001657`
- `KERNEL32!GetCurrentThreadId` at `0x180001657`
- `KERNEL32!QueryPerformanceCounter` at `0x180001673`
- `KERNEL32!QueryPerformanceCounter` at `0x180001673`
- `KERNEL32!GetCurrentProcessId` at `0x180001663`
- `KERNEL32!GetCurrentProcessId` at `0x180001663`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001649`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001649`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001614  mov     [rsp-8+arg_10], rbx
0x180001619  push    rbp
0x18000161a  mov     rbp, rsp
0x18000161d  sub     rsp, 30h
0x180001621  mov     rax, cs:__security_cookie
0x180001628  mov     rbx, 2B992DDFA232h
0x180001632  cmp     rax, rbx
0x180001635  jnz     short loc_1800016B4
0x180001637  xor     eax, eax
0x180001639  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000163d  mov     [rbp+var_10], rax
0x180001641  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001645  mov     qword ptr [rbp+PerformanceCount], rax
0x180001649  call    cs:__imp_GetSystemTimeAsFileTime
0x18000164f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001653  mov     [rbp+var_10], rax
0x180001657  call    cs:__imp_GetCurrentThreadId
0x18000165d  mov     eax, eax
0x18000165f  xor     [rbp+var_10], rax
0x180001663  call    cs:__imp_GetCurrentProcessId
0x180001669  mov     eax, eax
0x18000166b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000166f  xor     [rbp+var_10], rax
0x180001673  call    cs:__imp_QueryPerformanceCounter
0x180001679  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000167c  lea     rcx, [rbp+var_10]
0x180001680  shl     rax, 20h
0x180001684  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001688  xor     rax, [rbp+var_10]
0x18000168c  xor     rax, rcx
0x18000168f  mov     rcx, 0FFFFFFFFFFFFh
0x180001699  and     rax, rcx
0x18000169c  mov     rcx, 2B992DDFA233h
0x1800016a6  cmp     rax, rbx
0x1800016a9  cmovz   rax, rcx
0x1800016ad  mov     cs:__security_cookie, rax
0x1800016b4  mov     rbx, [rsp+30h+arg_10]
0x1800016b9  not     rax
0x1800016bc  mov     cs:__security_cookie_complement, rax
0x1800016c3  add     rsp, 30h
0x1800016c7  pop     rbp
0x1800016c8  retn
```
