# CCloudFileSystemApplier::CreatePlaceholder(IFspFile *,ulong,int,IFileConcurrencyBlob * *)

- ea: `0x18008f34c`
- end: `0x18008fa9e`
- name: `?CreatePlaceholder@CCloudFileSystemApplier@@AEAAJPEAUIFspFile@@KHPEAPEAUIFileConcurrencyBlob@@@Z`
- size: `1874`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IFspFile *, __int64, __int64, struct IFileConcurrencyBlob **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18008f1b8`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007e10`
- `0x180009188`
- `0x1800091ac`
- `0x180011314`
- `0x18001137c`
- `0x180058d88`
- `0x18008b670`
- `0x18008d358`
- `0x18008f34c`
- `0x1800908d8`
- `0x180096cf0`
- `0x180098eec`
- `0x18009976c`
- `0x18009a5c0`
- `0x1800bb298`
- `0x1800bb594`
- `0x1800bb748`
- `0x1800bbe18`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008f9cc`
- `KERNEL32!CloseHandle` at `0x18008f9cc`
- `cldapi!CfUpdatePlaceholder` at `0x18008f84b`
- `cldapi!CfUpdatePlaceholder` at `0x18008f920`
- `cldapi!CfUpdatePlaceholder` at `0x18008f84b`
- `cldapi!CfUpdatePlaceholder` at `0x18008f920`
- `cldapi!CfCreatePlaceholders` at `0x18008f78f`
- `cldapi!CfCreatePlaceholders` at `0x18008f78f`

## string_xrefs

- `0x18008f3ef`: `CCloudFileSystemApplier::CreatePlaceholder`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CCloudFileSystemApplier::CreatePlaceholder(
        const unsigned __int16 **this,
        struct IFspFile *a2,
        __int64 a3,
        __int64 a4,
        struct IFileConcurrencyBlob **a5)
{
  _DWORD *v7; // rax
  char v8; // cl
  int v9; // r14d
  __int16 v10; // ax
  __int64 v11; // rax
  bool v12; // sf
  __int16 v13; // ax
  int v14; // ecx
  unsigned int v15; // r8d
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // ebx
  int AbsoluteFileName; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh]
  char v22; // [rsp+58h] [rbp-A8h]
  const char *v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR SourceString; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *Src; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v33; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v35[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+E8h] [rbp-18h]
  __int64 v38; // [rsp+F0h] [rbp-10h]
  struct _FILE_ID_128 *v39; // [rsp+F8h] [rbp-8h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  __int128 v41; // [rsp+120h] [rbp+20h] BYREF
  __int128 v42; // [rsp+130h] [rbp+30h] BYREF
  __int64 v43; // [rsp+140h] [rbp+40h]
  struct _FILE_ID_128 v44; // [rsp+148h] [rbp+48h] BYREF
  __int128 v45; // [rsp+158h] [rbp+58h] BYREF
  __int128 v46; // [rsp+168h] [rbp+68h]
  __int128 v47; // [rsp+178h] [rbp+78h]

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (v7[17] & 0x100) == 0 || (v8 = 1, *((_BYTE *)v7 + 65) < 6u) )
    v8 = 0;
  AbsoluteFileName = 0;
  v21 = 637;
  v22 = v8;
  v23 = "CCloudFileSystemApplier::CreatePlaceholder";
  v24 = 0;
  memset_0(v35, 0, 0x58u);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v33 = 0;
  SourceString = 0;
  v30 = 0;
  Src = 0;
  v34 = 0;
  v32 = 0;
  v28 = 0;
  hObject = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    AbsoluteFileName = -2147024809;
    HIWORD(v21) = 655;
LABEL_55:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids, SourceString);
    }
    CCloudFileSystemApplier::DeleteSingle((CCloudFileSystemApplier *)this, SourceString, 0);
    goto LABEL_60;
  }
  v9 = 0;
  AbsoluteFileName = 0;
  LOWORD(v21) = 655;
  v25 = 0;
  v31 = 0;
  AbsoluteFileName = (**(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *))a2)(
                       a2,
                       &GUID_a1ad7a7a_ca8a_45c2_9b7c_4a8cbf1cc067,
                       &v25);
  v10 = 661;
  if ( AbsoluteFileName < 0 )
    goto LABEL_12;
  LOWORD(v21) = 661;
  AbsoluteFileName = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v25 + 24LL))(v25, &v31);
  v10 = 663;
  if ( AbsoluteFileName < 0 )
    goto LABEL_12;
  LOWORD(v21) = 663;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(
                       this[4],
                       v31,
                       L"{d9d80b89-eada-4aab-aeeb-1715a4d6f27b}.TMP",
                       &v33);
  v10 = 664;
  if ( AbsoluteFileName < 0 )
    goto LABEL_12;
  LOWORD(v21) = 664;
  v11 = -1;
  do
    ++v11;
  while ( v31[v11] );
  if ( v11 )
  {
    AbsoluteFileName = CPathUtilitiesBase<92>::CombinePathParts(&v30, 2, this[4], v31);
    v12 = AbsoluteFileName < 0;
    v10 = 669;
  }
  else
  {
    AbsoluteFileName = CSyncCoreStringUtils::StringCopyAlloc(this[4], &v30);
    v12 = AbsoluteFileName < 0;
    v10 = 673;
  }
  if ( v12 )
  {
LABEL_12:
    HIWORD(v21) = v10;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
    goto LABEL_49;
  }
  LOWORD(v21) = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids, v30);
  }
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
  AbsoluteFileName = CPathUtilities::GetNormalizedNtPath(v33, (unsigned __int16 **)&SourceString);
  v13 = 679;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 679;
  CCloudFileSystemApplier::DeleteSingle((CCloudFileSystemApplier *)this, SourceString, 0);
  v35[0] = L"{d9d80b89-eada-4aab-aeeb-1715a4d6f27b}.TMP";
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v41);
  v13 = 686;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 686;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, &v42);
  v13 = 687;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 687;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, char *))(*(_QWORD *)a2 + 88LL))(a2, (char *)&v42 + 8);
  v13 = 688;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 688;
  v35[1] = v41;
  v36 = v42;
  v35[2] = -1;
  v14 = (*(__int64 (__fastcall **)(struct IFspFile *, int *))(*(_QWORD *)a2 + 40LL))(a2, &v28);
  AbsoluteFileName = v14;
  v13 = 695;
  if ( v14 < 0 )
    goto LABEL_26;
  LOWORD(v21) = 695;
  LODWORD(v43) = v28;
  AbsoluteFileName = v14;
  if ( (v28 & 0x10) != 0 )
  {
    AbsoluteFileName = -2147024809;
    HIWORD(v21) = 699;
    goto LABEL_49;
  }
  AbsoluteFileName = 0;
  LOWORD(v21) = 699;
  LODWORD(v43) = v28 | 0x20;
  v37 = v28 | 0x20;
  AbsoluteFileName = (*(__int64 (__fastcall **)(struct IFspFile *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v32);
  v13 = 706;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 706;
  v38 = v32;
  v39 = &v44;
  v40 = 16;
  AbsoluteFileName = CfCreatePlaceholders(v30, v35, 1);
  v13 = 718;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 718;
  AbsoluteFileName = CFspCloudFileSystemOperations::CreateFileW(
                       SourceString,
                       0x130181u,
                       v15,
                       0,
                       0x2Au,
                       1u,
                       8u,
                       &hObject);
  v13 = 728;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 728;
  AbsoluteFileName = CFspCloudFileSystemOperations::GetFileId(hObject, &v44);
  v13 = 731;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 731;
  AbsoluteFileName = CfUpdatePlaceholder(hObject, 0, &v44, 16, 0, 0, 0, 0, 0);
  v13 = 734;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 734;
  AbsoluteFileName = CPathUtilities::GetAbsoluteFileName(this[3], a2, &Src);
  v13 = 737;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 737;
  AbsoluteFileName = CFspCloudFileSystemOperations::Rename(hObject, Src);
  v13 = 740;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 740;
  v9 = 1;
  *(_QWORD *)&v45 = v41;
  v46 = v42;
  *((_QWORD *)&v45 + 1) = -1;
  LODWORD(v47) = v43;
  *((_QWORD *)&v47 + 1) = v32;
  AbsoluteFileName = CfUpdatePlaceholder(hObject, &v45, &v44, 16, 0, 0, 2, 0, 0);
  v13 = 761;
  if ( AbsoluteFileName < 0 )
    goto LABEL_26;
  LOWORD(v21) = 761;
  if ( a5 )
  {
    AbsoluteFileName = CCloudFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                         (CCloudFileSystemApplier *)this,
                         &hObject,
                         Src,
                         0,
                         a5);
    v13 = 767;
    if ( AbsoluteFileName >= 0 )
    {
      LOWORD(v21) = 767;
      goto LABEL_45;
    }
LABEL_26:
    HIWORD(v21) = v13;
    goto LABEL_49;
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SqDii(*((_QWORD *)WPP_GLOBAL_Control + 7), v16, v17, (_DWORD)Src, (char)a2, v43, v41, v42);
  }
LABEL_49:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( AbsoluteFileName < 0 && !v9 )
    goto LABEL_55;
LABEL_60:
  v18 = AbsoluteFileName;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&Src);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v30);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v33);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&AbsoluteFileName);
  return v18;
}

```

