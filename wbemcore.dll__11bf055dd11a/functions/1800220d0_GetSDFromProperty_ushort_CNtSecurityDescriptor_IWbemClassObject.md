# GetSDFromProperty(ushort *,CNtSecurityDescriptor *,IWbemClassObject *)

- ea: `0x1800220d0`
- end: `0x180022594`
- name: `?GetSDFromProperty@@YAJPEAGPEAVCNtSecurityDescriptor@@PEAUIWbemClassObject@@@Z`
- size: `1220`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct CNtSecurityDescriptor *, struct IWbemClassObject *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021520`
- `0x180024428`
- `0x1800bf004`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000e87c`
- `0x18000e950`
- `0x1800220d0`
- `0x180086760`
- `0x180096504`
- `0x1800da010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002216c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002216c`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18002218d`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x1800221ab`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18002218d`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x1800221ab`
- `wbemcomn!??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z` at `0x1800221a2`
- `wbemcomn!??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z` at `0x1800221a2`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x180022182`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x180022182`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x1800221da`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180022559`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x1800221da`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180022559`
- `wbemcomn!GetMemLogObject` at `0x180022213`
- `wbemcomn!GetMemLogObject` at `0x180022333`
- `wbemcomn!GetMemLogObject` at `0x180022403`
- `wbemcomn!GetMemLogObject` at `0x180022464`
- `wbemcomn!GetMemLogObject` at `0x180022504`
- `wbemcomn!GetMemLogObject` at `0x18002257d`
- `wbemcomn!GetMemLogObject` at `0x180022213`
- `wbemcomn!GetMemLogObject` at `0x180022333`
- `wbemcomn!GetMemLogObject` at `0x180022403`
- `wbemcomn!GetMemLogObject` at `0x180022464`
- `wbemcomn!GetMemLogObject` at `0x180022504`
- `wbemcomn!GetMemLogObject` at `0x18002257d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022222`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022341`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022411`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022472`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022514`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022588`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022222`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022341`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022411`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022472`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022514`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022588`
- `OLEAUT32!__imp_VariantInit` at `0x1800220f5`
- `OLEAUT32!__imp_VariantInit` at `0x1800222c9`
- `OLEAUT32!__imp_VariantInit` at `0x18002239d`
- `OLEAUT32!__imp_VariantInit` at `0x1800220f5`
- `OLEAUT32!__imp_VariantInit` at `0x1800222c9`
- `OLEAUT32!__imp_VariantInit` at `0x18002239d`
- `OLEAUT32!__imp_VariantClear` at `0x1800221ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002224d`
- `OLEAUT32!__imp_VariantClear` at `0x1800222ac`
- `OLEAUT32!__imp_VariantClear` at `0x18002237f`
- `OLEAUT32!__imp_VariantClear` at `0x18002244f`
- `OLEAUT32!__imp_VariantClear` at `0x1800221ef`
- `OLEAUT32!__imp_VariantClear` at `0x18002224d`
- `OLEAUT32!__imp_VariantClear` at `0x1800222ac`
- `OLEAUT32!__imp_VariantClear` at `0x18002237f`
- `OLEAUT32!__imp_VariantClear` at `0x18002244f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002214a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002214a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221e4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022242`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800224b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022563`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221e4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022242`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800224b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022563`

## string_xrefs

