# CPropertyBagProxy::LoadFromSecDescr(void)

- ea: `0x180046e20`
- end: `0x1800473b2`
- name: `?LoadFromSecDescr@CPropertyBagProxy@@UEAAJXZ`
- size: `1426`
- prototype: `__int64 __fastcall(CPropertyBagProxy *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001304`
- `0x180001350`
- `0x1800020ba`
- `0x180002520`
- `0x180002a6c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18003ff90`
- `0x180043dac`
- `0x180044048`
- `0x180046e20`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18007c000`
- `0x180083a68`
- `0x180083c24`
- `0x180084bc4`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18004705d`
- `KERNEL32!CreateFileW` at `0x18004705d`
- `KERNEL32!CloseHandle` at `0x180047147`
- `KERNEL32!CloseHandle` at `0x180047147`
- `KERNEL32!LocalFree` at `0x1800471f9`
- `KERNEL32!LocalFree` at `0x1800471f9`
- `ADVAPI32!GetSecurityInfo` at `0x1800470ba`
- `ADVAPI32!GetSecurityInfo` at `0x1800470ba`

## string_xrefs

- `0x180046e5e`: `base\fs\fsrm\service\modulewrp\propertybagproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CPropertyBagProxy::LoadFromSecDescr(CPropertyBagProxy *this)
{
  int v2; // eax
  _QWORD *v3; // rax
  const char *v4; // rdx
  char *v5; // r12
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  HANDLE FileW; // rsi
  signed int SecurityInfo; // eax
  __int64 v11; // rdx
  PSECURITY_DESCRIPTOR v12; // r15
  char *v13; // rdi
  char *v14; // rbx
  char *v15; // r14
  __int64 v16; // rcx
  char *i; // rbx
  unsigned int v18; // ebx
  _QWORD *v20; // r8
  char *v21; // rdx
  int Hr; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  int LastFailureAsHRESULT; // eax
  char v27; // al
  char v28[8]; // [rsp+60h] [rbp-248h] BYREF
  void *v29; // [rsp+68h] [rbp-240h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+70h] [rbp-238h] BYREF
  PACL ppSacl; // [rsp+78h] [rbp-230h] BYREF
  int v32; // [rsp+80h] [rbp-228h] BYREF
  char *v33; // [rsp+88h] [rbp-220h]
  char *v34; // [rsp+90h] [rbp-218h]
  char *v35; // [rsp+98h] [rbp-210h]
  void *Block[2]; // [rsp+A0h] [rbp-208h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-1F8h]
  char v38[8]; // [rsp+C0h] [rbp-1E8h] BYREF
  _QWORD *v39; // [rsp+C8h] [rbp-1E0h]
  __int64 v40; // [rsp+D0h] [rbp-1D8h]
  _com_error *v41; // [rsp+E0h] [rbp-1C8h] BYREF
  const exception *v42; // [rsp+E8h] [rbp-1C0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+F0h] [rbp-1B8h] BYREF
  _QWORD v44[3]; // [rsp+108h] [rbp-1A0h] BYREF
  int v45; // [rsp+120h] [rbp-188h]
  int v46; // [rsp+124h] [rbp-184h]
  int v47; // [rsp+128h] [rbp-180h]
  _DWORD v48[26]; // [rsp+130h] [rbp-178h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+198h] [rbp-110h] BYREF
  __int64 v50; // [rsp+1A8h] [rbp-100h]
  unsigned __int64 v51; // [rsp+1B0h] [rbp-F8h]
  void **v52; // [rsp+1C0h] [rbp-E8h] BYREF
  int v53; // [rsp+1C8h] [rbp-E0h]
  unsigned int v54; // [rsp+1ECh] [rbp-BCh]

  v35 = (char *)v44;
  v44[0] = L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp";
  v44[1] = L"CPropertyBagProxy::LoadFromSecDescr";
  v44[2] = L"PROPBGPC";
  v45 = 947;
  v46 = 22;
  v47 = 255;
  v48[24] = 0x1000000;
  memset_0(v48, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v52, (const struct CSrmDebugInfo *)v44, 0);
  try
  {
    v29 = 0;
    v2 = (*(__int64 (__fastcall **)(CPropertyBagProxy *, void **))(*(_QWORD *)this + 64LL))(this, &v29);
    v53 = v2;
    if ( v2 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v52);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v52, Hr);
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v52);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v52, 0x3B9u, v23, 0);
    }
    v53 = v2;
    CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)v28, (char *)v29);
    v51 = 7;
    v50 = 0;
    LOWORD(lpFileName[0]) = 0;
    v40 = 0;
    v3 = operator new(0x50u);
    if ( !v3 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v4);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v39 = v3;
    *v3 = v3;
    v3[1] = v39;
    v3[2] = v39;
    *((_BYTE *)v3 + 72) = 1;
    *((_BYTE *)v3 + 73) = 1;
    hMem = 0;
    ppSacl = 0;
    *(_OWORD *)Block = 0;
    v37 = 0;
    v5 = (char *)this + 80;
    CPropertyBagFieldsBase::BuildFullPath((char *)this + 80, 0, 0, lpFileName);
    SrmConvertToLongPath(lpFileName);
    v6 = (const WCHAR *)lpFileName;
    if ( v51 >= 8 )
      v6 = lpFileName[0];
    FileW = CreateFileW(v6, 0x20000u, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v52, LastFailureAsHRESULT);
      v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v52);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v52, 0x3D1u, v27, 0);
    }
    v53 = 0;
    SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 0x20u, 0, 0, 0, &ppSacl, &hMem);
    if ( SecurityInfo > 0 )
      SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
    v53 = SecurityInfo;
    if ( SecurityInfo < 0 )
    {
      v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v52);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v52, v24);
      v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v52);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v52, 0x3DAu, v25, 0);
    }
    v53 = SecurityInfo;
    v12 = hMem;
    SrmParseResourceControlList(ppSacl, v11, (char **)Block);
    v13 = (char *)Block[0];
    v14 = (char *)Block[0];
    v34 = (char *)Block[0];
    v15 = (char *)Block[1];
    while ( 1 )
    {
      v35 = v15;
      if ( v14 == v15 )
        break;
      v20 = v14 + 40;
      if ( *((_QWORD *)v14 + 8) >= 8u )
        v20 = (_QWORD *)*v20;
      if ( *((_QWORD *)v14 + 3) < 8u )
        v21 = v14;
      else
        v21 = *(char **)v14;
      (*(void (__fastcall **)(char *, char *, _QWORD *, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v5 + 80LL))(
        v5,
        v21,
        v20,
        *((unsigned int *)v14 + 20),
        0,
        *((_DWORD *)v14 + 21));
      v14 += 88;
      v34 = v14;
    }
    CloseHandle(FileW);
    if ( v13 )
    {
      for ( i = v13; ; i += 88 )
      {
        v33 = i;
        if ( i == v15 )
          break;
        std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v16, i);
      }
      operator delete(v13);
    }
    *(_OWORD *)Block = 0;
    v37 = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v38);
    if ( v51 >= 8 )
      operator delete((void *)lpFileName[0]);
    v51 = 7;
    v50 = 0;
    LOWORD(lpFileName[0]) = 0;
    if ( v12 )
      LocalFree(v12);
    CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v28);
  }
  catch ( long v32 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v52,
      v32,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::LoadFromSecDescr",
      0x3E7u,
      v54);
  }
  catch ( _com_error *v41 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v52,
      v41,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::LoadFromSecDescr",
      0x3E7u,
      v54);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v52,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::LoadFromSecDescr",
      0x3E7u,
      v54);
  }
  catch ( const exception *v42 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v52,
      v42,
      L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
      L"PROPBGPC",
      L"CPropertyBagProxy::LoadFromSecDescr",
      0x3E7u,
      v54);
  }
  v18 = v53;
  v52 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v52);
  return v18;
}

```

