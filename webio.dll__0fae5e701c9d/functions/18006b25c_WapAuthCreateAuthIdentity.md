# WapAuthCreateAuthIdentity

- ea: `0x18006b25c`
- end: `0x18006b429`
- name: `WapAuthCreateAuthIdentity`
- size: `461`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180067030`
- `0x18006af94`
- `0x18006c4dc`

## callees

- `0x18006b25c`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `SspiCli!SspiEncryptAuthIdentity` at `0x18006b387`
- `SspiCli!SspiEncryptAuthIdentity` at `0x18006b387`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b3db`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b408`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b3db`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006b408`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006b36c`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006b36c`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x18006b3b5`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x18006b3b5`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b3eb`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b418`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b3eb`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006b418`

## pseudocode

```c
__int64 __fastcall WapAuthCreateAuthIdentity(
        int a1,
        const WCHAR *a2,
        const WCHAR *a3,
        char a4,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *a5)
{
  __int64 v6; // rsi
  unsigned int v9; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  _DWORD *v13; // rcx
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+20h] [rbp-41h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+28h] [rbp-39h] BYREF
  _DWORD AuthData[20]; // [rsp+30h] [rbp-31h] BYREF

  v6 = a1;
  memset_0(AuthData, 0, 0x48u);
  ppAuthIdentity = 0;
  AuthDataCopy = 0;
  *a5 = 0;
  if ( a2 )
  {
    if ( !a3 )
      return 87;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( v11 > 0x8000 || v12 > 0x8000 )
    {
      v9 = 87;
      goto LABEL_23;
    }
  }
  else if ( a3 || (byte_1800AC120[48 * v6] & 1) == 0 )
  {
    return 87;
  }
  if ( !a2 && !a3 )
  {
    AuthData[0] = 512;
    v13 = AuthData;
    AuthData[1] = 72;
    AuthData[13] = 2;
LABEL_16:
    v9 = SspiCopyAuthIdentity(v13, &AuthDataCopy);
    if ( !v9 && (!a4 || (v9 = SspiEncryptAuthIdentity(AuthDataCopy)) == 0) )
    {
      v9 = 0;
      *a5 = AuthDataCopy;
      AuthDataCopy = 0;
    }
    goto LABEL_23;
  }
  v9 = SspiEncodeStringsAsAuthIdentity(a2, 0, a3, &ppAuthIdentity);
  if ( !v9 )
  {
    v13 = ppAuthIdentity;
    goto LABEL_16;
  }
LABEL_23:
  if ( ppAuthIdentity )
  {
    SspiZeroAuthIdentity(ppAuthIdentity);
    SspiFreeAuthIdentity(ppAuthIdentity);
    ppAuthIdentity = 0;
  }
  if ( AuthDataCopy )
  {
    SspiZeroAuthIdentity(AuthDataCopy);
    SspiFreeAuthIdentity(AuthDataCopy);
  }
  return v9;
}

