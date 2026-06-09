# BinXmlReader::WriteTokenText(BinXmlToken &,utl::vector<wchar_t const *,utl::allocator<wchar_t const *>> &,WriteBuffer &)

- ea: `0x1800031f0`
- end: `0x180003776`
- name: `?WriteTokenText@BinXmlReader@@AEAAXAEAUBinXmlToken@@AEAV?$vector@PEB_WV?$allocator@PEB_W@utl@@@utl@@AEAVWriteBuffer@@@Z`
- size: `1414`
- prototype: `void __fastcall(BinXmlReader *this, __int64 **, _QWORD *, WriteBuffer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180003158`

## callees

- `0x180001e9c`
- `0x180002098`
- `0x1800023e8`
- `0x18000314c`
- `0x1800031f0`
- `0x180003780`
- `0x180004070`
- `0x180023548`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlReader::WriteTokenText(BinXmlReader *this, __int64 **a2, _QWORD *a3, WriteBuffer *a4)
{
  int v4; // r10d
  int v9; // r10d
  int v10; // r10d
  int v11; // r10d
  __int64 v12; // r14
  _WORD *v13; // r14
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  _QWORD *v18; // rax
  int v19; // r10d
  int v20; // r10d
  int v21; // r10d
  int v22; // r10d
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v24; // [rsp+30h] [rbp-28h]
  int v25; // [rsp+38h] [rbp-20h]
  int v26; // [rsp+3Ch] [rbp-1Ch]
  int v27; // [rsp+40h] [rbp-18h]
  __int64 v28; // [rsp+98h] [rbp+40h] BYREF

  v4 = *((_DWORD *)a2 + 4);
  if ( v4 == 5 )
  {
    WriteCharDataText(a4);
    return;
  }
  if ( v4 > 5 )
  {
    v19 = v4 - 6;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        WriteBuffer::Write(a4, L"<![CDATA[", 0x12u);
        WriteCharDataText(a4);
        v16 = 8;
        v15 = L"]]> ";
        goto LABEL_15;
      }
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 != 1 )
            goto LABEL_55;
          WriteBuffer::Write(a4, L"<?", 4u);
          WriteNameText(a4, *a2);
          WriteBuffer::Write(a4, L" ", 2u);
          BinXmlReader::NextToken(this, (struct BinXmlToken *)a2, 1);
          WriteCharDataText(a4);
          v16 = 4;
          v15 = L"?>";
          goto LABEL_15;
        }
        WriteBuffer::Write(a4, L"&", 2u);
        WriteNameText(a4, *a2);
      }
      else
      {
        WriteBuffer::Write(a4, L"&#", 4u);
        WriteCharDataText(a4);
      }
      v15 = L";";
LABEL_14:
      v16 = 2;
LABEL_15:
      WriteBuffer::Write(a4, v15, v16);
      return;
    }
    WriteBuffer::Write(a4, L" ", 2u);
    WriteNameText(a4, *a2);
    WriteBuffer::Write(a4, L"='", 4u);
    while ( 1 )
    {
      BinXmlReader::NextToken(this, (struct BinXmlToken *)a2, 1);
      switch ( *((_DWORD *)a2 + 4) )
      {
        case 5:
          WriteCharDataText(a4);
          break;
        case 9:
          WriteBuffer::Write(a4, L"&", 2u);
          WriteNameText(a4, *a2);
LABEL_68:
          WriteBuffer::Write(a4, L";", 2u);
          break;
        case 8:
          WriteBuffer::Write(a4, L"&#", 4u);
          WriteCharDataText(a4);
          goto LABEL_68;
      }
      if ( !*((_BYTE *)a2 + 20) )
      {
        v15 = L"'";
        goto LABEL_14;
      }
    }
  }
  if ( !v4 )
  {
    v15 = (const wchar_t *)&dword_180040234;
    goto LABEL_14;
  }
  v9 = v4 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
    {
LABEL_13:
      v15 = L">";
      goto LABEL_14;
    }
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v12 = a3[1];
        if ( *a3 == v12 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
          }
          v24 = 0;
          v25 = 13;
          v26 = -1;
          pExceptionObject = 0;
          v27 = 2499;
          throw (EvtException *)&pExceptionObject;
        }
        v13 = *(_WORD **)(v12 - 8);
        utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(a3);
        if ( !v13 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
          }
          v24 = 0;
          v25 = 13;
          v26 = -1;
          pExceptionObject = 0;
          v27 = 2507;
          throw (EvtException *)&pExceptionObject;
        }
        WriteBuffer::Write(a4, L"</", 4u);
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        WriteBuffer::Write(a4, v13, 2 * v14);
        goto LABEL_13;
      }
