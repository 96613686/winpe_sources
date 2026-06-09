# CNtfsFileSystemApplier::UpdateFromStaged(IFspStagedFile *,IFspInPlaceFile *,ushort const *,ushort const *,ulong,ulong,int,IFileConcurrencyBlob * *,IFileConcurrencyBlob * *)

- ea: `0x18010fd2c`
- end: `0x180110386`
- name: `?UpdateFromStaged@CNtfsFileSystemApplier@@AEAAJPEAUIFspStagedFile@@PEAUIFspInPlaceFile@@PEBG2KKHPEAPEAUIFileConcurrencyBlob@@3@Z`
- size: `1626`
- prototype: `int(CNtfsFileSystemApplier *__hidden this, struct IFspStagedFile *, struct IFspInPlaceFile *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int, struct IFileConcurrencyBlob **, struct IFileConcurrencyBlob **)`
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010bad0`
- `0x18010d440`
- `0x18010f5a0`
- `0x18010fa70`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x18001137c`
- `0x18002db48`
- `0x180058d88`
- `0x18008c2d0`
- `0x1800bb594`
- `0x1800bb748`
- `0x1800bb948`
- `0x18010c520`
- `0x18010e084`
- `0x18010fd2c`
- `0x18011038c`
- `0x180110784`
- `0x1801119ac`
- `0x180111f4c`
- `0x1801124dc`
- `0x1801127bc`
- `0x180112aa0`
- `0x18013e010`

## import_xrefs

- `ADVAPI32!DecryptFileW` at `0x18011011f`
- `ADVAPI32!DecryptFileW` at `0x180110150`
- `ADVAPI32!DecryptFileW` at `0x18011011f`
- `ADVAPI32!DecryptFileW` at `0x180110150`
- `ntdll!NtClose` at `0x180110057`
- `ntdll!NtClose` at `0x1801102bd`
- `ntdll!NtClose` at `0x1801102cc`
- `ntdll!NtClose` at `0x180110057`
- `ntdll!NtClose` at `0x1801102bd`
- `ntdll!NtClose` at `0x1801102cc`
- `KERNELBASE!ReplaceFileExInternal` at `0x1801101cd`
- `KERNELBASE!ReplaceFileExInternal` at `0x1801101cd`

## string_xrefs

