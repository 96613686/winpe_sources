# ExecuteSqlBatches(TaskParameters *)

- ea: `0x10043a150`
- end: `0x10043a561`
- name: `?ExecuteSqlBatches@@YA?AVSQLError@@PEAUTaskParameters@@@Z`
- size: `1041`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x100439f60`

## callees

- `0x10043a150`
- `0x1004403d0`
- `0x10044bad0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x10043a4a7`
- `KERNEL32!SetEvent` at `0x10043a4a7`
- `sqlmin!?GetCurrentState@DBTABLE@@QEBA?AW4_AvailablityState@DBStateMgr@@XZ` at `0x10043a203`
- `sqlmin!?GetCurrentState@DBTABLE@@QEBA?AW4_AvailablityState@DBStateMgr@@XZ` at `0x10043a203`
- `sqlmin!?IsRecoveryThread@RecoveryUnit@@QEBAHXZ` at `0x10043a225`
- `sqlmin!?IsRecoveryThread@RecoveryUnit@@QEBAHXZ` at `0x10043a225`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x10043a238`
- `sqlmin!?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z` at `0x10043a238`
- `sqlmin!?IsUpdateable@RecoveryUnit@@QEBAHXZ` at `0x10043a24d`
- `sqlmin!?IsUpdateable@RecoveryUnit@@QEBAHXZ` at `0x10043a24d`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x10043a1f6`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x10043a1f6`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x10043a537`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x10043a537`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10043a1da`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10043a1da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a3b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a3b1`
- `sqldk!SystemThread_TlsOffset` at `0x10043a28f`
- `sqldk!SystemThread_TlsOffset` at `0x10043a397`
- `sqldk!SystemThread_TlsIndex` at `0x10043a27e`
- `sqldk!SystemThread_TlsIndex` at `0x10043a38e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043a1cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043a314`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043a1cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043a314`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10043a477`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10043a477`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x10043a3c7`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x10043a3c7`

## string_xrefs

- `0x10043a308`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned int *__fastcall ExecuteSqlBatches(unsigned int *a1, __int64 a2)
{
  bool v4; // si
  _QWORD *v5; // rax
  unsigned __int16 MasterDbId; // ax
  __int64 v7; // r14
  __int64 v8; // r9
  char v9; // r14
  __int64 v10; // r14
  __int64 v11; // rcx
  struct IExecSql *ExecSql; // r12
  int v13; // r15d
  __int64 v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  void *v18; // rcx
  int v20; // [rsp+28h] [rbp-49h]
  __int64 v21; // [rsp+60h] [rbp-11h] BYREF
  int v22; // [rsp+68h] [rbp-9h]
  _BYTE v23[24]; // [rsp+70h] [rbp-1h] BYREF
  __int64 v24; // [rsp+88h] [rbp+17h] BYREF
  unsigned int v25; // [rsp+90h] [rbp+1Fh]
  __int128 v26; // [rsp+98h] [rbp+27h]

  *(_QWORD *)a1 = 0;
  a1[2] = -1;
  *(_QWORD *)(a1 + 3) = 0;
  v4 = 1;
  if ( !a2 || (v5 = *(_QWORD **)(a2 + 8)) == 0 || !*(_DWORD *)(a2 + 16) || !*v5 )
    utassert_fail(
      1u,
      "params && params->_sqlBatch && params->_sqlBatchCount != 0 && *params->_sqlBatch",
      "\"sql\\\\ntdbms\\\\ksource\\\\xplat.cpp\"",
      287,
      0);
  v21 = 0;
  v22 = 0;
  MasterDbId = GetMasterDbId();
  AutoOpenDB::Open((AutoOpenDB *)&v21, 0, MasterDbId, 1u, 1);
  v7 = v21;
  if ( !(unsigned int)DBTABLE::GetCurrentState(v21)
    && ((*(_DWORD *)(v7 + 1648) & 2) == 0 || RecoveryUnit::IsRecoveryThread(*(RecoveryUnit **)(v7 + 4624)))
    && !DBTABLE::IsMarkedReadOnly((DBTABLE *)v7, 0)
    && RecoveryUnit::IsUpdateable(*(RecoveryUnit **)(v7 + 4624)) )
  {
    v24 = 0;
    v26 = 0;
    v25 = 1;
    v8 = 8LL * SystemThread_TlsIndex;
    *(_QWORD *)&v26 = *(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                            + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v8))
                                + 144LL);
    v9 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v8)
                              + SystemThread_TlsOffset)
                  + 152LL);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 464LL))(v26) )
    {
      if ( v9 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 488LL))(v26) )
        utassert_fail(
          1u,
          "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
          "automsqlxact.cpp",
          235,
          0);
      (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v26 + 232LL))(v26, 2, 1, (char *)&v24 + 4);
      v25 = 1;
      LODWORD(v24) = 3;
    }
    else
    {
      v20 = 2;
      (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)v26 + 8LL))(v26, L"ExecuteSqlBatches", 34);
      LODWORD(v24) = 1;
    }
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v11 = *(_QWORD *)(v10 + 256);
    if ( !v11 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v11 = *(_QWORD *)(v10 + 256);
    }
    ExecSql = CreateExecSql(*(struct IMemObj **)(v11 + 1000), 0);
    (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
    (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 56LL))(ExecSql);
    v13 = 0;
    if ( *(int *)(a2 + 16) <= 0 )
    {
LABEL_31:
      CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v24, 0);
      v18 = *(void **)(a2 + 24);
      if ( v18 )
        SetEvent(v18);
    }
    else
    {
      v14 = 0;
      while ( v4 )
      {
        v15 = *(_QWORD *)(v14 + *(_QWORD *)(a2 + 8));
        if ( v15 )
        {
          v4 = (*(unsigned int (__fastcall **)(struct IExecSql *, __int64, _QWORD))(*(_QWORD *)ExecSql + 8LL))(
                 ExecSql,
                 v15,
                 0) != 0;
          v16 = (*(__int64 (__fastcall **)(struct IExecSql *, _BYTE *))(*(_QWORD *)ExecSql + 176LL))(ExecSql, v23);
          *(_OWORD *)a1 = *(_OWORD *)v16;
          a1[4] = *(_DWORD *)(v16 + 16);
          v17 = *a1;
          if ( (_DWORD)v17 )
          {
            v4 = 0;
            if ( a1[4] != 1 )
              v17 = (unsigned __int16)v17;
            scierrlog(*(_DWORD *)(a2 + 20), v17, a1[1], a1[3]);
          }
          else if ( !v4 )
          {
            ex_raise(27, 13, 25, 10);
          }
        }
        ++v13;
        v14 += 8;
        if ( v13 >= *(_DWORD *)(a2 + 16) )
        {
          if ( !v4 )
            break;
          goto LABEL_31;
        }
      }
    }
    (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
    if ( (_DWORD)v24 )
    {
      switch ( (_DWORD)v24 )
      {
        case 1:
        case 2:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 32LL))(v26);
          break;
        case 3:
          LOBYTE(v20) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v26 + 248LL))(
            v26,
            2,
            v25,
            HIDWORD(v24),
            v20);
          break;
        case 4:
          LOBYTE(v20) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v26 + 248LL))(
            v26,
            1,
            v25,
            HIDWORD(v24),
            v20);
          break;
      }
      LODWORD(v24) = 0;
    }
  }
  if ( v21 )
    AutoOpenDB::CloseDB((AutoOpenDB *)&v21);
  return a1;
}

```

