# PrintServiceUsageTable

- ea: `0x140021184`
- end: `0x140021305`
- name: `PrintServiceUsageTable`
- size: `385`
- prototype: `void __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140016ae0`

## callees

- `0x140013a04`
- `0x140016360`
- `0x1400164c4`
- `0x140021184`

## string_xrefs

- `0x1400211f4`: `	<Item>\n		<Data name='serviceName'>%s</Data>\n`
- `0x140021286`: `		<Data name='status'>%s</Data>\n		<Data name='group'>%s</Data>\n		<Data name='cpu'>%.4f</Data>\n		<Data name='threads'>%d</Data>\n		<Data name='kernelCpuPer'>%.4f</Data>\n		<Data name='userCpuPer'>%.4f</Data>\n		<Data name='readRate'>%1.3f</Data>\n		<Data name='writeRate'>%1.3f</Data>\n		<Data name='pfRate'>%1.3f</Data>\n		<Data name='regRate'>%1.3f</Data>\n	</Item>\n`
- `0x1400211ae`: `<Table name='serviceStats' level='1' key='100' topic='service'>\n`
- `0x1400211cc`: `	<Header>\n		<Sort field='cpu' type='number' order='descending'/>\n		<Sort field='serviceName' type='text' order='ascending'/>\n		<Threshold type='top' field='count' value='3'/>\n		<Threshold type='octave' field='cpu'/>\n		<Data name='serviceName' class='string'/>\n		<Data name='pid' class='string'/>\n		<Data name='description' class='string'/>\n		<Data name='status' class='string'/>\n		<Data name='group' class='string'/>\n		<Data name='cpu' summary='total' class='number' format='#,##0`

## pseudocode

```c
void __fastcall PrintServiceUsageTable(struct _iobuf *a1)
{
  struct _PROCESS_RECORD *i; // rdi
  __int64 *j; // rsi
  const unsigned __int16 *v4; // r9
  const wchar_t *v5; // r8
  __int64 v6; // [rsp+28h] [rbp-70h]

  if ( qword_140082130 != (struct _PROCESS_RECORD *)&qword_140082130 )
  {
    TracerptFPutws((wchar_t *)L"<Table name='serviceStats' level='1' key='100' topic='service'>\r\n", a1);
    TracerptFPutws(
      (wchar_t *)L"<Summary key='1' find='total' field='cpu' exclude='pid' value='0' topic='process'>\r\n"
                  "  <Data name='totalCpu' format='#,##0'/>\r\n"
                  "</Summary>\r\n"
                  "<Summary key='1' find='top' field='groupCpu' exclude='pid' value='0' topic='process'>\r\n"
                  "  <Data name='process' label='topProcessGroup'/>\r\n"
                  "</Summary>\r\n",
      a1);
    TracerptFPutws(
      (wchar_t *)L"\t<Header>\r\n"
                  "\t\t<Sort field='cpu' type='number' order='descending'/>\r\n"
                  "\t\t<Sort field='serviceName' type='text' order='ascending'/>\r\n"
                  "\t\t<Threshold type='top' field='count' value='3'/>\r\n"
                  "\t\t<Threshold type='octave' field='cpu'/>\r\n"
                  "\t\t<Data name='serviceName' class='string'/>\r\n"
                  "\t\t<Data name='pid' class='string'/>\r\n"
                  "\t\t<Data name='description' class='string'/>\r\n"
                  "\t\t<Data name='status' class='string'/>\r\n"
                  "\t\t<Data name='group' class='string'/>\r\n"
                  "\t\t<Data name='cpu' summary='total' class='number' format='#,##0.0'/>\r\n"
                  "\t\t<Data name='threads' class='number' visible='false'/>\r\n"
                  "\t\t<Data name='kernelCpuPer' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t\t<Data name='userCpuPer' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t\t<Data name='readRate' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t\t<Data name='writeRate' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t\t<Data name='pfRate' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t\t<Data name='regRate' class='number' format='#,##0.0' visible='false'/>\r\n"
                  "\t</Header>\r\n",
      a1);
    for ( i = qword_140082130; i != (struct _PROCESS_RECORD *)&qword_140082130; i = *(struct _PROCESS_RECORD **)i )
    {
      for ( j = (__int64 *)*((_QWORD *)i + 4); j != (__int64 *)((char *)i + 32); j = (__int64 *)*j )
      {
        TracerptFWPrintf(a1, (wchar_t *)L"\t<Item>\r\n\t\t<Data name='serviceName'>%s</Data>\r\n", j[5]);
        if ( *((_DWORD *)i + 30) )
          TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='pid'>%d</Data>\r\n");
        else
          TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='pid'>-</Data>\r\n");
        TracerptFWPrintf(a1, (wchar_t *)L"\t\t<Data name='description'>");
        PrintWString(a1, 1, 0, (unsigned __int16 *)j[6]);
        TracerptFWPrintf(a1, (wchar_t *)L"</Data>\r\n");
        v4 = L"-";
        v5 = L"Stopped";
        if ( *((_QWORD *)i + 14) )
          v4 = (const unsigned __int16 *)*((_QWORD *)i + 14);
        if ( *((_DWORD *)i + 30) )
          v5 = L"Running";
        LODWORD(v6) = *((_DWORD *)j + 26);
        TracerptFWPrintf(
          a1,
          (wchar_t *)L"\t\t<Data name='status'>%s</Data>\r\n"
                      "\t\t<Data name='group'>%s</Data>\r\n"
                      "\t\t<Data name='cpu'>%.4f</Data>\r\n"
                      "\t\t<Data name='threads'>%d</Data>\r\n"
                      "\t\t<Data name='kernelCpuPer'>%.4f</Data>\r\n"
                      "\t\t<Data name='userCpuPer'>%.4f</Data>\r\n"
                      "\t\t<Data name='readRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='writeRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='pfRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='regRate'>%1.3f</Data>\r\n"
                      "\t</Item>\r\n",
          v5,
          v4,
          j[10],
          v6,
          *(_OWORD *)(j + 11),
          j[17],
          *((_OWORD *)j + 9),
          j[3]);
      }
    }
    TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
  }
}

```

