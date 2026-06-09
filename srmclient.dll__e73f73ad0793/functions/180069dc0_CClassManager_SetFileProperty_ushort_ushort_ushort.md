# CClassManager::SetFileProperty(ushort *,ushort *,ushort *)

- ea: `0x180069dc0`
- end: `0x18006a7e1`
- name: `?SetFileProperty@CClassManager@@UEAAJPEAG00@Z`
- size: `2593`
- prototype: `__int64 __fastcall(CClassManager *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x180010b24`
- `0x180010bc4`
- `0x18001bc58`
- `0x18002a7e0`
- `0x18003ff90`
- `0x180061518`
- `0x180061be4`
- `0x1800640e4`
- `0x180065c60`
- `0x1800687ec`
- `0x180068f48`
- `0x1800691a4`
- `0x180069dc0`
- `0x18006ae28`
- `0x18006d4d0`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x18007023c`
- `0x180070380`
- `0x180070648`
- `0x180071efc`
- `0x180072a80`
- `0x180072b44`
- `0x180072ed8`
- `0x180073a80`
- `0x180083a68`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006a2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a2c5`

## string_xrefs

- `0x180069e09`: `base\fs\fsrm\service\classmanager\classmanager.cpp`
- `0x18006a1d0`: `base\fs\fsrm\service\classmanager\classmanager.cpp`
- `0x18006a314`: `base\fs\fsrm\service\classmanager\classmanager.cpp`
- `0x180069e17`: `CClassManager::SetFileProperty`
- `0x18006a1df`: `CClassManager::SetFileProperty`
- `0x18006a31b`: `CClassManager::SetFileProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CClassManager::SetFileProperty(
        CClassManager *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdx
  CFciPropertyDefinition *v11; // rbx
  __int64 v12; // rdx
  CClassManager *v13; // rcx
  signed int v14; // eax
  bool v15; // di
  int v16; // esi
  const unsigned __int16 *v17; // rax
  void **v18; // rdx
  __int64 v19; // r8
  void **v20; // rdx
  __int64 v21; // r8
  unsigned __int16 i; // cx
  void **v23; // rdx
  __int64 v24; // r8
  struct CSrmDebugInfo *v25; // rax
  unsigned __int16 *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rdx
  DWORD v29; // ebx
  char v31; // al
  char v32; // al
  int v33; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  int v37; // eax
  char v38; // al
  void *StringW; // rax
  int v40; // eax
  char v41; // al
  int v42; // eax
  char v43; // al
  char v44; // al
  char v45; // al
  char Hr; // al
  int v47; // [rsp+44h] [rbp-3C4h] BYREF
  int v48[2]; // [rsp+48h] [rbp-3C0h] BYREF
  unsigned __int16 *v49; // [rsp+50h] [rbp-3B8h] BYREF
  __int64 v50; // [rsp+58h] [rbp-3B0h] BYREF
  __int64 v51; // [rsp+60h] [rbp-3A8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-3A0h] BYREF
  CClassManager *v53; // [rsp+70h] [rbp-398h] BYREF
  CFciPropertyDefinition *v54; // [rsp+78h] [rbp-390h] BYREF
  unsigned __int16 *v55; // [rsp+88h] [rbp-380h] BYREF
  __int64 v56; // [rsp+90h] [rbp-378h] BYREF
  const unsigned __int16 *v57; // [rsp+98h] [rbp-370h] BYREF
  const unsigned __int16 *v58; // [rsp+A0h] [rbp-368h]
  const unsigned __int16 *v59; // [rsp+A8h] [rbp-360h]
  int v60; // [rsp+B0h] [rbp-358h]
  int v61; // [rsp+B4h] [rbp-354h]
  int v62; // [rsp+B8h] [rbp-350h]
  _QWORD v63[12]; // [rsp+C0h] [rbp-348h] BYREF
  int v64; // [rsp+120h] [rbp-2E8h]
  _BYTE v65[144]; // [rsp+138h] [rbp-2D0h] BYREF
  _BYTE v66[152]; // [rsp+1C8h] [rbp-240h] BYREF
  void **v67; // [rsp+260h] [rbp-1A8h] BYREF
  DWORD dwMessageId; // [rsp+268h] [rbp-1A0h]
  unsigned __int16 *v69[2]; // [rsp+310h] [rbp-F8h] BYREF
  __int64 v70; // [rsp+320h] [rbp-E8h]
  unsigned __int64 v71; // [rsp+328h] [rbp-E0h]
  _BYTE v72[16]; // [rsp+340h] [rbp-C8h] BYREF
  void *Block[3]; // [rsp+350h] [rbp-B8h] BYREF
  unsigned __int64 v74; // [rsp+368h] [rbp-A0h]
  _BYTE v75[40]; // [rsp+378h] [rbp-90h] BYREF
  void *v76[3]; // [rsp+3A0h] [rbp-68h] BYREF
  unsigned __int64 v77; // [rsp+3B8h] [rbp-50h]

  v49 = a4;
  v53 = this;
  v50 = (__int64)&v57;
  v57 = L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp";
  v58 = L"CClassManager::SetFileProperty";
  v59 = L"SRMCLSCC";
  v60 = 1463;
  v61 = 21;
  v62 = 255;
  v64 = 0x1000000;
  memset_0(v63, 0, sizeof(v63));
  CSrmFunctionTracer::CSrmFunctionTracer(&v67, &v57, 0);
  v8 = *((_QWORD *)this + 14);
  if ( v8 )
  {
    v29 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v8 + 256LL))(
            v8,
            a2,
            a3,
            a4);
    v67 = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v71 = 7;
    v70 = 0;
    LOWORD(v69[0]) = 0;
    if ( !a2 || !*a2 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, -2147200250);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5C4u, Hr, 0);
    }
    dwMessageId = 0;
    if ( !a3 || !*a3 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, -2147024809);
      v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5C5u, v45, 0);
    }
    dwMessageId = 0;
    if ( CClassManager::IsManagementProperty(this, a3) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, -2147200239);
      v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5CAu, v44, 0);
    }
    dwMessageId = 0;
    CClassManager::TriggerPropDefSync(1);
    v54 = 0;
    if ( !(unsigned int)CFciConfigObject::GetObjectByObjectName<CFciPropertyDefinition>(a3, v9, &v54) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, -2147200255);
      v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5D7u, v31, 0);
    }
    dwMessageId = 0;
    v10 = a4;
    v11 = v54;
    if ( !CFciPropertyDefinition::IsValueValidForPropertyType(v54, v10) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, -2147024809);
      v32 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5DCu, v32, 0);
    }
    dwMessageId = 0;
    bstrString = 0;
    CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)v48, v12, 0);
    CClassManager::EnsureAndCheckUnmappedPath(v13, a2, (struct CSrmComBSTR *)&bstrString);
    CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v48);
    v47 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*((_QWORD *)v11 + 1) + 176LL))((__int64)v11 + 8, &v47);
    dwMessageId = v14;
    if ( v14 < 0 )
    {
      v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, v33);
      v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x5EEu, v34, 0);
    }
    dwMessageId = v14;
    LODWORD(v51) = v47 & 4;
    v15 = (_DWORD)v51 != 0;
    v16 = (_DWORD)v51 != 0 ? 0x60000 : 0;
    CSetPropertyContainer::CSetPropertyContainer((CSetPropertyContainer *)v72);
    v17 = v49;
    if ( !v49 )
      v17 = &dword_1800DC394;
    dwMessageId = CClassManager::ClassifyPath(
                    bstrString,
                    v16 + 1048967,
                    3,
                    (struct CSrmClientSessionCallback *)v72,
                    a3,
                    v17,
                    v15);
    if ( (dwMessageId & 0x80000000) != 0 )
    {
      if ( v72[12] )
      {
        v18 = Block;
        if ( v74 >= 8 )
          v18 = (void **)Block[0];
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)v18 + v19) );
        std::wstring::assign(v69, v18);
        dwMessageId = -2147200172;
        v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, v35);
        v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x610u, v36, 0);
      }
      CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v67);
    }
    if ( v72[9] || v72[10] )
    {
      v23 = Block;
      if ( v74 >= 8 )
        v23 = (void **)Block[0];
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)v23 + v24) );
      std::wstring::assign(v69, v23);
      dwMessageId = -2147200172;
      v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, v42);
      v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x625u, v43, 0);
    }
    if ( v72[11] )
    {
      v48[0] = 0;
      CSetPropertyContainer::GetPropertyFlags((CSetPropertyContainer *)v72, a3, v48);
      if ( (v48[0] & 0x400) != 0 )
      {
        v20 = Block;
        if ( v74 >= 8 )
          v20 = (void **)Block[0];
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)v20 + v21) );
        std::wstring::assign(v69, v20);
        dwMessageId = -2147200172;
        v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, v37);
        v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x63Au, v38, 0);
      }
    }
    if ( !(_DWORD)v51 && !v72[8] )
    {
      StringW = (void *)CSrmResource::LoadStringW(v76, 0x1167u);
      std::wstring::assign(v69, StringW);
      if ( v77 >= 8 )
        operator delete(v76[0]);
      v77 = 7;
      v76[2] = 0;
      LOWORD(v76[0]) = 0;
      dwMessageId = -2147200172;
      v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v67, v40);
      v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v67);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v67, 0x649u, v41, 0);
    }
    if ( CClassManager::IsFileLoggingEnabled(v53) )
    {
      v53 = (CClassManager *)a2;
      v51 = 4422;
      CSrmFunctionTracerBase::AddContext(&v67, 1, &v51, &v53);
      v55 = a3;
      v56 = 4423;
      CSrmFunctionTracerBase::AddContext(&v67, 1, &v56, &v55);
      v50 = 4424;
      CSrmFunctionTracerBase::AddContext(&v67, 1, &v50, &v49);
      *(_QWORD *)v48 = &v57;
      v57 = L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp";
      v58 = L"CClassManager::SetFileProperty";
      v59 = L"SRMCLSCC";
      v60 = 1621;
      v61 = 21;
      v62 = 255;
      v64 = 0x1000000;
      for ( i = 0; i < 0xCu; ++i )
        v63[i] = 0;
      CSrmFunctionTracer::LogError(&v67, 2147754047LL, &v57, 4);
    }
    v50 = (__int64)v75;
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v75);
    if ( v74 >= 8 )
      operator delete(Block[0]);
    v74 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
    SysFreeString(bstrString);
    if ( v11 )
      (*(void (__fastcall **)(CFciPropertyDefinition *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v70 )
    {
      v50 = (__int64)v65;
      v57 = L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp";
      v58 = L"CClassManager::SetFileProperty";
      v59 = L"SRMCLSCC";
      v60 = 1633;
      v61 = 21;
      v62 = 255;
      v64 = 0x1000000;
      memset_0(v63, 0, sizeof(v63));
      v25 = (struct CSrmDebugInfo *)CSrmDebugInfo::operator<<(
                                      (struct CSrmDebugInfo *)&v57,
                                      (CSrmDebugInfo *)v66,
                                      dwMessageId);
      v26 = (unsigned __int16 *)v69;
      if ( v71 >= 8 )
        v26 = v69[0];
      v27 = CSrmDebugInfo::operator<<(v25, (CSrmDebugInfo *)v65, v26);
      CSrmFunctionTracer::SetError(&v67, v28, v27);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v66);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v57);
    }
    else
    {
      CSrmFunctionTracer::SetComError((CSrmFunctionTracer *)&v67);
    }
    v29 = dwMessageId;
    if ( v71 >= 8 )
      operator delete(v69[0]);
    v71 = 7;
    v70 = 0;
    LOWORD(v69[0]) = 0;
    v67 = &CSrmFunctionTracer::`vftable';
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v67);
  return v29;
}

