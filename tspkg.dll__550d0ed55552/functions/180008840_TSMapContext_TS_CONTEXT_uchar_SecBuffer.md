# TSMapContext(_TS_CONTEXT *,uchar *,_SecBuffer *)

- ea: `0x180008840`
- end: `0x180009062`
- name: `?TSMapContext@@YAJPEAU_TS_CONTEXT@@PEAEPEAU_SecBuffer@@@Z`
- size: `2082`
- prototype: `__int64 __fastcall(struct _TS_CONTEXT *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001160`
- `0x180006650`

## callees

- `0x1800032c0`
- `0x180005ed0`
- `0x180008810`
- `0x180008840`
- `0x18000b550`
- `0x180017314`
- `0x18001a12c`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a4d`
- `SspiCli!SspiFreeAuthIdentity` at `0x180008a65`
- `SspiCli!SspiFreeAuthIdentity` at `0x180008a65`
- `SspiCli!QueryContextAttributesW` at `0x180008920`
- `SspiCli!QueryContextAttributesW` at `0x180008bf2`
- `SspiCli!QueryContextAttributesW` at `0x180008e5e`
- `SspiCli!QueryContextAttributesW` at `0x180008920`
- `SspiCli!QueryContextAttributesW` at `0x180008bf2`
- `SspiCli!QueryContextAttributesW` at `0x180008e5e`
- `SspiCli!FreeContextBuffer` at `0x180008a2e`
- `SspiCli!FreeContextBuffer` at `0x180008a2e`
- `SspiCli!SspiCopyAuthIdentity` at `0x1800089e7`
- `SspiCli!SspiCopyAuthIdentity` at `0x1800089e7`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180008ac7`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180008ac7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180008f56`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180008f92`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180008f56`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180008f92`
- `ntdll!NtQueryInformationToken` at `0x180008eac`
- `ntdll!NtQueryInformationToken` at `0x180008ee5`
- `ntdll!NtQueryInformationToken` at `0x180008eac`
- `ntdll!NtQueryInformationToken` at `0x180008ee5`
- `ntdll!RtlInitUnicodeString` at `0x180008c11`
- `ntdll!RtlInitUnicodeString` at `0x180008c22`
- `ntdll!RtlInitUnicodeString` at `0x180008c11`
- `ntdll!RtlInitUnicodeString` at `0x180008c22`

## pseudocode

