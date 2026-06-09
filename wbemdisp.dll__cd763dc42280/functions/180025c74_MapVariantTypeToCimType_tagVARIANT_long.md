# MapVariantTypeToCimType(tagVARIANT *,long)

- ea: `0x180025c74`
- end: `0x180025dc6`
- name: `?MapVariantTypeToCimType@@YA?AW4WbemCimtypeEnum@@PEAUtagVARIANT@@J@Z`
- size: `338`
- prototype: `enum WbemCimtypeEnum __fastcall(struct tagVARIANT *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800229f0`
- `0x1800230a0`

## callees

- `0x180002ef4`
- `0x180025074`
- `0x180025414`
- `0x180025ae8`
- `0x180025c74`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180025ca9`
- `OLEAUT32!__imp_VariantInit` at `0x180025ca9`
- `OLEAUT32!__imp_VariantClear` at `0x180025dae`
- `OLEAUT32!__imp_VariantClear` at `0x180025dae`
- `OLEAUT32!__imp_VariantCopy` at `0x180025cff`
- `OLEAUT32!__imp_VariantCopy` at `0x180025cff`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025d7e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025d7e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025d6a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025d6a`

## pseudocode

```c
__int64 __fastcall MapVariantTypeToCimType(struct tagVARIANT *a1, LONG a2)
{
  unsigned int v3; // ebx
  VARTYPE vt; // cx
  const VARIANTARG *v5; // rdx
  int v6; // edx
  enum WbemCimtypeEnum CIMType; // eax
  int v8; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  LONG plLbound; // [rsp+70h] [rbp+20h] BYREF
  LONG plUbound; // [rsp+78h] [rbp+28h] BYREF

  plUbound = a2;
  v3 = 3;
  if ( a1 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    vt = a1->vt;
    if ( a1->vt < 2u )
    {
LABEL_17:
      VariantClear(&pvarg);
      return v3;
    }
    if ( ((vt - 8204) & 0xBFFF) != 0 )
    {
      v5 = a1;
      if ( ((vt - 9) & 0xBFFF) != 0 )
        goto LABEL_7;
      if ( (unsigned int)ConvertDispatchToArray(&pvarg, a1, 3, 0, 1u) )
      {
        v5 = a1;
LABEL_7:
        if ( VariantCopy(&pvarg, v5) < 0 || (unsigned int)MapToCIMOMObject(&pvarg) )
          goto LABEL_17;
        CIMType = GetCIMType(&pvarg, v6, 0, 0, 0);
        goto LABEL_16;
      }
    }
    else if ( ConvertArray(&pvarg, a1, 0, 1) || (unsigned int)MapToCIMOMObject(&pvarg) )
    {
      goto LABEL_17;
    }
    plLbound = 0;
    plUbound = 0;
    if ( SafeArrayGetLBound(pvarg.parray, 1u, &plLbound) < 0
      || SafeArrayGetUBound(pvarg.parray, 1u, &plUbound) < 0
      || plUbound - plLbound == -1 )
    {
      goto LABEL_17;
    }
    CIMType = GetCIMType(&pvarg, v8, 1, plLbound, plUbound);
LABEL_16:
    v3 = CIMType;
    goto LABEL_17;
  }
  return v3;
}

```

## disassembly

