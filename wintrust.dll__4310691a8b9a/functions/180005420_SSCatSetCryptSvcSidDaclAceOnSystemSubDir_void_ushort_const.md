# _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(void *,ushort const *)

- ea: `0x180005420`
- end: `0x180005910`
- name: `?_SSCatSetCryptSvcSidDaclAceOnSystemSubDir@@YAXPEAXPEBG@Z`
- size: `1264`
- prototype: `void __fastcall(void *, const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004ea0`

## callees

- `0x180005420`
- `0x180005d00`
- `0x18004de52`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800054fd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800054fd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005749`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000550b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000550b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800054a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000552d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800055c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800054a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000552d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800055c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000566b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005679`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000566b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005679`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005817`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005905`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800056e7`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800056e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005484`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800054cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005484`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800054cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800055b0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800055b0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800058ab`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800058ab`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180005711`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180005711`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180005574`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180005574`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180005609`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180005609`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180005875`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180005875`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005557`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005557`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800058e1`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800058e1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800055e2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800055e2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000559f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000559f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000562c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000562c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000564f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000564f`

## pseudocode

```c
void __fastcall _SSCatSetCryptSvcSidDaclAceOnSystemSubDir(void *a1, const unsigned __int16 *Src)
{
  struct _ACL *v2; // r14
  __int64 v5; // rbx
  UINT SystemDirectoryW; // eax
  UINT v7; // r12d
  WCHAR *v8; // rax
  WCHAR *v9; // r15
  HLOCAL v10; // rsi
  UINT v11; // eax
  DWORD LastError; // eax
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // rcx
  DWORD LengthSid; // eax
  DWORD v18; // ebx
  struct _ACL *v19; // rax
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rcx
  DWORD i; // ebx
  unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // r9
  void *v26; // rcx
  WCHAR *v27; // rcx
  unsigned __int16 *v28; // rcx
  HLOCAL v29; // rax
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // rcx
  unsigned __int16 *v32; // rcx
  unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rcx
  int lpnLengthNeeded; // [rsp+20h] [rbp-58h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-58h]
  int lpnLengthNeededb; // [rsp+20h] [rbp-58h]
  int v38; // [rsp+28h] [rbp-50h]
  DWORD nLengthNeeded; // [rsp+30h] [rbp-48h] BYREF
  WCHAR Buffer; // [rsp+34h] [rbp-44h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-40h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp-3Ch] BYREF
  PACL pDacl; // [rsp+40h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-30h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-28h] BYREF
  int v46; // [rsp+58h] [rbp-20h]

  v2 = 0;
  Buffer = 0;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  nLengthNeeded = 0;
  pAclInformation = 0;
  v46 = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  SystemDirectoryW = GetSystemDirectoryW(&Buffer, 1u);
  v7 = SystemDirectoryW;
  if ( SystemDirectoryW > 1 )
  {
    v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * ((unsigned int)v5 + SystemDirectoryW + 2));
    v9 = v8;
    if ( v8 )
    {
      v10 = 0;
      v11 = GetSystemDirectoryW(v8, v7);
      if ( v11 >= v7 )
        goto LABEL_22;
      v9[v11] = 92;
      memcpy_0(&v9[v11 + 1], Src, 2LL * (unsigned int)(v5 + 1));
      if ( CreateDirectoryW(v9, 0) )
      {
        SetFileAttributesW(v9, 0x2000u);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          ErrLog_LogError(v13, 3u, 0x7Bu, LastError, lpnLengthNeeded, v38);
          v27 = v9;
          goto LABEL_27;
        }
      }
      nLengthNeeded = 1024;
      v10 = LocalAlloc(0x40u, 0x400u);
      if ( v10 )
      {
        while ( !GetFileSecurityW(v9, 4u, v10, nLengthNeeded, &nLengthNeeded) )
        {
          if ( GetLastError() != 122 )
          {
            ErrLog_LogError(v28, 3u, 0x95u, 0, lpnLengthNeededa, v38);
            v26 = v9;
            goto LABEL_24;
          }
          v29 = LocalReAlloc(v10, nLengthNeeded, 0x40u);
          if ( !v29 )
          {
            ErrLog_LogError(v30, 3u, 0x9Cu, 0, lpnLengthNeededa, v38);
            v26 = v9;
            goto LABEL_24;
          }
          v10 = v29;
        }
        if ( !GetSecurityDescriptorDacl(v10, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          ErrLog_LogError(v15, 3u, 0xA8u, 0, lpnLengthNeededa, v38);
          v26 = v9;
          goto LABEL_24;
        }
        if ( pDacl )
        {
          if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
          {
            ErrLog_LogError(v16, 3u, 0xB3u, 0, lpnLengthNeededa, v38);
            v26 = v9;
            goto LABEL_24;
          }
        }
        else
        {
          pAclInformation = 0;
          v46 = 0;
        }
        LengthSid = GetLengthSid(a1);
        v18 = LengthSid + HIDWORD(pAclInformation) + 8;
        v19 = (struct _ACL *)LocalAlloc(0x40u, v18);
        v2 = v19;
        if ( !v19 )
        {
          ErrLog_LogError(v20, 3u, 0xC4u, 0, lpnLengthNeededa, v38);
          v26 = v9;
          goto LABEL_24;
        }
        if ( !InitializeAcl(v19, v18, 2u) )
        {
          ErrLog_LogError(v21, 3u, 0xCAu, 0, lpnLengthNeededa, v38);
LABEL_21:
          LocalFree(v9);
          goto LABEL_23;
        }
        if ( !AddAccessAllowedAceEx(v2, 2u, 3u, 0x1F01FFu, a1) )
        {
          ErrLog_LogError(v22, 3u, 0xD4u, 0, lpnLengthNeededb, v38);
          LocalFree(v9);
LABEL_23:
          v26 = v2;
LABEL_24:
          LocalFree(v26);
          goto LABEL_25;
        }
        for ( i = 0; i < (unsigned int)pAclInformation; ++i )
        {
          if ( !GetAce(pDacl, i, &pAce) )
          {
            ErrLog_LogError(v24, 3u, 0xE0u, 0, lpnLengthNeededb, v38);
            LocalFree(v9);
            goto LABEL_23;
          }
          v25 = (unsigned __int16 *)pAce;
          if ( !*(_BYTE *)pAce )
          {
            if ( EqualSid(a1, (char *)pAce + 8) )
              goto LABEL_21;
            v25 = (unsigned __int16 *)pAce;
          }
          if ( !AddAce(v2, 2u, 0xFFFFFFFF, v25, v25[1]) )
          {
            ErrLog_LogError(v31, 3u, 0xF1u, 0, lpnLengthNeededb, v38);
            LocalFree(v9);
            goto LABEL_23;
          }
        }
        if ( !InitializeSecurityDescriptor(v10, 1u) )
        {
          ErrLog_LogError(v32, 3u, 0x104u, 0, lpnLengthNeededb, v38);
          LocalFree(v9);
          goto LABEL_23;
        }
        if ( !SetSecurityDescriptorDacl(v10, 1, v2, 0) )
        {
          ErrLog_LogError(v33, 3u, 0x10Du, 0, lpnLengthNeededb, v38);
          LocalFree(v9);
          goto LABEL_23;
        }
        if ( !SetFileSecurityW(v9, 4u, v10) )
        {
          ErrLog_LogError(v34, 3u, 0x116u, 0, lpnLengthNeededb, v38);
          LocalFree(v9);
          goto LABEL_23;
        }
LABEL_22:
        LocalFree(v9);
        if ( !v2 )
        {
LABEL_25:
          if ( !v10 )
            return;
          v27 = (WCHAR *)v10;
          goto LABEL_27;
        }
        goto LABEL_23;
      }
      ErrLog_LogError(v14, 3u, 0x88u, 0, lpnLengthNeeded, v38);
      v27 = v9;
LABEL_27:
      LocalFree(v27);
    }
  }
}

```

