# CRegAccount::AddSidToToken(void *,void *,int *)

- ea: `0x180021ca8`
- end: `0x1800221db`
- name: `?AddSidToToken@CRegAccount@@SAJPEAX0PEAH@Z`
- size: `1331`
- prototype: `__int64 __fastcall(void *, void *, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cdb4`
- `0x18001d740`
- `0x18001d800`
- `0x180044a48`

## callees

- `0x180021ca8`
- `0x180023a58`
- `0x18004d030`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x180064c30`

## import_xrefs

- `USER32!GetUserObjectSecurity` at `0x180021d5d`
- `USER32!GetUserObjectSecurity` at `0x180021da7`
- `USER32!GetUserObjectSecurity` at `0x180021d5d`
- `USER32!GetUserObjectSecurity` at `0x180021da7`
- `USER32!SetUserObjectSecurity` at `0x180022188`
- `USER32!SetUserObjectSecurity` at `0x180022188`
- `ADVAPI32!AddAccessAllowedAce` at `0x180021f48`
- `ADVAPI32!AddAccessAllowedAce` at `0x180021f48`
- `ADVAPI32!GetLengthSid` at `0x180021e59`
- `ADVAPI32!GetLengthSid` at `0x180021e59`
- `ADVAPI32!InitializeAcl` at `0x180021e9b`
- `ADVAPI32!InitializeAcl` at `0x180021e9b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022166`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022166`
- `ADVAPI32!AddAce` at `0x180021f0e`
- `ADVAPI32!AddAce` at `0x180021f0e`
- `ADVAPI32!GetAce` at `0x180021eeb`
- `ADVAPI32!GetAce` at `0x180021f7f`
- `ADVAPI32!GetAce` at `0x180021eeb`
- `ADVAPI32!GetAce` at `0x180021f7f`
- `ADVAPI32!GetAclInformation` at `0x180021e47`
- `ADVAPI32!GetAclInformation` at `0x180021ecb`
- `ADVAPI32!GetAclInformation` at `0x180021f65`
- `ADVAPI32!GetAclInformation` at `0x180021e47`
- `ADVAPI32!GetAclInformation` at `0x180021ecb`
- `ADVAPI32!GetAclInformation` at `0x180021f65`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180021dea`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180021dea`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180021dcc`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180021dcc`
- `ADVAPI32!MakeAbsoluteSD` at `0x180021fe2`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002214b`
- `ADVAPI32!MakeAbsoluteSD` at `0x180021fe2`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002214b`

## pseudocode

