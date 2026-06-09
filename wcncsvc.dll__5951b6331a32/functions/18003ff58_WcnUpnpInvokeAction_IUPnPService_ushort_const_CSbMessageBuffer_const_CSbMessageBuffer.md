# WcnUpnpInvokeAction(IUPnPService *,ushort const *,CSbMessageBuffer const *,CSbMessageBuffer *)

- ea: `0x18003ff58`
- end: `0x1800402dd`
- name: `?WcnUpnpInvokeAction@@YAJPEAUIUPnPService@@PEBGPEBVCSbMessageBuffer@@PEAV2@@Z`
- size: `901`
- prototype: `int(struct IUPnPService *, const unsigned __int16 *, const struct CSbMessageBuffer *, struct CSbMessageBuffer *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18003e6c0`
- `0x1800448b0`
- `0x180044b70`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003f9a4`
- `0x18003fc80`
- `0x18003ff58`
- `0x180040644`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800400e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800400e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180040278`
- `OLEAUT32!__imp_SysFreeString` at `0x180040278`
- `OLEAUT32!__imp_VariantInit` at `0x18004004a`
- `OLEAUT32!__imp_VariantInit` at `0x180040054`
- `OLEAUT32!__imp_VariantInit` at `0x18004005e`
- `OLEAUT32!__imp_VariantInit` at `0x180040068`
- `OLEAUT32!__imp_VariantInit` at `0x18004004a`
- `OLEAUT32!__imp_VariantInit` at `0x180040054`
- `OLEAUT32!__imp_VariantInit` at `0x18004005e`
- `OLEAUT32!__imp_VariantInit` at `0x180040068`
- `OLEAUT32!__imp_VariantClear` at `0x18004024c`
- `OLEAUT32!__imp_VariantClear` at `0x180040256`
- `OLEAUT32!__imp_VariantClear` at `0x180040260`
- `OLEAUT32!__imp_VariantClear` at `0x18004026a`
- `OLEAUT32!__imp_VariantClear` at `0x18004024c`
- `OLEAUT32!__imp_VariantClear` at `0x180040256`
- `OLEAUT32!__imp_VariantClear` at `0x180040260`
- `OLEAUT32!__imp_VariantClear` at `0x18004026a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800400d8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800400d8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180040286`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180040286`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004010f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18004010f`

## string_xrefs

- `0x180040007`: `pService`

## pseudocode

