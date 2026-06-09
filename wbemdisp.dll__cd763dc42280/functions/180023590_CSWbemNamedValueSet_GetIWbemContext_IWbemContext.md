# CSWbemNamedValueSet::GetIWbemContext(IWbemContext * *)

- ea: `0x180023590`
- end: `0x1800237a1`
- name: `?GetIWbemContext@CSWbemNamedValueSet@@UEAAJPEAPEAUIWbemContext@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(CSWbemNamedValueSet *__hidden this, struct IWbemContext **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002ef4`
- `0x180023590`
- `0x180025074`
- `0x180025414`
- `0x180025aa4`
- `0x180025dcc`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023766`
- `OLEAUT32!__imp_SysFreeString` at `0x180023766`
- `OLEAUT32!__imp_VariantInit` at `0x18002360a`
- `OLEAUT32!__imp_VariantInit` at `0x180023648`
- `OLEAUT32!__imp_VariantInit` at `0x1800236e3`
- `OLEAUT32!__imp_VariantInit` at `0x18002360a`
- `OLEAUT32!__imp_VariantInit` at `0x180023648`
- `OLEAUT32!__imp_VariantInit` at `0x1800236e3`
- `OLEAUT32!__imp_VariantClear` at `0x180023734`
- `OLEAUT32!__imp_VariantClear` at `0x18002375c`
- `OLEAUT32!__imp_VariantClear` at `0x180023778`
- `OLEAUT32!__imp_VariantClear` at `0x180023734`
- `OLEAUT32!__imp_VariantClear` at `0x18002375c`
- `OLEAUT32!__imp_VariantClear` at `0x180023778`
- `OLEAUT32!__imp_VariantCopy` at `0x1800236ac`
- `OLEAUT32!__imp_VariantCopy` at `0x1800236b4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800236ac`
- `OLEAUT32!__imp_VariantCopy` at `0x1800236b4`

## pseudocode

```c
__int64 __fastcall CSWbemNamedValueSet::GetIWbemContext(CSWbemNamedValueSet *this, struct IWbemContext **a2)
{
  int v2; // ebx
  __int64 v4; // rcx
  HRESULT v5; // eax
  HRESULT v6; // eax
  unsigned __int16 AcceptableQualType; // ax
  __int16 v8; // cx
  VARIANTARG *p_pvargDest; // r9
  VARIANTARG pvargDest; // [rsp+30h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-1h] BYREF
  VARIANTARG v13; // [rsp+60h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+6Fh] BYREF

  v2 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = *((_QWORD *)this + 5);
    if ( v4 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
      if ( v2 >= 0 )
      {
        v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*a2)->lpVtbl->BeginEnumeration)(*a2, 0);
        if ( v2 >= 0 )
        {
          bstrString = 0;
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          while ( 1 )
          {
            if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, BSTR *, VARIANTARG *))(*a2)->lpVtbl->Next)(
                   *a2,
                   0,
                   &bstrString,
                   &pvarg) )
            {
              ((void (__fastcall *)(_QWORD))(*a2)->lpVtbl->EndEnumeration)(*a2);
              return (unsigned int)v2;
            }
            memset(&pvargDest, 0, sizeof(pvargDest));
            VariantInit(&pvargDest);
            if ( pvarg.vt == 8204 )
              break;
            if ( pvarg.vt == 9 )
            {
              if ( ConvertDispatchToArray(&pvargDest, &pvarg, 4095, 0, 1u) >= 0 )
                goto LABEL_16;
              v5 = VariantCopy(&pvargDest, &pvarg);
              goto LABEL_9;
            }
            v6 = VariantCopy(&pvargDest, &pvarg);
LABEL_15:
            v2 = v6;
