# __security_init_cookie

- ea: `0x1400021bc`
- end: `0x140002271`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001eb0`

## callees

- `0x1400021bc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400021ff`
- `KERNEL32!GetCurrentThreadId` at `0x1400021ff`
- `KERNEL32!GetCurrentProcessId` at `0x14000220b`
- `KERNEL32!GetCurrentProcessId` at `0x14000220b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000221b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000221b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400021f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400021f1`

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
0x1400021bc  mov     [rsp-8+arg_10], rbx
0x1400021c1  push    rbp
0x1400021c2  mov     rbp, rsp
0x1400021c5  sub     rsp, 30h
0x1400021c9  mov     rax, cs:__security_cookie
0x1400021d0  mov     rbx, 2B992DDFA232h
0x1400021da  cmp     rax, rbx
0x1400021dd  jnz     short loc_14000225C
0x1400021df  xor     eax, eax
0x1400021e1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400021e5  mov     [rbp+var_10], rax
0x1400021e9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400021ed  mov     qword ptr [rbp+PerformanceCount], rax
0x1400021f1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400021f7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400021fb  mov     [rbp+var_10], rax
0x1400021ff  call    cs:__imp_GetCurrentThreadId
0x140002205  mov     eax, eax
0x140002207  xor     [rbp+var_10], rax
0x14000220b  call    cs:__imp_GetCurrentProcessId
0x140002211  mov     eax, eax
0x140002213  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002217  xor     [rbp+var_10], rax
0x14000221b  call    cs:__imp_QueryPerformanceCounter
0x140002221  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002224  lea     rcx, [rbp+var_10]
0x140002228  shl     rax, 20h
0x14000222c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002230  xor     rax, [rbp+var_10]
0x140002234  xor     rax, rcx
0x140002237  mov     rcx, 0FFFFFFFFFFFFh
0x140002241  and     rax, rcx
0x140002244  mov     rcx, 2B992DDFA233h
0x14000224e  cmp     rax, rbx
0x140002251  cmovz   rax, rcx
0x140002255  mov     cs:__security_cookie, rax
0x14000225c  mov     rbx, [rsp+30h+arg_10]
0x140002261  not     rax
0x140002264  mov     cs:__security_cookie_complement, rax
0x14000226b  add     rsp, 30h
0x14000226f  pop     rbp
0x140002270  retn
```
