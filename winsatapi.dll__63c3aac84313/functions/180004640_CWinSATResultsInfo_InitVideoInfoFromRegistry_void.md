# CWinSATResultsInfo::InitVideoInfoFromRegistry(void)

- ea: `0x180004640`
- end: `0x1800049b5`
- name: `?InitVideoInfoFromRegistry@CWinSATResultsInfo@@AEAAJXZ`
- size: `885`
- prototype: `__int64 __fastcall(CWinSATResultsInfo *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002678`

## callees

- `0x180004640`
- `0x1800054e0`
- `0x1800071d0`
- `0x18000a770`
- `0x18000e28c`
- `0x18000e2d8`
- `0x18001006c`
- `0x180013220`
- `0x180013290`
- `0x180013fb6`
- `0x18002dec0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800047c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004806`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800048a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800048aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004955`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000495e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000497a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004983`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800047fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004806`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800048a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800048aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004955`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000495e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000497a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000478f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004848`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000478f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004848`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWinSATResultsInfo::InitVideoInfoFromRegistry(CWinSATResultsInfo *this)
{
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  void *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  void *v7; // rax
  __int64 v8; // rcx
  int v9; // r14d
  HMODULE ModuleHandleW; // rax
  _QWORD *v11; // rsi
  bool v12; // zf
  void *v13; // rcx
  void *v14; // rbx
  void *v15; // rcx
  HMODULE v16; // rax
  _QWORD *v17; // rbx
  HKEY *v18; // rdx
  void *v19; // rdi
  void *v20; // rcx
  unsigned __int64 v21; // r9
  int v22; // eax
  __int64 v23; // r8
  void *v24; // rcx
  void *v25; // rcx
  _QWORD *v27; // [rsp+30h] [rbp-2A8h] BYREF
  _QWORD *v28; // [rsp+38h] [rbp-2A0h]
  unsigned __int64 v29; // [rsp+40h] [rbp-298h] BYREF
  _QWORD *v30; // [rsp+48h] [rbp-290h] BYREF
  void **v31; // [rsp+58h] [rbp-280h] BYREF
  __int16 v32; // [rsp+60h] [rbp-278h]
  HMODULE v33; // [rsp+68h] [rbp-270h]
  __int64 v34; // [rsp+70h] [rbp-268h]
  __int64 v35; // [rsp+78h] [rbp-260h]
  CWinSATResultsInfo *v36; // [rsp+80h] [rbp-258h]
  __int64 v37; // [rsp+88h] [rbp-250h]
  _DWORD v38[4]; // [rsp+90h] [rbp-248h] BYREF
  _DWORD v39[4]; // [rsp+A0h] [rbp-238h] BYREF
  unsigned __int16 v40[256]; // [rsp+B0h] [rbp-228h] BYREF

  v37 = -2;
  v36 = this;
  v1 = operator new(0x28u);
  v2 = v1;
  if ( !v1 )
    std::_Xbad_alloc();
  v28 = v1;
  v1[2] = 1;
  v1[3] = 0;
  *v1 = 0;
  v1[1] = 0;
  v3 = operator new(2u);
  if ( !v3 )
    std::_Xbad_alloc();
  v2[3] = v3;
  if ( *v2 )
    memcpy_0(v3, 0, 2LL * *v2);
  v4 = v2[3];
  if ( v4 )
    *(_WORD *)(v4 + 2LL * *v2) = 0;
  v30 = v2;
  LODWORD(v29) = 0;
  v5 = operator new(0x28u);
  v6 = v5;
  if ( !v5 )
    std::_Xbad_alloc();
  v28 = v5;
  v5[2] = 1;
  v5[3] = 0;
  *v5 = 0;
  v5[1] = 0;
  v7 = operator new(2u);
  if ( !v7 )
    std::_Xbad_alloc();
  v6[3] = v7;
  if ( *v6 )
    memcpy_0(v7, 0, 2LL * *v6);
  v8 = v6[3];
  if ( v8 )
    *(_WORD *)(v8 + 2LL * *v6) = 0;
  v9 = 0;
  v28 = v6;
  ModuleHandleW = g_DLLModuleHandle;
  v31 = &mlib::MUILoader::`vftable';
  v32 = 10016;
  if ( !g_DLLModuleHandle )
    ModuleHandleW = GetModuleHandleW(0);
  try
  {
    v33 = ModuleHandleW;
    v34 = 0;
    v35 = 0;
    v11 = (_QWORD *)*mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                       &v27,
                       (__int64)&v31);
    v12 = v6[2]-- == 1;
    if ( v12 )
    {
      v13 = (void *)v6[3];
      if ( v13 )
        operator delete(v13);
      operator delete(v6);
    }
    v28 = v11;
    ++v11[2];
    v12 = v27[2]-- == 1;
    if ( v12 )
    {
      v14 = v27;
      if ( v27 )
      {
        v15 = (void *)v27[3];
        if ( v15 )
          operator delete(v15);
        operator delete(v14);
      }
    }
  }
  catch ( mlib::MSError v38 )
  {
    LODWORD(v27) = v38[0];
    mlib::MSError::~MSError((mlib::MSError *)v38);
    v9 = (int)v27;
    v11 = v28;
    if ( (int)v27 < 0 )
    {
      v17 = v30;
      goto LABEL_45;
    }
  }
  v16 = g_DLLModuleHandle;
  v31 = &mlib::MUILoader::`vftable';
  v32 = 10001;
  if ( !g_DLLModuleHandle )
    v16 = GetModuleHandleW(0);
  try
  {
    v33 = v16;
    v34 = 0;
    v35 = 0;
    v17 = (_QWORD *)*mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                       &v27,
                       (__int64)&v31);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v30);
    v30 = v17;
    ++v17[2];
    v12 = v27[2]-- == 1;
    if ( v12 )
    {
      v19 = v27;
      if ( v27 )
      {
        v20 = (void *)v27[3];
        if ( v20 )
          operator delete(v20);
        operator delete(v19);
      }
    }
  }
  catch ( mlib::MSError v39 )
  {
    LODWORD(v27) = v39[0];
    mlib::MSError::~MSError((mlib::MSError *)v39);
    v17 = v30;
    v9 = (int)v27;
    v11 = v28;
  }
  if ( v9 >= 0 )
  {
    D3DCommon::DXGetVideoInfoFromRegistry((D3DCommon *)&v29, v18);
    v21 = CWinSATResultsInfo::FixupReportedGraphicsMemory((unsigned int)v29);
    v22 = v21 ? StringCchPrintfW(v40, 0x100u, L"%u %ws", v21, v17[3]) : StringCchPrintfW(v40, 0x100u, L"%ws", v11[3]);
    v9 = v22;
    if ( v22 >= 0 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
        (unsigned __int64 **)v36 + 63,
        (char *)v40,
        v23);
  }
