# __security_init_cookie

- ea: `0x3838916b0`
- end: `0x38389175b`
- name: `__security_init_cookie`
- size: `171`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x383892c5c`

## callees

- `0x3838916b0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x383891702`
- `KERNEL32!GetTickCount` at `0x383891702`
- `KERNEL32!GetCurrentThreadId` at `0x3838916f6`
- `KERNEL32!GetCurrentThreadId` at `0x3838916f6`
- `KERNEL32!QueryPerformanceCounter` at `0x383891713`
- `KERNEL32!QueryPerformanceCounter` at `0x383891713`
- `KERNEL32!GetCurrentProcessId` at `0x3838916ea`
- `KERNEL32!GetCurrentProcessId` at `0x3838916ea`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x3838916df`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x3838916df`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  struct _FILETIME v0; // rbx
  unsigned __int64 v1; // rbx
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rbx
  uintptr_t v4; // r11
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v0 = SystemTimeAsFileTime;
    v1 = GetCurrentProcessId() ^ *(unsigned __int64 *)&v0;
    v2 = GetCurrentThreadId() ^ v1;
    v3 = GetTickCount() ^ v2;
    QueryPerformanceCounter(&PerformanceCount);
    v4 = (v3 ^ PerformanceCount.QuadPart) & 0xFFFFFFFFFFFFLL;
    if ( v4 == 0x2B992DDFA232LL )
      v4 = 0x2B992DDFA233LL;
    _security_cookie = v4;
    _security_cookie_complement = ~v4;
  }
  else
  {
    _security_cookie_complement = ~_security_cookie;
  }
}

```

## disassembly

```asm
0x3838916b0  mov     [rsp+arg_10], rbx
0x3838916b5  push    rdi
0x3838916b6  sub     rsp, 20h
0x3838916ba  mov     rax, cs:__security_cookie
0x3838916c1  and     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x3838916c7  mov     rdi, 2B992DDFA232h
0x3838916d1  cmp     rax, rdi
0x3838916d4  jnz     loc_383910348
0x3838916da  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x3838916df  call    cs:__imp_GetSystemTimeAsFileTime
0x3838916e5  mov     rbx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x3838916ea  call    cs:__imp_GetCurrentProcessId
0x3838916f0  mov     r11d, eax
0x3838916f3  xor     rbx, r11
0x3838916f6  call    cs:__imp_GetCurrentThreadId
0x3838916fc  mov     r11d, eax
0x3838916ff  xor     rbx, r11
0x383891702  call    cs:__imp_GetTickCount
0x383891708  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x38389170d  mov     r11d, eax
0x383891710  xor     rbx, r11
0x383891713  call    cs:__imp_QueryPerformanceCounter
0x383891719  mov     r11, qword ptr [rsp+28h+PerformanceCount]
0x38389171e  xor     r11, rbx
0x383891721  mov     rax, 0FFFFFFFFFFFFh
0x38389172b  and     r11, rax
0x38389172e  mov     rax, 2B992DDFA233h
0x383891738  cmp     r11, rdi
0x38389173b  cmovz   r11, rax
0x38389173f  mov     cs:__security_cookie, r11
0x383891746  not     r11
0x383891749  mov     cs:__security_cookie_complement, r11
0x383891750  mov     rbx, [rsp+28h+arg_10]
0x383891755  add     rsp, 20h
0x383891759  pop     rdi
0x38389175a  retn
0x383910348  not     rax
0x38391034b  mov     cs:__security_cookie_complement, rax
0x383910352  jmp     loc_383891750
```
