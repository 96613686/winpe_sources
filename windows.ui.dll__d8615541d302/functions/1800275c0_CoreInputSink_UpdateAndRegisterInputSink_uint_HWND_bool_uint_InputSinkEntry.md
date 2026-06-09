# CoreInputSink::UpdateAndRegisterInputSink(uint,HWND__ *,bool,uint,_InputSinkEntry *)

- ea: `0x1800275c0`
- end: `0x180027ca0`
- name: `?UpdateAndRegisterInputSink@CoreInputSink@@AEAAJIPEAUHWND__@@_NIPEAU_InputSinkEntry@@@Z`
- size: `1760`
- prototype: `__int64 __fastcall(CoreInputSink *__hidden this, unsigned int, HWND, bool, unsigned int, struct _InputSinkEntry *)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002714c`
- `0x1800274f4`

## callees

- `0x1800275c0`
- `0x180027ca8`
- `0x180028490`
- `0x180050360`
- `0x180056348`
- `0x180056d3c`
- `0x180071c60`
- `0x18008abdc`
- `0x180096534`
- `0x1800965b4`
- `0x18009674c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002783d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800279cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027a9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027c64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002783d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027960`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800279cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027a9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027c64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c2f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027a49`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027a49`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1800276bc`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1800276bc`
- `dcomp!__imp_NtCreateImplicitCompositionInputSink` at `0x180027aff`
- `dcomp!__imp_NtCreateImplicitCompositionInputSink` at `0x180027aff`

## string_xrefs

