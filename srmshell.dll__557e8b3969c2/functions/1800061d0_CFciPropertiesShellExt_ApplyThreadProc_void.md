# CFciPropertiesShellExt::ApplyThreadProc(void)

- ea: `0x1800061d0`
- end: `0x1800065b5`
- name: `?ApplyThreadProc@CFciPropertiesShellExt@@AEAAXXZ`
- size: `997`
- prototype: `void __fastcall(CFciPropertiesShellExt *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002960`

## callees

- `0x180001e44`
- `0x1800061d0`
- `0x1800083e0`
- `0x180009d18`
- `0x18000d368`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000639a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800063f1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000639a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800063f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063be`
- `OLEAUT32!__imp_SysFreeString` at `0x180006414`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063be`
- `OLEAUT32!__imp_SysFreeString` at `0x180006414`
- `OLEAUT32!__imp_VariantInit` at `0x1800062c1`
- `OLEAUT32!__imp_VariantInit` at `0x180006304`
- `OLEAUT32!__imp_VariantInit` at `0x180006360`
- `OLEAUT32!__imp_VariantInit` at `0x1800063ce`
- `OLEAUT32!__imp_VariantInit` at `0x1800062c1`
- `OLEAUT32!__imp_VariantInit` at `0x180006304`
- `OLEAUT32!__imp_VariantInit` at `0x180006360`
- `OLEAUT32!__imp_VariantInit` at `0x1800063ce`
- `OLEAUT32!__imp_VariantClear` at `0x18000646c`
- `OLEAUT32!__imp_VariantClear` at `0x180006478`
- `OLEAUT32!__imp_VariantClear` at `0x1800064a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800064ae`
- `OLEAUT32!__imp_VariantClear` at `0x18000646c`
- `OLEAUT32!__imp_VariantClear` at `0x180006478`
- `OLEAUT32!__imp_VariantClear` at `0x1800064a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800064ae`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000642d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180006450`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000642d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180006450`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800062d2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180006315`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800062d2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180006315`

## string_xrefs

