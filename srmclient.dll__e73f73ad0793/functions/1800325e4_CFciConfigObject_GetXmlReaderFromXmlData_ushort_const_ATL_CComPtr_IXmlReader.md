# CFciConfigObject::GetXmlReaderFromXmlData(ushort const *,ATL::CComPtr<IXmlReader> &)

- ea: `0x1800325e4`
- end: `0x180032988`
- name: `?GetXmlReaderFromXmlData@CFciConfigObject@@SAXPEBGAEAV?$CComPtr@UIXmlReader@@@ATL@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031c74`
- `0x180032eb8`
- `0x18003354c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x1800325e4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x1800326a2`
- `ole32!CreateStreamOnHGlobal` at `0x1800326a2`
- `XmlLite!CreateXmlReader` at `0x180032728`
- `XmlLite!CreateXmlReader` at `0x180032728`

## string_xrefs

- `0x180032612`: `base\fs\fsrm\service\globalstore\fciconfigobject.cpp`
- `0x18003261e`: `CFciConfigObject::GetXmlReaderFromXmlData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CFciConfigObject::GetXmlReaderFromXmlData(__int64 a1, _QWORD *a2)
{
  HRESULT StreamOnHGlobal; // eax
  __int64 v5; // r8
  int v6; // eax
  int v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  void *v11; // rcx
  void *v12; // rbx
  int v13; // eax
  char v14; // al
  char Hr; // al
  int v16; // eax
  char v17; // al
  int v18; // eax
  char v19; // al
  int v20; // eax
  char v21; // al
  int v22; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  void *ppvObject; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+38h] [rbp-C8h] BYREF
  LPSTREAM ppstm[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v29[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+70h] [rbp-90h]
  _BYTE v31[96]; // [rsp+78h] [rbp-88h] BYREF
  int v32; // [rsp+D8h] [rbp-28h]
  __int16 v33; // [rsp+E0h] [rbp-20h]
  __int64 v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  void **v36; // [rsp+110h] [rbp+10h] BYREF
  HRESULT v37; // [rsp+118h] [rbp+18h]

  v29[0] = L"base\\fs\\fsrm\\service\\globalstore\\fciconfigobject.cpp";
  v29[1] = L"CFciConfigObject::GetXmlReaderFromXmlData";
  v29[2] = L"CFCICFGO";
  v29[3] = 950;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v36, (const struct CSrmDebugInfo *)v29, 0);
  ppstm[0] = 0;
  ppvObject = 0;
  v35 = 7;
  v34 = 0;
  v33 = 0;
  if ( !a1 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3BDu, Hr, 0);
  }
  v37 = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
  v37 = StreamOnHGlobal;
  if ( StreamOnHGlobal < 0 )
  {
    v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v16);
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3C2u, v17, 0);
  }
  v37 = StreamOnHGlobal;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  v6 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm[0] + 32LL))(
         ppstm[0],
         a1,
         (unsigned int)(2 * v5),
         0);
  v37 = v6;
  if ( v6 < 0 )
  {
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v18);
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3C4u, v19, 0);
  }
  v37 = v6;
  ppstm[1] = 0;
  v7 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm[0] + 40LL))(ppstm[0], 0, 0, 0);
  v37 = v7;
  if ( v7 < 0 )
  {
    v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v20);
    v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3C7u, v21, 0);
  }
  v37 = v7;
  v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v37 = v8;
  if ( v8 < 0 )
  {
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v22);
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3C9u, v23, 0);
  }
  v37 = v8;
  v9 = (*(__int64 (__fastcall **)(void *, LPSTREAM))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm[0]);
  v37 = v9;
  if ( v9 < 0 )
  {
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v24);
    v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3CBu, v25, 0);
  }
  v37 = v9;
  v27 = 0;
  do
  {
    v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v27);
    v37 = v10;
    if ( v10 < 0 )
    {
      v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v13);
      v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x3D2u, v14, 0);
    }
    v37 = v10;
  }
  while ( v27 != 1 );
  v11 = ppvObject;
  if ( (void *)*a2 != ppvObject )
  {
    v12 = ppvObject;
    if ( ppvObject )
    {
      (*(void (**)(void))(*(_QWORD *)ppvObject + 8LL))();
      v11 = ppvObject;
    }
    if ( *a2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
      v11 = ppvObject;
    }
    *a2 = v12;
  }
  if ( v11 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( ppstm[0] )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm[0] + 16LL))(ppstm[0]);
  v36 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v36);
}

```

## disassembly