- `0x180022295`: `SetSD failed trying accessing SD property`
- `0x1800222e8`: `__PATH`
- `0x1800223b8`: `__PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetSDFromProperty(
        unsigned __int16 *a1,
        struct CNtSecurityDescriptor *a2,
        struct IWbemClassObject *a3)
{
  int v6; // eax
  char v7; // bl
  SAFEARRAY *parray; // rbx
  HRESULT v9; // edi
  HRESULT v10; // eax
  struct IErrorInfo *v11; // rdx
  CMemoryLog *v13; // rax
  HRESULT v14; // eax
  struct IErrorInfo *v15; // rdx
  unsigned int v16; // ebx
  HRESULT v17; // eax
  struct IErrorInfo *v18; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  _BYTE v24[16]; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG v26; // [rsp+68h] [rbp-18h] BYREF
  void *ppvData; // [rsp+B0h] [rbp+30h] BYREF
  SAFEARRAY *v28; // [rsp+B8h] [rbp+38h]

  VariantInit(&pvarg);
  v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
         a3,
         a1,
         0,
         &pvarg,
         0,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    VariantInit(&v26);
    ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
      a3,
      L"__PATH",
      0,
      &v26,
      0,
      0);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        v26.lVal,
        v7);
    }
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217398);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749898LL);
    }
    VariantClear(&v26);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    return 2147749898LL;
  }
  else
  {
    if ( pvarg.vt != 8209 )
    {
      VariantInit(&v26);
      ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
        a3,
        L"__PATH",
        0,
        &v26,
        0,
        0);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v26.llVal);
      }
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749896LL);
      }
      VariantClear(&v26);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      return 2147749896LL;
    }
    parray = pvarg.parray;
    ppvData = 0;
    v9 = SafeArrayAccessData(pvarg.parray, &ppvData);
    if ( v9 < 0 )
    {
      v16 = DumpErrorMsgAndReturn(-2147217400, L"SetSD failed trying accessing SD property");
      v17 = VariantClear(&pvarg);
      if ( v17 < 0 )
        _com_raise_error(v17, v18);
      return v16;
    }
    else
    {
      v28 = parray;
      if ( parray->rgsabound[0].cElements )
      {
        if ( IsValidSecurityDescriptor(ppvData) )
        {
          CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v24, ppvData);
          if ( CNtSecurityDescriptor::GetStatus((CNtSecurityDescriptor *)v24) )
          {
            v22 = GetMemLogObject();
            v9 = -2147217402;
            CMemoryLog::Write(v22, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                60,
                WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
                2147749894LL);
            }
            CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v24);
            SafeArrayUnaccessData(parray);
            _variant_t::~_variant_t((_variant_t *)&pvarg);
          }
          else
          {
            CNtSecurityDescriptor::operator=(a2, v24);
            if ( CNtSecurityDescriptor::GetStatus(a2) )
            {
              v9 = -2147217402;
              v23 = GetMemLogObject();
              CMemoryLog::Write(v23, -2147217402);
            }
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
                (unsigned int)v9);
            }
            CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v24);
            SafeArrayUnaccessData(parray);
            v10 = VariantClear(&pvarg);
            if ( v10 < 0 )
              _com_raise_error(v10, v11);
          }
          return (unsigned int)v9;
        }
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, -2147217400);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749896LL);
        }
        SafeArrayUnaccessData(parray);
        v14 = VariantClear(&pvarg);
        if ( v14 < 0 )
          _com_raise_error(v14, v15);
        return 2147749896LL;
      }
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749896LL);
      }
      SafeArrayUnaccessData(parray);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      return 2147749896LL;
    }
  }
}

```

## disassembly