- `0x18010fdc0`: `CNtfsFileSystemApplier::UpdateFromStaged`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNtfsFileSystemApplier::UpdateFromStaged(
        const unsigned __int16 **this,
        struct IFspStagedFile *a2,
        struct IFspInPlaceFile *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        struct IFileConcurrencyBlob **a9,
        const WCHAR *a10)
{
  _DWORD *v14; // rax
  char v15; // cl
  const unsigned __int16 *v16; // rdi
  struct IFileConcurrencyBlob **v17; // r15
  const unsigned __int16 *v18; // r13
  __int16 v19; // ax
  unsigned int v20; // r8d
  bool v21; // sf
  const WCHAR *v22; // r14
  HANDLE v23; // rbx
  __int16 v24; // ax
  ULONG v25; // edx
  unsigned int v26; // esi
  CNtfsFileSystemApplier *v27; // rcx
  struct IFspFile *v28; // r12
  __int16 v29; // ax
  CNtfsFileSystemApplier *v30; // rcx
  unsigned int v31; // ebx
  unsigned int v33; // [rsp+30h] [rbp-81h]
  int AbsoluteFileName; // [rsp+58h] [rbp-59h] BYREF
  int v35; // [rsp+5Ch] [rbp-55h]
  char v36; // [rsp+60h] [rbp-51h]
  const char *v37; // [rsp+68h] [rbp-49h]
  __int64 v38; // [rsp+70h] [rbp-41h]
  LPCWSTR lpFileName; // [rsp+78h] [rbp-39h] BYREF
  PCWSTR SourceString; // [rsp+80h] [rbp-31h] BYREF
  HANDLE v41; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 *v42; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 *v43; // [rsp+98h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-11h] BYREF
  void *v45[8]; // [rsp+A8h] [rbp-9h] BYREF
  struct IFspFile *v47; // [rsp+100h] [rbp+4Fh] BYREF

  v47 = a2;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  if ( (v14[17] & 0x100) == 0 || (v15 = 1, *((_BYTE *)v14 + 65) < 6u) )
    v15 = 0;
  AbsoluteFileName = 0;
  v35 = 936;
  v36 = v15;
  v37 = "CNtfsFileSystemApplier::UpdateFromStaged";
  v38 = 0;
  v43 = 0;
  v42 = 0;
  SourceString = 0;
  lpFileName = 0;
  v16 = 0;
  Handle = 0;
  a6 = 0;
  v45[0] = 0;
  v41 = 0;
  if ( a9 )
    *a9 = 0;
  v17 = (struct IFileConcurrencyBlob **)a10;
  if ( a10 )
    *(_QWORD *)a10 = 0;
  if ( !a2 )
  {
    AbsoluteFileName = -2147024809;
    HIWORD(v35) = 952;
LABEL_70:
    if ( a8 && v16 )
    {
      v30 = (CNtfsFileSystemApplier *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids, v16);
      }
      CNtfsFileSystemApplier::DeleteSingle(v30, v16, 0);
    }
    goto LABEL_77;
  }
  LOWORD(v35) = 952;
  v18 = a5;
  if ( (a5 == 0) != (v17 == 0) )
  {
    AbsoluteFileName = -2147024809;
    HIWORD(v35) = 956;
    goto LABEL_70;
  }
  AbsoluteFileName = 0;
  LOWORD(v35) = 956;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[1], a2, &v43);
  v19 = 961;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 961;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[2], a2, &v42);
  v19 = 965;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 965;
  if ( a4 )
  {
    AbsoluteFileName = CPathUtilities::GetNormalizedNtPath(a4, (unsigned __int16 **)&SourceString);
    v19 = 973;
    if ( AbsoluteFileName >= 0 )
    {
      LOWORD(v35) = 973;
      v16 = SourceString;
      AbsoluteFileName = CPathUtilities::GetNormalizedWin32Path(a4, (unsigned __int16 **)&lpFileName);
      v21 = AbsoluteFileName < 0;
      v19 = 977;
      goto LABEL_22;
    }
LABEL_17:
    HIWORD(v35) = v19;
    goto LABEL_67;
  }
  if ( !a3 )
  {
    v16 = v43;
    v22 = v42;
    goto LABEL_28;
  }
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[1], a3, (unsigned __int16 **)&SourceString);
  v19 = 991;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 991;
  v16 = SourceString;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[2], a3, (unsigned __int16 **)&lpFileName);
  v21 = AbsoluteFileName < 0;
  v19 = 996;
LABEL_22:
  if ( v21 )
    goto LABEL_17;
  LOWORD(v35) = v19;
  v22 = lpFileName;
