# CWbemDispatchMgr::InvokeWbemProperty(long,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800058c0`
- end: `0x180005be9`
- name: `?InvokeWbemProperty@CWbemDispatchMgr@@AEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `809`
- prototype: `__int64 __fastcall(CWbemDispatchMgr *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800055c0`

## callees

- `0x1800019a0`
- `0x1800058c0`
- `0x180005bf0`
- `0x18000c0b0`
- `0x180013750`
- `0x180024984`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005966`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005966`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a20`
- `OLEAUT32!__imp_SysFreeString` at `0x180005aa5`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a20`
- `OLEAUT32!__imp_SysFreeString` at `0x180005aa5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000595a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000595a`
- `OLEAUT32!__imp_VariantInit` at `0x180005989`
- `OLEAUT32!__imp_VariantInit` at `0x180005a5e`
- `OLEAUT32!__imp_VariantInit` at `0x180005989`
- `OLEAUT32!__imp_VariantInit` at `0x180005a5e`
- `OLEAUT32!__imp_VariantClear` at `0x180005a16`
- `OLEAUT32!__imp_VariantClear` at `0x180005b23`
- `OLEAUT32!__imp_VariantClear` at `0x180005a16`
- `OLEAUT32!__imp_VariantClear` at `0x180005b23`
- `OLEAUT32!__imp_VariantCopy` at `0x180005a0a`
- `OLEAUT32!__imp_VariantCopy` at `0x180005a0a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180005a74`
- `OLEAUT32!__imp_VariantChangeType` at `0x180005a74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemDispatchMgr::InvokeWbemProperty(
        CWbemDispatchMgr *this,
        int a2,
        __int16 a3,
        struct tagDISPPARAMS *a4,
        VARIANTARG *pvargDest,
        struct tagEXCEPINFO *a6,
        unsigned int *a7)
{
  int v8; // r10d
  HRESULT scode; // esi
  __int64 v11; // r8
  VARIANTARG *v12; // r12
  unsigned __int16 *v13; // rdi
  __int64 *v14; // r8
  __int64 v15; // rbx
  OLECHAR *v16; // rcx
  UINT v17; // eax
  int v18; // ebx
  __int64 v19; // rcx
  struct ISWbemInternalObject *v20; // r8
  const VARIANTARG **p_rgvarg; // rsi
  __int64 i; // rax
  struct tagEXCEPINFO *v24; // rbx
  int *v25; // [rsp+20h] [rbp-71h]
  __int64 v26; // [rsp+50h] [rbp-41h] BYREF
  __int64 v27; // [rsp+58h] [rbp-39h] BYREF
  unsigned __int16 *v28; // [rsp+60h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-29h] BYREF
  VARIANTARG v30; // [rsp+80h] [rbp-11h] BYREF
  int v31; // [rsp+E0h] [rbp+4Fh] BYREF
  struct tagDISPPARAMS *v32; // [rsp+F8h] [rbp+67h]

  v32 = a4;
  v8 = a2;
  scode = -2147467259;
  v11 = *((_QWORD *)this + 8);
  if ( !v11 )
    return (unsigned int)scode;
  v12 = pvargDest;
  if ( (a3 & 2) != 0 )
  {
    if ( !pvargDest )
      return 2147942487LL;
  }
  else
  {
    if ( a4->cArgs - 1 > 1 )
      return 2147614734LL;
    if ( a4->cNamedArgs != 1 || *a4->rgdispidNamedArgs != -3 )
      return 2147614735LL;
  }
  v13 = 0;
  v28 = 0;
  v14 = *(__int64 **)(v11 + 16);
  v15 = *v14;
  while ( 1 )
  {
    if ( (__int64 *)v15 == v14 )
      goto LABEL_21;
    if ( v8 == *(_DWORD *)(v15 + 48) )
      break;
    if ( !*(_BYTE *)(v15 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v15 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v15 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
        {
          if ( v15 != *(_QWORD *)(i + 16) )
            break;
          v15 = i;
        }
        v15 = i;
      }
      else
      {
        v15 = std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min();
      }
    }
  }
  v16 = *(OLECHAR **)(v15 + 32);
  if ( v16 )
  {
    v17 = SysStringLen(v16);
    v13 = SysAllocStringLen(*(const OLECHAR **)(v15 + 32), v17);
    v28 = v13;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  v31 = 0;
  VariantInit(&pvarg);
  v25 = &v31;
  v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 2) + 32LL))(
          *((_QWORD *)this + 2),
          v13,
          0,
          &pvarg);
  if ( v18 >= 0 )
  {
    v19 = *((_QWORD *)this + 3);
    if ( (a3 & 2) != 0 )
    {
      v20 = (struct ISWbemInternalObject *)(v19 + 16);
      if ( !v19 )
        v20 = 0;
      scode = MapFromCIMOMObject(*((struct CSWbemServices **)this + 4), &pvarg, v20, v13, (int)&v31);
      if ( scode >= 0 )
      {
        if ( (v31 & 0x2000) != 0 && (p_rgvarg = (const VARIANTARG **)&v32->rgvarg, v32->cArgs) )
        {
          memset(&v30, 0, sizeof(v30));
          VariantInit(&v30);
          if ( VariantChangeType(&v30, *p_rgvarg, 0, 3u) )
            scode = -2147352571;
          else
            scode = assignArrayElementToVariant(pvarg.parray, pvarg.vt & 0xDFFF, v30.lVal, v12);
          VariantClear(&v30);
        }
        else if ( (pvarg.vt & 0x2000) != 0 )
        {
          scode = ConvertArrayRev(v12, &pvarg);
        }
        else
        {
          scode = VariantCopy(v12, &pvarg);
        }
      }
    }
    else
    {
      v27 = 0;
      scode = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 216LL))(v19, &v27);
      if ( scode >= 0 )
      {
        v26 = 0;
        scode = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64 *))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  v13,
                  0,
                  &v26);
        if ( scode >= 0 )
        {
          v24 = a6;
          LOWORD(v25) = a3;
          scode = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD, int *, struct tagDISPPARAMS *, VARIANTARG *, struct tagEXCEPINFO *, unsigned int *))(*(_QWORD *)v26 + 48LL))(
                    v26,
                    0,
                    &GUID_NULL,
                    0,
                    v25,
                    v32,
                    v12,
                    a6,
                    a7);
          if ( scode < 0 )
          {
            if ( v24 )
              scode = v24->scode;
          }
        }
        ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v26);
      }
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v27);
    }
    VariantClear(&pvarg);