LABEL_16:
            if ( v2 < 0 )
              goto LABEL_25;
            if ( (pvargDest.vt & 0x9FFF) != 0xD )
            {
              memset(&v13, 0, sizeof(v13));
              VariantInit(&v13);
              AcceptableQualType = GetAcceptableQualType(pvargDest.vt);
              if ( AcceptableQualType == v8 )
              {
                p_pvargDest = &pvargDest;
LABEL_22:
                v2 = ((__int64 (__fastcall *)(_QWORD, BSTR, _QWORD, VARIANTARG *))(*a2)->lpVtbl->SetValue)(
                       *a2,
                       bstrString,
                       0,
                       p_pvargDest);
              }
              else
              {
                v2 = QualifierVariantChangeType(&v13, &pvargDest, AcceptableQualType);
                if ( v2 >= 0 )
                {
                  p_pvargDest = &v13;
                  goto LABEL_22;
                }
              }
              VariantClear(&v13);
              goto LABEL_25;
            }
            v2 = ((__int64 (__fastcall *)(_QWORD, BSTR, _QWORD, VARIANTARG *))(*a2)->lpVtbl->SetValue)(
                   *a2,
                   bstrString,
                   0,
                   &pvargDest);
LABEL_25:
            VariantClear(&pvargDest);
            SysFreeString(bstrString);
            bstrString = 0;
            VariantClear(&pvarg);
          }
          v5 = ConvertArray(&pvargDest, &pvarg, 0, 1u);
