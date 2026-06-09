# EventXmlDump::DumpData(_iobuf *,EventDumpWorkspace *,int)

- ea: `0x14000ffcc`
- end: `0x1400104ea`
- name: `?DumpData@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@H@Z`
- size: `1310`
- prototype: `__int64 __fastcall(EventXmlDump *this, struct _iobuf *, struct EventDumpWorkspace *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000faa4`

## callees

- `0x14000d738`
- `0x14000d818`
- `0x14000d96c`
- `0x14000e088`
- `0x14000e1c4`
- `0x14000ffcc`
- `0x140013a04`
- `0x14001601c`
- `0x1400161b0`
- `0x140016360`

## string_xrefs

- `0x140010052`: `		</ComplexData>\n`
- `0x1400103c7`: `		</ComplexData>\n`
- `0x14001040f`: `		</ComplexData>\n`
- `0x14001008d`: `		<ComplexData Name="`

## pseudocode

```c
__int64 __fastcall EventXmlDump::DumpData(EventXmlDump *this, struct _iobuf *a2, struct EventDumpWorkspace *a3, int a4)
{
  __int64 v7; // r15
  unsigned int v8; // esi
  unsigned int v9; // r14d
  int v10; // eax
  const char *v11; // rcx
  unsigned int v12; // ecx
  int v13; // edx
  struct _EVENT_DUMP_DATA *NextInFrameDescent; // rdi
  unsigned __int16 *v16; // r13
  int v17; // r12d
  int v18; // r14d
  __int64 v19; // r15
  __int64 v20; // rcx
  struct _EVENT_DUMP_DATA *NextSameLevel; // rax
  unsigned int i; // edi
  __int64 v24; // [rsp+20h] [rbp-30h] BYREF
  int v25; // [rsp+28h] [rbp-28h]
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  int v27; // [rsp+40h] [rbp-10h]

  TracerptFPutws(L"\t<EventData>\r\n", a2);
  EventDumpIterator::EventDumpIterator((EventDumpIterator *)&v24, a3);
  v7 = v24;
  v8 = 0;
  while ( v7 )
  {
    NextInFrameDescent = EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)&v24, 0);
    if ( !NextInFrameDescent )
      goto LABEL_63;
    v7 = v24;
    while ( 1 )
    {
      v9 = 0;
      if ( v8 <= (v25 & (unsigned int)-(v7 != 0)) )
        break;
      if ( --v8 )
      {
        do
        {
          TracerptFPuts("\t", a2);
          ++v9;
        }
        while ( v9 < v8 );
      }
      TracerptFPuts("\t\t</ComplexData>\r\n", a2);
    }
    if ( v8 )
    {
      do
      {
        TracerptFPuts("\t", a2);
        ++v9;
      }
      while ( v9 < v8 );
    }
    v10 = *((_DWORD *)NextInFrameDescent + 15);
    if ( (v10 & 0x10) == 0 )
    {
      if ( (v10 & 8) != 0 )
      {
        TracerptFPuts("\t\t<ComplexData Name=\"", a2);
        PrintWString(a2, 1u, 0, *(unsigned __int16 **)NextInFrameDescent);
        TracerptFPuts("\">\r\n", a2);
        ++v8;
      }
      else
      {
        if ( (v10 & 4) != 0 )
        {
          TracerptFPuts("\t\t<Data Name=\"", a2);
          PrintWString(a2, 1u, 0, *(unsigned __int16 **)NextInFrameDescent);
          v11 = "\"></Data>\r\n";
LABEL_29:
          TracerptFPuts(v11, a2);
          goto LABEL_30;
        }
        if ( a4 && (v10 & 0x80u) != 0 )
        {
          v16 = *(unsigned __int16 **)NextInFrameDescent;
          v17 = 0;
          v18 = 0;
          EventDumpIterator::CopyFrom((EventDumpIterator *)&v26, (const struct EventDumpIterator *)&v24);
          v19 = v26;
          if ( !v26 || *(_DWORD *)(v26 + 8) == -1 )
            v20 = 0;
          else
            v20 = *(_QWORD *)v26 + 80LL * *(unsigned int *)(v26 + 8);
          if ( (*(_BYTE *)(v20 + 60) & 8) != 0 )
          {
            if ( v26 )
            {
              if ( v27 == 3 )
              {
                v17 = 1;
              }
              else if ( v27 == 2 && *((_WORD *)NextInFrameDescent + 32) )
              {
                v17 = 1;
                v18 = 1;
              }
            }
          }
          else if ( *(_WORD *)(v20 + 64) )
          {
            v17 = 1;
            if ( *((_WORD *)NextInFrameDescent + 32) )
              v18 = 1;
          }
          TracerptFPuts("\t\t<Data Name=\"", a2);
          PrintWString(a2, 1u, 0, v16);
          TracerptFPuts("\" Type=\"", a2);
          PrintWString(a2, 1u, 0, L"win:ErrorLessData");
          TracerptFPuts("\">", a2);
          if ( *((_QWORD *)a3 + 41) )
            TracerptFPrintf(a2, "0x%ws");
          TracerptFPuts("</Data>\r\n", a2);
          if ( v17 )
          {
            if ( v18 )
              NextSameLevel = v19 ? EventDumpIterator::GetNextInFrameDescent((EventDumpIterator *)&v26, 0) : 0LL;
            else
              NextSameLevel = EventDumpIterator::GetNextSameLevel((EventDumpIterator *)&v26);
            if ( NextSameLevel )
            {
              do
              {
                if ( v8 )
                  TracerptFPuts("\t", a2);
                TracerptFPuts("\t\t<Data Name=\"", a2);
                PrintWString(a2, 1u, 0, v16);
                TracerptFPuts("\" Type=\"", a2);
                PrintWString(a2, 1u, 0, L"win:ErrorLessData");
                TracerptFPuts("\">", a2);
                TracerptFPuts("</Data>\r\n", a2);
              }
              while ( EventDumpIterator::GetNextSameLevel((EventDumpIterator *)&v26) );
            }
          }
          if ( v8 )
            TracerptFPuts("\t\t</ComplexData>\r\n", a2);
          EventDumpIterator::~EventDumpIterator((EventDumpIterator *)&v26);
LABEL_63:
          v7 = v24;
          break;
        }
        if ( *((_WORD *)NextInFrameDescent + 28) == 28 )
        {
          v12 = 28;
        }
        else
        {
          TracerptFPuts("\t\t<Data Name=\"", a2);
          PrintWString(a2, 1u, 0, *(unsigned __int16 **)NextInFrameDescent);
          TracerptFPuts("\">", a2);
          v12 = *((unsigned __int16 *)NextInFrameDescent + 28);
        }
        if ( *(_WORD *)(*((_QWORD *)NextInFrameDescent + 6) + 8LL) == 8
          && ((unsigned __int16)v12 > 0x1Fu || (v13 = -394002432, !_bittest(&v13, v12))) )
        {
          TracerptFPrintf(a2, "%8ws", *((_QWORD *)NextInFrameDescent + 1));
        }
        else
        {
          PrintWString(a2, 1u, (_WORD)v12 == 28, *((unsigned __int16 **)NextInFrameDescent + 1));
        }
        if ( *((_WORD *)NextInFrameDescent + 28) != 28 )
        {
          v11 = "</Data>\r\n";
          goto LABEL_29;
        }
LABEL_30:
        if ( (*((_DWORD *)NextInFrameDescent + 15) & 0x200) != 0 )
          break;
      }
    }
  }
  while ( v8 > (v25 & (unsigned int)-(v7 != 0)) )
  {
    if ( --v8 )
    {
      for ( i = 0; i < v8; ++i )
        TracerptFPuts("\t", a2);
    }
    TracerptFPuts("\t\t</ComplexData>\r\n", a2);
  }
  if ( a4 && *((_QWORD *)a3 + 42) )
  {
    TracerptFPuts("\t\t<Data Name=\"", a2);
    PrintWString(a2, 1u, 0, L"win:ExtraPayload");
    TracerptFPuts("\" Type=\"", a2);
    PrintWString(a2, 1u, 0, L"win:ErrorMoreData");
    TracerptFPuts("\">", a2);
    TracerptFPrintf(a2, "0x%ws", *((_QWORD *)a3 + 42));
    TracerptFPuts("</Data>\r\n", a2);
  }
  TracerptFPutws(L"\t</EventData>\r\n", a2);
  EventDumpIterator::~EventDumpIterator((EventDumpIterator *)&v24);
  return 0;
}

```

