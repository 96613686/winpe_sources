# DavOpenCreateConnection

- ea: `0x180005de4`
- end: `0x180006565`
- name: `DavOpenCreateConnection`
- size: `1921`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006d20`

## callees

- `0x18000591c`
- `0x180005de4`
- `0x180006618`
- `0x18000b4f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000c5a4`
- `0x18002cf56`
- `0x18002cf62`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800064ad`
- `ntdll!NtCreateFile` at `0x1800064ad`
- `ntdll!RtlNtStatusToDosError` at `0x180005e92`
- `ntdll!RtlNtStatusToDosError` at `0x180005e92`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180005e57`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180005e86`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180005e57`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180005e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f6e`
- `KERNEL32!LocalFree` at `0x1800063fa`
- `KERNEL32!LocalFree` at `0x1800063fa`
- `KERNEL32!LocalAlloc` at `0x180005f56`
- `KERNEL32!LocalAlloc` at `0x180005f56`
- `SspiCli!SspiMarshalAuthIdentity` at `0x180005e7e`
- `SspiCli!SspiMarshalAuthIdentity` at `0x180005e7e`
- `SspiCli!SspiLocalFree` at `0x180006433`
- `SspiCli!SspiLocalFree` at `0x180006433`
- `SspiCli!SspiFreeAuthIdentity` at `0x180006409`
- `SspiCli!SspiFreeAuthIdentity` at `0x180006409`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180005e4f`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180005e4f`

## pseudocode

