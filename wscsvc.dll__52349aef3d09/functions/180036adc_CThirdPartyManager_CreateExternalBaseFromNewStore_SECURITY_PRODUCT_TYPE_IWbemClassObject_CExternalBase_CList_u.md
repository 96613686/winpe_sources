# CThirdPartyManager::CreateExternalBaseFromNewStore(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)

- ea: `0x180036adc`
- end: `0x1800371e6`
- name: `?CreateExternalBaseFromNewStore@CThirdPartyManager@@IEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z`
- size: `1802`
- prototype: `__int64 __fastcall(CSecurityVerificationManager **this, unsigned int, __int64 *, CExternalBase **, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800371ec`

## callees

- `0x180005710`
- `0x1800080c0`
- `0x180008910`
- `0x180008b80`
- `0x180008cc0`
- `0x180008e48`
- `0x180009390`
- `0x180015bf0`
- `0x180016120`
- `0x1800191c0`
- `0x18001b7f0`
- `0x18001c4c0`
- `0x18001fa14`
- `0x1800202e8`
- `0x180023a0c`
- `0x180029158`
- `0x180036adc`
- `0x1800378c0`
- `0x180037a0c`
- `0x180039474`
- `0x180039614`
- `0x18003e88c`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180036b2f`
- `OLEAUT32!__imp_VariantInit` at `0x180036b49`
- `OLEAUT32!__imp_VariantInit` at `0x180036b60`
- `OLEAUT32!__imp_VariantInit` at `0x180036b77`
- `OLEAUT32!__imp_VariantInit` at `0x180036b8e`
- `OLEAUT32!__imp_VariantInit` at `0x180036ba5`
- `OLEAUT32!__imp_VariantInit` at `0x180036b2f`
- `OLEAUT32!__imp_VariantInit` at `0x180036b49`
- `OLEAUT32!__imp_VariantInit` at `0x180036b60`
- `OLEAUT32!__imp_VariantInit` at `0x180036b77`
- `OLEAUT32!__imp_VariantInit` at `0x180036b8e`
- `OLEAUT32!__imp_VariantInit` at `0x180036ba5`
- `OLEAUT32!__imp_VariantClear` at `0x180037190`
- `OLEAUT32!__imp_VariantClear` at `0x18003719a`
- `OLEAUT32!__imp_VariantClear` at `0x1800371a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800371af`
- `OLEAUT32!__imp_VariantClear` at `0x1800371b9`
- `OLEAUT32!__imp_VariantClear` at `0x1800371c3`
- `OLEAUT32!__imp_VariantClear` at `0x180037190`
- `OLEAUT32!__imp_VariantClear` at `0x18003719a`
- `OLEAUT32!__imp_VariantClear` at `0x1800371a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800371af`
- `OLEAUT32!__imp_VariantClear` at `0x1800371b9`
- `OLEAUT32!__imp_VariantClear` at `0x1800371c3`

## string_xrefs

- `0x180036e19`: `pathToSignedProductExe`
- `0x180036ca5`: `pathToSignedReportingExe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThirdPartyManager::CreateExternalBaseFromNewStore(
        CSecurityVerificationManager **this,
        unsigned int a2,
        __int64 *a3,
        CExternalBase **a4,
        __int64 a5)
{
  __int64 v9; // rax
  int v10; // eax
  int v11; // ebx
  CThirdPartyManager *v12; // rcx
  __int64 v13; // rdx
  CSecurityVerificationManager *v14; // rax
  unsigned __int16 *v15; // rax
  LONGLONG v16; // r8
  int v17; // r9d
  int v18; // edx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rcx
  LONGLONG v21; // r8
  int v22; // eax
  int v23; // edx
  const unsigned __int16 *bstrVal; // rdx
  __int64 v25; // r9
  int v26; // edx
  CExternalBase *v27; // rdi
  CWmiEventManager *v28; // rcx
  struct IWbemServices *v29; // rsi
  unsigned int v30; // esi
  CExternalBase *v31; // rcx
  int ProductNotification; // eax
  CExternalBase *v33; // rcx
  __int64 v34; // r8
  CWmiEventManager *v35; // rcx
  int v36; // edx
  struct IWbemServices *v37; // rsi
  int updated; // eax
  int v39; // r14d
  unsigned int ProductState; // eax
  int v41; // eax
  CExternalBase *v43; // [rsp+40h] [rbp-A1h] BYREF
  VARIANTARG v44; // [rsp+48h] [rbp-99h] BYREF
  CExternalBase *v45; // [rsp+60h] [rbp-81h] BYREF
  struct CExternalBase *v46; // [rsp+68h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-71h] BYREF
  VARIANTARG v48; // [rsp+88h] [rbp-59h] BYREF
  VARIANTARG v49; // [rsp+A0h] [rbp-41h] BYREF
  VARIANTARG v50; // [rsp+B8h] [rbp-29h] BYREF
  VARIANTARG v51; // [rsp+D0h] [rbp-11h] BYREF
  struct IWbemServices *v52; // [rsp+150h] [rbp+6Fh] BYREF

  if ( a3 && a4 )
  {
    v43 = 0;
    v46 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    memset(&v44, 0, sizeof(v44));
    VariantInit(&v44);
    memset(&v51, 0, sizeof(v51));
    VariantInit(&v51);
    memset(&v48, 0, sizeof(v48));
    VariantInit(&v48);
    memset(&v49, 0, sizeof(v49));
    VariantInit(&v49);
    memset(&v50, 0, sizeof(v50));
    VariantInit(&v50);
    v44.llVal = (LONGLONG)&qword_180045B70;
    v9 = *a3;
    LODWORD(v52) = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(v9 + 32))(
            a3,
            L"instanceGuid",
            0,
            &pvarg,
            0,
            0);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_59;
      }
      v13 = 25;
      goto LABEL_57;
    }
    v14 = *this;
    v45 = 0;
    if ( (*((int (__fastcall **)(CSecurityVerificationManager **, CExternalBase **))v14 + 1))(this, &v45) >= 0 )
    {
      v15 = (unsigned __int16 *)*((_QWORD *)v45 + 1);
      v16 = pvarg.llVal - (_QWORD)v15;
      do
      {
        v17 = *(unsigned __int16 *)((char *)v15 + v16);
        v18 = *v15 - v17;
        if ( v18 )
          break;
        ++v15;
      }
      while ( v17 );
      if ( v18 )
      {
        if ( v45 )
          (**(void (__fastcall ***)(CExternalBase *, __int64))v45)(v45, 1);
      }
      else
      {
        v43 = v45;
      }
    }
    if ( !v43 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
              a3,
              L"pathToSignedReportingExe",
              0,
              &v44,
              0,
              0);
      v11 = v10;
      if ( v10 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_59;
        }
        v13 = 26;
        goto LABEL_57;
      }
      if ( v44.vt != 1 )
      {
        v11 = CThirdPartyManager::ProductMatchesRemovedProduct(v19, v44.llVal, a5, &v52);
        if ( v11 < 0 )
        {
LABEL_59:
          EvtLog_LogErrorInvalidWmiInstanceId(pvarg.bstrVal, v44.bstrVal);
          CThirdPartyManager::CreateExternalBase((CThirdPartyManager *)this, pvarg.bstrVal, 0, 0, 0, 0, &v46);
          v27 = v46;
          if ( v46 )
          {
            v28 = this[9];
            v52 = 0;
            if ( (int)CWmiEventManager::GetWbemServices(v28, v26, &v52) >= 0 )
            {
              v29 = v52;
              if ( v52 )
              {
                CExternalBase::RemoveFromPersistentStore(v27, v52, (enum _SECURITY_PRODUCT_TYPE)a2);
                ((void (__fastcall *)(struct IWbemServices *))v29->lpVtbl->Release)(v29);
              }
            }
            if ( v27 )
              (**(void (__fastcall ***)(CExternalBase *, __int64))v27)(v27, 1);
          }
          if ( v43 )
            (**(void (__fastcall ***)(CExternalBase *, __int64))v43)(v43, 1);
          goto LABEL_85;
        }
        if ( (_DWORD)v52 )
        {
          *((_DWORD *)this + 21) = 1;
          EvtLog_LogInformational(0x4000000Du);
          v11 = -2147024894;
          goto LABEL_59;
        }
        v11 = CSecurityVerificationManager::CreateExternalBaseFromPESettings(this[8], v44.bstrVal, &v43);
        if ( v11 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_59;
          }
          v13 = 27;
          v25 = (unsigned int)v11;
          goto LABEL_58;
        }
        v20 = (unsigned __int16 *)*((_QWORD *)v43 + 1);
        v21 = pvarg.llVal - (_QWORD)v20;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v20 + v21);
          v23 = *v20 - v22;
          if ( v23 )
            break;
          ++v20;
        }
        while ( v22 );
        if ( v23 )
          v11 = -2147024883;
        if ( v11 < 0 )
          goto LABEL_59;
        v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
                a3,
                L"displayName",
                0,
                &v49,
                0,
                0);
        v11 = v10;
        if ( v10 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_59;
          }
          v13 = 29;
