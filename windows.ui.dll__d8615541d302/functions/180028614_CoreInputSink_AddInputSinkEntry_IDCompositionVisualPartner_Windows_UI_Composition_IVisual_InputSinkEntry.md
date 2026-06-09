# CoreInputSink::AddInputSinkEntry(IDCompositionVisualPartner *,Windows::UI::Composition::IVisual *,_InputSinkEntry * *)

- ea: `0x180028614`
- end: `0x1800287f3`
- name: `?AddInputSinkEntry@CoreInputSink@@AEAAJPEAUIDCompositionVisualPartner@@PEAUIVisual@Composition@UI@Windows@@PEAPEAU_InputSinkEntry@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CoreInputSink *__hidden this, struct IDCompositionVisualPartner *, struct Windows::UI::Composition::IVisual *, struct _InputSinkEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002714c`

## callees

- `0x18000cdc8`
- `0x180028614`
- `0x18005f1a4`
- `0x18006c524`
- `0x180071d6c`
- `0x18009664c`
- `0x1800c7366`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002876f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002876f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800287c3`

## string_xrefs

- `0x1800287a7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\helper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoreInputSink::AddInputSinkEntry(
        CoreInputSink *this,
        struct IDCompositionVisualPartner *a2,
        struct Windows::UI::Composition::IVisual *a3,
        _InputSinkEntry ***a4)
{
  _InputSinkEntry **v8; // rax
  _InputSinkEntry **v9; // rbx
  unsigned int v10; // esi
  unsigned int v11; // edi
  _InputSinkEntry *v12; // rax
  _InputSinkEntry *v14; // rcx
  DWORD CurrentThreadId; // eax
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
      this,
      CurrentThreadId,
      a2,
      a3);
  }
  if ( (a3 == 0) == (a2 == 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\helper.cpp",
      (const char *)a4);
  *a4 = 0;
  v8 = (_InputSinkEntry **)operator new(0x150u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v8[39] = 0;
    v8[40] = 0;
    v10 = 0;
    memset_0(v8, 0, 0x150u);
    if ( v9[39] != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(struct IDCompositionVisualPartner *))(*(_QWORD *)a2 + 8LL))(a2);
      v14 = v9[39];
      v9[39] = a2;
      if ( v14 )
        (*(void (__fastcall **)(_InputSinkEntry *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    Microsoft::WRL::ComPtr<IUnknown>::operator=(v9 + 40, a3);
    *((_DWORD *)v9 + 4) = 296;
    v11 = ++CoreInputSink::_cInputSinks;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = GetCurrentThreadId();
      WPP_SF_qDqqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, this, v16, v9, this, v11);
    }
    v12 = CoreInputSink::_pInputSinkList;
    CoreInputSink::_pInputSinkList = (_InputSinkEntry *)v9;
    *v9 = v12;
    *a4 = v9;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v10;
}

```

## disassembly

```asm
0x180028614  push    rbx
0x180028616  push    rbp
0x180028617  push    rsi
0x180028618  push    rdi
0x180028619  push    r14
0x18002861b  push    r15
0x18002861d  sub     rsp, 48h
0x180028621  mov     r15, r9
0x180028624  mov     rbp, r8
0x180028627  mov     rdi, rdx
0x18002862a  mov     r14, rcx
0x18002862d  lea     rcx, WPP_GLOBAL_Control
0x180028634  mov     rax, cs:WPP_GLOBAL_Control
0x18002863b  cmp     rax, rcx
0x18002863e  jnz     loc_18002875B
0x180028644  mov     rcx, [rsp+78h]; this
0x180028649  xor     edx, edx
0x18002864b  test    rdi, rdi
0x18002864e  setz    dl
0x180028651  xor     eax, eax
0x180028653  test    rbp, rbp
0x180028656  setz    al
0x180028659  cmp     eax, edx
0x18002865b  jz      loc_1800287A7
0x180028661  mov     qword ptr [r15], 0
0x180028668  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002866f  mov     ecx, 150h; unsigned __int64
0x180028674  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028679  mov     rbx, rax
0x18002867c  test    rax, rax
0x18002867f  jz      loc_180028754
0x180028685  mov     qword ptr [rax+138h], 0
0x180028690  mov     qword ptr [rax+140h], 0
0x18002869b  xor     esi, esi
0x18002869d  xor     edx, edx; Val
0x18002869f  mov     r8d, 150h; Size
0x1800286a5  mov     rcx, rax; void *
0x1800286a8  call    memset_0
0x1800286ad  cmp     [rbx+138h], rdi
0x1800286b4  jnz     short loc_18002871A
0x1800286b6  lea     rcx, [rbx+140h]
0x1800286bd  mov     rdx, rbp
0x1800286c0  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x1800286c5  mov     dword ptr [rbx+10h], 128h
0x1800286cc  mov     edi, cs:?_cInputSinks@CoreInputSink@@0IA; uint CoreInputSink::_cInputSinks
0x1800286d2  inc     edi
0x1800286d4  mov     cs:?_cInputSinks@CoreInputSink@@0IA, edi; uint CoreInputSink::_cInputSinks
0x1800286da  mov     rax, cs:WPP_GLOBAL_Control
0x1800286e1  lea     rcx, WPP_GLOBAL_Control
0x1800286e8  cmp     rax, rcx
0x1800286eb  jz      short loc_1800286F7
0x1800286ed  test    byte ptr [rax+1Ch], 4
0x1800286f1  jnz     loc_1800287B9
0x1800286f7  mov     rax, cs:?_pInputSinkList@CoreInputSink@@0PEAU_InputSinkEntry@@EA; _InputSinkEntry * CoreInputSink::_pInputSinkList
0x1800286fe  mov     cs:?_pInputSinkList@CoreInputSink@@0PEAU_InputSinkEntry@@EA, rbx; _InputSinkEntry * CoreInputSink::_pInputSinkList
0x180028705  mov     [rbx], rax
0x180028708  mov     [r15], rbx
0x18002870b  mov     eax, esi
0x18002870d  add     rsp, 48h
0x180028711  pop     r15
0x180028713  pop     r14
0x180028715  pop     rdi
0x180028716  pop     rsi
0x180028717  pop     rbp
0x180028718  pop     rbx
0x180028719  retn
0x18002871a  test    rdi, rdi
0x18002871d  jz      short loc_18002872F
0x18002871f  mov     rax, [rdi]
0x180028722  mov     rcx, rdi
0x180028725  mov     rax, [rax+8]
0x180028729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002872e  nop
0x18002872f  mov     rcx, [rbx+138h]
0x180028736  mov     [rbx+138h], rdi
0x18002873d  test    rcx, rcx
0x180028740  jz      short loc_18002874F
0x180028742  mov     rax, [rcx]
0x180028745  mov     rax, [rax+10h]
0x180028749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002874e  nop
0x18002874f  jmp     loc_1800286B6
0x180028754  mov     esi, 8007000Eh
0x180028759  jmp     short loc_18002870B
0x18002875b  test    byte ptr [rax+1Ch], 40h
0x18002875f  jz      loc_180028644
0x180028765  cmp     byte ptr [rax+19h], 4
0x180028769  jb      loc_180028644
0x18002876f  call    cs:__imp_GetCurrentThreadId
0x180028775  mov     edx, 11h
0x18002877a  mov     [rsp+78h+var_48], rbp
0x18002877f  mov     [rsp+78h+var_50], rdi
0x180028784  mov     [rsp+78h+var_58], eax
0x180028788  mov     r9, r14
0x18002878b  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180028792  mov     rcx, cs:WPP_GLOBAL_Control
0x180028799  mov     rcx, [rcx+10h]
0x18002879d  call    WPP_SF_qDqq
0x1800287a2  jmp     loc_180028644
0x1800287a7  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800287ae  mov     edx, 20Ah; void *
0x1800287b3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800287b9  cmp     byte ptr [rax+19h], 4
0x1800287bd  jb      loc_1800286F7
0x1800287c3  call    cs:__imp_GetCurrentThreadId
0x1800287c9  mov     [rsp+78h+var_40], edi
0x1800287cd  mov     [rsp+78h+var_48], r14
0x1800287d2  mov     [rsp+78h+var_50], rbx
0x1800287d7  mov     [rsp+78h+var_58], eax
0x1800287db  mov     r9, r14
0x1800287de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287e5  mov     rcx, [rcx+10h]
0x1800287e9  call    WPP_SF_qDqqd
0x1800287ee  jmp     loc_1800286F7
```
