# BaseSrvSxsInvalidateSystemDefaultActivationContextCache

- ea: `0x180005de0`
- end: `0x180005f02`
- name: `BaseSrvSxsInvalidateSystemDefaultActivationContextCache`
- size: `290`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005de0`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180005e10`
- `ntdll!RtlEnterCriticalSection` at `0x180005e10`
- `ntdll!RtlLeaveCriticalSection` at `0x180005e60`
- `ntdll!RtlLeaveCriticalSection` at `0x180005e60`
- `ntdll!RtlLeaveCriticalSection` at `0x180006f95`
- `ntdll!NtClose` at `0x180005e76`
- `ntdll!NtClose` at `0x180005e8c`
- `ntdll!NtClose` at `0x180005ea2`
- `ntdll!NtClose` at `0x180005eb8`
- `ntdll!NtClose` at `0x180005ecc`
- `ntdll!NtClose` at `0x180005e76`
- `ntdll!NtClose` at `0x180005e8c`
- `ntdll!NtClose` at `0x180005ea2`
- `ntdll!NtClose` at `0x180005eb8`
- `ntdll!NtClose` at `0x180005ecc`

## pseudocode

```c
__int64 BaseSrvSxsInvalidateSystemDefaultActivationContextCache()
{
  void *v0; // rbx
  __int64 v1; // r8
  __int64 v2; // rcx
  HANDLE Handle[2]; // [rsp+28h] [rbp-40h]
  HANDLE v5[2]; // [rsp+38h] [rbp-30h]
  void *v6; // [rsp+48h] [rbp-20h]

  v0 = 0;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)v5 = 0;
  v6 = 0;
  RtlEnterCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  v1 = 0;
  while ( (_DWORD)v1 != 5 )
  {
    v2 = 4LL * (unsigned int)v1;
    Handle[v1] = (HANDLE)SxsSystemDefaultActivationContexts[v2];
    SxsSystemDefaultActivationContexts[v2] = 0;
    v1 = (unsigned int)(v1 + 1);
    v0 = v6;
  }
  RtlLeaveCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  if ( Handle[0] )
    NtClose(Handle[0]);
  if ( Handle[1] )
    NtClose(Handle[1]);
  if ( v5[0] )
    NtClose(v5[0]);
  if ( v5[1] )
    NtClose(v5[1]);
  if ( v0 )
    NtClose(v0);
  return 0;
}

```

## disassembly

```asm
0x180005de0  push    rbx
0x180005de2  sub     rsp, 60h
0x180005de6  mov     rax, cs:__security_cookie
0x180005ded  xor     rax, rsp
0x180005df0  mov     [rsp+68h+var_18], rax
0x180005df5  xorps   xmm0, xmm0
0x180005df8  xor     ebx, ebx
0x180005dfa  movups  xmmword ptr [rsp+68h+Handle], xmm0
0x180005dff  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x180005e04  mov     [rsp+68h+var_20], rbx
0x180005e09  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180005e10  call    cs:__imp_RtlEnterCriticalSection
0x180005e17  nop     dword ptr [rax+rax+00h]
0x180005e1c  nop
0x180005e1d  xor     r8d, r8d
0x180005e20  mov     [rsp+68h+var_48], r8d
0x180005e25  lea     r9, SxsSystemDefaultActivationContexts
0x180005e2c  cmp     r8d, 5
0x180005e30  jz      short loc_180005E59
0x180005e32  mov     ecx, r8d
0x180005e35  shl     rcx, 5
0x180005e39  mov     rax, [rcx+r9]
0x180005e3d  mov     [rsp+r8*8+68h+Handle], rax
0x180005e42  mov     qword ptr [rcx+r9], 0
0x180005e4a  inc     r8d
0x180005e4d  mov     [rsp+68h+var_48], r8d
0x180005e52  mov     rbx, [rsp+68h+var_20]
0x180005e57  jmp     short loc_180005E2C
0x180005e59  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180005e60  call    cs:__imp_RtlLeaveCriticalSection
0x180005e67  nop     dword ptr [rax+rax+00h]
0x180005e6c  mov     rcx, [rsp+68h+Handle]; Handle
0x180005e71  test    rcx, rcx
0x180005e74  jz      short loc_180005E82
0x180005e76  call    cs:__imp_NtClose
0x180005e7d  nop     dword ptr [rax+rax+00h]
0x180005e82  mov     rcx, [rsp+68h+Handle+8]; Handle
0x180005e87  test    rcx, rcx
0x180005e8a  jz      short loc_180005E98
0x180005e8c  call    cs:__imp_NtClose
0x180005e93  nop     dword ptr [rax+rax+00h]
0x180005e98  mov     rcx, [rsp+68h+var_30]; Handle
0x180005e9d  test    rcx, rcx
0x180005ea0  jz      short loc_180005EAE
0x180005ea2  call    cs:__imp_NtClose
0x180005ea9  nop     dword ptr [rax+rax+00h]
0x180005eae  mov     rcx, [rsp+68h+var_30+8]; Handle
0x180005eb3  test    rcx, rcx
0x180005eb6  jz      short loc_180005EC4
0x180005eb8  call    cs:__imp_NtClose
0x180005ebf  nop     dword ptr [rax+rax+00h]
0x180005ec4  test    rbx, rbx
0x180005ec7  jz      short loc_180005ED8
0x180005ec9  mov     rcx, rbx; Handle
0x180005ecc  call    cs:__imp_NtClose
0x180005ed3  nop     dword ptr [rax+rax+00h]
0x180005ed8  xor     eax, eax
0x180005eda  mov     rcx, [rsp+68h+var_18]
0x180005edf  xor     rcx, rsp; StackCookie
0x180005ee2  call    __security_check_cookie
0x180005ee7  add     rsp, 60h
0x180005eeb  pop     rbx
0x180005eec  retn
0x180005eee  mov     rcx, [rsp+68h+var_18]
0x180005ef3  xor     rcx, rsp; StackCookie
0x180005ef6  call    __security_check_cookie
0x180005efb  add     rsp, 60h
0x180005eff  pop     rbx
0x180005f00  retn
0x180006f80  push    rbp
0x180006f82  sub     rsp, 20h
0x180006f86  mov     rbp, rdx
0x180006f89  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection
0x180006f90  add     rsp, 20h
0x180006f94  pop     rbp
0x180006f95  jmp     cs:__imp_RtlLeaveCriticalSection
```
