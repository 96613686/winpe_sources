# RpcDeleteFileFromVHD

- ea: `0x1800377c0`
- end: `0x180037a21`
- name: `RpcDeleteFileFromVHD`
- size: `609`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180019b38`
- `0x18001a280`
- `0x18001a2a4`
- `0x180035bcc`
- `0x180035d40`
- `0x180035e20`
- `0x1800377c0`
- `0x18004a578`
- `0x18004ad48`
- `0x18005a1cc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800379aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800379aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003793c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003793c`

## string_xrefs

- `0x180037896`: `CheckAccessToRpcMethod failed: 0x%x in %s`
- `0x1800378f2`: `Failed to mount VHD failed: 0x%x in %s`
- `0x180037926`: `Failed to build source file path failed: 0x%x in %s`
- `0x180037808`: `RpcDeleteFileFromVHD`
- `0x180037962`: `Failed to delete file failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcDeleteFileFromVHD(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rdi
  int v9; // eax
  int v10; // eax
  const WCHAR *v11; // rax
  signed int LastError; // eax
  const unsigned __int16 *v13; // rax
  RdVhd::Util::CVhdHelper *v14; // rcx
  const char *v15; // rdx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  void **v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+44h] [rbp-BCh]
  int v21; // [rsp+4Ch] [rbp-B4h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  int v23; // [rsp+58h] [rbp-A8h]
  void **v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+6Ch] [rbp-94h]
  int v27; // [rsp+74h] [rbp-8Ch]
  __int64 v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[592]; // [rsp+90h] [rbp-70h] BYREF

  hObject = (HANDLE)-1LL;
  v23 = 0x8000000;
  v29 = 0x8000000;
  v20 = 128;
  v22 = 0;
  v21 = 0;
  v19 = 0;
  v18 = &CPathString::`vftable';
  v26 = 128;
  v28 = 0;
  v27 = 0;
  v25 = 0;
  v24 = &CPathString::`vftable';
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v30, a2, "RpcDeleteFileFromVHD");
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    v15 = "Invalid input parameters failed: 0x%x in %s";
    goto LABEL_22;
  }
  v5 = CSessEnvRpc::CheckAccessToRpcMethod(L"O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899010-3337817248-2959896732-3640118089-1866760602)");
  v6 = v5;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "CheckAccessToRpcMethod failed: 0x%x in %s", (unsigned int)v5, "RpcDeleteFileFromVHD");
    goto LABEL_23;
  }
  v7 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
  v8 = (void (__fastcall ***)(_QWORD, __int64))v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    v15 = "Failed to allocate CVhdHelper failed: 0x%x in %s";
LABEL_22:
    _DbgPrintMessage(8, v15, v6, "RpcDeleteFileFromVHD");
    goto LABEL_23;
  }
  *v7 = &RdVhd::Util::CVhdHelper::`vftable';
  v9 = RdVhd::Util::CVhdHelper::MountVhdVolume(v7, a2, 1, &v18, &hObject);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v10 = CPathString::BuildPath((CPathString *)&v24, (const struct CPathString *)&v18, a3);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v11 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v24);
      if ( DeleteFileW(v11) )
        goto LABEL_16;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
LABEL_16:
        v6 = 0;
      else
        _DbgPrintMessage(8, "Failed to delete file failed: 0x%x in %s", v6, "RpcDeleteFileFromVHD");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "Failed to build source file path failed: 0x%x in %s",
        (unsigned int)v10,
        "RpcDeleteFileFromVHD");
    }
    v13 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v18);
    RdVhd::Util::CVhdHelper::SetVolumeOffline(v14, v13);
  }
  else
  {
    _DbgPrintMessage(8, "Failed to mount VHD failed: 0x%x in %s", v9, "RpcDeleteFileFromVHD");
  }
  (**v8)(v8, 1);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_23:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v30);
  CPathString::~CPathString((CPathString *)&v24);
  CPathString::~CPathString((CPathString *)&v18);
  return v6;
}

```