```c
__int64 __fastcall CRegAccount::AddSidToToken(void *a1, void *a2, int *a3)
{
  __int64 v3; // rbx
  unsigned int DoesAccessExist; // edi
  _BYTE *v7; // r15
  DWORD v8; // esi
  DWORD LengthSid; // eax
  DWORD v10; // edi
  struct _ACL *v11; // r14
  struct _ACL *v12; // r13
  DWORD v13; // r12d
  DWORD v14; // r10d
  DWORD v15; // r11d
  DWORD v16; // r12d
  DWORD v17; // r13d
  DWORD v18; // ecx
  DWORD v19; // esi
  _BYTE *v20; // rsi
  DWORD nLengthNeeded; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwOwnerSize; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwSaclSize; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDaclSize; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pSIRequested; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclPresent; // [rsp+7Ch] [rbp-84h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp-78h] BYREF
  PSID pSid; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pAce; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v34; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hObj; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+B8h] [rbp-48h]
  _DWORD pAclInformation[4]; // [rsp+C0h] [rbp-40h] BYREF
  void *lpMem[2]; // [rsp+D0h] [rbp-30h]
  _BYTE *v40; // [rsp+E0h] [rbp-20h]
  _BYTE pSID[4000]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = 0;
  hObj = a1;
  pSid = a2;
  pSIRequested = 4;
  nLengthNeeded = 0;
  pDacl = 0;
  DoesAccessExist = 0;
  bDaclDefaulted = 0;
  bDaclPresent = 0;
  dwPrimaryGroupSize = 0;
  dwOwnerSize = 0;
  dwSaclSize = 0;
  dwDaclSize = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v40 = 0;
  v34 = 0;
  *(_OWORD *)lpMem = 0;
  if ( !a1 || !a2 )
  {
    DoesAccessExist = -2147024809;
    goto LABEL_44;
  }
  v7 = pSID;
  if ( !GetUserObjectSecurity(a1, &pSIRequested, pSID, 0xFA0u, &nLengthNeeded) )
  {
    if ( nLengthNeeded <= 0xFA0 )
      goto LABEL_8;
    lpMem[0] = MemAllocClear(nLengthNeeded);
    v7 = lpMem[0];
    if ( !lpMem[0] )
    {
LABEL_6:
      DoesAccessExist = -2147024882;
      goto LABEL_44;
    }
    if ( !GetUserObjectSecurity(a1, &pSIRequested, lpMem[0], nLengthNeeded, &nLengthNeeded) )
      goto LABEL_8;
  }
  v8 = 0;
  if ( nLengthNeeded < 0xFA0 )
    v8 = nLengthNeeded;
  nLengthNeeded = GetSecurityDescriptorLength(v7);
  if ( !nLengthNeeded || !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    goto LABEL_8;
  if ( !bDaclPresent || pDacl )
  {
    DoesAccessExist = CRegAccount::DoesAccessExist(pDacl, &pSid, 1, 0xF01FFu, a3);
    if ( !DoesAccessExist && !*a3 )
    {
      if ( !GetAclInformation(pDacl, pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_8;
      LengthSid = GetLengthSid(pSid);
      v10 = LengthSid + pAclInformation[1] + 12;
      if ( v10 + v8 >= 0xFA0 )
      {
        lpMem[1] = MemAllocClear(v10);
        v11 = (struct _ACL *)lpMem[1];
        if ( !lpMem[1] )
          goto LABEL_6;
      }
      else
      {
        v11 = (struct _ACL *)&pSID[v8];
        v8 += v10;
      }
      if ( !InitializeAcl(v11, v10, 2u) )
        goto LABEL_8;
      v12 = pDacl;
      DoesAccessExist = 0;
      if ( !pDacl )
        goto LABEL_30;
      v36 = 0;
      v37 = 0;
      if ( GetAclInformation(pDacl, &v36, 0xCu, AclSizeInformation) )
      {
        v13 = 0;
        if ( !(_DWORD)v36 )
          goto LABEL_30;
        while ( 1 )
        {
          pAce = 0;
          if ( !GetAce(v12, v13, &pAce) || !AddAce(v11, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
            break;
          if ( ++v13 >= (unsigned int)v36 )
            goto LABEL_31;
        }
      }
      DoesAccessExist = GetLastWin32Error();
LABEL_30:
      if ( !DoesAccessExist )
      {
LABEL_31:
        if ( AddAccessAllowedAce(v11, 2u, 0xF01FFu, pSid)
          && GetAclInformation(v11, pAclInformation, 0xCu, AclSizeInformation)
          && GetAce(v11, pAclInformation[0] - 1, &v34)
          && v34 )
        {
          *((_BYTE *)v34 + 1) = 3;
          MakeAbsoluteSD(
            v7,
            0,
            &dwAbsoluteSecurityDescriptorSize,
            0,
            &dwDaclSize,
            0,
            &dwSaclSize,
            0,
            &dwOwnerSize,
            0,
            &dwPrimaryGroupSize);
          v14 = ((dwAbsoluteSecurityDescriptorSize & 7) != 0 ? 8 - (dwAbsoluteSecurityDescriptorSize & 7) : 0)
              + dwAbsoluteSecurityDescriptorSize;
          dwAbsoluteSecurityDescriptorSize = v14;
          v15 = ((dwDaclSize & 7) != 0 ? 8 - (dwDaclSize & 7) : 0) + dwDaclSize;
          dwDaclSize = v15;
          v16 = dwSaclSize + ((dwSaclSize & 7) != 0 ? 8 - (dwSaclSize & 7) : 0);
          dwSaclSize = v16;
          v17 = dwOwnerSize + ((dwOwnerSize & 7) != 0 ? 8 - (dwOwnerSize & 7) : 0);
          dwOwnerSize = v17;
          v18 = dwPrimaryGroupSize + ((dwPrimaryGroupSize & 7) != 0 ? 8 - (dwPrimaryGroupSize & 7) : 0);
          dwPrimaryGroupSize = v18;
          v19 = ((v8 & 7) != 0 ? 8 - (v8 & 7) : 0) + v8;
          if ( v15 + v14 + v19 + v18 + v16 + v17 >= 0xFA0 )
          {
            v40 = MemAllocClear(v15 + v14 + v16 + v17 + v18);
            v20 = v40;
            if ( !v40 )
              goto LABEL_6;
            v17 = dwOwnerSize;
            v16 = dwSaclSize;
            v15 = dwDaclSize;
            v14 = dwAbsoluteSecurityDescriptorSize;
          }
          else
          {
            v20 = &pSID[v19];
          }
          if ( MakeAbsoluteSD(
                 v7,
                 v20,
                 &dwAbsoluteSecurityDescriptorSize,
                 (PACL)&v20[v14],
                 &dwDaclSize,
                 (PACL)&v20[v14 + v15],
                 &dwSaclSize,
                 &v20[v14 + v15 + v16],
                 &dwOwnerSize,
                 &v20[v17 + v14 + v15 + v16],
                 &dwPrimaryGroupSize) )
          {
            if ( SetSecurityDescriptorDacl(v20, 1, v11, 0) )
            {
              pSIRequested = 4;
              if ( SetUserObjectSecurity(hObj, &pSIRequested, v20) )
                goto LABEL_44;
            }
          }
        }
LABEL_8:
        DoesAccessExist = GetLastWin32Error();
        goto LABEL_44;
      }
      goto LABEL_44;
    }
  }
  do
LABEL_44:
    MemFree(lpMem[v3++]);
  while ( v3 < 3 );
  return DoesAccessExist;
}

```

