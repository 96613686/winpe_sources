# CPropertyBagFields::GetMessages(tagSAFEARRAY * *)

- ea: `0x18004e290`
- end: `0x18004e4e3`
- name: `?GetMessages@CPropertyBagFields@@UEBAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `595`
- prototype: `void __fastcall(CPropertyBagFields *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180012238`
- `0x18004e290`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18008d668`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004e3b3`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e3b3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004e3e3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004e3e3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004e366`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004e366`

## string_xrefs

- `0x18004e2d2`: `base\fs\fsrm\service\pipeline\pbfields.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPropertyBagFields::GetMessages(CPropertyBagFields *this, struct tagSAFEARRAY **a2)
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
  v18[0] = L"base\\fs\\fsrm\\service\\pipeline\\pbfields.cpp";
  v18[1] = L"CPropertyBagFields::GetMessages";
  v18[2] = L"PBFIELDC";
  v19 = 335;
  v20 = 22;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v24, (const struct CSrmDebugInfo *)v18, 0);
  v15 = 0;
  v14 = &CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&public: static tagSAFEARRAY * & DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable';
  Vector = SafeArrayCreateVector(0xCu, 0, **((_DWORD **)this + 2));
  v15 = Vector;
  if ( !Vector )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v24, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v24);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v24, 0x155u, Hr, 0);
  }
  v25 = 0;
  rgIndices = 0;
  v5 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)v5 )
  {
    v6 = 0;
    do
    {
      v7 = *(const OLECHAR **)(*(_QWORD *)(v5 + 8) + 8LL * v6);
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
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v24, 0x15Bu, v11, 0);
      }
      v25 = v9;
      _variant_t::~_variant_t(&pv);
      v6 = rgIndices + 1;
      rgIndices = v6;
      v5 = *((_QWORD *)this + 2);
    }
    while ( v6 < *(_DWORD *)v5 );
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
0x18004e290  mov     [rsp-8+arg_10], rbx
0x18004e295  mov     [rsp-8+arg_18], rsi
0x18004e29a  push    rbp
0x18004e29b  push    rdi
0x18004e29c  push    r12
0x18004e29e  push    r13
0x18004e2a0  push    r14
0x18004e2a2  lea     rbp, [rsp-0B0h]
0x18004e2aa  sub     rsp, 1B0h
0x18004e2b1  mov     rax, cs:__security_cookie
0x18004e2b8  xor     rax, rsp
0x18004e2bb  mov     [rbp+0D0h+var_30], rax
0x18004e2c2  mov     r14, rdx
0x18004e2c5  mov     rsi, rcx
0x18004e2c8  lea     rax, [rsp+1D0h+var_178]
0x18004e2cd  mov     [rsp+1D0h+var_180], rax
0x18004e2d2  lea     rax, aBaseFsFsrmServ_5; "base\\fs\\fsrm\\service\\pipeline\\pbfi"...
0x18004e2d9  mov     [rsp+1D0h+var_178], rax
0x18004e2de  lea     rax, aCpropertybagfi; "CPropertyBagFields::GetMessages"
0x18004e2e5  mov     [rsp+1D0h+var_170], rax
0x18004e2ea  lea     rax, aPbfieldc; "PBFIELDC"
0x18004e2f1  mov     [rsp+1D0h+var_168], rax
0x18004e2f6  mov     [rsp+1D0h+var_160], 14Fh
0x18004e2fe  mov     [rsp+1D0h+var_15C], 16h
0x18004e306  mov     [rsp+1D0h+var_158], 0FFh
0x18004e30e  mov     [rbp+0D0h+var_F0], 1000000h
0x18004e315  xor     edx, edx; Val
0x18004e317  lea     r8d, [rdx+60h]; Size
0x18004e31b  lea     rcx, [rbp+0D0h+var_150]; void *
0x18004e31f  call    memset_0
0x18004e324  nop
0x18004e325  xor     r8d, r8d
0x18004e328  lea     rdx, [rsp+1D0h+var_178]
0x18004e32d  lea     rcx, [rbp+0D0h+var_E0]
0x18004e331  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004e336  nop
0x18004e337  lea     r12, ??_7?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>::`vftable'
0x18004e33e  mov     [rsp+1D0h+var_1A8], r12
0x18004e343  mov     [rsp+1D0h+var_1A0], 0
0x18004e34c  lea     r13, ??_7?$CSrmAuto@PEAUtagSAFEARRAY@@V?$CSrmAutoGenericValue_Storage@PEAUtagSAFEARRAY@@$0A@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUtagSAFEARRAY@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<tagSAFEARRAY *,CSrmAutoGenericValue_Storage<tagSAFEARRAY *,0,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY * & (*)(tagSAFEARRAY * &),&DTyper<tagSAFEARRAY *>::Identity(tagSAFEARRAY * &)>>::`vftable'
0x18004e353  mov     [rsp+1D0h+var_1A8], r13
0x18004e358  mov     r8, [rsi+10h]
0x18004e35c  mov     ecx, 0Ch; vt
0x18004e361  mov     r8d, [r8]; cElements
0x18004e364  xor     edx, edx; lLbound
0x18004e366  call    cs:__imp_SafeArrayCreateVector
0x18004e36c  mov     rdi, rax
0x18004e36f  mov     [rsp+1D0h+var_1A0], 0
0x18004e378  mov     [rsp+1D0h+var_1A0], rax
0x18004e37d  mov     ecx, [rbp+0D0h+var_D8]
0x18004e380  mov     [rbp+0D0h+var_D8], ecx
0x18004e383  test    rax, rax
0x18004e386  jz      loc_18004E4AC
0x18004e38c  mov     [rbp+0D0h+var_D8], 0
0x18004e393  mov     [rsp+1D0h+rgIndices], 0
0x18004e39b  mov     rdx, [rsi+10h]
0x18004e39f  cmp     dword ptr [rdx], 0
0x18004e3a2  jbe     short loc_18004E413
0x18004e3a4  xor     eax, eax
0x18004e3a6  mov     ecx, eax
0x18004e3a8  mov     rax, [rdx+8]
0x18004e3ac  mov     rbx, [rax+rcx*8]
0x18004e3b0  mov     rcx, rbx; psz
0x18004e3b3  call    cs:__imp_SysAllocString
0x18004e3b9  test    rax, rax
0x18004e3bc  jnz     short loc_18004E3C7
0x18004e3be  test    rbx, rbx
0x18004e3c1  jnz     loc_18004E4D8
0x18004e3c7  mov     ecx, 8
0x18004e3cc  mov     [rsp+1D0h+pv], cx
0x18004e3d1  mov     [rsp+1D0h+var_190], rax
0x18004e3d6  lea     r8, [rsp+1D0h+pv]; pv
0x18004e3db  lea     rdx, [rsp+1D0h+rgIndices]; rgIndices
0x18004e3e0  mov     rcx, rdi; psa
0x18004e3e3  call    cs:__imp_SafeArrayPutElement
0x18004e3e9  mov     [rbp+0D0h+var_D8], eax
0x18004e3ec  test    eax, eax
0x18004e3ee  js      loc_18004E47A
0x18004e3f4  mov     [rbp+0D0h+var_D8], eax
0x18004e3f7  lea     rcx, [rsp+1D0h+pv]; this
0x18004e3fc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004e401  mov     eax, [rsp+1D0h+rgIndices]
0x18004e405  inc     eax
0x18004e407  mov     [rsp+1D0h+rgIndices], eax
0x18004e40b  mov     rdx, [rsi+10h]
0x18004e40f  cmp     eax, [rdx]
0x18004e411  jb      short loc_18004E3A6
0x18004e413  mov     [rsp+1D0h+var_1A0], 0
0x18004e41c  mov     [r14], rdi
0x18004e41f  mov     [rsp+1D0h+var_1A8], r13
0x18004e424  mov     [rsp+1D0h+var_1A0], 0
0x18004e42d  mov     [rsp+1D0h+var_1A8], r12
0x18004e432  mov     [rsp+1D0h+var_1A0], 0
0x18004e43b  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004e442  mov     [rbp+0D0h+var_E0], rax
0x18004e446  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e44a  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004e44f  mov     rcx, [rbp+0D0h+var_30]
0x18004e456  xor     rcx, rsp; StackCookie
0x18004e459  call    __security_check_cookie
0x18004e45e  lea     r11, [rsp+1D0h+var_20]
0x18004e466  mov     rbx, [r11+40h]
0x18004e46a  mov     rsi, [r11+48h]
0x18004e46e  mov     rsp, r11
0x18004e471  pop     r14
0x18004e473  pop     r13
0x18004e475  pop     r12
0x18004e477  pop     rdi
0x18004e478  pop     rbp
0x18004e479  retn
0x18004e47a  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e47e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004e483  mov     edx, eax; int
0x18004e485  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e489  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004e48e  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e492  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004e497  mov     r8d, eax; char
0x18004e49a  xor     r9d, r9d; unsigned __int16 *
0x18004e49d  mov     edx, 15Bh; unsigned int
0x18004e4a2  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e4a6  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004e4ac  mov     edx, 8007000Eh; int
0x18004e4b1  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e4b5  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004e4ba  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e4be  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004e4c3  mov     r8d, eax; char
0x18004e4c6  xor     r9d, r9d; unsigned __int16 *
0x18004e4c9  mov     edx, 155h; unsigned int
0x18004e4ce  lea     rcx, [rbp+0D0h+var_E0]; this
0x18004e4d2  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004e4d8  mov     ecx, 8007000Eh; int
0x18004e4dd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