## disassembly

```asm
0x1800377c0  mov     [rsp-8+arg_0], rbx
0x1800377c5  push    rbp
0x1800377c6  push    rsi
0x1800377c7  push    rdi
0x1800377c8  push    r12
0x1800377ca  push    r14
0x1800377cc  lea     rbp, [rsp-1F0h]
0x1800377d4  sub     rsp, 2F0h
0x1800377db  mov     rax, cs:__security_cookie
0x1800377e2  xor     rax, rsp
0x1800377e5  mov     [rbp+210h+var_30], rax
0x1800377ec  mov     ecx, 8000000h
0x1800377f1  mov     [rsp+310h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800377fa  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180037801  mov     [rsp+310h+var_2B8], ecx
0x180037805  mov     [rbp+210h+var_290], ecx
0x180037808  lea     r12, aRpcdeletefilef; "RpcDeleteFileFromVHD"
0x18003780f  mov     rsi, r8
0x180037812  mov     [rsp+310h+var_2CC], 80h
0x18003781b  lea     rcx, [rbp+210h+var_280]; this
0x18003781f  mov     [rsp+310h+var_2C0], 0
0x180037828  mov     r8, r12; char *
0x18003782b  mov     [rsp+310h+var_2C4], 0
0x180037833  mov     r14, rdx
0x180037836  mov     [rsp+310h+var_2D0], 0
0x18003783e  mov     [rsp+310h+var_2D8], rax
0x180037843  mov     [rsp+310h+var_2A4], 80h
0x18003784c  mov     [rsp+310h+var_298], 0
0x180037855  mov     [rsp+310h+var_29C], 0
0x18003785d  mov     [rsp+310h+var_2A8], 0
0x180037865  mov     [rsp+310h+var_2B0], rax
0x18003786a  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18003786f  test    r14, r14
0x180037872  jz      loc_1800379C0
0x180037878  test    rsi, rsi
0x18003787b  jz      loc_1800379C0
0x180037881  lea     rcx, aOSygSydA0x0001_0; "O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899"...
0x180037888  call    ?CheckAccessToRpcMethod@CSessEnvRpc@@SAJPEBG@Z; CSessEnvRpc::CheckAccessToRpcMethod(ushort const *)
0x18003788d  mov     ebx, eax
0x18003788f  test    eax, eax
0x180037891  jns     short loc_1800378A2
0x180037893  mov     r8d, eax
0x180037896  lea     rdx, aCheckaccesstor; "CheckAccessToRpcMethod failed: 0x%x in "...
0x18003789d  jmp     loc_1800379CF
0x1800378a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800378a9  mov     ecx, 8; unsigned __int64
0x1800378ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800378b3  mov     rdi, rax
0x1800378b6  test    rax, rax
0x1800378b9  jz      loc_1800379B2
0x1800378bf  lea     rax, ??_7CVhdHelper@Util@RdVhd@@6B@; const RdVhd::Util::CVhdHelper::`vftable'
0x1800378c6  mov     r8d, 1
0x1800378cc  mov     [rdi], rax
0x1800378cf  lea     r9, [rsp+310h+var_2D8]
0x1800378d4  lea     rax, [rsp+310h+hObject]
0x1800378d9  mov     rdx, r14
0x1800378dc  mov     rcx, rdi
0x1800378df  mov     [rsp+310h+var_2F0], rax
0x1800378e4  call    ?MountVhdVolume@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@PEAVCPathString@@PEAPEAX2@Z; RdVhd::Util::CVhdHelper::MountVhdVolume(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,CPathString *,void * *,CPathString *)
0x1800378e9  mov     ebx, eax
0x1800378eb  test    eax, eax
0x1800378ed  jns     short loc_18003790B
0x1800378ef  mov     r9, r12
0x1800378f2  lea     rdx, aFailedToMountV; "Failed to mount VHD failed: 0x%x in %s"
0x1800378f9  mov     r8d, eax
0x1800378fc  mov     ecx, 8; int
0x180037901  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037906  jmp     loc_18003798C
0x18003790b  mov     r8, rsi; unsigned __int16 *
0x18003790e  lea     rdx, [rsp+310h+var_2D8]; struct CPathString *
0x180037913  lea     rcx, [rsp+310h+var_2B0]; this
0x180037918  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x18003791d  mov     ebx, eax
0x18003791f  test    eax, eax
0x180037921  jns     short loc_18003792F
0x180037923  mov     r8d, eax
0x180037926  lea     rdx, aFailedToBuildS; "Failed to build source file path failed"...
0x18003792d  jmp     short loc_180037969
0x18003792f  lea     rcx, [rsp+310h+var_2B0]
0x180037934  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037939  mov     rcx, rax; lpFileName
0x18003793c  call    cs:__imp_DeleteFileW
0x180037942  test    eax, eax
0x180037944  jnz     short loc_180037978
0x180037946  call    cs:__imp_GetLastError
0x18003794c  mov     ebx, eax
0x18003794e  test    eax, eax
0x180037950  jle     short loc_18003795B
0x180037952  movzx   ebx, ax
0x180037955  or      ebx, 80070000h
0x18003795b  test    ebx, ebx
0x18003795d  jns     short loc_180037978
0x18003795f  mov     r8d, ebx
0x180037962  lea     rdx, aFailedToDelete; "Failed to delete file failed: 0x%x in %"...
0x180037969  mov     r9, r12
0x18003796c  mov     ecx, 8; int
0x180037971  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037976  jmp     short loc_18003797A
0x180037978  xor     ebx, ebx
0x18003797a  lea     rcx, [rsp+310h+var_2D8]
0x18003797f  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180037984  mov     rdx, rax; unsigned __int16 *
0x180037987  call    ?SetVolumeOffline@CVhdHelper@Util@RdVhd@@QEBAJPEBG@Z; RdVhd::Util::CVhdHelper::SetVolumeOffline(ushort const *)
0x18003798c  mov     rax, [rdi]
0x18003798f  mov     edx, 1
0x180037994  mov     rcx, rdi
0x180037997  mov     rax, [rax]
0x18003799a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003799f  mov     rcx, [rsp+310h+hObject]; hObject
0x1800379a4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800379a8  jz      short loc_1800379DC
0x1800379aa  call    cs:__imp_CloseHandle
0x1800379b0  jmp     short loc_1800379DC
0x1800379b2  mov     ebx, 8007000Eh
0x1800379b7  lea     rdx, aFailedToAlloca; "Failed to allocate CVhdHelper failed: 0"...
0x1800379be  jmp     short loc_1800379CC
0x1800379c0  mov     ebx, 80070057h
0x1800379c5  lea     rdx, aInvalidInputPa; "Invalid input parameters failed: 0x%x i"...
0x1800379cc  mov     r8d, ebx
0x1800379cf  mov     r9, r12
0x1800379d2  mov     ecx, 8; int
0x1800379d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800379dc  lea     rcx, [rbp+210h+var_280]; this
0x1800379e0  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800379e5  lea     rcx, [rsp+310h+var_2B0]; this
0x1800379ea  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800379ef  lea     rcx, [rsp+310h+var_2D8]; this
0x1800379f4  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800379f9  mov     eax, ebx
0x1800379fb  mov     rcx, [rbp+210h+var_30]
0x180037a02  xor     rcx, rsp; StackCookie
0x180037a05  call    __security_check_cookie
0x180037a0a  mov     rbx, [rsp+310h+arg_0]
0x180037a12  add     rsp, 2F0h
0x180037a19  pop     r14
0x180037a1b  pop     r12
0x180037a1d  pop     rdi
0x180037a1e  pop     rsi
0x180037a1f  pop     rbp
0x180037a20  retn
```
