# CRegAccount::GrantAccessToMetabasePath(ushort const *,IMSAdminBaseW *,void *,ulong)

- ea: `0x180024d70`
- end: `0x1800251a5`
- name: `?GrantAccessToMetabasePath@CRegAccount@@CAJPEBGPEAUIMSAdminBaseW@@PEAXK@Z`
- size: `1077`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IMSAdminBaseW *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180024c9c`

## callees

- `0x180021730`
- `0x180023a58`
- `0x180024d70`
- `0x18003abe4`
- `0x18003acd4`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x180065b60`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180025089`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180025089`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180024f1e`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180024f1e`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024fe7`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002506e`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024fe7`
- `ADVAPI32!MakeAbsoluteSD` at `0x18002506e`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800250ad`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800250d1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800250ad`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800250d1`

## string_xrefs

- `0x180024db6`: `Granting access to metabase path: `
- `0x18002512e`: `Granting access to metabase path: `
- `0x180024dc8`: `GrantAccessToMetabasePath`
- `0x18002513d`: `GrantAccessToMetabasePath`

## pseudocode

```c
__int64 __fastcall CRegAccount::GrantAccessToMetabasePath(
        const unsigned __int16 *a1,
        struct IMSAdminBaseW *a2,
        void *a3,
        unsigned int a4)
{
  int *v7; // rdi
  void *v8; // rsi
  unsigned int DoesAccessExist; // ebx
  struct IMSAdminBaseWVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IMSAdminBaseW *, METADATA_HANDLE, LPCWSTR, PMETADATA_RECORD, DWORD *); // rax
  unsigned int v12; // eax
  DWORD v13; // eax
  struct IMSAdminBaseWVtbl *v14; // rax
  HRESULT (__stdcall *v15)(IMSAdminBaseW *, METADATA_HANDLE, LPCWSTR, PMETADATA_RECORD, DWORD *); // rax
  unsigned int LastWin32Error; // eax
  DWORD v17; // r9d
  int v18; // r15d
  char *v19; // rax
  int *v20; // rax
  struct IMSAdminBaseWVtbl *v21; // rax
  HRESULT (__stdcall *SetData)(IMSAdminBaseW *, METADATA_HANDLE, LPCWSTR, PMETADATA_RECORD); // rax
  unsigned int v24; // [rsp+60h] [rbp-39h] BYREF
  WINBOOL bDaclPresent; // [rsp+64h] [rbp-35h] BYREF
  DWORD dwOwnerSize; // [rsp+68h] [rbp-31h] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp-2Dh] BYREF
  DWORD dwDaclSize; // [rsp+70h] [rbp-29h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+74h] [rbp-25h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+78h] [rbp-21h] BYREF
  __int64 v31; // [rsp+80h] [rbp-19h] BYREF
  int v32; // [rsp+88h] [rbp-11h]
  int v33; // [rsp+8Ch] [rbp-Dh]
  __int64 v34; // [rsp+90h] [rbp-9h]
  int *v35; // [rsp+98h] [rbp-1h]
  __int64 v36; // [rsp+A0h] [rbp+7h]
  int v37; // [rsp+A8h] [rbp+Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+ACh] [rbp+13h] BYREF
  PACL pDacl; // [rsp+B0h] [rbp+17h] BYREF
  PACL v40; // [rsp+B8h] [rbp+1Fh] BYREF
  DWORD dwBufferLength; // [rsp+108h] [rbp+6Fh] BYREF
  void *v42; // [rsp+110h] [rbp+77h] BYREF

  v42 = a3;
  v24 = 0;
  dwBufferLength = 0;
  v40 = 0;
  pDacl = 0;
  v37 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  v7 = 0;
  dwPrimaryGroupSize = 0;
  dwOwnerSize = 0;
  v8 = 0;
  dwSaclSize = 0;
  dwDaclSize = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  CSetupLogging::Log(1, "GrantAccessToMetabasePath", 0, "Granting access to metabase path: ", a1);
  DoesAccessExist = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))a2->lpVtbl->OpenKey)(
                      a2,
                      0,
                      a1,
                      3,
                      60000,
                      &v24);
  if ( !DoesAccessExist )
  {
    v35 = &v37;
    lpVtbl = a2->lpVtbl;
    v34 = 0;
    v36 = 0;
    GetData = lpVtbl->GetData;
    v31 = 6027;
    v32 = 1;
    v33 = 3;
    v12 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const wchar_t *, __int64 *, DWORD *))GetData)(
            a2,
            v24,
            L"/",
            &v31,
            &dwBufferLength);
    DoesAccessExist = v12;
    if ( v12 == -2147024774 || !v12 )
    {
      v13 = dwBufferLength;
      if ( dwBufferLength || DoesAccessExist )
      {
        dwBufferLength += 100;
        v7 = (int *)MemAllocClear(v13 + 100);
        if ( !v7 )
        {
LABEL_7:
          DoesAccessExist = -2147024882;
          goto LABEL_23;
        }
        v34 = dwBufferLength;
        v14 = a2->lpVtbl;
        v36 = 0;
        v15 = v14->GetData;
        v31 = 6027;
        v32 = 1;
        v33 = 3;
        v35 = v7;
        DoesAccessExist = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const wchar_t *, __int64 *, DWORD *))v15)(
                            a2,
                            v24,
                            L"/",
                            &v31,
                            &dwBufferLength);
        if ( !DoesAccessExist )
        {
          if ( !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
            goto LABEL_10;
          if ( !bDaclPresent || pDacl )
          {
            DoesAccessExist = CRegAccount::DoesAccessExist(pDacl, &v42, 1, a4, &bDaclPresent);
            if ( !DoesAccessExist && !bDaclPresent )
            {
              v17 = a4;
              v18 = DoesAccessExist + 1;
              DoesAccessExist = CRegAccount::AddAccess(&pDacl, &v42, DoesAccessExist + 1, v17, 0, 0, &v40);
              if ( !DoesAccessExist )
              {
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
                v19 = (char *)MemAllocClear(
                                dwPrimaryGroupSize
                              + dwOwnerSize
                              + dwSaclSize
                              + dwAbsoluteSecurityDescriptorSize
                              + dwDaclSize);
                v8 = v19;
                if ( !v19 )
                  goto LABEL_7;
                if ( MakeAbsoluteSD(
                       v7,
                       v19,
                       &dwAbsoluteSecurityDescriptorSize,
                       (PACL)&v19[dwAbsoluteSecurityDescriptorSize],
                       &dwDaclSize,
                       (PACL)&v19[dwAbsoluteSecurityDescriptorSize + dwDaclSize],
                       &dwSaclSize,
                       &v19[dwAbsoluteSecurityDescriptorSize + dwDaclSize + dwSaclSize],
                       &dwOwnerSize,
                       &v19[dwAbsoluteSecurityDescriptorSize + dwDaclSize + dwSaclSize + dwOwnerSize],
                       &dwPrimaryGroupSize)
                  && SetSecurityDescriptorDacl(v8, v18, v40, 0) )
                {
                  MemFree(v7);
                  dwBufferLength = 0;
                  MakeSelfRelativeSD(v8, v7, &dwBufferLength);
                  v20 = (int *)MemAllocClear(dwBufferLength);
                  v7 = v20;
                  if ( !v20 )
                    goto LABEL_7;
                  if ( MakeSelfRelativeSD(v8, v20, &dwBufferLength) )
                  {
                    LODWORD(v34) = dwBufferLength;
                    v21 = a2->lpVtbl;
                    v31 = 0xD0000178BLL;
                    v32 = v18;
                    SetData = v21->SetData;
                    v33 = 3;
                    v35 = v7;
                    LODWORD(v36) = 0;
                    LastWin32Error = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const wchar_t *, __int64 *))SetData)(
                                       a2,
                                       v24,
                                       L"/",
                                       &v31);
                    goto LABEL_22;
                  }
                }
LABEL_10:
                LastWin32Error = GetLastWin32Error();
LABEL_22:
                DoesAccessExist = LastWin32Error;
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
  CSetupLogging::Log(
    DoesAccessExist,
    "GrantAccessToMetabasePath",
    0,
    "Granting access to metabase path: ",
    a1,
    -2146646015);
  if ( v8 )
    MemFree(v8);
  if ( v7 )
    MemFree(v7);
  MemFree(v40);
  if ( v24 )
    ((void (__fastcall *)(struct IMSAdminBaseW *))a2->lpVtbl->CloseKey)(a2);
  return DoesAccessExist;
}

```

