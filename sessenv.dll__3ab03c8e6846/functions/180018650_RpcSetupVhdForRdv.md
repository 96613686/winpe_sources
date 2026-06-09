# RpcSetupVhdForRdv

- ea: `0x180018650`
- end: `0x180018af9`
- name: `RpcSetupVhdForRdv`
- size: `1193`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, BYTE *, DWORD cbProvisionBinDataSize)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180012b90`
- `0x180012c40`
- `0x180018650`
- `0x180019b38`
- `0x18001a280`
- `0x18001a2a4`
- `0x180035bcc`
- `0x180035d40`
- `0x180035db4`
- `0x180035e20`
- `0x1800365a4`
- `0x180036ae0`
- `0x18004a7a4`
- `0x18004ad48`
- `0x18005a1cc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a6d`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800188bf`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800188bf`
- `netjoin!NetRequestOfflineDomainJoin` at `0x180018986`
- `netjoin!NetRequestOfflineDomainJoin` at `0x180018986`

## string_xrefs

- `0x18001876a`: `CheckAccessToRpcMethod failed: 0x%x in %s`
- `0x1800187c9`: `Failed to mount VHD failed: 0x%x in %s`
- `0x1800187fa`: `Failed to build source file path failed: 0x%x in %s`
- `0x180018a0b`: `Failed to build target path failed: 0x%x in %s`
- `0x1800189ed`: `Failed to move source file failed: 0x%x in %s`
- `0x18001890c`: `RDV: RpcSetupVhdForRdv, strSourceFilePath:%ws, strTargetFilePath:%ws, strVhdVolumeRootPath:%ws, szFileName:%ws, szRelativeTargetPath: %ws.`
- `0x180018a02`: `Failed to build Windows path failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcSetupVhdForRdv(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        BYTE *a6,
        DWORD cbProvisionBinDataSize)
{
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rax
  __int64 v13; // r8
  void (__fastcall ***v14)(_QWORD, __int64); // rdi
  int v15; // eax
  int v16; // eax
  __int64 i; // rsi
  int v18; // eax
  const WCHAR *v19; // rax
  LPCWSTR v20; // r10
  signed int LastError; // eax
  __int64 v22; // rax
  __int64 v23; // r10
  __int64 v24; // r11
  const unsigned __int16 *v25; // rax
  const WCHAR *v26; // rax
  signed int v27; // eax
  const unsigned __int16 *v28; // rax
  int v29; // eax
  const char *v30; // rdx
  const unsigned __int16 *v31; // rax
  RdVhd::Util::CVhdHelper *v32; // rcx
  const char *v33; // rdx
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  void **v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+54h] [rbp-ACh]
  int v39; // [rsp+5Ch] [rbp-A4h]
  __int64 v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v42; // [rsp+70h] [rbp-90h]
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  void **v44; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+8Ch] [rbp-74h]
  int v47; // [rsp+94h] [rbp-6Ch]
  __int64 v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+A0h] [rbp-60h]
  void **v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B4h] [rbp-4Ch]
  int v53; // [rsp+BCh] [rbp-44h]
  __int64 v54; // [rsp+C0h] [rbp-40h]
  int v55; // [rsp+C8h] [rbp-38h]
  BYTE *pProvisionBinData; // [rsp+D0h] [rbp-30h]
  _BYTE v57[592]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v58[40]; // [rsp+330h] [rbp+230h] BYREF

  v42 = a5;
  pProvisionBinData = a6;
  hObject = (HANDLE)-1LL;
  `vector constructor iterator'(v58, 0x28u, 8u, (void *(*)(void *))CPathString::CPathString);
  v35 = 8;
  v55 = 0x8000000;
  v49 = 0x8000000;
  v52 = 128;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v50 = &CPathString::`vftable';
  v46 = 128;
  v48 = 0;
  v47 = 0;
  v45 = 0;
  v44 = &CPathString::`vftable';
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v57, (int)&CPathString::`vftable', "RpcSetupVhdForRdv");
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v11 = -2147024809;
    v33 = "Invalid input parameters failed: 0x%x in %s";
    goto LABEL_44;
  }
  v10 = CSessEnvRpc::CheckAccessToRpcMethod(L"O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899010-3337817248-2959896732-3640118089-1866760602)");
  v11 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "CheckAccessToRpcMethod failed: 0x%x in %s", (unsigned int)v10, "RpcSetupVhdForRdv");
    goto LABEL_45;
  }
  v12 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
  v14 = (void (__fastcall ***)(_QWORD, __int64))v12;
  if ( !v12 )
  {
    v11 = -2147024882;
    v33 = "Failed to allocate CVhdHelper failed: 0x%x in %s";
LABEL_44:
    _DbgPrintMessage(8, v33, v11, "RpcSetupVhdForRdv");
    goto LABEL_45;
  }
  *v12 = &RdVhd::Util::CVhdHelper::`vftable';
  v15 = RdVhd::Util::CVhdHelper::MountVhdVolume(v12, a2, v13, v58, &v35, &hObject);
  v11 = v15;
  if ( v15 >= 0 )
  {
    v16 = CPathString::BuildPath((CPathString *)&v50, a4, a3);
    v11 = v16;
    if ( v16 >= 0 )
    {
      for ( i = 0; (unsigned int)i < v35; i = (unsigned int)(i + 1) )
      {
        v38 = 128;
        v40 = 0;
        v39 = 0;
        v41 = 0x8000000;
        v37 = 0;
        v36 = &CPathString::`vftable';
        v18 = CPathString::BuildPath((CPathString *)&v36, (const struct CPathString *)&v58[5 * i], v42);
        v11 = v18;
        if ( v18 < 0
          || (v18 = CPathString::BuildPath((CPathString *)&v36, (const struct CPathString *)&v36, a3), v11 = v18, v18 < 0) )
        {
          v30 = "Failed to build target path failed: 0x%x in %s";
          goto LABEL_35;
        }
        CBaseStringT<unsigned short>::PContents(&v36);
        v19 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v50);
        if ( !CopyFileExW(v19, v20, 0, 0, 0, 0) )
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          if ( (v11 & 0x80000000) != 0 )
          {
            _DbgPrintMessage(8, "Failed to move source file failed: 0x%x in %s", v11, "RpcSetupVhdForRdv");
LABEL_36:
            CPathString::~CPathString((CPathString *)&v36);
            goto LABEL_38;
          }
        }
        CBaseStringT<unsigned short>::PContents(&v58[5 * i]);
        CBaseStringT<unsigned short>::PContents(&v36);
        v22 = CBaseStringT<unsigned short>::PContents(&v50);
        _DbgPrintMessage(
          8,
          "RDV: RpcSetupVhdForRdv, strSourceFilePath:%ws, strTargetFilePath:%ws, strVhdVolumeRootPath:%ws, szFileName:%ws"
          ", szRelativeTargetPath: %ws.",
          v22,
          v23,
          v24,
          a3,
          v42);
        v18 = CPathString::BuildPath((CPathString *)&v44, (const struct CPathString *)&v58[5 * i], L"Windows");
        v11 = v18;
        if ( v18 < 0 )
        {
          v30 = "Failed to build Windows path failed: 0x%x in %s";
LABEL_35:
          _DbgPrintMessage(8, v30, (unsigned int)v18, "RpcSetupVhdForRdv");
          goto LABEL_36;
        }
        if ( cbProvisionBinDataSize )
        {
          v25 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v44);
          if ( (unsigned int)FolderExists(v25) )
          {
            v26 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v44);
            v27 = NetRequestOfflineDomainJoin(pProvisionBinData, cbProvisionBinDataSize, 0, v26);
            v11 = v27;
            if ( v27 > 0 )
              v11 = (unsigned __int16)v27 | 0x80070000;
            if ( (v11 & 0x80000000) != 0 )
            {
              _DbgPrintMessage(8, "NetRequestOfflineDomainJoin Failed... failed: 0x%x in %s", v11, "RpcSetupVhdForRdv");
              goto LABEL_36;
            }
          }
        }
        v28 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v58[5 * i]);
        v29 = PrepareRdvFolder(v28, a4);
        if ( (int)(v29 + 0x80000000) >= 0 && v29 != -2147024894 )
          _DbgPrintMessage(8, "RDV: PrepareRdvFolder failed -- 0x%x.", v29);
        CPathString::~CPathString((CPathString *)&v36);
      }
      v11 = 0;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to build source file path failed: 0x%x in %s", (unsigned int)v16, "RpcSetupVhdForRdv");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to mount VHD failed: 0x%x in %s", (unsigned int)v15, "RpcSetupVhdForRdv");
  }
