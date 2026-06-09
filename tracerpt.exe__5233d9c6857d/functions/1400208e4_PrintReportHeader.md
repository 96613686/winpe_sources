# PrintReportHeader

- ea: `0x1400208e4`
- end: `0x14002117c`
- name: `PrintReportHeader`
- size: `2200`
- prototype: `__int64 __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016ae0`

## callees

- `0x140013a04`
- `0x140016360`
- `0x1400164c4`
- `0x14001f040`
- `0x14001f0f8`
- `0x1400208e4`
- `0x140032488`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140021152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140021152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002090d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021144`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002090d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021144`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140020921`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140020921`

## string_xrefs

- `0x140020974`: `		<Data name='computer' header='computer'>%s</Data>\n`
- `0x140020988`: `		<Data name='computer' header='computer' translate='value'>Client</Data>\n`
- `0x140021024`: `	<Header>\n		<Sort field='count' type='number' order='descending'/>\n		<Threshold type='top' field='count' value='3'/>\n		<Threshold type='octave' field='count'/>\n		<Data name='event' class='string'/>\n		<Data name='opcode' class='string'/>\n		<Data name='task' class='string'/>\n		<Data name='payloadGuid' class='code'/>\n		<Data name='payloadId' class='string'/>\n		<Data name='version' class='string'/>\n		<Data name='count' class='number' summary='total'/>\n	</Header>\n`
- `0x1400210b4`: `	<Item>\n		<Data name='event'>%s</Data>\n		<Data name='opcode'>%s</Data>\n		<Data name='task'>%d</Data>\n		<Data name='payloadGuid'>%s</Data>\n		<Data name='payloadId'>%d</Data>\n		<Data name='version'>%d</Data>\n		<Data name='count'>%d</Data>\n	</Item>\n`
- `0x1400210d7`: `	<Item>\n		<Data name='event'>Unknown</Data>\n		<Data name='opcode'>%d</Data>\n		<Data name='task'>%d</Data>\n		<Data name='payloadGuid'>%s</Data>\n		<Data name='payloadId'>%d</Data>\n		<Data name='version'>%d</Data>\n		<Data name='count'>%d</Data>\n	</Item>\n`

## pseudocode