LABEL_45:
  v12 = v11[2]-- == 1;
  if ( v12 && v11 )
  {
    v24 = (void *)v11[3];
    if ( v24 )
      operator delete(v24);
    operator delete(v11);
  }
  v12 = v17[2]-- == 1;
  if ( v12 && v17 )
  {
    v25 = (void *)v17[3];
    if ( v25 )
      operator delete(v25);
    operator delete(v17);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004640  mov     rax, rsp
0x180004643  push    rdi
0x180004644  push    r14
0x180004646  push    r15
0x180004648  sub     rsp, 2C0h
0x18000464f  mov     qword ptr [rax-250h], 0FFFFFFFFFFFFFFFEh
0x18000465a  mov     [rax+10h], rbx
0x18000465e  mov     [rax+18h], rsi
0x180004662  mov     rax, cs:__security_cookie
0x180004669  xor     rax, rsp
0x18000466c  mov     [rsp+2D8h+var_28], rax
0x180004674  mov     [rsp+2D8h+var_258], rcx
0x18000467c  mov     ecx, 28h ; '('; Size
0x180004681  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004686  mov     rbx, rax
0x180004689  test    rax, rax
0x18000468c  jnz     short loc_180004694
0x18000468e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004694  mov     [rsp+2D8h+var_2A0], rbx
0x180004699  mov     qword ptr [rax+10h], 1
0x1800046a1  xor     edi, edi
0x1800046a3  mov     [rax+18h], rdi
0x1800046a7  mov     [rax], rdi
0x1800046aa  mov     [rax+8], rdi
0x1800046ae  mov     ecx, 2; Size
0x1800046b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046b8  test    rax, rax
0x1800046bb  jnz     short loc_1800046C3
0x1800046bd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800046c3  mov     [rbx+18h], rax
0x1800046c7  mov     r8, [rbx]
0x1800046ca  test    r8, r8
0x1800046cd  jz      short loc_1800046DC
0x1800046cf  add     r8, r8; Size
0x1800046d2  xor     edx, edx; Src
0x1800046d4  mov     rcx, rax; void *
0x1800046d7  call    memcpy_0
0x1800046dc  mov     rdx, [rbx+18h]
0x1800046e0  test    rdx, rdx
0x1800046e3  jz      short loc_1800046EC
0x1800046e5  mov     rax, [rbx]
0x1800046e8  mov     [rdx+rax*2], di
0x1800046ec  mov     [rsp+2D8h+var_290], rbx
0x1800046f1  mov     dword ptr [rsp+2D8h+var_298], edi
0x1800046f5  mov     ecx, 28h ; '('; Size
0x1800046fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046ff  mov     rbx, rax
0x180004702  test    rax, rax
0x180004705  jnz     short loc_18000470D
0x180004707  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000470d  mov     [rsp+2D8h+var_2A0], rbx
0x180004712  mov     qword ptr [rax+10h], 1
0x18000471a  mov     [rax+18h], rdi
0x18000471e  mov     [rax], rdi
0x180004721  mov     [rax+8], rdi
0x180004725  mov     ecx, 2; Size
0x18000472a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000472f  test    rax, rax
0x180004732  jnz     short loc_18000473A
0x180004734  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000473a  mov     [rbx+18h], rax
0x18000473e  mov     r8, [rbx]
0x180004741  test    r8, r8
0x180004744  jz      short loc_180004753
0x180004746  add     r8, r8; Size
0x180004749  xor     edx, edx; Src
0x18000474b  mov     rcx, rax; void *
0x18000474e  call    memcpy_0
0x180004753  mov     rcx, [rbx+18h]
0x180004757  test    rcx, rcx
0x18000475a  jz      short loc_180004763
0x18000475c  mov     rax, [rbx]
0x18000475f  mov     [rcx+rax*2], di
0x180004763  mov     r14d, edi
0x180004766  mov     [rsp+2D8h+var_2A0], rbx
0x18000476b  mov     rax, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x180004772  lea     r15, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x180004779  mov     [rsp+2D8h+var_280], r15
0x18000477e  mov     ecx, 2720h
0x180004783  mov     [rsp+2D8h+var_278], cx
0x180004788  test    rax, rax
0x18000478b  jnz     short loc_180004795
0x18000478d  xor     ecx, ecx; lpModuleName
0x18000478f  call    cs:__imp_GetModuleHandleW
0x180004795  mov     [rsp+2D8h+var_270], rax
0x18000479a  mov     [rsp+2D8h+var_268], rdi
0x18000479f  mov     [rsp+2D8h+var_260], rdi
0x1800047a4  lea     rdx, [rsp+2D8h+var_280]
0x1800047a9  lea     rcx, [rsp+2D8h+var_2A8]
0x1800047ae  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1800047b3  mov     rsi, [rax]
0x1800047b6  sub     qword ptr [rbx+10h], 1
0x1800047bb  jnz     short loc_1800047D5
0x1800047bd  mov     rcx, [rbx+18h]
0x1800047c1  test    rcx, rcx
0x1800047c4  jz      short loc_1800047CC
0x1800047c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800047cc  mov     rcx, rbx
0x1800047cf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800047d5  mov     [rsp+2D8h+var_2A0], rsi
0x1800047da  inc     qword ptr [rsi+10h]
0x1800047de  mov     rax, [rsp+2D8h+var_2A8]
0x1800047e3  sub     qword ptr [rax+10h], 1
0x1800047e8  jnz     short loc_18000480D
0x1800047ea  mov     rbx, [rsp+2D8h+var_2A8]
0x1800047ef  test    rbx, rbx
0x1800047f2  jz      short loc_18000480D
0x1800047f4  mov     rcx, [rbx+18h]
0x1800047f8  test    rcx, rcx
0x1800047fb  jz      short loc_180004803
0x1800047fd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004803  mov     rcx, rbx
0x180004806  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000480c  nop
0x18000480d  jmp     short loc_18000482B
0x18000480f  mov     r14d, dword ptr [rsp+2D8h+var_2A8]
0x180004814  mov     rsi, [rsp+2D8h+var_2A0]
0x180004819  test    r14d, r14d
0x18000481c  js      loc_18000493B
0x180004822  xor     edi, edi
0x180004824  lea     r15, ??_7MUILoader@mlib@@6B@; const mlib::MUILoader::`vftable'
0x18000482b  mov     rax, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x180004832  mov     [rsp+2D8h+var_280], r15
0x180004837  mov     ecx, 2711h
0x18000483c  mov     [rsp+2D8h+var_278], cx
0x180004841  test    rax, rax
0x180004844  jnz     short loc_18000484E
0x180004846  xor     ecx, ecx; lpModuleName
0x180004848  call    cs:__imp_GetModuleHandleW
0x18000484e  mov     [rsp+2D8h+var_270], rax
0x180004853  mov     [rsp+2D8h+var_268], rdi
0x180004858  mov     [rsp+2D8h+var_260], rdi
0x18000485d  lea     rdx, [rsp+2D8h+var_280]
0x180004862  lea     rcx, [rsp+2D8h+var_2A8]
0x180004867  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18000486c  mov     rbx, [rax]
0x18000486f  lea     rcx, [rsp+2D8h+var_290]
0x180004874  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004879  mov     [rsp+2D8h+var_290], rbx
0x18000487e  inc     qword ptr [rbx+10h]
0x180004882  mov     rax, [rsp+2D8h+var_2A8]
0x180004887  sub     qword ptr [rax+10h], 1
0x18000488c  jnz     short loc_1800048B1
0x18000488e  mov     rdi, [rsp+2D8h+var_2A8]
0x180004893  test    rdi, rdi
0x180004896  jz      short loc_1800048B1
0x180004898  mov     rcx, [rdi+18h]
0x18000489c  test    rcx, rcx
0x18000489f  jz      short loc_1800048A7
0x1800048a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800048a7  mov     rcx, rdi
0x1800048aa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800048b0  nop
0x1800048b1  jmp     short loc_1800048C2
0x1800048b3  mov     rbx, [rsp+2D8h+var_290]
0x1800048b8  mov     r14d, dword ptr [rsp+2D8h+var_2A8]
0x1800048bd  mov     rsi, [rsp+2D8h+var_2A0]
0x1800048c2  test    r14d, r14d
0x1800048c5  js      short loc_180004940
0x1800048c7  lea     rcx, [rsp+2D8h+var_298]; this
0x1800048cc  call    ?DXGetVideoInfoFromRegistry@D3DCommon@@YAJPEAK@Z; D3DCommon::DXGetVideoInfoFromRegistry(ulong *)
0x1800048d1  mov     ecx, dword ptr [rsp+2D8h+var_298]; unsigned __int64
0x1800048d5  call    ?FixupReportedGraphicsMemory@CWinSATResultsInfo@@CA_K_K@Z; CWinSATResultsInfo::FixupReportedGraphicsMemory(unsigned __int64)
0x1800048da  mov     r9, rax
0x1800048dd  mov     edx, 100h; unsigned __int64
0x1800048e2  lea     rcx, [rsp+2D8h+var_228]; unsigned __int16 *
0x1800048ea  test    rax, rax
0x1800048ed  jnz     short loc_180004901
0x1800048ef  mov     r9, [rsi+18h]
0x1800048f3  lea     r8, aWs; "%ws"
0x1800048fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800048ff  jmp     short loc_180004916
0x180004901  mov     rax, [rbx+18h]
0x180004905  mov     [rsp+2D8h+var_2B8], rax
0x18000490a  lea     r8, aUWs; "%u %ws"
0x180004911  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004916  mov     r14d, eax
0x180004919  test    eax, eax
0x18000491b  js      short loc_180004940
0x18000491d  mov     rcx, [rsp+2D8h+var_258]
0x180004925  add     rcx, 1F8h
0x18000492c  lea     rdx, [rsp+2D8h+var_228]
0x180004934  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x180004939  jmp     short loc_180004940
0x18000493b  mov     rbx, [rsp+2D8h+var_290]
0x180004940  sub     qword ptr [rsi+10h], 1
0x180004945  jnz     short loc_180004965
0x180004947  test    rsi, rsi
0x18000494a  jz      short loc_180004965
0x18000494c  mov     rcx, [rsi+18h]
0x180004950  test    rcx, rcx
0x180004953  jz      short loc_18000495B
0x180004955  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000495b  mov     rcx, rsi
0x18000495e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004964  nop
0x180004965  sub     qword ptr [rbx+10h], 1
0x18000496a  jnz     short loc_180004989
0x18000496c  test    rbx, rbx
0x18000496f  jz      short loc_180004989
0x180004971  mov     rcx, [rbx+18h]
0x180004975  test    rcx, rcx
0x180004978  jz      short loc_180004980
0x18000497a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004980  mov     rcx, rbx
0x180004983  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004989  mov     eax, r14d
0x18000498c  mov     rcx, [rsp+2D8h+var_28]
0x180004994  xor     rcx, rsp; StackCookie
0x180004997  call    __security_check_cookie
0x18000499c  lea     r11, [rsp+2D8h+var_18]
0x1800049a4  mov     rbx, [r11+28h]
0x1800049a8  mov     rsi, [r11+30h]
0x1800049ac  mov     rsp, r11
0x1800049af  pop     r15
0x1800049b1  pop     r14
0x1800049b3  pop     rdi
0x1800049b4  retn
```
