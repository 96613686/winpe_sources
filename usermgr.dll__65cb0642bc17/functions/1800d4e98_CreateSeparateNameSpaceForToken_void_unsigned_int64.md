# CreateSeparateNameSpaceForToken(void *,unsigned __int64 *)

- ea: `0x1800d4e98`
- end: `0x1800d5019`
- name: `?CreateSeparateNameSpaceForToken@@YAJPEAXPEA_K@Z`
- size: `385`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18008ae08`
- `0x1800d40bc`

## callees

- `0x1800d4e98`
- `0x1800d5218`
- `0x1800de450`

## import_xrefs

- `ntdll!NtClose` at `0x1800d4fe9`
- `ntdll!NtClose` at `0x1800d4fe9`
- `ntdll!NtSetInformationToken` at `0x1800d4fac`
- `ntdll!NtSetInformationToken` at `0x1800d4fac`
- `ntdll!NtQueryInformationToken` at `0x1800d4f0a`
- `ntdll!NtQueryInformationToken` at `0x1800d4f36`
- `ntdll!NtQueryInformationToken` at `0x1800d4f0a`
- `ntdll!NtQueryInformationToken` at `0x1800d4f36`

## pseudocode

```c
__int64 __fastcall CreateSeparateNameSpaceForToken(HANDLE TokenHandle, unsigned __int64 *a2)
{
  int v4; // edi
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int64 i; // rbx
  HANDLE v8; // rcx
  ULONG ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-ACh] BYREF
  int v12; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handle[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *v14[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v15[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v16; // [rsp+90h] [rbp-70h] BYREF
  void *TokenInformation; // [rsp+A0h] [rbp-60h] BYREF

  v12 = 0;
  *a2 = 0;
  v16 = 0;
  v11 = 0;
  ReturnLength = 0;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)v14 = 0;
  *(_OWORD *)v15 = 0;
  v4 = NtQueryInformationToken(TokenHandle, TokenUser, &TokenInformation, 0x54u, &ReturnLength);
  if ( v4 < 0
    || (v4 = NtQueryInformationToken(TokenHandle, TokenSessionId, &v11, 4u, &ReturnLength), v4 < 0)
    || (v4 = CreateUserObjectDirectories(TokenInformation, v11, Handle, &Handle[1], v14, &v14[1], v15, &v15[1], &v16),
        v4 < 0)
    || (v12 = 1, v4 = NtSetInformationToken(TokenHandle, TokenIsRestricted|TokenGroups, &v12, 4u), v4 < 0) )
  {
    for ( i = 0; i != 7; ++i )
    {
      v8 = Handle[i];
      if ( v8 )
        NtClose(v8);
    }
  }
  else
  {
    v5 = *(_OWORD *)v14;
    *(_OWORD *)a2 = *(_OWORD *)Handle;
    v6 = *(_OWORD *)v15;
    *((_OWORD *)a2 + 1) = v5;
    *(_QWORD *)&v5 = v16;
    *((_OWORD *)a2 + 2) = v6;
    a2[6] = v5;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d4e98  mov     [rsp-8+arg_10], rbx
0x1800d4e9d  push    rbp
0x1800d4e9e  push    rsi
0x1800d4e9f  push    rdi
0x1800d4ea0  lea     rbp, [rsp-10h]
0x1800d4ea5  sub     rsp, 110h
0x1800d4eac  mov     rax, cs:__security_cookie
0x1800d4eb3  xor     rax, rsp
0x1800d4eb6  mov     [rbp+20h+var_20], rax
0x1800d4eba  xor     eax, eax
0x1800d4ebc  mov     [rsp+120h+var_C8], 0
0x1800d4ec4  xorps   xmm0, xmm0
0x1800d4ec7  mov     [rdx], rax
0x1800d4eca  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800d4ed0  mov     [rbp+20h+var_90], rax
0x1800d4ed4  mov     rbx, rdx
0x1800d4ed7  mov     [rsp+120h+var_CC], 0
0x1800d4edf  lea     rax, [rsp+120h+var_D0]
0x1800d4ee4  mov     [rsp+120h+var_D0], 0
0x1800d4eec  lea     r8, [rbp+20h+TokenInformation]; TokenInformation
0x1800d4ef0  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800d4ef5  lea     edx, [r9-53h]; TokenInformationClass
0x1800d4ef9  mov     rsi, rcx
0x1800d4efc  movups  xmmword ptr [rsp+120h+Handle], xmm0
0x1800d4f01  movups  xmmword ptr [rsp+120h+var_B0], xmm0
0x1800d4f06  movups  xmmword ptr [rbp+20h+var_A0], xmm0
0x1800d4f0a  call    cs:__imp_NtQueryInformationToken
0x1800d4f10  mov     edi, eax
0x1800d4f12  test    eax, eax
0x1800d4f14  js      loc_1800D4FDD
0x1800d4f1a  mov     r9d, 4; TokenInformationLength
0x1800d4f20  lea     rax, [rsp+120h+var_D0]
0x1800d4f25  lea     r8, [rsp+120h+var_CC]; TokenInformation
0x1800d4f2a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800d4f2f  mov     rcx, rsi; TokenHandle
0x1800d4f32  lea     edx, [r9+8]; TokenInformationClass
0x1800d4f36  call    cs:__imp_NtQueryInformationToken
0x1800d4f3c  mov     edi, eax
0x1800d4f3e  test    eax, eax
0x1800d4f40  js      loc_1800D4FDD
0x1800d4f46  mov     edx, [rsp+120h+var_CC]; unsigned int
0x1800d4f4a  lea     rax, [rbp+20h+var_90]
0x1800d4f4e  mov     rcx, [rbp+20h+TokenInformation]; void *
0x1800d4f52  lea     r9, [rsp+120h+Handle+8]; void **
0x1800d4f57  mov     [rsp+120h+var_E0], rax; void **
0x1800d4f5c  lea     r8, [rsp+120h+Handle]; void **
0x1800d4f61  lea     rax, [rbp+20h+var_A0+8]
0x1800d4f65  mov     [rsp+120h+var_E8], rax; void **
0x1800d4f6a  lea     rax, [rbp+20h+var_A0]
0x1800d4f6e  mov     [rsp+120h+var_F0], rax; void **
0x1800d4f73  lea     rax, [rsp+120h+var_B0+8]
0x1800d4f78  mov     [rsp+120h+var_F8], rax; void **
0x1800d4f7d  lea     rax, [rsp+120h+var_B0]
0x1800d4f82  mov     [rsp+120h+ReturnLength], rax; PHANDLE
0x1800d4f87  call    ?CreateUserObjectDirectories@@YAJPEAXKPEAPEAX111111@Z; CreateUserObjectDirectories(void *,ulong,void * *,void * *,void * *,void * *,void * *,void * *,void * *)
0x1800d4f8c  mov     edi, eax
0x1800d4f8e  test    eax, eax
0x1800d4f90  js      short loc_1800D4FDD
0x1800d4f92  mov     r9d, 4; TokenInformationLength
0x1800d4f98  mov     [rsp+120h+var_C8], 1
0x1800d4fa0  lea     r8, [rsp+120h+var_C8]; TokenInformation
0x1800d4fa5  mov     rcx, rsi; TokenHandle
0x1800d4fa8  lea     edx, [r9+26h]; TokenInformationClass
0x1800d4fac  call    cs:__imp_NtSetInformationToken
0x1800d4fb2  mov     edi, eax
0x1800d4fb4  test    eax, eax
0x1800d4fb6  js      short loc_1800D4FDD
0x1800d4fb8  movups  xmm0, xmmword ptr [rsp+120h+Handle]
0x1800d4fbd  movups  xmm1, xmmword ptr [rsp+120h+var_B0]
0x1800d4fc2  movups  xmmword ptr [rbx], xmm0
0x1800d4fc5  movups  xmm0, xmmword ptr [rbp+20h+var_A0]
0x1800d4fc9  movups  xmmword ptr [rbx+10h], xmm1
0x1800d4fcd  movsd   xmm1, [rbp+20h+var_90]
0x1800d4fd2  movups  xmmword ptr [rbx+20h], xmm0
0x1800d4fd6  movsd   qword ptr [rbx+30h], xmm1
0x1800d4fdb  jmp     short loc_1800D4FF8
0x1800d4fdd  xor     ebx, ebx
0x1800d4fdf  mov     rcx, [rsp+rbx*8+120h+Handle]; Handle
0x1800d4fe4  test    rcx, rcx
0x1800d4fe7  jz      short loc_1800D4FEF
0x1800d4fe9  call    cs:__imp_NtClose
0x1800d4fef  inc     rbx
0x1800d4ff2  cmp     rbx, 7
0x1800d4ff6  jnz     short loc_1800D4FDF
0x1800d4ff8  mov     eax, edi
0x1800d4ffa  mov     rcx, [rbp+20h+var_20]
0x1800d4ffe  xor     rcx, rsp; StackCookie
0x1800d5001  call    __security_check_cookie
0x1800d5006  mov     rbx, [rsp+120h+arg_10]
0x1800d500e  add     rsp, 110h
0x1800d5015  pop     rdi
0x1800d5016  pop     rsi
0x1800d5017  pop     rbp
0x1800d5018  retn
```
