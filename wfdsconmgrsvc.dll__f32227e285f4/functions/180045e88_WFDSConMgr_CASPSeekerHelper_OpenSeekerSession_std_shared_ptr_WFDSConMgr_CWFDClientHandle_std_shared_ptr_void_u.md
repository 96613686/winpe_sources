# WFDSConMgr::CASPSeekerHelper::OpenSeekerSession(std::shared_ptr<WFDSConMgr::CWFDClientHandle>,std::shared_ptr<void>,ushort const *,uchar const (&)[6],ulong)

- ea: `0x180045e88`
- end: `0x180046241`
- name: `?OpenSeekerSession@CASPSeekerHelper@WFDSConMgr@@QEAAXV?$shared_ptr@VCWFDClientHandle@WFDSConMgr@@@std@@V?$shared_ptr@X@4@PEBGAEAY05$$CBEK@Z`
- size: `953`
- prototype: `__int64 __usercall@<rax>(WFDSConMgr::CASPSeekerHelper *this@<rcx>, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18005a6e0`

## callees

- `0x18000421c`
- `0x18000475c`
- `0x180004ca8`
- `0x180006740`
- `0x180006c60`
- `0x180008a10`
- `0x180029f8c`
- `0x1800440f4`
- `0x180044514`
- `0x180045e88`
- `0x1800462a0`
- `0x1800465b8`
- `0x18005c888`
- `0x18006d010`

## string_xrefs

- `0x180046216`: `Bad parameters to OpenSeekerSession`
- `0x180045f36`: `WFDSConMgr::CASPSeekerHelper::OpenSeekerSession`
- `0x180045f6c`: `WFDSConMgr::CASPSeekerHelper::OpenSeekerSession`
- `0x18004603a`: `WFDSConMgr::CASPSeekerHelper::OpenSeekerSession`
- `0x18004622f`: `WFDSConMgr::CASPSeekerHelper::OpenSeekerSession`
- `0x180045f1d`: `ASP Session was already canceled`
- `0x180045f53`: `Cannot call OpenSeekerSession multiple times`
- `0x180046021`: `Failure in OpenSeekerSession, bailing out`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall WFDSConMgr::CASPSeekerHelper::OpenSeekerSession(
        WFDSConMgr::CASPSeekerHelper *this,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  struct WFDSConMgr::IASPListenerSpecific *v13; // rdi
  int v14; // ebx
  _QWORD *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  _QWORD *v18; // r10
  _QWORD *v19; // r11
  struct WFDSConMgr::IASPListenerSpecific *v20; // rdi
  unsigned int v21; // edx
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rcx
  std::_Ref_count_base *v24; // rcx
  _DWORD *v25; // [rsp+58h] [rbp-B0h]
  WFDSConMgr::CASPHandle *v26; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-A0h]
  _QWORD v28[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v29; // [rsp+88h] [rbp-80h]
  __int64 v30[3]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v31[3]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v36[72]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v37; // [rsp+170h] [rbp+68h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_d165b0dc1f223b1ad60133bc0034f705_Traceguids, this);
  }
  if ( !a4 || !*a2 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CASPSeekerHelper::OpenSeekerSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\asphelper.cpp",
      136,
      L"Bad parameters to OpenSeekerSession",
      this);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v36,
    (RTL_SRWLOCK *)this + 7);
  if ( *((_BYTE *)this + 64) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CASPSeekerHelper::OpenSeekerSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\asphelper.cpp",
      143,
      L"ASP Session was already canceled",
      this);
  if ( *((_BYTE *)this + 96) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CASPSeekerHelper::OpenSeekerSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\asphelper.cpp",
      148,
      L"Cannot call OpenSeekerSession multiple times",
      this);
  if ( !*((_QWORD *)this + 5) )
    WFDSConMgr::CASPSeekerHelper::OpenWFDHandle(this);
  v37 = 0;
  v10 = a5;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, int, char *, __int64 *))(**((_QWORD **)this + 1) + 32LL))(
          *((_QWORD *)this + 1),
          *(_QWORD *)(*((_QWORD *)this + 5) + 32LL),
          0,
          a4,
          a5,
          a6,
          (char *)this + 108,
          &v37);
  v12 = *((_QWORD *)this + 2);
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v26 = (WFDSConMgr::CASPHandle *)*((_QWORD *)this + 1);
  v28[1] = v26;
  v28[0] = *((_QWORD *)this + 2);
  v28[2] = v28[0];
  v27 = v37;
  v29 = v37;
  if ( v11 )
    WFDSConMgr::CException::Throw(
      v11,
      "WFDSConMgr::CASPSeekerHelper::OpenSeekerSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\asphelper.cpp",
      169,
      L"Failure in OpenSeekerSession, bailing out",
      this);
  *(_DWORD *)((char *)this + 97) = *(_DWORD *)v10;
  *(_WORD *)((char *)this + 101) = *(_WORD *)(v10 + 4);
  *((_DWORD *)this + 26) = a6;
  v13 = (struct WFDSConMgr::IASPListenerSpecific *)operator new(0xB0u);
  v31[2] = v13;
  v14 = *((_DWORD *)this + 27);
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v32, a3);
  v29 = 0;
  v30[0] = (__int64)v26;
  v30[1] = v28[0];
  *(_OWORD *)&v28[1] = 0;
  v30[2] = v27;
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v33, (_QWORD *)this + 3);
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v34, a2);
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(&v35, (_QWORD *)this + 5);
  v15 = std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(v31, (_QWORD *)this + 1);
  v20 = WFDSConMgr::CASPHandle::CASPHandle(v13, v15, v16, v17, v18, v30, v19, a5, a6, v14);
  v25 = operator new(0x18u);
  *(_OWORD *)v25 = 0;
  v25[2] = 1;
  v25[3] = 1;
  *(_QWORD *)v25 = &std::_Ref_count<WFDSConMgr::CASPHandle>::`vftable';
  *((_QWORD *)v25 + 2) = v20;
  v26 = 0;
  std::_Temporary_owner<WFDSConMgr::CASPHandle>::~_Temporary_owner<WFDSConMgr::CASPHandle>(&v26, v21);
  *((_QWORD *)this + 14) = v20;
  v22 = (std::_Ref_count_base *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v25;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  WFDSConMgr::CASPHandle::RegisterListener(*((WFDSConMgr::CASPHandle **)this + 14), this);
  *((_BYTE *)this + 96) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_d165b0dc1f223b1ad60133bc0034f705_Traceguids, this);
  }
  std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>(&v28[1]);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v36);
  v23 = (std::_Ref_count_base *)a2[1];
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v24 = (std::_Ref_count_base *)a3[1];
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
}

```