## disassembly

```asm
0x180024d70  mov     [rsp-8+arg_0], rbx
0x180024d75  mov     [rsp-8+arg_10], r8
0x180024d7a  push    rbp
0x180024d7b  push    rsi
0x180024d7c  push    rdi
0x180024d7d  push    r12
0x180024d7f  push    r13
0x180024d81  push    r14
0x180024d83  push    r15
0x180024d85  lea     rbp, [rsp-27h]
0x180024d8a  sub     rsp, 0C0h
0x180024d91  xor     r13d, r13d
0x180024d94  mov     [rsp+0F0h+lpdwDaclSize], rcx; unsigned __int16 *
0x180024d99  mov     r15d, r9d
0x180024d9c  mov     [rbp+57h+var_90], r13d
0x180024da0  mov     r14, rdx
0x180024da3  mov     [rbp+57h+dwBufferLength], r13d
0x180024da7  mov     r12, rcx
0x180024daa  mov     [rbp+57h+var_38], r13
0x180024dae  lea     ecx, [r13+1]; int
0x180024db2  mov     [rbp+57h+pDacl], r13
0x180024db6  lea     r9, aGrantingAccess; "Granting access to metabase path: "
0x180024dbd  mov     [rbp+57h+var_48], r13d
0x180024dc1  xor     r8d, r8d; unsigned int
0x180024dc4  mov     [rbp+57h+bDaclPresent], r13d
0x180024dc8  lea     rdx, aGrantaccesstom_0; "GrantAccessToMetabasePath"
0x180024dcf  mov     [rbp+57h+bDaclDefaulted], r13d
0x180024dd3  mov     edi, r13d
0x180024dd6  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x180024dda  mov     [rbp+57h+dwOwnerSize], r13d
0x180024dde  mov     esi, r13d
0x180024de1  mov     [rbp+57h+dwSaclSize], r13d
0x180024de5  mov     [rbp+57h+dwDaclSize], r13d
0x180024de9  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x180024ded  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180024df2  mov     rax, [r14]
0x180024df5  lea     rcx, [rbp+57h+var_90]
0x180024df9  mov     [rsp+0F0h+pSacl], rcx
0x180024dfe  lea     r9d, [r13+3]
0x180024e02  mov     r8, r12
0x180024e05  mov     dword ptr [rsp+0F0h+lpdwDaclSize], 0EA60h
0x180024e0d  xor     edx, edx
0x180024e0f  mov     rcx, r14
0x180024e12  mov     rax, [rax+88h]
0x180024e19  call    cs:__guard_dispatch_icall_fptr
0x180024e1f  mov     ebx, eax
0x180024e21  test    eax, eax
0x180024e23  jnz     loc_180025126
0x180024e29  mov     edx, [rbp+57h+var_90]
0x180024e2c  lea     rax, [rbp+57h+var_48]
0x180024e30  mov     [rbp+57h+var_58], rax
0x180024e34  lea     rcx, [rbp+57h+dwBufferLength]
0x180024e38  mov     rax, [r14]
0x180024e3b  lea     r9, [rbp+57h+var_70]
0x180024e3f  mov     [rsp+0F0h+lpdwDaclSize], rcx
0x180024e44  lea     r8, asc_18006AB9C; "/"
0x180024e4b  mov     rcx, r14
0x180024e4e  mov     [rbp+57h+var_60], r13
0x180024e52  mov     [rbp+57h+var_50], r13
0x180024e56  mov     rax, [rax+50h]
0x180024e5a  mov     [rbp+57h+var_70], 178Bh
0x180024e62  mov     [rbp+57h+var_68], 1
0x180024e69  mov     [rbp+57h+var_64], 3
0x180024e70  call    cs:__guard_dispatch_icall_fptr
0x180024e76  mov     ebx, eax
0x180024e78  cmp     eax, 8007007Ah
0x180024e7d  jz      short loc_180024E87
0x180024e7f  test    eax, eax
0x180024e81  jnz     loc_180025126
0x180024e87  mov     eax, [rbp+57h+dwBufferLength]
0x180024e8a  cmp     eax, 1
0x180024e8d  jnb     short loc_180024E97
0x180024e8f  test    ebx, ebx
0x180024e91  jz      loc_180025126
0x180024e97  add     eax, 64h ; 'd'
0x180024e9a  mov     ecx, eax; unsigned __int64
0x180024e9c  mov     [rbp+57h+dwBufferLength], eax
0x180024e9f  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180024ea4  mov     rdi, rax
0x180024ea7  test    rax, rax
0x180024eaa  jnz     short loc_180024EB6
0x180024eac  mov     ebx, 8007000Eh
0x180024eb1  jmp     loc_180025126
0x180024eb6  mov     eax, [rbp+57h+dwBufferLength]
0x180024eb9  lea     rcx, [rbp+57h+dwBufferLength]
0x180024ebd  mov     edx, [rbp+57h+var_90]
0x180024ec0  lea     r9, [rbp+57h+var_70]
0x180024ec4  mov     dword ptr [rbp+57h+var_60], eax
0x180024ec7  lea     r8, asc_18006AB9C; "/"
0x180024ece  mov     rax, [r14]
0x180024ed1  mov     [rsp+0F0h+lpdwDaclSize], rcx
0x180024ed6  mov     rcx, r14
0x180024ed9  mov     dword ptr [rbp+57h+var_60+4], r13d
0x180024edd  mov     [rbp+57h+var_50], r13
0x180024ee1  mov     rax, [rax+50h]
0x180024ee5  mov     [rbp+57h+var_70], 178Bh
0x180024eed  mov     [rbp+57h+var_68], 1
0x180024ef4  mov     [rbp+57h+var_64], 3
0x180024efb  mov     [rbp+57h+var_58], rdi
0x180024eff  call    cs:__guard_dispatch_icall_fptr
0x180024f05  mov     ebx, eax
0x180024f07  test    eax, eax
0x180024f09  jnz     loc_180025126
0x180024f0f  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180024f13  mov     rcx, rdi; pSecurityDescriptor
0x180024f16  lea     r8, [rbp+57h+pDacl]; pDacl
0x180024f1a  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180024f1e  call    cs:__imp_GetSecurityDescriptorDacl
0x180024f24  test    eax, eax
0x180024f26  jnz     short loc_180024F32
0x180024f28  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180024f2d  jmp     loc_180025124
0x180024f32  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180024f36  cmp     [rbp+57h+bDaclPresent], r13d
0x180024f3a  jz      short loc_180024F45
0x180024f3c  test    rcx, rcx
0x180024f3f  jz      loc_180025126
0x180024f45  lea     rax, [rbp+57h+bDaclPresent]
0x180024f49  mov     r9d, r15d; unsigned int
0x180024f4c  mov     r8d, 1; int
0x180024f52  mov     [rsp+0F0h+lpdwDaclSize], rax; int *
0x180024f57  lea     rdx, [rbp+57h+arg_10]; void **
0x180024f5b  call    ?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z; CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)
0x180024f60  mov     ebx, eax
0x180024f62  test    eax, eax
0x180024f64  jnz     loc_180025126
0x180024f6a  cmp     [rbp+57h+bDaclPresent], r13d
0x180024f6e  jnz     loc_180025126
0x180024f74  lea     rax, [rbp+57h+var_38]
0x180024f78  mov     r9d, r15d; unsigned int
0x180024f7b  mov     [rsp+0F0h+lpdwSaclSize], rax; struct _ACL **
0x180024f80  lea     r15d, [rbx+1]
0x180024f84  mov     byte ptr [rsp+0F0h+pSacl], r13b; char
0x180024f89  lea     rdx, [rbp+57h+arg_10]; void **
0x180024f8d  mov     r8d, r15d; int
0x180024f90  mov     [rsp+0F0h+lpdwDaclSize], r13; int *
0x180024f95  lea     rcx, [rbp+57h+pDacl]; struct _ACL **
0x180024f99  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)
0x180024f9e  mov     ebx, eax
0x180024fa0  test    eax, eax
0x180024fa2  jnz     loc_180025126
0x180024fa8  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180024fac  xor     r9d, r9d; pDacl
0x180024faf  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180024fb4  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180024fb8  mov     [rsp+0F0h+pPrimaryGroup], r13; pPrimaryGroup
0x180024fbd  lea     rax, [rbp+57h+dwOwnerSize]
0x180024fc1  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180024fc6  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180024fc8  mov     [rsp+0F0h+pOwner], r13; pOwner
0x180024fcd  lea     rax, [rbp+57h+dwSaclSize]
0x180024fd1  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180024fd6  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x180024fd9  lea     rax, [rbp+57h+dwDaclSize]
0x180024fdd  mov     [rsp+0F0h+pSacl], r13; pSacl
0x180024fe2  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x180024fe7  call    cs:__imp_MakeAbsoluteSD
0x180024fed  mov     ecx, [rbp+57h+dwDaclSize]
0x180024ff0  add     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180024ff3  add     ecx, [rbp+57h+dwSaclSize]
0x180024ff6  add     ecx, [rbp+57h+dwOwnerSize]
0x180024ff9  add     ecx, [rbp+57h+dwPrimaryGroupSize]; unsigned __int64
0x180024ffc  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180025001  mov     rsi, rax
0x180025004  test    rax, rax
0x180025007  jz      loc_180024EAC
0x18002500d  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180025010  mov     edx, [rbp+57h+dwDaclSize]
0x180025013  add     edx, ecx
0x180025015  mov     r8d, edx
0x180025018  lea     r9, [rax+rcx]; pDacl
0x18002501c  add     r8, rax
0x18002501f  mov     ecx, [rbp+57h+dwSaclSize]
0x180025022  add     ecx, edx
0x180025024  mov     edx, ecx
0x180025026  add     rdx, rax
0x180025029  mov     eax, [rbp+57h+dwOwnerSize]
0x18002502c  add     eax, ecx
0x18002502e  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x180025032  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x180025037  add     rax, rsi
0x18002503a  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x18002503f  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x180025042  lea     rax, [rbp+57h+dwOwnerSize]
0x180025046  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18002504b  lea     rax, [rbp+57h+dwSaclSize]
0x18002504f  mov     [rsp+0F0h+pOwner], rdx; pOwner
0x180025054  mov     rdx, rsi; pAbsoluteSecurityDescriptor
0x180025057  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18002505c  lea     rax, [rbp+57h+dwDaclSize]
0x180025060  mov     [rsp+0F0h+pSacl], r8; pSacl
0x180025065  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180025069  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x18002506e  call    cs:__imp_MakeAbsoluteSD
0x180025074  test    eax, eax
0x180025076  jz      loc_180024F28
0x18002507c  mov     r8, [rbp+57h+var_38]; pDacl
0x180025080  xor     r9d, r9d; bDaclDefaulted
0x180025083  mov     edx, r15d; bDaclPresent
0x180025086  mov     rcx, rsi; pSecurityDescriptor
0x180025089  call    cs:__imp_SetSecurityDescriptorDacl
0x18002508f  test    eax, eax
0x180025091  jz      loc_180024F28
0x180025097  mov     rcx, rdi; lpMem
0x18002509a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002509f  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800250a3  mov     [rbp+57h+dwBufferLength], r13d
0x1800250a7  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x1800250aa  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x1800250ad  call    cs:__imp_MakeSelfRelativeSD
0x1800250b3  mov     ecx, [rbp+57h+dwBufferLength]; unsigned __int64
0x1800250b6  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800250bb  mov     rdi, rax
0x1800250be  test    rax, rax
0x1800250c1  jz      loc_180024EAC
0x1800250c7  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800250cb  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800250ce  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x1800250d1  call    cs:__imp_MakeSelfRelativeSD
0x1800250d7  test    eax, eax
0x1800250d9  jz      loc_180024F28
0x1800250df  mov     eax, [rbp+57h+dwBufferLength]
0x1800250e2  lea     r9, [rbp+57h+var_70]
0x1800250e6  mov     edx, [rbp+57h+var_90]
0x1800250e9  lea     r8, asc_18006AB9C; "/"
0x1800250f0  mov     dword ptr [rbp+57h+var_60], eax
0x1800250f3  mov     rcx, r14
0x1800250f6  mov     rax, [r14]
0x1800250f9  mov     dword ptr [rbp+57h+var_70], 178Bh
0x180025100  mov     dword ptr [rbp+57h+var_70+4], 0Dh
0x180025107  mov     [rbp+57h+var_68], r15d
0x18002510b  mov     rax, [rax+48h]
0x18002510f  mov     [rbp+57h+var_64], 3
0x180025116  mov     [rbp+57h+var_58], rdi
0x18002511a  mov     dword ptr [rbp+57h+var_50], r13d
0x18002511e  call    cs:__guard_dispatch_icall_fptr
0x180025124  mov     ebx, eax
0x180025126  mov     dword ptr [rsp+0F0h+pSacl], 800CC801h; int
0x18002512e  lea     r9, aGrantingAccess; "Granting access to metabase path: "
0x180025135  xor     r8d, r8d; unsigned int
0x180025138  mov     [rsp+0F0h+lpdwDaclSize], r12; unsigned __int16 *
0x18002513d  lea     rdx, aGrantaccesstom_0; "GrantAccessToMetabasePath"
0x180025144  mov     ecx, ebx; int
0x180025146  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBGJ@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *,long)
0x18002514b  test    rsi, rsi
0x18002514e  jz      short loc_180025158
0x180025150  mov     rcx, rsi; lpMem
0x180025153  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180025158  test    rdi, rdi
0x18002515b  jz      short loc_180025165
0x18002515d  mov     rcx, rdi; lpMem
0x180025160  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180025165  mov     rcx, [rbp+57h+var_38]; lpMem
0x180025169  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002516e  mov     edx, [rbp+57h+var_90]
0x180025171  test    edx, edx
0x180025173  jz      short loc_180025188
0x180025175  mov     rax, [r14]
0x180025178  mov     rcx, r14
0x18002517b  mov     rax, [rax+90h]
0x180025182  call    cs:__guard_dispatch_icall_fptr
0x180025188  mov     eax, ebx
0x18002518a  mov     rbx, [rsp+0F0h+arg_0]
0x180025192  add     rsp, 0C0h
0x180025199  pop     r15
0x18002519b  pop     r14
0x18002519d  pop     r13
0x18002519f  pop     r12
0x1800251a1  pop     rdi
0x1800251a2  pop     rsi
0x1800251a3  pop     rbp
0x1800251a4  retn
```
