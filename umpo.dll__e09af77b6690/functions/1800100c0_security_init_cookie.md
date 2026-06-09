# __security_init_cookie

- ea: `0x1800100c0`
- end: `0x180010175`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010020`

## callees

- `0x1800100c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001010f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001010f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010103`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800100f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800100f5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001011f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001011f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800100c0  mov     [rsp-8+arg_10], rbx
0x1800100c5  push    rbp
0x1800100c6  mov     rbp, rsp
0x1800100c9  sub     rsp, 30h
0x1800100cd  mov     rax, cs:__security_cookie
0x1800100d4  mov     rbx, 2B992DDFA232h
0x1800100de  cmp     rax, rbx
0x1800100e1  jnz     short loc_180010160
0x1800100e3  xor     eax, eax
0x1800100e5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800100e9  mov     [rbp+var_10], rax
0x1800100ed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800100f1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800100f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800100fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800100ff  mov     [rbp+var_10], rax
0x180010103  call    cs:__imp_GetCurrentThreadId
0x180010109  mov     eax, eax
0x18001010b  xor     [rbp+var_10], rax
0x18001010f  call    cs:__imp_GetCurrentProcessId
0x180010115  mov     eax, eax
0x180010117  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001011b  xor     [rbp+var_10], rax
0x18001011f  call    cs:__imp_QueryPerformanceCounter
0x180010125  mov     eax, dword ptr [rbp+PerformanceCount]
0x180010128  lea     rcx, [rbp+var_10]
0x18001012c  shl     rax, 20h
0x180010130  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010134  xor     rax, [rbp+var_10]
0x180010138  xor     rax, rcx
0x18001013b  mov     rcx, 0FFFFFFFFFFFFh
0x180010145  and     rax, rcx
0x180010148  mov     rcx, 2B992DDFA233h
0x180010152  cmp     rax, rbx
0x180010155  cmovz   rax, rcx
0x180010159  mov     cs:__security_cookie, rax
0x180010160  mov     rbx, [rsp+30h+arg_10]
0x180010165  not     rax
0x180010168  mov     cs:__security_cookie_complement, rax
0x18001016f  add     rsp, 30h
0x180010173  pop     rbp
0x180010174  retn
```
