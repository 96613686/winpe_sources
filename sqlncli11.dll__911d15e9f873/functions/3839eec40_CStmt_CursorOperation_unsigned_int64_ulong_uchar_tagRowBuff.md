# CStmt::CursorOperation(unsigned __int64,ulong,uchar,tagRowBuff *)

- ea: `0x3839eec40`
- end: `0x3839ef5d6`
- name: `?CursorOperation@CStmt@@AEAAH_KKEPEAUtagRowBuff@@@Z`
- size: `2454`
- prototype: `__int64 __usercall@<rax>(CStmt *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, struct tagRowBuff *)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x3838b8f30`
- `0x3839f1030`

## callees

- `0x3838424f0`
- `0x3838435f0`
- `0x383849540`
- `0x3838527a0`
- `0x383876e40`
- `0x383876f60`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839bdb30`
- `0x3839e29f0`
- `0x3839eec40`
- `0x3839ef620`
- `0x3839f03e0`
- `0x383a1aa50`

## import_xrefs

- `MSVCR100!memmove` at `0x3839ef0da`
- `MSVCR100!memmove` at `0x3839ef0da`
- `MSVCR100!_wcsicmp` at `0x3839ef1df`
- `MSVCR100!_wcsicmp` at `0x3839ef1df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStmt::CursorOperation(CStmt *this, int a2, unsigned int a3, __int64 a4, struct tagRowBuff *a5)
{
  __int64 v5; // r12
  unsigned int v8; // esi
  __int64 v9; // rax
  char *v10; // rax
  struct BATCHCTX *v11; // r13
  __int64 v12; // rax
  __int64 v13; // r8
  CConnection *v14; // rcx
  int inserted; // edi
  int NewBatchCtx; // eax
  unsigned __int16 v17; // cx
  int v18; // eax
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // r9
  int v22; // ecx
  int v23; // eax
  __int64 v24; // r9
  struct tagRowBuff *v25; // r15
  int v26; // eax
  struct BATCHCTX *v27; // rdx
  struct BATCHCTX *v28; // r12
  unsigned int v29; // r13d
  char *v30; // rcx
  __int64 v31; // r14
  unsigned int v32; // r15d
  unsigned __int8 v33; // al
  __int64 v34; // rdx
  __int64 v35; // rax
  char *v36; // rax
  __int64 v37; // r9
  __int64 v38; // r9
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rcx
  char *v42; // rax
  const wchar_t *v43; // r8
  char *v44; // rax
  int v45; // eax
  __int16 v46; // r12
  struct CRowMetadata *RowMetadata; // rax
  unsigned __int64 v48; // r15
  struct BATCHCTX *v49; // r14
  unsigned __int64 v50; // r12
  struct tagRowBuff *v51; // rcx
  struct COLINFO *v52; // r8
  unsigned int v53; // eax
  int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rcx
  CStmt *v59; // rax
  int v60; // ecx
  _QWORD *v61; // rbx
  CStmt *v62; // rdi
  BATCHCTX *v63; // rcx
  __int64 v65; // [rsp+20h] [rbp-71h]
  struct BATCHCTX *v66; // [rsp+40h] [rbp-51h]
  unsigned int v67; // [rsp+48h] [rbp-49h]
  char *v68; // [rsp+50h] [rbp-41h]
  __int64 v69; // [rsp+58h] [rbp-39h] BYREF
  CStmt *v70; // [rsp+60h] [rbp-31h]
  _QWORD *v71; // [rsp+68h] [rbp-29h]
  __int64 v72; // [rsp+70h] [rbp-21h]
  __int64 v73; // [rsp+78h] [rbp-19h]
  __int64 v74; // [rsp+80h] [rbp-11h]
  __int64 v75; // [rsp+88h] [rbp-9h]
  __int64 v76; // [rsp+90h] [rbp-1h]
  __int64 v77; // [rsp+98h] [rbp+7h]
  __int64 v78; // [rsp+A0h] [rbp+Fh]
  __int64 v79; // [rsp+A8h] [rbp+17h]
  int v80; // [rsp+F0h] [rbp+5Fh] BYREF
  unsigned int v81; // [rsp+100h] [rbp+6Fh]

  v81 = a3;
  v79 = -2;
  v5 = a3;
  v8 = -1;
  if ( !*((_QWORD *)this + 53) )
  {
    v9 = *((_QWORD *)this + 88);
    if ( v9 )
      *((_QWORD *)this + 53) = *(_QWORD *)(v9 + 1944);
  }
  v10 = (char *)*((_QWORD *)this + 53);
  v68 = v10;
  if ( !v10 || (*((_WORD *)this + 292) & 0x2000) != 0 )
  {
    v10 = (char *)this + 320;
    v68 = (char *)this + 320;
  }
  v67 = *((unsigned __int16 *)v10 + 1);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v11 = 0;
  v66 = 0;
  v70 = 0;
  v69 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4A990[0] )
  {
    v12 = *((_QWORD *)this + 15);
    if ( v12 )
      v13 = *(unsigned int *)(v12 + 52);
    else
      v13 = *((unsigned int *)this + 13);
    bidScopeEnterW(&v69, off_383B4A990[0], v13, this);
  }
  if ( *((_QWORD *)this + 12) )
    goto LABEL_25;
  v14 = *(CConnection **)(*((_QWORD *)this + 66) + 1832LL);
  if ( !v14 )
  {
    inserted = -2147467259;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_138;
    if ( off_383B49128[0] )
      bidTraceW(off_383B432B8[0], 3839017, off_383B49128[0], 2147500037LL);
    goto LABEL_22;
  }
  NewBatchCtx = CConnection::GetNewBatchCtx(v14, this, (struct BATCHCTX **)this + 12);
  inserted = NewBatchCtx;
  if ( NewBatchCtx >= 0 )
  {
LABEL_25:
    v11 = (struct BATCHCTX *)*((_QWORD *)this + 12);
    v66 = v11;
    if ( (*(_BYTE *)(*((_QWORD *)v11 + 8) + 400LL) & 1) != 0 )
    {
      ++*((_DWORD *)this + 26);
      v70 = this;
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      inserted = bidTraceHR(off_383B432B8[0], 3848201, (unsigned int)NewBatchCtx);
    if ( inserted < 0 )
    {
LABEL_22:
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B432E0[0], 622633, off_383B49128[0], (unsigned int)inserted);
      goto LABEL_138;
    }
  }
  v17 = 0;
  if ( (v5 & 0xFFFF7FFF) == 1 )
    v17 = 2;
  v18 = CStmt::StmtAddRpcCmd(this, v11, L"sp_cursor", 9u, v17, *((_DWORD *)this + 51));
  inserted = v18;
  if ( v18 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432E0[0], 630793, (unsigned int)v18);
    goto LABEL_138;
  }
  v65 = 4;
  LOBYTE(v19) = 38;
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 16) + 48LL))(
          *((_QWORD *)this + 16),
          0,
          0,
          v19);
  inserted = v20;
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432E0[0], 642057, (unsigned int)v20);
    goto LABEL_138;
  }
  if ( (v5 & 0x8000) != 0 )
  {
    v8 = -1;
LABEL_100:
    v46 = v5 & 0x7FFF;
    *((_WORD *)this + 344) = v46;
    if ( *((_QWORD *)this + 84) )
    {
      *((_DWORD *)this + 50) |= 0x400u;
      RowMetadata = CStmt::GetRowMetadata(this);
      v48 = *((_QWORD *)this + 84);
      v49 = (struct BATCHCTX *)(*((_QWORD *)RowMetadata + 2) + 304 * v48);
      v50 = *((unsigned __int16 *)RowMetadata + 1);
      if ( v48 <= v50 )
      {
        v51 = a5;
        do
        {
          v52 = (struct COLINFO *)*(unsigned int *)((char *)v51 + *((_QWORD *)v49 + 25));
          if ( ((unsigned int)v52 & 0xC0000000) != 0
            && (((unsigned int)v52 & 0x40000000) == 0 || ((unsigned int)v52 & 0x1FFFFFFF) != 0xD)
            && ((unsigned int)v52 & 0x20000000) != 0 )
          {
            v53 = CStmt::AddColumnValueParam(this, v49, v52, (unsigned int)v51, (struct tagRowBuff *)v65);
            if ( !v8 && v53 == 1 || (v8 & 0xFFFE) == 0 && v53 )
              v8 = v53;
            if ( v8 == -1 )
            {
              CStmt::Flush(this);
              goto LABEL_138;
            }
            v51 = a5;
          }
          ++v48;
          v49 = (struct BATCHCTX *)((char *)v49 + 304);
        }
        while ( v48 <= v50 );
      }
      *((_DWORD *)this + 50) &= ~0x400u;
      *((_DWORD *)this + 53) = 2;
      *((_QWORD *)this + 35) = -1;
      *((_BYTE *)this + 221) = 2;
      v54 = CStmt::StmtSendRPC(this, v11, 0);
      inserted = v54;
      if ( v54 >= 0 )
      {
        v55 = CDBConnection::ProcessTDSStream(*((CDBConnection **)this + 66), v11, this, 0x88u, *((_DWORD *)this + 51));
        if ( !v8 && v55 == 1 || (v8 & 0xFFFE) == 0 && v55 )
          v8 = v55;
      }
      else if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceHR(off_383B432E0[0], 902153, (unsigned int)v54);
      }
    }
    else if ( v8 != -1 )
    {
      if ( v46 != 1 )
        *((_QWORD *)this + 35) = 0;
      v56 = CStmt::ExecRPCImmediate(this, v11, 0);
      if ( !v8 && v56 == 1 || (v8 & 0xFFFE) == 0 && v56 )
        v8 = v56;
      if ( v8 == 2 && *((_WORD *)this + 344) == 1 )
        *((_DWORD *)this + 50) |= 0x80000u;
    }
