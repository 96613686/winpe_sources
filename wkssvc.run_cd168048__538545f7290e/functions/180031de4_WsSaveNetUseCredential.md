# WsSaveNetUseCredential

- ea: `0x180031de4`
- end: `0x180031f82`
- name: `WsSaveNetUseCredential`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001750`

## callees

- `0x18001fbd0`
- `0x1800204f6`
- `0x180031774`
- `0x180031de4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ef9`
- `SspiCli!SspiFreeAuthIdentity` at `0x180031eb7`
- `SspiCli!SspiFreeAuthIdentity` at `0x180031eb7`
- `SspiCli!SspiLocalFree` at `0x180031f10`
- `SspiCli!SspiLocalFree` at `0x180031f26`
- `SspiCli!SspiLocalFree` at `0x180031f56`
- `SspiCli!SspiLocalFree` at `0x180031f10`
- `SspiCli!SspiLocalFree` at `0x180031f26`
- `SspiCli!SspiLocalFree` at `0x180031f56`
- `SspiCli!SspiPrepareForCredWrite` at `0x180031ea4`
- `SspiCli!SspiPrepareForCredWrite` at `0x180031ea4`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180031e54`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180031e54`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180031ee9`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180031ee9`

## pseudocode

```c
__int64 __fastcall WsSaveNetUseCredential(__int64 a1, char *a2, unsigned int a3, DWORD *a4)
{
  DWORD LastError; // ebx
  LPBYTE CredentialBlob; // rcx
  __int64 CredentialBlobSize; // rax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+40h] [rbp-C0h] BYREF
  struct _CREDENTIALW Credential; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszTargetName[344]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(&Credential, 0, sizeof(Credential));
  ppAuthIdentity = 0;
  if ( !(unsigned int)ComputeTargetNameFromUncName(a1, pszTargetName)
    || SspiUnmarshalAuthIdentity(a3, a2, &ppAuthIdentity) )
  {
    return 87;
  }
  else
  {
    memset_0(&Credential, 0, sizeof(Credential));
    LastError = SspiPrepareForCredWrite(
                  ppAuthIdentity,
                  pszTargetName,
                  &Credential.Type,
                  (PCWSTR *)&Credential.TargetName,
                  (PCWSTR *)&Credential.UserName,
                  &Credential.CredentialBlob,
                  &Credential.CredentialBlobSize);
    SspiFreeAuthIdentity(ppAuthIdentity);
    ppAuthIdentity = 0;
    if ( !LastError )
    {
      *a4 = Credential.Type;
      Credential.Persist = 2;
      if ( !CredWriteW(&Credential, 0) )
        LastError = GetLastError();
      if ( Credential.UserName )
        SspiLocalFree(Credential.UserName);
      if ( Credential.TargetName )
        SspiLocalFree(Credential.TargetName);
      CredentialBlob = Credential.CredentialBlob;
      if ( Credential.CredentialBlob )
      {
        CredentialBlobSize = Credential.CredentialBlobSize;
        if ( Credential.CredentialBlobSize )
        {
          do
          {
            *CredentialBlob++ = 0;
            --CredentialBlobSize;
          }
          while ( CredentialBlobSize );
          CredentialBlob = Credential.CredentialBlob;
        }
        SspiLocalFree(CredentialBlob);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180031de4  push    rbp
0x180031de6  push    rbx
0x180031de7  push    rsi
0x180031de8  push    rdi
0x180031de9  push    r14
0x180031deb  lea     rbp, [rsp-260h]
0x180031df3  sub     rsp, 360h
0x180031dfa  mov     rax, cs:__security_cookie
0x180031e01  xor     rax, rsp
0x180031e04  mov     [rbp+280h+var_30], rax
0x180031e0b  mov     rdi, rdx
0x180031e0e  mov     esi, r8d
0x180031e11  xor     edx, edx; Val
0x180031e13  mov     rbx, rcx
0x180031e16  lea     rcx, [rsp+380h+Credential]; void *
0x180031e1b  mov     r14, r9
0x180031e1e  lea     r8d, [rdx+50h]; Size
0x180031e22  call    memset_0
0x180031e27  lea     rdx, [rbp+280h+pszTargetName]
0x180031e2b  mov     [rsp+380h+ppAuthIdentity], 0
0x180031e34  mov     rcx, rbx
0x180031e37  call    ComputeTargetNameFromUncName
0x180031e3c  test    eax, eax
0x180031e3e  jnz     short loc_180031E4A
0x180031e40  mov     ebx, 57h ; 'W'
0x180031e45  jmp     loc_180031F62
0x180031e4a  lea     r8, [rsp+380h+ppAuthIdentity]; ppAuthIdentity
0x180031e4f  mov     rdx, rdi; AuthIdentityByteArray
0x180031e52  mov     ecx, esi; AuthIdentityLength
0x180031e54  call    cs:__imp_SspiUnmarshalAuthIdentity
0x180031e5b  nop     dword ptr [rax+rax+00h]
0x180031e60  test    eax, eax
0x180031e62  jnz     short loc_180031E40
0x180031e64  xor     edx, edx; Val
0x180031e66  lea     r8d, [rax+50h]; Size
0x180031e6a  lea     rcx, [rsp+380h+Credential]; void *
0x180031e6f  call    memset_0
0x180031e74  mov     rcx, [rsp+380h+ppAuthIdentity]; AuthIdentity
0x180031e79  lea     rax, [rsp+380h+Credential.CredentialBlobSize]
0x180031e7e  mov     [rsp+380h+pCredentialBlobSize], rax; pCredentialBlobSize
0x180031e83  lea     r9, [rsp+380h+Credential.TargetName]; ppszCredmanTargetName
0x180031e88  lea     rax, [rsp+380h+Credential.CredentialBlob]
0x180031e8d  mov     [rsp+380h+ppCredentialBlob], rax; ppCredentialBlob
0x180031e92  lea     r8, [rsp+380h+Credential.Type]; pCredmanCredentialType
0x180031e97  lea     rax, [rbp+280h+Credential.UserName]
0x180031e9b  lea     rdx, [rbp+280h+pszTargetName]; pszTargetName
0x180031e9f  mov     [rsp+380h+ppszCredmanUserName], rax; ppszCredmanUserName
0x180031ea4  call    cs:__imp_SspiPrepareForCredWrite
0x180031eab  nop     dword ptr [rax+rax+00h]
0x180031eb0  mov     rcx, [rsp+380h+ppAuthIdentity]; AuthData
0x180031eb5  mov     ebx, eax
0x180031eb7  call    cs:__imp_SspiFreeAuthIdentity
0x180031ebe  nop     dword ptr [rax+rax+00h]
0x180031ec3  mov     [rsp+380h+ppAuthIdentity], 0
0x180031ecc  test    ebx, ebx
0x180031ece  jnz     loc_180031F62
0x180031ed4  mov     ecx, [rsp+380h+Credential.Type]
0x180031ed8  xor     edx, edx; Flags
0x180031eda  mov     [r14], ecx
0x180031edd  lea     rcx, [rsp+380h+Credential]; Credential
0x180031ee2  mov     [rbp+280h+Credential.Persist], 2
0x180031ee9  call    cs:__imp_CredWriteW
0x180031ef0  nop     dword ptr [rax+rax+00h]
0x180031ef5  test    eax, eax
0x180031ef7  jnz     short loc_180031F07
0x180031ef9  call    cs:__imp_GetLastError
0x180031f00  nop     dword ptr [rax+rax+00h]
0x180031f05  mov     ebx, eax
0x180031f07  mov     rcx, [rbp+280h+Credential.UserName]; DataBuffer
0x180031f0b  test    rcx, rcx
0x180031f0e  jz      short loc_180031F1C
0x180031f10  call    cs:__imp_SspiLocalFree
0x180031f17  nop     dword ptr [rax+rax+00h]
0x180031f1c  mov     rcx, [rsp+380h+Credential.TargetName]; DataBuffer
0x180031f21  test    rcx, rcx
0x180031f24  jz      short loc_180031F32
0x180031f26  call    cs:__imp_SspiLocalFree
0x180031f2d  nop     dword ptr [rax+rax+00h]
0x180031f32  mov     rcx, [rsp+380h+Credential.CredentialBlob]
0x180031f37  test    rcx, rcx
0x180031f3a  jz      short loc_180031F62
0x180031f3c  mov     eax, [rsp+380h+Credential.CredentialBlobSize]
0x180031f40  test    rax, rax
0x180031f43  jz      short loc_180031F56
0x180031f45  mov     byte ptr [rcx], 0
0x180031f48  inc     rcx
0x180031f4b  sub     rax, 1
0x180031f4f  jnz     short loc_180031F45
0x180031f51  mov     rcx, [rsp+380h+Credential.CredentialBlob]; DataBuffer
0x180031f56  call    cs:__imp_SspiLocalFree
0x180031f5d  nop     dword ptr [rax+rax+00h]
0x180031f62  mov     eax, ebx
0x180031f64  mov     rcx, [rbp+280h+var_30]
0x180031f6b  xor     rcx, rsp; StackCookie
0x180031f6e  call    __security_check_cookie
0x180031f73  add     rsp, 360h
0x180031f7a  pop     r14
0x180031f7c  pop     rdi
0x180031f7d  pop     rsi
0x180031f7e  pop     rbx
0x180031f7f  pop     rbp
0x180031f80  retn
```