LABEL_21:
    SysFreeString(v13);
    return (unsigned int)scode;
  }
  SysFreeString(v13);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800058c0  mov     [rsp-8+arg_8], rbx
0x1800058c5  mov     [rsp-8+arg_18], r9
0x1800058ca  push    rbp
0x1800058cb  push    rsi
0x1800058cc  push    rdi
0x1800058cd  push    r12
0x1800058cf  push    r13
0x1800058d1  push    r14
0x1800058d3  push    r15
0x1800058d5  lea     rbp, [rsp-0Fh]
0x1800058da  sub     rsp, 0A0h
0x1800058e1  movzx   r13d, r8w
0x1800058e5  mov     r10d, edx
0x1800058e8  mov     r15, rcx
0x1800058eb  mov     esi, 80004005h
0x1800058f0  mov     r8, [rcx+40h]
0x1800058f4  test    r8, r8
0x1800058f7  jz      loc_180005A26
0x1800058fd  mov     r14d, r13d
0x180005900  mov     r12, [rbp+3Fh+pvargDest]
0x180005904  and     r14d, 2
0x180005908  jz      loc_180005ABE
0x18000590e  test    r12, r12
0x180005911  jz      loc_180005AEB
0x180005917  xor     edi, edi
0x180005919  mov     [rbp+3Fh+var_70], rdi
0x18000591d  mov     r8, [r8+10h]
0x180005921  mov     rbx, [r8]
0x180005924  cmp     rbx, r8
0x180005927  jz      loc_180005A1D
0x18000592d  cmp     r10d, [rbx+30h]
0x180005931  jz      short loc_180005951
0x180005933  cmp     byte ptr [rbx+19h], 0
0x180005937  jnz     short loc_180005924
0x180005939  mov     rcx, [rbx+10h]
0x18000593d  cmp     byte ptr [rcx+19h], 0
0x180005941  jnz     loc_180005AF5
0x180005947  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x18000594c  mov     rbx, rax
0x18000594f  jmp     short loc_180005924
0x180005951  mov     rcx, [rbx+20h]; pbstr
0x180005955  test    rcx, rcx
0x180005958  jz      short loc_180005973
0x18000595a  call    cs:__imp_SysStringLen
0x180005960  mov     edx, eax; ui
0x180005962  mov     rcx, [rbx+20h]; strIn
0x180005966  call    cs:__imp_SysAllocStringLen
0x18000596c  mov     rdi, rax
0x18000596f  mov     [rbp+3Fh+var_70], rax
0x180005973  xorps   xmm0, xmm0
0x180005976  xor     eax, eax
0x180005978  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18000597c  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180005980  xor     esi, esi
0x180005982  mov     [rbp+3Fh+arg_0], esi
0x180005985  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180005989  call    cs:__imp_VariantInit
0x18000598f  mov     rcx, [r15+10h]
0x180005993  mov     rax, [rcx]
0x180005996  mov     [rsp+0D0h+var_A8], rsi
0x18000599b  lea     rdx, [rbp+3Fh+arg_0]
0x18000599f  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x1800059a4  lea     r9, [rbp+3Fh+pvarg]
0x1800059a8  xor     r8d, r8d
0x1800059ab  mov     rdx, rdi
0x1800059ae  mov     rax, [rax+20h]
0x1800059b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b7  mov     ebx, eax
0x1800059b9  test    eax, eax
0x1800059bb  js      loc_180005AA2
0x1800059c1  mov     rcx, [r15+18h]
0x1800059c5  test    r14d, r14d
0x1800059c8  jz      loc_180005B2E
0x1800059ce  lea     r8, [rcx+10h]
0x1800059d2  test    rcx, rcx
0x1800059d5  cmovz   r8, rsi; struct ISWbemInternalObject *
0x1800059d9  mov     r9, rdi; unsigned __int16 *
0x1800059dc  lea     rdx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x1800059e0  mov     rcx, [r15+20h]; struct CSWbemServices *
0x1800059e4  call    ?MapFromCIMOMObject@@YAJPEAVCSWbemServices@@PEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z; MapFromCIMOMObject(CSWbemServices *,tagVARIANT *,ISWbemInternalObject *,ushort *,long)
0x1800059e9  mov     esi, eax
0x1800059eb  test    eax, eax
0x1800059ed  js      short loc_180005A12
0x1800059ef  mov     eax, 2000h
0x1800059f4  test    [rbp+3Fh+arg_0], eax
0x1800059f7  jnz     short loc_180005A43
0x1800059f9  lea     rdx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x1800059fd  mov     rcx, r12; struct tagVARIANT *
0x180005a00  test    word ptr [rbp+3Fh+pvarg], ax
0x180005a04  jnz     loc_180005AB2
0x180005a0a  call    cs:__imp_VariantCopy
0x180005a10  mov     esi, eax
0x180005a12  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180005a16  call    cs:__imp_VariantClear
0x180005a1c  nop
0x180005a1d  mov     rcx, rdi; bstrString
0x180005a20  call    cs:__imp_SysFreeString
0x180005a26  mov     eax, esi
0x180005a28  mov     rbx, [rsp+0D0h+arg_8]
0x180005a30  add     rsp, 0A0h
0x180005a37  pop     r15
0x180005a39  pop     r14
0x180005a3b  pop     r13
0x180005a3d  pop     r12
0x180005a3f  pop     rdi
0x180005a40  pop     rsi
0x180005a41  pop     rbp
0x180005a42  retn
0x180005a43  mov     rsi, [rbp+3Fh+arg_18]
0x180005a47  cmp     dword ptr [rsi+10h], 0
0x180005a4b  jbe     short loc_1800059F9
0x180005a4d  xorps   xmm0, xmm0
0x180005a50  xor     eax, eax
0x180005a52  movups  xmmword ptr [rbp+3Fh+var_50], xmm0
0x180005a56  mov     qword ptr [rbp+3Fh+var_50+10h], rax
0x180005a5a  lea     rcx, [rbp+3Fh+var_50]; pvarg
0x180005a5e  call    cs:__imp_VariantInit
0x180005a64  mov     r9d, 3; vt
0x180005a6a  xor     r8d, r8d; wFlags
0x180005a6d  mov     rdx, [rsi]; pvarSrc
0x180005a70  lea     rcx, [rbp+3Fh+var_50]; pvargDest
0x180005a74  call    cs:__imp_VariantChangeType
0x180005a7a  test    eax, eax
0x180005a7c  jnz     loc_180005B1A
0x180005a82  movzx   edx, word ptr [rbp+3Fh+pvarg]
0x180005a86  mov     eax, 0DFFFh
0x180005a8b  and     dx, ax; unsigned __int16
0x180005a8e  mov     r9, r12; struct tagVARIANT *
0x180005a91  mov     r8d, dword ptr [rbp+3Fh+var_50+8]; int
0x180005a95  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x180005a99  call    ?assignArrayElementToVariant@@YAJPEAUtagSAFEARRAY@@GJPEAUtagVARIANT@@@Z; assignArrayElementToVariant(tagSAFEARRAY *,ushort,long,tagVARIANT *)
0x180005a9e  mov     esi, eax
0x180005aa0  jmp     short loc_180005B1F
0x180005aa2  mov     rcx, rdi; bstrString
0x180005aa5  call    cs:__imp_SysFreeString
0x180005aab  mov     eax, ebx
0x180005aad  jmp     loc_180005A28
0x180005ab2  call    ?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z; ConvertArrayRev(tagVARIANT *,tagVARIANT *)
0x180005ab7  mov     esi, eax
0x180005ab9  jmp     loc_180005A12
0x180005abe  mov     eax, [r9+10h]
0x180005ac2  dec     eax
0x180005ac4  cmp     eax, 1
0x180005ac7  ja      loc_180005BDF
0x180005acd  cmp     dword ptr [r9+14h], 1
0x180005ad2  jnz     short loc_180005AE1
0x180005ad4  mov     rax, [r9+8]
0x180005ad8  cmp     dword ptr [rax], 0FFFFFFFDh
0x180005adb  jz      loc_180005917
0x180005ae1  mov     eax, 8002000Fh
0x180005ae6  jmp     loc_180005A28
0x180005aeb  mov     eax, 80070057h
0x180005af0  jmp     loc_180005A28
0x180005af5  mov     rax, [rbx+8]
0x180005af9  cmp     byte ptr [rax+19h], 0
0x180005afd  jnz     short loc_180005B12
0x180005aff  cmp     rbx, [rax+10h]
0x180005b03  jnz     short loc_180005B12
0x180005b05  mov     rbx, rax
0x180005b08  mov     rax, [rax+8]
0x180005b0c  cmp     byte ptr [rax+19h], 0
0x180005b10  jz      short loc_180005AFF
0x180005b12  mov     rbx, rax
0x180005b15  jmp     loc_180005924
0x180005b1a  mov     esi, 80020005h
0x180005b1f  lea     rcx, [rbp+3Fh+var_50]; pvarg
0x180005b23  call    cs:__imp_VariantClear
0x180005b29  jmp     loc_180005A12
0x180005b2e  mov     [rbp+3Fh+var_78], rsi
0x180005b32  mov     rax, [rcx]
0x180005b35  lea     rdx, [rbp+3Fh+var_78]
0x180005b39  mov     rax, [rax+0D8h]
0x180005b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b45  mov     esi, eax
0x180005b47  test    eax, eax
0x180005b49  js      loc_180005BD1
0x180005b4f  mov     [rbp+3Fh+var_80], 0
0x180005b57  mov     rcx, [rbp+3Fh+var_78]
0x180005b5b  mov     rax, [rcx]
0x180005b5e  lea     r9, [rbp+3Fh+var_80]
0x180005b62  xor     r8d, r8d
0x180005b65  mov     rdx, rdi
0x180005b68  mov     rax, [rax+40h]
0x180005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b71  mov     esi, eax
0x180005b73  test    eax, eax
0x180005b75  js      short loc_180005BC7
0x180005b77  mov     rcx, [rbp+3Fh+var_80]
0x180005b7b  mov     rax, [rcx]
0x180005b7e  mov     rdx, [rbp+3Fh+arg_30]
0x180005b82  mov     [rsp+0D0h+var_90], rdx
0x180005b87  mov     rbx, [rbp+3Fh+arg_28]
0x180005b8b  mov     [rsp+0D0h+var_98], rbx
0x180005b90  mov     [rsp+0D0h+var_A0], r12
0x180005b95  mov     rsi, [rbp+3Fh+arg_18]
0x180005b99  mov     [rsp+0D0h+var_A8], rsi
0x180005b9e  mov     word ptr [rsp+0D0h+var_B0], r13w
0x180005ba4  xor     r9d, r9d
0x180005ba7  lea     r8, GUID_NULL
0x180005bae  xor     edx, edx
0x180005bb0  mov     rax, [rax+30h]
0x180005bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb9  mov     esi, eax
0x180005bbb  test    eax, eax
0x180005bbd  jns     short loc_180005BC7
0x180005bbf  test    rbx, rbx
0x180005bc2  jz      short loc_180005BC7
0x180005bc4  mov     esi, [rbx+38h]
0x180005bc7  lea     rcx, [rbp+3Fh+var_80]
0x180005bcb  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180005bd0  nop
0x180005bd1  lea     rcx, [rbp+3Fh+var_78]
0x180005bd5  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180005bda  jmp     loc_180005A12
0x180005bdf  mov     eax, 8002000Eh
0x180005be4  jmp     loc_180005A28
```