LABEL_138:
    if ( inserted < 0 )
      goto LABEL_139;
    if ( v8 == -1 )
      goto LABEL_141;
    goto LABEL_143;
  }
  v22 = *((_DWORD *)qword_3839EF5D8 + v5);
  v80 = v22;
  if ( (_DWORD)v5 == 1 || (_DWORD)v5 == 2 || (_DWORD)v5 == 3 )
    v80 = v22 | 0x20;
  LOBYTE(v21) = 38;
  v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int *, _QWORD))(**((_QWORD **)this + 16) + 48LL))(
          *((_QWORD *)this + 16),
          0,
          0,
          v21,
          4,
          4,
          &v80,
          0);
  inserted = v23;
  if ( v23 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432E0[0], 667657, (unsigned int)v23);
    goto LABEL_138;
  }
  if ( (unsigned int)v5 < 5 )
  {
    v80 = a2;
    v25 = a5;
  }
  else
  {
    v25 = a5;
    v80 = *((_DWORD *)a5 + 32);
  }
  v65 = 4;
  LOBYTE(v24) = 38;
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 16) + 48LL))(
          *((_QWORD *)this + 16),
          0,
          0,
          v24);
  inserted = v26;
  if ( v26 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B432E0[0], 690185, (unsigned int)v26);
    goto LABEL_138;
  }
  *((_QWORD *)this + 84) = 0;
  v8 = 0;
  if ( (_DWORD)v5 != 2 && (_DWORD)v5 != 4 && (_DWORD)v5 != 5 )
    goto LABEL_100;
  v28 = 0;
  v29 = 1;
  v30 = v68;
  v31 = *((_QWORD *)v68 + 2) + 304LL;
  if ( !v67 )
  {
LABEL_95:
    LOWORD(v5) = v81;
    if ( v81 != 4 )
    {
      v57 = *((_QWORD *)this + 16);
      if ( v57 )
        (*(void (__fastcall **)(__int64, CStmt *))(*(_QWORD *)v57 + 104LL))(v57, this);
      goto LABEL_138;
    }
    inserted = CStmt::InsertDefaultValues(this, v27);
    if ( inserted < 0 )
      v8 = -1;
LABEL_99:
    v11 = v66;
    goto LABEL_100;
  }
  while ( 1 )
  {
    v32 = *(_DWORD *)((char *)v25 + *(_QWORD *)(v31 + 200));
    if ( (v32 & 0xC0000000) == 0 || (v32 & 0x40000000) != 0 && (v32 & 0x1FFFFFFF) == 0xD )
      goto LABEL_83;
    if ( !*(_QWORD *)(v31 + 104) )
    {
      v33 = *(_BYTE *)(v31 + 122);
      if ( v33 )
      {
        v34 = *((_QWORD *)v30 + 3);
        if ( v34 )
          memmove((void *)(v31 + 72), (const void *)(*(_QWORD *)(v34 + 32) + 40LL * v33), 0x28u);
      }
    }
    v27 = *(struct BATCHCTX **)(v31 + 104);
    if ( !v27 )
      break;
    if ( v28 )
    {
      if ( v27 != v28 )
      {
        v41 = *((_QWORD *)this + 88);
        if ( !v41 || (v42 = *(char **)(v41 + 1952)) == 0 )
          v42 = (char *)this + 360;
        v43 = (const wchar_t *)((char *)v28 + *((_QWORD *)v42 + 4));
        if ( !v41 || (v44 = *(char **)(v41 + 1952)) == 0 )
          v44 = (char *)this + 360;
        if ( _wcsicmp(v43, (const wchar_t *)((char *)v27 + *((_QWORD *)v44 + 4))) )
        {
          if ( (bidGblFlags & 2) != 0 )
            v45 = bidTraceHR(off_383B432E0[0], 779273, (unsigned int)inserted);
          else
            v45 = inserted;
          CErrorData::PostStandardError((CStmt *)((char *)this + 136), 0x9D01u, v45, 0);
          v8 = -1;
LABEL_98:
          LOWORD(v5) = v81;
          goto LABEL_99;
        }
      }
    }
    else
    {
      v28 = *(struct BATCHCTX **)(v31 + 104);
      v35 = *((_QWORD *)this + 88);
      if ( !v35 || (v36 = *(char **)(v35 + 1952)) == 0 )
        v36 = (char *)this + 360;
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)((char *)v27 + 2 * v37 + *((_QWORD *)v36 + 4)) );
      v38 = 2 * v37;
      v39 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 66) + 200LL) + 1080LL);
      LODWORD(v73) = *(_DWORD *)(v39 + 1816);
      BYTE4(v73) = *(_BYTE *)(v39 + 1820);
      v65 = v38;
      LOBYTE(v38) = -25;
      v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 16) + 48LL))(
              *((_QWORD *)this + 16),
              0,
              0,
              v38);
      inserted = v40;
      if ( v40 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B432E0[0], 768009, (unsigned int)v40);
        goto LABEL_138;
      }
    }
    if ( (v32 & 0x20000000) != 0 )
    {
      v30 = v68;
      if ( !*((_QWORD *)this + 84) )
        *((_QWORD *)this + 84) = (unsigned __int16)v29;
    }
    else
    {
      v8 = CStmt::AddColumnValueParam(
             this,
             (struct BATCHCTX *)v31,
             (struct COLINFO *)v32,
             (unsigned int)a5,
             (struct tagRowBuff *)v65);
      if ( v8 == -1 )
        goto LABEL_98;
      v30 = v68;
    }