```c
int __fastcall PrintReportHeader(struct _iobuf *a1)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // r14
  wchar_t *v5; // rdx
  wchar_t *v6; // rdx
  wchar_t *v7; // rdx
  wchar_t *v8; // rdx
  wchar_t *v9; // rdx
  char v10; // bl
  wchar_t *v11; // rdx
  const wchar_t *v12; // r8
  _QWORD *v13; // rcx
  int v14; // ebp
  __int64 *v15; // rsi
  __int64 *v16; // rbx
  unsigned __int16 *v17; // r9
  unsigned __int16 *v18; // r9
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 v21; // rax
  unsigned int v22; // esi
  unsigned __int16 *v23; // rbx
  _QWORD *v24; // r8
  __int64 v25; // r15
  __int64 v26; // rsi
  unsigned __int64 v27; // r12
  char v28; // r13
  __int64 v29; // rdx
  unsigned __int16 *v30; // rax
  LPVOID *v31; // rbx
  int v32; // r13d
  LPVOID *v33; // rbp
  unsigned __int16 *v34; // rax
  _WORD *v35; // rcx
  __int64 v36; // r9
  _WORD *v37; // rdx
  __int64 v38; // r8
  _WORD *v39; // rcx
  LPVOID *v40; // rsi
  LPVOID *v41; // r11
  LPVOID *v42; // rdx
  LPVOID *v43; // rbp
  LPVOID *v44; // r12
  __int16 v45; // ax
  unsigned __int16 v46; // r8
  const wchar_t *v47; // r9
  HANDLE v48; // rax
  __int64 v50; // [rsp+20h] [rbp-928h]
  __int64 v51; // [rsp+20h] [rbp-928h]
  char v52[8]; // [rsp+28h] [rbp-920h]
  __int64 v53; // [rsp+30h] [rbp-918h]
  __int64 v54; // [rsp+38h] [rbp-910h]
  __int64 v55; // [rsp+40h] [rbp-908h]
  int v56; // [rsp+50h] [rbp-8F8h]
  unsigned __int16 *v57; // [rsp+50h] [rbp-8F8h]
  LPVOID *v58; // [rsp+60h] [rbp-8E8h]
  unsigned __int16 *v59; // [rsp+68h] [rbp-8E0h]
  unsigned __int16 v60[64]; // [rsp+70h] [rbp-8D8h] BYREF
  _WORD v61[1024]; // [rsp+F0h] [rbp-858h] BYREF

  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x800u);
  v59 = v3;
  v4 = v3;
  if ( v3 )
  {
    TracerptFPutws((wchar_t *)L"<Section key='-90000' name='tracerptHeader'>\r\n", a1);
    TracerptFPutws((wchar_t *)L"<Table name='client' style='info'>\r\n", a1);
    TracerptFPutws((wchar_t *)L"\t<Item>\r\n", a1);
    if ( lpMem )
      TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='computer' header='computer'>%s</Data>\r\n");
    else
      TracerptFPutws((wchar_t *)L"\t\t<Data name='computer' header='computer' translate='value'>Client</Data>\r\n", a1);
    v5 = L"\t\t<Data name='build'>%d</Data>\r\n";
    if ( !dword_140082124 )
      v5 = (wchar_t *)L"\t\t<Data name='build' visible='false'>%d</Data>\r\n";
    TracerptFWPrintf(a1, v5);
    v6 = L"\t\t<Data name='processors'>%d</Data>\r\n";
    if ( !dword_14008210C )
      v6 = (wchar_t *)L"\t\t<Data name='processors' visible='false'>%d</Data>\r\n";
    TracerptFWPrintf(a1, v6);
    v7 = L"\t\t<Data name='clock' units='MHz'>%d</Data>\r\n";
    if ( !dword_140082110 )
      v7 = (wchar_t *)L"\t\t<Data name='clock' units='MHz' visible='false'>%d</Data>\r\n";
    TracerptFWPrintf(a1, v7);
    v8 = L"\t\t<Data name='memory' units='MB'>%d</Data>\r\n";
    if ( !dword_140082114 )
      v8 = (wchar_t *)L"\t\t<Data name='memory' units='MB' visible='false'>%d</Data>\r\n";
    TracerptFWPrintf(a1, v8);
    v9 = L"\t\t<Data name='architecture' units='bit'>%d</Data>\r\n";
    if ( !*((_DWORD *)g_TraceContext + 2170) )
      v9 = (wchar_t *)L"\t\t<Data name='architecture' units='bit' visible='false'>%d</Data>\r\n";
    TracerptFWPrintf(a1, v9);
    TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
    TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
    TracerptFPutws((wchar_t *)L"<Table name='collection' style='info'>\r\n", a1);
    TracerptFPutws((wchar_t *)L"\t<Item>\r\n", a1);
    if ( g_TraceContext )
    {
      v10 = byte_1400820CA == 0;
      PrintDateStringXmlTag(v4, *(_QWORD *)&CurrentSystem, byte_1400820CA == 0);
      TracerptFWPrintf(a1, v4);
      PrintDateStringXmlTag(v4, *(_QWORD *)&SystemTimeAsFileTime, v10);
      TracerptFWPrintf(a1, v4);
      TracerptFWPrintf(
        a1,
        (wchar_t *)L"\t\t<Data name='duration' header='duration' units='sec'>%I64u</Data>\r\n",
        (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem) / 0x989680uLL);
      if ( *((_DWORD *)g_TraceContext + 2) || *((_DWORD *)g_TraceContext + 3) )
      {
        LODWORD(v50) = TotalEventsLost;
        TracerptFWPrintf(
          a1,
          (wchar_t *)L"\t\t<Data name='buffers'>%d</Data>\r\n"
                      "\t\t<Data name='events'>%d</Data>\r\n"
                      "\t\t<Data name='lostEvents'>%d</Data>\r\n",
          TotalBuffersRead,
          TotalEventCount,
          v50);
        v11 = L"\t\t<Data name='skippedEvents'>%d</Data>\r\n";
        if ( !TotalEventSkipped )
          v11 = (wchar_t *)L"\t\t<Data name='skippedEvents' visible='false'>%d</Data>\r\n";
        TracerptFWPrintf(a1, v11);
        v12 = L"Yes";
        if ( !*((_BYTE *)g_TraceContext + 8505) )
          v12 = L"No";
        TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='useTimingWindow' translate='value'>%ws</Data>\r\n", v12);
      }
    }
    TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
    TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
    v13 = g_TraceContext;
    v14 = 1;
    if ( g_TraceContext )
    {
      v15 = (__int64 *)qword_1400821B0;
      if ( (__int64 *)qword_1400821B0 != &qword_1400821B0 )
      {
        do
        {
          v16 = v15;
          v15 = (__int64 *)*v15;
          if ( v14 )
          {
            TracerptFPutws((wchar_t *)L"<Table name='files' style='info'>\r\n", a1);
            v14 = 0;
          }
          TracerptFPutws((wchar_t *)L"\t<Item>\r\n", a1);
          TracerptFPutws((wchar_t *)L"\t\t<Data name='file'>", a1);
          v17 = L"-";
          if ( v16[4] )
            v17 = (unsigned __int16 *)v16[4];
          PrintWString(a1, 1u, 0, v17);
          TracerptFPutws((wchar_t *)L"</Data>\r\n", a1);
          TracerptFPutws((wchar_t *)L"\t\t<Data name='logger'>", a1);
          v18 = L"-";
          if ( v16[5] )
            v18 = (unsigned __int16 *)v16[5];
          PrintWString(a1, 1u, 0, v18);
          TracerptFPutws((wchar_t *)L"</Data>\r\n", a1);
          v19 = v16[2];
          if ( !v19 )
          {
            v16[2] = (__int64)CurrentSystem;
            v19 = (__int64)CurrentSystem;
          }
          if ( !v16[3] )
            v16[3] = (__int64)SystemTimeAsFileTime;
          PrintDateStringXmlTag(v4, v19, 1);
          TracerptFWPrintf(a1, v4);
          v51 = v16[3];
          v20 = (v51 - v16[2]) / 0x989680uLL;
          PrintDateStringXmlTag(v4, v51, 1);
          TracerptFWPrintf(a1, v4);
          TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='fileDuration' units='sec'>%I64u</Data>\r\n", v20);
          TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
        }
        while ( v15 != &qword_1400821B0 );
        v13 = g_TraceContext;
      }
    }
    v21 = v13[1086];
    if ( v21 )
    {
      v22 = 0;
      v23 = *(unsigned __int16 **)(v21 + 56);
      v56 = 0;
      if ( *(_DWORD *)(v21 + 32) )
      {
        do
        {
          if ( v14 )
          {
            TracerptFPutws((wchar_t *)L"<Table name='files' style='info'>\r\n", a1);
            v14 = 0;
          }
          TracerptFPutws((wchar_t *)L"\t<Item>\r\n", a1);
          TracerptFPutws((wchar_t *)L"\t\t<Data name='file'>", a1);
          PrintWString(a1, 1u, 0, v23);
          TracerptFPutws((wchar_t *)L"</Data>\r\n", a1);
          v24 = g_TraceContext;
          if ( !*(_DWORD *)(*((_QWORD *)g_TraceContext + 1086) + 28LL) )
          {
            v25 = qword_1400820A8;
            v26 = qword_1400820A0;
            v27 = (qword_1400820A8 - qword_1400820A0) / 0x989680uLL;
            if ( *((_BYTE *)g_TraceContext + 8505) )
            {
              v26 = PDHToTraceTime(qword_1400820A0);
              v25 = PDHToTraceTime(qword_1400820A8);
              v28 = 1;
            }
            else
            {
              v28 = 0;
            }
            PrintDateStringXmlTag(v4, v26, v28);
            TracerptFWPrintf(a1, v4);
            PrintDateStringXmlTag(v4, v25, v28);
            TracerptFWPrintf(a1, v4);
            TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='fileDuration' units='sec'>%I64u</Data>\r\n", v27);
            v24 = g_TraceContext;
            v22 = v56;
          }
          v29 = -1;
          do
            ++v29;
          while ( v23[v29] );
          v30 = &v23[v29 + 1];
          v23 = 0;
          if ( v22 != *(_DWORD *)(v24[1086] + 32LL) - 1 )
            v23 = v30;
          TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
          v13 = g_TraceContext;
          v56 = ++v22;
        }
        while ( v22 < *(_DWORD *)(*((_QWORD *)g_TraceContext + 1086) + 32LL) );
      }
    }
    if ( !v14 )
    {
      TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
      v13 = g_TraceContext;
    }
    if ( v13 )
    {
      v31 = (LPVOID *)qword_140082180;
      v32 = 1;
      if ( &qword_140082180 != qword_140082180 )
      {
        do
        {
          memset_0(v61, 0, sizeof(v61));
          v33 = (LPVOID *)*v31;
          v58 = (LPVOID *)*v31;
          if ( *((_DWORD *)v31 + 11) )
          {
            v34 = CpdiGuidToString(v60, 0x40u, (struct _GUID *)v31 + 3);
            v35 = v31[4];
            v57 = v34;
            if ( v35 )
            {
              v36 = 2147483646;
              v37 = v61;
              v38 = 1024;
              do
              {
                if ( !v36 )
                  break;
                if ( !*v35 )
                  break;
                *v37++ = *v35++;
                --v36;
                --v38;
              }
              while ( v38 );
              v39 = v37 - 1;
              if ( v38 )
                v39 = v37;
              *v39 = 0;
            }
            else
            {
              v61[0] = 0;
            }
            v40 = (LPVOID *)v31[520];
            if ( v31 + 520 != v40 )
            {
              do
              {
                v41 = v40;
                v42 = v40;
                v43 = v40;
                v44 = v40;
                v40 = (LPVOID *)*v40;
                if ( v32 )
                {
                  TracerptFPutws((wchar_t *)L"<Table name='events'>\r\n", a1);
                  TracerptFWPrintf(
                    a1,
                    (wchar_t *)L"\t<Header>\r\n"
                                "\t\t<Sort field='count' type='number' order='descending'/>\r\n"
                                "\t\t<Threshold type='top' field='count' value='3'/>\r\n"
                                "\t\t<Threshold type='octave' field='count'/>\r\n"
                                "\t\t<Data name='event' class='string'/>\r\n"
                                "\t\t<Data name='opcode' class='string'/>\r\n"
                                "\t\t<Data name='task' class='string'/>\r\n"
                                "\t\t<Data name='payloadGuid' class='code'/>\r\n"
                                "\t\t<Data name='payloadId' class='string'/>\r\n"
                                "\t\t<Data name='version' class='string'/>\r\n"
                                "\t\t<Data name='count' class='number' summary='total'/>\r\n"
                                "\t</Header>\r\n");
                  v32 = 0;
                  v41 = v44;
                  v42 = v44;
                }
                if ( *((_DWORD *)v41 + 5) )
                {
                  v45 = *((_WORD *)v31 + 3124);
                  if ( (v45 & 8) != 0 || (v45 & 0x100) == 0 )
                    v46 = *((_WORD *)v43 + 12);
                  else
                    v46 = *((unsigned __int8 *)v43 + 29);
                  if ( v61[0] )
                  {
                    v47 = L"Default";
                    if ( v41[5] )
                      v47 = (const wchar_t *)v41[5];
                    LODWORD(v55) = *((_DWORD *)v41 + 5);
                    LODWORD(v54) = *((unsigned __int8 *)v44 + 26);
                    LODWORD(v53) = v46;
                    LODWORD(v50) = *((unsigned __int16 *)v44 + 15);
                    TracerptFWPrintf(
                      a1,
                      (wchar_t *)L"\t<Item>\r\n"
                                  "\t\t<Data name='event'>%s</Data>\r\n"
                                  "\t\t<Data name='opcode'>%s</Data>\r\n"
                                  "\t\t<Data name='task'>%d</Data>\r\n"
                                  "\t\t<Data name='payloadGuid'>%s</Data>\r\n"
                                  "\t\t<Data name='payloadId'>%d</Data>\r\n"
                                  "\t\t<Data name='version'>%d</Data>\r\n"
                                  "\t\t<Data name='count'>%d</Data>\r\n"
                                  "\t</Item>\r\n",
                      v61,
                      v47,
                      v50,
                      v57,
                      v53,
                      v54,
                      v55);
                  }
                  else
                  {
                    LODWORD(v54) = *((_DWORD *)v41 + 5);
                    LODWORD(v53) = *((unsigned __int8 *)v44 + 26);
                    *(_DWORD *)v52 = v46;
                    TracerptFWPrintf(
                      a1,
                      (wchar_t *)L"\t<Item>\r\n"
                                  "\t\t<Data name='event'>Unknown</Data>\r\n"
                                  "\t\t<Data name='opcode'>%d</Data>\r\n"
                                  "\t\t<Data name='task'>%d</Data>\r\n"
                                  "\t\t<Data name='payloadGuid'>%s</Data>\r\n"
                                  "\t\t<Data name='payloadId'>%d</Data>\r\n"
                                  "\t\t<Data name='version'>%d</Data>\r\n"
                                  "\t\t<Data name='count'>%d</Data>\r\n"
                                  "\t</Item>\r\n",
                      *((unsigned __int8 *)v42 + 29),
                      *((unsigned __int16 *)v44 + 15),
                      v57,
                      *(_QWORD *)v52,
                      v53,
                      v54);
                  }
                }
              }
              while ( v31 + 520 != v40 );
              v33 = v58;
            }
          }
          v31 = v33;
        }
        while ( &qword_140082180 != v33 );
        v4 = v59;
        if ( !v32 )
          TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
      }
    }
    TracerptFPutws((wchar_t *)L"</Section>\r\n", a1);
    v48 = GetProcessHeap();
    LODWORD(v3) = HeapFree(v48, 0, v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x1400208e4  push    rbx
0x1400208e6  push    rbp
0x1400208e7  push    rsi
0x1400208e8  push    rdi
0x1400208e9  push    r12
0x1400208eb  push    r13
0x1400208ed  push    r14
0x1400208ef  push    r15
0x1400208f1  sub     rsp, 908h
0x1400208f8  mov     rax, cs:__security_cookie
0x1400208ff  xor     rax, rsp
0x140020902  mov     [rsp+948h+var_58], rax
0x14002090a  mov     rdi, rcx
0x14002090d  call    cs:__imp_GetProcessHeap
0x140020913  mov     edx, 8; dwFlags
0x140020918  mov     r8d, 800h; dwBytes
0x14002091e  mov     rcx, rax; hHeap
0x140020921  call    cs:__imp_HeapAlloc
0x140020927  xor     r15d, r15d
0x14002092a  mov     [rsp+948h+var_8E0], rax
0x14002092f  mov     r14, rax
0x140020932  test    rax, rax
0x140020935  jz      loc_140021158
0x14002093b  mov     rdx, rdi; struct _iobuf *
0x14002093e  lea     rcx, aSectionKey9000_0; "<Section key='-90000' name='tracerptHea"...
0x140020945  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002094a  mov     rdx, rdi; struct _iobuf *
0x14002094d  lea     rcx, aTableNameClien_1; "<Table name='client' style='info'>\r\n"
0x140020954  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020959  mov     rdx, rdi; struct _iobuf *
0x14002095c  lea     rcx, aItem_0; "\t<Item>\r\n"
0x140020963  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020968  mov     r8, cs:lpMem
0x14002096f  test    r8, r8
0x140020972  jz      short loc_140020985
0x140020974  lea     rdx, aDataNameComput_0; "\t\t<Data name='computer' header='compu"...
0x14002097b  mov     rcx, rdi; struct _iobuf *
0x14002097e  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020983  jmp     short loc_140020994
0x140020985  mov     rdx, rdi; struct _iobuf *
0x140020988  lea     rcx, aDataNameComput; "\t\t<Data name='computer' header='compu"...
0x14002098f  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020994  mov     r8d, cs:dword_140082124
0x14002099b  lea     rdx, aDataNameBuildD; "\t\t<Data name='build'>%d</Data>\r\n"
0x1400209a2  mov     rcx, rdi; struct _iobuf *
0x1400209a5  test    r8d, r8d
0x1400209a8  jnz     short loc_1400209B1
0x1400209aa  lea     rdx, aDataNameBuildV; "\t\t<Data name='build' visible='false'>"...
0x1400209b1  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400209b6  mov     r8d, cs:dword_14008210C
0x1400209bd  lea     rdx, aDataNameProces; "\t\t<Data name='processors'>%d</Data>\r"...
0x1400209c4  mov     rcx, rdi; struct _iobuf *
0x1400209c7  test    r8d, r8d
0x1400209ca  jnz     short loc_1400209D3
0x1400209cc  lea     rdx, aDataNameProces_0; "\t\t<Data name='processors' visible='fa"...
0x1400209d3  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400209d8  mov     r8d, cs:dword_140082110
0x1400209df  lea     rdx, aDataNameClockU; "\t\t<Data name='clock' units='MHz'>%d</"...
0x1400209e6  mov     rcx, rdi; struct _iobuf *
0x1400209e9  test    r8d, r8d
0x1400209ec  jnz     short loc_1400209F5
0x1400209ee  lea     rdx, aDataNameClockU_0; "\t\t<Data name='clock' units='MHz' visi"...
0x1400209f5  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400209fa  mov     r8d, cs:dword_140082114
0x140020a01  lea     rdx, aDataNameMemory; "\t\t<Data name='memory' units='MB'>%d</"...
0x140020a08  mov     rcx, rdi; struct _iobuf *
0x140020a0b  test    r8d, r8d
0x140020a0e  jnz     short loc_140020A17
0x140020a10  lea     rdx, aDataNameMemory_0; "\t\t<Data name='memory' units='MB' visi"...
0x140020a17  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020a1c  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020a23  lea     rdx, aDataNameArchit; "\t\t<Data name='architecture' units='bi"...
0x140020a2a  mov     rcx, rdi; struct _iobuf *
0x140020a2d  mov     r8d, [rax+21E8h]
0x140020a34  test    r8d, r8d
0x140020a37  lea     rax, aDataNameArchit_0; "\t\t<Data name='architecture' units='bi"...
0x140020a3e  cmovz   rdx, rax; unsigned __int16 *
0x140020a42  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020a47  mov     rdx, rdi; struct _iobuf *
0x140020a4a  lea     rcx, aItem_1; "\t</Item>\r\n"
0x140020a51  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020a56  mov     rdx, rdi; struct _iobuf *
0x140020a59  lea     rcx, aTable_0; "</Table>\r\n"
0x140020a60  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020a65  mov     rdx, rdi; struct _iobuf *
0x140020a68  lea     rcx, aTableNameColle; "<Table name='collection' style='info'>"...
0x140020a6f  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020a74  mov     rdx, rdi; struct _iobuf *
0x140020a77  lea     rcx, aItem_0; "\t<Item>\r\n"
0x140020a7e  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020a83  cmp     cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA, r15; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020a8a  mov     r13, 0D6BF94D5E57A42BDh
0x140020a94  jz      loc_140020BB7
0x140020a9a  cmp     cs:byte_1400820CA, r15b
0x140020aa1  lea     r9, aHeaderCollecte; "header='collected'"
0x140020aa8  mov     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140020aaf  lea     r8, aStart; "start"
0x140020ab6  setz    bl
0x140020ab9  mov     rcx, r14; unsigned __int16 *
0x140020abc  mov     [rsp+948h+var_920], bl; char
0x140020ac0  mov     [rsp+948h+var_928], rax; __int64
0x140020ac5  call    PrintDateStringXmlTag
0x140020aca  mov     rdx, r14; unsigned __int16 *
0x140020acd  mov     rcx, rdi; struct _iobuf *
0x140020ad0  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020ad5  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140020adc  lea     r8, aEnd; "end"
0x140020ae3  mov     [rsp+948h+var_920], bl; char
0x140020ae7  xor     r9d, r9d
0x140020aea  mov     rcx, r14; unsigned __int16 *
0x140020aed  mov     [rsp+948h+var_928], rax; __int64
0x140020af2  call    PrintDateStringXmlTag
0x140020af7  mov     rdx, r14; unsigned __int16 *
0x140020afa  mov     rcx, rdi; struct _iobuf *
0x140020afd  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020b02  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140020b09  mov     rax, r13
0x140020b0c  sub     rcx, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140020b13  mul     rcx
0x140020b16  mov     rcx, rdi; struct _iobuf *
0x140020b19  shr     rdx, 17h
0x140020b1d  mov     r8, rdx
0x140020b20  lea     rdx, aDataNameDurati; "\t\t<Data name='duration' header='durat"...
0x140020b27  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020b2c  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020b33  cmp     [rax+8], r15d
0x140020b37  ja      short loc_140020B3F
0x140020b39  cmp     [rax+0Ch], r15d
0x140020b3d  jbe     short loc_140020BB7
0x140020b3f  mov     eax, cs:?TotalEventsLost@@3KA; ulong TotalEventsLost
0x140020b45  lea     rdx, aDataNameBuffer; "\t\t<Data name='buffers'>%d</Data>\r\n"...
0x140020b4c  mov     r9d, cs:?TotalEventCount@@3KA; ulong TotalEventCount
0x140020b53  mov     rcx, rdi; struct _iobuf *
0x140020b56  mov     r8d, cs:?TotalBuffersRead@@3KA; ulong TotalBuffersRead
0x140020b5d  mov     dword ptr [rsp+948h+var_928], eax
0x140020b61  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020b66  mov     r8d, cs:?TotalEventSkipped@@3KA; ulong TotalEventSkipped
0x140020b6d  lea     rdx, aDataNameSkippe; "\t\t<Data name='skippedEvents'>%d</Data"...
0x140020b74  mov     rcx, rdi; struct _iobuf *
0x140020b77  test    r8d, r8d
0x140020b7a  jnz     short loc_140020B83
0x140020b7c  lea     rdx, aDataNameSkippe_0; "\t\t<Data name='skippedEvents' visible="...
0x140020b83  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020b88  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020b8f  lea     rcx, aNo; "No"
0x140020b96  lea     r8, aYes; "Yes"
0x140020b9d  lea     rdx, aDataNameUsetim; "\t\t<Data name='useTimingWindow' transl"...
0x140020ba4  cmp     [rax+2139h], r15b
0x140020bab  cmovz   r8, rcx
0x140020baf  mov     rcx, rdi; struct _iobuf *
0x140020bb2  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020bb7  mov     rdx, rdi; struct _iobuf *
0x140020bba  lea     rcx, aItem_1; "\t</Item>\r\n"
0x140020bc1  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020bc6  mov     rdx, rdi; struct _iobuf *
0x140020bc9  lea     rcx, aTable_0; "</Table>\r\n"
0x140020bd0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020bd5  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020bdc  mov     ebp, 1
0x140020be1  test    rcx, rcx
0x140020be4  jz      loc_140020D65
0x140020bea  mov     rsi, cs:qword_1400821B0
0x140020bf1  lea     r12, qword_1400821B0
0x140020bf8  cmp     rsi, r12
0x140020bfb  jz      loc_140020D65
0x140020c01  lea     rbx, [rsi]
0x140020c04  mov     rsi, [rsi]
0x140020c07  test    ebp, ebp
0x140020c09  jz      short loc_140020C1D
0x140020c0b  mov     rdx, rdi; struct _iobuf *
0x140020c0e  lea     rcx, aTableNameFiles; "<Table name='files' style='info'>\r\n"
0x140020c15  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020c1a  mov     ebp, r15d
0x140020c1d  mov     rdx, rdi; struct _iobuf *
0x140020c20  lea     rcx, aItem_0; "\t<Item>\r\n"
0x140020c27  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020c2c  mov     rdx, rdi; struct _iobuf *
0x140020c2f  lea     rcx, aDataNameFile; "\t\t<Data name='file'>"
0x140020c36  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020c3b  cmp     [rbx+20h], r15
0x140020c3f  lea     r9, asc_140049BB4; "-"
0x140020c46  mov     dl, 1; unsigned __int8
0x140020c48  mov     rcx, rdi; struct _iobuf *
0x140020c4b  cmovnz  r9, [rbx+20h]; unsigned __int16 *
0x140020c50  xor     r8d, r8d; unsigned __int8
0x140020c53  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140020c58  mov     rdx, rdi; struct _iobuf *
0x140020c5b  lea     rcx, aData; "</Data>\r\n"
0x140020c62  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020c67  mov     rdx, rdi; struct _iobuf *
0x140020c6a  lea     rcx, aDataNameLogger; "\t\t<Data name='logger'>"
0x140020c71  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020c76  cmp     [rbx+28h], r15
0x140020c7a  lea     r9, asc_140049BB4; "-"
0x140020c81  mov     dl, 1; unsigned __int8
0x140020c83  mov     rcx, rdi; struct _iobuf *
0x140020c86  cmovnz  r9, [rbx+28h]; unsigned __int16 *
0x140020c8b  xor     r8d, r8d; unsigned __int8
0x140020c8e  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140020c93  mov     rdx, rdi; struct _iobuf *
0x140020c96  lea     rcx, aData; "</Data>\r\n"
0x140020c9d  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020ca2  mov     rcx, [rbx+10h]
0x140020ca6  test    rcx, rcx
0x140020ca9  jnz     short loc_140020CBD
0x140020cab  mov     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140020cb2  mov     [rbx+10h], rax
0x140020cb6  mov     rcx, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140020cbd  cmp     [rbx+18h], r15
0x140020cc1  jnz     short loc_140020CCE
0x140020cc3  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140020cca  mov     [rbx+18h], rax
0x140020cce  mov     [rsp+948h+var_920], 1; char
0x140020cd3  lea     r8, aStart; "start"
0x140020cda  mov     [rsp+948h+var_928], rcx; __int64
0x140020cdf  xor     r9d, r9d
0x140020ce2  mov     rcx, r14; unsigned __int16 *
0x140020ce5  call    PrintDateStringXmlTag
0x140020cea  mov     rdx, r14; unsigned __int16 *
0x140020ced  mov     rcx, rdi; struct _iobuf *
0x140020cf0  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020cf5  mov     r9, [rbx+18h]
0x140020cf9  lea     r8, aEnd; "end"
0x140020d00  mov     rcx, r9
0x140020d03  mov     [rsp+948h+var_920], 1; char
0x140020d08  sub     rcx, [rbx+10h]
0x140020d0c  mov     rax, r13
0x140020d0f  mul     rcx
0x140020d12  mov     [rsp+948h+var_928], r9; __int64
0x140020d17  mov     rcx, r14; unsigned __int16 *
0x140020d1a  mov     rbx, rdx
0x140020d1d  xor     r9d, r9d
0x140020d20  shr     rbx, 17h
0x140020d24  call    PrintDateStringXmlTag
0x140020d29  mov     rdx, r14; unsigned __int16 *
0x140020d2c  mov     rcx, rdi; struct _iobuf *
0x140020d2f  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020d34  mov     r8, rbx
0x140020d37  lea     rdx, aDataNameFiledu; "\t\t<Data name='fileDuration' units='se"...
0x140020d3e  mov     rcx, rdi; struct _iobuf *
0x140020d41  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140020d46  mov     rdx, rdi; struct _iobuf *
0x140020d49  lea     rcx, aItem_1; "\t</Item>\r\n"
0x140020d50  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020d55  cmp     rsi, r12
0x140020d58  jnz     loc_140020C01
0x140020d5e  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020d65  mov     rax, [rcx+21F0h]
0x140020d6c  test    rax, rax
0x140020d6f  jz      loc_140020F12
0x140020d75  mov     esi, r15d
0x140020d78  mov     rbx, [rax+38h]
0x140020d7c  mov     dword ptr [rsp+948h+var_8F8], r15d
0x140020d81  cmp     [rax+20h], r15d
0x140020d85  jbe     loc_140020F12
0x140020d8b  test    ebp, ebp
0x140020d8d  jz      short loc_140020DA1
0x140020d8f  mov     rdx, rdi; struct _iobuf *
0x140020d92  lea     rcx, aTableNameFiles; "<Table name='files' style='info'>\r\n"
0x140020d99  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020d9e  mov     ebp, r15d
0x140020da1  mov     rdx, rdi; struct _iobuf *
0x140020da4  lea     rcx, aItem_0; "\t<Item>\r\n"
0x140020dab  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020db0  mov     rdx, rdi; struct _iobuf *
0x140020db3  lea     rcx, aDataNameFile; "\t\t<Data name='file'>"
0x140020dba  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020dbf  mov     r9, rbx; unsigned __int16 *
0x140020dc2  xor     r8d, r8d; unsigned __int8
0x140020dc5  mov     dl, 1; unsigned __int8
0x140020dc7  mov     rcx, rdi; struct _iobuf *
0x140020dca  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140020dcf  mov     rdx, rdi; struct _iobuf *
0x140020dd2  lea     rcx, aData; "</Data>\r\n"
0x140020dd9  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140020dde  mov     r8, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140020de5  mov     rax, [r8+21F0h]
0x140020dec  cmp     [rax+1Ch], r15d
0x140020df0  jnz     loc_140020EBC
0x140020df6  mov     r15, cs:qword_1400820A8
0x140020dfd  mov     rax, r13
0x140020e00  mov     rsi, cs:qword_1400820A0
0x140020e07  mov     rcx, r15
0x140020e0a  sub     rcx, rsi
0x140020e0d  mul     rcx
0x140020e10  xor     eax, eax
0x140020e12  mov     r12, rdx
0x140020e15  shr     r12, 17h
0x140020e19  cmp     [r8+2139h], al
0x140020e20  jz      short loc_140020E41
0x140020e22  mov     rcx, rsi
0x140020e25  call    PDHToTraceTime
0x140020e2a  mov     rcx, cs:qword_1400820A8
0x140020e31  mov     rsi, rax
0x140020e34  call    PDHToTraceTime
0x140020e39  mov     r15, rax
0x140020e3c  mov     r13b, 1
0x140020e3f  jmp     short loc_140020E44
0x140020e41  mov     r13b, al
0x140020e44  mov     [rsp+948h+var_920], r13b; char
  ... truncated ...
```
