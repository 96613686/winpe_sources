# PrintDiskTotals

- ea: `0x14001f330`
- end: `0x14001f4a6`
- name: `PrintDiskTotals`
- size: `374`
- prototype: `void __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140016ae0`

## callees

- `0x140016360`
- `0x1400164c4`
- `0x14001f330`
- `0x14001fb68`

## string_xrefs

- `0x14001f373`: `<Table level='1' name='diskTotals' key='200' topic='diskBreakDown'>\n<Summary key='4' find='top' field='ioRate' topic='diskInfo'>\n  <Data name='diskNumber' label='topDiskIO'/>\n  <Data name='ioRate' format='#,##0'/>\n</Summary>\n	<Header>\n		<Sort field='ioRate' type='number' order='descending'/>\n		<Threshold type='top' value='all'/>\n		<Data name='diskNumber' class='string'/>\n		<Data name='readRate' class='number' format='#,##0.0'/>\n		<Data name='readSize' class='number'/>\n		<Da`
- `0x14001f382`: `	<Header>\n		<Sort field='ioRate' type='number' order='descending'/>\n		<Data name='image' class='string'/>\n		<Data name='pid' class='string'/>\n		<Data name='authority' class='string'/>\n		<Data name='readRate' class='number' format='#,##0.0'/>\n		<Data name='readSize' class='number'/>\n		<Data name='writeRate' class='number' format='#,##0.0'/>\n		<Data name='writeSize' class='number'/>\n	</Header>\n`
- `0x14001f423`: `	<Item>\n		<Data name='diskNumber'>%d</Data>\n		<Data name='ioRate' visible='false'>%1.3f</Data>\n		<Data name='readRate'>%1.3f</Data>\n		<Data name='readSize'>%d</Data>\n		<Data name='writeRate'>%1.3f</Data>\n		<Data name='writeSize'>%d</Data>\n`

## pseudocode

```c
void __fastcall PrintDiskTotals(struct _iobuf *a1)
{
  unsigned __int64 v2; // rdi
  LPVOID *v3; // rbx
  int v4; // r8d
  int v5; // ecx
  int v6; // r9d
  unsigned int v7; // eax
  __int64 v8; // [rsp+28h] [rbp-50h]
  __int64 v9; // [rsp+38h] [rbp-40h]

  v2 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem;
  if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem >= 0x989680u && qword_140082140 != &qword_140082140 )
  {
    TracerptFPutws(
      (wchar_t *)L"<Table level='1' name='diskTotals' key='200' topic='diskBreakDown'>\r\n"
                  "<Summary key='4' find='top' field='ioRate' topic='diskInfo'>\r\n"
                  "  <Data name='diskNumber' label='topDiskIO'/>\r\n"
                  "  <Data name='ioRate' format='#,##0'/>\r\n"
                  "</Summary>\r\n"
                  "\t<Header>\r\n"
                  "\t\t<Sort field='ioRate' type='number' order='descending'/>\r\n"
                  "\t\t<Threshold type='top' value='all'/>\r\n"
                  "\t\t<Data name='diskNumber' class='string'/>\r\n"
                  "\t\t<Data name='readRate' class='number' format='#,##0.0'/>\r\n"
                  "\t\t<Data name='readSize' class='number'/>\r\n"
                  "\t\t<Data name='writeRate' class='number' format='#,##0.0'/>\r\n"
                  "\t\t<Data name='writeSize' class='number'/>\r\n",
      a1);
    TracerptFPutws(
      (wchar_t *)L"\t<Header>\r\n"
                  "\t\t<Sort field='ioRate' type='number' order='descending'/>\r\n"
                  "\t\t<Data name='image' class='string'/>\r\n"
                  "\t\t<Data name='pid' class='string'/>\r\n"
                  "\t\t<Data name='authority' class='string'/>\r\n"
                  "\t\t<Data name='readRate' class='number' format='#,##0.0'/>\r\n"
                  "\t\t<Data name='readSize' class='number'/>\r\n"
                  "\t\t<Data name='writeRate' class='number' format='#,##0.0'/>\r\n"
                  "\t\t<Data name='writeSize' class='number'/>\r\n"
                  "\t</Header>\r\n",
      a1);
    TracerptFPutws((wchar_t *)L"\t</Header>\r\n", a1);
    v3 = (LPVOID *)qword_140082140;
    if ( qword_140082140 != &qword_140082140 )
    {
      do
      {
        v4 = *((_DWORD *)v3 + 8) + *((_DWORD *)v3 + 12);
        v5 = *((_DWORD *)v3 + 9);
        if ( v5 )
          v6 = *((_DWORD *)v3 + 11) / (unsigned int)v5;
        else
          v6 = 0;
        if ( v4 )
          v7 = (*((_DWORD *)v3 + 10) + *((_DWORD *)v3 + 13)) / (unsigned int)v4;
        else
          v7 = 0;
        LODWORD(v9) = v6;
        LODWORD(v8) = v7;
        TracerptFWPrintf(
          a1,
          (wchar_t *)L"\t<Item>\r\n"
                      "\t\t<Data name='diskNumber'>%d</Data>\r\n"
                      "\t\t<Data name='ioRate' visible='false'>%1.3f</Data>\r\n"
                      "\t\t<Data name='readRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='readSize'>%d</Data>\r\n"
                      "\t\t<Data name='writeRate'>%1.3f</Data>\r\n"
                      "\t\t<Data name='writeSize'>%d</Data>\r\n",
          *((unsigned int *)v3 + 4),
          (double)v4 / (double)(int)(v2 / 0x989680) + (double)v5 / (double)(int)(v2 / 0x989680),
          (double)v4 / (double)(int)(v2 / 0x989680),
          v8,
          (double)v5 / (double)(int)(v2 / 0x989680),
          v9);
        PrintPerThreadPerDiskTable(a1);
        TracerptFPutws((wchar_t *)L"\t</Item>\r\n", a1);
        v3 = (LPVOID *)*v3;
      }
      while ( v3 != &qword_140082140 );
    }
    TracerptFPutws((wchar_t *)L"</Table>\r\n\r\n", a1);
  }
}

```