LABEL_83:
    ++v29;
    v31 += 304;
    if ( v29 > v67 )
    {
      if ( !v28 )
        goto LABEL_95;
      goto LABEL_98;
    }
    v25 = a5;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    bidTraceW(off_383B432E0[0], 743465, off_383B49128[0], 2147500037LL);
LABEL_139:
  v8 = -1;
LABEL_141:
  v58 = *((_QWORD *)this + 16);
  if ( v58 )
    (*(void (__fastcall **)(__int64, CStmt *))(*(_QWORD *)v58 + 104LL))(v58, this);
LABEL_143:
  if ( v69 != -1 )
  {
    if ( (bidGblFlags & 4) != 0 )
    {
      if ( bidID != -1 )
        off_383B15058();
    }
    else
    {
      v69 = -1;
    }
  }
  v59 = v70;
  if ( v70 )
  {
    v60 = *((_DWORD *)v70 + 26) - 1;
    *((_DWORD *)v70 + 26) = v60;
    if ( !v60 )
    {
      v61 = (_QWORD *)((char *)v59 + 112);
      if ( v59 != (CStmt *)-112LL )
      {
        if ( *v61 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v61 + 32LL) + 8LL))(*v61 + 32LL);
        v61 = (_QWORD *)*v61;
      }
      v71 = v61;
      v62 = v70;
      v63 = (BATCHCTX *)*((_QWORD *)v70 + 12);
      if ( !*((_QWORD *)v63 + 12) )
      {
        BATCHCTX::Release(v63);
        *((_QWORD *)v62 + 12) = 0;
      }
      if ( v61 )
        (*(void (__fastcall **)(_QWORD *))(v61[4] + 24LL))(v61 + 4);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x3839eec40  mov     [rsp-8+arg_10], r8d
