# CCacheStore::OpenContainer(CWxCallerIdentity *,ushort const *,ushort const *,unsigned __int64,ulong,ulong,CContainerProps * *,ulong *)

- ea: `0x18001f5fc`
- end: `0x180020199`
- name: `?OpenContainer@CCacheStore@@QEAAJPEAVCWxCallerIdentity@@PEBG1_KKKPEAPEAVCContainerProps@@PEAK@Z`
- size: `2973`
- prototype: `__int64 __usercall@<rax>(CCacheStore *__hidden this@<rcx>, struct CWxCallerIdentity *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int64, unsigned int, unsigned int, struct CContainerProps **, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180041bf0`

## callees

- `0x18001f5fc`
- `0x1800201a0`
- `0x1800201e8`
- `0x1800204f8`
- `0x180021360`
- `0x18002153c`
- `0x180021e38`
- `0x180021fec`
- `0x180025910`
- `0x180046a1c`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x1800861f8`
- `0x180086300`
- `0x1800acab8`
- `0x1800b64b0`
- `0x1800ee168`
- `0x1800eee94`
- `0x1800fa844`
- `0x18011eb38`
- `0x18014a7a0`
- `0x1801a997c`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e3918`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001faa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa1a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001fe5c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001fe5c`
- `ESENT!JetSetColumn` at `0x18001f8f7`
- `ESENT!JetSetColumn` at `0x18001f938`
- `ESENT!JetSetColumn` at `0x18001f994`
- `ESENT!JetSetColumn` at `0x18001f8f7`
- `ESENT!JetSetColumn` at `0x18001f938`
- `ESENT!JetSetColumn` at `0x18001f994`
- `ESENT!JetRetrieveColumn` at `0x18001f814`
- `ESENT!JetRetrieveColumn` at `0x18001fcd8`
- `ESENT!JetRetrieveColumn` at `0x18001f814`
- `ESENT!JetRetrieveColumn` at `0x18001fcd8`
- `ESENT!JetCommitTransaction` at `0x18001fb30`
- `ESENT!JetCommitTransaction` at `0x18001fb30`
- `ESENT!JetUpdate` at `0x18001f9bb`
- `ESENT!JetUpdate` at `0x180020119`
- `ESENT!JetUpdate` at `0x18001f9bb`
- `ESENT!JetUpdate` at `0x180020119`
- `ESENT!JetPrepareUpdate` at `0x18001f8a7`
- `ESENT!JetPrepareUpdate` at `0x18001f9e4`
- `ESENT!JetPrepareUpdate` at `0x18001fc70`
- `ESENT!JetPrepareUpdate` at `0x18001f8a7`
- `ESENT!JetPrepareUpdate` at `0x18001f9e4`
- `ESENT!JetPrepareUpdate` at `0x18001fc70`
- `ESENT!JetRollback` at `0x18001f9f0`
- `ESENT!JetRollback` at `0x18001fe1b`
- `ESENT!JetRollback` at `0x18001f9f0`
- `ESENT!JetRollback` at `0x18001fe1b`
- `ESENT!JetBeginTransaction` at `0x18001f729`
- `ESENT!JetBeginTransaction` at `0x18001f729`

## pseudocode

```c
__int64 __fastcall CCacheStore::OpenContainer(
        CJetContextList **this,
        const unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned int a7,
        struct CContainerProps **a8,
        unsigned int *a9)
{
  struct CContainerProps **v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // r12
  unsigned int *v11; // rax
  JET_ERR BasicColumn; // ebx
  CJetContextList **v16; // rsi
  unsigned int v17; // r9d
  JET_SESID *v18; // rdi
  JET_ERR v19; // eax
  int v20; // eax
  JET_ERR v21; // eax
  int v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  CContainerProps *v25; // rdi
  int v26; // esi
  int v29; // r14d
  JET_ERR v30; // eax
  unsigned int v31; // r15d
  int v32; // edi
  int v33; // ecx
  CContainerProps *v34; // rax
  JET_ERR v35; // eax
  BOOL v36; // eax
  JET_ERR v37; // eax
  int v38; // eax
  DWORD FileAttributesW; // eax
  JET_ERR v40; // eax
  const unsigned __int16 *cbData; // [rsp+20h] [rbp-E0h]
  unsigned int *pcbActual; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *grbit; // [rsp+30h] [rbp-D0h]
  JET_RETINFO *pretinfo; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v45; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v46; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+60h] [rbp-A0h]
  int v49; // [rsp+68h] [rbp-98h]
  unsigned int v50; // [rsp+6Ch] [rbp-94h]
  CJetContext *v51; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v52; // [rsp+78h] [rbp-88h]
  unsigned int *v53; // [rsp+80h] [rbp-80h]
  CContainerProps *v54; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v55[2]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+B4h] [rbp-4Ch]
  struct CContainerProps **v58; // [rsp+B8h] [rbp-48h]
  CContainerProps *v59; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v60[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 pvData; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v62; // [rsp+D8h] [rbp-28h] BYREF
  BOOL v63; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int v64; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v65; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v66[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v67; // [rsp+100h] [rbp+0h] BYREF

  v9 = a8;
  v10 = (struct _RTL_CRITICAL_SECTION *)(this + 35);
  v11 = a9;
  v52 = a4;
  v58 = a8;
  v55[0] = (unsigned __int16 *)&Data;
  v66[0] = (unsigned __int16 *)&Data;
  lpFileName[0] = &Data;
  v53 = a9;
  v49 = 0;
  *(_DWORD *)v60 = 0;
  pvData = 0;
  v67 = 0;
  v63 = 0;
  v64 = 0;
  v55[1] = 0;
  v66[1] = 0;
  lpFileName[1] = 0;
  v51 = 0;
  v54 = 0;
  v59 = 0;
  v65 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qqSSiDdqq(
      (unsigned int)&Data,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      a5,
      a6,
      a7,
      (__int64)a8,
      (__int64)a9);
    a4 = v52;
    v11 = v53;
  }
  if ( v9 )
    *v9 = 0;
  if ( v11 )
    *v11 = 0;
  BasicColumn = ValidateContainerDirectory(a4, v60);
  if ( BasicColumn < 0 )
  {
    v16 = this + 40;
    goto LABEL_35;
  }
  if ( v10 )
  {
    EnterCriticalSection(v10);
    v49 = 1;
  }
  v16 = this + 40;
  BasicColumn = CJetContextList::AcquireContext(this[40], &v51, 0);
  if ( BasicColumn < 0 )
    goto LABEL_35;
  v18 = (JET_SESID *)v51;
  BasicColumn = CJetContext::SetCurrentIndex(v51, 1u, L"PartitionIdIndex", v17);
  if ( BasicColumn < 0 )
    goto LABEL_35;
  v19 = JetBeginTransaction(v18[2]);
  BasicColumn = HRESULTFromJET_ERR(v19, 1);
  if ( BasicColumn < 0 )
    goto LABEL_35;
  v48 = 0;
  v50 = a6 & 0x30;
  if ( *((_DWORD *)a2 + 1) == 3 || (a6 & 0x30) == 0 )
  {
    BasicColumn = CWxString::Set((CWxString *)v55, a2[1]);
    if ( BasicColumn < 0 )
      goto LABEL_34;
    v20 = SeekToContainer((struct CJetContext *)v18, v55[0], a3);
    BasicColumn = v20;
    if ( v20 < 0 )
      goto LABEL_34;
    if ( v20 )
    {
      *(_DWORD *)v60 = 0;
      v35 = JetPrepareUpdate(v18[2], v18[4], 0);
      BasicColumn = HRESULTFromJET_ERR(v35, 1);
      if ( BasicColumn < 0 )
        goto LABEL_34;
      v36 = *((_DWORD *)a2 + 1) == 1 && (a6 & 0x40) == 0;
      v63 = v36;
      v37 = JetRetrieveColumn(v18[2], v18[4], **(_DWORD **)(v18[5] + 8), &pvData, 8u, &v64, 1u, 0);
      BasicColumn = HRESULTFromJET_ERR(v37, 1);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetStringColumn((CJetContext *)v18, 1u, v55[0]);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetStringColumn((CJetContext *)v18, 2u, a3);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 3u, &v63, 4u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 5u, &v67, 8u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetStringColumn((CJetContext *)v18, 8u, 0);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBinaryColumn((CJetContext *)v18, 9u, 0, 0);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBinaryColumn((CJetContext *)v18, 0xAu, 0, 0);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 4u, &a6, 4u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 6u, &a5, 8u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetStringColumn((CJetContext *)v18, 7u, v52);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 0xBu, &v65, 8u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 0xCu, &a7, 4u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v18, 0xDu, &v65, 8u);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      v40 = JetUpdate(v18[2], v18[4], 0, 0, 0);
      BasicColumn = HRESULTFromJET_ERR(v40, 1);
      if ( BasicColumn < 0 )
        goto LABEL_33;
      v48 = 1;
    }
    else
    {
      v57 = 0;
      v62 = 0;
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 0, (__int64)&pvData);
      v21 = JetRetrieveColumn(v18[2], v18[4], **(_DWORD **)(v18[5] + 8), &pvData, 8u, &v62, 0, 0);
      BasicColumn = HRESULTFromJET_ERR(v21, 1);
      if ( BasicColumn >= 0 )
      {
        if ( v62 == 8 )
        {
          BasicColumn = 0;
        }
        else
        {
          BasicColumn = -2147418113;
          v57 = 214;
        }
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BasicColumn);
      if ( BasicColumn < 0 )
        goto LABEL_34;
      *((_QWORD *)this[42] + 1) = pvData;
      v22 = CWxRefMap<CContainerPropsMap,CContainerProps>::Find(this[41], this[42], &v54);
      BasicColumn = v22;
      if ( v22 < 0 )
        goto LABEL_34;
      if ( v22 != 1 )
      {
        v29 = 1;
        *(_DWORD *)v60 = 0;
        goto LABEL_52;
      }
      v23 = JetPrepareUpdate(v18[2], v18[4], 2u);
      BasicColumn = HRESULTFromJET_ERR(v23, BasicColumn);
      if ( BasicColumn < 0 )
        goto LABEL_34;
      BasicColumn = JetSetColumn(v18[2], v18[4], *(_DWORD *)(*(_QWORD *)(v18[5] + 8) + 16LL), &a6, 4u, 0, 0);
      if ( BasicColumn < 0
        || (BasicColumn = JetSetColumn(v18[2], v18[4], *(_DWORD *)(*(_QWORD *)(v18[5] + 8) + 24LL), &a5, 8u, 0, 0),
            BasicColumn < 0)
        || (BasicColumn = CJetContext::SetStringColumn((CJetContext *)v18, 7u, v52), BasicColumn < 0)
        || (BasicColumn = JetSetColumn(v18[2], v18[4], *(_DWORD *)(*(_QWORD *)(v18[5] + 8) + 48LL), &a7, 4u, 0, 0),
            BasicColumn < 0)
        || (v24 = JetUpdate(v18[2], v18[4], 0, 0, 0), BasicColumn = HRESULTFromJET_ERR(v24, 1), BasicColumn < 0) )
      {
LABEL_33:
        JetPrepareUpdate(v18[2], v18[4], 3u);
        goto LABEL_34;
      }
    }
    v29 = 0;
