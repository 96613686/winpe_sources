# DfsCredWrite

- ea: `0x180027680`
- end: `0x1800279cc`
- name: `DfsCredWrite`
- size: `844`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d998`
- `0x1800204f6`
- `0x180027680`

## import_xrefs

- `ntdll!DbgPrint` at `0x180027735`
- `ntdll!DbgPrint` at `0x180027735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027767`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800277a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800277e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800277a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800277e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002796b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002797f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002796b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002797f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800278cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800278cb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027994`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027994`
- `RPCRT4!RpcImpersonateClient` at `0x180027823`
- `RPCRT4!RpcImpersonateClient` at `0x180027823`
- `RPCRT4!RpcServerTestCancel` at `0x180027706`
- `RPCRT4!RpcServerTestCancel` at `0x180027706`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027720`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800279a4`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027720`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800279a4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180027831`
- `RPCRT4!I_RpcMapWin32Status` at `0x180027831`
- `SspiCli!SspiFreeAuthIdentity` at `0x180027943`
- `SspiCli!SspiFreeAuthIdentity` at `0x180027943`
- `SspiCli!SspiLocalFree` at `0x1800278e0`
- `SspiCli!SspiLocalFree` at `0x1800278f5`
- `SspiCli!SspiLocalFree` at `0x180027919`
- `SspiCli!SspiLocalFree` at `0x1800278e0`
- `SspiCli!SspiLocalFree` at `0x1800278f5`
- `SspiCli!SspiLocalFree` at `0x180027919`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180027864`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180027864`
- `SspiCli!SspiPrepareForCredWrite` at `0x1800278a0`
- `SspiCli!SspiPrepareForCredWrite` at `0x1800278a0`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x1800278bf`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x1800278bf`

## string_xrefs

- `0x18002772e`: `DfsCredWrite: RPC has been cancelled by client %X\n`

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
0x180027680  mov     [rsp-8+arg_0], rbx
0x180027685  mov     [rsp-8+BindingHandle], rdx
0x18002768a  push    rbp
0x18002768b  push    rsi
0x18002768c  push    rdi
0x18002768d  push    r12
0x18002768f  push    r13
0x180027691  push    r14
0x180027693  push    r15
0x180027695  lea     rbp, [rsp-1Fh]
0x18002769a  sub     rsp, 90h
0x1800276a1  xor     edx, edx; Val
0x1800276a3  mov     r15, r8
0x1800276a6  mov     r13, rcx
0x1800276a9  mov     rsi, r9
0x1800276ac  lea     rcx, [rbp+4Fh+Credential]; void *
0x1800276b0  lea     r8d, [rdx+50h]; Size
0x1800276b4  call    memset_0
0x1800276b9  xor     ecx, ecx
0x1800276bb  mov     [rbp+4Fh+ppAuthIdentity], rcx
0x1800276bf  mov     edi, ecx
0x1800276c1  mov     r12d, ecx
0x1800276c4  mov     r14d, ecx
0x1800276c7  test    r15, r15
0x1800276ca  jz      loc_180027935
0x1800276d0  cmp     [r15], cx
0x1800276d4  jbe     loc_180027935
0x1800276da  test    rsi, rsi
0x1800276dd  jz      loc_180027935
0x1800276e3  cmp     [rsi], cx
0x1800276e6  jbe     loc_180027935
0x1800276ec  mov     rbx, [rbp+4Fh+arg_20]
0x1800276f0  test    rbx, rbx
0x1800276f3  jz      loc_180027935
0x1800276f9  cmp     [rbx], cx
0x1800276fc  jbe     loc_180027935
0x180027702  mov     rcx, [rbp+4Fh+BindingHandle]; BindingHandle
0x180027706  call    cs:__imp_RpcServerTestCancel
0x18002770d  nop     dword ptr [rax+rax+00h]
0x180027712  test    eax, eax
0x180027714  jnz     short loc_180027746
0x180027716  mov     edx, 71Ah; ExceptionCode
0x18002771b  mov     rcx, r13; pAsync
0x18002771e  xor     ebx, ebx
0x180027720  call    cs:__imp_RpcAsyncAbortCall
0x180027727  nop     dword ptr [rax+rax+00h]
0x18002772c  mov     edx, eax
0x18002772e  lea     rcx, aDfscredwriteRp; "DfsCredWrite: RPC has been cancelled by"...
0x180027735  call    cs:__imp_DbgPrint
0x18002773c  nop     dword ptr [rax+rax+00h]
0x180027741  jmp     loc_18002793A
0x180027746  movzx   edx, word ptr [r15]
0x18002774a  mov     ecx, 40h ; '@'; uFlags
0x18002774f  add     rdx, 2; uBytes
0x180027753  call    cs:__imp_LocalAlloc
0x18002775a  nop     dword ptr [rax+rax+00h]
0x18002775f  mov     rdi, rax
0x180027762  test    rax, rax
0x180027765  jnz     short loc_18002777A
0x180027767  call    cs:__imp_GetLastError
0x18002776e  nop     dword ptr [rax+rax+00h]
0x180027773  mov     ebx, eax
0x180027775  jmp     loc_18002793A
0x18002777a  movzx   r9d, word ptr [r15]; SourceSize
0x18002777e  mov     rcx, rdi; Destination
0x180027781  mov     r8, [r15+8]; Source
0x180027785  lea     rdx, [r9+2]; DestinationSize
0x180027789  call    memcpy_s
0x18002778e  movzx   ecx, word ptr [r15]
0x180027792  xor     eax, eax
0x180027794  shr     rcx, 1
0x180027797  lea     r15d, [rax+40h]
0x18002779b  mov     [rdi+rcx*2], ax
0x18002779f  mov     ecx, r15d; uFlags
0x1800277a2  movzx   edx, word ptr [rsi]
0x1800277a5  add     rdx, 2; uBytes
0x1800277a9  call    cs:__imp_LocalAlloc
0x1800277b0  nop     dword ptr [rax+rax+00h]
0x1800277b5  mov     r12, rax
0x1800277b8  test    rax, rax
0x1800277bb  jz      short loc_180027767
0x1800277bd  movzx   r9d, word ptr [rsi]; SourceSize
0x1800277c1  mov     rcx, rax; Destination
0x1800277c4  mov     r8, [rsi+8]; Source
0x1800277c8  lea     rdx, [r9+2]; DestinationSize
0x1800277cc  call    memcpy_s
0x1800277d1  movzx   edx, word ptr [rsi]
0x1800277d4  xor     eax, eax
0x1800277d6  shr     rdx, 1
0x1800277d9  mov     ecx, r15d; uFlags
0x1800277dc  mov     [r12+rdx*2], ax
0x1800277e1  movzx   edx, word ptr [rbx]
0x1800277e4  add     rdx, 2; uBytes
0x1800277e8  call    cs:__imp_LocalAlloc
0x1800277ef  nop     dword ptr [rax+rax+00h]
0x1800277f4  mov     r14, rax
0x1800277f7  test    rax, rax
0x1800277fa  jz      loc_180027767
0x180027800  movzx   r9d, word ptr [rbx]; SourceSize
0x180027804  mov     rcx, rax; Destination
0x180027807  mov     r8, [rbx+8]; Source
0x18002780b  lea     rdx, [r9+2]; DestinationSize
0x18002780f  call    memcpy_s
0x180027814  movzx   ecx, word ptr [rbx]
0x180027817  xor     eax, eax
0x180027819  shr     rcx, 1
0x18002781c  mov     [r14+rcx*2], ax
0x180027821  xor     ecx, ecx; BindingHandle
0x180027823  call    cs:__imp_RpcImpersonateClient
0x18002782a  nop     dword ptr [rax+rax+00h]
0x18002782f  mov     ecx, eax; Status
0x180027831  call    cs:__imp_I_RpcMapWin32Status
0x180027838  nop     dword ptr [rax+rax+00h]
0x18002783d  mov     ebx, eax
0x18002783f  test    eax, eax
0x180027841  jnz     loc_18002793A
0x180027847  lea     esi, [rax+50h]
0x18002784a  xor     edx, edx; Val
0x18002784c  mov     r8d, esi; Size
0x18002784f  lea     rcx, [rbp+4Fh+Credential]; void *
0x180027853  call    memset_0
0x180027858  lea     r9, [rbp+4Fh+ppAuthIdentity]; ppAuthIdentity
0x18002785c  mov     r8, r14; pszPackedCredentialsString
0x18002785f  xor     edx, edx; pszDomainName
0x180027861  mov     rcx, r12; pszUserName
0x180027864  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x18002786b  nop     dword ptr [rax+rax+00h]
0x180027870  mov     ebx, eax
0x180027872  test    eax, eax
0x180027874  jnz     short loc_1800278CB
0x180027876  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthIdentity
0x18002787a  lea     rax, [rbp+4Fh+Credential.CredentialBlobSize]
0x18002787e  mov     [rsp+0C0h+pCredentialBlobSize], rax; pCredentialBlobSize
0x180027883  lea     r9, [rbp+4Fh+Credential.TargetName]; ppszCredmanTargetName
0x180027887  lea     rax, [rbp+4Fh+Credential.CredentialBlob]
0x18002788b  mov     rdx, rdi; pszTargetName
0x18002788e  mov     [rsp+0C0h+ppCredentialBlob], rax; ppCredentialBlob
0x180027893  lea     r8, [rbp+4Fh+Credential.Type]; pCredmanCredentialType
0x180027897  lea     rax, [rbp+4Fh+Credential.UserName]
0x18002789b  mov     [rsp+0C0h+ppszCredmanUserName], rax; ppszCredmanUserName
0x1800278a0  call    cs:__imp_SspiPrepareForCredWrite
0x1800278a7  nop     dword ptr [rax+rax+00h]
0x1800278ac  mov     [rbp+4Fh+Credential.Persist], 1
0x1800278b3  mov     ebx, eax
0x1800278b5  test    eax, eax
0x1800278b7  jnz     short loc_1800278CB
0x1800278b9  xor     edx, edx; Flags
0x1800278bb  lea     rcx, [rbp+4Fh+Credential]; Credential
0x1800278bf  call    cs:__imp_CredWriteW
0x1800278c6  nop     dword ptr [rax+rax+00h]
0x1800278cb  call    cs:__imp_RevertToSelf
0x1800278d2  nop     dword ptr [rax+rax+00h]
0x1800278d7  mov     rcx, [rbp+4Fh+Credential.UserName]; DataBuffer
0x1800278db  test    rcx, rcx
0x1800278de  jz      short loc_1800278EC
0x1800278e0  call    cs:__imp_SspiLocalFree
0x1800278e7  nop     dword ptr [rax+rax+00h]
0x1800278ec  mov     rcx, [rbp+4Fh+Credential.TargetName]; DataBuffer
0x1800278f0  test    rcx, rcx
0x1800278f3  jz      short loc_180027901
0x1800278f5  call    cs:__imp_SspiLocalFree
0x1800278fc  nop     dword ptr [rax+rax+00h]
0x180027901  mov     rcx, [rbp+4Fh+Credential.CredentialBlob]; void *
0x180027905  test    rcx, rcx
0x180027908  jz      short loc_180027925
0x18002790a  mov     r8d, [rbp+4Fh+Credential.CredentialBlobSize]; Size
0x18002790e  xor     edx, edx; Val
0x180027910  call    memset_0
0x180027915  mov     rcx, [rbp+4Fh+Credential.CredentialBlob]; DataBuffer
0x180027919  call    cs:__imp_SspiLocalFree
0x180027920  nop     dword ptr [rax+rax+00h]
0x180027925  mov     r8, rsi; Size
0x180027928  lea     rcx, [rbp+4Fh+Credential]; void *
0x18002792c  xor     edx, edx; Val
0x18002792e  call    memset_0
0x180027933  jmp     short loc_18002793A
0x180027935  mov     ebx, 57h ; 'W'
0x18002793a  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x18002793e  test    rcx, rcx
0x180027941  jz      short loc_18002794F
0x180027943  call    cs:__imp_SspiFreeAuthIdentity
0x18002794a  nop     dword ptr [rax+rax+00h]
0x18002794f  test    rdi, rdi
0x180027952  jz      short loc_180027963
0x180027954  mov     rcx, rdi; hMem
0x180027957  call    cs:__imp_LocalFree
0x18002795e  nop     dword ptr [rax+rax+00h]
0x180027963  test    r12, r12
0x180027966  jz      short loc_180027977
0x180027968  mov     rcx, r12; hMem
0x18002796b  call    cs:__imp_LocalFree
0x180027972  nop     dword ptr [rax+rax+00h]
0x180027977  test    r14, r14
0x18002797a  jz      short loc_18002798B
0x18002797c  mov     rcx, r14; hMem
0x18002797f  call    cs:__imp_LocalFree
0x180027986  nop     dword ptr [rax+rax+00h]
0x18002798b  mov     rcx, r13; pAsync
0x18002798e  test    ebx, ebx
0x180027990  jnz     short loc_1800279A2
0x180027992  xor     edx, edx; Reply
0x180027994  call    cs:__imp_RpcAsyncCompleteCall
0x18002799b  nop     dword ptr [rax+rax+00h]
0x1800279a0  jmp     short loc_1800279B0
0x1800279a2  mov     edx, ebx; ExceptionCode
0x1800279a4  call    cs:__imp_RpcAsyncAbortCall
0x1800279ab  nop     dword ptr [rax+rax+00h]
0x1800279b0  mov     rbx, [rsp+0C0h+arg_0]
0x1800279b8  add     rsp, 90h
0x1800279bf  pop     r15
0x1800279c1  pop     r14
0x1800279c3  pop     r13
0x1800279c5  pop     r12
0x1800279c7  pop     rdi
0x1800279c8  pop     rsi
0x1800279c9  pop     rbp
0x1800279ca  retn
```
