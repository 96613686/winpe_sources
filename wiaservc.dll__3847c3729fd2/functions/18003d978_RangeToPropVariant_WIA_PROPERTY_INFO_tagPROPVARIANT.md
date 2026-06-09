# RangeToPropVariant(_WIA_PROPERTY_INFO *,tagPROPVARIANT *)

- ea: `0x18003d978`
- end: `0x18003dc02`
- name: `?RangeToPropVariant@@YAJPEAU_WIA_PROPERTY_INFO@@PEAUtagPROPVARIANT@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct _WIA_PROPERTY_INFO *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180018180`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x18003d978`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18003da46`
- `ole32!CoTaskMemAlloc` at `0x18003da8d`
- `ole32!CoTaskMemAlloc` at `0x18003dad4`
- `ole32!CoTaskMemAlloc` at `0x18003db23`
- `ole32!CoTaskMemAlloc` at `0x18003db61`
- `ole32!CoTaskMemAlloc` at `0x18003da46`
- `ole32!CoTaskMemAlloc` at `0x18003da8d`
- `ole32!CoTaskMemAlloc` at `0x18003dad4`
- `ole32!CoTaskMemAlloc` at `0x18003db23`
- `ole32!CoTaskMemAlloc` at `0x18003db61`

## pseudocode

