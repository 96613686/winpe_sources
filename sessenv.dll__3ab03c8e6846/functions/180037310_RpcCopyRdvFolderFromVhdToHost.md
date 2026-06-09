# RpcCopyRdvFolderFromVhdToHost

- ea: `0x180037310`
- end: `0x180037633`
- name: `RpcCopyRdvFolderFromVhdToHost`
- size: `803`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180019b38`
- `0x18001a280`
- `0x18001a2a4`
- `0x180035bcc`
- `0x180035d40`
- `0x180035db4`
- `0x180035e20`
- `0x180035fdc`
- `0x180037310`
- `0x18004a578`
- `0x18004ad48`
- `0x18005a1cc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800375aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800375aa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003749a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003749a`

## string_xrefs

- `0x1800374c0`: `CreateDirectory failed: 0x%x in %s`
- `0x180037567`: `CopyFolder failed: 0x%x in %s`
- `0x18003750b`: `rdvFolderOnVhdPath.BuildPath failed: 0x%x in %s`
- `0x18003747f`: `rdvFolderOnHostPath.BuildPath failed: 0x%x in %s`
- `0x1800373f4`: `CheckAccessToRpcMethod failed: 0x%x in %s`
- `0x18003744f`: `Failed to mount VHD failed: 0x%x in %s`
- `0x180037367`: `RpcCopyRdvFolderFromVhdToHost`
- `0x18003752e`: `RDV: RpcCopyFolderFromVhdToHost, CopyFolder is called, rdvFolderOnVhdPath: %ws, rdvFolderOnHostPath: %ws`

## pseudocode

```c
__int64 __fastcall RpcCopyRdvFolderFromVhdToHost(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  const char *v8; // rdx
  _QWORD *v9; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // rdi
  int v11; // eax
  int v12; // eax
  const char *v13; // rdx
  const WCHAR *v14; // rax
  signed int LastError; // eax
  const unsigned __int16 *v16; // rax
  __int64 v17; // rax
  __int64 v18; // r10
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r10
  const unsigned __int16 *v21; // rax
  RdVhd::Util::CVhdHelper *v22; // rcx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  void **v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+44h] [rbp-BCh]
  int v28; // [rsp+4Ch] [rbp-B4h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+58h] [rbp-A8h]
  void **v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+6Ch] [rbp-94h]
  int v34; // [rsp+74h] [rbp-8Ch]
  __int64 v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  void **v37; // [rsp+88h] [rbp-78h] BYREF
  int v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+94h] [rbp-6Ch]
  int v40; // [rsp+9Ch] [rbp-64h]
  __int64 v41; // [rsp+A0h] [rbp-60h]
  int v42; // [rsp+A8h] [rbp-58h]
  _BYTE v43[592]; // [rsp+B0h] [rbp-50h] BYREF

  hObject = (HANDLE)-1LL;
  v39 = 128;
  v42 = 0x8000000;
  v30 = 0x8000000;
  v36 = 0x8000000;
  v41 = 0;
  v40 = 0;
  v38 = 0;
  v37 = &CPathString::`vftable';
  v27 = 128;
  v29 = 0;
  v28 = 0;
  v26 = 0;
  v25 = &CPathString::`vftable';
  v33 = 128;
  v35 = 0;
  v34 = 0;
  v32 = 0;
  v31 = &CPathString::`vftable';
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v43, a2, "RpcCopyRdvFolderFromVhdToHost");
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    v8 = "Invalid input parameters failed: 0x%x in %s";
    v7 = 2147942487LL;
    goto LABEL_26;
  }
  v5 = CSessEnvRpc::CheckAccessToRpcMethod(L"O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899010-3337817248-2959896732-3640118089-1866760602)");
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = "CheckAccessToRpcMethod failed: 0x%x in %s";
LABEL_26:
    _DbgPrintMessage(8, v8, v7, "RpcCopyRdvFolderFromVhdToHost");
    goto LABEL_27;
  }
  v9 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
  v10 = (void (__fastcall ***)(_QWORD, __int64))v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    _DbgPrintMessage(
      8,
      "Failed to allocate CVhdHelper failed: 0x%x in %s",
      2147942414LL,
      "RpcCopyRdvFolderFromVhdToHost");
    goto LABEL_27;
  }
  *v9 = &RdVhd::Util::CVhdHelper::`vftable';
  v11 = RdVhd::Util::CVhdHelper::MountVhdVolume(v9, a2, 1, &v37, &hObject);
  v6 = v11;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "Failed to mount VHD failed: 0x%x in %s", v11, "RpcCopyRdvFolderFromVhdToHost");
    goto LABEL_22;
  }
  v12 = CPathString::BuildPath((CPathString *)&v31, a3, L"rdvdata");
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = "rdvFolderOnHostPath.BuildPath failed: 0x%x in %s";
LABEL_20:
    _DbgPrintMessage(8, v13, (unsigned int)v12, "RpcCopyRdvFolderFromVhdToHost");
    goto LABEL_21;
  }
  v14 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v31);
  if ( CreateDirectoryW(v14, 0) )
    goto LABEL_15;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_15:
    v16 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v37);
    v12 = CPathString::BuildPath((CPathString *)&v25, v16, L"Windows");
    v6 = v12;
    if ( v12 < 0
      || (v12 = CPathString::BuildPath((CPathString *)&v25, (const struct CPathString *)&v25, L"rdvdata"),
          v6 = v12,
          v12 < 0) )
    {
      v13 = "rdvFolderOnVhdPath.BuildPath failed: 0x%x in %s";
      goto LABEL_20;
    }
    CBaseStringT<unsigned short>::PContents(&v31);
    v17 = CBaseStringT<unsigned short>::PContents(&v25);
    _DbgPrintMessage(
      8,
      "RDV: RpcCopyFolderFromVhdToHost, CopyFolder is called, rdvFolderOnVhdPath: %ws, rdvFolderOnHostPath: %ws",
      v17,
      v18);
    CBaseStringT<unsigned short>::PContents(&v31);
    v19 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
    v12 = CopyFolder(v19, v20);
    v6 = v12;
    if ( v12 < 0 )
    {
      v13 = "CopyFolder failed: 0x%x in %s";
      goto LABEL_20;
    }
  }
  else
  {
    _DbgPrintMessage(8, "CreateDirectory failed: 0x%x in %s", v6, "RpcCopyRdvFolderFromVhdToHost");
  }