```c
__int64 __fastcall DavOpenCreateConnection(
        struct _UNICODE_STRING *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        void *a4,
        unsigned int a5,
        const wchar_t *pszSrc,
        __int16 a7,
        char *AuthIdentityByteArray,
        ACCESS_MASK DesiredAccess,
        unsigned int AuthIdentityLength,
        ULONG CreateOptions,
        int a12,
        PHANDLE FileHandle,
        HLOCAL hMem,
        int a15,
        int a16,
        size_t Size,
        void *Src)
{
  char *v19; // rcx
  unsigned int v21; // r8d
  const WCHAR *v22; // rcx
  ULONG v23; // eax
  NTSTATUS v24; // eax
  ULONG v25; // eax
  ULONG v26; // ebx
  ULONG v27; // eax
  int v28; // eax
  unsigned int v29; // edx
  int v30; // edi
  ULONG v31; // ecx
  ULONG EaLength; // r13d
  HLOCAL v33; // rax
  _DWORD *v34; // r10
  DWORD LastError; // eax
  __int64 v36; // r12
  _DWORD *v37; // rbx
  __int64 v38; // r14
  __int64 v39; // r15
  __int64 v40; // rax
  const char *v41; // r8
  __int64 v42; // rdx
  _BYTE *v43; // rcx
  _BYTE *v44; // rax
  __int64 v45; // rax
  const char *v46; // r8
  __int64 v47; // rdx
  _BYTE *v48; // rcx
  _BYTE *v49; // rax
  __int16 v50; // ax
  unsigned int v51; // ecx
  __int64 v52; // rcx
  void *v53; // r10
  __int64 v54; // rax
  const char *v55; // r9
  __int64 v56; // r8
  _BYTE *v57; // rcx
  bool v58; // zf
  _BYTE *v59; // rax
  size_t v60; // r8
  unsigned int v61; // r8d
  __int64 v62; // rcx
  _BYTE *v63; // rcx
  __int64 v64; // rax
  const char *v65; // r8
  __int64 v66; // rdx
  _BYTE *v67; // rcx
  _BYTE *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  const char *v71; // rdx
  _BYTE *v72; // rcx
  _BYTE *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rax
  const char *v76; // r9
  __int64 v77; // rdx
  _BYTE *v78; // rcx
  _BYTE *v79; // rax
  unsigned __int16 v80; // r11
  __int64 v81; // rcx
  __int64 v82; // rax
  const char *v83; // r8
  __int64 v84; // rdx
  _BYTE *v85; // rcx
  _BYTE *v86; // rax
  _BYTE *v87; // rcx
  int v88; // eax
  const char *v89; // rax
  _BYTE *v90; // rax
  ULONG v91; // eax
  HLOCAL v92; // r14
  char *v93; // rcx
  __int64 v94; // rax
  unsigned int v96; // eax
  unsigned int v97; // ebx
  unsigned int v98; // eax
  ULONG v99; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+60h] [rbp-49h] BYREF
  size_t v101; // [rsp+68h] [rbp-41h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int16 v104; // [rsp+F8h] [rbp+4Fh]
  void *v105; // [rsp+108h] [rbp+5Fh]

  v105 = a4;
  ppAuthIdentity = 0;
  v19 = 0;
  AuthIdentityLength = 0;
  AuthIdentityByteArray = 0;
  v21 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( a2 )
  {
    v22 = a2;
    if ( *a2 )
      a2 = 0;
    v23 = SspiEncodeStringsAsAuthIdentity(v22, a2, a3, &ppAuthIdentity);
    v24 = RtlMapSecurityErrorToNtStatus(v23);
    if ( v24 < 0 )
    {
      v25 = WsMapStatus((unsigned int)v24);
LABEL_6:
      v26 = v25;
      goto LABEL_106;
    }
    v27 = SspiMarshalAuthIdentity(ppAuthIdentity, &AuthIdentityLength, &AuthIdentityByteArray);
    v28 = RtlMapSecurityErrorToNtStatus(v27);
    if ( v28 < 0 )
    {
      v25 = RtlNtStatusToDosError(v28);
      goto LABEL_6;
    }
    v21 = AuthIdentityLength;
    v19 = AuthIdentityByteArray;
    a4 = v105;
  }
  v104 = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.Length = 48;
  v29 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v19 )
    v29 = (v21 + 25) & 0xFFFFFFFC;
  if ( a4 )
  {
    v29 += (a5 + 23) & 0xFFFFFFFC;
  }
  else if ( a16 )
  {
    v29 += 24;
  }
  if ( pszSrc )
  {
    v104 = 2 * a7;
    v29 += ((unsigned __int16)(2 * a7) + 19) & 0xFFFFFFFC;
  }
  v30 = a15;
  v31 = v29 + 52;
  if ( !a15 )
    v31 = v29 + 36;
  if ( Src )
    EaLength = v31 + ((Size + 15) & 0xFFFFFFFC);
  else
    EaLength = v31;
  v101 = EaLength;
  v33 = LocalAlloc(0x40u, EaLength);
  hMem = v33;
  v34 = v33;
  if ( !v33 )
  {
    LastError = GetLastError();
    v26 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    goto LABEL_106;
  }
  v36 = 8;
  v37 = v33;
  v38 = 2147483646;
  v39 = 16;
  if ( v30 )
  {
    v40 = 2147483646;
    v41 = "Https:";
    v42 = 8;
    v43 = v34 + 2;
    do
    {
      if ( !v40 )
        break;
      if ( !*v41 )
        break;
      *v43++ = *v41++;
      --v40;
      --v42;
    }
    while ( v42 );
    v44 = v43 - 1;
    if ( v42 )
      v44 = v43;
    v37 = v34 + 4;
    *v44 = 0;
    v34[1] = 1792;
    *v34 = 16;
  }
  if ( AuthIdentityByteArray )
  {
    v45 = 2147483646;
    v46 = "AuthIdentity";
    v47 = 14;
    v48 = v37 + 2;
    do
    {
      if ( !v45 )
        break;
      if ( !*v46 )
        break;
      *v48++ = *v46++;
      --v45;
      --v47;
    }
    while ( v47 );
    v49 = v48 - 1;
    if ( v47 )
      v49 = v48;
    *v49 = 0;
    *((_BYTE *)v37 + 5) = 13;
    v50 = AuthIdentityLength;
    if ( AuthIdentityLength )
    {
      memcpy_0((char *)v37 + 22, AuthIdentityByteArray, AuthIdentityLength);
      v50 = AuthIdentityLength;
    }
    *((_WORD *)v37 + 3) = v50;
    v51 = AuthIdentityLength + 25;
    *((_BYTE *)v37 + 4) = 0;
    v52 = v51 & 0xFFFFFFFC;
    *v37 = v52;
    v37 = (_DWORD *)((char *)v37 + v52);
  }
  v53 = Src;
  if ( !Src )
    goto LABEL_55;
  v54 = 2147483646;
  v55 = "Pin";
  v56 = 4;
  v57 = v37 + 2;
  do
  {
    if ( !v54 )
      break;
    if ( !*v55 )
      break;
    *v57++ = *v55++;
    --v54;
    --v56;
  }
  while ( v56 );
  v58 = v56 == 0;
  v59 = v57 - 1;
  v60 = (unsigned int)Size;
  if ( !v58 )
    v59 = v57;
  *v59 = 0;
  *((_BYTE *)v37 + 5) = 3;
  memcpy_0(v37 + 3, v53, v60);
  v61 = Size;
  *((_WORD *)v37 + 3) = Size;
  *((_BYTE *)v37 + 4) = 0;
  v62 = (v61 + 15) & 0xFFFFFFFC;
  *v37 = v62;
  v37 = (_DWORD *)((char *)v37 + v62);
  v63 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v61);
LABEL_55:
    v63 = WPP_GLOBAL_Control;
  }
  if ( v105 )
  {
    v64 = 2147483646;
    v65 = "Client-Cert";
    v66 = 12;
    v67 = v37 + 2;
    do
    {
      if ( !v64 )
        break;
      if ( !*v65 )
        break;
      *v67++ = *v65++;
      --v64;
      --v66;
    }
    while ( v66 );
    v68 = v67 - 1;
    if ( v66 )
      v68 = v67;
    *v68 = 0;
    *((_BYTE *)v37 + 5) = 11;
    memcpy_0(v37 + 5, v105, a5);
    *((_WORD *)v37 + 3) = a5;
    v69 = (a5 + 23) & 0xFFFFFFFC;
    *v37 = v69;
    *((_BYTE *)v37 + 4) = 0;
    v37 = (_DWORD *)((char *)v37 + v69);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a5);
    goto LABEL_80;
  }
  if ( a16 )
  {
    v70 = 2147483646;
    v71 = "NoClient-Cert";
    v72 = v37 + 2;
    do
    {
      if ( !v70 )
        break;
      if ( !*v71 )
        break;
      *v72++ = *v71++;
      --v70;
      --v39;
    }
    while ( v39 );
    v73 = v72 - 1;
    if ( v39 )
      v73 = v72;
    *v73 = 0;
    v37[1] = 3840;
    *v37 = 24;
    v37 += 6;
    v63 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v74 = 198;
  }
  else
  {
    if ( v63 == (_BYTE *)&WPP_GLOBAL_Control || (v63[28] & 2) == 0 )
      goto LABEL_80;
    v74 = 199;
  }
  WPP_SF_(*((_QWORD *)v63 + 2), v74, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
LABEL_80:
  if ( pszSrc )
  {
    v75 = 2147483646;
    v76 = "Cookie:";
    v77 = 8;
    v78 = v37 + 2;
    do
    {
      if ( !v75 )
        break;
      if ( !*v76 )
        break;
      *v78++ = *v76++;
      --v75;
      --v77;
    }
    while ( v77 );
    v79 = v78 - 1;
    if ( v77 )
      v79 = v78;
    *v79 = 0;
    *((_BYTE *)v37 + 5) = 7;
    StringCbCopyW((STRSAFE_LPWSTR)v37 + 8, v104, pszSrc);
    *((_WORD *)v37 + 3) = v80;
    v81 = (v80 + 19) & 0xFFFFFFFC;
    *v37 = v81;
    *((_BYTE *)v37 + 4) = 0;
    v37 = (_DWORD *)((char *)v37 + v81);
  }
  v82 = 2147483646;
  v83 = "Type";
  v84 = 8;
  v85 = v37 + 2;
  do
  {
    if ( !v82 )
      break;
    if ( !*v83 )
      break;
    *v85++ = *v83++;
    --v82;
    --v84;
  }
  while ( v84 );
  v86 = v85 - 1;
  if ( v84 )
    v86 = v85;
  v87 = v37 + 7;
  *v86 = 0;
  v88 = a12;
  v37[1] = 263936;
  v37[4] = v88;
  v89 = "mrxdav";
  *v37 = 20;
  do
  {
    if ( !v38 )
      break;
    LOBYTE(v84) = *v89;
    if ( !*v89 )
      break;
    *v87 = v84;
    ++v89;
    ++v87;
    --v38;
    --v36;
  }
  while ( v36 );
  v90 = v87 - 1;
  if ( v36 )
    v90 = v87;
  *v90 = 0;
  v37[6] = 1792;
  v37[5] = 0;
  v91 = DavImpersonateClient(v87, v84, v83);
  v26 = v91;
  if ( v91 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v91);
    v92 = hMem;
  }
  else
  {
    v92 = hMem;
    v96 = NtCreateFile(
            FileHandle,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            (CreateOptions & 0x80u) != 0 ? 2 : 128,
            7u,
            1u,
            CreateOptions,
            hMem,
            EaLength);
    v97 = v96;
    if ( v96 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v96);
      v98 = DavRevertToSelf();
      if ( v98
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v98);
      }
      v26 = WsMapStatus(v97);
    }
    else
    {
      WsMapStatus(0);
      v99 = DavRevertToSelf();
      v26 = v99;
      if ( v99
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v99);
      }
    }
  }
  memset_0(v92, 0, v101);
  LocalFree(v92);
LABEL_106:
  if ( ppAuthIdentity )
    SspiFreeAuthIdentity(ppAuthIdentity);
  v93 = AuthIdentityByteArray;
  if ( AuthIdentityByteArray )
  {
    v94 = AuthIdentityLength;
    if ( AuthIdentityLength )
    {
      do
      {
        *v93++ = 0;
        --v94;
      }
      while ( v94 );
      v93 = AuthIdentityByteArray;
    }
    SspiLocalFree(v93);
  }
  return v26;
}

```

