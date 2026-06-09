# CAdReader::GetConfigurationNamingContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180014ed4`
- end: `0x1800152ee`
- name: `?GetConfigurationNamingContext@CAdReader@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `1050`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001671c`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x180010bc4`
- `0x180014ed4`
- `0x180017fd8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015161`
- `ole32!CoTaskMemFree` at `0x180015161`
- `OLEAUT32!__imp_SysAllocString` at `0x1800150d7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800150d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180015108`
- `OLEAUT32!__imp_SysFreeString` at `0x180015108`
- `OLEAUT32!__imp_VariantInit` at `0x180014fbc`
- `OLEAUT32!__imp_VariantInit` at `0x180014fbc`
- `OLEAUT32!__imp_VariantClear` at `0x18001513d`
- `OLEAUT32!__imp_VariantClear` at `0x18001513d`
- `NETAPI32!DsGetDcNameW` at `0x180014fdf`
- `NETAPI32!DsGetDcNameW` at `0x180014fdf`
- `NETAPI32!NetApiBufferFree` at `0x18001516b`
- `NETAPI32!NetApiBufferFree` at `0x18001516b`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800150b3`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800150b3`

## string_xrefs

- `0x180014f21`: `ADREADRC`
- `0x180014f0a`: `base\fs\fsrm\service\globalstore\adreader.cpp`
- `0x180014f16`: `CAdReader::GetConfigurationNamingContext`
- `0x1800150d0`: `configurationNamingContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CAdReader::GetConfigurationNamingContext(_QWORD *a1, _QWORD *a2)
{
  _WORD *v4; // rcx
  _WORD *v5; // rcx
  signed int DcNameW; // eax
  PDOMAIN_CONTROLLER_INFOW v7; // rax
  PDOMAIN_CONTROLLER_INFOW v8; // r14
  LPWSTR DomainControllerName; // rdx
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rbx
  unsigned __int64 v13; // rdx
  WCHAR *v14; // rbx
  int v15; // eax
  HRESULT Object; // eax
  void *v17; // r12
  __int64 v18; // r13
  BSTR v19; // rax
  OLECHAR *v20; // rsi
  HRESULT v21; // eax
  int v22; // eax
  char v23; // al
  int Hr; // eax
  char v25; // al
  int v26; // eax
  char v27; // al
  int v28; // eax
  char v29; // al
  int v30; // eax
  char v31; // al
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-D0h] BYREF
  void *ppObject; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszPathName; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+48h] [rbp-B8h] BYREF
  PDOMAIN_CONTROLLER_INFOW v36; // [rsp+58h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+94h] [rbp-6Ch]
  int v41; // [rsp+98h] [rbp-68h]
  _BYTE v42[96]; // [rsp+A0h] [rbp-60h] BYREF
  int v43; // [rsp+100h] [rbp+0h]
  void **v44; // [rsp+110h] [rbp+10h] BYREF
  int v45; // [rsp+118h] [rbp+18h]

  v38[0] = L"base\\fs\\fsrm\\service\\globalstore\\adreader.cpp";
  v38[1] = L"CAdReader::GetConfigurationNamingContext";
  v38[2] = L"ADREADRC";
  v39 = 319;
  v40 = 30;
  v41 = 255;
  v43 = 0x1000000;
  memset_0(v42, 0, sizeof(v42));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v44, (const struct CSrmDebugInfo *)v38, 0);
  if ( a1[3] < 8u )
    v4 = a1;
  else
    v4 = (_WORD *)*a1;
  a1[2] = 0;
  *v4 = 0;
  if ( a2[3] < 8u )
    v5 = a2;
  else
    v5 = (_WORD *)*a2;
  a2[2] = 0;
  *v5 = 0;
  DomainControllerInfo = 0;
  v36 = 0;
  pExceptionObject[1] = &CSrmAuto<_DOMAIN_CONTROLLER_INFOW *,CSrmAutoGenericValue_Storage<_DOMAIN_CONTROLLER_INFOW *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),_DOMAIN_CONTROLLER_INFOW * & (*)(_DOMAIN_CONTROLLER_INFOW * &),&public: static _DOMAIN_CONTROLLER_INFOW * & DTyper<_DOMAIN_CONTROLLER_INFOW *>::Identity(_DOMAIN_CONTROLLER_INFOW * &)>>::`vftable';
  lpszPathName = 0;
  ppObject = 0;
  VariantInit(&pvarg);
  DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x40000010u, &DomainControllerInfo);
  if ( DcNameW > 0 )
    DcNameW = (unsigned __int16)DcNameW | 0x80070000;
  v45 = DcNameW;
  if ( DcNameW < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, Hr);
    v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x155u, v25, 0);
  }
  v45 = DcNameW;
  v7 = DomainControllerInfo;
  v8 = DomainControllerInfo;
  v36 = DomainControllerInfo;
  if ( !DomainControllerInfo || (DomainControllerName = DomainControllerInfo->DomainControllerName) == 0 )
  {
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v44,
      0x8Cu,
      0x15Du,
      L"Could not get fully-qualified domain controller name");
    v45 = -2147467259;
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, v22);
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x15Eu, v23, 0);
  }
  if ( *DomainControllerName == 92 )
  {
    while ( 1 )
    {
      v7->DomainControllerName = ++DomainControllerName;
      if ( *DomainControllerName != 92 )
        break;
      v7 = DomainControllerInfo;
    }
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( DomainControllerName[v11] );
  std::wstring::assign(a2, DomainControllerName);
  v12 = -1;
  do
    ++v12;
  while ( DomainControllerInfo->DomainControllerName[v12] );
  CSrmAutoPWSZ::Allocate((LPVOID *)&lpszPathName, v12 + 17);
  v13 = v12 + 18;
  v14 = (WCHAR *)lpszPathName;
  v15 = StringCchPrintfW(
          (unsigned __int16 *)lpszPathName,
          v13,
          L"LDAP://%s/RootDSE",
          DomainControllerInfo->DomainControllerName);
  v45 = v15;
  if ( v15 < 0 )
  {
    v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, v26);
    v27 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x16Du, v27, 0);
  }
  v45 = v15;
  Object = ADsGetObject(v14, &IID_IADs, &ppObject);
  v45 = Object;
  if ( Object < 0 )
  {
    v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, v28);
    v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x170u, v29, 0);
  }
  v45 = Object;
  v17 = ppObject;
  v18 = *(_QWORD *)ppObject;
  v19 = SysAllocString(L"configurationNamingContext");
  v20 = v19;
  pExceptionObject[0] = v19;
  if ( !v19 )
  {
    LODWORD(pExceptionObject[0]) = -2147024882;
    throw (long *)pExceptionObject;
  }
  v45 = (*(__int64 (__fastcall **)(void *, BSTR, VARIANTARG *))(v18 + 120))(v17, v19, &pvarg);
  SysFreeString(v20);
  if ( v45 < 0 )
  {
    v30 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, v30);
    v31 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x173u, v31, 0);
  }
  do
    ++v10;
  while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
  std::wstring::assign(a1, pvarg.bstrVal);
  v21 = VariantClear(&pvarg);
  if ( v21 < 0 )
    _com_issue_error(v21);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  CoTaskMemFree(v14);
  NetApiBufferFree(v8);
  v44 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v44);
}

```