LABEL_21:
  v21 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v37);
  RdVhd::Util::CVhdHelper::SetVolumeOffline(v22, v21);
LABEL_22:
  (**v10)(v10, 1);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_27:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v43);
  CPathString::~CPathString((CPathString *)&v31);
  CPathString::~CPathString((CPathString *)&v25);
  CPathString::~CPathString((CPathString *)&v37);
  return v6;
}

```

## disassembly

```asm
0x180037310  mov     [rsp-8+arg_0], rbx
0x180037315  push    rbp
0x180037316  push    rsi
0x180037317  push    rdi
0x180037318  push    r12
0x18003731a  push    r13
0x18003731c  push    r14
0x18003731e  push    r15
0x180037320  lea     rbp, [rsp-210h]
0x180037328  sub     rsp, 310h
0x18003732f  mov     rax, cs:__security_cookie
0x180037336  xor     rax, rsp
0x180037339  mov     [rbp+240h+var_40], rax
0x180037340  xor     r12d, r12d
0x180037343  mov     [rsp+340h+hObject], 0FFFFFFFFFFFFFFFFh
0x18003734c  mov     ecx, 8000000h
0x180037351  mov     [rbp+240h+var_2AC], 80h
0x180037359  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180037360  mov     [rbp+240h+var_298], ecx
0x180037363  mov     [rsp+340h+var_2E8], ecx
0x180037367  lea     r13, aRpccopyrdvfold; "RpcCopyRdvFolderFromVhdToHost"
0x18003736e  mov     [rbp+240h+var_2C0], ecx
0x180037371  mov     r14, r8
0x180037374  lea     rcx, [rbp+240h+var_290]; this
0x180037378  mov     [rbp+240h+var_2A0], r12
0x18003737c  mov     r8, r13; char *
0x18003737f  mov     [rbp+240h+var_2A4], r12d
0x180037383  mov     r15, rdx
0x180037386  mov     [rbp+240h+var_2B0], r12d
0x18003738a  mov     [rbp+240h+var_2B8], rax
0x18003738e  mov     [rsp+340h+var_2FC], 80h
0x180037397  mov     [rsp+340h+var_2F0], r12
0x18003739c  mov     [rsp+340h+var_2F4], r12d
0x1800373a1  mov     [rsp+340h+var_300], r12d
0x1800373a6  mov     [rsp+340h+var_308], rax
0x1800373ab  mov     [rsp+340h+var_2D4], 80h
0x1800373b4  mov     [rsp+340h+var_2C8], r12
0x1800373b9  mov     [rsp+340h+var_2CC], r12d
0x1800373be  mov     [rsp+340h+var_2D8], r12d
0x1800373c3  mov     [rsp+340h+var_2E0], rax
0x1800373c8  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800373cd  test    r15, r15
0x1800373d0  jz      loc_1800375C5
0x1800373d6  test    r14, r14
0x1800373d9  jz      loc_1800375C5
0x1800373df  lea     rcx, aOSygSydA0x0001_0; "O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899"...
0x1800373e6  call    ?CheckAccessToRpcMethod@CSessEnvRpc@@SAJPEBG@Z; CSessEnvRpc::CheckAccessToRpcMethod(ushort const *)
0x1800373eb  mov     ebx, eax
0x1800373ed  test    eax, eax
0x1800373ef  jns     short loc_180037400
0x1800373f1  mov     r8d, eax
0x1800373f4  lea     rdx, aCheckaccesstor; "CheckAccessToRpcMethod failed: 0x%x in "...
0x1800373fb  jmp     loc_1800375D4
0x180037400  mov     esi, 8
0x180037405  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003740c  mov     ecx, esi; unsigned __int64
0x18003740e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037413  mov     rdi, rax
0x180037416  test    rax, rax
0x180037419  jz      loc_1800375B2
0x18003741f  lea     rax, ??_7CVhdHelper@Util@RdVhd@@6B@; const RdVhd::Util::CVhdHelper::`vftable'
0x180037426  mov     rdx, r15
0x180037429  mov     [rdi], rax
0x18003742c  lea     r9, [rbp+240h+var_2B8]
0x180037430  lea     rax, [rsp+340h+hObject]
0x180037435  mov     rcx, rdi
0x180037438  lea     r8d, [rsi-7]
0x18003743c  mov     [rsp+340h+var_320], rax
0x180037441  call    ?MountVhdVolume@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@PEAVCPathString@@PEAPEAX2@Z; RdVhd::Util::CVhdHelper::MountVhdVolume(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,CPathString *,void * *,CPathString *)
0x180037446  mov     ebx, eax
0x180037448  test    eax, eax
0x18003744a  jns     short loc_180037465
0x18003744c  mov     r9, r13
0x18003744f  lea     rdx, aFailedToMountV; "Failed to mount VHD failed: 0x%x in %s"
0x180037456  mov     r8d, eax
0x180037459  mov     ecx, esi; int
0x18003745b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037460  jmp     loc_18003758C
0x180037465  lea     r8, aRdvdata; "rdvdata"
0x18003746c  mov     rdx, r14; unsigned __int16 *
0x18003746f  lea     rcx, [rsp+340h+var_2E0]; this
0x180037474  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180037479  mov     ebx, eax
0x18003747b  test    eax, eax
0x18003747d  jns     short loc_18003748B
0x18003747f  lea     rdx, aRdvfolderonhos; "rdvFolderOnHostPath.BuildPath failed: 0"...
0x180037486  jmp     loc_18003756E
0x18003748b  lea     rcx, [rsp+340h+var_2E0]
0x180037490  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037495  mov     rcx, rax; lpPathName
0x180037498  xor     edx, edx; lpSecurityAttributes
0x18003749a  call    cs:__imp_CreateDirectoryW
0x1800374a0  test    eax, eax
0x1800374a2  jnz     short loc_1800374CC
0x1800374a4  call    cs:__imp_GetLastError
0x1800374aa  mov     ebx, eax
0x1800374ac  test    eax, eax
0x1800374ae  jle     short loc_1800374B9
0x1800374b0  movzx   ebx, ax
0x1800374b3  or      ebx, 80070000h
0x1800374b9  test    ebx, ebx
0x1800374bb  jns     short loc_1800374CC
0x1800374bd  mov     r8d, ebx
0x1800374c0  lea     rdx, aCreatedirector_0; "CreateDirectory failed: 0x%x in %s"
0x1800374c7  jmp     loc_180037571
0x1800374cc  lea     rcx, [rbp+240h+var_2B8]
0x1800374d0  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800374d5  lea     r8, aWindows; "Windows"
0x1800374dc  mov     rdx, rax; unsigned __int16 *
0x1800374df  lea     rcx, [rsp+340h+var_308]; this
0x1800374e4  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x1800374e9  mov     ebx, eax
0x1800374eb  test    eax, eax
0x1800374ed  js      short loc_18003750B
0x1800374ef  lea     r8, aRdvdata; "rdvdata"
0x1800374f6  lea     rdx, [rsp+340h+var_308]; struct CPathString *
0x1800374fb  lea     rcx, [rsp+340h+var_308]; this
0x180037500  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x180037505  mov     ebx, eax
0x180037507  test    eax, eax
0x180037509  jns     short loc_180037514
0x18003750b  lea     rdx, aRdvfolderonvhd; "rdvFolderOnVhdPath.BuildPath failed: 0x"...
0x180037512  jmp     short loc_18003756E
0x180037514  lea     rcx, [rsp+340h+var_2E0]
0x180037519  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18003751e  lea     rcx, [rsp+340h+var_308]
0x180037523  mov     r10, rax
0x180037526  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18003752b  mov     r9, r10
0x18003752e  lea     rdx, aRdvRpccopyfold; "RDV: RpcCopyFolderFromVhdToHost, CopyFo"...
0x180037535  mov     r8, rax
0x180037538  mov     ecx, esi; int
0x18003753a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003753f  lea     rcx, [rsp+340h+var_2E0]
0x180037544  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037549  lea     rcx, [rsp+340h+var_308]
0x18003754e  mov     r10, rax
0x180037551  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037556  mov     rdx, r10; unsigned __int16 *
0x180037559  mov     rcx, rax; unsigned __int16 *
0x18003755c  call    ?CopyFolder@@YAJPEBG0@Z; CopyFolder(ushort const *,ushort const *)
0x180037561  mov     ebx, eax
0x180037563  test    eax, eax
0x180037565  jns     short loc_18003757B
0x180037567  lea     rdx, aCopyfolderFail; "CopyFolder failed: 0x%x in %s"
0x18003756e  mov     r8d, eax
0x180037571  mov     r9, r13
0x180037574  mov     ecx, esi; int
0x180037576  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003757b  lea     rcx, [rbp+240h+var_2B8]
0x18003757f  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037584  mov     rdx, rax; unsigned __int16 *
0x180037587  call    ?SetVolumeOffline@CVhdHelper@Util@RdVhd@@QEBAJPEBG@Z; RdVhd::Util::CVhdHelper::SetVolumeOffline(ushort const *)
0x18003758c  mov     rax, [rdi]
0x18003758f  mov     edx, 1
0x180037594  mov     rcx, rdi
0x180037597  mov     rax, [rax]
0x18003759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003759f  mov     rcx, [rsp+340h+hObject]; hObject
0x1800375a4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800375a8  jz      short loc_1800375E1
0x1800375aa  call    cs:__imp_CloseHandle
0x1800375b0  jmp     short loc_1800375E1
0x1800375b2  mov     ebx, 8007000Eh
0x1800375b7  lea     rdx, aFailedToAlloca; "Failed to allocate CVhdHelper failed: 0"...
0x1800375be  mov     r8d, ebx
0x1800375c1  mov     ecx, esi
0x1800375c3  jmp     short loc_1800375D9
0x1800375c5  mov     ebx, 80070057h
0x1800375ca  lea     rdx, aInvalidInputPa; "Invalid input parameters failed: 0x%x i"...
0x1800375d1  mov     r8d, ebx
0x1800375d4  mov     ecx, 8; int
0x1800375d9  mov     r9, r13
0x1800375dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800375e1  lea     rcx, [rbp+240h+var_290]; this
0x1800375e5  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800375ea  lea     rcx, [rsp+340h+var_2E0]; this
0x1800375ef  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800375f4  lea     rcx, [rsp+340h+var_308]; this
0x1800375f9  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800375fe  lea     rcx, [rbp+240h+var_2B8]; this
0x180037602  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180037607  mov     eax, ebx
0x180037609  mov     rcx, [rbp+240h+var_40]
0x180037610  xor     rcx, rsp; StackCookie
0x180037613  call    __security_check_cookie
0x180037618  mov     rbx, [rsp+340h+arg_0]
0x180037620  add     rsp, 310h
0x180037627  pop     r15
0x180037629  pop     r14
0x18003762b  pop     r13
0x18003762d  pop     r12
0x18003762f  pop     rdi
0x180037630  pop     rsi
0x180037631  pop     rbp
0x180037632  retn
```
