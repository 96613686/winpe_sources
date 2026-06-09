# CAssocQuery::PathPointsToObj(ushort const *,IWbemClassObject *,CWbemNamespace *)

- ea: `0x180027ff0`
- end: `0x1800285be`
- name: `?PathPointsToObj@CAssocQuery@@CAJPEBGPEAUIWbemClassObject@@PEAVCWbemNamespace@@@Z`
- size: `1486`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IWbemClassObject *, struct CWbemNamespace *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180026280`

## callees

- `0x18000b140`
- `0x180027ff0`
- `0x1800285d0`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002832b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028370`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800283b5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800283fa`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002843f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028484`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002832b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028370`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800283b5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800283fa`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002843f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180028484`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002817c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028186`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002828d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028297`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002817c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028186`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002828d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028297`
- `wbemcomn!GetMemLogObject` at `0x180028259`
- `wbemcomn!GetMemLogObject` at `0x1800282bd`
- `wbemcomn!GetMemLogObject` at `0x1800284c4`
- `wbemcomn!GetMemLogObject` at `0x180028566`
- `wbemcomn!GetMemLogObject` at `0x180028259`
- `wbemcomn!GetMemLogObject` at `0x1800282bd`
- `wbemcomn!GetMemLogObject` at `0x1800284c4`
- `wbemcomn!GetMemLogObject` at `0x180028566`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028267`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800282cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800284d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028574`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028267`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800282cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800284d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028574`
- `OLEAUT32!__imp_VariantInit` at `0x180028029`
- `OLEAUT32!__imp_VariantInit` at `0x1800280db`
- `OLEAUT32!__imp_VariantInit` at `0x180028029`
- `OLEAUT32!__imp_VariantInit` at `0x1800280db`
- `OLEAUT32!__imp_VariantClear` at `0x180028191`
- `OLEAUT32!__imp_VariantClear` at `0x18002819c`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800282ad`
- `OLEAUT32!__imp_VariantClear` at `0x1800282ec`
- `OLEAUT32!__imp_VariantClear` at `0x180028517`
- `OLEAUT32!__imp_VariantClear` at `0x180028522`
- `OLEAUT32!__imp_VariantClear` at `0x180028191`
- `OLEAUT32!__imp_VariantClear` at `0x18002819c`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800282ad`
- `OLEAUT32!__imp_VariantClear` at `0x1800282ec`
- `OLEAUT32!__imp_VariantClear` at `0x180028517`
- `OLEAUT32!__imp_VariantClear` at `0x180028522`

## string_xrefs

- `0x180028046`: `__RELPATH`
- `0x1800280f8`: `__PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAssocQuery::PathPointsToObj(
        const unsigned __int16 *a1,
        struct IWbemClassObject *a2,
        struct CWbemNamespace *a3)
{
  WCHAR *bstrVal; // rsi
  const unsigned __int16 *i; // rdi
  WCHAR v8; // bx
  WCHAR v9; // cx
  WCHAR *v10; // rsi
  const unsigned __int16 *j; // rdi
  WCHAR v12; // bx
  WCHAR v13; // cx
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // r15
  WCHAR *v19; // r14
  WCHAR *k; // rsi
  WCHAR v21; // di
  WCHAR v22; // cx
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  CMemoryLog *v31; // rax
  CMemoryLog *MemLogObject; // rax
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG v34; // [rsp+68h] [rbp-18h] BYREF
  WCHAR DestStr; // [rsp+C0h] [rbp+40h] BYREF
  WCHAR SrcStr; // [rsp+D8h] [rbp+58h] BYREF

