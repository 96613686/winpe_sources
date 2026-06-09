# TSObtainRedirectableCreds(_SecHandle *,_UNICODE_STRING *,void *,_TS_CONTEXT *,_TS_PRIMARY_CREDENTIAL * *)

- ea: `0x180014a84`
- end: `0x180014e89`
- name: `?TSObtainRedirectableCreds@@YAJPEAU_SecHandle@@PEAU_UNICODE_STRING@@PEAXPEAU_TS_CONTEXT@@PEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z`
- size: `1029`
- prototype: `__int64 __fastcall(PCtxtHandle phContext, struct _UNICODE_STRING *, void *, struct _TS_CONTEXT *, struct _TS_PRIMARY_CREDENTIAL **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006650`

## callees

- `0x1800032c0`
- `0x180003830`
- `0x180007df0`
- `0x18000b550`
- `0x18000b92c`
- `0x18000c1a4`
- `0x180012904`
- `0x180014a84`
- `0x180014e90`
- `0x1800162a4`
- `0x1800163fc`
- `0x180016480`
- `0x18001b6a0`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180014e3c`
- `SspiCli!FreeCredentialsHandle` at `0x180014e3c`
- `SspiCli!AcquireCredentialsHandleW` at `0x180014c6d`
- `SspiCli!AcquireCredentialsHandleW` at `0x180014c6d`
- `SspiCli!QueryContextAttributesW` at `0x180014bd7`
- `SspiCli!QueryContextAttributesW` at `0x180014bd7`
- `SspiCli!FreeContextBuffer` at `0x180014e46`
- `SspiCli!FreeContextBuffer` at `0x180014e46`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014c79`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d0d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014c79`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d0d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d3e`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180014bdf`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180014bdf`
- `ntdll!RtlInitUnicodeString` at `0x180014c01`
- `ntdll!RtlInitUnicodeString` at `0x180014c01`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180014b42`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180014b42`
- `LSASRV!LsaIGetRemoteCredGuardLogonBuffer` at `0x180014d01`
- `LSASRV!LsaIGetRemoteCredGuardLogonBuffer` at `0x180014d01`

## pseudocode

