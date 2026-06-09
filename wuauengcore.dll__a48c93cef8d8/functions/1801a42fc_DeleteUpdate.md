# DeleteUpdate

- ea: `0x1801a42fc`
- end: `0x1801a4926`
- name: `DeleteUpdate`
- size: `1578`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a4b78`

## callees

- `0x18012b618`
- `0x180182f58`
- `0x1801832c8`
- `0x180183724`
- `0x1801839f0`
- `0x1801844a0`
- `0x1801844ec`
- `0x18018457c`
- `0x1801853f0`
- `0x180192564`
- `0x1801a415c`
- `0x1801a42fc`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a48be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a48f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a48be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a48f0`
- `ESENT!JetMove` at `0x1801a4712`
- `ESENT!JetMove` at `0x1801a47b1`
- `ESENT!JetMove` at `0x1801a4712`
- `ESENT!JetMove` at `0x1801a47b1`
- `ESENT!JetDelete` at `0x1801a46f8`
- `ESENT!JetDelete` at `0x1801a4796`
- `ESENT!JetDelete` at `0x1801a48ce`
- `ESENT!JetDelete` at `0x1801a46f8`
- `ESENT!JetDelete` at `0x1801a4796`
- `ESENT!JetDelete` at `0x1801a48ce`

## string_xrefs