```

## disassembly

```asm
0x180069dc0  mov     r11, rsp
0x180069dc3  push    rbx
0x180069dc4  push    rsi
0x180069dc5  push    rdi
0x180069dc6  push    r12
0x180069dc8  push    r13
0x180069dca  push    r14
0x180069dcc  push    r15
0x180069dce  sub     rsp, 3D0h
0x180069dd5  mov     rax, cs:__security_cookie
0x180069ddc  xor     rax, rsp
0x180069ddf  mov     [rsp+408h+var_40], rax
0x180069de7  mov     rbx, r9
0x180069dea  mov     [rsp+408h+var_3B8], rbx
0x180069def  mov     r15, r8
0x180069df2  mov     r13, rdx
0x180069df5  mov     rdi, rcx
0x180069df8  mov     [rsp+408h+var_398], rcx
0x180069dfd  lea     rax, [r11-370h]
0x180069e04  mov     [rsp+408h+var_3B0], rax
0x180069e09  lea     rax, aBaseFsFsrmServ_24; "base\\fs\\fsrm\\service\\classmanager\\"...
0x180069e10  mov     [r11-370h], rax
0x180069e17  lea     rax, aCclassmanagerS_0; "CClassManager::SetFileProperty"
0x180069e1e  mov     [r11-368h], rax
0x180069e25  lea     rax, aSrmclscc; "SRMCLSCC"
0x180069e2c  mov     [r11-360h], rax
0x180069e33  mov     [rsp+408h+var_358], 5B7h
0x180069e3e  mov     [rsp+408h+var_354], 15h
0x180069e49  mov     [rsp+408h+var_350], 0FFh
0x180069e54  xor     r14d, r14d
0x180069e57  mov     [rsp+408h+var_2E8], 1000000h
0x180069e62  xor     edx, edx; Val
0x180069e64  lea     r12d, [r14+1]
0x180069e68  lea     r8d, [r14+60h]; Size
0x180069e6c  lea     rcx, [r11-348h]; void *
0x180069e73  call    memset_0
0x180069e78  nop
0x180069e79  xor     r8d, r8d
0x180069e7c  lea     rdx, [rsp+408h+var_370]
0x180069e84  lea     rcx, [rsp+408h+var_1A8]
0x180069e8c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180069e91  nop
0x180069e92  mov     rcx, [rdi+70h]
0x180069e96  test    rcx, rcx
0x180069e99  jnz     loc_18006A470
0x180069e9f  mov     [rsp+408h+var_E0], 7
0x180069eab  mov     [rsp+408h+var_E8], r14
0x180069eb3  mov     word ptr [rsp+408h+var_F8], r14w
0x180069ebc  mov     eax, [rsp+408h+dwMessageId]
0x180069ec3  mov     [rsp+408h+dwMessageId], eax
0x180069eca  test    r13, r13
0x180069ecd  jz      loc_18006A7A8
0x180069ed3  cmp     [r13+0], r14w
0x180069ed8  jz      loc_18006A7A8
0x180069ede  mov     [rsp+408h+dwMessageId], r14d
0x180069ee6  mov     [rsp+408h+dwMessageId], r14d
0x180069eee  test    r15, r15
0x180069ef1  jz      loc_18006A771
0x180069ef7  cmp     [r15], r14w
0x180069efb  jz      loc_18006A771
0x180069f01  mov     [rsp+408h+dwMessageId], r14d
0x180069f09  mov     [rsp+408h+dwMessageId], r14d
0x180069f11  mov     rdx, r15; unsigned __int16 *
0x180069f14  mov     rcx, rdi; this
0x180069f17  call    ?IsManagementProperty@CClassManager@@AEAA_NPEBG@Z; CClassManager::IsManagementProperty(ushort const *)
0x180069f1c  test    al, al
0x180069f1e  jnz     loc_18006A73A
0x180069f24  mov     [rsp+408h+dwMessageId], r14d
0x180069f2c  mov     cl, r12b; bool
0x180069f2f  call    ?TriggerPropDefSync@CClassManager@@CAX_N@Z; CClassManager::TriggerPropDefSync(bool)
0x180069f34  mov     [rsp+408h+var_390], r14
0x180069f39  mov     eax, [rsp+408h+dwMessageId]
0x180069f40  mov     [rsp+408h+dwMessageId], eax
0x180069f47  lea     r8, [rsp+408h+var_390]
0x180069f4c  mov     rcx, r15
0x180069f4f  call    ??$GetObjectByObjectName@VCFciPropertyDefinition@@@CFciConfigObject@@SAHPEBGHPEAPEAVCFciPropertyDefinition@@@Z; CFciConfigObject::GetObjectByObjectName<CFciPropertyDefinition>(ushort const *,int,CFciPropertyDefinition * *)
0x180069f54  test    eax, eax
0x180069f56  jz      loc_18006A4CB
0x180069f5c  mov     [rsp+408h+dwMessageId], r14d
0x180069f64  mov     [rsp+408h+dwMessageId], r14d
0x180069f6c  mov     rdx, rbx; unsigned __int16 *
0x180069f6f  mov     rbx, [rsp+408h+var_390]
0x180069f74  mov     rcx, rbx; this
0x180069f77  call    ?IsValueValidForPropertyType@CFciPropertyDefinition@@QEAAHPEBG@Z; CFciPropertyDefinition::IsValueValidForPropertyType(ushort const *)
0x180069f7c  test    eax, eax
0x180069f7e  jz      loc_18006A502
0x180069f84  mov     [rsp+408h+dwMessageId], r14d
0x180069f8c  mov     [rsp+408h+bstrString], r14
0x180069f91  xor     r8d, r8d; bool
0x180069f94  lea     rcx, [rsp+408h+var_3C0]; this
0x180069f99  call    ??0CSrmImpersonationSession@@QEAA@_N0@Z; CSrmImpersonationSession::CSrmImpersonationSession(bool,bool)
0x180069f9e  nop
0x180069f9f  lea     r8, [rsp+408h+bstrString]; struct CSrmComBSTR *
0x180069fa4  mov     rdx, r13; unsigned __int16 *
0x180069fa7  call    ?EnsureAndCheckUnmappedPath@CClassManager@@AEAAXPEBGAEAVCSrmComBSTR@@@Z; CClassManager::EnsureAndCheckUnmappedPath(ushort const *,CSrmComBSTR &)
0x180069fac  nop
0x180069fad  lea     rcx, [rsp+408h+var_3C0]; this
0x180069fb2  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x180069fb7  mov     [rsp+408h+var_3C4], r14d
0x180069fbc  lea     rcx, [rbx+8]
0x180069fc0  mov     rax, [rcx]
0x180069fc3  lea     rdx, [rsp+408h+var_3C4]
0x180069fc8  mov     rax, [rax+0B0h]
0x180069fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069fd4  mov     [rsp+408h+dwMessageId], eax
0x180069fdb  test    eax, eax
0x180069fdd  js      loc_18006A53A
0x180069fe3  mov     [rsp+408h+dwMessageId], eax
0x180069fea  mov     eax, [rsp+408h+var_3C4]
0x180069fee  and     eax, 4
0x180069ff1  mov     dword ptr [rsp+408h+var_3A8], eax
0x180069ff5  setnz   dil
0x180069ff9  neg     eax
0x180069ffb  sbb     esi, esi
0x180069ffd  and     esi, 60000h
0x18006a003  lea     rcx, [rsp+408h+var_C8]; this
0x18006a00b  call    ??0CSetPropertyContainer@@QEAA@XZ; CSetPropertyContainer::CSetPropertyContainer(void)
0x18006a010  nop
0x18006a011  lea     rdx, dword_1800DC394
0x18006a018  mov     rcx, [rsp+408h+var_3B8]
0x18006a01d  mov     rax, rcx
0x18006a020  test    rcx, rcx
0x18006a023  cmovz   rax, rdx
0x18006a027  mov     [rsp+408h+var_3D8], dil; bool
0x18006a02c  mov     [rsp+408h+var_3E0], rax; unsigned __int16 *
0x18006a031  mov     [rsp+408h+var_3E8], r15; unsigned __int16 *
0x18006a036  lea     r9, [rsp+408h+var_C8]; struct CSrmClientSessionCallback *
0x18006a03e  mov     r8d, 3; int
0x18006a044  lea     edx, [rsi+100187h]; unsigned int
0x18006a04a  mov     rcx, [rsp+408h+bstrString]; unsigned __int16 *
0x18006a04f  call    ?ClassifyPath@CClassManager@@CAJPEBGKJPEAVCSrmClientSessionCallback@@00_N@Z; CClassManager::ClassifyPath(ushort const *,ulong,long,CSrmClientSessionCallback *,ushort const *,ushort const *,bool)
0x18006a054  mov     [rsp+408h+dwMessageId], eax
0x18006a05b  test    eax, eax
0x18006a05d  jns     short loc_18006A09B
0x18006a05f  cmp     [rsp+408h+var_BC], r14b
0x18006a067  jz      loc_18006A5D5
0x18006a06d  lea     rdx, [rsp+408h+Block]
0x18006a075  cmp     [rsp+408h+var_A0], 8
0x18006a07e  cmovnb  rdx, [rsp+408h+Block]; Src
0x18006a087  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006a08b  inc     r8
0x18006a08e  cmp     [rdx+r8*2], r14w
0x18006a093  jz      loc_18006A57C
0x18006a099  jmp     short loc_18006A08B
0x18006a09b  cmp     [rsp+408h+var_BF], r14b
0x18006a0a3  jnz     loc_18006A2E3
0x18006a0a9  cmp     [rsp+408h+var_BE], r14b
0x18006a0b1  jnz     loc_18006A2E3
0x18006a0b7  cmp     [rsp+408h+var_BD], r14b
0x18006a0bf  jz      short loc_18006A113
0x18006a0c1  mov     [rsp+408h+var_3C0], r14d
0x18006a0c6  lea     r8, [rsp+408h+var_3C0]; int *
0x18006a0cb  mov     rdx, r15; unsigned __int16 *
0x18006a0ce  lea     rcx, [rsp+408h+var_C8]; this
0x18006a0d6  call    ?GetPropertyFlags@CSetPropertyContainer@@QEBA_NPEBGPEAJ@Z; CSetPropertyContainer::GetPropertyFlags(ushort const *,long *)
0x18006a0db  test    [rsp+408h+var_3C0], 400h
0x18006a0e3  jz      short loc_18006A113
0x18006a0e5  lea     rdx, [rsp+408h+Block]
0x18006a0ed  cmp     [rsp+408h+var_A0], 8
0x18006a0f6  cmovnb  rdx, [rsp+408h+Block]; Src
0x18006a0ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006a103  inc     r8
0x18006a106  cmp     [rdx+r8*2], r14w
0x18006a10b  jz      loc_18006A5E2
0x18006a111  jmp     short loc_18006A103
0x18006a113  cmp     dword ptr [rsp+408h+var_3A8], r14d
0x18006a118  jnz     short loc_18006A128
0x18006a11a  cmp     [rsp+408h+var_C0], r14b
0x18006a122  jz      loc_18006A63B
0x18006a128  mov     rcx, [rsp+408h+var_398]; this
0x18006a12d  call    ?IsFileLoggingEnabled@CClassManager@@AEAA_NXZ; CClassManager::IsFileLoggingEnabled(void)
0x18006a132  test    al, al
0x18006a134  jz      loc_18006A270
0x18006a13a  mov     [rsp+408h+var_398], r13
0x18006a13f  mov     [rsp+408h+var_3A8], 1146h
0x18006a148  lea     r9, [rsp+408h+var_398]
0x18006a14d  lea     r8, [rsp+408h+var_3A8]
0x18006a152  mov     edx, r12d
0x18006a155  lea     rcx, [rsp+408h+var_1A8]
0x18006a15d  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18006a162  mov     [rsp+408h+var_380], r15
0x18006a16a  mov     [rsp+408h+var_378], 1147h
0x18006a176  lea     r9, [rsp+408h+var_380]
0x18006a17e  lea     r8, [rsp+408h+var_378]
0x18006a186  mov     edx, r12d
0x18006a189  lea     rcx, [rsp+408h+var_1A8]
0x18006a191  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18006a196  mov     rax, [rsp+408h+var_3B8]
0x18006a19b  mov     [rsp+408h+var_3B8], rax
0x18006a1a0  mov     [rsp+408h+var_3B0], 1148h
0x18006a1a9  lea     r9, [rsp+408h+var_3B8]
0x18006a1ae  lea     r8, [rsp+408h+var_3B0]
0x18006a1b3  mov     edx, r12d
0x18006a1b6  lea     rcx, [rsp+408h+var_1A8]
0x18006a1be  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x18006a1c3  lea     r8, [rsp+408h+var_370]
0x18006a1cb  mov     qword ptr [rsp+408h+var_3C0], r8
0x18006a1d0  lea     rax, aBaseFsFsrmServ_24; "base\\fs\\fsrm\\service\\classmanager\\"...
0x18006a1d7  mov     [rsp+408h+var_370], rax
0x18006a1df  lea     rax, aCclassmanagerS_0; "CClassManager::SetFileProperty"
0x18006a1e6  mov     [rsp+408h+var_368], rax
0x18006a1ee  lea     rax, aSrmclscc; "SRMCLSCC"
0x18006a1f5  mov     [rsp+408h+var_360], rax
0x18006a1fd  mov     [rsp+408h+var_358], 655h
0x18006a208  mov     [rsp+408h+var_354], 15h
0x18006a213  mov     [rsp+408h+var_350], 0FFh
0x18006a21e  mov     word ptr [rsp+408h+var_2E8], r14w
0x18006a227  mov     byte ptr [rsp+408h+var_2E8+2], r14b
0x18006a22f  mov     byte ptr [rsp+408h+var_2E8+3], r12b
0x18006a237  movzx   ecx, r14w
0x18006a23b  mov     [rsp+408h+var_3C8], cx
0x18006a240  cmp     cx, 0Ch
0x18006a244  jnb     short loc_18006A257
0x18006a246  movzx   eax, cx
0x18006a249  mov     [rsp+rax*8+408h+var_348], r14
0x18006a251  add     cx, r12w
0x18006a255  jmp     short loc_18006A23B
0x18006a257  mov     r9d, 4
0x18006a25d  mov     edx, 8004203Fh
0x18006a262  lea     rcx, [rsp+408h+var_1A8]
0x18006a26a  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18006a26f  nop
0x18006a270  lea     rax, [rsp+408h+var_90]
0x18006a278  mov     [rsp+408h+var_3B0], rax
0x18006a27d  lea     rcx, [rsp+408h+var_90]
0x18006a285  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x18006a28a  nop
0x18006a28b  cmp     [rsp+408h+var_A0], 8
0x18006a294  jb      short loc_18006A2A3
0x18006a296  mov     rcx, [rsp+408h+Block]; Block
0x18006a29e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006a2a3  mov     [rsp+408h+var_A0], 7
0x18006a2af  mov     [rsp+408h+var_A8], r14
0x18006a2b7  mov     word ptr [rsp+408h+Block], r14w
0x18006a2c0  mov     rcx, [rsp+408h+bstrString]; bstrString
0x18006a2c5  call    cs:__imp_SysFreeString
0x18006a2cb  nop
0x18006a2cc  test    rbx, rbx
0x18006a2cf  jz      short loc_18006A2E1
0x18006a2d1  mov     rax, [rbx]
0x18006a2d4  mov     rcx, rbx
0x18006a2d7  mov     rax, [rax+10h]
0x18006a2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2e0  nop
0x18006a2e1  jmp     short loc_18006A314
0x18006a2e3  lea     rdx, [rsp+408h+Block]
0x18006a2eb  cmp     [rsp+408h+var_A0], 8
0x18006a2f4  cmovnb  rdx, [rsp+408h+Block]; Src
0x18006a2fd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006a301  inc     r8
0x18006a304  cmp     [rdx+r8*2], r14w
0x18006a309  jz      loc_18006A6E0
0x18006a30f  jmp     short loc_18006A301
0x18006a311  xor     r14d, r14d
0x18006a314  lea     rax, aBaseFsFsrmServ_24; "base\\fs\\fsrm\\service\\classmanager\\"...
0x18006a31b  lea     rcx, aCclassmanagerS_0; "CClassManager::SetFileProperty"
0x18006a322  lea     rdx, aSrmclscc; "SRMCLSCC"
0x18006a329  cmp     [rsp+408h+var_E8], r14
0x18006a331  jnz     short loc_18006A349
0x18006a333  lea     rcx, [rsp+408h+var_1A8]; this
0x18006a33b  call    ?SetComError@CSrmFunctionTracer@@QEAAXXZ; CSrmFunctionTracer::SetComError(void)
0x18006a340  jmp     loc_18006A423
0x18006a345  jmp     short loc_18006A311
0x18006a347  jmp     short loc_18006A311
0x18006a349  lea     r8, [rsp+408h+var_2D0]
0x18006a351  mov     [rsp+408h+var_3B0], r8
0x18006a356  mov     [rsp+408h+var_370], rax
0x18006a35e  mov     [rsp+408h+var_368], rcx
0x18006a366  mov     [rsp+408h+var_360], rdx
0x18006a36e  mov     [rsp+408h+var_358], 661h
0x18006a379  mov     [rsp+408h+var_354], 15h
0x18006a384  mov     [rsp+408h+var_350], 0FFh
0x18006a38f  mov     [rsp+408h+var_2E8], 1000000h
0x18006a39a  xor     edx, edx; Val
0x18006a39c  lea     r8d, [rdx+60h]; Size
0x18006a3a0  lea     rcx, [rsp+408h+var_348]; void *
0x18006a3a8  call    memset_0
0x18006a3ad  nop
0x18006a3ae  mov     r8d, [rsp+408h+dwMessageId]; dwMessageId
0x18006a3b6  lea     rdx, [rsp+408h+var_240]; this
0x18006a3be  lea     rcx, [rsp+408h+var_370]; struct CSrmDebugInfo *
0x18006a3c6  call    ??6CSrmDebugInfo@@QEAA?AU0@J@Z; CSrmDebugInfo::operator<<(long)
0x18006a3cb  nop
0x18006a3cc  lea     r8, [rsp+408h+var_F8]
0x18006a3d4  cmp     [rsp+408h+var_E0], 8
0x18006a3dd  cmovnb  r8, [rsp+408h+var_F8]; unsigned __int16 *
0x18006a3e6  lea     rdx, [rsp+408h+var_2D0]; this
0x18006a3ee  mov     rcx, rax; struct CSrmDebugInfo *
0x18006a3f1  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18006a3f6  nop
0x18006a3f7  mov     r8, rax
0x18006a3fa  lea     rcx, [rsp+408h+var_1A8]
0x18006a402  call    ?SetError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@@Z; CSrmFunctionTracer::SetError(ulong,CSrmDebugInfo)
0x18006a407  nop
0x18006a408  lea     rcx, [rsp+408h+var_240]; this
0x18006a410  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18006a415  nop
0x18006a416  lea     rcx, [rsp+408h+var_370]; this
0x18006a41e  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18006a423  mov     ebx, [rsp+408h+dwMessageId]
  ... truncated ...
```
