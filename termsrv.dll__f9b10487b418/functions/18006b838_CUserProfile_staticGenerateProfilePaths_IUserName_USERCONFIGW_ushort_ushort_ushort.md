# CUserProfile::staticGenerateProfilePaths(IUserName *,_USERCONFIGW *,ushort * *,ushort * *,ushort * *)

- ea: `0x18006b838`
- end: `0x18006bb47`
- name: `?staticGenerateProfilePaths@CUserProfile@@SAJPEAUIUserName@@PEAU_USERCONFIGW@@PEAPEAG22@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct IUserName *, struct _USERCONFIGW *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18005b650`

## callees

- `0x18000a210`
- `0x18003269c`
- `0x18006a9d0`
- `0x18006ad58`
- `0x18006ae04`
- `0x18006aee8`
- `0x18006b1cc`
- `0x18006b308`
- `0x18006b3d4`
- `0x18006b4c0`
- `0x18006b838`
- `0x1800b1570`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ba91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006baa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bae4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006baf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ba91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006baa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bae4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006baf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb00`

## string_xrefs

- `0x18006b8a9`: `IsAppServerInstalled failed: 0x%x in %s`
- `0x18006b8b3`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006b8e5`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006b988`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006b9df`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006ba0b`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006b92c`: `AssembleThePath(wszProfilePath) failed: 0x%x in %s`
- `0x18006b947`: `CopyThePath(wszPolicyProfilePath) failed: 0x%x in %s`
- `0x18006b969`: `CopyThePath(wszProfilePath) failed: 0x%x in %s`
- `0x18006b9d5`: `AssembleThePath(wszHomeDir) failed: 0x%x in %s`
- `0x18006ba15`: `CopyHomeDrive(wszHomeDirDrive) failed: 0x%x in %s`
- `0x18006ba49`: `CopyThePath(wszHomeDir) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserProfile::staticGenerateProfilePaths(
        struct IUserName *a1,
        struct _USERCONFIGW *a2,
        HLOCAL *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // r12
  unsigned __int16 *v7; // r15
  HLOCAL v8; // rdi
  HLOCAL v9; // rsi
  int IsAppServerInstalled; // eax
  int HomeDrectory; // ebx
  int PolicyProfile; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int PolicyHomeDir; // eax
  struct IUserName *v18; // r13
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+20h] [rbp-40h] BYREF
  int v24; // [rsp+24h] [rbp-3Ch] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-38h] BYREF
  HLOCAL v26; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL v27; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-10h] BYREF

  *a3 = 0;
  v5 = 0;
  *a4 = 0;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  *a5 = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v30 = 0;
  v27 = 0;
  hMem = 0;
  v26 = 0;
  v24 = 0;
  v23 = 0;
  IsAppServerInstalled = CSLQuery::IsAppServerInstalled(&v23);
  HomeDrectory = IsAppServerInstalled;
  if ( IsAppServerInstalled < 0 )
  {
    _DbgPrintMessage(
      8,
      "IsAppServerInstalled failed: 0x%x in %s",
      (unsigned int)IsAppServerInstalled,
      "CUserProfile::staticGenerateProfilePaths");
    goto LABEL_34;
  }
  if ( !v23 )
    goto LABEL_40;
  PolicyProfile = CUserProfile::GetPolicyProfile(&v28, &v24);
  HomeDrectory = PolicyProfile;
  if ( PolicyProfile < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetPolicyProfile failed: 0x%x in %s",
      PolicyProfile,
      "CUserProfile::staticGenerateProfilePaths");
    v5 = v28;
LABEL_34:
    CUserProfile::ReportProfileFailed(a1);
    if ( v27 )
      LocalFree(v27);
    if ( v8 )
      LocalFree(v8);
    if ( v9 )
      LocalFree(v9);
    goto LABEL_40;
  }
  v5 = v28;
  if ( PolicyProfile )
  {
    v16 = CUserProfile::CopyThePath((const unsigned __int16 *)a2 + 750, (unsigned __int16 **)&v27);
    HomeDrectory = v16;
    if ( v16 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CopyThePath(wszProfilePath) failed: 0x%x in %s",
        (unsigned int)v16,
        "CUserProfile::staticGenerateProfilePaths");
      goto LABEL_34;
    }
  }
  else if ( v24 )
  {
    v15 = CUserProfile::CopyThePath(v28, (unsigned __int16 **)&v27);
    HomeDrectory = v15;
    if ( v15 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CopyThePath(wszPolicyProfilePath) failed: 0x%x in %s",
        (unsigned int)v15,
        "CUserProfile::staticGenerateProfilePaths");
      goto LABEL_34;
    }
  }
  else
  {
    v14 = CUserProfile::AssembleThePath(v28, a1, (unsigned __int16 **)&v27);
    HomeDrectory = v14;
    if ( v14 < 0 )
    {
      _DbgPrintMessage(
        8,
        "AssembleThePath(wszProfilePath) failed: 0x%x in %s",
        (unsigned int)v14,
        "CUserProfile::staticGenerateProfilePaths");
      goto LABEL_34;
    }
  }
  PolicyHomeDir = CUserProfile::GetPolicyHomeDir(&v29, &v30);
  HomeDrectory = PolicyHomeDir;
  if ( PolicyHomeDir < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetPolicyHomeDir failed: 0x%x in %s",
      PolicyHomeDir,
      "CUserProfile::staticGenerateProfilePaths");
    v6 = v29;
    v7 = v30;
    goto LABEL_34;
  }
  v6 = v29;
  v7 = v30;
  if ( PolicyHomeDir )
  {
    v21 = CUserProfile::CopyThePath((const unsigned __int16 *)a2 + 1007, (unsigned __int16 **)&hMem);
    HomeDrectory = v21;
    if ( v21 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CopyThePath(wszHomeDir) failed: 0x%x in %s",
        (unsigned int)v21,
        "CUserProfile::staticGenerateProfilePaths");
      goto LABEL_20;
    }
    v20 = CUserProfile::CopyHomeDrive((const unsigned __int16 *)a2 + 1264, (unsigned __int16 **)&v26);
    HomeDrectory = v20;
    if ( v20 < 0 )
    {
LABEL_22:
      _DbgPrintMessage(
        8,
        "CopyHomeDrive(wszHomeDirDrive) failed: 0x%x in %s",
        v20,
        "CUserProfile::staticGenerateProfilePaths");
      v8 = hMem;
      v9 = v26;
      goto LABEL_34;
    }
    v18 = a1;
  }
  else
  {
    v18 = a1;
    v19 = CUserProfile::AssembleThePath(v29, a1, (unsigned __int16 **)&hMem);
    HomeDrectory = v19;
    if ( v19 < 0 )
    {
      _DbgPrintMessage(
        8,
        "AssembleThePath(wszHomeDir) failed: 0x%x in %s",
        (unsigned int)v19,
        "CUserProfile::staticGenerateProfilePaths");
LABEL_20:
      v8 = hMem;
      goto LABEL_34;
    }
    v20 = CUserProfile::CopyHomeDrive(v7, (unsigned __int16 **)&v26);
    HomeDrectory = v20;
    if ( v20 < 0 )
      goto LABEL_22;
  }
  v8 = hMem;
  if ( hMem && (HomeDrectory = CUserProfile::CreateHomeDrectory(v18, (LPWSTR)hMem), HomeDrectory < 0) )
  {
    CUserProfile::ReportHomeDirectoryFailed(v18);
    LocalFree(v8);
    v9 = v26;
    v8 = 0;
    if ( v26 )
    {
      LocalFree(v26);
      v9 = 0;
    }
    HomeDrectory = 0;
  }
  else
  {
    v9 = v26;
  }
  *a3 = v27;
  *a4 = (unsigned __int16 *)v8;
  *a5 = (unsigned __int16 *)v9;
  if ( HomeDrectory < 0 )
    goto LABEL_34;
LABEL_40:
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
  return (unsigned int)HomeDrectory;
}

```

