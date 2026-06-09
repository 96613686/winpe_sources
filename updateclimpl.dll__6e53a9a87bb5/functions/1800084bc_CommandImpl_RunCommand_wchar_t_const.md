# CommandImpl::RunCommand(wchar_t const *)

- ea: `0x1800084bc`
- end: `0x180008846`
- name: `?RunCommand@CommandImpl@@QEAAJPEB_W@Z`
- size: `906`
- prototype: `__int64 __fastcall(CommandImpl *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008e40`

## callees

- `0x180007dec`
- `0x180008408`
- `0x1800084bc`
- `0x180008910`
- `0x180008b90`
- `0x180008cdc`
- `0x180008f78`
- `0x18000917c`
- `0x180009320`
- `0x18000acf4`
- `0x18000c3d0`
- `0x18000d1cc`
- `0x18000d3b4`
- `0x18001022c`
- `0x180010310`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008538`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180008519`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180008519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000852c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000852c`

## pseudocode

```c
__int64 __fastcall CommandImpl::RunCommand(CommandImpl *this, const wchar_t *a2)
{
  wchar_t *v4; // r15
  int v5; // eax
  LPWSTR *v6; // rax
  void *v7; // rcx
  signed int LastError; // eax
  signed int v9; // esi
  const wchar_t *v10; // rcx
  const struct CommandEntry near *const *v11; // rbx
  unsigned int v12; // r14d
  char *v13; // rdi
  _QWORD *ResourceString; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  char *v17; // rbx
  char *v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned int v25; // r8d
  unsigned int v26; // ebx
  unsigned int v27; // edi
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  char *v31; // rdx
  __int64 v32; // rax
  unsigned __int64 v33; // [rsp+20h] [rbp-E0h]
  wchar_t *v34; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v35[32]; // [rsp+38h] [rbp-C8h] BYREF
  int pNumArgs; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v37[21]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v34 = 0;
  v5 = 0;
  pNumArgs = 0;
  if ( !a2 || !*a2 )
    goto LABEL_10;
  v6 = CommandLineToArgvW(a2, &pNumArgs);
  v7 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v6;
  if ( v7 )
    LocalFree(v7);
  if ( *((_QWORD *)this + 1) )
  {
    v5 = pNumArgs;
LABEL_10:
    v9 = CommandLineBase::Parse(this, *((const wchar_t ***)this + 1), v5, (const wchar_t **)&v34, v33);
    v4 = v34;
    goto LABEL_11;
  }
  LastError = GetLastError();
  v9 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v9 = LastError;
LABEL_11:
  v10 = (const wchar_t *)*((_QWORD *)this + 3);
  if ( v10 && *v10 )
  {
    if ( *((_QWORD *)this + 4) && !wcsicmp(v10, L"help") )
    {
      *((_QWORD *)this + 3) = *((_QWORD *)this + 4);
      *((_QWORD *)this + 4) = 0;
      *((_BYTE *)this + 16) = 1;
    }
    v11 = &CommandImpl::_commands;
    do
    {
      if ( !wcsicmp(*(const wchar_t **)v11, *((const wchar_t **)this + 3)) )
      {
        if ( *((_BYTE *)this + 16) && (v25 = *((_DWORD *)v11 + 7)) != 0 )
        {
          CommandImpl::ShowDetailedHelp(*(const wchar_t **)v11, *((_DWORD *)v11 + 6), v25);
          return 0;
        }
        else
        {
          memset(v37, 0, 0x148u);
          DWORD2(v37[0]) = 0;
          BYTE12(v37[0]) = 0;
          BYTE8(v37[4]) = 0;
          LODWORD(v37[3]) = 0;
          *((_QWORD *)&v37[3] + 1) = "RunCmd";
          *(_QWORD *)&v37[4] = 0;
          LODWORD(v37[5]) = 0;
          v37[15] = 0;
          memset((char *)&v37[5] + 8, 0, 0x98u);
          LODWORD(v37[16]) = 1;
          *((_QWORD *)&v37[16] + 1) = 0;
          *(_QWORD *)&v37[17] = (char *)v37 + 8;
          *((_QWORD *)&v37[17] + 1) = 0;
          *(_QWORD *)&v37[18] = 0;
          *((_QWORD *)&v37[18] + 1) = v37;
          *(_QWORD *)&v37[19] = 0;
          DWORD2(v37[19]) = 0;
          *(_QWORD *)&v37[20] = &v37[3];
          *(_QWORD *)&v37[0] = &Telemetry4UpdateCli::RunCmd::`vftable';
          Telemetry4UpdateCli::RunCmd::StartActivity(
            (Telemetry4UpdateCli::RunCmd *)v37,
            *((const wchar_t **)this + 3),
            *((const wchar_t **)this + 4));
          v26 = CommandImpl::ProcessInternalCommand(
                  *((int (**)(const wchar_t *, const wchar_t *))v11 + 2),
                  a2,
                  *(const wchar_t **)v11);
          Telemetry4UpdateCli::RunCmd::Stop(
            (Telemetry4UpdateCli::RunCmd *)v37,
            *((const wchar_t **)this + 3),
            *((const wchar_t **)this + 4),
            v26);
          Telemetry4UpdateCli::RunCmd::~RunCmd((Telemetry4UpdateCli::RunCmd *)v37);
          return v26;
        }
      }
      v11 += 4;
    }
    while ( v11 != (const struct CommandEntry near *const *)&off_180017CE0 );
    v12 = CommandImpl::ShowHelp(a2, L"help");
    v13 = (char *)*((_QWORD *)this + 3);
    ResourceString = (_QWORD *)CliUtils::LoadResourceString(v35, 2003);
    v15 = ResourceString[2];
    if ( ResourceString[3] > 7u )
      ResourceString = (_QWORD *)*ResourceString;
    v16 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcerr, ResourceString, v15);
    v17 = byte_180018020;
    v18 = byte_180018020;
    if ( v13 )
      v18 = v13;
    v19 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v16, v18);
    std::endl<wchar_t,std::char_traits<wchar_t>>(v19);
    std::wstring::~wstring(v35);
    if ( v9 < 0 )
    {
      v20 = (_QWORD *)CliUtils::LoadResourceString(v35, 2003);
      v21 = v20[2];
      if ( v20[3] > 7u )
        v20 = (_QWORD *)*v20;
      v22 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcerr, v20, v21);
      if ( v4 )
        v17 = (char *)v4;
      v23 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v22, v17);
      std::endl<wchar_t,std::char_traits<wchar_t>>(v23);
      std::wstring::~wstring(v35);
    }
    return v12;
  }
  else
  {
    v27 = CommandImpl::ShowHelp(a2, L"help");
    if ( v9 < 0 )
    {
      v28 = (_QWORD *)CliUtils::LoadResourceString(v35, 2003);
      v29 = v28[2];
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      v30 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcerr, v28, v29);
      v31 = byte_180018020;
      if ( v4 )
        v31 = (char *)v4;
      v32 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v30, v31);
      std::endl<wchar_t,std::char_traits<wchar_t>>(v32);
      std::wstring::~wstring(v35);
    }
    return v27;
  }
}

```

## disassembly

```asm
0x1800084bc  mov     [rsp-8+arg_10], rbx
0x1800084c1  mov     [rsp-8+arg_18], rsi
0x1800084c6  push    rbp
0x1800084c7  push    rdi
0x1800084c8  push    r12
0x1800084ca  push    r14
0x1800084cc  push    r15
0x1800084ce  lea     rbp, [rsp-0C0h]
0x1800084d6  sub     rsp, 1C0h
0x1800084dd  mov     rax, cs:__security_cookie
0x1800084e4  xor     rax, rsp
0x1800084e7  mov     [rbp+0E0h+var_30], rax
0x1800084ee  mov     r14, rdx
0x1800084f1  mov     rdi, rcx
0x1800084f4  xor     r12d, r12d
0x1800084f7  mov     r15d, r12d
0x1800084fa  mov     [rsp+1E0h+var_1B0], r12
0x1800084ff  mov     eax, r12d
0x180008502  mov     [rsp+1E0h+pNumArgs], eax
0x180008506  test    rdx, rdx
0x180008509  jz      short loc_180008552
0x18000850b  cmp     [rdx], r12w
0x18000850f  jz      short loc_180008552
0x180008511  lea     rdx, [rsp+1E0h+pNumArgs]; pNumArgs
0x180008516  mov     rcx, r14; lpCmdLine
0x180008519  call    cs:__imp_CommandLineToArgvW
0x18000851f  mov     rcx, [rdi+8]; hMem
0x180008523  mov     [rdi+8], rax
0x180008527  test    rcx, rcx
0x18000852a  jz      short loc_180008532
0x18000852c  call    cs:__imp_LocalFree
0x180008532  cmp     [rdi+8], r12
0x180008536  jnz     short loc_18000854E
0x180008538  call    cs:__imp_GetLastError
0x18000853e  movzx   esi, ax
0x180008541  or      esi, 80070000h
0x180008547  test    eax, eax
0x180008549  cmovle  esi, eax
0x18000854c  jmp     short loc_18000856D
0x18000854e  mov     eax, [rsp+1E0h+pNumArgs]
0x180008552  movsxd  r8, eax; unsigned __int64
0x180008555  lea     r9, [rsp+1E0h+var_1B0]; wchar_t **
0x18000855a  mov     rdx, [rdi+8]; wchar_t **
0x18000855e  mov     rcx, rdi; this
0x180008561  call    ?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z; CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)
0x180008566  mov     esi, eax
0x180008568  mov     r15, [rsp+1E0h+var_1B0]
0x18000856d  mov     rcx, [rdi+18h]; String1
0x180008571  test    rcx, rcx
0x180008574  jz      loc_1800087AE
0x18000857a  cmp     [rcx], r12w
0x18000857e  jz      loc_1800087AE
0x180008584  cmp     [rdi+20h], r12
0x180008588  jz      short loc_1800085AA
0x18000858a  lea     rdx, aHelp; "help"
0x180008591  call    _wcsicmp
0x180008596  test    eax, eax
0x180008598  jnz     short loc_1800085AA
0x18000859a  mov     rax, [rdi+20h]
0x18000859e  mov     [rdi+18h], rax
0x1800085a2  mov     [rdi+20h], r12
0x1800085a6  mov     byte ptr [rdi+10h], 1
0x1800085aa  lea     rbx, ?_commands@CommandImpl@@0QBUCommandEntry@@B; CommandEntry const near * const CommandImpl::_commands
0x1800085b1  mov     rdx, [rdi+18h]; String2
0x1800085b5  mov     rcx, [rbx]; String1
0x1800085b8  call    _wcsicmp
0x1800085bd  test    eax, eax
0x1800085bf  jz      loc_1800086A2
0x1800085c5  add     rbx, 20h ; ' '
0x1800085c9  lea     rax, off_180017CE0
0x1800085d0  cmp     rbx, rax
0x1800085d3  jnz     short loc_1800085B1
0x1800085d5  lea     rdx, aHelp; "help"
0x1800085dc  mov     rcx, r14; wchar_t *
0x1800085df  call    ?ShowHelp@CommandImpl@@CAJPEB_W0@Z; CommandImpl::ShowHelp(wchar_t const *,wchar_t const *)
0x1800085e4  mov     r14d, eax
0x1800085e7  mov     rdi, [rdi+18h]
0x1800085eb  mov     edx, 7D3h
0x1800085f0  lea     rcx, [rsp+1E0h+var_1A8]
0x1800085f5  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x1800085fa  nop
0x1800085fb  mov     r8, [rax+10h]
0x1800085ff  cmp     qword ptr [rax+18h], 7
0x180008604  jbe     short loc_180008609
0x180008606  mov     rax, [rax]
0x180008609  mov     rdx, rax
0x18000860c  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x180008613  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008618  lea     rbx, byte_180018020
0x18000861f  mov     rdx, rbx
0x180008622  test    rdi, rdi
0x180008625  cmovnz  rdx, rdi
0x180008629  mov     rcx, rax
0x18000862c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008631  mov     rcx, rax
0x180008634  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180008639  nop
0x18000863a  lea     rcx, [rsp+1E0h+var_1A8]
0x18000863f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008644  test    esi, esi
0x180008646  jns     short loc_18000869A
0x180008648  mov     edx, 7D3h
0x18000864d  lea     rcx, [rsp+1E0h+var_1A8]
0x180008652  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x180008657  nop
0x180008658  mov     r8, [rax+10h]
0x18000865c  cmp     qword ptr [rax+18h], 7
0x180008661  jbe     short loc_180008666
0x180008663  mov     rax, [rax]
0x180008666  mov     rdx, rax
0x180008669  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x180008670  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180008675  test    r15, r15
0x180008678  cmovnz  rbx, r15
0x18000867c  mov     rdx, rbx
0x18000867f  mov     rcx, rax
0x180008682  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008687  mov     rcx, rax
0x18000868a  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x18000868f  nop
0x180008690  lea     rcx, [rsp+1E0h+var_1A8]
0x180008695  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000869a  mov     eax, r14d
0x18000869d  jmp     loc_18000881B
0x1800086a2  cmp     [rdi+10h], r12b
0x1800086a6  jz      short loc_1800086C3
0x1800086a8  mov     r8d, [rbx+1Ch]; unsigned int
0x1800086ac  test    r8d, r8d
0x1800086af  jz      short loc_1800086C3
0x1800086b1  mov     edx, [rbx+18h]; unsigned int
0x1800086b4  mov     rcx, [rbx]; wchar_t *
0x1800086b7  call    ?ShowDetailedHelp@CommandImpl@@CAXPEB_WIK@Z; CommandImpl::ShowDetailedHelp(wchar_t const *,uint,ulong)
0x1800086bc  xor     eax, eax
0x1800086be  jmp     loc_18000881B
0x1800086c3  xor     edx, edx; Val
0x1800086c5  mov     r8d, 148h; Size
0x1800086cb  lea     rcx, [rsp+1E0h+var_180]; void *
0x1800086d0  call    memset
0x1800086d5  nop
0x1800086d6  mov     [rsp+1E0h+var_178], r12d
0x1800086db  mov     [rsp+1E0h+var_174], r12b
0x1800086e0  mov     [rbp+0E0h+var_138], r12b
0x1800086e4  mov     [rbp+0E0h+var_150], r12d
0x1800086e8  lea     rax, aRuncmd; "RunCmd"
0x1800086ef  mov     [rbp+0E0h+var_148], rax
0x1800086f3  mov     [rbp+0E0h+var_140], r12
0x1800086f7  mov     [rbp+0E0h+var_130], r12d
0x1800086fb  xorps   xmm0, xmm0
0x1800086fe  movdqa  [rbp+0E0h+var_90], xmm0
0x180008703  xor     edx, edx; Val
0x180008705  mov     r8d, 98h; Size
0x18000870b  lea     rcx, [rbp+0E0h+var_128]; void *
0x18000870f  call    memset
0x180008714  mov     [rbp+0E0h+var_80], 1
0x18000871b  xor     eax, eax
0x18000871d  mov     [rbp+0E0h+var_78], rax
0x180008721  lea     rax, [rsp+1E0h+var_178]
0x180008726  mov     [rbp+0E0h+var_70], rax
0x18000872a  mov     [rbp+0E0h+var_68], r12
0x18000872e  mov     [rbp+0E0h+var_60], r12
0x180008735  lea     rax, [rsp+1E0h+var_180]
0x18000873a  mov     [rbp+0E0h+var_58], rax
0x180008741  mov     [rbp+0E0h+var_50], r12
0x180008748  mov     [rbp+0E0h+var_48], r12d
0x18000874f  lea     rax, [rbp+0E0h+var_150]
0x180008753  mov     [rbp+0E0h+var_40], rax
0x18000875a  lea     rax, ??_7RunCmd@Telemetry4UpdateCli@@6B@; const Telemetry4UpdateCli::RunCmd::`vftable'
0x180008761  mov     [rsp+1E0h+var_180], rax
0x180008766  mov     r8, [rdi+20h]; wchar_t *
0x18000876a  mov     rdx, [rdi+18h]; wchar_t *
0x18000876e  lea     rcx, [rsp+1E0h+var_180]; this
0x180008773  call    ?StartActivity@RunCmd@Telemetry4UpdateCli@@QEAAXPEB_W0@Z; Telemetry4UpdateCli::RunCmd::StartActivity(wchar_t const *,wchar_t const *)
0x180008778  nop
0x180008779  mov     r8, [rbx]; wchar_t *
0x18000877c  mov     rdx, r14; wchar_t *
0x18000877f  mov     rcx, [rbx+10h]; int (*)(const wchar_t *, const wchar_t *)
0x180008783  call    ?ProcessInternalCommand@CommandImpl@@CAJP6AJPEB_W0@Z00@Z; CommandImpl::ProcessInternalCommand(long (*)(wchar_t const *,wchar_t const *),wchar_t const *,wchar_t const *)
0x180008788  mov     ebx, eax
0x18000878a  mov     r9d, eax; int
0x18000878d  mov     r8, [rdi+20h]; wchar_t *
0x180008791  mov     rdx, [rdi+18h]; wchar_t *
0x180008795  lea     rcx, [rsp+1E0h+var_180]; this
0x18000879a  call    ?Stop@RunCmd@Telemetry4UpdateCli@@QEAAXPEB_W0J@Z; Telemetry4UpdateCli::RunCmd::Stop(wchar_t const *,wchar_t const *,long)
0x18000879f  nop
0x1800087a0  lea     rcx, [rsp+1E0h+var_180]; this
0x1800087a5  call    ??1RunCmd@Telemetry4UpdateCli@@QEAA@XZ; Telemetry4UpdateCli::RunCmd::~RunCmd(void)
0x1800087aa  mov     eax, ebx
0x1800087ac  jmp     short loc_18000881B
0x1800087ae  lea     rdx, aHelp; "help"
0x1800087b5  mov     rcx, r14; wchar_t *
0x1800087b8  call    ?ShowHelp@CommandImpl@@CAJPEB_W0@Z; CommandImpl::ShowHelp(wchar_t const *,wchar_t const *)
0x1800087bd  mov     edi, eax
0x1800087bf  test    esi, esi
0x1800087c1  jns     short loc_180008819
0x1800087c3  mov     edx, 7D3h
0x1800087c8  lea     rcx, [rsp+1E0h+var_1A8]
0x1800087cd  call    ?LoadResourceString@CliUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; CliUtils::LoadResourceString(uint)
0x1800087d2  nop
0x1800087d3  mov     r8, [rax+10h]
0x1800087d7  cmp     qword ptr [rax+18h], 7
0x1800087dc  jbe     short loc_1800087E1
0x1800087de  mov     rax, [rax]
0x1800087e1  mov     rdx, rax
0x1800087e4  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x1800087eb  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1800087f0  lea     rdx, byte_180018020
0x1800087f7  test    r15, r15
0x1800087fa  cmovnz  rdx, r15
0x1800087fe  mov     rcx, rax
0x180008801  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180008806  mov     rcx, rax
0x180008809  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x18000880e  nop
0x18000880f  lea     rcx, [rsp+1E0h+var_1A8]
0x180008814  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008819  mov     eax, edi
0x18000881b  mov     rcx, [rbp+0E0h+var_30]
0x180008822  xor     rcx, rsp; StackCookie
0x180008825  call    __security_check_cookie
0x18000882a  lea     r11, [rsp+1E0h+var_20]
0x180008832  mov     rbx, [r11+40h]
0x180008836  mov     rsi, [r11+48h]
0x18000883a  mov     rsp, r11
0x18000883d  pop     r15
0x18000883f  pop     r14
0x180008841  pop     r12
0x180008843  pop     rdi
0x180008844  pop     rbp
0x180008845  retn
```