LABEL_57:
          v25 = (unsigned int)v10;
LABEL_58:
          WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, v25);
          goto LABEL_59;
        }
        if ( v49.vt == 1 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
          }
          v11 = -2147467259;
        }
        else
        {
          v11 = CExternalBase::SetDisplayName(v43, v49.bstrVal);
        }
        if ( v11 < 0 )
          goto LABEL_59;
        if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
               a3,
               L"pathToSignedProductExe",
               0,
               &v48,
               0,
               0) >= 0
          && v48.vt != 1 )
        {
          CExternalBase::SetPath(v43, v48.bstrVal);
        }
        if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
               a3,
               L"timestamp",
               0,
               &v50,
               0,
               0) < 0
          || v50.vt == 1 )
        {
          bstrVal = 0;
        }
        else
        {
          bstrVal = v50.bstrVal;
        }
        CExternalBase::SetTimestamp(v43, bstrVal);
      }
    }
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
            a3,
            L"productState",
            0,
            &v51,
            0,
            0);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_59;
      }
      v13 = 30;
      goto LABEL_57;
    }
    if ( v51.vt != 1 )
    {
      v30 = v51.lVal | 0x40000;
      *((_DWORD *)v43 + 20) ^= ((v51.lVal | 0x40000) ^ *((_DWORD *)v43 + 20)) & 0xF0000;
      v31 = v43;
      *((_DWORD *)v43 + 20) &= 0xFFFFFF0F;
      *((_DWORD *)v31 + 20) |= v30 & 0x10;
      ProductNotification = ExtractProductNotification(v30);
      v33 = v43;
      *((_DWORD *)v43 + 20) &= 0xFF0FFFFF;
      *((_DWORD *)v33 + 20) |= ProductNotification;
      if ( *((_DWORD *)this + 20) && (unsigned int)ExtractProductState(v30) == 4096 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
            *((_QWORD *)v43 + 1));
        }
        CExternalBase::SetProductState(v43, 0, v34);
        v35 = this[9];
        v52 = 0;
        if ( (int)CWmiEventManager::GetWbemServices(v35, v36, &v52) < 0 )
          goto LABEL_83;
        v37 = v52;
        if ( !v52 )
          goto LABEL_83;
        updated = CExternalBase::UpdatePersistentStore(v43, v52, a2, 4);
        v39 = updated;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, (_DWORD)v43, a2, *((_QWORD *)v43 + 1), updated);
        }
        ((void (__fastcall *)(struct IWbemServices *))v37->lpVtbl->Release)(v37);
      }
      else
      {
        ProductState = ExtractProductState(v30);
        CExternalBase::SetProductStateEx(v43, ProductState);
        v41 = CExternalBase::UpdatePersistentStoreRegistry((__int64)v43, a2, 4);
        v39 = v41;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, *((_QWORD *)v43 + 1), a2, *((_QWORD *)v43 + 1), v41);
        }
      }
      if ( v39 >= 0 )