LABEL_52:
    v30 = JetCommitTransaction(v18[2], 1u);
    BasicColumn = HRESULTFromJET_ERR(v30, 1);
    if ( BasicColumn >= 0 )
    {
      CCacheStore::ReleaseContainerContext((CCacheStore *)this, &v51);
      if ( *(_DWORD *)v60 )
      {
        BasicColumn = CCacheStore::PurgeContainer((CCacheStore *)this, pvData, 0);
        if ( BasicColumn < 0 )
          goto LABEL_35;
      }
      v31 = v50;
      v32 = 0;
      goto LABEL_55;
    }
LABEL_34:
    JetRollback(v18[2], 0);
    goto LABEL_35;
  }
  v38 = SeekToContainer((struct CJetContext *)v18, "M", a3);
  BasicColumn = v38;
  if ( v38 < 0 )
    goto LABEL_34;
  if ( v38 )
  {
    BasicColumn = -2147024891;
    goto LABEL_34;
  }
  BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v18, 4u, &a6, 4u);
  if ( BasicColumn < 0 )
    goto LABEL_34;
  v31 = v50;
  if ( (a6 & v50) != v50 )
  {
    BasicColumn = -2147024891;
    goto LABEL_34;
  }
  BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v18, 0, &pvData, 8u);
  if ( BasicColumn < 0 )
    goto LABEL_34;
  BasicColumn = CJetContext::GetStringColumn((CJetContext *)v18, 7u, (struct CWxString *)v66);
  if ( BasicColumn < 0 )
    goto LABEL_34;
  JetRollback(v18[2], 0);
  CCacheStore::ReleaseContainerContext((CCacheStore *)this, &v51);
  BasicColumn = CWxString::SetPath(
                  (CWxString *)lpFileName,
                  v66[0],
                  L"container.dat",
                  0,
                  cbData,
                  (const unsigned __int16 *)pcbActual,
                  grbit,
                  (const unsigned __int16 *)pretinfo,
                  v45,
                  v46,
                  v47);
  if ( BasicColumn >= 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName[0]);
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
    {
      v32 = 1;
      *(_DWORD *)v60 = 0;
      v29 = 0;
LABEL_55:
      BasicColumn = CCacheStore::AcquireContainerProps((CCacheStore *)this, pvData, &v59);
      if ( BasicColumn >= 0 )
      {
        if ( v48 )
          *((_DWORD *)v59 + 57) = 1;
        if ( !v29 || (BasicColumn = CContainerProps::UpdateContainerInfo(v59, v52, a5, a6, a7), BasicColumn >= 0) )
        {
          if ( v10 && v49 )
          {
            LeaveCriticalSection(v10);
            v49 = 0;
          }
          if ( v32 )
          {
            v33 = (v31 >> 4) & 1;
            if ( (v31 & 0x20) != 0 )
              v33 |= 2u;
          }
          else
          {
            v33 = 15;
            if ( (a6 & 0x30) != 0 )
              v33 = 7;
          }
          v34 = v59;
          v59 = 0;
          *v58 = v34;
          *v53 = v33;
        }
      }
      goto LABEL_35;
    }
    BasicColumn = CCacheStore::PurgeContainer((CCacheStore *)this, pvData, 1);
    if ( BasicColumn >= 0 )
      BasicColumn = -2147024891;
  }