- `0x180027aed`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\helper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoreInputSink::UpdateAndRegisterInputSink(
        CoreInputSink *this,
        char a2,
        HWND a3,
        char a4,
        unsigned int a5,
        struct _InputSinkEntry *a6)
{
  HWND v7; // r14
  CoreInputSink *v9; // rdi
  PVOID *v10; // rax
  int v11; // r12d
  char *v12; // rcx
  int v13; // eax
  int v14; // r13d
  unsigned int v15; // ebx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  CoreInputSink *v20; // rcx
  void *v21; // rcx
  int v22; // ebx
  DWORD v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  DWORD v28; // eax
  DWORD v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rdi
  __int64 v32; // rsi
  __int64 v33; // r14
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  DWORD CurrentThreadId; // [rsp+20h] [rbp-60h]
  __int64 v38; // [rsp+28h] [rbp-58h]
  __int64 v39; // [rsp+30h] [rbp-50h]
  unsigned int v40; // [rsp+50h] [rbp-30h]
  HANDLE hObject; // [rsp+58h] [rbp-28h] BYREF
  CoreInputSink *v42; // [rsp+60h] [rbp-20h] BYREF
  int v43; // [rsp+68h] [rbp-18h]
  int v44; // [rsp+6Ch] [rbp-14h]
  int v45; // [rsp+70h] [rbp-10h]
  HWND v46; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v7 = a3;
  v46 = a3;
  v9 = this;
  v42 = this;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    HIDWORD(v39) = HIDWORD(a3);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDDqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, v9);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7
    && ((a2 & 1) != 0 && *((_QWORD *)a6 + 18)
     || (a2 & 2) != 0 && *((_QWORD *)a6 + 25)
     || (a2 & 4) != 0 && *((_QWORD *)a6 + 4)
     || (a2 & 8) != 0 && *((_QWORD *)a6 + 11)) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    {
      v28 = GetCurrentThreadId();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9, v28);
    }
    RoOriginateError(2147942487LL, 0);
    return (unsigned int)-2147024809;
  }
  v40 = 0;
  v43 = a2 & 1;
  if ( (a2 & 1) != 0 )
  {
    InitCompositionInputQueue(v7, 0, (char *)a6 + 136);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v38 = *((_QWORD *)a6 + 18);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9);
    }
  }
  v44 = a2 & 2;
  if ( (a2 & 2) != 0 )
  {
    InitCompositionInputQueue(v7, 0, (char *)a6 + 192);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v38 = *((_QWORD *)a6 + 25);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9);
    }
  }
  v45 = a2 & 4;
  if ( (a2 & 4) != 0 )
  {
    InitCompositionInputQueue(v7, 0, (char *)a6 + 24);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v38 = *((_QWORD *)a6 + 4);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9);
    }
  }
  v11 = a2 & 8;
  if ( v11 )
  {
    InitCompositionInputQueue(v7, 0, (char *)a6 + 80);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v38 = *((_QWORD *)a6 + 11);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9);
    }
  }
  *((_DWORD *)a6 + 62) = 0;
  *((_QWORD *)a6 + 32) = 0;
  *(_OWORD *)((char *)a6 + 264) = 0;
  *(_OWORD *)((char *)a6 + 280) = 0;
  *((_QWORD *)a6 + 37) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v39 = *((_QWORD *)a6 + 25);
    v38 = *((_QWORD *)a6 + 18);
    CurrentThreadId = GetCurrentThreadId();
    v9 = v42;
    WPP_SF_qDqqqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, v42);
    v7 = v46;
  }
  v12 = (char *)a6 + 16;
  *((_DWORD *)a6 + 5) = a5;
  hObject = 0;
  if ( a4 )
    v13 = NtCreateImplicitCompositionInputSink(v12, &hObject);
  else
    v13 = NtCreateCompositionInputSink(v12, &hObject);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v30 = *((_QWORD *)a6 + 11);
      v31 = *((_QWORD *)a6 + 4);
      v32 = *((_QWORD *)a6 + 25);
      v33 = *((_QWORD *)a6 + 18);
      v34 = GetCurrentThreadId();
      LODWORD(v38) = v14;
      WPP_SF_qDDqqqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, v42, v34, v38, v33, v32, v31, v30);
    }
    return v40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    HIDWORD(v38) = HIDWORD(hObject);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9);
  }
  v17 = *((_QWORD *)a6 + 39);
  if ( v17 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v17 + 280LL))(v17, hObject);
    v40 = v19;
  }
  else
  {
    if ( !*((_QWORD *)a6 + 40) )
    {
LABEL_22:
      v21 = (void *)*((_QWORD *)a6 + 1);
      if ( v21 )
        CloseHandle(v21);
      *((_QWORD *)a6 + 1) = hObject;
      if ( v7 )
        ++*((_DWORD *)a6 + 82);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = *((_DWORD *)a6 + 82);
        v23 = GetCurrentThreadId();
        LODWORD(v39) = v22;
        WPP_SF_qDqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
          v9,
          v23,
          a6,
          v39);
      }
      return v40;
    }
    v42 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>::As<Windows::UI::Composition::Internal::IVisualInternal>(
            (char *)a6 + 320,
            &v42);
    if ( v18 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x2AE,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\helper.cpp",
        (const char *)(unsigned int)v18,
        CurrentThreadId);
    v19 = (*(__int64 (__fastcall **)(CoreInputSink *, HANDLE))(*(_QWORD *)v42 + 80LL))(v42, hObject);
    v40 = v19;
    v20 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(CoreInputSink *))(*(_QWORD *)v20 + 16LL))(v20);
      v19 = v40;
    }
  }
  if ( v19 >= 0 )
    goto LABEL_22;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    v15 = v40;
  }
  else
  {
    v29 = GetCurrentThreadId();
    v15 = v40;
    LODWORD(v38) = v40;
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, v9, v29, v38);
  }
  CloseHandle(hObject);
  if ( v43 )
  {
    *((_QWORD *)a6 + 18) = 0;
    *((_DWORD *)a6 + 34) = 0;
  }
  if ( v44 )
  {
    *((_QWORD *)a6 + 25) = 0;
    *((_DWORD *)a6 + 48) = 0;
  }
  if ( v45 )
  {
    *((_QWORD *)a6 + 4) = 0;
    *((_DWORD *)a6 + 6) = 0;
  }
  if ( v11 )
  {
    *((_QWORD *)a6 + 11) = 0;
    *((_DWORD *)a6 + 20) = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x1800275c0  mov     [rsp-38h+arg_8], rbx
0x1800275c5  push    rbp
0x1800275c6  push    rsi
0x1800275c7  push    rdi
0x1800275c8  push    r12
0x1800275ca  push    r13
0x1800275cc  push    r14
0x1800275ce  push    r15
0x1800275d0  mov     rbp, rsp
0x1800275d3  sub     rsp, 80h
0x1800275da  mov     r13b, r9b
0x1800275dd  mov     r14, r8
0x1800275e0  mov     [rbp+var_8], r8
0x1800275e4  mov     r12d, edx
0x1800275e7  mov     rdi, rcx
0x1800275ea  mov     [rbp+var_20], rcx
0x1800275ee  mov     r15, [rbp+arg_28]
0x1800275f2  lea     rbx, WPP_GLOBAL_Control
0x1800275f9  mov     rax, cs:WPP_GLOBAL_Control
0x180027600  cmp     rax, rbx
0x180027603  jnz     loc_180027873
0x180027609  xor     ecx, ecx
0x18002760b  test    r14, r14
0x18002760e  jnz     loc_1800279FB
0x180027614  mov     [rbp+var_30], ecx
0x180027617  mov     eax, r12d
0x18002761a  lea     rsi, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027621  and     eax, 1
0x180027624  mov     [rbp+var_18], eax
0x180027627  jnz     loc_180027801
0x18002762d  mov     eax, r12d
0x180027630  and     eax, 2
0x180027633  mov     [rbp+var_14], eax
0x180027636  jnz     loc_1800278BF
0x18002763c  mov     eax, r12d
0x18002763f  and     eax, 4
0x180027642  mov     [rbp+var_10], eax
0x180027645  jnz     loc_18002798F
0x18002764b  lea     rbx, WPP_GLOBAL_Control
0x180027652  and     r12d, 8
0x180027656  jnz     loc_18002792A
0x18002765c  xorps   xmm0, xmm0
0x18002765f  xor     eax, eax
0x180027661  mov     [r15+0F8h], eax
0x180027668  mov     [r15+100h], rax
0x18002766f  movups  xmmword ptr [r15+108h], xmm0
0x180027677  movups  xmmword ptr [r15+118h], xmm0
0x18002767f  mov     [r15+128h], rax
0x180027686  mov     rax, cs:WPP_GLOBAL_Control
0x18002768d  lea     rbx, WPP_GLOBAL_Control
0x180027694  cmp     rax, rbx
0x180027697  jnz     loc_180027A74
0x18002769d  lea     rcx, [r15+10h]
0x1800276a1  mov     eax, [rbp+arg_20]
0x1800276a4  mov     [rcx+4], eax
0x1800276a7  mov     [rbp+hObject], 0
0x1800276af  lea     rdx, [rbp+hObject]
0x1800276b3  test    r13b, r13b
0x1800276b6  jnz     loc_180027AFF
0x1800276bc  call    cs:__imp_NtCreateCompositionInputSink
0x1800276c2  mov     r13d, eax
0x1800276c5  test    eax, eax
0x1800276c7  jns     short loc_1800276F9
0x1800276c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800276d0  cmp     rax, rbx
0x1800276d3  jnz     loc_180027C3A
0x1800276d9  mov     ebx, [rbp+var_30]
0x1800276dc  mov     eax, ebx
0x1800276de  mov     rbx, [rsp+80h+arg_8]
0x1800276e6  add     rsp, 80h
0x1800276ed  pop     r15
0x1800276ef  pop     r14
0x1800276f1  pop     r13
0x1800276f3  pop     r12
0x1800276f5  pop     rdi
0x1800276f6  pop     rsi
0x1800276f7  pop     rbp
0x1800276f8  retn
0x1800276f9  mov     rax, cs:WPP_GLOBAL_Control
0x180027700  cmp     rax, rbx
0x180027703  jz      short loc_18002770F
0x180027705  test    byte ptr [rax+1Ch], 40h
0x180027709  jnz     loc_180027B4C
0x18002770f  mov     rcx, [r15+138h]
0x180027716  xor     r13d, r13d
0x180027719  test    rcx, rcx
0x18002771c  jnz     loc_180027A59
0x180027722  lea     rcx, [r15+140h]
0x180027729  cmp     [rcx], r13
0x18002772c  jz      short loc_180027782
0x18002772e  mov     [rbp+var_20], r13
0x180027732  lea     rdx, [rbp+var_20]
0x180027736  call    ??$As@UIVisualInternal@Internal@Composition@UI@Windows@@@?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVisualInternal@Internal@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>::As<Windows::UI::Composition::Internal::IVisualInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::IVisualInternal>>)
0x18002773b  mov     rcx, [rbp+38h]; this
0x18002773f  test    eax, eax
0x180027741  js      loc_180027AEA
0x180027747  mov     rcx, [rbp+var_20]
0x18002774b  mov     rax, [rcx]
0x18002774e  mov     rdx, [rbp+hObject]
0x180027752  mov     rax, [rax+50h]
0x180027756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002775b  mov     [rbp+var_30], eax
0x18002775e  mov     rcx, [rbp+var_20]
0x180027762  test    rcx, rcx
0x180027765  jz      short loc_18002777A
0x180027767  mov     [rbp+var_20], r13
0x18002776b  mov     rax, [rcx]
0x18002776e  mov     rax, [rax+10h]
0x180027772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027777  mov     eax, [rbp+var_30]
0x18002777a  test    eax, eax
0x18002777c  js      loc_180027B90
0x180027782  mov     rcx, [r15+8]; hObject
0x180027786  test    rcx, rcx
0x180027789  jnz     loc_180027C2F
0x18002778f  mov     rax, [rbp+hObject]
0x180027793  mov     [r15+8], rax
0x180027797  test    r14, r14
0x18002779a  jz      short loc_1800277A3
0x18002779c  inc     dword ptr [r15+148h]
0x1800277a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800277aa  cmp     rax, rbx
0x1800277ad  jz      loc_1800276D9
0x1800277b3  test    byte ptr [rax+1Ch], 40h
0x1800277b7  jz      loc_1800276D9
0x1800277bd  cmp     byte ptr [rax+19h], 4
0x1800277c1  jb      loc_1800276D9
0x1800277c7  mov     ebx, [r15+148h]
0x1800277ce  call    cs:__imp_GetCurrentThreadId
0x1800277d4  mov     edx, 1Dh
0x1800277d9  mov     dword ptr [rsp+80h+var_50], ebx
0x1800277dd  mov     [rsp+80h+var_58], r15
0x1800277e2  mov     [rsp+80h+var_60], eax
0x1800277e6  mov     r9, rdi
0x1800277e9  mov     r8, rsi
0x1800277ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277f3  mov     rcx, [rcx+10h]
0x1800277f7  call    WPP_SF_qDqd
0x1800277fc  jmp     loc_1800276D9
0x180027801  lea     r8, [r15+88h]
0x180027808  xor     edx, edx
0x18002780a  mov     rcx, r14
0x18002780d  call    InitCompositionInputQueue
0x180027812  mov     rax, cs:WPP_GLOBAL_Control
0x180027819  cmp     rax, rbx
0x18002781c  jz      loc_18002762D
0x180027822  test    byte ptr [rax+1Ch], 40h
0x180027826  jz      loc_18002762D
0x18002782c  cmp     byte ptr [rax+19h], 4
0x180027830  jb      loc_18002762D
0x180027836  mov     rbx, [r15+90h]
0x18002783d  call    cs:__imp_GetCurrentThreadId
0x180027843  mov     edx, 17h
0x180027848  mov     [rsp+80h+var_58], rbx
0x18002784d  mov     [rsp+80h+var_60], eax
0x180027851  mov     r9, rdi
0x180027854  mov     r8, rsi
0x180027857  mov     rcx, cs:WPP_GLOBAL_Control
0x18002785e  mov     rcx, [rcx+10h]
0x180027862  call    WPP_SF_qDq
0x180027867  lea     rbx, WPP_GLOBAL_Control
0x18002786e  jmp     loc_18002762D
0x180027873  test    byte ptr [rax+1Ch], 40h
0x180027877  jz      loc_180027609
0x18002787d  cmp     byte ptr [rax+19h], 4
0x180027881  jb      loc_180027609
0x180027887  call    cs:__imp_GetCurrentThreadId
0x18002788d  mov     [rsp+80h+var_48], r15
0x180027892  mov     [rsp+80h+var_50], r14
0x180027897  mov     dword ptr [rsp+80h+var_58], r12d
0x18002789c  mov     [rsp+80h+var_60], eax
0x1800278a0  mov     r9, rdi
0x1800278a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278aa  mov     rcx, [rcx+10h]
0x1800278ae  call    WPP_SF_qDDqq
0x1800278b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800278ba  jmp     loc_180027609
0x1800278bf  lea     r8, [r15+0C0h]
0x1800278c6  xor     edx, edx
0x1800278c8  mov     rcx, r14
0x1800278cb  call    InitCompositionInputQueue
0x1800278d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800278d7  cmp     rax, rbx
0x1800278da  jz      loc_18002763C
0x1800278e0  test    byte ptr [rax+1Ch], 40h
0x1800278e4  jz      loc_18002763C
0x1800278ea  cmp     byte ptr [rax+19h], 4
0x1800278ee  jb      loc_18002763C
0x1800278f4  mov     rbx, [r15+0C8h]
0x1800278fb  call    cs:__imp_GetCurrentThreadId
0x180027901  mov     edx, 18h
0x180027906  mov     [rsp+80h+var_58], rbx
0x18002790b  mov     [rsp+80h+var_60], eax
0x18002790f  mov     r9, rdi
0x180027912  mov     r8, rsi
0x180027915  mov     rcx, cs:WPP_GLOBAL_Control
0x18002791c  mov     rcx, [rcx+10h]
0x180027920  call    WPP_SF_qDq
0x180027925  jmp     loc_18002763C
0x18002792a  lea     r8, [r15+50h]
0x18002792e  xor     edx, edx
0x180027930  mov     rcx, r14
0x180027933  call    InitCompositionInputQueue
0x180027938  mov     rax, cs:WPP_GLOBAL_Control
0x18002793f  cmp     rax, rbx
0x180027942  jz      loc_18002765C
0x180027948  test    byte ptr [rax+1Ch], 40h
0x18002794c  jz      loc_18002765C
0x180027952  cmp     byte ptr [rax+19h], 4
0x180027956  jb      loc_18002765C
0x18002795c  mov     rbx, [r15+58h]
0x180027960  call    cs:__imp_GetCurrentThreadId
0x180027966  mov     edx, 1Ah
0x18002796b  mov     [rsp+80h+var_58], rbx
0x180027970  mov     [rsp+80h+var_60], eax
0x180027974  mov     r9, rdi
0x180027977  mov     r8, rsi
0x18002797a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027981  mov     rcx, [rcx+10h]
0x180027985  call    WPP_SF_qDq
0x18002798a  jmp     loc_18002765C
0x18002798f  lea     r8, [r15+18h]
0x180027993  xor     edx, edx
0x180027995  mov     rcx, r14
0x180027998  call    InitCompositionInputQueue
0x18002799d  mov     rax, cs:WPP_GLOBAL_Control
0x1800279a4  lea     rbx, WPP_GLOBAL_Control
0x1800279ab  cmp     rax, rbx
0x1800279ae  jz      loc_180027652
0x1800279b4  test    byte ptr [rax+1Ch], 40h
0x1800279b8  jz      loc_180027652
0x1800279be  cmp     byte ptr [rax+19h], 4
0x1800279c2  jb      loc_180027652
0x1800279c8  mov     rbx, [r15+20h]
0x1800279cc  call    cs:__imp_GetCurrentThreadId
0x1800279d2  mov     edx, 19h
0x1800279d7  mov     [rsp+80h+var_58], rbx
0x1800279dc  mov     [rsp+80h+var_60], eax
0x1800279e0  mov     r9, rdi
0x1800279e3  mov     r8, rsi
0x1800279e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279ed  mov     rcx, [rcx+10h]
0x1800279f1  call    WPP_SF_qDq
0x1800279f6  jmp     loc_18002764B
0x1800279fb  test    r12b, 1
0x1800279ff  jz      short loc_180027A0A
0x180027a01  cmp     [r15+90h], rcx
0x180027a08  jnz     short loc_180027A39
0x180027a0a  test    r12b, 2
0x180027a0e  jz      short loc_180027A19
0x180027a10  cmp     [r15+0C8h], rcx
0x180027a17  jnz     short loc_180027A39
0x180027a19  test    r12b, 4
0x180027a1d  jz      short loc_180027A25
0x180027a1f  cmp     [r15+20h], rcx
0x180027a23  jnz     short loc_180027A39
0x180027a25  test    r12b, 8
0x180027a29  jz      loc_180027614
0x180027a2f  cmp     [r15+58h], rcx
0x180027a33  jz      loc_180027614
0x180027a39  cmp     rax, rbx
0x180027a3c  jnz     loc_180027B0A
0x180027a42  xor     edx, edx
0x180027a44  mov     ecx, 80070057h
0x180027a49  call    cs:__imp_RoOriginateError
0x180027a4f  mov     ebx, 80070057h
0x180027a54  jmp     loc_1800276DC
0x180027a59  mov     rax, [rcx]
0x180027a5c  mov     rdx, [rbp+hObject]
0x180027a60  mov     rax, [rax+118h]
0x180027a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a6c  mov     [rbp+var_30], eax
0x180027a6f  jmp     loc_18002777A
0x180027a74  test    byte ptr [rax+1Ch], 40h
0x180027a78  jz      loc_18002769D
0x180027a7e  cmp     byte ptr [rax+19h], 4
0x180027a82  jb      loc_18002769D
0x180027a88  mov     rbx, [r15+58h]
0x180027a8c  mov     rdi, [r15+20h]
0x180027a90  mov     rsi, [r15+0C8h]
0x180027a97  mov     r14, [r15+90h]
0x180027a9e  call    cs:__imp_GetCurrentThreadId
0x180027aa4  mov     [rsp+80h+var_40], rbx
0x180027aa9  mov     [rsp+80h+var_48], rdi
0x180027aae  mov     [rsp+80h+var_50], rsi
0x180027ab3  mov     [rsp+80h+var_58], r14
0x180027ab8  mov     [rsp+80h+var_60], eax
0x180027abc  mov     rdi, [rbp+var_20]
0x180027ac0  mov     r9, rdi
0x180027ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027aca  mov     rcx, [rcx+10h]
0x180027ace  call    WPP_SF_qDqqqq
0x180027ad3  lea     rsi, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027ada  mov     r14, [rbp+var_8]
0x180027ade  lea     rbx, WPP_GLOBAL_Control
0x180027ae5  jmp     loc_18002769D
0x180027aea  mov     r9d, eax; char *
0x180027aed  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180027af4  mov     edx, 2AEh; void *
0x180027af9  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
  ... truncated ...
```