```c
__int64 __fastcall WcnUpnpInvokeAction(
        struct IUPnPService *a1,
        const unsigned __int16 *a2,
        const struct CSbMessageBuffer *a3,
        UUID *a4)
{
  SAFEARRAY *v4; // rdi
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  const char *v13; // r9
  int VariantFromBlob; // eax
  int v16; // ebx
  OLECHAR *v17; // rsi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct IUPnPServiceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *InvokeAction)(IUPnPService *, BSTR, VARIANT, VARIANT *, VARIANT *); // rax
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  const char *v25; // rax
  __int64 v26; // r10
  unsigned int v27; // eax
  __int64 v28; // r10
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-71h] BYREF
  VARIANTARG v31; // [rsp+50h] [rbp-59h] BYREF
  VARIANTARG pv; // [rsp+68h] [rbp-41h] BYREF
  VARIANTARG v33; // [rsp+80h] [rbp-29h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-9h] BYREF
  IRecordInfo *pRecInfo; // [rsp+B0h] [rbp+7h]
  LONG rgIndices; // [rsp+110h] [rbp+67h] BYREF

  v4 = 0;
  rgIndices = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pv, 0, sizeof(pv));
  memset(&v31, 0, sizeof(v31));
  memset(&v33, 0, sizeof(v33));
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 28, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 29;
    v13 = "pService";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v9 + 2), v12, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v13);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v12 = 30;
    v13 = "wszActionName";
    goto LABEL_12;
  }
  VariantInit(&pvarg);
  VariantInit(&pv);
  VariantInit(&v31);
  VariantInit(&v33);
  rgsabound = 0;
  if ( a3 )
  {
    rgsabound.cElements = 1;
    VariantFromBlob = WcnUpnpGetVariantFromBlob(a3, &pv);
    v16 = VariantFromBlob;
    if ( VariantFromBlob < 0 )
    {
      v17 = 0;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_39;
      v19 = 31;
      goto LABEL_19;
    }
  }
  v4 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v17 = SysAllocString(a2);
  if ( !v17 || !v4 )
  {
    v16 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v26 + 16), 32, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v25);
    }
    goto LABEL_39;
  }
  if ( a3 )
  {
    VariantFromBlob = SafeArrayPutElement(v4, &rgIndices, &pv);
    v16 = VariantFromBlob;
    if ( VariantFromBlob < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_39;
      v19 = 33;
      goto LABEL_19;
    }
  }
  pvarg.llVal = (LONGLONG)v4;
  pvarg.vt = 8204;
  lpVtbl = a1->lpVtbl;
  v4 = 0;
  pRecInfo = pvarg.pRecInfo;
  InvokeAction = lpVtbl->InvokeAction;
  v34 = *(_OWORD *)&pvarg.vt;
  v22 = ((__int64 (__fastcall *)(struct IUPnPService *, OLECHAR *, __int128 *, VARIANTARG *, VARIANTARG *))InvokeAction)(
          a1,
          v17,
          &v34,
          &v31,
          &v33);
  v16 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, (_DWORD)a2, v22);
    goto LABEL_39;
  }
  if ( a4 )
  {
    VariantFromBlob = WcnUpnpGetBlobFromOutArgsVariant((__int64)&v31, a4);
    v16 = VariantFromBlob;
    if ( VariantFromBlob < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 35;
LABEL_19:
        WPP_SF_d(v18[2], v19, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, (unsigned int)VariantFromBlob);
      }
    }
  }
LABEL_39:
  VariantClear(&pvarg);
  VariantClear(&v31);
  VariantClear(&v33);
  VariantClear(&pv);
  if ( v17 )
    SysFreeString(v17);
  if ( v4 )
    SafeArrayDestroy(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v16 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v27 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v28 + 16), 36, (unsigned int)WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v27, v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18003ff58  push    rbp
0x18003ff5a  push    rbx
0x18003ff5b  push    rsi
0x18003ff5c  push    rdi
0x18003ff5d  push    r12
0x18003ff5f  push    r13
0x18003ff61  push    r14
0x18003ff63  push    r15
0x18003ff65  lea     rbp, [rsp-1Fh]
0x18003ff6a  sub     rsp, 0C8h
0x18003ff71  xor     eax, eax
0x18003ff73  xorps   xmm0, xmm0
0x18003ff76  xorps   xmm1, xmm1
0x18003ff79  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003ff7d  xor     edi, edi
0x18003ff7f  mov     qword ptr [rbp+57h+pv+10h], rax
0x18003ff83  mov     [rbp+57h+rgIndices], edi
0x18003ff86  mov     r12, r9
0x18003ff89  mov     r14, r8
0x18003ff8c  mov     qword ptr [rbp+57h+var_B0+10h], rax
0x18003ff90  mov     r15, rdx
0x18003ff93  mov     qword ptr [rbp+57h+var_80+10h], rax
0x18003ff97  mov     r13, rcx
0x18003ff9a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003ff9e  movups  xmmword ptr [rbp+57h+pv], xmm1
0x18003ffa2  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18003ffa6  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x18003ffaa  mov     r10, cs:WPP_GLOBAL_Control
0x18003ffb1  lea     rax, WPP_GLOBAL_Control
0x18003ffb8  lea     esi, [rdi+1]
0x18003ffbb  cmp     r10, rax
0x18003ffbe  jz      short loc_18003FFF2
0x18003ffc0  cmp     byte ptr [r10+19h], 6
0x18003ffc5  jb      short loc_18003FFF2
0x18003ffc7  mov     ecx, esi; int
0x18003ffc9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ffce  mov     rcx, [r10+10h]
0x18003ffd2  lea     edx, [rdi+1Ch]
0x18003ffd5  mov     r9, rax
0x18003ffd8  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x18003ffdf  call    WPP_SF_s
0x18003ffe4  mov     r10, cs:WPP_GLOBAL_Control
0x18003ffeb  lea     rax, WPP_GLOBAL_Control
0x18003fff2  test    r13, r13
0x18003fff5  jnz     short loc_180040010
0x18003fff7  cmp     r10, rax
0x18003fffa  jz      short loc_18004003C
0x18003fffc  cmp     byte ptr [r10+19h], 2
0x180040001  jb      short loc_18004003C
0x180040003  lea     edx, [r13+1Dh]
0x180040007  lea     r9, aPservice; "pService"
0x18004000e  jmp     short loc_18004002C
0x180040010  test    r15, r15
0x180040013  jnz     short loc_180040046
0x180040015  cmp     r10, rax
0x180040018  jz      short loc_18004003C
0x18004001a  cmp     byte ptr [r10+19h], 2
0x18004001f  jb      short loc_18004003C
0x180040021  lea     edx, [r15+1Eh]
0x180040025  lea     r9, aWszactionname; "wszActionName"
0x18004002c  mov     rcx, [r10+10h]
0x180040030  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x180040037  call    WPP_SF_s
0x18004003c  mov     eax, 80004003h
0x180040041  jmp     loc_1800402C9
0x180040046  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004004a  call    cs:__imp_VariantInit
0x180040050  lea     rcx, [rbp+57h+pv]; pvarg
0x180040054  call    cs:__imp_VariantInit
0x18004005a  lea     rcx, [rbp+57h+var_B0]; pvarg
0x18004005e  call    cs:__imp_VariantInit
0x180040064  lea     rcx, [rbp+57h+var_80]; pvarg
0x180040068  call    cs:__imp_VariantInit
0x18004006e  mov     qword ptr [rbp+57h+rgsabound.cElements], rdi
0x180040072  test    r14, r14
0x180040075  jz      short loc_1800400CD
0x180040077  lea     rdx, [rbp+57h+pv]; pvarg
0x18004007b  mov     [rbp+57h+rgsabound.cElements], esi
0x18004007e  mov     rcx, r14; this
0x180040081  call    WcnUpnpGetVariantFromBlob
0x180040086  mov     ebx, eax
0x180040088  test    eax, eax
0x18004008a  jns     short loc_1800400CD
0x18004008c  mov     rsi, rdi
0x18004008f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040096  lea     r14, WPP_GLOBAL_Control
0x18004009d  cmp     rcx, r14
0x1800400a0  jz      loc_180040248
0x1800400a6  cmp     byte ptr [rcx+19h], 2
0x1800400aa  jb      loc_180040248
0x1800400b0  mov     edx, 1Fh
0x1800400b5  mov     rcx, [rcx+10h]
0x1800400b9  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x1800400c0  mov     r9d, eax
0x1800400c3  call    WPP_SF_d
0x1800400c8  jmp     loc_180040248
0x1800400cd  mov     ecx, 0Ch; vt
0x1800400d2  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800400d6  mov     edx, esi; cDims
0x1800400d8  call    cs:__imp_SafeArrayCreate
0x1800400de  mov     rcx, r15; psz
0x1800400e1  mov     rdi, rax
0x1800400e4  call    cs:__imp_SysAllocString
0x1800400ea  mov     rsi, rax
0x1800400ed  test    rax, rax
0x1800400f0  jz      loc_180040201
0x1800400f6  test    rdi, rdi
0x1800400f9  jz      loc_180040201
0x1800400ff  test    r14, r14
0x180040102  jz      short loc_180040146
0x180040104  lea     r8, [rbp+57h+pv]; pv
0x180040108  mov     rcx, rdi; psa
0x18004010b  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18004010f  call    cs:__imp_SafeArrayPutElement
0x180040115  mov     ebx, eax
0x180040117  test    eax, eax
0x180040119  jns     short loc_180040146
0x18004011b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040122  lea     r14, WPP_GLOBAL_Control
0x180040129  cmp     rcx, r14
0x18004012c  jz      loc_180040248
0x180040132  cmp     byte ptr [rcx+19h], 2
0x180040136  jb      loc_180040248
0x18004013c  mov     edx, 21h ; '!'
0x180040141  jmp     loc_1800400B5
0x180040146  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18004014b  lea     rcx, [rbp+57h+var_80]
0x18004014f  mov     qword ptr [rbp+57h+pvarg+8], rdi
0x180040153  lea     r9, [rbp+57h+var_B0]
0x180040157  mov     eax, 200Ch
0x18004015c  mov     [rsp+100h+var_E0], rcx
0x180040161  mov     word ptr [rbp+57h+pvarg], ax
0x180040165  lea     r8, [rbp+57h+var_60]
0x180040169  mov     rax, [r13+0]
0x18004016d  mov     rdx, rsi
0x180040170  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180040174  mov     rcx, r13
0x180040177  xor     edi, edi
0x180040179  movsd   [rbp+57h+var_50], xmm1
0x18004017e  mov     rax, [rax+40h]
0x180040182  movaps  [rbp+57h+var_60], xmm0
0x180040186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004018b  mov     ebx, eax
0x18004018d  test    eax, eax
0x18004018f  jns     short loc_1800401C7
0x180040191  mov     rcx, cs:WPP_GLOBAL_Control
0x180040198  lea     r14, WPP_GLOBAL_Control
0x18004019f  cmp     rcx, r14
0x1800401a2  jz      loc_180040248
0x1800401a8  cmp     byte ptr [rcx+19h], 2
0x1800401ac  jb      loc_180040248
0x1800401b2  mov     rcx, [rcx+10h]
0x1800401b6  mov     r9, r15
0x1800401b9  mov     dword ptr [rsp+100h+var_E0], eax
0x1800401bd  call    WPP_SF_Sd
0x1800401c2  jmp     loc_180040248
0x1800401c7  test    r12, r12
0x1800401ca  jz      short loc_180040241
0x1800401cc  mov     rdx, r12
0x1800401cf  lea     rcx, [rbp+57h+var_B0]
0x1800401d3  call    WcnUpnpGetBlobFromOutArgsVariant
0x1800401d8  mov     ebx, eax
0x1800401da  test    eax, eax
0x1800401dc  jns     short loc_180040241
0x1800401de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800401e5  lea     r14, WPP_GLOBAL_Control
0x1800401ec  cmp     rcx, r14
0x1800401ef  jz      short loc_180040248
0x1800401f1  cmp     byte ptr [rcx+19h], 2
0x1800401f5  jb      short loc_180040248
0x1800401f7  mov     edx, 23h ; '#'
0x1800401fc  jmp     loc_1800400B5
0x180040201  mov     ebx, 8007000Eh
0x180040206  mov     r10, cs:WPP_GLOBAL_Control
0x18004020d  lea     r14, WPP_GLOBAL_Control
0x180040214  cmp     r10, r14
0x180040217  jz      short loc_180040248
0x180040219  cmp     byte ptr [r10+19h], 2
0x18004021e  jb      short loc_180040248
0x180040220  xor     ecx, ecx; int
0x180040222  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040227  mov     rcx, [r10+10h]
0x18004022b  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x180040232  mov     edx, 20h ; ' '
0x180040237  mov     r9, rax
0x18004023a  call    WPP_SF_s
0x18004023f  jmp     short loc_180040248
0x180040241  lea     r14, WPP_GLOBAL_Control
0x180040248  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004024c  call    cs:__imp_VariantClear
0x180040252  lea     rcx, [rbp+57h+var_B0]; pvarg
0x180040256  call    cs:__imp_VariantClear
0x18004025c  lea     rcx, [rbp+57h+var_80]; pvarg
0x180040260  call    cs:__imp_VariantClear
0x180040266  lea     rcx, [rbp+57h+pv]; pvarg
0x18004026a  call    cs:__imp_VariantClear
0x180040270  test    rsi, rsi
0x180040273  jz      short loc_18004027E
0x180040275  mov     rcx, rsi; bstrString
0x180040278  call    cs:__imp_SysFreeString
0x18004027e  test    rdi, rdi
0x180040281  jz      short loc_18004028C
0x180040283  mov     rcx, rdi; psa
0x180040286  call    cs:__imp_SafeArrayDestroy
0x18004028c  mov     r10, cs:WPP_GLOBAL_Control
0x180040293  cmp     r10, r14
0x180040296  jz      short loc_1800402C7
0x180040298  test    ebx, ebx
0x18004029a  js      short loc_1800402A3
0x18004029c  cmp     byte ptr [r10+19h], 6
0x1800402a1  jb      short loc_1800402C7
0x1800402a3  or      ecx, 0FFFFFFFFh; int
0x1800402a6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800402ab  mov     rcx, [r10+10h]
0x1800402af  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x1800402b6  mov     edx, 24h ; '$'
0x1800402bb  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800402bf  mov     r9, rax
0x1800402c2  call    WPP_SF_sd
0x1800402c7  mov     eax, ebx
0x1800402c9  add     rsp, 0C8h
0x1800402d0  pop     r15
0x1800402d2  pop     r14
0x1800402d4  pop     r13
0x1800402d6  pop     r12
0x1800402d8  pop     rdi
0x1800402d9  pop     rsi
0x1800402da  pop     rbx
0x1800402db  pop     rbp
0x1800402dc  retn
```