- `0x18000620d`: `CFciPropertiesShellExt::ApplyThreadProc`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::ApplyThreadProc(CFciPropertiesShellExt *this)
{
  __int64 v2; // rbx
  __int64 i; // rax
  struct tagSAFEARRAY *Vector; // r8
  __int64 j; // rbx
  const OLECHAR *v6; // rcx
  BSTR v7; // rax
  const OLECHAR *v8; // rcx
  BSTR v9; // rax
  HRESULT v10; // eax
  HRESULT v11; // eax
  char v12; // al
  char Hr; // al
  int v14; // eax
  char v15; // al
  int v16; // eax
  char v17; // al
  LONG rgIndices; // [rsp+20h] [rbp-E0h] BYREF
  BSTR pExceptionObject; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v20; // [rsp+30h] [rbp-D0h]
  VARIANTARG v21; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v22; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pv; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v25[3]; // [rsp+98h] [rbp-68h] BYREF
  int v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+B8h] [rbp-48h]
  _BYTE v29[96]; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+120h] [rbp+20h]
  void **v31; // [rsp+130h] [rbp+30h] BYREF
  HRESULT v32; // [rsp+138h] [rbp+38h]

  v20 = v25;
  v25[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  v25[1] = L"CFciPropertiesShellExt::ApplyThreadProc";
  v25[2] = L"FCIPROPC";
  v26 = 1336;
  v27 = 17;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CSrmFunctionTracer::CSrmFunctionTracer(&v31, v25, 0);
  v2 = 0;
  for ( i = *((_QWORD *)this + 8); i != *((_QWORD *)this + 9); i += 224 )
  {
    if ( *(_DWORD *)(i + 208) == 3 || *(_DWORD *)(i + 208) == 4 )
      ++v2;
  }
  if ( v2 )
  {
    VariantInit(&pvarg);
    pvarg.llVal = (LONGLONG)SafeArrayCreateVector(0xCu, 0, v2);
    if ( !pvarg.llVal )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0x55Du, Hr, 0);
    }
    v32 = 0;
    pvarg.vt = 8204;
    VariantInit(&v22);
    Vector = SafeArrayCreateVector(0xCu, 0, v2);
    v22.llVal = (LONGLONG)Vector;
    if ( !Vector )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, -2147024882);
      v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0x562u, v12, 0);
    }
    v32 = 0;
    v22.vt = 8204;
    rgIndices = 0;
    for ( j = *((_QWORD *)this + 8); ; j += 224 )
    {
      if ( j == *((_QWORD *)this + 9) )
      {
        CFciPropertiesShellExt::InvokeClassifier((HANDLE *)this, pvarg.parray, Vector);
        VariantClear(&v22);
        VariantClear(&pvarg);
        v31 = &CSrmFunctionTracer::`vftable';
        goto LABEL_9;
      }
      VariantInit(&v21);
      if ( *(_DWORD *)(j + 208) == 3 )
      {
        v6 = (const OLECHAR *)(j + 168);
        if ( *(_QWORD *)(j + 192) >= 8u )
          v6 = *(const OLECHAR **)v6;
        if ( v6 )
        {
          v7 = SysAllocString(v6);
          pExceptionObject = v7;
          if ( !v7 )
          {
            LODWORD(pExceptionObject) = -2147024882;
            throw (long *)&pExceptionObject;
          }
        }
        else
        {
          pExceptionObject = 0;
          v7 = 0;
        }
        pExceptionObject = 0;
        v21.llVal = (LONGLONG)v7;
        SysFreeString(0);
        v21.vt = 8;
      }
      else if ( *(_DWORD *)(j + 208) != 4 )
      {
        goto LABEL_32;
      }
      VariantInit(&pv);
      if ( *(_QWORD *)(j + 24) < 8u )
        v8 = (const OLECHAR *)j;
      else
        v8 = *(const OLECHAR **)j;
      if ( v8 )
      {
        v9 = SysAllocString(v8);
        v20 = v9;
        if ( !v9 )
        {
          LODWORD(pExceptionObject) = -2147024882;
          throw (long *)&pExceptionObject;
        }
      }
      else
      {
        v20 = 0;
        v9 = 0;
      }
      v20 = 0;
      pv.llVal = (LONGLONG)v9;
      SysFreeString(0);
      pv.vt = 8;
      v10 = SafeArrayPutElement(pvarg.parray, &rgIndices, &pv);
      v32 = v10;
      if ( v10 < 0 )
      {
        v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, v16);
        v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0x584u, v17, 0);
      }
      v32 = v10;
      v11 = SafeArrayPutElement(v22.parray, &rgIndices, &v21);
      v32 = v11;
      if ( v11 < 0 )
      {
        v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v31, v14);
        v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v31);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v31, 0x585u, v15, 0);
      }
      v32 = v11;
      ++rgIndices;
      VariantClear(&pv);
LABEL_32:
      VariantClear(&v21);
      Vector = v22.parray;
    }
  }
  v31 = &CSrmFunctionTracer::`vftable';
LABEL_9:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v31);
}

