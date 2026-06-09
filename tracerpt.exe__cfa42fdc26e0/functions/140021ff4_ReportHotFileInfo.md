# ReportHotFileInfo

- ea: `0x140021ff4`
- end: `0x14002247a`
- name: `ReportHotFileInfo`
- size: `1158`
- prototype: `__int64 __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140016ae0`

## callees

- `0x1400020e4`
- `0x140002724`
- `0x140009c04`
- `0x140013a04`
- `0x140016360`
- `0x1400164c4`
- `0x14001e8a8`
- `0x140021eb4`
- `0x140021ff4`
- `0x140040130`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1400221f6`
- `msvcrt!_wcsnicmp` at `0x1400221f6`
- `msvcrt!qsort` at `0x140022151`
- `msvcrt!qsort` at `0x140022151`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400221ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400221ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400221be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400221be`

## string_xrefs

- `0x14002215c`: `<Table name='hotFile' level='1' key='100' topic='hotFiles'>\n<Summary key='4' find='top' field='ioRate' topic='diskInfo'>\n  <Data name='file' label='topFileIO'/>\n  <Data name='ioRate' format='#,##0'/>\n</Summary>\n<Header>\n  <Sort field='ioRate' type='number' order='descending'/>\n  <Threshold type='top' field='count' value='%d'/>\n  <Threshold type='octave' field='ioRate'/>\n  <Data name="disk" class="string"/>\n  <Data name="file" class="string"/>\n  <Data name="readRate" class="`
- `0x140022312`: `		<Data name='ioRate' visible='false'>%1.3f</Data>\n		<Data name='readRate'>%1.3f</Data>\n		<Data name='readSize'>%d</Data>\n		<Data name='writeRate'>%1.3f</Data>\n		<Data name='writeSize'>%d</Data>\n`
- `0x1400223d3`: `		<Item>\n			<Data name='image'>%s</Data>\n			<Data name='pid'>%d</Data>\n			<Data name='ioRate' visible='false'>%1.3f</Data>\n			<Data name='readRate'>%1.3f</Data>\n			<Data name='readSize'>%d</Data>\n			<Data name='writeRate'>%1.3f</Data>\n			<Data name='writeSize'>%d</Data>\n		</Item>\n`

## pseudocode

