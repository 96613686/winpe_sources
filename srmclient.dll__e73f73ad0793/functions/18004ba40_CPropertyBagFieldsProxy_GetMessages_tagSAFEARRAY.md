# CPropertyBagFieldsProxy::GetMessages(tagSAFEARRAY * *)

- ea: `0x18004ba40`
- end: `0x18004bd66`
- name: `?GetMessages@CPropertyBagFieldsProxy@@UEBAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `806`
- prototype: `void __fastcall(CPropertyBagFieldsProxy *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012238`
- `0x18004ba40`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004bb78`
- `OLEAUT32!__imp_SysAllocString` at `0x18004bbf2`
- `OLEAUT32!__imp_SysAllocString` at `0x18004bb78`
- `OLEAUT32!__imp_SysAllocString` at `0x18004bbf2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bba4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bc1e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bba4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004bc1e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004bb20`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004bb20`

## string_xrefs

- `0x18004ba82`: `base\fs\fsrm\service\modulewrp\pbfproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CPropertyBagFieldsProxy::GetMessages(CPropertyBagFieldsProxy *this, struct tagSAFEARRAY **a2)
{
  ULONG v4; // r14d
  SAFEARRAY *Vector; // rsi
  __int64 v6; // rdx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  const OLECHAR *v9; // rdi
  BSTR v10; // rax
  HRESULT v11; // eax
  const OLECHAR *v12; // rdi
  BSTR v13; // rax
  HRESULT v14; // eax
  int v15; // eax
  char v16; // al
  char Hr; // al
  int v18; // eax
  char v19; // al
  LONG rgIndices; // [rsp+20h] [rbp-E0h] BYREF
  LONG v21; // [rsp+24h] [rbp-DCh] BYREF
  void **v22; // [rsp+28h] [rbp-D8h]
  SAFEARRAY *v23; // [rsp+30h] [rbp-D0h]
  VARIANTARG pv; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v25; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v26; // [rsp+68h] [rbp-98h]
  _QWORD v27[3]; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+90h] [rbp-70h]
  _BYTE v31[96]; // [rsp+98h] [rbp-68h] BYREF
  int v32; // [rsp+F8h] [rbp-8h]
  void **v33; // [rsp+100h] [rbp+0h] BYREF
  HRESULT v34; // [rsp+108h] [rbp+8h]

  v26 = v27;
  v27[0] = L"base\\fs\\fsrm\\service\\modulewrp\\pbfproxy.cpp";
  v27[1] = L"CPropertyBagFieldsProxy::GetMessages";
  v27[2] = L"PBFPROXC";
  v28 = 297;
  v29 = 22;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v33, (const struct CSrmDebugInfo *)v27, 0);
  v4 = **((_DWORD **)this + 2) + *(_DWORD *)(*((_QWORD *)this + 50) + 4LL);
  v22 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  Vector = SafeArrayCreateVector(0xCu, 0, v4);
  v23 = Vector;
  if ( !Vector )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x135u, Hr, 0);
  }
  v34 = 0;
  rgIndices = 0;
  v6 = *((_QWORD *)this + 2);
  v7 = *(_DWORD *)v6;
  if ( *(_DWORD *)v6 )
  {
    v8 = 0;
    do
    {
      v9 = *(const OLECHAR **)(*(_QWORD *)(v6 + 8) + 8LL * v8);
      v10 = SysAllocString(v9);
      if ( !v10 && v9 )
        _com_issue_error(-2147024882);
      pv.vt = 8;
      pv.llVal = (LONGLONG)v10;
      v11 = SafeArrayPutElement(Vector, &rgIndices, &pv);
      v34 = v11;
      if ( v11 < 0 )
      {
        v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v18);
        v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x13Eu, v19, 0);
      }
      v34 = v11;
      _variant_t::~_variant_t(&pv);
      v8 = rgIndices + 1;
      rgIndices = v8;
      v6 = *((_QWORD *)this + 2);
      v7 = *(_DWORD *)v6;
    }
    while ( v8 < *(_DWORD *)v6 );
  }
  while ( 1 )
  {
    v21 = v7;
    if ( v7 >= v4 )
      break;
    v12 = *(const OLECHAR **)(*(_QWORD *)(*((_QWORD *)this + 50) + 8LL) + 8LL * (v7 - **((_DWORD **)this + 2)));
    v13 = SysAllocString(v12);
    if ( !v13 && v12 )
      _com_issue_error(-2147024882);
    v25.vt = 8;
    v25.llVal = (LONGLONG)v13;
    v14 = SafeArrayPutElement(Vector, &v21, &v25);
    v34 = v14;
    if ( v14 < 0 )
    {
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v33, v15);
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v33);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v33, 0x148u, v16, 0);
    }
    v34 = v14;
    _variant_t::~_variant_t(&v25);
    v7 = v21 + 1;
  }
  *a2 = Vector;
  v22 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v23 = 0;
  v33 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v33);
}

