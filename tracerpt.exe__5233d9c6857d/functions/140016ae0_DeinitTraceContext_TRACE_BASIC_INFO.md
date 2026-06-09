# DeinitTraceContext(_TRACE_BASIC_INFO *)

- ea: `0x140016ae0`
- end: `0x140017176`
- name: `?DeinitTraceContext@@YAKPEAU_TRACE_BASIC_INFO@@@Z`
- size: `1686`
- prototype: `unsigned int __fastcall(struct _TRACE_BASIC_INFO *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14002ec00`

## callees

- `0x1400020e4`
- `0x1400020f0`
- `0x14000abf4`
- `0x14000bc10`
- `0x140015fa0`
- `0x14001601c`
- `0x1400162b4`
- `0x140016360`
- `0x1400164c4`
- `0x140016754`
- `0x140016920`
- `0x140016998`
- `0x140016ae0`
- `0x1400172f4`
- `0x14001a214`
- `0x14001db34`
- `0x14001e96c`
- `0x14001f330`
- `0x14001f8d8`
- `0x14001fa40`
- `0x14001fd7c`
- `0x140020310`
- `0x140020748`
- `0x1400208e4`
- `0x140021184`
- `0x140021ff4`
- `0x140022480`
- `0x140026d88`
- `0x1400277c8`
- `0x140027de4`
- `0x14002b818`
- `0x14002d560`
- `0x14002fba4`
- `0x14003012c`
- `0x140040130`
- `0x140041010`

## import_xrefs