## disassembly

```asm
0x10043a150  mov     rax, rsp
0x10043a153  push    rbp
0x10043a154  push    r12
0x10043a156  push    r13
0x10043a158  push    r14
0x10043a15a  push    r15
0x10043a15c  lea     rbp, [rax-5Fh]
0x10043a160  sub     rsp, 0A0h
0x10043a167  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x10043a16f  mov     [rax+10h], rbx
0x10043a173  mov     [rax+18h], rsi
0x10043a177  mov     [rax+20h], rdi
0x10043a17b  mov     rdi, rdx
0x10043a17e  mov     rbx, rcx
0x10043a181  xor     r13d, r13d
0x10043a184  mov     [rcx], r13
0x10043a187  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x10043a18e  mov     [rcx+0Ch], r13
0x10043a192  mov     sil, 1
0x10043a195  test    rdx, rdx
0x10043a198  jz      short loc_10043A1AE
0x10043a19a  mov     rax, [rdx+8]
0x10043a19e  test    rax, rax
0x10043a1a1  jz      short loc_10043A1AE
0x10043a1a3  cmp     [rdx+10h], r13d
0x10043a1a7  jz      short loc_10043A1AE
0x10043a1a9  cmp     [rax], r13
0x10043a1ac  jnz     short loc_10043A1D2
0x10043a1ae  mov     qword ptr [rsp+0C0h+var_A0], r13
0x10043a1b3  mov     r9d, 11Fh
0x10043a1b9  lea     r8, aSqlNtdbmsKsour_4; "\"sql\\\\ntdbms\\\\ksource\\\\xplat.cpp"...
0x10043a1c0  lea     rdx, aParamsParamsSq; "params && params->_sqlBatch && params->"...
0x10043a1c7  mov     ecx, 1
0x10043a1cc  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10043a1d2  mov     [rbp+57h+var_68], r13
0x10043a1d6  mov     [rbp+57h+var_60], r13d
0x10043a1da  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10043a1e0  movzx   r8d, ax
0x10043a1e4  mov     [rsp+0C0h+var_A0], 1
0x10043a1ec  xor     edx, edx
0x10043a1ee  lea     r9d, [rdx+1]
0x10043a1f2  lea     rcx, [rbp+57h+var_68]
0x10043a1f6  call    cs:__imp_?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z; AutoOpenDB::Open(BaseXact *,ulong,ulong,int)
0x10043a1fc  mov     r14, [rbp+57h+var_68]
0x10043a200  mov     rcx, r14
0x10043a203  call    cs:__imp_?GetCurrentState@DBTABLE@@QEBA?AW4_AvailablityState@DBStateMgr@@XZ; DBTABLE::GetCurrentState(void)
0x10043a209  test    eax, eax
0x10043a20b  jnz     loc_10043A52C
0x10043a211  mov     eax, [r14+670h]
0x10043a218  shr     eax, 1
0x10043a21a  test    al, 1
0x10043a21c  jz      short loc_10043A233
0x10043a21e  mov     rcx, [r14+1210h]
0x10043a225  call    cs:__imp_?IsRecoveryThread@RecoveryUnit@@QEBAHXZ; RecoveryUnit::IsRecoveryThread(void)
0x10043a22b  test    eax, eax
0x10043a22d  jz      loc_10043A52C
0x10043a233  xor     edx, edx
0x10043a235  mov     rcx, r14
0x10043a238  call    cs:__imp_?IsMarkedReadOnly@DBTABLE@@QEBA_N_N@Z; DBTABLE::IsMarkedReadOnly(bool)
0x10043a23e  test    al, al
0x10043a240  jnz     loc_10043A52C
0x10043a246  mov     rcx, [r14+1210h]
0x10043a24d  call    cs:__imp_?IsUpdateable@RecoveryUnit@@QEBAHXZ; RecoveryUnit::IsUpdateable(void)
0x10043a253  test    eax, eax
0x10043a255  jz      loc_10043A52C
0x10043a25b  mov     [rbp+57h+var_40], r13
0x10043a25f  mov     [rbp+57h+var_38], 1
0x10043a266  xorps   xmm0, xmm0
0x10043a269  movdqu  [rbp+57h+var_30], xmm0
0x10043a26e  mov     [rbp+57h+var_38], 1
0x10043a275  mov     rdx, gs:58h
0x10043a27e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a285  mov     ecx, [rax]
0x10043a287  lea     r9, ds:0[rcx*8]
0x10043a28f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a296  mov     r8d, [rax]
0x10043a299  mov     rax, [r9+rdx]
0x10043a29d  mov     rax, [r8+rax]
0x10043a2a1  mov     rcx, [rax+90h]
0x10043a2a8  mov     qword ptr [rbp+57h+var_30], rcx
0x10043a2ac  mov     rax, gs:58h
0x10043a2b5  mov     rcx, [r9+rax]
0x10043a2b9  mov     rax, [rcx+r8]
0x10043a2bd  movzx   r14d, byte ptr [rax+98h]
0x10043a2c5  mov     r15d, r13d
0x10043a2c8  test    r14b, r14b
0x10043a2cb  setnz   r15b
0x10043a2cf  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a2d3  mov     rax, [rcx]
0x10043a2d6  call    qword ptr [rax+1D0h]
0x10043a2dc  test    al, al
0x10043a2de  jz      short loc_10043A344
0x10043a2e0  test    r14b, r14b
0x10043a2e3  jz      short loc_10043A31A
0x10043a2e5  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a2e9  mov     rax, [rcx]
0x10043a2ec  call    qword ptr [rax+1E8h]
0x10043a2f2  test    al, al
0x10043a2f4  jz      short loc_10043A31A
0x10043a2f6  mov     qword ptr [rsp+0C0h+var_A0], r13
0x10043a2fb  mov     r9d, 0EBh
0x10043a301  lea     r8, aAutomsqlxactCp; "automsqlxact.cpp"
0x10043a308  lea     rdx, ?szExpression@?9??BeginNestedXact@CAutoMsqlXact@@QEAAXPEB_WHW4ReadWriteMode@CMsqlXact@@W4DistributionMode@4@W4NestedXactOption@4@W4CTRSupportOption@4@@Z@4QBDB; "rwMode == CMsqlXact::ReadOnly || ctrOpt"...
0x10043a30f  mov     ecx, 1
0x10043a314  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10043a31a  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a31e  mov     rax, [rcx]
0x10043a321  lea     r9, [rbp+57h+var_40+4]
0x10043a325  mov     edx, 2
0x10043a32a  lea     r8d, [rdx-1]
0x10043a32e  call    qword ptr [rax+0E8h]
0x10043a334  mov     [rbp+57h+var_38], 1
0x10043a33b  mov     dword ptr [rbp+57h+var_40], 3
0x10043a342  jmp     short loc_10043A385
0x10043a344  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a348  mov     rax, [rcx]
0x10043a34b  mov     [rsp+0C0h+var_80], r15d
0x10043a350  mov     qword ptr [rsp+0C0h+var_88], r13
0x10043a355  mov     byte ptr [rsp+0C0h+var_90], 0
0x10043a35a  mov     dword ptr [rsp+0C0h+var_98], 1
0x10043a362  mov     [rsp+0C0h+var_A0], 2
0x10043a36a  mov     r9d, 1
0x10043a370  lea     r8d, [r9+21h]
0x10043a374  lea     rdx, aExecutesqlbatc; "ExecuteSqlBatches"
0x10043a37b  call    qword ptr [rax+8]
0x10043a37e  mov     dword ptr [rbp+57h+var_40], 1
0x10043a385  mov     rdx, gs:58h
0x10043a38e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a395  mov     ecx, [rax]
0x10043a397  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a39e  mov     r14d, [rax]
0x10043a3a1  add     r14, [rdx+rcx*8]
0x10043a3a5  mov     rcx, [r14+100h]
0x10043a3ac  test    rcx, rcx
0x10043a3af  jnz     short loc_10043A3BE
0x10043a3b1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a3b7  mov     rcx, [r14+100h]
0x10043a3be  xor     edx, edx
0x10043a3c0  mov     rcx, [rcx+3E8h]
0x10043a3c7  call    cs:__imp_?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z; CreateExecSql(IMemObj *,ICallerParse *)
0x10043a3cd  mov     r12, rax
0x10043a3d0  mov     [rbp+57h+arg_0], rax
0x10043a3d4  mov     rdx, [rax]
0x10043a3d7  mov     rcx, rax
0x10043a3da  call    qword ptr [rdx+30h]
0x10043a3dd  mov     rdx, [r12]
0x10043a3e1  mov     rcx, r12
0x10043a3e4  call    qword ptr [rdx+38h]
0x10043a3e7  mov     r15d, r13d
0x10043a3ea  cmp     [rdi+10h], r13d
0x10043a3ee  jle     loc_10043A493
0x10043a3f4  mov     r14, r13
0x10043a3f7  test    sil, sil
0x10043a3fa  jz      loc_10043A4AE
0x10043a400  mov     rax, [rdi+8]
0x10043a404  mov     rdx, [r14+rax]
0x10043a408  test    rdx, rdx
0x10043a40b  jz      short loc_10043A47D
0x10043a40d  mov     rax, [r12]
0x10043a411  xor     r8d, r8d
0x10043a414  mov     rcx, r12
0x10043a417  call    qword ptr [rax+8]
0x10043a41a  test    eax, eax
0x10043a41c  setnz   sil
0x10043a420  mov     rax, [r12]
0x10043a424  lea     rdx, [rbp+57h+var_58]
0x10043a428  mov     rcx, r12
0x10043a42b  call    qword ptr [rax+0B0h]
0x10043a431  movups  xmm0, xmmword ptr [rax]
0x10043a434  movups  xmmword ptr [rbx], xmm0
0x10043a437  mov     eax, [rax+10h]
0x10043a43a  mov     [rbx+10h], eax
0x10043a43d  mov     edx, [rbx]
0x10043a43f  test    edx, edx
0x10043a441  jz      short loc_10043A462
0x10043a443  xor     sil, sil
0x10043a446  movzx   eax, dx
0x10043a449  cmp     dword ptr [rbx+10h], 1
0x10043a44d  cmovnz  edx, eax
0x10043a450  mov     r9d, [rbx+0Ch]
0x10043a454  mov     r8d, [rbx+4]
0x10043a458  mov     ecx, [rdi+14h]; unsigned int
0x10043a45b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043a460  jmp     short loc_10043A47D
0x10043a462  test    sil, sil
0x10043a465  jnz     short loc_10043A47D
0x10043a467  mov     edx, 0Dh
0x10043a46c  lea     ecx, [rdx+0Eh]
0x10043a46f  lea     r9d, [rdx-3]
0x10043a473  lea     r8d, [rdx+0Ch]
0x10043a477  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10043a47d  inc     r15d
0x10043a480  add     r14, 8
0x10043a484  cmp     r15d, [rdi+10h]
0x10043a488  jl      loc_10043A3F7
0x10043a48e  test    sil, sil
0x10043a491  jz      short loc_10043A4AE
0x10043a493  xor     edx, edx; bool
0x10043a495  lea     rcx, [rbp+57h+var_40]; this
0x10043a499  call    ?CommitNestedXact@CAutoMsqlXact@@QEAAX_N@Z; CAutoMsqlXact::CommitNestedXact(bool)
0x10043a49e  mov     rcx, [rdi+18h]; hEvent
0x10043a4a2  test    rcx, rcx
0x10043a4a5  jz      short loc_10043A4AE
0x10043a4a7  call    cs:__imp_SetEvent
0x10043a4ad  nop
0x10043a4ae  mov     rax, [r12]
0x10043a4b2  mov     edx, 1
0x10043a4b7  mov     rcx, r12
0x10043a4ba  call    qword ptr [rax+0E0h]
0x10043a4c0  nop
0x10043a4c1  mov     ecx, dword ptr [rbp+57h+var_40]
0x10043a4c4  test    ecx, ecx
0x10043a4c6  jz      short loc_10043A52C
0x10043a4c8  sub     ecx, 1
0x10043a4cb  jz      short loc_10043A51E
0x10043a4cd  sub     ecx, 1
0x10043a4d0  jz      short loc_10043A51E
0x10043a4d2  sub     ecx, 1
0x10043a4d5  jz      short loc_10043A4FD
0x10043a4d7  cmp     ecx, 1
0x10043a4da  jnz     short loc_10043A528
0x10043a4dc  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a4e0  mov     rax, [rcx]
0x10043a4e3  mov     byte ptr [rsp+0C0h+var_A0], 0
0x10043a4e8  mov     r9d, dword ptr [rbp+57h+var_40+4]
0x10043a4ec  mov     r8d, [rbp+57h+var_38]
0x10043a4f0  mov     edx, 1
0x10043a4f5  call    qword ptr [rax+0F8h]
0x10043a4fb  jmp     short loc_10043A528
0x10043a4fd  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a501  mov     rax, [rcx]
0x10043a504  mov     byte ptr [rsp+0C0h+var_A0], 0
0x10043a509  mov     r9d, dword ptr [rbp+57h+var_40+4]
0x10043a50d  mov     r8d, [rbp+57h+var_38]
0x10043a511  mov     edx, 2
0x10043a516  call    qword ptr [rax+0F8h]
0x10043a51c  jmp     short loc_10043A528
0x10043a51e  mov     rcx, qword ptr [rbp+57h+var_30]
0x10043a522  mov     rax, [rcx]
0x10043a525  call    qword ptr [rax+20h]
0x10043a528  mov     dword ptr [rbp+57h+var_40], r13d
0x10043a52c  cmp     [rbp+57h+var_68], 0
0x10043a531  jz      short loc_10043A53D
0x10043a533  lea     rcx, [rbp+57h+var_68]
0x10043a537  call    cs:__imp_?CloseDB@AutoOpenDB@@AEAAXXZ; AutoOpenDB::CloseDB(void)
0x10043a53d  mov     rax, rbx
0x10043a540  lea     r11, [rsp+0C0h+var_20]
0x10043a548  mov     rbx, [r11+38h]
0x10043a54c  mov     rsi, [r11+40h]
0x10043a550  mov     rdi, [r11+48h]
0x10043a554  mov     rsp, r11
0x10043a557  pop     r15
0x10043a559  pop     r14
0x10043a55b  pop     r13
0x10043a55d  pop     r12
0x10043a55f  pop     rbp
0x10043a560  retn
```