```c
__int64 __fastcall RangeToPropVariant(struct _WIA_PROPERTY_INFO *a1, struct tagPROPVARIANT *a2)
{
  struct tagWiaTraceData_Type *v4; // rax
  char *v5; // rdx
  unsigned int v6; // r8d
  unsigned int v7; // esi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  BYTE *v13; // rax
  BYTE *v14; // rax
  BYTE *v15; // rax
  BYTE *v16; // rax
  __int64 v17; // rcx
  BYTE *v18; // rax
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-88h]
  _BYTE v26[120]; // [rsp+30h] [rbp-78h] BYREF

  v4 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::RangeToPropVariant");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v26, v5, v6, "RangeToPropVariant", lpMem, v4);
  v7 = 0;
  a2->vt = *((_WORD *)a1 + 2) | 0x1000;
  if ( *((_WORD *)a1 + 2) == 2 )
    goto LABEL_19;
  if ( *((_WORD *)a1 + 2) == 3 )
  {
LABEL_9:
    v13 = (BYTE *)CoTaskMemAlloc(0x10u);
    if ( v13 )
    {
      a2->bstrblobVal.pData = v13;
      a2->lVal = 4;
      *(_DWORD *)v13 = *((_DWORD *)a1 + 2);
      *((_DWORD *)a2->bstrblobVal.pData + 1) = *((_DWORD *)a1 + 3);
      *((_DWORD *)a2->bstrblobVal.pData + 2) = *((_DWORD *)a1 + 4);
      *((_DWORD *)a2->bstrblobVal.pData + 3) = *((_DWORD *)a1 + 5);
      goto LABEL_22;
    }
LABEL_21:
    v19 = (char *)WiaTrace_TraceLog("RangeToPropVariant, unable to allocate range list");
    WriteDbgTraceErrorWI("RangeToPropVariant", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void **)WiaTrace_Trace("RangeToPropVariant, unable to allocate range list");
    WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"RangeToPropVariant", 1, v21);
    v7 = -2147024882;
    goto LABEL_22;
  }
  if ( *((_WORD *)a1 + 2) != 4 )
  {
    if ( *((_WORD *)a1 + 2) == 5 )
    {
      v15 = (BYTE *)CoTaskMemAlloc(0x20u);
      if ( v15 )
      {
        a2->bstrblobVal.pData = v15;
        a2->lVal = 4;
        *(_QWORD *)v15 = *((_QWORD *)a1 + 1);
        *((_QWORD *)a2->bstrblobVal.pData + 1) = *((_QWORD *)a1 + 2);
        *((_QWORD *)a2->bstrblobVal.pData + 2) = *((_QWORD *)a1 + 3);
        *((_QWORD *)a2->bstrblobVal.pData + 3) = *((_QWORD *)a1 + 4);
        goto LABEL_22;
      }
      goto LABEL_21;
    }
    if ( *((_WORD *)a1 + 2) == 17 )
    {
      v14 = (BYTE *)CoTaskMemAlloc(4u);
      if ( v14 )
      {
        a2->bstrblobVal.pData = v14;
        a2->lVal = 4;
        *v14 = *((_BYTE *)a1 + 8);
        a2->bstrblobVal.pData[1] = *((_BYTE *)a1 + 12);
        a2->bstrblobVal.pData[2] = *((_BYTE *)a1 + 16);
        a2->bstrblobVal.pData[3] = *((_BYTE *)a1 + 20);
        goto LABEL_22;
      }
      goto LABEL_21;
    }
    if ( *((_WORD *)a1 + 2) != 18 )
    {
      if ( *((_WORD *)a1 + 2) != 19 )
      {
        v8 = (char *)WiaTrace_TraceLog("RangeToPropVariant, type not supported");
        WriteDbgTraceErrorWI("RangeToPropVariant", v8);
        WiaTrcLib::Free((WiaTrcLib *)v8, v9);
        v10 = (void **)WiaTrace_Trace("RangeToPropVariant, type not supported");
        WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"RangeToPropVariant", 1, v10);
        v7 = -2147024809;
        goto LABEL_22;
      }
      goto LABEL_9;
    }
LABEL_19:
    v18 = (BYTE *)CoTaskMemAlloc(8u);
    if ( v18 )
    {
      a2->bstrblobVal.pData = v18;
      a2->lVal = 4;
      *(_WORD *)v18 = *((_WORD *)a1 + 4);
      *((_WORD *)a2->bstrblobVal.pData + 1) = *((_WORD *)a1 + 6);
      *((_WORD *)a2->bstrblobVal.pData + 2) = *((_WORD *)a1 + 8);
      *((_WORD *)a2->bstrblobVal.pData + 3) = *((_WORD *)a1 + 10);
      goto LABEL_22;
    }
    goto LABEL_21;
  }
  v16 = (BYTE *)CoTaskMemAlloc(0x10u);
  if ( !v16 )
    goto LABEL_21;
  a2->lVal = 4;
  v17 = 0;
  a2->bstrblobVal.pData = v16;
  do
  {
    *(float *)&a2->bstrblobVal.pData[4 * v17] = *((double *)a1 + v17 + 1);
    ++v17;
  }
  while ( v17 != 4 );
LABEL_22:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v26);
  return v7;
}

```

## disassembly