  if ( !a1 || !a2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"__RELPATH",
         0,
         &pvarg,
         0,
         0) < 0
    || pvarg.vt != 8 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749889LL);
    }
    VariantClear(&pvarg);
    return 2147749889LL;
  }
  bstrVal = pvarg.bstrVal;
  for ( i = a1; ; ++i )
  {
    v8 = *i;
    if ( *i )
    {
      if ( v8 > 0x7Fu )
      {
        SrcStr = *i;
        DestStr = 0;
        v25 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
        v8 = DestStr;
        if ( !v25 )
          v8 = SrcStr;
      }
      else if ( (unsigned __int16)(v8 - 65) <= 0x19u )
      {
        v8 += 32;
      }
    }
    else if ( !*bstrVal )
    {
      goto LABEL_31;
    }
    v9 = *bstrVal;
    if ( *bstrVal > 0x7Fu )
    {
      SrcStr = *bstrVal;
      DestStr = 0;
      v26 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v9 = DestStr;
      if ( !v26 )
        v9 = SrcStr;
    }
    else if ( (unsigned __int16)(v9 - 65) <= 0x19u )
    {
      v9 += 32;
    }
    if ( v8 != v9 )
      break;
    ++bstrVal;
  }
  VariantInit(&v34);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"__PATH",
         0,
         &v34,
         0,
         0) < 0
    || pvarg.vt != 8 )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749889LL);
    }
    VariantClear(&v34);
    VariantClear(&pvarg);
    return 2147749889LL;
  }
  v10 = v34.bstrVal;
  for ( j = a1; ; ++j )
  {
    v12 = *j;
    if ( *j )
    {
      if ( v12 > 0x7Fu )
      {
        SrcStr = *j;
        DestStr = 0;
        v27 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
        v12 = DestStr;
        if ( !v27 )
          v12 = SrcStr;
      }
      else if ( (unsigned __int16)(v12 - 65) <= 0x19u )
      {
        v12 += 32;
      }
    }
    else if ( !*v10 )
    {
      goto LABEL_30;
    }
    v13 = *v10;
    if ( *v10 > 0x7Fu )
    {
      SrcStr = *v10;
      DestStr = 0;
      v28 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v13 = DestStr;
      if ( !v28 )
        v13 = SrcStr;
    }
    else if ( (unsigned __int16)(v13 - 65) <= 0x19u )
    {
      v13 += 32;
    }
    if ( v12 != v13 )
      break;
    ++v10;
  }
  v15 = CQueryEngine::NormalizePath(a1, a3);
  v16 = 0;
  if ( v34.vt == 8 )
    v16 = v34.bstrVal;
  v17 = CQueryEngine::NormalizePath(v16, a3);
  v18 = v17;
  if ( !v15 || !v17 )
  {
LABEL_48:
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749889LL);
    }
    CWin32DefaultArena::WbemMemFree(v18);
    CWin32DefaultArena::WbemMemFree(v15);
    VariantClear(&v34);
    VariantClear(&pvarg);
    return 2147749889LL;
  }
  v19 = v17;
  for ( k = v15; ; ++k )
  {
    v21 = *k;
    if ( !*k )
      break;
    if ( v21 > 0x7Fu )
    {
      SrcStr = *k;
      DestStr = 0;
      v29 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v21 = DestStr;
      if ( !v29 )
        v21 = SrcStr;
    }
    else if ( (unsigned __int16)(v21 - 65) <= 0x19u )
    {
      v21 += 32;
    }
LABEL_41:
    v22 = *v19;
    if ( *v19 > 0x7Fu )
    {
      SrcStr = *v19;
      DestStr = 0;
      v30 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1);
      v22 = DestStr;
      if ( !v30 )
        v22 = SrcStr;
    }
    else if ( (unsigned __int16)(v22 - 65) <= 0x19u )
    {
      v22 += 32;
    }
    if ( v21 != v22 )
      goto LABEL_48;
    ++v19;
  }
  if ( *v19 )
    goto LABEL_41;
  CWin32DefaultArena::WbemMemFree(v18);
  CWin32DefaultArena::WbemMemFree(v15);
LABEL_30:
  VariantClear(&v34);
