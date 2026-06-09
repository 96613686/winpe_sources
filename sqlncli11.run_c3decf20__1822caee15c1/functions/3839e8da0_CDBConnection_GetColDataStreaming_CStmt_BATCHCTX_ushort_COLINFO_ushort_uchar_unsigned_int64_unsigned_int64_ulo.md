# CDBConnection::GetColDataStreaming(CStmt *,BATCHCTX *,ushort,COLINFO *,ushort,uchar *,unsigned __int64,unsigned __int64 *,ulong *,ulong,ulong,ushort *)

- ea: `0x3839e8da0`
- end: `0x3839e9395`
- name: `?GetColDataStreaming@CDBConnection@@QEAAHPEAVCStmt@@PEAVBATCHCTX@@GPEAUCOLINFO@@GPEAE_KPEA_KPEAKKKPEAG@Z`
- size: `1525`
- prototype: `int(CDBConnection *__hidden this, struct CStmt *, struct BATCHCTX *, unsigned __int16, struct COLINFO *, unsigned __int16, unsigned __int8 *, unsigned __int64, unsigned __int64 *, unsigned int *, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x3838b8f30`
- `0x3839e60f0`
- `0x3839e64e0`

## callees

- `0x3838427d0`
- `0x3838455b0`
- `0x3838457b0`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839d3300`
- `0x3839e8d20`
- `0x3839e8da0`
- `0x3839ea960`
- `0x383acdff0`

## import_xrefs

- `MSVCR100!memmove` at `0x3839e8f94`
- `MSVCR100!memmove` at `0x3839e928e`
- `MSVCR100!memmove` at `0x3839e8f94`
- `MSVCR100!memmove` at `0x3839e928e`

## pseudocode

```c
__int64 __fastcall CDBConnection::GetColDataStreaming(
        CDBConnection *this,
        struct CStmt *a2,
        struct BATCHCTX *a3,
        unsigned __int16 a4,
        struct COLINFO *a5,
        unsigned __int16 a6,
        unsigned __int8 *a7,
        size_t Size,
        unsigned __int64 *a9,
        unsigned int *a10,
        unsigned int a11,
        _WORD *a12)
{
  unsigned int *v12; // rsi
  struct COLINFO *v16; // r13
  unsigned int v17; // r12d
  int DataLen; // edi
  BOOL v20; // r12d
  unsigned __int64 v21; // r15
  size_t v22; // rbx
  size_t v23; // rsi
  unsigned __int8 *XlatCharBuf; // rax
  unsigned __int8 *v25; // rcx
  unsigned int *v26; // rcx
  unsigned __int8 *v27; // rbx
  unsigned __int8 *v28; // rax
  size_t v29; // rsi
  int v30; // eax
  size_t v31; // rax
  bool v32; // zf
  size_t v33; // rax
  unsigned __int8 *v34; // rax
  unsigned __int8 *v35; // rbx
  size_t v36; // r12
  int Data; // eax
  unsigned __int64 v38; // r9
  size_t v39; // r15
  int v40; // eax
  unsigned __int8 *v41; // rax
  int v42; // eax
  unsigned __int64 v43; // r13
  unsigned int *v44; // rsi
  size_t v45; // r12
  size_t v46; // rax
  size_t v47; // r13
  char *v48; // rcx
  wchar_t *v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdx
  struct CErrorData *v52; // [rsp+38h] [rbp-51h]
  unsigned __int64 v53; // [rsp+40h] [rbp-49h] BYREF
  size_t v54; // [rsp+48h] [rbp-41h] BYREF
  size_t v55; // [rsp+50h] [rbp-39h] BYREF
  size_t v56; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int8 *v57; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int8 *v58; // [rsp+68h] [rbp-21h] BYREF
  __int64 v59; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int8 *v60; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v61[8]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int8 v64; // [rsp+E8h] [rbp+5Fh] BYREF

  v12 = a10;
  *a9 = 0;
  *v12 = 0;
  if ( a4 != *((_WORD *)a3 + 72) )
    *((_QWORD *)a2 + 93) = 0;
  v16 = a5;
  v17 = a11;
  DataLen = BATCHCTX::GetDataLen(a3, a2, a4, a5, a11, &v54, (int *)&a10);
  if ( DataLen < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
        bidTraceW(off_383B432D0[0], 902185, off_383B49128[0], (unsigned int)DataLen);
    }
    goto LABEL_37;
  }
  if ( (_DWORD)a10 )
  {
    *v12 = 3;
    if ( *((_DWORD *)v16 + 5) )
      goto LABEL_36;
  }
  else
  {
    if ( (*((_BYTE *)this + 1812) & 8) != 0 )
    {
      DataLen = BATCHCTX::FlushData(a3, a2, a4, v16, v17);
      if ( DataLen < 0 )
        goto LABEL_37;
      if ( *((_DWORD *)v16 + 5) )
        *a12 |= 2u;
      *((_WORD *)this + 906) &= ~8u;
      return 1;
    }
    v20 = a6 == 129 && (*((_BYTE *)v16 + 60) & 1) != 0;
    v21 = *((_QWORD *)a2 + 93);
    v22 = Size;
    if ( v21 )
    {
      v23 = *((_QWORD *)a2 + 93);
      if ( Size < v21 )
        v23 = Size;
      XlatCharBuf = CStmt::GetXlatCharBuf(a2);
      memcpy(a7, XlatCharBuf, v23);
      v25 = a7;
      *a9 += v23;
      v26 = (unsigned int *)&v25[v23];
      a10 = v26;
      v56 = v21 - v23;
      *((_QWORD *)a2 + 93) = v21 - v23;
      v22 -= v23;
      if ( !v22 )
      {
        if ( v23 < v21 )
        {
          v27 = &CStmt::GetXlatCharBuf(a2)[v23];
          v28 = CStmt::GetXlatCharBuf(a2);
          memmove(v28, v27, v56);
        }
        goto LABEL_37;
      }
    }
    else
    {
      v26 = (unsigned int *)a7;
      a10 = (unsigned int *)a7;
    }
    v29 = v54;
    if ( !v54 )
      goto LABEL_37;
    v53 = 0;
    if ( v20 )
    {
      v33 = 1024;
      v53 = v54;
      if ( v22 < 0x400 )
        v33 = v22;
      v54 = v33;
      while ( 1 )
      {
        if ( v33 < v29 )
          v29 = v33;
        v34 = CStmt::GetXlatCharBuf(a2);
        v35 = v34;
        if ( !v34 )
          break;
        v36 = *((_QWORD *)a2 + 92);
        v60 = v34;
        v55 = 0;
        Data = BATCHCTX::FetchData(a3, a2, &v60, v29, 1, a11, &v55, &v53);
        DataLen = Data;
        if ( Data < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceHR(off_383B432D0[0], 1036297, (unsigned int)Data);
          goto LABEL_37;
        }
        v39 = v55;
        if ( !(unsigned int)CDBConnection::IsDBCSCharAligned(
                              *((_DWORD *)v16 + 14),
                              (unsigned int)v35,
                              (unsigned __int8 *)v55,
                              v38) )
        {
          v58 = &v64;
          v56 = 0;
          v40 = BATCHCTX::FetchData(a3, a2, &v58, 1u, 1, a11, &v56, v61);
          DataLen = v40;
          if ( v40 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              bidTraceHR(off_383B432D0[0], 1059849, (unsigned int)v40);
            goto LABEL_37;
          }
          if ( v56 )
          {
            if ( v35 != CStmt::GetXlatCharBuf(a2) )
            {
              v41 = CStmt::GetXlatCharBuf(a2);
              memcpy(v41, v35, v39);
              v35 = CStmt::GetXlatCharBuf(a2);
            }
            v35[v39++] = v64;
          }
        }
        LODWORD(v52) = *((_DWORD *)v16 + 14);
        v42 = CDBConnection::XlateCharFromServer(
                this,
                (const char *)v35,
                v39,
                (char *)v35,
                v36,
                &v59,
                (struct CStmt *)((char *)a2 + 136),
                v52,
                v53);
        if ( v42 == -1 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v48 = off_383B432D0[0];
            if ( off_383B49128[0] )
            {
              v49 = off_383B49128[0];
              v50 = 2147500037LL;
              v51 = 1088553;
LABEL_69:
              bidTraceW(v48, v51, v49, v50);
              return 0xFFFFFFFFLL;
            }
          }
          return 0xFFFFFFFFLL;
        }
        v43 = v59;
        v44 = a10;
        v45 = v59;
        if ( v42 == 1 )
          DataLen = 265937;
        if ( v54 < v59 )
          v45 = v54;
        memcpy(a10, v35, v45);
        v46 = v54;
        *a9 += v45;
        v33 = v46 - v45;
        a10 = (unsigned int *)((char *)v44 + v45);
        v29 = v53;
        v54 = v33;
        if ( !v33 )
        {
          if ( v45 < v43 )
          {
            v47 = v43 - v45;
            memmove(v35, &v35[v45], v47);
            *((_QWORD *)a2 + 93) = v47;
          }
LABEL_64:
          if ( !*((_DWORD *)a5 + 5) )
            goto LABEL_37;
          v32 = v39 == v29;
LABEL_35:
          if ( v32 )
LABEL_36:
            *a12 |= 2u;
          goto LABEL_37;
        }
        if ( v39 == v53 )
          goto LABEL_64;
        v16 = a5;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        v48 = off_383B432D0[0];
        if ( off_383B49128[0] )
        {
          v49 = off_383B49128[0];
          v50 = 2147942414LL;
          v51 = 1023017;
          goto LABEL_69;
        }
      }
      return 0xFFFFFFFFLL;
    }
    v57 = (unsigned __int8 *)v26;
    if ( v22 < v54 )
      v29 = v22;
    v55 = 0;
    v30 = BATCHCTX::FetchData(a3, a2, &v57, v29, 1, a11, &v55, &v53);
    DataLen = v30;
    if ( v30 >= 0 )
    {
      v31 = v55;
      *a9 += v55;
      if ( *((_DWORD *)v16 + 5) )
      {
        v32 = v31 == v53;
        goto LABEL_35;
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      bidTraceHR(off_383B432D0[0], 992265, (unsigned int)v30);
    }
  }
