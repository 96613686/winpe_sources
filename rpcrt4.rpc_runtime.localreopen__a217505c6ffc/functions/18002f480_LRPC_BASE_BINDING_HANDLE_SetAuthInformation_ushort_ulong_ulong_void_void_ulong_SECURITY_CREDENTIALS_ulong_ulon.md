# LRPC_BASE_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)

- ea: `0x18002f480`
- end: `0x18002fd2e`
- name: `?SetAuthInformation@LRPC_BASE_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z`
- size: `2222`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, PSID pSourceSid, int, int, PSECURITY_DESCRIPTOR CreatorDescriptor)`
- caller_count: `6`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ae0`
- `0x18002ea9c`
- `0x18002ed80`
- `0x18002ef98`
- `0x180030df0`
- `0x18008d0f0`

## callees

- `0x180010244`
- `0x180023a40`
- `0x1800295d8`
- `0x18002e750`
- `0x18002f480`
- `0x1800307e0`
- `0x180031308`
- `0x180031af0`
- `0x18005c214`
- `0x1800859b8`
- `0x1800941b0`
- `0x1800ba820`
- `0x1800bb860`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002f821`
- `ntdll!NtOpenThreadToken` at `0x18002f821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f6b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f6b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f801`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fb21`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fb21`
- `SspiCli!SspiValidateAuthIdentity` at `0x18002fab7`
- `SspiCli!SspiValidateAuthIdentity` at `0x18002fab7`
- `SspiCli!LogonUserExExW` at `0x18002fc31`
- `SspiCli!LogonUserExExW` at `0x18002fc31`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_BINDING_HANDLE::SetAuthInformation(
        LRPC_BASE_BINDING_HANDLE *this,
        unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData,
        void *a6,
        unsigned int a7,
        struct SECURITY_CREDENTIALS *a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        void *a14,
        PSID pSourceSid,
        int a16,
        int a17,
        PSECURITY_DESCRIPTOR CreatorDescriptor)
{
  PSID v18; // r15
  int v20; // esi
  DWORD LowPart; // ebx
  int v22; // r14d
  void *v23; // rcx
  unsigned int v24; // eax
  void *v25; // r13
  int v26; // ecx
  unsigned __int16 *v27; // r12
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  int v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  char *v36; // rcx
  unsigned __int16 *v37; // rsi
  unsigned int v38; // r12d
  HANDLE CurrentThread; // rax
  NTSTATUS v41; // eax
  __int64 v42; // rax
  unsigned int v43; // eax
  SID_CACHE *v44; // rcx
  __int64 v45; // rax
  __int64 (__fastcall *v46)(LRPC_BASE_BINDING_HANDLE *); // rax
  int v47; // eax
  unsigned __int16 v48; // r8
  DWORD v49; // eax
  DWORD LastError; // eax
  unsigned __int16 *v51; // [rsp+60h] [rbp-A0h]
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+70h] [rbp-90h]
  void *v54; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *Src; // [rsp+80h] [rbp-80h]
  struct _LUID v56; // [rsp+88h] [rbp-78h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR ppszUserName; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR ppszPackedCredentialsString; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR ppszDomainName; // [rsp+A8h] [rbp-58h] BYREF
  int v61; // [rsp+B0h] [rbp-50h] BYREF
  DWORD v62; // [rsp+B8h] [rbp-48h]
  void *v63; // [rsp+C8h] [rbp-38h]
  _OWORD TokenInformation[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct _LUID v65; // [rsp+100h] [rbp+0h]

  v18 = pSourceSid;
  Src = a2;
  v20 = a3;
  v63 = AuthData;
  LowPart = 0;
  v54 = 0;
  TokenHandle = 0;
  v56 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v65 = 0;
  ReturnLength = 0;
  ppszUserName = 0;
  ppszPackedCredentialsString = 0;
  ppszDomainName = 0;
  if ( a13 || a14 )
  {
    RpcpErrorAddRecord(2u, 1764, 0x35Cu, 0, 0);
    return 1764;
  }
  if ( a3 <= 6 )
  {
    if ( a3 != 1 )
      v20 = 6;
    v22 = 10;
    if ( a4 != 20 )
      v22 = a4;
    if ( v22 != 10 && v22 )
    {
      RpcpErrorAddRecord(2u, 1747, 0x35Du, 0, 0);
      return 1747;
    }
    if ( !AuthData )
    {
LABEL_10:
      v23 = (void *)*((_QWORD *)this + 51);
      if ( v23 )
      {
        FreeWrapper(v23);
        *((_QWORD *)this + 51) = 0;
      }
      if ( CreatorDescriptor
        && (unsigned int)RpcpNormalizeSecurityDescriptor(CreatorDescriptor, 0x18u, (void **)this + 51) )
      {
        return 14;
      }
      v24 = a11;
      v25 = 0;
      v53 = 0;
      v26 = 0;
      v51 = 0;
      v27 = 0;
      if ( (a11 & 1) == 0 )
        goto LABEL_14;
      if ( pSourceSid )
      {
LABEL_55:
        a11 = v24 | 0x10;
LABEL_14:
        if ( v18 )
        {
          if ( !v26 )
          {
            v18 = DuplicateSID(v18);
            if ( !v18 )
            {
              v38 = 14;
              v37 = 0;
              goto LABEL_40;
            }
            v53 = 1;
          }
          v25 = DuplicateSID(v18);
          if ( !v25 )
          {
            v38 = 14;
LABEL_61:
            v37 = v51;
LABEL_40:
            if ( ppszUserName )
              WipeAndFreeEncodedString(ppszUserName);
            if ( ppszPackedCredentialsString )
              WipeAndFreeEncodedString(ppszPackedCredentialsString);
            if ( ppszDomainName )
              WipeAndFreeEncodedString(ppszDomainName);
            if ( TokenHandle )
              CloseCapturedToken(TokenHandle);
            if ( v18 && v53 )
              FreeWrapper(v18);
            if ( v25 )
              FreeWrapper(v25);
            if ( v37 )
              FreeWrapper(v37);
            return v38;
          }
        }
        if ( Src )
        {
          if ( *Src )
          {
            v51 = DuplicateString(Src);
            v27 = v51;
            if ( !v51 )
            {
              v38 = 14;
              v37 = 0;
              goto LABEL_40;
            }
          }
        }
        v28 = a10;
        if ( a10 )
        {
LABEL_17:
          *((_DWORD *)this + 21) = 10;
          *((_QWORD *)this + 14) = 0;
          *((_QWORD *)this + 15) = a6;
          if ( v22 )
          {
            *((_DWORD *)this + 104) = v28;
            *((_DWORD *)this + 33) = v28;
            v29 = 1;
            if ( v20 != 1 )
              v29 = a9;
            *((_DWORD *)this + 32) = a7;
            v30 = v29;
            *((_DWORD *)this + 20) = v20;
            if ( !v29 )
              v30 = 3;
            *((_DWORD *)this + 34) = v29;
            *((_DWORD *)this + 105) = v30;
            if ( a17 )
              v31 = (*(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *, __int64))(*(_QWORD *)this + 424LL))(this, 3);
            else
              v31 = a16;
            v32 = a11;
          }
          else
          {
            v45 = *(_QWORD *)this;
            *((_DWORD *)this + 20) = 6;
            *((_DWORD *)this + 32) = 0;
            *((_DWORD *)this + 105) = 3;
            v46 = *(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(v45 + 416);
            *((_DWORD *)this + 34) = 3;
            v47 = v46(this);
            *((_DWORD *)this + 104) = v47;
            v32 = 0;
            *((_DWORD *)this + 33) = v47;
            v31 = (*(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(*(_QWORD *)this + 424LL))(this);
          }
          if ( v31 )
            *((_DWORD *)this + 124) |= 2u;
          else
            *((_DWORD *)this + 124) &= ~2u;
          v33 = (void *)*((_QWORD *)this + 13);
          *((_DWORD *)this + 35) = v32;
          if ( v33 )
            FreeWrapper(v33);
          *((_QWORD *)this + 13) = v18;
          v18 = 0;
          v34 = (void *)*((_QWORD *)this + 50);
          if ( v34 )
            FreeWrapper(v34);
          *((_QWORD *)this + 50) = v25;
          v25 = 0;
          v35 = (void *)*((_QWORD *)this + 12);
          if ( v35 )
            FreeWrapper(v35);
          v36 = (char *)*((_QWORD *)this + 63);
          v37 = 0;
          *((_QWORD *)this + 12) = v27;
          if ( v36 )
          {
            if ( (unsigned __int64)(v36 - 0xFFFFFFFDLL) > 1 )
              CloseHandle(v36);
            *((_QWORD *)this + 63) = 0;
            *((_QWORD *)this + 64) = 0;
          }
          if ( !*((_DWORD *)this + 104) )
          {
            *((_QWORD *)this + 63) = TokenHandle;
            *((_DWORD *)this + 129) = v56.HighPart;
            TokenHandle = 0;
            *((_DWORD *)this + 128) = LowPart;
          }
          v38 = 0;
          goto LABEL_40;
        }
        if ( v63 )
        {
          if ( !(unsigned int)EncodeAuthIdentityAsStrings(
                                v63,
                                &ppszUserName,
                                &ppszDomainName,
                                &ppszPackedCredentialsString) )
          {
            if ( !(unsigned int)LogonUserExExW(
                                  ppszUserName,
                                  ppszDomainName,
                                  ppszPackedCredentialsString,
                                  3,
                                  3,
                                  0,
                                  &TokenHandle,
                                  0,
                                  0,
                                  0,
                                  0) )
            {
              LastError = GetLastError();
              if ( LastError == 5 || LastError != 14 && (LastError == 1314 || LastError == 1326 || LastError == 1385) )
                v38 = 5;
              else
                v38 = 14;
              v62 = LastError;
              v61 = 3;
              RpcpErrorAddRecord(2u, v38, 0x363u, 1, (struct tagParam *)&v61);
              v37 = v51;
              TokenHandle = 0;
              goto LABEL_40;
            }
            if ( !GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
            {
              v49 = GetLastError();
              v38 = v49;
              if ( v49 )
              {
                RpcpErrorAddRecord(2u, v49, 0x364u, 0, 0);
                v37 = v51;
                goto LABEL_40;
              }
              v27 = v51;
            }
            LowPart = v65.LowPart;
            v56 = v65;
LABEL_69:
            v28 = 0;
            goto LABEL_17;
          }
          v38 = 87;
          RpcpErrorAddRecord(2u, 87, 0x365u, 0, 0);
        }
        else
        {
          CurrentThread = GetCurrentThread();
          v38 = 14;
          v41 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, &TokenHandle);
          switch ( v41 )
          {
            case -1073741700:
              v42 = 4294967293LL;
LABEL_66:
              TokenHandle = (void *)v42;
LABEL_67:
              v38 = CaptureModifiedIdEx(&v56);
              if ( v38 )
                goto LABEL_61;
              LowPart = v56.LowPart;
              v27 = v51;
              goto LABEL_69;
            case -1073741790:
              v38 = 5;
              break;
            case -1073741658:
              v42 = 4294967294LL;
              goto LABEL_66;
            case 0:
              goto LABEL_67;
          }
          v62 = v41;
          TokenHandle = 0;
          v61 = 3;
          RpcpErrorAddRecord(2u, v38, 0x460u, 1, (struct tagParam *)&v61);
        }
        v37 = v51;
        goto LABEL_40;
      }
      if ( *(_QWORD *)&SIDCache.Revision )
      {
        v38 = SID_CACHE::Query(0, Src, &v54);
        if ( !v38 )
        {
          v18 = v54;
          if ( v54 )
            goto LABEL_76;
          v43 = RpcpLookupAccountNameDirect(Src, &v54);
          v18 = v54;
          v38 = v43;
          if ( v43 == 1789 )
          {
            v38 = 5;
          }
          else if ( !v43 && *(_QWORD *)&SIDCache.Revision )
          {
            SID_CACHE::Add(v44, Src, v54, 0);
          }
          if ( !v38 )
          {
LABEL_76:
            v24 = a11;
            v26 = 1;
            v53 = 1;
            v27 = 0;
            goto LABEL_55;
          }
        }
      }
      else
      {
        v38 = 14;
      }
      RpcpErrorAddRecord(2u, v38, 0x35Eu, 0, 0);
      v18 = 0;
      v37 = 0;
      goto LABEL_40;
    }
    if ( SspiValidateAuthIdentity(AuthData) >= 0 )
    {
      if ( !a10 )
        goto LABEL_10;
      v48 = 866;
    }
    else
    {
      v48 = 865;
    }
    v38 = 87;
    RpcpErrorAddRecord(2u, 87, v48, 0, 0);
    return v38;
  }
  v62 = a3;
  v61 = 3;
  RpcpErrorAddRecord(2u, 1748, 0x360u, 1, (struct tagParam *)&v61);
  return 1748;
}

```

