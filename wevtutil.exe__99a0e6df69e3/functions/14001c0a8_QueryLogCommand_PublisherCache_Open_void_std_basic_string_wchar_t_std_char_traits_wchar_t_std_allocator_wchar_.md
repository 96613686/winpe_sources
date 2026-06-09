# QueryLogCommand::PublisherCache::Open(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *,ulong)

- ea: `0x14001c0a8`
- end: `0x14001c1d7`
- name: `?Open@PublisherCache@QueryLogCommand@@QEAAPEAXPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WK@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b8e8`
- `0x14000be14`

## callees

- `0x14001c0a8`
- `0x14001c1e0`
- `0x14001c204`
- `0x14001c2f8`
- `0x140027df8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14001c12c`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x14001c12c`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x14001c119`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x14001c119`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14001c167`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14001c19f`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14001c167`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14001c19f`

## pseudocode

```c
EVT_HANDLE __fastcall QueryLogCommand::PublisherCache::Open(
        _QWORD *a1,
        void *a2,
        __int64 a3,
        const WCHAR *a4,
        LCID Locale)
{
  EVT_HANDLE v9; // rdi
  LANGID ThreadUILanguage; // ax
  LCID v11; // edi
  LANGID v12; // bp
  bool v13; // cc
  const WCHAR *v14; // rdx
  const WCHAR *v15; // rdx
  _QWORD *v16; // rax
  _BYTE v18[72]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  std::_Tree<std::_Tmap_traits<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>>>,0>>::find(
    a1,
    &v19);
  if ( v19 == *a1 )
  {
    v9 = 0;
  }
  else
  {
    v9 = *(EVT_HANDLE *)(v19 + 64);
    if ( v9 )
      return v9;
  }
  if ( *(_QWORD *)(a3 + 16) )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>>>,0>>::find(
      a1,
      &v19);
    if ( v19 == *a1 )
    {
      ThreadUILanguage = GetThreadUILanguage();
      v11 = Locale;
      v12 = ThreadUILanguage;
      if ( SetThreadUILanguage(Locale) == (_WORD)v11 )
      {
        v13 = *(_QWORD *)(a3 + 24) <= 7u;
        LOWORD(v19) = v12;
        BYTE2(v19) = 1;
        if ( v13 )
          v14 = (const WCHAR *)a3;
        else
          v14 = *(const WCHAR **)a3;
        v9 = EvtOpenPublisherMetadata(a2, v14, a4, 0, 0);
        tlx::_UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___::__UndoSolo__QueryLogCommand::PublisherCache::Open_::_8_::_lambda_1___(&v19);
      }
      else
      {
        if ( *(_QWORD *)(a3 + 24) <= 7u )
          v15 = (const WCHAR *)a3;
        else
          v15 = *(const WCHAR **)a3;
        v9 = EvtOpenPublisherMetadata(a2, v15, a4, v11, 0);
      }
      v16 = (_QWORD *)std::map<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>>>>::_Try_emplace<std::wstring const &,>(
                        a1,
                        v18,
                        a3);
      tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::reset(*v16 + 64LL, v9);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14001c0a8  mov     rax, rsp
0x14001c0ab  push    rbx
0x14001c0ac  push    rbp
0x14001c0ad  push    rsi
0x14001c0ae  push    rdi
0x14001c0af  push    r14
0x14001c0b1  push    r15
0x14001c0b3  sub     rsp, 48h
0x14001c0b7  mov     r15, rdx
0x14001c0ba  mov     r14, r9
0x14001c0bd  lea     rdx, [rax+8]
0x14001c0c1  mov     rbx, r8
0x14001c0c4  mov     rsi, rcx
0x14001c0c7  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@Uistring_less_ordinal@4@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>>>,0>>::find(std::wstring const &)
0x14001c0cc  mov     rax, [rsp+78h+arg_0]
0x14001c0d4  cmp     rax, [rsi]
0x14001c0d7  jnz     short loc_14001C0DD
0x14001c0d9  xor     edi, edi
0x14001c0db  jmp     short loc_14001C0EA
0x14001c0dd  mov     rdi, [rax+40h]
0x14001c0e1  test    rdi, rdi
0x14001c0e4  jnz     loc_14001C1C7
0x14001c0ea  cmp     qword ptr [rbx+10h], 0
0x14001c0ef  jz      loc_14001C1C7
0x14001c0f5  mov     r8, rbx
0x14001c0f8  lea     rdx, [rsp+78h+arg_0]
0x14001c100  mov     rcx, rsi
0x14001c103  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@Uistring_less_ordinal@4@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>>>,0>>::find(std::wstring const &)
0x14001c108  mov     rax, [rsi]
0x14001c10b  cmp     [rsp+78h+arg_0], rax
0x14001c113  jnz     loc_14001C1C7
0x14001c119  call    cs:__imp_GetThreadUILanguage
0x14001c11f  mov     edi, [rsp+78h+Locale]
0x14001c126  movzx   ecx, di; LangId
0x14001c129  movzx   ebp, ax
0x14001c12c  call    cs:__imp_SetThreadUILanguage
0x14001c132  cmp     ax, di
0x14001c135  jnz     short loc_14001C17F
0x14001c137  cmp     qword ptr [rbx+18h], 7
0x14001c13c  mov     word ptr [rsp+78h+arg_0], bp
0x14001c144  mov     byte ptr [rsp+78h+arg_0+2], 1
0x14001c14c  jbe     short loc_14001C153
0x14001c14e  mov     rdx, [rbx]
0x14001c151  jmp     short loc_14001C156
0x14001c153  mov     rdx, rbx; PublisherId
0x14001c156  xor     r9d, r9d; Locale
0x14001c159  mov     [rsp+78h+Flags], 0; Flags
0x14001c161  mov     r8, r14; LogFilePath
0x14001c164  mov     rcx, r15; Session
0x14001c167  call    cs:__imp_EvtOpenPublisherMetadata
0x14001c16d  lea     rcx, [rsp+78h+arg_0]
0x14001c175  mov     rdi, rax
0x14001c178  call    tlx___UndoSolo__QueryLogCommand__PublisherCache__Open____8____lambda_1_______UndoSolo__QueryLogCommand__PublisherCache__Open____8____lambda_1___
0x14001c17d  jmp     short loc_14001C1A8
0x14001c17f  cmp     qword ptr [rbx+18h], 7
0x14001c184  jbe     short loc_14001C18B
0x14001c186  mov     rdx, [rbx]
0x14001c189  jmp     short loc_14001C18E
0x14001c18b  mov     rdx, rbx; PublisherId
0x14001c18e  mov     r9d, edi; Locale
0x14001c191  mov     [rsp+78h+Flags], 0; Flags
0x14001c199  mov     r8, r14; LogFilePath
0x14001c19c  mov     rcx, r15; Session
0x14001c19f  call    cs:__imp_EvtOpenPublisherMetadata
0x14001c1a5  mov     rdi, rax
0x14001c1a8  mov     r8, rbx
0x14001c1ab  lea     rdx, [rsp+78h+var_48]
0x14001c1b0  mov     rcx, rsi
0x14001c1b3  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@Uistring_less_ordinal@4@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x14001c1b8  mov     rdx, rdi
0x14001c1bb  mov     rcx, [rax]
0x14001c1be  add     rcx, 40h ; '@'
0x14001c1c2  call    ?reset@?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::reset(void *)
0x14001c1c7  mov     rax, rdi
0x14001c1ca  add     rsp, 48h
0x14001c1ce  pop     r15
0x14001c1d0  pop     r14
0x14001c1d2  pop     rdi
0x14001c1d3  pop     rsi
0x14001c1d4  pop     rbp
0x14001c1d5  pop     rbx
0x14001c1d6  retn
```