LABEL_55:
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
      }
      v24 = 0;
      v25 = 13;
      v26 = -1;
      pExceptionObject = 0;
      v27 = 2633;
      throw (EvtException *)&pExceptionObject;
    }
    if ( *a3 == a3[1] )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 13);
      }
      v24 = 0;
      v25 = 13;
      v26 = -1;
      pExceptionObject = 0;
      v27 = 2526;
      throw (EvtException *)&pExceptionObject;
    }
    WriteBuffer::Write(a4, L"/>", 4u);
    utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(a3);
  }
  else
  {
    v17 = **a2;
    v18 = (_QWORD *)a3[1];
    v28 = v17;
    if ( v18 == (_QWORD *)a3[2] )
    {
      if ( !(unsigned __int8)utl::vector<wchar_t const *,utl::allocator<wchar_t const *>>::_PushBackOne2<wchar_t const * const &>(
                               a3,
                               &v28) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids, 14);
        }
        v24 = 0;
        v25 = 14;
        v26 = -1;
        pExceptionObject = 0;
        v27 = 2486;
        throw (EvtException *)&pExceptionObject;
      }
    }
    else
    {
      *v18 = v17;
      a3[1] += 8LL;
    }
    WriteBuffer::Write(a4, L"<", 2u);
    WriteNameText(a4, *a2);
  }
}