0x3839eec45  push    rbp
0x3839eec46  push    rsi
0x3839eec47  push    rdi
0x3839eec48  push    r12
0x3839eec4a  push    r13
0x3839eec4c  push    r14
0x3839eec4e  push    r15
0x3839eec50  lea     rbp, [rsp-1Fh]
0x3839eec55  sub     rsp, 0B0h
0x3839eec5c  mov     [rbp+4Fh+var_38], 0FFFFFFFFFFFFFFFEh
0x3839eec64  mov     [rsp+0E0h+arg_8], rbx
0x3839eec6c  mov     r12d, r8d
0x3839eec6f  mov     r15, rdx
0x3839eec72  mov     rbx, rcx
0x3839eec75  or      esi, 0FFFFFFFFh
0x3839eec78  cmp     qword ptr [rcx+1A8h], 0
0x3839eec80  jnz     short loc_3839EEC9C
0x3839eec82  mov     rax, [rcx+2C0h]
0x3839eec89  test    rax, rax
0x3839eec8c  jz      short loc_3839EEC9C
0x3839eec8e  mov     rax, [rax+798h]
0x3839eec95  mov     [rcx+1A8h], rax
0x3839eec9c  mov     rax, [rcx+1A8h]
0x3839eeca3  mov     [rbp+4Fh+var_90], rax
0x3839eeca7  test    rax, rax
0x3839eecaa  jz      short loc_3839EECBA
0x3839eecac  mov     ecx, 2000h
0x3839eecb1  test    [rbx+248h], cx
0x3839eecb8  jz      short loc_3839EECC5
0x3839eecba  lea     rax, [rbx+140h]
0x3839eecc1  mov     [rbp+4Fh+var_90], rax
0x3839eecc5  movzx   eax, word ptr [rax+2]
0x3839eecc9  mov     [rbp+4Fh+var_98], eax
0x3839eeccc  xor     ecx, ecx
0x3839eecce  mov     [rbp+4Fh+var_70], rcx
0x3839eecd2  xor     eax, eax
0x3839eecd4  mov     [rbp+4Fh+var_68], rax
0x3839eecd8  mov     [rbp+4Fh+var_60], rax
0x3839eecdc  mov     [rbp+4Fh+var_58], rax
0x3839eece0  mov     [rbp+4Fh+var_50], rax
0x3839eece4  mov     [rbp+4Fh+var_48], rax
0x3839eece8  mov     [rbp+4Fh+var_40], rax
0x3839eecec  mov     r13d, ecx
0x3839eecef  mov     [rbp+4Fh+var_A0], rcx
0x3839eecf3  mov     [rbp+4Fh+var_80], rcx
0x3839eecf7  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFFh
0x3839eecff  test    byte ptr cs:_bidGblFlags, 4
0x3839eed06  jz      short loc_3839EED55
0x3839eed08  mov     rax, cs:off_383B4A990; "<CStmt::CursorOperation|OLEDB|EXEC> %u#"...
0x3839eed0f  test    rax, rax
0x3839eed12  jz      short loc_3839EED55
0x3839eed14  mov     rax, [rbx+78h]
0x3839eed18  test    rax, rax
0x3839eed1b  jz      short loc_3839EED23
0x3839eed1d  mov     r8d, [rax+34h]
0x3839eed21  jmp     short loc_3839EED27
0x3839eed23  mov     r8d, [rbx+34h]
0x3839eed27  movzx   eax, r9b
0x3839eed2b  mov     r9, [rbp+4Fh+arg_20]
0x3839eed2f  mov     [rsp+0E0h+var_A8], r9
0x3839eed34  mov     dword ptr [rsp+0E0h+var_B0], eax
0x3839eed38  mov     [rsp+0E0h+var_B8], r12d
0x3839eed3d  mov     [rsp+0E0h+var_C0], rdx
0x3839eed42  mov     r9, rbx
0x3839eed45  mov     rdx, cs:off_383B4A990; "<CStmt::CursorOperation|OLEDB|EXEC> %u#"...
0x3839eed4c  lea     rcx, [rbp+4Fh+var_88]
0x3839eed50  call    _bidScopeEnterW
0x3839eed55  cmp     qword ptr [rbx+60h], 0
0x3839eed5a  jnz     loc_3839EEE30
0x3839eed60  mov     rax, [rbx+210h]
0x3839eed67  mov     rcx, [rax+728h]; this
0x3839eed6e  test    rcx, rcx
0x3839eed71  jnz     short loc_3839EEDB6
0x3839eed73  mov     edi, 80004005h
0x3839eed78  test    byte ptr cs:_bidGblFlags, 2
0x3839eed7f  jz      loc_3839EF4FE
0x3839eed85  mov     rcx, cs:off_383B432B8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eed8c  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839eed93  test    rax, rax
0x3839eed96  jz      short loc_3839EEDEB
0x3839eed98  mov     dword ptr [rsp+0E0h+var_C0], 0EA5h
0x3839eeda0  mov     r9d, edi
0x3839eeda3  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839eedaa  mov     edx, 3A9429h
0x3839eedaf  call    _bidTraceW
0x3839eedb4  jmp     short loc_3839EEDEB
0x3839eedb6  lea     r8, [rbx+60h]; struct BATCHCTX **
0x3839eedba  mov     rdx, rbx; struct CConnection *
0x3839eedbd  call    ?GetNewBatchCtx@CConnection@@QEAAJPEAXPEAPEAVBATCHCTX@@@Z; CConnection::GetNewBatchCtx(void *,BATCHCTX * *)
0x3839eedc2  mov     edi, eax
0x3839eedc4  test    eax, eax
0x3839eedc6  jns     short loc_3839EEE30
0x3839eedc8  test    byte ptr cs:_bidGblFlags, 2
0x3839eedcf  jz      short loc_3839EEDE7
0x3839eedd1  mov     r8d, eax
0x3839eedd4  mov     edx, 3AB809h
0x3839eedd9  mov     rcx, cs:off_383B432B8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eede0  call    _bidTraceHR
0x3839eede5  mov     edi, eax
0x3839eede7  test    edi, edi
0x3839eede9  jns     short loc_3839EEE4C
0x3839eedeb  test    byte ptr cs:_bidGblFlags, 2
0x3839eedf2  jz      loc_3839EF4FE
0x3839eedf8  mov     rcx, cs:off_383B432E0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eedff  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839eee06  test    rax, rax
0x3839eee09  jz      loc_3839EF4FE
0x3839eee0f  mov     dword ptr [rsp+0E0h+var_C0], 260h
0x3839eee17  mov     r9d, edi
0x3839eee1a  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839eee21  mov     edx, 98029h
0x3839eee26  call    _bidTraceW
0x3839eee2b  jmp     loc_3839EF4FE
0x3839eee30  mov     r13, [rbx+60h]
0x3839eee34  mov     [rbp+4Fh+var_A0], r13
0x3839eee38  mov     rax, [r13+40h]
0x3839eee3c  test    byte ptr [rax+190h], 1
0x3839eee43  jz      short loc_3839EEE4C
0x3839eee45  inc     dword ptr [rbx+68h]
0x3839eee48  mov     [rbp+4Fh+var_80], rbx
0x3839eee4c  mov     eax, r12d
0x3839eee4f  btr     eax, 0Fh
0x3839eee53  xor     ecx, ecx
0x3839eee55  mov     edx, 2
0x3839eee5a  cmp     eax, 1
0x3839eee5d  cmovz   cx, dx
0x3839eee61  mov     eax, [rbx+0CCh]
0x3839eee67  mov     [rsp+0E0h+var_B8], eax; int
0x3839eee6b  mov     word ptr [rsp+0E0h+var_C0], cx; unsigned __int16
0x3839eee70  lea     r9d, [rdx+7]; unsigned __int64
0x3839eee74  lea     r8, aSpCursor_0; "sp_cursor"
0x3839eee7b  mov     rdx, r13; struct BATCHCTX *
0x3839eee7e  mov     rcx, rbx; this
0x3839eee81  call    ?StmtAddRpcCmd@CStmt@@QEAAJPEAVBATCHCTX@@PEBG_KGH@Z; CStmt::StmtAddRpcCmd(BATCHCTX *,ushort const *,unsigned __int64,ushort,int)
0x3839eee86  mov     edi, eax
0x3839eee88  test    eax, eax
0x3839eee8a  jns     short loc_3839EEEB2
0x3839eee8c  test    byte ptr cs:_bidGblFlags, 2
0x3839eee93  jz      loc_3839EF4FE
0x3839eee99  mov     r8d, eax
0x3839eee9c  mov     edx, 9A009h
0x3839eeea1  mov     rcx, cs:off_383B432E0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eeea8  call    _bidTraceHR
0x3839eeead  jmp     loc_3839EF4FE
0x3839eeeb2  mov     rcx, [rbx+80h]
0x3839eeeb9  mov     r10, [rcx]
0x3839eeebc  lea     rax, [rbx+12Ch]
0x3839eeec3  xor     r8d, r8d
0x3839eeec6  mov     [rsp+0E0h+var_A8], r8
0x3839eeecb  mov     [rsp+0E0h+var_B0], rax
0x3839eeed0  mov     qword ptr [rsp+0E0h+var_B8], 4
0x3839eeed9  mov     [rsp+0E0h+var_C0], 4
0x3839eeee2  mov     r9b, 26h ; '&'
0x3839eeee5  xor     edx, edx
0x3839eeee7  call    qword ptr [r10+30h]
0x3839eeeeb  mov     edi, eax
0x3839eeeed  test    eax, eax
0x3839eeeef  jns     short loc_3839EEF17
0x3839eeef1  test    byte ptr cs:_bidGblFlags, 2
0x3839eeef8  jz      loc_3839EF4FE
0x3839eeefe  mov     r8d, eax
0x3839eef01  mov     edx, 9CC09h
0x3839eef06  mov     rcx, cs:off_383B432E0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eef0d  call    _bidTraceHR
0x3839eef12  jmp     loc_3839EF4FE
0x3839eef17  bt      r12d, 0Fh
0x3839eef1c  jnb     short loc_3839EEF26
0x3839eef1e  or      esi, 0FFFFFFFFh
0x3839eef21  jmp     loc_3839EF326
0x3839eef26  lea     rcx, qword_3839EF5D8
0x3839eef2d  mov     ecx, [rcx+r12*4]
0x3839eef31  mov     [rbp+4Fh+arg_0], ecx
0x3839eef34  cmp     r12d, 1
0x3839eef38  jz      short loc_3839EEF46
0x3839eef3a  cmp     r12d, 2
0x3839eef3e  jz      short loc_3839EEF46
0x3839eef40  cmp     r12d, 3
0x3839eef44  jnz     short loc_3839EEF4C
0x3839eef46  or      ecx, 20h
0x3839eef49  mov     [rbp+4Fh+arg_0], ecx
0x3839eef4c  mov     rcx, [rbx+80h]
0x3839eef53  mov     rax, [rcx]
0x3839eef56  xor     r8d, r8d
0x3839eef59  mov     [rsp+0E0h+var_A8], r8
0x3839eef5e  lea     rdx, [rbp+4Fh+arg_0]
0x3839eef62  mov     [rsp+0E0h+var_B0], rdx
0x3839eef67  mov     qword ptr [rsp+0E0h+var_B8], 4
0x3839eef70  mov     [rsp+0E0h+var_C0], 4
0x3839eef79  mov     r9b, 26h ; '&'
0x3839eef7c  xor     edx, edx
0x3839eef7e  call    qword ptr [rax+30h]
0x3839eef81  mov     edi, eax
0x3839eef83  test    eax, eax
0x3839eef85  jns     short loc_3839EEFAD
0x3839eef87  test    byte ptr cs:_bidGblFlags, 2
0x3839eef8e  jz      loc_3839EF4FE
0x3839eef94  mov     r8d, eax
0x3839eef97  mov     edx, 0A3009h
0x3839eef9c  mov     rcx, cs:off_383B432E0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839eefa3  call    _bidTraceHR
0x3839eefa8  jmp     loc_3839EF4FE
0x3839eefad  cmp     r12d, 5
0x3839eefb1  jb      short loc_3839EEFC3
0x3839eefb3  mov     r15, [rbp+4Fh+arg_20]
0x3839eefb7  mov     eax, [r15+80h]
0x3839eefbe  mov     [rbp+4Fh+arg_0], eax
0x3839eefc1  jmp     short loc_3839EEFCB
0x3839eefc3  mov     [rbp+4Fh+arg_0], r15d
0x3839eefc7  mov     r15, [rbp+4Fh+arg_20]
0x3839eefcb  mov     rcx, [rbx+80h]
0x3839eefd2  mov     rax, [rcx]
0x3839eefd5  xor     r8d, r8d
0x3839eefd8  mov     [rsp+0E0h+var_A8], r8
0x3839eefdd  lea     rdx, [rbp+4Fh+arg_0]
0x3839eefe1  mov     [rsp+0E0h+var_B0], rdx
0x3839eefe6  mov     qword ptr [rsp+0E0h+var_B8], 4
0x3839eefef  mov     [rsp+0E0h+var_C0], 4; struct tagRowBuff *
0x3839eeff8  mov     r9b, 26h ; '&'
0x3839eeffb  xor     edx, edx
0x3839eeffd  call    qword ptr [rax+30h]
0x3839ef000  mov     edi, eax
0x3839ef002  test    eax, eax
0x3839ef004  jns     short loc_3839EF02C
0x3839ef006  test    byte ptr cs:_bidGblFlags, 2
0x3839ef00d  jz      loc_3839EF4FE
0x3839ef013  mov     r8d, eax
0x3839ef016  mov     edx, 0A8809h
0x3839ef01b  mov     rcx, cs:off_383B432E0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ef022  call    _bidTraceHR
0x3839ef027  jmp     loc_3839EF4FE
0x3839ef02c  mov     qword ptr [rbx+2A0h], 0
0x3839ef037  xor     esi, esi
0x3839ef039  cmp     r12d, 2
0x3839ef03d  jz      short loc_3839EF04F
0x3839ef03f  cmp     r12d, 4
0x3839ef043  jz      short loc_3839EF04F
0x3839ef045  cmp     r12d, 5
0x3839ef049  jnz     loc_3839EF326
0x3839ef04f  xor     r12d, r12d
0x3839ef052  mov     r13d, 1
0x3839ef058  mov     rcx, [rbp+4Fh+var_90]
0x3839ef05c  mov     r14, [rcx+10h]
0x3839ef060  add     r14, 130h
0x3839ef067  cmp     [rbp+4Fh+var_98], r13d
0x3839ef06b  jb      loc_3839EF2FD
0x3839ef071  mov     rax, [r14+0C8h]
0x3839ef078  mov     r15d, [r15+rax]
0x3839ef07c  test    r15d, 0C0000000h
0x3839ef083  jz      loc_3839EF230
0x3839ef089  bt      r15d, 1Eh
0x3839ef08e  jnb     short loc_3839EF0A1
0x3839ef090  mov     eax, r15d
0x3839ef093  and     eax, 1FFFFFFFh
0x3839ef098  cmp     eax, 0Dh
0x3839ef09b  jz      loc_3839EF230
0x3839ef0a1  xor     eax, eax
0x3839ef0a3  cmp     [r14+68h], rax
0x3839ef0a7  setnbe  al
0x3839ef0aa  test    eax, eax
0x3839ef0ac  jnz     short loc_3839EF0E0
0x3839ef0ae  movzx   eax, byte ptr [r14+7Ah]
0x3839ef0b3  test    al, al
0x3839ef0b5  jz      short loc_3839EF0E0
0x3839ef0b7  mov     rdx, [rcx+18h]
0x3839ef0bb  test    rdx, rdx
0x3839ef0be  jz      short loc_3839EF0E0
0x3839ef0c0  mov     rdx, [rdx+20h]
0x3839ef0c4  movzx   eax, al
0x3839ef0c7  lea     eax, [rax+rax*4]
0x3839ef0ca  cdqe
0x3839ef0cc  lea     rdx, [rdx+rax*8]; Src
0x3839ef0d0  lea     rcx, [r14+48h]; void *
0x3839ef0d4  mov     r8d, 28h ; '('; Size
0x3839ef0da  call    cs:__imp_memmove
0x3839ef0e0  mov     rdx, [r14+68h]
0x3839ef0e4  test    rdx, rdx
0x3839ef0e7  jz      loc_3839EF2B0
0x3839ef0ed  test    r12, r12
0x3839ef0f0  jnz     loc_3839EF192
0x3839ef0f6  mov     r12, rdx
0x3839ef0f9  mov     rax, [rbx+2C0h]
0x3839ef100  test    rax, rax
0x3839ef103  jz      short loc_3839EF111
0x3839ef105  mov     rax, [rax+7A0h]
0x3839ef10c  test    rax, rax
0x3839ef10f  jnz     short loc_3839EF118
0x3839ef111  lea     rax, [rbx+168h]
0x3839ef118  mov     r10, [rax+20h]
0x3839ef11c  add     r10, rdx
0x3839ef11f  or      r9, 0FFFFFFFFFFFFFFFFh
0x3839ef123  inc     r9
0x3839ef126  cmp     word ptr [r10+r9*2], 0
0x3839ef12c  jnz     short loc_3839EF123
0x3839ef12e  add     r9, r9
0x3839ef131  mov     rax, [rbx+210h]
0x3839ef138  mov     rcx, [rax+0C8h]
0x3839ef13f  mov     rdx, [rcx+438h]
0x3839ef146  mov     eax, [rdx+718h]
0x3839ef14c  mov     dword ptr [rbp+4Fh+var_68], eax
  ... truncated ...
```