LABEL_28:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      22,
      (unsigned int)WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids,
      (_DWORD)v16,
      (__int64)v43);
  }
  AbsoluteFileName = CFspFileSystemOperations::CreateFileW(v16, 0x120181u, v20, 0, 0x20u, v33, 8u, &Handle);
  v23 = Handle;
  v24 = 1026;
  if ( AbsoluteFileName < 0 )
    goto LABEL_33;
  LOWORD(v35) = 1026;
  AbsoluteFileName = CFspFileSystemOperations::GetAttributes(Handle, &a6);
  v24 = 1033;
  if ( AbsoluteFileName < 0 )
    goto LABEL_33;
  LOWORD(v35) = 1033;
  v26 = a6 & 0x6800 | 0x20;
  AbsoluteFileName = CFspFileSystemOperations::GetSecurity(v23, v25, v45);
  v24 = 1047;
  if ( AbsoluteFileName < 0 )
    goto LABEL_33;
  LOWORD(v35) = 1047;
  if ( a3 )
  {
    AbsoluteFileName = CNtfsFileSystemApplier::ValidateFileUnchanged(v27, v23, a3);
    v24 = 1056;
    if ( AbsoluteFileName < 0 )
    {
LABEL_33:
      HIWORD(v35) = v24;
LABEL_65:
      if ( v23 )
        NtClose(v23);
      goto LABEL_67;
    }
    LOWORD(v35) = 1056;
  }
  AbsoluteFileName = CFspFileSystemOperations::ClearReadOnly(v23);
  v24 = 1061;
  if ( AbsoluteFileName < 0 )
    goto LABEL_33;
  LOWORD(v35) = 1061;
  NtClose(v23);
  v23 = 0;
  a10 = 0;
  v28 = v47;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, const WCHAR **))(*(_QWORD *)v47 + 104LL))(v47, &a10);
  v19 = 1079;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 1079;
  a6 = 0;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(*(_QWORD *)v28 + 40LL))(v28, &a6);
  v19 = 1089;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 1089;
  if ( (a6 & 4) != 0 && (v26 & 0x4000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        23,
        (unsigned int)WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids,
        (_DWORD)v22,
        (__int64)a10);
    }
    if ( !DecryptFileW(v22, 0) )
    {
      AbsoluteFileName = EcsGetLastFailureAsHRESULT();
      v19 = 1103;
      goto LABEL_17;
    }
    AbsoluteFileName = 0;
    LOWORD(v35) = 1103;
    if ( !DecryptFileW(a10, 0) )
    {
      AbsoluteFileName = EcsGetLastFailureAsHRESULT();
      v19 = 1104;
      goto LABEL_17;
    }
    AbsoluteFileName = 0;
    LOWORD(v35) = 1104;
    v26 &= ~0x4000u;
  }
  if ( v18 && v17 )
  {
    AbsoluteFileName = CFspFileSystemOperations::OpenFileAttribute(v16, &v41);
    v19 = 1119;
    if ( AbsoluteFileName < 0 )
      goto LABEL_17;
    LOWORD(v35) = 1119;
  }
  if ( !(unsigned int)ReplaceFileExInternal(v22, a10, v18, 0) )
  {
    AbsoluteFileName = EcsGetLastFailureAsHRESULT();
    v19 = 1135;
    goto LABEL_17;
  }
  LOWORD(v35) = 1135;
  AbsoluteFileName = CNtfsFileSystemApplier::UpdateInPlace(
                       (CNtfsFileSystemApplier *)this,
                       v28,
                       0,
                       v22,
                       v42,
                       v26,
                       8u,
                       v45[0],
                       4u,
                       a9);
  v19 = 1155;
  if ( AbsoluteFileName < 0 )
    goto LABEL_17;
  LOWORD(v35) = 1155;
  if ( v18 && v17 )
  {
    v47 = 0;
    AbsoluteFileName = CPathUtilities::GetNormalizedNtPath(v18, (unsigned __int16 **)&v47);
    v29 = 1164;
    if ( AbsoluteFileName < 0
      || (LOWORD(v35) = 1164,
          AbsoluteFileName = CNtfsFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                               (CNtfsFileSystemApplier *)this,
                               &v41,
                               (const unsigned __int16 *)v47,
                               v17),
          v29 = 1168,
          AbsoluteFileName < 0) )
    {
      HIWORD(v35) = v29;
      CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v47);
      goto LABEL_67;
    }
    LOWORD(v35) = 1168;
    CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v47);
    goto LABEL_65;
  }
LABEL_67:
  if ( v41 )
  {
    NtClose(v41);
    v41 = 0;
  }
  if ( AbsoluteFileName < 0 )
    goto LABEL_70;
LABEL_77:
  v31 = AbsoluteFileName;
  CEcsMemPtr<unsigned char,0>::~CEcsMemPtr<unsigned char,0>(v45);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&lpFileName);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v42);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v43);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&AbsoluteFileName);
  return v31;
}

