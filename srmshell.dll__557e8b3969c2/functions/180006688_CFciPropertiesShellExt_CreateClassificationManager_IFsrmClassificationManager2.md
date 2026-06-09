# CFciPropertiesShellExt::CreateClassificationManager(IFsrmClassificationManager2 * *)

- ea: `0x180006688`
- end: `0x180006885`
- name: `?CreateClassificationManager@CFciPropertiesShellExt@@AEAAXPEAPEAUIFsrmClassificationManager2@@@Z`
- size: `509`
- prototype: `void __fastcall(CFciPropertiesShellExt *__hidden this, struct IFsrmClassificationManager2 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009d18`

## callees

- `0x180006688`
- `0x18000688c`
- `0x1800083e0`
- `0x18000d368`
- `0x18000f4b0`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006751`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006751`

## string_xrefs

- `0x1800066c9`: `CFciPropertiesShellExt::CreateClassificationManager`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::CreateClassificationManager(
        CFciPropertiesShellExt *this,
        struct IFsrmClassificationManager2 **a2)
{
  HRESULT v4; // eax
  int v5; // eax
  _QWORD *v6; // rbx
  struct IFsrmClassificationManager2 *v7; // rax
  int v8; // eax
  char v9; // al
  int Hr; // eax
  char v11; // al
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  int v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[96]; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+C8h] [rbp-38h]
  void **v20; // [rsp+D0h] [rbp-30h] BYREF
  HRESULT v21; // [rsp+D8h] [rbp-28h]

  v13 = v14;
  v14[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  v14[1] = L"CFciPropertiesShellExt::CreateClassificationManager";
  v14[2] = L"FCIPROPC";
  v15 = 1649;
  v16 = 17;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer(&v20, v14, 0);
  *a2 = 0;
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_b15c0e47_c391_45b9_95c8_eb596c853f3a,
         0,
         0x17u,
         &GUID_0004c1c9_127e_4765_ba07_6a3147bca112,
         &ppv);
  v21 = v4;
  if ( v4 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, Hr);
    v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x67Du, v11, 0);
  }
  v21 = v4;
  v13 = 0;
  v5 = ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(&v13);
  v21 = v5;
  if ( v5 < 0 )
  {
    v8 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v20, v8);
    v9 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v20);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v20, 0x681u, v9, 0);
  }
  v21 = v5;
  v6 = v13;
  if ( v13 )
    (*(void (__fastcall **)(_QWORD *))(*v13 + 8LL))(v13);
  CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(v6, ppv, this);
  v7 = (struct IFsrmClassificationManager2 *)ppv;
  ppv = 0;
  *a2 = v7;
  if ( v6 )
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v20 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v20);
}

