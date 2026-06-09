# EventXmlDump::DumpHeader(_iobuf *,EventDumpWorkspace *)

- ea: `0x140010594`
- end: `0x140010a80`
- name: `?DumpHeader@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z`
- size: `1260`
- prototype: `unsigned int(EventXmlDump *__hidden this, struct _iobuf *, struct EventDumpWorkspace *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000faa4`

## callees

- `0x140010594`
- `0x140013a04`
- `0x14001601c`
- `0x1400161b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400108bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400108bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001089e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001089e`

## string_xrefs

- `0x140010682`: `		<Task>%u</Task>\n`
- `0x1400106cf`: `		<TimeCreated RawTime="%I64u" />\n`
- `0x1400106ec`: `		<TimeCreated SystemTime="`
- `0x14001076e`: `		<Execution ProcessID="%u" ThreadID="%u" ProcessorID="%u" `
- `0x140010835`: `		<Computer>`
- `0x140010858`: `</Computer>\n`
- `0x140010866`: `		<Computer />\n`
- `0x140010881`: `		<Security UserID="`

## pseudocode

```c
__int64 __fastcall EventXmlDump::DumpHeader(EventXmlDump *this, struct _iobuf *a2, struct EventDumpWorkspace *a3)
{
  __int64 v3; // rsi
  int v6; // ebp
  _DWORD *v7; // r8
  const char *v8; // rcx
  void *v9; // rcx
  unsigned int i; // esi
  __int64 v11; // r8
  _QWORD *v12; // r8
  unsigned int j; // esi
  LPWSTR StringSid; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a3;
  if ( (*(_WORD *)(*(_QWORD *)a3 + 4LL) & 0x200) != 0 )
    v6 = *(unsigned __int16 *)(v3 + 80);
  else
    v6 = *(unsigned __int8 *)(v3 + 80);
  TracerptFPuts("\t<System>\r\n", a2);
  TracerptFPuts("\t\t<Provider", a2);
  if ( *((_QWORD *)this + 2) )
  {
    TracerptFPuts(" Name=\"", a2);
    PrintWString(a2, 1u, 0, *((unsigned __int16 **)this + 2));
    TracerptFPuts("\"", a2);
  }
  if ( *((_QWORD *)this + 35) )
    TracerptFPrintf(a2, " Guid=\"%ws\"");
  TracerptFPuts(" />\r\n", a2);
  TracerptFPrintf(a2, "\t\t<EventID>%u</EventID>\r\n", *(unsigned __int16 *)(v3 + 40));
  TracerptFPrintf(a2, "\t\t<Version>%u</Version>\r\n", *(unsigned __int8 *)(v3 + 42));
  TracerptFPrintf(a2, "\t\t<Level>%u</Level>\r\n", *(unsigned __int8 *)(v3 + 44));
  TracerptFPrintf(a2, "\t\t<Task>%u</Task>\r\n", *(unsigned __int16 *)(v3 + 46));
  TracerptFPrintf(a2, "\t\t<Opcode>%u</Opcode>\r\n", *(unsigned __int8 *)(v3 + 45));
  TracerptFPrintf(a2, "\t\t<Keywords>0x%I64X</Keywords>\r\n", *(_QWORD *)(v3 + 48));
  if ( (*((_DWORD *)g_TraceContext + 1604) & 0x1000) != 0 )
  {
    TracerptFPrintf(a2, "\t\t<TimeCreated RawTime=\"%I64u\" />\r\n", *(_QWORD *)(v3 + 16));
  }
  else if ( *((_DWORD *)this + 104) )
  {
    TracerptFPuts("\t\t<TimeCreated SystemTime=\"", a2);
    PrintWString(a2, 1u, 0, (unsigned __int16 *)this + 144);
    TracerptFPuts("\" />\r\n", a2);
  }
  TracerptFPrintf(a2, "\t\t<Correlation");
  TracerptFPrintf(a2, " ActivityID=\"%ws\"", *((_QWORD *)this + 54));
  if ( *((_QWORD *)this + 88) )
    TracerptFPrintf(a2, " RelatedActivityID=\"%ws\"");
  TracerptFPuts(" />\r\n", a2);
  TracerptFPrintf(
    a2,
    "\t\t<Execution ProcessID=\"%u\" ThreadID=\"%u\" ProcessorID=\"%u\" ",
    *(_DWORD *)(v3 + 12),
    *(_DWORD *)(v3 + 8),
    v6);
  v7 = (_DWORD *)*((_QWORD *)this + 121);
  if ( v7 )
    TracerptFPrintf(a2, "SessionID=\"%lu\" ", *v7);
  if ( g_bUserMode )
    TracerptFPrintf(a2, "KernelTime=\"%I64u\" />\r\n", *(_QWORD *)(v3 + 56));
  else
    TracerptFPrintf(
      a2,
      "KernelTime=\"%lu\" UserTime=\"%lu\" />\r\n",
      dword_1400820F8 * *(_DWORD *)(v3 + 56),
      dword_1400820F8 * *(_DWORD *)(v3 + 60));
  if ( *((_QWORD *)this + 122) )
  {
    TracerptFPuts("\t\t<Channel>", a2);
    PrintWString(a2, 1u, 0, *((unsigned __int16 **)this + 122));
    v8 = "</Channel>\r\n";
  }
  else
  {
    v8 = "\t\t<Channel />\r\n";
  }
  TracerptFPuts(v8, a2);
  if ( lpMem )
  {
    TracerptFPuts("\t\t<Computer>", a2);
    PrintWString(a2, 1u, 0, lpMem);
    TracerptFPuts("</Computer>\r\n", a2);
  }
  else
  {
    TracerptFPrintf(a2, "\t\t<Computer />\r\n");
  }
  if ( *((_QWORD *)this + 124) )
  {
    TracerptFPuts("\t\t<Security UserID=\"", a2);
    v9 = (void *)*((_QWORD *)this + 124);
    StringSid = 0;
    if ( ConvertSidToStringSidW(v9, &StringSid) )
    {
      PrintWString(a2, 1u, 0, StringSid);
      LocalFree(StringSid);
    }
    TracerptFPuts("\" />\r\n", a2);
  }
  if ( *((_QWORD *)this + 125) )
  {
    TracerptFPuts("\t\t<PsmKey>", a2);
    PrintWString(a2, 1u, 0, *((unsigned __int16 **)this + 125));
    TracerptFPuts("</PsmKey>\r\n", a2);
  }
  if ( *((_QWORD *)this + 126) || *((_QWORD *)this + 127) )
  {
    TracerptFPuts("\t\t<Stack>\r\n", a2);
    TracerptFPrintf(a2, "\t\t\t<MatchId>0x%016I64X</MatchId>\r\n", *((_QWORD *)this + 129));
    for ( i = 0; i < *((_DWORD *)this + 256); ++i )
    {
      TracerptFPuts("\t\t\t<Address>", a2);
      v11 = *((_QWORD *)this + 126);
      if ( v11 )
        TracerptFPrintf(a2, "0x%08X", *(_DWORD *)(v11 + 4LL * i));
      else
        TracerptFPrintf(a2, "0x%016I64X", *(_QWORD *)(*((_QWORD *)this + 127) + 8LL * i));
      TracerptFPuts("</Address>\r\n", a2);
    }
    TracerptFPuts("\t\t</Stack>\r\n", a2);
  }
  v12 = (_QWORD *)*((_QWORD *)this + 130);
  if ( v12 )
    TracerptFPrintf(a2, "\t\t<PebsIndex>0x%016I64X</PebsIndex>\r\n", *v12);
  if ( *((_QWORD *)this + 131) )
  {
    TracerptFPuts("\t\t<PmcCounters>\r\n", a2);
    for ( j = 0; j < *((_DWORD *)this + 264); ++j )
    {
      TracerptFPuts("\t\t\t<PmcCounter>", a2);
      TracerptFPrintf(a2, "0x%016I64X", *(_QWORD *)(*((_QWORD *)this + 131) + 8LL * j));
      TracerptFPuts("</PmcCounter>\r\n", a2);
    }
    TracerptFPuts("\t\t</PmcCounters>\r\n", a2);
  }
  TracerptFPuts("\t</System>\r\n", a2);
  return 0;
}

```