- `msvcrt!fclose` at `0x140016faf`
- `msvcrt!fclose` at `0x140016fdc`
- `msvcrt!fclose` at `0x140016faf`
- `msvcrt!fclose` at `0x140016fdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016f96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400170d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016f96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400170d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016f88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400170c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016f88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400170c6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001709c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001709c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhUnloadManifest` at `0x140016b76`
- `api-ms-win-eventing-tdh-l1-1-0!TdhUnloadManifest` at `0x140016b76`
- `ntdll!RtlDeleteCriticalSection` at `0x140017064`
- `ntdll!RtlDeleteCriticalSection` at `0x140017064`
- `WS2_32!__imp_WSACleanup` at `0x140017057`
- `WS2_32!__imp_WSACleanup` at `0x140017057`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016f48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016fc3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016ff0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016f48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016fc3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016ff0`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140016b44`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140016b44`
- `wevtapi!EvtClose` at `0x14001704c`
- `wevtapi!EvtClose` at `0x14001704c`

## string_xrefs

- `0x140016c8f`: `<?xml version="1.0" encoding="UTF-16"?>\n`
- `0x140016cb7`: `<?xml-stylesheet type="text/xsl" href="%s"?>\n`

## pseudocode

```c
__int64 __fastcall DeinitTraceContext(struct _TRACE_BASIC_INFO *a1)
{
  LPVOID v1; // rdx
  unsigned int v4; // ebp
  unsigned int v5; // ebx
  unsigned int v6; // edi
  TRACEHANDLE v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rbx
  int v10; // r8d
  WCHAR *v11; // rax
  __int64 v12; // rcx
  unsigned int TempName; // eax
  __int64 v14; // r8
  WCHAR *v15; // rcx
  unsigned __int16 v16; // r10
  struct _iobuf *v17; // rax
  struct _iobuf *v18; // rbx
  unsigned int *v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // r11
  DpcIsrData *v23; // rcx
  struct _TRACERPT_REPORT *v24; // rdi
  struct _TRACERPT_REPORT *v25; // rsi
  struct _TRACERPT_SECTION *v26; // rdx
  __int64 v27; // rcx
  void *v28; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v30; // rbx
  HANDLE v31; // rax
  int v32; // eax
  struct _iobuf *v33; // rcx
  void *v34; // rcx
  _QWORD *v35; // rbx
  _BYTE *v36; // rdi
  __int64 v37; // rcx
  struct _PDH_CONTEXT_BLOCK *v38; // rcx
  HANDLE v39; // rax
  void *v40; // rbx
  _QWORD **v41; // rbx
  _QWORD *v42; // rdi
  __int64 v43; // [rsp+28h] [rbp-840h]
  WCHAR FileName[1024]; // [rsp+30h] [rbp-838h] BYREF

  v1 = g_TraceContext;
  if ( !g_TraceContext )
    return 6;
  v4 = 0;
  v5 = 0;
  v6 = *((_DWORD *)g_TraceContext + 2) + *((_DWORD *)g_TraceContext + 3);
  if ( v6 )
  {
    do
    {
      v7 = *((_QWORD *)v1 + v5 + 805);
      if ( v7 != -1 )
      {
        CloseTrace(v7);
        v1 = g_TraceContext;
        *((_QWORD *)g_TraceContext + v5 + 805) = -1;
      }
      ++v5;
    }
    while ( v5 < v6 );
  }
  v8 = 0;
  if ( *((_DWORD *)a1 + 6) )
  {
    do
      TdhUnloadManifest(*(PWSTR *)(*((_QWORD *)a1 + 6) + 8LL * v8++));
    while ( v8 < *((_DWORD *)a1 + 6) );
    v1 = g_TraceContext;
  }
  v9 = 1024;
  if ( (*((_DWORD *)v1 + 1604) & 0x400) != 0 )
  {
    WriteSummary();
    v1 = g_TraceContext;
  }
  v10 = *((_DWORD *)v1 + 1604);
  if ( (v10 & 8) != 0 )
  {
    v11 = (WCHAR *)*((_QWORD *)v1 + 772);
    if ( v11 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      if ( v12 )
      {
        if ( (v10 & 0x40000) != 0 && *((_QWORD *)v1 + 775) )
        {
          TempName = GetTempName(FileName, 0x400u);
          v1 = g_TraceContext;
          v4 = TempName;
        }
        else
        {
          v14 = 2147483646;
          v15 = FileName;
          v16 = 0;
          while ( v14 )
          {
            if ( *v11 )
            {
              *v15++ = *v11++;
              --v14;
              if ( --v9 )
                continue;
            }
            if ( !v9 )
            {
              --v15;
              v16 = 122;
            }
            break;
          }
          *v15 = 0;
          v4 = v16;
        }
        if ( !v4 )
        {
          dword_1400846E8 = *((_DWORD *)v1 + 1604);
          v17 = TracerptWFopen(FileName, 1u, 0);
          v18 = v17;
          if ( v17 )
          {
            TracerptFPutwc(0xFEFFu, v17);
            TracerptFPutws(L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n", v18);
            v19 = (unsigned int *)g_TraceContext;
            if ( (*((_DWORD *)g_TraceContext + 1604) & 0x40000) == 0 && *((_QWORD *)g_TraceContext + 775) )
            {
              TracerptFWPrintf(v18, L"<?xml-stylesheet type=\"text/xsl\" href=\"%s\"?>\r\n");
              v19 = (unsigned int *)g_TraceContext;
            }
            if ( qword_140082288 && (v20 = *((_QWORD *)qword_140082288 + 8)) != 0 )
            {
              LODWORD(v43) = *(_DWORD *)(v20 + 160);
              TracerptFWPrintf(
                v18,
                L"<Report name='%wZ' level='%d' top='%d' version='%d'>\r\n",
                v20 + 176,
                v19[2174],
                *(_DWORD *)(v20 + 164),
                v43);
            }
            else
            {
              TracerptFWPrintf(
                v18,
                L"<Report name='tracerpt' level='%d' top='25' version='%d.%d'>\r\n",
                v19[2174],
                10,
                0);
            }
            PrintReportHeader(v18);
            v21 = g_TraceContext;
            if ( !g_TraceContext )
              goto LABEL_51;
            ReportPrintJobInfo(v18);
            v21 = g_TraceContext;
            if ( !g_TraceContext )
              goto LABEL_51;
            ReportIisEvents(v18);
            v21 = g_TraceContext;
            if ( !g_TraceContext )
              goto LABEL_51;
            if ( *((_BYTE *)g_TraceContext + 8504) )
            {
              TracerptFWPrintf(v18, L"<Section name='%s' key='%d'%s", L"tracerptCpusection", 6000, L">\r\n");
              WriteTransactionStatistics(v18);
              CalculateServiceUsage();
              PrintProcessData(v18);
              PrintServiceUsageTable(v18);
              PrintProcessSubDataExclusive(v18);
              PrintProcessSubDataInclusive(v18);
              TracerptFPutws(L"</Section>\r\n", v18);
              TracerptFWPrintf(v18, L"<Section name='%s' key='%d'%s", L"tracerptDisk", 8000, L">\r\n");
              ReportHotFileInfo(v18);
              PrintDiskTotals(v18);
              TracerptFPutws(L"</Section>\r\n", v18);
              if ( dword_140083648 != 1 && qword_140083640 )
              {
                SortTimeStamps_DpcIsrData::EVENT_INSTANCE_DATA_DpcIsrData::ExitTimeExtractor_(
                  *((_QWORD *)qword_140083640 + 1),
                  *(unsigned int *)qword_140083640);
                SortTimeStamps_DpcIsrData::EVENT_INSTANCE_DATA_DpcIsrData::ExitTimeExtractor_(
                  *(_QWORD *)(v22 + 24),
                  *(unsigned int *)(v22 + 16));
                TracerptFWPrintf(v18, L"<Section name='%s' key='%d'%s", L"tracerptDpcisr", 10000, L">\r\n");
                DpcIsrData::Report(v23, v18);
                TracerptFPutws(L"</Section>\r\n", v18);
              }
              v21 = g_TraceContext;
            }
            if ( v21 && qword_140082288 )
            {
              v24 = (struct _TRACERPT_REPORT *)*((_QWORD *)qword_140082288 + 8);
              if ( v24 )
              {
                v25 = *(struct _TRACERPT_REPORT **)v24;
                while ( v24 != v25 )
                {
                  v26 = v25;
                  v25 = *(struct _TRACERPT_REPORT **)v25;
                  GenerateSection(v18, v26);
                }
                PrintPdhTitles(v18);
                PrintSchemaTitles(v18, v24);
              }
            }
            else
            {
LABEL_51:
              v27 = v21[1086];
              if ( v27 && !*(_DWORD *)(v27 + 28) )
                PrintPdhCountersOutput(v18);
            }
            TracerptFPutws(L"</Report>\r\n", v18);
            TracerptFClose(v18);
            TracerptMergeSections(FileName);
          }
          v1 = g_TraceContext;
          if ( (*((_DWORD *)g_TraceContext + 1604) & 0x40000) != 0 && *((_QWORD *)g_TraceContext + 775) )
          {
            v4 = TransformXML(FileName, *((OLECHAR **)g_TraceContext + 775), *((LPCWSTR *)g_TraceContext + 772));
            DeleteFileW(FileName);
            v1 = g_TraceContext;
          }
        }
      }
    }
  }
  v28 = (void *)*((_QWORD *)v1 + 785);
  if ( v28 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v28);
    v1 = g_TraceContext;
  }
  v30 = lpMem;
  if ( lpMem )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v30);
    v1 = g_TraceContext;
  }
  if ( Stream )
  {
    fclose(Stream);
    Stream = 0;
    DeleteFileW(TempPrintFile);
    v1 = g_TraceContext;
  }
  if ( qword_1400820E8 )
  {
    fclose(qword_1400820E8);
    qword_1400820E8 = 0;
    DeleteFileW(TempIisFile);
    v1 = g_TraceContext;
  }
  v32 = *((_DWORD *)v1 + 1604);
  if ( (v32 & 0x80u) != 0 )
  {
    v33 = (struct _iobuf *)*((_QWORD *)v1 + 799);
    if ( v33 )
    {
      if ( (v32 & 0x9000000) != 0 )
      {
        TracerptFPrintf(v33, "</Events>\r\n");
        v1 = g_TraceContext;
      }
      TracerptFClose(*((struct _iobuf **)v1 + 799));
      v1 = g_TraceContext;
    }
    v34 = (void *)*((_QWORD *)v1 + 1088);
    if ( v34 )
      EvtClose(v34);
  }
  ProcessCleanup();
  WSACleanup();
  RtlDeleteCriticalSection(&TLCritSect);
  v35 = g_TraceContext;
  v36 = g_TraceContext;
  v37 = *((_QWORD *)g_TraceContext + 1089);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v35 = g_TraceContext;
  }
  if ( v36[8720] )
  {
    CoUninitialize();
    v35 = g_TraceContext;
  }
  v38 = (struct _PDH_CONTEXT_BLOCK *)v35[1086];
  if ( v38 )
  {
    CleanupPdhContextBlock(v38);
    v35 = g_TraceContext;
  }
  if ( v35 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v35);
  }
  v40 = Block;
  g_TraceContext = 0;
  if ( Block )
  {
    utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,FileRecord>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,FileRecord>>,0>::~_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,FileRecord>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,FileRecord>>,0>(Block);
    operator delete(v40);
  }
  v41 = (_QWORD **)qword_140082158;
  Block = 0;
  if ( qword_140082158 )
  {
    while ( 1 )
    {
      v42 = *v41;
      if ( *v41 == (_QWORD *)-1LL )
        break;
      *v41 = (_QWORD *)*v42;
      FileRecord::~FileRecord((FileRecord *)(v42 + 1));
      operator delete(v42, (const struct std::nothrow_t *)&std::nothrow);
    }
    operator delete(v41);
  }
  qword_140082158 = 0;
  return v4;
}

