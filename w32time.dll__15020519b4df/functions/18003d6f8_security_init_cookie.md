# __security_init_cookie

- ea: `0x18003d6f8`
- end: `0x18003d7ad`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d220`

## callees

- `0x18003d6f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d72d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d73b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d73b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d757`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d757`

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
0x18003d6f8  mov     [rsp-8+arg_10], rbx
0x18003d6fd  push    rbp
0x18003d6fe  mov     rbp, rsp
0x18003d701  sub     rsp, 30h
0x18003d705  mov     rax, cs:__security_cookie
0x18003d70c  mov     rbx, 2B992DDFA232h
0x18003d716  cmp     rax, rbx
0x18003d719  jnz     short loc_18003D798
0x18003d71b  xor     eax, eax
0x18003d71d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003d721  mov     [rbp+var_10], rax
0x18003d725  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003d729  mov     qword ptr [rbp+PerformanceCount], rax
0x18003d72d  call    cs:__imp_GetSystemTimeAsFileTime
0x18003d733  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003d737  mov     [rbp+var_10], rax
0x18003d73b  call    cs:__imp_GetCurrentThreadId
0x18003d741  mov     eax, eax
0x18003d743  xor     [rbp+var_10], rax
0x18003d747  call    cs:__imp_GetCurrentProcessId
0x18003d74d  mov     eax, eax
0x18003d74f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003d753  xor     [rbp+var_10], rax
0x18003d757  call    cs:__imp_QueryPerformanceCounter
0x18003d75d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003d760  lea     rcx, [rbp+var_10]
0x18003d764  shl     rax, 20h
0x18003d768  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003d76c  xor     rax, [rbp+var_10]
0x18003d770  xor     rax, rcx
0x18003d773  mov     rcx, 0FFFFFFFFFFFFh
0x18003d77d  and     rax, rcx
0x18003d780  mov     rcx, 2B992DDFA233h
0x18003d78a  cmp     rax, rbx
0x18003d78d  cmovz   rax, rcx
0x18003d791  mov     cs:__security_cookie, rax
0x18003d798  mov     rbx, [rsp+30h+arg_10]
0x18003d79d  not     rax
0x18003d7a0  mov     cs:__security_cookie_complement, rax
0x18003d7a7  add     rsp, 30h
0x18003d7ab  pop     rbp
0x18003d7ac  retn
```