```asm
0x180025c74  mov     [rsp-18h+arg_10], rbx
0x180025c79  mov     [rsp-18h+plUbound], edx
0x180025c7d  push    rbp
0x180025c7e  push    rsi
0x180025c7f  push    rdi
0x180025c80  mov     rbp, rsp
0x180025c83  sub     rsp, 50h
0x180025c87  mov     rsi, rcx
0x180025c8a  mov     ebx, 3
0x180025c8f  test    rcx, rcx
0x180025c92  jz      loc_180025DB4
0x180025c98  xorps   xmm0, xmm0
0x180025c9b  lea     rcx, [rbp+pvarg]; pvarg
0x180025c9f  xor     eax, eax
0x180025ca1  movups  xmmword ptr [rbp+pvarg], xmm0
0x180025ca5  mov     qword ptr [rbp+pvarg+10h], rax
0x180025ca9  call    cs:__imp_VariantInit
0x180025caf  movzx   ecx, word ptr [rsi]
0x180025cb2  cmp     cx, 2
0x180025cb6  jb      loc_180025DAA
0x180025cbc  mov     edx, 200Ch
0x180025cc1  movzx   eax, cx
0x180025cc4  sub     ax, dx
0x180025cc7  mov     edx, 0BFFFh
0x180025ccc  test    dx, ax
0x180025ccf  jz      short loc_180025D2A
0x180025cd1  sub     cx, 9
0x180025cd5  test    dx, cx
0x180025cd8  mov     rdx, rsi; struct tagVARIANT *
0x180025cdb  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180025cdf  jnz     short loc_180025CFF
0x180025ce1  lea     edi, [rbx-2]
0x180025ce4  xor     r9d, r9d; int
0x180025ce7  mov     r8d, ebx; int
0x180025cea  mov     [rsp+50h+var_30], di; unsigned __int16
0x180025cef  call    ?ConvertDispatchToArray@@YAJPEAUtagVARIANT@@0JHG@Z; ConvertDispatchToArray(tagVARIANT *,tagVARIANT *,long,int,ushort)
0x180025cf4  test    eax, eax
0x180025cf6  jz      short loc_180025D52
0x180025cf8  mov     rdx, rsi; pvargSrc
0x180025cfb  lea     rcx, [rbp+pvarg]; pvargDest
0x180025cff  call    cs:__imp_VariantCopy
0x180025d05  test    eax, eax
0x180025d07  js      loc_180025DAA
0x180025d0d  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180025d11  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x180025d16  test    eax, eax
0x180025d18  jnz     loc_180025DAA
0x180025d1e  xor     r9d, r9d
0x180025d21  mov     dword ptr [rsp+50h+var_30], eax
0x180025d25  xor     r8d, r8d
0x180025d28  jmp     short loc_180025D9F
0x180025d2a  mov     edi, 1
0x180025d2f  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180025d33  mov     r9d, edi; unsigned __int16
0x180025d36  xor     r8d, r8d; int
0x180025d39  mov     rdx, rsi; struct tagVARIANT *
0x180025d3c  call    ?ConvertArray@@YAJPEAUtagVARIANT@@0HG@Z; ConvertArray(tagVARIANT *,tagVARIANT *,int,ushort)
0x180025d41  test    eax, eax
0x180025d43  jnz     short loc_180025DAA
0x180025d45  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180025d49  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x180025d4e  test    eax, eax
0x180025d50  jnz     short loc_180025DAA
0x180025d52  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180025d56  lea     r8, [rbp+plLbound]; plLbound
0x180025d5a  mov     edx, edi; nDim
0x180025d5c  mov     [rbp+plLbound], 0
0x180025d63  mov     [rbp+plUbound], 0
0x180025d6a  call    cs:__imp_SafeArrayGetLBound
0x180025d70  test    eax, eax
0x180025d72  js      short loc_180025DAA
0x180025d74  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180025d78  lea     r8, [rbp+plUbound]; plUbound
0x180025d7c  mov     edx, edi; nDim
0x180025d7e  call    cs:__imp_SafeArrayGetUBound
0x180025d84  test    eax, eax
0x180025d86  js      short loc_180025DAA
0x180025d88  mov     ecx, [rbp+plUbound]
0x180025d8b  mov     eax, ecx
0x180025d8d  mov     r9d, [rbp+plLbound]; int
0x180025d91  sub     eax, r9d
0x180025d94  add     eax, edi
0x180025d96  jz      short loc_180025DAA
0x180025d98  mov     r8b, dil; bool
0x180025d9b  mov     dword ptr [rsp+50h+var_30], ecx; int
0x180025d9f  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180025da3  call    ?GetCIMType@@YA?AW4WbemCimtypeEnum@@AEAUtagVARIANT@@J_NJJ@Z; GetCIMType(tagVARIANT &,long,bool,long,long)
0x180025da8  mov     ebx, eax
0x180025daa  lea     rcx, [rbp+pvarg]; pvarg
0x180025dae  call    cs:__imp_VariantClear
0x180025db4  mov     eax, ebx
0x180025db6  mov     rbx, [rsp+50h+arg_10]
0x180025dbe  add     rsp, 50h
0x180025dc2  pop     rdi
0x180025dc3  pop     rsi
0x180025dc4  pop     rbp
0x180025dc5  retn
```