## disassembly

```asm
0x180005de4  mov     [rsp-8+arg_0], rbx
0x180005de9  mov     [rsp-8+arg_18], r9
0x180005dee  push    rbp
0x180005def  push    rsi
0x180005df0  push    rdi
0x180005df1  push    r12
0x180005df3  push    r13
0x180005df5  push    r14
0x180005df7  push    r15
0x180005df9  lea     rbp, [rsp-7]
0x180005dfe  sub     rsp, 0B0h
0x180005e05  xorps   xmm0, xmm0
0x180005e08  xor     r15d, r15d
0x180005e0b  mov     rbx, rcx
0x180005e0e  mov     [rbp+37h+ppAuthIdentity], r15
0x180005e12  xor     ecx, ecx
0x180005e14  mov     [rbp+37h+AuthIdentityLength], r15d
0x180005e1b  mov     [rbp+37h+AuthIdentityByteArray], rcx
0x180005e1f  mov     r10, r8
0x180005e22  mov     rax, rdx
0x180005e25  mov     r8d, r15d
0x180005e28  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x180005e2c  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x180005e30  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x180005e34  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180005e38  test    rdx, rdx
0x180005e3b  jz      short loc_180005EA9
0x180005e3d  lea     r9, [rbp+37h+ppAuthIdentity]; ppAuthIdentity
0x180005e41  mov     r8, r10; pszPackedCredentialsString
0x180005e44  mov     rcx, rdx; pszUserName
0x180005e47  cmp     [rdx], r15w
0x180005e4b  jz      short loc_180005E4F
0x180005e4d  xor     edx, edx; pszDomainName
0x180005e4f  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x180005e55  mov     ecx, eax; SecurityError
0x180005e57  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x180005e5d  test    eax, eax
0x180005e5f  jns     short loc_180005E6F
0x180005e61  mov     ecx, eax
0x180005e63  call    WsMapStatus
0x180005e68  mov     ebx, eax
0x180005e6a  jmp     loc_180006400
0x180005e6f  mov     rcx, [rbp+37h+ppAuthIdentity]; AuthIdentity
0x180005e73  lea     r8, [rbp+37h+AuthIdentityByteArray]; AuthIdentityByteArray
0x180005e77  lea     rdx, [rbp+37h+AuthIdentityLength]; AuthIdentityLength
0x180005e7e  call    cs:__imp_SspiMarshalAuthIdentity
0x180005e84  mov     ecx, eax; SecurityError
0x180005e86  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x180005e8c  test    eax, eax
0x180005e8e  jns     short loc_180005E9A
0x180005e90  mov     ecx, eax; Status
0x180005e92  call    cs:__imp_RtlNtStatusToDosError
0x180005e98  jmp     short loc_180005E68
0x180005e9a  mov     r8d, [rbp+37h+AuthIdentityLength]
0x180005ea1  mov     rcx, [rbp+37h+AuthIdentityByteArray]
0x180005ea5  mov     r9, [rbp+37h+arg_18]
0x180005ea9  mov     [rbp+37h+arg_8], r15d
0x180005ead  mov     r10d, 40h ; '@'
0x180005eb3  mov     [rbp+37h+ObjectAttributes.Attributes], r10d
0x180005eb7  xorps   xmm0, xmm0
0x180005eba  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x180005ec1  mov     edx, r15d
0x180005ec4  mov     [rbp+37h+ObjectAttributes.RootDirectory], r15
0x180005ec8  mov     esi, 0FFFFFFFCh
0x180005ecd  mov     [rbp+37h+ObjectAttributes.ObjectName], rbx
0x180005ed1  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005ed6  test    rcx, rcx
0x180005ed9  jz      short loc_180005EE1
0x180005edb  lea     edx, [r8+19h]
0x180005edf  and     edx, esi
0x180005ee1  test    r9, r9
0x180005ee4  jz      short loc_180005EF2
0x180005ee6  mov     eax, dword ptr [rbp+37h+arg_20]
0x180005ee9  add     eax, 17h
0x180005eec  and     eax, esi
0x180005eee  add     edx, eax
0x180005ef0  jmp     short loc_180005EFE
0x180005ef2  cmp     [rbp+37h+arg_78], r15d
0x180005ef9  jz      short loc_180005EFE
0x180005efb  add     edx, 18h
0x180005efe  cmp     [rbp+37h+pszSrc], r15
0x180005f02  jz      short loc_180005F19
0x180005f04  movzx   eax, [rbp+37h+arg_30]
0x180005f08  add     ax, ax
0x180005f0b  movzx   ecx, ax
0x180005f0e  mov     word ptr [rbp+37h+arg_8], cx
0x180005f12  add     ecx, 13h
0x180005f15  and     ecx, esi
0x180005f17  add     edx, ecx
0x180005f19  mov     edi, [rbp+37h+arg_70]
0x180005f1f  lea     eax, [rdx+24h]
0x180005f22  test    edi, edi
0x180005f24  lea     ecx, [rax+10h]
0x180005f27  cmovz   ecx, eax
0x180005f2a  cmp     [rbp+37h+Src], r15
0x180005f31  jz      short loc_180005F46
0x180005f33  mov     r13d, dword ptr [rbp+37h+Size]
0x180005f3a  add     r13d, 0Fh
0x180005f3e  and     r13d, esi
0x180005f41  add     r13d, ecx
0x180005f44  jmp     short loc_180005F49
0x180005f46  mov     r13d, ecx
0x180005f49  mov     eax, r13d
0x180005f4c  mov     ecx, r10d; uFlags
0x180005f4f  mov     edx, r13d; uBytes
0x180005f52  mov     [rbp+37h+var_78], rax
0x180005f56  call    cs:__imp_LocalAlloc
0x180005f5c  xor     r11d, r11d
0x180005f5f  mov     [rbp+37h+hMem], rax
0x180005f66  mov     r10, rax
0x180005f69  test    rax, rax
0x180005f6c  jnz     short loc_180005FB4
0x180005f6e  call    cs:__imp_GetLastError
0x180005f74  mov     ebx, eax
0x180005f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f7d  lea     rsi, WPP_GLOBAL_Control
0x180005f84  cmp     rcx, rsi
0x180005f87  jz      loc_180006400
0x180005f8d  test    byte ptr [rcx+1Ch], 1
0x180005f91  jz      loc_180006400
0x180005f97  mov     rcx, [rcx+10h]
0x180005f9b  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180005fa2  mov     edx, 0C3h
0x180005fa7  mov     r9d, eax
0x180005faa  call    WPP_SF_d
0x180005faf  jmp     loc_180006400
0x180005fb4  mov     r12d, 8
0x180005fba  mov     rbx, r10
0x180005fbd  mov     r14d, 7FFFFFFEh
0x180005fc3  lea     r15d, [r12+8]
0x180005fc8  test    edi, edi
0x180005fca  jz      short loc_180006018
0x180005fcc  mov     eax, r14d
0x180005fcf  lea     r8, aHttps; "Https:"
0x180005fd6  mov     edx, r12d
0x180005fd9  lea     rcx, [r10+8]
0x180005fdd  test    rax, rax
0x180005fe0  jz      short loc_180005FFC
0x180005fe2  mov     r9b, [r8]
0x180005fe5  test    r9b, r9b
0x180005fe8  jz      short loc_180005FFC
0x180005fea  mov     [rcx], r9b
0x180005fed  inc     r8
0x180005ff0  inc     rcx
0x180005ff3  dec     rax
0x180005ff6  sub     rdx, 1
0x180005ffa  jnz     short loc_180005FDD
0x180005ffc  test    rdx, rdx
0x180005fff  lea     rax, [rcx-1]
0x180006003  cmovnz  rax, rcx
0x180006007  add     rbx, r15
0x18000600a  mov     [rax], r11b
0x18000600d  mov     dword ptr [r10+4], 700h
0x180006015  mov     [r10], r15d
0x180006018  cmp     [rbp+37h+AuthIdentityByteArray], r11
0x18000601c  jz      short loc_18000609D
0x18000601e  mov     rax, r14
0x180006021  lea     r8, aAuthidentity; "AuthIdentity"
0x180006028  mov     edx, 0Eh
0x18000602d  lea     rcx, [rbx+8]
0x180006031  test    rax, rax
0x180006034  jz      short loc_180006050
0x180006036  mov     r9b, [r8]
0x180006039  test    r9b, r9b
0x18000603c  jz      short loc_180006050
0x18000603e  mov     [rcx], r9b
0x180006041  inc     r8
0x180006044  inc     rcx
0x180006047  dec     rax
0x18000604a  sub     rdx, 1
0x18000604e  jnz     short loc_180006031
0x180006050  test    rdx, rdx
0x180006053  lea     rax, [rcx-1]
0x180006057  cmovnz  rax, rcx
0x18000605b  mov     [rax], r11b
0x18000605e  mov     byte ptr [rbx+5], 0Dh
0x180006062  mov     eax, [rbp+37h+AuthIdentityLength]
0x180006068  test    eax, eax
0x18000606a  jz      short loc_180006085
0x18000606c  mov     rdx, [rbp+37h+AuthIdentityByteArray]; Src
0x180006070  lea     rcx, [rbx+16h]; void *
0x180006074  mov     r8d, eax; Size
0x180006077  call    memcpy_0
0x18000607c  mov     eax, [rbp+37h+AuthIdentityLength]
0x180006082  xor     r11d, r11d
0x180006085  mov     [rbx+6], ax
0x180006089  mov     ecx, [rbp+37h+AuthIdentityLength]
0x18000608f  add     ecx, 19h
0x180006092  mov     [rbx+4], r11b
0x180006096  and     ecx, esi
0x180006098  mov     [rbx], ecx
0x18000609a  add     rbx, rcx
0x18000609d  mov     r10, [rbp+37h+Src]
0x1800060a4  lea     rdi, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800060ab  lea     rsi, WPP_GLOBAL_Control
0x1800060b2  test    r10, r10
0x1800060b5  jz      loc_180006159
0x1800060bb  mov     rax, r14
0x1800060be  lea     r9, aPin; "Pin"
0x1800060c5  mov     r8d, 4
0x1800060cb  lea     rcx, [rbx+8]
0x1800060cf  test    rax, rax
0x1800060d2  jz      short loc_1800060EC
0x1800060d4  mov     dl, [r9]
0x1800060d7  test    dl, dl
0x1800060d9  jz      short loc_1800060EC
0x1800060db  mov     [rcx], dl
0x1800060dd  inc     r9
0x1800060e0  inc     rcx
0x1800060e3  dec     rax
0x1800060e6  sub     r8, 1
0x1800060ea  jnz     short loc_1800060CF
0x1800060ec  test    r8, r8
0x1800060ef  lea     rax, [rcx-1]
0x1800060f3  mov     r8d, dword ptr [rbp+37h+Size]; Size
0x1800060fa  mov     rdx, r10; Src
0x1800060fd  cmovnz  rax, rcx
0x180006101  lea     rcx, [rbx+0Ch]; void *
0x180006105  mov     [rax], r11b
0x180006108  mov     byte ptr [rbx+5], 3
0x18000610c  call    memcpy_0
0x180006111  mov     r8d, dword ptr [rbp+37h+Size]
0x180006118  xor     r11d, r11d
0x18000611b  mov     [rbx+6], r8w
0x180006120  mov     [rbx+4], r11b
0x180006124  lea     ecx, [r8+0Fh]
0x180006128  and     ecx, 0FFFFFFFCh
0x18000612b  mov     [rbx], ecx
0x18000612d  add     rbx, rcx
0x180006130  mov     rcx, cs:WPP_GLOBAL_Control
0x180006137  cmp     rcx, rsi
0x18000613a  jz      short loc_180006160
0x18000613c  test    byte ptr [rcx+1Ch], 2
0x180006140  jz      short loc_180006160
0x180006142  mov     rcx, [rcx+10h]
0x180006146  mov     r9d, r8d
0x180006149  mov     r8, rdi
0x18000614c  mov     edx, 0C4h
0x180006151  call    WPP_SF_d
0x180006156  xor     r11d, r11d
0x180006159  mov     rcx, cs:WPP_GLOBAL_Control
0x180006160  mov     r10, [rbp+37h+arg_18]
0x180006164  test    r10, r10
0x180006167  jz      loc_18000620F
0x18000616d  mov     rax, r14
0x180006170  lea     r8, aClientCert; "Client-Cert"
0x180006177  mov     edx, 0Ch
0x18000617c  lea     rcx, [rbx+8]
0x180006180  test    rax, rax
0x180006183  jz      short loc_18000619F
0x180006185  mov     r9b, [r8]
0x180006188  test    r9b, r9b
0x18000618b  jz      short loc_18000619F
0x18000618d  mov     [rcx], r9b
0x180006190  inc     r8
0x180006193  inc     rcx
0x180006196  dec     rax
0x180006199  sub     rdx, 1
0x18000619d  jnz     short loc_180006180
0x18000619f  mov     r15d, dword ptr [rbp+37h+arg_20]
0x1800061a3  lea     rax, [rcx-1]
0x1800061a7  test    rdx, rdx
0x1800061aa  mov     r8d, r15d; Size
0x1800061ad  mov     rdx, r10; Src
0x1800061b0  cmovnz  rax, rcx
0x1800061b4  lea     rcx, [rbx+14h]; void *
0x1800061b8  mov     [rax], r11b
0x1800061bb  mov     byte ptr [rbx+5], 0Bh
0x1800061bf  call    memcpy_0
0x1800061c4  lea     ecx, [r15+17h]
0x1800061c8  mov     [rbx+6], r15w
0x1800061cd  and     ecx, 0FFFFFFFCh
0x1800061d0  xor     r11d, r11d
0x1800061d3  mov     [rbx], ecx
0x1800061d5  mov     [rbx+4], r11b
0x1800061d9  add     rbx, rcx
0x1800061dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061e3  cmp     rcx, rsi
0x1800061e6  jz      loc_18000629C
0x1800061ec  test    byte ptr [rcx+1Ch], 2
0x1800061f0  jz      loc_18000629C
0x1800061f6  mov     rcx, [rcx+10h]
0x1800061fa  mov     edx, 0C5h
0x1800061ff  mov     r9d, r15d
0x180006202  mov     r8, rdi
0x180006205  call    WPP_SF_d
0x18000620a  jmp     loc_180006299
0x18000620f  cmp     [rbp+37h+arg_78], r11d
0x180006216  jz      short loc_18000627D
0x180006218  mov     rax, r14
0x18000621b  lea     rdx, aNoclientCert; "NoClient-Cert"
0x180006222  lea     rcx, [rbx+8]
0x180006226  test    rax, rax
0x180006229  jz      short loc_180006245
0x18000622b  mov     r8b, [rdx]
0x18000622e  test    r8b, r8b
0x180006231  jz      short loc_180006245
0x180006233  mov     [rcx], r8b
0x180006236  inc     rdx
0x180006239  inc     rcx
  ... truncated ...
```