```c
__int64 __fastcall TSMapContext(struct _TS_CONTEXT *a1, unsigned __int8 *a2, struct _SecBuffer *a3)
{
  int v4; // ecx
  SECURITY_STATUS InformationToken; // ebx
  __int64 v6; // rdx
  char v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rax
  bool v10; // zf
  unsigned int v11; // r13d
  unsigned int v12; // esi
  unsigned int v13; // r12d
  __int64 v14; // rdx
  __int64 v15; // rcx
  PWSTR Buffer; // rcx
  __int64 MaximumLength; // rax
  char *v19; // rax
  const WCHAR *v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // r8d
  __int64 v23; // rdx
  unsigned int v24; // ecx
  __int64 v25; // rax
  _DWORD *v26; // rdi
  char *v27; // r15
  char *v28; // rbx
  char *v29; // rbx
  char *v30; // rbx
  __int64 v31; // rdx
  char *v32; // rbx
  struct _SecBuffer *v33; // rax
  char v34; // [rsp+38h] [rbp-D0h]
  PVOID pBuffer; // [rsp+40h] [rbp-C8h] BYREF
  struct _UNICODE_STRING pBuffer_8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 TokenInformation; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy[3]; // [rsp+70h] [rbp-98h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-70h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-68h] BYREF
  const WCHAR *v44; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-50h] BYREF
  struct _UNICODE_STRING v47; // [rsp+C0h] [rbp-48h] BYREF
  struct _SecBuffer *v48; // [rsp+D0h] [rbp-38h]
  unsigned __int8 *v49; // [rsp+D8h] [rbp-30h]
  _DWORD v50[10]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v51[10]; // [rsp+108h] [rbp+0h] BYREF
  _DWORD v52[14]; // [rsp+158h] [rbp+50h] BYREF

  v49 = a2;
  TokenHandle = 0;
  pBuffer = 0;
  v4 = 0;
  v46 = 0;
  memset(v52, 0, sizeof(v52));
  v48 = a3;
  memset(v50, 0, 32);
  hObject = 0;
  v45 = 0;
  DuplicateTokenHandle = 0;
  v43 = 0;
  TokenInformation = 0;
  memset(AuthDataCopy, 0, sizeof(AuthDataCopy));
  DestinationString = 0;
  pBuffer_8 = 0;
  if ( !a1 )
    return 3221225485LL;
  LOBYTE(v4) = a3 == 0;
  if ( (a2 == 0) | v4 )
    return 3221225485LL;
  InformationToken = QueryContextAttributesW((PCtxtHandle)((char *)a1 + 24), 0xAu, &pBuffer);
  if ( InformationToken < 0 || !pBuffer )
    goto LABEL_20;
  v6 = *((_QWORD *)pBuffer + 2);
  v7 = 0;
  v34 = 0;
  v8 = -1;
  if ( !v6 )
  {
    v12 = 84;
    v11 = 0;
    goto LABEL_11;
  }
  v9 = -1;
  do
    v10 = *(_WORD *)(v6 + 2 * v9++ + 2) == 0;
  while ( !v10 );
  v11 = 2 * v9 + 2;
  v12 = 2 * v9 + 86;
  if ( v12 >= 0x54 )
  {
LABEL_11:
    v13 = 0;
    v14 = *((_QWORD *)pBuffer + 3);
    if ( v14 )
    {
      do
        v10 = *(_WORD *)(v14 + 2 * v8++ + 2) == 0;
      while ( !v10 );
      v13 = 2 * v8 + 2;
      if ( v13 + v12 < v12 )
      {
        InformationToken = -1073741675;
LABEL_20:
        v7 = 0;
        goto LABEL_21;
      }
      v12 += v13;
    }
    v15 = *((_QWORD *)a1 + 12);
    if ( !v15 )
      goto LABEL_53;
    if ( *(_DWORD *)v15 == 3 )
    {
      v34 = 1;
      InformationToken = SspiCopyAuthIdentity(*(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(v15 + 168), AuthDataCopy);
      if ( InformationToken < 0 )
      {
        v7 = 1;
        AuthDataCopy[0] = 0;
        goto LABEL_21;
      }
      InformationToken = SspiEncryptAuthIdentityEx(1u, AuthDataCopy[0]);
      if ( InformationToken >= 0 )
      {
        InformationToken = TSUnpackAuthIdEx2LogonBuffer(
                             AuthDataCopy[0],
                             0,
                             (struct _UNICODE_STRING *)&AuthDataCopy[1],
                             &DestinationString,
                             &pBuffer_8);
        if ( InformationToken >= 0 )
          goto LABEL_49;
      }
LABEL_79:
      v7 = v34;
      goto LABEL_21;
    }
    if ( *(_DWORD *)v15 == 6 )
    {
      *(_DWORD *)v15 = 1;
      memset(v51, 0, 72);
      *(_QWORD *)&v47.Length = 4718664;
      v47.Buffer = (PWSTR)v51;
      v44 = 0;
      v19 = (char *)TSAllocate(0x20u);
      if ( !v19 )
      {
        InformationToken = -1073741801;
        goto LABEL_20;
      }
      *(_QWORD *)v19 = a1;
      v19[24] = 1;
      *(_OWORD *)(v19 + 8) = 0;
      v51[3] = TSInitRedirectedLogon;
      v51[4] = TSDoRedirectedLogonOperation;
      v51[5] = TSCleanupRedirectedLogon;
      v51[6] = TSGetRedirectedLogonCreds;
      v51[7] = TSGetRedirectedSuppCreds;
      v51[8] = TSGetRedirectedLogonSid;
      v51[2] = v19;
      LODWORD(v51[0]) = -1027713961;
      *(_QWORD *)((char *)v51 + 4) = 0x68744EAE483E82EBLL;
      HIDWORD(v51[1]) = 164959471;
      InformationToken = TSProtectPassword(&v47, &pBuffer_8);
      if ( InformationToken < 0 )
        goto LABEL_79;
      if ( QueryContextAttributesW((PCtxtHandle)((char *)a1 + 24), 1u, &v44) < 0 || (v20 = v44) == 0 )
        v20 = L"Unknown";
      RtlInitUnicodeString((PUNICODE_STRING)&AuthDataCopy[1], v20);
      RtlInitUnicodeString(&DestinationString, &word_18001FCF4);
    }
    else
    {
      InformationToken = TSProtectPassword((struct _UNICODE_STRING *)(v15 + 40), &pBuffer_8);
      if ( InformationToken < 0 )
        goto LABEL_79;
      v21 = *((_QWORD *)a1 + 12);
      *(_OWORD *)&AuthDataCopy[1] = *(_OWORD *)(v21 + 24);
      DestinationString = *(_UNICODE_STRING *)(v21 + 8);
    }
LABEL_49:
    v22 = pBuffer_8.Length + v12 + DestinationString.Length + LOWORD(AuthDataCopy[1]);
    if ( v22 < v12
      || (v23 = *((_QWORD *)a1 + 12), v24 = v22 + *(_DWORD *)(v23 + 72), v24 < v22)
      || (v12 = v24 + *(_DWORD *)(v23 + 160), v12 < v24) )
    {
      v7 = v34;
      InformationToken = -1073741675;
      goto LABEL_21;
    }
LABEL_53:
    v25 = ((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocateLsaHeap)(v12);
    v26 = (_DWORD *)v25;
    if ( !v25 )
    {
      InformationToken = -1073741670;
      goto LABEL_81;
    }
    v27 = (char *)(v25 + 84);
    if ( *((_QWORD *)a1 + 12) )
    {
      memcpy_0((void *)(v25 + 84), AuthDataCopy[2], LOWORD(AuthDataCopy[1]));
      v26[7] = (_DWORD)v27 - (_DWORD)v26;
      *((_WORD *)v26 + 12) = AuthDataCopy[1];
      *((_WORD *)v26 + 13) = AuthDataCopy[1];
      v28 = &v27[LOWORD(AuthDataCopy[1])];
      memcpy_0(v28, DestinationString.Buffer, DestinationString.Length);
      v26[5] = (_DWORD)v28 - (_DWORD)v26;
      *((_WORD *)v26 + 8) = DestinationString.Length;
      *((_WORD *)v26 + 9) = DestinationString.Length;
      v29 = &v28[DestinationString.Length];
      memcpy_0(v29, pBuffer_8.Buffer, pBuffer_8.Length);
      v26[9] = (_DWORD)v29 - (_DWORD)v26;
      *((_WORD *)v26 + 16) = pBuffer_8.Length;
      *((_WORD *)v26 + 17) = pBuffer_8.Length;
      v30 = &v29[pBuffer_8.Length];
      memcpy_0(v30, *(const void **)(*((_QWORD *)a1 + 12) + 64LL), *(unsigned int *)(*((_QWORD *)a1 + 12) + 72LL));
      v26[10] = (_DWORD)v30 - (_DWORD)v26;
      v26[11] = *(_DWORD *)(*((_QWORD *)a1 + 12) + 72LL);
      v31 = *((_QWORD *)a1 + 12);
      v32 = &v30[*(unsigned int *)(v31 + 72)];
      memcpy_0(v32, *(const void **)(v31 + 152), *(unsigned int *)(v31 + 160));
      v26[12] = (_DWORD)v32 - (_DWORD)v26;
      v26[13] = *(_DWORD *)(*((_QWORD *)a1 + 12) + 160LL);
      v27 = &v32[*(unsigned int *)(*((_QWORD *)a1 + 12) + 160LL)];
    }
    v26[14] = *(_DWORD *)pBuffer;
    *((_WORD *)v26 + 30) = *((_WORD *)pBuffer + 2);
    *((_WORD *)v26 + 31) = *((_WORD *)pBuffer + 3);
    v26[16] = *((_DWORD *)pBuffer + 2);
    if ( v11 )
    {
      memcpy_0(v27, *((const void **)pBuffer + 2), v11);
      v26[17] = (_DWORD)v27 - (_DWORD)v26;
      v27 += v11;
    }
    if ( v13 )
    {
      memcpy_0(v27, *((const void **)pBuffer + 3), v13);
      v26[18] = (_DWORD)v27 - (_DWORD)v26;
    }
    if ( !*((_QWORD *)a1 + 12) || QueryContextAttributesW((PCtxtHandle)((char *)a1 + 24), 0x12u, &TokenHandle) < 0 )
    {
LABEL_78:
      InformationToken = 0;
      v26[3] = *((_DWORD *)a1 + 30);
      *(_QWORD *)(v26 + 19) = *(_QWORD *)((char *)a1 + 132);
      v33 = v48;
      v48->pvBuffer = v26;
      v33->cbBuffer = v12;
      *v49 = 1;
      goto LABEL_79;
    }
    InformationToken = ((__int64 (__fastcall *)(_DWORD *))TSGlobalLsaFunctions->GetClientInfo)(v50);
    if ( InformationToken >= 0 )
    {
      InformationToken = NtQueryInformationToken(
                           TokenHandle,
                           TokenElevationType,
                           &TokenInformation,
                           4u,
                           (PULONG)&TokenInformation + 1);
      if ( InformationToken >= 0 )
      {
        if ( (_DWORD)TokenInformation != 3 )
        {
          if ( DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
          {
            InformationToken = ((__int64 (__fastcall *)(HANDLE, __int64 *))TSGlobalLsaFunctions->DuplicateHandle)(
                                 DuplicateTokenHandle,
                                 &v43);
            if ( InformationToken < 0 )
              goto LABEL_81;
LABEL_76:
            v26[2] = v43;
            InformationToken = ((__int64 (__fastcall *)(HANDLE, __int64 *))TSGlobalLsaFunctions->DuplicateHandle)(
                                 TokenHandle,
                                 &v46);
            if ( InformationToken < 0 )
              goto LABEL_81;
            *v26 = v46;
            goto LABEL_78;
          }
LABEL_80:
          InformationToken = -1073741801;
          goto LABEL_81;
        }
        InformationToken = NtQueryInformationToken(
                             TokenHandle,
                             TokenStatistics,
                             v52,
                             0x38u,
                             (PULONG)&TokenInformation + 1);
        if ( InformationToken >= 0 )
        {
          InformationToken = ((__int64 (__fastcall *)(_DWORD *, HANDLE *))TSGlobalLsaFunctions->OpenTokenByLogonId)(
                               &v52[2],
                               &hObject);
          if ( InformationToken >= 0 )
          {
            if ( LOBYTE(v50[4]) )
            {
              InformationToken = ((__int64 (__fastcall *)(HANDLE, __int64 *))TSGlobalLsaFunctions->DuplicateHandle)(
                                   hObject,
                                   &v45);
              if ( InformationToken < 0 )
                goto LABEL_81;
              v26[1] = v45;
            }
            if ( DuplicateToken(hObject, SecurityIdentification, &DuplicateTokenHandle) )
            {
              InformationToken = ((__int64 (__fastcall *)(HANDLE, __int64 *))TSGlobalLsaFunctions->DuplicateHandle)(
                                   DuplicateTokenHandle,
                                   &v43);
              if ( InformationToken < 0 )
                goto LABEL_81;
              goto LABEL_76;
            }
            goto LABEL_80;
          }
        }
      }
    }
LABEL_81:
    if ( v26 )
    {
      ((void (__fastcall *)(_DWORD *))TSGlobalLsaFunctions->FreeLsaHeap)(v26);
      v7 = v34;
      goto LABEL_21;
    }
    goto LABEL_79;
  }
  InformationToken = -1073741675;
LABEL_21:
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  if ( hObject )
    CloseHandle(hObject);
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( v7 )
  {
    SspiFreeAuthIdentity(AuthDataCopy[0]);
    TSFreeString((struct _UNICODE_STRING *)&AuthDataCopy[1]);
    TSFreeString(&DestinationString);
  }
  Buffer = pBuffer_8.Buffer;
  if ( pBuffer_8.Buffer )
  {
    MaximumLength = pBuffer_8.MaximumLength;
    if ( pBuffer_8.MaximumLength )
    {
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --MaximumLength;
      }
      while ( MaximumLength );
      Buffer = pBuffer_8.Buffer;
    }
    if ( Buffer )
      TSFree(Buffer);
  }
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x180008840  mov     r11, rsp
0x180008843  push    rbp
0x180008844  push    r14
0x180008846  push    r15
0x180008848  lea     rbp, [r11-0C8h]
0x18000884f  sub     rsp, 1B0h
0x180008856  mov     rax, cs:__security_cookie
0x18000885d  xor     rax, rsp
0x180008860  mov     [rbp+0C0h+var_38], rax
0x180008867  xor     r15d, r15d
0x18000886a  mov     [rbp+0C0h+var_F0], rdx
0x18000886e  xorps   xmm0, xmm0
0x180008871  mov     [rsp+1C0h+TokenHandle], r15
0x180008876  mov     r14, rcx
0x180008879  mov     qword ptr [rsp+1C0h+pBuffer], r15
0x18000887e  xor     ecx, ecx
0x180008880  mov     [rbp+0C0h+var_110], r15
0x180008884  mov     [rbp+0C0h+var_70], r15d
0x180008888  mov     rax, r8
0x18000888b  mov     [rbp+0C0h+var_F8], rax
0x18000888f  xorps   xmm1, xmm1
0x180008892  mov     [rbp+0C0h+var_3C], ecx
0x180008898  mov     [rbp+0C0h+var_E8], r15d
0x18000889c  mov     [rbp+0C0h+hObject], r15
0x1800088a0  mov     [rbp+0C0h+var_118], r15
0x1800088a4  mov     [rsp+1C0h+DuplicateTokenHandle], r15
0x1800088a9  mov     [rbp+0C0h+var_128], r15
0x1800088ad  mov     dword ptr [rsp+1C0h+TokenInformation+4], r15d
0x1800088b2  mov     dword ptr [rsp+1C0h+TokenInformation], r15d
0x1800088b7  mov     qword ptr [rsp+1C0h+AuthDataCopy], r15
0x1800088bc  movups  xmmword ptr [rbp+0C0h+var_E4], xmm0
0x1800088c0  movups  [rbp+0C0h+var_6C], xmm0
0x1800088c4  movups  [rbp+0C0h+var_5C], xmm0
0x1800088c8  movups  [rbp+0C0h+var_4C], xmm0
0x1800088cc  movups  xmmword ptr [rbp+0C0h+var_E4+0Ch], xmm0
0x1800088d0  movups  xmmword ptr [rsp+1C0h+AuthDataCopy+8], xmm0
0x1800088d5  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x1800088d9  movups  [rsp+1C0h+pBuffer+8], xmm0
0x1800088de  test    r14, r14
0x1800088e1  jz      loc_180009041
0x1800088e7  test    rax, rax
0x1800088ea  mov     eax, r15d
0x1800088ed  setz    cl
0x1800088f0  test    rdx, rdx
0x1800088f3  setz    al
0x1800088f6  or      ecx, eax
0x1800088f8  jnz     loc_180009041
0x1800088fe  mov     [r11+20h], rbx
0x180008902  lea     r8, [rsp+1C0h+pBuffer]; pBuffer
0x180008907  mov     [r11-28h], rdi
0x18000890b  lea     rcx, [r14+18h]; phContext
0x18000890f  mov     [r11-30h], r12
0x180008913  mov     edx, 0Ah; ulAttribute
0x180008918  mov     [r11-20h], rsi
0x18000891c  mov     [r11-38h], r13
0x180008920  call    cs:__imp_QueryContextAttributesW
0x180008926  mov     ebx, eax
0x180008928  test    eax, eax
0x18000892a  js      loc_180008A09
0x180008930  mov     rcx, qword ptr [rsp+1C0h+pBuffer]
0x180008935  test    rcx, rcx
0x180008938  jz      loc_180008A09
0x18000893e  mov     rdx, [rcx+10h]
0x180008942  xor     r12b, r12b
0x180008945  mov     byte ptr [rsp+1C0h+var_190], r12b
0x18000894a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008951  test    rdx, rdx
0x180008954  jz      short loc_180008987
0x180008956  mov     rax, rcx
0x180008959  nop     dword ptr [rax+00000000h]
0x180008960  cmp     [rdx+rax*2+2], r15w
0x180008966  lea     rax, [rax+1]
0x18000896a  jnz     short loc_180008960
0x18000896c  lea     r13d, ds:2[rax*2]
0x180008974  lea     esi, [r13+54h]
0x180008978  cmp     esi, 54h ; 'T'
0x18000897b  jnb     short loc_18000898F
0x18000897d  mov     ebx, 0C0000095h
0x180008982  jmp     loc_180008A0C
0x180008987  mov     esi, 54h ; 'T'
0x18000898c  mov     r13d, r15d
0x18000898f  mov     rax, qword ptr [rsp+1C0h+pBuffer]
0x180008994  mov     r12d, r15d
0x180008997  mov     rdx, [rax+18h]
0x18000899b  test    rdx, rdx
0x18000899e  jz      short loc_1800089BE
0x1800089a0  cmp     [rdx+rcx*2+2], r15w
0x1800089a6  lea     rcx, [rcx+1]
0x1800089aa  jnz     short loc_1800089A0
0x1800089ac  lea     r12d, ds:2[rcx*2]
0x1800089b4  lea     eax, [r12+rsi]
0x1800089b8  cmp     eax, esi
0x1800089ba  jb      short loc_180008A04
0x1800089bc  mov     esi, eax
0x1800089be  mov     rcx, [r14+60h]
0x1800089c2  test    rcx, rcx
0x1800089c5  jz      loc_180008C9D
0x1800089cb  mov     eax, [rcx]
0x1800089cd  cmp     eax, 3
0x1800089d0  jnz     loc_180008B05
0x1800089d6  mov     rcx, [rcx+0A8h]; AuthData
0x1800089dd  lea     rdx, [rsp+1C0h+AuthDataCopy]; AuthDataCopy
0x1800089e2  mov     byte ptr [rsp+1C0h+var_190], 1
0x1800089e7  call    cs:__imp_SspiCopyAuthIdentity
0x1800089ed  mov     ebx, eax
0x1800089ef  test    eax, eax
0x1800089f1  jns     loc_180008ABD
0x1800089f7  movzx   r12d, byte ptr [rsp+1C0h+var_190]
0x1800089fd  mov     qword ptr [rsp+1C0h+AuthDataCopy], r15
0x180008a02  jmp     short loc_180008A0C
0x180008a04  mov     ebx, 0C0000095h
0x180008a09  xor     r12b, r12b
0x180008a0c  mov     rcx, qword ptr [rsp+1C0h+pBuffer]; pvContextBuffer
0x180008a11  mov     r13, [rsp+1C0h+var_30]
0x180008a19  mov     rdi, [rsp+1C0h+var_20]
0x180008a21  mov     rsi, [rsp+1A8h]
0x180008a29  test    rcx, rcx
0x180008a2c  jz      short loc_180008A34
0x180008a2e  call    cs:__imp_FreeContextBuffer
0x180008a34  mov     rcx, [rbp+0C0h+hObject]; hObject
0x180008a38  test    rcx, rcx
0x180008a3b  jz      short loc_180008A43
0x180008a3d  call    cs:__imp_CloseHandle
0x180008a43  mov     rcx, [rsp+1C0h+DuplicateTokenHandle]; hObject
0x180008a48  test    rcx, rcx
0x180008a4b  jz      short loc_180008A53
0x180008a4d  call    cs:__imp_CloseHandle
0x180008a53  test    r12b, r12b
0x180008a56  mov     r12, [rsp+1C0h+var_28]
0x180008a5e  jz      short loc_180008A7E
0x180008a60  mov     rcx, qword ptr [rsp+1C0h+AuthDataCopy]; AuthData
0x180008a65  call    cs:__imp_SspiFreeAuthIdentity
0x180008a6b  lea     rcx, [rsp+1C0h+AuthDataCopy+8]; struct _UNICODE_STRING *
0x180008a70  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x180008a75  lea     rcx, [rbp+0C0h+DestinationString]; struct _UNICODE_STRING *
0x180008a79  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x180008a7e  mov     rcx, [rsp+1C0h+Src]
0x180008a83  test    rcx, rcx
0x180008a86  jz      short loc_180008AAE
0x180008a88  movzx   eax, word ptr [rsp+1C0h+pBuffer+0Ah]
0x180008a8d  test    rax, rax
0x180008a90  jz      short loc_180008AA4
0x180008a92  mov     byte ptr [rcx], 0
0x180008a95  lea     rcx, [rcx+1]
0x180008a99  sub     rax, 1
0x180008a9d  jnz     short loc_180008A92
0x180008a9f  mov     rcx, [rsp+1C0h+Src]; void *
0x180008aa4  test    rcx, rcx
0x180008aa7  jz      short loc_180008AAE
0x180008aa9  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180008aae  mov     eax, ebx
0x180008ab0  mov     rbx, [rsp+1C0h+arg_18]
0x180008ab8  jmp     loc_180009046
0x180008abd  mov     rdx, qword ptr [rsp+1C0h+AuthDataCopy]; AuthData
0x180008ac2  mov     ecx, 1; Options
0x180008ac7  call    cs:__imp_SspiEncryptAuthIdentityEx
0x180008acd  mov     ebx, eax
0x180008acf  test    eax, eax
0x180008ad1  js      loc_18000900E
0x180008ad7  mov     rcx, qword ptr [rsp+1C0h+AuthDataCopy]; pAuthIdentity
0x180008adc  lea     rax, [rsp+1C0h+pBuffer+8]
0x180008ae1  lea     r9, [rbp+0C0h+DestinationString]; struct _UNICODE_STRING *
0x180008ae5  mov     [rsp+20h], rax; struct _UNICODE_STRING *
0x180008aea  lea     r8, [rsp+1C0h+AuthDataCopy+8]; struct _UNICODE_STRING *
0x180008aef  xor     edx, edx; unsigned __int8
0x180008af1  call    ?TSUnpackAuthIdEx2LogonBuffer@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@EPEAU_UNICODE_STRING@@11@Z; TSUnpackAuthIdEx2LogonBuffer(_SEC_WINNT_AUTH_IDENTITY_EX2 *,uchar,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180008af6  mov     ebx, eax
0x180008af8  test    eax, eax
0x180008afa  js      loc_18000900E
0x180008b00  jmp     loc_180008C57
0x180008b05  cmp     eax, 6
0x180008b08  jnz     loc_180008C2A
0x180008b0e  xorps   xmm0, xmm0
0x180008b11  mov     dword ptr [rcx], 1
0x180008b17  xor     eax, eax
0x180008b19  mov     [rbp+0C0h+var_C0], r15d
0x180008b1d  mov     [rbp+0C0h+var_7C], eax
0x180008b20  mov     ecx, 20h ; ' '; Size
0x180008b25  lea     rax, [rbp+0C0h+var_C0]
0x180008b29  mov     qword ptr [rbp+0C0h+var_108.Length], 480048h
0x180008b31  mov     [rbp+0C0h+var_108.Buffer], rax
0x180008b35  movups  [rbp+0C0h+var_BC], xmm0
0x180008b39  mov     [rbp+0C0h+var_120], r15
0x180008b3d  movups  [rbp+0C0h+var_AC], xmm0
0x180008b41  movups  [rbp+0C0h+var_9C], xmm0
0x180008b45  movups  [rbp+0C0h+var_8C], xmm0
0x180008b49  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180008b4e  test    rax, rax
0x180008b51  jnz     short loc_180008B5D
0x180008b53  mov     ebx, 0C0000017h
0x180008b58  jmp     loc_180008A09
0x180008b5d  mov     [rax], r14
0x180008b60  lea     rcx, ?TSInitRedirectedLogon@@YAJPEAXPEBU_UNICODE_STRING@@KPEBU_LUID@@@Z; TSInitRedirectedLogon(void *,_UNICODE_STRING const *,ulong,_LUID const *)
0x180008b67  mov     byte ptr [rax+18h], 1
0x180008b6b  lea     rdx, [rsp+1C0h+pBuffer+8]; DestinationString
0x180008b70  xorps   xmm0, xmm0
0x180008b73  movups  xmmword ptr [rax+8], xmm0
0x180008b77  mov     qword ptr [rbp+0C0h+var_AC+4], rcx
0x180008b7b  lea     rcx, ?TSDoRedirectedLogonOperation@@YAJPEAX0KPEAPEAXPEAK@Z; TSDoRedirectedLogonOperation(void *,void *,ulong,void * *,ulong *)
0x180008b82  mov     qword ptr [rbp+0C0h+var_AC+0Ch], rcx
0x180008b86  lea     rcx, ?TSCleanupRedirectedLogon@@YAXPEAX@Z; TSCleanupRedirectedLogon(void *)
0x180008b8d  mov     qword ptr [rbp+0C0h+var_9C+4], rcx
0x180008b91  lea     rcx, ?TSGetRedirectedLogonCreds@@YAJPEAXPEAPEAEPEAK@Z; TSGetRedirectedLogonCreds(void *,uchar * *,ulong *)
0x180008b98  mov     qword ptr [rbp+0C0h+var_9C+0Ch], rcx
0x180008b9c  lea     rcx, ?TSGetRedirectedSuppCreds@@YAJPEAXPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; TSGetRedirectedSuppCreds(void *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x180008ba3  mov     qword ptr [rbp+0C0h+var_8C+4], rcx
0x180008ba7  lea     rcx, ?TSGetRedirectedLogonSid@@YAJPEAXPEAPEAX@Z; TSGetRedirectedLogonSid(void *,void * *)
0x180008bae  mov     qword ptr [rbp+0C0h+var_8C+0Ch], rcx
0x180008bb2  lea     rcx, [rbp+0C0h+var_108]; struct _UNICODE_STRING *
0x180008bb6  mov     qword ptr [rbp+0C0h+var_BC+0Ch], rax
0x180008bba  mov     [rbp+0C0h+var_C0], 0C2BE5457h
0x180008bc1  mov     dword ptr [rbp+0C0h+var_BC], 483E82EBh
0x180008bc8  mov     dword ptr [rbp+0C0h+var_BC+4], 68744EAEh
0x180008bcf  mov     dword ptr [rbp+0C0h+var_BC+8], 9D514EFh
0x180008bd6  call    ?TSProtectPassword@@YAJPEAU_UNICODE_STRING@@0@Z; TSProtectPassword(_UNICODE_STRING *,_UNICODE_STRING *)
0x180008bdb  mov     ebx, eax
0x180008bdd  test    eax, eax
0x180008bdf  js      loc_18000900E
0x180008be5  lea     r8, [rbp+0C0h+var_120]; pBuffer
0x180008be9  mov     edx, 1; ulAttribute
0x180008bee  lea     rcx, [r14+18h]; phContext
0x180008bf2  call    cs:__imp_QueryContextAttributesW
0x180008bf8  test    eax, eax
0x180008bfa  js      short loc_180008C05
0x180008bfc  mov     rdx, [rbp+0C0h+var_120]
0x180008c00  test    rdx, rdx
0x180008c03  jnz     short loc_180008C0C
0x180008c05  lea     rdx, SourceString; "Unknown"
0x180008c0c  lea     rcx, [rsp+1C0h+AuthDataCopy+8]; DestinationString
0x180008c11  call    cs:__imp_RtlInitUnicodeString
0x180008c17  lea     rdx, word_18001FCF4; SourceString
0x180008c1e  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x180008c22  call    cs:__imp_RtlInitUnicodeString
0x180008c28  jmp     short loc_180008C57
0x180008c2a  add     rcx, 28h ; '('; struct _UNICODE_STRING *
0x180008c2e  lea     rdx, [rsp+1C0h+pBuffer+8]; DestinationString
0x180008c33  call    ?TSProtectPassword@@YAJPEAU_UNICODE_STRING@@0@Z; TSProtectPassword(_UNICODE_STRING *,_UNICODE_STRING *)
0x180008c38  mov     ebx, eax
0x180008c3a  test    eax, eax
0x180008c3c  js      loc_18000900E
0x180008c42  mov     rax, [r14+60h]
0x180008c46  movups  xmm0, xmmword ptr [rax+18h]
0x180008c4a  movups  xmmword ptr [rsp+1C0h+AuthDataCopy+8], xmm0
0x180008c4f  movups  xmm1, xmmword ptr [rax+8]
0x180008c53  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x180008c57  movzx   edx, [rbp+0C0h+DestinationString.Length]
0x180008c5b  movzx   ecx, word ptr [rsp+1C0h+pBuffer+8]
0x180008c60  add     edx, esi
0x180008c62  movzx   r8d, word ptr [rsp+1C0h+AuthDataCopy+8]
0x180008c68  add     edx, ecx
0x180008c6a  add     r8d, edx
0x180008c6d  cmp     r8d, esi
0x180008c70  jb      short loc_180008C8D
0x180008c72  mov     rdx, [r14+60h]
0x180008c76  mov     ecx, [rdx+48h]
0x180008c79  add     ecx, r8d
0x180008c7c  cmp     ecx, r8d
0x180008c7f  jb      short loc_180008C8D
0x180008c81  mov     esi, [rdx+0A0h]
0x180008c87  add     esi, ecx
0x180008c89  cmp     esi, ecx
0x180008c8b  jnb     short loc_180008C9D
0x180008c8d  movzx   r12d, byte ptr [rsp+1C0h+var_190]
0x180008c93  mov     ebx, 0C0000095h
0x180008c98  jmp     loc_180008A0C
0x180008c9d  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180008ca4  mov     ecx, esi
0x180008ca6  mov     rax, [rax+28h]
0x180008caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008caf  mov     rdi, rax
0x180008cb2  test    rax, rax
0x180008cb5  jnz     short loc_180008CC1
0x180008cb7  mov     ebx, 0C000009Ah
0x180008cbc  jmp     loc_18000901E
0x180008cc1  cmp     qword ptr [r14+60h], 0
0x180008cc6  lea     r15, [rax+54h]
0x180008cca  jz      loc_180008DCF
0x180008cd0  movzx   r8d, word ptr [rsp+1C0h+AuthDataCopy+8]; Size
0x180008cd6  mov     rcx, r15; void *
0x180008cd9  mov     rdx, qword ptr [rsp+1C0h+AuthDataCopy+10h]; Src
0x180008cde  call    memcpy_0
0x180008ce3  mov     eax, r15d
0x180008ce6  sub     eax, edi
0x180008ce8  mov     [rdi+1Ch], eax
0x180008ceb  movzx   eax, word ptr [rsp+1C0h+AuthDataCopy+8]
0x180008cf0  mov     [rdi+18h], ax
0x180008cf4  movzx   eax, word ptr [rsp+1C0h+AuthDataCopy+8]
0x180008cf9  mov     [rdi+1Ah], ax
0x180008cfd  movzx   ebx, word ptr [rsp+1C0h+AuthDataCopy+8]
0x180008d02  movzx   r8d, [rbp+0C0h+DestinationString.Length]; Size
0x180008d07  add     rbx, r15
0x180008d0a  mov     rdx, [rbp+0C0h+DestinationString.Buffer]; Src
0x180008d0e  mov     rcx, rbx; void *
0x180008d11  call    memcpy_0
0x180008d16  mov     eax, ebx
0x180008d18  sub     eax, edi
0x180008d1a  mov     [rdi+14h], eax
0x180008d1d  movzx   eax, [rbp+0C0h+DestinationString.Length]
0x180008d21  mov     [rdi+10h], ax
0x180008d25  movzx   eax, [rbp+0C0h+DestinationString.Length]
  ... truncated ...
```
