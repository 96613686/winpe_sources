# WpCreateXmlDoc

- ea: `0x180027c10`
- end: `0x180027f29`
- name: `WpCreateXmlDoc`
- size: `793`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026f98`
- `0x180027054`
- `0x180027408`
- `0x180027a54`
- `0x18003f264`
- `0x180102304`
- `0x1801b30ac`
- `0x1801b3814`
- `0x1801be3dc`

## callees

- `0x180027c10`
- `0x180027f30`
- `0x18007d684`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c7a`
- `OLEAUT32!__imp_SysAllocString` at `0x180027cbe`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d06`
- `OLEAUT32!__imp_SysAllocString` at `0x180027cbe`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cce`
- `OLEAUT32!__imp_SysFreeString` at `0x180027db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cce`
- `OLEAUT32!__imp_SysFreeString` at `0x180027db0`
- `OLEAUT32!__imp_VariantInit` at `0x180027c4d`
- `OLEAUT32!__imp_VariantInit` at `0x180027c57`
- `OLEAUT32!__imp_VariantInit` at `0x180027c4d`
- `OLEAUT32!__imp_VariantInit` at `0x180027c57`
- `OLEAUT32!__imp_VariantClear` at `0x180027cdb`
- `OLEAUT32!__imp_VariantClear` at `0x180027d14`
- `OLEAUT32!__imp_VariantClear` at `0x180027d9d`
- `OLEAUT32!__imp_VariantClear` at `0x180027da7`
- `OLEAUT32!__imp_VariantClear` at `0x180027e47`
- `OLEAUT32!__imp_VariantClear` at `0x180027cdb`
- `OLEAUT32!__imp_VariantClear` at `0x180027d14`
- `OLEAUT32!__imp_VariantClear` at `0x180027d9d`
- `OLEAUT32!__imp_VariantClear` at `0x180027da7`
- `OLEAUT32!__imp_VariantClear` at `0x180027e47`

## string_xrefs

