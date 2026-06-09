# WaAuthDecryptAuthIdentity

- ea: `0x180069408`
- end: `0x1800694b0`
- name: `WaAuthDecryptAuthIdentity`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180069050`
- `0x1800692f8`
- `0x18008c3e0`
- `0x18008cdc0`

## callees

- `0x180069408`
- `0x1800722f0`

## import_xrefs

- `SspiCli!SspiZeroAuthIdentity` at `0x180069491`
- `SspiCli!SspiZeroAuthIdentity` at `0x180069491`
- `SspiCli!SspiCopyAuthIdentity` at `0x180069439`
- `SspiCli!SspiCopyAuthIdentity` at `0x180069439`
- `SspiCli!SspiDecryptAuthIdentity` at `0x180069450`
- `SspiCli!SspiDecryptAuthIdentity` at `0x180069450`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800694a2`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800694a2`

## pseudocode

```c
__int64 __fastcall WaAuthDecryptAuthIdentity(void *a1, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *a2)
{
  SECURITY_STATUS v3; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v4; // rcx
  unsigned int v5; // ebx
  SECURITY_STATUS v6; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  AuthDataCopy = 0;
  v3 = SspiCopyAuthIdentity(a1, &AuthDataCopy);
  v4 = AuthDataCopy;
  v5 = v3;
  if ( !v3 )
  {
    v6 = SspiDecryptAuthIdentity(AuthDataCopy);
    v4 = AuthDataCopy;
    v5 = v6;
    if ( !v6 )
    {
      *a2 = AuthDataCopy;
      v4 = 0;
      AuthDataCopy = 0;
    }
  }
  if ( v4 )
  {
    SspiZeroAuthIdentity(v4);
    SspiFreeAuthIdentity(AuthDataCopy);
  }
  return v5;
}

```

## disassembly

```asm
0x180069408  mov     [rsp+arg_10], rbx
0x18006940d  push    rdi
0x18006940e  sub     rsp, 30h
0x180069412  mov     rax, cs:__security_cookie
0x180069419  xor     rax, rsp
0x18006941c  mov     [rsp+38h+var_10], rax
0x180069421  mov     rdi, rdx
0x180069424  mov     qword ptr [rdx], 0
0x18006942b  lea     rdx, [rsp+38h+AuthDataCopy]; AuthDataCopy
0x180069430  mov     [rsp+38h+AuthDataCopy], 0
0x180069439  call    cs:__imp_SspiCopyAuthIdentity
0x180069440  nop     dword ptr [rax+rax+00h]
0x180069445  mov     rcx, [rsp+38h+AuthDataCopy]; EncryptedAuthData
0x18006944a  mov     ebx, eax
0x18006944c  test    eax, eax
0x18006944e  jnz     short loc_180069471
0x180069450  call    cs:__imp_SspiDecryptAuthIdentity
0x180069457  nop     dword ptr [rax+rax+00h]
0x18006945c  mov     rcx, [rsp+38h+AuthDataCopy]
0x180069461  mov     ebx, eax
0x180069463  test    eax, eax
0x180069465  jnz     short loc_180069471
0x180069467  mov     [rdi], rcx
0x18006946a  xor     ecx, ecx; AuthData
0x18006946c  mov     [rsp+38h+AuthDataCopy], rcx
0x180069471  test    rcx, rcx
0x180069474  jnz     short loc_180069491
0x180069476  mov     eax, ebx
0x180069478  mov     rcx, [rsp+38h+var_10]
0x18006947d  xor     rcx, rsp; StackCookie
0x180069480  call    __security_check_cookie
0x180069485  mov     rbx, [rsp+38h+arg_10]
0x18006948a  add     rsp, 30h
0x18006948e  pop     rdi
0x18006948f  retn
0x180069491  call    cs:__imp_SspiZeroAuthIdentity
0x180069498  nop     dword ptr [rax+rax+00h]
0x18006949d  mov     rcx, [rsp+38h+AuthDataCopy]; AuthData
0x1800694a2  call    cs:__imp_SspiFreeAuthIdentity
0x1800694a9  nop     dword ptr [rax+rax+00h]
0x1800694ae  jmp     short loc_180069476
```