```asm
0x18003d978  push    rbx
0x18003d97a  push    rbp
0x18003d97b  push    rsi
0x18003d97c  push    rdi
0x18003d97d  sub     rsp, 88h
0x18003d984  mov     rdi, rcx
0x18003d987  mov     rbx, rdx
0x18003d98a  lea     rcx, aRangetopropvar_2; "::RangeToPropVariant"
0x18003d991  call    WiaTrace_Trace
0x18003d996  lea     rbp, aRangetopropvar; "RangeToPropVariant"
0x18003d99d  mov     [rsp+0A8h+var_80], rax; struct tagWiaTraceData_Type *
0x18003d9a2  mov     r9, rbp; char *
0x18003d9a5  lea     rcx, [rsp+0A8h+var_78]; this
0x18003d9aa  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18003d9af  mov     eax, 1000h
0x18003d9b4  xor     esi, esi
0x18003d9b6  or      ax, [rdi+4]
0x18003d9ba  mov     [rbx], ax
0x18003d9bd  movzx   ecx, word ptr [rdi+4]
0x18003d9c1  sub     ecx, 2
0x18003d9c4  jz      loc_18003DB5C
0x18003d9ca  sub     ecx, 1
0x18003d9cd  jz      short loc_18003DA41
0x18003d9cf  sub     ecx, 1
0x18003d9d2  jz      loc_18003DB1E
0x18003d9d8  sub     ecx, 1
0x18003d9db  jz      loc_18003DACF
0x18003d9e1  sub     ecx, 0Ch
0x18003d9e4  jz      loc_18003DA88
0x18003d9ea  sub     ecx, 1
0x18003d9ed  jz      loc_18003DB5C
0x18003d9f3  cmp     ecx, 1
0x18003d9f6  jz      short loc_18003DA41
0x18003d9f8  lea     rcx, aRangetopropvar_0; "RangeToPropVariant, type not supported"
0x18003d9ff  call    WiaTrace_TraceLog
0x18003da04  mov     rdx, rax; char *
0x18003da07  mov     rcx, rbp; char *
0x18003da0a  mov     rbx, rax
0x18003da0d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003da12  mov     rcx, rbx; this
0x18003da15  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003da1a  lea     rcx, aRangetopropvar_0; "RangeToPropVariant, type not supported"
0x18003da21  call    WiaTrace_Trace
0x18003da26  lea     r9d, [rsi+1]; int
0x18003da2a  mov     [rsp+0A8h+lpMem], rax; lpMem
0x18003da2f  mov     r8, rbp; int
0x18003da32  call    WiaTrace_ProcessTrace_Ex
0x18003da37  mov     esi, 80070057h
0x18003da3c  jmp     loc_18003DBEA
0x18003da41  mov     ecx, 10h; cb
0x18003da46  call    cs:__imp_CoTaskMemAlloc
0x18003da4c  test    rax, rax
0x18003da4f  jz      loc_18003DBA4
0x18003da55  mov     [rbx+10h], rax
0x18003da59  mov     dword ptr [rbx+8], 4
0x18003da60  mov     ecx, [rdi+8]
0x18003da63  mov     [rax], ecx
0x18003da65  mov     rcx, [rbx+10h]
0x18003da69  mov     eax, [rdi+0Ch]
0x18003da6c  mov     [rcx+4], eax
0x18003da6f  mov     rcx, [rbx+10h]
0x18003da73  mov     eax, [rdi+10h]
0x18003da76  mov     [rcx+8], eax
0x18003da79  mov     rcx, [rbx+10h]
0x18003da7d  mov     eax, [rdi+14h]
0x18003da80  mov     [rcx+0Ch], eax
0x18003da83  jmp     loc_18003DBEA
0x18003da88  mov     ecx, 4; cb
0x18003da8d  call    cs:__imp_CoTaskMemAlloc
0x18003da93  test    rax, rax
0x18003da96  jz      loc_18003DBA4
0x18003da9c  mov     [rbx+10h], rax
0x18003daa0  mov     dword ptr [rbx+8], 4
0x18003daa7  mov     cl, [rdi+8]
0x18003daaa  mov     [rax], cl
0x18003daac  mov     rcx, [rbx+10h]
0x18003dab0  mov     al, [rdi+0Ch]
0x18003dab3  mov     [rcx+1], al
0x18003dab6  mov     rcx, [rbx+10h]
0x18003daba  mov     al, [rdi+10h]
0x18003dabd  mov     [rcx+2], al
0x18003dac0  mov     rcx, [rbx+10h]
0x18003dac4  mov     al, [rdi+14h]
0x18003dac7  mov     [rcx+3], al
0x18003daca  jmp     loc_18003DBEA
0x18003dacf  mov     ecx, 20h ; ' '; cb
0x18003dad4  call    cs:__imp_CoTaskMemAlloc
0x18003dada  test    rax, rax
0x18003dadd  jz      loc_18003DBA4
0x18003dae3  mov     [rbx+10h], rax
0x18003dae7  mov     dword ptr [rbx+8], 4
0x18003daee  mov     rcx, [rdi+8]
0x18003daf2  mov     [rax], rcx
0x18003daf5  mov     rcx, [rbx+10h]
0x18003daf9  mov     rax, [rdi+10h]
0x18003dafd  mov     [rcx+8], rax
0x18003db01  mov     rcx, [rbx+10h]
0x18003db05  mov     rax, [rdi+18h]
0x18003db09  mov     [rcx+10h], rax
0x18003db0d  mov     rcx, [rbx+10h]
0x18003db11  mov     rax, [rdi+20h]
0x18003db15  mov     [rcx+18h], rax
0x18003db19  jmp     loc_18003DBEA
0x18003db1e  mov     ecx, 10h; cb
0x18003db23  call    cs:__imp_CoTaskMemAlloc
0x18003db29  test    rax, rax
0x18003db2c  jz      short loc_18003DBA4
0x18003db2e  mov     dword ptr [rbx+8], 4
0x18003db35  xor     ecx, ecx
0x18003db37  mov     [rbx+10h], rax
0x18003db3b  movsd   xmm0, qword ptr [rdi+rcx*8+8]
0x18003db41  mov     rax, [rbx+10h]
0x18003db45  cvtpd2ps xmm0, xmm0
0x18003db49  movss   dword ptr [rax+rcx*4], xmm0
0x18003db4e  inc     rcx
0x18003db51  cmp     rcx, 4
0x18003db55  jnz     short loc_18003DB3B
0x18003db57  jmp     loc_18003DBEA
0x18003db5c  mov     ecx, 8; cb
0x18003db61  call    cs:__imp_CoTaskMemAlloc
0x18003db67  test    rax, rax
0x18003db6a  jz      short loc_18003DBA4
0x18003db6c  mov     [rbx+10h], rax
0x18003db70  mov     dword ptr [rbx+8], 4
0x18003db77  movzx   ecx, word ptr [rdi+8]
0x18003db7b  mov     [rax], cx
0x18003db7e  mov     rcx, [rbx+10h]
0x18003db82  movzx   eax, word ptr [rdi+0Ch]
0x18003db86  mov     [rcx+2], ax
0x18003db8a  mov     rcx, [rbx+10h]
0x18003db8e  movzx   eax, word ptr [rdi+10h]
0x18003db92  mov     [rcx+4], ax
0x18003db96  mov     rcx, [rbx+10h]
0x18003db9a  movzx   eax, word ptr [rdi+14h]
0x18003db9e  mov     [rcx+6], ax
0x18003dba2  jmp     short loc_18003DBEA
0x18003dba4  lea     rcx, aRangetopropvar_1; "RangeToPropVariant, unable to allocate "...
0x18003dbab  call    WiaTrace_TraceLog
0x18003dbb0  mov     rdx, rax; char *
0x18003dbb3  mov     rcx, rbp; char *
0x18003dbb6  mov     rbx, rax
0x18003dbb9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003dbbe  mov     rcx, rbx; this
0x18003dbc1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003dbc6  lea     rcx, aRangetopropvar_1; "RangeToPropVariant, unable to allocate "...
0x18003dbcd  call    WiaTrace_Trace
0x18003dbd2  mov     r9d, 1; int
0x18003dbd8  mov     [rsp+0A8h+lpMem], rax; lpMem
0x18003dbdd  mov     r8, rbp; int
0x18003dbe0  call    WiaTrace_ProcessTrace_Ex
0x18003dbe5  mov     esi, 8007000Eh
0x18003dbea  lea     rcx, [rsp+0A8h+var_78]; this
0x18003dbef  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18003dbf4  mov     eax, esi
0x18003dbf6  add     rsp, 88h
0x18003dbfd  pop     rdi
0x18003dbfe  pop     rsi
0x18003dbff  pop     rbp
0x18003dc00  pop     rbx
0x18003dc01  retn
```