```c
__int64 __fastcall TSObtainRedirectableCreds(
        PCtxtHandle phContext,
        struct _UNICODE_STRING *a2,
        void *a3,
        struct _TS_CONTEXT *a4,
        struct _TS_PRIMARY_CREDENTIAL **a5)
{
  bool v5; // zf
  struct _RTL_AVL_TABLE *v10; // rax
  int v11; // r8d
  struct _RTL_AVL_TABLE *v12; // rbx
  _UNKNOWN **v13; // rdx
  NTSTATUS v14; // ebx
  struct _TS_PRIMARY_CREDENTIAL *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // r9
  SECURITY_STATUS v18; // eax
  struct _TS_PRIMARY_CREDENTIAL *v19; // rbx
  unsigned __int8 v20; // r8
  int v21; // edx
  RedirectedCredContextTable *v22; // rcx
  size_t Size; // [rsp+50h] [rbp-51h] BYREF
  PVOID pBuffer; // [rsp+58h] [rbp-49h] BYREF
  void *Src; // [rsp+60h] [rbp-41h] BYREF
  void (*v27)(void *); // [rsp+68h] [rbp-39h] BYREF
  int (*v28)(void *, void *, unsigned int, void **, unsigned int *); // [rsp+70h] [rbp-31h] BYREF
  void *v29; // [rsp+78h] [rbp-29h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+80h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-19h] BYREF
  struct _SecHandle phCredential; // [rsp+98h] [rbp-9h] BYREF

  v5 = phContext->dwLower == -1;
  pBuffer = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v29 = 0;
  phCredential = 0;
  ptsExpiry.QuadPart = 0;
  v28 = 0;
  v27 = 0;
  if ( v5 || phContext->dwUpper == -1 || !a5 )
    return 3221225485LL;
  v10 = (struct _RTL_AVL_TABLE *)operator new(0x68u, (const struct std::nothrow_t *)TSGlobalNoThrow);
  v12 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, sizeof(struct _RTL_AVL_TABLE));
    RtlInitializeGenericTableAvl(v12, TableCompare, TSTableAllocate, TSTableFree, 0);
  }
  else
  {
    v12 = 0;
  }
  *((_QWORD *)a4 + 20) = v12;
  v13 = &WPP_GLOBAL_Control;
  if ( !v12 )
  {
    v14 = -2146893056;
LABEL_12:
    v16 = WPP_GLOBAL_Control;
LABEL_13:
    if ( pBuffer && (v17 = *((_QWORD *)pBuffer + 2)) != 0 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_SD(v16[2], (unsigned int)&WPP_GLOBAL_Control, v11, v17, v14);
    }
    else if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
    {
      WPP_SF_d(v16[2], 52, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, (unsigned int)v14);
    }
    v22 = (RedirectedCredContextTable *)*((_QWORD *)a4 + 20);
    if ( v22 )
      RedirectedCredContextTable::`scalar deleting destructor'(v22, (unsigned int)v13);
    *((_QWORD *)a4 + 20) = 0;
    TSFreePrimaryCredentials(*a5);
    *a5 = 0;
    goto LABEL_41;
  }
  v15 = (struct _TS_PRIMARY_CREDENTIAL *)TSAllocate(0xE8u);
  *a5 = v15;
  if ( !v15 )
  {
    v14 = -2146893056;
LABEL_11:
    v13 = &WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v18 = QueryContextAttributesW(phContext, 0xAu, &pBuffer);
  v14 = RtlMapSecurityErrorToNtStatus(v18);
  if ( v14 < 0 )
    goto LABEL_11;
  v19 = *a5;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)pBuffer + 2));
  v14 = TSDuplicateStringEx((struct _UNICODE_STRING *)((char *)v19 + 184), &DestinationString, v20);
  if ( v14 < 0 )
    goto LABEL_11;
  v14 = TSGlobalLsaFunctions->ImpersonateClient();
  if ( v14 < 0 )
    goto LABEL_11;
  v14 = AcquireCredentialsHandleW(0, *((LPWSTR *)pBuffer + 2), 2u, 0, a3, 0, 0, &phCredential, &ptsExpiry);
  if ( v14 < 0 )
  {
    RevertToSelf();
    v16 = WPP_GLOBAL_Control;
    v13 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    v21 = 49;
    goto LABEL_25;
  }
  v14 = LsaIGetRemoteCredGuardLogonBuffer(
          (char *)*a5 + 184,
          phCredential.dwUpper,
          phContext->dwUpper,
          a2,
          &v29,
          &v28,
          &v27,
          &Size,
          &Src);
  if ( v14 < 0 )
  {
    RevertToSelf();
    v16 = WPP_GLOBAL_Control;
    v13 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    v21 = 50;
LABEL_25:
    WPP_SF_Sd(v16[2], v21, v11, *((_QWORD *)pBuffer + 2), v14);
    goto LABEL_11;
  }
  RevertToSelf();
  v14 = RedirectedCredContextTable::AddPackage(
          *((PRTL_AVL_TABLE *)a4 + 20),
          (PCUNICODE_STRING)((char *)*a5 + 184),
          v29,
          v28,
          v27);
  if ( v14 < 0 )
    goto LABEL_11;
  *((_QWORD *)*a5 + 26) = TSAllocate((unsigned int)Size);
  if ( !*((_QWORD *)*a5 + 26) )
  {
    v14 = -1073741801;
    goto LABEL_11;
  }
  *((_DWORD *)*a5 + 50) = Size;
  memcpy_0(*((void **)*a5 + 26), Src, (unsigned int)Size);
  v14 = TSObtainRedirectableSupplementalCreds(a3);
  if ( v14 < 0 )
    goto LABEL_11;
  *(_DWORD *)*a5 = 6;
LABEL_41:
  if ( phCredential.dwUpper )
    FreeCredentialsHandle(&phCredential);
  FreeContextBuffer(pBuffer);
  ((void (__fastcall *)(void *))TSGlobalLsaFunctions->FreeLsaHeap)(Src);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180014a84  push    rbp