## disassembly

```asm
0x140021184  push    rbx
0x140021186  push    rbp
0x140021187  push    rsi
0x140021188  push    rdi
0x140021189  push    r14
0x14002118b  sub     rsp, 70h
0x14002118f  lea     rbp, qword_140082130
0x140021196  movaps  [rsp+98h+var_38], xmm6
0x14002119b  cmp     cs:qword_140082130, rbp
0x1400211a2  mov     rbx, rcx
0x1400211a5  jz      loc_1400212F5
0x1400211ab  mov     rdx, rcx; struct _iobuf *
0x1400211ae  lea     rcx, aTableNameServi; "<Table name='serviceStats' level='1' ke"...
0x1400211b5  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400211ba  mov     rdx, rbx; struct _iobuf *
0x1400211bd  lea     rcx, aSummaryKey1Fin_0; "<Summary key='1' find='total' field='cp"...
0x1400211c4  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400211c9  mov     rdx, rbx; struct _iobuf *
0x1400211cc  lea     rcx, aHeaderSortFiel_5; "\t<Header>\r\n\t\t<Sort field='cpu' typ"...
0x1400211d3  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400211d8  mov     rdi, cs:qword_140082130
0x1400211df  jmp     loc_1400212DD
0x1400211e4  lea     r14, [rdi+20h]
0x1400211e8  mov     rsi, [r14]
0x1400211eb  jmp     loc_1400212D1
0x1400211f0  mov     r8, [rsi+28h]
0x1400211f4  lea     rdx, aItemDataNameSe; "\t<Item>\r\n\t\t<Data name='serviceName"...
0x1400211fb  mov     rcx, rbx; struct _iobuf *
0x1400211fe  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140021203  mov     r8d, [rdi+78h]
0x140021207  mov     rcx, rbx; struct _iobuf *
0x14002120a  test    r8d, r8d
0x14002120d  jz      short loc_14002121D
0x14002120f  lea     rdx, aDataNamePidDDa; "\t\t<Data name='pid'>%d</Data>\r\n"
0x140021216  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14002121b  jmp     short loc_140021229
0x14002121d  lea     rdx, aDataNamePidDat; "\t\t<Data name='pid'>-</Data>\r\n"
0x140021224  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140021229  lea     rdx, aDataNameDescri; "\t\t<Data name='description'>"
0x140021230  mov     rcx, rbx; struct _iobuf *
0x140021233  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140021238  mov     r9, [rsi+30h]; unsigned __int16 *
0x14002123c  xor     r8d, r8d; unsigned __int8
0x14002123f  mov     dl, 1; unsigned __int8
0x140021241  mov     rcx, rbx; struct _iobuf *
0x140021244  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140021249  lea     rdx, aData; "</Data>\r\n"
0x140021250  mov     rcx, rbx; struct _iobuf *
0x140021253  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140021258  cmp     qword ptr [rdi+70h], 0
0x14002125d  lea     rcx, aRunning; "Running"
0x140021264  movups  xmm1, xmmword ptr [rsi+90h]
0x14002126b  lea     r9, asc_140049BB4; "-"
0x140021272  mov     eax, [rsi+68h]
0x140021275  movsd   xmm0, qword ptr [rsi+18h]
0x14002127a  lea     r8, aStopped; "Stopped"
0x140021281  cmovnz  r9, [rdi+70h]
0x140021286  lea     rdx, aDataNameStatus; "\t\t<Data name='status'>%s</Data>\r\n\t"...
0x14002128d  movups  xmm4, xmmword ptr [rsi+58h]
0x140021291  cmp     dword ptr [rdi+78h], 0
0x140021295  movsd   xmm3, qword ptr [rsi+88h]
0x14002129d  movsd   xmm6, qword ptr [rsi+50h]
0x1400212a2  cmovnz  r8, rcx
0x1400212a6  movsd   [rsp+98h+var_40], xmm0
0x1400212ac  mov     rcx, rbx; struct _iobuf *
0x1400212af  movups  [rsp+98h+var_50], xmm1
0x1400212b4  movsd   [rsp+98h+var_58], xmm3
0x1400212ba  movups  [rsp+98h+var_68], xmm4
0x1400212bf  mov     dword ptr [rsp+98h+var_70], eax
0x1400212c3  movsd   [rsp+98h+var_78], xmm6
0x1400212c9  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400212ce  mov     rsi, [rsi]
0x1400212d1  cmp     rsi, r14
0x1400212d4  jnz     loc_1400211F0
0x1400212da  mov     rdi, [rdi]
0x1400212dd  cmp     rdi, rbp
0x1400212e0  jnz     loc_1400211E4
0x1400212e6  mov     rdx, rbx; struct _iobuf *
0x1400212e9  lea     rcx, aTable_0; "</Table>\r\n"
0x1400212f0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400212f5  movaps  xmm6, [rsp+98h+var_38]
0x1400212fa  add     rsp, 70h
0x1400212fe  pop     r14
0x140021300  pop     rdi
0x140021301  pop     rsi
0x140021302  pop     rbp
0x140021303  pop     rbx
0x140021304  retn
```