## disassembly

```asm
0x140010594  mov     [rsp+arg_8], rbx
0x140010599  mov     [rsp+arg_10], rbp
0x14001059e  push    rsi
0x14001059f  push    rdi
0x1400105a0  push    r14
0x1400105a2  sub     rsp, 30h
0x1400105a6  mov     rsi, [r8]
0x1400105a9  mov     eax, 200h
0x1400105ae  mov     rbx, rdx
0x1400105b1  mov     rdi, rcx
0x1400105b4  test    [rsi+4], ax
0x1400105b8  jz      short loc_1400105C0
0x1400105ba  movzx   ebp, word ptr [rsi+50h]
0x1400105be  jmp     short loc_1400105C4
0x1400105c0  movzx   ebp, byte ptr [rsi+50h]
0x1400105c4  lea     rcx, aSystem_1; "\t<System>\r\n"
0x1400105cb  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400105d0  mov     rdx, rbx; struct _iobuf *
0x1400105d3  lea     rcx, aProvider_2; "\t\t<Provider"
0x1400105da  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400105df  xor     r14d, r14d
0x1400105e2  cmp     [rdi+10h], r14
0x1400105e6  jz      short loc_140010617
0x1400105e8  mov     rdx, rbx; struct _iobuf *
0x1400105eb  lea     rcx, aName; " Name=\""
0x1400105f2  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400105f7  mov     r9, [rdi+10h]; unsigned __int16 *
0x1400105fb  xor     r8d, r8d; unsigned __int8
0x1400105fe  mov     dl, 1; unsigned __int8
0x140010600  mov     rcx, rbx; struct _iobuf *
0x140010603  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010608  mov     rdx, rbx; struct _iobuf *
0x14001060b  lea     rcx, asc_140045268; "\""
0x140010612  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010617  mov     r8, [rdi+118h]
0x14001061e  test    r8, r8
0x140010621  jz      short loc_140010632
0x140010623  lea     rdx, aGuidWs; " Guid=\"%ws\""
0x14001062a  mov     rcx, rbx; struct _iobuf *
0x14001062d  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010632  mov     rdx, rbx; struct _iobuf *
0x140010635  lea     rcx, asc_14004527C; " />\r\n"
0x14001063c  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010641  movzx   r8d, word ptr [rsi+28h]
0x140010646  lea     rdx, aEventidUEventi; "\t\t<EventID>%u</EventID>\r\n"
0x14001064d  mov     rcx, rbx; struct _iobuf *
0x140010650  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010655  movzx   r8d, byte ptr [rsi+2Ah]
0x14001065a  lea     rdx, aVersionUVersio; "\t\t<Version>%u</Version>\r\n"
0x140010661  mov     rcx, rbx; struct _iobuf *
0x140010664  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010669  movzx   r8d, byte ptr [rsi+2Ch]
0x14001066e  lea     rdx, aLevelULevel; "\t\t<Level>%u</Level>\r\n"
0x140010675  mov     rcx, rbx; struct _iobuf *
0x140010678  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14001067d  movzx   r8d, word ptr [rsi+2Eh]
0x140010682  lea     rdx, aTaskUTask; "\t\t<Task>%u</Task>\r\n"
0x140010689  mov     rcx, rbx; struct _iobuf *
0x14001068c  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010691  movzx   r8d, byte ptr [rsi+2Dh]
0x140010696  lea     rdx, aOpcodeUOpcode; "\t\t<Opcode>%u</Opcode>\r\n"
0x14001069d  mov     rcx, rbx; struct _iobuf *
0x1400106a0  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400106a5  mov     r8, [rsi+30h]
0x1400106a9  lea     rdx, aKeywords0xI64x; "\t\t<Keywords>0x%I64X</Keywords>\r\n"
0x1400106b0  mov     rcx, rbx; struct _iobuf *
0x1400106b3  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400106b8  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x1400106bf  test    dword ptr [rax+1910h], 1000h
0x1400106c9  jz      short loc_1400106E0
0x1400106cb  mov     r8, [rsi+10h]
0x1400106cf  lea     rdx, aTimecreatedRaw; "\t\t<TimeCreated RawTime=\"%I64u\" />\r"...
0x1400106d6  mov     rcx, rbx; struct _iobuf *
0x1400106d9  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400106de  jmp     short loc_14001071B
0x1400106e0  cmp     [rdi+1A0h], r14d
0x1400106e7  jz      short loc_14001071B
0x1400106e9  mov     rdx, rbx; struct _iobuf *
0x1400106ec  lea     rcx, aTimecreatedSys; "\t\t<TimeCreated SystemTime=\""
0x1400106f3  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400106f8  lea     r9, [rdi+120h]; unsigned __int16 *
0x1400106ff  xor     r8d, r8d; unsigned __int8
0x140010702  mov     dl, 1; unsigned __int8
0x140010704  mov     rcx, rbx; struct _iobuf *
0x140010707  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001070c  mov     rdx, rbx; struct _iobuf *
0x14001070f  lea     rcx, asc_14004537C; "\" />\r\n"
0x140010716  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001071b  lea     rdx, aCorrelation; "\t\t<Correlation"
0x140010722  mov     rcx, rbx; struct _iobuf *
0x140010725  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14001072a  mov     r8, [rdi+1B0h]
0x140010731  lea     rdx, aActivityidWs; " ActivityID=\"%ws\""
0x140010738  mov     rcx, rbx; struct _iobuf *
0x14001073b  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010740  mov     r8, [rdi+2C0h]
0x140010747  test    r8, r8
0x14001074a  jz      short loc_14001075B
0x14001074c  lea     rdx, aRelatedactivit; " RelatedActivityID=\"%ws\""
0x140010753  mov     rcx, rbx; struct _iobuf *
0x140010756  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14001075b  mov     rdx, rbx; struct _iobuf *
0x14001075e  lea     rcx, asc_14004527C; " />\r\n"
0x140010765  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001076a  mov     r9d, [rsi+8]
0x14001076e  lea     rdx, aExecutionProce; "\t\t<Execution ProcessID=\"%u\" ThreadI"...
0x140010775  mov     r8d, [rsi+0Ch]
0x140010779  mov     rcx, rbx; struct _iobuf *
0x14001077c  mov     [rsp+48h+var_28], ebp
0x140010780  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010785  mov     r8, [rdi+3C8h]
0x14001078c  test    r8, r8
0x14001078f  jz      short loc_1400107A3
0x140010791  mov     r8d, [r8]
0x140010794  lea     rdx, aSessionidLu; "SessionID=\"%lu\" "
0x14001079b  mov     rcx, rbx; struct _iobuf *
0x14001079e  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400107a3  cmp     cs:?g_bUserMode@@3HA, r14d; int g_bUserMode
0x1400107aa  mov     rcx, rbx; struct _iobuf *
0x1400107ad  jnz     short loc_1400107D5
0x1400107af  mov     r9d, [rsi+3Ch]
0x1400107b3  lea     rdx, aKerneltimeLuUs; "KernelTime=\"%lu\" UserTime=\"%lu\" />"...
0x1400107ba  mov     r8d, [rsi+38h]
0x1400107be  imul    r9d, cs:dword_1400820F8
0x1400107c6  imul    r8d, cs:dword_1400820F8
0x1400107ce  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400107d3  jmp     short loc_1400107E5
0x1400107d5  mov     r8, [rsi+38h]
0x1400107d9  lea     rdx, aKerneltimeI64u; "KernelTime=\"%I64u\" />\r\n"
0x1400107e0  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400107e5  cmp     [rdi+3D0h], r14
0x1400107ec  jz      short loc_14001081A
0x1400107ee  mov     rdx, rbx; struct _iobuf *
0x1400107f1  lea     rcx, aChannel; "\t\t<Channel>"
0x1400107f8  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400107fd  mov     r9, [rdi+3D0h]; unsigned __int16 *
0x140010804  xor     r8d, r8d; unsigned __int8
0x140010807  mov     dl, 1; unsigned __int8
0x140010809  mov     rcx, rbx; struct _iobuf *
0x14001080c  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010811  lea     rcx, aChannel_0; "</Channel>\r\n"
0x140010818  jmp     short loc_140010821
0x14001081a  lea     rcx, aChannel_2; "\t\t<Channel />\r\n"
0x140010821  mov     rdx, rbx; struct _iobuf *
0x140010824  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010829  cmp     cs:lpMem, r14
0x140010830  jz      short loc_140010866
0x140010832  mov     rdx, rbx; struct _iobuf *
0x140010835  lea     rcx, aComputer; "\t\t<Computer>"
0x14001083c  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010841  mov     r9, cs:lpMem; unsigned __int16 *
0x140010848  xor     r8d, r8d; unsigned __int8
0x14001084b  mov     dl, 1; unsigned __int8
0x14001084d  mov     rcx, rbx; struct _iobuf *
0x140010850  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010855  mov     rdx, rbx; struct _iobuf *
0x140010858  lea     rcx, aComputer_0; "</Computer>\r\n"
0x14001085f  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010864  jmp     short loc_140010875
0x140010866  lea     rdx, aComputer_1; "\t\t<Computer />\r\n"
0x14001086d  mov     rcx, rbx; struct _iobuf *
0x140010870  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010875  cmp     [rdi+3E0h], r14
0x14001087c  jz      short loc_1400108D4
0x14001087e  mov     rdx, rbx; struct _iobuf *
0x140010881  lea     rcx, aSecurityUserid; "\t\t<Security UserID=\""
0x140010888  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001088d  mov     rcx, [rdi+3E0h]; Sid
0x140010894  lea     rdx, [rsp+48h+StringSid]; StringSid
0x140010899  mov     [rsp+48h+StringSid], r14
0x14001089e  call    cs:__imp_ConvertSidToStringSidW
0x1400108a4  test    eax, eax
0x1400108a6  jz      short loc_1400108C5
0x1400108a8  mov     r9, [rsp+48h+StringSid]; unsigned __int16 *
0x1400108ad  xor     r8d, r8d; unsigned __int8
0x1400108b0  mov     dl, 1; unsigned __int8
0x1400108b2  mov     rcx, rbx; struct _iobuf *
0x1400108b5  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400108ba  mov     rcx, [rsp+48h+StringSid]; hMem
0x1400108bf  call    cs:__imp_LocalFree
0x1400108c5  mov     rdx, rbx; struct _iobuf *
0x1400108c8  lea     rcx, asc_14004537C; "\" />\r\n"
0x1400108cf  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400108d4  cmp     [rdi+3E8h], r14
0x1400108db  jz      short loc_14001090F
0x1400108dd  mov     rdx, rbx; struct _iobuf *
0x1400108e0  lea     rcx, aPsmkey; "\t\t<PsmKey>"
0x1400108e7  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400108ec  mov     r9, [rdi+3E8h]; unsigned __int16 *
0x1400108f3  xor     r8d, r8d; unsigned __int8
0x1400108f6  mov     dl, 1; unsigned __int8
0x1400108f8  mov     rcx, rbx; struct _iobuf *
0x1400108fb  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010900  mov     rdx, rbx; struct _iobuf *
0x140010903  lea     rcx, aPsmkey_0; "</PsmKey>\r\n"
0x14001090a  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001090f  cmp     [rdi+3F0h], r14
0x140010916  jnz     short loc_140010925
0x140010918  cmp     [rdi+3F8h], r14
0x14001091f  jz      loc_1400109C7
0x140010925  mov     rdx, rbx; struct _iobuf *
0x140010928  lea     rcx, aStack_0; "\t\t<Stack>\r\n"
0x14001092f  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010934  mov     r8, [rdi+408h]
0x14001093b  lea     rdx, aMatchid0x016i6; "\t\t\t<MatchId>0x%016I64X</MatchId>\r\n"
0x140010942  mov     rcx, rbx; struct _iobuf *
0x140010945  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14001094a  mov     esi, r14d
0x14001094d  cmp     [rdi+400h], r14d
0x140010954  jbe     short loc_1400109B8
0x140010956  mov     rdx, rbx; struct _iobuf *
0x140010959  lea     rcx, aAddress; "\t\t\t<Address>"
0x140010960  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010965  mov     r8, [rdi+3F0h]
0x14001096c  mov     rcx, rbx; struct _iobuf *
0x14001096f  mov     eax, esi
0x140010971  test    r8, r8
0x140010974  jz      short loc_140010988
0x140010976  mov     r8d, [r8+rax*4]
0x14001097a  lea     rdx, a0x08x; "0x%08X"
0x140010981  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010986  jmp     short loc_14001099F
0x140010988  mov     r8, [rdi+3F8h]
0x14001098f  lea     rdx, a0x016i64x; "0x%016I64X"
0x140010996  mov     r8, [r8+rax*8]
0x14001099a  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14001099f  mov     rdx, rbx; struct _iobuf *
0x1400109a2  lea     rcx, aAddress_0; "</Address>\r\n"
0x1400109a9  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400109ae  inc     esi
0x1400109b0  cmp     esi, [rdi+400h]
0x1400109b6  jb      short loc_140010956
0x1400109b8  mov     rdx, rbx; struct _iobuf *
0x1400109bb  lea     rcx, aStack; "\t\t</Stack>\r\n"
0x1400109c2  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400109c7  mov     r8, [rdi+410h]
0x1400109ce  test    r8, r8
0x1400109d1  jz      short loc_1400109E5
0x1400109d3  mov     r8, [r8]
0x1400109d6  lea     rdx, aPebsindex0x016; "\t\t<PebsIndex>0x%016I64X</PebsIndex>\r"...
0x1400109dd  mov     rcx, rbx; struct _iobuf *
0x1400109e0  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400109e5  cmp     [rdi+418h], r14
0x1400109ec  jz      short loc_140010A5C
0x1400109ee  mov     rdx, rbx; struct _iobuf *
0x1400109f1  lea     rcx, aPmccounters_0; "\t\t<PmcCounters>\r\n"
0x1400109f8  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400109fd  mov     esi, r14d
0x140010a00  cmp     [rdi+420h], r14d
0x140010a07  jbe     short loc_140010A4D
0x140010a09  mov     rdx, rbx; struct _iobuf *
0x140010a0c  lea     rcx, aPmccounter_0; "\t\t\t<PmcCounter>"
0x140010a13  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010a18  mov     r8, [rdi+418h]
0x140010a1f  lea     rdx, a0x016i64x; "0x%016I64X"
0x140010a26  mov     eax, esi
0x140010a28  mov     rcx, rbx; struct _iobuf *
0x140010a2b  mov     r8, [r8+rax*8]
0x140010a2f  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010a34  mov     rdx, rbx; struct _iobuf *
0x140010a37  lea     rcx, aPmccounter; "</PmcCounter>\r\n"
0x140010a3e  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010a43  inc     esi
0x140010a45  cmp     esi, [rdi+420h]
0x140010a4b  jb      short loc_140010A09
0x140010a4d  mov     rdx, rbx; struct _iobuf *
0x140010a50  lea     rcx, aPmccounters; "\t\t</PmcCounters>\r\n"
0x140010a57  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010a5c  mov     rdx, rbx; struct _iobuf *
0x140010a5f  lea     rcx, aSystem_2; "\t</System>\r\n"
0x140010a66  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010a6b  mov     rbx, [rsp+48h+arg_8]
0x140010a70  xor     eax, eax
0x140010a72  mov     rbp, [rsp+48h+arg_10]
0x140010a77  add     rsp, 30h
0x140010a7b  pop     r14
0x140010a7d  pop     rdi
0x140010a7e  pop     rsi
0x140010a7f  retn
```