```c
void __fastcall ReportHotFileInfo(struct _iobuf *a1)
{
  unsigned __int64 v2; // rsi
  _DWORD *v3; // rax
  unsigned __int64 v4; // rdx
  bool v5; // zf
  _DWORD *v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rbx
  unsigned __int64 v9; // rax
  double v10; // xmm6_8
  double v11; // xmm6_8
  unsigned __int64 v12; // rcx
  unsigned __int16 *v13; // r14
  __int64 v14; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // rax
  int v17; // eax
  unsigned __int16 *v18; // rbx
  unsigned __int64 v19; // rax
  int v20; // ecx
  int v21; // r9d
  double v22; // xmm1_8
  double v23; // xmm0_8
  int v24; // ecx
  int v25; // r8d
  double v26; // xmm2_8
  double v27; // xmm3_8
  double v28; // xmm2_8
  _DWORD *v29; // rbx
  _DWORD *v30; // rdi
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  double v34; // xmm3_8
  double v35; // xmm2_8
  int v36; // ecx
  double v37; // xmm0_8
  double v38; // xmm1_8
  double v39; // xmm0_8
  const struct std::nothrow_t *v40; // rdx
  __int64 v41; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+30h] [rbp-D0h]
  __int64 v43; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  void *Base; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v46[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v47[88]; // [rsp+80h] [rbp-80h] BYREF

  if ( HotFileTableOn
    && qword_140082140 != &qword_140082140
    && qword_140082130 != (struct _PROCESS_RECORD *)&qword_140082130 )
  {
    v2 = 0;
    v3 = *(_DWORD **)Block;
    while ( v3 != Block )
    {
      v4 = v2 + 1;
      v5 = (v3[21] | v3[23]) == 0;
      v3 = *(_DWORD **)v3;
      if ( v5 )
        v4 = v2;
      v2 = v4;
    }
    v6 = qword_140082158;
    while ( 1 )
    {
      v6 = *(_DWORD **)v6;
      if ( v6 == (_DWORD *)-1LL )
        break;
      v7 = v2 + 1;
      if ( !(v6[15] | v6[17]) )
        v7 = v2;
      v2 = v7;
    }
    if ( v2 )
    {
      v8 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem;
      v9 = 16 * v2;
      if ( !is_mul_ok(v2, 0x10u) )
        v9 = -1;
      Base = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
      if ( Base )
      {
        if ( v8 < 0 )
          v10 = (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1))
              + (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1));
        else
          v10 = (double)(int)v8;
        v11 = v10 / 10000000.0;
        v44 = 0;
        v46[0] = &Base;
        v46[1] = &v44;
        ForEachHotFile__lambda_6c0bdc72014db60bac9be87f94169d1e_(v46);
        qsort(Base, v2, 0x10u, (_CoreCrtNonSecureSearchSortCompareFunction)CompareFileRecord);
        if ( v2 > 0x14 )
          v2 = 20;
        TracerptFWPrintf(
          a1,
          (wchar_t *)L"<Table name='hotFile' level='1' key='100' topic='hotFiles'>\r\n"
                      "<Summary key='4' find='top' field='ioRate' topic='diskInfo'>\r\n"
                      "  <Data name='file' label='topFileIO'/>\r\n"
                      "  <Data name='ioRate' format='#,##0'/>\r\n"
                      "</Summary>\r\n"
                      "<Header>\r\n"
                      "  <Sort field='ioRate' type='number' order='descending'/>\r\n"
                      "  <Threshold type='top' field='count' value='%d'/>\r\n"
                      "  <Threshold type='octave' field='ioRate'/>\r\n"
                      "  <Data name=\"disk\" class=\"string\"/>\r\n"
                      "  <Data name=\"file\" class=\"string\"/>\r\n"
                      "  <Data name=\"readRate\" class=\"number\" format='#,##0.0'/>\r\n"
                      "  <Data name=\"readSize\" class=\"number\"/>\r\n"
                      "  <Data name=\"writeRate\" class=\"number\" format='#,##0.0'/>\r\n"
                      "  <Data name=\"writeSize\" class=\"number\"/>\r\n"
                      "  <Header>\r\n"
                      "    <Sort field='ioRate' type='number' order='descending'/>\r\n"
                      "    <Data name=\"image\" class=\"string\"/>\r\n"
                      "    <Data name=\"pid\" class=\"string\"/>\r\n"
                      "    <Data name=\"readRate\" class=\"number\" format='#,##0.0'/>\r\n"
                      "    <Data name=\"readSize\" class=\"number\"/>\r\n"
                      "    <Data name=\"writeRate\" class=\"number\" format='#,##0.0'/>\r\n"
                      "    <Data name=\"writeSize\" class=\"number\"/>\r\n"
                      "  </Header>\r\n"
                      "</Header>\r\n",
          10);
        v44 = 0;
        v12 = 0;
        while ( 1 )
        {
          v13 = (unsigned __int16 *)&Ext;
          v14 = *((_QWORD *)Base + 2 * v12);
          if ( *(_QWORD *)(v14 + 32) )
            v13 = *(unsigned __int16 **)(v14 + 32);
          if ( *(_QWORD *)(v14 + 40) )
            goto LABEL_30;
          ProcessHeap = GetProcessHeap();
          v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          *(_QWORD *)(v14 + 40) = v16;
          if ( v16 )
            break;
LABEL_75:
          v12 = v44 + 1;
          v44 = v12;
          if ( v12 >= v2 )
          {
            TracerptFPutws((wchar_t *)L"</Table>\r\n\r\n", a1);
            operator delete(Base, v40);
            return;
          }
        }
        StringCchCopyW(v16, 8u, L"Unknown");
LABEL_30:
        v17 = _wcsnicmp(*(const wchar_t **)(v14 + 40), L"\\Device\\", 8u);
        v18 = *(unsigned __int16 **)(v14 + 40);
        if ( !v17 )
        {
          for ( v18 += 8; *v18 != 92 && *v18; ++v18 )
            ;
        }
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        if ( v19 > 0x50 )
        {
          ReduceStringW(v47);
          v18 = v47;
        }
        TracerptFWPrintf(a1, (wchar_t *)L"\t<Item>\r\n\t\t<Data name='disk'>%d</Data>\r\n", *(unsigned int *)(v14 + 48));
        TracerptFPutws((wchar_t *)L"\t\t<Data name='file'>", a1);
        PrintWString(a1, 1, 0, v13);
        PrintWString(a1, 1, 0, v18);
        TracerptFPutws((wchar_t *)L"</Data>\r\n", a1);
        v20 = *(_DWORD *)(v14 + 60);
        if ( v20 )
          v21 = *(_DWORD *)(v14 + 68) / (unsigned int)v20;
        else
          v21 = 0;
        v22 = (double)v20;
        if ( v11 == 0.0 )
          v23 = 0.0;
        else
          v23 = v22 / v11;
        v24 = *(_DWORD *)(v14 + 52);
        if ( v24 )
          v25 = *(_DWORD *)(v14 + 64) / (unsigned int)v24;
        else
          v25 = 0;
        v26 = (double)v24;
        if ( v11 == 0.0 )
          v27 = 0.0;
        else
          v27 = v26 / v11;
        if ( v11 == 0.0 )
          v28 = 0.0;
        else
          v28 = v26 / v11 + v22 / v11;
        LODWORD(v42) = v21;
        LODWORD(v41) = v25;
        TracerptFWPrintf(
          a1,
          (wchar_t *)L"\t\t<Data name='ioRate' visible='false'>%1.3f</Data>\r\n"
                      "\t\t<Data name='readRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='readSize'>%d</Data>\r\n"
                      "\t\t<Data name='writeRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='writeSize'>%d</Data>\r\n",
          v28,
          v27,
          v41,
          v23,
          v42);
        v29 = *(_DWORD **)v14;
        v30 = *(_DWORD **)(v14 + 8);
        while ( v29 != v30 )
        {
          v31 = v29[3];
          v32 = v29[2];
          if ( *((_QWORD *)v29 + 1) )
          {
            if ( v31 )
              v33 = v29[6] / (unsigned int)v31;
            else
              v33 = 0;
            v34 = (double)v31;
            if ( v11 == 0.0 )
              v35 = 0.0;
            else
              v35 = v34 / v11;
            if ( v32 )
              v36 = v29[5] / (unsigned int)v32;
            else
              v36 = 0;
            v37 = (double)v32;
            if ( v11 == 0.0 )
              v38 = 0.0;
            else
              v38 = v37 / v11;
            if ( v11 == 0.0 )
              v39 = 0.0;
            else
              v39 = v37 / v11 + v34 / v11;
            LODWORD(v43) = v33;
            LODWORD(v42) = v36;
            TracerptFWPrintf(
              a1,
              (wchar_t *)L"\t\t<Item>\r\n"
                          "\t\t\t<Data name='image'>%s</Data>\r\n"
                          "\t\t\t<Data name='pid'>%d</Data>\r\n"
                          "\t\t\t<Data name='ioRate' visible='false'>%1.3f</Data>\r\n"
                          "\t\t\t<Data name='readRate'>%1.3f</Data>\r\n"
                          "\t\t\t<Data name='readSize'>%d</Data>\r\n"
                          "\t\t\t<Data name='writeRate'>%1.3f</Data>\r\n"
                          "\t\t\t<Data name='writeSize'>%d</Data>\r\n"
                          "\t\t</Item>\r\n",
              *(_QWORD *)(*(_QWORD *)v29 + 104LL),
              *(unsigned int *)(*(_QWORD *)v29 + 120LL),
              v39,
              v38,
              v42,
              v35,
              v43);
          }
          v29 += 8;
        }
        TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
        goto LABEL_75;
      }
    }
  }
}

```

