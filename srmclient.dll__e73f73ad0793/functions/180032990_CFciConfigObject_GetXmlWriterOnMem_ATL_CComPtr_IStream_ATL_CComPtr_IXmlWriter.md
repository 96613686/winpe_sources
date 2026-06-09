# CFciConfigObject::GetXmlWriterOnMem(ATL::CComPtr<IStream> &,ATL::CComPtr<IXmlWriter> &)

- ea: `0x180032990`
- end: `0x180032d34`
- name: `?GetXmlWriterOnMem@CFciConfigObject@@SAXAEAV?$CComPtr@UIStream@@@ATL@@AEAV?$CComPtr@UIXmlWriter@@@3@@Z`
- size: `932`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003354c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180032990`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180032a43`
- `ole32!CreateStreamOnHGlobal` at `0x180032a43`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180032a6a`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180032a6a`
- `XmlLite!CreateXmlWriter` at `0x180032a8d`
- `XmlLite!CreateXmlWriter` at `0x180032a8d`

## string_xrefs

- `0x1800329be`: `base\fs\fsrm\service\globalstore\fciconfigobject.cpp`
- `0x1800329ca`: `CFciConfigObject::GetXmlWriterOnMem`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CFciConfigObject::GetXmlWriterOnMem(LPSTREAM *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *v10; // rbx
  void *v11; // rax
  LPSTREAM v12; // rbx
  LPSTREAM v13; // rcx
  int v14; // eax
  char v15; // al
  int Hr; // eax
  char v17; // al
  int v18; // eax
  char v19; // al
  int v20; // eax
  char v21; // al
  int v22; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  void *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  LPSTREAM ppstm; // [rsp+28h] [rbp-D8h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v29[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  char v31[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+C0h] [rbp-40h]
  void **v33; // [rsp+D0h] [rbp-30h] BYREF
  HRESULT v34; // [rsp+D8h] [rbp-28h]

  v29[0] = L"base\\fs\\fsrm\\service\\globalstore\\fciconfigobject.cpp";
  v29[1] = L"CFciConfigObject::GetXmlWriterOnMem";
  v29[2] = L"CFCICFGO";
  v29[3] = 873;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v33, (const struct CSrmDebugInfo *)v29, 0);
  ppstm = 0;
  ppOutput = 0;
  ppvObject = 0;
  v4 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v34 = v4;
  if ( v4 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, Hr);
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x374u, v17, 0);
  }
  v34 = v4;
  v5 = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-16", &ppOutput);
  v34 = v5;
  if ( v5 < 0 )
  {
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v18);
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x377u, v19, 0);
  }
  v34 = v5;
  v6 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v34 = v6;
  if ( v6 < 0 )
  {
    v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v20);
    v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x379u, v21, 0);
  }
  v34 = v6;
  v7 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  v34 = v7;
  if ( v7 < 0 )
  {
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v22);
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x37Bu, v23, 0);
  }
  v34 = v7;
  if ( ppOutput )
  {
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
  }
  v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
  v34 = v8;
  if ( v8 < 0 )
  {
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v24);
    v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x37Fu, v25, 0);
  }
  v34 = v8;
  v9 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 0);
  v34 = v9;
  if ( v9 < 0 )
  {
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v14);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x381u, v15, 0);
  }
  v34 = v9;
  v10 = ppvObject;
  v11 = 0;
  ppvObject = 0;
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    v11 = ppvObject;
  }
  *a2 = v10;
  v12 = ppstm;
  v13 = 0;
  ppstm = 0;
  if ( *a1 )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)*a1 + 16LL))(*a1);
    v13 = ppstm;
    v11 = ppvObject;
  }
  *a1 = v12;
  if ( v11 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    v13 = ppstm;
  }
  if ( ppOutput )
  {
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    v13 = ppstm;
  }
  if ( v13 )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v13 + 16LL))(v13);
  v33 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v33);
}