LABEL_37:
  if ( !DataLen )
    return 0;
  if ( DataLen < 0 )
  {
    if ( DataLen == -2147023436 )
      return 2;
    return 0xFFFFFFFFLL;
  }
  return DataLen == 265937;
}

```

## disassembly

```asm
0x3839e8da0  mov     [rsp-8+arg_8], rbx
0x3839e8da5  mov     [rsp-8+arg_10], r8
0x3839e8daa  mov     [rsp-8+arg_0], rcx
0x3839e8daf  push    rbp
0x3839e8db0  push    rsi
0x3839e8db1  push    rdi
0x3839e8db2  push    r12
0x3839e8db4  push    r13
0x3839e8db6  push    r14
0x3839e8db8  push    r15
0x3839e8dba  lea     rbp, [rsp-7]
0x3839e8dbf  sub     rsp, 90h
0x3839e8dc6  mov     rax, [rbp+37h+arg_40]
0x3839e8dcd  mov     rsi, [rbp+37h+arg_48]
0x3839e8dd4  xor     ecx, ecx
0x3839e8dd6  mov     [rax], rcx
0x3839e8dd9  mov     [rsi], ecx
0x3839e8ddb  movzx   ebx, r9w
0x3839e8ddf  mov     r15, r8
0x3839e8de2  mov     r14, rdx
0x3839e8de5  cmp     r9w, [r8+90h]
0x3839e8ded  jz      short loc_3839E8DF6
0x3839e8def  mov     [rdx+2E8h], rcx
0x3839e8df6  mov     r13, [rbp+37h+arg_20]
0x3839e8dfa  mov     r12d, [rbp+37h+arg_50]
0x3839e8e01  lea     rax, [rbp+37h+arg_48]
0x3839e8e08  mov     [rsp+0C0h+var_90], rax; int *
0x3839e8e0d  lea     rax, [rbp+37h+var_78]
0x3839e8e11  mov     r9, r13; struct BaseMetaInfo *
0x3839e8e14  mov     [rsp+0C0h+var_98], rax; unsigned __int64 *
0x3839e8e19  movzx   r8d, bx; unsigned __int16
0x3839e8e1d  mov     rcx, r15; this
0x3839e8e20  mov     dword ptr [rsp+0C0h+var_A0], r12d; unsigned int
0x3839e8e25  call    ?GetDataLen@BATCHCTX@@QEAAJPEAXGPEAUBaseMetaInfo@@KPEA_KPEAH@Z; BATCHCTX::GetDataLen(void *,ushort,BaseMetaInfo *,ulong,unsigned __int64 *,int *)
0x3839e8e2a  mov     edi, eax
0x3839e8e2c  mov     eax, 40ED1h
0x3839e8e31  test    edi, edi
0x3839e8e33  jns     short loc_3839E8E7A
0x3839e8e35  test    byte ptr cs:_bidGblFlags, 2
0x3839e8e3c  jz      loc_3839E9062
0x3839e8e42  mov     rcx, cs:off_383B432D0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839e8e49  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839e8e50  test    rax, rax
0x3839e8e53  jz      loc_3839E905D
0x3839e8e59  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839e8e60  mov     r9d, edi
0x3839e8e63  mov     edx, 0DC429h
0x3839e8e68  mov     dword ptr [rsp+0C0h+var_A0], 371h
0x3839e8e70  call    _bidTraceW
0x3839e8e75  jmp     loc_3839E905D
0x3839e8e7a  cmp     dword ptr [rbp+37h+arg_48], 0
0x3839e8e81  jz      short loc_3839E8E99
0x3839e8e83  mov     dword ptr [rsi], 3
0x3839e8e89  cmp     dword ptr [r13+14h], 0
0x3839e8e8e  jz      loc_3839E9062
0x3839e8e94  jmp     loc_3839E9052
0x3839e8e99  mov     rsi, [rbp+37h+arg_0]
0x3839e8e9d  test    byte ptr [rsi+714h], 8
0x3839e8ea4  jz      short loc_3839E8EEF
0x3839e8ea6  mov     r9, r13; struct BaseMetaInfo *
0x3839e8ea9  movzx   r8d, bx; unsigned __int16
0x3839e8ead  mov     rdx, r14; void *
0x3839e8eb0  mov     rcx, r15; this
0x3839e8eb3  mov     dword ptr [rsp+0C0h+var_A0], r12d; unsigned int
0x3839e8eb8  call    ?FlushData@BATCHCTX@@QEAAJPEAXGPEAUBaseMetaInfo@@K@Z; BATCHCTX::FlushData(void *,ushort,BaseMetaInfo *,ulong)
0x3839e8ebd  mov     edi, eax
0x3839e8ebf  test    eax, eax
0x3839e8ec1  js      loc_3839E905D
0x3839e8ec7  cmp     dword ptr [r13+14h], 0
0x3839e8ecc  jz      short loc_3839E8ED9
0x3839e8ece  mov     rax, [rbp+37h+arg_58]
0x3839e8ed5  or      word ptr [rax], 2
0x3839e8ed9  mov     eax, 0FFF7h
0x3839e8ede  and     [rsi+714h], ax
0x3839e8ee5  mov     eax, 1
0x3839e8eea  jmp     loc_3839E92EF
0x3839e8eef  mov     eax, 81h
0x3839e8ef4  cmp     [rbp+37h+arg_28], ax
0x3839e8ef8  jnz     short loc_3839E8F07
0x3839e8efa  test    byte ptr [r13+3Ch], 1
0x3839e8eff  jz      short loc_3839E8F07
0x3839e8f01  lea     r12d, [rax-80h]
0x3839e8f05  jmp     short loc_3839E8F0A
0x3839e8f07  xor     r12d, r12d
0x3839e8f0a  mov     r15, [r14+2E8h]
0x3839e8f11  mov     rbx, [rbp+37h+Size]
0x3839e8f15  test    r15, r15
0x3839e8f18  jz      loc_3839E8F9F
0x3839e8f1e  mov     rsi, r15
0x3839e8f21  cmp     rbx, r15
0x3839e8f24  mov     rcx, r14; this
0x3839e8f27  cmovb   rsi, rbx
0x3839e8f2b  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e8f30  mov     rcx, [rbp+37h+arg_30]; void *
0x3839e8f34  mov     rdx, rax; Src
0x3839e8f37  mov     r8, rsi; Size
0x3839e8f3a  call    memcpy
0x3839e8f3f  mov     rax, [rbp+37h+arg_40]
0x3839e8f46  mov     rcx, [rbp+37h+arg_30]
0x3839e8f4a  add     [rax], rsi
0x3839e8f4d  add     rcx, rsi
0x3839e8f50  mov     rax, r15
0x3839e8f53  sub     rax, rsi
0x3839e8f56  mov     [rbp+37h+arg_48], rcx
0x3839e8f5d  mov     [rbp+37h+var_68], rax
0x3839e8f61  mov     [r14+2E8h], rax
0x3839e8f68  sub     rbx, rsi
0x3839e8f6b  jnz     short loc_3839E8FAA
0x3839e8f6d  cmp     rsi, r15
0x3839e8f70  jnb     loc_3839E905D
0x3839e8f76  mov     rcx, r14; this
0x3839e8f79  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e8f7e  mov     rcx, r14; this
0x3839e8f81  lea     rbx, [rsi+rax]
0x3839e8f85  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e8f8a  mov     r8, [rbp+37h+var_68]; Size
0x3839e8f8e  mov     rcx, rax; void *
0x3839e8f91  mov     rdx, rbx; Src
0x3839e8f94  call    cs:__imp_memmove
0x3839e8f9a  jmp     loc_3839E905D
0x3839e8f9f  mov     rcx, [rbp+37h+arg_30]
0x3839e8fa3  mov     [rbp+37h+arg_48], rcx
0x3839e8faa  mov     rsi, [rbp+37h+var_78]
0x3839e8fae  test    rsi, rsi
0x3839e8fb1  jz      loc_3839E905D
0x3839e8fb7  mov     [rbp+37h+var_80], 0
0x3839e8fbf  test    r12d, r12d
0x3839e8fc2  jnz     loc_3839E9071
0x3839e8fc8  lea     rax, [rbp+37h+var_80]
0x3839e8fcc  mov     [rbp+37h+var_60], rcx
0x3839e8fd0  mov     rcx, [rbp+37h+arg_10]; this
0x3839e8fd4  mov     [rsp+0C0h+var_88], rax; unsigned __int64 *
0x3839e8fd9  lea     rax, [rbp+37h+var_70]
0x3839e8fdd  cmp     rbx, rsi
0x3839e8fe0  mov     [rsp+0C0h+var_90], rax; unsigned __int64 *
0x3839e8fe5  mov     eax, [rbp+37h+arg_50]
0x3839e8feb  cmovb   rsi, rbx
0x3839e8fef  mov     dword ptr [rsp+0C0h+var_98], eax; unsigned int
0x3839e8ff3  lea     r8, [rbp+37h+var_60]; unsigned __int8 **
0x3839e8ff7  mov     r9, rsi; unsigned __int64
0x3839e8ffa  mov     rdx, r14; void *
0x3839e8ffd  mov     dword ptr [rsp+0C0h+var_A0], 1; int
0x3839e9005  mov     [rbp+37h+var_70], 0
0x3839e900d  call    ?FetchData@BATCHCTX@@QEAAJPEAXPEAPEAE_KHKPEA_K3@Z; BATCHCTX::FetchData(void *,uchar * *,unsigned __int64,int,ulong,unsigned __int64 *,unsigned __int64 *)
0x3839e9012  mov     edi, eax
0x3839e9014  test    eax, eax
0x3839e9016  jns     short loc_3839E9037
0x3839e9018  test    byte ptr cs:_bidGblFlags, 2
0x3839e901f  jz      short loc_3839E905D
0x3839e9021  mov     rcx, cs:off_383B432D0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839e9028  mov     r8d, eax
0x3839e902b  mov     edx, 0F2409h
0x3839e9030  call    _bidTraceHR
0x3839e9035  jmp     short loc_3839E905D
0x3839e9037  mov     rcx, [rbp+37h+arg_40]
0x3839e903e  mov     rax, [rbp+37h+var_70]
0x3839e9042  add     [rcx], rax
0x3839e9045  cmp     dword ptr [r13+14h], 0
0x3839e904a  jz      short loc_3839E905D
0x3839e904c  cmp     rax, [rbp+37h+var_80]
0x3839e9050  jnz     short loc_3839E905D
0x3839e9052  mov     rax, [rbp+37h+arg_58]
0x3839e9059  or      word ptr [rax], 2
0x3839e905d  mov     eax, 40ED1h
0x3839e9062  test    edi, edi
0x3839e9064  jnz     loc_3839E936B
0x3839e906a  xor     eax, eax
0x3839e906c  jmp     loc_3839E92EF
0x3839e9071  mov     eax, 400h
0x3839e9076  mov     [rbp+37h+var_80], rsi
0x3839e907a  cmp     rbx, rax
0x3839e907d  cmovb   rax, rbx
0x3839e9081  mov     [rbp+37h+var_78], rax
0x3839e9085  nop     word ptr [rax+rax+00000000h]
0x3839e9090  cmp     rax, rsi
0x3839e9093  mov     rcx, r14; this
0x3839e9096  cmovb   rsi, rax
0x3839e909a  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e909f  mov     rbx, rax
0x3839e90a2  test    rax, rax
0x3839e90a5  jz      loc_3839E9330
0x3839e90ab  mov     r12, [r14+2E0h]
0x3839e90b2  mov     [rbp+37h+var_48], rax
0x3839e90b6  lea     rax, [rbp+37h+var_80]
0x3839e90ba  mov     [rsp+0C0h+var_88], rax; unsigned __int64 *
0x3839e90bf  lea     rax, [rbp+37h+var_70]
0x3839e90c3  mov     r9, rsi; unsigned __int64
0x3839e90c6  mov     rsi, [rbp+37h+arg_10]
0x3839e90ca  mov     [rsp+0C0h+var_90], rax; unsigned __int64 *
0x3839e90cf  mov     eax, [rbp+37h+arg_50]
0x3839e90d5  mov     dword ptr [rsp+0C0h+var_98], eax; unsigned int
0x3839e90d9  lea     r8, [rbp+37h+var_48]; unsigned __int8 **
0x3839e90dd  mov     rdx, r14; void *
0x3839e90e0  mov     rcx, rsi; this
0x3839e90e3  mov     dword ptr [rsp+0C0h+var_A0], 1; int
0x3839e90eb  mov     [rbp+37h+var_70], 0
0x3839e90f3  call    ?FetchData@BATCHCTX@@QEAAJPEAXPEAPEAE_KHKPEA_K3@Z; BATCHCTX::FetchData(void *,uchar * *,unsigned __int64,int,ulong,unsigned __int64 *,unsigned __int64 *)
0x3839e90f8  mov     edi, eax
0x3839e90fa  test    eax, eax
0x3839e90fc  js      loc_3839E930A
0x3839e9102  mov     r15, [rbp+37h+var_70]
0x3839e9106  mov     ecx, [r13+38h]; CodePage
0x3839e910a  mov     rdx, rbx; unsigned int
0x3839e910d  mov     r8, r15; unsigned __int8 *
0x3839e9110  call    ?IsDBCSCharAligned@CDBConnection@@QEAAHIPEAE_K@Z; CDBConnection::IsDBCSCharAligned(uint,uchar *,unsigned __int64)
0x3839e9115  test    eax, eax
0x3839e9117  jnz     loc_3839E91B1
0x3839e911d  lea     rax, [rbp+37h+arg_18]
0x3839e9121  lea     r8, [rbp+37h+var_58]; unsigned __int8 **
0x3839e9125  mov     r9d, 1; unsigned __int64
0x3839e912b  mov     [rbp+37h+var_58], rax
0x3839e912f  lea     rax, [rbp+37h+var_40]
0x3839e9133  mov     rdx, r14; void *
0x3839e9136  mov     [rsp+0C0h+var_88], rax; unsigned __int64 *
0x3839e913b  lea     rax, [rbp+37h+var_68]
0x3839e913f  mov     rcx, rsi; this
0x3839e9142  mov     [rsp+0C0h+var_90], rax; unsigned __int64 *
0x3839e9147  mov     eax, [rbp+37h+arg_50]
0x3839e914d  mov     [rbp+37h+var_68], 0
0x3839e9155  mov     dword ptr [rsp+0C0h+var_98], eax; unsigned int
0x3839e9159  mov     dword ptr [rsp+0C0h+var_A0], 1; int
0x3839e9161  call    ?FetchData@BATCHCTX@@QEAAJPEAXPEAPEAE_KHKPEA_K3@Z; BATCHCTX::FetchData(void *,uchar * *,unsigned __int64,int,ulong,unsigned __int64 *,unsigned __int64 *)
0x3839e9166  mov     edi, eax
0x3839e9168  test    eax, eax
0x3839e916a  js      loc_3839E9256
0x3839e9170  cmp     [rbp+37h+var_68], 0
0x3839e9175  jz      short loc_3839E91B1
0x3839e9177  mov     rcx, r14; this
0x3839e917a  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e917f  cmp     rbx, rax
0x3839e9182  jz      short loc_3839E91A5
0x3839e9184  mov     rcx, r14; this
0x3839e9187  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e918c  mov     r8, r15; Size
0x3839e918f  mov     rdx, rbx; Src
0x3839e9192  mov     rcx, rax; void *
0x3839e9195  call    memcpy
0x3839e919a  mov     rcx, r14; this
0x3839e919d  call    ?GetXlatCharBuf@CStmt@@QEAAPEAEXZ; CStmt::GetXlatCharBuf(void)
0x3839e91a2  mov     rbx, rax
0x3839e91a5  movzx   eax, [rbp+37h+arg_18]
0x3839e91a9  inc     r15
0x3839e91ac  mov     [rbx+r15-1], al
0x3839e91b1  mov     eax, [r13+38h]
0x3839e91b5  lea     rcx, [r14+88h]
0x3839e91bc  mov     r9, rbx; char *
0x3839e91bf  mov     dword ptr [rsp+0C0h+var_88], eax; struct CErrorData *
0x3839e91c3  mov     [rsp+0C0h+var_90], rcx; struct CErrorData *
0x3839e91c8  mov     rcx, [rbp+37h+arg_0]; this
0x3839e91cc  lea     rax, [rbp+37h+var_50]
0x3839e91d0  mov     r8, r15; __int64
0x3839e91d3  mov     rdx, rbx; char *
0x3839e91d6  mov     [rsp+0C0h+var_98], rax; __int64 *
0x3839e91db  mov     [rsp+0C0h+var_A0], r12; Size
0x3839e91e0  call    ?XlateCharFromServer@CDBConnection@@QEAAHPEBD_JPEAD1PEA_JHPEAVCErrorData@@I@Z; CDBConnection::XlateCharFromServer(char const *,__int64,char *,__int64,__int64 *,int,CErrorData *,uint)
0x3839e91e5  cmp     eax, 0FFFFFFFFh
0x3839e91e8  jz      loc_3839E92B1
0x3839e91ee  mov     r13, [rbp+37h+var_50]
0x3839e91f2  mov     rsi, [rbp+37h+arg_48]
0x3839e91f9  cmp     eax, 1
0x3839e91fc  mov     eax, 40ED1h
0x3839e9201  mov     r12, r13
0x3839e9204  mov     rdx, rbx; Src
0x3839e9207  cmovz   edi, eax
0x3839e920a  mov     rax, [rbp+37h+var_78]
0x3839e920e  mov     rcx, rsi; void *
0x3839e9211  cmp     rax, r13
0x3839e9214  cmovb   r12, rax
0x3839e9218  mov     r8, r12; Size
0x3839e921b  call    memcpy
0x3839e9220  mov     rax, [rbp+37h+var_78]
0x3839e9224  mov     rcx, [rbp+37h+arg_40]
0x3839e922b  add     [rcx], r12
0x3839e922e  add     rsi, r12
0x3839e9231  sub     rax, r12
0x3839e9234  mov     [rbp+37h+arg_48], rsi
0x3839e923b  mov     rsi, [rbp+37h+var_80]
0x3839e923f  mov     [rbp+37h+var_78], rax
0x3839e9243  test    rax, rax
0x3839e9246  jz      short loc_3839E927C
0x3839e9248  cmp     r15, rsi
0x3839e924b  jz      short loc_3839E929B
0x3839e924d  mov     r13, [rbp+37h+arg_20]
0x3839e9251  jmp     loc_3839E9090
0x3839e9256  test    byte ptr cs:_bidGblFlags, 2
0x3839e925d  jz      loc_3839E905D
0x3839e9263  mov     rcx, cs:off_383B432D0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839e926a  mov     r8d, eax
0x3839e926d  mov     edx, 102C09h
0x3839e9272  call    _bidTraceHR
0x3839e9277  jmp     loc_3839E905D
0x3839e927c  cmp     r12, r13
0x3839e927f  jnb     short loc_3839E929B
0x3839e9281  sub     r13, r12
0x3839e9284  lea     rdx, [rbx+r12]; Src
0x3839e9288  mov     rcx, rbx; void *
0x3839e928b  mov     r8, r13; Size
0x3839e928e  call    cs:__imp_memmove
0x3839e9294  mov     [r14+2E8h], r13
0x3839e929b  mov     rax, [rbp+37h+arg_20]
  ... truncated ...
```
