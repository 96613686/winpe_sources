# RdVhd::Uvhd::CDirectoryHelper::SetFileOrFolderSecurityForUser(ushort const *,ushort const *,int)

- ea: `0x18004f3d0`
- end: `0x18004f964`
- name: `?SetFileOrFolderSecurityForUser@CDirectoryHelper@Uvhd@RdVhd@@UEBAJPEBG0H@Z`
- size: `1428`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800191a0`
- `0x1800192a4`
- `0x180042ff4`
- `0x1800488e4`
- `0x180048b28`
- `0x18004c82c`
- `0x18004e128`
- `0x18004f09c`
- `0x18004f3d0`
- `0x18004f96c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f811`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004f69a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004f69a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004f780`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004f780`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f564`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f564`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f90d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f90d`

## string_xrefs

- `0x18004f433`: `szPath`
- `0x18004f47c`: `szSidString`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::SetFileOrFolderSecurityForUser(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  PSECURITY_DESCRIPTOR v4; // r12
  PACL v6; // r15
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  signed int v11; // ebx
  int v12; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int LastError; // eax
  unsigned int v17; // ecx
  HLOCAL v18; // rax
  unsigned int v19; // r8d
  void *v20; // r13
  RdVhd::Uvhd::CDirectoryHelper *v21; // rcx
  signed int v22; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // eax
  RdVhd::Uvhd::CDirectoryHelper *v27; // rcx
  signed int v28; // eax
  int v29; // eax
  unsigned int v30; // r8d
  signed int v31; // eax
  RdVhd::Uvhd::CDirectoryHelper *v32; // rcx
  signed int v33; // eax
  RdVhd::Uvhd::CDirectoryHelper *v34; // rcx
  int v35; // eax
  RdVhd::Uvhd::CDirectoryHelper *v36; // rcx
  unsigned int v38; // [rsp+30h] [rbp-38h] BYREF
  WINBOOL bDaclPresent; // [rsp+34h] [rbp-34h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  PACL v42; // [rsp+48h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-18h] BYREF
  SIZE_T uBytes; // [rsp+B8h] [rbp+50h] BYREF

  v4 = 0;
  v6 = 0;
  pSecurityDescriptor = 0;
  v42 = 0;
  LODWORD(uBytes) = 0;
  v38 = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    v9 = 22;
    v10 = L"szPath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v10);
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    v9 = 23;
    v10 = L"szSidString";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    if ( RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(this, a2, (unsigned int)a3, 0, 0, (unsigned int *)&uBytes) )
    {
      v11 = -797309640;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v14 = 26;
LABEL_117:
      v15 = (unsigned int)v11;
      goto LABEL_118;
    }
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      v17 = v17 & 0x8000FFFF | 0x50020000;
    }
    v11 = 0;
    if ( (_WORD)v17 != 122 )
      v11 = v17;
    if ( v11 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v11;
      }
      v14 = 25;
      goto LABEL_117;
    }
    v18 = LocalAlloc(0, (unsigned int)uBytes);
    v20 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids);
      }
      return (unsigned int)-2147024882;
    }
    v38 = uBytes;
    if ( RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(
           (RdVhd::Uvhd::CDirectoryHelper *)&v38,
           a2,
           v19,
           v18,
           uBytes,
           &v38) )
    {
      goto LABEL_50;
    }
    v22 = GetLastError();
    v11 = v22;
    if ( v22 && (v22 & 0xFFFF0000) == 0 )
    {
      if ( v22 > 0 )
        v11 = (unsigned __int16)v22 | 0x80070000;
      v11 = v11 & 0x8000FFFF | 0x50030000;
    }
    if ( v11 >= 0 )
    {
LABEL_50:
      v26 = RdVhd::Uvhd::CDirectoryHelper::SelfRelativeToAbsoluteSD(v21, v20, &pSecurityDescriptor);
      v11 = v26;
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids,
            (unsigned int)v26);
        }
        v4 = pSecurityDescriptor;
        goto LABEL_109;
      }
      v4 = pSecurityDescriptor;
      if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        goto LABEL_68;
      v28 = GetLastError();
      v11 = v28;
      if ( v28 && (v28 & 0xFFFF0000) == 0 )
      {
        if ( v28 > 0 )
          v11 = (unsigned __int16)v28 | 0x80070000;
        v11 = v11 & 0x8000FFFF | 0x50040000;
      }
      if ( v11 >= 0 )
      {
LABEL_68:
        if ( !bDaclPresent || !pDacl )
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, a2);
          }
          v35 = RdVhd::Uvhd::CDirectoryHelper::SetFileOrFolderSecurityForUserStrict(v34, a2, a3);
          v11 = v35;
          if ( v35 >= 0 )
            goto LABEL_109;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_109;
          }
          v24 = 32;
          v25 = (unsigned int)v35;
          goto LABEL_108;
        }
        v29 = RdVhd::Uvhd::CDirectoryHelper::AddUserAce(v27, pDacl, a3, &v42);
        v11 = v29;
        if ( v29 < 0 )
        {
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids,
              (unsigned int)v29);
          }
          v6 = v42;
          goto LABEL_109;
        }
        v6 = v42;
        if ( SetSecurityDescriptorDacl(v4, 1, v42, 0) )
          goto LABEL_86;
        v31 = GetLastError();
        v11 = v31;
        if ( v31 && (v31 & 0xFFFF0000) == 0 )
        {
          if ( v31 > 0 )
            v11 = (unsigned __int16)v31 | 0x80070000;
          v11 = v11 & 0x8000FFFF | 0x50050000;
        }
        if ( v11 >= 0 )
        {
LABEL_86:
          v32 = (RdVhd::Uvhd::CDirectoryHelper *)pDacl;
          v6 = 0;
          if ( pDacl )
            LocalFree(pDacl);
          if ( RdVhd::Uvhd::CDirectoryHelper::SetFileSecurityW(v32, a2, v30, v4) )
            goto LABEL_109;
          v33 = GetLastError();
          v11 = v33;
          if ( v33 && (v33 & 0xFFFF0000) == 0 )
          {
            if ( v33 > 0 )
              v11 = (unsigned __int16)v33 | 0x80070000;
            v11 = v11 & 0x8000FFFF | 0x50060000;
          }
          if ( v11 >= 0 )
            goto LABEL_109;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_109;
          }
          v24 = 35;
        }
        else
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_109;
          }
          v24 = 34;
        }
      }
      else
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_109;
        }
        v24 = 30;
      }
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v24 = 28;
    }
    v25 = (unsigned int)v11;
