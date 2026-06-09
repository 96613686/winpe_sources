# CSyncSharePartnershipManagerInternal::GetPartnership(ushort *,ISyncSharePartnershipDescriptor * *)

- ea: `0x180018ba0`
- end: `0x180018f7e`
- name: `?GetPartnership@CSyncSharePartnershipManagerInternal@@UEAAJPEAGPEAPEAUISyncSharePartnershipDescriptor@@@Z`
- size: `990`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *, struct ISyncSharePartnershipDescriptor **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009158`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001511c`
- `0x18001520c`
- `0x18001588c`
- `0x1800164c4`
- `0x1800165d0`
- `0x180018ba0`
- `0x18001a0d0`
- `0x18001a274`
- `0x180023e64`
- `0x18002612c`
- `0x180026270`
- `0x18002663c`
- `0x18013e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180018f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180018efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180018f09`
- `OLEAUT32!__imp_SysStringLen` at `0x180018c4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180018c4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f3a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180018cc4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180018cc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSyncSharePartnershipManagerInternal::GetPartnership(
        CSyncStateManager **this,
        unsigned __int16 *a2,
        struct ISyncSharePartnershipDescriptor **a3)
{
  _BYTE *v6; // rax
  char v7; // al
  HRESULT v8; // eax
  unsigned __int64 QuotaBytes; // r15
  unsigned __int64 UsedBytes; // r14
  int v11; // eax
  CSyncSharePartnershipDescriptor *v12; // rdi
  int v13; // eax
  const unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // rax
  __int16 v16; // ax
  __int16 v17; // r9
  struct ISyncSharePartnershipDescriptor *v18; // rax
  unsigned int v19; // ebx
  int v21; // [rsp+40h] [rbp-2D8h] BYREF
  int v22; // [rsp+44h] [rbp-2D4h]
  char v23; // [rsp+48h] [rbp-2D0h]
  const char *v24; // [rsp+50h] [rbp-2C8h]
  __int64 v25; // [rsp+58h] [rbp-2C0h]
  BSTR bstrString; // [rsp+60h] [rbp-2B8h] BYREF
  BSTR v27; // [rsp+68h] [rbp-2B0h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-2A8h] BYREF
  int v29; // [rsp+74h] [rbp-2A4h] BYREF
  HRESULT v30; // [rsp+78h] [rbp-2A0h] BYREF
  int v31; // [rsp+7Ch] [rbp-29Ch] BYREF
  int v32; // [rsp+80h] [rbp-298h] BYREF
  CSyncShareExtendedInfo *v33; // [rsp+88h] [rbp-290h] BYREF
  __int64 v34; // [rsp+90h] [rbp-288h] BYREF
  BSTR v35; // [rsp+98h] [rbp-280h] BYREF
  int v36; // [rsp+A0h] [rbp-278h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-270h] BYREF
  char v38; // [rsp+B0h] [rbp-268h]
  const ATL::CAtlException *v39; // [rsp+B8h] [rbp-260h] BYREF
  _BYTE v40[32]; // [rsp+C0h] [rbp-258h] BYREF
  _BYTE v41[168]; // [rsp+E0h] [rbp-238h] BYREF
  _BYTE v42[312]; // [rsp+188h] [rbp-190h] BYREF
  _BYTE v43[32]; // [rsp+2C0h] [rbp-58h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v7 = 0;
LABEL_9:
  v21 = 0;
  v22 = 929;
  v23 = v7;
  v24 = "CSyncSharePartnershipManagerInternal::GetPartnership";
  v25 = 0;
  if ( a3 )
    *a3 = 0;
  try
  {
    if ( !SysStringLen(a2) )
    {
      v21 = -2147024809;
      HIWORD(v22) = 934;
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v22) = 934;
    v21 = 0;
    if ( !a3 )
    {
      v21 = -2147024809;
      HIWORD(v22) = 935;
      v29 = -2147024809;
      throw (long *)&v29;
    }
    LOWORD(v22) = 935;
    v8 = CoImpersonateClient();
    v21 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v22) = 937;
      v30 = v8;
      throw (long *)&v30;
    }
    LOWORD(v22) = 937;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, this + 27);
    CSyncStateManager::AddImpersonatingUser(this[18], (__int64)v40);
    std::wstring::~wstring(v40);
    CSyncStateManager::GetPartnershipById(this[18], v41, a2);
    QuotaBytes = CSyncStateManager::GetQuotaBytes(this[18], a2);
    UsedBytes = CSyncStateManager::GetUsedBytes(this[18], a2);
    bstrString = 0;
    v11 = ATL::CComObject<CSyncSharePartnershipDescriptor>::CreateInstance(&bstrString);
    v21 = v11;
    if ( v11 < 0 )
    {
      HIWORD(v22) = 948;
      v31 = v11;
      throw (long *)&v31;
    }
    LOWORD(v22) = 948;
    v12 = (CSyncSharePartnershipDescriptor *)bstrString;
    v27 = bstrString;
    if ( bstrString )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
    CSyncSharePartnershipDescriptor::Initialize(v12, (struct ClientPartnershipDescriptor *)v41);
    v33 = 0;
    v13 = ATL::CComObject<CSyncShareExtendedInfo>::CreateInstance(&v33);
    v21 = v13;
    if ( v13 < 0 )
    {
      HIWORD(v22) = 954;
      v32 = v13;
      throw (long *)&v32;
    }
    LOWORD(v22) = 954;
    v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v35, v14);
    v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v15);
    v16 = -1;
    if ( v42[227] )
      v17 = -1;
    else
      v17 = 0;
    if ( !v42[212] )
      v16 = 0;
    CSyncShareExtendedInfo::Initialize(v33, v35, bstrString, v17, v16, QuotaBytes, UsedBytes);
    ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(&v34, v33);
    (*(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)v27 + 192LL))(v27, v34);
    v18 = (struct ISyncSharePartnershipDescriptor *)v27;
    v27 = 0;
    *a3 = v18;
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v34);
    SysFreeString(bstrString);
    SysFreeString(v35);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v27);
    ClientPartnershipDescriptor::~ClientPartnershipDescriptor((ClientPartnershipDescriptor *)v41);
    if ( v38 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v38 = 0;
    }
  }
  catch ( long v36 )
  {
    v21 = v36;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v22) = 973;
    v21 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v22) = 973;
    v21 = -2147418113;
  }
  catch ( const ATL::CAtlException *v39 )
  {
    HIWORD(v22) = 973;
    v21 = *(_DWORD *)v39;
  }
  v19 = v21;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v21);
  return v19;
}

```