- `0x180027cff`: `xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:WLANPolicy='http://www.microsoft.com/networking/WLAN/policy/v1' xmlns:LANProfile='http://www.microsoft.com/networking/LAN/profile/v1' xmlns:LANPolicy='http://www.microsoft.com/networking/LAN/policy/v1' xmlns:LANPolicyV2='http://www.microsoft.com/networking/LAN/policy/v2' xmlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WpCreateXmlDoc(int a1, struct IUnknown *a2, struct IXMLDOMSchemaCollection **a3)
{
  struct IXMLDOMSchemaCollection *v4; // rbx
  struct IXMLDOMSchemaCollection *v5; // r14
  OLECHAR *v6; // rdi
  HRESULT Instance; // eax
  unsigned int v8; // esi
  int v9; // eax
  BSTR v10; // rsi
  __m128i v11; // xmm1
  IRecordInfo *pRecInfo; // xmm2_8
  int v13; // eax
  struct IXMLDOMSchemaCollection *v14; // rax
  int v16; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG v18; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v19; // [rsp+60h] [rbp-20h] BYREF
  struct IXMLDOMSchemaCollection *ppv; // [rsp+C0h] [rbp+40h] BYREF
  IRecordInfo *v21; // [rsp+C8h] [rbp+48h]

  v4 = 0;
  v5 = 0;
  ppv = 0;
  *a3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      ATL::AtlComPtrAssign((struct IUnknown **)&ppv, a2);
      v5 = ppv;
    }
    else
    {
      v8 = WpCreateProfileSchemaCollectionInternal(&ppv);
      v5 = ppv;
      if ( v8 )
        goto LABEL_20;
    }
  }
  ppv = 0;
  v6 = 0;
  VariantInit(&pvarg);
  VariantInit(&v18);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, (LPVOID *)&ppv);
  v8 = Instance;
  if ( Instance >= 0 )
    goto LABEL_50;
  if ( (Instance & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)Instance;
  if ( !v8 )
  {
LABEL_50:
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMSchemaCollection *, _QWORD))ppv->lpVtbl[4].add)(ppv, 0);
    v8 = v9;
    if ( v9 >= 0 )
      goto LABEL_51;
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v9;
    if ( !v8 )
    {
LABEL_51:
      SysFreeString(0);
      v10 = SysAllocString(L"SelectionNamespaces");
      if ( v10 )
      {
        SysFreeString(0);
        v6 = v10;
      }
      v8 = 8;
      if ( VariantClear(&pvarg) < 0
        || (v21 = 0,
            *(_OWORD *)&v19.vt = 0,
            v19.vt = 8,
            v19.llVal = (LONGLONG)SysAllocString(
                                    L"xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:WLANPo"
                                     "licy='http://www.microsoft.com/networking/WLAN/policy/v1' xmlns:LANProfile='http://"
                                     "www.microsoft.com/networking/LAN/profile/v1' xmlns:LANPolicy='http://www.microsoft."
                                     "com/networking/LAN/policy/v1' xmlns:LANPolicyV2='http://www.microsoft.com/networkin"
                                     "g/LAN/policy/v2' xmlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:bas"
                                     "eeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnection"
                                     "PropertiesV1' xmlns:mspeapconnectionpropertiesv1='http://www.microsoft.com/provisio"
                                     "ning/MsPeapConnectionPropertiesV1' xmlns:mschapv2connectionpropertiesv1='http://www"
                                     ".microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1' xmlns:WLANProfileV2='ht"
                                     "tp://www.microsoft.com/networking/WLAN/profile/v2' xmlns:WLANProfileV3='http://www."
                                     "microsoft.com/networking/WLAN/profile/v3' xmlns:WLANProfileV4='http://www.microsoft"
                                     ".com/networking/WLAN/profile/v4' xmlns:WLANProfileV5='http://www.microsoft.com/netw"
                                     "orking/WLAN/profile/v5' xmlns:WLANPolicyV2='http://www.microsoft.com/networking/WLA"
                                     "N/policy/v2' xmlns:WLANPolicyV3='http://www.microsoft.com/networking/WLAN/policy/v3"
                                     "' xmlns:WLANPolicyV4='http://www.microsoft.com/networking/WLAN/policy/v4' xmlns:WLA"
                                     "NAPProfile='http://www.microsoft.com/networking/WLANAP/profile/v1' xmlns:WFDProfile"
                                     "='http://www.microsoft.com/networking/WiFiDirect/profile/v1' xmlns:WFDLegacyProfile"
                                     "='http://www.microsoft.com/networking/WiFiDirectLegacy/profile/v1' "),
            VariantClear(&pvarg) < 0) )
      {
        pRecInfo = pvarg.pRecInfo;
        v11 = *(__m128i *)&pvarg.vt;
      }
      else
      {
        v11 = *(__m128i *)&v19.vt;
        *(_OWORD *)&pvarg.vt = *(_OWORD *)&v19.vt;
        pRecInfo = v21;
        pvarg.pRecInfo = v21;
      }
      if ( v6 && (unsigned __int16)_mm_cvtsi128_si32(v11) == 8 && _mm_srli_si128(v11, 8).m128i_u64[0] )
      {
        *(__m128i *)&v19.vt = v11;
        v19.pRecInfo = pRecInfo;
        v13 = ((__int64 (__fastcall *)(struct IXMLDOMSchemaCollection *, OLECHAR *, VARIANTARG *))ppv->lpVtbl[5].get_length)(
                ppv,
                v6,
                &v19);
        v8 = v13;
        if ( v13 < 0 )
        {
          if ( (v13 & 0x1FFF0000) == 0x70000 )
            v8 = (unsigned __int16)v13;
          if ( v8 )
            goto LABEL_16;
        }
        else
        {
          v8 = 0;
        }
        if ( v5 )
        {
          VariantClear(&v18);
          v18.vt = 9;
          v18.llVal = (LONGLONG)v5;
          ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v5->lpVtbl->AddRef)(v5);
          v19 = v18;
          v16 = ((__int64 (__fastcall *)(struct IXMLDOMSchemaCollection *, VARIANTARG *))ppv->lpVtbl[5].get)(ppv, &v19);
          v8 = v16;
          if ( v16 < 0 )
          {
            if ( (v16 & 0x1FFF0000) == 0x70000 )
              v8 = (unsigned __int16)v16;
            if ( v8 )
              goto LABEL_16;
          }
          else
          {
            v8 = 0;
          }
        }
        v4 = ppv;
        ppv = 0;
      }
    }
  }
LABEL_16:
  VariantClear(&v18);
  VariantClear(&pvarg);
  SysFreeString(v6);
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))ppv->lpVtbl->Release)(ppv);
  if ( !v8 )
  {
    v14 = v4;
    v4 = 0;
    *a3 = v14;
  }
LABEL_20:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v4->lpVtbl->Release)(v4);
  return v8;
}

```

