# WdcMemoryWidget::Render(void)

- ea: `0x180004b98`
- end: `0x180004f9a`
- name: `?Render@WdcMemoryWidget@@QEAAJXZ`
- size: `1026`
- prototype: `__int64 __fastcall(WdcMemoryWidget *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f6cc`

## callees

- `0x180004b98`
- `0x180004fa0`
- `0x18000519c`
- `0x180006a80`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004c41`
- `KERNEL32!LeaveCriticalSection` at `0x180004c41`
- `KERNEL32!TryEnterCriticalSection` at `0x180004bf2`
- `KERNEL32!TryEnterCriticalSection` at `0x180004bf2`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180004f74`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180004f74`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180004e4c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180004e4c`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180004e63`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180004e63`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180004ec6`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180004ee9`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180004ec6`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180004ee9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180004eda`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180004efd`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180004eda`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180004efd`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180004f35`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180004f35`
- `DUI70!?Create@TableLayout@DirectUI@@SAJHPEAHPEAPEAVValue@2@@Z` at `0x180004f13`
- `DUI70!?Create@TableLayout@DirectUI@@SAJHPEAHPEAPEAVValue@2@@Z` at `0x180004f13`
- `DUI70!?LayoutProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180004f24`

## pseudocode

```c
__int64 __fastcall WdcMemoryWidget::Render(WdcMemoryWidget *this)
{
  __int64 v1; // rbx
  unsigned int v3; // ebx
  bool v4; // zf
  unsigned __int64 v5; // rsi
  __int64 v6; // r8
  unsigned int v7; // ecx
  unsigned __int64 v8; // rsi
  int v9; // r15d
  int v10; // edx
  int v11; // r14d
  int v12; // r12d
  int v13; // esi
  int v14; // eax
  WdcDataValue *v15; // rcx
  WdcDataValue *v16; // rcx
  WdcStringMap *v17; // rcx
  int v18; // eax
  const char *v19; // rdx
  int v20; // r8d
  const char *v21; // rdx
  unsigned __int16 *v22; // rsi
  int v23; // r8d
  unsigned int i; // r14d
  int v25; // eax
  DirectUI::Element *v26; // rcx
  DirectUI::Element *v27; // rcx
  __int64 *v28; // rdx
  __int64 v30; // [rsp+20h] [rbp-50h]
  _QWORD v31[4]; // [rsp+30h] [rbp-40h]
  unsigned __int64 v32; // [rsp+50h] [rbp-20h]
  struct DirectUI::Value *v33; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v34; // [rsp+A8h] [rbp+38h] BYREF

  v1 = *((_QWORD *)this + 4);
  v32 = 0;
  v34 = 0;
  v33 = 0;
  if ( !v1 )
    return (unsigned int)-2147418113;
  if ( !*(_DWORD *)(v1 + 48) || !TryEnterCriticalSection((LPCRITICAL_SECTION)(v1 + 8)) )
  {
    v3 = -2147467259;
    goto LABEL_44;
  }
  v4 = *(_DWORD *)(v1 + 48) == 0;
  v5 = *(_QWORD *)(v1 + 9392);
  v31[0] = *(_QWORD *)(v1 + 9352);
  v31[1] = *(_QWORD *)(v1 + 9368);
  v31[2] = *(_QWORD *)(v1 + 9376);
  v31[3] = *(_QWORD *)(v1 + 9384);
  v32 = v5;
  if ( !v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
  v6 = 0;
  do
  {
    *((_DWORD *)this + v6 + 95) = v31[(int)v6] >> 20;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (int)v6 < 4 );
  v7 = *((_DWORD *)this + 95);
  v8 = v5 >> 10;
  *((_DWORD *)this + 99) = v8;
  if ( (unsigned int)v8 < v7 )
    *((_DWORD *)this + 99) = v7;
  v9 = *((_DWORD *)this + 97);
  v10 = *((_DWORD *)this + 98);
  v11 = *((_DWORD *)this + 96);
  v12 = v10 + v9;
  if ( v7 < v10 + v9 + v11 )
    v13 = 0;
  else
    v13 = v7 - v10 - v9 - v11;
  if ( !v7 )
  {
    v3 = -2147467259;
    goto LABEL_46;
  }
  v14 = WdcMemoryWidget::SetBarWidths(this);
  v3 = v14;
  if ( v14 >= 0 )
  {
    v15 = (WdcDataValue *)*((_QWORD *)this + 2);
    if ( !v15
      || (v14 = WdcDataValue::SetValue(v15, 0x8102u, 1.0, 100.0 / (double)*((int *)this + 95), (double)v13),
          v3 = v14,
          v14 >= 0) )
    {
      v16 = (WdcDataValue *)*((_QWORD *)this + 3);
      if ( !v16
        || (v14 = WdcDataValue::SetValue(v16, 0x8103u, 1.0, 100.0 / (double)*((int *)this + 95), (double)v12),
            v3 = v14,
            v14 >= 0) )
      {
        *((_DWORD *)this + 87) = *((_DWORD *)this + 96);
        *((_DWORD *)this + 88) = *((_DWORD *)this + 97);
        *((_DWORD *)this + 89) = *((_DWORD *)this + 98);
        *((_DWORD *)this + 86) = v13;
        v17 = (WdcStringMap *)*((unsigned int *)this + 95);
        *((_DWORD *)this + 92) = v9 + v11;
        *((_DWORD *)this + 90) = (_DWORD)v17;
        *((_DWORD *)this + 91) = v12;
        v18 = *((_DWORD *)this + 99);
        *((_DWORD *)this + 93) = v18;
        *((_DWORD *)this + 94) = v18 - (_DWORD)v17;
        v14 = WdcStringMap::LoadStringW(v17, 0x8104u, &v34);
        v3 = v14;
        if ( v14 >= 0 )
        {
          v22 = (unsigned __int16 *)WdcAlloc(0x800u, v19, v20);
          if ( !v22 )
          {
            v3 = -2147024882;
LABEL_44:
            LODWORD(v30) = v3;
            goto LABEL_45;
          }
          *v22 = 0;
          for ( i = 0; i < 9; ++i )
          {
            v25 = StringCchPrintfW(v22, 0x400u, v34, *((unsigned int *)this + (int)i + 86));
            v3 = v25;
            if ( v25 >= 0 )
            {
              v26 = (DirectUI::Element *)*((_QWORD *)this + (int)i + 32);
              if ( !v26 )
                continue;
              v25 = DirectUI::Element::SetContentString(v26, v22);
              v3 = v25;
              if ( v25 >= 0 )
              {
                v25 = DirectUI::Element::SetAccName(*((DirectUI::Element **)this + (int)i + 32), v22);
                v3 = v25;
                if ( v25 >= 0 )
                  continue;
              }
            }
            LODWORD(v30) = v25;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
              "WdcMemoryWidget::Render",
              0,
              L"FAILURE: 0x%08x",
              v30);
            goto LABEL_42;
          }
          v27 = (DirectUI::Element *)*((_QWORD *)this + 41);
          if ( v27 && *((_QWORD *)this + 42) )
          {
            if ( *((_DWORD *)this + 99) == *((_DWORD *)this + 95) )
            {
              if ( !DirectUI::Element::GetLayoutPos(v27) )
              {
                DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 41), -3);
                v28 = qword_1800B25B0;
                goto LABEL_40;
              }
            }
            else if ( DirectUI::Element::GetLayoutPos(v27) == -3 )
            {
              DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 41), 0);
              v28 = qword_1800B2550;
LABEL_40:
              DirectUI::TableLayout::Create(23, (int *)v28, &v33);
              v3 = 0;
              if ( v33 )
                DirectUI::Element::SetValue(
                  *((DirectUI::Element **)this + 42),
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LayoutProp,
                  1,
                  v33);
            }
          }
LABEL_42:
          WdcFree(v22, v21, v23);
          goto LABEL_46;
        }
      }
    }
  }
  LODWORD(v30) = v14;