LABEL_31:
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x180027ff0  mov     [rsp-38h+arg_8], rbx
0x180027ff5  push    rbp
0x180027ff6  push    rsi
0x180027ff7  push    rdi
0x180027ff8  push    r12
0x180027ffa  push    r13
0x180027ffc  push    r14
0x180027ffe  push    r15
0x180028000  mov     rbp, rsp
0x180028003  sub     rsp, 80h
0x18002800a  mov     r12, r8
0x18002800d  mov     r14, rdx
0x180028010  mov     r15, rcx
0x180028013  test    rcx, rcx
0x180028016  jz      loc_180028566
0x18002801c  test    rdx, rdx
0x18002801f  jz      loc_180028566
0x180028025  lea     rcx, [rbp+pvarg]; pvarg
0x180028029  call    cs:__imp_VariantInit
0x18002802f  nop
0x180028030  mov     rax, [r14]
0x180028033  xor     ecx, ecx
0x180028035  mov     qword ptr [rsp+80h+cchDest], rcx
0x18002803a  mov     [rsp+80h+lpDestStr], rcx
0x18002803f  lea     r9, [rbp+pvarg]
0x180028043  xor     r8d, r8d
0x180028046  lea     rdx, aRelpath_0; "__RELPATH"
0x18002804d  mov     rcx, r14
0x180028050  mov     rax, [rax+20h]
0x180028054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028059  test    eax, eax
0x18002805b  js      loc_1800282BD
0x180028061  mov     r13d, 8
0x180028067  cmp     r13w, word ptr [rbp+pvarg]
0x18002806c  jnz     loc_1800282BD
0x180028072  mov     rsi, qword ptr [rbp+pvarg+8]
0x180028076  mov     rdi, r15
0x180028079  nop     dword ptr [rax+00000000h]
0x180028080  movzx   ebx, word ptr [rdi]
0x180028083  test    bx, bx
0x180028086  jz      short loc_1800280CC
0x180028088  cmp     bx, 7Fh
0x18002808c  ja      loc_1800282FC
0x180028092  lea     eax, [rbx-41h]
0x180028095  cmp     ax, 19h
0x180028099  jbe     short loc_1800280C0
0x18002809b  movzx   ecx, word ptr [rsi]
0x18002809e  cmp     cx, 7Fh
0x1800280a2  ja      loc_180028341
0x1800280a8  lea     eax, [rcx-41h]
0x1800280ab  cmp     ax, 19h
0x1800280af  jbe     short loc_1800280C6
0x1800280b1  cmp     bx, cx
0x1800280b4  jnz     short loc_1800280D7
0x1800280b6  add     rdi, 2
0x1800280ba  add     rsi, 2
0x1800280be  jmp     short loc_180028080
0x1800280c0  add     bx, 20h ; ' '
0x1800280c4  jmp     short loc_18002809B
0x1800280c6  add     cx, 20h ; ' '
0x1800280ca  jmp     short loc_1800280B1
0x1800280cc  cmp     word ptr [rsi], 0
0x1800280d0  jnz     short loc_18002809B
0x1800280d2  jmp     loc_180028198
0x1800280d7  lea     rcx, [rbp+var_18]; pvarg
0x1800280db  call    cs:__imp_VariantInit
0x1800280e1  nop
0x1800280e2  mov     rax, [r14]
0x1800280e5  xor     ecx, ecx
0x1800280e7  mov     qword ptr [rsp+80h+cchDest], rcx
0x1800280ec  mov     [rsp+80h+lpDestStr], rcx
0x1800280f1  lea     r9, [rbp+var_18]
0x1800280f5  xor     r8d, r8d
0x1800280f8  lea     rdx, aPath; "__PATH"
0x1800280ff  mov     rcx, r14
0x180028102  mov     rax, [rax+20h]
0x180028106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002810b  test    eax, eax
0x18002810d  js      loc_1800284C4
0x180028113  cmp     r13w, word ptr [rbp+pvarg]
0x180028118  jnz     loc_1800284C4
0x18002811e  mov     rsi, qword ptr [rbp+var_18+8]
0x180028122  mov     rdi, r15
0x180028125  movzx   ebx, word ptr [rdi]
0x180028128  test    bx, bx
0x18002812b  jz      short loc_180028171
0x18002812d  cmp     bx, 7Fh
0x180028131  ja      loc_180028386
0x180028137  lea     eax, [rbx-41h]
0x18002813a  cmp     ax, 19h
0x18002813e  jbe     short loc_180028165
0x180028140  movzx   ecx, word ptr [rsi]
0x180028143  cmp     cx, 7Fh
0x180028147  ja      loc_1800283CB
0x18002814d  lea     eax, [rcx-41h]
0x180028150  cmp     ax, 19h
0x180028154  jbe     short loc_18002816B
0x180028156  cmp     bx, cx
0x180028159  jnz     short loc_1800281BF
0x18002815b  add     rdi, 2
0x18002815f  add     rsi, 2
0x180028163  jmp     short loc_180028125
0x180028165  add     bx, 20h ; ' '
0x180028169  jmp     short loc_180028140
0x18002816b  add     cx, 20h ; ' '
0x18002816f  jmp     short loc_180028156
0x180028171  cmp     word ptr [rsi], 0
0x180028175  jnz     short loc_180028140
0x180028177  jmp     short loc_18002818D
0x180028179  mov     rcx, r15
0x18002817c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180028182  nop
0x180028183  mov     rcx, rbx
0x180028186  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002818c  nop
0x18002818d  lea     rcx, [rbp+var_18]; pvarg
0x180028191  call    cs:__imp_VariantClear
0x180028197  nop
0x180028198  lea     rcx, [rbp+pvarg]; pvarg
0x18002819c  call    cs:__imp_VariantClear
0x1800281a2  xor     eax, eax
0x1800281a4  mov     rbx, [rsp+80h+arg_8]
0x1800281ac  add     rsp, 80h
0x1800281b3  pop     r15
0x1800281b5  pop     r14
0x1800281b7  pop     r13
0x1800281b9  pop     r12
0x1800281bb  pop     rdi
0x1800281bc  pop     rsi
0x1800281bd  pop     rbp
0x1800281be  retn
0x1800281bf  mov     rdx, r12; struct CWbemNamespace *
0x1800281c2  mov     rcx, r15; unsigned __int16 *
0x1800281c5  call    ?NormalizePath@CQueryEngine@@SAPEAGPEBGPEAVCWbemNamespace@@@Z; CQueryEngine::NormalizePath(ushort const *,CWbemNamespace *)
0x1800281ca  mov     rbx, rax
0x1800281cd  xor     ecx, ecx
0x1800281cf  cmp     word ptr [rbp+var_18], 8
0x1800281d4  cmovz   rcx, qword ptr [rbp+var_18+8]; unsigned __int16 *
0x1800281d9  mov     rdx, r12; struct CWbemNamespace *
0x1800281dc  call    ?NormalizePath@CQueryEngine@@SAPEAGPEBGPEAVCWbemNamespace@@@Z; CQueryEngine::NormalizePath(ushort const *,CWbemNamespace *)
0x1800281e1  mov     r15, rax
0x1800281e4  mov     [rbp+var_40], rbx
0x1800281e8  mov     [rbp+var_38], rax
0x1800281ec  test    rbx, rbx
0x1800281ef  jz      short loc_180028259
0x1800281f1  test    rax, rax
0x1800281f4  jz      short loc_180028259
0x1800281f6  mov     r14, rax
0x1800281f9  mov     rsi, rbx
0x1800281fc  nop     dword ptr [rax+00h]
0x180028200  movzx   edi, word ptr [rsi]
0x180028203  test    di, di
0x180028206  jz      short loc_18002824D
0x180028208  cmp     di, 7Fh
0x18002820c  ja      loc_180028410
0x180028212  lea     eax, [rdi-41h]
0x180028215  cmp     ax, 19h
0x180028219  jbe     short loc_180028241
0x18002821b  movzx   ecx, word ptr [r14]
0x18002821f  cmp     cx, 7Fh
0x180028223  ja      loc_180028455
0x180028229  lea     eax, [rcx-41h]
0x18002822c  cmp     ax, 19h
0x180028230  jbe     short loc_180028247
0x180028232  cmp     di, cx
0x180028235  jnz     short loc_180028259
0x180028237  add     rsi, 2
0x18002823b  add     r14, 2
0x18002823f  jmp     short loc_180028200
0x180028241  add     di, 20h ; ' '
0x180028245  jmp     short loc_18002821B
0x180028247  add     cx, 20h ; ' '
0x18002824b  jmp     short loc_180028232
0x18002824d  cmp     word ptr [r14], 0
0x180028252  jnz     short loc_18002821B
0x180028254  jmp     loc_180028179
0x180028259  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002825f  mov     edx, 80041001h
0x180028264  mov     rcx, rax
0x180028267  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002826d  lea     rax, WPP_GLOBAL_Control
0x180028274  mov     rcx, cs:WPP_GLOBAL_Control
0x18002827b  cmp     rcx, rax
0x18002827e  jz      short loc_18002828A
0x180028280  test    byte ptr [rcx+1Ch], 1
0x180028284  jnz     loc_18002849A
0x18002828a  mov     rcx, r15
0x18002828d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180028293  nop
0x180028294  mov     rcx, rbx
0x180028297  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002829d  nop
0x18002829e  lea     rcx, [rbp+var_18]; pvarg
0x1800282a2  call    cs:__imp_VariantClear
0x1800282a8  nop
0x1800282a9  lea     rcx, [rbp+pvarg]; pvarg
0x1800282ad  call    cs:__imp_VariantClear
0x1800282b3  mov     eax, 80041001h
0x1800282b8  jmp     loc_1800281A4
0x1800282bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800282c3  mov     edx, 80041001h
0x1800282c8  mov     rcx, rax
0x1800282cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800282d1  lea     rax, WPP_GLOBAL_Control
0x1800282d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282df  cmp     rcx, rax
0x1800282e2  jnz     loc_180028532
0x1800282e8  lea     rcx, [rbp+pvarg]; pvarg
0x1800282ec  call    cs:__imp_VariantClear
0x1800282f2  mov     eax, 80041001h
0x1800282f7  jmp     loc_1800281A4
0x1800282fc  mov     [rbp+SrcStr], bx
0x180028300  xor     eax, eax
0x180028302  mov     [rbp+DestStr], ax
0x180028306  mov     [rsp+80h+cchDest], 1; cchDest
0x18002830e  lea     rax, [rbp+DestStr]
0x180028312  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x180028317  mov     r9d, 1; cchSrc
0x18002831d  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180028321  mov     edx, 100h; dwMapFlags
0x180028326  mov     ecx, 7Fh; Locale
0x18002832b  call    cs:__imp_LCMapStringW
0x180028331  movzx   ebx, [rbp+DestStr]
0x180028335  test    eax, eax
0x180028337  cmovz   bx, [rbp+SrcStr]
0x18002833c  jmp     loc_18002809B
0x180028341  mov     [rbp+SrcStr], cx
0x180028345  xor     eax, eax
0x180028347  mov     [rbp+DestStr], ax
0x18002834b  mov     [rsp+80h+cchDest], 1; cchDest
0x180028353  lea     rax, [rbp+DestStr]
0x180028357  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x18002835c  mov     r9d, 1; cchSrc
0x180028362  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180028366  mov     edx, 100h; dwMapFlags
0x18002836b  mov     ecx, 7Fh; Locale
0x180028370  call    cs:__imp_LCMapStringW
0x180028376  movzx   ecx, [rbp+DestStr]
0x18002837a  test    eax, eax
0x18002837c  cmovz   cx, [rbp+SrcStr]
0x180028381  jmp     loc_1800280B1
0x180028386  mov     [rbp+SrcStr], bx
0x18002838a  xor     eax, eax
0x18002838c  mov     [rbp+DestStr], ax
0x180028390  mov     [rsp+80h+cchDest], 1; cchDest
0x180028398  lea     rax, [rbp+DestStr]
0x18002839c  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x1800283a1  mov     r9d, 1; cchSrc
0x1800283a7  lea     r8, [rbp+SrcStr]; lpSrcStr
0x1800283ab  mov     edx, 100h; dwMapFlags
0x1800283b0  mov     ecx, 7Fh; Locale
0x1800283b5  call    cs:__imp_LCMapStringW
0x1800283bb  movzx   ebx, [rbp+DestStr]
0x1800283bf  test    eax, eax
0x1800283c1  cmovz   bx, [rbp+SrcStr]
0x1800283c6  jmp     loc_180028140
0x1800283cb  mov     [rbp+SrcStr], cx
0x1800283cf  xor     eax, eax
0x1800283d1  mov     [rbp+DestStr], ax
0x1800283d5  mov     [rsp+80h+cchDest], 1; cchDest
0x1800283dd  lea     rax, [rbp+DestStr]
0x1800283e1  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x1800283e6  mov     r9d, 1; cchSrc
0x1800283ec  lea     r8, [rbp+SrcStr]; lpSrcStr
0x1800283f0  mov     edx, 100h; dwMapFlags
0x1800283f5  mov     ecx, 7Fh; Locale
0x1800283fa  call    cs:__imp_LCMapStringW
0x180028400  movzx   ecx, [rbp+DestStr]
0x180028404  test    eax, eax
0x180028406  cmovz   cx, [rbp+SrcStr]
0x18002840b  jmp     loc_180028156
0x180028410  mov     [rbp+SrcStr], di
0x180028414  xor     eax, eax
0x180028416  mov     [rbp+DestStr], ax
0x18002841a  mov     [rsp+80h+cchDest], 1; cchDest
0x180028422  lea     rax, [rbp+DestStr]
0x180028426  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x18002842b  mov     r9d, 1; cchSrc
0x180028431  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180028435  mov     edx, 100h; dwMapFlags
0x18002843a  mov     ecx, 7Fh; Locale
0x18002843f  call    cs:__imp_LCMapStringW
0x180028445  movzx   edi, [rbp+DestStr]
0x180028449  test    eax, eax
0x18002844b  cmovz   di, [rbp+SrcStr]
0x180028450  jmp     loc_18002821B
0x180028455  mov     [rbp+SrcStr], cx
0x180028459  xor     eax, eax
0x18002845b  mov     [rbp+DestStr], ax
0x18002845f  mov     [rsp+80h+cchDest], 1; cchDest
0x180028467  lea     rax, [rbp+DestStr]
0x18002846b  mov     [rsp+80h+lpDestStr], rax; lpDestStr
0x180028470  mov     r9d, 1; cchSrc
0x180028476  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18002847a  mov     edx, 100h; dwMapFlags
0x18002847f  mov     ecx, 7Fh; Locale
0x180028484  call    cs:__imp_LCMapStringW
0x18002848a  movzx   ecx, [rbp+DestStr]
0x18002848e  test    eax, eax
0x180028490  cmovz   cx, [rbp+SrcStr]
  ... truncated ...
```