LABEL_9:
          v2 = v5;
          if ( v5 < 0 )
            goto LABEL_25;
          v6 = MapToCIMOMObject(&pvargDest);
          goto LABEL_15;
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180023590  push    rbp
0x180023592  push    rbx
0x180023593  push    rdi
0x180023594  push    r14
0x180023596  lea     rbp, [rsp-3Fh]
0x18002359b  sub     rsp, 88h
0x1800235a2  xor     ebx, ebx
0x1800235a4  mov     rdi, rdx
0x1800235a7  test    rdx, rdx
0x1800235aa  jz      loc_180023792
0x1800235b0  mov     [rdx], rbx
0x1800235b3  mov     rcx, [rcx+28h]
0x1800235b7  test    rcx, rcx
0x1800235ba  jz      loc_180023792
0x1800235c0  mov     rax, [rcx]
0x1800235c3  mov     rax, [rax+18h]
0x1800235c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235cc  mov     ebx, eax
0x1800235ce  test    eax, eax
0x1800235d0  js      loc_180023792
0x1800235d6  mov     rcx, [rdi]
0x1800235d9  xor     edx, edx
0x1800235db  mov     rax, [rcx]
0x1800235de  mov     rax, [rax+28h]
0x1800235e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235e7  mov     ebx, eax
0x1800235e9  test    eax, eax
0x1800235eb  js      loc_180023792
0x1800235f1  xorps   xmm0, xmm0
0x1800235f4  mov     [rbp+57h+bstrString], 0
0x1800235fc  xor     eax, eax
0x1800235fe  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023602  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180023606  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002360a  call    cs:__imp_VariantInit
0x180023610  mov     r14d, 1
0x180023616  mov     rcx, [rdi]
0x180023619  lea     r9, [rbp+57h+pvarg]
0x18002361d  lea     r8, [rbp+57h+bstrString]
0x180023621  xor     edx, edx
0x180023623  mov     rax, [rcx]
0x180023626  mov     rax, [rax+30h]
0x18002362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002362f  test    eax, eax
0x180023631  jnz     loc_180023783
0x180023637  xorps   xmm0, xmm0
0x18002363a  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x18002363e  xor     eax, eax
0x180023640  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180023644  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180023648  call    cs:__imp_VariantInit
0x18002364e  mov     eax, 200Ch
0x180023653  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180023657  lea     rcx, [rbp+57h+pvargDest]; struct tagVARIANT *
0x18002365b  cmp     ax, word ptr [rbp+57h+pvarg]
0x18002365f  jnz     short loc_180023681
0x180023661  mov     r9d, r14d; unsigned __int16
0x180023664  xor     r8d, r8d; int
0x180023667  call    ?ConvertArray@@YAJPEAUtagVARIANT@@0HG@Z; ConvertArray(tagVARIANT *,tagVARIANT *,int,ushort)
0x18002366c  mov     ebx, eax
0x18002366e  test    eax, eax
0x180023670  js      loc_180023758
0x180023676  lea     rcx, [rbp+57h+pvargDest]; struct tagVARIANT *
0x18002367a  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x18002367f  jmp     short loc_1800236BA
0x180023681  mov     eax, 9
0x180023686  cmp     ax, word ptr [rbp+57h+pvarg]
0x18002368a  jnz     short loc_1800236B4
0x18002368c  xor     r9d, r9d; int
0x18002368f  mov     [rsp+0A0h+var_80], r14w; unsigned __int16
0x180023695  mov     r8d, 0FFFh; int
0x18002369b  call    ?ConvertDispatchToArray@@YAJPEAUtagVARIANT@@0JHG@Z; ConvertDispatchToArray(tagVARIANT *,tagVARIANT *,long,int,ushort)
0x1800236a0  test    eax, eax
0x1800236a2  jns     short loc_1800236BC
0x1800236a4  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x1800236a8  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x1800236ac  call    cs:__imp_VariantCopy
0x1800236b2  jmp     short loc_18002366C
0x1800236b4  call    cs:__imp_VariantCopy
0x1800236ba  mov     ebx, eax
0x1800236bc  test    ebx, ebx
0x1800236be  js      loc_180023758
0x1800236c4  movzx   eax, word ptr [rbp+57h+pvargDest]
0x1800236c8  and     eax, 0FFFF9FFFh
0x1800236cd  cmp     eax, 0Dh
0x1800236d0  jz      short loc_18002373C
0x1800236d2  xorps   xmm0, xmm0
0x1800236d5  lea     rcx, [rbp+57h+var_40]; pvarg
0x1800236d9  xor     eax, eax
0x1800236db  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x1800236df  mov     qword ptr [rbp+57h+var_40+10h], rax
0x1800236e3  call    cs:__imp_VariantInit
0x1800236e9  movzx   ecx, word ptr [rbp+57h+pvargDest]; unsigned __int16
0x1800236ed  call    ?GetAcceptableQualType@@YAGG@Z; GetAcceptableQualType(ushort)
0x1800236f2  cmp     ax, cx
0x1800236f5  jz      short loc_180023714
0x1800236f7  movzx   r8d, ax; unsigned __int16
0x1800236fb  lea     rdx, [rbp+57h+pvargDest]; struct tagVARIANT *
0x1800236ff  lea     rcx, [rbp+57h+var_40]; struct tagVARIANT *
0x180023703  call    ?QualifierVariantChangeType@@YAJPEAUtagVARIANT@@0G@Z; QualifierVariantChangeType(tagVARIANT *,tagVARIANT *,ushort)
0x180023708  mov     ebx, eax
0x18002370a  test    eax, eax
0x18002370c  js      short loc_180023730
0x18002370e  lea     r9, [rbp+57h+var_40]
0x180023712  jmp     short loc_180023718
0x180023714  lea     r9, [rbp+57h+pvargDest]
0x180023718  mov     rcx, [rdi]
0x18002371b  xor     r8d, r8d
0x18002371e  mov     rdx, [rbp+57h+bstrString]
0x180023722  mov     rax, [rcx]
0x180023725  mov     rax, [rax+40h]
0x180023729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002372e  mov     ebx, eax
0x180023730  lea     rcx, [rbp+57h+var_40]; pvarg
0x180023734  call    cs:__imp_VariantClear
0x18002373a  jmp     short loc_180023758
0x18002373c  mov     rcx, [rdi]
0x18002373f  lea     r9, [rbp+57h+pvargDest]
0x180023743  mov     rdx, [rbp+57h+bstrString]
0x180023747  xor     r8d, r8d
0x18002374a  mov     rax, [rcx]
0x18002374d  mov     rax, [rax+40h]
0x180023751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023756  mov     ebx, eax
0x180023758  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x18002375c  call    cs:__imp_VariantClear
0x180023762  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180023766  call    cs:__imp_SysFreeString
0x18002376c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023770  mov     [rbp+57h+bstrString], 0
0x180023778  call    cs:__imp_VariantClear
0x18002377e  jmp     loc_180023616
0x180023783  mov     rcx, [rdi]
0x180023786  mov     rax, [rcx]
0x180023789  mov     rax, [rax+38h]
0x18002378d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023792  mov     eax, ebx
0x180023794  add     rsp, 88h
0x18002379b  pop     r14
0x18002379d  pop     rdi
0x18002379e  pop     rbx
0x18002379f  pop     rbp
0x1800237a0  retn
```