## disassembly

```asm
0x18008f34c  mov     [rsp-8+arg_10], rbx
0x18008f351  push    rbp
0x18008f352  push    rsi
0x18008f353  push    rdi
0x18008f354  push    r12
0x18008f356  push    r13
0x18008f358  push    r14
0x18008f35a  push    r15
0x18008f35c  lea     rbp, [rsp-90h]
0x18008f364  sub     rsp, 190h
0x18008f36b  mov     rax, cs:__security_cookie
0x18008f372  xor     rax, rsp
0x18008f375  mov     [rbp+0C0h+var_38], rax
0x18008f37c  mov     rbx, rdx
0x18008f37f  mov     rsi, rcx
0x18008f382  mov     rdi, [rbp+0C0h+arg_20]
0x18008f389  lea     r12, WPP_GLOBAL_Control
0x18008f390  mov     r13d, 100h
0x18008f396  mov     rax, cs:WPP_GLOBAL_Control
0x18008f39d  cmp     rax, r12
0x18008f3a0  jz      short loc_18008F3CA
0x18008f3a2  test    [rax+44h], r13d
0x18008f3a6  jz      short loc_18008F3CA
0x18008f3a8  cmp     byte ptr [rax+41h], 6
0x18008f3ac  jb      short loc_18008F3CA
0x18008f3ae  mov     edx, 13h
0x18008f3b3  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18008f3ba  mov     rcx, [rax+38h]
0x18008f3be  call    WPP_SF_
0x18008f3c3  mov     rax, cs:WPP_GLOBAL_Control
0x18008f3ca  xor     r15d, r15d
0x18008f3cd  test    [rax+44h], r13d
0x18008f3d1  jz      short loc_18008F3DB
0x18008f3d3  cmp     byte ptr [rax+41h], 6
0x18008f3d7  mov     cl, 1
0x18008f3d9  jnb     short loc_18008F3DE
0x18008f3db  mov     cl, r15b
0x18008f3de  mov     [rsp+1C0h+var_170], r15d
0x18008f3e3  mov     [rsp+1C0h+var_16C], 27Dh
0x18008f3eb  mov     [rsp+1C0h+var_168], cl
0x18008f3ef  lea     rax, aCcloudfilesyst_71; "CCloudFileSystemApplier::CreatePlacehol"...
0x18008f3f6  mov     [rsp+1C0h+var_160], rax
0x18008f3fb  mov     [rsp+1C0h+var_158], r15
0x18008f400  xor     edx, edx; Val
0x18008f402  lea     r8d, [rdx+58h]; Size
0x18008f406  lea     rcx, [rbp+0C0h+var_100]; void *
0x18008f40a  call    memset_0
0x18008f40f  xorps   xmm0, xmm0
0x18008f412  movups  [rbp+0C0h+var_68], xmm0
0x18008f416  movups  [rbp+0C0h+var_58], xmm0
0x18008f41a  movups  [rbp+0C0h+var_48], xmm0
0x18008f41e  xorps   xmm1, xmm1
0x18008f421  xor     eax, eax
0x18008f423  movups  [rbp+0C0h+var_A0], xmm1
0x18008f427  movups  [rbp+0C0h+var_90], xmm1
0x18008f42b  mov     [rbp+0C0h+var_80], rax
0x18008f42f  movups  xmmword ptr [rbp+0C0h+var_78.Identifier], xmm0
0x18008f433  mov     [rbp+0C0h+var_110], r15
0x18008f437  mov     [rbp+0C0h+SourceString], r15
0x18008f43b  mov     [rbp+0C0h+var_128], r15
0x18008f43f  mov     [rbp+0C0h+Src], r15
0x18008f443  mov     [rbp+0C0h+var_108], r15
0x18008f447  mov     [rbp+0C0h+var_118], r15
0x18008f44b  mov     [rbp+0C0h+var_138], r15d
0x18008f44f  mov     [rsp+1C0h+hObject], r15
0x18008f454  test    rdi, rdi
0x18008f457  jz      short loc_18008F45C
0x18008f459  mov     [rdi], r15
0x18008f45c  mov     eax, [rsp+1C0h+var_170]
0x18008f460  mov     [rsp+1C0h+var_170], eax
0x18008f464  mov     eax, 28Fh
0x18008f469  test    rbx, rbx
0x18008f46c  jz      loc_18008F9E5
0x18008f472  mov     r14d, r15d
0x18008f475  mov     [rsp+1C0h+var_170], r15d
0x18008f47a  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f47f  mov     [rsp+1C0h+var_150], r15
0x18008f484  mov     [rbp+0C0h+var_120], r15
0x18008f488  mov     rax, [rbx]
0x18008f48b  lea     r8, [rsp+1C0h+var_150]
0x18008f490  lea     rdx, _GUID_a1ad7a7a_ca8a_45c2_9b7c_4a8cbf1cc067
0x18008f497  mov     rcx, rbx
0x18008f49a  mov     rax, [rax]
0x18008f49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4a2  mov     [rsp+1C0h+var_170], eax
0x18008f4a6  mov     [rsp+1C0h+var_170], eax
0x18008f4aa  test    eax, eax
0x18008f4ac  mov     eax, 295h
0x18008f4b1  jns     short loc_18008F4C7
0x18008f4b3  mov     word ptr [rsp+1C0h+var_16C+2], ax
0x18008f4b8  lea     rcx, [rsp+1C0h+var_150]
0x18008f4bd  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18008f4c2  jmp     loc_18008F9C2
0x18008f4c7  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f4cc  mov     rcx, [rsp+1C0h+var_150]
0x18008f4d1  mov     rax, [rcx]
0x18008f4d4  lea     rdx, [rbp+0C0h+var_120]
0x18008f4d8  mov     rax, [rax+18h]
0x18008f4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4e1  mov     [rsp+1C0h+var_170], eax
0x18008f4e5  mov     [rsp+1C0h+var_170], eax
0x18008f4e9  test    eax, eax
0x18008f4eb  mov     eax, 297h
0x18008f4f0  js      short loc_18008F4B3
0x18008f4f2  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f4f7  lea     r9, [rbp+0C0h+var_110]; unsigned __int16 **
0x18008f4fb  lea     r12, aD9d80b89Eada4a; "{d9d80b89-eada-4aab-aeeb-1715a4d6f27b}."...
0x18008f502  mov     r8, r12; unsigned __int16 *
0x18008f505  mov     rdx, [rbp+0C0h+var_120]; unsigned __int16 *
0x18008f509  mov     rcx, [rsi+20h]; unsigned __int16 *
0x18008f50d  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBG00PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,ushort const *,ushort const *,ushort * *)
0x18008f512  mov     [rsp+1C0h+var_170], eax
0x18008f516  mov     [rsp+1C0h+var_170], eax
0x18008f51a  test    eax, eax
0x18008f51c  mov     eax, 298h
0x18008f521  jns     short loc_18008F53E
0x18008f523  mov     word ptr [rsp+1C0h+var_16C+2], ax
0x18008f528  lea     rcx, [rsp+1C0h+var_150]
0x18008f52d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18008f532  lea     r12, WPP_GLOBAL_Control
0x18008f539  jmp     loc_18008F9C2
0x18008f53e  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f543  mov     r9, [rbp+0C0h+var_120]
0x18008f547  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008f54b  inc     rax
0x18008f54e  cmp     [r9+rax*2], r15w
0x18008f553  jnz     short loc_18008F54B
0x18008f555  mov     rcx, [rsi+20h]; unsigned __int16 *
0x18008f559  test    rax, rax
0x18008f55c  jz      loc_18008F5F4
0x18008f562  mov     r8, rcx
0x18008f565  mov     edx, 2
0x18008f56a  lea     rcx, [rbp+0C0h+var_128]
0x18008f56e  call    ?CombinePathParts@?$CPathUtilitiesBase@$0FM@@@SAJPEAPEAGKZZ; CPathUtilitiesBase<92>::CombinePathParts(ushort * *,ulong,...)
0x18008f573  mov     [rsp+1C0h+var_170], eax
0x18008f577  mov     [rsp+1C0h+var_170], eax
0x18008f57b  test    eax, eax
0x18008f57d  mov     eax, 29Dh
0x18008f582  js      short loc_18008F523
0x18008f584  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f589  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f590  lea     rax, WPP_GLOBAL_Control
0x18008f597  cmp     rcx, rax
0x18008f59a  jz      short loc_18008F5C2
0x18008f59c  test    [rcx+44h], r13d
0x18008f5a0  jz      short loc_18008F5C2
0x18008f5a2  cmp     byte ptr [rcx+41h], 4
0x18008f5a6  jb      short loc_18008F5C2
0x18008f5a8  mov     edx, 14h
0x18008f5ad  mov     r9, [rbp+0C0h+var_128]
0x18008f5b1  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18008f5b8  mov     rcx, [rcx+38h]
0x18008f5bc  call    WPP_SF_S
0x18008f5c1  nop
0x18008f5c2  lea     rcx, [rsp+1C0h+var_150]
0x18008f5c7  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18008f5cc  lea     rdx, [rbp+0C0h+SourceString]; unsigned __int16 **
0x18008f5d0  mov     rcx, [rbp+0C0h+var_110]; unsigned __int16 *
0x18008f5d4  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x18008f5d9  mov     [rsp+1C0h+var_170], eax
0x18008f5dd  mov     [rsp+1C0h+var_170], eax
0x18008f5e1  test    eax, eax
0x18008f5e3  mov     eax, 2A7h
0x18008f5e8  jns     short loc_18008F611
0x18008f5ea  mov     word ptr [rsp+1C0h+var_16C+2], ax
0x18008f5ef  jmp     loc_18008F532
0x18008f5f4  lea     rdx, [rbp+0C0h+var_128]; unsigned __int16 **
0x18008f5f8  call    ?StringCopyAlloc@CSyncCoreStringUtils@@SAJPEBGPEAPEAG@Z; CSyncCoreStringUtils::StringCopyAlloc(ushort const *,ushort * *)
0x18008f5fd  mov     [rsp+1C0h+var_170], eax
0x18008f601  mov     [rsp+1C0h+var_170], eax
0x18008f605  test    eax, eax
0x18008f607  mov     eax, 2A1h
0x18008f60c  jmp     loc_18008F582
0x18008f611  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f616  xor     r8d, r8d; struct IFspInPlaceFile *
0x18008f619  mov     rdx, [rbp+0C0h+SourceString]; unsigned __int16 *
0x18008f61d  mov     rcx, rsi; this
0x18008f620  call    ?DeleteSingle@CCloudFileSystemApplier@@AEAAJPEBGPEAUIFspInPlaceFile@@@Z; CCloudFileSystemApplier::DeleteSingle(ushort const *,IFspInPlaceFile *)
0x18008f625  mov     [rbp+0C0h+var_100], r12
0x18008f629  mov     rax, [rbx]
0x18008f62c  lea     rdx, [rbp+0C0h+var_A0]
0x18008f630  mov     rcx, rbx
0x18008f633  mov     rax, [rax+38h]
0x18008f637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f63c  mov     [rsp+1C0h+var_170], eax
0x18008f640  mov     [rsp+1C0h+var_170], eax
0x18008f644  test    eax, eax
0x18008f646  mov     eax, 2AEh
0x18008f64b  js      short loc_18008F5EA
0x18008f64d  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f652  mov     rax, [rbx]
0x18008f655  lea     rdx, [rbp+0C0h+var_90]
0x18008f659  mov     rcx, rbx
0x18008f65c  mov     rax, [rax+30h]
0x18008f660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f665  mov     [rsp+1C0h+var_170], eax
0x18008f669  mov     [rsp+1C0h+var_170], eax
0x18008f66d  test    eax, eax
0x18008f66f  mov     eax, 2AFh
0x18008f674  js      loc_18008F5EA
0x18008f67a  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f67f  mov     rax, [rbx]
0x18008f682  lea     rdx, [rbp+0C0h+var_90+8]
0x18008f686  mov     rcx, rbx
0x18008f689  mov     rax, [rax+58h]
0x18008f68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f692  mov     [rsp+1C0h+var_170], eax
0x18008f696  mov     [rsp+1C0h+var_170], eax
0x18008f69a  test    eax, eax
0x18008f69c  mov     eax, 2B0h
0x18008f6a1  js      loc_18008F5EA
0x18008f6a7  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f6ac  mov     rax, qword ptr [rbp+0C0h+var_A0]
0x18008f6b0  mov     [rbp+0C0h+var_F8], rax
0x18008f6b4  mov     rax, qword ptr [rbp+0C0h+var_90]
0x18008f6b8  mov     qword ptr [rbp+0C0h+var_E8], rax
0x18008f6bc  mov     rax, qword ptr [rbp+0C0h+var_90+8]
0x18008f6c0  mov     qword ptr [rbp+0C0h+var_E8+8], rax
0x18008f6c4  mov     [rbp+0C0h+var_F0], 0FFFFFFFFFFFFFFFFh
0x18008f6cc  mov     rax, [rbx]
0x18008f6cf  lea     rdx, [rbp+0C0h+var_138]
0x18008f6d3  mov     rcx, rbx
0x18008f6d6  mov     rax, [rax+28h]
0x18008f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6df  mov     ecx, eax
0x18008f6e1  mov     [rsp+1C0h+var_170], eax
0x18008f6e5  mov     [rsp+1C0h+var_170], eax
0x18008f6e9  test    eax, eax
0x18008f6eb  mov     eax, 2B7h
0x18008f6f0  js      loc_18008F5EA
0x18008f6f6  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f6fb  mov     eax, [rbp+0C0h+var_138]
0x18008f6fe  mov     dword ptr [rbp+0C0h+var_80], eax
0x18008f701  mov     [rsp+1C0h+var_170], ecx
0x18008f705  mov     r12d, 10h
0x18008f70b  mov     ecx, 2BBh
0x18008f710  test    r12b, al
0x18008f713  jz      short loc_18008F727
0x18008f715  mov     [rsp+1C0h+var_170], 80070057h
0x18008f71d  mov     word ptr [rsp+1C0h+var_16C+2], cx
0x18008f722  jmp     loc_18008F532
0x18008f727  mov     [rsp+1C0h+var_170], r15d
0x18008f72c  mov     word ptr [rsp+1C0h+var_16C], cx
0x18008f731  or      eax, 20h
0x18008f734  mov     dword ptr [rbp+0C0h+var_80], eax
0x18008f737  mov     [rbp+0C0h+var_D8], eax
0x18008f73a  mov     rax, [rbx]
0x18008f73d  lea     rdx, [rbp+0C0h+var_118]
0x18008f741  mov     rcx, rbx
0x18008f744  mov     rax, [rax+40h]
0x18008f748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f74d  mov     [rsp+1C0h+var_170], eax
0x18008f751  mov     [rsp+1C0h+var_170], eax
0x18008f755  test    eax, eax
0x18008f757  mov     eax, 2C2h
0x18008f75c  js      loc_18008F5EA
0x18008f762  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f767  mov     rax, [rbp+0C0h+var_118]
0x18008f76b  mov     [rbp+0C0h+var_D0], rax
0x18008f76f  lea     rax, [rbp+0C0h+var_78]
0x18008f773  mov     [rbp+0C0h+var_C8], rax
0x18008f777  mov     [rbp+0C0h+var_C0], r12
0x18008f77b  mov     qword ptr [rsp+1C0h+var_1A0], r15
0x18008f780  xor     r9d, r9d
0x18008f783  lea     r8d, [r9+1]
0x18008f787  lea     rdx, [rbp+0C0h+var_100]
0x18008f78b  mov     rcx, [rbp+0C0h+var_128]
0x18008f78f  call    cs:__imp_CfCreatePlaceholders
0x18008f795  mov     [rsp+1C0h+var_170], eax
0x18008f799  mov     [rsp+1C0h+var_170], eax
0x18008f79d  test    eax, eax
0x18008f79f  mov     eax, 2CEh
0x18008f7a4  js      loc_18008F5EA
0x18008f7aa  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f7af  lea     rax, [rsp+1C0h+hObject]
0x18008f7b4  mov     [rsp+1C0h+var_188], rax; void **
0x18008f7b9  mov     [rsp+1C0h+var_190], 8; unsigned int
0x18008f7c1  mov     [rsp+1C0h+var_198], 1; ULONG
0x18008f7c9  mov     [rsp+1C0h+var_1A0], 2Ah ; '*'; ULONG
0x18008f7d1  xor     r9d, r9d; unsigned int
0x18008f7d4  mov     edx, 130181h; DesiredAccess
0x18008f7d9  mov     rcx, [rbp+0C0h+SourceString]; SourceString
0x18008f7dd  call    ?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18008f7e2  mov     [rsp+1C0h+var_170], eax
0x18008f7e6  mov     [rsp+1C0h+var_170], eax
0x18008f7ea  test    eax, eax
0x18008f7ec  mov     eax, 2D8h
0x18008f7f1  js      loc_18008F5EA
0x18008f7f7  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f7fc  lea     rdx, [rbp+0C0h+var_78]; struct _FILE_ID_128 *
0x18008f800  mov     rcx, [rsp+1C0h+hObject]; FileHandle
0x18008f805  call    ?GetFileId@CFspCloudFileSystemOperations@@SAJPEAXPEAU_FILE_ID_128@@@Z; CFspCloudFileSystemOperations::GetFileId(void *,_FILE_ID_128 *)
0x18008f80a  mov     [rsp+1C0h+var_170], eax
0x18008f80e  mov     [rsp+1C0h+var_170], eax
0x18008f812  test    eax, eax
0x18008f814  mov     eax, 2DBh
0x18008f819  js      loc_18008F5EA
0x18008f81f  mov     word ptr [rsp+1C0h+var_16C], ax
0x18008f824  mov     [rsp+1C0h+var_180], r15
0x18008f829  mov     [rsp+1C0h+var_188], r15
  ... truncated ...
```