## disassembly

```asm
0x180014ed4  mov     [rsp-8+arg_10], rbx
0x180014ed9  push    rbp
0x180014eda  push    rsi
0x180014edb  push    rdi
0x180014edc  push    r12
0x180014ede  push    r13
0x180014ee0  push    r14
0x180014ee2  push    r15
0x180014ee4  lea     rbp, [rsp-0D0h]
0x180014eec  sub     rsp, 1D0h
0x180014ef3  mov     rax, cs:__security_cookie
0x180014efa  xor     rax, rsp
0x180014efd  mov     [rbp+100h+var_40], rax
0x180014f04  mov     rbx, rdx
0x180014f07  mov     r15, rcx
0x180014f0a  lea     rax, aBaseFsFsrmServ_14; "base\\fs\\fsrm\\service\\globalstore\\a"...
0x180014f11  mov     [rsp+200h+var_188], rax
0x180014f16  lea     rax, aCadreaderGetco; "CAdReader::GetConfigurationNamingContex"...
0x180014f1d  mov     [rbp+100h+var_180], rax
0x180014f21  lea     rax, aAdreadrc; "ADREADRC"
0x180014f28  mov     [rbp+100h+var_178], rax
0x180014f2c  mov     [rbp+100h+var_170], 13Fh
0x180014f33  mov     [rbp+100h+var_16C], 1Eh
0x180014f3a  mov     [rbp+100h+var_168], 0FFh
0x180014f41  xor     esi, esi
0x180014f43  mov     [rbp+100h+var_100], 1000000h
0x180014f4a  xor     edx, edx; Val
0x180014f4c  lea     r8d, [rsi+60h]; Size
0x180014f50  lea     rcx, [rbp+100h+var_160]; void *
0x180014f54  call    memset_0
0x180014f59  xor     r8d, r8d
0x180014f5c  lea     rdx, [rsp+200h+var_188]
0x180014f61  lea     rcx, [rbp+100h+var_F0]
0x180014f65  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180014f6a  nop
0x180014f6b  cmp     qword ptr [r15+18h], 8
0x180014f70  jb      short loc_180014F77
0x180014f72  mov     rcx, [r15]
0x180014f75  jmp     short loc_180014F7A
0x180014f77  mov     rcx, r15
0x180014f7a  mov     [r15+10h], rsi
0x180014f7e  mov     [rcx], si
0x180014f81  cmp     qword ptr [rbx+18h], 8
0x180014f86  jb      short loc_180014F8D
0x180014f88  mov     rcx, [rbx]
0x180014f8b  jmp     short loc_180014F90
0x180014f8d  mov     rcx, rbx
0x180014f90  mov     [rbx+10h], rsi
0x180014f94  mov     [rcx], si
0x180014f97  mov     [rsp+200h+var_1D0], rsi
0x180014f9c  mov     [rsp+200h+var_1A8], rsi
0x180014fa1  lea     rax, ??_7?$CSrmAuto@PEAU_DOMAIN_CONTROLLER_INFOW@@V?$CSrmAutoGenericValue_Storage@PEAU_DOMAIN_CONTROLLER_INFOW@@$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_DOMAIN_CONTROLLER_INFOW@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<_DOMAIN_CONTROLLER_INFOW *,CSrmAutoGenericValue_Storage<_DOMAIN_CONTROLLER_INFOW *,0,ulong (*)(void *),&NetApiBufferFree(void *),_DOMAIN_CONTROLLER_INFOW * & (*)(_DOMAIN_CONTROLLER_INFOW * &),&DTyper<_DOMAIN_CONTROLLER_INFOW *>::Identity(_DOMAIN_CONTROLLER_INFOW * &)>>::`vftable'
0x180014fa8  mov     [rsp+200h+var_1B0], rax
0x180014fad  mov     [rsp+200h+lpszPathName], rsi
0x180014fb2  mov     [rsp+200h+ppObject], rsi
0x180014fb7  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180014fbc  call    cs:__imp_VariantInit
0x180014fc2  nop
0x180014fc3  lea     rax, [rsp+200h+var_1D0]
0x180014fc8  mov     [rsp+200h+DomainControllerInfo], rax; DomainControllerInfo
0x180014fcd  mov     [rsp+200h+Flags], 40000010h; Flags
0x180014fd5  xor     r9d, r9d; SiteName
0x180014fd8  xor     r8d, r8d; DomainGuid
0x180014fdb  xor     edx, edx; DomainName
0x180014fdd  xor     ecx, ecx; ComputerName
0x180014fdf  call    cs:__imp_DsGetDcNameW
0x180014fe5  test    eax, eax
0x180014fe7  jle     short loc_180014FF1
0x180014fe9  movzx   eax, ax
0x180014fec  or      eax, 80070000h
0x180014ff1  mov     [rbp+100h+var_E8], eax
0x180014ff4  test    eax, eax
0x180014ff6  js      loc_18001520C
0x180014ffc  mov     [rbp+100h+var_E8], eax
0x180014fff  mov     rax, [rsp+200h+var_1D0]
0x180015004  mov     r14, rax
0x180015007  mov     [rsp+200h+var_1A8], rax
0x18001500c  test    rax, rax
0x18001500f  jz      loc_1800151B8
0x180015015  mov     rdx, [rax]; Src
0x180015018  test    rdx, rdx
0x18001501b  jz      loc_1800151B8
0x180015021  cmp     word ptr [rdx], 5Ch ; '\'
0x180015025  jnz     short loc_18001503B
0x180015027  add     rdx, 2
0x18001502b  mov     [rax], rdx
0x18001502e  cmp     word ptr [rdx], 5Ch ; '\'
0x180015032  jnz     short loc_18001503B
0x180015034  mov     rax, [rsp+200h+var_1D0]
0x180015039  jmp     short loc_180015027
0x18001503b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001503f  mov     r8, rdi
0x180015042  inc     r8
0x180015045  cmp     [rdx+r8*2], si
0x18001504a  jnz     short loc_180015042
0x18001504c  mov     rcx, rbx; void *
0x18001504f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015054  mov     rax, [rsp+200h+var_1D0]
0x180015059  mov     rcx, [rax]
0x18001505c  mov     rbx, rdi
0x18001505f  inc     rbx
0x180015062  cmp     [rcx+rbx*2], si
0x180015066  jnz     short loc_18001505F
0x180015068  lea     rdx, [rbx+11h]; unsigned __int64
0x18001506c  lea     rcx, [rsp+200h+lpszPathName]; this
0x180015071  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180015076  lea     rdx, [rbx+12h]; unsigned __int64
0x18001507a  mov     r9, [rsp+200h+var_1D0]
0x18001507f  mov     r9, [r9]
0x180015082  lea     r8, aLdapSRootdse; "LDAP://%s/RootDSE"
0x180015089  mov     rbx, [rsp+200h+lpszPathName]
0x18001508e  mov     rcx, rbx; unsigned __int16 *
0x180015091  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015096  mov     [rbp+100h+var_E8], eax
0x180015099  test    eax, eax
0x18001509b  js      loc_18001523E
0x1800150a1  mov     [rbp+100h+var_E8], eax
0x1800150a4  lea     r8, [rsp+200h+ppObject]; ppObject
0x1800150a9  lea     rdx, IID_IADs; riid
0x1800150b0  mov     rcx, rbx; lpszPathName
0x1800150b3  call    cs:__imp_ADsGetObject
0x1800150b9  mov     [rbp+100h+var_E8], eax
0x1800150bc  test    eax, eax
0x1800150be  js      loc_180015270
0x1800150c4  mov     [rbp+100h+var_E8], eax
0x1800150c7  mov     r12, [rsp+200h+ppObject]
0x1800150cc  mov     r13, [r12]
0x1800150d0  lea     rcx, aConfigurationn; "configurationNamingContext"
0x1800150d7  call    cs:__imp_SysAllocString
0x1800150dd  mov     rsi, rax
0x1800150e0  mov     [rsp+200h+pExceptionObject], rax
0x1800150e5  test    rax, rax
0x1800150e8  jz      loc_1800152A2
0x1800150ee  lea     r8, [rsp+200h+pvarg]
0x1800150f3  mov     rdx, rax
0x1800150f6  mov     rcx, r12
0x1800150f9  mov     rax, [r13+78h]
0x1800150fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015102  mov     [rbp+100h+var_E8], eax
0x180015105  mov     rcx, rsi; bstrString
0x180015108  call    cs:__imp_SysFreeString
0x18001510e  mov     eax, [rbp+100h+var_E8]
0x180015111  xor     esi, esi
0x180015113  test    eax, eax
0x180015115  js      loc_1800152BC
0x18001511b  mov     [rbp+100h+var_E8], eax
0x18001511e  mov     rdx, qword ptr [rsp+200h+pvarg+8]; Src
0x180015123  inc     rdi
0x180015126  cmp     [rdx+rdi*2], si
0x18001512a  jnz     short loc_180015123
0x18001512c  mov     r8, rdi
0x18001512f  mov     rcx, r15; void *
0x180015132  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015137  nop
0x180015138  lea     rcx, [rsp+200h+pvarg]; pvarg
0x18001513d  call    cs:__imp_VariantClear
0x180015143  test    eax, eax
0x180015145  js      short loc_1800151B0
0x180015147  mov     rcx, [rsp+200h+ppObject]
0x18001514c  test    rcx, rcx
0x18001514f  jz      short loc_18001515E
0x180015151  mov     rax, [rcx]
0x180015154  mov     rax, [rax+10h]
0x180015158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001515d  nop
0x18001515e  mov     rcx, rbx; pv
0x180015161  call    cs:__imp_CoTaskMemFree
0x180015167  nop
0x180015168  mov     rcx, r14; Buffer
0x18001516b  call    cs:__imp_NetApiBufferFree
0x180015171  nop
0x180015172  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180015179  mov     [rbp+100h+var_F0], rax
0x18001517d  lea     rcx, [rbp+100h+var_F0]; this
0x180015181  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180015186  mov     rcx, [rbp+100h+var_40]
0x18001518d  xor     rcx, rsp; StackCookie
0x180015190  call    __security_check_cookie
0x180015195  mov     rbx, [rsp+200h+arg_10]
0x18001519d  add     rsp, 1D0h
0x1800151a4  pop     r15
0x1800151a6  pop     r14
0x1800151a8  pop     r13
0x1800151aa  pop     r12
0x1800151ac  pop     rdi
0x1800151ad  pop     rsi
0x1800151ae  pop     rbp
0x1800151af  retn
0x1800151b0  mov     ecx, eax; int
0x1800151b2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800151b8  lea     r9, aCouldNotGetFul; "Could not get fully-qualified domain co"...
0x1800151bf  mov     edx, 8Ch; unsigned int
0x1800151c4  mov     r8d, 15Dh; unsigned int
0x1800151ca  lea     rcx, [rbp+100h+var_F0]; this
0x1800151ce  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800151d3  mov     [rbp+100h+var_E8], 80004005h
0x1800151da  lea     rcx, [rbp+100h+var_F0]; this
0x1800151de  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800151e3  mov     edx, eax; int
0x1800151e5  lea     rcx, [rbp+100h+var_F0]; this
0x1800151e9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800151ee  lea     rcx, [rbp+100h+var_F0]; this
0x1800151f2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800151f7  mov     r8d, eax; char
0x1800151fa  xor     r9d, r9d; unsigned __int16 *
0x1800151fd  mov     edx, 15Eh; unsigned int
0x180015202  lea     rcx, [rbp+100h+var_F0]; this
0x180015206  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001520c  lea     rcx, [rbp+100h+var_F0]; this
0x180015210  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180015215  mov     edx, eax; int
0x180015217  lea     rcx, [rbp+100h+var_F0]; this
0x18001521b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180015220  lea     rcx, [rbp+100h+var_F0]; this
0x180015224  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180015229  mov     r8d, eax; char
0x18001522c  xor     r9d, r9d; unsigned __int16 *
0x18001522f  mov     edx, 155h; unsigned int
0x180015234  lea     rcx, [rbp+100h+var_F0]; this
0x180015238  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001523e  lea     rcx, [rbp+100h+var_F0]; this
0x180015242  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180015247  mov     edx, eax; int
0x180015249  lea     rcx, [rbp+100h+var_F0]; this
0x18001524d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180015252  lea     rcx, [rbp+100h+var_F0]; this
0x180015256  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001525b  mov     r8d, eax; char
0x18001525e  xor     r9d, r9d; unsigned __int16 *
0x180015261  mov     edx, 16Dh; unsigned int
0x180015266  lea     rcx, [rbp+100h+var_F0]; this
0x18001526a  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180015270  lea     rcx, [rbp+100h+var_F0]; this
0x180015274  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180015279  mov     edx, eax; int
0x18001527b  lea     rcx, [rbp+100h+var_F0]; this
0x18001527f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180015284  lea     rcx, [rbp+100h+var_F0]; this
0x180015288  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001528d  mov     r8d, eax; char
0x180015290  xor     r9d, r9d; unsigned __int16 *
0x180015293  mov     edx, 170h; unsigned int
0x180015298  lea     rcx, [rbp+100h+var_F0]; this
0x18001529c  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800152a2  mov     dword ptr [rsp+200h+pExceptionObject], 8007000Eh
0x1800152aa  lea     rdx, _TI1J; pThrowInfo
0x1800152b1  lea     rcx, [rsp+200h+pExceptionObject]; pExceptionObject
0x1800152b6  call    _CxxThrowException_0
0x1800152bc  lea     rcx, [rbp+100h+var_F0]; this
0x1800152c0  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800152c5  mov     edx, eax; int
0x1800152c7  lea     rcx, [rbp+100h+var_F0]; this
0x1800152cb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800152d0  lea     rcx, [rbp+100h+var_F0]; this
0x1800152d4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800152d9  mov     r8d, eax; char
0x1800152dc  xor     r9d, r9d; unsigned __int16 *
0x1800152df  mov     edx, 173h; unsigned int
0x1800152e4  lea     rcx, [rbp+100h+var_F0]; this
0x1800152e8  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
