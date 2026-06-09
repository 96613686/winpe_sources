# DfsCredWrite

- ea: `0x1800258f0`
- end: `0x180025bb7`
- name: `DfsCredWrite`
- size: `711`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cdf0`
- `0x18001ed46`
- `0x1800258f0`

## import_xrefs

- `ntdll!DbgPrint` at `0x180025999`
- `ntdll!DbgPrint` at `0x180025999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025a34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800259fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025a34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b7d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025af3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025af3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025b8c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025b8c`
- `RPCRT4!RpcImpersonateClient` at `0x180025a69`
- `RPCRT4!RpcImpersonateClient` at `0x180025a69`
- `RPCRT4!RpcServerTestCancel` at `0x180025976`
- `RPCRT4!RpcServerTestCancel` at `0x180025976`
- `RPCRT4!RpcAsyncAbortCall` at `0x18002598a`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025b96`
- `RPCRT4!RpcAsyncAbortCall` at `0x18002598a`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025b96`
- `RPCRT4!I_RpcMapWin32Status` at `0x180025a71`
- `RPCRT4!I_RpcMapWin32Status` at `0x180025a71`
- `SspiCli!SspiFreeAuthIdentity` at `0x180025b53`
- `SspiCli!SspiFreeAuthIdentity` at `0x180025b53`
- `SspiCli!SspiLocalFree` at `0x180025b02`
- `SspiCli!SspiLocalFree` at `0x180025b11`
- `SspiCli!SspiLocalFree` at `0x180025b2f`
- `SspiCli!SspiLocalFree` at `0x180025b02`
- `SspiCli!SspiLocalFree` at `0x180025b11`
- `SspiCli!SspiLocalFree` at `0x180025b2f`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180025a9e`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180025a9e`
- `SspiCli!SspiPrepareForCredWrite` at `0x180025ad4`
- `SspiCli!SspiPrepareForCredWrite` at `0x180025ad4`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180025aed`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180025aed`

## string_xrefs

- `0x180025992`: `DfsCredWrite: RPC has been cancelled by client %X\n`

## pseudocode

```c
RPC_STATUS __fastcall DfsCredWrite(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  WCHAR *v8; // rdi
  WCHAR *v9; // r12
  WCHAR *v10; // r14
  unsigned __int16 *v11; // rbx
  unsigned int LastError; // ebx
  RPC_STATUS v13; // eax
  WCHAR *v14; // rax
  WCHAR *v15; // rax
  WCHAR *v16; // rax
  RPC_STATUS v17; // eax
  SECURITY_STATUS v18; // eax
  _CREDENTIALW Credential; // [rsp+40h] [rbp-31h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+E0h] [rbp+6Fh] BYREF

  memset_0(&Credential, 0, sizeof(Credential));
  ppAuthIdentity = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a3 && *a3 && a4 && *a4 && (v11 = a5) != 0 && *a5 )
  {
    if ( RpcServerTestCancel(a2) )
    {
      v14 = (WCHAR *)LocalAlloc(0x40u, *a3 + 2LL);
      v8 = v14;
      if ( !v14 )
        goto LABEL_10;
      memcpy_s(v14, *a3 + 2LL, *((const void *const *)a3 + 1), *a3);
      v8[(unsigned __int64)*a3 >> 1] = 0;
      v15 = (WCHAR *)LocalAlloc(0x40u, *a4 + 2LL);
      v9 = v15;
      if ( !v15 )
        goto LABEL_10;
      memcpy_s(v15, *a4 + 2LL, *((const void *const *)a4 + 1), *a4);
      v9[(unsigned __int64)*a4 >> 1] = 0;
      v16 = (WCHAR *)LocalAlloc(0x40u, *v11 + 2LL);
      v10 = v16;
      if ( v16 )
      {
        memcpy_s(v16, *v11 + 2LL, *((const void *const *)v11 + 1), *v11);
        v10[(unsigned __int64)*v11 >> 1] = 0;
        v17 = RpcImpersonateClient(0);
        LastError = I_RpcMapWin32Status(v17);
        if ( !LastError )
        {
          memset_0(&Credential, 0, sizeof(Credential));
          LastError = SspiEncodeStringsAsAuthIdentity(v9, 0, v10, &ppAuthIdentity);
          if ( !LastError )
          {
            v18 = SspiPrepareForCredWrite(
                    ppAuthIdentity,
                    v8,
                    &Credential.Type,
                    (PCWSTR *)&Credential.TargetName,
                    (PCWSTR *)&Credential.UserName,
                    &Credential.CredentialBlob,
                    &Credential.CredentialBlobSize);
            Credential.Persist = 1;
            LastError = v18;
            if ( !v18 )
              CredWriteW(&Credential, 0);
          }
          RevertToSelf();
          if ( Credential.UserName )
            SspiLocalFree(Credential.UserName);
          if ( Credential.TargetName )
            SspiLocalFree(Credential.TargetName);
          if ( Credential.CredentialBlob )
          {
            memset_0(Credential.CredentialBlob, 0, Credential.CredentialBlobSize);
            SspiLocalFree(Credential.CredentialBlob);
          }
          memset_0(&Credential, 0, sizeof(Credential));
        }
      }
      else
      {
LABEL_10:
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 0;
      v13 = RpcAsyncAbortCall(pAsync, 0x71Au);
      DbgPrint("DfsCredWrite: RPC has been cancelled by client %X\n", v13);
    }
  }
  else
  {
    LastError = 87;
  }
  if ( ppAuthIdentity )
    SspiFreeAuthIdentity(ppAuthIdentity);
  if ( v8 )
    LocalFree(v8);
  if ( v9 )
    LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
  if ( LastError )
    return RpcAsyncAbortCall(pAsync, LastError);
  else
    return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x1800258f0  mov     [rsp-8+arg_0], rbx
0x1800258f5  mov     [rsp-8+BindingHandle], rdx
0x1800258fa  push    rbp
0x1800258fb  push    rsi
0x1800258fc  push    rdi
0x1800258fd  push    r12
0x1800258ff  push    r13
0x180025901  push    r14
0x180025903  push    r15
0x180025905  lea     rbp, [rsp-1Fh]
0x18002590a  sub     rsp, 90h
0x180025911  xor     edx, edx; Val
0x180025913  mov     r15, r8
0x180025916  mov     r13, rcx
0x180025919  mov     rsi, r9
0x18002591c  lea     rcx, [rbp+4Fh+Credential]; void *
0x180025920  lea     r8d, [rdx+50h]; Size
0x180025924  call    memset_0
0x180025929  xor     ecx, ecx
0x18002592b  mov     [rbp+4Fh+ppAuthIdentity], rcx
0x18002592f  mov     edi, ecx
0x180025931  mov     r12d, ecx
0x180025934  mov     r14d, ecx
0x180025937  test    r15, r15
0x18002593a  jz      loc_180025B45
0x180025940  cmp     [r15], cx
0x180025944  jbe     loc_180025B45
0x18002594a  test    rsi, rsi
0x18002594d  jz      loc_180025B45
0x180025953  cmp     [rsi], cx
0x180025956  jbe     loc_180025B45
0x18002595c  mov     rbx, [rbp+4Fh+arg_20]
0x180025960  test    rbx, rbx
0x180025963  jz      loc_180025B45
0x180025969  cmp     [rbx], cx
0x18002596c  jbe     loc_180025B45
0x180025972  mov     rcx, [rbp+4Fh+BindingHandle]; BindingHandle
0x180025976  call    cs:__imp_RpcServerTestCancel
0x18002597c  test    eax, eax
0x18002597e  jnz     short loc_1800259A4
0x180025980  mov     edx, 71Ah; ExceptionCode
0x180025985  mov     rcx, r13; pAsync
0x180025988  xor     ebx, ebx
0x18002598a  call    cs:__imp_RpcAsyncAbortCall
0x180025990  mov     edx, eax
0x180025992  lea     rcx, aDfscredwriteRp; "DfsCredWrite: RPC has been cancelled by"...
0x180025999  call    cs:__imp_DbgPrint
0x18002599f  jmp     loc_180025B4A
0x1800259a4  movzx   edx, word ptr [r15]
0x1800259a8  mov     ecx, 40h ; '@'; uFlags
0x1800259ad  add     rdx, 2; uBytes
0x1800259b1  call    cs:__imp_LocalAlloc
0x1800259b7  mov     rdi, rax
0x1800259ba  test    rax, rax
0x1800259bd  jnz     short loc_1800259CC
0x1800259bf  call    cs:__imp_GetLastError
0x1800259c5  mov     ebx, eax
0x1800259c7  jmp     loc_180025B4A
0x1800259cc  movzx   r9d, word ptr [r15]; SourceSize
0x1800259d0  mov     rcx, rdi; Destination
0x1800259d3  mov     r8, [r15+8]; Source
0x1800259d7  lea     rdx, [r9+2]; DestinationSize
0x1800259db  call    memcpy_s
0x1800259e0  movzx   ecx, word ptr [r15]
0x1800259e4  xor     eax, eax
0x1800259e6  shr     rcx, 1
0x1800259e9  lea     r15d, [rax+40h]
0x1800259ed  mov     [rdi+rcx*2], ax
0x1800259f1  mov     ecx, r15d; uFlags
0x1800259f4  movzx   edx, word ptr [rsi]
0x1800259f7  add     rdx, 2; uBytes
0x1800259fb  call    cs:__imp_LocalAlloc
0x180025a01  mov     r12, rax
0x180025a04  test    rax, rax
0x180025a07  jz      short loc_1800259BF
0x180025a09  movzx   r9d, word ptr [rsi]; SourceSize
0x180025a0d  mov     rcx, rax; Destination
0x180025a10  mov     r8, [rsi+8]; Source
0x180025a14  lea     rdx, [r9+2]; DestinationSize
0x180025a18  call    memcpy_s
0x180025a1d  movzx   edx, word ptr [rsi]
0x180025a20  xor     eax, eax
0x180025a22  shr     rdx, 1
0x180025a25  mov     ecx, r15d; uFlags
0x180025a28  mov     [r12+rdx*2], ax
0x180025a2d  movzx   edx, word ptr [rbx]
0x180025a30  add     rdx, 2; uBytes
0x180025a34  call    cs:__imp_LocalAlloc
0x180025a3a  mov     r14, rax
0x180025a3d  test    rax, rax
0x180025a40  jz      loc_1800259BF
0x180025a46  movzx   r9d, word ptr [rbx]; SourceSize
0x180025a4a  mov     rcx, rax; Destination
0x180025a4d  mov     r8, [rbx+8]; Source
0x180025a51  lea     rdx, [r9+2]; DestinationSize
0x180025a55  call    memcpy_s
0x180025a5a  movzx   ecx, word ptr [rbx]
0x180025a5d  xor     eax, eax
0x180025a5f  shr     rcx, 1
0x180025a62  mov     [r14+rcx*2], ax
0x180025a67  xor     ecx, ecx; BindingHandle
0x180025a69  call    cs:__imp_RpcImpersonateClient
0x180025a6f  mov     ecx, eax; Status
0x180025a71  call    cs:__imp_I_RpcMapWin32Status
0x180025a77  mov     ebx, eax
0x180025a79  test    eax, eax
0x180025a7b  jnz     loc_180025B4A
0x180025a81  lea     esi, [rax+50h]
0x180025a84  xor     edx, edx; Val
0x180025a86  mov     r8d, esi; Size
0x180025a89  lea     rcx, [rbp+4Fh+Credential]; void *
0x180025a8d  call    memset_0
0x180025a92  lea     r9, [rbp+4Fh+ppAuthIdentity]; ppAuthIdentity
0x180025a96  mov     r8, r14; pszPackedCredentialsString
0x180025a99  xor     edx, edx; pszDomainName
0x180025a9b  mov     rcx, r12; pszUserName
0x180025a9e  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x180025aa4  mov     ebx, eax
0x180025aa6  test    eax, eax
0x180025aa8  jnz     short loc_180025AF3
0x180025aaa  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthIdentity
0x180025aae  lea     rax, [rbp+4Fh+Credential.CredentialBlobSize]
0x180025ab2  mov     [rsp+0C0h+pCredentialBlobSize], rax; pCredentialBlobSize
0x180025ab7  lea     r9, [rbp+4Fh+Credential.TargetName]; ppszCredmanTargetName
0x180025abb  lea     rax, [rbp+4Fh+Credential.CredentialBlob]
0x180025abf  mov     rdx, rdi; pszTargetName
0x180025ac2  mov     [rsp+0C0h+ppCredentialBlob], rax; ppCredentialBlob
0x180025ac7  lea     r8, [rbp+4Fh+Credential.Type]; pCredmanCredentialType
0x180025acb  lea     rax, [rbp+4Fh+Credential.UserName]
0x180025acf  mov     [rsp+0C0h+ppszCredmanUserName], rax; ppszCredmanUserName
0x180025ad4  call    cs:__imp_SspiPrepareForCredWrite
0x180025ada  mov     [rbp+4Fh+Credential.Persist], 1
0x180025ae1  mov     ebx, eax
0x180025ae3  test    eax, eax
0x180025ae5  jnz     short loc_180025AF3
0x180025ae7  xor     edx, edx; Flags
0x180025ae9  lea     rcx, [rbp+4Fh+Credential]; Credential
0x180025aed  call    cs:__imp_CredWriteW
0x180025af3  call    cs:__imp_RevertToSelf
0x180025af9  mov     rcx, [rbp+4Fh+Credential.UserName]; DataBuffer
0x180025afd  test    rcx, rcx
0x180025b00  jz      short loc_180025B08
0x180025b02  call    cs:__imp_SspiLocalFree
0x180025b08  mov     rcx, [rbp+4Fh+Credential.TargetName]; DataBuffer
0x180025b0c  test    rcx, rcx
0x180025b0f  jz      short loc_180025B17
0x180025b11  call    cs:__imp_SspiLocalFree
0x180025b17  mov     rcx, [rbp+4Fh+Credential.CredentialBlob]; void *
0x180025b1b  test    rcx, rcx
0x180025b1e  jz      short loc_180025B35
0x180025b20  mov     r8d, [rbp+4Fh+Credential.CredentialBlobSize]; Size
0x180025b24  xor     edx, edx; Val
0x180025b26  call    memset_0
0x180025b2b  mov     rcx, [rbp+4Fh+Credential.CredentialBlob]; DataBuffer
0x180025b2f  call    cs:__imp_SspiLocalFree
0x180025b35  mov     r8, rsi; Size
0x180025b38  lea     rcx, [rbp+4Fh+Credential]; void *
0x180025b3c  xor     edx, edx; Val
0x180025b3e  call    memset_0
0x180025b43  jmp     short loc_180025B4A
0x180025b45  mov     ebx, 57h ; 'W'
0x180025b4a  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x180025b4e  test    rcx, rcx
0x180025b51  jz      short loc_180025B59
0x180025b53  call    cs:__imp_SspiFreeAuthIdentity
0x180025b59  test    rdi, rdi
0x180025b5c  jz      short loc_180025B67
0x180025b5e  mov     rcx, rdi; hMem
0x180025b61  call    cs:__imp_LocalFree
0x180025b67  test    r12, r12
0x180025b6a  jz      short loc_180025B75
0x180025b6c  mov     rcx, r12; hMem
0x180025b6f  call    cs:__imp_LocalFree
0x180025b75  test    r14, r14
0x180025b78  jz      short loc_180025B83
0x180025b7a  mov     rcx, r14; hMem
0x180025b7d  call    cs:__imp_LocalFree
0x180025b83  mov     rcx, r13; pAsync
0x180025b86  test    ebx, ebx
0x180025b88  jnz     short loc_180025B94
0x180025b8a  xor     edx, edx; Reply
0x180025b8c  call    cs:__imp_RpcAsyncCompleteCall
0x180025b92  jmp     short loc_180025B9C
0x180025b94  mov     edx, ebx; ExceptionCode
0x180025b96  call    cs:__imp_RpcAsyncAbortCall
0x180025b9c  mov     rbx, [rsp+0C0h+arg_0]
0x180025ba4  add     rsp, 90h
0x180025bab  pop     r15
0x180025bad  pop     r14
0x180025baf  pop     r13
0x180025bb1  pop     r12
0x180025bb3  pop     rdi
0x180025bb4  pop     rsi
0x180025bb5  pop     rbp
0x180025bb6  retn
```
