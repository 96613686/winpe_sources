# XEPackage0::HistoryTarget::ProcessEvent<XE_CollectedEvent<XE_LiveSessionMetadata>>(void *,XECollectedEvent const * const,XEEvent const * const)

- ea: `0x1005d8740`
- end: `0x1005d8d4f`
- name: `??$ProcessEvent@V?$XE_CollectedEvent@VXE_LiveSessionMetadata@@@@@HistoryTarget@XEPackage0@@AEAAHPEAXQEBUXECollectedEvent@@QEBUXEEvent@@@Z`
- size: `1551`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1005d3630`

## callees

- `0x100403070`
- `0x100411fb0`
- `0x10044c490`
- `0x10044c9b0`
- `0x10044dfd0`
- `0x10044ea20`
- `0x10044f4f0`
- `0x1004506b0`
- `0x100450830`
- `0x100451560`
- `0x1005d5420`
- `0x1005d56a0`
- `0x1005d5a40`
- `0x1005d8740`
- `0x1005d9060`
- `0x1005d94f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1005d8b63`
- `KERNEL32!GetCurrentThreadId` at `0x1005d8b86`
- `KERNEL32!GetCurrentThreadId` at `0x1005d8ba5`
- `KERNEL32!GetCurrentThreadId` at `0x1005d8b63`
- `KERNEL32!GetCurrentThreadId` at `0x1005d8b86`
- `KERNEL32!GetCurrentThreadId` at `0x1005d8ba5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005d882f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005d882f`
- `KERNEL32!GetTickCount` at `0x1005d87a7`
- `KERNEL32!GetTickCount` at `0x1005d87a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XEPackage0::HistoryTarget::ProcessEvent<XE_CollectedEvent<XE_LiveSessionMetadata>>(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4)
{
  DWORD TickCount; // ebx
  signed __int64 v8; // r14
  __int64 v9; // r14
  int v10; // eax
  _BOOL8 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // edx
  struct EventTransformer **v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r12
  __int64 v20; // rax
  struct EventTransformer *EventTransformer; // r13
  CXFixedTable *v22; // rsi
  CXFixedTable *v23; // rax
  struct XEEvent *v24; // r15
  unsigned int v25; // r14d
  __int64 Next; // rcx
  unsigned int *v27; // r15
  unsigned int v28; // edx
  int v29; // r15d
  int v30; // r8d
  __int64 v31; // r13
  const struct XPRESS9_ENCODER_T *v32; // r8
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rsi
  unsigned __int64 v35; // r15
  bool v36; // zf
  struct XE_PublishedDescriptor *v38; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+5Ch] [rbp-A4h] BYREF
  struct XEEvent *v43; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v44[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v45[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v46; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+84h] [rbp-7Ch] BYREF
  int v48; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v49; // [rsp+8Ch] [rbp-74h]
  __int64 v50; // [rsp+90h] [rbp-70h]
  void *v51; // [rsp+98h] [rbp-68h] BYREF
  struct XERelativeObjectId *v52; // [rsp+A0h] [rbp-60h]
  __int64 v53; // [rsp+A8h] [rbp-58h]
  _BOOL8 v54; // [rsp+B0h] [rbp-50h]
  __int64 v55[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  CXFixedTable *v58; // [rsp+E8h] [rbp-18h]
  _BYTE v59[48]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v60[528]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v61[8448]; // [rsp+960h] [rbp+860h] BYREF

  v57 = -2;
  v43 = (struct XEEvent *)a4;
  v50 = a3;
  *(_QWORD *)v45 = a2;
  if ( *(_DWORD *)(a1 + 20) && (*(_BYTE *)(a4 + 3) & 4) == 0 )
  {
    TickCount = GetTickCount();
    v8 = 0;
    if ( TickCount - *(_DWORD *)(a1 + 30776) >= *(_DWORD *)(a1 + 8292) )
    {
      v53 = *(_QWORD *)(a1 + 14232);
      v9 = v53;
      v10 = qword_100714F50(v53, 0xFFFFFFFFLL, 0);
      v11 = v10 == 0;
      v54 = v11;
      if ( !v10 && TickCount - *(_DWORD *)(a1 + 30776) >= *(_DWORD *)(a1 + 8292) )
      {
        *(_DWORD *)(a1 + 30776) = TickCount;
        ++*(_QWORD *)(a1 + 30832);
        *(_QWORD *)(a1 + 30792) = *(_QWORD *)(a1 + 30784);
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 30784));
        *(_QWORD *)(a1 + 14240) = *(_QWORD *)(a1 + 30784);
        v47 = 12345683;
        v48 = 12345681;
        v46 = 0;
        v40 = -1;
        if ( !XE_CXFileWriter::StreamWriteUnaligned(*(XE_CXFileWriter **)(a1 + 10608), &v47, 4u, &v46) )
          goto LABEL_11;
        v12 = *(_QWORD *)(a1 + 10608);
        v13 = *(_QWORD *)(v12 + 600) + 80LL * *(unsigned int *)(v12 + 612);
        v14 = (*(_DWORD *)(v13 + 72) + 15) & 0xFFFFFFF0;
        *(_DWORD *)(v13 + 72) = v14;
        if ( *(_DWORD *)(v13 + 24) == v14 && !(unsigned int)XE_CXFileWriter::SwitchPageAndWrite((XE_CXFileWriter *)v12) )
          goto LABEL_11;
        if ( !XE_CXFileWriter::StreamWriteUnaligned(*(XE_CXFileWriter **)(a1 + 10608), &v48, 4u, &v40)
          || (*(_DWORD *)(a1 + 14248) = *(_DWORD *)(a1 + 14280),
              *(_DWORD *)(a1 + 14252) = v40,
              !(unsigned int)XE_CXTimelineFile::AddFrame(
                               *(XE_CXTimelineFile **)(a1 + 14224),
                               (const struct CXTimelineEntry *)(a1 + 14240))) )
        {
LABEL_11:
          *(_DWORD *)(a1 + 20) = 0;
          *(_DWORD *)(a1 + 24) = 1;
        }
      }
      if ( v11 )
        qword_100714F58(v9);
      v8 = 0;
    }
    v49 = (unsigned int)qword_100714FE8() % *(_DWORD *)(a1 + 10600);
    v15 = (struct EventTransformer **)v49;
    v16 = *(_QWORD *)(a1 + 10592) + 32LL * v49;
    v52 = (struct XERelativeObjectId *)(a4 + 4);
    v17 = *(_QWORD *)(a1 + 8LL * (*(_DWORD *)(a4 + 4) & 0x3FF) + 32);
    if ( v17 )
    {
      v18 = (*(_DWORD *)(a4 + 4) >> 10) & 0x3FFFF;
      v19 = *(_QWORD *)(v17 + 8) + 24LL * ((unsigned int)v18 + *(_DWORD *)v17 * v49);
      v20 = *(_QWORD *)(v17 + 16);
      v15 = (struct EventTransformer **)(v20 + 8 * v18);
      if ( v19 )
      {
        EventTransformer = *v15;
        if ( *v15
          || (v51 = a2,
              (EventTransformer = HistoryTargetTables::CreateEventTransformer(
                                    (HistoryTargetTables *)(a1 + 32),
                                    a2,
                                    (struct XE_LiveSessionMetadata *)&v51,
                                    0,
                                    v43,
                                    (struct EventTransformer **)(v20 + 8 * v18))) != 0) )
        {
          v22 = *(CXFixedTable **)(v19 + 16);
          if ( v22 )
            goto LABEL_28;
          v44[1] = (unsigned __int64)&XE_API::sm_ServiceAPI;
          v23 = (CXFixedTable *)qword_100714F08(a2, 64);
          v22 = v23;
          v58 = v23;
          if ( v23 )
          {
            *((_QWORD *)v23 + 1) = 0;
            *((_QWORD *)v23 + 3) = 0;
            *((_QWORD *)v23 + 7) = 0;
            *((_QWORD *)v23 + 5) = 0;
            *((_QWORD *)v23 + 6) = 0;
            *((_QWORD *)v23 + 4) = 0;
          }
          else
          {
            v22 = 0;
          }
          if ( v22 )
          {
            if ( !(unsigned int)CXFixedTable::InitFixedTable(
                                  v22,
                                  0x2000u,
                                  *((_DWORD *)EventTransformer + 6),
                                  *((struct ColumnDescriptor **)EventTransformer + 4))
              || (v8 = _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 16), (signed __int64)v22, 0)) != 0 )
            {
              XE_Delete<CXFixedTable>(v22);
              v22 = (CXFixedTable *)v8;
            }
            if ( v22 )
            {
LABEL_28:
              v39 = -1;
              v44[0] = (unsigned __int64)a2;
              v55[0] = (__int64)v44;
              v55[1] = v50;
              v24 = v43;
              v55[2] = (__int64)v43;
              v56 = 0;
              v42 = 0;
              v25 = 1;
              Next = (unsigned __int16)XE_CollectedEvent<XE_LiveSessionMetadata>::GetNext(v55, v59);
              if ( (_DWORD)Next != 0xFFFF )
              {
                while ( v25 )
                {
                  if ( (unsigned int)Next < *((unsigned __int16 *)v24 + 18) )
                  {
                    v27 = (unsigned int *)(*((_QWORD *)EventTransformer + 2) + 8 * Next);
                    v28 = *v27;
                    if ( (*v27 & 0x2000) == 0 )
                    {
                      v41 = -1;
                      v25 = XEPackage0::HistoryTarget::ProcessPublishedElement(
                              (XEPackage0::HistoryTarget *)a1,
                              v28,
                              (const struct XE_PublishedDescriptor *)v59,
                              &v41);
                      v60[v27[1]] = v41;
                    }
                    v24 = v43;
                  }
                  else
                  {
                    v25 = XEPackage0::HistoryTarget::RunTransformationsForAction(
                            (XEPackage0::HistoryTarget *)a1,
                            (const struct XE_PublishedDescriptor *)v59,
                            EventTransformer,
                            v60,
                            &v42,
                            (struct OffRowActionData *)v61);
                  }
                  Next = (unsigned __int16)XE_CollectedEvent<XE_LiveSessionMetadata>::GetNext(v55, v59);
                  if ( (_DWORD)Next == 0xFFFF )
                    goto LABEL_36;
                }
                goto LABEL_57;
              }
LABEL_36:
              if ( !v25 )
              {
LABEL_57:
                *(_DWORD *)(a1 + 20) = 0;
                *(_DWORD *)(a1 + 24) = 1;
                return v25;
              }
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(v16 + 16), GetCurrentThreadId(), 0) )
              {
                while ( 1 )
                {
                  qword_100714F50(*(_QWORD *)(v16 + 24), 0xFFFFFFFFLL, 0);
                  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v16 + 16), GetCurrentThreadId(), 0) )
                    break;
                  qword_100714F58(*(_QWORD *)(v16 + 24));
                  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v16 + 16), GetCurrentThreadId(), 0) )
                    goto LABEL_40;
                }
                v29 = 1;
              }
              else
              {
LABEL_40:
                v29 = 0;
              }
              v45[0] = -1;
              if ( v42 )
              {
                v25 = XE_CXFileWriter::WriteDataWithSize(*(XE_CXFileWriter **)(v16 + 8), v61, 16 * v42, v45);
                if ( !v25 )
                  goto LABEL_52;
              }
              v30 = _InterlockedExchangeAdd64((volatile signed __int64 *)v16, 1u) + 1;
              v38 = EventTransformer;
              v31 = v50;
              XEPackage0::HistoryTarget::StoreEvent<XE_CollectedEvent<XE_LiveSessionMetadata>>(
                a1,
                *(_QWORD *)(v50 + 32),
                v30,
                v45[0],
                (__int64)v55,
                (__int64)v43,
                v38,
                (struct EventTransformer *)v60,
                (unsigned int *)v22);
              v33 = *(_QWORD *)(v31 + 32);
              if ( v33 < *(_QWORD *)v19 )
                *(_QWORD *)v19 = v33;
              if ( v33 > *(_QWORD *)(v19 + 8) )
                *(_QWORD *)(v19 + 8) = v33;
              if ( *(_DWORD *)(**((_QWORD **)v22 + 3) + 8LL) == 0x2000 )
              {
                if ( !v29 )
                  qword_100714F50(*(_QWORD *)(v16 + 24), 0xFFFFFFFFLL, 0);
                v25 = CXFixedTable::FlushTable(v22, *(struct XE_CXFileWriter **)(v16 + 8), v32, &v39);
                v34 = *(_QWORD *)v19;
                v35 = *(_QWORD *)(v19 + 8);
                *(_QWORD *)v19 = -1;
                *(_QWORD *)(v19 + 8) = 0;
              }
              else
              {
LABEL_52:
                v34 = v44[0];
                v36 = v29 == 0;
                v35 = v44[0];
                if ( v36 )
                {
LABEL_54:
                  *(_DWORD *)(v16 + 16) = 0;
                  if ( v25 )
                  {
                    if ( v39 == -1 )
                      return v25;
                    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 30816));
                    v25 = XEPackage0::HistoryTarget::WriteEventTableFrame(
                            (XEPackage0::HistoryTarget *)a1,
                            v39,
                            v49,
                            v52,
                            v34,
                            v35);
                    if ( v25 )
                      return v25;
                  }
                  goto LABEL_57;
                }
              }
              qword_100714F58(*(_QWORD *)(v16 + 24));
              goto LABEL_54;
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64, struct EventTransformer **))(*(_QWORD *)(a1 + 8) + 8LL))(a1 + 8, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1005d8740  push    rbp
0x1005d8742  push    rbx
0x1005d8743  push    rsi
0x1005d8744  push    rdi
0x1005d8745  push    r12
0x1005d8747  push    r13
0x1005d8749  push    r14
0x1005d874b  push    r15
0x1005d874d  lea     rbp, [rsp-2978h]
0x1005d8755  mov     eax, 2A78h
0x1005d875a  call    _alloca_probe
0x1005d875f  sub     rsp, rax
0x1005d8762  mov     [rbp+29B0h+var_29D0], 0FFFFFFFFFFFFFFFEh
0x1005d876a  mov     rax, cs:__security_cookie
0x1005d8771  xor     rax, rsp
0x1005d8774  mov     [rbp+29B0h+var_50], rax
0x1005d877b  mov     r13, r9
0x1005d877e  mov     [rsp+2AB0h+var_2A50], r9
0x1005d8783  mov     [rbp+29B0h+var_2A20], r8
0x1005d8787  mov     r15, rdx
0x1005d878a  mov     rdi, rcx
0x1005d878d  mov     qword ptr [rsp+2AB0h+var_2A38], rdx
0x1005d8792  cmp     dword ptr [rcx+14h], 0
0x1005d8796  jz      loc_1005D8D2A
0x1005d879c  test    byte ptr [r9+3], 4
0x1005d87a1  jnz     loc_1005D8D2A
0x1005d87a7  call    cs:__imp_GetTickCount
0x1005d87ad  mov     ebx, eax
0x1005d87af  mov     ecx, eax
0x1005d87b1  sub     ecx, [rdi+7838h]
0x1005d87b7  xor     r14d, r14d
0x1005d87ba  cmp     ecx, [rdi+2064h]
0x1005d87c0  jb      loc_1005D891D
0x1005d87c6  mov     r14, [rdi+3798h]
0x1005d87cd  mov     [rbp+29B0h+var_2A08], r14
0x1005d87d1  xor     esi, esi
0x1005d87d3  mov     [rbp+29B0h+var_2A00], rsi
0x1005d87d7  xor     r8d, r8d
0x1005d87da  mov     edx, 0FFFFFFFFh
0x1005d87df  mov     rcx, r14
0x1005d87e2  call    cs:qword_100714F50
0x1005d87e8  test    eax, eax
0x1005d87ea  setz    sil
0x1005d87ee  mov     dword ptr [rbp+29B0h+var_2A00], esi
0x1005d87f1  test    eax, eax
0x1005d87f3  jnz     loc_1005D890D
0x1005d87f9  mov     eax, ebx
0x1005d87fb  sub     eax, [rdi+7838h]
0x1005d8801  cmp     eax, [rdi+2064h]
0x1005d8807  jb      loc_1005D890D
0x1005d880d  mov     [rdi+7838h], ebx
0x1005d8813  inc     qword ptr [rdi+7870h]
0x1005d881a  mov     rax, [rdi+7840h]
0x1005d8821  mov     [rdi+7848h], rax
0x1005d8828  lea     rcx, [rdi+7840h]; lpSystemTimeAsFileTime
0x1005d882f  call    cs:__imp_GetSystemTimeAsFileTime
0x1005d8835  mov     rax, [rdi+7840h]
0x1005d883c  mov     [rdi+37A0h], rax
0x1005d8843  mov     [rbp+29B0h+var_2A2C], 0BC6153h
0x1005d884a  mov     [rbp+29B0h+var_2A28], 0BC6151h
0x1005d8851  xor     ebx, ebx
0x1005d8853  mov     [rbp+29B0h+var_2A30], ebx
0x1005d8856  mov     [rsp+2AB0h+var_2A5C], 0FFFFFFFFh
0x1005d885e  lea     r9, [rbp+29B0h+var_2A30]; unsigned int *
0x1005d8862  lea     r8d, [rbx+4]; unsigned int
0x1005d8866  lea     rdx, [rbp+29B0h+var_2A2C]; void *
0x1005d886a  mov     rcx, [rdi+2970h]; this
0x1005d8871  call    ?StreamWriteUnaligned@XE_CXFileWriter@@QEAAHQEBXIAEAK@Z; XE_CXFileWriter::StreamWriteUnaligned(void const * const,uint,ulong &)
0x1005d8876  test    eax, eax
0x1005d8878  jz      loc_1005D8903
0x1005d887e  mov     rcx, [rdi+2970h]; this
0x1005d8885  mov     eax, [rcx+264h]
0x1005d888b  lea     r9, [rax+rax*4]
0x1005d888f  shl     r9, 4
0x1005d8893  add     r9, [rcx+258h]
0x1005d889a  mov     edx, [r9+48h]
0x1005d889e  add     edx, 0Fh
0x1005d88a1  and     edx, 0FFFFFFF0h
0x1005d88a4  mov     [r9+48h], edx
0x1005d88a8  cmp     [r9+18h], edx
0x1005d88ac  jnz     short loc_1005D88B7
0x1005d88ae  call    ?SwitchPageAndWrite@XE_CXFileWriter@@AEAAHXZ; XE_CXFileWriter::SwitchPageAndWrite(void)
0x1005d88b3  test    eax, eax
0x1005d88b5  jz      short loc_1005D8903
0x1005d88b7  lea     r9, [rsp+2AB0h+var_2A5C]; unsigned int *
0x1005d88bc  mov     r8d, 4; unsigned int
0x1005d88c2  lea     rdx, [rbp+29B0h+var_2A28]; void *
0x1005d88c6  mov     rcx, [rdi+2970h]; this
0x1005d88cd  call    ?StreamWriteUnaligned@XE_CXFileWriter@@QEAAHQEBXIAEAK@Z; XE_CXFileWriter::StreamWriteUnaligned(void const * const,uint,ulong &)
0x1005d88d2  test    eax, eax
0x1005d88d4  jz      short loc_1005D8903
0x1005d88d6  mov     eax, [rdi+37C8h]
0x1005d88dc  mov     [rdi+37A8h], eax
0x1005d88e2  mov     eax, [rsp+2AB0h+var_2A5C]
0x1005d88e6  mov     [rdi+37ACh], eax
0x1005d88ec  lea     rdx, [rdi+37A0h]; struct CXTimelineEntry *
0x1005d88f3  mov     rcx, [rdi+3790h]; this
0x1005d88fa  call    ?AddFrame@XE_CXTimelineFile@@QEAAHAEBUCXTimelineEntry@@@Z; XE_CXTimelineFile::AddFrame(CXTimelineEntry const &)
0x1005d88ff  test    eax, eax
0x1005d8901  jnz     short loc_1005D890D
0x1005d8903  mov     [rdi+14h], ebx
0x1005d8906  mov     dword ptr [rdi+18h], 1
0x1005d890d  test    esi, esi
0x1005d890f  jz      short loc_1005D891A
0x1005d8911  mov     rcx, r14
0x1005d8914  call    cs:qword_100714F58
0x1005d891a  xor     r14d, r14d
0x1005d891d  call    cs:qword_100714FE8
0x1005d8923  xor     edx, edx
0x1005d8925  div     dword ptr [rdi+2968h]
0x1005d892b  mov     ecx, edx
0x1005d892d  mov     [rbp+29B0h+var_2A24], ecx
0x1005d8930  mov     ebx, edx
0x1005d8932  shl     rbx, 5
0x1005d8936  add     rbx, [rdi+2960h]
0x1005d893d  lea     rax, [r13+4]
0x1005d8941  mov     [rbp+29B0h+var_2A10], rax
0x1005d8945  mov     r8d, [rax]
0x1005d8948  mov     eax, r8d
0x1005d894b  and     eax, 3FFh
0x1005d8950  mov     r9, [rdi+rax*8+20h]
0x1005d8955  test    r9, r9
0x1005d8958  jz      loc_1005D8D20
0x1005d895e  shr     r8d, 0Ah
0x1005d8962  and     r8d, 3FFFFh
0x1005d8969  mov     eax, ecx
0x1005d896b  imul    eax, [r9]
0x1005d896f  add     eax, r8d
0x1005d8972  lea     rcx, [rax+rax*2]
0x1005d8976  mov     rax, [r9+8]
0x1005d897a  lea     r12, [rax+rcx*8]
0x1005d897e  mov     rax, [r9+10h]
0x1005d8982  lea     rdx, [rax+r8*8]
0x1005d8986  test    r12, r12
0x1005d8989  jz      loc_1005D8D20
0x1005d898f  mov     r13, [rdx]
0x1005d8992  test    r13, r13
0x1005d8995  jnz     short loc_1005D89C9
0x1005d8997  mov     [rbp+29B0h+var_2A18], r15
0x1005d899b  lea     rcx, [rdi+20h]; this
0x1005d899f  mov     [rsp+2AB0h+var_2A88], rdx; struct EventTransformer **
0x1005d89a4  mov     rax, [rsp+2AB0h+var_2A50]
0x1005d89a9  mov     [rsp+2AB0h+var_2A90], rax; struct XEEvent *
0x1005d89ae  xor     r9d, r9d; struct XE_IMetadata *
0x1005d89b1  lea     r8, [rbp+29B0h+var_2A18]; struct XE_LiveSessionMetadata *
0x1005d89b5  mov     rdx, r15; void *
0x1005d89b8  call    ?CreateEventTransformer@HistoryTargetTables@@QEAAPEAUEventTransformer@@PEAXPEAVXE_LiveSessionMetadata@@PEAVXE_IMetadata@@QEBUXEEvent@@PEAPEAU2@@Z; HistoryTargetTables::CreateEventTransformer(void *,XE_LiveSessionMetadata *,XE_IMetadata *,XEEvent const * const,EventTransformer * *)
0x1005d89bd  mov     r13, rax
0x1005d89c0  test    rax, rax
0x1005d89c3  jz      loc_1005D8D20
0x1005d89c9  mov     rsi, [r12+10h]
0x1005d89ce  test    rsi, rsi
0x1005d89d1  jnz     loc_1005D8A63
0x1005d89d7  lea     rax, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x1005d89de  mov     [rsp+2AB0h+var_2A40], rax
0x1005d89e3  lea     edx, [rsi+40h]
0x1005d89e6  mov     rcx, r15
0x1005d89e9  call    cs:qword_100714F08
0x1005d89ef  mov     rsi, rax
0x1005d89f2  mov     [rbp+29B0h+var_29C8], rax
0x1005d89f6  test    rax, rax
0x1005d89f9  jz      short loc_1005D8A19
0x1005d89fb  mov     [rax+8], r14
0x1005d89ff  mov     [rax+18h], r14
0x1005d8a03  mov     qword ptr [rax+38h], 0
0x1005d8a0b  mov     [rax+28h], r14
0x1005d8a0f  mov     [rax+30h], r14
0x1005d8a13  mov     [rax+20h], r14
0x1005d8a17  jmp     short loc_1005D8A1C
0x1005d8a19  mov     rsi, r14
0x1005d8a1c  test    rsi, rsi
0x1005d8a1f  jz      loc_1005D8D20
0x1005d8a25  mov     r9, [r13+20h]; struct ColumnDescriptor *
0x1005d8a29  mov     r8d, [r13+18h]; unsigned int
0x1005d8a2d  mov     edx, 2000h; unsigned int
0x1005d8a32  mov     rcx, rsi; this
0x1005d8a35  call    ?InitFixedTable@CXFixedTable@@QEAAHIIPEAUColumnDescriptor@@@Z; CXFixedTable::InitFixedTable(uint,uint,ColumnDescriptor *)
0x1005d8a3a  test    eax, eax
0x1005d8a3c  jz      short loc_1005D8A4C
0x1005d8a3e  xor     eax, eax
0x1005d8a40  lock cmpxchg [r12+10h], rsi
0x1005d8a47  mov     r14, rax
0x1005d8a4a  jz      short loc_1005D8A57
0x1005d8a4c  mov     rcx, rsi
0x1005d8a4f  call    ??$XE_Delete@VCXFixedTable@@@@YAXPEAVCXFixedTable@@@Z; XE_Delete<CXFixedTable>(CXFixedTable *)
0x1005d8a54  mov     rsi, r14
0x1005d8a57  xor     r14d, r14d
0x1005d8a5a  test    rsi, rsi
0x1005d8a5d  jz      loc_1005D8D20
0x1005d8a63  mov     [rsp+2AB0h+var_2A60], 0FFFFFFFFh
0x1005d8a6b  mov     [rsp+2AB0h+var_2A48], r15
0x1005d8a70  lea     rax, [rsp+2AB0h+var_2A48]
0x1005d8a75  mov     [rbp+29B0h+var_29F8], rax
0x1005d8a79  mov     rax, [rbp+29B0h+var_2A20]
0x1005d8a7d  mov     [rbp+29B0h+var_29F0], rax
0x1005d8a81  mov     r15, [rsp+2AB0h+var_2A50]
0x1005d8a86  mov     [rbp+29B0h+var_29E8], r15
0x1005d8a8a  mov     [rbp+29B0h+var_29E0], 0
0x1005d8a91  mov     [rsp+2AB0h+var_2A54], r14d
0x1005d8a96  mov     r14d, 1
0x1005d8a9c  lea     rdx, [rbp+29B0h+var_29C0]
0x1005d8aa0  lea     rcx, [rbp+29B0h+var_29F8]
0x1005d8aa4  call    ?GetNext@?$XE_CollectedEvent@VXE_LiveSessionMetadata@@@@QEAAGAEAVXE_PublishedDescriptor@@@Z; XE_CollectedEvent<XE_LiveSessionMetadata>::GetNext(XE_PublishedDescriptor &)
0x1005d8aa9  movzx   ecx, ax
0x1005d8aac  cmp     ecx, 0FFFFh
0x1005d8ab2  jz      loc_1005D8B5A
0x1005d8ab8  nop     dword ptr [rax+rax]
0x1005d8abc  nop     dword ptr [rax+00h]
0x1005d8ac0  test    r14d, r14d
0x1005d8ac3  jz      loc_1005D8D0D
0x1005d8ac9  movzx   eax, word ptr [r15+24h]
0x1005d8ace  cmp     ecx, eax
0x1005d8ad0  jb      short loc_1005D8B00
0x1005d8ad2  lea     rax, [rbp+29B0h+var_2150]
0x1005d8ad9  mov     [rsp+2AB0h+var_2A88], rax; struct OffRowActionData *
0x1005d8ade  lea     rax, [rsp+2AB0h+var_2A54]
0x1005d8ae3  mov     [rsp+2AB0h+var_2A90], rax; unsigned int *
0x1005d8ae8  lea     r9, [rbp+29B0h+var_2990]; unsigned int *
0x1005d8aec  mov     r8, r13; struct EventTransformer *
0x1005d8aef  lea     rdx, [rbp+29B0h+var_29C0]; struct XE_PublishedDescriptor *
0x1005d8af3  mov     rcx, rdi; this
0x1005d8af6  call    ?RunTransformationsForAction@HistoryTarget@XEPackage0@@AEAAHAEBVXE_PublishedDescriptor@@PEAUEventTransformer@@PEAIAEAIPEAUOffRowActionData@@@Z; XEPackage0::HistoryTarget::RunTransformationsForAction(XE_PublishedDescriptor const &,EventTransformer *,uint *,uint &,OffRowActionData *)
0x1005d8afb  mov     r14d, eax
0x1005d8afe  jmp     short loc_1005D8B3E
0x1005d8b00  mov     rax, [r13+10h]
0x1005d8b04  lea     r15, [rax+rcx*8]
0x1005d8b08  mov     edx, [r15]; unsigned int
0x1005d8b0b  bt      edx, 0Dh
0x1005d8b0f  jb      short loc_1005D8B39
0x1005d8b11  mov     [rsp+2AB0h+var_2A58], 0FFFFFFFFh
0x1005d8b19  lea     r9, [rsp+2AB0h+var_2A58]; unsigned int *
0x1005d8b1e  lea     r8, [rbp+29B0h+var_29C0]; struct XE_PublishedDescriptor *
0x1005d8b22  mov     rcx, rdi; this
0x1005d8b25  call    ?ProcessPublishedElement@HistoryTarget@XEPackage0@@AEAAHIAEBVXE_PublishedDescriptor@@AEAK@Z; XEPackage0::HistoryTarget::ProcessPublishedElement(uint,XE_PublishedDescriptor const &,ulong &)
0x1005d8b2a  mov     r14d, eax
0x1005d8b2d  mov     ecx, [r15+4]
0x1005d8b31  mov     eax, [rsp+2AB0h+var_2A58]
0x1005d8b35  mov     [rbp+rcx*4+29B0h+var_2990], eax
0x1005d8b39  mov     r15, [rsp+2AB0h+var_2A50]
0x1005d8b3e  lea     rdx, [rbp+29B0h+var_29C0]
0x1005d8b42  lea     rcx, [rbp+29B0h+var_29F8]
0x1005d8b46  call    ?GetNext@?$XE_CollectedEvent@VXE_LiveSessionMetadata@@@@QEAAGAEAVXE_PublishedDescriptor@@@Z; XE_CollectedEvent<XE_LiveSessionMetadata>::GetNext(XE_PublishedDescriptor &)
0x1005d8b4b  movzx   ecx, ax
0x1005d8b4e  cmp     ecx, 0FFFFh
0x1005d8b54  jnz     loc_1005D8AC0
0x1005d8b5a  test    r14d, r14d
0x1005d8b5d  jz      loc_1005D8D0D
0x1005d8b63  call    cs:__imp_GetCurrentThreadId
0x1005d8b69  mov     ecx, eax
0x1005d8b6b  xor     eax, eax
0x1005d8b6d  lock cmpxchg [rbx+10h], ecx
0x1005d8b72  jz      short loc_1005D8BB6
0x1005d8b74  xor     r8d, r8d
0x1005d8b77  mov     edx, 0FFFFFFFFh
0x1005d8b7c  mov     rcx, [rbx+18h]
0x1005d8b80  call    cs:qword_100714F50
0x1005d8b86  call    cs:__imp_GetCurrentThreadId
0x1005d8b8c  mov     ecx, eax
0x1005d8b8e  xor     eax, eax
0x1005d8b90  lock cmpxchg [rbx+10h], ecx
0x1005d8b95  jz      loc_1005D8CA9
0x1005d8b9b  mov     rcx, [rbx+18h]
0x1005d8b9f  call    cs:qword_100714F58
0x1005d8ba5  call    cs:__imp_GetCurrentThreadId
0x1005d8bab  mov     ecx, eax
0x1005d8bad  xor     eax, eax
0x1005d8baf  lock cmpxchg [rbx+10h], ecx
0x1005d8bb4  jnz     short loc_1005D8B74
0x1005d8bb6  xor     r15d, r15d
0x1005d8bb9  mov     [rsp+2AB0h+var_2A38], 0FFFFFFFFh
0x1005d8bc1  mov     r8d, [rsp+2AB0h+var_2A54]
0x1005d8bc6  test    r8d, r8d
0x1005d8bc9  jz      short loc_1005D8BEF
0x1005d8bcb  shl     r8d, 4; unsigned int
0x1005d8bcf  lea     r9, [rsp+2AB0h+var_2A38]; unsigned int *
0x1005d8bd4  lea     rdx, [rbp+29B0h+var_2150]; void *
0x1005d8bdb  mov     rcx, [rbx+8]; this
0x1005d8bdf  call    ?WriteDataWithSize@XE_CXFileWriter@@QEAAHQEBXIAEAK@Z; XE_CXFileWriter::WriteDataWithSize(void const * const,uint,ulong &)
0x1005d8be4  mov     r14d, eax
0x1005d8be7  test    eax, eax
0x1005d8be9  jz      loc_1005D8CB4
0x1005d8bef  mov     r8d, 1
0x1005d8bf5  lock xadd [rbx], r8
0x1005d8bfa  inc     r8; int
0x1005d8bfd  mov     [rsp+2AB0h+var_2A70], rsi; unsigned int *
0x1005d8c02  lea     rax, [rbp+29B0h+var_2990]
0x1005d8c06  mov     [rsp+2AB0h+var_2A78], rax; struct EventTransformer *
0x1005d8c0b  mov     [rsp+2AB0h+var_2A80], r13; struct XE_PublishedDescriptor *
0x1005d8c10  mov     rax, [rsp+2AB0h+var_2A50]
0x1005d8c15  mov     [rsp+2AB0h+var_2A88], rax; __int64
0x1005d8c1a  lea     rax, [rbp+29B0h+var_29F8]
0x1005d8c1e  mov     [rsp+2AB0h+var_2A90], rax; __int64
0x1005d8c23  mov     r9d, [rsp+2AB0h+var_2A38]; int
0x1005d8c28  mov     r13, [rbp+29B0h+var_2A20]
0x1005d8c2c  mov     rdx, [r13+20h]; int
0x1005d8c30  mov     rcx, rdi; int
0x1005d8c33  call    ??$StoreEvent@V?$XE_CollectedEvent@VXE_LiveSessionMetadata@@@@@HistoryTarget@XEPackage0@@AEAAX_K0KAEAV?$XE_CollectedEvent@VXE_LiveSessionMetadata@@@@QEBUXEEvent@@PEAUEventTransformer@@PEAIPEAVCXFixedTable@@@Z; XEPackage0::HistoryTarget::StoreEvent<XE_CollectedEvent<XE_LiveSessionMetadata>>(unsigned __int64,unsigned __int64,ulong,XE_CollectedEvent<XE_LiveSessionMetadata> &,XEEvent const * const,EventTransformer *,uint *,CXFixedTable *)
0x1005d8c38  mov     rax, [r13+20h]
0x1005d8c3c  cmp     rax, [r12]
0x1005d8c40  jnb     short loc_1005D8C46
  ... truncated ...
```
