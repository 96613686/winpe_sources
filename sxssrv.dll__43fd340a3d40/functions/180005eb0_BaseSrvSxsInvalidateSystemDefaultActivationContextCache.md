# BaseSrvSxsInvalidateSystemDefaultActivationContextCache

- ea: `0x180005eb0`
- end: `0x180005fc6`
- name: `BaseSrvSxsInvalidateSystemDefaultActivationContextCache`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005eb0`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180005ede`
- `ntdll!RtlEnterCriticalSection` at `0x180005ede`
- `ntdll!RtlLeaveCriticalSection` at `0x180005f24`
- `ntdll!RtlLeaveCriticalSection` at `0x180005f24`
- `ntdll!RtlLeaveCriticalSection` at `0x180007055`
- `ntdll!NtClose` at `0x180005f3a`
- `ntdll!NtClose` at `0x180005f50`
- `ntdll!NtClose` at `0x180005f66`
- `ntdll!NtClose` at `0x180005f7c`
- `ntdll!NtClose` at `0x180005f92`
- `ntdll!NtClose` at `0x180005f3a`
- `ntdll!NtClose` at `0x180005f50`
- `ntdll!NtClose` at `0x180005f66`
- `ntdll!NtClose` at `0x180005f7c`
- `ntdll!NtClose` at `0x180005f92`

## pseudocode

```c
__int64 BaseSrvSxsInvalidateSystemDefaultActivationContextCache()
{
  __int64 i; // r8
  __int64 v1; // rcx
  HANDLE Handle[2]; // [rsp+28h] [rbp-40h]
  HANDLE v4[2]; // [rsp+38h] [rbp-30h]
  HANDLE v5; // [rsp+48h] [rbp-20h]

  *(_OWORD *)Handle = 0;
  *(_OWORD *)v4 = 0;
  v5 = 0;
  RtlEnterCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  for ( i = 0; (_DWORD)i != 5; i = (unsigned int)(i + 1) )
  {
    v1 = 4LL * (unsigned int)i;
    Handle[i] = (HANDLE)SxsSystemDefaultActivationContexts[v1];
    SxsSystemDefaultActivationContexts[v1] = 0;
  }
  RtlLeaveCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
  if ( Handle[0] )
    NtClose(Handle[0]);
  if ( Handle[1] )
    NtClose(Handle[1]);
  if ( v4[0] )
    NtClose(v4[0]);
  if ( v4[1] )
    NtClose(v4[1]);
  if ( v5 )
    NtClose(v5);
  return 0;
}

```

## disassembly

```asm
0x180005eb0  sub     rsp, 68h
0x180005eb4  mov     rax, cs:__security_cookie
0x180005ebb  xor     rax, rsp
0x180005ebe  mov     [rsp+68h+var_18], rax
0x180005ec3  xorps   xmm0, xmm0
0x180005ec6  xor     eax, eax
0x180005ec8  movups  xmmword ptr [rsp+68h+Handle], xmm0
0x180005ecd  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x180005ed2  mov     [rsp+68h+var_20], rax
0x180005ed7  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180005ede  call    cs:__imp_RtlEnterCriticalSection
0x180005ee5  nop     dword ptr [rax+rax+00h]
0x180005eea  nop
0x180005eeb  xor     r8d, r8d
0x180005eee  lea     r9, SxsSystemDefaultActivationContexts
0x180005ef5  mov     [rsp+68h+var_48], r8d
0x180005efa  cmp     r8d, 5
0x180005efe  jz      short loc_180005F1D
0x180005f00  mov     ecx, r8d
0x180005f03  shl     rcx, 5
0x180005f07  mov     rax, [rcx+r9]
0x180005f0b  mov     [rsp+r8*8+68h+Handle], rax
0x180005f10  mov     qword ptr [rcx+r9], 0
0x180005f18  inc     r8d
0x180005f1b  jmp     short loc_180005EF5
0x180005f1d  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x180005f24  call    cs:__imp_RtlLeaveCriticalSection
0x180005f2b  nop     dword ptr [rax+rax+00h]
0x180005f30  mov     rcx, [rsp+68h+Handle]; Handle
0x180005f35  test    rcx, rcx
0x180005f38  jz      short loc_180005F46
0x180005f3a  call    cs:__imp_NtClose
0x180005f41  nop     dword ptr [rax+rax+00h]
0x180005f46  mov     rcx, [rsp+68h+Handle+8]; Handle
0x180005f4b  test    rcx, rcx
0x180005f4e  jz      short loc_180005F5C
0x180005f50  call    cs:__imp_NtClose
0x180005f57  nop     dword ptr [rax+rax+00h]
0x180005f5c  mov     rcx, [rsp+68h+var_30]; Handle
0x180005f61  test    rcx, rcx
0x180005f64  jz      short loc_180005F72
0x180005f66  call    cs:__imp_NtClose
0x180005f6d  nop     dword ptr [rax+rax+00h]
0x180005f72  mov     rcx, [rsp+68h+var_30+8]; Handle
0x180005f77  test    rcx, rcx
0x180005f7a  jz      short loc_180005F88
0x180005f7c  call    cs:__imp_NtClose
0x180005f83  nop     dword ptr [rax+rax+00h]
0x180005f88  mov     rcx, [rsp+68h+var_20]; Handle
0x180005f8d  test    rcx, rcx
0x180005f90  jz      short loc_180005F9E
0x180005f92  call    cs:__imp_NtClose
0x180005f99  nop     dword ptr [rax+rax+00h]
0x180005f9e  xor     eax, eax
0x180005fa0  mov     rcx, [rsp+68h+var_18]
0x180005fa5  xor     rcx, rsp; StackCookie
0x180005fa8  call    __security_check_cookie
0x180005fad  add     rsp, 68h
0x180005fb1  retn
0x180005fb3  mov     rcx, [rsp+68h+var_18]
0x180005fb8  xor     rcx, rsp; StackCookie
0x180005fbb  call    __security_check_cookie
0x180005fc0  add     rsp, 68h
0x180005fc4  retn
0x180007040  push    rbp
0x180007042  sub     rsp, 20h
0x180007046  mov     rbp, rdx
0x180007049  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection
0x180007050  add     rsp, 20h
0x180007054  pop     rbp
0x180007055  jmp     cs:__imp_RtlLeaveCriticalSection
```