LABEL_108:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v25);
LABEL_109:
    LocalFree(v20);
    if ( v4 )
      RdVhd::Uvhd::CDirectoryHelper::DeleteSD(v36, v4);
    if ( v6 )
      LocalFree(v6);
    return (unsigned int)v11;
  }
  v12 = RdVhd::Uvhd::CDirectoryHelper::SetFileOrFolderSecurityForUserStrict(this, a2, a3);
  v11 = v12;
  if ( v12 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 24;
      v15 = (unsigned int)v12;
LABEL_118:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v15);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004f3d0  push    rbp
0x18004f3d2  push    rbx
0x18004f3d3  push    rsi
0x18004f3d4  push    rdi
0x18004f3d5  push    r12
0x18004f3d7  push    r13
0x18004f3d9  push    r14
0x18004f3db  push    r15
0x18004f3dd  mov     rbp, rsp
0x18004f3e0  sub     rsp, 68h
0x18004f3e4  xor     r12d, r12d
0x18004f3e7  mov     r14, r8
0x18004f3ea  xor     r15d, r15d
0x18004f3ed  mov     [rbp+pSecurityDescriptor], r12
0x18004f3f1  mov     [rbp+var_20], r15
0x18004f3f5  mov     rsi, rdx
0x18004f3f8  mov     dword ptr [rbp+uBytes], r12d
0x18004f3fc  mov     [rbp+var_38], r12d
0x18004f400  mov     [rbp+pDacl], r12
0x18004f404  mov     [rbp+bDaclPresent], r12d
0x18004f408  mov     [rbp+bDaclDefaulted], r12d
0x18004f40c  test    rdx, rdx
0x18004f40f  jnz     short loc_18004F454
0x18004f411  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f418  lea     rdi, WPP_GLOBAL_Control
0x18004f41f  cmp     rcx, rdi
0x18004f422  jz      short loc_18004F44A
0x18004f424  test    byte ptr [rcx+1Ch], 4
0x18004f428  jz      short loc_18004F44A
0x18004f42a  cmp     byte ptr [rcx+19h], 2
0x18004f42e  jb      short loc_18004F44A
0x18004f430  lea     edx, [rsi+16h]
0x18004f433  lea     r9, aSzpath; "szPath"
0x18004f43a  mov     rcx, [rcx+10h]
0x18004f43e  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004f445  call    WPP_SF_S
0x18004f44a  mov     ebx, 80070057h
0x18004f44f  jmp     loc_18004F951
0x18004f454  test    r14, r14
0x18004f457  jnz     short loc_18004F485
0x18004f459  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004f460  lea     rdi, WPP_GLOBAL_Control
0x18004f467  cmp     rcx, rdi
0x18004f46a  jz      short loc_18004F44A
0x18004f46c  test    byte ptr [rcx+1Ch], 4
0x18004f470  jz      short loc_18004F44A
0x18004f472  cmp     byte ptr [rcx+19h], 2
0x18004f476  jb      short loc_18004F44A
0x18004f478  lea     edx, [r14+17h]; unsigned __int16 *
0x18004f47c  lea     r9, aSzsidstring; "szSidString"
0x18004f483  jmp     short loc_18004F43A
0x18004f485  test    r9d, r9d
0x18004f488  jz      short loc_18004F4D1
0x18004f48a  call    ?SetFileOrFolderSecurityForUserStrict@CDirectoryHelper@Uvhd@RdVhd@@AEBAJPEBG0@Z; RdVhd::Uvhd::CDirectoryHelper::SetFileOrFolderSecurityForUserStrict(ushort const *,ushort const *)
0x18004f48f  mov     ebx, eax
0x18004f491  test    eax, eax
0x18004f493  jns     loc_18004F951
0x18004f499  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004f4a0  lea     rdi, WPP_GLOBAL_Control
0x18004f4a7  cmp     rcx, rdi
0x18004f4aa  jz      loc_18004F951
0x18004f4b0  test    byte ptr [rcx+1Ch], 4
0x18004f4b4  jz      loc_18004F951
0x18004f4ba  cmp     byte ptr [rcx+19h], 2
0x18004f4be  jb      loc_18004F951
0x18004f4c4  mov     edx, 18h; unsigned __int16 *
0x18004f4c9  mov     r9d, eax
0x18004f4cc  jmp     loc_18004F941
0x18004f4d1  lea     rax, [rbp+uBytes]
0x18004f4d5  xor     r9d, r9d; void *
0x18004f4d8  mov     [rsp+68h+var_40], rax; unsigned int *
0x18004f4dd  mov     [rsp+68h+var_48], r12d; unsigned int
0x18004f4e2  call    ?GetFileSecurityW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGKPEAXKPEAK@Z; RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(ushort const *,ulong,void *,ulong,ulong *)
0x18004f4e7  test    eax, eax
0x18004f4e9  jnz     loc_18004F915
0x18004f4ef  call    cs:__imp_GetLastError
0x18004f4f5  mov     ecx, eax
0x18004f4f7  mov     edi, 0FFFF0000h
0x18004f4fc  test    eax, eax
0x18004f4fe  jz      short loc_18004F51D
0x18004f500  test    edi, eax
0x18004f502  jnz     short loc_18004F51D
0x18004f504  test    eax, eax
0x18004f506  jle     short loc_18004F511
0x18004f508  movzx   ecx, ax
0x18004f50b  or      ecx, 80070000h
0x18004f511  and     ecx, 0D002FFFFh
0x18004f517  or      ecx, 50020000h
0x18004f51d  xor     ebx, ebx
0x18004f51f  cmp     cx, 7Ah ; 'z'
0x18004f523  cmovnz  ebx, ecx
0x18004f526  test    ebx, ebx
0x18004f528  jns     short loc_18004F55F
0x18004f52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f531  lea     rdi, WPP_GLOBAL_Control
0x18004f538  cmp     rcx, rdi
0x18004f53b  jz      loc_18004F951
0x18004f541  test    byte ptr [rcx+1Ch], 4
0x18004f545  jz      loc_18004F951
0x18004f54b  cmp     byte ptr [rcx+19h], 2
0x18004f54f  jb      loc_18004F951
0x18004f555  mov     edx, 19h
0x18004f55a  jmp     loc_18004F93E
0x18004f55f  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18004f562  xor     ecx, ecx; uFlags
0x18004f564  call    cs:__imp_LocalAlloc
0x18004f56a  mov     r13, rax
0x18004f56d  test    rax, rax
0x18004f570  jnz     short loc_18004F5AE
0x18004f572  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f579  lea     rdi, WPP_GLOBAL_Control
0x18004f580  cmp     rcx, rdi
0x18004f583  jz      short loc_18004F5A4
0x18004f585  test    byte ptr [rcx+1Ch], 4
0x18004f589  jz      short loc_18004F5A4
0x18004f58b  cmp     byte ptr [rcx+19h], 2
0x18004f58f  jb      short loc_18004F5A4
0x18004f591  mov     rcx, [rcx+10h]
0x18004f595  lea     edx, [rax+1Bh]
0x18004f598  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004f59f  call    WPP_SF_
0x18004f5a4  mov     ebx, 8007000Eh
0x18004f5a9  jmp     loc_18004F951
0x18004f5ae  mov     eax, dword ptr [rbp+uBytes]
0x18004f5b1  lea     rcx, [rbp+var_38]; this
0x18004f5b5  mov     [rsp+68h+var_40], rcx; unsigned int *
0x18004f5ba  mov     r9, r13; void *
0x18004f5bd  mov     rdx, rsi; unsigned __int16 *
0x18004f5c0  mov     [rsp+68h+var_48], eax; unsigned int
0x18004f5c4  mov     [rbp+var_38], eax
0x18004f5c7  call    ?GetFileSecurityW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGKPEAXKPEAK@Z; RdVhd::Uvhd::CDirectoryHelper::GetFileSecurityW(ushort const *,ulong,void *,ulong,ulong *)
0x18004f5cc  test    eax, eax
0x18004f5ce  jnz     short loc_18004F635
0x18004f5d0  call    cs:__imp_GetLastError
0x18004f5d6  mov     ebx, eax
0x18004f5d8  test    eax, eax
0x18004f5da  jz      short loc_18004F5F9
0x18004f5dc  test    edi, eax
0x18004f5de  jnz     short loc_18004F5F9
0x18004f5e0  test    eax, eax
0x18004f5e2  jle     short loc_18004F5ED
0x18004f5e4  movzx   ebx, ax
0x18004f5e7  or      ebx, 80070000h
0x18004f5ed  and     ebx, 0D003FFFFh
0x18004f5f3  or      ebx, 50030000h
0x18004f5f9  test    ebx, ebx
0x18004f5fb  jns     short loc_18004F635
0x18004f5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f604  lea     rdi, WPP_GLOBAL_Control
0x18004f60b  cmp     rcx, rdi
0x18004f60e  jz      loc_18004F8EF
0x18004f614  test    byte ptr [rcx+1Ch], 4
0x18004f618  jz      loc_18004F8EF
0x18004f61e  cmp     byte ptr [rcx+19h], 2
0x18004f622  jb      loc_18004F8EF
0x18004f628  mov     edx, 1Ch
0x18004f62d  mov     r9d, ebx
0x18004f630  jmp     loc_18004F8DF
0x18004f635  lea     r8, [rbp+pSecurityDescriptor]; void **
0x18004f639  mov     rdx, r13; void *
0x18004f63c  call    ?SelfRelativeToAbsoluteSD@CDirectoryHelper@Uvhd@RdVhd@@AEBAJPEAXPEAPEAX@Z; RdVhd::Uvhd::CDirectoryHelper::SelfRelativeToAbsoluteSD(void *,void * *)
0x18004f641  mov     ebx, eax
0x18004f643  test    eax, eax
0x18004f645  jns     short loc_18004F687
0x18004f647  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f64e  lea     rdi, WPP_GLOBAL_Control
0x18004f655  cmp     rcx, rdi
0x18004f658  jz      short loc_18004F67E
0x18004f65a  test    byte ptr [rcx+1Ch], 4
0x18004f65e  jz      short loc_18004F67E
0x18004f660  cmp     byte ptr [rcx+19h], 2
0x18004f664  jb      short loc_18004F67E
0x18004f666  mov     rcx, [rcx+10h]
0x18004f66a  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004f671  mov     edx, 1Dh
0x18004f676  mov     r9d, eax
0x18004f679  call    WPP_SF_d
0x18004f67e  mov     r12, [rbp+pSecurityDescriptor]
0x18004f682  jmp     loc_18004F8EF
0x18004f687  mov     r12, [rbp+pSecurityDescriptor]
0x18004f68b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18004f68f  mov     rcx, r12; pSecurityDescriptor
0x18004f692  lea     r8, [rbp+pDacl]; pDacl
0x18004f696  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004f69a  call    cs:__imp_GetSecurityDescriptorDacl
0x18004f6a0  test    eax, eax
0x18004f6a2  jnz     short loc_18004F706
0x18004f6a4  call    cs:__imp_GetLastError
0x18004f6aa  mov     ebx, eax
0x18004f6ac  test    eax, eax
0x18004f6ae  jz      short loc_18004F6CD
0x18004f6b0  test    edi, eax
0x18004f6b2  jnz     short loc_18004F6CD
0x18004f6b4  test    eax, eax
0x18004f6b6  jle     short loc_18004F6C1
0x18004f6b8  movzx   ebx, ax
0x18004f6bb  or      ebx, 80070000h
0x18004f6c1  and     ebx, 0D004FFFFh
0x18004f6c7  or      ebx, 50040000h
0x18004f6cd  test    ebx, ebx
0x18004f6cf  jns     short loc_18004F706
0x18004f6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6d8  lea     rdi, WPP_GLOBAL_Control
0x18004f6df  cmp     rcx, rdi
0x18004f6e2  jz      loc_18004F8EF
0x18004f6e8  test    byte ptr [rcx+1Ch], 4
0x18004f6ec  jz      loc_18004F8EF
0x18004f6f2  cmp     byte ptr [rcx+19h], 2
0x18004f6f6  jb      loc_18004F8EF
0x18004f6fc  mov     edx, 1Eh
0x18004f701  jmp     loc_18004F62D
0x18004f706  cmp     [rbp+bDaclPresent], r15d
0x18004f70a  jz      loc_18004F877
0x18004f710  mov     rdx, [rbp+pDacl]; struct _ACL *
0x18004f714  test    rdx, rdx
0x18004f717  jz      loc_18004F877
0x18004f71d  lea     r9, [rbp+var_20]; struct _ACL **
0x18004f721  mov     r8, r14; unsigned __int16 *
0x18004f724  call    ?AddUserAce@CDirectoryHelper@Uvhd@RdVhd@@AEBAJPEAU_ACL@@PEBGPEAPEAU4@@Z; RdVhd::Uvhd::CDirectoryHelper::AddUserAce(_ACL *,ushort const *,_ACL * *)
0x18004f729  mov     ebx, eax
0x18004f72b  test    eax, eax
0x18004f72d  jns     short loc_18004F76F
0x18004f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f736  lea     rdi, WPP_GLOBAL_Control
0x18004f73d  cmp     rcx, rdi
0x18004f740  jz      short loc_18004F766
0x18004f742  test    byte ptr [rcx+1Ch], 4
0x18004f746  jz      short loc_18004F766
0x18004f748  cmp     byte ptr [rcx+19h], 2
0x18004f74c  jb      short loc_18004F766
0x18004f74e  mov     rcx, [rcx+10h]
0x18004f752  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004f759  mov     edx, 21h ; '!'
0x18004f75e  mov     r9d, eax
0x18004f761  call    WPP_SF_d
0x18004f766  mov     r15, [rbp+var_20]
0x18004f76a  jmp     loc_18004F8EF
0x18004f76f  mov     r15, [rbp+var_20]
0x18004f773  xor     r9d, r9d; bDaclDefaulted
0x18004f776  mov     r8, r15; pDacl
0x18004f779  mov     rcx, r12; pSecurityDescriptor
0x18004f77c  lea     edx, [r9+1]; bDaclPresent
0x18004f780  call    cs:__imp_SetSecurityDescriptorDacl
0x18004f786  test    eax, eax
0x18004f788  jnz     short loc_18004F7EC
0x18004f78a  call    cs:__imp_GetLastError
0x18004f790  mov     ebx, eax
0x18004f792  test    eax, eax
0x18004f794  jz      short loc_18004F7B3
0x18004f796  test    edi, eax
0x18004f798  jnz     short loc_18004F7B3
0x18004f79a  test    eax, eax
0x18004f79c  jle     short loc_18004F7A7
0x18004f79e  movzx   ebx, ax
0x18004f7a1  or      ebx, 80070000h
0x18004f7a7  and     ebx, 0D005FFFFh
0x18004f7ad  or      ebx, 50050000h
0x18004f7b3  test    ebx, ebx
0x18004f7b5  jns     short loc_18004F7EC
0x18004f7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f7be  lea     rdi, WPP_GLOBAL_Control
0x18004f7c5  cmp     rcx, rdi
0x18004f7c8  jz      loc_18004F8EF
0x18004f7ce  test    byte ptr [rcx+1Ch], 4
0x18004f7d2  jz      loc_18004F8EF
0x18004f7d8  cmp     byte ptr [rcx+19h], 2
0x18004f7dc  jb      loc_18004F8EF
0x18004f7e2  mov     edx, 22h ; '"'
0x18004f7e7  jmp     loc_18004F62D
0x18004f7ec  mov     rcx, [rbp+pDacl]; hMem
0x18004f7f0  xor     r15d, r15d
0x18004f7f3  test    rcx, rcx
0x18004f7f6  jz      short loc_18004F7FE
0x18004f7f8  call    cs:__imp_LocalFree
0x18004f7fe  mov     r9, r12; void *
0x18004f801  mov     rdx, rsi; unsigned __int16 *
0x18004f804  call    ?SetFileSecurityW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBGKPEAX@Z; RdVhd::Uvhd::CDirectoryHelper::SetFileSecurityW(ushort const *,ulong,void *)
0x18004f809  test    eax, eax
0x18004f80b  jnz     loc_18004F8EF
0x18004f811  call    cs:__imp_GetLastError
0x18004f817  mov     ebx, eax
0x18004f819  test    eax, eax
0x18004f81b  jz      short loc_18004F83A
0x18004f81d  test    edi, eax
0x18004f81f  jnz     short loc_18004F83A
0x18004f821  test    eax, eax
0x18004f823  jle     short loc_18004F82E
0x18004f825  movzx   ebx, ax
0x18004f828  or      ebx, 80070000h
0x18004f82e  and     ebx, 0D006FFFFh
0x18004f834  or      ebx, 50060000h
0x18004f83a  test    ebx, ebx
0x18004f83c  jns     loc_18004F8EF
0x18004f842  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f849  lea     rdi, WPP_GLOBAL_Control
0x18004f850  cmp     rcx, rdi
0x18004f853  jz      loc_18004F8EF
0x18004f859  test    byte ptr [rcx+1Ch], 4
0x18004f85d  jz      loc_18004F8EF
0x18004f863  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