## disassembly

```asm
0x180018ba0  push    rbx
0x180018ba2  push    rsi
0x180018ba3  push    rdi
0x180018ba4  push    r14
0x180018ba6  push    r15
0x180018ba8  sub     rsp, 2F0h
0x180018baf  mov     rax, cs:__security_cookie
0x180018bb6  xor     rax, rsp
0x180018bb9  mov     [rsp+318h+var_38], rax
0x180018bc1  mov     rsi, r8
0x180018bc4  mov     rdi, rdx
0x180018bc7  mov     r14, rcx
0x180018bca  lea     rcx, WPP_GLOBAL_Control
0x180018bd1  mov     rax, cs:WPP_GLOBAL_Control
0x180018bd8  cmp     rax, rcx
0x180018bdb  jz      short loc_180018C05
0x180018bdd  test    byte ptr [rax+44h], 8
0x180018be1  jz      short loc_180018C17
0x180018be3  cmp     byte ptr [rax+41h], 6
0x180018be7  jb      short loc_180018C05
0x180018be9  mov     edx, 46h ; 'F'
0x180018bee  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180018bf5  mov     rcx, [rax+38h]
0x180018bf9  call    WPP_SF_
0x180018bfe  mov     rax, cs:WPP_GLOBAL_Control
0x180018c05  test    byte ptr [rax+44h], 8
0x180018c09  jz      short loc_180018C17
0x180018c0b  cmp     byte ptr [rax+41h], 6
0x180018c0f  jb      short loc_180018C17
0x180018c11  mov     al, 1
0x180018c13  xor     ebx, ebx
0x180018c15  jmp     short loc_180018C1B
0x180018c17  xor     ebx, ebx
0x180018c19  mov     al, bl
0x180018c1b  mov     [rsp+318h+var_2D8], ebx
0x180018c1f  mov     [rsp+318h+var_2D4], 3A1h
0x180018c27  mov     [rsp+318h+var_2D0], al
0x180018c2b  lea     rax, aCsyncsharepart_48; "CSyncSharePartnershipManagerInternal::G"...
0x180018c32  mov     [rsp+318h+var_2C8], rax
0x180018c37  mov     [rsp+318h+var_2C0], rbx
0x180018c3c  test    rsi, rsi
0x180018c3f  jz      short loc_180018C44
0x180018c41  mov     [rsi], rbx
0x180018c44  mov     eax, [rsp+318h+var_2D8]
0x180018c48  mov     [rsp+318h+var_2D8], eax
0x180018c4c  mov     rcx, rdi; pbstr
0x180018c4f  call    cs:__imp_SysStringLen
0x180018c55  mov     ecx, 3A6h
0x180018c5a  test    eax, eax
0x180018c5c  jnz     short loc_180018C81
0x180018c5e  mov     eax, 80070057h
0x180018c63  mov     [rsp+318h+var_2D8], eax
0x180018c67  mov     word ptr [rsp+318h+var_2D4+2], cx
0x180018c6c  mov     [rsp+318h+pExceptionObject], eax
0x180018c70  lea     rdx, _TI1J; pThrowInfo
0x180018c77  lea     rcx, [rsp+318h+pExceptionObject]; pExceptionObject
0x180018c7c  call    _CxxThrowException_0
0x180018c81  mov     [rsp+318h+var_2D8], ebx
0x180018c85  mov     word ptr [rsp+318h+var_2D4], cx
0x180018c8a  mov     [rsp+318h+var_2D8], ebx
0x180018c8e  mov     ecx, 3A7h
0x180018c93  test    rsi, rsi
0x180018c96  jnz     short loc_180018CBB
0x180018c98  mov     eax, 80070057h
0x180018c9d  mov     [rsp+318h+var_2D8], eax
0x180018ca1  mov     word ptr [rsp+318h+var_2D4+2], cx
0x180018ca6  mov     [rsp+318h+var_2A4], eax
0x180018caa  lea     rdx, _TI1J; pThrowInfo
0x180018cb1  lea     rcx, [rsp+318h+var_2A4]; pExceptionObject
0x180018cb6  call    _CxxThrowException_0
0x180018cbb  mov     [rsp+318h+var_2D8], ebx
0x180018cbf  mov     word ptr [rsp+318h+var_2D4], cx
0x180018cc4  call    cs:__imp_CoImpersonateClient
0x180018cca  mov     [rsp+318h+var_2D8], eax
0x180018cce  mov     [rsp+318h+var_2D8], eax
0x180018cd2  mov     ecx, 3A9h
0x180018cd7  test    eax, eax
0x180018cd9  jns     short loc_180018CF5
0x180018cdb  mov     word ptr [rsp+318h+var_2D4+2], cx
0x180018ce0  mov     [rsp+318h+var_2A0], eax
0x180018ce4  lea     rdx, _TI1J; pThrowInfo
0x180018ceb  lea     rcx, [rsp+318h+var_2A0]; pExceptionObject
0x180018cf0  call    _CxxThrowException_0
0x180018cf5  mov     word ptr [rsp+318h+var_2D4], cx
0x180018cfa  lea     rdx, [r14+0D8h]
0x180018d01  lea     rcx, [rsp+318h+lpCriticalSection]
0x180018d09  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180018d0e  nop
0x180018d0f  lea     rdx, [rsp+318h+var_258]
0x180018d17  mov     rcx, [r14+90h]; this
0x180018d1e  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x180018d23  lea     rcx, [rsp+318h+var_258]
0x180018d2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d30  mov     r8, rdi
0x180018d33  lea     rdx, [rsp+318h+var_238]
0x180018d3b  mov     rcx, [r14+90h]
0x180018d42  call    ?GetPartnershipById@CSyncStateManager@@QEAA?AVClientPartnershipDescriptor@@PEBG@Z; CSyncStateManager::GetPartnershipById(ushort const *)
0x180018d47  nop
0x180018d48  mov     rdx, rdi; unsigned __int16 *
0x180018d4b  mov     rcx, [r14+90h]; this
0x180018d52  call    ?GetQuotaBytes@CSyncStateManager@@QEAA_KPEBG@Z; CSyncStateManager::GetQuotaBytes(ushort const *)
0x180018d57  mov     r15, rax
0x180018d5a  mov     rdx, rdi; unsigned __int16 *
0x180018d5d  mov     rcx, [r14+90h]; this
0x180018d64  call    ?GetUsedBytes@CSyncStateManager@@QEAA_KPEBG@Z; CSyncStateManager::GetUsedBytes(ushort const *)
0x180018d69  mov     r14, rax
0x180018d6c  mov     [rsp+318h+bstrString], rbx
0x180018d71  lea     rcx, [rsp+318h+bstrString]
0x180018d76  call    ?CreateInstance@?$CComObject@VCSyncSharePartnershipDescriptor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncSharePartnershipDescriptor>::CreateInstance(ATL::CComObject<CSyncSharePartnershipDescriptor> * *)
0x180018d7b  mov     [rsp+318h+var_2D8], eax
0x180018d7f  mov     [rsp+318h+var_2D8], eax
0x180018d83  mov     ecx, 3B4h
0x180018d88  test    eax, eax
0x180018d8a  jns     short loc_180018DA6
0x180018d8c  mov     word ptr [rsp+318h+var_2D4+2], cx
0x180018d91  mov     [rsp+318h+var_29C], eax
0x180018d95  lea     rdx, _TI1J; pThrowInfo
0x180018d9c  lea     rcx, [rsp+318h+var_29C]; pExceptionObject
0x180018da1  call    _CxxThrowException_0
0x180018da6  mov     word ptr [rsp+318h+var_2D4], cx
0x180018dab  mov     rdi, [rsp+318h+bstrString]
0x180018db0  mov     [rsp+318h+var_2B0], rdi
0x180018db5  test    rdi, rdi
0x180018db8  jz      short loc_180018DCA
0x180018dba  mov     rax, [rdi]
0x180018dbd  mov     rcx, rdi
0x180018dc0  mov     rax, [rax+8]
0x180018dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dc9  nop
0x180018dca  lea     rdx, [rsp+318h+var_238]; struct ClientPartnershipDescriptor *
0x180018dd2  mov     rcx, rdi; this
0x180018dd5  call    ?Initialize@CSyncSharePartnershipDescriptor@@QEAAXAEAVClientPartnershipDescriptor@@@Z; CSyncSharePartnershipDescriptor::Initialize(ClientPartnershipDescriptor &)
0x180018dda  mov     [rsp+318h+var_290], rbx
0x180018de2  lea     rcx, [rsp+318h+var_290]
0x180018dea  call    ?CreateInstance@?$CComObject@VCSyncShareExtendedInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncShareExtendedInfo>::CreateInstance(ATL::CComObject<CSyncShareExtendedInfo> * *)
0x180018def  mov     [rsp+318h+var_2D8], eax
0x180018df3  mov     [rsp+318h+var_2D8], eax
0x180018df7  mov     ecx, 3BAh
0x180018dfc  test    eax, eax
0x180018dfe  jns     short loc_180018E20
0x180018e00  mov     word ptr [rsp+318h+var_2D4+2], cx
0x180018e05  mov     [rsp+318h+var_298], eax
0x180018e0c  lea     rdx, _TI1J; pThrowInfo
0x180018e13  lea     rcx, [rsp+318h+var_298]; pExceptionObject
0x180018e1b  call    _CxxThrowException_0
0x180018e20  mov     word ptr [rsp+318h+var_2D4], cx
0x180018e25  lea     rcx, [rsp+318h+var_190]
0x180018e2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018e32  mov     rdx, rax; unsigned __int16 *
0x180018e35  lea     rcx, [rsp+318h+var_280]; this
0x180018e3d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180018e42  nop
0x180018e43  lea     rcx, [rsp+318h+var_58]
0x180018e4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018e50  mov     rdx, rax; unsigned __int16 *
0x180018e53  lea     rcx, [rsp+318h+bstrString]; this
0x180018e58  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180018e5d  nop
0x180018e5e  or      eax, 0FFFFFFFFh
0x180018e61  cmp     [rsp+318h+var_AD], bl
0x180018e68  jz      short loc_180018E70
0x180018e6a  movzx   r9d, ax
0x180018e6e  jmp     short loc_180018E73
0x180018e70  mov     r9d, ebx; __int16
0x180018e73  cmp     [rsp+318h+var_BC], bl
0x180018e7a  jnz     short loc_180018E7F
0x180018e7c  movzx   eax, bx
0x180018e7f  mov     [rsp+318h+var_2E8], r14; unsigned __int64
0x180018e84  mov     [rsp+318h+var_2F0], r15; unsigned __int64
0x180018e89  mov     [rsp+318h+var_2F8], ax; __int16
0x180018e8e  mov     r8, [rsp+318h+bstrString]; unsigned __int16 *
0x180018e93  mov     rdx, [rsp+318h+var_280]; unsigned __int16 *
0x180018e9b  mov     rcx, [rsp+318h+var_290]; this
0x180018ea3  call    ?Initialize@CSyncShareExtendedInfo@@QEAAXPEBG0FF_K1@Z; CSyncShareExtendedInfo::Initialize(ushort const *,ushort const *,short,short,unsigned __int64,unsigned __int64)
0x180018ea8  mov     rdx, [rsp+318h+var_290]
0x180018eb0  lea     rcx, [rsp+318h+var_288]
0x180018eb8  call    ??0?$CComPtr@UISyncShareExtendedInfo@@@ATL@@QEAA@PEAUISyncShareExtendedInfo@@@Z; ATL::CComPtr<ISyncShareExtendedInfo>::CComPtr<ISyncShareExtendedInfo>(ISyncShareExtendedInfo *)
0x180018ebd  nop
0x180018ebe  mov     rcx, [rsp+318h+var_2B0]
0x180018ec3  mov     rax, [rcx]
0x180018ec6  mov     rdx, [rsp+318h+var_288]
0x180018ece  mov     rax, [rax+0C0h]
0x180018ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eda  mov     rax, [rsp+318h+var_2B0]
0x180018edf  mov     [rsp+318h+var_2B0], rbx
0x180018ee4  mov     [rsi], rax
0x180018ee7  lea     rcx, [rsp+318h+var_288]
0x180018eef  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x180018ef4  nop
0x180018ef5  mov     rcx, [rsp+318h+bstrString]; bstrString
0x180018efa  call    cs:__imp_SysFreeString
0x180018f00  nop
0x180018f01  mov     rcx, [rsp+318h+var_280]; bstrString
0x180018f09  call    cs:__imp_SysFreeString
0x180018f0f  nop
0x180018f10  lea     rcx, [rsp+318h+var_2B0]
0x180018f15  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x180018f1a  nop
0x180018f1b  lea     rcx, [rsp+318h+var_238]; this
0x180018f23  call    ??1ClientPartnershipDescriptor@@QEAA@XZ; ClientPartnershipDescriptor::~ClientPartnershipDescriptor(void)
0x180018f28  nop
0x180018f29  cmp     [rsp+318h+var_268], bl
0x180018f30  jz      short loc_180018F47
0x180018f32  mov     rcx, [rsp+318h+lpCriticalSection]; lpCriticalSection
0x180018f3a  call    cs:__imp_LeaveCriticalSection
0x180018f40  mov     [rsp+318h+var_268], bl
0x180018f47  jmp     short loc_180018F4F
0x180018f49  jmp     short loc_180018F4F
0x180018f4b  jmp     short loc_180018F4F
0x180018f4d  jmp     short $+2
0x180018f4f  mov     ebx, [rsp+318h+var_2D8]
0x180018f53  lea     rcx, [rsp+318h+var_2D8]; this
0x180018f58  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180018f5d  mov     eax, ebx
0x180018f5f  mov     rcx, [rsp+318h+var_38]
0x180018f67  xor     rcx, rsp; StackCookie
0x180018f6a  call    __security_check_cookie
0x180018f6f  add     rsp, 2F0h
0x180018f76  pop     r15
0x180018f78  pop     r14
0x180018f7a  pop     rdi
0x180018f7b  pop     rsi
0x180018f7c  pop     rbx
0x180018f7d  retn
```
