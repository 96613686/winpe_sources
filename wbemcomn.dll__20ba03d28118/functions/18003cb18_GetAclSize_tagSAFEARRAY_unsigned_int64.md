# GetAclSize(tagSAFEARRAY *,unsigned __int64 *)

- ea: `0x18003cb18`
- end: `0x18003cee1`
- name: `?GetAclSize@@YAJPEAUtagSAFEARRAY@@PEA_K@Z`
- size: `969`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e7c4`

## callees

- `0x180013564`
- `0x1800137d4`
- `0x180014120`
- `0x18001bb20`
- `0x18001c010`
- `0x180028484`
- `0x18003a648`
- `0x18003ac1c`
- `0x18003ad10`
- `0x18003c6f8`
- `0x18003cb18`
- `0x18003eff4`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003cb44`
- `OLEAUT32!__imp_VariantInit` at `0x18003cb44`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cbc3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cbc3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003cb65`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003cb65`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003cc82`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003cc82`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetAclSize(SAFEARRAY *psa, unsigned __int64 *a2)
{
  HRESULT LBound; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HRESULT UBound; // eax
  LONG i; // eax
  HRESULT Element; // eax
  struct IErrorInfo *v11; // rdx
  __int64 v12; // rax
  signed int v13; // eax
  __int64 (__fastcall *v14)(LONGLONG, GUID *, struct IWbemClassObject **); // rbx
  signed int v15; // eax
  ULONG Size; // eax
  unsigned int v17; // edx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  LONG plLbound; // [rsp+40h] [rbp-40h] BYREF
  LONG plUbound; // [rsp+44h] [rbp-3Ch] BYREF
  struct IWbemClassObject *v25; // [rsp+48h] [rbp-38h] BYREF
  CNtSid *v26; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v27; // [rsp+58h] [rbp-28h] BYREF
  CNtSid *v28; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF
  __int64 rgIndices; // [rsp+B0h] [rbp+30h] BYREF
  __int64 pv; // [rsp+B8h] [rbp+38h] BYREF

  v27 = 8;
  VariantInit(&pvarg);
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
  v5 = LBound;
  if ( LBound >= 0 )
  {
    UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
    v5 = UBound;
    if ( UBound >= 0 )
    {
      if ( plLbound <= plUbound )
      {
        rgIndices = 8;
        SafeInt<unsigned __int64>::operator*=<long>(&rgIndices);
        SafeInt<unsigned __int64>::operator+=<unsigned __int64>(&v27, rgIndices);
        for ( i = plLbound; ; i = rgIndices + 1 )
        {
          LODWORD(rgIndices) = i;
          if ( i > plUbound )
            break;
          pv = 0;
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
          pv = 0;
          Element = SafeArrayGetElement(psa, (LONG *)&rgIndices, &pv);
          v5 = Element;
          if ( Element < 0 )
          {
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, Element);
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_42;
            }
            v21 = 84;
LABEL_41:
            WPP_SF_D(v20[2], v21, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v5);
            goto LABEL_42;
          }
          v12 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
                  &pv,
                  v11);
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(
                  v12,
                  L"Trustee",
                  0,
                  &pvarg,
                  0,
                  0);
          v5 = v13;
          if ( v13 < 0 )
          {
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v13);
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_42;
            }
            v21 = 85;
            goto LABEL_41;
          }
          if ( pvarg.vt != 13 )
          {
            *a2 = 128;
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
            goto LABEL_44;
          }
          v25 = 0;
          v14 = **(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IWbemClassObject **))pvarg.llVal;
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v25);
          v25 = 0;
          v5 = v14(pvarg.llVal, &IID_IWbemClassObject, &v25);
          if ( (v5 & 0x80000000) != 0 )
          {
            _variant_t::Clear((_variant_t *)&pvarg);
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v5);
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = 86;
LABEL_30:
              WPP_SF_D(v18[2], v19, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v5);
            }
LABEL_31:
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v25);
LABEL_42:
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
            goto LABEL_45;
          }
          _variant_t::Clear((_variant_t *)&pvarg);
          v26 = 0;
          v15 = LoadSIDFromTrustee(v25, &v26);
          v5 = v15;
          if ( v15 < 0 )
          {
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v15);
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = 87;
              goto LABEL_30;
            }
            goto LABEL_31;
          }
          v28 = v26;
          Size = CNtSid::GetSize((PSID *)v26);
          SafeInt<unsigned __int64>::operator+=<unsigned __int64>(&v27, Size);
          CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v28, v17);
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v25);
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
        }
        *a2 = v27;
      }
      else
      {
        *a2 = 8;
      }