## disassembly

```asm
0x180021ca8  mov     [rsp-8+arg_18], rbx
0x180021cad  push    rbp
0x180021cae  push    rsi
0x180021caf  push    rdi
0x180021cb0  push    r12
0x180021cb2  push    r13
0x180021cb4  push    r14
0x180021cb6  push    r15
0x180021cb8  lea     rbp, [rsp-0FA0h]
0x180021cc0  mov     eax, 10A0h
0x180021cc5  call    _alloca_probe
0x180021cca  sub     rsp, rax
0x180021ccd  mov     rax, cs:__security_cookie
0x180021cd4  xor     rax, rsp
0x180021cd7  mov     [rbp+0FD0h+var_40], rax
0x180021cde  xor     ebx, ebx
0x180021ce0  mov     [rbp+0FD0h+hObj], rcx
0x180021ce4  mov     [rbp+0FD0h+pSid], rdx
0x180021ce8  xorps   xmm0, xmm0
0x180021ceb  mov     [rsp+10D0h+pSIRequested], 4
0x180021cf3  mov     r14, r8
0x180021cf6  mov     [rsp+10D0h+nLengthNeeded], ebx
0x180021cfa  mov     rsi, rcx
0x180021cfd  mov     [rbp+0FD0h+pDacl], rbx
0x180021d01  mov     edi, ebx
0x180021d03  mov     [rbp+0FD0h+bDaclDefaulted], ebx
0x180021d06  mov     [rsp+10D0h+bDaclPresent], ebx
0x180021d0a  mov     [rsp+10D0h+dwPrimaryGroupSize], ebx
0x180021d0e  mov     [rsp+10D0h+dwOwnerSize], ebx
0x180021d12  mov     [rsp+10D0h+dwSaclSize], ebx
0x180021d16  mov     [rsp+10D0h+dwDaclSize], ebx
0x180021d1a  mov     [rsp+10D0h+dwAbsoluteSecurityDescriptorSize], ebx
0x180021d1e  mov     [rbp+0FD0h+var_FF0], rbx
0x180021d22  mov     [rbp+0FD0h+var_1030], rbx
0x180021d26  movdqu  xmmword ptr [rbp+0FD0h+lpMem], xmm0
0x180021d2b  test    rcx, rcx
0x180021d2e  jz      loc_180022197
0x180021d34  test    rdx, rdx
0x180021d37  jz      loc_180022197
0x180021d3d  lea     rax, [rsp+10D0h+nLengthNeeded]
0x180021d42  mov     r13d, 0FA0h
0x180021d48  mov     r9d, r13d; nLength
0x180021d4b  mov     [rsp+10D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180021d50  lea     r8, [rbp+0FD0h+pSID]; pSID
0x180021d54  lea     rdx, [rsp+10D0h+pSIRequested]; pSIRequested
0x180021d59  lea     r15, [rbp+0FD0h+pSID]
0x180021d5d  call    cs:__imp_GetUserObjectSecurity
0x180021d63  test    eax, eax
0x180021d65  jnz     short loc_180021DBD
0x180021d67  cmp     [rsp+10D0h+nLengthNeeded], r13d
0x180021d6c  jbe     short loc_180021DB1
0x180021d6e  mov     ecx, [rsp+10D0h+nLengthNeeded]; unsigned __int64
0x180021d72  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180021d77  mov     [rbp+0FD0h+lpMem], rax
0x180021d7b  mov     r15, rax
0x180021d7e  test    rax, rax
0x180021d81  jnz     short loc_180021D8D
0x180021d83  mov     edi, 8007000Eh
0x180021d88  jmp     loc_18002219C
0x180021d8d  mov     r9d, [rsp+10D0h+nLengthNeeded]; nLength
0x180021d92  lea     rax, [rsp+10D0h+nLengthNeeded]
0x180021d97  mov     r8, r15; pSID
0x180021d9a  mov     [rsp+10D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180021d9f  lea     rdx, [rsp+10D0h+pSIRequested]; pSIRequested
0x180021da4  mov     rcx, rsi; hObj
0x180021da7  call    cs:__imp_GetUserObjectSecurity
0x180021dad  test    eax, eax
0x180021daf  jnz     short loc_180021DBD
0x180021db1  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180021db6  mov     edi, eax
0x180021db8  jmp     loc_18002219C
0x180021dbd  cmp     [rsp+10D0h+nLengthNeeded], r13d
0x180021dc2  mov     esi, ebx
0x180021dc4  mov     rcx, r15; pSecurityDescriptor
0x180021dc7  cmovb   esi, [rsp+10D0h+nLengthNeeded]
0x180021dcc  call    cs:__imp_GetSecurityDescriptorLength
0x180021dd2  mov     [rsp+10D0h+nLengthNeeded], eax
0x180021dd6  test    eax, eax
0x180021dd8  jz      short loc_180021DB1
0x180021dda  lea     r9, [rbp+0FD0h+bDaclDefaulted]; lpbDaclDefaulted
0x180021dde  mov     rcx, r15; pSecurityDescriptor
0x180021de1  lea     r8, [rbp+0FD0h+pDacl]; pDacl
0x180021de5  lea     rdx, [rsp+10D0h+bDaclPresent]; lpbDaclPresent
0x180021dea  call    cs:__imp_GetSecurityDescriptorDacl
0x180021df0  test    eax, eax
0x180021df2  jz      short loc_180021DB1
0x180021df4  mov     rcx, [rbp+0FD0h+pDacl]; pAcl
0x180021df8  cmp     [rsp+10D0h+bDaclPresent], ebx
0x180021dfc  jz      short loc_180021E07
0x180021dfe  test    rcx, rcx
0x180021e01  jz      loc_18002219C
0x180021e07  mov     r9d, 0F01FFh; unsigned int
0x180021e0d  mov     [rsp+10D0h+lpnLengthNeeded], r14; int *
0x180021e12  mov     r8d, 1; int
0x180021e18  lea     rdx, [rbp+0FD0h+pSid]; void **
0x180021e1c  call    ?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z; CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)
0x180021e21  mov     edi, eax
0x180021e23  test    eax, eax
0x180021e25  jnz     loc_18002219C
0x180021e2b  cmp     [r14], ebx
0x180021e2e  jnz     loc_18002219C
0x180021e34  mov     rcx, [rbp+0FD0h+pDacl]; pAcl
0x180021e38  lea     r12d, [rax+2]
0x180021e3c  mov     r9d, r12d; dwAclInformationClass
0x180021e3f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180021e43  lea     rdx, [rbp+0FD0h+pAclInformation]; pAclInformation
0x180021e47  call    cs:__imp_GetAclInformation
0x180021e4d  test    eax, eax
0x180021e4f  jz      loc_180021DB1
0x180021e55  mov     rcx, [rbp+0FD0h+pSid]; pSid
0x180021e59  call    cs:__imp_GetLengthSid
0x180021e5f  mov     edi, [rbp+0FD0h+var_100C]
0x180021e62  add     edi, 0Ch
0x180021e65  add     edi, eax
0x180021e67  lea     ecx, [rdi+rsi]
0x180021e6a  cmp     ecx, r13d
0x180021e6d  jnb     short loc_180021E7C
0x180021e6f  mov     eax, esi
0x180021e71  lea     r14, [rbp+0FD0h+pSID]
0x180021e75  add     r14, rax
0x180021e78  mov     esi, ecx
0x180021e7a  jmp     short loc_180021E93
0x180021e7c  mov     ecx, edi; unsigned __int64
0x180021e7e  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180021e83  mov     [rbp+0FD0h+lpMem+8], rax
0x180021e87  mov     r14, rax
0x180021e8a  test    rax, rax
0x180021e8d  jz      loc_180021D83
0x180021e93  mov     r8d, r12d; dwAclRevision
0x180021e96  mov     edx, edi; nAclLength
0x180021e98  mov     rcx, r14; pAcl
0x180021e9b  call    cs:__imp_InitializeAcl
0x180021ea1  test    eax, eax
0x180021ea3  jz      loc_180021DB1
0x180021ea9  mov     r13, [rbp+0FD0h+pDacl]
0x180021ead  mov     edi, ebx
0x180021eaf  test    r13, r13
0x180021eb2  jz      short loc_180021F2A
0x180021eb4  xor     eax, eax
0x180021eb6  lea     rdx, [rbp+0FD0h+var_1020]; pAclInformation
0x180021eba  mov     r9d, r12d; dwAclInformationClass
0x180021ebd  mov     [rbp+0FD0h+var_1020], rax
0x180021ec1  mov     rcx, r13; pAcl
0x180021ec4  mov     [rbp+0FD0h+var_1018], eax
0x180021ec7  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180021ecb  call    cs:__imp_GetAclInformation
0x180021ed1  test    eax, eax
0x180021ed3  jz      short loc_180021F23
0x180021ed5  mov     r12d, ebx
0x180021ed8  cmp     dword ptr [rbp+0FD0h+var_1020], ebx
0x180021edb  jbe     short loc_180021F2A
0x180021edd  lea     r8, [rbp+0FD0h+pAce]; pAce
0x180021ee1  mov     [rbp+0FD0h+pAce], rbx
0x180021ee5  mov     edx, r12d; dwAceIndex
0x180021ee8  mov     rcx, r13; pAcl
0x180021eeb  call    cs:__imp_GetAce
0x180021ef1  test    eax, eax
0x180021ef3  jz      short loc_180021F23
0x180021ef5  mov     r9, [rbp+0FD0h+pAce]; pAceList
0x180021ef9  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180021efd  mov     edx, 2; dwAceRevision
0x180021f02  mov     rcx, r14; pAcl
0x180021f05  movzx   eax, word ptr [r9+2]
0x180021f0a  mov     dword ptr [rsp+10D0h+lpnLengthNeeded], eax; nAceListLength
0x180021f0e  call    cs:__imp_AddAce
0x180021f14  test    eax, eax
0x180021f16  jz      short loc_180021F23
0x180021f18  inc     r12d
0x180021f1b  cmp     r12d, dword ptr [rbp+0FD0h+var_1020]
0x180021f1f  jb      short loc_180021EDD
0x180021f21  jmp     short loc_180021F32
0x180021f23  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180021f28  mov     edi, eax
0x180021f2a  test    edi, edi
0x180021f2c  jnz     loc_18002219C
0x180021f32  mov     r9, [rbp+0FD0h+pSid]; pSid
0x180021f36  mov     r12d, 2
0x180021f3c  mov     edx, r12d; dwAceRevision
0x180021f3f  mov     r8d, 0F01FFh; AccessMask
0x180021f45  mov     rcx, r14; pAcl
0x180021f48  call    cs:__imp_AddAccessAllowedAce
0x180021f4e  test    eax, eax
0x180021f50  jz      loc_180021DB1
0x180021f56  mov     r9d, r12d; dwAclInformationClass
0x180021f59  lea     r8d, [r12+0Ah]; nAclInformationLength
0x180021f5e  lea     rdx, [rbp+0FD0h+pAclInformation]; pAclInformation
0x180021f62  mov     rcx, r14; pAcl
0x180021f65  call    cs:__imp_GetAclInformation
0x180021f6b  test    eax, eax
0x180021f6d  jz      loc_180021DB1
0x180021f73  mov     edx, [rbp+0FD0h+pAclInformation]
0x180021f76  lea     r8, [rbp+0FD0h+var_1030]; pAce
0x180021f7a  dec     edx; dwAceIndex
0x180021f7c  mov     rcx, r14; pAcl
0x180021f7f  call    cs:__imp_GetAce
0x180021f85  test    eax, eax
0x180021f87  jz      loc_180021DB1
0x180021f8d  mov     rax, [rbp+0FD0h+var_1030]
0x180021f91  test    rax, rax
0x180021f94  jz      loc_180021DB1
0x180021f9a  mov     byte ptr [rax+1], 3
0x180021f9e  lea     r8, [rsp+10D0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180021fa3  lea     rax, [rsp+10D0h+dwPrimaryGroupSize]
0x180021fa8  xor     r9d, r9d; pDacl
0x180021fab  mov     [rsp+10D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180021fb0  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180021fb2  mov     [rsp+10D0h+pPrimaryGroup], rbx; pPrimaryGroup
0x180021fb7  lea     rax, [rsp+10D0h+dwOwnerSize]
0x180021fbc  mov     [rsp+10D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180021fc1  mov     rcx, r15; pSelfRelativeSecurityDescriptor
0x180021fc4  mov     [rsp+10D0h+pOwner], rbx; pOwner
0x180021fc9  lea     rax, [rsp+10D0h+dwSaclSize]
0x180021fce  mov     [rsp+10D0h+lpdwSaclSize], rax; lpdwSaclSize
0x180021fd3  lea     rax, [rsp+10D0h+dwDaclSize]
0x180021fd8  mov     [rsp+10D0h+pSacl], rbx; pSacl
0x180021fdd  mov     [rsp+10D0h+lpnLengthNeeded], rax; lpdwDaclSize
0x180021fe2  call    cs:__imp_MakeAbsoluteSD
0x180021fe8  mov     r10d, [rsp+10D0h+dwAbsoluteSecurityDescriptorSize]
0x180021fed  lea     r9d, [r12+5]
0x180021ff2  mov     r11d, [rsp+10D0h+dwDaclSize]
0x180021ff7  lea     r8d, [r12+6]
0x180021ffc  mov     eax, r10d
0x180021fff  mov     ecx, r8d
0x180022002  and     eax, r9d
0x180022005  mov     r12d, r8d
0x180022008  sub     ecx, eax
0x18002200a  mov     r13d, r8d
0x18002200d  neg     eax
0x18002200f  sbb     eax, eax
0x180022011  and     eax, ecx
0x180022013  mov     ecx, r8d
0x180022016  add     r10d, eax
0x180022019  mov     eax, r11d
0x18002201c  and     eax, r9d
0x18002201f  mov     [rsp+10D0h+dwAbsoluteSecurityDescriptorSize], r10d
0x180022024  sub     ecx, eax
0x180022026  neg     eax
0x180022028  sbb     eax, eax
0x18002202a  and     eax, ecx
0x18002202c  mov     ecx, r8d
0x18002202f  add     r11d, eax
0x180022032  mov     eax, [rsp+10D0h+dwSaclSize]
0x180022036  and     eax, r9d
0x180022039  mov     [rsp+10D0h+dwDaclSize], r11d
0x18002203e  sub     r12d, eax
0x180022041  neg     eax
0x180022043  sbb     eax, eax
0x180022045  and     r12d, eax
0x180022048  mov     eax, [rsp+10D0h+dwOwnerSize]
0x18002204c  add     r12d, [rsp+10D0h+dwSaclSize]
0x180022051  and     eax, r9d
0x180022054  sub     r13d, eax
0x180022057  mov     [rsp+10D0h+dwSaclSize], r12d
0x18002205c  neg     eax
0x18002205e  sbb     eax, eax
0x180022060  and     r13d, eax
0x180022063  mov     eax, [rsp+10D0h+dwPrimaryGroupSize]
0x180022067  add     r13d, [rsp+10D0h+dwOwnerSize]
0x18002206c  and     eax, r9d
0x18002206f  sub     ecx, eax
0x180022071  mov     [rsp+10D0h+dwOwnerSize], r13d
0x180022076  neg     eax
0x180022078  sbb     eax, eax
0x18002207a  and     ecx, eax
0x18002207c  mov     eax, esi
0x18002207e  add     ecx, [rsp+10D0h+dwPrimaryGroupSize]
0x180022082  and     eax, r9d
0x180022085  sub     r8d, eax
0x180022088  mov     [rsp+10D0h+dwPrimaryGroupSize], ecx
0x18002208c  neg     eax
0x18002208e  sbb     eax, eax
0x180022090  and     eax, r8d
0x180022093  add     esi, eax
0x180022095  lea     eax, [r12+r13]
0x180022099  add     eax, ecx
0x18002209b  add     eax, esi
0x18002209d  add     eax, r10d
0x1800220a0  add     eax, r11d
0x1800220a3  cmp     eax, 0FA0h
0x1800220a8  jnb     short loc_1800220B5
0x1800220aa  mov     eax, esi
0x1800220ac  lea     rsi, [rbp+0FD0h+pSID]
0x1800220b0  add     rsi, rax
0x1800220b3  jmp     short loc_1800220EA
0x1800220b5  lea     eax, [r12+r13]
0x1800220b9  add     ecx, eax
0x1800220bb  add     ecx, r10d
0x1800220be  add     ecx, r11d; unsigned __int64
0x1800220c1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800220c6  mov     [rbp+0FD0h+var_FF0], rax
0x1800220ca  mov     rsi, rax
0x1800220cd  test    rax, rax
0x1800220d0  jz      loc_180021D83
0x1800220d6  mov     r13d, [rsp+10D0h+dwOwnerSize]
0x1800220db  mov     r12d, [rsp+10D0h+dwSaclSize]
0x1800220e0  mov     r11d, [rsp+10D0h+dwDaclSize]
0x1800220e5  mov     r10d, [rsp+10D0h+dwAbsoluteSecurityDescriptorSize]
0x1800220ea  lea     eax, [r10+r11]
0x1800220ee  mov     r9d, r10d
0x1800220f1  lea     ecx, [rax+r12]
  ... truncated ...
```