```

## disassembly

```asm
0x18006b25c  mov     [rsp-8+arg_0], rbx
0x18006b261  mov     [rsp-8+arg_18], rsi
0x18006b266  push    rbp
0x18006b267  push    rdi
0x18006b268  push    r12
0x18006b26a  push    r14
0x18006b26c  push    r15
0x18006b26e  lea     rbp, [rsp-2Fh]
0x18006b273  sub     rsp, 90h
0x18006b27a  mov     rax, cs:__security_cookie
0x18006b281  xor     rax, rsp
0x18006b284  mov     [rbp+4Fh+var_30], rax
0x18006b288  mov     r14, [rbp+4Fh+arg_20]
0x18006b28c  mov     rdi, rdx
0x18006b28f  xor     edx, edx; Val
0x18006b291  movsxd  rsi, ecx
0x18006b294  mov     rbx, r8
0x18006b297  lea     rcx, [rbp+4Fh+AuthData]; void *
0x18006b29b  mov     r15b, r9b
0x18006b29e  lea     r8d, [rdx+48h]; Size
0x18006b2a2  call    memset_0
0x18006b2a7  xor     r12d, r12d
0x18006b2aa  mov     [rbp+4Fh+ppAuthIdentity], r12
0x18006b2ae  mov     [rbp+4Fh+AuthDataCopy], r12
0x18006b2b2  mov     [r14], r12
0x18006b2b5  test    rdi, rdi
0x18006b2b8  jnz     short loc_18006B303
0x18006b2ba  test    rbx, rbx
0x18006b2bd  jnz     short loc_18006B2D3
0x18006b2bf  lea     rcx, [rsi+rsi*2]
0x18006b2c3  add     rcx, rcx
0x18006b2c6  lea     rax, byte_1800AC120
0x18006b2cd  test    byte ptr [rax+rcx*8], 1
0x18006b2d1  jnz     short loc_18006B345
0x18006b2d3  mov     ebx, 57h ; 'W'
0x18006b2d8  mov     eax, ebx
0x18006b2da  mov     rcx, [rbp+4Fh+var_30]
0x18006b2de  xor     rcx, rsp; StackCookie
0x18006b2e1  call    __security_check_cookie
0x18006b2e6  lea     r11, [rsp+0B0h+var_20]
0x18006b2ee  mov     rbx, [r11+30h]
0x18006b2f2  mov     rsi, [r11+48h]
0x18006b2f6  mov     rsp, r11
0x18006b2f9  pop     r15
0x18006b2fb  pop     r14
0x18006b2fd  pop     r12
0x18006b2ff  pop     rdi
0x18006b300  pop     rbp
0x18006b301  retn
0x18006b303  test    rbx, rbx
0x18006b306  jz      short loc_18006B2D3
0x18006b308  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006b30c  mov     rcx, r12
0x18006b30f  mov     rax, rdx
0x18006b312  inc     rax
0x18006b315  cmp     [rdi+rax*2], r12w
0x18006b31a  jnz     short loc_18006B312
0x18006b31c  test    rbx, rbx
0x18006b31f  jz      short loc_18006B32E
0x18006b321  mov     rcx, rdx
0x18006b324  inc     rcx
0x18006b327  cmp     [rbx+rcx*2], r12w
0x18006b32c  jnz     short loc_18006B324
0x18006b32e  mov     edx, 8000h
0x18006b333  cmp     rax, rdx
0x18006b336  ja      loc_18006B3CD
0x18006b33c  cmp     rcx, rdx
0x18006b33f  ja      loc_18006B3CD
0x18006b345  test    rdi, rdi
0x18006b348  jnz     short loc_18006B3A9
0x18006b34a  test    rbx, rbx
0x18006b34d  jnz     short loc_18006B3A9
0x18006b34f  mov     [rbp+4Fh+AuthData], 200h
0x18006b356  lea     rcx, [rbp+4Fh+AuthData]; AuthData
0x18006b35a  mov     [rbp+4Fh+var_7C], 48h ; 'H'
0x18006b361  mov     [rbp+4Fh+var_4C], 2
0x18006b368  lea     rdx, [rbp+4Fh+AuthDataCopy]; AuthDataCopy
0x18006b36c  call    cs:__imp_SspiCopyAuthIdentity
0x18006b373  nop     dword ptr [rax+rax+00h]
0x18006b378  mov     ebx, eax
0x18006b37a  test    eax, eax
0x18006b37c  jnz     short loc_18006B3D2
0x18006b37e  test    r15b, r15b
0x18006b381  jz      short loc_18006B399
0x18006b383  mov     rcx, [rbp+4Fh+AuthDataCopy]; AuthData
0x18006b387  call    cs:__imp_SspiEncryptAuthIdentity
0x18006b38e  nop     dword ptr [rax+rax+00h]
0x18006b393  mov     ebx, eax
0x18006b395  test    eax, eax
0x18006b397  jnz     short loc_18006B3D2
0x18006b399  mov     rax, [rbp+4Fh+AuthDataCopy]
0x18006b39d  mov     ebx, r12d
0x18006b3a0  mov     [r14], rax
0x18006b3a3  mov     [rbp+4Fh+AuthDataCopy], r12
0x18006b3a7  jmp     short loc_18006B3D2
0x18006b3a9  lea     r9, [rbp+4Fh+ppAuthIdentity]; ppAuthIdentity
0x18006b3ad  mov     r8, rbx; pszPackedCredentialsString
0x18006b3b0  xor     edx, edx; pszDomainName
0x18006b3b2  mov     rcx, rdi; pszUserName
0x18006b3b5  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x18006b3bc  nop     dword ptr [rax+rax+00h]
0x18006b3c1  mov     ebx, eax
0x18006b3c3  test    eax, eax
0x18006b3c5  jnz     short loc_18006B3D2
0x18006b3c7  mov     rcx, [rbp+4Fh+ppAuthIdentity]
0x18006b3cb  jmp     short loc_18006B368
0x18006b3cd  mov     ebx, 57h ; 'W'
0x18006b3d2  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x18006b3d6  test    rcx, rcx
0x18006b3d9  jz      short loc_18006B3FB
0x18006b3db  call    cs:__imp_SspiZeroAuthIdentity
0x18006b3e2  nop     dword ptr [rax+rax+00h]
0x18006b3e7  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x18006b3eb  call    cs:__imp_SspiFreeAuthIdentity
0x18006b3f2  nop     dword ptr [rax+rax+00h]
0x18006b3f7  mov     [rbp+4Fh+ppAuthIdentity], r12
0x18006b3fb  mov     rcx, [rbp+4Fh+AuthDataCopy]; AuthData
0x18006b3ff  test    rcx, rcx
0x18006b402  jz      loc_18006B2D8
0x18006b408  call    cs:__imp_SspiZeroAuthIdentity
0x18006b40f  nop     dword ptr [rax+rax+00h]
0x18006b414  mov     rcx, [rbp+4Fh+AuthDataCopy]; AuthData
0x18006b418  call    cs:__imp_SspiFreeAuthIdentity
0x18006b41f  nop     dword ptr [rax+rax+00h]
0x18006b424  jmp     loc_18006B2D8
```