## disassembly

```asm
0x180005420  push    rbp
0x180005422  push    rbx
0x180005423  push    rdi
0x180005424  push    r12
0x180005426  push    r13
0x180005428  push    r14
0x18000542a  mov     rbp, rsp
0x18000542d  sub     rsp, 78h
0x180005431  mov     rax, cs:__security_cookie
0x180005438  xor     rax, rsp
0x18000543b  mov     [rbp+var_18], rax
0x18000543f  xor     r14d, r14d
0x180005442  mov     rdi, rdx
0x180005445  mov     [rbp+Buffer], r14w
0x18000544a  mov     r13, rcx
0x18000544d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005454  inc     rbx
0x180005457  cmp     [rdx+rbx*2], r14w
0x18000545c  jnz     short loc_180005454
0x18000545e  xor     eax, eax
0x180005460  mov     [rbp+nLengthNeeded], r14d
0x180005464  mov     edx, 1; uSize
0x180005469  mov     [rbp+pAclInformation], rax
0x18000546d  lea     rcx, [rbp+Buffer]; lpBuffer
0x180005471  mov     [rbp+var_20], eax
0x180005474  mov     [rbp+pDacl], r14
0x180005478  mov     [rbp+bDaclPresent], r14d
0x18000547c  mov     [rbp+bDaclDefaulted], r14d
0x180005480  mov     [rbp+pAce], r14
0x180005484  call    cs:__imp_GetSystemDirectoryW
0x18000548a  mov     r12d, eax
0x18000548d  cmp     eax, 1
0x180005490  jbe     loc_18000569A
0x180005496  lea     edx, [rax+2]
0x180005499  mov     [rsp+78h+var_8], r15
0x18000549e  add     edx, ebx
0x1800054a0  mov     ecx, 40h ; '@'; uFlags
0x1800054a5  add     rdx, rdx; uBytes
0x1800054a8  call    cs:__imp_LocalAlloc
0x1800054ae  mov     r15, rax
0x1800054b1  test    rax, rax
0x1800054b4  jz      loc_180005695
0x1800054ba  mov     [rsp+78h+arg_10], rsi
0x1800054c2  mov     edx, r12d; uSize
0x1800054c5  mov     rcx, rax; lpBuffer
0x1800054c8  mov     rsi, r14
0x1800054cb  call    cs:__imp_GetSystemDirectoryW
0x1800054d1  cmp     eax, r12d
0x1800054d4  jnb     loc_180005668
0x1800054da  mov     ecx, eax
0x1800054dc  lea     r8d, [rbx+1]
0x1800054e0  add     r8, r8; Size
0x1800054e3  mov     rdx, rdi; Src
0x1800054e6  inc     eax
0x1800054e8  mov     word ptr [r15+rcx*2], 5Ch ; '\'
0x1800054ef  lea     rcx, [r15+rax*2]; void *
0x1800054f3  call    memcpy_0
0x1800054f8  xor     edx, edx; lpSecurityAttributes
0x1800054fa  mov     rcx, r15; lpPathName
0x1800054fd  call    cs:__imp_CreateDirectoryW
0x180005503  test    eax, eax
0x180005505  jnz     loc_180005741
0x18000550b  call    cs:__imp_GetLastError
0x180005511  cmp     eax, 0B7h
0x180005516  jnz     loc_180005726
0x18000551c  mov     edx, 400h; uBytes
0x180005521  mov     [rbp+nLengthNeeded], 400h
0x180005528  mov     ecx, 40h ; '@'; uFlags
0x18000552d  call    cs:__imp_LocalAlloc
0x180005533  mov     rsi, rax
0x180005536  test    rax, rax
0x180005539  jz      loc_180005754
0x18000553f  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180005543  lea     rax, [rbp+nLengthNeeded]
0x180005547  mov     r8, rsi; pSecurityDescriptor
0x18000554a  mov     [rsp+78h+lpnLengthNeeded], rax; int
0x18000554f  mov     edx, 4; RequestedInformation
0x180005554  mov     rcx, r15; lpFileName
0x180005557  call    cs:__imp_GetFileSecurityW
0x18000555d  test    eax, eax
0x18000555f  jz      loc_1800056CC
0x180005565  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180005569  mov     rcx, rsi; pSecurityDescriptor
0x18000556c  lea     r8, [rbp+pDacl]; pDacl
0x180005570  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180005574  call    cs:__imp_GetSecurityDescriptorDacl
0x18000557a  test    eax, eax
0x18000557c  jz      loc_1800056B4
0x180005582  mov     rcx, [rbp+pDacl]; pAcl
0x180005586  test    rcx, rcx
0x180005589  jz      loc_1800057C0
0x18000558f  mov     r9d, 2; dwAclInformationClass
0x180005595  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x180005599  mov     r8d, 0Ch; nAclInformationLength
0x18000559f  call    cs:__imp_GetAclInformation
0x1800055a5  test    eax, eax
0x1800055a7  jz      loc_1800057A5
0x1800055ad  mov     rcx, r13; pSid
0x1800055b0  call    cs:__imp_GetLengthSid
0x1800055b6  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1800055b9  mov     ecx, 40h ; '@'; uFlags
0x1800055be  add     ebx, 8
0x1800055c1  add     ebx, eax
0x1800055c3  mov     edx, ebx; uBytes
0x1800055c5  call    cs:__imp_LocalAlloc
0x1800055cb  mov     r14, rax
0x1800055ce  test    rax, rax
0x1800055d1  jz      loc_1800057CE
0x1800055d7  mov     r8d, 2; dwAclRevision
0x1800055dd  mov     edx, ebx; nAclLength
0x1800055df  mov     rcx, rax; pAcl
0x1800055e2  call    cs:__imp_InitializeAcl
0x1800055e8  test    eax, eax
0x1800055ea  jz      loc_1800057E9
0x1800055f0  mov     edx, 2; dwAceRevision
0x1800055f5  mov     [rsp+78h+lpnLengthNeeded], r13; int
0x1800055fa  mov     r9d, 1F01FFh; AccessMask
0x180005600  mov     r8d, 3; AceFlags
0x180005606  mov     rcx, r14; pAcl
0x180005609  call    cs:__imp_AddAccessAllowedAceEx
0x18000560f  test    eax, eax
0x180005611  jz      loc_180005801
0x180005617  xor     ebx, ebx
0x180005619  cmp     ebx, dword ptr [rbp+pAclInformation]
0x18000561c  jnb     loc_18000586D
0x180005622  mov     rcx, [rbp+pDacl]; pAcl
0x180005626  lea     r8, [rbp+pAce]; pAce
0x18000562a  mov     edx, ebx; dwAceIndex
0x18000562c  call    cs:__imp_GetAce
0x180005632  test    eax, eax
0x180005634  jz      loc_18000584C
0x18000563a  mov     r9, [rbp+pAce]; pAceList
0x18000563e  cmp     byte ptr [r9], 0
0x180005642  jnz     loc_1800056FA
0x180005648  lea     rdx, [r9+8]; pSid2
0x18000564c  mov     rcx, r13; pSid1
0x18000564f  call    cs:__imp_EqualSid
0x180005655  test    eax, eax
0x180005657  jz      loc_180005822
0x18000565d  mov     rcx, r15; hMem
0x180005660  call    cs:__imp_LocalFree
0x180005666  jmp     short loc_180005676
0x180005668  mov     rcx, r15; hMem
0x18000566b  call    cs:__imp_LocalFree
0x180005671  test    r14, r14
0x180005674  jz      short loc_18000567F
0x180005676  mov     rcx, r14; hMem
0x180005679  call    cs:__imp_LocalFree
0x18000567f  test    rsi, rsi
0x180005682  jz      short loc_18000568D
0x180005684  mov     rcx, rsi; hMem
0x180005687  call    cs:__imp_LocalFree
0x18000568d  mov     rsi, [rsp+78h+arg_10]
0x180005695  mov     r15, [rsp+78h+var_8]
0x18000569a  mov     rcx, [rbp+var_18]
0x18000569e  xor     rcx, rsp; StackCookie
0x1800056a1  call    __security_check_cookie
0x1800056a6  add     rsp, 78h
0x1800056aa  pop     r14
0x1800056ac  pop     r13
0x1800056ae  pop     r12
0x1800056b0  pop     rdi
0x1800056b1  pop     rbx
0x1800056b2  pop     rbp
0x1800056b3  retn
0x1800056b4  xor     r9d, r9d; unsigned int
0x1800056b7  mov     edx, 3; unsigned int
0x1800056bc  mov     r8d, 0A8h; unsigned int
0x1800056c2  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800056c7  mov     rcx, r15
0x1800056ca  jmp     short loc_180005679
0x1800056cc  call    cs:__imp_GetLastError
0x1800056d2  cmp     eax, 7Ah ; 'z'
0x1800056d5  jnz     loc_18000578A
0x1800056db  mov     edx, [rbp+nLengthNeeded]; uBytes
0x1800056de  mov     r8d, 40h ; '@'; uFlags
0x1800056e4  mov     rcx, rsi; hMem
0x1800056e7  call    cs:__imp_LocalReAlloc
0x1800056ed  test    rax, rax
0x1800056f0  jz      short loc_18000576F
0x1800056f2  mov     rsi, rax
0x1800056f5  jmp     loc_18000553F
0x1800056fa  movzx   eax, word ptr [r9+2]
0x1800056ff  mov     edx, 2; dwAceRevision
0x180005704  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18000570a  mov     dword ptr [rsp+78h+lpnLengthNeeded], eax; int
0x18000570e  mov     rcx, r14; pAcl
0x180005711  call    cs:__imp_AddAce
0x180005717  test    eax, eax
0x180005719  jz      loc_18000582B
0x18000571f  inc     ebx
0x180005721  jmp     loc_180005619
0x180005726  mov     r9d, eax; unsigned int
0x180005729  mov     edx, 3; unsigned int
0x18000572e  mov     r8d, 7Bh ; '{'; unsigned int
0x180005734  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005739  mov     rcx, r15
0x18000573c  jmp     loc_180005687
0x180005741  mov     edx, 2000h; dwFileAttributes
0x180005746  mov     rcx, r15; lpFileName
0x180005749  call    cs:__imp_SetFileAttributesW
0x18000574f  jmp     loc_18000551C
0x180005754  xor     r9d, r9d; unsigned int
0x180005757  mov     edx, 3; unsigned int
0x18000575c  mov     r8d, 88h; unsigned int
0x180005762  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005767  mov     rcx, r15
0x18000576a  jmp     loc_180005687
0x18000576f  xor     r9d, r9d; unsigned int
0x180005772  mov     edx, 3; unsigned int
0x180005777  mov     r8d, 9Ch; unsigned int
0x18000577d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005782  mov     rcx, r15
0x180005785  jmp     loc_180005679
0x18000578a  xor     r9d, r9d; unsigned int
0x18000578d  mov     edx, 3; unsigned int
0x180005792  mov     r8d, 95h; unsigned int
0x180005798  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000579d  mov     rcx, r15
0x1800057a0  jmp     loc_180005679
0x1800057a5  xor     r9d, r9d; unsigned int
0x1800057a8  mov     edx, 3; unsigned int
0x1800057ad  mov     r8d, 0B3h; unsigned int
0x1800057b3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800057b8  mov     rcx, r15
0x1800057bb  jmp     loc_180005679
0x1800057c0  xor     eax, eax
0x1800057c2  mov     [rbp+pAclInformation], rax
0x1800057c6  mov     [rbp+var_20], eax
0x1800057c9  jmp     loc_1800055AD
0x1800057ce  xor     r9d, r9d; unsigned int
0x1800057d1  mov     edx, 3; unsigned int
0x1800057d6  mov     r8d, 0C4h; unsigned int
0x1800057dc  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800057e1  mov     rcx, r15
0x1800057e4  jmp     loc_180005679
0x1800057e9  xor     r9d, r9d; unsigned int
0x1800057ec  mov     edx, 3; unsigned int
0x1800057f1  mov     r8d, 0CAh; unsigned int
0x1800057f7  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800057fc  jmp     loc_18000565D
0x180005801  xor     r9d, r9d; unsigned int
0x180005804  mov     edx, 3; unsigned int
0x180005809  mov     r8d, 0D4h; unsigned int
0x18000580f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005814  mov     rcx, r15; hMem
0x180005817  call    cs:__imp_LocalFree
0x18000581d  jmp     loc_180005676
0x180005822  mov     r9, [rbp+pAce]
0x180005826  jmp     loc_1800056FA
0x18000582b  xor     r9d, r9d; unsigned int
0x18000582e  mov     edx, 3; unsigned int
0x180005833  mov     r8d, 0F1h; unsigned int
0x180005839  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000583e  mov     rcx, r15; hMem
0x180005841  call    cs:__imp_LocalFree
0x180005847  jmp     loc_180005676
0x18000584c  xor     r9d, r9d; unsigned int
0x18000584f  mov     edx, 3; unsigned int
0x180005854  mov     r8d, 0E0h; unsigned int
0x18000585a  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000585f  mov     rcx, r15; hMem
0x180005862  call    cs:__imp_LocalFree
0x180005868  jmp     loc_180005676
0x18000586d  mov     edx, 1; dwRevision
0x180005872  mov     rcx, rsi; pSecurityDescriptor
0x180005875  call    cs:__imp_InitializeSecurityDescriptor
0x18000587b  xor     r9d, r9d; unsigned int
0x18000587e  test    eax, eax
0x180005880  jnz     short loc_1800058A0
0x180005882  mov     edx, 3; unsigned int
0x180005887  mov     r8d, 104h; unsigned int
0x18000588d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005892  mov     rcx, r15; hMem
0x180005895  call    cs:__imp_LocalFree
0x18000589b  jmp     loc_180005676
0x1800058a0  mov     r8, r14; pDacl
0x1800058a3  mov     edx, 1; bDaclPresent
0x1800058a8  mov     rcx, rsi; pSecurityDescriptor
0x1800058ab  call    cs:__imp_SetSecurityDescriptorDacl
0x1800058b1  test    eax, eax
0x1800058b3  jnz     short loc_1800058D6
0x1800058b5  xor     r9d, r9d; unsigned int
0x1800058b8  mov     edx, 3; unsigned int
0x1800058bd  mov     r8d, 10Dh; unsigned int
0x1800058c3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800058c8  mov     rcx, r15; hMem
0x1800058cb  call    cs:__imp_LocalFree
0x1800058d1  jmp     loc_180005676
0x1800058d6  mov     r8, rsi; pSecurityDescriptor
0x1800058d9  mov     edx, 4; SecurityInformation
0x1800058de  mov     rcx, r15; lpFileName
0x1800058e1  call    cs:__imp_SetFileSecurityW
0x1800058e7  test    eax, eax
0x1800058e9  jnz     loc_180005668
0x1800058ef  xor     r9d, r9d; unsigned int
0x1800058f2  mov     edx, 3; unsigned int
0x1800058f7  mov     r8d, 116h; unsigned int
0x1800058fd  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005902  mov     rcx, r15; hMem
  ... truncated ...
```
