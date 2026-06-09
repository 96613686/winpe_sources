# WapAuthCompareIdentities

- ea: `0x1800692f8`
- end: `0x1800693ff`
- name: `WapAuthCompareIdentities`
- size: `263`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800046c4`
- `0x1800692b0`
- `0x18006af94`
- `0x18006c4dc`

## callees

- `0x1800692f8`
- `0x180069408`
- `0x1800722f0`

## import_xrefs

- `SspiCli!SspiCompareAuthIdentities` at `0x18006937c`
- `SspiCli!SspiCompareAuthIdentities` at `0x18006937c`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800693a5`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800693c9`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800693a5`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800693c9`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x180069344`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x180069344`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800693b5`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800693d8`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800693b5`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800693d8`

## pseudocode

```c
__int64 __fastcall WapAuthCompareIdentities(__int64 a1, void *a2, _BYTE *a3)
{
  void *v3; // rbx
  unsigned int v6; // edi
  unsigned int v7; // eax
  SECURITY_STATUS v8; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity1; // [rsp+20h] [rbp-20h] BYREF
  void *v11; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int8 SameSuppliedIdentity; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 SameSuppliedUser[7]; // [rsp+31h] [rbp-Fh] BYREF

  v3 = 0;
  AuthIdentity1 = 0;
  v11 = 0;
  SameSuppliedUser[0] = 0;
  SameSuppliedIdentity = 0;
  *a3 = 0;
  v6 = WaAuthDecryptAuthIdentity(a1, &AuthIdentity1);
  if ( !v6 )
  {
    if ( SspiIsAuthIdentityEncrypted(a2) )
    {
      v7 = WaAuthDecryptAuthIdentity(a2, &v11);
      v3 = v11;
      v6 = v7;
      if ( v7 )
        goto LABEL_9;
      a2 = v11;
    }
    v8 = SspiCompareAuthIdentities(AuthIdentity1, a2, SameSuppliedUser, &SameSuppliedIdentity);
    if ( v8 )
    {
      v6 = v8;
    }
    else if ( SameSuppliedIdentity )
    {
      *a3 = 1;
    }
  }
LABEL_9:
  if ( AuthIdentity1 )
  {
    SspiZeroAuthIdentity(AuthIdentity1);
    SspiFreeAuthIdentity(AuthIdentity1);
  }
  if ( v3 )
  {
    SspiZeroAuthIdentity(v3);
    SspiFreeAuthIdentity(v3);
  }
  return v6;
}

```

## disassembly

```asm
0x1800692f8  push    rbp
0x1800692fa  push    rbx
0x1800692fb  push    rdi
0x1800692fc  push    r14
0x1800692fe  push    r15
0x180069300  mov     rbp, rsp
0x180069303  sub     rsp, 40h
0x180069307  mov     rax, cs:__security_cookie
0x18006930e  xor     rax, rsp
0x180069311  mov     [rbp+var_8], rax
0x180069315  xor     ebx, ebx
0x180069317  mov     [rbp+AuthIdentity1], 0
0x18006931f  mov     r14, rdx
0x180069322  mov     [rbp+var_18], rbx
0x180069326  lea     rdx, [rbp+AuthIdentity1]
0x18006932a  mov     [rbp+SameSuppliedUser], bl
0x18006932d  mov     [rbp+SameSuppliedIdentity], bl
0x180069330  mov     r15, r8
0x180069333  mov     [r8], bl
0x180069336  call    WaAuthDecryptAuthIdentity
0x18006933b  mov     edi, eax
0x18006933d  test    eax, eax
0x18006933f  jnz     short loc_18006939A
0x180069341  mov     rcx, r14; EncryptedAuthData
0x180069344  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18006934b  nop     dword ptr [rax+rax+00h]
0x180069350  test    al, al
0x180069352  jz      short loc_18006936D
0x180069354  lea     rdx, [rbp+var_18]
0x180069358  mov     rcx, r14
0x18006935b  call    WaAuthDecryptAuthIdentity
0x180069360  mov     rbx, [rbp+var_18]
0x180069364  mov     edi, eax
0x180069366  test    eax, eax
0x180069368  jnz     short loc_18006939A
0x18006936a  mov     r14, rbx
0x18006936d  mov     rcx, [rbp+AuthIdentity1]; AuthIdentity1
0x180069371  lea     r9, [rbp+SameSuppliedIdentity]; SameSuppliedIdentity
0x180069375  lea     r8, [rbp+SameSuppliedUser]; SameSuppliedUser
0x180069379  mov     rdx, r14; AuthIdentity2
0x18006937c  call    cs:__imp_SspiCompareAuthIdentities
0x180069383  nop     dword ptr [rax+rax+00h]
0x180069388  test    eax, eax
0x18006938a  jz      short loc_180069390
0x18006938c  mov     edi, eax
0x18006938e  jmp     short loc_18006939A
0x180069390  cmp     [rbp+SameSuppliedIdentity], 0
0x180069394  jz      short loc_18006939A
0x180069396  mov     byte ptr [r15], 1
0x18006939a  cmp     [rbp+AuthIdentity1], 0
0x18006939f  jz      short loc_1800693C1
0x1800693a1  mov     rcx, [rbp+AuthIdentity1]; AuthData
0x1800693a5  call    cs:__imp_SspiZeroAuthIdentity
0x1800693ac  nop     dword ptr [rax+rax+00h]
0x1800693b1  mov     rcx, [rbp+AuthIdentity1]; AuthData
0x1800693b5  call    cs:__imp_SspiFreeAuthIdentity
0x1800693bc  nop     dword ptr [rax+rax+00h]
0x1800693c1  test    rbx, rbx
0x1800693c4  jz      short loc_1800693E4
0x1800693c6  mov     rcx, rbx; AuthData
0x1800693c9  call    cs:__imp_SspiZeroAuthIdentity
0x1800693d0  nop     dword ptr [rax+rax+00h]
0x1800693d5  mov     rcx, rbx; AuthData
0x1800693d8  call    cs:__imp_SspiFreeAuthIdentity
0x1800693df  nop     dword ptr [rax+rax+00h]
0x1800693e4  mov     eax, edi
0x1800693e6  mov     rcx, [rbp+var_8]
0x1800693ea  xor     rcx, rsp; StackCookie
0x1800693ed  call    __security_check_cookie
0x1800693f2  add     rsp, 40h
0x1800693f6  pop     r15
0x1800693f8  pop     r14
0x1800693fa  pop     rdi
0x1800693fb  pop     rbx
0x1800693fc  pop     rbp
0x1800693fd  retn
```
