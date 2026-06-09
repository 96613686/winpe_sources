# __security_init_cookie

- ea: `0x1400017b0`
- end: `0x140001865`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x1400017b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400017f3`
- `KERNEL32!GetCurrentThreadId` at `0x1400017f3`
- `KERNEL32!QueryPerformanceCounter` at `0x14000180f`
- `KERNEL32!QueryPerformanceCounter` at `0x14000180f`
- `KERNEL32!GetCurrentProcessId` at `0x1400017ff`
- `KERNEL32!GetCurrentProcessId` at `0x1400017ff`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400017e5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400017e5`

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
0x1400017b0  mov     [rsp-8+arg_10], rbx
0x1400017b5  push    rbp
0x1400017b6  mov     rbp, rsp
0x1400017b9  sub     rsp, 30h
0x1400017bd  mov     rax, cs:__security_cookie
0x1400017c4  mov     rbx, 2B992DDFA232h
0x1400017ce  cmp     rax, rbx
0x1400017d1  jnz     short loc_140001850
0x1400017d3  xor     eax, eax
0x1400017d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017d9  mov     [rbp+var_10], rax
0x1400017dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017ef  mov     [rbp+var_10], rax
0x1400017f3  call    cs:__imp_GetCurrentThreadId
0x1400017f9  mov     eax, eax
0x1400017fb  xor     [rbp+var_10], rax
0x1400017ff  call    cs:__imp_GetCurrentProcessId
0x140001805  mov     eax, eax
0x140001807  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000180b  xor     [rbp+var_10], rax
0x14000180f  call    cs:__imp_QueryPerformanceCounter
0x140001815  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001818  lea     rcx, [rbp+var_10]
0x14000181c  shl     rax, 20h
0x140001820  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001824  xor     rax, [rbp+var_10]
0x140001828  xor     rax, rcx
0x14000182b  mov     rcx, 0FFFFFFFFFFFFh
0x140001835  and     rax, rcx
0x140001838  mov     rcx, 2B992DDFA233h
0x140001842  cmp     rax, rbx
0x140001845  cmovz   rax, rcx
0x140001849  mov     cs:__security_cookie, rax
0x140001850  mov     rbx, [rsp+30h+arg_10]
0x140001855  not     rax
0x140001858  mov     cs:__security_cookie_complement, rax
0x14000185f  add     rsp, 30h
0x140001863  pop     rbp
0x140001864  retn
```