## disassembly

```asm
0x14001f330  push    rbx
0x14001f332  push    rbp
0x14001f333  push    rsi
0x14001f334  push    rdi
0x14001f335  sub     rsp, 58h
0x14001f339  mov     rdi, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14001f340  mov     rsi, rcx
0x14001f343  sub     rdi, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x14001f34a  movaps  [rsp+78h+var_38], xmm6
0x14001f34f  cmp     rdi, 989680h
0x14001f356  jb      loc_14001F498
0x14001f35c  lea     rbp, qword_140082140
0x14001f363  cmp     cs:qword_140082140, rbp
0x14001f36a  jz      loc_14001F498
0x14001f370  mov     rdx, rcx; struct _iobuf *
0x14001f373  lea     rcx, aTableLevel1Nam_3; "<Table level='1' name='diskTotals' key="...
0x14001f37a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f37f  mov     rdx, rsi; struct _iobuf *
0x14001f382  lea     rcx, aHeaderSortFiel_2; "\t<Header>\r\n\t\t<Sort field='ioRate' "...
0x14001f389  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f38e  mov     rdx, rsi; struct _iobuf *
0x14001f391  lea     rcx, aHeader_2; "\t</Header>\r\n"
0x14001f398  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f39d  mov     rbx, cs:qword_140082140
0x14001f3a4  cmp     rbx, rbp
0x14001f3a7  jz      loc_14001F489
0x14001f3ad  mov     rax, 0D6BF94D5E57A42BDh
0x14001f3b7  xorps   xmm6, xmm6
0x14001f3ba  mul     rdi
0x14001f3bd  shr     rdx, 17h
0x14001f3c1  test    rdx, rdx
0x14001f3c4  js      short loc_14001F3CD
0x14001f3c6  cvtsi2sd xmm6, rdx
0x14001f3cb  jmp     short loc_14001F3E2
0x14001f3cd  mov     rax, rdx
0x14001f3d0  and     edx, 1
0x14001f3d3  shr     rax, 1
0x14001f3d6  or      rax, rdx
0x14001f3d9  cvtsi2sd xmm6, rax
0x14001f3de  addsd   xmm6, xmm6
0x14001f3e2  mov     r8d, [rbx+30h]
0x14001f3e6  add     r8d, [rbx+20h]
0x14001f3ea  mov     ecx, [rbx+24h]
0x14001f3ed  test    ecx, ecx
0x14001f3ef  jnz     short loc_14001F3F6
0x14001f3f1  xor     r9d, r9d
0x14001f3f4  jmp     short loc_14001F400
0x14001f3f6  mov     eax, [rbx+2Ch]
0x14001f3f9  xor     edx, edx
0x14001f3fb  div     ecx
0x14001f3fd  mov     r9d, eax
0x14001f400  xorps   xmm1, xmm1
0x14001f403  cvtsi2sd xmm1, rcx
0x14001f408  divsd   xmm1, xmm6
0x14001f40c  test    r8d, r8d
0x14001f40f  jnz     short loc_14001F415
0x14001f411  xor     eax, eax
0x14001f413  jmp     short loc_14001F420
0x14001f415  mov     eax, [rbx+34h]
0x14001f418  xor     edx, edx
0x14001f41a  add     eax, [rbx+28h]
0x14001f41d  div     r8d
0x14001f420  mov     ecx, r8d
0x14001f423  lea     rdx, aItemDataNameDi; "\t<Item>\r\n\t\t<Data name='diskNumber'"...
0x14001f42a  mov     r8d, [rbx+10h]
0x14001f42e  xorps   xmm0, xmm0
0x14001f431  mov     dword ptr [rsp+78h+var_40], r9d
0x14001f436  movsd   [rsp+78h+var_48], xmm1
0x14001f43c  cvtsi2sd xmm0, rcx
0x14001f441  mov     dword ptr [rsp+78h+var_50], eax
0x14001f445  mov     rcx, rsi; struct _iobuf *
0x14001f448  divsd   xmm0, xmm6
0x14001f44c  movaps  xmm3, xmm0
0x14001f44f  movsd   [rsp+78h+var_58], xmm0
0x14001f455  addsd   xmm3, xmm1
0x14001f459  movq    r9, xmm3
0x14001f45e  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f463  mov     edx, [rbx+10h]
0x14001f466  mov     rcx, rsi; struct _iobuf *
0x14001f469  call    PrintPerThreadPerDiskTable
0x14001f46e  mov     rdx, rsi; struct _iobuf *
0x14001f471  lea     rcx, aItem_1; "\t</Item>\r\n"
0x14001f478  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f47d  mov     rbx, [rbx]
0x14001f480  cmp     rbx, rbp
0x14001f483  jnz     loc_14001F3E2
0x14001f489  mov     rdx, rsi; struct _iobuf *
0x14001f48c  lea     rcx, aTable; "</Table>\r\n\r\n"
0x14001f493  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f498  movaps  xmm6, [rsp+78h+var_38]
0x14001f49d  add     rsp, 58h
0x14001f4a1  pop     rdi
0x14001f4a2  pop     rsi
0x14001f4a3  pop     rbp
0x14001f4a4  pop     rbx
0x14001f4a5  retn
```