LABEL_83:
        WscMigrationComplete((enum _SECURITY_PRODUCT_TYPE)a2);
    }
    *a4 = v43;
LABEL_85:
    VariantClear(&v48);
    VariantClear(&v49);
    VariantClear(&pvarg);
    VariantClear(&v44);
    VariantClear(&v50);
    VariantClear(&v51);
    return (unsigned int)v11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180036adc  push    rbp
0x180036ade  push    rbx
0x180036adf  push    rsi
0x180036ae0  push    rdi
0x180036ae1  push    r12
0x180036ae3  push    r13
0x180036ae5  push    r14
0x180036ae7  push    r15
0x180036ae9  lea     rbp, [rsp-17h]
0x180036aee  sub     rsp, 0F8h
0x180036af5  xor     edi, edi
0x180036af7  mov     r13, r9
0x180036afa  mov     rsi, r8
0x180036afd  mov     r12d, edx
0x180036b00  mov     r15, rcx
0x180036b03  test    r8, r8
0x180036b06  jz      loc_1800371CD
0x180036b0c  test    r9, r9
0x180036b0f  jz      loc_1800371CD
0x180036b15  xorps   xmm0, xmm0
0x180036b18  mov     [rsp+130h+var_F0], rdi
0x180036b1d  xor     eax, eax
0x180036b1f  mov     [rbp+4Fh+var_C8], rdi
0x180036b23  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180036b27  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180036b2b  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180036b2f  call    cs:__imp_VariantInit
0x180036b35  xorps   xmm0, xmm0
0x180036b38  lea     rcx, [rsp+130h+var_E8]; pvarg
0x180036b3d  xor     eax, eax
0x180036b3f  movups  xmmword ptr [rsp+130h+var_E8], xmm0
0x180036b44  mov     qword ptr [rsp+130h+var_E8+10h], rax
0x180036b49  call    cs:__imp_VariantInit
0x180036b4f  xorps   xmm0, xmm0
0x180036b52  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x180036b56  xor     eax, eax
0x180036b58  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180036b5c  mov     qword ptr [rbp+4Fh+var_60+10h], rax
0x180036b60  call    cs:__imp_VariantInit
0x180036b66  xorps   xmm0, xmm0
0x180036b69  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x180036b6d  xor     eax, eax
0x180036b6f  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x180036b73  mov     qword ptr [rbp+4Fh+var_A8+10h], rax
0x180036b77  call    cs:__imp_VariantInit
0x180036b7d  xorps   xmm0, xmm0
0x180036b80  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180036b84  xor     eax, eax
0x180036b86  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x180036b8a  mov     qword ptr [rbp+4Fh+var_90+10h], rax
0x180036b8e  call    cs:__imp_VariantInit
0x180036b94  xorps   xmm0, xmm0
0x180036b97  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x180036b9b  xor     eax, eax
0x180036b9d  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180036ba1  mov     qword ptr [rbp+4Fh+var_78+10h], rax
0x180036ba5  call    cs:__imp_VariantInit
0x180036bab  lea     rax, qword_180045B70
0x180036bb2  mov     qword ptr [rsp+130h+var_108], rdi
0x180036bb7  mov     qword ptr [rsp+130h+var_E8+8], rax
0x180036bbc  lea     r9, [rbp+4Fh+pvarg]
0x180036bc0  mov     rax, [rsi]
0x180036bc3  lea     rdx, aInstanceguid; "instanceGuid"
0x180036bca  xor     r8d, r8d
0x180036bcd  mov     dword ptr [rbp+4Fh+arg_10], edi
0x180036bd0  mov     rcx, rsi
0x180036bd3  mov     [rsp+130h+var_110], rdi
0x180036bd8  mov     rax, [rax+20h]
0x180036bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036be1  lea     r14d, [rdi+1]
0x180036be5  mov     ebx, eax
0x180036be7  test    eax, eax
0x180036be9  jns     short loc_180036C1C
0x180036beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bf2  lea     rdi, WPP_GLOBAL_Control
0x180036bf9  cmp     rcx, rdi
0x180036bfc  jz      loc_180036F33
0x180036c02  test    [rcx+1Ch], r14b
0x180036c06  jz      loc_180036F33
0x180036c0c  lea     edx, [r14+18h]
0x180036c10  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180036c17  jmp     loc_180036F27
0x180036c1c  mov     rax, [r15]
0x180036c1f  lea     rdx, [rsp+130h+var_D0]
0x180036c24  mov     rcx, r15
0x180036c27  mov     [rsp+130h+var_D0], rdi
0x180036c2c  mov     rax, [rax+8]
0x180036c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c35  test    eax, eax
0x180036c37  js      short loc_180036C7D
0x180036c39  mov     rcx, [rsp+130h+var_D0]
0x180036c3e  mov     r8, qword ptr [rbp+4Fh+pvarg+8]
0x180036c42  mov     rax, [rcx+8]
0x180036c46  sub     r8, rax
0x180036c49  movzx   edx, word ptr [rax]
0x180036c4c  movzx   r9d, word ptr [rax+r8]
0x180036c51  sub     edx, r9d
0x180036c54  jnz     short loc_180036C5F
0x180036c56  add     rax, 2
0x180036c5a  test    r9d, r9d
0x180036c5d  jnz     short loc_180036C49
0x180036c5f  test    edx, edx
0x180036c61  jnz     short loc_180036C6A
0x180036c63  mov     [rsp+130h+var_F0], rcx
0x180036c68  jmp     short loc_180036C7D
0x180036c6a  test    rcx, rcx
0x180036c6d  jz      short loc_180036C7D
0x180036c6f  mov     rax, [rcx]
0x180036c72  mov     edx, r14d
0x180036c75  mov     rax, [rax]
0x180036c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c7d  xor     ebx, ebx
0x180036c7f  lea     rdi, WPP_GLOBAL_Control
0x180036c86  lea     r14, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180036c8d  cmp     [rsp+130h+var_F0], rbx
0x180036c92  jnz     loc_180036EDC
0x180036c98  mov     rax, [rsi]
0x180036c9b  lea     r9, [rsp+130h+var_E8]
0x180036ca0  mov     qword ptr [rsp+130h+var_108], rbx
0x180036ca5  lea     rdx, aPathtosignedre_0; "pathToSignedReportingExe"
0x180036cac  xor     r8d, r8d
0x180036caf  mov     [rsp+130h+var_110], rbx
0x180036cb4  mov     rcx, rsi
0x180036cb7  mov     rax, [rax+20h]
0x180036cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cc0  mov     ebx, eax
0x180036cc2  test    eax, eax
0x180036cc4  jns     short loc_180036CEA
0x180036cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ccd  cmp     rcx, rdi
0x180036cd0  jz      loc_180036F33
0x180036cd6  test    byte ptr [rcx+1Ch], 1
0x180036cda  jz      loc_180036F33
0x180036ce0  mov     edx, 1Ah
0x180036ce5  jmp     loc_180036F24
0x180036cea  mov     eax, 1
0x180036cef  cmp     word ptr [rsp+130h+var_E8], ax
0x180036cf4  jz      loc_180036EDA
0x180036cfa  mov     r8, [rbp+4Fh+arg_20]
0x180036cfe  lea     r9, [rbp+4Fh+arg_10]
0x180036d02  mov     rdx, qword ptr [rsp+130h+var_E8+8]
0x180036d07  call    ?ProductMatchesRemovedProduct@CThirdPartyManager@@QEAAJPEBGPEAV?$CList@PEAGPEAG@@AEAH@Z; CThirdPartyManager::ProductMatchesRemovedProduct(ushort const *,CList<ushort *,ushort *> *,int &)
0x180036d0c  mov     ebx, eax
0x180036d0e  test    eax, eax
0x180036d10  js      loc_180036F33
0x180036d16  cmp     dword ptr [rbp+4Fh+arg_10], 0
0x180036d1a  jz      short loc_180036D38
0x180036d1c  mov     ecx, 4000000Dh; dwEventID
0x180036d21  mov     dword ptr [r15+54h], 1
0x180036d29  call    ?EvtLog_LogInformational@@YAXK@Z; EvtLog_LogInformational(ulong)
0x180036d2e  mov     ebx, 80070002h
0x180036d33  jmp     loc_180036F33
0x180036d38  mov     rdx, qword ptr [rsp+130h+var_E8+8]; unsigned __int16 *
0x180036d3d  lea     r8, [rsp+130h+var_F0]; struct CExternalBase **
0x180036d42  mov     rcx, [r15+40h]; this
0x180036d46  call    ?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z; CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)
0x180036d4b  mov     ebx, eax
0x180036d4d  test    eax, eax
0x180036d4f  js      loc_180036EBB
0x180036d55  mov     rax, [rsp+130h+var_F0]
0x180036d5a  mov     r8, qword ptr [rbp+4Fh+pvarg+8]
0x180036d5e  mov     rcx, [rax+8]
0x180036d62  sub     r8, rcx
0x180036d65  movzx   edx, word ptr [rcx]
0x180036d68  movzx   eax, word ptr [rcx+r8]
0x180036d6d  sub     edx, eax
0x180036d6f  jnz     short loc_180036D79
0x180036d71  add     rcx, 2
0x180036d75  test    eax, eax
0x180036d77  jnz     short loc_180036D65
0x180036d79  test    edx, edx
0x180036d7b  mov     eax, 8007000Dh
0x180036d80  cmovnz  ebx, eax
0x180036d83  test    ebx, ebx
0x180036d85  js      loc_180036F33
0x180036d8b  mov     rax, [rsi]
0x180036d8e  lea     r9, [rbp+4Fh+var_90]
0x180036d92  mov     qword ptr [rsp+130h+var_108], 0
0x180036d9b  lea     rdx, aDisplayname_0; "displayName"
0x180036da2  xor     r8d, r8d
0x180036da5  mov     [rsp+130h+var_110], 0
0x180036dae  mov     rcx, rsi
0x180036db1  mov     rax, [rax+20h]
0x180036db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dba  mov     ebx, eax
0x180036dbc  test    eax, eax
0x180036dbe  js      loc_180036E9E
0x180036dc4  mov     eax, 1
0x180036dc9  cmp     word ptr [rbp+4Fh+var_90], ax
0x180036dcd  jz      short loc_180036DE1
0x180036dcf  mov     rdx, qword ptr [rbp+4Fh+var_90+8]; unsigned __int16 *
0x180036dd3  mov     rcx, [rsp+130h+var_F0]; this
0x180036dd8  call    ?SetDisplayName@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetDisplayName(ushort const *)
0x180036ddd  mov     ebx, eax
0x180036ddf  jmp     short loc_180036E08
0x180036de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180036de8  cmp     rcx, rdi
0x180036deb  jz      short loc_180036E03
0x180036ded  test    [rcx+1Ch], al
0x180036df0  jz      short loc_180036E03
0x180036df2  mov     rcx, [rcx+10h]
0x180036df6  mov     edx, 1Ch
0x180036dfb  mov     r8, r14
0x180036dfe  call    WPP_SF_
0x180036e03  mov     ebx, 80004005h
0x180036e08  test    ebx, ebx
0x180036e0a  js      loc_180036F33
0x180036e10  mov     rax, [rsi]
0x180036e13  lea     r9, [rbp+4Fh+var_A8]
0x180036e17  xor     ebx, ebx
0x180036e19  lea     rdx, aPathtosignedpr; "pathToSignedProductExe"
0x180036e20  mov     qword ptr [rsp+130h+var_108], rbx
0x180036e25  xor     r8d, r8d
0x180036e28  mov     rcx, rsi
0x180036e2b  mov     [rsp+130h+var_110], rbx
0x180036e30  mov     rax, [rax+20h]
0x180036e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e39  test    eax, eax
0x180036e3b  js      short loc_180036E54
0x180036e3d  lea     eax, [rbx+1]
0x180036e40  cmp     word ptr [rbp+4Fh+var_A8], ax
0x180036e44  jz      short loc_180036E54
0x180036e46  mov     rdx, qword ptr [rbp+4Fh+var_A8+8]; unsigned __int16 *
0x180036e4a  mov     rcx, [rsp+130h+var_F0]; this
0x180036e4f  call    ?SetPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetPath(ushort const *)
0x180036e54  mov     rax, [rsi]
0x180036e57  lea     r9, [rbp+4Fh+var_78]
0x180036e5b  mov     qword ptr [rsp+130h+var_108], rbx
0x180036e60  lea     rdx, aTimestamp; "timestamp"
0x180036e67  xor     r8d, r8d
0x180036e6a  mov     [rsp+130h+var_110], rbx
0x180036e6f  mov     rcx, rsi
0x180036e72  mov     rax, [rax+20h]
0x180036e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e7b  test    eax, eax
0x180036e7d  js      short loc_180036E9A
0x180036e7f  mov     eax, 1
0x180036e84  cmp     word ptr [rbp+4Fh+var_78], ax
0x180036e88  jz      short loc_180036E9A
0x180036e8a  mov     rdx, qword ptr [rbp+4Fh+var_78+8]; unsigned __int16 *
0x180036e8e  mov     rcx, [rsp+130h+var_F0]; this
0x180036e93  call    ?SetTimestamp@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetTimestamp(ushort const *)
0x180036e98  jmp     short loc_180036EDC
0x180036e9a  xor     edx, edx
0x180036e9c  jmp     short loc_180036E8E
0x180036e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ea5  cmp     rcx, rdi
0x180036ea8  jz      loc_180036F33
0x180036eae  test    byte ptr [rcx+1Ch], 1
0x180036eb2  jz      short loc_180036F33
0x180036eb4  mov     edx, 1Dh
0x180036eb9  jmp     short loc_180036F24
0x180036ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ec2  cmp     rcx, rdi
0x180036ec5  jz      short loc_180036F33
0x180036ec7  test    byte ptr [rcx+1Ch], 1
0x180036ecb  jz      short loc_180036F33
0x180036ecd  mov     edx, 1Bh
0x180036ed2  mov     r9d, ebx
0x180036ed5  mov     r8, r14
0x180036ed8  jmp     short loc_180036F2A
0x180036eda  xor     ebx, ebx
0x180036edc  mov     rax, [rsi]
0x180036edf  lea     r9, [rbp+4Fh+var_60]
0x180036ee3  mov     qword ptr [rsp+130h+var_108], rbx
0x180036ee8  lea     rdx, aProductstate; "productState"
0x180036eef  xor     r8d, r8d
0x180036ef2  mov     [rsp+130h+var_110], rbx
0x180036ef7  mov     rcx, rsi
0x180036efa  mov     rax, [rax+20h]
0x180036efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f03  mov     ebx, eax
0x180036f05  test    eax, eax
0x180036f07  jns     loc_180036FE8
0x180036f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f14  cmp     rcx, rdi
0x180036f17  jz      short loc_180036F33
0x180036f19  test    byte ptr [rcx+1Ch], 1
0x180036f1d  jz      short loc_180036F33
0x180036f1f  mov     edx, 1Eh
0x180036f24  mov     r8, r14
0x180036f27  mov     r9d, eax
0x180036f2a  mov     rcx, [rcx+10h]
0x180036f2e  call    WPP_SF_d
0x180036f33  mov     rdx, qword ptr [rsp+130h+var_E8+8]; unsigned __int16 *
0x180036f38  mov     rcx, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x180036f3c  call    ?EvtLog_LogErrorInvalidWmiInstanceId@@YAXPEBG0@Z; EvtLog_LogErrorInvalidWmiInstanceId(ushort const *,ushort const *)
0x180036f41  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x180036f45  lea     rax, [rbp+4Fh+var_C8]
0x180036f49  mov     [rsp+130h+var_100], rax; struct CExternalBase **
0x180036f4e  xor     r14d, r14d
0x180036f51  mov     [rsp+130h+var_108], r14d; unsigned int
0x180036f56  xor     r9d, r9d; unsigned __int16 *
0x180036f59  xor     r8d, r8d; unsigned __int16 *
0x180036f5c  mov     [rsp+130h+var_110], r14; unsigned __int16 *
0x180036f61  mov     rcx, r15; this
0x180036f64  call    ?CreateExternalBase@CThirdPartyManager@@QEAAJPEBG000KPEAPEAVCExternalBase@@@Z; CThirdPartyManager::CreateExternalBase(ushort const *,ushort const *,ushort const *,ushort const *,ulong,CExternalBase * *)
0x180036f69  mov     rdi, [rbp+4Fh+var_C8]
0x180036f6d  test    rdi, rdi
0x180036f70  jz      short loc_180036FC5
  ... truncated ...
```