LABEL_44:
      v5 = 0;
    }
    else
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, UBound);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 83;
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        goto LABEL_11;
      }
    }
  }
  else
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, LBound);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 82;
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_11:
      WPP_SF_D(v7, v6, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v5);
    }
  }
LABEL_45:
  _variant_t::~_variant_t(&pvarg);
  return v5;
}

```

## disassembly

```asm
0x18003cb18  mov     [rsp-18h+arg_0], rbx
0x18003cb1d  mov     [rsp-18h+arg_8], rsi
0x18003cb22  push    rbp
0x18003cb23  push    rdi
0x18003cb24  push    r12
0x18003cb26  mov     rbp, rsp
0x18003cb29  sub     rsp, 80h
0x18003cb30  mov     rdi, rdx
0x18003cb33  mov     rsi, rcx
0x18003cb36  mov     r12d, 8
0x18003cb3c  mov     [rbp+var_28], r12
0x18003cb40  lea     rcx, [rbp+pvarg]; pvarg
0x18003cb44  call    cs:__imp_VariantInit
0x18003cb4a  nop
0x18003cb4b  mov     [rbp+plLbound], 0
0x18003cb52  mov     [rbp+plUbound], 0
0x18003cb59  lea     r8, [rbp+plLbound]; plLbound
0x18003cb5d  lea     edx, [r12-7]; nDim
0x18003cb62  mov     rcx, rsi; psa
0x18003cb65  call    cs:__imp_SafeArrayGetLBound
0x18003cb6b  mov     ebx, eax
0x18003cb6d  test    eax, eax
0x18003cb6f  jns     short loc_18003CBB7
0x18003cb71  mov     edx, eax; int
0x18003cb73  lea     rcx, qword_18006A9C0; this
0x18003cb7a  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cb7f  lea     rcx, WPP_GLOBAL_Control
0x18003cb86  mov     r10, cs:WPP_GLOBAL_Control
0x18003cb8d  cmp     r10, rcx
0x18003cb90  jz      loc_18003CEBE
0x18003cb96  test    byte ptr [r10+1Ch], 1
0x18003cb9b  jz      loc_18003CEBE
0x18003cba1  cmp     byte ptr [r10+19h], 2
0x18003cba6  jb      loc_18003CEBE
0x18003cbac  lea     edx, [r12+4Ah]
0x18003cbb1  mov     rcx, [r10+10h]
0x18003cbb5  jmp     short loc_18003CC11
0x18003cbb7  lea     r8, [rbp+plUbound]; plUbound
0x18003cbbb  mov     edx, 1; nDim
0x18003cbc0  mov     rcx, rsi; psa
0x18003cbc3  call    cs:__imp_SafeArrayGetUBound
0x18003cbc9  mov     ebx, eax
0x18003cbcb  test    eax, eax
0x18003cbcd  jns     short loc_18003CC25
0x18003cbcf  mov     edx, eax; int
0x18003cbd1  lea     rcx, qword_18006A9C0; this
0x18003cbd8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cbdd  lea     rcx, WPP_GLOBAL_Control
0x18003cbe4  mov     rax, cs:WPP_GLOBAL_Control
0x18003cbeb  cmp     rax, rcx
0x18003cbee  jz      loc_18003CEBE
0x18003cbf4  test    byte ptr [rax+1Ch], 1
0x18003cbf8  jz      loc_18003CEBE
0x18003cbfe  cmp     byte ptr [rax+19h], 2
0x18003cc02  jb      loc_18003CEBE
0x18003cc08  mov     edx, 53h ; 'S'
0x18003cc0d  mov     rcx, [rax+10h]
0x18003cc11  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003cc18  mov     r9d, ebx
0x18003cc1b  call    WPP_SF_D
0x18003cc20  jmp     loc_18003CEBE
0x18003cc25  mov     edx, [rbp+plUbound]
0x18003cc28  cmp     [rbp+plLbound], edx
0x18003cc2b  jle     short loc_18003CC35
0x18003cc2d  mov     [rdi], r12
0x18003cc30  jmp     loc_18003CEBC
0x18003cc35  mov     [rbp+rgIndices], r12
0x18003cc39  lea     rcx, [rbp+rgIndices]
0x18003cc3d  call    ??$?XJ@?$SafeInt@_K@@QEAAAEAV0@J@Z; SafeInt<unsigned __int64>::operator*=<long>(long)
0x18003cc42  mov     rdx, [rbp+rgIndices]
0x18003cc46  lea     rcx, [rbp+var_28]
0x18003cc4a  call    ??$?Y_K@?$SafeInt@_K@@QEAAAEAV0@_K@Z; SafeInt<unsigned __int64>::operator+=<unsigned __int64>(unsigned __int64)
0x18003cc4f  mov     eax, [rbp+plLbound]
0x18003cc52  mov     dword ptr [rbp+rgIndices], eax
0x18003cc55  cmp     eax, [rbp+plUbound]
0x18003cc58  jg      loc_18003CEB5
0x18003cc5e  mov     [rbp+pv], 0
0x18003cc66  lea     rcx, [rbp+pv]
0x18003cc6a  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003cc6f  mov     [rbp+pv], 0
0x18003cc77  lea     r8, [rbp+pv]; pv
0x18003cc7b  lea     rdx, [rbp+rgIndices]; rgIndices
0x18003cc7f  mov     rcx, rsi; psa
0x18003cc82  call    cs:__imp_SafeArrayGetElement
0x18003cc88  mov     ebx, eax
0x18003cc8a  test    eax, eax
0x18003cc8c  js      loc_18003CE64
0x18003cc92  lea     rcx, [rbp+pv]
0x18003cc96  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003cc9b  mov     r10, rax
0x18003cc9e  mov     rcx, [rax]
0x18003cca1  mov     rax, [rcx+20h]
0x18003cca5  mov     [rsp+80h+var_58], 0
0x18003ccae  mov     [rsp+80h+var_60], 0
0x18003ccb7  lea     r9, [rbp+pvarg]
0x18003ccbb  xor     r8d, r8d
0x18003ccbe  lea     rdx, aTrustee_0; "Trustee"
0x18003ccc5  mov     rcx, r10
0x18003ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cccd  mov     ebx, eax
0x18003cccf  test    eax, eax
0x18003ccd1  js      loc_18003CE30
0x18003ccd7  cmp     word ptr [rbp+pvarg], 0Dh
0x18003ccdc  jnz     loc_18003CE1B
0x18003cce2  mov     [rbp+var_38], 0
0x18003ccea  mov     rax, qword ptr [rbp+pvarg+8]
0x18003ccee  mov     rcx, [rax]
0x18003ccf1  mov     rbx, [rcx]
0x18003ccf4  lea     rcx, [rbp+var_38]
0x18003ccf8  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ccfd  mov     [rbp+var_38], 0
0x18003cd05  lea     r8, [rbp+var_38]
0x18003cd09  lea     rdx, IID_IWbemClassObject
0x18003cd10  mov     rcx, qword ptr [rbp+pvarg+8]
0x18003cd14  mov     rax, rbx
0x18003cd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd1c  mov     ebx, eax
0x18003cd1e  lea     rcx, [rbp+pvarg]; this
0x18003cd22  test    eax, eax
0x18003cd24  js      loc_18003CDC2
0x18003cd2a  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003cd2f  mov     [rbp+var_30], 0
0x18003cd37  lea     rdx, [rbp+var_30]; struct CNtSid **
0x18003cd3b  mov     rcx, [rbp+var_38]; struct IWbemClassObject *
0x18003cd3f  call    ?LoadSIDFromTrustee@@YAJPEAUIWbemClassObject@@PEAPEAVCNtSid@@@Z; LoadSIDFromTrustee(IWbemClassObject *,CNtSid * *)
0x18003cd44  mov     ebx, eax
0x18003cd46  test    eax, eax
0x18003cd48  js      short loc_18003CD8E
0x18003cd4a  mov     rax, [rbp+var_30]
0x18003cd4e  mov     [rbp+var_20], rax
0x18003cd52  mov     rcx, [rbp+var_30]; this
0x18003cd56  call    ?GetSize@CNtSid@@QEAAKXZ; CNtSid::GetSize(void)
0x18003cd5b  mov     edx, eax
0x18003cd5d  lea     rcx, [rbp+var_28]
0x18003cd61  call    ??$?Y_K@?$SafeInt@_K@@QEAAAEAV0@_K@Z; SafeInt<unsigned __int64>::operator+=<unsigned __int64>(unsigned __int64)
0x18003cd66  nop
0x18003cd67  lea     rcx, [rbp+var_20]
0x18003cd6b  call    ??1?$CDeleteMe@VCNtSid@@@@QEAA@XZ; CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(void)
0x18003cd70  nop
0x18003cd71  lea     rcx, [rbp+var_38]
0x18003cd75  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003cd7a  nop
0x18003cd7b  lea     rcx, [rbp+pv]
0x18003cd7f  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003cd84  mov     eax, dword ptr [rbp+rgIndices]
0x18003cd87  inc     eax
0x18003cd89  jmp     loc_18003CC52
0x18003cd8e  mov     edx, ebx; int
0x18003cd90  lea     rcx, qword_18006A9C0; this
0x18003cd97  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cd9c  lea     rcx, WPP_GLOBAL_Control
0x18003cda3  mov     rax, cs:WPP_GLOBAL_Control
0x18003cdaa  cmp     rax, rcx
0x18003cdad  jz      short loc_18003CE0D
0x18003cdaf  test    byte ptr [rax+1Ch], 1
0x18003cdb3  jz      short loc_18003CE0D
0x18003cdb5  cmp     byte ptr [rax+19h], 2
0x18003cdb9  jb      short loc_18003CE0D
0x18003cdbb  mov     edx, 57h ; 'W'
0x18003cdc0  jmp     short loc_18003CDF9
0x18003cdc2  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003cdc7  mov     edx, ebx; int
0x18003cdc9  lea     rcx, qword_18006A9C0; this
0x18003cdd0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cdd5  lea     rcx, WPP_GLOBAL_Control
0x18003cddc  mov     rax, cs:WPP_GLOBAL_Control
0x18003cde3  cmp     rax, rcx
0x18003cde6  jz      short loc_18003CE0D
0x18003cde8  test    byte ptr [rax+1Ch], 1
0x18003cdec  jz      short loc_18003CE0D
0x18003cdee  cmp     byte ptr [rax+19h], 2
0x18003cdf2  jb      short loc_18003CE0D
0x18003cdf4  mov     edx, 56h ; 'V'
0x18003cdf9  mov     r9d, ebx
0x18003cdfc  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003ce03  mov     rcx, [rax+10h]
0x18003ce07  call    WPP_SF_D
0x18003ce0c  nop
0x18003ce0d  lea     rcx, [rbp+var_38]
0x18003ce11  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ce16  jmp     loc_18003CEAA
0x18003ce1b  mov     qword ptr [rdi], 80h
0x18003ce22  lea     rcx, [rbp+pv]
0x18003ce26  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ce2b  jmp     loc_18003CEBC
0x18003ce30  mov     edx, ebx; int
0x18003ce32  lea     rcx, qword_18006A9C0; this
0x18003ce39  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ce3e  lea     rcx, WPP_GLOBAL_Control
0x18003ce45  mov     rax, cs:WPP_GLOBAL_Control
0x18003ce4c  cmp     rax, rcx
0x18003ce4f  jz      short loc_18003CEAA
0x18003ce51  test    byte ptr [rax+1Ch], 1
0x18003ce55  jz      short loc_18003CEAA
0x18003ce57  cmp     byte ptr [rax+19h], 2
0x18003ce5b  jb      short loc_18003CEAA
0x18003ce5d  mov     edx, 55h ; 'U'
0x18003ce62  jmp     short loc_18003CE96
0x18003ce64  mov     edx, ebx; int
0x18003ce66  lea     rcx, qword_18006A9C0; this
0x18003ce6d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ce72  lea     rcx, WPP_GLOBAL_Control
0x18003ce79  mov     rax, cs:WPP_GLOBAL_Control
0x18003ce80  cmp     rax, rcx
0x18003ce83  jz      short loc_18003CEAA
0x18003ce85  test    byte ptr [rax+1Ch], 1
0x18003ce89  jz      short loc_18003CEAA
0x18003ce8b  cmp     byte ptr [rax+19h], 2
0x18003ce8f  jb      short loc_18003CEAA
0x18003ce91  mov     edx, 54h ; 'T'
0x18003ce96  mov     r9d, ebx
0x18003ce99  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003cea0  mov     rcx, [rax+10h]
0x18003cea4  call    WPP_SF_D
0x18003cea9  nop
0x18003ceaa  lea     rcx, [rbp+pv]
0x18003ceae  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ceb3  jmp     short loc_18003CEBE
0x18003ceb5  mov     rax, [rbp+var_28]
0x18003ceb9  mov     [rdi], rax
0x18003cebc  xor     ebx, ebx
0x18003cebe  lea     rcx, [rbp+pvarg]; this
0x18003cec2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003cec7  mov     eax, ebx
0x18003cec9  lea     r11, [rsp+80h+var_s0]
0x18003ced1  mov     rbx, [r11+20h]
0x18003ced5  mov     rsi, [r11+28h]
0x18003ced9  mov     rsp, r11
0x18003cedc  pop     r12
0x18003cede  pop     rdi
0x18003cedf  pop     rbp
0x18003cee0  retn
```