## disassembly

```asm
0x180045e88  mov     rax, rsp
0x180045e8b  mov     [rax+8], rbx
0x180045e8f  mov     [rax+18h], r8
0x180045e93  mov     [rax+10h], rdx
0x180045e97  push    rbp
0x180045e98  push    rsi
0x180045e99  push    rdi
0x180045e9a  push    r12
0x180045e9c  push    r13
0x180045e9e  push    r14
0x180045ea0  push    r15
0x180045ea2  lea     rbp, [rax-48h]
0x180045ea6  sub     rsp, 110h
0x180045ead  mov     rbx, r9
0x180045eb0  mov     r13, r8
0x180045eb3  mov     r15, rdx
0x180045eb6  mov     rsi, rcx
0x180045eb9  lea     rax, WPP_GLOBAL_Control
0x180045ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ec7  cmp     rcx, rax
0x180045eca  jz      short loc_180045EF0
0x180045ecc  cmp     byte ptr [rcx+19h], 4
0x180045ed0  jb      short loc_180045EF0
0x180045ed2  test    byte ptr [rcx+1Ch], 1
0x180045ed6  jz      short loc_180045EF0
0x180045ed8  mov     edx, 34h ; '4'
0x180045edd  mov     r9, rsi
0x180045ee0  lea     r8, WPP_d165b0dc1f223b1ad60133bc0034f705_Traceguids
0x180045ee7  mov     rcx, [rcx+10h]
0x180045eeb  call    WPP_SF_q
0x180045ef0  xor     edi, edi
0x180045ef2  test    rbx, rbx
0x180045ef5  jz      loc_180046211
0x180045efb  cmp     [r15], rdi
0x180045efe  jz      loc_180046211
0x180045f04  lea     rdx, [rsi+38h]
0x180045f08  lea     rcx, [rbp+40h+var_48]
0x180045f0c  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x180045f11  nop
0x180045f12  cmp     [rsi+40h], dil
0x180045f16  jz      short loc_180045F48
0x180045f18  mov     [rsp+140h+var_118], rsi; void *
0x180045f1d  lea     rax, aAspSessionWasA; "ASP Session was already canceled"
0x180045f24  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x180045f29  mov     r9d, 28Fh; char
0x180045f2f  lea     r8, aOnecoreuapNetW_23; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180045f36  lea     rdx, aWfdsconmgrCasp_5; "WFDSConMgr::CASPSeekerHelper::OpenSeeke"...
0x180045f3d  mov     ecx, 800704C7h; char
0x180045f42  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180045f48  cmp     [rsi+60h], dil
0x180045f4c  jz      short loc_180045F7E
0x180045f4e  mov     [rsp+140h+var_118], rsi; void *
0x180045f53  lea     rax, aCannotCallOpen; "Cannot call OpenSeekerSession multiple "...
0x180045f5a  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x180045f5f  mov     r9d, 294h; char
0x180045f65  lea     r8, aOnecoreuapNetW_23; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180045f6c  lea     rdx, aWfdsconmgrCasp_5; "WFDSConMgr::CASPSeekerHelper::OpenSeeke"...
0x180045f73  mov     ecx, 8007139Fh; char
0x180045f78  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180045f7e  lea     r12, [rsi+28h]
0x180045f82  cmp     [r12], rdi
0x180045f86  jnz     short loc_180045F90
0x180045f88  mov     rcx, rsi; this
0x180045f8b  call    ?OpenWFDHandle@CASPSeekerHelper@WFDSConMgr@@IEAAXXZ; WFDSConMgr::CASPSeekerHelper::OpenWFDHandle(void)
0x180045f90  mov     [rbp+40h+arg_18], rdi
0x180045f94  lea     r14, [rsi+8]
0x180045f98  mov     rcx, [r14]
0x180045f9b  lea     r8, [rsi+6Ch]
0x180045f9f  mov     rax, [rcx]
0x180045fa2  mov     rdx, [r12]
0x180045fa6  lea     r9, [rbp+40h+arg_18]
0x180045faa  mov     [rsp+140h+var_108], r9
0x180045faf  mov     [rsp+140h+var_110], r8
0x180045fb4  mov     r8d, [rbp+40h+arg_28]
0x180045fb8  mov     dword ptr [rsp+140h+var_118], r8d
0x180045fbd  mov     rdi, [rbp+40h+arg_20]
0x180045fc1  mov     [rsp+140h+var_120], rdi
0x180045fc6  mov     r9, rbx
0x180045fc9  xor     r8d, r8d
0x180045fcc  mov     rdx, [rdx+20h]
0x180045fd0  mov     rax, [rax+20h]
0x180045fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fd9  mov     rcx, [r14+8]
0x180045fdd  test    rcx, rcx
0x180045fe0  jz      short loc_180045FE6
0x180045fe2  lock inc dword ptr [rcx+8]
0x180045fe6  mov     rcx, [r14]
0x180045fe9  mov     [rsp+140h+var_E8], rcx
0x180045fee  mov     qword ptr [rsp+140h+var_D8+8], rcx
0x180045ff3  mov     rcx, [r14+8]
0x180045ff7  mov     qword ptr [rsp+140h+var_D8], rcx
0x180045ffc  mov     qword ptr [rsp+140h+var_D8+10h], rcx
0x180046001  mov     rcx, [rbp+40h+arg_18]
0x180046005  mov     [rsp+140h+var_E0], rcx
0x18004600a  mov     [rbp+40h+var_C0], rcx
0x18004600e  test    eax, eax
0x180046010  jz      short loc_180046049
0x180046012  jle     short loc_18004601C
0x180046014  movzx   eax, ax
0x180046017  or      eax, 80070000h
0x18004601c  mov     [rsp+140h+var_118], rsi; void *
0x180046021  lea     rcx, aFailureInOpens; "Failure in OpenSeekerSession, bailing o"...
0x180046028  mov     [rsp+140h+var_120], rcx; unsigned __int16 *
0x18004602d  mov     r9d, 2A9h; char
0x180046033  lea     r8, aOnecoreuapNetW_23; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004603a  lea     rdx, aWfdsconmgrCasp_5; "WFDSConMgr::CASPSeekerHelper::OpenSeeke"...
0x180046041  mov     ecx, eax; char
0x180046043  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180046049  mov     eax, [rdi]
0x18004604b  mov     [rsi+61h], eax
0x18004604e  movzx   eax, word ptr [rdi+4]
0x180046052  mov     [rsi+65h], ax
0x180046056  mov     eax, [rbp+40h+arg_28]
0x180046059  mov     [rsi+68h], eax
0x18004605c  mov     ecx, 0B0h; Size
0x180046061  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046066  mov     rdi, rax
0x180046069  mov     [rbp+40h+var_90], rax
0x18004606d  mov     ebx, [rsi+6Ch]
0x180046070  mov     rdx, r13
0x180046073  lea     rcx, [rbp+40h+var_88]
0x180046077  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x18004607c  mov     r11, rax
0x18004607f  mov     [rbp+40h+var_C0], 0
0x180046087  mov     rax, [rsp+140h+var_E8]
0x18004608c  mov     [rbp+40h+var_B8], rax
0x180046090  mov     rax, qword ptr [rsp+140h+var_D8]
0x180046095  mov     [rbp+40h+var_B0], rax
0x180046099  xorps   xmm0, xmm0
0x18004609c  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x1800460a2  mov     rax, [rsp+140h+var_E0]
0x1800460a7  mov     [rbp+40h+var_A8], rax
0x1800460ab  lea     rdx, [rsi+18h]
0x1800460af  lea     rcx, [rbp+40h+var_78]
0x1800460b3  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x1800460b8  mov     r10, rax
0x1800460bb  mov     rdx, r15
0x1800460be  lea     rcx, [rbp+40h+var_68]
0x1800460c2  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x1800460c7  mov     r9, rax
0x1800460ca  mov     rdx, r12
0x1800460cd  lea     rcx, [rbp+40h+var_58]
0x1800460d1  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x1800460d6  mov     r8, rax
0x1800460d9  mov     rdx, r14
0x1800460dc  lea     rcx, [rbp+40h+var_A0]
0x1800460e0  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x1800460e5  mov     [rsp+140h+var_F8], ebx; int
0x1800460e9  mov     ecx, [rbp+40h+arg_28]
0x1800460ec  mov     [rsp+140h+var_100], ecx; int
0x1800460f0  mov     rcx, [rbp+40h+arg_20]
0x1800460f4  mov     [rsp+140h+var_108], rcx; __int64
0x1800460f9  mov     [rsp+140h+var_110], r11; __int64
0x1800460fe  lea     rcx, [rbp+40h+var_B8]
0x180046102  mov     [rsp+140h+var_118], rcx; __int64
0x180046107  mov     [rsp+140h+var_120], r10; __int64
0x18004610c  mov     rdx, rax
0x18004610f  mov     rcx, rdi; struct WFDSConMgr::IASPListenerSpecific *
0x180046112  call    ??0CASPHandle@WFDSConMgr@@QEAA@V?$shared_ptr@VCASPShim@WFDSConMgr@@@std@@V?$shared_ptr@VCWFDLowPrivHandle@WFDSConMgr@@@3@V?$shared_ptr@VCWFDClientHandle@WFDSConMgr@@@3@V?$shared_ptr@VCWlanApiShim@WFDSConMgr@@@3@V?$unique_ptr@PEAXUASPCloseSessionDeleter@WFDSConMgr@@@3@V?$shared_ptr@X@3@AEAY05$$CBEKK@Z; WFDSConMgr::CASPHandle::CASPHandle(std::shared_ptr<WFDSConMgr::CASPShim>,std::shared_ptr<WFDSConMgr::CWFDLowPrivHandle>,std::shared_ptr<WFDSConMgr::CWFDClientHandle>,std::shared_ptr<WFDSConMgr::CWlanApiShim>,std::unique_ptr<void *,WFDSConMgr::ASPCloseSessionDeleter>,std::shared_ptr<void>,uchar const (&)[6],ulong,ulong)
0x180046117  mov     rdi, rax
0x18004611a  mov     [rsp+140h+var_E8], rax
0x18004611f  mov     ecx, 18h; Size
0x180046124  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046129  mov     rbx, rax
0x18004612c  mov     [rsp+140h+var_F0], rax
0x180046131  xorps   xmm0, xmm0
0x180046134  movups  xmmword ptr [rax], xmm0
0x180046137  mov     r14d, 1
0x18004613d  mov     [rax+8], r14d
0x180046141  mov     [rax+0Ch], r14d
0x180046145  lea     rax, ??_7?$_Ref_count@VCASPHandle@WFDSConMgr@@@std@@6B@; const std::_Ref_count<WFDSConMgr::CASPHandle>::`vftable'
0x18004614c  mov     [rbx], rax
0x18004614f  mov     [rbx+10h], rdi
0x180046153  mov     [rsp+140h+var_E8], 0
0x18004615c  lea     rcx, [rsp+140h+var_E8]
0x180046161  call    ??1?$_Temporary_owner@VCASPHandle@WFDSConMgr@@@std@@QEAA@XZ; std::_Temporary_owner<WFDSConMgr::CASPHandle>::~_Temporary_owner<WFDSConMgr::CASPHandle>(void)
0x180046166  mov     [rsi+70h], rdi
0x18004616a  mov     rcx, [rsi+78h]; this
0x18004616e  mov     [rsi+78h], rbx
0x180046172  test    rcx, rcx
0x180046175  jz      short loc_18004617C
0x180046177  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004617c  mov     rdx, rsi; struct WFDSConMgr::IASPListener *
0x18004617f  mov     rcx, [rsi+70h]; this
0x180046183  call    ?RegisterListener@CASPHandle@WFDSConMgr@@QEAAXPEAVIASPListener@2@@Z; WFDSConMgr::CASPHandle::RegisterListener(WFDSConMgr::IASPListener *)
0x180046188  mov     [rsi+60h], r14b
0x18004618c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046193  lea     rax, WPP_GLOBAL_Control
0x18004619a  cmp     rcx, rax
0x18004619d  jz      short loc_1800461C4
0x18004619f  cmp     byte ptr [rcx+19h], 4
0x1800461a3  jb      short loc_1800461C4
0x1800461a5  test    [rcx+1Ch], r14b
0x1800461a9  jz      short loc_1800461C4
0x1800461ab  mov     edx, 35h ; '5'
0x1800461b0  mov     r9, rsi
0x1800461b3  lea     r8, WPP_d165b0dc1f223b1ad60133bc0034f705_Traceguids
0x1800461ba  mov     rcx, [rcx+10h]
0x1800461be  call    WPP_SF_q
0x1800461c3  nop
0x1800461c4  lea     rcx, [rsp+140h+var_D8+8]
0x1800461c9  call    ??1?$unique_ptr@PEAUDAF_ASSOCIATION_HANDLE__@@UDafAssociationContextDeleter@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>(void)
0x1800461ce  nop
0x1800461cf  lea     rcx, [rbp+40h+var_48]
0x1800461d3  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x1800461d8  nop
0x1800461d9  mov     rcx, [r15+8]; this
0x1800461dd  test    rcx, rcx
0x1800461e0  jz      short loc_1800461E8
0x1800461e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800461e7  nop
0x1800461e8  mov     rcx, [r13+8]; this
0x1800461ec  test    rcx, rcx
0x1800461ef  jz      short loc_1800461F6
0x1800461f1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800461f6  mov     rbx, [rsp+140h+arg_0]
0x1800461fe  add     rsp, 110h
0x180046205  pop     r15
0x180046207  pop     r14
0x180046209  pop     r13
0x18004620b  pop     r12
0x18004620d  pop     rdi
0x18004620e  pop     rsi
0x18004620f  pop     rbp
0x180046210  retn
0x180046211  mov     [rsp+140h+var_118], rsi; void *
0x180046216  lea     rax, aBadParametersT_2; "Bad parameters to OpenSeekerSession"
0x18004621d  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x180046222  mov     r9d, 288h; char
0x180046228  lea     r8, aOnecoreuapNetW_23; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004622f  lea     rdx, aWfdsconmgrCasp_5; "WFDSConMgr::CASPSeekerHelper::OpenSeeke"...
0x180046236  mov     ecx, 80070057h; char
0x18004623b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
