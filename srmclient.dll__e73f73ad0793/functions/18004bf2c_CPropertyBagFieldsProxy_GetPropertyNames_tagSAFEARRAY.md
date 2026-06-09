# CPropertyBagFieldsProxy::GetPropertyNames(tagSAFEARRAY * *)

- ea: `0x18004bf2c`
- end: `0x18004c186`
- name: `?GetPropertyNames@CPropertyBagFieldsProxy@@QEBAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `602`
- prototype: `void __fastcall(CPropertyBagFieldsProxy *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049d90`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012238`
- `0x18004bf2c`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004c055`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c055`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004c085`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004c085`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004c003`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004c003`

## string_xrefs

- `0x18004bf6e`: `base\fs\fsrm\service\modulewrp\pbfproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPropertyBagFieldsProxy::GetPropertyNames(CPropertyBagFieldsProxy *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *Vector; // rdi
  __int64 v5; // rdx
  unsigned int v6; // eax
  const OLECHAR *v7; // rbx
  BSTR v8; // rax
  HRESULT v9; // eax
  int v10; // eax
  char v11; // al
  char Hr; // al
  LONG rgIndices; // [rsp+20h] [rbp-E0h] BYREF
  void **v14; // [rsp+28h] [rbp-D8h]
  SAFEARRAY *v15; // [rsp+30h] [rbp-D0h]
  VARIANTARG pv; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v17; // [rsp+50h] [rbp-B0h]
  _QWORD v18[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+74h] [rbp-8Ch]
  int v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[96]; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+E0h] [rbp-20h]
  void **v24; // [rsp+F0h] [rbp-10h] BYREF
  HRESULT v25; // [rsp+F8h] [rbp-8h]

  v17 = v18;
  v18[0] = L"base\\fs\\fsrm\\service\\modulewrp\\pbfproxy.cpp";
  v18[1] = L"CPropertyBagFieldsProxy::GetPropertyNames";
  v18[2] = L"PBFPROXC";
  v19 = 339;
  v20 = 22;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v24, (const struct CSrmDebugInfo *)v18, 0);
  v15 = 0;
  v14 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  Vector = SafeArrayCreateVector(0xCu, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 16LL));
  v15 = Vector;
  if ( !Vector )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v24, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v24);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v24, 0x159u, Hr, 0);
  }
  v25 = 0;
  rgIndices = 0;
  v5 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v5 + 16) )
  {
    v6 = 0;
    do
    {
      v7 = *(const OLECHAR **)(32LL * v6 + *(_QWORD *)(v5 + 24));
      v8 = SysAllocString(v7);
      if ( !v8 && v7 )
        _com_issue_error(-2147024882);
      pv.vt = 8;
      pv.llVal = (LONGLONG)v8;
      v9 = SafeArrayPutElement(Vector, &rgIndices, &pv);
      v25 = v9;
      if ( v9 < 0 )
      {
        v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v24);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v24, v10);
        v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v24);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v24, 0x160u, v11, 0);
      }
      v25 = v9;
      _variant_t::~_variant_t(&pv);
      v6 = rgIndices + 1;
      rgIndices = v6;
      v5 = *((_QWORD *)this + 2);
    }
    while ( v6 < *(_DWORD *)(v5 + 16) );
  }
  *a2 = Vector;
  v14 = &CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable';
  v15 = 0;
  v24 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v24);
}

```

## disassembly

```asm
0x18004bf2c  mov     [rsp-8+arg_10], rbx
0x18004bf31  mov     [rsp-8+arg_18], rsi
0x18004bf36  push    rbp
0x18004bf37  push    rdi
0x18004bf38  push    r12
0x18004bf3a  push    r13
0x18004bf3c  push    r14
0x18004bf3e  lea     rbp, [rsp-0B0h]
0x18004bf46  sub     rsp, 1B0h
0x18004bf4d  mov     rax, cs:__security_cookie
0x18004bf54  xor     rax, rsp
0x18004bf57  mov     [rbp+0D0h+var_30], rax
0x18004bf5e  mov     r14, rdx
0x18004bf61  mov     rsi, rcx
0x18004bf64  lea     rax, [rsp+1D0h+var_178]
0x18004bf69  mov     [rsp+1D0h+var_180], rax
0x18004bf6e  lea     rax, aBaseFsFsrmServ_15; "base\\fs\\fsrm\\service\\modulewrp\\pbf"...
0x18004bf75  mov     [rsp+1D0h+var_178], rax
0x18004bf7a  lea     rax, aCpropertybagfi_20; "CPropertyBagFieldsProxy::GetPropertyNam"...
0x18004bf81  mov     [rsp+1D0h+var_170], rax
0x18004bf86  lea     rax, aPbfproxc; "PBFPROXC"
0x18004bf8d  mov     [rsp+1D0h+var_168], rax
0x18004bf92  mov     [rsp+1D0h+var_160], 153h
0x18004bf9a  mov     [rsp+1D0h+var_15C], 16h
0x18004bfa2  mov     [rsp+1D0h+var_158], 0FFh
0x18004bfaa  mov     [rbp+0D0h+var_F0], 1000000h
0x18004bfb1  xor     edx, edx; Val
0x18004bfb3  lea     r8d, [rdx+60h]; Size
0x18004bfb7  lea     rcx, [rbp+0D0h+var_150]; void *
0x18004bfbb  call    memset_0
0x18004bfc0  nop
0x18004bfc1  xor     r8d, r8d
0x18004bfc4  lea     rdx, [rsp+1D0h+var_178]
0x18004bfc9  lea     rcx, [rbp+0D0h+var_E0]
0x18004bfcd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004bfd2  nop
0x18004bfd3  lea     r12, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18004bfda  mov     [rsp+1D0h+var_1A8], r12
0x18004bfdf  mov     [rsp+1D0h+var_1A0], 0
0x18004bfe8  lea     r13, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18004bfef  mov     [rsp+1D0h+var_1A8], r13
0x18004bff4  mov     r8, [rsi+10h]
0x18004bff8  mov     ecx, 0Ch; vt
0x18004bffd  mov     r8d, [r8+10h]; cElements
0x18004c001  xor     edx, edx; lLbound
0x18004c003  call    cs:__imp_SafeArrayCreateVector
0x18004c009  mov     rdi, rax
0x18004c00c  mov     [rsp+1D0h+var_1A0], 0
0x18004c015  mov     [rsp+1D0h+var_1A0], rax
0x18004c01a  mov     ecx, [rbp+0D0h+var_D8]
0x18004c01d  mov     [rbp+0D0h+var_D8], ecx
0x18004c020  test    rax, rax
0x18004c023  jz      loc_18004C14F
0x18004c029  mov     [rbp+0D0h+var_D8], 0
0x18004c030  mov     [rsp+1D0h+rgIndices], 0
0x18004c038  mov     rdx, [rsi+10h]
0x18004c03c  cmp     dword ptr [rdx+10h], 0
0x18004c040  jbe     short loc_18004C0B6
0x18004c042  xor     eax, eax
0x18004c044  mov     ecx, eax
0x18004c046  shl     rcx, 5
0x18004c04a  mov     rax, [rdx+18h]
0x18004c04e  mov     rbx, [rcx+rax]
0x18004c052  mov     rcx, rbx; psz
0x18004c055  call    cs:__imp_SysAllocString
0x18004c05b  test    rax, rax
0x18004c05e  jnz     short loc_18004C069
0x18004c060  test    rbx, rbx
0x18004c063  jnz     loc_18004C17B
0x18004c069  mov     ecx, 8
0x18004c06e  mov     [rsp+1D0h+pv], cx
0x18004c073  mov     [rsp+1D0h+var_190], rax
0x18004c078  lea     r8, [rsp+1D0h+pv]; pv
0x18004c07d  lea     rdx, [rsp+1D0h+rgIndices]; rgIndices
0x18004c082  mov     rcx, rdi; psa
0x18004c085  call    cs:__imp_SafeArrayPutElement
0x18004c08b  mov     [rbp+0D0h+var_D8], eax
0x18004c08e  test    eax, eax
0x18004c090  js      loc_18004C11D
0x18004c096  mov     [rbp+0D0h+var_D8], eax
0x18004c099  lea     rcx, [rsp+1D0h+pv]; this
0x18004c09e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004c0a3  mov     eax, [rsp+1D0h+rgIndices]
0x18004c0a7  inc     eax
0x18004c0a9  mov     [rsp+1D0h+rgIndices], eax
0x18004c0ad  mov     rdx, [rsi+10h]
0x18004c0b1  cmp     eax, [rdx+10h]
0x18004c0b4  jb      short loc_18004C044
0x18004c0b6  mov     [rsp+1D0h+var_1A0], 0
0x18004c0bf  mov     [r14], rdi
0x18004c0c2  mov     [rsp+1D0h+var_1A8], r13
0x18004c0c7  mov     [rsp+1D0h+var_1A0], 0
0x18004c0d0  mov     [rsp+1D0h+var_1A8], r12
0x18004c0d5  mov     [rsp+1D0h+var_1A0], 0
0x18004c0de  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004c0e5  mov     [rbp+0D0h+var_E0], rax
0x18004c0e9  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c0ed  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004c0f2  mov     rcx, [rbp+0D0h+var_30]
0x18004c0f9  xor     rcx, rsp; StackCookie
0x18004c0fc  call    __security_check_cookie
0x18004c101  lea     r11, [rsp+1D0h+var_20]
0x18004c109  mov     rbx, [r11+40h]
0x18004c10d  mov     rsi, [r11+48h]
0x18004c111  mov     rsp, r11
0x18004c114  pop     r14
0x18004c116  pop     r13
0x18004c118  pop     r12
0x18004c11a  pop     rdi
0x18004c11b  pop     rbp
0x18004c11c  retn
0x18004c11d  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c121  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004c126  mov     edx, eax; int
0x18004c128  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c12c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004c131  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c135  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004c13a  mov     r8d, eax; char
0x18004c13d  xor     r9d, r9d; unsigned __int16 *
0x18004c140  mov     edx, 160h; unsigned int
0x18004c145  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c149  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004c14f  mov     edx, 8007000Eh; int
0x18004c154  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c158  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004c15d  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c161  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004c166  mov     r8d, eax; char
0x18004c169  xor     r9d, r9d; unsigned __int16 *
0x18004c16c  mov     edx, 159h; unsigned int
0x18004c171  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004c175  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004c17b  mov     ecx, 8007000Eh; int
0x18004c180  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