```asm
0x1800220d0  mov     [rsp-18h+arg_0], rbx
0x1800220d5  mov     [rsp-18h+arg_8], rsi
0x1800220da  push    rbp
0x1800220db  push    rdi
0x1800220dc  push    r14
0x1800220de  mov     rbp, rsp
0x1800220e1  sub     rsp, 80h
0x1800220e8  mov     rdi, r8
0x1800220eb  mov     rsi, rdx
0x1800220ee  mov     rbx, rcx
0x1800220f1  lea     rcx, [rbp+pvarg]; pvarg
0x1800220f5  call    cs:__imp_VariantInit
0x1800220fb  nop
0x1800220fc  mov     rax, [rdi]
0x1800220ff  xor     r14d, r14d
0x180022102  mov     [rsp+80h+var_58], r14
0x180022107  mov     [rsp+80h+var_60], r14
0x18002210c  lea     r9, [rbp+pvarg]
0x180022110  xor     r8d, r8d
0x180022113  mov     rdx, rbx
0x180022116  mov     rcx, rdi
0x180022119  mov     rax, [rax+20h]
0x18002211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022122  mov     ebx, eax
0x180022124  test    eax, eax
0x180022126  js      loc_1800222C5
0x18002212c  mov     eax, 2011h
0x180022131  cmp     word ptr [rbp+pvarg], ax
0x180022135  jnz     loc_180022399
0x18002213b  mov     rbx, qword ptr [rbp+pvarg+8]
0x18002213f  mov     [rbp+ppvData], r14
0x180022143  lea     rdx, [rbp+ppvData]; ppvData
0x180022147  mov     rcx, rbx; psa
0x18002214a  call    cs:__imp_SafeArrayAccessData
0x180022150  mov     edi, eax
0x180022152  test    eax, eax
0x180022154  js      loc_180022295
0x18002215a  mov     [rbp+arg_18], rbx
0x18002215e  cmp     [rbx+18h], r14d
0x180022162  jz      loc_180022464
0x180022168  mov     rcx, [rbp+ppvData]; pSecurityDescriptor
0x18002216c  call    cs:__imp_IsValidSecurityDescriptor
0x180022172  test    eax, eax
0x180022174  jz      loc_180022213
0x18002217a  mov     rdx, [rbp+ppvData]
0x18002217e  lea     rcx, [rbp+var_40]
0x180022182  call    cs:__imp_??0CNtSecurityDescriptor@@QEAA@PEAX@Z; CNtSecurityDescriptor::CNtSecurityDescriptor(void *)
0x180022188  nop
0x180022189  lea     rcx, [rbp+var_40]
0x18002218d  call    cs:__imp_?GetStatus@CNtSecurityDescriptor@@QEAAKXZ; CNtSecurityDescriptor::GetStatus(void)
0x180022193  test    eax, eax
0x180022195  jnz     loc_180022504
0x18002219b  lea     rdx, [rbp+var_40]
0x18002219f  mov     rcx, rsi
0x1800221a2  call    cs:__imp_??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z; CNtSecurityDescriptor::operator=(CNtSecurityDescriptor &)
0x1800221a8  mov     rcx, rsi
0x1800221ab  call    cs:__imp_?GetStatus@CNtSecurityDescriptor@@QEAAKXZ; CNtSecurityDescriptor::GetStatus(void)
0x1800221b1  test    eax, eax
0x1800221b3  jnz     loc_180022578
0x1800221b9  lea     rsi, WPP_GLOBAL_Control
0x1800221c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221c7  cmp     rcx, rsi
0x1800221ca  jz      short loc_1800221D6
0x1800221cc  test    byte ptr [rcx+1Ch], 1
0x1800221d0  jnz     loc_18002226E
0x1800221d6  lea     rcx, [rbp+var_40]
0x1800221da  call    cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::~CNtSecurityDescriptor(void)
0x1800221e0  nop
0x1800221e1  mov     rcx, rbx; psa
0x1800221e4  call    cs:__imp_SafeArrayUnaccessData
0x1800221ea  nop
0x1800221eb  lea     rcx, [rbp+pvarg]; pvarg
0x1800221ef  call    cs:__imp_VariantClear
0x1800221f5  test    eax, eax
0x1800221f7  js      short loc_18002225E
0x1800221f9  mov     eax, edi
0x1800221fb  lea     r11, [rsp+80h+var_s0]
0x180022203  mov     rbx, [r11+20h]
0x180022207  mov     rsi, [r11+28h]
0x18002220b  mov     rsp, r11
0x18002220e  pop     r14
0x180022210  pop     rdi
0x180022211  pop     rbp
0x180022212  retn
0x180022213  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022219  nop
0x18002221a  mov     edx, 80041008h
0x18002221f  mov     rcx, rax
0x180022222  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022228  lea     rsi, WPP_GLOBAL_Control
0x18002222f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022236  cmp     rcx, rsi
0x180022239  jnz     loc_1800224D0
0x18002223f  mov     rcx, rbx; psa
0x180022242  call    cs:__imp_SafeArrayUnaccessData
0x180022248  nop
0x180022249  lea     rcx, [rbp+pvarg]; pvarg
0x18002224d  call    cs:__imp_VariantClear
0x180022253  test    eax, eax
0x180022255  js      short loc_180022266
0x180022257  mov     eax, 80041008h
0x18002225c  jmp     short loc_1800221FB
0x18002225e  mov     ecx, eax; int
0x180022260  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180022266  mov     ecx, eax; int
0x180022268  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18002226e  cmp     byte ptr [rcx+19h], 2
0x180022272  jb      loc_1800221D6
0x180022278  mov     edx, 3Dh ; '='
0x18002227d  mov     r9d, edi
0x180022280  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x180022287  mov     rcx, [rcx+10h]
0x18002228b  call    WPP_SF_d
0x180022290  jmp     loc_1800221D6
0x180022295  lea     rdx, aSetsdFailedTry; "SetSD failed trying accessing SD proper"...
0x18002229c  mov     ecx, 80041008h; int
0x1800222a1  call    ?DumpErrorMsgAndReturn@@YAJJPEBG@Z; DumpErrorMsgAndReturn(long,ushort const *)
0x1800222a6  mov     ebx, eax
0x1800222a8  lea     rcx, [rbp+pvarg]; pvarg
0x1800222ac  call    cs:__imp_VariantClear
0x1800222b2  test    eax, eax
0x1800222b4  js      short loc_1800222BD
0x1800222b6  mov     eax, ebx
0x1800222b8  jmp     loc_1800221FB
0x1800222bd  mov     ecx, eax; int
0x1800222bf  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800222c5  lea     rcx, [rbp+var_18]; pvarg
0x1800222c9  call    cs:__imp_VariantInit
0x1800222cf  nop
0x1800222d0  mov     rcx, [rdi]
0x1800222d3  mov     rax, [rcx+20h]
0x1800222d7  mov     [rsp+80h+var_58], r14
0x1800222dc  mov     [rsp+80h+var_60], r14
0x1800222e1  lea     r9, [rbp+var_18]
0x1800222e5  xor     r8d, r8d
0x1800222e8  lea     rdx, aPath; "__PATH"
0x1800222ef  mov     rcx, rdi
0x1800222f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f7  lea     rsi, WPP_GLOBAL_Control
0x1800222fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180022305  cmp     rcx, rsi
0x180022308  jz      short loc_180022333
0x18002230a  test    byte ptr [rcx+1Ch], 1
0x18002230e  jz      short loc_180022333
0x180022310  cmp     byte ptr [rcx+19h], 5
0x180022314  jb      short loc_180022333
0x180022316  mov     edx, 36h ; '6'
0x18002231b  mov     dword ptr [rsp+80h+var_60], ebx
0x18002231f  mov     r9, qword ptr [rbp+var_18+8]
0x180022323  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18002232a  mov     rcx, [rcx+10h]
0x18002232e  call    WPP_SF_SD
0x180022333  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022339  mov     edx, 8004100Ah
0x18002233e  mov     rcx, rax
0x180022341  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022347  mov     rcx, cs:WPP_GLOBAL_Control
0x18002234e  cmp     rcx, rsi
0x180022351  jz      short loc_18002237B
0x180022353  test    byte ptr [rcx+1Ch], 1
0x180022357  jz      short loc_18002237B
0x180022359  cmp     byte ptr [rcx+19h], 2
0x18002235d  jb      short loc_18002237B
0x18002235f  mov     edx, 37h ; '7'
0x180022364  mov     r9d, 8004100Ah
0x18002236a  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x180022371  mov     rcx, [rcx+10h]
0x180022375  call    WPP_SF_d
0x18002237a  nop
0x18002237b  lea     rcx, [rbp+var_18]; pvarg
0x18002237f  call    cs:__imp_VariantClear
0x180022385  nop
0x180022386  lea     rcx, [rbp+pvarg]; this
0x18002238a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002238f  mov     eax, 8004100Ah
0x180022394  jmp     loc_1800221FB
0x180022399  lea     rcx, [rbp+var_18]; pvarg
0x18002239d  call    cs:__imp_VariantInit
0x1800223a3  nop
0x1800223a4  mov     rax, [rdi]
0x1800223a7  mov     [rsp+80h+var_58], r14
0x1800223ac  mov     [rsp+80h+var_60], r14
0x1800223b1  lea     r9, [rbp+var_18]
0x1800223b5  xor     r8d, r8d
0x1800223b8  lea     rdx, aPath; "__PATH"
0x1800223bf  mov     rcx, rdi
0x1800223c2  mov     rax, [rax+20h]
0x1800223c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223cb  lea     rsi, WPP_GLOBAL_Control
0x1800223d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223d9  cmp     rcx, rsi
0x1800223dc  jz      short loc_180022403
0x1800223de  test    byte ptr [rcx+1Ch], 1
0x1800223e2  jz      short loc_180022403
0x1800223e4  cmp     byte ptr [rcx+19h], 5
0x1800223e8  jb      short loc_180022403
0x1800223ea  mov     edx, 38h ; '8'
0x1800223ef  mov     r9, qword ptr [rbp+var_18+8]
0x1800223f3  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800223fa  mov     rcx, [rcx+10h]
0x1800223fe  call    WPP_SF_S
0x180022403  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022409  mov     edx, 80041008h
0x18002240e  mov     rcx, rax
0x180022411  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022417  mov     rcx, cs:WPP_GLOBAL_Control
0x18002241e  cmp     rcx, rsi
0x180022421  jz      short loc_18002244B
0x180022423  test    byte ptr [rcx+1Ch], 1
0x180022427  jz      short loc_18002244B
0x180022429  cmp     byte ptr [rcx+19h], 2
0x18002242d  jb      short loc_18002244B
0x18002242f  mov     edx, 39h ; '9'
0x180022434  mov     r9d, 80041008h
0x18002243a  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x180022441  mov     rcx, [rcx+10h]
0x180022445  call    WPP_SF_d
0x18002244a  nop
0x18002244b  lea     rcx, [rbp+var_18]; pvarg
0x18002244f  call    cs:__imp_VariantClear
0x180022455  nop
0x180022456  lea     rcx, [rbp+pvarg]; this
0x18002245a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002245f  jmp     loc_180022257
0x180022464  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002246a  mov     edx, 80041008h
0x18002246f  mov     rcx, rax
0x180022472  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180022478  lea     rsi, WPP_GLOBAL_Control
0x18002247f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022486  cmp     rcx, rsi
0x180022489  jz      short loc_1800224B3
0x18002248b  test    byte ptr [rcx+1Ch], 1
0x18002248f  jz      short loc_1800224B3
0x180022491  cmp     byte ptr [rcx+19h], 2
0x180022495  jb      short loc_1800224B3
0x180022497  mov     edx, 3Ah ; ':'
0x18002249c  mov     r9d, 80041008h
0x1800224a2  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800224a9  mov     rcx, [rcx+10h]
0x1800224ad  call    WPP_SF_d
0x1800224b2  nop
0x1800224b3  mov     rcx, rbx; psa
0x1800224b6  call    cs:__imp_SafeArrayUnaccessData
0x1800224bc  nop
0x1800224bd  lea     rcx, [rbp+pvarg]; this
0x1800224c1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800224c6  mov     eax, 80041008h
0x1800224cb  jmp     loc_1800221FB
0x1800224d0  test    byte ptr [rcx+1Ch], 1
0x1800224d4  jz      loc_18002223F
0x1800224da  cmp     byte ptr [rcx+19h], 2
0x1800224de  jb      loc_18002223F
0x1800224e4  mov     edx, 3Bh ; ';'
0x1800224e9  mov     r9d, 80041008h
0x1800224ef  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800224f6  mov     rcx, [rcx+10h]
0x1800224fa  call    WPP_SF_d
0x1800224ff  jmp     loc_18002223F
0x180022504  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002250a  mov     edi, 80041006h
0x18002250f  mov     edx, edi
0x180022511  mov     rcx, rax
0x180022514  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002251a  lea     rsi, WPP_GLOBAL_Control
0x180022521  mov     rcx, cs:WPP_GLOBAL_Control
0x180022528  cmp     rcx, rsi
0x18002252b  jz      short loc_180022555
0x18002252d  test    byte ptr [rcx+1Ch], 1
0x180022531  jz      short loc_180022555
0x180022533  cmp     byte ptr [rcx+19h], 2
0x180022537  jb      short loc_180022555
0x180022539  mov     edx, 3Ch ; '<'
0x18002253e  mov     r9d, 80041006h
0x180022544  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18002254b  mov     rcx, [rcx+10h]
0x18002254f  call    WPP_SF_d
0x180022554  nop
0x180022555  lea     rcx, [rbp+var_40]
0x180022559  call    cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::~CNtSecurityDescriptor(void)
0x18002255f  nop
0x180022560  mov     rcx, rbx; psa
0x180022563  call    cs:__imp_SafeArrayUnaccessData
0x180022569  nop
0x18002256a  lea     rcx, [rbp+pvarg]; this
0x18002256e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180022573  jmp     loc_1800221F9
0x180022578  mov     edi, 80041006h
0x18002257d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180022583  mov     edx, edi
0x180022585  mov     rcx, rax
0x180022588  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002258e  jmp     loc_1800221B9
```