```

## disassembly

```asm
0x140016ae0  mov     [rsp+arg_8], rbx
0x140016ae5  mov     [rsp+arg_10], rbp
0x140016aea  push    rsi
0x140016aeb  push    rdi
0x140016aec  push    r13
0x140016aee  push    r14
0x140016af0  push    r15
0x140016af2  sub     rsp, 840h
0x140016af9  mov     rax, cs:__security_cookie
0x140016b00  xor     rax, rsp
0x140016b03  mov     [rsp+868h+var_38], rax
0x140016b0b  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016b12  xor     r15d, r15d
0x140016b15  mov     rsi, rcx
0x140016b18  test    rdx, rdx
0x140016b1b  jnz     short loc_140016B25
0x140016b1d  lea     eax, [rdx+6]
0x140016b20  jmp     loc_14001714A
0x140016b25  mov     edi, [rdx+0Ch]
0x140016b28  mov     ebp, r15d
0x140016b2b  mov     ebx, r15d
0x140016b2e  add     edi, [rdx+8]
0x140016b31  jz      short loc_140016B63
0x140016b33  mov     r14d, ebx
0x140016b36  mov     rcx, [rdx+r14*8+1928h]; TraceHandle
0x140016b3e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140016b42  jz      short loc_140016B5D
0x140016b44  call    cs:__imp_CloseTrace
0x140016b4a  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016b51  mov     qword ptr [rdx+r14*8+1928h], 0FFFFFFFFFFFFFFFFh
0x140016b5d  inc     ebx
0x140016b5f  cmp     ebx, edi
0x140016b61  jb      short loc_140016B33
0x140016b63  mov     ebx, r15d
0x140016b66  cmp     [rsi+18h], r15d
0x140016b6a  jbe     short loc_140016B8A
0x140016b6c  mov     rcx, [rsi+30h]
0x140016b70  mov     eax, ebx
0x140016b72  mov     rcx, [rcx+rax*8]; Manifest
0x140016b76  call    cs:__imp_TdhUnloadManifest
0x140016b7c  inc     ebx
0x140016b7e  cmp     ebx, [rsi+18h]
0x140016b81  jb      short loc_140016B6C
0x140016b83  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016b8a  mov     ebx, 400h
0x140016b8f  test    [rdx+1910h], ebx
0x140016b95  jz      short loc_140016BA3
0x140016b97  call    ?WriteSummary@@YAXXZ; WriteSummary(void)
0x140016b9c  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016ba3  mov     r8d, [rdx+1910h]
0x140016baa  test    r8b, 8
0x140016bae  jz      loc_140016F55
0x140016bb4  mov     rax, [rdx+1820h]
0x140016bbb  test    rax, rax
0x140016bbe  jz      loc_140016F55
0x140016bc4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140016bc8  inc     rcx
0x140016bcb  cmp     [rax+rcx*2], r15w
0x140016bd0  jnz     short loc_140016BC8
0x140016bd2  test    rcx, rcx
0x140016bd5  jz      loc_140016F55
0x140016bdb  mov     r14d, 40000h
0x140016be1  test    r14d, r8d
0x140016be4  jz      short loc_140016C07
0x140016be6  cmp     [rdx+1838h], r15
0x140016bed  jz      short loc_140016C07
0x140016bef  mov     rdx, rbx; unsigned __int64
0x140016bf2  lea     rcx, [rsp+868h+FileName]; unsigned __int16 *
0x140016bf7  call    ?GetTempName@@YAKPEAG_K@Z; GetTempName(ushort *,unsigned __int64)
0x140016bfc  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016c03  mov     ebp, eax
0x140016c05  jmp     short loc_140016C50
0x140016c07  mov     r8d, 7FFFFFFEh
0x140016c0d  lea     rcx, [rsp+868h+FileName]
0x140016c12  mov     r10d, r15d
0x140016c15  test    r8, r8
0x140016c18  jz      short loc_140016C48
0x140016c1a  movzx   r9d, word ptr [rax]
0x140016c1e  test    r9w, r9w
0x140016c22  jz      short loc_140016C39
0x140016c24  mov     [rcx], r9w
0x140016c28  add     rax, 2
0x140016c2c  add     rcx, 2
0x140016c30  dec     r8
0x140016c33  sub     rbx, 1
0x140016c37  jnz     short loc_140016C15
0x140016c39  test    rbx, rbx
0x140016c3c  jnz     short loc_140016C48
0x140016c3e  sub     rcx, 2
0x140016c42  mov     r10d, 8007007Ah
0x140016c48  mov     [rcx], r15w
0x140016c4c  movzx   ebp, r10w
0x140016c50  test    ebp, ebp
0x140016c52  jnz     loc_140016F55
0x140016c58  mov     eax, [rdx+1910h]
0x140016c5e  lea     rcx, [rsp+868h+FileName]; unsigned __int16 *
0x140016c63  mov     dl, 1; unsigned __int8
0x140016c65  mov     cs:dword_1400846E8, eax
0x140016c6b  xor     r8d, r8d; unsigned __int8
0x140016c6e  call    ?TracerptWFopen@@YAPEAU_iobuf@@PEBGEE@Z; TracerptWFopen(ushort const *,uchar,uchar)
0x140016c73  mov     rbx, rax
0x140016c76  test    rax, rax
0x140016c79  jz      loc_140016F11
0x140016c7f  mov     ecx, 0FEFFh; unsigned __int16
0x140016c84  mov     rdx, rax; struct _iobuf *
0x140016c87  call    ?TracerptFPutwc@@YAKGPEAU_iobuf@@@Z; TracerptFPutwc(ushort,_iobuf *)
0x140016c8c  mov     rdx, rbx; struct _iobuf *
0x140016c8f  lea     rcx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x140016c96  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140016c9b  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016ca2  test    [rcx+1910h], r14d
0x140016ca9  jnz     short loc_140016CCD
0x140016cab  mov     r8, [rcx+1838h]
0x140016cb2  test    r8, r8
0x140016cb5  jz      short loc_140016CCD
0x140016cb7  lea     rdx, aXmlStylesheetT; "<?xml-stylesheet type=\"text/xsl\" href"...
0x140016cbe  mov     rcx, rbx; struct _iobuf *
0x140016cc1  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016cc6  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016ccd  mov     rdx, cs:qword_140082288
0x140016cd4  test    rdx, rdx
0x140016cd7  jz      short loc_140016D15
0x140016cd9  mov     rdx, [rdx+40h]
0x140016cdd  test    rdx, rdx
0x140016ce0  jz      short loc_140016D15
0x140016ce2  mov     eax, [rdx+0A0h]
0x140016ce8  lea     r8, [rdx+0B0h]
0x140016cef  mov     r9d, [rcx+21F8h]
0x140016cf6  mov     rcx, rbx; struct _iobuf *
0x140016cf9  mov     dword ptr [rsp+868h+var_840], eax
0x140016cfd  mov     eax, [rdx+0A4h]
0x140016d03  lea     rdx, aReportNameWzLe; "<Report name='%wZ' level='%d' top='%d' "...
0x140016d0a  mov     dword ptr [rsp+868h+var_848], eax
0x140016d0e  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016d13  jmp     short loc_140016D36
0x140016d15  mov     r8d, [rcx+21F8h]
0x140016d1c  lea     rdx, aReportNameTrac; "<Report name='tracerpt' level='%d' top="...
0x140016d23  mov     rcx, rbx; struct _iobuf *
0x140016d26  mov     dword ptr [rsp+868h+var_848], r15d
0x140016d2b  mov     r9d, 0Ah
0x140016d31  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016d36  mov     rcx, rbx; struct _iobuf *
0x140016d39  call    PrintReportHeader
0x140016d3e  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016d45  test    rax, rax
0x140016d48  jz      loc_140016ED6
0x140016d4e  mov     rcx, rbx; struct _iobuf *
0x140016d51  call    ReportPrintJobInfo
0x140016d56  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016d5d  test    rax, rax
0x140016d60  jz      loc_140016ED6
0x140016d66  mov     rcx, rbx
0x140016d69  call    ReportIisEvents
0x140016d6e  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016d75  test    rax, rax
0x140016d78  jz      loc_140016ED6
0x140016d7e  cmp     [rax+2138h], r15b
0x140016d85  jz      loc_140016E92
0x140016d8b  lea     rdi, aSectionNameSKe; "<Section name='%s' key='%d'%s"
0x140016d92  mov     r9d, 1770h
0x140016d98  lea     r13, asc_140047FF0; ">\r\n"
0x140016d9f  mov     rdx, rdi; unsigned __int16 *
0x140016da2  lea     r8, aTracerptcpusec; "tracerptCpusection"
0x140016da9  mov     [rsp+868h+var_848], r13
0x140016dae  mov     rcx, rbx; struct _iobuf *
0x140016db1  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016db6  mov     rcx, rbx; struct _iobuf *
0x140016db9  call    WriteTransactionStatistics
0x140016dbe  call    CalculateServiceUsage
0x140016dc3  mov     rcx, rbx; struct _iobuf *
0x140016dc6  call    PrintProcessData
0x140016dcb  mov     rcx, rbx; struct _iobuf *
0x140016dce  call    PrintServiceUsageTable
0x140016dd3  mov     rcx, rbx; struct _iobuf *
0x140016dd6  call    PrintProcessSubDataExclusive
0x140016ddb  mov     rcx, rbx; struct _iobuf *
0x140016dde  call    PrintProcessSubDataInclusive
0x140016de3  lea     rsi, aSection; "</Section>\r\n"
0x140016dea  mov     rdx, rbx; struct _iobuf *
0x140016ded  mov     rcx, rsi; unsigned __int16 *
0x140016df0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140016df5  mov     r9d, 1F40h
0x140016dfb  mov     [rsp+868h+var_848], r13
0x140016e00  lea     r8, aTracerptdisk; "tracerptDisk"
0x140016e07  mov     rdx, rdi; unsigned __int16 *
0x140016e0a  mov     rcx, rbx; struct _iobuf *
0x140016e0d  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016e12  mov     rcx, rbx; struct _iobuf *
0x140016e15  call    ReportHotFileInfo
0x140016e1a  mov     rcx, rbx; struct _iobuf *
0x140016e1d  call    PrintDiskTotals
0x140016e22  mov     rdx, rbx; struct _iobuf *
0x140016e25  mov     rcx, rsi; unsigned __int16 *
0x140016e28  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140016e2d  cmp     cs:dword_140083648, 1
0x140016e34  jz      short loc_140016E8B
0x140016e36  mov     r11, cs:qword_140083640
0x140016e3d  test    r11, r11
0x140016e40  jz      short loc_140016E8B
0x140016e42  mov     rcx, [r11+8]
0x140016e46  mov     edx, [r11]
0x140016e49  call    SortTimeStamps_DpcIsrData__EVENT_INSTANCE_DATA_DpcIsrData__ExitTimeExtractor_
0x140016e4e  mov     rcx, [r11+18h]
0x140016e52  mov     edx, [r11+10h]
0x140016e56  call    SortTimeStamps_DpcIsrData__EVENT_INSTANCE_DATA_DpcIsrData__ExitTimeExtractor_
0x140016e5b  mov     r9d, 2710h
0x140016e61  mov     [rsp+868h+var_848], r13
0x140016e66  lea     r8, aTracerptdpcisr; "tracerptDpcisr"
0x140016e6d  mov     rcx, rbx; struct _iobuf *
0x140016e70  mov     rdx, rdi; unsigned __int16 *
0x140016e73  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140016e78  mov     rdx, rbx; struct _iobuf *
0x140016e7b  call    ?Report@DpcIsrData@@QEBAXPEAU_iobuf@@@Z; DpcIsrData::Report(_iobuf *)
0x140016e80  mov     rdx, rbx; struct _iobuf *
0x140016e83  mov     rcx, rsi; unsigned __int16 *
0x140016e86  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140016e8b  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016e92  test    rax, rax
0x140016e95  jz      short loc_140016ED6
0x140016e97  mov     rdi, cs:qword_140082288
0x140016e9e  test    rdi, rdi
0x140016ea1  jz      short loc_140016ED6
0x140016ea3  mov     rdi, [rdi+40h]
0x140016ea7  test    rdi, rdi
0x140016eaa  jz      short loc_140016EF0
0x140016eac  mov     rsi, [rdi]
0x140016eaf  jmp     short loc_140016EBC
0x140016eb1  mov     rdx, rsi; struct _TRACERPT_SECTION *
0x140016eb4  mov     rsi, [rsi]
0x140016eb7  call    ?GenerateSection@@YAXPEAU_iobuf@@PEAU_TRACERPT_SECTION@@@Z; GenerateSection(_iobuf *,_TRACERPT_SECTION *)
0x140016ebc  mov     rcx, rbx; struct _iobuf *
0x140016ebf  cmp     rdi, rsi
0x140016ec2  jnz     short loc_140016EB1
0x140016ec4  call    ?PrintPdhTitles@@YAXPEAU_iobuf@@@Z; PrintPdhTitles(_iobuf *)
0x140016ec9  mov     rdx, rdi; struct _TRACERPT_REPORT *
0x140016ecc  mov     rcx, rbx; struct _iobuf *
0x140016ecf  call    ?PrintSchemaTitles@@YAXPEAU_iobuf@@PEAU_TRACERPT_REPORT@@@Z; PrintSchemaTitles(_iobuf *,_TRACERPT_REPORT *)
0x140016ed4  jmp     short loc_140016EF0
0x140016ed6  mov     rcx, [rax+21F0h]
0x140016edd  test    rcx, rcx
0x140016ee0  jz      short loc_140016EF0
0x140016ee2  cmp     [rcx+1Ch], r15d
0x140016ee6  jnz     short loc_140016EF0
0x140016ee8  mov     rcx, rbx; struct _iobuf *
0x140016eeb  call    PrintPdhCountersOutput
0x140016ef0  mov     rdx, rbx; struct _iobuf *
0x140016ef3  lea     rcx, aReport_0; "</Report>\r\n"
0x140016efa  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140016eff  mov     rcx, rbx; struct _iobuf *
0x140016f02  call    ?TracerptFClose@@YAHPEAU_iobuf@@@Z; TracerptFClose(_iobuf *)
0x140016f07  lea     rcx, [rsp+868h+FileName]; unsigned __int16 *
0x140016f0c  call    ?TracerptMergeSections@@YAJPEBG@Z; TracerptMergeSections(ushort const *)
0x140016f11  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016f18  test    [rdx+1910h], r14d
0x140016f1f  jz      short loc_140016F55
0x140016f21  mov     rax, [rdx+1838h]
0x140016f28  test    rax, rax
0x140016f2b  jz      short loc_140016F55
0x140016f2d  mov     r8, [rdx+1820h]; lpFileName
0x140016f34  lea     rcx, [rsp+868h+FileName]; psz
0x140016f39  mov     rdx, rax; OLECHAR *
0x140016f3c  call    ?TransformXML@@YAJPEBG00@Z; TransformXML(ushort const *,ushort const *,ushort const *)
0x140016f41  lea     rcx, [rsp+868h+FileName]; lpFileName
0x140016f46  mov     ebp, eax
0x140016f48  call    cs:__imp_DeleteFileW
0x140016f4e  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016f55  mov     rbx, [rdx+1888h]
0x140016f5c  test    rbx, rbx
0x140016f5f  jz      short loc_140016F7C
0x140016f61  call    cs:__imp_GetProcessHeap
0x140016f67  mov     r8, rbx; lpMem
0x140016f6a  xor     edx, edx; dwFlags
0x140016f6c  mov     rcx, rax; hHeap
0x140016f6f  call    cs:__imp_HeapFree
0x140016f75  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016f7c  mov     rbx, cs:lpMem
0x140016f83  test    rbx, rbx
0x140016f86  jz      short loc_140016FA3
0x140016f88  call    cs:__imp_GetProcessHeap
0x140016f8e  mov     r8, rbx; lpMem
0x140016f91  xor     edx, edx; dwFlags
0x140016f93  mov     rcx, rax; hHeap
0x140016f96  call    cs:__imp_HeapFree
0x140016f9c  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016fa3  mov     rcx, cs:Stream; Stream
0x140016faa  test    rcx, rcx
0x140016fad  jz      short loc_140016FD0
0x140016faf  call    cs:__imp_fclose
0x140016fb5  lea     rcx, ?TempPrintFile@@3PAGA; lpFileName
0x140016fbc  mov     cs:Stream, r15
0x140016fc3  call    cs:__imp_DeleteFileW
0x140016fc9  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140016fd0  mov     rcx, cs:qword_1400820E8; Stream
0x140016fd7  test    rcx, rcx
0x140016fda  jz      short loc_140016FFD
0x140016fdc  call    cs:__imp_fclose
0x140016fe2  lea     rcx, ?TempIisFile@@3PAGA; lpFileName
0x140016fe9  mov     cs:qword_1400820E8, r15
0x140016ff0  call    cs:__imp_DeleteFileW
0x140016ff6  mov     rdx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
  ... truncated ...
```