## disassembly

```asm
0x14000ffcc  mov     [rsp-38h+arg_0], rbx
0x14000ffd1  mov     [rsp-38h+arg_18], r9d
0x14000ffd6  mov     [rsp-38h+arg_10], r8
0x14000ffdb  push    rbp
0x14000ffdc  push    rsi
0x14000ffdd  push    rdi
0x14000ffde  push    r12
0x14000ffe0  push    r13
0x14000ffe2  push    r14
0x14000ffe4  push    r15
0x14000ffe6  mov     rbp, rsp
0x14000ffe9  sub     rsp, 50h
0x14000ffed  lea     rcx, aEventdata_0; "\t<EventData>\r\n"
0x14000fff4  mov     r12d, r9d
0x14000fff7  mov     rdi, r8
0x14000fffa  mov     rbx, rdx
0x14000fffd  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140010002  mov     rdx, rdi; struct EventDumpWorkspace *
0x140010005  lea     rcx, [rbp+var_30]; this
0x140010009  call    ??0EventDumpIterator@@QEAA@PEAVEventDumpWorkspace@@@Z; EventDumpIterator::EventDumpIterator(EventDumpWorkspace *)
0x14001000e  mov     r15, [rbp+var_30]
0x140010012  xor     r13d, r13d
0x140010015  mov     esi, r13d
0x140010018  jmp     loc_1400101CD
0x14001001d  mov     r15, [rbp+var_30]
0x140010021  mov     rax, r15
0x140010024  mov     r14d, r13d
0x140010027  neg     rax
0x14001002a  sbb     ecx, ecx
0x14001002c  and     ecx, [rbp+var_28]
0x14001002f  cmp     esi, ecx
0x140010031  jbe     short loc_140010060
0x140010033  add     esi, 0FFFFFFFFh
0x140010036  jz      short loc_14001004F
0x140010038  mov     rdx, rbx; struct _iobuf *
0x14001003b  lea     rcx, asc_14004569C; "\t"
0x140010042  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010047  inc     r14d
0x14001004a  cmp     r14d, esi
0x14001004d  jb      short loc_140010038
0x14001004f  mov     rdx, rbx; struct _iobuf *
0x140010052  lea     rcx, aComplexdata; "\t\t</ComplexData>\r\n"
0x140010059  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001005e  jmp     short loc_140010021
0x140010060  test    esi, esi
0x140010062  jz      short loc_14001007B
0x140010064  mov     rdx, rbx; struct _iobuf *
0x140010067  lea     rcx, asc_14004569C; "\t"
0x14001006e  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010073  inc     r14d
0x140010076  cmp     r14d, esi
0x140010079  jb      short loc_140010064
0x14001007b  mov     eax, [rdi+3Ch]
0x14001007e  test    al, 10h
0x140010080  jnz     loc_1400101CD
0x140010086  test    al, 8
0x140010088  jz      short loc_1400100C5
0x14001008a  mov     rdx, rbx; struct _iobuf *
0x14001008d  lea     rcx, aComplexdataNam; "\t\t<ComplexData Name=\""
0x140010094  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010099  mov     r9, [rdi]; unsigned __int16 *
0x14001009c  xor     r8d, r8d; unsigned __int8
0x14001009f  mov     rcx, rbx; struct _iobuf *
0x1400100a2  lea     r14d, [r8+1]
0x1400100a6  mov     dl, r14b; unsigned __int8
0x1400100a9  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400100ae  mov     rdx, rbx; struct _iobuf *
0x1400100b1  lea     rcx, asc_1400456F0; "\">\r\n"
0x1400100b8  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400100bd  add     esi, r14d
0x1400100c0  jmp     loc_1400101CD
0x1400100c5  test    al, 4
0x1400100c7  jz      short loc_1400100F4
0x1400100c9  mov     rdx, rbx; struct _iobuf *
0x1400100cc  lea     rcx, aDataName; "\t\t<Data Name=\""
0x1400100d3  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400100d8  mov     r9, [rdi]; unsigned __int16 *
0x1400100db  xor     r8d, r8d; unsigned __int8
0x1400100de  mov     dl, 1; unsigned __int8
0x1400100e0  mov     rcx, rbx; struct _iobuf *
0x1400100e3  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400100e8  lea     rcx, aData_2; "\"></Data>\r\n"
0x1400100ef  jmp     loc_1400101B8
0x1400100f4  test    r12d, r12d
0x1400100f7  jz      short loc_140010101
0x1400100f9  test    al, al
0x1400100fb  js      loc_1400101F2
0x140010101  mov     r8d, 1Ch
0x140010107  cmp     [rdi+38h], r8w
0x14001010c  jz      short loc_14001014B
0x14001010e  mov     rdx, rbx; struct _iobuf *
0x140010111  lea     rcx, aDataName; "\t\t<Data Name=\""
0x140010118  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001011d  mov     r9, [rdi]; unsigned __int16 *
0x140010120  xor     r8d, r8d; unsigned __int8
0x140010123  mov     rcx, rbx; struct _iobuf *
0x140010126  lea     r14d, [r8+1]
0x14001012a  mov     dl, r14b; unsigned __int8
0x14001012d  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010132  mov     rdx, rbx; struct _iobuf *
0x140010135  lea     rcx, asc_14004574C; "\">"
0x14001013c  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010141  movzx   ecx, word ptr [rdi+38h]
0x140010145  lea     r8d, [r14+1Bh]
0x140010149  jmp     short loc_140010154
0x14001014b  mov     ecx, r8d
0x14001014e  mov     r14d, 1
0x140010154  mov     rax, [rdi+30h]
0x140010158  cmp     word ptr [rax+8], 8
0x14001015d  jnz     short loc_140010174
0x14001015f  cmp     cx, 1Fh
0x140010163  ja      short loc_14001016F
0x140010165  mov     edx, 0E8840000h
0x14001016a  bt      edx, ecx
0x14001016d  jb      short loc_140010174
0x14001016f  mov     eax, r14d
0x140010172  jmp     short loc_140010177
0x140010174  mov     eax, r13d
0x140010177  mov     r9, [rdi+8]; unsigned __int16 *
0x14001017b  test    eax, eax
0x14001017d  jz      short loc_140010193
0x14001017f  mov     r8, r9
0x140010182  lea     rdx, a8ws; "%8ws"
0x140010189  mov     rcx, rbx; struct _iobuf *
0x14001018c  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010191  jmp     short loc_1400101A6
0x140010193  cmp     cx, r8w
0x140010197  mov     dl, r14b; unsigned __int8
0x14001019a  mov     rcx, rbx; struct _iobuf *
0x14001019d  setz    r8b; unsigned __int8
0x1400101a1  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400101a6  mov     eax, 1Ch
0x1400101ab  cmp     [rdi+38h], ax
0x1400101af  jz      short loc_1400101C0
0x1400101b1  lea     rcx, aData_4; "</Data>\r\n"
0x1400101b8  mov     rdx, rbx; struct _iobuf *
0x1400101bb  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400101c0  test    dword ptr [rdi+3Ch], 200h
0x1400101c7  jnz     loc_1400103E0
0x1400101cd  test    r15, r15
0x1400101d0  jz      loc_1400103E0
0x1400101d6  xor     edx, edx; unsigned int
0x1400101d8  lea     rcx, [rbp+var_30]; this
0x1400101dc  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x1400101e1  mov     rdi, rax
0x1400101e4  test    rax, rax
0x1400101e7  jnz     loc_14001001D
0x1400101ed  jmp     loc_1400103DC
0x1400101f2  mov     r13, [rdi]
0x1400101f5  lea     rdx, [rbp+var_30]; struct EventDumpIterator *
0x1400101f9  lea     rcx, [rbp+var_18]; this
0x1400101fd  xor     r12d, r12d
0x140010200  xor     r14d, r14d
0x140010203  call    ?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z; EventDumpIterator::CopyFrom(EventDumpIterator const &)
0x140010208  mov     r15, [rbp+var_18]
0x14001020c  xor     eax, eax
0x14001020e  test    r15, r15
0x140010211  jz      short loc_14001022D
0x140010213  cmp     dword ptr [r15+8], 0FFFFFFFFh
0x140010218  jz      short loc_14001022D
0x14001021a  mov     eax, [r15+8]
0x14001021e  lea     rcx, [rax+rax*4]
0x140010222  shl     rcx, 4
0x140010226  add     rcx, [r15]
0x140010229  xor     eax, eax
0x14001022b  jmp     short loc_140010230
0x14001022d  mov     rcx, rax
0x140010230  test    byte ptr [rcx+3Ch], 8
0x140010234  jz      short loc_140010262
0x140010236  test    r15, r15
0x140010239  jz      short loc_140010278
0x14001023b  cmp     [rbp+var_10], 3
0x14001023f  jnz     short loc_140010249
0x140010241  mov     r12d, 1
0x140010247  jmp     short loc_140010278
0x140010249  cmp     [rbp+var_10], 2
0x14001024d  jnz     short loc_140010278
0x14001024f  cmp     [rdi+40h], ax
0x140010253  jbe     short loc_140010278
0x140010255  mov     eax, 1
0x14001025a  mov     r12d, eax
0x14001025d  mov     r14d, eax
0x140010260  jmp     short loc_140010278
0x140010262  cmp     [rcx+40h], ax
0x140010266  jbe     short loc_140010278
0x140010268  cmp     [rdi+40h], ax
0x14001026c  mov     ecx, 1
0x140010271  mov     r12d, ecx
0x140010274  cmova   r14d, ecx
0x140010278  mov     rdx, rbx; struct _iobuf *
0x14001027b  lea     rcx, aDataName; "\t\t<Data Name=\""
0x140010282  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010287  mov     r9, r13; unsigned __int16 *
0x14001028a  xor     r8d, r8d; unsigned __int8
0x14001028d  mov     dl, 1; unsigned __int8
0x14001028f  mov     rcx, rbx; struct _iobuf *
0x140010292  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010297  mov     rdx, rbx; struct _iobuf *
0x14001029a  lea     rcx, aType_0; "\" Type=\""
0x1400102a1  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400102a6  lea     r9, aWinErrorlessda; "win:ErrorLessData"
0x1400102ad  xor     r8d, r8d; unsigned __int8
0x1400102b0  mov     dl, 1; unsigned __int8
0x1400102b2  mov     rcx, rbx; struct _iobuf *
0x1400102b5  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400102ba  mov     rdx, rbx; struct _iobuf *
0x1400102bd  lea     rcx, asc_14004574C; "\">"
0x1400102c4  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400102c9  mov     rax, [rbp+arg_10]
0x1400102cd  xor     edi, edi
0x1400102cf  mov     r8, [rax+148h]
0x1400102d6  test    r8, r8
0x1400102d9  jz      short loc_1400102EA
0x1400102db  lea     rdx, a0xWs; "0x%ws"
0x1400102e2  mov     rcx, rbx; struct _iobuf *
0x1400102e5  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x1400102ea  mov     rdx, rbx; struct _iobuf *
0x1400102ed  lea     rcx, aData_4; "</Data>\r\n"
0x1400102f4  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400102f9  test    r12d, r12d
0x1400102fc  jz      loc_1400103BD
0x140010302  test    r14d, r14d
0x140010305  jz      short loc_14001031E
0x140010307  test    r15, r15
0x14001030a  jnz     short loc_140010311
0x14001030c  mov     rax, rdi
0x14001030f  jmp     short loc_140010327
0x140010311  xor     edx, edx; unsigned int
0x140010313  lea     rcx, [rbp+var_18]; this
0x140010317  call    ?GetNextInFrameDescent@EventDumpIterator@@AEAAPEAU_EVENT_DUMP_DATA@@K@Z; EventDumpIterator::GetNextInFrameDescent(ulong)
0x14001031c  jmp     short loc_140010327
0x14001031e  lea     rcx, [rbp+var_18]; this
0x140010322  call    ?GetNextSameLevel@EventDumpIterator@@QEAAPEAU_EVENT_DUMP_DATA@@XZ; EventDumpIterator::GetNextSameLevel(void)
0x140010327  test    rax, rax
0x14001032a  jz      loc_1400103BD
0x140010330  mov     r14d, 1
0x140010336  test    esi, esi
0x140010338  jz      short loc_140010349
0x14001033a  mov     rdx, rbx; struct _iobuf *
0x14001033d  lea     rcx, asc_14004569C; "\t"
0x140010344  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010349  mov     rdx, rbx; struct _iobuf *
0x14001034c  lea     rcx, aDataName; "\t\t<Data Name=\""
0x140010353  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010358  mov     r9, r13; unsigned __int16 *
0x14001035b  xor     r8d, r8d; unsigned __int8
0x14001035e  mov     dl, r14b; unsigned __int8
0x140010361  mov     rcx, rbx; struct _iobuf *
0x140010364  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010369  mov     rdx, rbx; struct _iobuf *
0x14001036c  lea     rcx, aType_0; "\" Type=\""
0x140010373  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010378  lea     r9, aWinErrorlessda; "win:ErrorLessData"
0x14001037f  xor     r8d, r8d; unsigned __int8
0x140010382  mov     dl, r14b; unsigned __int8
0x140010385  mov     rcx, rbx; struct _iobuf *
0x140010388  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001038d  mov     rdx, rbx; struct _iobuf *
0x140010390  lea     rcx, asc_14004574C; "\">"
0x140010397  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001039c  mov     rdx, rbx; struct _iobuf *
0x14001039f  lea     rcx, aData_4; "</Data>\r\n"
0x1400103a6  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400103ab  lea     rcx, [rbp+var_18]; this
0x1400103af  call    ?GetNextSameLevel@EventDumpIterator@@QEAAPEAU_EVENT_DUMP_DATA@@XZ; EventDumpIterator::GetNextSameLevel(void)
0x1400103b4  test    rax, rax
0x1400103b7  jnz     loc_140010336
0x1400103bd  xor     r13d, r13d
0x1400103c0  test    esi, esi
0x1400103c2  jz      short loc_1400103D3
0x1400103c4  mov     rdx, rbx; struct _iobuf *
0x1400103c7  lea     rcx, aComplexdata; "\t\t</ComplexData>\r\n"
0x1400103ce  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400103d3  lea     rcx, [rbp+var_18]; this
0x1400103d7  call    ??1EventDumpIterator@@QEAA@XZ; EventDumpIterator::~EventDumpIterator(void)
0x1400103dc  mov     r15, [rbp+var_30]
0x1400103e0  mov     rax, r15
0x1400103e3  neg     rax
0x1400103e6  sbb     ecx, ecx
0x1400103e8  and     ecx, [rbp+var_28]
0x1400103eb  cmp     esi, ecx
0x1400103ed  jbe     short loc_14001041D
0x1400103ef  add     esi, 0FFFFFFFFh
0x1400103f2  jz      short loc_14001040C
0x1400103f4  mov     edi, r13d
0x1400103f7  mov     rdx, rbx; struct _iobuf *
0x1400103fa  lea     rcx, asc_14004569C; "\t"
0x140010401  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010406  inc     edi
0x140010408  cmp     edi, esi
0x14001040a  jb      short loc_1400103F7
0x14001040c  mov     rdx, rbx; struct _iobuf *
0x14001040f  lea     rcx, aComplexdata; "\t\t</ComplexData>\r\n"
0x140010416  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001041b  jmp     short loc_1400103E0
0x14001041d  cmp     [rbp+arg_18], 0
0x140010421  jz      loc_1400104B8
0x140010427  mov     rdi, [rbp+arg_10]
0x14001042b  cmp     [rdi+150h], r13
0x140010432  jz      loc_1400104B8
  ... truncated ...
```