## disassembly

```asm
0x180027c10  mov     [rsp-28h+arg_0], rbx
0x180027c15  mov     [rsp-28h+arg_8], rsi
0x180027c1a  push    rbp
0x180027c1b  push    rdi
0x180027c1c  push    r13
0x180027c1e  push    r14
0x180027c20  push    r15
0x180027c22  mov     rbp, rsp
0x180027c25  sub     rsp, 80h
0x180027c2c  mov     r15, r8
0x180027c2f  xor     ebx, ebx
0x180027c31  xor     r14d, r14d
0x180027c34  mov     [rbp+arg_10], r14
0x180027c38  mov     [r8], rbx
0x180027c3b  test    ecx, ecx
0x180027c3d  jnz     loc_180027E21
0x180027c43  mov     [rbp+arg_10], rbx
0x180027c47  xor     edi, edi
0x180027c49  lea     rcx, [rbp+pvarg]; pvarg
0x180027c4d  call    cs:__imp_VariantInit
0x180027c53  lea     rcx, [rbp+var_38]; pvarg
0x180027c57  call    cs:__imp_VariantInit
0x180027c5d  lea     rax, [rbp+arg_10]
0x180027c61  mov     [rsp+80h+ppv], rax; ppv
0x180027c66  lea     r9, IID_IXMLDOMDocument2; riid
0x180027c6d  xor     edx, edx; pUnkOuter
0x180027c6f  lea     r8d, [rdi+1]; dwClsContext
0x180027c73  lea     rcx, CLSID_DOMDocument60; rclsid
0x180027c7a  call    cs:__imp_CoCreateInstance
0x180027c80  mov     esi, eax
0x180027c82  mov     r13d, 1FFF0000h
0x180027c88  test    eax, eax
0x180027c8a  js      loc_180027ED4
0x180027c90  mov     rcx, [rbp+arg_10]
0x180027c94  mov     rax, [rcx]
0x180027c97  xor     edx, edx
0x180027c99  mov     rax, [rax+1F8h]
0x180027ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca5  mov     esi, eax
0x180027ca7  test    eax, eax
0x180027ca9  js      loc_180027EE3
0x180027caf  xor     ecx, ecx; bstrString
0x180027cb1  call    cs:__imp_SysFreeString
0x180027cb7  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x180027cbe  call    cs:__imp_SysAllocString
0x180027cc4  mov     rsi, rax
0x180027cc7  test    rax, rax
0x180027cca  jz      short loc_180027CD7
0x180027ccc  xor     ecx, ecx; bstrString
0x180027cce  call    cs:__imp_SysFreeString
0x180027cd4  mov     rdi, rsi
0x180027cd7  lea     rcx, [rbp+pvarg]; pvarg
0x180027cdb  call    cs:__imp_VariantClear
0x180027ce1  mov     esi, 8
0x180027ce6  test    eax, eax
0x180027ce8  js      loc_180027EF2
0x180027cee  xorps   xmm0, xmm0
0x180027cf1  xor     eax, eax
0x180027cf3  mov     [rbp+arg_18], rax
0x180027cf7  movups  [rbp+var_20], xmm0
0x180027cfb  mov     word ptr [rbp+var_20], si
0x180027cff  lea     rcx, aXmlnsWlanprofi; "xmlns:WLANProfile='http://www.microsoft"...
0x180027d06  call    cs:__imp_SysAllocString
0x180027d0c  mov     qword ptr [rbp+var_20+8], rax
0x180027d10  lea     rcx, [rbp+pvarg]; pvarg
0x180027d14  call    cs:__imp_VariantClear
0x180027d1a  test    eax, eax
0x180027d1c  js      loc_180027EF2
0x180027d22  movups  xmm1, [rbp+var_20]
0x180027d26  movups  xmmword ptr [rbp+pvarg], xmm1
0x180027d2a  movsd   xmm2, [rbp+arg_18]
0x180027d2f  movsd   qword ptr [rbp+pvarg+10h], xmm2
0x180027d34  test    rdi, rdi
0x180027d37  jz      short loc_180027D99
0x180027d39  movd    eax, xmm1
0x180027d3d  cmp     ax, si
0x180027d40  jnz     short loc_180027D99
0x180027d42  movdqa  xmm0, xmm1
0x180027d46  psrldq  xmm0, 8
0x180027d4b  movq    rax, xmm0
0x180027d50  test    rax, rax
0x180027d53  jz      short loc_180027D99
0x180027d55  mov     rcx, [rbp+arg_10]
0x180027d59  movaps  [rbp+var_20], xmm1
0x180027d5d  movsd   [rbp+var_10], xmm2
0x180027d62  mov     rax, [rcx]
0x180027d65  lea     r8, [rbp+var_20]
0x180027d69  mov     rdx, rdi
0x180027d6c  mov     rax, [rax+280h]
0x180027d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d78  mov     esi, eax
0x180027d7a  test    eax, eax
0x180027d7c  js      loc_180027F00
0x180027d82  xor     esi, esi
0x180027d84  test    r14, r14
0x180027d87  jnz     loc_180027E43
0x180027d8d  mov     rbx, [rbp+arg_10]
0x180027d91  mov     [rbp+arg_10], 0
0x180027d99  lea     rcx, [rbp+var_38]; pvarg
0x180027d9d  call    cs:__imp_VariantClear
0x180027da3  lea     rcx, [rbp+pvarg]; pvarg
0x180027da7  call    cs:__imp_VariantClear
0x180027dad  mov     rcx, rdi; bstrString
0x180027db0  call    cs:__imp_SysFreeString
0x180027db6  nop
0x180027db7  mov     rcx, [rbp+arg_10]
0x180027dbb  test    rcx, rcx
0x180027dbe  jz      short loc_180027DCD
0x180027dc0  mov     rax, [rcx]
0x180027dc3  mov     rax, [rax+10h]
0x180027dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dcc  nop
0x180027dcd  test    esi, esi
0x180027dcf  jnz     short loc_180027DD9
0x180027dd1  mov     rax, rbx
0x180027dd4  xor     ebx, ebx
0x180027dd6  mov     [r15], rax
0x180027dd9  test    r14, r14
0x180027ddc  jz      short loc_180027DEE
0x180027dde  mov     rax, [r14]
0x180027de1  mov     rcx, r14
0x180027de4  mov     rax, [rax+10h]
0x180027de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ded  nop
0x180027dee  test    rbx, rbx
0x180027df1  jz      short loc_180027E03
0x180027df3  mov     rax, [rbx]
0x180027df6  mov     rcx, rbx
0x180027df9  mov     rax, [rax+10h]
0x180027dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e02  nop
0x180027e03  mov     eax, esi
0x180027e05  lea     r11, [rsp+80h+var_s0]
0x180027e0d  mov     rbx, [r11+30h]
0x180027e11  mov     rsi, [r11+38h]
0x180027e15  mov     rsp, r11
0x180027e18  pop     r15
0x180027e1a  pop     r14
0x180027e1c  pop     r13
0x180027e1e  pop     rdi
0x180027e1f  pop     rbp
0x180027e20  retn
0x180027e21  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x180027e25  test    rdx, rdx
0x180027e28  jnz     loc_180027EC6
0x180027e2e  call    ?WpCreateProfileSchemaCollectionInternal@@YAKPEAPEAUIXMLDOMSchemaCollection@@@Z; WpCreateProfileSchemaCollectionInternal(IXMLDOMSchemaCollection * *)
0x180027e33  mov     esi, eax
0x180027e35  mov     r14, [rbp+arg_10]
0x180027e39  test    eax, eax
0x180027e3b  jz      loc_180027C43
0x180027e41  jmp     short loc_180027DD9
0x180027e43  lea     rcx, [rbp+var_38]; pvarg
0x180027e47  call    cs:__imp_VariantClear
0x180027e4d  mov     eax, 9
0x180027e52  mov     word ptr [rbp+var_38], ax
0x180027e56  mov     qword ptr [rbp+var_38+8], r14
0x180027e5a  mov     rax, [r14]
0x180027e5d  mov     rcx, r14
0x180027e60  mov     rax, [rax+8]
0x180027e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e69  mov     rcx, [rbp+arg_10]
0x180027e6d  movups  xmm0, xmmword ptr [rbp+var_38]
0x180027e71  movaps  [rbp+var_20], xmm0
0x180027e75  movsd   xmm1, qword ptr [rbp+var_38+10h]
0x180027e7a  movsd   [rbp+var_10], xmm1
0x180027e7f  mov     rax, [rcx]
0x180027e82  lea     rdx, [rbp+var_20]
0x180027e86  mov     rax, [rax+270h]
0x180027e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e92  mov     esi, eax
0x180027e94  test    eax, eax
0x180027e96  js      short loc_180027F0F
0x180027e98  xor     esi, esi
0x180027e9a  jmp     loc_180027D8D
0x180027e9f  test    esi, esi
0x180027ea1  jnz     loc_180027D99
0x180027ea7  jmp     loc_180027CAF
0x180027eac  test    esi, esi
0x180027eae  jnz     loc_180027D99
0x180027eb4  jmp     loc_180027C90
0x180027eb9  test    esi, esi
0x180027ebb  jnz     loc_180027D99
0x180027ec1  jmp     loc_180027D84
0x180027ec6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180027ecb  mov     r14, [rbp+arg_10]
0x180027ecf  jmp     loc_180027C43
0x180027ed4  and     eax, r13d
0x180027ed7  cmp     eax, 70000h
0x180027edc  jnz     short loc_180027EAC
0x180027ede  movzx   esi, si
0x180027ee1  jmp     short loc_180027EAC
0x180027ee3  and     eax, r13d
0x180027ee6  cmp     eax, 70000h
0x180027eeb  jnz     short loc_180027E9F
0x180027eed  movzx   esi, si
0x180027ef0  jmp     short loc_180027E9F
0x180027ef2  movsd   xmm2, qword ptr [rbp+pvarg+10h]
0x180027ef7  movups  xmm1, xmmword ptr [rbp+pvarg]
0x180027efb  jmp     loc_180027D34
0x180027f00  and     eax, r13d
0x180027f03  cmp     eax, 70000h
0x180027f08  jnz     short loc_180027EB9
0x180027f0a  movzx   esi, si
0x180027f0d  jmp     short loc_180027EB9
0x180027f0f  and     eax, r13d
0x180027f12  cmp     eax, 70000h
0x180027f17  jnz     short loc_180027F1C
0x180027f19  movzx   esi, si
0x180027f1c  test    esi, esi
0x180027f1e  jnz     loc_180027D99
0x180027f24  jmp     loc_180027D8D
```