0x180014a86  push    rbx
0x180014a87  push    rsi
0x180014a88  push    rdi
0x180014a89  push    r12
0x180014a8b  push    r13
0x180014a8d  push    r14
0x180014a8f  push    r15
0x180014a91  lea     rbp, [rsp-17h]
0x180014a96  sub     rsp, 0B8h
0x180014a9d  mov     rax, cs:__security_cookie
0x180014aa4  xor     rax, rsp
0x180014aa7  mov     [rbp+4Fh+var_48], rax
0x180014aab  mov     rdi, [rbp+4Fh+arg_20]
0x180014aaf  xor     r13d, r13d
0x180014ab2  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180014ab6  xorps   xmm0, xmm0
0x180014ab9  mov     rsi, r9
0x180014abc  mov     [rbp+4Fh+pBuffer], r13
0x180014ac0  mov     r15, r8
0x180014ac3  mov     [rbp+4Fh+Src], r13
0x180014ac7  mov     r12, rdx
0x180014aca  mov     dword ptr [rbp+4Fh+Size], r13d
0x180014ace  mov     r14, rcx
0x180014ad1  mov     [rbp+4Fh+var_78], r13
0x180014ad5  movups  xmmword ptr [rbp+4Fh+var_58.dwLower], xmm0
0x180014ad9  mov     qword ptr [rbp+4Fh+var_70], r13
0x180014add  mov     [rbp+4Fh+var_80], r13
0x180014ae1  mov     [rbp+4Fh+var_88], r13
0x180014ae5  jz      loc_180014E64
0x180014aeb  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180014af0  jz      loc_180014E64
0x180014af6  test    rdi, rdi
0x180014af9  jz      loc_180014E64
0x180014aff  lea     rdx, ?TSGlobalNoThrow@@3Unothrow_t@std@@A; struct std::nothrow_t *
0x180014b06  lea     ecx, [r13+68h]; unsigned __int64
0x180014b0a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014b0f  mov     rbx, rax
0x180014b12  test    rax, rax
0x180014b15  jz      short loc_180014B4A
0x180014b17  xor     edx, edx; Val
0x180014b19  lea     r8d, [r13+68h]; Size
0x180014b1d  mov     rcx, rax; void *
0x180014b20  call    memset_0
0x180014b25  lea     r9, ?TSTableFree@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180014b2c  mov     [rsp+0F0h+TableContext], r13; TableContext
0x180014b31  lea     r8, ?TSTableAllocate@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180014b38  mov     rcx, rbx; Table
0x180014b3b  lea     rdx, TableCompare; CompareRoutine
0x180014b42  call    cs:__imp_RtlInitializeGenericTableAvl
0x180014b48  jmp     short loc_180014B4D
0x180014b4a  mov     rbx, r13
0x180014b4d  mov     [rsi+0A0h], rbx
0x180014b54  lea     rdx, WPP_GLOBAL_Control
0x180014b5b  test    rbx, rbx
0x180014b5e  jnz     short loc_180014B67
0x180014b60  mov     ebx, 80090300h
0x180014b65  jmp     short loc_180014B85
0x180014b67  mov     ecx, 0E8h; Size
0x180014b6c  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180014b71  mov     [rdi], rax
0x180014b74  test    rax, rax
0x180014b77  jnz     short loc_180014BCB
0x180014b79  mov     ebx, 80090300h
0x180014b7e  lea     rdx, WPP_GLOBAL_Control
0x180014b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b8c  mov     rax, [rbp+4Fh+pBuffer]
0x180014b90  test    rax, rax
0x180014b93  jz      loc_180014DEC
0x180014b99  mov     r9, [rax+10h]
0x180014b9d  test    r9, r9
0x180014ba0  jz      loc_180014DEC
0x180014ba6  cmp     rcx, rdx
0x180014ba9  jz      loc_180014E0F
0x180014baf  test    byte ptr [rcx+1Ch], 1
0x180014bb3  jz      loc_180014E0F
0x180014bb9  mov     rcx, [rcx+10h]
0x180014bbd  mov     dword ptr [rsp+0F0h+TableContext], ebx
0x180014bc1  call    WPP_SF_SD
0x180014bc6  jmp     loc_180014E0F
0x180014bcb  lea     r8, [rbp+4Fh+pBuffer]; pBuffer
0x180014bcf  mov     edx, 0Ah; ulAttribute
0x180014bd4  mov     rcx, r14; phContext
0x180014bd7  call    cs:__imp_QueryContextAttributesW
0x180014bdd  mov     ecx, eax; SecurityError
0x180014bdf  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x180014be5  mov     ebx, eax
0x180014be7  test    eax, eax
0x180014be9  js      short loc_180014B7E
0x180014beb  mov     rdx, [rbp+4Fh+pBuffer]
0x180014bef  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180014bf3  mov     rbx, [rdi]
0x180014bf6  xorps   xmm0, xmm0
0x180014bf9  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180014bfd  mov     rdx, [rdx+10h]; SourceString
0x180014c01  call    cs:__imp_RtlInitUnicodeString
0x180014c07  lea     rdx, [rbp+4Fh+DestinationString]; struct _UNICODE_STRING *
0x180014c0b  lea     rcx, [rbx+0B8h]; struct _UNICODE_STRING *
0x180014c12  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180014c17  mov     ebx, eax
0x180014c19  test    eax, eax
0x180014c1b  js      loc_180014B7E
0x180014c21  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180014c28  mov     rax, [rax+58h]
0x180014c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c31  mov     ebx, eax
0x180014c33  test    eax, eax
0x180014c35  js      loc_180014B7E
0x180014c3b  mov     rdx, [rbp+4Fh+pBuffer]
0x180014c3f  lea     rax, [rbp+4Fh+var_70]
0x180014c43  mov     [rsp+0F0h+ptsExpiry], rax; ptsExpiry
0x180014c48  xor     r9d, r9d; pvLogonId
0x180014c4b  lea     rax, [rbp+4Fh+var_58]
0x180014c4f  xor     ecx, ecx; pszPrincipal
0x180014c51  mov     [rsp+0F0h+phCredential], rax; phCredential
0x180014c56  mov     rdx, [rdx+10h]; pszPackage
0x180014c5a  mov     [rsp+0F0h+pvGetKeyArgument], r13; pvGetKeyArgument
0x180014c5f  lea     r8d, [r9+2]; fCredentialUse
0x180014c63  mov     [rsp+0F0h+pGetKeyFn], r13; pGetKeyFn
0x180014c68  mov     [rsp+0F0h+TableContext], r15; pAuthData
0x180014c6d  call    cs:__imp_AcquireCredentialsHandleW
0x180014c73  mov     ebx, eax
0x180014c75  test    eax, eax
0x180014c77  jns     short loc_180014CBF
0x180014c79  call    cs:__imp_RevertToSelf
0x180014c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c86  lea     rdx, WPP_GLOBAL_Control
0x180014c8d  cmp     rcx, rdx
0x180014c90  jz      loc_180014B8C
0x180014c96  test    byte ptr [rcx+1Ch], 2
0x180014c9a  jz      loc_180014B8C
0x180014ca0  mov     edx, 31h ; '1'
0x180014ca5  mov     r9, [rbp+4Fh+pBuffer]
0x180014ca9  mov     rcx, [rcx+10h]
0x180014cad  mov     dword ptr [rsp+0F0h+TableContext], ebx
0x180014cb1  mov     r9, [r9+10h]
0x180014cb5  call    WPP_SF_Sd
0x180014cba  jmp     loc_180014B7E
0x180014cbf  mov     rcx, [rdi]
0x180014cc2  lea     rax, [rbp+4Fh+Src]
0x180014cc6  mov     r8, [r14+8]
0x180014cca  add     rcx, 0B8h
0x180014cd1  mov     rdx, [rbp+4Fh+var_58.dwUpper]
0x180014cd5  mov     r9, r12
0x180014cd8  mov     [rsp+0F0h+ptsExpiry], rax
0x180014cdd  lea     rax, [rbp+4Fh+Size]
0x180014ce1  mov     [rsp+0F0h+phCredential], rax
0x180014ce6  lea     rax, [rbp+4Fh+var_88]
0x180014cea  mov     [rsp+0F0h+pvGetKeyArgument], rax
0x180014cef  lea     rax, [rbp+4Fh+var_80]
0x180014cf3  mov     [rsp+0F0h+pGetKeyFn], rax
0x180014cf8  lea     rax, [rbp+4Fh+var_78]
0x180014cfc  mov     [rsp+0F0h+TableContext], rax
0x180014d01  call    cs:__imp_LsaIGetRemoteCredGuardLogonBuffer
0x180014d07  mov     ebx, eax
0x180014d09  test    eax, eax
0x180014d0b  jns     short loc_180014D3E
0x180014d0d  call    cs:__imp_RevertToSelf
0x180014d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d1a  lea     rdx, WPP_GLOBAL_Control
0x180014d21  cmp     rcx, rdx
0x180014d24  jz      loc_180014B8C
0x180014d2a  test    byte ptr [rcx+1Ch], 2
0x180014d2e  jz      loc_180014B8C
0x180014d34  mov     edx, 32h ; '2'
0x180014d39  jmp     loc_180014CA5
0x180014d3e  call    cs:__imp_RevertToSelf
0x180014d44  mov     rdx, [rdi]
0x180014d47  mov     r14d, 0B8h
0x180014d4d  mov     rax, [rbp+4Fh+var_88]
0x180014d51  add     rdx, r14; SourceString
0x180014d54  mov     r9, [rbp+4Fh+var_80]; int (*)(void *, void *, unsigned int, void **, unsigned int *)
0x180014d58  mov     r8, [rbp+4Fh+var_78]; void *
0x180014d5c  mov     rcx, [rsi+0A0h]; Table
0x180014d63  mov     [rsp+0F0h+TableContext], rax; void (*)(void *)
0x180014d68  call    ?AddPackage@RedirectedCredContextTable@@QEAAJAEBU_UNICODE_STRING@@PEAXP6AJ11KPEAPEAXPEAK@ZP6AX1@Z@Z; RedirectedCredContextTable::AddPackage(_UNICODE_STRING const &,void *,long (*)(void *,void *,ulong,void * *,ulong *),void (*)(void *))
0x180014d6d  mov     ebx, eax
0x180014d6f  test    eax, eax
0x180014d71  js      loc_180014B7E
0x180014d77  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x180014d7a  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180014d7f  mov     rcx, [rdi]
0x180014d82  mov     [rcx+0D0h], rax
0x180014d89  mov     rcx, [rdi]
0x180014d8c  cmp     [rcx+0D0h], r13
0x180014d93  jnz     short loc_180014D9F
0x180014d95  mov     ebx, 0C0000017h
0x180014d9a  jmp     loc_180014B7E
0x180014d9f  mov     eax, dword ptr [rbp+4Fh+Size]
0x180014da2  mov     [rcx+0C8h], eax
0x180014da8  mov     rcx, [rdi]
0x180014dab  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x180014daf  mov     rdx, [rbp+4Fh+Src]; Src
0x180014db3  mov     rcx, [rcx+0D0h]; void *
0x180014dba  call    memcpy_0
0x180014dbf  mov     r9, [rdi]
0x180014dc2  mov     rdx, r12
0x180014dc5  mov     r8, [rsi+0A0h]
0x180014dcc  add     r9, r14
0x180014dcf  mov     rcx, r15; pAuthData
0x180014dd2  call    TSObtainRedirectableSupplementalCreds
0x180014dd7  mov     ebx, eax
0x180014dd9  test    eax, eax
0x180014ddb  js      loc_180014B7E
0x180014de1  mov     rax, [rdi]
0x180014de4  mov     dword ptr [rax], 6
0x180014dea  jmp     short loc_180014E32
0x180014dec  cmp     rcx, rdx
0x180014def  jz      short loc_180014E0F
0x180014df1  test    byte ptr [rcx+1Ch], 1
0x180014df5  jz      short loc_180014E0F
0x180014df7  mov     rcx, [rcx+10h]
0x180014dfb  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180014e02  mov     edx, 34h ; '4'
0x180014e07  mov     r9d, ebx
0x180014e0a  call    WPP_SF_d
0x180014e0f  mov     rcx, [rsi+0A0h]; this
0x180014e16  test    rcx, rcx
0x180014e19  jz      short loc_180014E20
0x180014e1b  call    ??_GRedirectedCredContextTable@@QEAAPEAXI@Z; RedirectedCredContextTable::`scalar deleting destructor'(uint)
0x180014e20  mov     [rsi+0A0h], r13
0x180014e27  mov     rcx, [rdi]; struct _TS_PRIMARY_CREDENTIAL *
0x180014e2a  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x180014e2f  mov     [rdi], r13
0x180014e32  cmp     [rbp+4Fh+var_58.dwUpper], r13
0x180014e36  jz      short loc_180014E42
0x180014e38  lea     rcx, [rbp+4Fh+var_58]; phCredential
0x180014e3c  call    cs:__imp_FreeCredentialsHandle
0x180014e42  mov     rcx, [rbp+4Fh+pBuffer]; pvContextBuffer
0x180014e46  call    cs:__imp_FreeContextBuffer
0x180014e4c  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180014e53  mov     rcx, [rbp+4Fh+Src]
0x180014e57  mov     rax, [rax+30h]
0x180014e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e60  mov     eax, ebx
0x180014e62  jmp     short loc_180014E69
0x180014e64  mov     eax, 0C000000Dh
0x180014e69  mov     rcx, [rbp+4Fh+var_48]
0x180014e6d  xor     rcx, rsp; StackCookie
0x180014e70  call    __security_check_cookie
0x180014e75  add     rsp, 0B8h
0x180014e7c  pop     r15
0x180014e7e  pop     r14
0x180014e80  pop     r13
0x180014e82  pop     r12
0x180014e84  pop     rdi
0x180014e85  pop     rsi
0x180014e86  pop     rbx
0x180014e87  pop     rbp
0x180014e88  retn
```
