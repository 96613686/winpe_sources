# WdcDataCollectorNode::GetAlertItem(PROPERTY_EXCHANGE,tagLVITEMW *)

- ea: `0x1800627d0`
- end: `0x180062a46`
- name: `?GetAlertItem@WdcDataCollectorNode@@CAJW4PROPERTY_EXCHANGE@@PEAUtagLVITEMW@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(char, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005b594`

## callees

- `0x180008ab0`
- `0x18000b854`
- `0x180040730`
- `0x1800627d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006292e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062954`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006292e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062954`
- `OLEAUT32!__imp_SysAllocString` at `0x180062991`
- `OLEAUT32!__imp_SysAllocString` at `0x180062991`
- `OLEAUT32!__imp_VariantInit` at `0x1800627fe`
- `OLEAUT32!__imp_VariantInit` at `0x1800627fe`
- `OLEAUT32!__imp_VariantClear` at `0x180062980`
- `OLEAUT32!__imp_VariantClear` at `0x180062a29`
- `OLEAUT32!__imp_VariantClear` at `0x180062980`
- `OLEAUT32!__imp_VariantClear` at `0x180062a29`
- `OLEAUT32!__imp_VariantCopy` at `0x18006282b`
- `OLEAUT32!__imp_VariantCopy` at `0x18006282b`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800628a4`
- `OLEAUT32!__imp_VariantChangeType` at `0x180062a01`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800628a4`
- `OLEAUT32!__imp_VariantChangeType` at `0x180062a01`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorNode::GetAlertItem(char a1, __int64 a2)
{
  unsigned int v4; // edi
  const char *v5; // rdx
  int v6; // r8d
  const VARIANTARG *v7; // rdx
  HRESULT v8; // eax
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdx
  VARIANTARG *v11; // rbx
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // rdi
  double v15; // xmm6_8
  BSTR v16; // rax
  __int64 v18; // [rsp+20h] [rbp-48h]
  __int64 v19; // [rsp+20h] [rbp-48h]
  VARIANTARG pvargDest; // [rsp+30h] [rbp-38h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  v4 = 0;
  VariantInit(&pvargDest);
  if ( a1 == 1 )
  {
    v11 = (VARIANTARG *)WdcAlloc(0x18u, v5, v6);
    if ( v11 )
    {
      *(_OWORD *)&v11->vt = 0;
      v11->pRecInfo = 0;
      v12 = *(const wchar_t **)(a2 + 24);
      *(_DWORD *)a2 |= 4u;
      *(_QWORD *)(a2 + 40) = v11;
      v13 = wcsrchr(v12, 0x3Eu);
      v14 = v13;
      if ( v13 )
      {
        v15 = DOUBLE_1_0;
        *v13 = 0;
      }
      else
      {
        v14 = wcsrchr(*(const wchar_t **)(a2 + 24), 0x3Cu);
        if ( !v14 )
        {
          v4 = 0;
          goto LABEL_26;
        }
        v15 = DOUBLE_N1_0;
        *v14 = 0;
      }
      do
        ++v14;
      while ( *v14 == 32 );
      VariantClear(v11);
      v11->llVal = 0;
      v16 = SysAllocString(v14);
      if ( v16 )
      {
        v11->llVal = (LONGLONG)v16;
        v11->vt = 8;
        v8 = VariantChangeType(v11, v11, 4u, 5u);
        v4 = v8;
        if ( v8 >= 0 )
        {
          v11->dblVal = v15 * v11->dblVal;
          goto LABEL_26;
        }
        goto LABEL_23;
      }
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      LODWORD(v19) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v19);
    }
    v4 = -2147024882;
    LODWORD(v18) = -2147024882;
LABEL_14:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
      "WdcDataCollectorNode::GetAlertItem",
      0,
      L"FAILURE: 0x%08x",
      v18);
    goto LABEL_26;
  }
  if ( a1 != 2 )
    goto LABEL_26;
  v7 = *(const VARIANTARG **)(a2 + 40);
  if ( !v7 )
    goto LABEL_26;
  v8 = VariantCopy(&pvargDest, v7);
  v4 = v8;
  if ( v8 < 0 )
    goto LABEL_23;
  v9 = *(unsigned __int16 **)(a2 + 24);
  v10 = *(int *)(a2 + 32);
  if ( pvargDest.dblVal >= 0.0 )
  {
    v8 = StringCchCatW(v9, v10, L">");
    v4 = v8;
    if ( v8 >= 0 )
      goto LABEL_9;
LABEL_23:
    LODWORD(v18) = v8;
    goto LABEL_14;
  }
  v8 = StringCchCatW(v9, v10, L"<");
  v4 = v8;
  if ( v8 < 0 )
    goto LABEL_23;
  pvargDest.dblVal = pvargDest.dblVal * -1.0;
LABEL_9:
  v8 = VariantChangeType(&pvargDest, &pvargDest, 4u, 8u);
  v4 = v8;
  if ( v8 < 0 )
    goto LABEL_23;
  v8 = StringCchCatW(*(unsigned __int16 **)(a2 + 24), *(int *)(a2 + 32), pvargDest.bstrVal);
  v4 = v8;
  if ( v8 < 0 )
    goto LABEL_23;
LABEL_26:
  VariantClear(&pvargDest);
  return v4;
}

```

