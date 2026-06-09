# CWcnUProxySession::SendProxiedResponse(CSbMessageBuffer const *)

- ea: `0x180043b40`
- end: `0x180044182`
- name: `?SendProxiedResponse@CWcnUProxySession@@AEAAJPEBVCSbMessageBuffer@@@Z`
- size: `1602`
- prototype: `int(CWcnUProxySession *__hidden this, const struct CSbMessageBuffer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800439e0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a808`
- `0x180043208`
- `0x180043b40`
- `0x1800441f4`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180043d34`
- `OLEAUT32!__imp_SysAllocString` at `0x180043d44`
- `OLEAUT32!__imp_SysAllocString` at `0x180043d34`
- `OLEAUT32!__imp_SysAllocString` at `0x180043d44`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440f1`
- `OLEAUT32!__imp_VariantInit` at `0x180043c4a`
- `OLEAUT32!__imp_VariantInit` at `0x180043c54`
- `OLEAUT32!__imp_VariantInit` at `0x180043c5e`
- `OLEAUT32!__imp_VariantInit` at `0x180043c68`
- `OLEAUT32!__imp_VariantInit` at `0x180043c72`
- `OLEAUT32!__imp_VariantInit` at `0x180043c7c`
- `OLEAUT32!__imp_VariantInit` at `0x180043c4a`
- `OLEAUT32!__imp_VariantInit` at `0x180043c54`
- `OLEAUT32!__imp_VariantInit` at `0x180043c5e`
- `OLEAUT32!__imp_VariantInit` at `0x180043c68`
- `OLEAUT32!__imp_VariantInit` at `0x180043c72`
- `OLEAUT32!__imp_VariantInit` at `0x180043c7c`
- `OLEAUT32!__imp_VariantClear` at `0x180044050`
- `OLEAUT32!__imp_VariantClear` at `0x18004405a`
- `OLEAUT32!__imp_VariantClear` at `0x180044064`
- `OLEAUT32!__imp_VariantClear` at `0x1800440c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800440cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800440d5`
- `OLEAUT32!__imp_VariantClear` at `0x180044050`
- `OLEAUT32!__imp_VariantClear` at `0x18004405a`
- `OLEAUT32!__imp_VariantClear` at `0x180044064`
- `OLEAUT32!__imp_VariantClear` at `0x1800440c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800440cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800440d5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180043cee`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180043d24`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180043cee`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180043d24`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800440ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004410d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800440ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004410d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180043d79`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180043d79`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180043df6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180043df6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043e68`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043eb1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043efb`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043e68`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043eb1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043efb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnUProxySession::SendProxiedResponse(CWcnUProxySession *this, const struct CSbMessageBuffer *a2)
{
  void *v4; // rcx
  _QWORD *v5; // r10
  const char *Indent; // rax
  __int64 v7; // r10
  CWcnUpnpGit *v9; // rcx
  int Item; // eax
  int v11; // ebx
  OLECHAR *v12; // r12
  SAFEARRAY *v13; // r14
  SAFEARRAY *v14; // r15
  OLECHAR *v15; // r13
  _QWORD *v16; // r10
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  unsigned __int64 v19; // rdi
  BSTR v20; // rax
  __int64 *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // r10
  char v25; // r11
  const char *v26; // rax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  SAFEARRAYBOUND v30; // [rsp+40h] [rbp-99h] BYREF
  void *ppvData; // [rsp+48h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-89h] BYREF
  VARIANTARG pv; // [rsp+68h] [rbp-71h] BYREF
  VARIANTARG v34; // [rsp+80h] [rbp-59h] BYREF
  VARIANTARG v35; // [rsp+98h] [rbp-41h] BYREF
  VARIANTARG v36; // [rsp+B0h] [rbp-29h] BYREF
  VARIANTARG v37; // [rsp+C8h] [rbp-11h] BYREF
  VARIANTARG v38; // [rsp+E0h] [rbp+7h] BYREF
  LONG rgIndices; // [rsp+148h] [rbp+6Fh] BYREF
  void *v40; // [rsp+150h] [rbp+77h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+158h] [rbp+7Fh] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v36, 0, sizeof(v36));
  memset(&v37, 0, sizeof(v37));
  rgsabound = 0;
  v30 = 0;
  ppvData = 0;
  memset(&pv, 0, sizeof(pv));
  memset(&v34, 0, sizeof(v34));
  memset(&v35, 0, sizeof(v35));
  v4 = 0;
  v40 = 0;
  rgIndices = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 29, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, Indent);
    v4 = v40;
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 2u )
    {
      WPP_SF_s(v5[2], 30, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, "pOutgoingMessage");
      v4 = v40;
    }
    if ( v4 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    return 2147500035LL;
  }
  VariantInit(&pvarg);
  VariantInit(&v36);
  VariantInit(&v37);
  VariantInit(&pv);
  VariantInit(&v34);
  VariantInit(&v35);
  Item = CWcnUpnpGit::GetItem(v9, *((_DWORD *)this + 34), &GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44, &v40);
  v11 = Item;
  if ( Item < 0 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 31;
LABEL_54:
      WPP_SF_d(v16[2], v17, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, (unsigned int)Item);
      v16 = WPP_GLOBAL_Control;
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  pvarg.vt = 8204;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v13 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v18 = (_QWORD *)*((_QWORD *)a2 + 3);
  if ( v18 )
    v19 = v18[1] - *v18;
  else
    v19 = 0;
  v30.cElements = v19;
  v30.lLbound = 0;
  v14 = SafeArrayCreate(0x11u, 1u, &v30);
  v15 = SysAllocString(*((const OLECHAR **)this + 18));
  v20 = SysAllocString(L"PutWLANResponse");
  v12 = v20;
  if ( v13 && v14 && v15 && v20 )
  {
    Item = SafeArrayAccessData(v14, &ppvData);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 33;
        goto LABEL_54;
      }
LABEL_55:
      if ( v11 == -2147220970 )
      {
        if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u )
        {
          v23 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v24 + 16), 40, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v23, v25);
        }
        v11 = 0;
      }
      goto LABEL_60;
    }
    Item = CSbSafeBuffer::CopyToBuffer(a2, (unsigned __int8 *)ppvData, v19);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 34;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    Item = SafeArrayUnaccessData(v14);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 35;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    pv.vt = 8209;
    pv.llVal = (LONGLONG)v14;
    v14 = 0;
    v34.vt = 17;
    v34.bVal = 2;
    v35.vt = 8;
    v35.llVal = (LONGLONG)v15;
    v15 = 0;
    rgIndices = 0;
    Item = SafeArrayPutElement(v13, &rgIndices, &pv);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 36;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    rgIndices = 1;
    Item = SafeArrayPutElement(v13, &rgIndices, &v34);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 37;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    rgIndices = 2;
    Item = SafeArrayPutElement(v13, &rgIndices, &v35);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 38;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    rgIndices = 3;
    pvarg.vt = 8204;
    pvarg.llVal = (LONGLONG)v13;
    v13 = 0;
    if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) != 0 )
    {
      v21 = (__int64 *)*((_QWORD *)a2 + 3);
      v22 = *v21;
      if ( v21 )
        LODWORD(v21) = v21[1] - v22;
      McTemplateU0zzjhbr3_EtwEventWriteTransfer(
        (_DWORD)v21,
        (unsigned int)RawSend,
        (unsigned int)L"UPROXY",
        (_DWORD)v12,
        (__int64)a2 + 32,
        (__int16)v21,
        v22);
    }
    v38 = pvarg;
    Item = (*(__int64 (__fastcall **)(void *, OLECHAR *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v40 + 64LL))(
             v40,
             v12,
             &v38,
             &v36,
             &v37);
    v11 = Item;
    if ( Item < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 39;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
  }
  else
  {
    v11 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v27 + 16), 32, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v26);
    }
  }
