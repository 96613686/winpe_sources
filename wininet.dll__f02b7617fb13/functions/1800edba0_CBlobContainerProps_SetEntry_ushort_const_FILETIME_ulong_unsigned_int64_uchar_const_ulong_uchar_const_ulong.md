# CBlobContainerProps::SetEntry(ushort const *,_FILETIME,ulong,unsigned __int64,uchar const *,ulong,uchar const *,ulong)

- ea: `0x1800edba0`
- end: `0x1800ee160`
- name: `?SetEntry@CBlobContainerProps@@QEAAJPEBGU_FILETIME@@K_KPEBEK3K@Z`
- size: `1472`
- prototype: `int(CBlobContainerProps *__hidden this, const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned __int64, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800ed970`

## callees

- `0x18007ec9c`
- `0x1800807c8`
- `0x180082700`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800edba0`
- `0x1800ee168`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e2f9c`
- `0x1801e3c78`
- `0x1801e3f04`

## import_xrefs

- `ESENT!JetSetCurrentIndex2W` at `0x1800ee0cf`
- `ESENT!JetSetCurrentIndex2W` at `0x1800ee0cf`
- `ESENT!JetSetColumn` at `0x1800edd61`
- `ESENT!JetSetColumn` at `0x1800eddd6`
- `ESENT!JetSetColumn` at `0x1800ede80`
- `ESENT!JetSetColumn` at `0x1800edee9`
- `ESENT!JetSetColumn` at `0x1800edf23`
- `ESENT!JetSetColumn` at `0x1800ee051`
- `ESENT!JetSetColumn` at `0x1800edd61`
- `ESENT!JetSetColumn` at `0x1800eddd6`
- `ESENT!JetSetColumn` at `0x1800ede80`
- `ESENT!JetSetColumn` at `0x1800edee9`
- `ESENT!JetSetColumn` at `0x1800edf23`
- `ESENT!JetSetColumn` at `0x1800ee051`
- `ESENT!JetCommitTransaction` at `0x1800edf67`
- `ESENT!JetCommitTransaction` at `0x1800edf67`
- `ESENT!JetUpdate` at `0x1800edf46`
- `ESENT!JetUpdate` at `0x1800edf46`
- `ESENT!JetPrepareUpdate` at `0x1800edd0b`
- `ESENT!JetPrepareUpdate` at `0x1800ee076`
- `ESENT!JetPrepareUpdate` at `0x1800edd0b`
- `ESENT!JetPrepareUpdate` at `0x1800ee076`
- `ESENT!JetRollback` at `0x1800edf83`
- `ESENT!JetRollback` at `0x1800edf83`
- `ESENT!JetBeginTransaction` at `0x1800edcc5`
- `ESENT!JetBeginTransaction` at `0x1800edcc5`

## pseudocode