## disassembly

```asm
0x1800627d0  mov     r11, rsp
0x1800627d3  mov     [r11+8], rbx
0x1800627d7  mov     [r11+10h], rsi
0x1800627db  push    rdi
0x1800627dc  sub     rsp, 60h
0x1800627e0  xorps   xmm0, xmm0
0x1800627e3  movaps  [rsp+68h+var_18], xmm6
0x1800627e8  mov     ebx, ecx
0x1800627ea  xor     eax, eax
0x1800627ec  movups  xmmword ptr [rsp+68h+pvargDest], xmm0
0x1800627f1  lea     rcx, [r11-38h]; pvarg
0x1800627f5  mov     [r11-28h], rax
0x1800627f9  mov     rsi, rdx
0x1800627fc  xor     edi, edi
0x1800627fe  call    cs:__imp_VariantInit
0x180062804  movzx   ecx, bl
0x180062807  sub     ecx, 1
0x18006280a  jz      loc_1800628D5
0x180062810  cmp     ecx, 1
0x180062813  jnz     loc_180062A24
0x180062819  mov     rdx, [rsi+28h]; pvargSrc
0x18006281d  test    rdx, rdx
0x180062820  jz      loc_180062A24
0x180062826  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x18006282b  call    cs:__imp_VariantCopy
0x180062831  mov     edi, eax
0x180062833  test    eax, eax
0x180062835  js      loc_180062A0D
0x18006283b  mov     rcx, [rsi+18h]; unsigned __int16 *
0x18006283f  xorps   xmm0, xmm0
0x180062842  comisd  xmm0, qword ptr [rsp+68h+pvargDest+8]
0x180062848  movsxd  rdx, dword ptr [rsi+20h]; unsigned __int64
0x18006284c  jbe     short loc_18006287A
0x18006284e  lea     r8, Delimiter; "<"
0x180062855  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006285a  mov     edi, eax
0x18006285c  test    eax, eax
0x18006285e  js      loc_180062A0D
0x180062864  movsd   xmm0, qword ptr [rsp+68h+pvargDest+8]
0x18006286a  mulsd   xmm0, cs:__real@bff0000000000000
0x180062872  movsd   qword ptr [rsp+68h+pvargDest+8], xmm0
0x180062878  jmp     short loc_180062890
0x18006287a  lea     r8, asc_1800941D0; ">"
0x180062881  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180062886  mov     edi, eax
0x180062888  test    eax, eax
0x18006288a  js      loc_180062A0D
0x180062890  mov     r9d, 8; vt
0x180062896  lea     rdx, [rsp+68h+pvargDest]; pvarSrc
0x18006289b  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x1800628a0  lea     r8d, [r9-4]; wFlags
0x1800628a4  call    cs:__imp_VariantChangeType
0x1800628aa  mov     edi, eax
0x1800628ac  test    eax, eax
0x1800628ae  js      loc_180062A0D
0x1800628b4  movsxd  rdx, dword ptr [rsi+20h]; unsigned __int64
0x1800628b8  mov     r8, qword ptr [rsp+68h+pvargDest+8]; unsigned __int16 *
0x1800628bd  mov     rcx, [rsi+18h]; unsigned __int16 *
0x1800628c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800628c6  mov     edi, eax
0x1800628c8  test    eax, eax
0x1800628ca  jns     loc_180062A24
0x1800628d0  jmp     loc_180062A0D
0x1800628d5  mov     ecx, 18h; dwBytes
0x1800628da  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800628df  mov     rbx, rax
0x1800628e2  test    rax, rax
0x1800628e5  jnz     short loc_180062914
0x1800628e7  mov     ebx, 8007000Eh
0x1800628ec  mov     edi, ebx
0x1800628ee  mov     [rsp+68h+var_48], ebx
0x1800628f2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800628f9  xor     r8d, r8d; int
0x1800628fc  lea     rdx, aWdcdatacollect_83; "WdcDataCollectorNode::GetAlertItem"
0x180062903  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18006290a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006290f  jmp     loc_180062A24
0x180062914  xor     eax, eax
0x180062916  xorps   xmm0, xmm0
0x180062919  movups  xmmword ptr [rbx], xmm0
0x18006291c  mov     [rbx+10h], rax
0x180062920  mov     rcx, [rsi+18h]; Str
0x180062924  or      dword ptr [rsi], 4
0x180062927  lea     edx, [rax+3Eh]; Ch
0x18006292a  mov     [rsi+28h], rbx
0x18006292e  call    cs:__imp_wcsrchr
0x180062934  mov     rdi, rax
0x180062937  test    rax, rax
0x18006293a  jz      short loc_18006294B
0x18006293c  movsd   xmm6, cs:__real@3ff0000000000000
0x180062944  xor     ecx, ecx
0x180062946  mov     [rax], cx
0x180062949  jmp     short loc_180062973
0x18006294b  mov     rcx, [rsi+18h]; Str
0x18006294f  mov     edx, 3Ch ; '<'; Ch
0x180062954  call    cs:__imp_wcsrchr
0x18006295a  mov     rdi, rax
0x18006295d  test    rax, rax
0x180062960  jz      loc_180062A22
0x180062966  movsd   xmm6, cs:__real@bff0000000000000
0x18006296e  xor     eax, eax
0x180062970  mov     [rdi], ax
0x180062973  add     rdi, 2
0x180062977  cmp     word ptr [rdi], 20h ; ' '
0x18006297b  jz      short loc_180062973
0x18006297d  mov     rcx, rbx; pvarg
0x180062980  call    cs:__imp_VariantClear
0x180062986  mov     rcx, rdi; psz
0x180062989  mov     qword ptr [rbx+8], 0
0x180062991  call    cs:__imp_SysAllocString
0x180062997  test    rax, rax
0x18006299a  jnz     short loc_1800629E8
0x18006299c  mov     ebx, 8007000Eh
0x1800629a1  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800629a8  xor     r8d, r8d; int
0x1800629ab  mov     [rsp+68h+var_48], ebx
0x1800629af  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800629b6  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800629bd  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800629c2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800629c9  mov     [rsp+68h+var_48], ebx
0x1800629cd  xor     r8d, r8d; int
0x1800629d0  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800629d7  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800629de  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800629e3  jmp     loc_1800628EC
0x1800629e8  mov     [rbx+8], rax
0x1800629ec  mov     word ptr [rbx], 8
0x1800629f1  mov     r9d, 5; vt
0x1800629f7  mov     rdx, rbx; pvarSrc
0x1800629fa  mov     rcx, rbx; pvargDest
0x1800629fd  lea     r8d, [r9-1]; wFlags
0x180062a01  call    cs:__imp_VariantChangeType
0x180062a07  mov     edi, eax
0x180062a09  test    eax, eax
0x180062a0b  jns     short loc_180062A16
0x180062a0d  mov     [rsp+68h+var_48], eax
0x180062a11  jmp     loc_1800628F2
0x180062a16  mulsd   xmm6, qword ptr [rbx+8]
0x180062a1b  movsd   qword ptr [rbx+8], xmm6
0x180062a20  jmp     short loc_180062A24
0x180062a22  xor     edi, edi
0x180062a24  lea     rcx, [rsp+68h+pvargDest]; pvarg
0x180062a29  call    cs:__imp_VariantClear
0x180062a2f  mov     rbx, [rsp+68h+arg_0]
0x180062a34  mov     eax, edi
0x180062a36  mov     rsi, [rsp+68h+arg_8]
0x180062a3b  movaps  xmm6, [rsp+68h+var_18]
0x180062a40  add     rsp, 60h
0x180062a44  pop     rdi
0x180062a45  retn
```