## disassembly

```asm
0x18006b838  mov     rax, rsp
0x18006b83b  mov     [rax+10h], rbx
0x18006b83f  mov     [rax+20h], r9
0x18006b843  mov     [rax+18h], r8
0x18006b847  mov     [rax+8], rcx
0x18006b84b  push    rbp
0x18006b84c  push    rsi
0x18006b84d  push    rdi
0x18006b84e  push    r12
0x18006b850  push    r13
0x18006b852  push    r14
0x18006b854  push    r15
0x18006b856  mov     rbp, rsp
0x18006b859  sub     rsp, 60h
0x18006b85d  mov     rax, [rbp+arg_20]
0x18006b861  xor     ecx, ecx
0x18006b863  mov     [r8], rcx
0x18006b866  mov     r14d, ecx
0x18006b869  mov     [r9], rcx
0x18006b86c  mov     r12d, ecx
0x18006b86f  mov     [rbp+var_20], rcx
0x18006b873  mov     r15d, ecx
0x18006b876  mov     [rax], rcx
0x18006b879  mov     edi, ecx
0x18006b87b  mov     [rbp+var_18], rcx
0x18006b87f  mov     esi, ecx
0x18006b881  mov     [rbp+var_10], rcx
0x18006b885  mov     r13, rdx
0x18006b888  mov     [rbp+var_28], rcx
0x18006b88c  mov     [rbp+hMem], rcx
0x18006b890  mov     [rbp+var_30], rcx
0x18006b894  mov     [rbp+var_3C], ecx
0x18006b897  mov     [rbp+var_40], ecx
0x18006b89a  lea     rcx, [rbp+var_40]; int *
0x18006b89e  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18006b8a3  mov     ebx, eax
0x18006b8a5  test    eax, eax
0x18006b8a7  jns     short loc_18006B8C9
0x18006b8a9  lea     rdx, aIsappserverins_0; "IsAppServerInstalled failed: 0x%x in %s"
0x18006b8b0  mov     r8d, eax
0x18006b8b3  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006b8ba  mov     ecx, 8; int
0x18006b8bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b8c4  jmp     loc_18006BAD2
0x18006b8c9  cmp     [rbp+var_40], esi
0x18006b8cc  jz      loc_18006BB06
0x18006b8d2  lea     rdx, [rbp+var_3C]; int *
0x18006b8d6  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x18006b8da  call    ?GetPolicyProfile@CUserProfile@@CAJPEAPEAGPEAH@Z; CUserProfile::GetPolicyProfile(ushort * *,int *)
0x18006b8df  mov     ebx, eax
0x18006b8e1  test    eax, eax
0x18006b8e3  jns     short loc_18006B909
0x18006b8e5  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006b8ec  mov     r8d, eax
0x18006b8ef  lea     rdx, aGetpolicyprofi; "GetPolicyProfile failed: 0x%x in %s"
0x18006b8f6  mov     ecx, 8; int
0x18006b8fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b900  mov     r14, [rbp+var_20]
0x18006b904  jmp     loc_18006BAD2
0x18006b909  mov     r14, [rbp+var_20]
0x18006b90d  test    eax, eax
0x18006b90f  jnz     short loc_18006B953
0x18006b911  mov     rcx, r14; unsigned __int16 *
0x18006b914  cmp     [rbp+var_3C], esi
0x18006b917  jnz     short loc_18006B938
0x18006b919  mov     rdx, [rbp+arg_0]; struct IUserName *
0x18006b91d  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18006b921  call    ?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z; CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)
0x18006b926  mov     ebx, eax
0x18006b928  test    eax, eax
0x18006b92a  jns     short loc_18006B975
0x18006b92c  lea     rdx, aAssemblethepat_0; "AssembleThePath(wszProfilePath) failed:"...
0x18006b933  jmp     loc_18006B8B0
0x18006b938  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18006b93c  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006b941  mov     ebx, eax
0x18006b943  test    eax, eax
0x18006b945  jns     short loc_18006B975
0x18006b947  lea     rdx, aCopythepathWsz_0; "CopyThePath(wszPolicyProfilePath) faile"...
0x18006b94e  jmp     loc_18006B8B0
0x18006b953  lea     rcx, [r13+5DCh]; unsigned __int16 *
0x18006b95a  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18006b95e  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006b963  mov     ebx, eax
0x18006b965  test    eax, eax
0x18006b967  jns     short loc_18006B975
0x18006b969  lea     rdx, aCopythepathWsz; "CopyThePath(wszProfilePath) failed: 0x%"...
0x18006b970  jmp     loc_18006B8B0
0x18006b975  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18006b979  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x18006b97d  call    ?GetPolicyHomeDir@CUserProfile@@CAJPEAPEAG0@Z; CUserProfile::GetPolicyHomeDir(ushort * *,ushort * *)
0x18006b982  mov     ebx, eax
0x18006b984  test    eax, eax
0x18006b986  jns     short loc_18006B9B0
0x18006b988  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006b98f  mov     r8d, eax
0x18006b992  lea     rdx, aGetpolicyhomed; "GetPolicyHomeDir failed: 0x%x in %s"
0x18006b999  mov     ecx, 8; int
0x18006b99e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b9a3  mov     r12, [rbp+var_18]
0x18006b9a7  mov     r15, [rbp+var_10]
0x18006b9ab  jmp     loc_18006BAD2
0x18006b9b0  mov     r12, [rbp+var_18]
0x18006b9b4  mov     r15, [rbp+var_10]
0x18006b9b8  test    eax, eax
0x18006b9ba  jnz     short loc_18006BA33
0x18006b9bc  mov     r13, [rbp+arg_0]
0x18006b9c0  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18006b9c4  mov     rdx, r13; struct IUserName *
0x18006b9c7  mov     rcx, r12; unsigned __int16 *
0x18006b9ca  call    ?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z; CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)
0x18006b9cf  mov     ebx, eax
0x18006b9d1  test    eax, eax
0x18006b9d3  jns     short loc_18006B9F9
0x18006b9d5  lea     rdx, aAssemblethepat; "AssembleThePath(wszHomeDir) failed: 0x%"...
0x18006b9dc  mov     r8d, eax
0x18006b9df  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006b9e6  mov     ecx, 8; int
0x18006b9eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b9f0  mov     rdi, [rbp+hMem]
0x18006b9f4  jmp     loc_18006BAD2
0x18006b9f9  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18006b9fd  mov     rcx, r15; unsigned __int16 *
0x18006ba00  call    ?CopyHomeDrive@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyHomeDrive(ushort const *,ushort * *)
0x18006ba05  mov     ebx, eax
0x18006ba07  test    eax, eax
0x18006ba09  jns     short loc_18006BA6C
0x18006ba0b  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006ba12  mov     r8d, eax
0x18006ba15  lea     rdx, aCopyhomedriveW; "CopyHomeDrive(wszHomeDirDrive) failed: "...
0x18006ba1c  mov     ecx, 8; int
0x18006ba21  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ba26  mov     rdi, [rbp+hMem]
0x18006ba2a  mov     rsi, [rbp+var_30]
0x18006ba2e  jmp     loc_18006BAD2
0x18006ba33  lea     rcx, [r13+7DEh]; unsigned __int16 *
0x18006ba3a  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18006ba3e  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006ba43  mov     ebx, eax
0x18006ba45  test    eax, eax
0x18006ba47  jns     short loc_18006BA52
0x18006ba49  lea     rdx, aCopythepathWsz_1; "CopyThePath(wszHomeDir) failed: 0x%x in"...
0x18006ba50  jmp     short loc_18006B9DC
0x18006ba52  lea     rcx, [r13+9E0h]; unsigned __int16 *
0x18006ba59  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18006ba5d  call    ?CopyHomeDrive@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyHomeDrive(ushort const *,ushort * *)
0x18006ba62  mov     ebx, eax
0x18006ba64  test    eax, eax
0x18006ba66  js      short loc_18006BA0B
0x18006ba68  mov     r13, [rbp+arg_0]
0x18006ba6c  mov     rdi, [rbp+hMem]
0x18006ba70  test    rdi, rdi
0x18006ba73  jz      short loc_18006BAB1
0x18006ba75  mov     rdx, rdi; pObjectName
0x18006ba78  mov     rcx, r13; struct IUserName *
0x18006ba7b  call    ?CreateHomeDrectory@CUserProfile@@CAJPEAUIUserName@@PEAG@Z; CUserProfile::CreateHomeDrectory(IUserName *,ushort *)
0x18006ba80  mov     ebx, eax
0x18006ba82  test    eax, eax
0x18006ba84  jns     short loc_18006BAB1
0x18006ba86  mov     rcx, r13; struct IUserName *
0x18006ba89  call    ?ReportHomeDirectoryFailed@CUserProfile@@CAJPEAUIUserName@@@Z; CUserProfile::ReportHomeDirectoryFailed(IUserName *)
0x18006ba8e  mov     rcx, rdi; hMem
0x18006ba91  call    cs:__imp_LocalFree
0x18006ba97  mov     rsi, [rbp+var_30]
0x18006ba9b  xor     edi, edi
0x18006ba9d  test    rsi, rsi
0x18006baa0  jz      short loc_18006BAAD
0x18006baa2  mov     rcx, rsi; hMem
0x18006baa5  call    cs:__imp_LocalFree
0x18006baab  xor     esi, esi
0x18006baad  xor     ebx, ebx
0x18006baaf  jmp     short loc_18006BAB5
0x18006bab1  mov     rsi, [rbp+var_30]
0x18006bab5  mov     rax, [rbp+var_28]
0x18006bab9  mov     rcx, [rbp+arg_10]
0x18006babd  mov     [rcx], rax
0x18006bac0  mov     rax, [rbp+arg_18]
0x18006bac4  mov     [rax], rdi
0x18006bac7  mov     rax, [rbp+arg_20]
0x18006bacb  mov     [rax], rsi
0x18006bace  test    ebx, ebx
0x18006bad0  jns     short loc_18006BB06
0x18006bad2  mov     rcx, [rbp+arg_0]; struct IUserName *
0x18006bad6  call    ?ReportProfileFailed@CUserProfile@@CAJPEAUIUserName@@@Z; CUserProfile::ReportProfileFailed(IUserName *)
0x18006badb  mov     rcx, [rbp+var_28]; hMem
0x18006badf  test    rcx, rcx
0x18006bae2  jz      short loc_18006BAEA
0x18006bae4  call    cs:__imp_LocalFree
0x18006baea  test    rdi, rdi
0x18006baed  jz      short loc_18006BAF8
0x18006baef  mov     rcx, rdi; hMem
0x18006baf2  call    cs:__imp_LocalFree
0x18006baf8  test    rsi, rsi
0x18006bafb  jz      short loc_18006BB06
0x18006bafd  mov     rcx, rsi; hMem
0x18006bb00  call    cs:__imp_LocalFree
0x18006bb06  test    r14, r14
0x18006bb09  jz      short loc_18006BB13
0x18006bb0b  mov     rcx, r14; Block
0x18006bb0e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bb13  test    r12, r12
0x18006bb16  jz      short loc_18006BB20
0x18006bb18  mov     rcx, r12; Block
0x18006bb1b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bb20  test    r15, r15
0x18006bb23  jz      short loc_18006BB2D
0x18006bb25  mov     rcx, r15; Block
0x18006bb28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006bb2d  mov     eax, ebx
0x18006bb2f  mov     rbx, [rsp+60h+arg_8]
0x18006bb37  add     rsp, 60h
0x18006bb3b  pop     r15
0x18006bb3d  pop     r14
0x18006bb3f  pop     r13
0x18006bb41  pop     r12
0x18006bb43  pop     rdi
0x18006bb44  pop     rsi
0x18006bb45  pop     rbp
0x18006bb46  retn
```