```c
__int64 __fastcall CBlobContainerProps::SetEntry(
        CBlobContainerProps *this,
        const unsigned __int16 *a2,
        struct _FILETIME a3,
        int a4,
        unsigned __int64 a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int8 *a8,
        unsigned int a9)
{
  unsigned int v9; // r14d
  __int64 v10; // r13
  unsigned int cbData; // r12d
  unsigned __int64 v14; // rax
  CInFlightLocks *v15; // rcx
  JET_ERR v16; // ebx
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  struct CJetContext *v20; // rdi
  JET_ERR v21; // eax
  int v22; // eax
  JET_ERR v23; // eax
  int v24; // edx
  int v25; // r8d
  JET_TABLEID v26; // r14
  JET_SESID v27; // r15
  __int64 v28; // rcx
  JET_COLUMNID v29; // ebx
  JET_ERR v30; // eax
  unsigned int v31; // eax
  int v32; // r8d
  int v33; // edx
  JET_TABLEID v34; // r15
  JET_SESID v35; // r12
  __int64 v36; // rcx
  JET_COLUMNID v37; // r14d
  unsigned int v38; // ebx
  const unsigned __int8 *v39; // r13
  JET_ERR v40; // eax
  unsigned int v41; // eax
  JET_ERR v42; // eax
  JET_ERR v43; // eax
  JET_TABLEID v45; // rdx
  JET_SESID v46; // rcx
  JET_ERR v47; // eax
  struct CJetContext *v48; // [rsp+48h] [rbp-39h] BYREF
  struct CInFlightEntry *v49; // [rsp+50h] [rbp-31h] BYREF
  const unsigned __int8 *v50; // [rsp+58h] [rbp-29h]
  int v51; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int64 v52; // [rsp+68h] [rbp-19h] BYREF
  struct _FILETIME pvData; // [rsp+70h] [rbp-11h] BYREF

  v9 = 0;
  v10 = (__int64)a6;
  pvData = a3;
  v51 = a4;
  v50 = a8;
  v52 = 0;
  v49 = 0;
  v48 = 0;
  cbData = a7;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_Siqd((_DWORD)this, (_DWORD)a2, a3.dwLowDateTime, (_DWORD)a2, a3.dwLowDateTime, (__int64)a6, a7);
  v14 = WxComputeUrlHash(a2, a2);
  v15 = (CInFlightLocks *)*((_QWORD *)this + 8);
  v52 = v14;
  v16 = CInFlightLocks::AcquireLock(v15, v14, &v49);
  if ( v16 >= 0 )
  {
    v16 = CJetContextList::AcquireContext(*((CJetContextList **)this + 9), &v48, 0);
    if ( v16 >= 0 )
    {
      v20 = v48;
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_qdSD(v18, v17, v19, (_DWORD)v48, 0, (__int64)L"HashEntryIdIndex", 0);
      if ( *((_DWORD *)v20 + 12) )
      {
        v45 = *((_QWORD *)v20 + 4);
        v46 = *((_QWORD *)v20 + 2);
        *((_DWORD *)v20 + 12) = -1;
        v47 = JetSetCurrentIndex2W(v46, v45, L"HashEntryIdIndex", 0);
        v16 = HRESULTFromJET_ERR(v47, 1);
        if ( v16 >= 0 )
          *((_DWORD *)v20 + 12) = 0;
      }
      else
      {
        v16 = 0;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)v16);
      if ( v16 >= 0 )
      {
        v21 = JetBeginTransaction(*((_QWORD *)v20 + 2));
        v16 = HRESULTFromJET_ERR(v21, 1);
        if ( v16 >= 0 )
        {
          v22 = SeekToBlobEntry(v20, a2, v52);
          v16 = v22;
          if ( v22 < 0 )
            goto LABEL_32;
          if ( !v22 )
          {
            v9 = 2;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_(1036, 24, WPP_449f88becdf731b1b0126ce91da74e00_Traceguids);
          }
          v23 = JetPrepareUpdate(*((_QWORD *)v20 + 2), *((_QWORD *)v20 + 4), v9);
          v16 = HRESULTFromJET_ERR(v23, 1);
          if ( v16 < 0 )
            goto LABEL_32;
          if ( !v9 )
          {
            v16 = CJetContext::SetStringColumn(v20, 2u, a2);
            if ( v16 < 0 )
              goto LABEL_39;
            v16 = JetSetColumn(
                    *((_QWORD *)v20 + 2),
                    *((_QWORD *)v20 + 4),
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL) + 4LL),
                    &v52,
                    8u,
                    0,
                    0);
            if ( v16 < 0 )
              goto LABEL_39;
          }
          v16 = JetSetColumn(
                  *((_QWORD *)v20 + 2),
                  *((_QWORD *)v20 + 4),
                  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL) + 12LL),
                  &pvData,
                  8u,
                  0,
                  0);
          if ( v16 < 0 )
            goto LABEL_39;
          v26 = *((_QWORD *)v20 + 4);
          v27 = *((_QWORD *)v20 + 2);
          v28 = *(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL);
          v29 = *(_DWORD *)(v28 + 24);
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_iiiqd(v28, v24, v25, v27, v26, v29, v10);
          v30 = JetSetColumn(v27, v26, v29, (const void *)(v10 & -(__int64)(cbData != 0)), cbData, 0, 0);
          v31 = HRESULTFromJET_ERR(v30, 1);
          v16 = v31;
          LOBYTE(v33) = BYTE1(xmmword_180266B60);
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          {
            WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v31);
            LOBYTE(v33) = BYTE1(xmmword_180266B60);
          }
          if ( v16 < 0 )
            goto LABEL_39;
          v34 = *((_QWORD *)v20 + 4);
          v35 = *((_QWORD *)v20 + 2);
          v36 = *(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL);
          v37 = *(_DWORD *)(v36 + 28);
          v38 = a9;
          v39 = v50;
          if ( (v33 & 0x10) != 0 )
            WPP_SF_iiiqd(v36, v33, v32, v35, v34, v37, (__int64)v50);
          v40 = JetSetColumn(v35, v34, v37, (const void *)((unsigned __int64)v39 & -(__int64)(v38 != 0)), v38, 0, 0);
          v41 = HRESULTFromJET_ERR(v40, 1);
          v16 = v41;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v41);
          if ( v16 < 0
            || (v16 = JetSetColumn(
                        *((_QWORD *)v20 + 2),
                        *((_QWORD *)v20 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL) + 16LL),
                        &v51,
                        4u,
                        0,
                        0),
                v16 < 0)
            || (v16 = JetSetColumn(
                        *((_QWORD *)v20 + 2),
                        *((_QWORD *)v20 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 5) + 8LL) + 20LL),
                        &a5,
                        8u,
                        0,
                        0),
                v16 < 0)
            || (v42 = JetUpdate(*((_QWORD *)v20 + 2), *((_QWORD *)v20 + 4), 0, 0, 0),
                v16 = HRESULTFromJET_ERR(v42, 1),
                v16 < 0) )
          {
LABEL_39:
            JetPrepareUpdate(*((_QWORD *)v20 + 2), *((_QWORD *)v20 + 4), 3u);
            goto LABEL_32;
          }
          v43 = JetCommitTransaction(*((_QWORD *)v20 + 2), 1u);
          v16 = HRESULTFromJET_ERR(v43, 1);
          if ( v16 < 0 )
          {
LABEL_32:
            JetRollback(*((_QWORD *)v20 + 2), 0);
            goto LABEL_33;
          }
          CJetContextList::ReleaseContext(*((CJetContextList **)this + 9), &v48);
          CInFlightLocks::ReleaseLock(*((CInFlightLocks **)this + 8), &v49);
          v16 = 0;
        }
      }
    }
  }
LABEL_33:
  CJetContextList::ReleaseContext(*((CJetContextList **)this + 9), &v48);
  CInFlightLocks::ReleaseLock(*((CInFlightLocks **)this + 8), &v49);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 25, WPP_449f88becdf731b1b0126ce91da74e00_Traceguids, (unsigned int)v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800edba0  push    rbp
0x1800edba2  push    rbx
0x1800edba3  push    rsi
0x1800edba4  push    rdi
0x1800edba5  push    r12
0x1800edba7  push    r13
0x1800edba9  push    r14
0x1800edbab  push    r15
0x1800edbad  lea     rbp, [rsp-7]
0x1800edbb2  sub     rsp, 88h
0x1800edbb9  mov     rax, cs:__security_cookie
0x1800edbc0  xor     rax, rsp
0x1800edbc3  mov     [rbp+3Fh+var_48], rax
0x1800edbc7  mov     rax, [rbp+3Fh+arg_38]
0x1800edbce  xor     r14d, r14d
0x1800edbd1  mov     r13, [rbp+3Fh+arg_28]
0x1800edbd5  mov     r15, rdx
0x1800edbd8  mov     [rbp+3Fh+pvData], r8
0x1800edbdc  mov     rsi, rcx
0x1800edbdf  mov     [rbp+3Fh+var_60], r9d
0x1800edbe3  mov     [rbp+3Fh+var_68], rax
0x1800edbe7  mov     [rbp+3Fh+var_7C], r14d
0x1800edbeb  mov     [rbp+3Fh+var_58], r14
0x1800edbef  mov     [rbp+3Fh+var_70], r14
0x1800edbf3  mov     [rbp+3Fh+var_78], r14
0x1800edbf7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800edbfe  mov     r12d, [rbp+3Fh+arg_30]
0x1800edc02  jz      short loc_1800EDC1B
0x1800edc04  mov     dword ptr [rsp+0C0h+psetinfo], r12d
0x1800edc09  mov     r9, rdx
0x1800edc0c  mov     qword ptr [rsp+0C0h+grbit], r13
0x1800edc11  mov     qword ptr [rsp+0C0h+cbData], r8
0x1800edc16  call    WPP_SF_Siqd
0x1800edc1b  mov     rcx, r15
0x1800edc1e  call    WxComputeUrlHash
0x1800edc23  mov     rcx, [rsi+40h]; this
0x1800edc27  lea     r8, [rbp+3Fh+var_70]; struct CInFlightEntry **
0x1800edc2b  mov     rdx, rax; unsigned __int64
0x1800edc2e  mov     [rbp+3Fh+var_58], rax
0x1800edc32  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x1800edc37  mov     ebx, eax
0x1800edc39  test    eax, eax
0x1800edc3b  js      loc_1800EE0AE
0x1800edc41  mov     rcx, [rsi+48h]; this
0x1800edc45  lea     rdx, [rbp+3Fh+var_78]; struct CJetContext **
0x1800edc49  xor     r8d, r8d; int *
0x1800edc4c  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800edc51  mov     ebx, eax
0x1800edc53  test    eax, eax
0x1800edc55  js      loc_1800EE0F4
0x1800edc5b  mov     rdi, [rbp+3Fh+var_78]
0x1800edc5f  mov     [rbp+3Fh+var_7C], r14d
0x1800edc63  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800edc6a  lea     rbx, aHashentryidind; "HashEntryIdIndex"
0x1800edc71  jz      short loc_1800EDC8A
0x1800edc73  mov     dword ptr [rsp+0C0h+psetinfo], r14d
0x1800edc78  mov     r9, rdi
0x1800edc7b  mov     qword ptr [rsp+0C0h+grbit], rbx
0x1800edc80  mov     [rsp+0C0h+cbData], r14d
0x1800edc85  call    WPP_SF_qdSD
0x1800edc8a  cmp     [rdi+30h], r14d
0x1800edc8e  jnz     loc_1800EE0BA
0x1800edc94  mov     ebx, r14d
0x1800edc97  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800edc9e  jz      short loc_1800EDCB9
0x1800edca0  mov     edx, 0Eh
0x1800edca5  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800edcac  mov     ecx, 40Ch
0x1800edcb1  mov     r9d, ebx
0x1800edcb4  call    WPP_SF_d
0x1800edcb9  test    ebx, ebx
0x1800edcbb  js      loc_1800EE100
0x1800edcc1  mov     rcx, [rdi+10h]; sesid
0x1800edcc5  call    cs:__imp_JetBeginTransaction
0x1800edccb  mov     ecx, eax; int
0x1800edccd  mov     edx, 1; int
0x1800edcd2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800edcd7  mov     ebx, eax
0x1800edcd9  test    eax, eax
0x1800edcdb  js      loc_1800EDF89
0x1800edce1  mov     r8, [rbp+3Fh+var_58]; unsigned __int64
0x1800edce5  mov     rdx, r15; unsigned __int16 *
0x1800edce8  mov     rcx, rdi; struct CJetContext *
0x1800edceb  call    ?SeekToBlobEntry@@YAJPEAVCJetContext@@PEBG_K@Z; SeekToBlobEntry(CJetContext *,ushort const *,unsigned __int64)
0x1800edcf0  mov     ebx, eax
0x1800edcf2  test    eax, eax
0x1800edcf4  js      loc_1800EE10C
0x1800edcfa  jz      loc_1800EE081
0x1800edd00  mov     rdx, [rdi+20h]; tableid
0x1800edd04  mov     r8d, r14d; prep
0x1800edd07  mov     rcx, [rdi+10h]; sesid
0x1800edd0b  call    cs:__imp_JetPrepareUpdate
0x1800edd11  mov     ecx, eax; int
0x1800edd13  mov     edx, 1; int
0x1800edd18  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800edd1d  mov     ebx, eax
0x1800edd1f  test    eax, eax
0x1800edd21  js      loc_1800EDF7D
0x1800edd27  test    r14d, r14d
0x1800edd2a  jz      loc_1800EE006
0x1800edd30  mov     rax, [rdi+28h]
0x1800edd34  lea     r9, [rbp+3Fh+pvData]; pvData
0x1800edd38  mov     rdx, [rdi+20h]; tableid
0x1800edd3c  mov     rcx, [rdi+10h]; sesid
0x1800edd40  mov     [rsp+0C0h+psetinfo], 0; psetinfo
0x1800edd49  mov     r8, [rax+8]
0x1800edd4d  mov     [rsp+0C0h+grbit], 0; grbit
0x1800edd55  mov     [rsp+0C0h+cbData], 8; cbData
0x1800edd5d  mov     r8d, [r8+0Ch]; columnid
0x1800edd61  call    cs:__imp_JetSetColumn
0x1800edd67  mov     ebx, eax
0x1800edd69  test    eax, eax
0x1800edd6b  js      loc_1800EE124
0x1800edd71  mov     rax, [rdi+28h]
0x1800edd75  mov     r14, [rdi+20h]
0x1800edd79  mov     r15, [rdi+10h]
0x1800edd7d  mov     rcx, [rax+8]
0x1800edd81  mov     ebx, [rcx+18h]
0x1800edd84  mov     [rbp+3Fh+var_7C], 0
0x1800edd8b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800edd92  jz      short loc_1800EDDB0
0x1800edd94  mov     [rsp+0C0h+var_88], r12d
0x1800edd99  mov     r9, r15
0x1800edd9c  mov     [rsp+0C0h+psetinfo], r13
0x1800edda1  mov     qword ptr [rsp+0C0h+grbit], rbx
0x1800edda6  mov     qword ptr [rsp+0C0h+cbData], r14
0x1800eddab  call    WPP_SF_iiiqd
0x1800eddb0  mov     eax, r12d
0x1800eddb3  mov     r8d, ebx; columnid
0x1800eddb6  neg     eax
0x1800eddb8  mov     rdx, r14; tableid
0x1800eddbb  mov     rcx, r15; sesid
0x1800eddbe  sbb     r9, r9
0x1800eddc1  and     r9, r13; pvData
0x1800eddc4  xor     r13d, r13d
0x1800eddc7  mov     [rsp+0C0h+psetinfo], r13; psetinfo
0x1800eddcc  mov     [rsp+0C0h+grbit], r13d; grbit
0x1800eddd1  mov     [rsp+0C0h+cbData], r12d; cbData
0x1800eddd6  call    cs:__imp_JetSetColumn
0x1800edddc  mov     ecx, eax; int
0x1800eddde  lea     edx, [r13+1]; int
0x1800edde2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800edde7  mov     ebx, eax
0x1800edde9  mov     dl, byte ptr cs:xmmword_180266B60+1
0x1800eddef  test    dl, 10h
0x1800eddf2  jz      short loc_1800EDE12
0x1800eddf4  lea     edx, [r13+15h]
0x1800eddf8  mov     ecx, 40Ch
0x1800eddfd  mov     r9d, eax
0x1800ede00  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800ede07  call    WPP_SF_d
0x1800ede0c  mov     dl, byte ptr cs:xmmword_180266B60+1
0x1800ede12  test    ebx, ebx
0x1800ede14  js      loc_1800EE130
0x1800ede1a  mov     rax, [rdi+28h]
0x1800ede1e  mov     r15, [rdi+20h]
0x1800ede22  mov     r12, [rdi+10h]
0x1800ede26  mov     rcx, [rax+8]
0x1800ede2a  mov     r14d, [rcx+1Ch]
0x1800ede2e  mov     [rbp+3Fh+var_7C], r13d
0x1800ede32  mov     ebx, [rbp+3Fh+arg_40]
0x1800ede38  mov     r13, [rbp+3Fh+var_68]
0x1800ede3c  test    dl, 10h
0x1800ede3f  jz      short loc_1800EDE5C
0x1800ede41  mov     [rsp+0C0h+var_88], ebx
0x1800ede45  mov     r9, r12
0x1800ede48  mov     [rsp+0C0h+psetinfo], r13
0x1800ede4d  mov     qword ptr [rsp+0C0h+grbit], r14
0x1800ede52  mov     qword ptr [rsp+0C0h+cbData], r15
0x1800ede57  call    WPP_SF_iiiqd
0x1800ede5c  mov     eax, ebx
0x1800ede5e  mov     r8d, r14d; columnid
0x1800ede61  neg     eax
0x1800ede63  mov     rdx, r15; tableid
0x1800ede66  mov     rcx, r12; sesid
0x1800ede69  sbb     r9, r9
0x1800ede6c  and     r9, r13; pvData
0x1800ede6f  xor     r13d, r13d
0x1800ede72  mov     [rsp+0C0h+psetinfo], r13; psetinfo
0x1800ede77  mov     [rsp+0C0h+grbit], r13d; grbit
0x1800ede7c  mov     [rsp+0C0h+cbData], ebx; cbData
0x1800ede80  call    cs:__imp_JetSetColumn
0x1800ede86  lea     r14d, [r13+1]
0x1800ede8a  mov     ecx, eax; int
0x1800ede8c  mov     edx, r14d; int
0x1800ede8f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ede94  mov     ebx, eax
0x1800ede96  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ede9d  jz      short loc_1800EDEB7
0x1800ede9f  lea     edx, [r13+15h]
0x1800edea3  mov     ecx, 40Ch
0x1800edea8  mov     r9d, eax
0x1800edeab  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800edeb2  call    WPP_SF_d
0x1800edeb7  test    ebx, ebx
0x1800edeb9  js      loc_1800EE13C
0x1800edebf  mov     rax, [rdi+28h]
0x1800edec3  lea     r9, [rbp+3Fh+var_60]; pvData
0x1800edec7  mov     rdx, [rdi+20h]; tableid
0x1800edecb  mov     rcx, [rdi+10h]; sesid
0x1800edecf  mov     [rsp+0C0h+psetinfo], r13; psetinfo
0x1800eded4  mov     r8, [rax+8]
0x1800eded8  mov     [rsp+0C0h+grbit], r13d; grbit
0x1800ededd  mov     [rsp+0C0h+cbData], 4; cbData
0x1800edee5  mov     r8d, [r8+10h]; columnid
0x1800edee9  call    cs:__imp_JetSetColumn
0x1800edeef  mov     ebx, eax
0x1800edef1  test    eax, eax
0x1800edef3  js      loc_1800EE148
0x1800edef9  mov     rax, [rdi+28h]
0x1800edefd  lea     r9, [rbp+3Fh+arg_20]; pvData
0x1800edf01  mov     rdx, [rdi+20h]; tableid
0x1800edf05  mov     rcx, [rdi+10h]; sesid
0x1800edf09  mov     [rsp+0C0h+psetinfo], r13; psetinfo
0x1800edf0e  mov     r8, [rax+8]
0x1800edf12  mov     [rsp+0C0h+grbit], r13d; grbit
0x1800edf17  mov     [rsp+0C0h+cbData], 8; cbData
0x1800edf1f  mov     r8d, [r8+14h]; columnid
0x1800edf23  call    cs:__imp_JetSetColumn
0x1800edf29  mov     ebx, eax
0x1800edf2b  test    eax, eax
0x1800edf2d  js      loc_1800EE154
0x1800edf33  mov     rdx, [rdi+20h]; tableid
0x1800edf37  xor     r9d, r9d; cbBookmark
0x1800edf3a  mov     rcx, [rdi+10h]; sesid
0x1800edf3e  xor     r8d, r8d; pvBookmark
0x1800edf41  mov     qword ptr [rsp+0C0h+cbData], r13; pcbActual
0x1800edf46  call    cs:__imp_JetUpdate
0x1800edf4c  mov     ecx, eax; int
0x1800edf4e  mov     edx, r14d; int
0x1800edf51  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800edf56  mov     ebx, eax
0x1800edf58  test    eax, eax
0x1800edf5a  js      loc_1800EE068
0x1800edf60  mov     rcx, [rdi+10h]; sesid
0x1800edf64  mov     edx, r14d; grbit
0x1800edf67  call    cs:__imp_JetCommitTransaction
0x1800edf6d  mov     ecx, eax; int
0x1800edf6f  mov     edx, r14d; int
0x1800edf72  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800edf77  mov     ebx, eax
0x1800edf79  test    eax, eax
0x1800edf7b  jns     short loc_1800EDFE7
0x1800edf7d  mov     rcx, [rdi+10h]; sesid
0x1800edf81  xor     edx, edx; grbit
0x1800edf83  call    cs:__imp_JetRollback
0x1800edf89  mov     rcx, [rsi+48h]; this
0x1800edf8d  lea     rdx, [rbp+3Fh+var_78]; struct CJetContext **
0x1800edf91  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800edf96  mov     rcx, [rsi+40h]; this
0x1800edf9a  lea     rdx, [rbp+3Fh+var_70]; struct CInFlightEntry **
0x1800edf9e  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x1800edfa3  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800edfaa  jz      short loc_1800EDFC5
0x1800edfac  mov     edx, 19h
0x1800edfb1  lea     r8, WPP_449f88becdf731b1b0126ce91da74e00_Traceguids
0x1800edfb8  mov     ecx, 40Ch
0x1800edfbd  mov     r9d, ebx
0x1800edfc0  call    WPP_SF_d
0x1800edfc5  mov     eax, ebx
0x1800edfc7  mov     rcx, [rbp+3Fh+var_48]
0x1800edfcb  xor     rcx, rsp; StackCookie
0x1800edfce  call    __security_check_cookie
0x1800edfd3  add     rsp, 88h
0x1800edfda  pop     r15
0x1800edfdc  pop     r14
0x1800edfde  pop     r13
0x1800edfe0  pop     r12
0x1800edfe2  pop     rdi
0x1800edfe3  pop     rsi
0x1800edfe4  pop     rbx
0x1800edfe5  pop     rbp
0x1800edfe6  retn
0x1800edfe7  mov     rcx, [rsi+48h]; this
0x1800edfeb  lea     rdx, [rbp+3Fh+var_78]; struct CJetContext **
0x1800edfef  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800edff4  mov     rcx, [rsi+40h]; this
0x1800edff8  lea     rdx, [rbp+3Fh+var_70]; struct CInFlightEntry **
0x1800edffc  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x1800ee001  mov     ebx, r13d
0x1800ee004  jmp     short loc_1800EDF89
0x1800ee006  mov     r8, r15; unsigned __int16 *
0x1800ee009  mov     edx, 2; unsigned int
0x1800ee00e  mov     rcx, rdi; this
0x1800ee011  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1800ee016  mov     ebx, eax
0x1800ee018  test    eax, eax
0x1800ee01a  js      loc_1800EE118
0x1800ee020  mov     rax, [rdi+28h]
0x1800ee024  lea     r9, [rbp+3Fh+var_58]; pvData
0x1800ee028  mov     rdx, [rdi+20h]; tableid
0x1800ee02c  mov     rcx, [rdi+10h]; sesid
0x1800ee030  mov     [rsp+0C0h+psetinfo], 0; psetinfo
0x1800ee039  mov     r8, [rax+8]
0x1800ee03d  mov     [rsp+0C0h+grbit], 0; grbit
0x1800ee045  mov     [rsp+0C0h+cbData], 8; cbData
0x1800ee04d  mov     r8d, [r8+4]; columnid
0x1800ee051  call    cs:__imp_JetSetColumn
0x1800ee057  mov     ebx, eax
0x1800ee059  test    eax, eax
  ... truncated ...
```