```

## disassembly

```asm
0x18004ba40  mov     [rsp-8+arg_10], rbx
0x18004ba45  mov     [rsp-8+arg_18], rsi
0x18004ba4a  push    rbp
0x18004ba4b  push    rdi
0x18004ba4c  push    r13
0x18004ba4e  push    r14
0x18004ba50  push    r15
0x18004ba52  lea     rbp, [rsp-0C0h]
0x18004ba5a  sub     rsp, 1C0h
0x18004ba61  mov     rax, cs:__security_cookie
0x18004ba68  xor     rax, rsp
0x18004ba6b  mov     [rbp+0E0h+var_30], rax
0x18004ba72  mov     r15, rdx
0x18004ba75  mov     rbx, rcx
0x18004ba78  lea     rax, [rsp+1E0h+var_170]
0x18004ba7d  mov     [rsp+1E0h+var_178], rax
0x18004ba82  lea     rax, aBaseFsFsrmServ_15; "base\\fs\\fsrm\\service\\modulewrp\\pbf"...
0x18004ba89  mov     [rsp+1E0h+var_170], rax
0x18004ba8e  lea     rax, aCpropertybagfi_1; "CPropertyBagFieldsProxy::GetMessages"
0x18004ba95  mov     [rsp+1E0h+var_168], rax
0x18004ba9a  lea     rax, aPbfproxc; "PBFPROXC"
0x18004baa1  mov     [rbp+0E0h+var_160], rax
0x18004baa5  mov     [rbp+0E0h+var_158], 129h
0x18004baac  mov     [rbp+0E0h+var_154], 16h
0x18004bab3  mov     [rbp+0E0h+var_150], 0FFh
0x18004baba  mov     [rbp+0E0h+var_E8], 1000000h
0x18004bac1  xor     edx, edx; Val
0x18004bac3  lea     r8d, [rdx+60h]; Size
0x18004bac7  lea     rcx, [rbp+0E0h+var_148]; void *
0x18004bacb  call    memset_0
0x18004bad0  nop
0x18004bad1  xor     r8d, r8d
0x18004bad4  lea     rdx, [rsp+1E0h+var_170]
0x18004bad9  lea     rcx, [rbp+0E0h+var_E0]
0x18004badd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004bae2  nop
0x18004bae3  mov     rax, [rbx+190h]
0x18004baea  mov     rcx, [rbx+10h]
0x18004baee  mov     r14d, [rax+4]
0x18004baf2  add     r14d, [rcx]
0x18004baf5  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18004bafc  mov     [rsp+1E0h+var_1B8], rax
0x18004bb01  mov     [rsp+1E0h+var_1B0], 0
0x18004bb0a  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18004bb11  mov     [rsp+1E0h+var_1B8], rax
0x18004bb16  mov     ecx, 0Ch; vt
0x18004bb1b  mov     r8d, r14d; cElements
0x18004bb1e  xor     edx, edx; lLbound
0x18004bb20  call    cs:__imp_SafeArrayCreateVector
0x18004bb26  mov     rsi, rax
0x18004bb29  mov     [rsp+1E0h+var_1B0], 0
0x18004bb32  mov     [rsp+1E0h+var_1B0], rax
0x18004bb37  mov     ecx, [rbp+0E0h+var_D8]
0x18004bb3a  mov     [rbp+0E0h+var_D8], ecx
0x18004bb3d  test    rax, rax
0x18004bb40  jz      loc_18004BCF2
0x18004bb46  mov     [rbp+0E0h+var_D8], 0
0x18004bb4d  mov     [rsp+1E0h+rgIndices], 0
0x18004bb55  mov     rdx, [rbx+10h]
0x18004bb59  mov     ecx, [rdx]
0x18004bb5b  mov     r13d, 8
0x18004bb61  test    ecx, ecx
0x18004bb63  jz      loc_18004BC42
0x18004bb69  xor     eax, eax
0x18004bb6b  mov     ecx, eax
0x18004bb6d  mov     rax, [rdx+8]
0x18004bb71  mov     rdi, [rax+rcx*8]
0x18004bb75  mov     rcx, rdi; psz
0x18004bb78  call    cs:__imp_SysAllocString
0x18004bb7e  test    rax, rax
0x18004bb81  jnz     short loc_18004BB8C
0x18004bb83  test    rdi, rdi
0x18004bb86  jnz     loc_18004BD1E
0x18004bb8c  mov     [rsp+1E0h+pv], r13w
0x18004bb92  mov     [rsp+1E0h+var_1A0], rax
0x18004bb97  lea     r8, [rsp+1E0h+pv]; pv
0x18004bb9c  lea     rdx, [rsp+1E0h+rgIndices]; rgIndices
0x18004bba1  mov     rcx, rsi; psa
0x18004bba4  call    cs:__imp_SafeArrayPutElement
0x18004bbaa  mov     [rbp+0E0h+var_D8], eax
0x18004bbad  test    eax, eax
0x18004bbaf  js      loc_18004BD29
0x18004bbb5  mov     [rbp+0E0h+var_D8], eax
0x18004bbb8  lea     rcx, [rsp+1E0h+pv]; this
0x18004bbbd  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004bbc2  mov     eax, [rsp+1E0h+rgIndices]
0x18004bbc6  inc     eax
0x18004bbc8  mov     [rsp+1E0h+rgIndices], eax
0x18004bbcc  mov     rdx, [rbx+10h]
0x18004bbd0  mov     ecx, [rdx]
0x18004bbd2  cmp     eax, ecx
0x18004bbd4  jb      short loc_18004BB6B
0x18004bbd6  jmp     short loc_18004BC42
0x18004bbd8  mov     rax, [rbx+10h]
0x18004bbdc  sub     ecx, [rax]
0x18004bbde  mov     edx, ecx
0x18004bbe0  mov     rax, [rbx+190h]
0x18004bbe7  mov     rcx, [rax+8]
0x18004bbeb  mov     rdi, [rcx+rdx*8]
0x18004bbef  mov     rcx, rdi; psz
0x18004bbf2  call    cs:__imp_SysAllocString
0x18004bbf8  test    rax, rax
0x18004bbfb  jnz     short loc_18004BC06
0x18004bbfd  test    rdi, rdi
0x18004bc00  jnz     loc_18004BD5B
0x18004bc06  mov     [rsp+1E0h+var_190], r13w
0x18004bc0c  mov     [rsp+1E0h+var_188], rax
0x18004bc11  lea     r8, [rsp+1E0h+var_190]; pv
0x18004bc16  lea     rdx, [rsp+1E0h+var_1BC]; rgIndices
0x18004bc1b  mov     rcx, rsi; psa
0x18004bc1e  call    cs:__imp_SafeArrayPutElement
0x18004bc24  mov     [rbp+0E0h+var_D8], eax
0x18004bc27  test    eax, eax
0x18004bc29  js      loc_18004BCC0
0x18004bc2f  mov     [rbp+0E0h+var_D8], eax
0x18004bc32  lea     rcx, [rsp+1E0h+var_190]; this
0x18004bc37  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004bc3c  mov     ecx, [rsp+1E0h+var_1BC]
0x18004bc40  inc     ecx
0x18004bc42  cmp     ecx, r14d
0x18004bc45  mov     [rsp+1E0h+var_1BC], ecx
0x18004bc49  jb      short loc_18004BBD8
0x18004bc4b  mov     [rsp+1E0h+var_1B0], 0
0x18004bc54  mov     [r15], rsi
0x18004bc57  lea     rax, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18004bc5e  mov     [rsp+1E0h+var_1B8], rax
0x18004bc63  mov     [rsp+1E0h+var_1B0], 0
0x18004bc6c  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18004bc73  mov     [rsp+1E0h+var_1B8], rax
0x18004bc78  mov     [rsp+1E0h+var_1B0], 0
0x18004bc81  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004bc88  mov     [rbp+0E0h+var_E0], rax
0x18004bc8c  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bc90  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004bc95  mov     rcx, [rbp+0E0h+var_30]
0x18004bc9c  xor     rcx, rsp; StackCookie
0x18004bc9f  call    __security_check_cookie
0x18004bca4  lea     r11, [rsp+1E0h+var_20]
0x18004bcac  mov     rbx, [r11+40h]
0x18004bcb0  mov     rsi, [r11+48h]
0x18004bcb4  mov     rsp, r11
0x18004bcb7  pop     r15
0x18004bcb9  pop     r14
0x18004bcbb  pop     r13
0x18004bcbd  pop     rdi
0x18004bcbe  pop     rbp
0x18004bcbf  retn
0x18004bcc0  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bcc4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004bcc9  mov     edx, eax; int
0x18004bccb  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bccf  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004bcd4  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bcd8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004bcdd  mov     r8d, eax; char
0x18004bce0  xor     r9d, r9d; unsigned __int16 *
0x18004bce3  mov     edx, 148h; unsigned int
0x18004bce8  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bcec  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004bcf2  mov     edx, 8007000Eh; int
0x18004bcf7  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bcfb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004bd00  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd04  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004bd09  mov     r8d, eax; char
0x18004bd0c  xor     r9d, r9d; unsigned __int16 *
0x18004bd0f  mov     edx, 135h; unsigned int
0x18004bd14  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd18  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004bd1e  mov     ecx, 8007000Eh; int
0x18004bd23  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004bd29  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd2d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004bd32  mov     edx, eax; int
0x18004bd34  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd38  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004bd3d  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd41  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004bd46  mov     r8d, eax; char
0x18004bd49  xor     r9d, r9d; unsigned __int16 *
0x18004bd4c  mov     edx, 13Eh; unsigned int
0x18004bd51  lea     rcx, [rbp+0E0h+var_E0]; this
0x18004bd55  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004bd5b  mov     ecx, 8007000Eh; int
0x18004bd60  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
