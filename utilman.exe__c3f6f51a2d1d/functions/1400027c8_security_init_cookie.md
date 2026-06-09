# __security_init_cookie

- ea: `0x1400027c8`
- end: `0x14000287d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002450`

## callees

- `0x1400027c8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400027fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400027fd`
- `KERNEL32!QueryPerformanceCounter` at `0x140002827`
- `KERNEL32!QueryPerformanceCounter` at `0x140002827`
- `KERNEL32!GetCurrentThreadId` at `0x14000280b`
- `KERNEL32!GetCurrentThreadId` at `0x14000280b`
- `KERNEL32!GetCurrentProcessId` at `0x140002817`
- `KERNEL32!GetCurrentProcessId` at `0x140002817`

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
0x1400027c8  mov     [rsp-8+arg_10], rbx
0x1400027cd  push    rbp
0x1400027ce  mov     rbp, rsp
0x1400027d1  sub     rsp, 30h
0x1400027d5  mov     rax, cs:__security_cookie
0x1400027dc  mov     rbx, 2B992DDFA232h
0x1400027e6  cmp     rax, rbx
0x1400027e9  jnz     short loc_140002868
0x1400027eb  xor     eax, eax
0x1400027ed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400027f1  mov     [rbp+var_10], rax
0x1400027f5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400027f9  mov     qword ptr [rbp+PerformanceCount], rax
0x1400027fd  call    cs:__imp_GetSystemTimeAsFileTime
0x140002803  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002807  mov     [rbp+var_10], rax
0x14000280b  call    cs:__imp_GetCurrentThreadId
0x140002811  mov     eax, eax
0x140002813  xor     [rbp+var_10], rax
0x140002817  call    cs:__imp_GetCurrentProcessId
0x14000281d  mov     eax, eax
0x14000281f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002823  xor     [rbp+var_10], rax
0x140002827  call    cs:__imp_QueryPerformanceCounter
0x14000282d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002830  lea     rcx, [rbp+var_10]
0x140002834  shl     rax, 20h
0x140002838  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000283c  xor     rax, [rbp+var_10]
0x140002840  xor     rax, rcx
0x140002843  mov     rcx, 0FFFFFFFFFFFFh
0x14000284d  and     rax, rcx
0x140002850  mov     rcx, 2B992DDFA233h
0x14000285a  cmp     rax, rbx
0x14000285d  cmovz   rax, rcx
0x140002861  mov     cs:__security_cookie, rax
0x140002868  mov     rbx, [rsp+30h+arg_10]
0x14000286d  not     rax
0x140002870  mov     cs:__security_cookie_complement, rax
0x140002877  add     rsp, 30h
0x14000287b  pop     rbp
0x14000287c  retn
```
