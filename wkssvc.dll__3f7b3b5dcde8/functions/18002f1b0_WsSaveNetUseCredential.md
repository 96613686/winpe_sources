# WsSaveNetUseCredential

- ea: `0x18002f1b0`
- end: `0x18002f319`
- name: `WsSaveNetUseCredential`
- size: `361`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001710`

## callees

- `0x18001e420`
- `0x18001ed46`
- `0x18002ebd4`
- `0x18002f1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a9`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002f277`
- `SspiCli!SspiFreeAuthIdentity` at `0x18002f277`
- `SspiCli!SspiLocalFree` at `0x18002f2ba`
- `SspiCli!SspiLocalFree` at `0x18002f2ca`
- `SspiCli!SspiLocalFree` at `0x18002f2f4`
- `SspiCli!SspiLocalFree` at `0x18002f2ba`
- `SspiCli!SspiLocalFree` at `0x18002f2ca`
- `SspiCli!SspiLocalFree` at `0x18002f2f4`
- `SspiCli!SspiPrepareForCredWrite` at `0x18002f26a`
- `SspiCli!SspiPrepareForCredWrite` at `0x18002f26a`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18002f220`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18002f220`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18002f29f`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18002f29f`

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
0x18002f1b0  push    rbp
0x18002f1b2  push    rbx
0x18002f1b3  push    rsi
0x18002f1b4  push    rdi
0x18002f1b5  push    r14
0x18002f1b7  lea     rbp, [rsp-260h]
0x18002f1bf  sub     rsp, 360h
0x18002f1c6  mov     rax, cs:__security_cookie
0x18002f1cd  xor     rax, rsp
0x18002f1d0  mov     [rbp+280h+var_30], rax
0x18002f1d7  mov     rdi, rdx
0x18002f1da  mov     esi, r8d
0x18002f1dd  xor     edx, edx; Val
0x18002f1df  mov     rbx, rcx
0x18002f1e2  lea     rcx, [rsp+380h+Credential]; void *
0x18002f1e7  mov     r14, r9
0x18002f1ea  lea     r8d, [rdx+50h]; Size
0x18002f1ee  call    memset_0
0x18002f1f3  lea     rdx, [rbp+280h+pszTargetName]
0x18002f1f7  mov     [rsp+380h+ppAuthIdentity], 0
0x18002f200  mov     rcx, rbx
0x18002f203  call    ComputeTargetNameFromUncName
0x18002f208  test    eax, eax
0x18002f20a  jnz     short loc_18002F216
0x18002f20c  mov     ebx, 57h ; 'W'
0x18002f211  jmp     loc_18002F2FA
0x18002f216  lea     r8, [rsp+380h+ppAuthIdentity]; ppAuthIdentity
0x18002f21b  mov     rdx, rdi; AuthIdentityByteArray
0x18002f21e  mov     ecx, esi; AuthIdentityLength
0x18002f220  call    cs:__imp_SspiUnmarshalAuthIdentity
0x18002f226  test    eax, eax
0x18002f228  jnz     short loc_18002F20C
0x18002f22a  xor     edx, edx; Val
0x18002f22c  lea     r8d, [rax+50h]; Size
0x18002f230  lea     rcx, [rsp+380h+Credential]; void *
0x18002f235  call    memset_0
0x18002f23a  mov     rcx, [rsp+380h+ppAuthIdentity]; AuthIdentity
0x18002f23f  lea     rax, [rsp+380h+Credential.CredentialBlobSize]
0x18002f244  mov     [rsp+380h+pCredentialBlobSize], rax; pCredentialBlobSize
0x18002f249  lea     r9, [rsp+380h+Credential.TargetName]; ppszCredmanTargetName
0x18002f24e  lea     rax, [rsp+380h+Credential.CredentialBlob]
0x18002f253  mov     [rsp+380h+ppCredentialBlob], rax; ppCredentialBlob
0x18002f258  lea     r8, [rsp+380h+Credential.Type]; pCredmanCredentialType
0x18002f25d  lea     rax, [rbp+280h+Credential.UserName]
0x18002f261  lea     rdx, [rbp+280h+pszTargetName]; pszTargetName
0x18002f265  mov     [rsp+380h+ppszCredmanUserName], rax; ppszCredmanUserName
0x18002f26a  call    cs:__imp_SspiPrepareForCredWrite
0x18002f270  mov     rcx, [rsp+380h+ppAuthIdentity]; AuthData
0x18002f275  mov     ebx, eax
0x18002f277  call    cs:__imp_SspiFreeAuthIdentity
0x18002f27d  mov     [rsp+380h+ppAuthIdentity], 0
0x18002f286  test    ebx, ebx
0x18002f288  jnz     short loc_18002F2FA
0x18002f28a  mov     ecx, [rsp+380h+Credential.Type]
0x18002f28e  xor     edx, edx; Flags
0x18002f290  mov     [r14], ecx
0x18002f293  lea     rcx, [rsp+380h+Credential]; Credential
0x18002f298  mov     [rbp+280h+Credential.Persist], 2
0x18002f29f  call    cs:__imp_CredWriteW
0x18002f2a5  test    eax, eax
0x18002f2a7  jnz     short loc_18002F2B1
0x18002f2a9  call    cs:__imp_GetLastError
0x18002f2af  mov     ebx, eax
0x18002f2b1  mov     rcx, [rbp+280h+Credential.UserName]; DataBuffer
0x18002f2b5  test    rcx, rcx
0x18002f2b8  jz      short loc_18002F2C0
0x18002f2ba  call    cs:__imp_SspiLocalFree
0x18002f2c0  mov     rcx, [rsp+380h+Credential.TargetName]; DataBuffer
0x18002f2c5  test    rcx, rcx
0x18002f2c8  jz      short loc_18002F2D0
0x18002f2ca  call    cs:__imp_SspiLocalFree
0x18002f2d0  mov     rcx, [rsp+380h+Credential.CredentialBlob]
0x18002f2d5  test    rcx, rcx
0x18002f2d8  jz      short loc_18002F2FA
0x18002f2da  mov     eax, [rsp+380h+Credential.CredentialBlobSize]
0x18002f2de  test    rax, rax
0x18002f2e1  jz      short loc_18002F2F4
0x18002f2e3  mov     byte ptr [rcx], 0
0x18002f2e6  inc     rcx
0x18002f2e9  sub     rax, 1
0x18002f2ed  jnz     short loc_18002F2E3
0x18002f2ef  mov     rcx, [rsp+380h+Credential.CredentialBlob]; DataBuffer
0x18002f2f4  call    cs:__imp_SspiLocalFree
0x18002f2fa  mov     eax, ebx
0x18002f2fc  mov     rcx, [rbp+280h+var_30]
0x18002f303  xor     rcx, rsp; StackCookie
0x18002f306  call    __security_check_cookie
0x18002f30b  add     rsp, 360h
0x18002f312  pop     r14
0x18002f314  pop     rdi
0x18002f315  pop     rsi
0x18002f316  pop     rbx
0x18002f317  pop     rbp
0x18002f318  retn
```