## disassembly

```asm
0x140021ff4  mov     rax, rsp
0x140021ff7  push    rbp
0x140021ff8  push    rbx
0x140021ff9  push    rsi
0x140021ffa  push    rdi
0x140021ffb  push    r12
0x140021ffd  push    r13
0x140021fff  push    r14
0x140022001  push    r15
0x140022003  lea     rbp, [rsp-68h]
0x140022008  sub     rsp, 168h
0x14002200f  movaps  xmmword ptr [rax-58h], xmm6
0x140022013  movaps  xmmword ptr [rax-68h], xmm7
0x140022017  mov     rax, cs:__security_cookie
0x14002201e  xor     rax, rsp
0x140022021  mov     [rbp+0A0h+var_70], rax
0x140022025  xor     r12d, r12d
0x140022028  mov     r15, rcx
0x14002202b  cmp     cs:?HotFileTableOn@@3EA, r12b; uchar HotFileTableOn
0x140022032  jz      loc_14002244C
0x140022038  lea     rax, qword_140082140
0x14002203f  cmp     cs:qword_140082140, rax
0x140022046  jz      loc_14002244C
0x14002204c  lea     rax, qword_140082130
0x140022053  cmp     cs:qword_140082130, rax
0x14002205a  jz      loc_14002244C
0x140022060  mov     r8, cs:Block
0x140022067  mov     esi, r12d
0x14002206a  mov     rax, [r8]
0x14002206d  cmp     rax, r8
0x140022070  jz      short loc_140022088
0x140022072  mov     ecx, [rax+5Ch]
0x140022075  lea     rdx, [rsi+1]
0x140022079  or      ecx, [rax+54h]
0x14002207c  mov     rax, [rax]
0x14002207f  cmovz   rdx, rsi
0x140022083  mov     rsi, rdx
0x140022086  jmp     short loc_14002206D
0x140022088  mov     rax, cs:qword_140082158
0x14002208f  or      r13, 0FFFFFFFFFFFFFFFFh
0x140022093  mov     rax, [rax]
0x140022096  cmp     rax, r13
0x140022099  jz      short loc_1400220AE
0x14002209b  mov     ecx, [rax+44h]
0x14002209e  lea     rdx, [rsi+1]
0x1400220a2  or      ecx, [rax+3Ch]
0x1400220a5  cmovz   rdx, rsi
0x1400220a9  mov     rsi, rdx
0x1400220ac  jmp     short loc_140022093
0x1400220ae  test    rsi, rsi
0x1400220b1  jz      loc_14002244C
0x1400220b7  mov     rbx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x1400220be  mov     edi, 10h
0x1400220c3  sub     rbx, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x1400220ca  mov     eax, edi
0x1400220cc  mul     rsi
0x1400220cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400220d6  cmovb   rax, r13
0x1400220da  mov     rcx, rax; unsigned __int64
0x1400220dd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400220e2  mov     [rsp+1A0h+Base], rax
0x1400220e7  test    rax, rax
0x1400220ea  jz      loc_14002244C
0x1400220f0  xorps   xmm6, xmm6
0x1400220f3  test    rbx, rbx
0x1400220f6  js      short loc_1400220FF
0x1400220f8  cvtsi2sd xmm6, rbx
0x1400220fd  jmp     short loc_140022114
0x1400220ff  mov     rax, rbx
0x140022102  and     ebx, 1
0x140022105  shr     rax, 1
0x140022108  or      rax, rbx
0x14002210b  cvtsi2sd xmm6, rax
0x140022110  addsd   xmm6, xmm6
0x140022114  divsd   xmm6, cs:__real@416312d000000000
0x14002211c  lea     rax, [rsp+1A0h+Base]
0x140022121  mov     [rsp+1A0h+var_150], r12
0x140022126  mov     [rsp+1A0h+var_138], rax
0x14002212b  lea     rcx, [rsp+1A0h+var_138]
0x140022130  lea     rax, [rsp+1A0h+var_150]
0x140022135  mov     [rsp+1A0h+var_130], rax
0x14002213a  call    ForEachHotFile__lambda_6c0bdc72014db60bac9be87f94169d1e___; ForEachHotFile__lambda_6c0bdc72014db60bac9be87f94169d1e_
0x14002213f  mov     rcx, [rsp+1A0h+Base]; Base
0x140022144  lea     r9, CompareFileRecord; CompareFunction
0x14002214b  mov     r8, rdi; SizeOfElements
0x14002214e  mov     rdx, rsi; NumOfElements
0x140022151  call    cs:__imp_qsort
0x140022157  mov     eax, 14h
0x14002215c  lea     rdx, aTableNameHotfi; "<Table name='hotFile' level='1' key='10"...
0x140022163  cmp     rsi, rax
0x140022166  mov     rcx, r15; struct _iobuf *
0x140022169  cmova   rsi, rax
0x14002216d  lea     r8d, [rax-0Ah]
0x140022171  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140022176  mov     [rsp+1A0h+var_150], r12
0x14002217b  test    rsi, rsi
0x14002217e  jz      loc_140022433
0x140022184  mov     rcx, r12
0x140022187  xorps   xmm7, xmm7
0x14002218a  mov     rax, [rsp+1A0h+Base]
0x14002218f  lea     r14, Ext
0x140022196  add     rcx, rcx
0x140022199  mov     rdi, [rax+rcx*8]
0x14002219d  cmp     [rdi+20h], r12
0x1400221a1  cmovnz  r14, [rdi+20h]
0x1400221a6  cmp     [rdi+28h], r12
0x1400221aa  jnz     short loc_1400221E5
0x1400221ac  call    cs:__imp_GetProcessHeap
0x1400221b2  mov     edx, 8; dwFlags
0x1400221b7  mov     rcx, rax; hHeap
0x1400221ba  lea     r8d, [rdx+8]; dwBytes
0x1400221be  call    cs:__imp_HeapAlloc
0x1400221c4  mov     [rdi+28h], rax
0x1400221c8  test    rax, rax
0x1400221cb  jz      loc_14002241D
0x1400221d1  lea     r8, aUnknown_2; "Unknown"
0x1400221d8  mov     edx, 8; unsigned __int64
0x1400221dd  mov     rcx, rax; unsigned __int16 *
0x1400221e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400221e5  mov     rcx, [rdi+28h]; String1
0x1400221e9  lea     rdx, aDevice; "\\Device\\"
0x1400221f0  mov     r8d, 8; MaxCount
0x1400221f6  call    cs:__imp__wcsnicmp
0x1400221fc  mov     rbx, [rdi+28h]
0x140022200  test    eax, eax
0x140022202  jnz     short loc_14002221C
0x140022204  add     rbx, 10h
0x140022208  jmp     short loc_140022213
0x14002220a  test    ax, ax
0x14002220d  jz      short loc_14002221C
0x14002220f  add     rbx, 2
0x140022213  movzx   eax, word ptr [rbx]
0x140022216  cmp     ax, 5Ch ; '\'
0x14002221a  jnz     short loc_14002220A
0x14002221c  mov     rax, r13
0x14002221f  inc     rax
0x140022222  cmp     [rbx+rax*2], r12w
0x140022227  jnz     short loc_14002221F
0x140022229  cmp     rax, 50h ; 'P'
0x14002222d  jbe     short loc_14002223F
0x14002222f  mov     r8, rbx
0x140022232  lea     rcx, [rbp+0A0h+var_120]; unsigned __int16 *
0x140022236  call    ReduceStringW
0x14002223b  lea     rbx, [rbp+0A0h+var_120]
0x14002223f  mov     r8d, [rdi+30h]
0x140022243  lea     rdx, aItemDataNameDi_0; "\t<Item>\r\n\t\t<Data name='disk'>%d</D"...
0x14002224a  mov     rcx, r15; struct _iobuf *
0x14002224d  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140022252  mov     rdx, r15; struct _iobuf *
0x140022255  lea     rcx, aDataNameFile; "\t\t<Data name='file'>"
0x14002225c  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140022261  mov     r9, r14; unsigned __int16 *
0x140022264  xor     r8d, r8d; unsigned __int8
0x140022267  mov     dl, 1; unsigned __int8
0x140022269  mov     rcx, r15; struct _iobuf *
0x14002226c  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140022271  mov     r9, rbx; unsigned __int16 *
0x140022274  xor     r8d, r8d; unsigned __int8
0x140022277  mov     dl, 1; unsigned __int8
0x140022279  mov     rcx, r15; struct _iobuf *
0x14002227c  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140022281  mov     rdx, r15; struct _iobuf *
0x140022284  lea     rcx, aData; "</Data>\r\n"
0x14002228b  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140022290  mov     ecx, [rdi+3Ch]
0x140022293  test    ecx, ecx
0x140022295  jz      short loc_1400222A3
0x140022297  mov     eax, [rdi+44h]
0x14002229a  xor     edx, edx
0x14002229c  div     ecx
0x14002229e  mov     r9d, eax
0x1400222a1  jmp     short loc_1400222A6
0x1400222a3  mov     r9d, r12d
0x1400222a6  ucomisd xmm6, xmm7
0x1400222aa  xorps   xmm1, xmm1
0x1400222ad  cvtsi2sd xmm1, rcx
0x1400222b2  jp      short loc_1400222BB
0x1400222b4  jnz     short loc_1400222BB
0x1400222b6  movaps  xmm0, xmm7
0x1400222b9  jmp     short loc_1400222C2
0x1400222bb  movaps  xmm0, xmm1
0x1400222be  divsd   xmm0, xmm6
0x1400222c2  mov     ecx, [rdi+34h]
0x1400222c5  test    ecx, ecx
0x1400222c7  jz      short loc_1400222D5
0x1400222c9  mov     eax, [rdi+40h]
0x1400222cc  xor     edx, edx
0x1400222ce  div     ecx
0x1400222d0  mov     r8d, eax
0x1400222d3  jmp     short loc_1400222D8
0x1400222d5  mov     r8d, r12d
0x1400222d8  ucomisd xmm6, xmm7
0x1400222dc  xorps   xmm2, xmm2
0x1400222df  cvtsi2sd xmm2, rcx
0x1400222e4  jp      short loc_1400222ED
0x1400222e6  jnz     short loc_1400222ED
0x1400222e8  movaps  xmm3, xmm7
0x1400222eb  jmp     short loc_1400222F4
0x1400222ed  movaps  xmm3, xmm2
0x1400222f0  divsd   xmm3, xmm6
0x1400222f4  ucomisd xmm6, xmm7
0x1400222f8  jp      short loc_140022301
0x1400222fa  jnz     short loc_140022301
0x1400222fc  movaps  xmm2, xmm7
0x1400222ff  jmp     short loc_14002230D
0x140022301  divsd   xmm2, xmm6
0x140022305  divsd   xmm1, xmm6
0x140022309  addsd   xmm2, xmm1
0x14002230d  mov     dword ptr [rsp+1A0h+var_170], r9d
0x140022312  lea     rdx, aDataNameIorate; "\t\t<Data name='ioRate' visible='false'"...
0x140022319  movsd   [rsp+1A0h+var_178], xmm0
0x14002231f  movq    r9, xmm3
0x140022324  mov     dword ptr [rsp+1A0h+var_180], r8d
0x140022329  mov     rcx, r15; struct _iobuf *
0x14002232c  movq    r8, xmm2
0x140022331  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140022336  mov     rbx, [rdi]
0x140022339  mov     rdi, [rdi+8]
0x14002233d  cmp     rbx, rdi
0x140022340  jz      loc_14002240E
0x140022346  mov     ecx, [rbx+0Ch]
0x140022349  mov     r8d, [rbx+8]
0x14002234d  mov     eax, ecx
0x14002234f  or      eax, r8d
0x140022352  jz      loc_140022405
0x140022358  test    ecx, ecx
0x14002235a  jz      short loc_140022368
0x14002235c  mov     eax, [rbx+18h]
0x14002235f  xor     edx, edx
0x140022361  div     ecx
0x140022363  mov     r9d, eax
0x140022366  jmp     short loc_14002236B
0x140022368  mov     r9d, r12d
0x14002236b  ucomisd xmm6, xmm7
0x14002236f  xorps   xmm3, xmm3
0x140022372  cvtsi2sd xmm3, rcx
0x140022377  jp      short loc_140022380
0x140022379  jnz     short loc_140022380
0x14002237b  movaps  xmm2, xmm7
0x14002237e  jmp     short loc_140022387
0x140022380  movaps  xmm2, xmm3
0x140022383  divsd   xmm2, xmm6
0x140022387  test    r8d, r8d
0x14002238a  jz      short loc_140022398
0x14002238c  mov     eax, [rbx+14h]
0x14002238f  xor     edx, edx
0x140022391  div     r8d
0x140022394  mov     ecx, eax
0x140022396  jmp     short loc_14002239B
0x140022398  mov     ecx, r12d
0x14002239b  ucomisd xmm6, xmm7
0x14002239f  xorps   xmm0, xmm0
0x1400223a2  cvtsi2sd xmm0, r8
0x1400223a7  jp      short loc_1400223B0
0x1400223a9  jnz     short loc_1400223B0
0x1400223ab  movaps  xmm1, xmm7
0x1400223ae  jmp     short loc_1400223B7
0x1400223b0  movaps  xmm1, xmm0
0x1400223b3  divsd   xmm1, xmm6
0x1400223b7  ucomisd xmm6, xmm7
0x1400223bb  jp      short loc_1400223C4
0x1400223bd  jnz     short loc_1400223C4
0x1400223bf  movaps  xmm0, xmm7
0x1400223c2  jmp     short loc_1400223D0
0x1400223c4  divsd   xmm0, xmm6
0x1400223c8  divsd   xmm3, xmm6
0x1400223cc  addsd   xmm0, xmm3
0x1400223d0  mov     r8, [rbx]
0x1400223d3  lea     rdx, aItemDataNameIm; "\t\t<Item>\r\n\t\t\t<Data name='image'>"...
0x1400223da  mov     [rsp+1A0h+var_160], r9d
0x1400223df  movsd   [rsp+1A0h+var_168], xmm2
0x1400223e5  mov     dword ptr [rsp+1A0h+var_170], ecx
0x1400223e9  mov     rcx, r15; struct _iobuf *
0x1400223ec  mov     r9d, [r8+78h]
0x1400223f0  mov     r8, [r8+68h]
0x1400223f4  movsd   [rsp+1A0h+var_178], xmm1
0x1400223fa  movsd   [rsp+1A0h+var_180], xmm0
0x140022400  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140022405  add     rbx, 20h ; ' '
0x140022409  jmp     loc_14002233D
0x14002240e  mov     rdx, r15; struct _iobuf *
0x140022411  lea     rcx, aItem_1; "\t</Item>\r\n"
0x140022418  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002241d  mov     rcx, [rsp+1A0h+var_150]
0x140022422  inc     rcx
0x140022425  mov     [rsp+1A0h+var_150], rcx
0x14002242a  cmp     rcx, rsi
0x14002242d  jb      loc_14002218A
0x140022433  mov     rdx, r15; struct _iobuf *
0x140022436  lea     rcx, aTable; "</Table>\r\n\r\n"
0x14002243d  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140022442  mov     rcx, [rsp+1A0h+Base]; void *
0x140022447  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002244c  mov     rcx, [rbp+0A0h+var_70]
0x140022450  xor     rcx, rsp; StackCookie
0x140022453  call    __security_check_cookie
0x140022458  lea     r11, [rsp+1A0h+var_38]
0x140022460  movaps  xmm6, xmmword ptr [r11-18h]
0x140022465  movaps  xmm7, xmmword ptr [r11-28h]
0x14002246a  mov     rsp, r11
  ... truncated ...
```
