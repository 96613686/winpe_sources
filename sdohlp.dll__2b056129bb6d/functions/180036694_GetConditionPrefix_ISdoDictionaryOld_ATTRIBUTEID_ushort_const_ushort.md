# GetConditionPrefix(ISdoDictionaryOld *,_ATTRIBUTEID,ushort * const,ushort * *)

- ea: `0x180036694`
- end: `0x180036a6b`
- name: `?GetConditionPrefix@@YAJPEAUISdoDictionaryOld@@W4_ATTRIBUTEID@@QEAGPEAPEAG@Z`
- size: `983`
- prototype: `int(struct ISdoDictionaryOld *, enum _ATTRIBUTEID, unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800360c0`
- `0x180036c90`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x18002f240`
- `0x180036694`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180036954`
- `msvcrt!swprintf_s` at `0x180036a3c`
- `msvcrt!swprintf_s` at `0x180036954`
- `msvcrt!swprintf_s` at `0x180036a3c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800368e9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800369b6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800368e9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800369b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180036a1b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800368cc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800368d7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800369a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800368cc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800368d7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800369a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800366b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800366cd`
- `OLEAUT32!__imp_VariantInit` at `0x180036830`
- `OLEAUT32!__imp_VariantInit` at `0x1800366b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800366cd`
- `OLEAUT32!__imp_VariantInit` at `0x180036830`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800367cc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800367cc`

## string_xrefs

- `0x180036808`: `Not enough memory to create safearray of Info Ids`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetConditionPrefix(
        struct ISdoDictionaryOld *a1,
        unsigned int a2,
        unsigned __int16 *const a3,
        unsigned __int16 **a4)
{
  int v8; // edi
  SAFEARRAY *v9; // rax
  __int64 v10; // rdx
  OLECHAR *v11; // r14
  __int64 v12; // rbx
  __int64 v13; // r13
  wchar_t *v14; // rax
  unsigned __int16 *v15; // rbx
  const wchar_t *v16; // rsi
  __int64 v17; // rbx
  __int64 v18; // r14
  wchar_t *v19; // rax
  VARIANTARG v21; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C8h] [rbp+60h] BYREF

  VariantInit(&pvarg);
  rgsabound = (SAFEARRAYBOUND)1LL;
  VariantInit(&v21);
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Invalid argument passed for pbstrConditionText");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids, "NPSSDO");
    }
    v8 = -2147024809;
    goto LABEL_44;
  }
  *a4 = 0;
  switch ( a2 )
  {
    case 0x1006u:
      v16 = L"TIMEOFDAY";
LABEL_35:
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v18 = v17 + SysStringLen(a3);
      v19 = SysAllocStringLen(0, (int)v18 + 4);
      v15 = v19;
      if ( !v19 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_43;
        }
        WppDbgPrint("Not enough memory to allocate BSTR for Condition Text");
        v10 = 11;
        goto LABEL_42;
      }
      v8 = 0;
      swprintf_s(v19, v18 + 5, L"%s(\"%s\")", v16, a3);
LABEL_46:
      *a4 = v15;
      goto LABEL_47;
    case 0x1023u:
      v16 = L"NTGROUPS";
      goto LABEL_35;
    case 0x1FB4u:
      v16 = L"MACHINENTGROUPS";
      goto LABEL_35;
    case 0x1FB5u:
      v16 = L"USERNTGROUPS";
      goto LABEL_35;
    case 0x1FD5u:
      v16 = L"ABSOLUTETIME";
      goto LABEL_35;
    case 0x1FD7u:
      v16 = L"EAPTYPES";
      goto LABEL_35;
  }
  pvarg.vt = 8195;
  v9 = SafeArrayCreate(3u, 1u, &rgsabound);
  if ( v9 )
  {
    *(_DWORD *)v9->pvData = 1;
    pvarg.llVal = (LONGLONG)v9;
    VariantInit(&v21);
    v8 = ((__int64 (__fastcall *)(struct ISdoDictionaryOld *, _QWORD, VARIANTARG *, VARIANTARG *))a1->lpVtbl->GetAttributeInfo)(
           a1,
           a2,
           &pvarg,
           &v21);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pDict->GetAttributeInfo(NAME) failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
          (unsigned int)"NPSSDO",
          v8);
      }
      goto LABEL_44;
    }
    v11 = *(OLECHAR **)(*(_QWORD *)(v21.llVal + 16) + 8LL);
    v12 = SysStringLen(v11);
    v13 = v12 + SysStringLen(a3);
    v14 = SysAllocStringLen(0, (int)v13 + 10);
    v15 = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_43;
      }
      WppDbgPrint("Not enough memory to allocate BSTR for Condition Text");
      v10 = 14;
      goto LABEL_42;
    }
    swprintf_s(v14, v13 + 11, L"%s(\"%s=%s\")", L"MATCH", v11, a3);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
  {
    goto LABEL_43;
  }
  WppDbgPrint("Not enough memory to create safearray of Info Ids");
  v10 = 12;
LABEL_42:
  WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids, "NPSSDO");
LABEL_43:
  v8 = -2147024882;
LABEL_44:
  SysFreeString(0);
LABEL_47:
  _variant_t::~_variant_t((_variant_t *)&v21);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036694  push    rbp
0x180036696  push    rbx
0x180036697  push    rsi
0x180036698  push    rdi
0x180036699  push    r12
0x18003669b  push    r13
0x18003669d  push    r14
0x18003669f  push    r15
0x1800366a1  mov     rbp, rsp
0x1800366a4  sub     rsp, 68h
0x1800366a8  mov     r15, r9
0x1800366ab  mov     r12, r8
0x1800366ae  mov     edi, edx
0x1800366b0  mov     r14, rcx
0x1800366b3  lea     rcx, [rbp+pvarg]; pvarg
0x1800366b7  call    cs:__imp_VariantInit
0x1800366bd  nop
0x1800366be  mov     qword ptr [rbp+rgsabound.cElements], 1
0x1800366c6  xor     r13d, r13d
0x1800366c9  lea     rcx, [rbp+var_38]; pvarg
0x1800366cd  call    cs:__imp_VariantInit
0x1800366d3  nop
0x1800366d4  mov     ebx, r13d
0x1800366d7  test    r15, r15
0x1800366da  jnz     short loc_180036736
0x1800366dc  lea     rax, WPP_GLOBAL_Control
0x1800366e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366ea  cmp     rcx, rax
0x1800366ed  jz      short loc_18003672C
0x1800366ef  cmp     byte ptr [rcx+19h], 2
0x1800366f3  jb      short loc_18003672C
0x1800366f5  test    dword ptr [rcx+1Ch], 400h
0x1800366fc  jz      short loc_18003672C
0x1800366fe  lea     rcx, aInvalidArgumen_0; "Invalid argument passed for pbstrCondit"...
0x180036705  call    WppDbgPrint
0x18003670a  lea     edx, [r13+0Ah]
0x18003670e  lea     r9, aNpssdo; "NPSSDO"
0x180036715  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x18003671c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036723  mov     rcx, [rcx+10h]
0x180036727  call    WPP_SF_s
0x18003672c  mov     edi, 80070057h
0x180036731  jmp     loc_180036A18
0x180036736  mov     [r15], r13
0x180036739  mov     ecx, edi
0x18003673b  mov     edx, 1006h
0x180036740  sub     ecx, edx
0x180036742  jz      loc_18003698C
0x180036748  sub     ecx, 1Dh
0x18003674b  jz      loc_180036983
0x180036751  lea     r8d, [rdx-75h]
0x180036755  sub     ecx, r8d
0x180036758  jz      loc_18003697A
0x18003675e  sub     ecx, 1
0x180036761  jz      loc_180036971
0x180036767  sub     ecx, 20h ; ' '
0x18003676a  jz      loc_180036968
0x180036770  cmp     ecx, 2
0x180036773  jz      loc_18003695F
0x180036779  lea     rsi, aMatch; "MATCH"
0x180036780  mov     ecx, edi
0x180036782  sub     ecx, edx
0x180036784  jz      loc_180036993
0x18003678a  sub     ecx, 1Dh
0x18003678d  jz      loc_180036993
0x180036793  sub     ecx, r8d
0x180036796  jz      loc_180036993
0x18003679c  sub     ecx, 1
0x18003679f  jz      loc_180036993
0x1800367a5  sub     ecx, 20h ; ' '
0x1800367a8  jz      loc_180036993
0x1800367ae  cmp     ecx, 2
0x1800367b1  jz      loc_180036993
0x1800367b7  mov     eax, 2003h
0x1800367bc  mov     word ptr [rbp+pvarg], ax
0x1800367c0  mov     ecx, 3; vt
0x1800367c5  lea     r8, [rbp+rgsabound]; rgsabound
0x1800367c9  lea     edx, [rcx-2]; cDims
0x1800367cc  call    cs:__imp_SafeArrayCreate
0x1800367d2  mov     rcx, rax
0x1800367d5  test    rax, rax
0x1800367d8  jnz     short loc_18003681E
0x1800367da  lea     rax, WPP_GLOBAL_Control
0x1800367e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367e8  cmp     rcx, rax
0x1800367eb  jz      loc_180036A13
0x1800367f1  cmp     byte ptr [rcx+19h], 2
0x1800367f5  jb      loc_180036A13
0x1800367fb  test    dword ptr [rcx+1Ch], 400h
0x180036802  jz      loc_180036A13
0x180036808  lea     rcx, aNotEnoughMemor_2; "Not enough memory to create safearray o"...
0x18003680f  call    WppDbgPrint
0x180036814  mov     edx, 0Ch
0x180036819  jmp     loc_1800369F5
0x18003681e  mov     rax, [rax+10h]
0x180036822  mov     dword ptr [rax], 1
0x180036828  mov     qword ptr [rbp+pvarg+8], rcx
0x18003682c  lea     rcx, [rbp+var_38]; pvarg
0x180036830  call    cs:__imp_VariantInit
0x180036836  mov     rax, [r14]
0x180036839  lea     r9, [rbp+var_38]
0x18003683d  lea     r8, [rbp+pvarg]
0x180036841  mov     edx, edi
0x180036843  mov     rcx, r14
0x180036846  mov     rax, [rax+40h]
0x18003684a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003684f  mov     edi, eax
0x180036851  test    eax, eax
0x180036853  jns     short loc_1800368BD
0x180036855  lea     rax, WPP_GLOBAL_Control
0x18003685c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036863  cmp     rcx, rax
0x180036866  jz      loc_180036A18
0x18003686c  cmp     byte ptr [rcx+19h], 2
0x180036870  jb      loc_180036A18
0x180036876  test    dword ptr [rcx+1Ch], 400h
0x18003687d  jz      loc_180036A18
0x180036883  mov     edx, edi
0x180036885  lea     rcx, aPdictGetattrib; "pDict->GetAttributeInfo(NAME) failed wi"...
0x18003688c  call    WppDbgPrint
0x180036891  mov     edx, 0Dh
0x180036896  mov     dword ptr [rsp+68h+var_48], edi
0x18003689a  lea     r9, aNpssdo; "NPSSDO"
0x1800368a1  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x1800368a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368af  mov     rcx, [rcx+10h]
0x1800368b3  call    WPP_SF_sd
0x1800368b8  jmp     loc_180036A18
0x1800368bd  mov     rax, qword ptr [rbp+var_38+8]
0x1800368c1  mov     rcx, [rax+10h]
0x1800368c5  mov     r14, [rcx+8]
0x1800368c9  mov     rcx, r14; pbstr
0x1800368cc  call    cs:__imp_SysStringLen
0x1800368d2  mov     ebx, eax
0x1800368d4  mov     rcx, r12; pbstr
0x1800368d7  call    cs:__imp_SysStringLen
0x1800368dd  mov     r13d, eax
0x1800368e0  add     r13, rbx
0x1800368e3  lea     edx, [r13+0Ah]; ui
0x1800368e7  xor     ecx, ecx; strIn
0x1800368e9  call    cs:__imp_SysAllocStringLen
0x1800368ef  mov     rbx, rax
0x1800368f2  test    rax, rax
0x1800368f5  jnz     short loc_180036939
0x1800368f7  lea     rax, WPP_GLOBAL_Control
0x1800368fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180036905  cmp     rcx, rax
0x180036908  jz      loc_180036A13
0x18003690e  cmp     byte ptr [rcx+19h], 2
0x180036912  jb      loc_180036A13
0x180036918  test    dword ptr [rcx+1Ch], 400h
0x18003691f  jz      loc_180036A13
0x180036925  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate BSTR for "...
0x18003692c  call    WppDbgPrint
0x180036931  lea     edx, [rbx+0Eh]
0x180036934  jmp     loc_1800369F5
0x180036939  lea     rdx, [r13+0Bh]; BufferCount
0x18003693d  mov     [rsp+68h+var_40], r12
0x180036942  mov     [rsp+68h+var_48], r14
0x180036947  mov     r9, rsi
0x18003694a  lea     r8, aSSS; "%s(\"%s=%s\")"
0x180036951  mov     rcx, rax; Buffer
0x180036954  call    cs:__imp_swprintf_s
0x18003695a  jmp     loc_180036A42
0x18003695f  lea     rsi, aEaptypes; "EAPTYPES"
0x180036966  jmp     short loc_180036993
0x180036968  lea     rsi, aAbsolutetime; "ABSOLUTETIME"
0x18003696f  jmp     short loc_180036993
0x180036971  lea     rsi, aUserntgroups; "USERNTGROUPS"
0x180036978  jmp     short loc_180036993
0x18003697a  lea     rsi, aMachinentgroup; "MACHINENTGROUPS"
0x180036981  jmp     short loc_180036993
0x180036983  lea     rsi, aNtgroups; "NTGROUPS"
0x18003698a  jmp     short loc_180036993
0x18003698c  lea     rsi, aTimeofday; "TIMEOFDAY"
0x180036993  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036997  inc     rbx
0x18003699a  cmp     [rsi+rbx*2], r13w
0x18003699f  jnz     short loc_180036997
0x1800369a1  mov     rcx, r12; pbstr
0x1800369a4  call    cs:__imp_SysStringLen
0x1800369aa  mov     r14d, eax
0x1800369ad  add     r14, rbx
0x1800369b0  lea     edx, [r14+4]; ui
0x1800369b4  xor     ecx, ecx; strIn
0x1800369b6  call    cs:__imp_SysAllocStringLen
0x1800369bc  mov     rbx, rax
0x1800369bf  test    rax, rax
0x1800369c2  jnz     short loc_180036A23
0x1800369c4  lea     rax, WPP_GLOBAL_Control
0x1800369cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369d2  cmp     rcx, rax
0x1800369d5  jz      short loc_180036A13
0x1800369d7  cmp     byte ptr [rcx+19h], 2
0x1800369db  jb      short loc_180036A13
0x1800369dd  test    dword ptr [rcx+1Ch], 400h
0x1800369e4  jz      short loc_180036A13
0x1800369e6  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate BSTR for "...
0x1800369ed  call    WppDbgPrint
0x1800369f2  lea     edx, [rbx+0Bh]
0x1800369f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369fc  lea     r9, aNpssdo; "NPSSDO"
0x180036a03  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036a0a  mov     rcx, [rcx+10h]
0x180036a0e  call    WPP_SF_s
0x180036a13  mov     edi, 8007000Eh
0x180036a18  mov     rcx, rbx; bstrString
0x180036a1b  call    cs:__imp_SysFreeString
0x180036a21  jmp     short loc_180036A45
0x180036a23  mov     edi, r13d
0x180036a26  lea     rdx, [r14+5]; BufferCount
0x180036a2a  mov     [rsp+68h+var_48], r12
0x180036a2f  mov     r9, rsi
0x180036a32  lea     r8, aSS; "%s(\"%s\")"
0x180036a39  mov     rcx, rax; Buffer
0x180036a3c  call    cs:__imp_swprintf_s
0x180036a42  mov     [r15], rbx
0x180036a45  lea     rcx, [rbp+var_38]; this
0x180036a49  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180036a4e  nop
0x180036a4f  lea     rcx, [rbp+pvarg]; this
0x180036a53  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180036a58  mov     eax, edi
0x180036a5a  add     rsp, 68h
0x180036a5e  pop     r15
0x180036a60  pop     r14
0x180036a62  pop     r13
0x180036a64  pop     r12
0x180036a66  pop     rdi
0x180036a67  pop     rsi
0x180036a68  pop     rbx
0x180036a69  pop     rbp
0x180036a6a  retn
```