LABEL_35:
  CJetContextList::ReleaseContext(*v16, &v51);
  v25 = v59;
  if ( v59 )
  {
    v26 = 0;
    v59 = 0;
    if ( v10 )
    {
      EnterCriticalSection(v10);
      v26 = 1;
    }
    if ( (*((_DWORD *)v25 + 4))-- == 1 )
      CWxRefMap<CContainerPropsMap,CContainerProps>::Delete(this[41], v25);
    CContainerProps::Release(v25);
    if ( v26 && v10 )
      LeaveCriticalSection(v10);
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 43, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)BasicColumn);
  if ( v54 )
    CContainerProps::Release(v54);
  CWxString::_Release((CWxString *)lpFileName);
  CWxString::_Release((CWxString *)v66);
  CWxString::_Release((CWxString *)v55);
  if ( v49 && v10 )
    LeaveCriticalSection(v10);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x18001f5fc  push    rbp
0x18001f5fe  push    rbx
0x18001f5ff  push    rsi
0x18001f600  push    rdi
0x18001f601  push    r12
0x18001f603  push    r13
0x18001f605  push    r14
0x18001f607  push    r15
0x18001f609  lea     rbp, [rsp-18h]
0x18001f60e  sub     rsp, 118h
0x18001f615  mov     rax, cs:__security_cookie
0x18001f61c  xor     rax, rsp
0x18001f61f  mov     [rbp+50h+var_48], rax
0x18001f623  mov     rbx, [rbp+50h+arg_38]
0x18001f62a  lea     r12, [rcx+118h]
0x18001f631  mov     rax, [rbp+50h+arg_40]
0x18001f638  xor     edi, edi
0x18001f63a  mov     r13, rcx
0x18001f63d  mov     [rsp+150h+var_D8], r9
0x18001f642  lea     rcx, Data
0x18001f649  mov     [rbp+50h+var_98], rbx
0x18001f64d  mov     [rbp+50h+var_C0], rcx
0x18001f651  mov     r15, r8
0x18001f654  mov     [rbp+50h+var_60], rcx
0x18001f658  mov     r14, rdx
0x18001f65b  mov     [rbp+50h+lpFileName], rcx
0x18001f65f  mov     [rbp+50h+var_D0], rax
0x18001f663  mov     [rsp+150h+var_EC], edi
0x18001f667  mov     [rsp+150h+var_E8], edi
0x18001f66b  mov     dword ptr [rbp+50h+var_88], edi
0x18001f66e  mov     [rbp+50h+pvData], rdi
0x18001f672  mov     [rbp+50h+var_50], rdi
0x18001f676  mov     [rbp+50h+var_74], edi
0x18001f679  mov     [rbp+50h+var_70], edi
0x18001f67c  mov     [rbp+50h+var_B8], rdi
0x18001f680  mov     [rbp+50h+var_58], rdi
0x18001f684  mov     [rbp+50h+var_A8], rdi
0x18001f688  mov     [rsp+150h+var_E0], rdi
0x18001f68d  mov     [rbp+50h+var_C8], rdi
0x18001f691  mov     [rbp+50h+var_90], rdi
0x18001f695  mov     [rbp+50h+var_68], rdi
0x18001f699  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18001f6a0  jnz     loc_18001FACB
0x18001f6a6  test    rbx, rbx
0x18001f6a9  jz      short loc_18001F6AE
0x18001f6ab  mov     [rbx], rdi
0x18001f6ae  test    rax, rax
0x18001f6b1  jz      short loc_18001F6B5
0x18001f6b3  mov     [rax], edi
0x18001f6b5  lea     rdx, [rbp+50h+var_88]; unsigned __int16 *
0x18001f6b9  mov     rcx, r9; unsigned __int16 *
0x18001f6bc  call    ?ValidateContainerDirectory@@YAJPEBGPEAH@Z; ValidateContainerDirectory(ushort const *,int *)
0x18001f6c1  mov     ebx, eax
0x18001f6c3  test    eax, eax
0x18001f6c5  js      loc_18001FC4A
0x18001f6cb  test    r12, r12
0x18001f6ce  jz      short loc_18001F6E1
0x18001f6d0  mov     rcx, r12; lpCriticalSection
0x18001f6d3  call    cs:__imp_EnterCriticalSection
0x18001f6d9  mov     [rsp+150h+var_E8], 1
0x18001f6e1  lea     rsi, [r13+140h]
0x18001f6e8  xor     r8d, r8d; int *
0x18001f6eb  mov     rcx, [rsi]; this
0x18001f6ee  lea     rdx, [rsp+150h+var_E0]; struct CJetContext **
0x18001f6f3  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18001f6f8  mov     ebx, eax
0x18001f6fa  test    eax, eax
0x18001f6fc  js      loc_18001FBEA
0x18001f702  mov     rdi, [rsp+150h+var_E0]
0x18001f707  lea     r8, aPartitionidind; "PartitionIdIndex"
0x18001f70e  mov     rcx, rdi; this
0x18001f711  mov     edx, 1; unsigned int
0x18001f716  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x18001f71b  mov     ebx, eax
0x18001f71d  test    eax, eax
0x18001f71f  js      loc_18001FD29
0x18001f725  mov     rcx, [rdi+10h]; sesid
0x18001f729  call    cs:__imp_JetBeginTransaction
0x18001f72f  mov     ecx, eax; int
0x18001f731  mov     edx, 1; int
0x18001f736  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18001f73b  mov     ebx, eax
0x18001f73d  test    eax, eax
0x18001f73f  js      loc_18001F9F6
0x18001f745  mov     eax, [rbp+50h+arg_28]
0x18001f74b  and     eax, 30h
0x18001f74e  mov     [rsp+150h+var_F0], 0
0x18001f756  cmp     dword ptr [r14+4], 3
0x18001f75b  mov     [rsp+150h+var_E4], eax
0x18001f75f  jnz     loc_18001FD36
0x18001f765  mov     rdx, [r14+8]; unsigned __int16 *
0x18001f769  lea     rcx, [rbp+50h+var_C0]; this
0x18001f76d  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x18001f772  mov     ebx, eax
0x18001f774  test    eax, eax
0x18001f776  js      loc_18001FEB6
0x18001f77c  mov     rdx, [rbp+50h+var_C0]; unsigned __int16 *
0x18001f780  mov     r8, r15; unsigned __int16 *
0x18001f783  mov     rcx, rdi; struct CJetContext *
0x18001f786  call    ?SeekToContainer@@YAJPEAVCJetContext@@PEBG1@Z; SeekToContainer(CJetContext *,ushort const *,ushort const *)
0x18001f78b  mov     ebx, eax
0x18001f78d  test    eax, eax
0x18001f78f  js      loc_18001FEC3
0x18001f795  jnz     loc_18001FC5E
0x18001f79b  mov     [rbp+50h+var_9C], 0
0x18001f7a2  mov     [rbp+50h+var_78], 0
0x18001f7a9  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18001f7b0  mov     r14d, 8
0x18001f7b6  jz      short loc_18001F7DE
0x18001f7b8  lea     rax, [rbp+50h+pvData]
0x18001f7bc  mov     dword ptr [rsp+150h+pcbActual], r14d
0x18001f7c1  lea     edx, [r14+9]
0x18001f7c5  mov     qword ptr [rsp+150h+cbData], rax
0x18001f7ca  mov     ecx, 40Ch
0x18001f7cf  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18001f7d6  xor     r9d, r9d
0x18001f7d9  call    WPP_SF_dqd
0x18001f7de  mov     rax, [rdi+28h]
0x18001f7e2  lea     r9, [rbp+50h+pvData]; pvData
0x18001f7e6  mov     rdx, [rdi+20h]; tableid
0x18001f7ea  mov     rcx, [rdi+10h]; sesid
0x18001f7ee  mov     [rsp+150h+pretinfo], 0; pretinfo
0x18001f7f7  mov     r8, [rax+8]
0x18001f7fb  lea     rax, [rbp+50h+var_78]
0x18001f7ff  mov     [rsp+150h+grbit], 0; grbit
0x18001f807  mov     [rsp+150h+pcbActual], rax; pcbActual
0x18001f80c  mov     [rsp+150h+cbData], r14d; cbData
0x18001f811  mov     r8d, [r8]; columnid
0x18001f814  call    cs:__imp_JetRetrieveColumn
0x18001f81a  mov     ecx, eax; int
0x18001f81c  mov     edx, 1; int
0x18001f821  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18001f826  mov     ebx, eax
0x18001f828  test    eax, eax
0x18001f82a  js      short loc_18001F838
0x18001f82c  cmp     [rbp+50h+var_78], r14d
0x18001f830  jnz     loc_18001FD18
0x18001f836  xor     ebx, ebx
0x18001f838  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18001f83f  jz      short loc_18001F85A
0x18001f841  mov     edx, 12h
0x18001f846  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18001f84d  mov     ecx, 40Ch
0x18001f852  mov     r9d, ebx
0x18001f855  call    WPP_SF_d
0x18001f85a  test    ebx, ebx
0x18001f85c  js      loc_18001FED0
0x18001f862  mov     rcx, [r13+150h]
0x18001f869  lea     r8, [rbp+50h+var_C8]
0x18001f86d  mov     rax, [rbp+50h+pvData]
0x18001f871  mov     [rcx+8], rax
0x18001f875  mov     rdx, [r13+150h]
0x18001f87c  mov     rcx, [r13+148h]
0x18001f883  call    ?Find@?$CWxRefMap@VCContainerPropsMap@@VCContainerProps@@@@QEAAJPEAVCContainerProps@@PEAPEAV2@@Z; CWxRefMap<CContainerPropsMap,CContainerProps>::Find(CContainerProps *,CContainerProps * *)
0x18001f888  mov     ebx, eax
0x18001f88a  test    eax, eax
0x18001f88c  js      loc_18001FEDD
0x18001f892  cmp     eax, 1
0x18001f895  jnz     loc_18001FB1A
0x18001f89b  mov     rdx, [rdi+20h]; tableid
0x18001f89f  lea     r8d, [rax+1]; prep
0x18001f8a3  mov     rcx, [rdi+10h]; sesid
0x18001f8a7  call    cs:__imp_JetPrepareUpdate
0x18001f8ad  mov     ecx, eax; int
0x18001f8af  mov     edx, ebx; int
0x18001f8b1  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18001f8b6  mov     ebx, eax
0x18001f8b8  test    eax, eax
0x18001f8ba  js      loc_18001F9EA
0x18001f8c0  mov     rax, [rdi+28h]
0x18001f8c4  lea     r9, [rbp+50h+arg_28]; pvData
0x18001f8cb  mov     rdx, [rdi+20h]; tableid
0x18001f8cf  mov     r15d, 4
0x18001f8d5  mov     rcx, [rdi+10h]; sesid
0x18001f8d9  mov     qword ptr [rsp+150h+grbit], 0; psetinfo
0x18001f8e2  mov     r8, [rax+8]
0x18001f8e6  mov     dword ptr [rsp+150h+pcbActual], 0; grbit
0x18001f8ee  mov     [rsp+150h+cbData], r15d; cbData
0x18001f8f3  mov     r8d, [r8+10h]; columnid
0x18001f8f7  call    cs:__imp_JetSetColumn
0x18001f8fd  mov     ebx, eax
0x18001f8ff  test    eax, eax
0x18001f901  js      loc_18001FEEA
0x18001f907  mov     rax, [rdi+28h]
0x18001f90b  lea     r9, [rbp+50h+arg_20]; pvData
0x18001f912  mov     rdx, [rdi+20h]; tableid
0x18001f916  mov     rcx, [rdi+10h]; sesid
0x18001f91a  mov     qword ptr [rsp+150h+grbit], 0; psetinfo
0x18001f923  mov     r8, [rax+8]
0x18001f927  mov     dword ptr [rsp+150h+pcbActual], 0; grbit
0x18001f92f  mov     [rsp+150h+cbData], r14d; cbData
0x18001f934  mov     r8d, [r8+18h]; columnid
0x18001f938  call    cs:__imp_JetSetColumn
0x18001f93e  mov     ebx, eax
0x18001f940  test    eax, eax
0x18001f942  js      loc_18001FEF7
0x18001f948  mov     r8, [rsp+150h+var_D8]; unsigned __int16 *
0x18001f94d  lea     edx, [r15+3]; unsigned int
0x18001f951  mov     rcx, rdi; this
0x18001f954  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x18001f959  mov     ebx, eax
0x18001f95b  test    eax, eax
0x18001f95d  js      loc_18001FF04
0x18001f963  mov     rax, [rdi+28h]
0x18001f967  lea     r9, [rbp+50h+arg_30]; pvData
0x18001f96e  mov     rdx, [rdi+20h]; tableid
0x18001f972  mov     rcx, [rdi+10h]; sesid
0x18001f976  mov     qword ptr [rsp+150h+grbit], 0; psetinfo
0x18001f97f  mov     r8, [rax+8]
0x18001f983  mov     dword ptr [rsp+150h+pcbActual], 0; grbit
0x18001f98b  mov     [rsp+150h+cbData], r15d; cbData
0x18001f990  mov     r8d, [r8+30h]; columnid
0x18001f994  call    cs:__imp_JetSetColumn
0x18001f99a  mov     ebx, eax
0x18001f99c  test    eax, eax
0x18001f99e  js      loc_18001FF11
0x18001f9a4  mov     rdx, [rdi+20h]; tableid
0x18001f9a8  xor     r9d, r9d; cbBookmark
0x18001f9ab  mov     rcx, [rdi+10h]; sesid
0x18001f9af  xor     r8d, r8d; pvBookmark
0x18001f9b2  mov     qword ptr [rsp+150h+cbData], 0; pcbActual
0x18001f9bb  call    cs:__imp_JetUpdate
0x18001f9c1  mov     ecx, eax; int
0x18001f9c3  lea     edx, [r15-3]; int
0x18001f9c7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18001f9cc  mov     ebx, eax
0x18001f9ce  test    eax, eax
0x18001f9d0  jns     loc_18002013D
0x18001f9d6  mov     rdx, [rdi+20h]; tableid
0x18001f9da  mov     r8d, 3; prep
0x18001f9e0  mov     rcx, [rdi+10h]; sesid
0x18001f9e4  call    cs:__imp_JetPrepareUpdate
0x18001f9ea  mov     rcx, [rdi+10h]; sesid
0x18001f9ee  xor     edx, edx; grbit
0x18001f9f0  call    cs:__imp_JetRollback
0x18001f9f6  mov     rcx, [rsi]; this
0x18001f9f9  lea     rdx, [rsp+150h+var_E0]; struct CJetContext **
0x18001f9fe  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x18001fa03  mov     rdi, [rbp+50h+var_90]
0x18001fa07  test    rdi, rdi
0x18001fa0a  jz      short loc_18001FA49
0x18001fa0c  xor     esi, esi
0x18001fa0e  mov     [rbp+50h+var_90], rsi
0x18001fa12  test    r12, r12
0x18001fa15  jz      short loc_18001FA25
0x18001fa17  mov     rcx, r12; lpCriticalSection
0x18001fa1a  call    cs:__imp_EnterCriticalSection
0x18001fa20  mov     esi, 1
0x18001fa25  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x18001fa29  jz      loc_18001FB8D
0x18001fa2f  mov     rcx, rdi; this
0x18001fa32  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x18001fa37  test    esi, esi
0x18001fa39  jz      short loc_18001FA49
0x18001fa3b  test    r12, r12
0x18001fa3e  jz      short loc_18001FA49
0x18001fa40  mov     rcx, r12; lpCriticalSection
0x18001fa43  call    cs:__imp_LeaveCriticalSection
0x18001fa49  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18001fa50  jz      short loc_18001FA6B
0x18001fa52  mov     edx, 2Bh ; '+'
0x18001fa57  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x18001fa5e  mov     ecx, 40Ch
0x18001fa63  mov     r9d, ebx
0x18001fa66  call    WPP_SF_d
0x18001fa6b  mov     rcx, [rbp+50h+var_C8]; this
0x18001fa6f  test    rcx, rcx
0x18001fa72  jz      short loc_18001FA79
0x18001fa74  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x18001fa79  lea     rcx, [rbp+50h+lpFileName]; this
0x18001fa7d  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18001fa82  lea     rcx, [rbp+50h+var_60]; this
0x18001fa86  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18001fa8b  lea     rcx, [rbp+50h+var_C0]; this
0x18001fa8f  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18001fa94  cmp     [rsp+150h+var_E8], 0
0x18001fa99  jz      short loc_18001FAA9
0x18001fa9b  test    r12, r12
0x18001fa9e  jz      short loc_18001FAA9
0x18001faa0  mov     rcx, r12; lpCriticalSection
0x18001faa3  call    cs:__imp_LeaveCriticalSection
0x18001faa9  mov     eax, ebx
0x18001faab  mov     rcx, [rbp+50h+var_48]
0x18001faaf  xor     rcx, rsp; StackCookie
0x18001fab2  call    __security_check_cookie
0x18001fab7  add     rsp, 118h
0x18001fabe  pop     r15
0x18001fac0  pop     r14
0x18001fac2  pop     r13
0x18001fac4  pop     r12
0x18001fac6  pop     rdi
0x18001fac7  pop     rsi
0x18001fac8  pop     rbx
0x18001fac9  pop     rbp
0x18001faca  retn
0x18001facb  mov     [rsp+150h+var_F8], rax
0x18001fad0  mov     eax, [rbp+50h+arg_30]
0x18001fad6  mov     [rsp+150h+var_100], rbx
0x18001fadb  mov     dword ptr [rsp+150h+var_108], eax
0x18001fadf  mov     eax, [rbp+50h+arg_28]
  ... truncated ...
```