```

## disassembly

```asm
0x1800061d0  push    rbp
0x1800061d2  push    rbx
0x1800061d3  push    rdi
0x1800061d4  push    r14
0x1800061d6  lea     rbp, [rsp-0F8h]
0x1800061de  sub     rsp, 1F8h
0x1800061e5  mov     rax, cs:__security_cookie
0x1800061ec  xor     rax, rsp
0x1800061ef  mov     [rbp+110h+var_30], rax
0x1800061f6  mov     rdi, rcx
0x1800061f9  lea     rax, [rbp+110h+var_178]
0x1800061fd  mov     [rsp+210h+var_1E0], rax
0x180006202  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180006209  mov     [rbp+110h+var_178], rax
0x18000620d  lea     rax, aCfciproperties_11; "CFciPropertiesShellExt::ApplyThreadProc"
0x180006214  mov     [rbp+110h+var_170], rax
0x180006218  lea     rax, aFcipropc; "FCIPROPC"
0x18000621f  mov     [rbp+110h+var_168], rax
0x180006223  mov     [rbp+110h+var_160], 538h
0x18000622a  mov     [rbp+110h+var_15C], 11h
0x180006231  mov     [rbp+110h+var_158], 0FFh
0x180006238  mov     [rbp+110h+var_F0], 1000000h
0x18000623f  xor     edx, edx; Val
0x180006241  lea     r8d, [rdx+60h]; Size
0x180006245  lea     rcx, [rbp+110h+var_150]; void *
0x180006249  call    memset_0
0x18000624e  nop
0x18000624f  xor     r8d, r8d
0x180006252  lea     rdx, [rbp+110h+var_178]
0x180006256  lea     rcx, [rbp+110h+var_E0]
0x18000625a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000625f  nop
0x180006260  xor     ebx, ebx
0x180006262  mov     rax, [rdi+40h]
0x180006266  cmp     rax, [rdi+48h]
0x18000626a  jz      short loc_180006287
0x18000626c  mov     edx, [rax+0D0h]
0x180006272  sub     edx, 3
0x180006275  jz      short loc_18000627C
0x180006277  cmp     edx, 1
0x18000627a  jnz     short loc_18000627F
0x18000627c  inc     rbx
0x18000627f  add     rax, 0E0h
0x180006285  jmp     short loc_180006266
0x180006287  test    rbx, rbx
0x18000628a  jnz     short loc_1800062BC
0x18000628c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180006293  mov     [rbp+110h+var_E0], rax
0x180006297  lea     rcx, [rbp+110h+var_E0]; this
0x18000629b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800062a0  mov     rcx, [rbp+110h+var_30]
0x1800062a7  xor     rcx, rsp; StackCookie
0x1800062aa  call    __security_check_cookie
0x1800062af  add     rsp, 1F8h
0x1800062b6  pop     r14
0x1800062b8  pop     rdi
0x1800062b9  pop     rbx
0x1800062ba  pop     rbp
0x1800062bb  retn
0x1800062bc  lea     rcx, [rsp+210h+pvarg]; pvarg
0x1800062c1  call    cs:__imp_VariantInit
0x1800062c7  nop
0x1800062c8  mov     ecx, 0Ch; vt
0x1800062cd  mov     r8d, ebx; cElements
0x1800062d0  xor     edx, edx; lLbound
0x1800062d2  call    cs:__imp_SafeArrayCreateVector
0x1800062d8  mov     qword ptr [rsp+210h+pvarg+8], rax
0x1800062dd  mov     ecx, [rbp+110h+var_D8]
0x1800062e0  mov     [rbp+110h+var_D8], ecx
0x1800062e3  test    rax, rax
0x1800062e6  jz      loc_1800064F1
0x1800062ec  mov     [rbp+110h+var_D8], 0
0x1800062f3  mov     r14d, 200Ch
0x1800062f9  mov     word ptr [rsp+210h+pvarg], r14w
0x1800062ff  lea     rcx, [rsp+210h+var_1C0]; pvarg
0x180006304  call    cs:__imp_VariantInit
0x18000630a  nop
0x18000630b  mov     ecx, 0Ch; vt
0x180006310  mov     r8d, ebx; cElements
0x180006313  xor     edx, edx; lLbound
0x180006315  call    cs:__imp_SafeArrayCreateVector
0x18000631b  mov     r8, rax; struct tagSAFEARRAY *
0x18000631e  mov     qword ptr [rsp+210h+var_1C0+8], rax
0x180006323  mov     eax, [rbp+110h+var_D8]
0x180006326  mov     [rbp+110h+var_D8], eax
0x180006329  test    r8, r8
0x18000632c  jz      loc_1800064C5
0x180006332  mov     [rbp+110h+var_D8], 0
0x180006339  mov     word ptr [rsp+210h+var_1C0], r14w
0x18000633f  mov     [rsp+210h+rgIndices], 0
0x180006347  mov     rbx, [rdi+40h]
0x18000634b  mov     r14d, 8
0x180006351  cmp     rbx, [rdi+48h]
0x180006355  jz      loc_18000648F
0x18000635b  lea     rcx, [rsp+210h+var_1D8]; pvarg
0x180006360  call    cs:__imp_VariantInit
0x180006366  nop
0x180006367  mov     ecx, [rbx+0D0h]
0x18000636d  sub     ecx, 3
0x180006370  jz      short loc_18000637C
0x180006372  cmp     ecx, 1
0x180006375  jz      short loc_1800063CA
0x180006377  jmp     loc_180006473
0x18000637c  lea     rcx, [rbx+0A8h]
0x180006383  cmp     [rcx+18h], r14
0x180006387  jb      short loc_18000638C
0x180006389  mov     rcx, [rcx]; psz
0x18000638c  test    rcx, rcx
0x18000638f  jnz     short loc_18000639A
0x180006391  mov     [rsp+210h+pExceptionObject], rcx
0x180006396  xor     eax, eax
0x180006398  jmp     short loc_1800063AE
0x18000639a  call    cs:__imp_SysAllocString
0x1800063a0  mov     [rsp+210h+pExceptionObject], rax
0x1800063a5  test    rax, rax
0x1800063a8  jz      loc_18000659B
0x1800063ae  mov     [rsp+210h+pExceptionObject], 0
0x1800063b7  mov     qword ptr [rsp+210h+var_1D8+8], rax
0x1800063bc  xor     ecx, ecx; bstrString
0x1800063be  call    cs:__imp_SysFreeString
0x1800063c4  mov     word ptr [rsp+210h+var_1D8], r14w
0x1800063ca  lea     rcx, [rbp+110h+pv]; pvarg
0x1800063ce  call    cs:__imp_VariantInit
0x1800063d4  nop
0x1800063d5  cmp     [rbx+18h], r14
0x1800063d9  jb      short loc_1800063E0
0x1800063db  mov     rcx, [rbx]
0x1800063de  jmp     short loc_1800063E3
0x1800063e0  mov     rcx, rbx; psz
0x1800063e3  test    rcx, rcx
0x1800063e6  jnz     short loc_1800063F1
0x1800063e8  mov     [rsp+210h+var_1E0], rcx
0x1800063ed  xor     eax, eax
0x1800063ef  jmp     short loc_180006405
0x1800063f1  call    cs:__imp_SysAllocString
0x1800063f7  mov     [rsp+210h+var_1E0], rax
0x1800063fc  test    rax, rax
0x1800063ff  jz      loc_180006581
0x180006405  mov     [rsp+210h+var_1E0], 0
0x18000640e  mov     qword ptr [rbp+110h+pv+8], rax
0x180006412  xor     ecx, ecx; bstrString
0x180006414  call    cs:__imp_SysFreeString
0x18000641a  mov     word ptr [rbp+110h+pv], r14w
0x18000641f  lea     r8, [rbp+110h+pv]; pv
0x180006423  lea     rdx, [rsp+210h+rgIndices]; rgIndices
0x180006428  mov     rcx, qword ptr [rsp+210h+pvarg+8]; psa
0x18000642d  call    cs:__imp_SafeArrayPutElement
0x180006433  mov     [rbp+110h+var_D8], eax
0x180006436  test    eax, eax
0x180006438  js      loc_18000654F
0x18000643e  mov     [rbp+110h+var_D8], eax
0x180006441  lea     r8, [rsp+210h+var_1D8]; pv
0x180006446  lea     rdx, [rsp+210h+rgIndices]; rgIndices
0x18000644b  mov     rcx, qword ptr [rsp+210h+var_1C0+8]; psa
0x180006450  call    cs:__imp_SafeArrayPutElement
0x180006456  mov     [rbp+110h+var_D8], eax
0x180006459  test    eax, eax
0x18000645b  js      loc_18000651D
0x180006461  mov     [rbp+110h+var_D8], eax
0x180006464  inc     [rsp+210h+rgIndices]
0x180006468  lea     rcx, [rbp+110h+pv]; pvarg
0x18000646c  call    cs:__imp_VariantClear
0x180006472  nop
0x180006473  lea     rcx, [rsp+210h+var_1D8]; pvarg
0x180006478  call    cs:__imp_VariantClear
0x18000647e  add     rbx, 0E0h
0x180006485  mov     r8, qword ptr [rsp+210h+var_1C0+8]
0x18000648a  jmp     loc_180006351
0x18000648f  mov     rdx, qword ptr [rsp+210h+pvarg+8]; psa
0x180006494  mov     rcx, rdi; this
0x180006497  call    ?InvokeClassifier@CFciPropertiesShellExt@@AEAAXPEAUtagSAFEARRAY@@0@Z; CFciPropertiesShellExt::InvokeClassifier(tagSAFEARRAY *,tagSAFEARRAY *)
0x18000649c  nop
0x18000649d  lea     rcx, [rsp+210h+var_1C0]; pvarg
0x1800064a2  call    cs:__imp_VariantClear
0x1800064a8  nop
0x1800064a9  lea     rcx, [rsp+210h+pvarg]; pvarg
0x1800064ae  call    cs:__imp_VariantClear
0x1800064b4  nop
0x1800064b5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800064bc  mov     [rbp+110h+var_E0], rax
0x1800064c0  jmp     loc_180006297
0x1800064c5  mov     edx, 8007000Eh; int
0x1800064ca  lea     rcx, [rbp+110h+var_E0]; this
0x1800064ce  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800064d3  lea     rcx, [rbp+110h+var_E0]; this
0x1800064d7  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800064dc  mov     r8d, eax; char
0x1800064df  xor     r9d, r9d; unsigned __int16 *
0x1800064e2  mov     edx, 562h; unsigned int
0x1800064e7  lea     rcx, [rbp+110h+var_E0]; this
0x1800064eb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800064f1  mov     edx, 8007000Eh; int
0x1800064f6  lea     rcx, [rbp+110h+var_E0]; this
0x1800064fa  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800064ff  lea     rcx, [rbp+110h+var_E0]; this
0x180006503  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180006508  mov     r8d, eax; char
0x18000650b  xor     r9d, r9d; unsigned __int16 *
0x18000650e  mov     edx, 55Dh; unsigned int
0x180006513  lea     rcx, [rbp+110h+var_E0]; this
0x180006517  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000651d  lea     rcx, [rbp+110h+var_E0]; this
0x180006521  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180006526  mov     edx, eax; int
0x180006528  lea     rcx, [rbp+110h+var_E0]; this
0x18000652c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180006531  lea     rcx, [rbp+110h+var_E0]; this
0x180006535  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000653a  mov     r8d, eax; char
0x18000653d  xor     r9d, r9d; unsigned __int16 *
0x180006540  mov     edx, 585h; unsigned int
0x180006545  lea     rcx, [rbp+110h+var_E0]; this
0x180006549  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000654f  lea     rcx, [rbp+110h+var_E0]; this
0x180006553  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180006558  mov     edx, eax; int
0x18000655a  lea     rcx, [rbp+110h+var_E0]; this
0x18000655e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180006563  lea     rcx, [rbp+110h+var_E0]; this
0x180006567  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000656c  mov     r8d, eax; char
0x18000656f  xor     r9d, r9d; unsigned __int16 *
0x180006572  mov     edx, 584h; unsigned int
0x180006577  lea     rcx, [rbp+110h+var_E0]; this
0x18000657b  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180006581  mov     dword ptr [rsp+210h+pExceptionObject], 8007000Eh
0x180006589  lea     rdx, _TI1J; pThrowInfo
0x180006590  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180006595  call    _CxxThrowException_0
0x18000659b  mov     dword ptr [rsp+210h+pExceptionObject], 8007000Eh
0x1800065a3  lea     rdx, _TI1J; pThrowInfo
0x1800065aa  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x1800065af  call    _CxxThrowException_0
```