LABEL_45:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
    "WdcMemoryWidget::Render",
    0,
    L"FAILURE: 0x%08x",
    v30);
LABEL_46:
  if ( v33 )
    DirectUI::Value::Release(v33);
  return v3;
}

```

## disassembly

```asm
0x180004b98  mov     [rsp-28h+arg_10], rbx
0x180004b9d  mov     [rsp-28h+arg_18], rsi
0x180004ba2  push    rbp
0x180004ba3  push    rdi
0x180004ba4  push    r12
0x180004ba6  push    r14
0x180004ba8  push    r15
0x180004baa  mov     rbp, rsp
0x180004bad  sub     rsp, 70h
0x180004bb1  mov     rbx, [rcx+20h]
0x180004bb5  mov     rdi, rcx
0x180004bb8  movaps  [rsp+70h+var_10], xmm6
0x180004bbd  mov     [rbp+var_20], 0
0x180004bc5  mov     [rbp+arg_8], 0
0x180004bcd  mov     [rbp+arg_0], 0
0x180004bd5  test    rbx, rbx
0x180004bd8  jnz     short loc_180004BE4
0x180004bda  mov     ebx, 8000FFFFh
0x180004bdf  jmp     loc_180004F7A
0x180004be4  cmp     dword ptr [rbx+30h], 0
0x180004be8  jz      loc_180004F45
0x180004bee  lea     rcx, [rbx+8]; lpCriticalSection
0x180004bf2  call    cs:__imp_TryEnterCriticalSection
0x180004bf8  test    eax, eax
0x180004bfa  jz      loc_180004F45
0x180004c00  cmp     dword ptr [rbx+30h], 0
0x180004c04  mov     rax, [rbx+2488h]
0x180004c0b  mov     rsi, [rbx+24B0h]
0x180004c12  mov     [rbp+var_40], rax
0x180004c16  mov     rax, [rbx+2498h]
0x180004c1d  mov     [rbp+var_38], rax
0x180004c21  mov     rax, [rbx+24A0h]
0x180004c28  mov     [rbp+var_30], rax
0x180004c2c  mov     rax, [rbx+24A8h]
0x180004c33  mov     [rbp+var_28], rax
0x180004c37  mov     [rbp+var_20], rsi
0x180004c3b  jz      short loc_180004C47
0x180004c3d  lea     rcx, [rbx+8]; lpCriticalSection
0x180004c41  call    cs:__imp_LeaveCriticalSection
0x180004c47  xor     r8d, r8d
0x180004c4a  lea     eax, ds:0[r8*8]
0x180004c52  movsxd  rcx, eax
0x180004c55  mov     rdx, [rbp+rcx+var_40]
0x180004c5a  shr     rdx, 14h
0x180004c5e  mov     [rdi+r8*4+17Ch], edx
0x180004c66  inc     r8d
0x180004c69  cmp     r8d, 4
0x180004c6d  jl      short loc_180004C4A
0x180004c6f  mov     ecx, [rdi+17Ch]
0x180004c75  shr     rsi, 0Ah
0x180004c79  mov     [rdi+18Ch], esi
0x180004c7f  cmp     esi, ecx
0x180004c81  jnb     short loc_180004C89
0x180004c83  mov     [rdi+18Ch], ecx
0x180004c89  mov     r15d, [rdi+184h]
0x180004c90  mov     edx, [rdi+188h]
0x180004c96  mov     r14d, [rdi+180h]
0x180004c9d  lea     r12d, [rdx+r15]
0x180004ca1  lea     eax, [r12+r14]
0x180004ca5  cmp     ecx, eax
0x180004ca7  jb      short loc_180004CB5
0x180004ca9  mov     esi, ecx
0x180004cab  sub     esi, edx
0x180004cad  sub     esi, r15d
0x180004cb0  sub     esi, r14d
0x180004cb3  jmp     short loc_180004CB7
0x180004cb5  xor     esi, esi
0x180004cb7  test    ecx, ecx
0x180004cb9  jnz     short loc_180004CC5
0x180004cbb  mov     ebx, 80004005h
0x180004cc0  jmp     loc_180004F6B
0x180004cc5  mov     rcx, rdi; this
0x180004cc8  call    ?SetBarWidths@WdcMemoryWidget@@QEAAJXZ; WdcMemoryWidget::SetBarWidths(void)
0x180004ccd  mov     ebx, eax
0x180004ccf  test    eax, eax
0x180004cd1  jns     short loc_180004CDC
0x180004cd3  mov     dword ptr [rsp+70h+var_50], eax
0x180004cd7  jmp     loc_180004F4E
0x180004cdc  mov     rcx, [rdi+10h]; this
0x180004ce0  movsd   xmm6, cs:__real@4059000000000000
0x180004ce8  test    rcx, rcx
0x180004ceb  jz      short loc_180004D2A
0x180004ced  movsd   xmm2, cs:__real@3ff0000000000000; double
0x180004cf5  xorps   xmm1, xmm1
0x180004cf8  mov     eax, esi
0x180004cfa  xorps   xmm0, xmm0
0x180004cfd  movaps  xmm3, xmm6
0x180004d00  mov     edx, 8102h; unsigned int
0x180004d05  cvtsi2sd xmm1, rax
0x180004d0a  mov     eax, [rdi+17Ch]
0x180004d10  cvtsi2sd xmm0, rax
0x180004d15  movsd   [rsp+70h+var_50], xmm1; double
0x180004d1b  divsd   xmm3, xmm0; double
0x180004d1f  call    ?SetValue@WdcDataValue@@QEAAJKNNN@Z; WdcDataValue::SetValue(ulong,double,double,double)
0x180004d24  mov     ebx, eax
0x180004d26  test    eax, eax
0x180004d28  js      short loc_180004CD3
0x180004d2a  mov     rcx, [rdi+18h]; this
0x180004d2e  test    rcx, rcx
0x180004d31  jz      short loc_180004D75
0x180004d33  movsd   xmm2, cs:__real@3ff0000000000000; double
0x180004d3b  xorps   xmm1, xmm1
0x180004d3e  mov     eax, r12d
0x180004d41  xorps   xmm0, xmm0
0x180004d44  mov     edx, 8103h; unsigned int
0x180004d49  cvtsi2sd xmm1, rax
0x180004d4e  mov     eax, [rdi+17Ch]
0x180004d54  cvtsi2sd xmm0, rax
0x180004d59  movsd   [rsp+70h+var_50], xmm1; double
0x180004d5f  divsd   xmm6, xmm0
0x180004d63  movaps  xmm3, xmm6; double
0x180004d66  call    ?SetValue@WdcDataValue@@QEAAJKNNN@Z; WdcDataValue::SetValue(ulong,double,double,double)
0x180004d6b  mov     ebx, eax
0x180004d6d  test    eax, eax
0x180004d6f  js      loc_180004CD3
0x180004d75  mov     eax, [rdi+180h]
0x180004d7b  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180004d7f  mov     [rdi+15Ch], eax
0x180004d85  mov     edx, 8104h; unsigned int
0x180004d8a  mov     eax, [rdi+184h]
0x180004d90  mov     [rdi+160h], eax
0x180004d96  mov     eax, [rdi+188h]
0x180004d9c  mov     [rdi+164h], eax
0x180004da2  lea     eax, [r15+r14]
0x180004da6  mov     [rdi+158h], esi
0x180004dac  mov     ecx, [rdi+17Ch]; this
0x180004db2  mov     [rdi+170h], eax
0x180004db8  mov     [rdi+168h], ecx
0x180004dbe  mov     [rdi+16Ch], r12d
0x180004dc5  mov     eax, [rdi+18Ch]
0x180004dcb  mov     [rdi+174h], eax
0x180004dd1  sub     eax, ecx
0x180004dd3  mov     [rdi+178h], eax
0x180004dd9  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x180004dde  mov     ebx, eax
0x180004de0  test    eax, eax
0x180004de2  js      loc_180004CD3
0x180004de8  mov     ecx, 800h; dwBytes
0x180004ded  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180004df2  mov     rsi, rax
0x180004df5  test    rax, rax
0x180004df8  jnz     short loc_180004E04
0x180004dfa  mov     ebx, 8007000Eh
0x180004dff  jmp     loc_180004F4A
0x180004e04  xor     eax, eax
0x180004e06  mov     [rsi], ax
0x180004e09  xor     r14d, r14d
0x180004e0c  lea     r12d, [rax+1]
0x180004e10  cmp     r14d, 9
0x180004e14  jnb     loc_180004E9A
0x180004e1a  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180004e1e  mov     edx, 400h; unsigned __int64
0x180004e23  movsxd  r15, r14d
0x180004e26  mov     rcx, rsi; unsigned __int16 *
0x180004e29  mov     r9d, [rdi+r15*4+158h]
0x180004e31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004e36  mov     ebx, eax
0x180004e38  test    eax, eax
0x180004e3a  js      short loc_180004E74
0x180004e3c  mov     rcx, [rdi+r15*8+100h]
0x180004e44  test    rcx, rcx
0x180004e47  jz      short loc_180004E6F
0x180004e49  mov     rdx, rsi
0x180004e4c  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180004e52  mov     ebx, eax
0x180004e54  test    eax, eax
0x180004e56  js      short loc_180004E74
0x180004e58  mov     rcx, [rdi+r15*8+100h]
0x180004e60  mov     rdx, rsi
0x180004e63  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180004e69  mov     ebx, eax
0x180004e6b  test    eax, eax
0x180004e6d  js      short loc_180004E74
0x180004e6f  add     r14d, r12d
0x180004e72  jmp     short loc_180004E10
0x180004e74  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180004e7b  mov     dword ptr [rsp+70h+var_50], eax
0x180004e7f  xor     r8d, r8d; int
0x180004e82  lea     rdx, aWdcmemorywidge; "WdcMemoryWidget::Render"
0x180004e89  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180004e90  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180004e95  jmp     loc_180004F3B
0x180004e9a  mov     rcx, [rdi+148h]
0x180004ea1  test    rcx, rcx
0x180004ea4  jz      loc_180004F3B
0x180004eaa  cmp     qword ptr [rdi+150h], 0
0x180004eb2  jz      loc_180004F3B
0x180004eb8  mov     eax, [rdi+17Ch]
0x180004ebe  cmp     [rdi+18Ch], eax
0x180004ec4  jnz     short loc_180004EE9
0x180004ec6  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x180004ecc  test    eax, eax
0x180004ece  jnz     short loc_180004F3B
0x180004ed0  mov     rcx, [rdi+148h]
0x180004ed7  lea     edx, [rax-3]
0x180004eda  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180004ee0  lea     rdx, qword_1800B25B0
0x180004ee7  jmp     short loc_180004F0A
0x180004ee9  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x180004eef  cmp     eax, 0FFFFFFFDh
0x180004ef2  jnz     short loc_180004F3B
0x180004ef4  mov     rcx, [rdi+148h]
0x180004efb  xor     edx, edx
0x180004efd  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180004f03  lea     rdx, qword_1800B2550
0x180004f0a  lea     r8, [rbp+arg_0]
0x180004f0e  mov     ecx, 17h
0x180004f13  call    cs:__imp_?Create@TableLayout@DirectUI@@SAJHPEAHPEAPEAVValue@2@@Z; DirectUI::TableLayout::Create(int,int *,DirectUI::Value * *)
0x180004f19  mov     r9, [rbp+arg_0]
0x180004f1d  xor     ebx, ebx
0x180004f1f  test    r9, r9
0x180004f22  jz      short loc_180004F3B
0x180004f24  mov     rdx, cs:__imp_?LayoutProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LayoutProp(void)
0x180004f2b  mov     r8d, r12d
0x180004f2e  mov     rcx, [rdi+150h]
0x180004f35  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180004f3b  mov     rcx, rsi; void *
0x180004f3e  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180004f43  jmp     short loc_180004F6B
0x180004f45  mov     ebx, 80004005h
0x180004f4a  mov     dword ptr [rsp+70h+var_50], ebx
0x180004f4e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180004f55  xor     r8d, r8d; int
0x180004f58  lea     rdx, aWdcmemorywidge; "WdcMemoryWidget::Render"
0x180004f5f  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180004f66  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180004f6b  mov     rcx, [rbp+arg_0]
0x180004f6f  test    rcx, rcx
0x180004f72  jz      short loc_180004F7A
0x180004f74  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180004f7a  movaps  xmm6, [rsp+70h+var_10]
0x180004f7f  lea     r11, [rsp+70h+var_s0]
0x180004f84  mov     rsi, [r11+48h]
0x180004f88  mov     eax, ebx
0x180004f8a  mov     rbx, [r11+40h]
0x180004f8e  mov     rsp, r11
0x180004f91  pop     r15
0x180004f93  pop     r14
0x180004f95  pop     r12
0x180004f97  pop     rdi
0x180004f98  pop     rbp
0x180004f99  retn
```