```

## disassembly

```asm
0x180032990  mov     [rsp-8+arg_10], rbx
0x180032995  push    rbp
0x180032996  push    rsi
0x180032997  push    rdi
0x180032998  lea     rbp, [rsp-90h]
0x1800329a0  sub     rsp, 190h
0x1800329a7  mov     rax, cs:__security_cookie
0x1800329ae  xor     rax, rsp
0x1800329b1  mov     [rbp+0A0h+var_20], rax
0x1800329b8  mov     rdi, rdx
0x1800329bb  mov     rsi, rcx
0x1800329be  lea     rax, aBaseFsFsrmServ_19; "base\\fs\\fsrm\\service\\globalstore\\f"...
0x1800329c5  mov     [rsp+1A0h+var_168], rax
0x1800329ca  lea     rax, aCfciconfigobje_10; "CFciConfigObject::GetXmlWriterOnMem"
0x1800329d1  mov     [rsp+1A0h+var_160], rax
0x1800329d6  lea     rax, aCfcicfgo; "CFCICFGO"
0x1800329dd  mov     [rsp+1A0h+var_158], rax
0x1800329e2  mov     [rsp+1A0h+var_150], 369h
0x1800329eb  mov     [rsp+1A0h+var_148], 0FFh
0x1800329f3  mov     [rbp+0A0h+var_E0], 1000000h
0x1800329fa  xor     edx, edx; Val
0x1800329fc  lea     r8d, [rdx+60h]; Size
0x180032a00  lea     rcx, [rsp+1A0h+var_140]; void *
0x180032a05  call    memset_0
0x180032a0a  xor     r8d, r8d
0x180032a0d  lea     rdx, [rsp+1A0h+var_168]
0x180032a12  lea     rcx, [rbp+0A0h+var_D0]
0x180032a16  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180032a1b  nop
0x180032a1c  mov     [rsp+1A0h+ppstm], 0
0x180032a25  mov     [rsp+1A0h+ppOutput], 0
0x180032a2e  mov     [rsp+1A0h+ppvObject], 0
0x180032a37  lea     r8, [rsp+1A0h+ppstm]; ppstm
0x180032a3c  mov     edx, 1; fDeleteOnRelease
0x180032a41  xor     ecx, ecx; hGlobal
0x180032a43  call    cs:__imp_CreateStreamOnHGlobal
0x180032a49  mov     [rbp+0A0h+var_C8], eax
0x180032a4c  test    eax, eax
0x180032a4e  js      loc_180032C3A
0x180032a54  mov     [rbp+0A0h+var_C8], eax
0x180032a57  lea     r9, [rsp+1A0h+ppOutput]; ppOutput
0x180032a5c  lea     r8, pwszEncodingName; "UTF-16"
0x180032a63  xor     edx, edx; pMalloc
0x180032a65  mov     rcx, [rsp+1A0h+ppstm]; pOutputStream
0x180032a6a  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180032a70  mov     [rbp+0A0h+var_C8], eax
0x180032a73  test    eax, eax
0x180032a75  js      loc_180032C6C
0x180032a7b  mov     [rbp+0A0h+var_C8], eax
0x180032a7e  xor     r8d, r8d; pMalloc
0x180032a81  lea     rdx, [rsp+1A0h+ppvObject]; ppvObject
0x180032a86  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180032a8d  call    cs:__imp_CreateXmlWriter
0x180032a93  mov     [rbp+0A0h+var_C8], eax
0x180032a96  test    eax, eax
0x180032a98  js      loc_180032C9E
0x180032a9e  mov     [rbp+0A0h+var_C8], eax
0x180032aa1  mov     rcx, [rsp+1A0h+ppvObject]
0x180032aa6  mov     rax, [rcx]
0x180032aa9  mov     rdx, [rsp+1A0h+ppOutput]
0x180032aae  mov     rax, [rax+18h]
0x180032ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ab7  mov     [rbp+0A0h+var_C8], eax
0x180032aba  test    eax, eax
0x180032abc  js      loc_180032CD0
0x180032ac2  mov     [rbp+0A0h+var_C8], eax
0x180032ac5  mov     rcx, [rsp+1A0h+ppOutput]
0x180032aca  test    rcx, rcx
0x180032acd  jz      short loc_180032AE4
0x180032acf  mov     rax, [rcx]
0x180032ad2  mov     rax, [rax+10h]
0x180032ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032adb  mov     [rsp+1A0h+ppOutput], 0
0x180032ae4  mov     rcx, [rsp+1A0h+ppvObject]
0x180032ae9  mov     rax, [rcx]
0x180032aec  xor     r8d, r8d
0x180032aef  lea     edx, [r8+2]
0x180032af3  mov     rax, [rax+28h]
0x180032af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032afc  mov     [rbp+0A0h+var_C8], eax
0x180032aff  test    eax, eax
0x180032b01  js      loc_180032D02
0x180032b07  mov     [rbp+0A0h+var_C8], eax
0x180032b0a  mov     rcx, [rsp+1A0h+ppvObject]
0x180032b0f  mov     rax, [rcx]
0x180032b12  xor     edx, edx
0x180032b14  mov     rax, [rax+0D0h]
0x180032b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b20  mov     [rbp+0A0h+var_C8], eax
0x180032b23  test    eax, eax
0x180032b25  js      loc_180032C08
0x180032b2b  mov     [rbp+0A0h+var_C8], eax
0x180032b2e  mov     rbx, [rsp+1A0h+ppvObject]
0x180032b33  xor     eax, eax
0x180032b35  mov     [rsp+1A0h+ppvObject], rax
0x180032b3a  mov     rcx, [rdi]
0x180032b3d  test    rcx, rcx
0x180032b40  jz      short loc_180032B53
0x180032b42  mov     rax, [rcx]
0x180032b45  mov     rax, [rax+10h]
0x180032b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b4e  mov     rax, [rsp+1A0h+ppvObject]
0x180032b53  mov     [rdi], rbx
0x180032b56  mov     rbx, [rsp+1A0h+ppstm]
0x180032b5b  xor     ecx, ecx
0x180032b5d  mov     [rsp+1A0h+ppstm], rcx
0x180032b62  mov     rdx, [rsi]
0x180032b65  test    rdx, rdx
0x180032b68  jz      short loc_180032B83
0x180032b6a  mov     rax, [rdx]
0x180032b6d  mov     rcx, rdx
0x180032b70  mov     rax, [rax+10h]
0x180032b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b79  mov     rcx, [rsp+1A0h+ppstm]
0x180032b7e  mov     rax, [rsp+1A0h+ppvObject]
0x180032b83  mov     [rsi], rbx
0x180032b86  test    rax, rax
0x180032b89  jz      short loc_180032BA2
0x180032b8b  mov     rcx, [rax]
0x180032b8e  mov     rdx, [rcx+10h]
0x180032b92  mov     rcx, rax
0x180032b95  mov     rax, rdx
0x180032b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b9d  mov     rcx, [rsp+1A0h+ppstm]
0x180032ba2  mov     rdx, [rsp+1A0h+ppOutput]
0x180032ba7  test    rdx, rdx
0x180032baa  jz      short loc_180032BC0
0x180032bac  mov     rax, [rdx]
0x180032baf  mov     rcx, rdx
0x180032bb2  mov     rax, [rax+10h]
0x180032bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bbb  mov     rcx, [rsp+1A0h+ppstm]
0x180032bc0  test    rcx, rcx
0x180032bc3  jz      short loc_180032BD2
0x180032bc5  mov     rax, [rcx]
0x180032bc8  mov     rax, [rax+10h]
0x180032bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bd1  nop
0x180032bd2  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180032bd9  mov     [rbp+0A0h+var_D0], rax
0x180032bdd  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032be1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180032be6  mov     rcx, [rbp+0A0h+var_20]
0x180032bed  xor     rcx, rsp; StackCookie
0x180032bf0  call    __security_check_cookie
0x180032bf5  mov     rbx, [rsp+1A0h+arg_10]
0x180032bfd  add     rsp, 190h
0x180032c04  pop     rdi
0x180032c05  pop     rsi
0x180032c06  pop     rbp
0x180032c07  retn
0x180032c08  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c0c  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c11  mov     edx, eax; int
0x180032c13  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c17  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032c1c  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c20  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c25  mov     r8d, eax; char
0x180032c28  xor     r9d, r9d; unsigned __int16 *
0x180032c2b  mov     edx, 381h; unsigned int
0x180032c30  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c34  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032c3a  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c3e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c43  mov     edx, eax; int
0x180032c45  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c49  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032c4e  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c52  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c57  mov     r8d, eax; char
0x180032c5a  xor     r9d, r9d; unsigned __int16 *
0x180032c5d  mov     edx, 374h; unsigned int
0x180032c62  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c66  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032c6c  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c70  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c75  mov     edx, eax; int
0x180032c77  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c7b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032c80  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c84  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032c89  mov     r8d, eax; char
0x180032c8c  xor     r9d, r9d; unsigned __int16 *
0x180032c8f  mov     edx, 377h; unsigned int
0x180032c94  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032c98  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032c9e  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032ca2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032ca7  mov     edx, eax; int
0x180032ca9  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cad  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032cb2  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cb6  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032cbb  mov     r8d, eax; char
0x180032cbe  xor     r9d, r9d; unsigned __int16 *
0x180032cc1  mov     edx, 379h; unsigned int
0x180032cc6  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cca  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032cd0  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cd4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032cd9  mov     edx, eax; int
0x180032cdb  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cdf  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032ce4  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032ce8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032ced  mov     r8d, eax; char
0x180032cf0  xor     r9d, r9d; unsigned __int16 *
0x180032cf3  mov     edx, 37Bh; unsigned int
0x180032cf8  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032cfc  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180032d02  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032d06  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032d0b  mov     edx, eax; int
0x180032d0d  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032d11  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180032d16  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032d1a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180032d1f  mov     r8d, eax; char
0x180032d22  xor     r9d, r9d; unsigned __int16 *
0x180032d25  mov     edx, 37Fh; unsigned int
0x180032d2a  lea     rcx, [rbp+0A0h+var_D0]; this
0x180032d2e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