```

## disassembly

```asm
0x180006688  push    rbp
0x18000668a  push    rbx
0x18000668b  push    rsi
0x18000668c  push    rdi
0x18000668d  lea     rbp, [rsp-98h]
0x180006695  sub     rsp, 198h
0x18000669c  mov     rax, cs:__security_cookie
0x1800066a3  xor     rax, rsp
0x1800066a6  mov     [rbp+0B0h+var_30], rax
0x1800066ad  mov     rdi, rdx
0x1800066b0  mov     rsi, rcx
0x1800066b3  lea     rax, [rsp+1B0h+var_170]
0x1800066b8  mov     [rsp+1B0h+var_178], rax
0x1800066bd  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x1800066c4  mov     [rsp+1B0h+var_170], rax
0x1800066c9  lea     rax, aCfciproperties_10; "CFciPropertiesShellExt::CreateClassific"...
0x1800066d0  mov     [rsp+1B0h+var_168], rax
0x1800066d5  lea     rax, aFcipropc; "FCIPROPC"
0x1800066dc  mov     [rsp+1B0h+var_160], rax
0x1800066e1  mov     [rsp+1B0h+var_158], 671h
0x1800066e9  mov     [rsp+1B0h+var_154], 11h
0x1800066f1  mov     [rsp+1B0h+var_150], 0FFh
0x1800066f9  mov     [rbp+0B0h+var_E8], 1000000h
0x180006700  xor     edx, edx; Val
0x180006702  lea     r8d, [rdx+60h]; Size
0x180006706  lea     rcx, [rsp+1B0h+var_148]; void *
0x18000670b  call    memset_0
0x180006710  nop
0x180006711  xor     r8d, r8d
0x180006714  lea     rdx, [rsp+1B0h+var_170]
0x180006719  lea     rcx, [rbp+0B0h+var_E0]
0x18000671d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180006722  nop
0x180006723  mov     qword ptr [rdi], 0
0x18000672a  mov     [rsp+1B0h+var_180], 0
0x180006733  lea     rax, [rsp+1B0h+var_180]
0x180006738  mov     [rsp+1B0h+ppv], rax; ppv
0x18000673d  lea     r9, _GUID_0004c1c9_127e_4765_ba07_6a3147bca112; riid
0x180006744  xor     edx, edx; pUnkOuter
0x180006746  lea     r8d, [rdx+17h]; dwClsContext
0x18000674a  lea     rcx, _GUID_b15c0e47_c391_45b9_95c8_eb596c853f3a; rclsid
0x180006751  call    cs:__imp_CoCreateInstance
0x180006757  mov     [rbp+0B0h+var_D8], eax
0x18000675a  test    eax, eax
0x18000675c  js      loc_180006853
0x180006762  mov     [rbp+0B0h+var_D8], eax
0x180006765  mov     [rsp+1B0h+var_178], 0
0x18000676e  lea     rcx, [rsp+1B0h+var_178]
0x180006773  call    ?CreateInstance@?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>> * *)
0x180006778  mov     [rbp+0B0h+var_D8], eax
0x18000677b  test    eax, eax
0x18000677d  js      loc_180006821
0x180006783  mov     [rbp+0B0h+var_D8], eax
0x180006786  mov     rbx, [rsp+1B0h+var_178]
0x18000678b  mov     [rsp+1B0h+var_178], rbx
0x180006790  test    rbx, rbx
0x180006793  jz      short loc_1800067A5
0x180006795  mov     rax, [rbx]
0x180006798  mov     rcx, rbx
0x18000679b  mov     rax, [rax+8]
0x18000679f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a4  nop
0x1800067a5  mov     r8, rsi
0x1800067a8  mov     rdx, [rsp+1B0h+var_180]
0x1800067ad  mov     rcx, rbx
0x1800067b0  call    ?Subscribe@?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAAXPEAUIUnknown@@PEAVCFciPropertiesShellExt@@@Z; CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(IUnknown *,CFciPropertiesShellExt *)
0x1800067b5  mov     rax, [rsp+1B0h+var_180]
0x1800067ba  mov     [rsp+1B0h+var_180], 0
0x1800067c3  mov     [rdi], rax
0x1800067c6  test    rbx, rbx
0x1800067c9  jz      short loc_1800067DB
0x1800067cb  mov     rax, [rbx]
0x1800067ce  mov     rcx, rbx
0x1800067d1  mov     rax, [rax+10h]
0x1800067d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067da  nop
0x1800067db  mov     rcx, [rsp+1B0h+var_180]
0x1800067e0  test    rcx, rcx
0x1800067e3  jz      short loc_1800067F2
0x1800067e5  mov     rax, [rcx]
0x1800067e8  mov     rax, [rax+10h]
0x1800067ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f1  nop
0x1800067f2  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800067f9  mov     [rbp+0B0h+var_E0], rax
0x1800067fd  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006801  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180006806  mov     rcx, [rbp+0B0h+var_30]
0x18000680d  xor     rcx, rsp; StackCookie
0x180006810  call    __security_check_cookie
0x180006815  add     rsp, 198h
0x18000681c  pop     rdi
0x18000681d  pop     rsi
0x18000681e  pop     rbx
0x18000681f  pop     rbp
0x180006820  retn
0x180006821  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006825  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000682a  mov     edx, eax; int
0x18000682c  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006830  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180006835  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006839  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000683e  mov     r8d, eax; char
0x180006841  xor     r9d, r9d; unsigned __int16 *
0x180006844  mov     edx, 681h; unsigned int
0x180006849  lea     rcx, [rbp+0B0h+var_E0]; this
0x18000684d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180006853  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006857  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000685c  mov     edx, eax; int
0x18000685e  lea     rcx, [rbp+0B0h+var_E0]; this
0x180006862  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180006867  lea     rcx, [rbp+0B0h+var_E0]; this
0x18000686b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180006870  mov     r8d, eax; char
0x180006873  xor     r9d, r9d; unsigned __int16 *
0x180006876  mov     edx, 67Dh; unsigned int
0x18000687b  lea     rcx, [rbp+0B0h+var_E0]; this
0x18000687f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
