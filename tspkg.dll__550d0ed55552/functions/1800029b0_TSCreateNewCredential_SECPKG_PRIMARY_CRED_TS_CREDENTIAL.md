# TSCreateNewCredential(_SECPKG_PRIMARY_CRED *,_TS_CREDENTIAL * *)

- ea: `0x1800029b0`
- end: `0x180002e40`
- name: `?TSCreateNewCredential@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_TS_CREDENTIAL@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(struct _SECPKG_PRIMARY_CRED *, struct _TS_CREDENTIAL **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002570`

## callees

- `0x1800029b0`
- `0x1800032c0`
- `0x180003340`
- `0x1800034b0`
- `0x180003830`
- `0x1800053d0`
- `0x180005ed0`
- `0x18000c1a4`
- `0x18001627c`
- `0x1800162a4`
- `0x18001a12c`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180002a41`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180002a41`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x180002a8f`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x180002a8f`
- `SspiCli!SspiFreeAuthIdentity` at `0x180002ad0`
- `SspiCli!SspiFreeAuthIdentity` at `0x180002afa`
- `SspiCli!SspiFreeAuthIdentity` at `0x180002ad0`
- `SspiCli!SspiFreeAuthIdentity` at `0x180002afa`

## pseudocode

```c
__int64 __fastcall TSCreateNewCredential(struct _SECPKG_PRIMARY_CRED *a1, struct _TS_CREDENTIAL **a2)
{
  struct _TS_PRIMARY_CREDENTIAL *v2; // rsi
  int v5; // eax
  struct _TS_CREDENTIAL *v6; // r14
  int v7; // ebx
  ULONG Flags; // eax
  unsigned int v9; // eax
  SECURITY_STATUS v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r15
  void *v15; // rax
  UNICODE_STRING *p_DownlevelName; // rbx
  int Length; // eax
  __int16 v18; // r13
  void *v19; // rax
  UNICODE_STRING *p_DomainName; // rbx
  int v21; // eax
  __int16 v22; // r13
  void *v23; // rax
  UNICODE_STRING *p_Password; // rdi
  USHORT v25; // dx
  __int16 v26; // bx
  USHORT v27; // bx
  void *v28; // rax
  size_t MaximumLength; // r8
  __int64 result; // rax
  struct _UNICODE_STRING v31; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING v32; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v33; // [rsp+50h] [rbp-20h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+A0h] [rbp+30h] BYREF
  struct _TS_PRIMARY_CREDENTIAL *v35; // [rsp+B0h] [rbp+40h] BYREF

  v2 = 0;
  ppAuthIdentity = 0;
  v35 = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  v5 = TSAllocateCredential((struct _TS_CREDENTIAL **)&ppAuthIdentity);
  v6 = (struct _TS_CREDENTIAL *)ppAuthIdentity;
  v7 = v5;
  if ( v5 < 0 )
    goto LABEL_68;
  *((_QWORD *)ppAuthIdentity + 14) = a1->LogonId;
  Flags = a1->Flags;
  if ( (Flags & 0x200) == 0 )
  {
    if ( (Flags & 1) == 0 )
      goto LABEL_67;
    if ( TSGlobalState == 1 )
    {
      v14 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(232);
    }
    else
    {
      v15 = (void *)((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(232);
      v14 = (__int64)v15;
      if ( v15 )
      {
        memset_0(v15, 0, 0xE8u);
        goto LABEL_28;
      }
    }
    if ( !v14 )
    {
      v7 = -1073741670;
      goto LABEL_58;
    }
LABEL_28:
    p_DownlevelName = &a1->DownlevelName;
    if ( a1 == (struct _SECPKG_PRIMARY_CRED *)-8LL || !a1->DownlevelName.Buffer )
    {
      *(_QWORD *)(v14 + 32) = 0;
      *(_DWORD *)(v14 + 24) = 0;
    }
    else
    {
      Length = p_DownlevelName->Length;
      if ( (unsigned __int16)Length > 0xFFFCu )
      {
        *(_QWORD *)(v14 + 32) = 0;
        v7 = -1073741562;
LABEL_64:
        TSFreePrimaryCredentials((struct _TS_PRIMARY_CREDENTIAL *)v14);
        goto LABEL_58;
      }
      v18 = Length + 2;
      v19 = TSAllocate((unsigned int)(Length + 2));
      *(_QWORD *)(v14 + 32) = v19;
      if ( !v19 )
      {
        v7 = -1073741670;
        goto LABEL_64;
      }
      *(_WORD *)(v14 + 24) = p_DownlevelName->Length;
      *(_WORD *)(v14 + 26) = v18;
      memcpy_0(v19, a1->DownlevelName.Buffer, p_DownlevelName->Length);
      *(_WORD *)(*(_QWORD *)(v14 + 32) + 2 * ((unsigned __int64)p_DownlevelName->Length >> 1)) = 0;
    }
    p_DomainName = &a1->DomainName;
    if ( a1 == (struct _SECPKG_PRIMARY_CRED *)-24LL || !a1->DomainName.Buffer )
    {
      *(_QWORD *)(v14 + 16) = 0;
      *(_DWORD *)(v14 + 8) = 0;
    }
    else
    {
      v21 = p_DomainName->Length;
      if ( (unsigned __int16)v21 > 0xFFFCu )
      {
        *(_QWORD *)(v14 + 16) = 0;
        v7 = -1073741562;
        goto LABEL_64;
      }
      v22 = v21 + 2;
      v23 = TSAllocate((unsigned int)(v21 + 2));
      *(_QWORD *)(v14 + 16) = v23;
      if ( !v23 )
      {
        v7 = -1073741670;
        goto LABEL_64;
      }
      *(_WORD *)(v14 + 8) = p_DomainName->Length;
      *(_WORD *)(v14 + 10) = v22;
      memcpy_0(v23, a1->DomainName.Buffer, p_DomainName->Length);
      *(_WORD *)(*(_QWORD *)(v14 + 16) + 2 * ((unsigned __int64)p_DomainName->Length >> 1)) = 0;
    }
    p_Password = &a1->Password;
    if ( p_Password->Buffer )
    {
      *(_QWORD *)(v14 + 48) = 0;
      *(_DWORD *)(v14 + 40) = 0;
      if ( p_Password )
      {
        if ( p_Password->Buffer )
        {
          v25 = p_Password->Length;
          v26 = 0;
          if ( (p_Password->Length & 7) != 0 )
            v26 = 8 - (p_Password->Length & 7);
          if ( v25 > 0xFFF4u )
          {
            v7 = -1073741717;
            goto LABEL_64;
          }
          v27 = v25 + v26;
          if ( v27 < v25 )
          {
            v7 = -1073741717;
            TSFreePrimaryCredentials((struct _TS_PRIMARY_CREDENTIAL *)v14);
            goto LABEL_58;
          }
          v28 = TSAllocate(v27);
          *(_QWORD *)(v14 + 48) = v28;
          if ( !v28 )
          {
            v7 = -1073741801;
            goto LABEL_64;
          }
          *(_WORD *)(v14 + 40) = p_Password->Length;
          *(_WORD *)(v14 + 42) = v27;
          if ( v27 == p_Password->MaximumLength )
            MaximumLength = p_Password->MaximumLength;
          else
            MaximumLength = p_Password->Length;
          memcpy_0(v28, p_Password->Buffer, MaximumLength);
        }
      }
    }
    *(_DWORD *)v14 = 1;
    v2 = (struct _TS_PRIMARY_CREDENTIAL *)v14;
    v7 = 0;
    goto LABEL_58;
  }
  v9 = a1->Password.Length;
  ppAuthIdentity = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( v9 < 0x30 )
  {
LABEL_67:
    v7 = -1073741811;
    goto LABEL_68;
  }
  v10 = SspiUnmarshalAuthIdentity(v9, (char *)a1->Password.Buffer, &ppAuthIdentity);
  v7 = v10;
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 34;
      v13 = (unsigned int)v10;
LABEL_10:
      WPP_SF_d(v11[2], v12, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, v13);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  if ( SspiIsAuthIdentityEncrypted(ppAuthIdentity) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids);
    v7 = -1073741811;
    SspiFreeAuthIdentity(ppAuthIdentity);
LABEL_17:
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 36;
      v13 = (unsigned int)v7;
      goto LABEL_10;
    }
LABEL_68:
    if ( v6 )
      TSDereferenceCredential(v6);
    return (unsigned int)v7;
  }
  v7 = TSUnpackAuthIdEx2LogonBuffer((unsigned __int16 *)ppAuthIdentity, 0, &v31, &v32, &v33);
  SspiFreeAuthIdentity(ppAuthIdentity);
  if ( v7 < 0 )
    goto LABEL_17;
  v7 = TSInitPrimaryCreds(&v31, &v32, &v33, &v35);
  TSFree(&v31);
  TSFree(&v32);
  TSFree(&v33);
  v2 = v35;
LABEL_58:
  if ( v7 < 0 )
  {
    if ( v2 )
      TSFreePrimaryCredentials(v2);
    goto LABEL_68;
  }
  if ( v2 != (struct _TS_PRIMARY_CREDENTIAL *)-40LL )
    ((void (__fastcall *)(_QWORD, _QWORD))TSGlobalLsaFunctions->LsaProtectMemory)(
      *((_QWORD *)v2 + 6),
      *((unsigned __int16 *)v2 + 21));
  *((_QWORD *)v6 + 17) = v2;
  result = (unsigned int)v7;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800029b0  push    rbp
0x1800029b2  push    rbx
0x1800029b3  push    rsi
0x1800029b4  push    rdi
0x1800029b5  push    r12
0x1800029b7  mov     rbp, rsp
0x1800029ba  sub     rsp, 70h
0x1800029be  xor     esi, esi
0x1800029c0  mov     [rbp+ppAuthIdentity], 0
0x1800029c8  mov     [rbp+arg_10], rsi
0x1800029cc  mov     r12, rdx
0x1800029cf  mov     rdi, rcx
0x1800029d2  test    rcx, rcx
0x1800029d5  jz      loc_180002E30
0x1800029db  test    rdx, rdx
0x1800029de  jz      loc_180002E30
0x1800029e4  lea     rcx, [rbp+ppAuthIdentity]; struct _TS_CREDENTIAL **
0x1800029e8  mov     [rsp+70h+var_8], r14
0x1800029ed  call    ?TSAllocateCredential@@YAJPEAPEAU_TS_CREDENTIAL@@@Z; TSAllocateCredential(_TS_CREDENTIAL * *)
0x1800029f2  mov     r14, [rbp+ppAuthIdentity]
0x1800029f6  mov     ebx, eax
0x1800029f8  test    eax, eax
0x1800029fa  js      loc_180002E11
0x180002a00  mov     rax, [rdi]
0x180002a03  mov     [r14+70h], rax
0x180002a07  mov     eax, [rdi+50h]
0x180002a0a  bt      eax, 9
0x180002a0e  jnb     loc_180002B66
0x180002a14  movzx   eax, word ptr [rdi+28h]
0x180002a18  xorps   xmm0, xmm0
0x180002a1b  mov     [rbp+ppAuthIdentity], rsi
0x180002a1f  xorps   xmm1, xmm1
0x180002a22  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x180002a26  movups  xmmword ptr [rbp+var_30.Length], xmm1
0x180002a2a  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x180002a2e  cmp     eax, 30h ; '0'
0x180002a31  jb      loc_180002E0C
0x180002a37  mov     rdx, [rdi+30h]; AuthIdentityByteArray
0x180002a3b  lea     r8, [rbp+ppAuthIdentity]; ppAuthIdentity
0x180002a3f  mov     ecx, eax; AuthIdentityLength
0x180002a41  call    cs:__imp_SspiUnmarshalAuthIdentity
0x180002a47  mov     ebx, eax
0x180002a49  test    eax, eax
0x180002a4b  jns     short loc_180002A8B
0x180002a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a54  lea     rdi, WPP_GLOBAL_Control
0x180002a5b  cmp     rcx, rdi
0x180002a5e  jz      loc_180002E11
0x180002a64  test    byte ptr [rcx+1Ch], 1
0x180002a68  jz      loc_180002E11
0x180002a6e  mov     edx, 22h ; '"'
0x180002a73  mov     r9d, eax
0x180002a76  mov     rcx, [rcx+10h]
0x180002a7a  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002a81  call    WPP_SF_d
0x180002a86  jmp     loc_180002E11
0x180002a8b  mov     rcx, [rbp+ppAuthIdentity]; EncryptedAuthData
0x180002a8f  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x180002a95  lea     rdi, WPP_GLOBAL_Control
0x180002a9c  test    al, al
0x180002a9e  jz      short loc_180002AD8
0x180002aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002aa7  cmp     rcx, rdi
0x180002aaa  jz      short loc_180002AC7
0x180002aac  test    byte ptr [rcx+1Ch], 1
0x180002ab0  jz      short loc_180002AC7
0x180002ab2  mov     rcx, [rcx+10h]
0x180002ab6  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180002abd  mov     edx, 23h ; '#'
0x180002ac2  call    WPP_SF_
0x180002ac7  mov     rcx, [rbp+ppAuthIdentity]; AuthData
0x180002acb  mov     ebx, 0C000000Dh
0x180002ad0  call    cs:__imp_SspiFreeAuthIdentity
0x180002ad6  jmp     short loc_180002B04
0x180002ad8  mov     rcx, [rbp+ppAuthIdentity]; pAuthIdentity
0x180002adc  lea     rax, [rbp+var_20]
0x180002ae0  lea     r9, [rbp+var_30]; struct _UNICODE_STRING *
0x180002ae4  mov     [rsp+70h+var_50], rax; struct _UNICODE_STRING *
0x180002ae9  lea     r8, [rbp+var_40]; struct _UNICODE_STRING *
0x180002aed  xor     edx, edx; unsigned __int8
0x180002aef  call    ?TSUnpackAuthIdEx2LogonBuffer@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@EPEAU_UNICODE_STRING@@11@Z; TSUnpackAuthIdEx2LogonBuffer(_SEC_WINNT_AUTH_IDENTITY_EX2 *,uchar,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180002af4  mov     rcx, [rbp+ppAuthIdentity]; AuthData
0x180002af8  mov     ebx, eax
0x180002afa  call    cs:__imp_SspiFreeAuthIdentity
0x180002b00  test    ebx, ebx
0x180002b02  jns     short loc_180002B2B
0x180002b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b0b  cmp     rcx, rdi
0x180002b0e  jz      loc_180002E11
0x180002b14  test    byte ptr [rcx+1Ch], 1
0x180002b18  jz      loc_180002E11
0x180002b1e  mov     edx, 24h ; '$'
0x180002b23  mov     r9d, ebx
0x180002b26  jmp     loc_180002A76
0x180002b2b  lea     r9, [rbp+arg_10]; struct _TS_PRIMARY_CREDENTIAL **
0x180002b2f  lea     r8, [rbp+var_20]; struct _UNICODE_STRING *
0x180002b33  lea     rdx, [rbp+var_30]; struct _UNICODE_STRING *
0x180002b37  lea     rcx, [rbp+var_40]; struct _UNICODE_STRING *
0x180002b3b  call    ?TSInitPrimaryCreds@@YAJPEAU_UNICODE_STRING@@00PEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSInitPrimaryCreds(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_TS_PRIMARY_CREDENTIAL * *)
0x180002b40  lea     rcx, [rbp+var_40]; void *
0x180002b44  mov     ebx, eax
0x180002b46  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180002b4b  lea     rcx, [rbp+var_30]; void *
0x180002b4f  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180002b54  lea     rcx, [rbp+var_20]; void *
0x180002b58  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180002b5d  mov     rsi, [rbp+arg_10]
0x180002b61  jmp     loc_180002DA3
0x180002b66  test    al, 1
0x180002b68  jz      loc_180002E0C
0x180002b6e  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180002b75  mov     [rsp+70h+var_10], r15
0x180002b7a  jnz     short loc_180002BA6
0x180002b7c  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180002b83  mov     ecx, 0E8h
0x180002b88  mov     rax, [rax+180h]
0x180002b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b94  mov     r15, rax
0x180002b97  test    r15, r15
0x180002b9a  jnz     short loc_180002BD2
0x180002b9c  mov     ebx, 0C000009Ah
0x180002ba1  jmp     loc_180002D9E
0x180002ba6  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180002bad  mov     ecx, 0E8h
0x180002bb2  mov     rax, [rax]
0x180002bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bba  mov     r15, rax
0x180002bbd  test    rax, rax
0x180002bc0  jz      short loc_180002B97
0x180002bc2  xor     edx, edx; Val
0x180002bc4  mov     r8d, 0E8h; Size
0x180002bca  mov     rcx, rax; void *
0x180002bcd  call    memset_0
0x180002bd2  lea     rbx, [rdi+8]
0x180002bd6  mov     [rsp+70h+arg_8], r13
0x180002bde  mov     ecx, 0FFFCh
0x180002be3  test    rbx, rbx
0x180002be6  jz      short loc_180002C57
0x180002be8  cmp     [rbx+8], rsi
0x180002bec  jz      short loc_180002C57
0x180002bee  movzx   eax, word ptr [rbx]
0x180002bf1  cmp     ax, cx
0x180002bf4  jbe     short loc_180002C04
0x180002bf6  mov     [r15+20h], rsi
0x180002bfa  mov     ebx, 0C0000106h
0x180002bff  jmp     loc_180002DF3
0x180002c04  lea     r13d, [rax+2]
0x180002c08  mov     ecx, r13d; Size
0x180002c0b  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180002c10  mov     [r15+20h], rax
0x180002c14  mov     rcx, rax; void *
0x180002c17  test    rax, rax
0x180002c1a  jnz     short loc_180002C26
0x180002c1c  mov     ebx, 0C000009Ah
0x180002c21  jmp     loc_180002DF3
0x180002c26  movzx   eax, word ptr [rbx]
0x180002c29  mov     [r15+18h], ax
0x180002c2e  mov     [r15+1Ah], r13w
0x180002c33  movzx   r8d, word ptr [rbx]; Size
0x180002c37  mov     rdx, [rbx+8]; Src
0x180002c3b  call    memcpy_0
0x180002c40  movzx   edx, word ptr [rbx]
0x180002c43  mov     rcx, [r15+20h]
0x180002c47  shr     rdx, 1
0x180002c4a  xor     eax, eax
0x180002c4c  mov     [rcx+rdx*2], ax
0x180002c50  mov     ecx, 0FFFCh
0x180002c55  jmp     short loc_180002C61
0x180002c57  xor     eax, eax
0x180002c59  mov     [r15+20h], rsi
0x180002c5d  mov     [r15+18h], eax
0x180002c61  lea     rbx, [rdi+18h]
0x180002c65  test    rbx, rbx
0x180002c68  jz      short loc_180002CD4
0x180002c6a  cmp     [rbx+8], rsi
0x180002c6e  jz      short loc_180002CD4
0x180002c70  movzx   eax, word ptr [rbx]
0x180002c73  cmp     ax, cx
0x180002c76  jbe     short loc_180002C86
0x180002c78  mov     [r15+10h], rsi
0x180002c7c  mov     ebx, 0C0000106h
0x180002c81  jmp     loc_180002DF3
0x180002c86  lea     r13d, [rax+2]
0x180002c8a  mov     ecx, r13d; Size
0x180002c8d  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180002c92  mov     [r15+10h], rax
0x180002c96  mov     rcx, rax; void *
0x180002c99  test    rax, rax
0x180002c9c  jnz     short loc_180002CA8
0x180002c9e  mov     ebx, 0C000009Ah
0x180002ca3  jmp     loc_180002DF3
0x180002ca8  movzx   eax, word ptr [rbx]
0x180002cab  mov     [r15+8], ax
0x180002cb0  mov     [r15+0Ah], r13w
0x180002cb5  movzx   r8d, word ptr [rbx]; Size
0x180002cb9  mov     rdx, [rbx+8]; Src
0x180002cbd  call    memcpy_0
0x180002cc2  movzx   edx, word ptr [rbx]
0x180002cc5  mov     rcx, [r15+10h]
0x180002cc9  shr     rdx, 1
0x180002ccc  xor     eax, eax
0x180002cce  mov     [rcx+rdx*2], ax
0x180002cd2  jmp     short loc_180002CDE
0x180002cd4  xor     eax, eax
0x180002cd6  mov     [r15+10h], rsi
0x180002cda  mov     [r15+8], eax
0x180002cde  add     rdi, 28h ; '('
0x180002ce2  cmp     [rdi+8], rsi
0x180002ce6  jz      loc_180002D8A
0x180002cec  xor     eax, eax
0x180002cee  mov     [r15+30h], rsi
0x180002cf2  mov     [r15+28h], eax
0x180002cf6  test    rdi, rdi
0x180002cf9  jz      loc_180002D8A
0x180002cff  cmp     [rdi+8], rax
0x180002d03  jz      loc_180002D8A
0x180002d09  movzx   edx, word ptr [rdi]
0x180002d0c  xor     ebx, ebx
0x180002d0e  movzx   eax, dx
0x180002d11  mov     ecx, 8
0x180002d16  and     ax, 7
0x180002d1a  sub     cx, ax
0x180002d1d  mov     eax, 0FFF4h
0x180002d22  cmp     cx, 8
0x180002d26  cmovnz  bx, cx
0x180002d2a  cmp     dx, ax
0x180002d2d  jbe     short loc_180002D39
0x180002d2f  mov     ebx, 0C000006Bh
0x180002d34  jmp     loc_180002DF3
0x180002d39  add     bx, dx
0x180002d3c  cmp     bx, dx
0x180002d3f  jnb     short loc_180002D50
0x180002d41  mov     rcx, r15; struct _TS_PRIMARY_CREDENTIAL *
0x180002d44  mov     ebx, 0C000006Bh
0x180002d49  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x180002d4e  jmp     short loc_180002D96
0x180002d50  movzx   ecx, bx; Size
0x180002d53  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180002d58  mov     [r15+30h], rax
0x180002d5c  test    rax, rax
0x180002d5f  jz      loc_180002DEE
0x180002d65  movzx   ecx, word ptr [rdi]
0x180002d68  mov     [r15+28h], cx
0x180002d6d  mov     [r15+2Ah], bx
0x180002d72  movzx   ecx, word ptr [rdi+2]
0x180002d76  mov     rdx, [rdi+8]; Src
0x180002d7a  cmp     bx, cx
0x180002d7d  jnz     short loc_180002DE8
0x180002d7f  mov     r8d, ecx; Size
0x180002d82  mov     rcx, rax; void *
0x180002d85  call    memcpy_0
0x180002d8a  mov     dword ptr [r15], 1
0x180002d91  mov     rsi, r15
0x180002d94  xor     ebx, ebx
0x180002d96  mov     r13, [rsp+70h+arg_8]
0x180002d9e  mov     r15, [rsp+70h+var_10]
0x180002da3  test    ebx, ebx
0x180002da5  js      short loc_180002DFD
0x180002da7  lea     rcx, [rsi+28h]
0x180002dab  test    rcx, rcx
0x180002dae  jz      short loc_180002DCB
0x180002db0  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180002db7  movzx   edx, word ptr [rcx+2]
0x180002dbb  mov     rcx, [rcx+8]
0x180002dbf  mov     rax, [rax+160h]
0x180002dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcb  mov     [r14+88h], rsi
0x180002dd2  mov     eax, ebx
0x180002dd4  mov     [r12], r14
0x180002dd8  mov     r14, [rsp+70h+var_8]
0x180002ddd  add     rsp, 70h
0x180002de1  pop     r12
0x180002de3  pop     rdi
0x180002de4  pop     rsi
0x180002de5  pop     rbx
0x180002de6  pop     rbp
0x180002de7  retn
0x180002de8  movzx   r8d, word ptr [rdi]
0x180002dec  jmp     short loc_180002D82
0x180002dee  mov     ebx, 0C0000017h
0x180002df3  mov     rcx, r15; struct _TS_PRIMARY_CREDENTIAL *
0x180002df6  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x180002dfb  jmp     short loc_180002D96
0x180002dfd  test    rsi, rsi
0x180002e00  jz      short loc_180002E11
0x180002e02  mov     rcx, rsi; struct _TS_PRIMARY_CREDENTIAL *
0x180002e05  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x180002e0a  jmp     short loc_180002E11
0x180002e0c  mov     ebx, 0C000000Dh
0x180002e11  test    r14, r14
0x180002e14  jz      short loc_180002E1E
0x180002e16  mov     rcx, r14; struct _TS_CREDENTIAL *
0x180002e19  call    ?TSDereferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSDereferenceCredential(_TS_CREDENTIAL *)
0x180002e1e  mov     r14, [rsp+70h+var_8]
0x180002e23  mov     eax, ebx
0x180002e25  add     rsp, 70h
0x180002e29  pop     r12
0x180002e2b  pop     rdi
0x180002e2c  pop     rsi
0x180002e2d  pop     rbx
  ... truncated ...
```