```

## disassembly

```asm
0x18010fd2c  mov     rax, rsp
0x18010fd2f  mov     [rax+18h], rbx
0x18010fd33  mov     [rax+10h], rdx
0x18010fd37  mov     [rax+8], rcx
0x18010fd3b  push    rbp
0x18010fd3c  push    rsi
0x18010fd3d  push    rdi
0x18010fd3e  push    r12
0x18010fd40  push    r13
0x18010fd42  push    r14
0x18010fd44  push    r15
0x18010fd46  lea     rbp, [rax-3Fh]
0x18010fd4a  sub     rsp, 0B0h
0x18010fd51  mov     rbx, r9
0x18010fd54  mov     r12, r8
0x18010fd57  mov     rsi, rdx
0x18010fd5a  mov     r14, rcx
0x18010fd5d  lea     r13, WPP_GLOBAL_Control
0x18010fd64  mov     rax, cs:WPP_GLOBAL_Control
0x18010fd6b  cmp     rax, r13
0x18010fd6e  jz      short loc_18010FD9B
0x18010fd70  test    dword ptr [rax+44h], 100h
0x18010fd77  jz      short loc_18010FD9B
0x18010fd79  cmp     byte ptr [rax+41h], 6
0x18010fd7d  jb      short loc_18010FD9B
0x18010fd7f  mov     edx, 15h
0x18010fd84  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18010fd8b  mov     rcx, [rax+38h]
0x18010fd8f  call    WPP_SF_
0x18010fd94  mov     rax, cs:WPP_GLOBAL_Control
0x18010fd9b  xor     r15d, r15d
0x18010fd9e  test    dword ptr [rax+44h], 100h
0x18010fda5  jz      short loc_18010FDAF
0x18010fda7  cmp     byte ptr [rax+41h], 6
0x18010fdab  mov     cl, 1
0x18010fdad  jnb     short loc_18010FDB2
0x18010fdaf  mov     cl, r15b
0x18010fdb2  mov     [rbp+37h+var_90], r15d
0x18010fdb6  mov     [rbp+37h+var_8C], 3A8h
0x18010fdbd  mov     [rbp+37h+var_88], cl
0x18010fdc0  lea     rax, aCntfsfilesyste_16; "CNtfsFileSystemApplier::UpdateFromStage"...
0x18010fdc7  mov     [rbp+37h+var_80], rax
0x18010fdcb  mov     [rbp+37h+var_78], r15
0x18010fdcf  mov     [rbp+37h+var_50], r15
0x18010fdd3  mov     [rbp+37h+var_58], r15
0x18010fdd7  mov     [rbp+37h+SourceString], r15
0x18010fddb  mov     [rbp+37h+lpFileName], r15
0x18010fddf  mov     rdi, r15
0x18010fde2  mov     [rbp+37h+Handle], r15
0x18010fde6  mov     [rbp+37h+arg_28], r15d
0x18010fdea  mov     [rbp+37h+var_40], r15
0x18010fdee  mov     [rbp+37h+var_60], r15
0x18010fdf2  mov     rax, [rbp+37h+arg_40]
0x18010fdf9  test    rax, rax
0x18010fdfc  jz      short loc_18010FE01
0x18010fdfe  mov     [rax], r15
0x18010fe01  mov     r15, [rbp+37h+arg_48]
0x18010fe08  test    r15, r15
0x18010fe0b  jz      short loc_18010FE14
0x18010fe0d  mov     qword ptr [r15], 0
0x18010fe14  mov     eax, 3B8h
0x18010fe19  test    rsi, rsi
0x18010fe1c  jnz     short loc_18010FE2E
0x18010fe1e  mov     [rbp+37h+var_90], 80070057h
0x18010fe25  mov     word ptr [rbp+37h+var_8C+2], ax
0x18010fe29  jmp     loc_1801102E7
0x18010fe2e  mov     word ptr [rbp+37h+var_8C], ax
0x18010fe32  xor     ecx, ecx
0x18010fe34  mov     r13, [rbp+37h+arg_20]
0x18010fe38  test    r13, r13
0x18010fe3b  setz    cl
0x18010fe3e  xor     eax, eax
0x18010fe40  test    r15, r15
0x18010fe43  setz    al
0x18010fe46  cmp     ecx, eax
0x18010fe48  mov     eax, 3BCh
0x18010fe4d  jz      short loc_18010FE5F
0x18010fe4f  mov     [rbp+37h+var_90], 80070057h
0x18010fe56  mov     word ptr [rbp+37h+var_8C+2], ax
0x18010fe5a  jmp     loc_1801102E0
0x18010fe5f  mov     [rbp+37h+var_90], 0
0x18010fe66  mov     word ptr [rbp+37h+var_8C], ax
0x18010fe6a  lea     r8, [rbp+37h+var_50]; unsigned __int16 **
0x18010fe6e  mov     rdx, rsi; struct IFspFile *
0x18010fe71  mov     rcx, [r14+8]; unsigned __int16 *
0x18010fe75  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x18010fe7a  mov     [rbp+37h+var_90], eax
0x18010fe7d  test    eax, eax
0x18010fe7f  mov     eax, 3C1h
0x18010fe84  jns     short loc_18010FE8F
0x18010fe86  mov     word ptr [rbp+37h+var_8C+2], ax
0x18010fe8a  jmp     loc_1801102C3
0x18010fe8f  mov     word ptr [rbp+37h+var_8C], ax
0x18010fe93  lea     r8, [rbp+37h+var_58]; unsigned __int16 **
0x18010fe97  mov     rdx, rsi; struct IFspFile *
0x18010fe9a  mov     rcx, [r14+10h]; unsigned __int16 *
0x18010fe9e  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x18010fea3  mov     [rbp+37h+var_90], eax
0x18010fea6  test    eax, eax
0x18010fea8  mov     eax, 3C5h
0x18010fead  js      short loc_18010FE86
0x18010feaf  mov     word ptr [rbp+37h+var_8C], ax
0x18010feb3  test    rbx, rbx
0x18010feb6  jz      short loc_18010FEFA
0x18010feb8  lea     rdx, [rbp+37h+SourceString]; unsigned __int16 **
0x18010febc  mov     rcx, rbx; unsigned __int16 *
0x18010febf  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x18010fec4  mov     [rbp+37h+var_90], eax
0x18010fec7  test    eax, eax
0x18010fec9  mov     eax, 3CDh
0x18010fece  js      short loc_18010FE86
0x18010fed0  mov     word ptr [rbp+37h+var_8C], ax
0x18010fed4  mov     rdi, [rbp+37h+SourceString]
0x18010fed8  lea     rdx, [rbp+37h+lpFileName]; unsigned __int16 **
0x18010fedc  mov     rcx, rbx; FileName
0x18010fedf  call    ?GetNormalizedWin32Path@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedWin32Path(ushort const *,ushort * *)
0x18010fee4  mov     [rbp+37h+var_90], eax
0x18010fee7  test    eax, eax
0x18010fee9  mov     eax, 3D1h
0x18010feee  js      short loc_18010FE86
0x18010fef0  mov     word ptr [rbp+37h+var_8C], ax
0x18010fef4  mov     r14, [rbp+37h+lpFileName]
0x18010fef8  jmp     short loc_18010FF4B
0x18010fefa  test    r12, r12
0x18010fefd  jz      short loc_18010FF43
0x18010feff  lea     r8, [rbp+37h+SourceString]; unsigned __int16 **
0x18010ff03  mov     rdx, r12; struct IFspFile *
0x18010ff06  mov     rcx, [r14+8]; unsigned __int16 *
0x18010ff0a  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x18010ff0f  mov     [rbp+37h+var_90], eax
0x18010ff12  test    eax, eax
0x18010ff14  mov     eax, 3DFh
0x18010ff19  js      loc_18010FE86
0x18010ff1f  mov     word ptr [rbp+37h+var_8C], ax
0x18010ff23  mov     rdi, [rbp+37h+SourceString]
0x18010ff27  lea     r8, [rbp+37h+lpFileName]; unsigned __int16 **
0x18010ff2b  mov     rdx, r12; struct IFspFile *
0x18010ff2e  mov     rcx, [r14+10h]; unsigned __int16 *
0x18010ff32  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x18010ff37  mov     [rbp+37h+var_90], eax
0x18010ff3a  test    eax, eax
0x18010ff3c  mov     eax, 3E4h
0x18010ff41  jmp     short loc_18010FEEE
0x18010ff43  mov     rdi, [rbp+37h+var_50]
0x18010ff47  mov     r14, [rbp+37h+var_58]
0x18010ff4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18010ff52  lea     rax, WPP_GLOBAL_Control
0x18010ff59  cmp     rcx, rax
0x18010ff5c  jz      short loc_18010FF8E
0x18010ff5e  test    dword ptr [rcx+44h], 100h
0x18010ff65  jz      short loc_18010FF8E
0x18010ff67  cmp     byte ptr [rcx+41h], 4
0x18010ff6b  jb      short loc_18010FF8E
0x18010ff6d  mov     edx, 16h
0x18010ff72  mov     rax, [rbp+37h+var_50]
0x18010ff76  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18010ff7b  mov     r9, rdi
0x18010ff7e  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x18010ff85  mov     rcx, [rcx+38h]
0x18010ff89  call    WPP_SF_SS
0x18010ff8e  lea     rax, [rbp+37h+Handle]
0x18010ff92  mov     [rsp+0E0h+var_A8], rax; void **
0x18010ff97  mov     [rsp+0E0h+var_B0], 8; unsigned int
0x18010ff9f  mov     [rsp+0E0h+var_C0], 20h ; ' '; ULONG
0x18010ffa7  xor     r9d, r9d; unsigned int
0x18010ffaa  mov     edx, 120181h; DesiredAccess
0x18010ffaf  mov     rcx, rdi; SourceString
0x18010ffb2  call    ?CreateFileW@CFspFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18010ffb7  mov     [rbp+37h+var_90], eax
0x18010ffba  mov     rbx, [rbp+37h+Handle]
0x18010ffbe  test    eax, eax
0x18010ffc0  mov     eax, 402h
0x18010ffc5  jns     short loc_18010FFD0
0x18010ffc7  mov     word ptr [rbp+37h+var_8C+2], ax
0x18010ffcb  jmp     loc_1801102B5
0x18010ffd0  mov     word ptr [rbp+37h+var_8C], ax
0x18010ffd4  lea     rdx, [rbp+37h+arg_28]; unsigned int *
0x18010ffd8  mov     rcx, rbx; FileHandle
0x18010ffdb  call    ?GetAttributes@CFspFileSystemOperations@@SAJPEAXPEAK@Z; CFspFileSystemOperations::GetAttributes(void *,ulong *)
0x18010ffe0  mov     [rbp+37h+var_90], eax
0x18010ffe3  test    eax, eax
0x18010ffe5  mov     eax, 409h
0x18010ffea  js      short loc_18010FFC7
0x18010ffec  mov     word ptr [rbp+37h+var_8C], ax
0x18010fff0  mov     esi, [rbp+37h+arg_28]
0x18010fff3  and     esi, 6800h
0x18010fff9  or      esi, 20h
0x18010fffc  lea     r8, [rbp+37h+var_40]; void **
0x180110000  mov     rcx, rbx; Handle
0x180110003  call    ?GetSecurity@CFspFileSystemOperations@@SAJPEAXKPEAPEAX@Z; CFspFileSystemOperations::GetSecurity(void *,ulong,void * *)
0x180110008  mov     [rbp+37h+var_90], eax
0x18011000b  test    eax, eax
0x18011000d  mov     eax, 417h
0x180110012  js      short loc_18010FFC7
0x180110014  mov     word ptr [rbp+37h+var_8C], ax
0x180110018  test    r12, r12
0x18011001b  jz      short loc_180110038
0x18011001d  mov     r8, r12; struct IFspInPlaceFile *
0x180110020  mov     rdx, rbx; void *
0x180110023  call    ?ValidateFileUnchanged@CNtfsFileSystemApplier@@AEAAJPEAXPEAUIFspInPlaceFile@@@Z; CNtfsFileSystemApplier::ValidateFileUnchanged(void *,IFspInPlaceFile *)
0x180110028  mov     [rbp+37h+var_90], eax
0x18011002b  test    eax, eax
0x18011002d  mov     eax, 420h
0x180110032  js      short loc_18010FFC7
0x180110034  mov     word ptr [rbp+37h+var_8C], ax
0x180110038  mov     rcx, rbx; FileHandle
0x18011003b  call    ?ClearReadOnly@CFspFileSystemOperations@@SAJPEAX@Z; CFspFileSystemOperations::ClearReadOnly(void *)
0x180110040  mov     [rbp+37h+var_90], eax
0x180110043  test    eax, eax
0x180110045  mov     eax, 425h
0x18011004a  js      loc_18010FFC7
0x180110050  mov     word ptr [rbp+37h+var_8C], ax
0x180110054  mov     rcx, rbx; Handle
0x180110057  call    cs:__imp_NtClose
0x18011005d  xor     ebx, ebx
0x18011005f  mov     [rbp+37h+arg_48], rbx
0x180110066  mov     r12, [rbp+37h+arg_8]
0x18011006a  mov     rax, [r12]
0x18011006e  lea     rdx, [rbp+37h+arg_48]
0x180110075  mov     rcx, r12
0x180110078  mov     rax, [rax+68h]
0x18011007c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110081  mov     [rbp+37h+var_90], eax
0x180110084  test    eax, eax
0x180110086  mov     eax, 437h
0x18011008b  js      loc_18010FE86
0x180110091  mov     word ptr [rbp+37h+var_8C], ax
0x180110095  mov     [rbp+37h+arg_28], ebx
0x180110098  mov     rax, [r12]
0x18011009c  lea     rdx, [rbp+37h+arg_28]
0x1801100a0  mov     rcx, r12
0x1801100a3  mov     rax, [rax+28h]
0x1801100a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801100ac  mov     [rbp+37h+var_90], eax
0x1801100af  test    eax, eax
0x1801100b1  mov     eax, 441h
0x1801100b6  js      loc_18010FE86
0x1801100bc  mov     word ptr [rbp+37h+var_8C], ax
0x1801100c0  test    byte ptr [rbp+37h+arg_28], 4
0x1801100c4  setnz   cl
0x1801100c7  bt      esi, 0Eh
0x1801100cb  setb    al
0x1801100ce  test    al, cl
0x1801100d0  jz      loc_18011017C
0x1801100d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801100dd  lea     rax, WPP_GLOBAL_Control
0x1801100e4  cmp     rcx, rax
0x1801100e7  jz      short loc_18011011A
0x1801100e9  test    dword ptr [rcx+44h], 100h
0x1801100f0  jz      short loc_18011011A
0x1801100f2  cmp     byte ptr [rcx+41h], 4
0x1801100f6  jb      short loc_18011011A
0x1801100f8  lea     edx, [rbx+17h]
0x1801100fb  mov     rax, [rbp+37h+arg_48]
0x180110102  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180110107  mov     r9, r14
0x18011010a  lea     r8, WPP_bfe3f9d07e6736223889f9787b891edb_Traceguids
0x180110111  mov     rcx, [rcx+38h]
0x180110115  call    WPP_SF_SS
0x18011011a  xor     edx, edx; dwReserved
0x18011011c  mov     rcx, r14; lpFileName
0x18011011f  call    cs:__imp_DecryptFileW
0x180110125  test    eax, eax
0x180110127  jnz     short loc_18011013B
0x180110129  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18011012e  mov     [rbp+37h+var_90], eax
0x180110131  mov     eax, 44Fh
0x180110136  jmp     loc_18010FE86
0x18011013b  mov     [rbp+37h+var_90], ebx
0x18011013e  mov     eax, 44Fh
0x180110143  mov     word ptr [rbp+37h+var_8C], ax
0x180110147  xor     edx, edx; dwReserved
0x180110149  mov     rcx, [rbp+37h+arg_48]; lpFileName
0x180110150  call    cs:__imp_DecryptFileW
0x180110156  test    eax, eax
0x180110158  jnz     short loc_18011016C
0x18011015a  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18011015f  mov     [rbp+37h+var_90], eax
0x180110162  mov     eax, 450h
0x180110167  jmp     loc_18010FE86
0x18011016c  mov     [rbp+37h+var_90], ebx
0x18011016f  mov     eax, 450h
0x180110174  mov     word ptr [rbp+37h+var_8C], ax
0x180110178  btr     esi, 0Eh
0x18011017c  test    r13, r13
0x18011017f  jz      short loc_1801101A6
0x180110181  test    r15, r15
0x180110184  jz      short loc_1801101A6
0x180110186  lea     rdx, [rbp+37h+var_60]; void **
0x18011018a  mov     rcx, rdi; SourceString
0x18011018d  call    ?OpenFileAttribute@CFspFileSystemOperations@@SAJPEBGPEAPEAX@Z; CFspFileSystemOperations::OpenFileAttribute(ushort const *,void * *)
0x180110192  mov     [rbp+37h+var_90], eax
0x180110195  test    eax, eax
0x180110197  mov     eax, 45Fh
0x18011019c  js      loc_18010FE86
0x1801101a2  mov     word ptr [rbp+37h+var_8C], ax
0x1801101a6  mov     [rsp+0E0h+var_A8], rbx
0x1801101ab  mov     qword ptr [rsp+0E0h+var_B0], rbx
0x1801101b0  mov     eax, 8
0x1801101b5  mov     [rsp+0E0h+var_B8], eax
  ... truncated ...
```
