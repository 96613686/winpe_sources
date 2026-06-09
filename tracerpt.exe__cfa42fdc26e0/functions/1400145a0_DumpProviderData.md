# DumpProviderData

- ea: `0x1400145a0`
- end: `0x140014895`
- name: `DumpProviderData`
- size: `757`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001489c`

## callees

- `0x1400140f8`
- `0x140014218`
- `0x1400144c4`
- `0x1400145a0`
- `0x140014ccc`
- `0x140016360`
- `0x1400164c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001461b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001472b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400147a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014828`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001461b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001472b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400147a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014828`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001460d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001471d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001481a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001460d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001471d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001481a`

## string_xrefs

- `0x14001464b`: `		<tasks>\n`
- `0x1400146a5`: `		</tasks>\n`
- `0x14001465d`: `			<task value="%d" name="task%d" message="$(string.string%d)" />\n`

## pseudocode

```c
_QWORD *__fastcall DumpProviderData(__int64 a1)
{
  void **v2; // rdi
  _QWORD *v3; // rax
  __int64 v4; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // rsi
  void **v7; // rdi
  _QWORD *v8; // rax
  __int64 v9; // rcx
  HANDLE v10; // rax
  _QWORD *v11; // rsi
  void **v12; // rdi
  _QWORD *v13; // rax
  __int64 v14; // rcx
  HANDLE v15; // rax
  _QWORD *v16; // rsi
  void **v17; // rdi
  _QWORD *v18; // rax
  __int64 v19; // rcx
  HANDLE v20; // rax
  _QWORD *v21; // rsi
  void **v22; // rdi
  _QWORD *v23; // rax
  __int64 v24; // rcx
  HANDLE v25; // rax
  _QWORD *v26; // rsi
  _QWORD *result; // rax
  __int64 v28; // [rsp+20h] [rbp-18h]
  __int64 v29; // [rsp+28h] [rbp-10h]

  if ( *(_QWORD *)(a1 + 32) != a1 + 32 )
  {
    DumpChannelList();
    *(_DWORD *)(a1 + 28) = 0;
  }
  v2 = (void **)(a1 + 56);
  if ( *v2 != v2 )
  {
    TracerptFPutws((wchar_t *)L"\t\t<keywords>\r\n", *(struct _iobuf **)a1);
    while ( 1 )
    {
      v6 = *v2;
      if ( *v2 == v2 )
        break;
      v3 = (_QWORD *)v6[1];
      v4 = *v6;
      *v3 = *v6;
      *(_QWORD *)(v4 + 8) = v3;
      LODWORD(v28) = *((_DWORD *)v6 + 4);
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<keyword name=\"keyword%d\" mask=\"0x%I64x\" message=\"$(string.string%d)\" />\r\n",
        *((unsigned int *)v6 + 8),
        v6[3],
        v28);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    TracerptFPutws((wchar_t *)L"\t\t</keywords>\r\n", *(struct _iobuf **)a1);
    *(_DWORD *)(a1 + 48) = 0;
  }
  v7 = (void **)(a1 + 104);
  if ( *v7 != v7 )
  {
    TracerptFPutws((wchar_t *)L"\t\t<tasks>\r\n", *(struct _iobuf **)a1);
    while ( 1 )
    {
      v11 = *v7;
      if ( *v7 == v7 )
        break;
      v8 = (_QWORD *)v11[1];
      v9 = *v11;
      *v8 = *v11;
      *(_QWORD *)(v9 + 8) = v8;
      LODWORD(v28) = *((_DWORD *)v11 + 4);
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<task value=\"%d\" name=\"task%d\" message=\"$(string.string%d)\" />\r\n",
        *((unsigned __int16 *)v11 + 10),
        *((unsigned int *)v11 + 6),
        v28);
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v11);
    }
    TracerptFPutws((wchar_t *)L"\t\t</tasks>\r\n", *(struct _iobuf **)a1);
    *(_DWORD *)(a1 + 96) = 0;
  }
  if ( *(_QWORD *)(a1 + 176) != a1 + 176 )
  {
    DumpMofTaskList((struct _iobuf **)a1);
    *(_DWORD *)(a1 + 168) = 1;
  }
  v12 = (void **)(a1 + 80);
  if ( *v12 != v12 )
  {
    TracerptFPutws((wchar_t *)L"\t\t<levels>\r\n", *(struct _iobuf **)a1);
    while ( 1 )
    {
      v16 = *v12;
      if ( *v12 == v12 )
        break;
      v13 = (_QWORD *)v16[1];
      v14 = *v16;
      *v13 = *v16;
      *(_QWORD *)(v14 + 8) = v13;
      LODWORD(v28) = *((_DWORD *)v16 + 4);
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<level value=\"%d\" name=\"level%d\" message=\"$(string.string%d)\" />\r\n",
        *((unsigned __int8 *)v16 + 20),
        *((unsigned int *)v16 + 6),
        v28);
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v16);
    }
    TracerptFPutws((wchar_t *)L"\t\t</levels>\r\n", *(struct _iobuf **)a1);
    *(_DWORD *)(a1 + 72) = 0;
  }
  v17 = (void **)(a1 + 128);
  if ( *v17 != v17 )
  {
    TracerptFPutws((wchar_t *)L"\t\t<opcodes>\r\n", *(struct _iobuf **)a1);
    while ( 1 )
    {
      v21 = *v17;
      if ( *v17 == v17 )
        break;
      v18 = (_QWORD *)v21[1];
      v19 = *v21;
      *v18 = *v21;
      *(_QWORD *)(v19 + 8) = v18;
      LODWORD(v28) = *((_DWORD *)v21 + 4);
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<opcode value=\"%d\" name=\"opcode%d\" message=\"$(string.string%d)\"/>\r\n",
        *((unsigned __int8 *)v21 + 20),
        *((unsigned int *)v21 + 6),
        v28);
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v21);
    }
    TracerptFPutws((wchar_t *)L"\t\t</opcodes>\r\n", *(struct _iobuf **)a1);
    *(_DWORD *)(a1 + 120) = 0;
  }
  v22 = (void **)(a1 + 200);
  if ( *v22 != v22 )
  {
    TracerptFPutws((wchar_t *)L"\t\t<opcodes>\r\n", *(struct _iobuf **)a1);
    while ( 1 )
    {
      v26 = *v22;
      if ( *v22 == v22 )
        break;
      v23 = (_QWORD *)v26[1];
      v24 = *v26;
      *v23 = *v26;
      *(_QWORD *)(v24 + 8) = v23;
      LODWORD(v29) = *((_DWORD *)v26 + 10);
      LODWORD(v28) = *((_DWORD *)v26 + 8);
      TracerptFWPrintf(
        *(struct _iobuf **)a1,
        (wchar_t *)L"\t\t\t<opcode value=\"%d\" name=\"opcode%d\" mofValue=\"%d\" message=\"$(string.string%d)\"/>\r\n",
        *((unsigned int *)v26 + 9),
        *((unsigned int *)v26 + 9),
        v28,
        v29);
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v26);
    }
    TracerptFPutws((wchar_t *)L"\t\t</opcodes>\r\n", *(struct _iobuf **)a1);
    *(_DWORD *)(a1 + 192) = 10;
  }
  if ( *(_QWORD *)(a1 + 152) != a1 + 152 )
  {
    DumpTemplateList(a1);
    *(_DWORD *)(a1 + 144) = 0;
  }
  result = (_QWORD *)(a1 + 8);
  if ( (_QWORD *)*result != result )
    result = (_QWORD *)DumpMapList(a1);
  *(_DWORD *)(a1 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x1400145a0  mov     [rsp+arg_0], rbx
0x1400145a5  mov     [rsp+arg_8], rsi
0x1400145aa  push    rdi
0x1400145ab  sub     rsp, 30h
0x1400145af  lea     rax, [rcx+20h]
0x1400145b3  mov     rbx, rcx
0x1400145b6  cmp     [rax], rax
0x1400145b9  jz      short loc_1400145C7
0x1400145bb  call    DumpChannelList
0x1400145c0  mov     dword ptr [rbx+1Ch], 0
0x1400145c7  lea     rdi, [rbx+38h]
0x1400145cb  cmp     [rdi], rdi
0x1400145ce  jz      short loc_14001463F
0x1400145d0  mov     rdx, [rbx]; struct _iobuf *
0x1400145d3  lea     rcx, aKeywords_0; "\t\t<keywords>\r\n"
0x1400145da  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400145df  jmp     short loc_140014621
0x1400145e1  mov     rax, [rsi+8]
0x1400145e5  lea     rdx, aKeywordNameKey; "\t\t\t<keyword name=\"keyword%d\" mask="...
0x1400145ec  mov     rcx, [rsi]
0x1400145ef  mov     [rax], rcx
0x1400145f2  mov     [rcx+8], rax
0x1400145f6  mov     eax, [rsi+10h]
0x1400145f9  mov     r9, [rsi+18h]
0x1400145fd  mov     r8d, [rsi+20h]
0x140014601  mov     rcx, [rbx]; struct _iobuf *
0x140014604  mov     dword ptr [rsp+38h+var_18], eax
0x140014608  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001460d  call    cs:__imp_GetProcessHeap
0x140014613  mov     r8, rsi; lpMem
0x140014616  xor     edx, edx; dwFlags
0x140014618  mov     rcx, rax; hHeap
0x14001461b  call    cs:__imp_HeapFree
0x140014621  mov     rsi, [rdi]
0x140014624  cmp     rsi, rdi
0x140014627  jnz     short loc_1400145E1
0x140014629  mov     rdx, [rbx]; struct _iobuf *
0x14001462c  lea     rcx, aKeywords; "\t\t</keywords>\r\n"
0x140014633  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014638  mov     dword ptr [rbx+30h], 0
0x14001463f  lea     rdi, [rbx+68h]
0x140014643  cmp     [rdi], rdi
0x140014646  jz      short loc_1400146B8
0x140014648  mov     rdx, [rbx]; struct _iobuf *
0x14001464b  lea     rcx, aTasks; "\t\t<tasks>\r\n"
0x140014652  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014657  jmp     short loc_14001469A
0x140014659  mov     rax, [rsi+8]
0x14001465d  lea     rdx, aTaskValueDName; "\t\t\t<task value=\"%d\" name=\"task%d"...
0x140014664  mov     rcx, [rsi]
0x140014667  mov     [rax], rcx
0x14001466a  mov     [rcx+8], rax
0x14001466e  mov     eax, [rsi+10h]
0x140014671  movzx   r8d, word ptr [rsi+14h]
0x140014676  mov     r9d, [rsi+18h]
0x14001467a  mov     rcx, [rbx]; struct _iobuf *
0x14001467d  mov     dword ptr [rsp+38h+var_18], eax
0x140014681  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014686  call    cs:__imp_GetProcessHeap
0x14001468c  mov     r8, rsi; lpMem
0x14001468f  xor     edx, edx; dwFlags
0x140014691  mov     rcx, rax; hHeap
0x140014694  call    cs:__imp_HeapFree
0x14001469a  mov     rsi, [rdi]
0x14001469d  cmp     rsi, rdi
0x1400146a0  jnz     short loc_140014659
0x1400146a2  mov     rdx, [rbx]; struct _iobuf *
0x1400146a5  lea     rcx, aTasks_0; "\t\t</tasks>\r\n"
0x1400146ac  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400146b1  mov     dword ptr [rbx+60h], 0
0x1400146b8  lea     rax, [rbx+0B0h]
0x1400146bf  cmp     [rax], rax
0x1400146c2  jz      short loc_1400146D6
0x1400146c4  mov     rcx, rbx
0x1400146c7  call    DumpMofTaskList
0x1400146cc  mov     dword ptr [rbx+0A8h], 1
0x1400146d6  lea     rdi, [rbx+50h]
0x1400146da  cmp     [rdi], rdi
0x1400146dd  jz      short loc_14001474F
0x1400146df  mov     rdx, [rbx]; struct _iobuf *
0x1400146e2  lea     rcx, aLevels; "\t\t<levels>\r\n"
0x1400146e9  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400146ee  jmp     short loc_140014731
0x1400146f0  mov     rax, [rsi+8]
0x1400146f4  lea     rdx, aLevelValueDNam; "\t\t\t<level value=\"%d\" name=\"level%"...
0x1400146fb  mov     rcx, [rsi]
0x1400146fe  mov     [rax], rcx
0x140014701  mov     [rcx+8], rax
0x140014705  mov     eax, [rsi+10h]
0x140014708  movzx   r8d, byte ptr [rsi+14h]
0x14001470d  mov     r9d, [rsi+18h]
0x140014711  mov     rcx, [rbx]; struct _iobuf *
0x140014714  mov     dword ptr [rsp+38h+var_18], eax
0x140014718  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001471d  call    cs:__imp_GetProcessHeap
0x140014723  mov     r8, rsi; lpMem
0x140014726  xor     edx, edx; dwFlags
0x140014728  mov     rcx, rax; hHeap
0x14001472b  call    cs:__imp_HeapFree
0x140014731  mov     rsi, [rdi]
0x140014734  cmp     rsi, rdi
0x140014737  jnz     short loc_1400146F0
0x140014739  mov     rdx, [rbx]; struct _iobuf *
0x14001473c  lea     rcx, aLevels_0; "\t\t</levels>\r\n"
0x140014743  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014748  mov     dword ptr [rbx+48h], 0
0x14001474f  lea     rdi, [rbx+80h]
0x140014756  cmp     [rdi], rdi
0x140014759  jz      short loc_1400147CB
0x14001475b  mov     rdx, [rbx]; struct _iobuf *
0x14001475e  lea     rcx, aOpcodes; "\t\t<opcodes>\r\n"
0x140014765  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001476a  jmp     short loc_1400147AD
0x14001476c  mov     rax, [rsi+8]
0x140014770  lea     rdx, aOpcodeValueDNa; "\t\t\t<opcode value=\"%d\" name=\"opcod"...
0x140014777  mov     rcx, [rsi]
0x14001477a  mov     [rax], rcx
0x14001477d  mov     [rcx+8], rax
0x140014781  mov     eax, [rsi+10h]
0x140014784  movzx   r8d, byte ptr [rsi+14h]
0x140014789  mov     r9d, [rsi+18h]
0x14001478d  mov     rcx, [rbx]; struct _iobuf *
0x140014790  mov     dword ptr [rsp+38h+var_18], eax
0x140014794  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140014799  call    cs:__imp_GetProcessHeap
0x14001479f  mov     r8, rsi; lpMem
0x1400147a2  xor     edx, edx; dwFlags
0x1400147a4  mov     rcx, rax; hHeap
0x1400147a7  call    cs:__imp_HeapFree
0x1400147ad  mov     rsi, [rdi]
0x1400147b0  cmp     rsi, rdi
0x1400147b3  jnz     short loc_14001476C
0x1400147b5  mov     rdx, [rbx]; struct _iobuf *
0x1400147b8  lea     rcx, aOpcodes_0; "\t\t</opcodes>\r\n"
0x1400147bf  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400147c4  mov     dword ptr [rbx+78h], 0
0x1400147cb  lea     rdi, [rbx+0C8h]
0x1400147d2  cmp     [rdi], rdi
0x1400147d5  jz      short loc_14001484F
0x1400147d7  mov     rdx, [rbx]; struct _iobuf *
0x1400147da  lea     rcx, aOpcodes; "\t\t<opcodes>\r\n"
0x1400147e1  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400147e6  jmp     short loc_14001482E
0x1400147e8  mov     rax, [rsi+8]
0x1400147ec  lea     rdx, aOpcodeValueDNa_0; "\t\t\t<opcode value=\"%d\" name=\"opcod"...
0x1400147f3  mov     rcx, [rsi]
0x1400147f6  mov     [rax], rcx
0x1400147f9  mov     [rcx+8], rax
0x1400147fd  mov     eax, [rsi+28h]
0x140014800  mov     r8d, [rsi+24h]
0x140014804  mov     r9d, r8d
0x140014807  mov     rcx, [rbx]; struct _iobuf *
0x14001480a  mov     [rsp+38h+var_10], eax
0x14001480e  mov     eax, [rsi+20h]
0x140014811  mov     dword ptr [rsp+38h+var_18], eax
0x140014815  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001481a  call    cs:__imp_GetProcessHeap
0x140014820  mov     r8, rsi; lpMem
0x140014823  xor     edx, edx; dwFlags
0x140014825  mov     rcx, rax; hHeap
0x140014828  call    cs:__imp_HeapFree
0x14001482e  mov     rsi, [rdi]
0x140014831  cmp     rsi, rdi
0x140014834  jnz     short loc_1400147E8
0x140014836  mov     rdx, [rbx]; struct _iobuf *
0x140014839  lea     rcx, aOpcodes_0; "\t\t</opcodes>\r\n"
0x140014840  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140014845  mov     dword ptr [rbx+0C0h], 0Ah
0x14001484f  lea     rax, [rbx+98h]
0x140014856  cmp     [rax], rax
0x140014859  jz      short loc_14001486D
0x14001485b  mov     rcx, rbx
0x14001485e  call    DumpTemplateList
0x140014863  mov     dword ptr [rbx+90h], 0
0x14001486d  lea     rax, [rbx+8]
0x140014871  cmp     [rax], rax
0x140014874  jz      short loc_14001487E
0x140014876  mov     rcx, rbx
0x140014879  call    DumpMapList
0x14001487e  mov     rsi, [rsp+38h+arg_8]
0x140014883  mov     dword ptr [rbx+18h], 0
0x14001488a  mov     rbx, [rsp+38h+arg_0]
0x14001488f  add     rsp, 30h
0x140014893  pop     rdi
0x140014894  retn
```