## disassembly

```asm
0x180046e20  mov     r11, rsp
0x180046e23  mov     [r11+10h], rbx
0x180046e27  mov     [r11+18h], rsi
0x180046e2b  push    rdi
0x180046e2c  push    r12
0x180046e2e  push    r13
0x180046e30  push    r14
0x180046e32  push    r15
0x180046e34  sub     rsp, 280h
0x180046e3b  mov     rax, cs:__security_cookie
0x180046e42  xor     rax, rsp
0x180046e45  mov     [rsp+2A8h+var_38], rax
0x180046e4d  mov     rbx, rcx
0x180046e50  lea     rax, [r11-1A0h]
0x180046e57  mov     [r11-210h], rax
0x180046e5e  lea     rax, aBaseFsFsrmServ_8; "base\\fs\\fsrm\\service\\modulewrp\\pro"...
0x180046e65  mov     [r11-1A0h], rax
0x180046e6c  lea     rax, aCpropertybagpr_31; "CPropertyBagProxy::LoadFromSecDescr"
0x180046e73  mov     [r11-198h], rax
0x180046e7a  lea     rax, aPropbgpc; "PROPBGPC"
0x180046e81  mov     [r11-190h], rax
0x180046e88  mov     [rsp+2A8h+var_188], 3B3h
0x180046e93  mov     [rsp+2A8h+var_184], 16h
0x180046e9e  mov     [rsp+2A8h+var_180], 0FFh
0x180046ea9  xor     r13d, r13d
0x180046eac  mov     [rsp+2A8h+var_118], 1000000h
0x180046eb7  xor     edx, edx; Val
0x180046eb9  lea     r8d, [r13+60h]; Size
0x180046ebd  lea     rcx, [r11-178h]; void *
0x180046ec4  call    memset_0
0x180046ec9  nop
0x180046eca  xor     r8d, r8d
0x180046ecd  lea     rdx, [rsp+2A8h+var_1A0]
0x180046ed5  lea     rcx, [rsp+2A8h+var_E8]
0x180046edd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180046ee2  nop
0x180046ee3  mov     [rsp+2A8h+var_240], r13
0x180046ee8  mov     rax, [rbx]
0x180046eeb  lea     rdx, [rsp+2A8h+var_240]
0x180046ef0  mov     rcx, rbx
0x180046ef3  mov     rax, [rax+40h]
0x180046ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046efc  mov     [rsp+2A8h+var_E0], eax
0x180046f03  test    eax, eax
0x180046f05  js      loc_1800472D2
0x180046f0b  mov     [rsp+2A8h+var_E0], eax
0x180046f12  mov     rdx, [rsp+2A8h+var_240]; void *
0x180046f17  lea     rcx, [rsp+2A8h+var_248]; this
0x180046f1c  call    ??0CSrmImpersonationSession@@QEAA@PEAX@Z; CSrmImpersonationSession::CSrmImpersonationSession(void *)
0x180046f21  nop
0x180046f22  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180046f29  mov     [rsp+2A8h+var_268], rax
0x180046f2e  mov     [rsp+2A8h+var_260], r13
0x180046f33  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x180046f3a  mov     [rsp+2A8h+var_268], rax
0x180046f3f  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoLocalPtr_Storage@PEAX@@@@6B@; const CSrmAuto<void *,CSrmAutoLocalPtr_Storage<void *>>::`vftable'
0x180046f46  mov     [rsp+2A8h+var_268], rax
0x180046f4b  mov     [rsp+2A8h+var_260], r13
0x180046f50  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoLocalPtr_Storage@PEAX@@@@6B@; const CSrmAuto<void *,CSrmAutoLocalPtr_Storage<void *>>::`vftable'
0x180046f57  mov     [rsp+2A8h+var_268], rax
0x180046f5c  mov     esi, 7
0x180046f61  mov     [rsp+2A8h+var_F8], rsi
0x180046f69  mov     [rsp+2A8h+var_100], r13
0x180046f71  mov     word ptr [rsp+2A8h+lpFileName], r13w
0x180046f7a  mov     [rsp+2A8h+var_1D8], r13
0x180046f82  lea     ecx, [rsi+49h]; Size
0x180046f85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046f8a  test    rax, rax
0x180046f8d  jz      loc_18004738F
0x180046f93  mov     [rsp+2A8h+var_1E0], rax
0x180046f9b  mov     [rax], rax
0x180046f9e  mov     rcx, [rsp+2A8h+var_1E0]
0x180046fa6  mov     [rax+8], rcx
0x180046faa  mov     rcx, [rsp+2A8h+var_1E0]
0x180046fb2  mov     [rax+10h], rcx
0x180046fb6  mov     byte ptr [rax+48h], 1
0x180046fba  mov     byte ptr [rax+49h], 1
0x180046fbe  mov     [rsp+2A8h+hMem], r13
0x180046fc3  mov     [rsp+2A8h+ppSacl], r13
0x180046fc8  xorps   xmm0, xmm0
0x180046fcb  movdqu  xmmword ptr [rsp+2A8h+Block], xmm0
0x180046fd4  mov     [rsp+2A8h+var_1F8], r13
0x180046fdc  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x180046fe3  mov     [rsp+2A8h+var_258], rax
0x180046fe8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046fec  mov     [rsp+2A8h+var_250], rdi
0x180046ff1  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180046ff8  mov     [rsp+2A8h+var_258], rax
0x180046ffd  lea     r12, [rbx+50h]
0x180047001  lea     r9, [rsp+2A8h+lpFileName]
0x180047009  xor     r8d, r8d
0x18004700c  xor     edx, edx
0x18004700e  mov     rcx, r12
0x180047011  call    ?BuildFullPath@CPropertyBagFieldsBase@@QEBAX_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::BuildFullPath(bool,ushort const *,std::wstring &)
0x180047016  lea     rcx, [rsp+2A8h+lpFileName]
0x18004701e  call    ?SrmConvertToLongPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmConvertToLongPath(std::wstring &)
0x180047023  lea     rcx, [rsp+2A8h+lpFileName]
0x18004702b  cmp     [rsp+2A8h+var_F8], 8
0x180047034  cmovnb  rcx, [rsp+2A8h+lpFileName]; lpFileName
0x18004703d  mov     [rsp+2A8h+hTemplateFile], r13; hTemplateFile
0x180047042  mov     [rsp+2A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18004704a  mov     [rsp+2A8h+dwCreationDisposition], 3; dwCreationDisposition
0x180047052  xor     r9d, r9d; lpSecurityAttributes
0x180047055  mov     r8d, esi; dwShareMode
0x180047058  mov     edx, 20000h; dwDesiredAccess
0x18004705d  call    cs:__imp_CreateFileW
0x180047063  mov     rsi, rax
0x180047066  mov     [rsp+2A8h+var_250], rdi
0x18004706b  mov     [rsp+2A8h+var_250], rax
0x180047070  mov     eax, [rsp+2A8h+var_E0]
0x180047077  mov     [rsp+2A8h+var_E0], eax
0x18004707e  cmp     rsi, rdi
0x180047081  jz      loc_180047355
0x180047087  mov     [rsp+2A8h+var_E0], r13d
0x18004708f  lea     rax, [rsp+2A8h+hMem]
0x180047094  mov     [rsp+2A8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180047099  lea     rax, [rsp+2A8h+ppSacl]
0x18004709e  mov     [rsp+2A8h+hTemplateFile], rax; ppSacl
0x1800470a3  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], r13; ppDacl
0x1800470a8  mov     qword ptr [rsp+2A8h+dwCreationDisposition], r13; ppsidGroup
0x1800470ad  xor     r9d, r9d; ppsidOwner
0x1800470b0  lea     edx, [rdi+2]; ObjectType
0x1800470b3  lea     r8d, [rdi+21h]; SecurityInfo
0x1800470b7  mov     rcx, rsi; handle
0x1800470ba  call    cs:__imp_GetSecurityInfo
0x1800470c0  test    eax, eax
0x1800470c2  jle     short loc_1800470CC
0x1800470c4  movzx   eax, ax
0x1800470c7  or      eax, 80070000h
0x1800470cc  mov     [rsp+2A8h+var_E0], eax
0x1800470d3  test    eax, eax
0x1800470d5  js      loc_180047314
0x1800470db  mov     [rsp+2A8h+var_E0], eax
0x1800470e2  mov     r15, [rsp+2A8h+hMem]
0x1800470e7  mov     [rsp+2A8h+var_260], r13
0x1800470ec  mov     [rsp+2A8h+var_260], r15
0x1800470f1  lea     r8, [rsp+2A8h+Block]
0x1800470f9  mov     rcx, [rsp+2A8h+ppSacl]; pAcl
0x1800470fe  call    ?SrmParseResourceControlList@@YAXPEAU_ACL@@_NAEAV?$vector@USrmSecureProperty@@V?$allocator@USrmSecureProperty@@@std@@@std@@@Z; SrmParseResourceControlList(_ACL *,bool,std::vector<SrmSecureProperty> &)
0x180047103  mov     rdi, [rsp+2A8h+Block]
0x18004710b  mov     rbx, rdi
0x18004710e  mov     [rsp+2A8h+var_218], rbx
0x180047116  mov     r14, [rsp+2A8h+Block+8]
0x18004711e  mov     [rsp+2A8h+var_210], r14
0x180047126  cmp     rbx, r14
0x180047129  jnz     loc_180047272
0x18004712f  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180047136  mov     [rsp+2A8h+var_258], rax
0x18004713b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004713f  cmp     rsi, rbx
0x180047142  jz      short loc_18004714D
0x180047144  mov     rcx, rsi; hObject
0x180047147  call    cs:__imp_CloseHandle
0x18004714d  mov     [rsp+2A8h+var_250], rbx
0x180047152  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x180047159  mov     [rsp+2A8h+var_258], rax
0x18004715e  mov     [rsp+2A8h+var_250], rbx
0x180047163  test    rdi, rdi
0x180047166  jz      short loc_18004718E
0x180047168  mov     rbx, rdi
0x18004716b  mov     [rsp+2A8h+var_220], rbx
0x180047173  cmp     rbx, r14
0x180047176  jz      short loc_180047186
0x180047178  mov     rdx, rbx
0x18004717b  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x180047180  add     rbx, 58h ; 'X'
0x180047184  jmp     short loc_18004716B
0x180047186  mov     rcx, rdi; Block
0x180047189  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004718e  xorps   xmm0, xmm0
0x180047191  movdqu  xmmword ptr [rsp+2A8h+Block], xmm0
0x18004719a  mov     [rsp+2A8h+var_1F8], r13
0x1800471a2  lea     rcx, [rsp+2A8h+var_1E8]
0x1800471aa  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ulong,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x1800471af  nop
0x1800471b0  cmp     [rsp+2A8h+var_F8], 8
0x1800471b9  jb      short loc_1800471C8
0x1800471bb  mov     rcx, [rsp+2A8h+lpFileName]; Block
0x1800471c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800471c8  mov     [rsp+2A8h+var_F8], 7
0x1800471d4  mov     [rsp+2A8h+var_100], r13
0x1800471dc  mov     word ptr [rsp+2A8h+lpFileName], r13w
0x1800471e5  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoLocalPtr_Storage@PEAX@@@@6B@; const CSrmAuto<void *,CSrmAutoLocalPtr_Storage<void *>>::`vftable'
0x1800471ec  mov     [rsp+2A8h+var_268], rax
0x1800471f1  test    r15, r15
0x1800471f4  jz      short loc_1800471FF
0x1800471f6  mov     rcx, r15; hMem
0x1800471f9  call    cs:__imp_LocalFree
0x1800471ff  mov     [rsp+2A8h+var_260], r13
0x180047204  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18004720b  mov     [rsp+2A8h+var_268], rax
0x180047210  mov     [rsp+2A8h+var_260], r13
0x180047215  lea     rcx, [rsp+2A8h+var_248]; this
0x18004721a  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x18004721f  nop
0x180047220  mov     ebx, [rsp+2A8h+var_E0]
0x180047227  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004722e  mov     [rsp+2A8h+var_E8], rax
0x180047236  lea     rcx, [rsp+2A8h+var_E8]; this
0x18004723e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180047243  mov     eax, ebx
0x180047245  mov     rcx, [rsp+2A8h+var_38]
0x18004724d  xor     rcx, rsp; StackCookie
0x180047250  call    __security_check_cookie
0x180047255  lea     r11, [rsp+2A8h+var_28]
0x18004725d  mov     rbx, [r11+38h]
0x180047261  mov     rsi, [r11+40h]
0x180047265  mov     rsp, r11
0x180047268  pop     r15
0x18004726a  pop     r14
0x18004726c  pop     r13
0x18004726e  pop     r12
0x180047270  pop     rdi
0x180047271  retn
0x180047272  mov     rax, [r12]
0x180047276  mov     r10, [rax+50h]
0x18004727a  mov     eax, [rbx+54h]
0x18004727d  lea     r8, [rbx+28h]
0x180047281  cmp     qword ptr [r8+18h], 8
0x180047286  jb      short loc_18004728B
0x180047288  mov     r8, [r8]
0x18004728b  cmp     qword ptr [rbx+18h], 8
0x180047290  jb      short loc_180047297
0x180047292  mov     rdx, [rbx]
0x180047295  jmp     short loc_18004729A
0x180047297  mov     rdx, rbx
0x18004729a  mov     [rsp+2A8h+dwFlagsAndAttributes], eax
0x18004729e  mov     [rsp+2A8h+dwCreationDisposition], r13d
0x1800472a3  mov     r9d, [rbx+50h]
0x1800472a7  mov     rcx, r12
0x1800472aa  mov     rax, r10
0x1800472ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472b2  add     rbx, 58h ; 'X'
0x1800472b6  mov     [rsp+2A8h+var_218], rbx
0x1800472be  jmp     loc_18004711E
0x1800472c3  jmp     loc_180047220
0x1800472c8  jmp     loc_180047220
0x1800472cd  jmp     loc_180047220
0x1800472d2  lea     rcx, [rsp+2A8h+var_E8]; this
0x1800472da  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800472df  mov     edx, eax; int
0x1800472e1  lea     rcx, [rsp+2A8h+var_E8]; this
0x1800472e9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800472ee  lea     rcx, [rsp+2A8h+var_E8]; this
0x1800472f6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800472fb  mov     r8d, eax; char
0x1800472fe  xor     r9d, r9d; unsigned __int16 *
0x180047301  mov     edx, 3B9h; unsigned int
0x180047306  lea     rcx, [rsp+2A8h+var_E8]; this
0x18004730e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180047314  lea     rcx, [rsp+2A8h+var_E8]; this
0x18004731c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180047321  mov     edx, eax; int
0x180047323  lea     rcx, [rsp+2A8h+var_E8]; this
0x18004732b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180047330  lea     rcx, [rsp+2A8h+var_E8]; this
0x180047338  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004733d  mov     r8d, eax; char
0x180047340  xor     r9d, r9d; unsigned __int16 *
0x180047343  mov     edx, 3DAh; unsigned int
0x180047348  lea     rcx, [rsp+2A8h+var_E8]; this
0x180047350  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180047355  call    GetLastFailureAsHRESULT
0x18004735a  mov     edx, eax; int
0x18004735c  lea     rcx, [rsp+2A8h+var_E8]; this
0x180047364  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180047369  lea     rcx, [rsp+2A8h+var_E8]; this
0x180047371  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180047376  mov     r8d, eax; char
0x180047379  xor     r9d, r9d; unsigned __int16 *
0x18004737c  mov     edx, 3D1h; unsigned int
0x180047381  lea     rcx, [rsp+2A8h+var_E8]; this
0x180047389  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004738f  lea     rcx, [rsp+2A8h+pExceptionObject]; this
0x180047397  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18004739c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800473a3  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x1800473ab  call    _CxxThrowException_0
```