- `0x1801a473b`: `JetMove`
- `0x1801a4750`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`
- `0x1801a4841`: `JetDelete`
- `0x1801a47f4`: `DS: 0x%08X: JetDelete failed. sesid: %Ix. tableid: %Ix`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteUpdate(
        __int64 a1,
        unsigned __int64 a2,
        JET_TABLEID a3,
        unsigned __int64 a4,
        JET_TABLEID a5,
        JET_TABLEID tableid,
        _DWORD *a7)
{
  unsigned __int64 v9; // rdi
  int VarColumns; // ebx
  int Data; // eax
  void *pvData; // r12
  unsigned int v13; // esi
  unsigned int v14; // r14d
  unsigned int *v15; // r15
  int v16; // eax
  unsigned int v17; // r9d
  JET_ERR v18; // esi
  int v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  int v22; // eax
  const char *v23; // rax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  unsigned int v26; // r14d
  int MultiValSetFixed; // eax
  void *v28; // rsi
  unsigned int *v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int itagSequence; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h]
  _QWORD v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  JET_TABLEID v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-80h] BYREF
  GUID v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+98h] [rbp-68h] BYREF
  int *v43; // [rsp+A0h] [rbp-60h] BYREF
  int v44; // [rsp+A8h] [rbp-58h]
  LPVOID pv; // [rsp+B0h] [rbp-50h]
  struct JET_RETRIEVECOLUMN v46[5]; // [rsp+C0h] [rbp-40h] BYREF

  v35 = a4;
  v37 = a3;
  v36[0] = &CSusEseTransaction::`vftable';
  v36[1] = 0;
  v41 = GUID_NULL;
  v42 = -1;
  v38 = 0;
  memset(v46, 0, sizeof(v46));
  v9 = *(_QWORD *)(a1 + 128);
  VarColumns = CSusEseTransaction::Begin(
                 (CSusEseTransaction *)v36,
                 (struct ISusEseSession *)((a1 + 8) & -(__int64)(a1 != 0)));
  if ( VarColumns >= 0 )
  {
    v46[0].columnid = dword_18033840C;
    v46[0].pvData = 0;
    v46[0].cbData = 0;
    v46[0].itagSequence = 0;
    v46[1].columnid = dword_180338450;
    v46[1].pvData = 0;
    v46[1].cbData = 0;
    v46[1].itagSequence = 0;
    v46[2].columnid = g_rgClientStoreColumnIds;
    v46[2].pvData = &v38;
    v46[2].cbData = 4;
    v46[2].itagSequence = 1;
    v46[3].columnid = dword_180338404;
    v46[3].pvData = &v41;
    v46[3].cbData = 16;
    v46[3].itagSequence = 1;
    v46[4].columnid = dword_180338408;
    v46[4].pvData = &v42;
    v46[4].cbData = 4;
    v46[4].itagSequence = 1;
    Data = DsqGetData(v9, a2, v46, 5u);
    VarColumns = Data;
    if ( Data < 0 )
    {
      if ( Data != -2145091577 )
        goto LABEL_56;
      if ( v46[2].err || v46[3].err || v46[4].err )
      {
        VarColumns = -2145091576;
        goto LABEL_56;
      }
    }
    itagSequence = v46[1].itagSequence;
    if ( v46[0].itagSequence )
    {
      VarColumns = -2145091573;
      goto LABEL_56;
    }
    *(&v46[0].columnid + 1) = 0;
    *(_OWORD *)&v46[0].cbData = 0;
    *(_OWORD *)&v46[0].itagSequence = 0;
    v46[0].columnid = dword_180338448;
    v46[0].pvData = 0;
    v46[0].cbData = 0;
    v46[0].itagSequence = 1;
    VarColumns = DsqRetrieveVarColumns(v9, a2, v46, 1);
    if ( (int)(VarColumns + 0x80000000) < 0 || VarColumns == -2145091577 )
    {
      v43 = &v38;
      v44 = 4;
      *a7 = v38;
      pvData = v46[0].pvData;
      v13 = v46[0].cbActual >> 2;
      if ( v46[0].pvData )
      {
        v14 = 0;
        if ( v13 )
        {
          v15 = (unsigned int *)v46[0].pvData;
          while ( 1 )
          {
            v16 = DsqDeleteFile(v9, v35, *v15, 0);
            VarColumns = v16;
            if ( v16 < 0 )
              break;
            ++v14;
            ++v15;
            if ( v14 >= v13 )
              goto LABEL_17;
          }
          if ( v16 == -2145091577 )
            VarColumns = -2145091575;
          goto LABEL_55;
        }
      }
LABEL_17:
      VarColumns = DsqSeekToRow(v9, a5, 0, (struct tagDsqSearchKey *)&v43, 1u, 1, 1, 0);
      if ( (int)(VarColumns + 0x80000000) < 0 || VarColumns == -2145091577 )
      {
        if ( VarColumns == -2145091577 )
        {
LABEL_45:
          v26 = itagSequence;
          if ( !itagSequence )
            goto LABEL_52;
          LODWORD(v43) = 20;
          HIDWORD(v43) = itagSequence;
          v44 = 16;
          pv = 0;
          MultiValSetFixed = DsqGetMultiValSetFixed(v9, a2, (struct tagDsqMultiValRetrieveFixed *)&v43, v17, v30);
          VarColumns = MultiValSetFixed;
          if ( MultiValSetFixed < 0 )
          {
            if ( MultiValSetFixed == -2145091577 )
              VarColumns = -2145091576;
            goto LABEL_54;
          }
          v28 = pv;
          VarColumns = DsqModifySupersededByLists(
                         v9,
                         v37,
                         0,
                         (const struct tagDSGlobalUpdateId *)&v41,
                         v26,
                         (struct _GUID *const)pv);
          if ( v28 )
            CoTaskMemFree(v28);
          if ( VarColumns >= 0 )
          {
LABEL_52:
            v24 = JetDelete(v9, a2);
            if ( v24 )
            {
LABEL_44:
              VarColumns = JETErrToHRESULTAndAttemptRecovery(v24);
              v32 = a2;
              v23 = "JetDelete";
LABEL_34:
              LODWORD(v31) = VarColumns;
              WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix", v31, v23, v9, v32);
            }
            else
            {
              VarColumns = CSusEseTransaction::Commit((CSusEseTransaction *)v36);
            }
          }
        }
        else
        {
          v39 = -1;
          v18 = 0;
          while ( 1 )
          {
            *(&v46[0].columnid + 1) = 0;
            *(_OWORD *)&v46[0].cbData = 0;
            *(_OWORD *)&v46[0].itagSequence = 0;
            v46[0].columnid = dword_180338510;
            v46[0].pvData = &v39;
            v46[0].cbData = 4;
            v46[0].itagSequence = 1;
            VarColumns = DsqGetData(v9, a5, v46, 1u);
            if ( VarColumns < 0 )
              break;
            if ( v39 != -1 )
            {
              v43 = &v39;
              v44 = 4;
              VarColumns = DsqSeekToRow(v9, tableid, "EulaIdMapLocRegion", (struct tagDsqSearchKey *)&v43, 1u, 1, 1, 0);
              if ( (int)(VarColumns + 0x80000000) >= 0 && VarColumns != -2145091577 )
                break;
              while ( v18 != -1603 )
              {
                v40 = 0;
                v33 = 0;
                memset(v46, 0, sizeof(v46));
                v46[0].columnid = dword_18033854C;
                v46[0].pvData = &v40;
                v46[0].cbData = 4;
                v46[0].itagSequence = 1;
                VarColumns = DsqGetData(v9, tableid, v46, 1u);
                if ( VarColumns < 0 )
                  goto LABEL_54;
                v19 = DsqDeleteFile(v9, v35, v40, &v33);
                VarColumns = v19;
                if ( v19 < 0 )
                {
                  if ( v19 == -2145091577 )
                    VarColumns = -2145091575;
                  goto LABEL_54;
                }
                if ( v33 )
                {
                  v20 = JetDelete(v9, tableid);
                  if ( v20 )
                  {
                    VarColumns = JETErrToHRESULTAndAttemptRecovery(v20);
                    LODWORD(v31) = VarColumns;
                    WUTrace(
                      0,
                      0,
                      0x2000,
                      1,
                      0,
                      L"DS: 0x%08X: JetDelete failed. sesid: %Ix. tableid: %Ix",
                      v31,
                      v9,
                      tableid);
                    goto LABEL_54;
                  }
                }
                v21 = JetMove(v9, tableid, 1, 0);
                v18 = v21;
                if ( v21 && v21 != -1603 )
                {
                  v22 = JETErrToHRESULTAndAttemptRecovery(v21);
                  v32 = tableid;
                  goto LABEL_33;
                }
              }
            }
            v24 = JetDelete(v9, a5);
            if ( v24 )
              goto LABEL_44;
            v25 = JetMove(v9, a5, 1, 0);
            v18 = v25;
            if ( v25 )
            {
              if ( v25 == -1603 )
                goto LABEL_45;
              v22 = JETErrToHRESULTAndAttemptRecovery(v25);
              v32 = a5;
LABEL_33:
              VarColumns = v22;
              v23 = "JetMove";
              goto LABEL_34;
            }
          }
        }
      }
LABEL_54:
      if ( !pvData )
        goto LABEL_56;
LABEL_55:
      CoTaskMemFree(pvData);
    }
  }