## disassembly

```asm
0x18002f480  push    rbp
0x18002f482  push    rbx
0x18002f483  push    rsi
0x18002f484  push    rdi
0x18002f485  push    r13
0x18002f487  push    r15
0x18002f489  lea     rbp, [rsp-18h]
0x18002f48e  sub     rsp, 118h
0x18002f495  mov     rax, cs:__security_cookie
0x18002f49c  xor     rax, rsp
0x18002f49f  mov     [rbp+40h+var_38], rax
0x18002f4a3  mov     r15, [rbp+40h+pSourceSid]
0x18002f4aa  xorps   xmm0, xmm0
0x18002f4ad  mov     r13, [rbp+40h+CreatorDescriptor]
0x18002f4b4  xor     eax, eax
0x18002f4b6  mov     [rbp+40h+Src], rdx
0x18002f4ba  mov     rdi, rcx
0x18002f4bd  mov     rcx, [rbp+40h+AuthData]; AuthData
0x18002f4c1  xor     edx, edx
0x18002f4c3  mov     esi, r8d
0x18002f4c6  mov     [rbp+40h+var_78], rcx
0x18002f4ca  mov     ebx, edx
0x18002f4cc  mov     [rsp+140h+var_C8], rdx
0x18002f4d1  mov     [rsp+140h+TokenHandle], rdx
0x18002f4d6  mov     qword ptr [rbp+40h+var_B8.LowPart], rdx
0x18002f4da  movups  [rbp+40h+TokenInformation], xmm0
0x18002f4de  mov     [rbp+40h+var_40], rax
0x18002f4e2  movups  [rbp+40h+var_60], xmm0
0x18002f4e6  mov     [rbp+40h+var_B0], edx
0x18002f4e9  movups  [rbp+40h+var_50], xmm0
0x18002f4ed  mov     [rbp+40h+ppszUserName], rdx
0x18002f4f1  mov     [rbp+40h+ppszPackedCredentialsString], rdx
0x18002f4f5  mov     [rbp+40h+ppszDomainName], rdx
0x18002f4f9  cmp     [rbp+40h+arg_60], eax
0x18002f4ff  jnz     loc_18002F909
0x18002f505  cmp     [rbp+40h+arg_68], rax
0x18002f50c  jnz     loc_18002F909
0x18002f512  cmp     r8d, 6
0x18002f516  ja      loc_18002FA70
0x18002f51c  mov     [rsp+140h+var_30], r14
0x18002f524  cmp     r8d, 1
0x18002f528  jz      short loc_18002F52F
0x18002f52a  mov     esi, 6
0x18002f52f  cmp     r9d, 14h
0x18002f533  mov     r14d, 0Ah
0x18002f539  cmovnz  r14d, r9d
0x18002f53d  cmp     r14d, 0Ah
0x18002f541  jnz     loc_18002FA1D
0x18002f547  mov     [rsp+140h+arg_10], r12
0x18002f54f  test    rcx, rcx
0x18002f552  jnz     loc_18002FAB7
0x18002f558  mov     rcx, [rdi+198h]; lpMem
0x18002f55f  test    rcx, rcx
0x18002f562  jnz     loc_18002F86B
0x18002f568  test    r13, r13
0x18002f56b  jnz     loc_18002F930
0x18002f571  mov     eax, [rbp+40h+arg_50]
0x18002f577  mov     r13, rdx
0x18002f57a  mov     [rsp+140h+var_D0], edx
0x18002f57e  mov     ecx, edx; this
0x18002f580  mov     [rsp+140h+var_E0], rdx
0x18002f585  mov     r12, rdx
0x18002f588  test    al, 1
0x18002f58a  jnz     loc_18002F78E
0x18002f590  test    r15, r15
0x18002f593  jnz     loc_18002F7A5
0x18002f599  mov     rax, [rbp+40h+Src]
0x18002f59d  test    rax, rax
0x18002f5a0  jnz     loc_18002F87E
0x18002f5a6  mov     ecx, [rbp+40h+arg_48]
0x18002f5ac  mov     edx, 3
0x18002f5b1  test    ecx, ecx
0x18002f5b3  jz      loc_18002F7F4
0x18002f5b9  mov     rax, [rbp+40h+arg_28]
0x18002f5bd  mov     dword ptr [rdi+54h], 0Ah
0x18002f5c4  mov     qword ptr [rdi+70h], 0
0x18002f5cc  mov     [rdi+78h], rax
0x18002f5d0  test    r14d, r14d
0x18002f5d3  jz      loc_18002F9C9
0x18002f5d9  mov     eax, [rbp+40h+arg_30]
0x18002f5df  cmp     esi, 1
0x18002f5e2  mov     [rdi+1A0h], ecx
0x18002f5e8  mov     [rdi+84h], ecx
0x18002f5ee  mov     ecx, 1
0x18002f5f3  cmovnz  ecx, [rbp+40h+arg_40]
0x18002f5fa  test    ecx, ecx
0x18002f5fc  mov     [rdi+80h], eax
0x18002f602  mov     eax, ecx
0x18002f604  mov     [rdi+50h], esi
0x18002f607  cmovz   eax, edx
0x18002f60a  mov     [rdi+88h], ecx
0x18002f610  cmp     [rbp+40h+arg_80], 0
0x18002f617  mov     [rdi+1A4h], eax
0x18002f61d  jz      loc_18002F7E9
0x18002f623  mov     rax, [rdi]
0x18002f626  mov     rcx, rdi
0x18002f629  mov     rax, [rax+1A8h]
0x18002f630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f635  mov     esi, [rbp+40h+arg_50]
0x18002f63b  test    eax, eax
0x18002f63d  jnz     loc_18002F8F5
0x18002f643  mov     eax, 0FFFFFFFDh
0x18002f648  and     [rdi+1F0h], eax
0x18002f64e  mov     rcx, [rdi+68h]; lpMem
0x18002f652  mov     [rdi+8Ch], esi
0x18002f658  test    rcx, rcx
0x18002f65b  jnz     loc_18002F77A
0x18002f661  mov     [rdi+68h], r15
0x18002f665  xor     r15d, r15d
0x18002f668  mov     rcx, [rdi+190h]; lpMem
0x18002f66f  test    rcx, rcx
0x18002f672  jz      short loc_18002F679
0x18002f674  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002f679  mov     [rdi+190h], r13
0x18002f680  xor     r13d, r13d
0x18002f683  mov     rcx, [rdi+60h]; lpMem
0x18002f687  test    rcx, rcx
0x18002f68a  jnz     loc_18002F784
0x18002f690  mov     rcx, [rdi+1F8h]; hObject
0x18002f697  xor     esi, esi
0x18002f699  mov     [rdi+60h], r12
0x18002f69d  test    rcx, rcx
0x18002f6a0  jz      short loc_18002F6CF
0x18002f6a2  mov     rax, 0FFFFFFFF00000003h
0x18002f6ac  add     rax, rcx
0x18002f6af  cmp     rax, 1
0x18002f6b3  jbe     short loc_18002F6C1
0x18002f6b5  call    cs:__imp_CloseHandle
0x18002f6bc  nop     dword ptr [rax+rax+00h]
0x18002f6c1  mov     [rdi+1F8h], rsi
0x18002f6c8  mov     [rdi+200h], rsi
0x18002f6cf  cmp     [rdi+1A0h], esi
0x18002f6d5  jnz     short loc_18002F6F7
0x18002f6d7  mov     rax, [rsp+140h+TokenHandle]
0x18002f6dc  mov     [rdi+1F8h], rax
0x18002f6e3  mov     eax, [rbp+40h+var_B8.HighPart]
0x18002f6e6  mov     [rdi+204h], eax
0x18002f6ec  mov     [rsp+140h+TokenHandle], rsi
0x18002f6f1  mov     [rdi+200h], ebx
0x18002f6f7  xor     r12d, r12d
0x18002f6fa  mov     rcx, [rbp+40h+ppszUserName]; unsigned __int16 *
0x18002f6fe  test    rcx, rcx
0x18002f701  jnz     loc_18002FCD4
0x18002f707  mov     rcx, [rbp+40h+ppszPackedCredentialsString]; unsigned __int16 *
0x18002f70b  test    rcx, rcx
0x18002f70e  jnz     loc_18002FCDE
0x18002f714  mov     rcx, [rbp+40h+ppszDomainName]; unsigned __int16 *
0x18002f718  test    rcx, rcx
0x18002f71b  jnz     loc_18002FCE8
0x18002f721  mov     rcx, [rsp+140h+TokenHandle]; void *
0x18002f726  test    rcx, rcx
0x18002f729  jnz     loc_18002FCF2
0x18002f72f  test    r15, r15
0x18002f732  jnz     loc_18002FCFC
0x18002f738  test    r13, r13
0x18002f73b  jnz     loc_18002FD14
0x18002f741  test    rsi, rsi
0x18002f744  jnz     loc_18002FD21
0x18002f74a  mov     eax, r12d
0x18002f74d  mov     r12, [rsp+140h+arg_10]
0x18002f755  mov     r14, [rsp+140h+var_30]
0x18002f75d  mov     rcx, [rbp+40h+var_38]
0x18002f761  xor     rcx, rsp; StackCookie
0x18002f764  call    __security_check_cookie
0x18002f769  add     rsp, 118h
0x18002f770  pop     r15
0x18002f772  pop     r13
0x18002f774  pop     rdi
0x18002f775  pop     rsi
0x18002f776  pop     rbx
0x18002f777  pop     rbp
0x18002f778  retn
0x18002f77a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002f77f  jmp     loc_18002F661
0x18002f784  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002f789  jmp     loc_18002F690
0x18002f78e  test    r15, r15
0x18002f791  jz      loc_18002F8AE
0x18002f797  or      eax, 10h
0x18002f79a  mov     [rbp+40h+arg_50], eax
0x18002f7a0  jmp     loc_18002F590
0x18002f7a5  test    ecx, ecx
0x18002f7a7  jnz     short loc_18002F7C5
0x18002f7a9  mov     rcx, r15; pSourceSid
0x18002f7ac  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18002f7b1  mov     r15, rax
0x18002f7b4  test    rax, rax
0x18002f7b7  jz      loc_18002FAA9
0x18002f7bd  mov     [rsp+140h+var_D0], 1
0x18002f7c5  mov     rcx, r15; pSourceSid
0x18002f7c8  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18002f7cd  mov     r13, rax
0x18002f7d0  test    rax, rax
0x18002f7d3  jnz     loc_18002F599
0x18002f7d9  mov     r12d, 0Eh
0x18002f7df  mov     rsi, [rsp+140h+var_E0]
0x18002f7e4  jmp     loc_18002F6FA
0x18002f7e9  mov     eax, [rbp+40h+arg_78]
0x18002f7ef  jmp     loc_18002F635
0x18002f7f4  mov     rcx, [rbp+40h+var_78]; void *
0x18002f7f8  test    rcx, rcx
0x18002f7fb  jnz     loc_18002FB86
0x18002f801  call    cs:__imp_GetCurrentThread
0x18002f808  nop     dword ptr [rax+rax+00h]
0x18002f80d  mov     r12d, 0Eh
0x18002f813  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x18002f818  mov     edx, r12d; DesiredAccess
0x18002f81b  mov     rcx, rax; ThreadHandle
0x18002f81e  mov     r8b, 1; OpenAsSelf
0x18002f821  call    cs:__imp_NtOpenThreadToken
0x18002f828  nop     dword ptr [rax+rax+00h]
0x18002f82d  cmp     eax, 0C000007Ch
0x18002f832  jnz     loc_18002FA4D
0x18002f838  mov     eax, 0FFFFFFFDh
0x18002f83d  mov     [rsp+140h+TokenHandle], rax
0x18002f842  lea     rcx, [rbp+40h+var_B8]; struct _LUID *
0x18002f846  call    ?CaptureModifiedIdEx@@YAJPEAU_LUID@@@Z; CaptureModifiedIdEx(_LUID *)
0x18002f84b  mov     r12d, eax
0x18002f84e  test    eax, eax
0x18002f850  jnz     short loc_18002F7DF
0x18002f852  mov     rbx, qword ptr [rbp+40h+var_B8.LowPart]
0x18002f856  mov     r12, [rsp+140h+var_E0]
0x18002f85b  mov     ecx, [rbp+40h+arg_48]
0x18002f861  mov     edx, 3
0x18002f866  jmp     loc_18002F5B9
0x18002f86b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002f870  xor     edx, edx
0x18002f872  mov     [rdi+198h], rdx
0x18002f879  jmp     loc_18002F568
0x18002f87e  cmp     [rax], bx
0x18002f881  jz      loc_18002F5A6
0x18002f887  mov     rcx, rax; Src
0x18002f88a  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18002f88f  mov     [rsp+140h+var_E0], rax
0x18002f894  mov     r12, rax
0x18002f897  test    rax, rax
0x18002f89a  jnz     loc_18002F5A6
0x18002f8a0  mov     r12d, 0Eh
0x18002f8a6  mov     rsi, rax
0x18002f8a9  jmp     loc_18002F6FA
0x18002f8ae  cmp     qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision, rbx; SID_CACHE * SIDCache ...
0x18002f8b5  jz      loc_18002FB70
0x18002f8bb  mov     rdx, [rbp+40h+Src]; unsigned __int16 *
0x18002f8bf  lea     r8, [rsp+140h+var_C8]; void **
0x18002f8c4  call    ?Query@SID_CACHE@@QEAAJPEBGPEAPEAX@Z; SID_CACHE::Query(ushort const *,void * *)
0x18002f8c9  mov     r12d, eax
0x18002f8cc  test    eax, eax
0x18002f8ce  jnz     short loc_18002F94F
0x18002f8d0  mov     r15, [rsp+140h+var_C8]
0x18002f8d5  test    r15, r15
0x18002f8d8  jz      loc_18002F977
0x18002f8de  mov     eax, [rbp+40h+arg_50]
0x18002f8e4  mov     ecx, 1
0x18002f8e9  mov     [rsp+140h+var_D0], ecx
0x18002f8ed  mov     r12, r13
0x18002f8f0  jmp     loc_18002F797
0x18002f8f5  mov     eax, [rdi+1F0h]
0x18002f8fb  or      eax, 2
0x18002f8fe  mov     [rdi+1F0h], eax
0x18002f904  jmp     loc_18002F64E
0x18002f909  mov     [rsp+140h+ReturnLength], rdx; struct tagParam *
0x18002f90e  mov     r8d, 35Ch; unsigned __int16
0x18002f914  mov     edx, 6E4h; int
0x18002f919  xor     r9d, r9d; int
0x18002f91c  mov     ecx, 2; unsigned int
0x18002f921  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002f926  mov     eax, 6E4h
0x18002f92b  jmp     loc_18002F75D
0x18002f930  lea     r8, [rdi+198h]; void **
0x18002f937  mov     edx, 18h; AutoInheritFlags
0x18002f93c  mov     rcx, r13; CreatorDescriptor
0x18002f93f  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x18002f944  test    eax, eax
0x18002f946  jnz     short loc_18002F9BF
0x18002f948  xor     edx, edx
0x18002f94a  jmp     loc_18002F571
0x18002f94f  xor     edx, edx
0x18002f951  mov     [rsp+140h+ReturnLength], rdx; struct tagParam *
0x18002f956  mov     r8d, 35Eh; unsigned __int16
0x18002f95c  mov     edx, r12d; int
0x18002f95f  xor     r9d, r9d; int
0x18002f962  mov     ecx, 2; unsigned int
0x18002f967  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002f96c  xor     r15d, r15d
0x18002f96f  mov     rsi, r13
0x18002f972  jmp     loc_18002F6FA
0x18002f977  mov     rcx, [rbp+40h+Src]; lpAccountName
0x18002f97b  lea     rdx, [rsp+140h+var_C8]; void **
0x18002f980  call    ?RpcpLookupAccountNameDirect@@YAJPEBGPEAPEAX@Z; RpcpLookupAccountNameDirect(ushort const *,void * *)
0x18002f985  mov     r15, [rsp+140h+var_C8]
0x18002f98a  mov     r12d, eax
0x18002f98d  cmp     eax, 6FDh
0x18002f992  jz      loc_18002FB7B
0x18002f998  test    eax, eax
0x18002f99a  jnz     short loc_18002F9B4
0x18002f99c  cmp     qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision, rbx; SID_CACHE * SIDCache ...
0x18002f9a3  jz      short loc_18002F9B4
0x18002f9a5  mov     rdx, [rbp+40h+Src]; unsigned __int16 *
0x18002f9a9  xor     r9d, r9d; int
0x18002f9ac  mov     r8, r15; void *
  ... truncated ...
```
