# SendAndExpect(unsigned __int64,char *,char const *)

- ea: `0x180014f00`
- end: `0x180014fb1`
- name: `?SendAndExpect@@YAH_KPEADPEBD@Z`
- size: `177`
- prototype: `__int64 __fastcall(unsigned __int64, char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014c50`

## callees

- `0x180014c1c`
- `0x180014f00`
- `0x180029280`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x180014f82`
- `KERNEL32!CompareStringA` at `0x180014f82`
- `WS2_32!__imp_send` at `0x180014f41`
- `WS2_32!__imp_send` at `0x180014f41`

## pseudocode

```c
_BOOL8 __fastcall SendAndExpect(SOCKET a1, char *a2, const char *a3)
{
  __int64 cchCount2; // rbx
  __int64 v6; // r8
  int v7; // r8d
  CHAR String1[512]; // [rsp+30h] [rbp-228h] BYREF

  cchCount2 = -1;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  else
  {
    LODWORD(v6) = 0;
  }
  if ( send(a1, a2, v6, 0) == -1 )
    return 0;
  Read(a1, String1, v7);
  if ( a3 )
  {
    do
      ++cchCount2;
    while ( a3[cchCount2] );
  }
  else
  {
    LODWORD(cchCount2) = 0;
  }
  return CompareStringA(0x400u, 0, String1, cchCount2, a3, cchCount2) == 2;
}

```

## disassembly

```asm
0x180014f00  push    rbx
0x180014f02  push    rsi
0x180014f03  push    rdi
0x180014f04  sub     rsp, 240h
0x180014f0b  mov     rax, cs:__security_cookie
0x180014f12  xor     rax, rsp
0x180014f15  mov     [rsp+258h+var_28], rax
0x180014f1d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014f21  mov     rdi, r8
0x180014f24  mov     rsi, rcx
0x180014f27  test    rdx, rdx
0x180014f2a  jz      short loc_180014F3B
0x180014f2c  mov     r8, rbx
0x180014f2f  inc     r8
0x180014f32  cmp     byte ptr [rdx+r8], 0
0x180014f37  jnz     short loc_180014F2F
0x180014f39  jmp     short loc_180014F3E
0x180014f3b  xor     r8d, r8d; len
0x180014f3e  xor     r9d, r9d; flags
0x180014f41  call    cs:__imp_send
0x180014f47  cmp     eax, ebx
0x180014f49  jz      short loc_180014F94
0x180014f4b  lea     rdx, [rsp+258h+String1]; char *
0x180014f50  mov     rcx, rsi; unsigned __int64
0x180014f53  call    ?Read@@YAX_KPEADH@Z; Read(unsigned __int64,char *,int)
0x180014f58  test    rdi, rdi
0x180014f5b  jz      short loc_180014F68
0x180014f5d  inc     rbx
0x180014f60  cmp     byte ptr [rdi+rbx], 0
0x180014f64  jnz     short loc_180014F5D
0x180014f66  jmp     short loc_180014F6A
0x180014f68  xor     ebx, ebx
0x180014f6a  mov     [rsp+258h+cchCount2], ebx; cchCount2
0x180014f6e  lea     r8, [rsp+258h+String1]; lpString1
0x180014f73  mov     r9d, ebx; cchCount1
0x180014f76  mov     [rsp+258h+lpString2], rdi; lpString2
0x180014f7b  xor     edx, edx; dwCmpFlags
0x180014f7d  mov     ecx, 400h; Locale
0x180014f82  call    cs:__imp_CompareStringA
0x180014f88  xor     ecx, ecx
0x180014f8a  cmp     eax, 2
0x180014f8d  setz    cl
0x180014f90  mov     eax, ecx
0x180014f92  jmp     short loc_180014F96
0x180014f94  xor     eax, eax
0x180014f96  mov     rcx, [rsp+258h+var_28]
0x180014f9e  xor     rcx, rsp; StackCookie
0x180014fa1  call    __security_check_cookie
0x180014fa6  add     rsp, 240h
0x180014fad  pop     rdi
0x180014fae  pop     rsi
0x180014faf  pop     rbx
0x180014fb0  retn
```
