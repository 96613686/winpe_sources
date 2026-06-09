# TSUnpackAuthIdEx2LogonBuffer(_SEC_WINNT_AUTH_IDENTITY_EX2 *,uchar,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x18001a12c`
- end: `0x18001a344`
- name: `?TSUnpackAuthIdEx2LogonBuffer@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@EPEAU_UNICODE_STRING@@11@Z`
- size: `536`
- prototype: `__int64 __usercall@<rax>(PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity@<rcx>, unsigned __int8@<dl>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800029b0`
- `0x180008840`
- `0x180015304`
- `0x180016b38`

## callees

- `0x180007df0`
- `0x180008810`
- `0x18001a12c`
- `0x18001d010`

## import_xrefs

- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18001a1c9`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18001a1c9`
- `SspiCli!SspiFreeAuthIdentity` at `0x18001a2e9`
- `SspiCli!SspiFreeAuthIdentity` at `0x18001a2e9`
- `SspiCli!SspiEncodeAuthIdentityAsStrings` at `0x18001a25f`
- `SspiCli!SspiEncodeAuthIdentityAsStrings` at `0x18001a25f`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18001a22c`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18001a22c`
- `SspiCli!SspiValidateAuthIdentity` at `0x18001a1ad`
- `SspiCli!SspiValidateAuthIdentity` at `0x18001a1ad`
- `SspiCli!SspiLocalFree` at `0x18001a30f`
- `SspiCli!SspiLocalFree` at `0x18001a319`
- `SspiCli!SspiLocalFree` at `0x18001a323`
- `SspiCli!SspiLocalFree` at `0x18001a30f`
- `SspiCli!SspiLocalFree` at `0x18001a319`
- `SspiCli!SspiLocalFree` at `0x18001a323`
- `SspiCli!SspiCopyAuthIdentity` at `0x18001a1da`
- `SspiCli!SspiCopyAuthIdentity` at `0x18001a1da`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a238`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a238`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a273`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a287`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a29b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a273`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a287`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a29b`

## pseudocode

```c
__int64 __fastcall TSUnpackAuthIdEx2LogonBuffer(
        unsigned __int16 *pAuthIdentity,
        char a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  struct _UNICODE_STRING *v5; // r12
  unsigned __int16 *v7; // rcx
  bool v11; // zf
  SECURITY_STATUS inited; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  int v17; // esi
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v18; // rcx
  unsigned __int8 v19; // r8
  unsigned __int8 v20; // r8
  unsigned __int8 v21; // r8
  PCWSTR ppszUserName; // [rsp+20h] [rbp-50h] BYREF
  PCWSTR ppszDomainName; // [rsp+28h] [rbp-48h] BYREF
  PCWSTR ppszPackedCredentialsString; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING v27; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING v28; // [rsp+58h] [rbp-18h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+A0h] [rbp+30h] BYREF

  v5 = a5;
  v7 = 0;
  *a3 = 0;
  *a4 = 0;
  AuthDataCopy = 0;
  *v5 = 0;
  v11 = *(_DWORD *)pAuthIdentity == 513;
  ppszUserName = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  DestinationString = 0;
  v27 = 0;
  v28 = 0;
  if ( v11 && pAuthIdentity[2] >= 0x30u && *((_DWORD *)pAuthIdentity + 2) >= (unsigned int)pAuthIdentity[2] )
  {
    inited = SspiValidateAuthIdentity(pAuthIdentity);
    if ( inited < 0 )
      goto LABEL_24;
    if ( !a2 || !SspiIsAuthIdentityEncrypted(pAuthIdentity) )
    {
      v18 = pAuthIdentity;
      AuthDataCopy = pAuthIdentity;
LABEL_17:
      inited = SspiEncodeAuthIdentityAsStrings(v18, &ppszUserName, &ppszDomainName, &ppszPackedCredentialsString);
      if ( inited >= 0 )
      {
        inited = RtlInitUnicodeStringEx(&DestinationString, ppszUserName);
        if ( inited >= 0 )
        {
          inited = RtlInitUnicodeStringEx(&v27, ppszDomainName);
          if ( inited >= 0 )
          {
            inited = RtlInitUnicodeStringEx(&v28, ppszPackedCredentialsString);
            if ( inited >= 0 )
            {
              inited = TSDuplicateStringEx(a3, &DestinationString, v19);
              if ( inited >= 0 )
              {
                inited = TSDuplicateStringEx(a4, &v27, v20);
                if ( inited >= 0 )
                  inited = TSDuplicateStringEx(v5, &v28, v21);
              }
            }
          }
        }
      }
      goto LABEL_24;
    }
    inited = SspiCopyAuthIdentity(pAuthIdentity, &AuthDataCopy);
    if ( inited < 0 )
      goto LABEL_24;
    v7 = (unsigned __int16 *)AuthDataCopy;
    v16 = *((_DWORD *)AuthDataCopy + 9);
    if ( (v16 & 0x40) != 0 )
    {
      inited = ((__int64 (__fastcall *)(PSEC_WINNT_AUTH_IDENTITY_OPAQUE, __int64, __int64, __int64, PCWSTR, PCWSTR, PCWSTR, _QWORD, PWSTR))TSGlobalLsaFunctions->ImpersonateClient)(
                 AuthDataCopy,
                 v13,
                 v14,
                 v15,
                 ppszUserName,
                 ppszDomainName,
                 ppszPackedCredentialsString,
                 *(_QWORD *)&DestinationString.Length,
                 DestinationString.Buffer);
      if ( inited >= 0 )
      {
        v7 = (unsigned __int16 *)AuthDataCopy;
        v17 = 1;
LABEL_12:
        inited = SspiDecryptAuthIdentityEx(1u, v7);
        if ( v17 )
          RevertToSelf();
        if ( inited < 0 )
          goto LABEL_24;
        v18 = AuthDataCopy;
        goto LABEL_17;
      }
LABEL_24:
      v7 = (unsigned __int16 *)AuthDataCopy;
      goto LABEL_26;
    }
    v17 = 0;
    if ( (v16 & 0x20) != 0 )
      goto LABEL_12;
  }
  inited = -1073741811;
LABEL_26:
  if ( v7 != pAuthIdentity )
    SspiFreeAuthIdentity(v7);
  if ( inited < 0 )
  {
    TSFreeString(a3);
    TSFreeString(a4);
    TSFreeString(v5);
  }
  SspiLocalFree((PVOID)ppszUserName);
  SspiLocalFree((PVOID)ppszDomainName);
  SspiLocalFree((PVOID)ppszPackedCredentialsString);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001a12c  mov     [rsp-28h+arg_8], rbx
0x18001a131  mov     [rsp-28h+arg_10], rsi
0x18001a136  push    rbp
0x18001a137  push    rdi
0x18001a138  push    r12
0x18001a13a  push    r14
0x18001a13c  push    r15
0x18001a13e  mov     rbp, rsp
0x18001a141  sub     rsp, 70h
0x18001a145  mov     r12, [rbp+arg_20]
0x18001a149  xorps   xmm1, xmm1
0x18001a14c  xorps   xmm0, xmm0
0x18001a14f  mov     rdi, rcx
0x18001a152  xor     ecx, ecx; AuthData
0x18001a154  mov     r14, r9
0x18001a157  movups  xmmword ptr [r8], xmm1
0x18001a15b  mov     r15, r8
0x18001a15e  mov     sil, dl
0x18001a161  movups  xmmword ptr [r9], xmm0
0x18001a165  mov     [rbp+AuthDataCopy], rcx
0x18001a169  movups  xmmword ptr [r12], xmm1
0x18001a16e  cmp     dword ptr [rdi], 201h
0x18001a174  mov     [rbp+ppszUserName], rcx
0x18001a178  mov     [rbp+ppszDomainName], rcx
0x18001a17c  mov     [rbp+ppszPackedCredentialsString], rcx
0x18001a180  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a184  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x18001a188  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x18001a18c  jnz     loc_18001A2DF
0x18001a192  cmp     word ptr [rdi+4], 30h ; '0'
0x18001a197  jb      loc_18001A2DF
0x18001a19d  movzx   eax, word ptr [rdi+4]
0x18001a1a1  cmp     [rdi+8], eax
0x18001a1a4  jb      loc_18001A2DF
0x18001a1aa  mov     rcx, rdi; AuthData
0x18001a1ad  call    cs:__imp_SspiValidateAuthIdentity
0x18001a1b3  mov     ebx, eax
0x18001a1b5  test    eax, eax
0x18001a1b7  js      loc_18001A2D9
0x18001a1bd  test    sil, sil
0x18001a1c0  jz      loc_18001A24C
0x18001a1c6  mov     rcx, rdi; EncryptedAuthData
0x18001a1c9  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18001a1cf  test    al, al
0x18001a1d1  jz      short loc_18001A24C
0x18001a1d3  lea     rdx, [rbp+AuthDataCopy]; AuthDataCopy
0x18001a1d7  mov     rcx, rdi; AuthData
0x18001a1da  call    cs:__imp_SspiCopyAuthIdentity
0x18001a1e0  mov     ebx, eax
0x18001a1e2  test    eax, eax
0x18001a1e4  js      loc_18001A2D9
0x18001a1ea  mov     rcx, [rbp+AuthDataCopy]
0x18001a1ee  mov     eax, [rcx+24h]
0x18001a1f1  test    al, 40h
0x18001a1f3  jz      short loc_18001A21A
0x18001a1f5  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18001a1fc  mov     rax, [rax+58h]
0x18001a200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a205  mov     ebx, eax
0x18001a207  test    eax, eax
0x18001a209  js      loc_18001A2D9
0x18001a20f  mov     rcx, [rbp+AuthDataCopy]
0x18001a213  mov     esi, 1
0x18001a218  jmp     short loc_18001A224
0x18001a21a  xor     esi, esi
0x18001a21c  test    al, 20h
0x18001a21e  jz      loc_18001A2DF
0x18001a224  mov     rdx, rcx; EncryptedAuthData
0x18001a227  mov     ecx, 1; Options
0x18001a22c  call    cs:__imp_SspiDecryptAuthIdentityEx
0x18001a232  mov     ebx, eax
0x18001a234  test    esi, esi
0x18001a236  jz      short loc_18001A23E
0x18001a238  call    cs:__imp_RevertToSelf
0x18001a23e  test    ebx, ebx
0x18001a240  js      loc_18001A2D9
0x18001a246  mov     rcx, [rbp+AuthDataCopy]
0x18001a24a  jmp     short loc_18001A253
0x18001a24c  mov     rcx, rdi; pAuthIdentity
0x18001a24f  mov     [rbp+AuthDataCopy], rcx
0x18001a253  lea     r9, [rbp+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x18001a257  lea     r8, [rbp+ppszDomainName]; ppszDomainName
0x18001a25b  lea     rdx, [rbp+ppszUserName]; ppszUserName
0x18001a25f  call    cs:__imp_SspiEncodeAuthIdentityAsStrings
0x18001a265  mov     ebx, eax
0x18001a267  test    eax, eax
0x18001a269  js      short loc_18001A2D9
0x18001a26b  mov     rdx, [rbp+ppszUserName]; SourceString
0x18001a26f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001a273  call    cs:__imp_RtlInitUnicodeStringEx
0x18001a279  mov     ebx, eax
0x18001a27b  test    eax, eax
0x18001a27d  js      short loc_18001A2D9
0x18001a27f  mov     rdx, [rbp+ppszDomainName]; SourceString
0x18001a283  lea     rcx, [rbp+var_28]; DestinationString
0x18001a287  call    cs:__imp_RtlInitUnicodeStringEx
0x18001a28d  mov     ebx, eax
0x18001a28f  test    eax, eax
0x18001a291  js      short loc_18001A2D9
0x18001a293  mov     rdx, [rbp+ppszPackedCredentialsString]; SourceString
0x18001a297  lea     rcx, [rbp+var_18]; DestinationString
0x18001a29b  call    cs:__imp_RtlInitUnicodeStringEx
0x18001a2a1  mov     ebx, eax
0x18001a2a3  test    eax, eax
0x18001a2a5  js      short loc_18001A2D9
0x18001a2a7  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x18001a2ab  mov     rcx, r15; struct _UNICODE_STRING *
0x18001a2ae  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18001a2b3  mov     ebx, eax
0x18001a2b5  test    eax, eax
0x18001a2b7  js      short loc_18001A2D9
0x18001a2b9  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x18001a2bd  mov     rcx, r14; struct _UNICODE_STRING *
0x18001a2c0  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18001a2c5  mov     ebx, eax
0x18001a2c7  test    eax, eax
0x18001a2c9  js      short loc_18001A2D9
0x18001a2cb  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x18001a2cf  mov     rcx, r12; struct _UNICODE_STRING *
0x18001a2d2  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18001a2d7  mov     ebx, eax
0x18001a2d9  mov     rcx, [rbp+AuthDataCopy]
0x18001a2dd  jmp     short loc_18001A2E4
0x18001a2df  mov     ebx, 0C000000Dh
0x18001a2e4  cmp     rcx, rdi
0x18001a2e7  jz      short loc_18001A2EF
0x18001a2e9  call    cs:__imp_SspiFreeAuthIdentity
0x18001a2ef  test    ebx, ebx
0x18001a2f1  jns     short loc_18001A30B
0x18001a2f3  mov     rcx, r15; struct _UNICODE_STRING *
0x18001a2f6  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x18001a2fb  mov     rcx, r14; struct _UNICODE_STRING *
0x18001a2fe  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x18001a303  mov     rcx, r12; struct _UNICODE_STRING *
0x18001a306  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x18001a30b  mov     rcx, [rbp+ppszUserName]; DataBuffer
0x18001a30f  call    cs:__imp_SspiLocalFree
0x18001a315  mov     rcx, [rbp+ppszDomainName]; DataBuffer
0x18001a319  call    cs:__imp_SspiLocalFree
0x18001a31f  mov     rcx, [rbp+ppszPackedCredentialsString]; DataBuffer
0x18001a323  call    cs:__imp_SspiLocalFree
0x18001a329  lea     r11, [rsp+70h+var_s0]
0x18001a32e  mov     eax, ebx
0x18001a330  mov     rbx, [r11+38h]
0x18001a334  mov     rsi, [r11+40h]
0x18001a338  mov     rsp, r11
0x18001a33b  pop     r15
0x18001a33d  pop     r14
0x18001a33f  pop     r12
0x18001a341  pop     rdi
0x18001a342  pop     rbp
0x18001a343  retn
```