```

## disassembly

```asm
0x1800031f0  push    rbp
0x1800031f2  push    rbx
0x1800031f3  push    rsi
0x1800031f4  push    rdi
0x1800031f5  push    r14
0x1800031f7  push    r15
0x1800031f9  mov     rbp, rsp
0x1800031fc  sub     rsp, 58h
0x180003200  mov     r10d, [rdx+10h]
0x180003204  xor     edi, edi
0x180003206  mov     rbx, r9
0x180003209  mov     rsi, r8
0x18000320c  mov     r14, rdx
0x18000320f  mov     r15, rcx
0x180003212  cmp     r10d, 5
0x180003216  jz      loc_180003310
0x18000321c  jg      loc_180003325
0x180003222  test    r10d, r10d
0x180003225  jz      loc_1800033CD
0x18000322b  sub     r10d, 1
0x18000322f  jz      loc_1800032C2
0x180003235  sub     r10d, 1
0x180003239  jz      short loc_1800032A0
0x18000323b  sub     r10d, 1
0x18000323f  jz      loc_18000339E
0x180003245  cmp     r10d, 1
0x180003249  jnz     loc_18000360E
0x18000324f  mov     r14, [r8+8]
0x180003253  cmp     [r8], r14
0x180003256  jz      loc_1800033D9
0x18000325c  mov     r14, [r14-8]
0x180003260  mov     rcx, r8
0x180003263  call    ?pop_back@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(void)
0x180003268  test    r14, r14
0x18000326b  jz      loc_180003441
0x180003271  lea     r8d, [rdi+4]; unsigned int
0x180003275  mov     rcx, rbx; this
0x180003278  lea     rdx, asc_180040184; "</"
0x18000327f  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180003284  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003288  inc     r8
0x18000328b  cmp     [r14+r8*2], di
0x180003290  jnz     short loc_180003288
0x180003292  add     r8d, r8d; unsigned int
0x180003295  mov     rdx, r14; void *
0x180003298  mov     rcx, rbx; this
0x18000329b  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800032a0  lea     rdx, asc_18004018C; ">"
0x1800032a7  mov     r8d, 2; unsigned int
0x1800032ad  mov     rcx, rbx; this
0x1800032b0  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800032b5  add     rsp, 58h
0x1800032b9  pop     r15
0x1800032bb  pop     r14
0x1800032bd  pop     rdi
0x1800032be  pop     rsi
0x1800032bf  pop     rbx
0x1800032c0  pop     rbp
0x1800032c1  retn
0x1800032c2  mov     rax, [rdx]
0x1800032c5  mov     rcx, [rax]
0x1800032c8  mov     rax, [r8+8]
0x1800032cc  mov     [rbp+arg_8], rcx
0x1800032d0  cmp     rax, [r8+10h]
0x1800032d4  jnz     loc_180003511
0x1800032da  lea     rdx, [rbp+arg_8]
0x1800032de  mov     rcx, rsi
0x1800032e1  call    ??$_PushBackOne2@AEBQEB_W@?$vector@PEB_WV?$allocator@PEB_W@utl@@@utl@@AEAA_NAEBQEB_W@Z; utl::vector<wchar_t const *,utl::allocator<wchar_t const *>>::_PushBackOne2<wchar_t const * const &>(wchar_t const * const &)
0x1800032e6  test    al, al
0x1800032e8  jz      loc_18000351E
0x1800032ee  mov     r8d, 2; unsigned int
0x1800032f4  lea     rdx, asc_1800401D0; "<"
0x1800032fb  mov     rcx, rbx; this
0x1800032fe  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180003303  mov     rdx, [r14]
0x180003306  mov     rcx, rbx
0x180003309  call    WriteNameText
0x18000330e  jmp     short loc_1800032B5
0x180003310  mov     r9, [r8+8]
0x180003314  mov     rcx, rbx; this
0x180003317  mov     r8b, 1
0x18000331a  mov     r9, [r9-8]
0x18000331e  call    WriteCharDataText
0x180003323  jmp     short loc_1800032B5
0x180003325  sub     r10d, 6
0x180003329  jnz     loc_180003586
0x18000332f  lea     r8d, [r10+2]; unsigned int
0x180003333  mov     rcx, rbx; this
0x180003336  lea     rdx, asc_1800401D4; " "
0x18000333d  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180003342  mov     rdx, [r14]
0x180003345  mov     rcx, rbx
0x180003348  call    WriteNameText
0x18000334d  mov     r8d, 4; unsigned int
0x180003353  lea     rdx, asc_1800401D8; "='"
0x18000335a  mov     rcx, rbx; this
0x18000335d  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180003362  mov     r8b, 1; bool
0x180003365  mov     rdx, r14; struct BinXmlToken *
0x180003368  mov     rcx, r15; this
0x18000336b  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x180003370  cmp     dword ptr [r14+10h], 5
0x180003375  jnz     loc_180003702
0x18000337b  xor     r9d, r9d
0x18000337e  mov     r8b, 2
0x180003381  mov     rdx, r14
0x180003384  mov     rcx, rbx; this
0x180003387  call    WriteCharDataText
0x18000338c  cmp     [r14+14h], dil
0x180003390  jnz     short loc_180003362
0x180003392  lea     rdx, asc_1800401E0; "'"
0x180003399  jmp     loc_1800032A7
0x18000339e  mov     rax, [r8+8]
0x1800033a2  cmp     [r8], rax
0x1800033a5  jz      loc_1800034A9
0x1800033ab  mov     r8d, 4; unsigned int
0x1800033b1  lea     rdx, asc_1800401F8; "/>"
0x1800033b8  mov     rcx, rbx; this
0x1800033bb  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800033c0  mov     rcx, rsi
0x1800033c3  call    ?pop_back@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(void)
0x1800033c8  jmp     loc_1800032B5
0x1800033cd  lea     rdx, dword_180040234
0x1800033d4  jmp     loc_1800032A7
0x1800033d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e0  lea     rax, WPP_GLOBAL_Control
0x1800033e7  mov     ebx, 0Dh
0x1800033ec  cmp     rcx, rax
0x1800033ef  jz      short loc_180003413
0x1800033f1  test    byte ptr [rcx+1Ch], 2
0x1800033f5  jz      short loc_180003413
0x1800033f7  cmp     byte ptr [rcx+19h], 2
0x1800033fb  jb      short loc_180003413
0x1800033fd  mov     rcx, [rcx+10h]
0x180003401  lea     edx, [rbx+2Ah]
0x180003404  mov     r9d, ebx
0x180003407  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x18000340e  call    WPP_SF_D
0x180003413  xorps   xmm0, xmm0
0x180003416  mov     [rbp+var_28], rdi
0x18000341a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003421  mov     [rbp+var_20], ebx
0x180003424  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003428  mov     [rbp+var_1C], 0FFFFFFFFh
0x18000342f  movdqu  [rbp+pExceptionObject], xmm0
0x180003434  mov     [rbp+var_18], 9C3h
0x18000343b  call    _CxxThrowException_0
0x180003441  mov     rcx, cs:WPP_GLOBAL_Control
0x180003448  lea     rax, WPP_GLOBAL_Control
0x18000344f  mov     ebx, 0Dh
0x180003454  cmp     rcx, rax
0x180003457  jz      short loc_18000347B
0x180003459  test    byte ptr [rcx+1Ch], 2
0x18000345d  jz      short loc_18000347B
0x18000345f  cmp     byte ptr [rcx+19h], 2
0x180003463  jb      short loc_18000347B
0x180003465  mov     rcx, [rcx+10h]
0x180003469  lea     edx, [rbx+2Bh]
0x18000346c  mov     r9d, ebx
0x18000346f  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003476  call    WPP_SF_D
0x18000347b  xorps   xmm0, xmm0
0x18000347e  mov     [rbp+var_28], rdi
0x180003482  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003489  mov     [rbp+var_20], ebx
0x18000348c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003490  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003497  movdqu  [rbp+pExceptionObject], xmm0
0x18000349c  mov     [rbp+var_18], 9CBh
0x1800034a3  call    _CxxThrowException_0
0x1800034a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034b0  lea     rax, WPP_GLOBAL_Control
0x1800034b7  mov     ebx, 0Dh
0x1800034bc  cmp     rcx, rax
0x1800034bf  jz      short loc_1800034E3
0x1800034c1  test    byte ptr [rcx+1Ch], 2
0x1800034c5  jz      short loc_1800034E3
0x1800034c7  cmp     byte ptr [rcx+19h], 2
0x1800034cb  jb      short loc_1800034E3
0x1800034cd  mov     rcx, [rcx+10h]
0x1800034d1  lea     edx, [rbx+2Ch]
0x1800034d4  mov     r9d, ebx
0x1800034d7  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x1800034de  call    WPP_SF_D
0x1800034e3  xorps   xmm0, xmm0
0x1800034e6  mov     [rbp+var_28], rdi
0x1800034ea  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800034f1  mov     [rbp+var_20], ebx
0x1800034f4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800034f8  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800034ff  movdqu  [rbp+pExceptionObject], xmm0
0x180003504  mov     [rbp+var_18], 9DEh
0x18000350b  call    _CxxThrowException_0
0x180003511  mov     [rax], rcx
0x180003514  add     qword ptr [r8+8], 8
0x180003519  jmp     loc_1800032EE
0x18000351e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003525  lea     rax, WPP_GLOBAL_Control
0x18000352c  mov     ebx, 0Eh
0x180003531  cmp     rcx, rax
0x180003534  jz      short loc_180003558
0x180003536  test    byte ptr [rcx+1Ch], 2
0x18000353a  jz      short loc_180003558
0x18000353c  cmp     byte ptr [rcx+19h], 2
0x180003540  jb      short loc_180003558
0x180003542  mov     rcx, [rcx+10h]
0x180003546  lea     edx, [rbx+28h]
0x180003549  mov     r9d, ebx
0x18000354c  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003553  call    WPP_SF_D
0x180003558  xorps   xmm0, xmm0
0x18000355b  mov     [rbp+var_28], rdi
0x18000355f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003566  mov     [rbp+var_20], ebx
0x180003569  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000356d  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003574  movdqu  [rbp+pExceptionObject], xmm0
0x180003579  mov     [rbp+var_18], 9B6h
0x180003580  call    _CxxThrowException_0
0x180003586  sub     r10d, 1
0x18000358a  jz      loc_1800036CA
0x180003590  sub     r10d, 1
0x180003594  jz      loc_180003698
0x18000359a  sub     r10d, 1
0x18000359e  jz      loc_180003676
0x1800035a4  cmp     r10d, 1
0x1800035a8  jnz     short loc_18000360E
0x1800035aa  lea     r8d, [r10+3]; unsigned int
0x1800035ae  mov     rcx, rbx; this
0x1800035b1  lea     rdx, asc_180042CDC; "<?"
0x1800035b8  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800035bd  mov     rdx, [r14]
0x1800035c0  mov     rcx, rbx
0x1800035c3  call    WriteNameText
0x1800035c8  mov     r8d, 2; unsigned int
0x1800035ce  lea     rdx, asc_1800401D4; " "
0x1800035d5  mov     rcx, rbx; this
0x1800035d8  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800035dd  mov     r8b, 1; bool
0x1800035e0  mov     rdx, r14; struct BinXmlToken *
0x1800035e3  mov     rcx, r15; this
0x1800035e6  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x1800035eb  xor     r9d, r9d
0x1800035ee  xor     r8d, r8d
0x1800035f1  mov     rdx, r14
0x1800035f4  mov     rcx, rbx; this
0x1800035f7  call    WriteCharDataText
0x1800035fc  mov     r8d, 4
0x180003602  lea     rdx, asc_180042CE4; "?>"
0x180003609  jmp     loc_1800032AD
0x18000360e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003615  lea     rax, WPP_GLOBAL_Control
0x18000361c  mov     ebx, 0Dh
0x180003621  cmp     rcx, rax
0x180003624  jz      short loc_180003648
0x180003626  test    byte ptr [rcx+1Ch], 2
0x18000362a  jz      short loc_180003648
0x18000362c  cmp     byte ptr [rcx+19h], 2
0x180003630  jb      short loc_180003648
0x180003632  mov     rcx, [rcx+10h]
0x180003636  lea     edx, [rbx+2Dh]
0x180003639  mov     r9d, ebx
0x18000363c  lea     r8, WPP_b24d6949f4d130a8e4c05984550f0c1e_Traceguids
0x180003643  call    WPP_SF_D
0x180003648  xorps   xmm0, xmm0
0x18000364b  mov     [rbp+var_28], rdi
0x18000364f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003656  mov     [rbp+var_20], ebx
0x180003659  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000365d  mov     [rbp+var_1C], 0FFFFFFFFh
0x180003664  movdqu  [rbp+pExceptionObject], xmm0
0x180003669  mov     [rbp+var_18], 0A49h
0x180003670  call    _CxxThrowException_0
0x180003676  mov     r8d, 2; unsigned int
0x18000367c  lea     rdx, asc_180042CCC; "&"
0x180003683  mov     rcx, rbx; this
0x180003686  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18000368b  mov     rdx, [r14]
0x18000368e  mov     rcx, rbx
0x180003691  call    WriteNameText
0x180003696  jmp     short loc_1800036BE
0x180003698  mov     r8d, 4; unsigned int
0x18000369e  lea     rdx, asc_180042CD4; "&#"
0x1800036a5  mov     rcx, rbx; this
0x1800036a8  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800036ad  xor     r9d, r9d
0x1800036b0  xor     r8d, r8d
0x1800036b3  mov     rdx, r14
0x1800036b6  mov     rcx, rbx; this
0x1800036b9  call    WriteCharDataText
0x1800036be  lea     rdx, asc_180042CD0; ";"
0x1800036c5  jmp     loc_1800032A7
0x1800036ca  mov     r8d, 12h; unsigned int
0x1800036d0  lea     rdx, aCdata; "<![CDATA["
0x1800036d7  mov     rcx, rbx; this
0x1800036da  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800036df  xor     r9d, r9d
0x1800036e2  xor     r8d, r8d
0x1800036e5  mov     rdx, r14
0x1800036e8  mov     rcx, rbx; this
  ... truncated ...
```