```asm
0x1800325e4  mov     [rsp-8+arg_10], rbx
0x1800325e9  push    rbp
0x1800325ea  push    rsi
0x1800325eb  push    rdi
0x1800325ec  lea     rbp, [rsp-0D0h]
0x1800325f4  sub     rsp, 1D0h
0x1800325fb  mov     rax, cs:__security_cookie
0x180032602  xor     rax, rsp
0x180032605  mov     [rbp+0E0h+var_20], rax
0x18003260c  mov     rdi, rdx
0x18003260f  mov     rbx, rcx
0x180032612  lea     rax, aBaseFsFsrmServ_19; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x180032619  mov     [rsp+1E0h+var_190], rax
0x18003261e  lea     rax, aCfciconfigobje_15; "CFciConfigObject::GetXmlReaderFromXmlDa"...
0x180032625  mov     [rsp+1E0h+var_188], rax
0x18003262a  lea     rax, aCfcicfgo; "CFCICFGO"
0x180032631  mov     [rsp+1E0h+var_180], rax
0x180032636  mov     [rsp+1E0h+var_178], 3B6h
0x18003263f  xor     esi, esi
0x180032641  mov     [rsp+1E0h+var_170], 0FFh
0x180032649  mov     [rbp+0E0h+var_108], 1000000h
0x180032650  xor     edx, edx; Val
0x180032652  lea     r8d, [rsi+60h]; Size
0x180032656  lea     rcx, [rsp+1E0h+var_168]; void *
0x18003265b  call    memset_0
0x180032660  xor     r8d, r8d
0x180032663  lea     rdx, [rsp+1E0h+var_190]
0x180032668  lea     rcx, [rbp+0E0h+var_D0]
0x18003266c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180032671  nop
0x180032672  mov     [rsp+1E0h+ppstm], rsi
0x180032677  mov     [rsp+1E0h+ppvObject], rsi
0x18003267c  mov     [rbp+0E0h+var_E8], 7
0x180032684  mov     [rbp+0E0h+var_F0], rsi
0x180032688  mov     [rbp+0E0h+var_100], si
0x18003268c  test    rbx, rbx
0x18003268f  jz      loc_180032862
0x180032695  mov     [rbp+0E0h+var_C8], esi
0x180032698  lea     r8, [rsp+1E0h+ppstm]; ppstm
0x18003269d  lea     edx, [rsi+1]; fDeleteOnRelease
0x1800326a0  xor     ecx, ecx; hGlobal
0x1800326a2  call    cs:__imp_CreateStreamOnHGlobal
0x1800326a8  mov     [rbp+0E0h+var_C8], eax
0x1800326ab  test    eax, eax
0x1800326ad  js      loc_18003288E
0x1800326b3  mov     [rbp+0E0h+var_C8], eax
0x1800326b6  mov     rcx, [rsp+1E0h+ppstm]
0x1800326bb  mov     rax, [rcx]
0x1800326be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800326c2  inc     r8
0x1800326c5  cmp     [rbx+r8*2], si
0x1800326ca  jnz     short loc_1800326C2
0x1800326cc  add     r8d, r8d
0x1800326cf  xor     r9d, r9d
0x1800326d2  mov     rdx, rbx
0x1800326d5  mov     rax, [rax+20h]
0x1800326d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326de  mov     [rbp+0E0h+var_C8], eax
0x1800326e1  test    eax, eax
0x1800326e3  js      loc_1800328C0
0x1800326e9  mov     [rbp+0E0h+var_C8], eax
0x1800326ec  mov     [rsp+1E0h+var_198], rsi
0x1800326f1  mov     rcx, [rsp+1E0h+ppstm]
0x1800326f6  mov     rax, [rcx]
0x1800326f9  xor     r9d, r9d
0x1800326fc  xor     r8d, r8d
0x1800326ff  mov     rdx, rsi
0x180032702  mov     rax, [rax+28h]
0x180032706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003270b  mov     [rbp+0E0h+var_C8], eax
0x18003270e  test    eax, eax
0x180032710  js      loc_1800328F2
0x180032716  mov     [rbp+0E0h+var_C8], eax
0x180032719  xor     r8d, r8d; pMalloc
0x18003271c  lea     rdx, [rsp+1E0h+ppvObject]; ppvObject
0x180032721  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180032728  call    cs:__imp_CreateXmlReader
0x18003272e  mov     [rbp+0E0h+var_C8], eax
0x180032731  test    eax, eax
0x180032733  js      loc_180032924
0x180032739  mov     [rbp+0E0h+var_C8], eax
0x18003273c  mov     rcx, [rsp+1E0h+ppvObject]
0x180032741  mov     rax, [rcx]
0x180032744  mov     rdx, [rsp+1E0h+ppstm]
0x180032749  mov     rax, [rax+18h]
0x18003274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032752  mov     [rbp+0E0h+var_C8], eax
0x180032755  test    eax, eax
0x180032757  js      loc_180032956
0x18003275d  mov     [rbp+0E0h+var_C8], eax
0x180032760  mov     [rsp+1E0h+var_1A8], esi
0x180032764  mov     rcx, [rsp+1E0h+ppvObject]
0x180032769  mov     rax, [rcx]
0x18003276c  lea     rdx, [rsp+1E0h+var_1A8]
0x180032771  mov     rax, [rax+30h]
0x180032775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003277a  mov     [rbp+0E0h+var_C8], eax
0x18003277d  test    eax, eax
0x18003277f  js      loc_180032830
0x180032785  mov     [rbp+0E0h+var_C8], eax
0x180032788  cmp     [rsp+1E0h+var_1A8], 1
0x18003278d  jnz     short loc_180032764
0x18003278f  mov     rcx, [rsp+1E0h+ppvObject]
0x180032794  cmp     [rdi], rcx
0x180032797  jz      short loc_1800327D1
0x180032799  mov     rbx, rcx
0x18003279c  test    rcx, rcx
0x18003279f  jz      short loc_1800327B2
0x1800327a1  mov     rax, [rcx]
0x1800327a4  mov     rax, [rax+8]
0x1800327a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327ad  mov     rcx, [rsp+1E0h+ppvObject]
0x1800327b2  mov     rdx, [rdi]
0x1800327b5  test    rdx, rdx
0x1800327b8  jz      short loc_1800327CE
0x1800327ba  mov     rax, [rdx]
0x1800327bd  mov     rcx, rdx
0x1800327c0  mov     rax, [rax+10h]
0x1800327c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327c9  mov     rcx, [rsp+1E0h+ppvObject]
0x1800327ce  mov     [rdi], rbx
0x1800327d1  test    rcx, rcx
0x1800327d4  jz      short loc_1800327E3
0x1800327d6  mov     rax, [rcx]
0x1800327d9  mov     rax, [rax+10h]
0x1800327dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327e2  nop
0x1800327e3  mov     rcx, [rsp+1E0h+ppstm]
0x1800327e8  test    rcx, rcx
0x1800327eb  jz      short loc_1800327FA
0x1800327ed  mov     rax, [rcx]
0x1800327f0  mov     rax, [rax+10h]
0x1800327f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327f9  nop
0x1800327fa  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180032801  mov     [rbp+0E0h+var_D0], rax
0x180032805  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032809  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18003280e  mov     rcx, [rbp+0E0h+var_20]
0x180032815  xor     rcx, rsp; StackCookie
0x180032818  call    __security_check_cookie
0x18003281d  mov     rbx, [rsp+1E0h+arg_10]
0x180032825  add     rsp, 1D0h
0x18003282c  pop     rdi
0x18003282d  pop     rsi
0x18003282e  pop     rbp
0x18003282f  retn
0x180032830  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032834  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032839  mov     edx, eax; int
0x18003283b  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003283f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032844  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032848  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18003284d  mov     r8d, eax; char
0x180032850  xor     r9d, r9d; unsigned __int16 *
0x180032853  mov     edx, 3D2h; unsigned int
0x180032858  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003285c  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032862  mov     edx, 80070057h; int
0x180032867  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003286b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032870  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032874  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032879  mov     r8d, eax; char
0x18003287c  xor     r9d, r9d; unsigned __int16 *
0x18003287f  mov     edx, 3BDh; unsigned int
0x180032884  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032888  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18003288e  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032892  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032897  mov     edx, eax; int
0x180032899  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003289d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800328a2  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328a6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800328ab  mov     r8d, eax; char
0x1800328ae  xor     r9d, r9d; unsigned __int16 *
0x1800328b1  mov     edx, 3C2h; unsigned int
0x1800328b6  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328ba  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800328c0  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328c4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800328c9  mov     edx, eax; int
0x1800328cb  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328cf  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800328d4  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328d8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800328dd  mov     r8d, eax; char
0x1800328e0  xor     r9d, r9d; unsigned __int16 *
0x1800328e3  mov     edx, 3C4h; unsigned int
0x1800328e8  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328ec  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800328f2  lea     rcx, [rbp+0E0h+var_D0]; this
0x1800328f6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800328fb  mov     edx, eax; int
0x1800328fd  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032901  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032906  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003290a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18003290f  mov     r8d, eax; char
0x180032912  xor     r9d, r9d; unsigned __int16 *
0x180032915  mov     edx, 3C7h; unsigned int
0x18003291a  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003291e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032924  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032928  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18003292d  mov     edx, eax; int
0x18003292f  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032933  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032938  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003293c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032941  mov     r8d, eax; char
0x180032944  xor     r9d, r9d; unsigned __int16 *
0x180032947  mov     edx, 3C9h; unsigned int
0x18003294c  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032950  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032956  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003295a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18003295f  mov     edx, eax; int
0x180032961  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032965  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18003296a  lea     rcx, [rbp+0E0h+var_D0]; this
0x18003296e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032973  mov     r8d, eax; char
0x180032976  xor     r9d, r9d; unsigned __int16 *
0x180032979  mov     edx, 3CBh; unsigned int
0x18003297e  lea     rcx, [rbp+0E0h+var_D0]; this
0x180032982  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
