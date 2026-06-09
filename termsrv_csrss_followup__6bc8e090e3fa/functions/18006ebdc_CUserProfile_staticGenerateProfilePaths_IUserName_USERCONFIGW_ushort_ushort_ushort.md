# CUserProfile::staticGenerateProfilePaths(IUserName *,_USERCONFIGW *,ushort * *,ushort * *,ushort * *)

- ea: `0x18006ebdc`
- end: `0x18006ef0a`
- name: `?staticGenerateProfilePaths@CUserProfile@@SAJPEAUIUserName@@PEAU_USERCONFIGW@@PEAPEAG22@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct IUserName *, struct _USERCONFIGW *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18005e3f0`

## callees

- `0x180009940`
- `0x18003440c`
- `0x18006dc90`
- `0x18006e044`
- `0x18006e100`
- `0x18006e1f4`
- `0x18006e514`
- `0x18006e650`
- `0x18006e720`
- `0x18006e818`
- `0x18006ebdc`
- `0x1800b7890`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eebc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ee94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eebc`

## string_xrefs

- `0x18006ec4d`: `IsAppServerInstalled failed: 0x%x in %s`
- `0x18006ec57`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006ec89`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006ed2c`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006ed83`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006edaf`: `CUserProfile::staticGenerateProfilePaths`
- `0x18006ecd0`: `AssembleThePath(wszProfilePath) failed: 0x%x in %s`
- `0x18006eceb`: `CopyThePath(wszPolicyProfilePath) failed: 0x%x in %s`
- `0x18006ed0d`: `CopyThePath(wszProfilePath) failed: 0x%x in %s`
- `0x18006ed79`: `AssembleThePath(wszHomeDir) failed: 0x%x in %s`
- `0x18006edb9`: `CopyHomeDrive(wszHomeDirDrive) failed: 0x%x in %s`
- `0x18006eded`: `CopyThePath(wszHomeDir) failed: 0x%x in %s`

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
0x18006ebdc  mov     rax, rsp
0x18006ebdf  mov     [rax+10h], rbx
0x18006ebe3  mov     [rax+20h], r9
0x18006ebe7  mov     [rax+18h], r8
0x18006ebeb  mov     [rax+8], rcx
0x18006ebef  push    rbp
0x18006ebf0  push    rsi
0x18006ebf1  push    rdi
0x18006ebf2  push    r12
0x18006ebf4  push    r13
0x18006ebf6  push    r14
0x18006ebf8  push    r15
0x18006ebfa  mov     rbp, rsp
0x18006ebfd  sub     rsp, 60h
0x18006ec01  mov     rax, [rbp+arg_20]
0x18006ec05  xor     ecx, ecx
0x18006ec07  mov     [r8], rcx
0x18006ec0a  mov     r14d, ecx
0x18006ec0d  mov     [r9], rcx
0x18006ec10  mov     r12d, ecx
0x18006ec13  mov     [rbp+var_20], rcx
0x18006ec17  mov     r15d, ecx
0x18006ec1a  mov     [rax], rcx
0x18006ec1d  mov     edi, ecx
0x18006ec1f  mov     [rbp+var_18], rcx
0x18006ec23  mov     esi, ecx
0x18006ec25  mov     [rbp+var_10], rcx
0x18006ec29  mov     r13, rdx
0x18006ec2c  mov     [rbp+var_28], rcx
0x18006ec30  mov     [rbp+hMem], rcx
0x18006ec34  mov     [rbp+var_30], rcx
0x18006ec38  mov     [rbp+var_3C], ecx
0x18006ec3b  mov     [rbp+var_40], ecx
0x18006ec3e  lea     rcx, [rbp+var_40]; int *
0x18006ec42  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18006ec47  mov     ebx, eax
0x18006ec49  test    eax, eax
0x18006ec4b  jns     short loc_18006EC6D
0x18006ec4d  lea     rdx, aIsappserverins_0; "IsAppServerInstalled failed: 0x%x in %s"
0x18006ec54  mov     r8d, eax
0x18006ec57  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006ec5e  mov     ecx, 8; int
0x18006ec63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ec68  jmp     loc_18006EE82
0x18006ec6d  cmp     [rbp+var_40], esi
0x18006ec70  jz      loc_18006EEC8
0x18006ec76  lea     rdx, [rbp+var_3C]; int *
0x18006ec7a  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x18006ec7e  call    ?GetPolicyProfile@CUserProfile@@CAJPEAPEAGPEAH@Z; CUserProfile::GetPolicyProfile(ushort * *,int *)
0x18006ec83  mov     ebx, eax
0x18006ec85  test    eax, eax
0x18006ec87  jns     short loc_18006ECAD
0x18006ec89  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006ec90  mov     r8d, eax
0x18006ec93  lea     rdx, aGetpolicyprofi; "GetPolicyProfile failed: 0x%x in %s"
0x18006ec9a  mov     ecx, 8; int
0x18006ec9f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006eca4  mov     r14, [rbp+var_20]
0x18006eca8  jmp     loc_18006EE82
0x18006ecad  mov     r14, [rbp+var_20]
0x18006ecb1  test    eax, eax
0x18006ecb3  jnz     short loc_18006ECF7
0x18006ecb5  mov     rcx, r14; unsigned __int16 *
0x18006ecb8  cmp     [rbp+var_3C], esi
0x18006ecbb  jnz     short loc_18006ECDC
0x18006ecbd  mov     rdx, [rbp+arg_0]; struct IUserName *
0x18006ecc1  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18006ecc5  call    ?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z; CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)
0x18006ecca  mov     ebx, eax
0x18006eccc  test    eax, eax
0x18006ecce  jns     short loc_18006ED19
0x18006ecd0  lea     rdx, aAssemblethepat_0; "AssembleThePath(wszProfilePath) failed:"...
0x18006ecd7  jmp     loc_18006EC54
0x18006ecdc  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18006ece0  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006ece5  mov     ebx, eax
0x18006ece7  test    eax, eax
0x18006ece9  jns     short loc_18006ED19
0x18006eceb  lea     rdx, aCopythepathWsz_0; "CopyThePath(wszPolicyProfilePath) faile"...
0x18006ecf2  jmp     loc_18006EC54
0x18006ecf7  lea     rcx, [r13+5DCh]; unsigned __int16 *
0x18006ecfe  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18006ed02  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006ed07  mov     ebx, eax
0x18006ed09  test    eax, eax
0x18006ed0b  jns     short loc_18006ED19
0x18006ed0d  lea     rdx, aCopythepathWsz; "CopyThePath(wszProfilePath) failed: 0x%"...
0x18006ed14  jmp     loc_18006EC54
0x18006ed19  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18006ed1d  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x18006ed21  call    ?GetPolicyHomeDir@CUserProfile@@CAJPEAPEAG0@Z; CUserProfile::GetPolicyHomeDir(ushort * *,ushort * *)
0x18006ed26  mov     ebx, eax
0x18006ed28  test    eax, eax
0x18006ed2a  jns     short loc_18006ED54
0x18006ed2c  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006ed33  mov     r8d, eax
0x18006ed36  lea     rdx, aGetpolicyhomed; "GetPolicyHomeDir failed: 0x%x in %s"
0x18006ed3d  mov     ecx, 8; int
0x18006ed42  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ed47  mov     r12, [rbp+var_18]
0x18006ed4b  mov     r15, [rbp+var_10]
0x18006ed4f  jmp     loc_18006EE82
0x18006ed54  mov     r12, [rbp+var_18]
0x18006ed58  mov     r15, [rbp+var_10]
0x18006ed5c  test    eax, eax
0x18006ed5e  jnz     short loc_18006EDD7
0x18006ed60  mov     r13, [rbp+arg_0]
0x18006ed64  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18006ed68  mov     rdx, r13; struct IUserName *
0x18006ed6b  mov     rcx, r12; unsigned __int16 *
0x18006ed6e  call    ?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z; CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)
0x18006ed73  mov     ebx, eax
0x18006ed75  test    eax, eax
0x18006ed77  jns     short loc_18006ED9D
0x18006ed79  lea     rdx, aAssemblethepat; "AssembleThePath(wszHomeDir) failed: 0x%"...
0x18006ed80  mov     r8d, eax
0x18006ed83  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006ed8a  mov     ecx, 8; int
0x18006ed8f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ed94  mov     rdi, [rbp+hMem]
0x18006ed98  jmp     loc_18006EE82
0x18006ed9d  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18006eda1  mov     rcx, r15; unsigned __int16 *
0x18006eda4  call    ?CopyHomeDrive@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyHomeDrive(ushort const *,ushort * *)
0x18006eda9  mov     ebx, eax
0x18006edab  test    eax, eax
0x18006edad  jns     short loc_18006EE10
0x18006edaf  lea     r9, aCuserprofileSt; "CUserProfile::staticGenerateProfilePath"...
0x18006edb6  mov     r8d, eax
0x18006edb9  lea     rdx, aCopyhomedriveW; "CopyHomeDrive(wszHomeDirDrive) failed: "...
0x18006edc0  mov     ecx, 8; int
0x18006edc5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006edca  mov     rdi, [rbp+hMem]
0x18006edce  mov     rsi, [rbp+var_30]
0x18006edd2  jmp     loc_18006EE82
0x18006edd7  lea     rcx, [r13+7DEh]; unsigned __int16 *
0x18006edde  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18006ede2  call    ?CopyThePath@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyThePath(ushort const *,ushort * *)
0x18006ede7  mov     ebx, eax
0x18006ede9  test    eax, eax
0x18006edeb  jns     short loc_18006EDF6
0x18006eded  lea     rdx, aCopythepathWsz_1; "CopyThePath(wszHomeDir) failed: 0x%x in"...
0x18006edf4  jmp     short loc_18006ED80
0x18006edf6  lea     rcx, [r13+9E0h]; unsigned __int16 *
0x18006edfd  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18006ee01  call    ?CopyHomeDrive@CUserProfile@@CAJPEBGPEAPEAG@Z; CUserProfile::CopyHomeDrive(ushort const *,ushort * *)
0x18006ee06  mov     ebx, eax
0x18006ee08  test    eax, eax
0x18006ee0a  js      short loc_18006EDAF
0x18006ee0c  mov     r13, [rbp+arg_0]
0x18006ee10  mov     rdi, [rbp+hMem]
0x18006ee14  test    rdi, rdi
0x18006ee17  jz      short loc_18006EE61
0x18006ee19  mov     rdx, rdi; pObjectName
0x18006ee1c  mov     rcx, r13; struct IUserName *
0x18006ee1f  call    ?CreateHomeDrectory@CUserProfile@@CAJPEAUIUserName@@PEAG@Z; CUserProfile::CreateHomeDrectory(IUserName *,ushort *)
0x18006ee24  mov     ebx, eax
0x18006ee26  test    eax, eax
0x18006ee28  jns     short loc_18006EE61
0x18006ee2a  mov     rcx, r13; struct IUserName *
0x18006ee2d  call    ?ReportHomeDirectoryFailed@CUserProfile@@CAJPEAUIUserName@@@Z; CUserProfile::ReportHomeDirectoryFailed(IUserName *)
0x18006ee32  mov     rcx, rdi; hMem
0x18006ee35  call    cs:__imp_LocalFree
0x18006ee3c  nop     dword ptr [rax+rax+00h]
0x18006ee41  mov     rsi, [rbp+var_30]
0x18006ee45  xor     edi, edi
0x18006ee47  test    rsi, rsi
0x18006ee4a  jz      short loc_18006EE5D
0x18006ee4c  mov     rcx, rsi; hMem
0x18006ee4f  call    cs:__imp_LocalFree
0x18006ee56  nop     dword ptr [rax+rax+00h]
0x18006ee5b  xor     esi, esi
0x18006ee5d  xor     ebx, ebx
0x18006ee5f  jmp     short loc_18006EE65
0x18006ee61  mov     rsi, [rbp+var_30]
0x18006ee65  mov     rax, [rbp+var_28]
0x18006ee69  mov     rcx, [rbp+arg_10]
0x18006ee6d  mov     [rcx], rax
0x18006ee70  mov     rax, [rbp+arg_18]
0x18006ee74  mov     [rax], rdi
0x18006ee77  mov     rax, [rbp+arg_20]
0x18006ee7b  mov     [rax], rsi
0x18006ee7e  test    ebx, ebx
0x18006ee80  jns     short loc_18006EEC8
0x18006ee82  mov     rcx, [rbp+arg_0]; struct IUserName *
0x18006ee86  call    ?ReportProfileFailed@CUserProfile@@CAJPEAUIUserName@@@Z; CUserProfile::ReportProfileFailed(IUserName *)
0x18006ee8b  mov     rcx, [rbp+var_28]; hMem
0x18006ee8f  test    rcx, rcx
0x18006ee92  jz      short loc_18006EEA0
0x18006ee94  call    cs:__imp_LocalFree
0x18006ee9b  nop     dword ptr [rax+rax+00h]
0x18006eea0  test    rdi, rdi
0x18006eea3  jz      short loc_18006EEB4
0x18006eea5  mov     rcx, rdi; hMem
0x18006eea8  call    cs:__imp_LocalFree
0x18006eeaf  nop     dword ptr [rax+rax+00h]
0x18006eeb4  test    rsi, rsi
0x18006eeb7  jz      short loc_18006EEC8
0x18006eeb9  mov     rcx, rsi; hMem
0x18006eebc  call    cs:__imp_LocalFree
0x18006eec3  nop     dword ptr [rax+rax+00h]
0x18006eec8  test    r14, r14
0x18006eecb  jz      short loc_18006EED5
0x18006eecd  mov     rcx, r14; Block
0x18006eed0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006eed5  test    r12, r12
0x18006eed8  jz      short loc_18006EEE2
0x18006eeda  mov     rcx, r12; Block
0x18006eedd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006eee2  test    r15, r15
0x18006eee5  jz      short loc_18006EEEF
0x18006eee7  mov     rcx, r15; Block
0x18006eeea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006eeef  mov     eax, ebx
0x18006eef1  mov     rbx, [rsp+60h+arg_8]
0x18006eef9  add     rsp, 60h
0x18006eefd  pop     r15
0x18006eeff  pop     r14
0x18006ef01  pop     r13
0x18006ef03  pop     r12
0x18006ef05  pop     rdi
0x18006ef06  pop     rsi
0x18006ef07  pop     rbp
0x18006ef08  retn
```