LABEL_56:
  CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v36);
  return (unsigned int)VarColumns;
}

```

## disassembly

```asm
0x1801a42fc  push    rbp
0x1801a42fe  push    rbx
0x1801a42ff  push    rsi
0x1801a4300  push    rdi
0x1801a4301  push    r12
0x1801a4303  push    r13
0x1801a4305  push    r14
0x1801a4307  push    r15
0x1801a4309  lea     rbp, [rsp-0C8h]
0x1801a4311  sub     rsp, 1C8h
0x1801a4318  mov     rax, cs:__security_cookie
0x1801a431f  xor     rax, rsp
0x1801a4322  mov     [rbp+100h+var_50], rax
0x1801a4329  mov     [rsp+200h+var_1A8], r9
0x1801a432e  mov     [rsp+200h+var_190], r8
0x1801a4333  mov     r13, rdx
0x1801a4336  mov     rbx, rcx
0x1801a4339  mov     rsi, [rbp+100h+arg_30]
0x1801a4340  xorps   xmm0, xmm0
0x1801a4343  movups  [rsp+200h+var_1A0], xmm0
0x1801a4348  lea     rax, ??_7CSusEseTransaction@@6B@; const CSusEseTransaction::`vftable'
0x1801a434f  mov     qword ptr [rsp+200h+var_1A0], rax
0x1801a4354  xor     r15d, r15d
0x1801a4357  mov     qword ptr [rsp+200h+var_1A0+8], r15
0x1801a435c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801a4363  movdqu  [rbp+100h+var_178], xmm0
0x1801a4368  mov     [rbp+100h+var_168], 0FFFFFFFFh
0x1801a436f  mov     [rsp+200h+var_188], r15d
0x1801a4374  xor     edx, edx; Val
0x1801a4376  mov     r8d, 0F0h; Size
0x1801a437c  lea     rcx, [rbp+100h+var_140]; void *
0x1801a4380  call    memset
0x1801a4385  mov     rdi, [rbx+80h]
0x1801a438c  lea     rax, [rbx+8]
0x1801a4390  neg     rbx
0x1801a4393  sbb     rdx, rdx
0x1801a4396  and     rdx, rax; struct ISusEseSession *
0x1801a4399  lea     rcx, [rsp+200h+var_1A0]; this
0x1801a439e  call    ?Begin@CSusEseTransaction@@QEAAJPEAUISusEseSession@@@Z; CSusEseTransaction::Begin(ISusEseSession *)
0x1801a43a3  mov     ebx, eax
0x1801a43a5  test    eax, eax
0x1801a43a7  js      loc_1801A48F7
0x1801a43ad  mov     eax, cs:dword_18033840C
0x1801a43b3  mov     [rbp+100h+var_140.columnid], eax
0x1801a43b6  mov     [rbp+100h+var_140.pvData], r15
0x1801a43ba  mov     [rbp+100h+var_140.cbData], r15d
0x1801a43be  mov     [rbp+100h+var_140.itagSequence], r15d
0x1801a43c2  mov     eax, cs:dword_180338450
0x1801a43c8  mov     [rbp+100h+var_110], eax
0x1801a43cb  mov     [rbp+100h+var_108], r15
0x1801a43cf  mov     [rbp+100h+var_100], r15d
0x1801a43d3  mov     [rbp+100h+var_F0], r15d
0x1801a43d7  mov     eax, cs:?g_rgClientStoreColumnIds@@3PAKA; ulong near * g_rgClientStoreColumnIds
0x1801a43dd  mov     [rbp+100h+var_E0], eax
0x1801a43e0  lea     rax, [rsp+200h+var_188]
0x1801a43e5  mov     [rbp+100h+var_D8], rax
0x1801a43e9  mov     [rbp+100h+var_D0], 4
0x1801a43f0  lea     r14d, [r15+1]
0x1801a43f4  mov     [rbp+100h+var_C0], r14d
0x1801a43f8  mov     eax, cs:dword_180338404
0x1801a43fe  mov     [rbp+100h+var_B0], eax
0x1801a4401  lea     rax, [rbp+100h+var_178]
0x1801a4405  mov     [rbp+100h+var_A8], rax
0x1801a4409  mov     [rbp+100h+var_A0], 10h
0x1801a4410  mov     [rbp+100h+var_90], r14d
0x1801a4414  mov     eax, cs:dword_180338408
0x1801a441a  mov     [rbp+100h+var_80], eax
0x1801a4420  lea     rax, [rbp+100h+var_168]
0x1801a4424  mov     [rbp+100h+var_78], rax
0x1801a442b  mov     [rbp+100h+var_70], 4
0x1801a4435  mov     [rbp+100h+var_60], r14d
0x1801a443c  lea     r9d, [r15+5]; unsigned int
0x1801a4440  lea     r8, [rbp+100h+var_140]; struct JET_RETRIEVECOLUMN *
0x1801a4444  mov     rdx, r13; unsigned __int64
0x1801a4447  mov     rcx, rdi; unsigned __int64
0x1801a444a  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x1801a444f  mov     ebx, eax
0x1801a4451  mov     r12d, 80248007h
0x1801a4457  test    eax, eax
0x1801a4459  jns     short loc_1801A4483
0x1801a445b  cmp     eax, r12d
0x1801a445e  jnz     loc_1801A48F7
0x1801a4464  cmp     [rbp+100h+var_B8], r15d
0x1801a4468  jnz     short loc_1801A4479
0x1801a446a  cmp     [rbp+100h+var_88], r15d
0x1801a446e  jnz     short loc_1801A4479
0x1801a4470  cmp     [rbp+100h+var_58], r15d
0x1801a4477  jz      short loc_1801A4483
0x1801a4479  mov     ebx, 80248008h
0x1801a447e  jmp     loc_1801A48F7
0x1801a4483  mov     eax, [rbp+100h+var_F0]
0x1801a4486  mov     [rsp+200h+var_1AC], eax
0x1801a448a  cmp     [rbp+100h+var_140.itagSequence], r15d
0x1801a448e  jz      short loc_1801A449A
0x1801a4490  mov     ebx, 8024800Bh
0x1801a4495  jmp     loc_1801A48F7
0x1801a449a  xorps   xmm0, xmm0
0x1801a449d  movups  xmmword ptr [rbp+100h+var_140.columnid], xmm0
0x1801a44a1  movups  xmmword ptr [rbp+100h+var_140.cbData], xmm0
0x1801a44a5  movups  xmmword ptr [rbp+100h+var_140.itagSequence], xmm0
0x1801a44a9  mov     eax, cs:dword_180338448
0x1801a44af  mov     [rbp+100h+var_140.columnid], eax
0x1801a44b2  mov     [rbp+100h+var_140.pvData], r15
0x1801a44b6  mov     [rbp+100h+var_140.cbData], r15d
0x1801a44ba  mov     [rbp+100h+var_140.itagSequence], r14d
0x1801a44be  mov     [rsp+200h+var_1D8], r15
0x1801a44c3  mov     dword ptr [rsp+200h+var_1E0], r15d
0x1801a44c8  mov     r9d, r14d
0x1801a44cb  lea     r8, [rbp+100h+var_140]
0x1801a44cf  mov     rdx, r13
0x1801a44d2  mov     rcx, rdi
0x1801a44d5  call    ?DsqRetrieveVarColumns@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@KW4tagDsqAllocMethod@@PEAW42@@Z; DsqRetrieveVarColumns(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong,tagDsqAllocMethod,tagDsqAllocMethod *)
0x1801a44da  mov     ebx, eax
0x1801a44dc  mov     ecx, 80000000h
0x1801a44e1  add     eax, ecx
0x1801a44e3  test    ecx, eax
0x1801a44e5  jnz     short loc_1801A44F0
0x1801a44e7  cmp     ebx, r12d
0x1801a44ea  jnz     loc_1801A48F7
0x1801a44f0  lea     rax, [rsp+200h+var_188]
0x1801a44f5  mov     [rbp+100h+var_160], rax
0x1801a44f9  mov     [rbp+100h+var_158], 4
0x1801a4500  mov     eax, [rsp+200h+var_188]
0x1801a4504  mov     [rsi], eax
0x1801a4506  mov     r12, [rbp+100h+var_140.pvData]
0x1801a450a  mov     esi, [rbp+100h+var_140.cbActual]
0x1801a450d  shr     esi, 2
0x1801a4510  test    r12, r12
0x1801a4513  jz      short loc_1801A4551
0x1801a4515  mov     r14d, r15d
0x1801a4518  test    esi, esi
0x1801a451a  jz      short loc_1801A454B
0x1801a451c  mov     r15, r12
0x1801a451f  xor     r9d, r9d; int *
0x1801a4522  mov     r8d, [r15]; unsigned int
0x1801a4525  mov     rdx, [rsp+200h+var_1A8]; unsigned __int64
0x1801a452a  mov     rcx, rdi; unsigned __int64
0x1801a452d  call    ?DsqDeleteFile@@YAJ_K0KPEAH@Z; DsqDeleteFile(unsigned __int64,unsigned __int64,ulong,int *)
0x1801a4532  mov     ebx, eax
0x1801a4534  test    eax, eax
0x1801a4536  js      loc_1801A477D
0x1801a453c  inc     r14d
0x1801a453f  add     r15, 4
0x1801a4543  cmp     r14d, esi
0x1801a4546  jb      short loc_1801A451F
0x1801a4548  xor     r15d, r15d
0x1801a454b  mov     r14d, 1
0x1801a4551  mov     [rsp+200h+var_1C8], r15d; int
0x1801a4556  mov     dword ptr [rsp+200h+var_1D0], r14d; int
0x1801a455b  mov     dword ptr [rsp+200h+var_1D8], r14d; int
0x1801a4560  mov     dword ptr [rsp+200h+var_1E0], r14d; unsigned int *
0x1801a4565  lea     r9, [rbp+100h+var_160]; struct tagDsqSearchKey *
0x1801a4569  xor     r8d, r8d; char *
0x1801a456c  mov     r15, [rbp+100h+arg_20]
0x1801a4573  mov     rdx, r15; tableid
0x1801a4576  mov     rcx, rdi; sesid
0x1801a4579  call    ?DsqSeekToRow@@YAJ_K0PEBDPEAUtagDsqSearchKey@@KHHH@Z; DsqSeekToRow(unsigned __int64,unsigned __int64,char const *,tagDsqSearchKey *,ulong,int,int,int)
0x1801a457e  mov     ebx, eax
0x1801a4580  mov     ecx, 80000000h
0x1801a4585  add     eax, ecx
0x1801a4587  test    ecx, eax
0x1801a4589  jnz     short loc_1801A4597
0x1801a458b  cmp     ebx, 80248007h
0x1801a4591  jnz     loc_1801A48E8
0x1801a4597  cmp     ebx, 80248007h
0x1801a459d  jz      loc_1801A484D
0x1801a45a3  mov     [rsp+200h+var_184], 0FFFFFFFFh
0x1801a45ab  xor     esi, esi
0x1801a45ad  mov     r14, [rbp+100h+tableid]
0x1801a45b4  xorps   xmm0, xmm0
0x1801a45b7  movups  xmmword ptr [rbp+100h+var_140.columnid], xmm0
0x1801a45bb  movups  xmmword ptr [rbp+100h+var_140.cbData], xmm0
0x1801a45bf  movups  xmmword ptr [rbp+100h+var_140.itagSequence], xmm0
0x1801a45c3  mov     eax, cs:dword_180338510
0x1801a45c9  mov     [rbp+100h+var_140.columnid], eax
0x1801a45cc  lea     rax, [rsp+200h+var_184]
0x1801a45d1  mov     [rbp+100h+var_140.pvData], rax
0x1801a45d5  mov     [rbp+100h+var_140.cbData], 4
0x1801a45dc  mov     eax, 1
0x1801a45e1  mov     [rbp+100h+var_140.itagSequence], eax
0x1801a45e4  mov     r9d, eax; unsigned int
0x1801a45e7  lea     r8, [rbp+100h+var_140]; struct JET_RETRIEVECOLUMN *
0x1801a45eb  mov     rdx, r15; unsigned __int64
0x1801a45ee  mov     rcx, rdi; unsigned __int64
0x1801a45f1  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x1801a45f6  mov     ebx, eax
0x1801a45f8  test    eax, eax
0x1801a45fa  js      loc_1801A48E8
0x1801a4600  cmp     [rsp+200h+var_184], 0FFFFFFFFh
0x1801a4605  jz      loc_1801A4790
0x1801a460b  lea     rax, [rsp+200h+var_184]
0x1801a4610  mov     [rbp+100h+var_160], rax
0x1801a4614  mov     [rbp+100h+var_158], 4
0x1801a461b  mov     [rsp+200h+var_1C8], 0; int
0x1801a4623  mov     eax, 1
0x1801a4628  mov     dword ptr [rsp+200h+var_1D0], eax; int
0x1801a462c  mov     dword ptr [rsp+200h+var_1D8], eax; int
0x1801a4630  mov     dword ptr [rsp+200h+var_1E0], eax; unsigned int
0x1801a4634  lea     r9, [rbp+100h+var_160]; struct tagDsqSearchKey *
0x1801a4638  lea     r8, ?c_szIdxEEulaMapLocRegionId@@3QBDB; "EulaIdMapLocRegion"
0x1801a463f  mov     rdx, r14; tableid
0x1801a4642  mov     rcx, rdi; sesid
0x1801a4645  call    ?DsqSeekToRow@@YAJ_K0PEBDPEAUtagDsqSearchKey@@KHHH@Z; DsqSeekToRow(unsigned __int64,unsigned __int64,char const *,tagDsqSearchKey *,ulong,int,int,int)
0x1801a464a  mov     ebx, eax
0x1801a464c  mov     ecx, 80000000h
0x1801a4651  add     eax, ecx
0x1801a4653  test    ecx, eax
0x1801a4655  jnz     short loc_1801A4663
0x1801a4657  cmp     ebx, 80248007h
0x1801a465d  jnz     loc_1801A48E8
0x1801a4663  cmp     esi, 0FFFFF9BDh
0x1801a4669  jz      loc_1801A4790
0x1801a466f  mov     [rbp+100h+var_180], 0
0x1801a4676  mov     [rsp+200h+var_1B0], 0
0x1801a467e  xor     edx, edx; Val
0x1801a4680  mov     r8d, 0F0h; Size
0x1801a4686  lea     rcx, [rbp+100h+var_140]; void *
0x1801a468a  call    memset
0x1801a468f  mov     eax, cs:dword_18033854C
0x1801a4695  mov     [rbp+100h+var_140.columnid], eax
0x1801a4698  lea     rax, [rbp+100h+var_180]
0x1801a469c  mov     [rbp+100h+var_140.pvData], rax
0x1801a46a0  mov     [rbp+100h+var_140.cbData], 4
0x1801a46a7  mov     esi, 1
0x1801a46ac  mov     [rbp+100h+var_140.itagSequence], esi
0x1801a46af  mov     r9d, esi; unsigned int
0x1801a46b2  lea     r8, [rbp+100h+var_140]; struct JET_RETRIEVECOLUMN *
0x1801a46b6  mov     rdx, r14; unsigned __int64
0x1801a46b9  mov     rcx, rdi; unsigned __int64
0x1801a46bc  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x1801a46c1  mov     ebx, eax
0x1801a46c3  test    eax, eax
0x1801a46c5  js      loc_1801A48E8
0x1801a46cb  lea     r9, [rsp+200h+var_1B0]; int *
0x1801a46d0  mov     r8d, [rbp+100h+var_180]; unsigned int
0x1801a46d4  mov     rdx, [rsp+200h+var_1A8]; unsigned __int64
0x1801a46d9  mov     rcx, rdi; unsigned __int64
0x1801a46dc  call    ?DsqDeleteFile@@YAJ_K0KPEAH@Z; DsqDeleteFile(unsigned __int64,unsigned __int64,ulong,int *)
0x1801a46e1  mov     ebx, eax
0x1801a46e3  test    eax, eax
0x1801a46e5  js      loc_1801A4820
0x1801a46eb  cmp     [rsp+200h+var_1B0], 0
0x1801a46f0  jz      short loc_1801A4706
0x1801a46f2  mov     rdx, r14; tableid
0x1801a46f5  mov     rcx, rdi; sesid
0x1801a46f8  call    cs:__imp_JetDelete
0x1801a46fe  test    eax, eax
0x1801a4700  jnz     loc_1801A47DD
0x1801a4706  xor     r9d, r9d; grbit
0x1801a4709  mov     r8d, esi; cRow
0x1801a470c  mov     rdx, r14; tableid
0x1801a470f  mov     rcx, rdi; sesid
0x1801a4712  call    cs:__imp_JetMove
0x1801a4718  mov     esi, eax
0x1801a471a  test    eax, eax
0x1801a471c  jz      loc_1801A4663
0x1801a4722  cmp     eax, 0FFFFF9BDh
0x1801a4727  jz      loc_1801A4663
0x1801a472d  mov     ecx, eax; int
0x1801a472f  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x1801a4734  mov     [rsp+200h+var_1B8], r14
0x1801a4739  mov     ebx, eax
0x1801a473b  lea     rax, aJetmove_0; "JetMove"
0x1801a4742  mov     [rsp+200h+var_1C0], rdi
0x1801a4747  mov     qword ptr [rsp+200h+var_1C8], rax
0x1801a474c  mov     dword ptr [rsp+200h+var_1D0], ebx
0x1801a4750  lea     rax, aDs0x08xHsFaile_0; "DS: 0x%08x: %hs failed. sesid: %Ix. tab"...
0x1801a4757  mov     [rsp+200h+var_1D8], rax
0x1801a475c  mov     [rsp+200h+var_1E0], 0
0x1801a4765  xor     edx, edx
0x1801a4767  xor     ecx, ecx
0x1801a4769  lea     r9d, [rdx+1]
0x1801a476d  mov     r8d, 2000h
0x1801a4773  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801a4778  jmp     loc_1801A48E8
0x1801a477d  cmp     eax, 80248007h
0x1801a4782  jnz     loc_1801A48ED
0x1801a4788  lea     ebx, [rax+2]
0x1801a478b  jmp     loc_1801A48ED
0x1801a4790  mov     rdx, r15; tableid
0x1801a4793  mov     rcx, rdi; sesid
0x1801a4796  call    cs:__imp_JetDelete
0x1801a479c  test    eax, eax
0x1801a479e  jnz     loc_1801A4833
0x1801a47a4  xor     r9d, r9d; grbit
0x1801a47a7  lea     r8d, [rax+1]; cRow
0x1801a47ab  mov     rdx, r15; tableid
0x1801a47ae  mov     rcx, rdi; sesid
0x1801a47b1  call    cs:__imp_JetMove
0x1801a47b7  mov     esi, eax
0x1801a47b9  test    eax, eax
0x1801a47bb  jz      loc_1801A45B4
0x1801a47c1  cmp     eax, 0FFFFF9BDh
0x1801a47c6  jz      loc_1801A484D
0x1801a47cc  mov     ecx, eax; int
0x1801a47ce  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x1801a47d3  mov     [rsp+200h+var_1B8], r15
0x1801a47d8  jmp     loc_1801A4739
0x1801a47dd  mov     ecx, eax; int
0x1801a47df  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
  ... truncated ...
```
