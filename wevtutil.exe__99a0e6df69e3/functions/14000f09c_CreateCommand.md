# CreateCommand

- ea: `0x14000f09c`
- end: `0x14000f938`
- name: `CreateCommand`
- size: `2204`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400238ac`

## callees

- `0x140002bd0`
- `0x14000d868`
- `0x14000f09c`
- `0x140010450`
- `0x1400196b0`
- `0x140022634`
- `0x140022688`
- `0x1400226dc`
- `0x140022cec`
- `0x140022f04`
- `0x140022fa8`
- `0x14002303c`
- `0x140023118`
- `0x14002320c`
- `0x14002445c`
- `0x140028908`
- `0x140031810`

## string_xrefs

- `0x14000f806`: `install-manifest`
- `0x14000f879`: `uninstall-manifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
QueryLogCommand **__fastcall CreateCommand(QueryLogCommand **a1, __int64 a2)
{
  __int64 Src; // rdi
  CommandBase *v4; // rax
  CommandBase *v5; // rdi
  QueryLogCommand **Publisher; // rax
  QueryLogCommand *v8; // rcx
  CommandBase *v9; // rax
  CommandBase *v10; // rax
  CommandBase *v11; // rax
  QueryLogCommand *v12; // rax
  QueryLogCommand *LogCommand; // rax
  CommandBase *v14; // rax
  CommandBase *v15; // rax
  QueryLogCommand **v16; // rax
  QueryLogCommand *v17; // rcx
  CommandBase *v18; // rax
  QueryLogCommand **v19; // rax
  QueryLogCommand *v20; // rcx
  const char *v21; // [rsp+20h] [rbp-69h]
  const wchar_t *v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+58h] [rbp-31h]
  const wchar_t *v24; // [rsp+60h] [rbp-29h] BYREF
  __int64 v25; // [rsp+68h] [rbp-21h]
  __int128 v26; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+90h] [rbp+7h] BYREF
  CommandBase *v29; // [rsp+100h] [rbp+77h] BYREF
  char v30; // [rsp+108h] [rbp+7Fh] BYREF

  Src = CommandArguments::GetArgument(a2, 0);
  v22 = L"ep";
  v23 = 2;
  v24 = L"enum-publishers";
  v25 = 15;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v24, &v22) )
  {
    if ( (unsigned __int8)IsEvtOpenPublisherEnumPresent() )
    {
      v4 = (CommandBase *)operator new(0x28u);
      v5 = v4;
      v29 = v4;
      if ( v4 )
      {
        CommandBase::CommandBase(v4, 0x2Du);
        *(_QWORD *)v5 = &EnumPublisherCommand::`vftable';
      }
      else
      {
        v5 = 0;
      }
LABEL_6:
      v29 = 0;
      *a1 = v5;
      std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(&v29);
      return a1;
    }
    goto LABEL_50;
  }
  v24 = L"gp";
  v25 = 2;
  v22 = L"get-publisher";
  v23 = 13;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
  {
    if ( (unsigned __int8)IsEvtQueryPresent() )
    {
      Publisher = (QueryLogCommand **)std::make_unique<GetPublisherCommand,,0>(&v29);
      v8 = *Publisher;
      *Publisher = 0;
      *a1 = v8;
      std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(&v29);
      return a1;
    }
    goto LABEL_50;
  }
  v24 = L"gl";
  v25 = 2;
  v22 = L"get-log";
  v23 = 7;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
  {
    if ( (unsigned __int8)IsEvtExportLogPresent() )
    {
      v9 = (CommandBase *)operator new(0x78u);
      v5 = v9;
      v29 = v9;
      if ( v9 )
      {
        CommandBase::CommandBase(v9, 0x2Bu);
        *(_QWORD *)v5 = &GetChannelCommand::`vftable';
        *(_OWORD *)((char *)v5 + 40) = 0;
        *((_QWORD *)v5 + 7) = 0;
        *((_QWORD *)v5 + 8) = 7;
        *((_WORD *)v5 + 20) = 0;
        *((_QWORD *)v5 + 9) = -1;
        *((_QWORD *)v5 + 10) = 0;
        *((_QWORD *)v5 + 11) = 0;
        *((_QWORD *)v5 + 12) = 0;
        *((_WORD *)v5 + 52) = 0;
        *((_BYTE *)v5 + 112) = 0;
      }
      else
      {
        v5 = 0;
      }
      goto LABEL_6;
    }
LABEL_50:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e84feadb56ea336140feb03498ba5aea_Traceguids, 87);
    }
    if ( *(_QWORD *)(Src + 24) > 7u )
      Src = *(_QWORD *)Src;
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v21, 177, 0x58u, (const wchar_t *)Src);
    throw (EvtException *)pExceptionObject;
  }
  v24 = L"sl";
  v25 = 2;
  v22 = L"set-log";
  v23 = 7;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
  {
    if ( (unsigned __int8)IsEvtExportLogPresent() )
    {
      v10 = (CommandBase *)operator new(0x68u);
      v5 = v10;
      v29 = v10;
      if ( v10 )
      {
        CommandBase::CommandBase(v10, 0x2Cu);
        *(_QWORD *)v5 = &SetChannelCommand::`vftable';
        *(_OWORD *)((char *)v5 + 40) = 0;
        *((_QWORD *)v5 + 7) = 0;
        *((_QWORD *)v5 + 8) = 7;
        *((_WORD *)v5 + 20) = 0;
        *(_OWORD *)((char *)v5 + 72) = 0;
        *((_QWORD *)v5 + 11) = 0;
        *((_QWORD *)v5 + 12) = 7;
        *((_WORD *)v5 + 36) = 0;
      }
      else
      {
        v5 = 0;
      }
      goto LABEL_6;
    }
    goto LABEL_50;
  }
  v24 = L"el";
  v25 = 2;
  v22 = L"enum-logs";
  v23 = 9;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
  {
    if ( (unsigned __int8)IsEvtOpenPublisherEnumPresent() )
    {
      v11 = (CommandBase *)operator new(0x28u);
      v5 = v11;
      v29 = v11;
      if ( v11 )
      {
        CommandBase::CommandBase(v11, 0x28u);
        *(_QWORD *)v5 = &EnumChannelCommand::`vftable';
      }
      else
      {
        v5 = 0;
      }
      goto LABEL_6;
    }
    goto LABEL_50;
  }
  v24 = L"qe";
  v25 = 2;
  v22 = L"query-events";
  v23 = 12;
  v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
  if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
  {
    if ( !(unsigned __int8)IsEvtQueryPresent() )
      goto LABEL_50;
    v12 = (QueryLogCommand *)operator new(0x108u);
    v29 = v12;
    if ( v12 )
      LogCommand = QueryLogCommand::QueryLogCommand(v12);
    else
      LogCommand = 0;
    v29 = 0;
    *a1 = LogCommand;
    std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(&v29);
  }
  else
  {
    v24 = L"gli";
    v25 = 3;
    v22 = L"get-loginfo";
    v23 = 11;
    v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
    if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
    {
      if ( (unsigned __int8)IsEvtOpenPublisherEnumPresent() )
      {
        v14 = (CommandBase *)operator new(0x78u);
        v5 = v14;
        v29 = v14;
        if ( v14 )
        {
          CommandBase::CommandBase(v14, 0x36u);
          *(_QWORD *)v5 = &GetLogInfoCommand::`vftable';
          *(_OWORD *)((char *)v5 + 40) = 0;
          *((_QWORD *)v5 + 7) = 0;
          *((_QWORD *)v5 + 8) = 7;
          *((_WORD *)v5 + 20) = 0;
          *((_QWORD *)v5 + 9) = -1;
          *((_QWORD *)v5 + 10) = 0;
          *((_QWORD *)v5 + 11) = 0;
          *((_QWORD *)v5 + 12) = 0;
          *((_WORD *)v5 + 52) = 0;
          *((_WORD *)v5 + 56) = 0;
        }
        else
        {
          v5 = 0;
        }
        goto LABEL_6;
      }
      goto LABEL_50;
    }
    v24 = L"cl";
    v25 = 2;
    v22 = L"clear-log";
    v23 = 9;
    v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
    if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
    {
      if ( (unsigned __int8)IsEvtOpenPublisherEnumPresent() )
      {
        v15 = (CommandBase *)operator new(0x68u);
        v5 = v15;
        v29 = v15;
        if ( v15 )
        {
          CommandBase::CommandBase(v15, 0x37u);
          *(_QWORD *)v5 = &ClearLogCommand::`vftable';
          *(_OWORD *)((char *)v5 + 40) = 0;
          *((_QWORD *)v5 + 7) = 0;
          *((_QWORD *)v5 + 8) = 7;
          *((_WORD *)v5 + 20) = 0;
          *(_OWORD *)((char *)v5 + 72) = 0;
          *((_QWORD *)v5 + 11) = 0;
          *((_QWORD *)v5 + 12) = 7;
          *((_WORD *)v5 + 36) = 0;
        }
        else
        {
          v5 = 0;
        }
        goto LABEL_6;
      }
      goto LABEL_50;
    }
    v24 = L"epl";
    v25 = 3;
    v22 = L"export-log";
    v23 = 10;
    v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
    if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
    {
      if ( (unsigned __int8)IsEvtExportLogPresent() )
      {
        v16 = (QueryLogCommand **)std::make_unique<ExportLogCommand,,0>(&v29);
        v17 = *v16;
        *v16 = 0;
        *a1 = v17;
        std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(&v29);
        return a1;
      }
      goto LABEL_50;
    }
    v24 = L"al";
    v25 = 2;
    v22 = L"archive-log";
    v23 = 11;
    v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
    if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
    {
      if ( (unsigned __int8)IsEvtOpenPublisherEnumPresent() )
      {
        v18 = (CommandBase *)operator new(0x50u);
        v5 = v18;
        v29 = v18;
        if ( v18 )
        {
          CommandBase::CommandBase(v18, 0x3Bu);
          *(_QWORD *)v5 = &ArchiveLogCommand::`vftable';
          *(_OWORD *)((char *)v5 + 40) = 0;
          *((_QWORD *)v5 + 7) = 0;
          *((_QWORD *)v5 + 8) = 7;
          *((_WORD *)v5 + 20) = 0;
          *((_DWORD *)v5 + 18) = 0;
        }
        else
        {
          v5 = 0;
        }
        goto LABEL_6;
      }
      goto LABEL_50;
    }
    v24 = L"im";
    v25 = 2;
    v22 = L"install-manifest";
    v23 = 16;
    v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
    if ( (unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
    {
      LOBYTE(v29) = 1;
    }
    else
    {
      v24 = L"um";
      v25 = 2;
      v22 = L"uninstall-manifest";
      v23 = 18;
      v26 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v27);
      if ( !(unsigned __int8)MatchCommandName(&v26, &v22, &v24) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e84feadb56ea336140feb03498ba5aea_Traceguids, 87);
        }
        if ( *(_QWORD *)(Src + 24) > 7u )
          Src = *(_QWORD *)Src;
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v21, 182, 6u, (const wchar_t *)Src);
        throw (EvtException *)pExceptionObject;
      }
      LOBYTE(v29) = 0;
    }
    v19 = (QueryLogCommand **)std::make_unique<InstallManifestCommand,bool,0>(&v30, &v29);
    v20 = *v19;
    *v19 = 0;
    *a1 = v20;
    std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(&v30);
  }
  return a1;
}

```

## disassembly

```asm
0x14000f09c  mov     [rsp-8+arg_0], rbx
0x14000f0a1  push    rbp
0x14000f0a2  push    rsi
0x14000f0a3  push    rdi
0x14000f0a4  push    r14
0x14000f0a6  push    r15
0x14000f0a8  lea     rbp, [rsp-37h]
0x14000f0ad  sub     rsp, 0C0h
0x14000f0b4  mov     rax, rdx
0x14000f0b7  mov     rbx, rcx
0x14000f0ba  xor     esi, esi
0x14000f0bc  xor     edx, edx
0x14000f0be  mov     rcx, rax
0x14000f0c1  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x14000f0c6  mov     rdi, rax
0x14000f0c9  lea     rax, aEp; "ep"
0x14000f0d0  mov     [rbp+57h+var_90], rax
0x14000f0d4  lea     r15d, [rsi+2]
0x14000f0d8  mov     [rbp+57h+var_88], r15
0x14000f0dc  lea     rax, aEnumPublishers; "enum-publishers"
0x14000f0e3  mov     [rbp+57h+var_80], rax
0x14000f0e7  mov     [rbp+57h+var_78], 0Fh
0x14000f0ef  lea     rdx, [rbp+57h+var_60]
0x14000f0f3  mov     rcx, rdi
0x14000f0f6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f0fb  movups  xmm0, xmmword ptr [rax]
0x14000f0fe  movdqu  [rbp+57h+var_70], xmm0
0x14000f103  lea     r8, [rbp+57h+var_90]
0x14000f107  lea     rdx, [rbp+57h+var_80]
0x14000f10b  lea     rcx, [rbp+57h+var_70]
0x14000f10f  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f114  lea     r14d, [rsi+7]
0x14000f118  test    al, al
0x14000f11a  jz      short loc_14000F181
0x14000f11c  call    IsEvtOpenPublisherEnumPresent
0x14000f121  test    al, al
0x14000f123  jz      loc_14000F77A
0x14000f129  lea     ecx, [rsi+28h]; dwBytes
0x14000f12c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f131  mov     rdi, rax
0x14000f134  mov     [rbp+57h+arg_10], rax
0x14000f138  test    rax, rax
0x14000f13b  jz      short loc_14000F154
0x14000f13d  lea     edx, [rsi+2Dh]; unsigned int
0x14000f140  mov     rcx, rax; this
0x14000f143  call    ??0CommandBase@@QEAA@I@Z; CommandBase::CommandBase(uint)
0x14000f148  lea     rax, ??_7EnumPublisherCommand@@6B@; const EnumPublisherCommand::`vftable'
0x14000f14f  mov     [rdi], rax
0x14000f152  jmp     short loc_14000F157
0x14000f154  mov     rdi, rsi
0x14000f157  mov     [rbp+57h+arg_10], rsi
0x14000f15b  mov     [rbx], rdi
0x14000f15e  lea     rcx, [rbp+57h+arg_10]
0x14000f162  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f167  mov     rax, rbx
0x14000f16a  mov     rbx, [rsp+0E0h+arg_0]
0x14000f172  add     rsp, 0C0h
0x14000f179  pop     r15
0x14000f17b  pop     r14
0x14000f17d  pop     rdi
0x14000f17e  pop     rsi
0x14000f17f  pop     rbp
0x14000f180  retn
0x14000f181  lea     rax, aGp; "gp"
0x14000f188  mov     [rbp+57h+var_80], rax
0x14000f18c  mov     [rbp+57h+var_78], r15
0x14000f190  lea     rax, aGetPublisher; "get-publisher"
0x14000f197  mov     [rbp+57h+var_90], rax
0x14000f19b  mov     [rbp+57h+var_88], 0Dh
0x14000f1a3  lea     rdx, [rbp+57h+var_60]
0x14000f1a7  mov     rcx, rdi
0x14000f1aa  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f1af  movups  xmm0, xmmword ptr [rax]
0x14000f1b2  movdqu  [rbp+57h+var_70], xmm0
0x14000f1b7  lea     r8, [rbp+57h+var_80]
0x14000f1bb  lea     rdx, [rbp+57h+var_90]
0x14000f1bf  lea     rcx, [rbp+57h+var_70]
0x14000f1c3  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f1c8  test    al, al
0x14000f1ca  jz      short loc_14000F1F9
0x14000f1cc  call    IsEvtQueryPresent
0x14000f1d1  test    al, al
0x14000f1d3  jz      loc_14000F77A
0x14000f1d9  lea     rcx, [rbp+57h+arg_10]
0x14000f1dd  call    ??$make_unique@VGetPublisherCommand@@$$V$0A@@std@@YA?AV?$unique_ptr@VGetPublisherCommand@@U?$default_delete@VGetPublisherCommand@@@std@@@0@XZ; std::make_unique<GetPublisherCommand,,0>(void)
0x14000f1e2  mov     rcx, [rax]
0x14000f1e5  mov     [rax], rsi
0x14000f1e8  mov     [rbx], rcx
0x14000f1eb  lea     rcx, [rbp+57h+arg_10]
0x14000f1ef  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f1f4  jmp     loc_14000F167
0x14000f1f9  lea     rax, aGl; "gl"
0x14000f200  mov     [rbp+57h+var_80], rax
0x14000f204  mov     [rbp+57h+var_78], r15
0x14000f208  lea     rax, aGetLog; "get-log"
0x14000f20f  mov     [rbp+57h+var_90], rax
0x14000f213  mov     [rbp+57h+var_88], r14
0x14000f217  lea     rdx, [rbp+57h+var_60]
0x14000f21b  mov     rcx, rdi
0x14000f21e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f223  movups  xmm0, xmmword ptr [rax]
0x14000f226  movdqu  [rbp+57h+var_70], xmm0
0x14000f22b  lea     r8, [rbp+57h+var_80]
0x14000f22f  lea     rdx, [rbp+57h+var_90]
0x14000f233  lea     rcx, [rbp+57h+var_70]
0x14000f237  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f23c  test    al, al
0x14000f23e  jz      loc_14000F2C7
0x14000f244  call    IsEvtExportLogPresent
0x14000f249  test    al, al
0x14000f24b  jz      loc_14000F77A
0x14000f251  mov     ecx, 78h ; 'x'; dwBytes
0x14000f256  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f25b  mov     rdi, rax
0x14000f25e  mov     [rbp+57h+arg_10], rax
0x14000f262  test    rax, rax
0x14000f265  jz      short loc_14000F2AF
0x14000f267  mov     edx, 2Bh ; '+'; unsigned int
0x14000f26c  mov     rcx, rax; this
0x14000f26f  call    ??0CommandBase@@QEAA@I@Z; CommandBase::CommandBase(uint)
0x14000f274  lea     rax, ??_7GetChannelCommand@@6B@; const GetChannelCommand::`vftable'
0x14000f27b  mov     [rdi], rax
0x14000f27e  xorps   xmm0, xmm0
0x14000f281  movups  xmmword ptr [rdi+28h], xmm0
0x14000f285  mov     [rdi+38h], rsi
0x14000f289  mov     [rdi+40h], r14
0x14000f28d  mov     [rdi+28h], si
0x14000f291  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x14000f299  mov     [rdi+50h], rsi
0x14000f29d  mov     [rdi+58h], rsi
0x14000f2a1  mov     [rdi+60h], rsi
0x14000f2a5  mov     [rdi+68h], si
0x14000f2a9  mov     [rdi+70h], sil
0x14000f2ad  jmp     short loc_14000F2B2
0x14000f2af  mov     rdi, rsi
0x14000f2b2  mov     [rbp+57h+arg_10], rsi
0x14000f2b6  mov     [rbx], rdi
0x14000f2b9  lea     rcx, [rbp+57h+arg_10]
0x14000f2bd  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f2c2  jmp     loc_14000F167
0x14000f2c7  lea     rax, aSl; "sl"
0x14000f2ce  mov     [rbp+57h+var_80], rax
0x14000f2d2  mov     [rbp+57h+var_78], r15
0x14000f2d6  lea     rax, aSetLog; "set-log"
0x14000f2dd  mov     [rbp+57h+var_90], rax
0x14000f2e1  mov     [rbp+57h+var_88], r14
0x14000f2e5  lea     rdx, [rbp+57h+var_60]
0x14000f2e9  mov     rcx, rdi
0x14000f2ec  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f2f1  movups  xmm0, xmmword ptr [rax]
0x14000f2f4  movdqu  [rbp+57h+var_70], xmm0
0x14000f2f9  lea     r8, [rbp+57h+var_80]
0x14000f2fd  lea     rdx, [rbp+57h+var_90]
0x14000f301  lea     rcx, [rbp+57h+var_70]
0x14000f305  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f30a  test    al, al
0x14000f30c  jz      short loc_14000F385
0x14000f30e  call    IsEvtExportLogPresent
0x14000f313  test    al, al
0x14000f315  jz      loc_14000F77A
0x14000f31b  mov     ecx, 68h ; 'h'; dwBytes
0x14000f320  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f325  mov     rdi, rax
0x14000f328  mov     [rbp+57h+arg_10], rax
0x14000f32c  test    rax, rax
0x14000f32f  jz      short loc_14000F36D
0x14000f331  mov     edx, 2Ch ; ','; unsigned int
0x14000f336  mov     rcx, rax; this
0x14000f339  call    ??0CommandBase@@QEAA@I@Z; CommandBase::CommandBase(uint)
0x14000f33e  lea     rax, ??_7SetChannelCommand@@6B@; const SetChannelCommand::`vftable'
0x14000f345  mov     [rdi], rax
0x14000f348  xorps   xmm0, xmm0
0x14000f34b  movups  xmmword ptr [rdi+28h], xmm0
0x14000f34f  mov     [rdi+38h], rsi
0x14000f353  mov     [rdi+40h], r14
0x14000f357  mov     [rdi+28h], si
0x14000f35b  movups  xmmword ptr [rdi+48h], xmm0
0x14000f35f  mov     [rdi+58h], rsi
0x14000f363  mov     [rdi+60h], r14
0x14000f367  mov     [rdi+48h], si
0x14000f36b  jmp     short loc_14000F370
0x14000f36d  mov     rdi, rsi
0x14000f370  mov     [rbp+57h+arg_10], rsi
0x14000f374  mov     [rbx], rdi
0x14000f377  lea     rcx, [rbp+57h+arg_10]
0x14000f37b  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f380  jmp     loc_14000F167
0x14000f385  lea     rax, aEl; "el"
0x14000f38c  mov     [rbp+57h+var_80], rax
0x14000f390  mov     [rbp+57h+var_78], r15
0x14000f394  lea     rax, aEnumLogs; "enum-logs"
0x14000f39b  mov     [rbp+57h+var_90], rax
0x14000f39f  mov     [rbp+57h+var_88], 9
0x14000f3a7  lea     rdx, [rbp+57h+var_60]
0x14000f3ab  mov     rcx, rdi
0x14000f3ae  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f3b3  movups  xmm0, xmmword ptr [rax]
0x14000f3b6  movdqu  [rbp+57h+var_70], xmm0
0x14000f3bb  lea     r8, [rbp+57h+var_80]
0x14000f3bf  lea     rdx, [rbp+57h+var_90]
0x14000f3c3  lea     rcx, [rbp+57h+var_70]
0x14000f3c7  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f3cc  test    al, al
0x14000f3ce  jz      short loc_14000F424
0x14000f3d0  call    IsEvtOpenPublisherEnumPresent
0x14000f3d5  test    al, al
0x14000f3d7  jz      loc_14000F77A
0x14000f3dd  mov     ecx, 28h ; '('; dwBytes
0x14000f3e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f3e7  mov     rdi, rax
0x14000f3ea  mov     [rbp+57h+arg_10], rax
0x14000f3ee  test    rax, rax
0x14000f3f1  jz      short loc_14000F40C
0x14000f3f3  mov     edx, 28h ; '('; unsigned int
0x14000f3f8  mov     rcx, rax; this
0x14000f3fb  call    ??0CommandBase@@QEAA@I@Z; CommandBase::CommandBase(uint)
0x14000f400  lea     rax, ??_7EnumChannelCommand@@6B@; const EnumChannelCommand::`vftable'
0x14000f407  mov     [rdi], rax
0x14000f40a  jmp     short loc_14000F40F
0x14000f40c  mov     rdi, rsi
0x14000f40f  mov     [rbp+57h+arg_10], rsi
0x14000f413  mov     [rbx], rdi
0x14000f416  lea     rcx, [rbp+57h+arg_10]
0x14000f41a  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f41f  jmp     loc_14000F167
0x14000f424  lea     rax, aQe; "qe"
0x14000f42b  mov     [rbp+57h+var_80], rax
0x14000f42f  mov     [rbp+57h+var_78], r15
0x14000f433  lea     rax, aQueryEvents; "query-events"
0x14000f43a  mov     [rbp+57h+var_90], rax
0x14000f43e  mov     [rbp+57h+var_88], 0Ch
0x14000f446  lea     rdx, [rbp+57h+var_60]
0x14000f44a  mov     rcx, rdi
0x14000f44d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f452  movups  xmm0, xmmword ptr [rax]
0x14000f455  movdqu  [rbp+57h+var_70], xmm0
0x14000f45a  lea     r8, [rbp+57h+var_80]
0x14000f45e  lea     rdx, [rbp+57h+var_90]
0x14000f462  lea     rcx, [rbp+57h+var_70]
0x14000f466  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f46b  test    al, al
0x14000f46d  jz      short loc_14000F4B1
0x14000f46f  call    IsEvtQueryPresent
0x14000f474  test    al, al
0x14000f476  jz      loc_14000F77A
0x14000f47c  mov     ecx, 108h; dwBytes
0x14000f481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f486  mov     [rbp+57h+arg_10], rax
0x14000f48a  test    rax, rax
0x14000f48d  jz      short loc_14000F499
0x14000f48f  mov     rcx, rax; this
0x14000f492  call    ??0QueryLogCommand@@QEAA@XZ; QueryLogCommand::QueryLogCommand(void)
0x14000f497  jmp     short loc_14000F49C
0x14000f499  mov     rax, rsi
0x14000f49c  mov     [rbp+57h+arg_10], rsi
0x14000f4a0  mov     [rbx], rax
0x14000f4a3  lea     rcx, [rbp+57h+arg_10]
0x14000f4a7  call    ??1?$unique_ptr@VEnumPublisherCommand@@U?$default_delete@VEnumPublisherCommand@@@std@@@std@@QEAA@XZ; std::unique_ptr<EnumPublisherCommand>::~unique_ptr<EnumPublisherCommand>(void)
0x14000f4ac  jmp     loc_14000F167
0x14000f4b1  lea     rax, aGli; "gli"
0x14000f4b8  mov     [rbp+57h+var_80], rax
0x14000f4bc  mov     [rbp+57h+var_78], 3
0x14000f4c4  lea     rax, aGetLoginfo; "get-loginfo"
0x14000f4cb  mov     [rbp+57h+var_90], rax
0x14000f4cf  mov     [rbp+57h+var_88], 0Bh
0x14000f4d7  lea     rdx, [rbp+57h+var_60]
0x14000f4db  mov     rcx, rdi
0x14000f4de  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000f4e3  movups  xmm0, xmmword ptr [rax]
0x14000f4e6  movdqu  [rbp+57h+var_70], xmm0
0x14000f4eb  lea     r8, [rbp+57h+var_80]
0x14000f4ef  lea     rdx, [rbp+57h+var_90]
0x14000f4f3  lea     rcx, [rbp+57h+var_70]
0x14000f4f7  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000f4fc  test    al, al
0x14000f4fe  jz      loc_14000F587
0x14000f504  call    IsEvtOpenPublisherEnumPresent
0x14000f509  test    al, al
0x14000f50b  jz      loc_14000F77A
0x14000f511  mov     ecx, 78h ; 'x'; dwBytes
0x14000f516  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f51b  mov     rdi, rax
0x14000f51e  mov     [rbp+57h+arg_10], rax
0x14000f522  test    rax, rax
0x14000f525  jz      short loc_14000F56F
0x14000f527  mov     edx, 36h ; '6'; unsigned int
0x14000f52c  mov     rcx, rax; this
0x14000f52f  call    ??0CommandBase@@QEAA@I@Z; CommandBase::CommandBase(uint)
0x14000f534  lea     rax, ??_7GetLogInfoCommand@@6B@; const GetLogInfoCommand::`vftable'
0x14000f53b  mov     [rdi], rax
0x14000f53e  xorps   xmm0, xmm0
0x14000f541  movups  xmmword ptr [rdi+28h], xmm0
0x14000f545  mov     [rdi+38h], rsi
0x14000f549  mov     [rdi+40h], r14
0x14000f54d  mov     [rdi+28h], si
0x14000f551  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x14000f559  mov     [rdi+50h], rsi
0x14000f55d  mov     [rdi+58h], rsi
0x14000f561  mov     [rdi+60h], rsi
0x14000f565  mov     [rdi+68h], si
  ... truncated ...
```