LABEL_38:
  if ( v35 )
  {
    v31 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(v58);
    RdVhd::Util::CVhdHelper::SetVolumeOffline(v32, v31);
  }
  (**v14)(v14, 1);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_45:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v57);
  CPathString::~CPathString((CPathString *)&v44);
  CPathString::~CPathString((CPathString *)&v50);
  `vector destructor iterator'(v58, 0x28u, 8u, (void (*)(void *))CPathString::~CPathString);
  return v11;
}

```

## disassembly

```asm
0x180018650  push    rbp
0x180018652  push    rbx
0x180018653  push    rsi
0x180018654  push    rdi
0x180018655  push    r12
0x180018657  push    r14
0x180018659  push    r15
0x18001865b  lea     rbp, [rsp-380h]
0x180018663  sub     rsp, 480h
0x18001866a  mov     rax, cs:__security_cookie
0x180018671  xor     rax, rsp
0x180018674  mov     [rbp+3B0h+var_40], rax
0x18001867b  mov     rax, [rbp+3B0h+arg_28]
0x180018682  lea     rcx, [rbp+3B0h+var_180]; void *
0x180018689  mov     rbx, [rbp+3B0h+arg_20]
0x180018690  mov     rsi, rdx
0x180018693  mov     edx, 28h ; '('; unsigned __int64
0x180018698  mov     [rsp+4B0h+var_440], rbx
0x18001869d  mov     r12, r9
0x1800186a0  mov     [rbp+3B0h+pProvisionBinData], rax
0x1800186a4  mov     r14, r8
0x1800186a7  mov     [rsp+4B0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800186b0  lea     r9, ??0CPathString@@QEAA@XZ; void *(*)(void *)
0x1800186b7  lea     r8d, [rdx-20h]; unsigned __int64
0x1800186bb  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800186c0  mov     ecx, 8000000h
0x1800186c5  mov     [rsp+4B0h+var_470], 8
0x1800186cd  lea     rdx, ??_7CPathString@@6B@; int
0x1800186d4  mov     [rbp+3B0h+var_3E8], ecx
0x1800186d7  mov     [rbp+3B0h+var_410], ecx
0x1800186da  lea     r15, aRpcsetupvhdfor; "RpcSetupVhdForRdv"
0x1800186e1  lea     rcx, [rbp+3B0h+var_3D0]; this
0x1800186e5  mov     [rbp+3B0h+var_3FC], 80h
0x1800186ed  mov     r8, r15; char *
0x1800186f0  mov     [rbp+3B0h+var_3F0], 0
0x1800186f8  mov     [rbp+3B0h+var_3F4], 0
0x1800186ff  mov     [rbp+3B0h+var_400], 0
0x180018706  mov     [rbp+3B0h+var_408], rdx
0x18001870a  mov     [rbp+3B0h+var_424], 80h
0x180018712  mov     [rbp+3B0h+var_418], 0
0x18001871a  mov     [rbp+3B0h+var_41C], 0
0x180018721  mov     [rbp+3B0h+var_428], 0
0x180018728  mov     [rbp+3B0h+var_430], rdx
0x18001872c  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180018731  test    rsi, rsi
0x180018734  jz      loc_180018A83
0x18001873a  test    r14, r14
0x18001873d  jz      loc_180018A83
0x180018743  test    r12, r12
0x180018746  jz      loc_180018A83
0x18001874c  test    rbx, rbx
0x18001874f  jz      loc_180018A83
0x180018755  lea     rcx, aOSygSydA0x0001_0; "O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899"...
0x18001875c  call    ?CheckAccessToRpcMethod@CSessEnvRpc@@SAJPEBG@Z; CSessEnvRpc::CheckAccessToRpcMethod(ushort const *)
0x180018761  mov     ebx, eax
0x180018763  test    eax, eax
0x180018765  jns     short loc_180018776
0x180018767  mov     r8d, eax
0x18001876a  lea     rdx, aCheckaccesstor; "CheckAccessToRpcMethod failed: 0x%x in "...
0x180018771  jmp     loc_180018A92
0x180018776  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001877d  mov     ecx, 8; unsigned __int64
0x180018782  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018787  mov     rdi, rax
0x18001878a  test    rax, rax
0x18001878d  jz      loc_180018A75
0x180018793  lea     rax, ??_7CVhdHelper@Util@RdVhd@@6B@; const RdVhd::Util::CVhdHelper::`vftable'
0x18001879a  mov     rdx, rsi
0x18001879d  mov     [rdi], rax
0x1800187a0  lea     r9, [rbp+3B0h+var_180]
0x1800187a7  lea     rax, [rsp+4B0h+hObject]
0x1800187ac  mov     rcx, rdi
0x1800187af  mov     qword ptr [rsp+4B0h+dwCopyFlags], rax
0x1800187b4  lea     rax, [rsp+4B0h+var_470]
0x1800187b9  mov     [rsp+4B0h+pbCancel], rax
0x1800187be  call    ?MountVhdVolume@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@QEAVCPathString@@PEAKPEAPEAXPEAV6@@Z; RdVhd::Util::CVhdHelper::MountVhdVolume(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,CPathString * const,ulong *,void * *,CPathString *)
0x1800187c3  mov     ebx, eax
0x1800187c5  test    eax, eax
0x1800187c7  jns     short loc_1800187E5
0x1800187c9  lea     rdx, aFailedToMountV; "Failed to mount VHD failed: 0x%x in %s"
0x1800187d0  mov     r8d, eax
0x1800187d3  mov     r9, r15
0x1800187d6  mov     ecx, 8; int
0x1800187db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800187e0  jmp     loc_180018A34
0x1800187e5  mov     r8, r14; unsigned __int16 *
0x1800187e8  lea     rcx, [rbp+3B0h+var_408]; this
0x1800187ec  mov     rdx, r12; unsigned __int16 *
0x1800187ef  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x1800187f4  mov     ebx, eax
0x1800187f6  test    eax, eax
0x1800187f8  jns     short loc_180018803
0x1800187fa  lea     rdx, aFailedToBuildS; "Failed to build source file path failed"...
0x180018801  jmp     short loc_1800187D0
0x180018803  xor     esi, esi
0x180018805  cmp     esi, [rsp+4B0h+var_470]
0x180018809  jnb     loc_180018A32
0x18001880f  mov     r8, [rsp+4B0h+var_440]; unsigned __int16 *
0x180018814  lea     rcx, [rsi+rsi*4]
0x180018818  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18001881f  mov     [rsp+4B0h+var_45C], 80h
0x180018828  lea     r15, [rbp+3B0h+var_180]
0x18001882f  mov     [rsp+4B0h+var_450], 0
0x180018838  lea     r15, [r15+rcx*8]
0x18001883c  mov     [rsp+4B0h+var_454], 0
0x180018844  mov     rdx, r15; struct CPathString *
0x180018847  mov     [rsp+4B0h+var_448], 8000000h
0x18001884f  lea     rcx, [rsp+4B0h+var_468]; this
0x180018854  mov     [rsp+4B0h+var_460], 0
0x18001885c  mov     [rsp+4B0h+var_468], rax
0x180018861  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x180018866  mov     ebx, eax
0x180018868  test    eax, eax
0x18001886a  js      loc_180018A0B
0x180018870  mov     r8, r14; unsigned __int16 *
0x180018873  lea     rdx, [rsp+4B0h+var_468]; struct CPathString *
0x180018878  lea     rcx, [rsp+4B0h+var_468]; this
0x18001887d  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x180018882  mov     ebx, eax
0x180018884  test    eax, eax
0x180018886  js      loc_180018A0B
0x18001888c  lea     rcx, [rsp+4B0h+var_468]
0x180018891  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018896  lea     rcx, [rbp+3B0h+var_408]
0x18001889a  mov     r10, rax
0x18001889d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800188a2  xor     r9d, r9d; lpData
0x1800188a5  mov     [rsp+4B0h+dwCopyFlags], 0; dwCopyFlags
0x1800188ad  xor     r8d, r8d; lpProgressRoutine
0x1800188b0  mov     [rsp+4B0h+pbCancel], 0; pbCancel
0x1800188b9  mov     rdx, r10; lpNewFileName
0x1800188bc  mov     rcx, rax; lpExistingFileName
0x1800188bf  call    cs:__imp_CopyFileExW
0x1800188c5  test    eax, eax
0x1800188c7  jnz     short loc_1800188E6
0x1800188c9  call    cs:__imp_GetLastError
0x1800188cf  mov     ebx, eax
0x1800188d1  test    eax, eax
0x1800188d3  jle     short loc_1800188DE
0x1800188d5  movzx   ebx, ax
0x1800188d8  or      ebx, 80070000h
0x1800188de  test    ebx, ebx
0x1800188e0  js      loc_1800189EA
0x1800188e6  mov     rcx, r15
0x1800188e9  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800188ee  lea     rcx, [rsp+4B0h+var_468]
0x1800188f3  mov     r11, rax
0x1800188f6  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800188fb  lea     rcx, [rbp+3B0h+var_408]
0x1800188ff  mov     r10, rax
0x180018902  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018907  mov     rcx, [rsp+4B0h+var_440]
0x18001890c  lea     rdx, aRdvRpcsetupvhd; "RDV: RpcSetupVhdForRdv, strSourceFilePa"...
0x180018913  mov     [rsp+4B0h+var_480], rcx
0x180018918  mov     r9, r10
0x18001891b  mov     qword ptr [rsp+4B0h+dwCopyFlags], r14
0x180018920  mov     ecx, 8; int
0x180018925  mov     r8, rax
0x180018928  mov     [rsp+4B0h+pbCancel], r11
0x18001892d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018932  lea     r8, aWindows; "Windows"
0x180018939  mov     rdx, r15; struct CPathString *
0x18001893c  lea     rcx, [rbp+3B0h+var_430]; this
0x180018940  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x180018945  mov     ebx, eax
0x180018947  test    eax, eax
0x180018949  js      loc_180018A02
0x18001894f  cmp     [rbp+3B0h+cbProvisionBinDataSize], 0
0x180018956  jz      short loc_18001899F
0x180018958  lea     rcx, [rbp+3B0h+var_430]
0x18001895c  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018961  mov     rcx, rax; unsigned __int16 *
0x180018964  call    ?FolderExists@@YAHPEBG@Z; FolderExists(ushort const *)
0x180018969  test    eax, eax
0x18001896b  jz      short loc_18001899F
0x18001896d  lea     rcx, [rbp+3B0h+var_430]
0x180018971  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018976  mov     edx, [rbp+3B0h+cbProvisionBinDataSize]; cbProvisionBinDataSize
0x18001897c  mov     r9, rax; lpWindowsPath
0x18001897f  mov     rcx, [rbp+3B0h+pProvisionBinData]; pProvisionBinData
0x180018983  xor     r8d, r8d; dwOptions
0x180018986  call    cs:__imp_NetRequestOfflineDomainJoin
0x18001898c  mov     ebx, eax
0x18001898e  test    eax, eax
0x180018990  jle     short loc_18001899B
0x180018992  movzx   ebx, ax
0x180018995  or      ebx, 80070000h
0x18001899b  test    ebx, ebx
0x18001899d  js      short loc_1800189F6
0x18001899f  mov     rcx, r15
0x1800189a2  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800189a7  mov     rcx, rax; unsigned __int16 *
0x1800189aa  mov     rdx, r12; unsigned __int16 *
0x1800189ad  call    ?PrepareRdvFolder@@YAJPEBG0@Z; PrepareRdvFolder(ushort const *,ushort const *)
0x1800189b2  mov     ebx, 80000000h
0x1800189b7  lea     ecx, [rax+rbx]
0x1800189ba  test    ebx, ecx
0x1800189bc  jnz     short loc_1800189D9
0x1800189be  cmp     eax, 80070002h
0x1800189c3  jz      short loc_1800189D9
0x1800189c5  mov     r8d, eax
0x1800189c8  lea     rdx, aRdvPreparerdvf; "RDV: PrepareRdvFolder failed -- 0x%x."
0x1800189cf  mov     ecx, 8; int
0x1800189d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800189d9  lea     rcx, [rsp+4B0h+var_468]; this
0x1800189de  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800189e3  inc     esi
0x1800189e5  jmp     loc_180018805
0x1800189ea  mov     r8d, ebx
0x1800189ed  lea     rdx, aFailedToMoveSo; "Failed to move source file failed: 0x%x"...
0x1800189f4  jmp     short loc_180018A15
0x1800189f6  mov     r8d, ebx
0x1800189f9  lea     rdx, aNetrequestoffl_0; "NetRequestOfflineDomainJoin Failed... f"...
0x180018a00  jmp     short loc_180018A15
0x180018a02  lea     rdx, aFailedToBuildW_0; "Failed to build Windows path failed: 0x"...
0x180018a09  jmp     short loc_180018A12
0x180018a0b  lea     rdx, aFailedToBuildT; "Failed to build target path failed: 0x%"...
0x180018a12  mov     r8d, eax
0x180018a15  lea     r9, aRpcsetupvhdfor; "RpcSetupVhdForRdv"
0x180018a1c  mov     ecx, 8; int
0x180018a21  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018a26  lea     rcx, [rsp+4B0h+var_468]; this
0x180018a2b  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018a30  jmp     short loc_180018A34
0x180018a32  xor     ebx, ebx
0x180018a34  cmp     [rsp+4B0h+var_470], 0
0x180018a39  jbe     short loc_180018A4F
0x180018a3b  lea     rcx, [rbp+3B0h+var_180]
0x180018a42  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018a47  mov     rdx, rax; unsigned __int16 *
0x180018a4a  call    ?SetVolumeOffline@CVhdHelper@Util@RdVhd@@QEBAJPEBG@Z; RdVhd::Util::CVhdHelper::SetVolumeOffline(ushort const *)
0x180018a4f  mov     rax, [rdi]
0x180018a52  mov     edx, 1
0x180018a57  mov     rcx, rdi
0x180018a5a  mov     rax, [rax]
0x180018a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a62  mov     rcx, [rsp+4B0h+hObject]; hObject
0x180018a67  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180018a6b  jz      short loc_180018A9F
0x180018a6d  call    cs:__imp_CloseHandle
0x180018a73  jmp     short loc_180018A9F
0x180018a75  mov     ebx, 8007000Eh
0x180018a7a  lea     rdx, aFailedToAlloca; "Failed to allocate CVhdHelper failed: 0"...
0x180018a81  jmp     short loc_180018A8F
0x180018a83  mov     ebx, 80070057h
0x180018a88  lea     rdx, aInvalidInputPa; "Invalid input parameters failed: 0x%x i"...
0x180018a8f  mov     r8d, ebx
0x180018a92  mov     r9, r15
0x180018a95  mov     ecx, 8; int
0x180018a9a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018a9f  lea     rcx, [rbp+3B0h+var_3D0]; this
0x180018aa3  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180018aa8  lea     rcx, [rbp+3B0h+var_430]; this
0x180018aac  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018ab1  lea     rcx, [rbp+3B0h+var_408]; this
0x180018ab5  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018aba  mov     edx, 28h ; '('; unsigned __int64
0x180018abf  lea     r9, ??1CPathString@@QEAA@XZ; void (*)(void *)
0x180018ac6  lea     rcx, [rbp+3B0h+var_180]; void *
0x180018acd  lea     r8d, [rdx-20h]; unsigned __int64
0x180018ad1  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180018ad6  mov     eax, ebx
0x180018ad8  mov     rcx, [rbp+3B0h+var_40]
0x180018adf  xor     rcx, rsp; StackCookie
0x180018ae2  call    __security_check_cookie
0x180018ae7  add     rsp, 480h
0x180018aee  pop     r15
0x180018af0  pop     r14
0x180018af2  pop     r12
0x180018af4  pop     rdi
0x180018af5  pop     rsi
0x180018af6  pop     rbx
0x180018af7  pop     rbp
0x180018af8  retn
```