LABEL_60:
  VariantClear(&pvarg);
  VariantClear(&v36);
  VariantClear(&v37);
  if ( rgIndices )
  {
    if ( rgIndices != 1 )
    {
      if ( rgIndices != 2 )
        goto LABEL_70;
      goto LABEL_69;
    }
  }
  else
  {
    VariantClear(&pv);
  }
  VariantClear(&v34);
LABEL_69:
  VariantClear(&v35);
LABEL_70:
  if ( v12 )
    SysFreeString(v12);
  if ( v15 )
    SysFreeString(v15);
  if ( v14 )
    SafeArrayDestroy(v14);
  if ( v13 )
    SafeArrayDestroy(v13);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v28 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v29 + 16), 41, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v28, v11);
  }
  if ( v40 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180043b40  mov     [rsp-8+arg_0], rbx
0x180043b45  push    rbp
0x180043b46  push    rsi
0x180043b47  push    rdi
0x180043b48  push    r12
0x180043b4a  push    r13
0x180043b4c  push    r14
0x180043b4e  push    r15
0x180043b50  lea     rbp, [rsp-27h]
0x180043b55  sub     rsp, 100h
0x180043b5c  mov     rsi, rdx
0x180043b5f  mov     r13, rcx
0x180043b62  xorps   xmm0, xmm0
0x180043b65  xor     eax, eax
0x180043b67  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x180043b6c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180043b70  xorps   xmm1, xmm1
0x180043b73  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x180043b77  mov     qword ptr [rbp+57h+var_80+10h], rax
0x180043b7b  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180043b7f  mov     qword ptr [rbp+57h+var_68+10h], rax
0x180043b83  mov     qword ptr [rbp+57h+rgsabound.cElements], rax
0x180043b87  mov     qword ptr [rsp+130h+var_F0.cElements], rax
0x180043b8c  mov     [rsp+130h+ppvData], rax
0x180043b91  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180043b95  mov     qword ptr [rbp+57h+pv+10h], rax
0x180043b99  movups  xmmword ptr [rbp+57h+var_B0], xmm1
0x180043b9d  mov     qword ptr [rbp+57h+var_B0+10h], rax
0x180043ba1  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180043ba5  mov     qword ptr [rbp+57h+var_98+10h], rax
0x180043ba9  xor     ecx, ecx
0x180043bab  mov     [rbp+57h+arg_10], rcx
0x180043baf  mov     [rbp+57h+rgIndices], ecx
0x180043bb2  lea     rdi, WPP_GLOBAL_Control
0x180043bb9  lea     r15d, [rax+1]
0x180043bbd  mov     r10, cs:WPP_GLOBAL_Control
0x180043bc4  cmp     r10, rdi
0x180043bc7  jz      short loc_180043BFA
0x180043bc9  cmp     byte ptr [r10+19h], 6
0x180043bce  jb      short loc_180043BFA
0x180043bd0  mov     ecx, r15d; int
0x180043bd3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180043bd8  lea     edx, [r15+1Ch]
0x180043bdc  mov     r9, rax
0x180043bdf  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043be6  mov     rcx, [r10+10h]
0x180043bea  call    WPP_SF_s
0x180043bef  mov     rcx, [rbp+57h+arg_10]
0x180043bf3  mov     r10, cs:WPP_GLOBAL_Control
0x180043bfa  test    rsi, rsi
0x180043bfd  jnz     short loc_180043C45
0x180043bff  cmp     r10, rdi
0x180043c02  jz      short loc_180043C29
0x180043c04  cmp     byte ptr [r10+19h], 2
0x180043c09  jb      short loc_180043C29
0x180043c0b  lea     edx, [rsi+1Eh]
0x180043c0e  lea     r9, aPoutgoingmessa; "pOutgoingMessage"
0x180043c15  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043c1c  mov     rcx, [r10+10h]
0x180043c20  call    WPP_SF_s
0x180043c25  mov     rcx, [rbp+57h+arg_10]
0x180043c29  test    rcx, rcx
0x180043c2c  jz      short loc_180043C3B
0x180043c2e  mov     rax, [rcx]
0x180043c31  mov     rax, [rax+10h]
0x180043c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c3a  nop
0x180043c3b  mov     eax, 80004003h
0x180043c40  jmp     loc_180044167
0x180043c45  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180043c4a  call    cs:__imp_VariantInit
0x180043c50  lea     rcx, [rbp+57h+var_80]; pvarg
0x180043c54  call    cs:__imp_VariantInit
0x180043c5a  lea     rcx, [rbp+57h+var_68]; pvarg
0x180043c5e  call    cs:__imp_VariantInit
0x180043c64  lea     rcx, [rbp+57h+pv]; pvarg
0x180043c68  call    cs:__imp_VariantInit
0x180043c6e  lea     rcx, [rbp+57h+var_B0]; pvarg
0x180043c72  call    cs:__imp_VariantInit
0x180043c78  lea     rcx, [rbp+57h+var_98]; pvarg
0x180043c7c  call    cs:__imp_VariantInit
0x180043c82  lea     r9, [rbp+57h+arg_10]; void **
0x180043c86  lea     r8, _GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44; struct _GUID *
0x180043c8d  mov     edx, [r13+88h]; unsigned int
0x180043c94  call    ?GetItem@CWcnUpnpGit@@QEAAJKAEBU_GUID@@PEAPEAX@Z; CWcnUpnpGit::GetItem(ulong,_GUID const &,void * *)
0x180043c99  mov     ebx, eax
0x180043c9b  test    eax, eax
0x180043c9d  jns     short loc_180043CD0
0x180043c9f  xor     r12d, r12d
0x180043ca2  xor     r14d, r14d
0x180043ca5  xor     r15d, r15d
0x180043ca8  xor     r13d, r13d
0x180043cab  mov     r10, cs:WPP_GLOBAL_Control
0x180043cb2  cmp     r10, rdi
0x180043cb5  jz      loc_180044007
0x180043cbb  cmp     byte ptr [r10+19h], 2
0x180043cc0  jb      loc_180044007
0x180043cc6  lea     edx, [r12+1Fh]
0x180043ccb  jmp     loc_180043FED
0x180043cd0  mov     eax, 200Ch
0x180043cd5  mov     word ptr [rsp+130h+pvarg], ax
0x180043cda  mov     qword ptr [rbp+57h+rgsabound.cElements], 3
0x180043ce2  mov     ecx, 0Ch; vt
0x180043ce7  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180043ceb  mov     edx, r15d; cDims
0x180043cee  call    cs:__imp_SafeArrayCreate
0x180043cf4  mov     r14, rax
0x180043cf7  mov     rcx, [rsi+18h]
0x180043cfb  test    rcx, rcx
0x180043cfe  jz      short loc_180043D09
0x180043d00  mov     rdi, [rcx+8]
0x180043d04  sub     rdi, [rcx]
0x180043d07  jmp     short loc_180043D0B
0x180043d09  xor     edi, edi
0x180043d0b  mov     [rsp+130h+var_F0.cElements], edi
0x180043d0f  mov     [rsp+130h+var_F0.lLbound], 0
0x180043d17  mov     ecx, 11h; vt
0x180043d1c  lea     r8, [rsp+130h+var_F0]; rgsabound
0x180043d21  mov     edx, r15d; cDims
0x180043d24  call    cs:__imp_SafeArrayCreate
0x180043d2a  mov     r15, rax
0x180043d2d  mov     rcx, [r13+90h]; psz
0x180043d34  call    cs:__imp_SysAllocString
0x180043d3a  mov     r13, rax
0x180043d3d  lea     rcx, aPutwlanrespons; "PutWLANResponse"
0x180043d44  call    cs:__imp_SysAllocString
0x180043d4a  mov     r12, rax
0x180043d4d  test    r14, r14
0x180043d50  jz      loc_18004407D
0x180043d56  test    r15, r15
0x180043d59  jz      loc_18004407D
0x180043d5f  test    r13, r13
0x180043d62  jz      loc_18004407D
0x180043d68  test    rax, rax
0x180043d6b  jz      loc_18004407D
0x180043d71  lea     rdx, [rsp+130h+ppvData]; ppvData
0x180043d76  mov     rcx, r15; psa
0x180043d79  call    cs:__imp_SafeArrayAccessData
0x180043d7f  mov     ebx, eax
0x180043d81  test    eax, eax
0x180043d83  jns     short loc_180043DB1
0x180043d85  mov     r10, cs:WPP_GLOBAL_Control
0x180043d8c  lea     rdi, WPP_GLOBAL_Control
0x180043d93  cmp     r10, rdi
0x180043d96  jz      loc_180044007
0x180043d9c  cmp     byte ptr [r10+19h], 2
0x180043da1  jb      loc_180044007
0x180043da7  mov     edx, 21h ; '!'
0x180043dac  jmp     loc_180043FED
0x180043db1  mov     r8, rdi; unsigned __int64
0x180043db4  mov     rdx, [rsp+130h+ppvData]; unsigned __int8 *
0x180043db9  mov     rcx, rsi; this
0x180043dbc  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x180043dc1  mov     ebx, eax
0x180043dc3  test    eax, eax
0x180043dc5  jns     short loc_180043DF3
0x180043dc7  mov     r10, cs:WPP_GLOBAL_Control
0x180043dce  lea     rdi, WPP_GLOBAL_Control
0x180043dd5  cmp     r10, rdi
0x180043dd8  jz      loc_180044007
0x180043dde  cmp     byte ptr [r10+19h], 2
0x180043de3  jb      loc_180044007
0x180043de9  mov     edx, 22h ; '"'
0x180043dee  jmp     loc_180043FED
0x180043df3  mov     rcx, r15; psa
0x180043df6  call    cs:__imp_SafeArrayUnaccessData
0x180043dfc  mov     ebx, eax
0x180043dfe  test    eax, eax
0x180043e00  jns     short loc_180043E2E
0x180043e02  mov     r10, cs:WPP_GLOBAL_Control
0x180043e09  lea     rdi, WPP_GLOBAL_Control
0x180043e10  cmp     r10, rdi
0x180043e13  jz      loc_180044007
0x180043e19  cmp     byte ptr [r10+19h], 2
0x180043e1e  jb      loc_180044007
0x180043e24  mov     edx, 23h ; '#'
0x180043e29  jmp     loc_180043FED
0x180043e2e  mov     eax, 2011h
0x180043e33  mov     word ptr [rbp+57h+pv], ax
0x180043e37  mov     qword ptr [rbp+57h+pv+8], r15
0x180043e3b  xor     r15d, r15d
0x180043e3e  lea     eax, [r15+11h]
0x180043e42  mov     word ptr [rbp+57h+var_B0], ax
0x180043e46  mov     byte ptr [rbp+57h+var_B0+8], 2
0x180043e4a  lea     eax, [r15+8]
0x180043e4e  mov     word ptr [rbp+57h+var_98], ax
0x180043e52  mov     qword ptr [rbp+57h+var_98+8], r13
0x180043e56  xor     r13d, r13d
0x180043e59  mov     [rbp+57h+rgIndices], r13d
0x180043e5d  lea     r8, [rbp+57h+pv]; pv
0x180043e61  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180043e65  mov     rcx, r14; psa
0x180043e68  call    cs:__imp_SafeArrayPutElement
0x180043e6e  mov     ebx, eax
0x180043e70  test    eax, eax
0x180043e72  jns     short loc_180043E9F
0x180043e74  mov     r10, cs:WPP_GLOBAL_Control
0x180043e7b  lea     rdi, WPP_GLOBAL_Control
0x180043e82  cmp     r10, rdi
0x180043e85  jz      loc_180044007
0x180043e8b  cmp     byte ptr [r10+19h], 2
0x180043e90  jb      loc_180044007
0x180043e96  lea     edx, [r15+24h]
0x180043e9a  jmp     loc_180043FED
0x180043e9f  mov     [rbp+57h+rgIndices], 1
0x180043ea6  lea     r8, [rbp+57h+var_B0]; pv
0x180043eaa  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180043eae  mov     rcx, r14; psa
0x180043eb1  call    cs:__imp_SafeArrayPutElement
0x180043eb7  mov     ebx, eax
0x180043eb9  test    eax, eax
0x180043ebb  jns     short loc_180043EE9
0x180043ebd  mov     r10, cs:WPP_GLOBAL_Control
0x180043ec4  lea     rdi, WPP_GLOBAL_Control
0x180043ecb  cmp     r10, rdi
0x180043ece  jz      loc_180044007
0x180043ed4  cmp     byte ptr [r10+19h], 2
0x180043ed9  jb      loc_180044007
0x180043edf  mov     edx, 25h ; '%'
0x180043ee4  jmp     loc_180043FED
0x180043ee9  mov     [rbp+57h+rgIndices], 2
0x180043ef0  lea     r8, [rbp+57h+var_98]; pv
0x180043ef4  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180043ef8  mov     rcx, r14; psa
0x180043efb  call    cs:__imp_SafeArrayPutElement
0x180043f01  mov     ebx, eax
0x180043f03  test    eax, eax
0x180043f05  jns     short loc_180043F33
0x180043f07  mov     r10, cs:WPP_GLOBAL_Control
0x180043f0e  lea     rdi, WPP_GLOBAL_Control
0x180043f15  cmp     r10, rdi
0x180043f18  jz      loc_180044007
0x180043f1e  cmp     byte ptr [r10+19h], 2
0x180043f23  jb      loc_180044007
0x180043f29  mov     edx, 26h ; '&'
0x180043f2e  jmp     loc_180043FED
0x180043f33  mov     [rbp+57h+rgIndices], 3
0x180043f3a  mov     eax, 200Ch
0x180043f3f  mov     word ptr [rsp+130h+pvarg], ax
0x180043f44  mov     qword ptr [rsp+130h+pvarg+8], r14
0x180043f49  xor     r14d, r14d
0x180043f4c  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, 1
0x180043f53  jz      short loc_180043F91
0x180043f55  mov     rcx, [rsi+18h]
0x180043f59  mov     rdx, [rcx]
0x180043f5c  test    rcx, rcx
0x180043f5f  jz      short loc_180043F68
0x180043f61  mov     rcx, [rcx+8]
0x180043f65  sub     rcx, rdx
0x180043f68  lea     rax, [rsi+20h]
0x180043f6c  mov     [rsp+130h+var_100], rdx
0x180043f71  mov     [rsp+130h+var_108], cx
0x180043f76  mov     [rsp+130h+var_110], rax
0x180043f7b  mov     r9, r12
0x180043f7e  lea     r8, aUproxy; "UPROXY"
0x180043f85  lea     rdx, RawSend
0x180043f8c  call    McTemplateU0zzjhbr3_EtwEventWriteTransfer
0x180043f91  mov     rcx, [rbp+57h+arg_10]
0x180043f95  movups  xmm0, xmmword ptr [rsp+130h+pvarg]
0x180043f9a  movaps  [rbp+57h+var_50], xmm0
0x180043f9e  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180043fa3  movsd   [rbp+57h+var_40], xmm1
0x180043fa8  mov     rax, [rcx]
0x180043fab  lea     rdx, [rbp+57h+var_68]
0x180043faf  mov     [rsp+130h+var_110], rdx
0x180043fb4  lea     r9, [rbp+57h+var_80]
0x180043fb8  lea     r8, [rbp+57h+var_50]
0x180043fbc  mov     rdx, r12
0x180043fbf  mov     rax, [rax+40h]
0x180043fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fc8  mov     ebx, eax
0x180043fca  test    eax, eax
0x180043fcc  jns     short loc_180044044
0x180043fce  mov     r10, cs:WPP_GLOBAL_Control
0x180043fd5  lea     rdi, WPP_GLOBAL_Control
0x180043fdc  cmp     r10, rdi
0x180043fdf  jz      short loc_180044007
0x180043fe1  cmp     byte ptr [r10+19h], 2
0x180043fe6  jb      short loc_180044007
0x180043fe8  mov     edx, 27h ; '''
0x180043fed  mov     r9d, eax
0x180043ff0  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043ff7  mov     rcx, [r10+10h]
0x180043ffb  call    WPP_SF_d
0x180044000  mov     r10, cs:WPP_GLOBAL_Control
0x180044007  mov     r11d, 80040216h
0x18004400d  cmp     ebx, r11d
0x180044010  jnz     short loc_180044044
0x180044012  cmp     r10, rdi
0x180044015  jz      short loc_180044042
0x180044017  cmp     byte ptr [r10+19h], 3
0x18004401c  jb      short loc_180044042
0x18004401e  xor     ecx, ecx; int
0x180044020  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044025  mov     edx, 28h ; '('
0x18004402a  mov     dword ptr [rsp+130h+var_110], r11d
0x18004402f  mov     r9, rax
0x180044032  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180044039  mov     rcx, [r10+10h]
0x18004403d  call    WPP_SF_sd
  ... truncated ...
```
