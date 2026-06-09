# CServiceCache::AddService(CSusEseSession *,_GUID const &,tagDSServicePropsAll const *)

- ea: `0x1801882f4`
- end: `0x180188c7f`
- name: `?AddService@CServiceCache@@QEAAJPEAVCSusEseSession@@AEBU_GUID@@PEBUtagDSServicePropsAll@@@Z`
- size: `2443`
- prototype: `int(CServiceCache *__hidden this, struct CSusEseSession *, const struct _GUID *, const struct tagDSServicePropsAll *)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180189f7c`
- `0x18018b0c0`
- `0x18018f57c`

## callees

- `0x180015cec`
- `0x18011b214`
- `0x18012b618`
- `0x1801826f4`
- `0x180182c4c`
- `0x1801844a0`
- `0x1801844ec`
- `0x18018457c`
- `0x180184634`
- `0x180184708`
- `0x1801853f0`
- `0x180187728`
- `0x1801882f4`
- `0x180188c88`
- `0x18018baf0`
- `0x18018c728`
- `0x18018c830`
- `0x18018fef8`
- `0x1801900ec`
- `0x1801f755c`
- `0x180238960`
- `0x180239110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18018842d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18018842d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180188688`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180188688`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801885fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180188be7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180188c36`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801885fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180188be7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180188c36`
- `ESENT!JetDeleteTableA` at `0x180188568`
- `ESENT!JetDeleteTableA` at `0x180188802`
- `ESENT!JetDeleteTableA` at `0x180188568`
- `ESENT!JetDeleteTableA` at `0x180188802`

## string_xrefs

- `0x180188400`: `C:\__w\1\s\src\Client\Engine\store\dsqservice.cpp`
- `0x18018859f`: `0x%08x: JetDeleteTable failed for table %hs. sesid: %Ix. dbid: %lx`
- `0x18018861c`: `Failed to add service %ls: 0x%08lX`
- `0x180188c01`: `Service %ls added`
- `0x180188c48`: `Default service for AU is %ls`
- `0x18018890b`: `tbPerSrvUpdate`
- `0x18018895f`: `tbPerSrvUserUpdateData`
- `0x18018847a`: `tbServiceData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CServiceCache::AddService(
        CServiceCache *this,
        JET_SESID *a2,
        const struct _GUID *a3,
        const struct tagDSServicePropsAll *a4)
{
  const struct _GUID *v5; // r13
  unsigned int v7; // esi
  int v8; // r12d
  JET_SESID v9; // r15
  int updated; // ebx
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // rax
  JET_DBID v14; // r13d
  __int64 v15; // r8
  __int64 v16; // r12
  _QWORD *v17; // r15
  __int64 v18; // r9
  JET_ERR v19; // eax
  JET_PCSTR v20; // rax
  int v21; // edi
  struct _RTL_CRITICAL_SECTION *v22; // rbx
  __int128 *v24; // r14
  int v25; // eax
  unsigned int v26; // eax
  int v27; // eax
  JET_ERR v28; // eax
  unsigned int v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // r9
  int v32; // edx
  char *v33; // rax
  char *v34; // rcx
  __int64 v35; // rcx
  unsigned int v36; // edx
  unsigned int v37; // edx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r9
  int v42; // eax
  unsigned int v43; // ecx
  __int64 v44; // rdx
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  unsigned int v47; // [rsp+28h] [rbp-D8h]
  unsigned int v48; // [rsp+28h] [rbp-D8h]
  __int64 v49; // [rsp+38h] [rbp-C8h]
  JET_SESID v50; // [rsp+40h] [rbp-C0h]
  JET_DBID v51; // [rsp+48h] [rbp-B8h]
  int v52; // [rsp+50h] [rbp-B0h]
  int v53; // [rsp+58h] [rbp-A8h]
  unsigned int v55[2]; // [rsp+68h] [rbp-98h] BYREF
  JET_SESID sesid; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+78h] [rbp-88h]
  unsigned int v58; // [rsp+7Ch] [rbp-84h]
  int v59; // [rsp+80h] [rbp-80h]
  struct CSusEseSession *v60; // [rsp+88h] [rbp-78h]
  struct _GUID v61; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v63[2]; // [rsp+A8h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+B8h] [rbp-48h]
  _QWORD v65[3]; // [rsp+C8h] [rbp-38h] BYREF
  JET_PCSTR szTableName[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v67; // [rsp+F0h] [rbp-10h]
  __int128 v68; // [rsp+100h] [rbp+0h]
  JET_PCSTR v69[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v70; // [rsp+120h] [rbp+20h]
  __int128 v71; // [rsp+130h] [rbp+30h]
  __int128 v72; // [rsp+140h] [rbp+40h] BYREF
  __int128 v73; // [rsp+150h] [rbp+50h]
  __int128 v74; // [rsp+160h] [rbp+60h]
  __int128 v75; // [rsp+170h] [rbp+70h]
  __int128 v76; // [rsp+180h] [rbp+80h]
  __int128 v77; // [rsp+190h] [rbp+90h]
  __int128 v78; // [rsp+1A0h] [rbp+A0h]
  __int128 v79; // [rsp+1B0h] [rbp+B0h]
  __int128 v80; // [rsp+1C0h] [rbp+C0h]
  __int128 v81; // [rsp+1D0h] [rbp+D0h]
  __int128 v82; // [rsp+1E0h] [rbp+E0h]
  __int128 v83; // [rsp+1F0h] [rbp+F0h]
  __int128 v84; // [rsp+200h] [rbp+100h]
  __int128 v85; // [rsp+210h] [rbp+110h]
  __int128 v86; // [rsp+220h] [rbp+120h]
  OLECHAR sz; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v88[72]; // [rsp+232h] [rbp+132h] BYREF
  __int16 v89; // [rsp+27Ah] [rbp+17Ah]

  v5 = a3;
  v60 = (struct CSusEseSession *)a2;
  *(_QWORD *)&v61.Data1 = a2 + 1;
  v65[0] = 0;
  v65[1] = (unsigned __int64)(a2 + 1) & -(__int64)(a2 != 0);
  v65[2] = 0;
  lpCriticalSection[0] = (LPCRITICAL_SECTION)((char *)this + 40);
  v57 = 0;
  lpCriticalSection[1] = 0;
  v63[0] = &CSusEseTransaction::`vftable';
  v63[1] = 0;
  *(_OWORD *)szTableName = g_tablePerSrvUpdate;
  v67 = *(_OWORD *)&off_1802A2EF8;
  v68 = *(_OWORD *)&off_1802A2F08;
  *(_OWORD *)v69 = g_tablePerSrvUserUpdateData;
  v70 = *(_OWORD *)&off_1802A2EC8;
  v71 = *(_OWORD *)&off_1802A2ED8;
  v62 = -1;
  v7 = 0;
  v8 = 0;
  v52 = 0;
  v55[0] = 0;
  v58 = 0;
  v59 = 0;
  v9 = a2[16];
  sesid = v9;
  updated = CAutoSectionLock::LockWrite(
              (CAutoSectionLock *)v65,
              (unsigned int)a2,
              L"C:\\__w\\1\\s\\src\\Client\\Engine\\store\\dsqservice.cpp",
              0x460u);
  v53 = updated;
  if ( updated < 0 )
    goto LABEL_20;
  if ( this != (CServiceCache *)-40LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v57 = 1;
    LODWORD(lpCriticalSection[1]) = 1;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 5) )
  {
    while ( 1 )
    {
      v12 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v7);
      v13 = *(_QWORD *)v12 - *(_QWORD *)&v5->Data1;
      if ( *(_QWORD *)v12 == *(_QWORD *)&v5->Data1 )
        v13 = *(_QWORD *)(v12 + 8) - *(_QWORD *)v5->Data4;
      if ( !v13 )
        break;
      if ( ++v7 >= *((_DWORD *)this + 5) )
        goto LABEL_9;
    }
    if ( !*(_DWORD *)(v12 + 176) )
    {
      v72 = *(_OWORD *)a4;
      v73 = *((_OWORD *)a4 + 1);
      v74 = *((_OWORD *)a4 + 2);
      v75 = *((_OWORD *)a4 + 3);
      v76 = *((_OWORD *)a4 + 4);
      v77 = *((_OWORD *)a4 + 5);
      v78 = *((_OWORD *)a4 + 6);
      v79 = *((_OWORD *)a4 + 7);
      v24 = (__int128 *)((char *)a4 + 128);
      v80 = *v24;
      v81 = v24[1];
      v82 = v24[2];
      v83 = v24[3];
      v84 = v24[4];
      v85 = v24[5];
      v86 = v24[6];
      v25 = 0;
      if ( *(_BYTE *)(v12 + 283) == 1 )
        v25 = 2;
      DWORD2(v73) = v25;
      updated = CServiceCache::UpdateService(this, v60, 0x1Fu, v5, (const struct tagDSServicePropsAll *)&v72);
      v53 = updated;
      goto LABEL_20;
    }
  }
LABEL_9:
  updated = CSusEseSession::OpenTable(v60, "tbServiceData", &v62, v11, v45);
  v53 = updated;
  if ( updated < 0 )
    goto LABEL_20;
  updated = CSusEseTransaction::Begin((CSusEseTransaction *)v63, *(struct ISusEseSession **)&v61.Data1);
  v53 = updated;
  if ( updated < 0 )
    goto LABEL_20;
  v14 = *((_DWORD *)v60 + 34);
  updated = SetServiceProps(v9, 0, (__int64)a4);
  v53 = updated;
  LODWORD(v15) = 0;
  if ( updated < 0 )
  {
LABEL_19:
    v5 = a3;
    goto LABEL_20;
  }
  if ( v7 >= *((_DWORD *)this + 5) )
  {
    if ( v7 != *((_DWORD *)this + 5) )
      goto LABEL_64;
    *(_QWORD *)v55 = 0;
    *(_QWORD *)&v61.Data1 = 0;
    updated = CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::Grow(this, v7 + 1);
    v53 = updated;
    if ( updated < 0 )
      goto LABEL_19;
    v33 = (char *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
    v34 = v33;
    if ( v33 )
    {
      *(_QWORD *)(v33 + 172) = 0;
      *(_WORD *)(v33 + 283) = 0;
      v33[282] = 0;
      *(GUID *)v33 = GUID_NULL;
    }
    else
    {
      v34 = 0;
    }
    v16 = 8LL * v7;
    v17 = (_QWORD *)((char *)this + 8);
    *(_QWORD *)(v16 + *((_QWORD *)this + 1)) = v34;
    v35 = *(_QWORD *)(v16 + *((_QWORD *)this + 1));
    if ( !v35 )
    {
      updated = -2147024882;
      v53 = -2147024882;
      v8 = 0;
      goto LABEL_19;
    }
    StringCchCopyExA((char *)(v35 + 180), 0x2Fu, "tbPerSrvUpdate", (char **)&v61, (unsigned __int64 *)v55, v47);
    HexStringFromBlobA((const unsigned __int8 *)a3, v36, *(char **)&v61.Data1, v55[0]);
    *(_QWORD *)&v61.Data1 = 0;
    *(_QWORD *)v55 = 0;
    StringCchCopyExA(
      (char *)(*(_QWORD *)(v16 + *v17) + 227LL),
      0x37u,
      "tbPerSrvUserUpdateData",
      (char **)&v61,
      (unsigned __int64 *)v55,
      v48);
    HexStringFromBlobA((const unsigned __int8 *)a3, v37, *(char **)&v61.Data1, v55[0]);
    *(_BYTE *)(*(_QWORD *)(v16 + *v17) + 284LL) = (*((_DWORD *)a4 + 24) & 8) != 0;
    *(_BYTE *)(*(_QWORD *)(v16 + *v17) + 282LL) = (*((_DWORD *)a4 + 24) & 2) != 0;
    *(_DWORD *)(*(_QWORD *)(v16 + *v17) + 176LL) = 1;
    *(_QWORD *)(*(_QWORD *)(v16 + *v17) + 16LL) = *((_QWORD *)a4 + 9);
    *(struct _GUID *)*(_QWORD *)(v16 + *v17) = *a3;
    *(_DWORD *)(*(_QWORD *)(v16 + *v17) + 172LL) = 0;
    v38 = 24;
    v39 = 33;
    do
    {
      *(_DWORD *)(v38 + *(_QWORD *)(v16 + *v17)) = -1;
      v38 += 4;
      --v39;
    }
    while ( v39 );
    v40 = 156;
    v15 = 4;
    do
    {
      *(_DWORD *)(v40 + *(_QWORD *)(v16 + *v17)) = -1;
      v40 += 4;
      --v15;
    }
    while ( v15 );
    v32 = 1;
    v52 = 1;
    v30 = (_QWORD *)((char *)this + 8);
    v31 = 8LL * v7;
    goto LABEL_57;
  }
  v16 = 8LL * v7;
  v17 = (_QWORD *)((char *)this + 8);
  v18 = *(_QWORD *)(v16 + *((_QWORD *)this + 1));
  szTableName[0] = (JET_PCSTR)(v18 + 180);
  v69[0] = (JET_PCSTR)(v18 + 227);
  updated = DSValidateTableAndSetColumnids(
              sesid,
              v14,
              (const struct tagSusTableCreate *)szTableName,
              (unsigned int *)(v18 + 24));
  v53 = updated;
  if ( updated >= 0 )
  {
    v26 = v55[0];
  }
  else
  {
    if ( updated != -2145091580 )
    {
LABEL_18:
      v8 = v52;
      goto LABEL_19;
    }
    AsimovTelemetryEventFactory::Fire(134, -2145091580);
    v19 = JetDeleteTableA(sesid, v14, szTableName[0]);
    if ( v19 )
    {
      updated = JETErrToHRESULTAndAttemptRecovery(v19);
      v51 = v14;
      v50 = sesid;
      v20 = szTableName[0];
LABEL_17:
      v53 = updated;
      WUTrace(
        0,
        0,
        0x2000,
        1,
        0,
        L"0x%08x: JetDeleteTable failed for table %hs. sesid: %Ix. dbid: %lx",
        updated,
        v20,
        v50,
        v51);
      goto LABEL_18;
    }
    v26 = 1;
    v55[0] = 1;
  }
  v58 = v26;
  v27 = DSValidateTableAndSetColumnids(
          sesid,
          v14,
          (const struct tagSusTableCreate *)v69,
          (unsigned int *)(*(_QWORD *)(v16 + *v17) + 156LL));
  updated = v27;
  v53 = v27;
  LODWORD(v15) = 0;
  if ( v27 >= 0 )
  {
    v29 = v55[0];
  }
  else
  {
    if ( v27 != -2145091580 )
    {
      v8 = 0;
      goto LABEL_19;
    }
    AsimovTelemetryEventFactory::Fire(134, -2145091580);
    v28 = JetDeleteTableA(sesid, v14, v69[0]);
    LODWORD(v15) = 0;
    if ( v28 )
    {
      updated = JETErrToHRESULTAndAttemptRecovery(v28);
      v51 = v14;
      v50 = sesid;
      v20 = v69[0];
      goto LABEL_17;
    }
    v29 = 1;
    v59 = 1;
  }
  v30 = (_QWORD *)((char *)this + 8);
  v31 = 8LL * v7;
  v32 = 0;
  v52 = 0;
  if ( v29 )
  {
LABEL_57:
    v41 = *(_QWORD *)(v31 + *v30);
    szTableName[0] = (JET_PCSTR)(v41 + 180);
    v69[0] = (JET_PCSTR)(v41 + 227);
    if ( v58 != (_DWORD)v15 || v32 )
    {
      updated = DSCreateTable(sesid, v14, (const struct tagSusTableCreate *)szTableName, (unsigned int *)(v41 + 24));
      v53 = updated;
      LODWORD(v15) = 0;
      if ( updated < 0 )
        goto LABEL_18;
      v32 = v52;
    }
    if ( v59 != (_DWORD)v15 || v32 )
    {
      updated = DSCreateTable(
                  sesid,
                  v14,
                  (const struct tagSusTableCreate *)v69,
                  (unsigned int *)(*(_QWORD *)(v16 + *v17) + 156LL));
      v53 = updated;
      LODWORD(v15) = 0;
      if ( updated < 0 )
        goto LABEL_18;
    }
  }
LABEL_64:
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v7) + 176LL) = v15;
  if ( *((_DWORD *)a4 + 6) == 2
    && (*(_QWORD *)&c_idSrvNone.Data1 != *((_QWORD *)this + 10) || *(_QWORD *)c_idSrvNone.Data4 != *((_QWORD *)this + 11))
    && (*((_BYTE *)a4 + 96) & 1) == 0 )
  {
    v61 = (struct _GUID)*((_OWORD *)this + 5);
    updated = CServiceCache::UpdateServiceStateForAU(this, v60, v62, &v61, v46);
    v53 = updated;
    if ( updated < 0 )
      goto LABEL_18;
  }
  updated = CSusEseTransaction::Commit((CSusEseTransaction *)v63);
  v53 = updated;
  if ( updated < 0 )
    goto LABEL_18;
  v42 = *((_DWORD *)this + 5);
  if ( v7 == v42 )
    *((_DWORD *)this + 5) = v42 + 1;
  ++g_cServices;
  *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v7) + 283LL) = 0;
  if ( *((_DWORD *)a4 + 6) != 2
    || (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v7) + 283LL) = 1, (*((_BYTE *)a4 + 96) & 1) != 0) )
  {
    v5 = a3;
  }
  else
  {
    v43 = 0;
    if ( *((_DWORD *)this + 5) )
    {
      while ( 1 )
      {
        v44 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v43);
        if ( *(_QWORD *)v44 == *((_QWORD *)this + 10) && *(_QWORD *)(v44 + 8) == *((_QWORD *)this + 11) )
          break;
        if ( ++v43 >= *((_DWORD *)this + 5) )
          goto LABEL_80;
      }
      *(_BYTE *)(v44 + 283) = 0;
    }
LABEL_80:
    v5 = a3;
    *((struct _GUID *)this + 5) = *a3;
  }
  StringFromGUID2(v5, &sz, 39);
  v89 = 0;
  WUTrace(0, 0, 0x2000, 4, 0, L"Service %ls added", v88);
  StringFromGUID2((const GUID *const)this + 5, &sz, 39);
  WUTrace(0, 0, 0x2000, 5, 0, L"Default service for AU is %ls", &sz);
  v8 = v52;
LABEL_20:
  CSusEseSession::CloseTable(v60, v62);
  if ( updated < 0 )
  {
    if ( v8 )
    {
      StringFromGUID2(v5, &sz, 39);
      v89 = 0;
      LODWORD(v49) = updated;
      WUTrace(0, 0, 0x2000, 3, 0, L"Failed to add service %ls: 0x%08lX", v88, v49);
      if ( *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v7) )
      {
        if ( v7 < *((_DWORD *)this + 5) )
          CSusArrayList<tagDSServiceInfo *,CSusArrayListItemOpDelete<tagDSServiceInfo *>>::RemoveArraySection(
            this,
            v7,
            v7,
            1);
      }
    }
  }
  CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v63);
  if ( this != (CServiceCache *)-40LL )
  {
    v21 = v57;
    if ( v57 )
    {
      v22 = lpCriticalSection[0];
      do
      {
        LeaveCriticalSection(v22);
        --v21;
      }
      while ( v21 );
      updated = v53;
    }
  }
  CAutoSectionLock::~CAutoSectionLock((CAutoSectionLock *)v65);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801882f4  push    rbp
0x1801882f6  push    rbx
0x1801882f7  push    rsi
0x1801882f8  push    rdi
0x1801882f9  push    r12
0x1801882fb  push    r13
0x1801882fd  push    r14
0x1801882ff  push    r15
0x180188301  lea     rbp, [rsp-198h]
0x180188309  sub     rsp, 298h
0x180188310  mov     rax, cs:__security_cookie
0x180188317  xor     rax, rsp
0x18018831a  mov     [rbp+1D0h+var_50], rax
0x180188321  mov     r14, r9
0x180188324  mov     r13, r8
0x180188327  mov     [rsp+2D0h+rguid], r8
0x18018832c  mov     [rbp+1D0h+var_248], rdx
0x180188330  mov     rdi, rcx
0x180188333  xorps   xmm0, xmm0
0x180188336  xor     eax, eax
0x180188338  movups  [rbp+1D0h+var_208], xmm0
0x18018833c  mov     [rbp+1D0h+var_1F8], rax
0x180188340  lea     r8, [rdx+8]
0x180188344  mov     qword ptr [rbp+1D0h+var_240.Data1], r8
0x180188348  xor     r9d, r9d
0x18018834b  mov     dword ptr [rbp+1D0h+var_208], r9d
0x18018834f  mov     rax, rdx
0x180188352  neg     rax
0x180188355  sbb     rcx, rcx
0x180188358  and     rcx, r8
0x18018835b  mov     qword ptr [rbp+1D0h+var_208+8], rcx
0x18018835f  mov     dword ptr [rbp+1D0h+var_1F8], r9d
0x180188363  movups  xmmword ptr [rbp+1D0h+lpCriticalSection], xmm0
0x180188367  lea     rax, [rdi+28h]
0x18018836b  mov     [rbp+1D0h+lpCriticalSection], rax
0x18018836f  mov     [rsp+2D0h+var_258], r9d
0x180188374  mov     dword ptr [rbp+1D0h+lpCriticalSection+8], r9d
0x180188378  movups  [rbp+1D0h+var_228], xmm0
0x18018837c  lea     rax, ??_7CSusEseTransaction@@6B@; const CSusEseTransaction::`vftable'
0x180188383  mov     qword ptr [rbp+1D0h+var_228], rax
0x180188387  mov     qword ptr [rbp+1D0h+var_228+8], r9
0x18018838b  movups  xmm0, xmmword ptr cs:?g_tablePerSrvUpdate@@3UtagSusTableCreate@@A; tagSusTableCreate g_tablePerSrvUpdate
0x180188392  movups  xmmword ptr [rbp+1D0h+szTableName], xmm0
0x180188396  movups  xmm1, xmmword ptr cs:off_1802A2EF8
0x18018839d  movups  [rbp+1D0h+var_1E0], xmm1
0x1801883a1  movups  xmm0, xmmword ptr cs:off_1802A2F08
0x1801883a8  movups  [rbp+1D0h+var_1D0], xmm0
0x1801883ac  movups  xmm1, xmmword ptr cs:?g_tablePerSrvUserUpdateData@@3UtagSusTableCreate@@A; tagSusTableCreate g_tablePerSrvUserUpdateData
0x1801883b3  movups  xmmword ptr [rbp+1D0h+var_1C0], xmm1
0x1801883b7  movups  xmm0, xmmword ptr cs:off_1802A2EC8
0x1801883be  movups  [rbp+1D0h+var_1B0], xmm0
0x1801883c2  movups  xmm1, xmmword ptr cs:off_1802A2ED8
0x1801883c9  movups  [rbp+1D0h+var_1A0], xmm1
0x1801883cd  mov     [rbp+1D0h+var_230], 0FFFFFFFFFFFFFFFFh
0x1801883d5  mov     esi, r9d
0x1801883d8  mov     r12d, r9d
0x1801883db  mov     [rsp+2D0h+var_280], r9d
0x1801883e0  mov     [rsp+2D0h+var_268], r9d
0x1801883e5  mov     [rsp+2D0h+var_254], r9d
0x1801883ea  mov     [rbp+1D0h+var_250], r9d
0x1801883ee  mov     r15, [rdx+80h]
0x1801883f5  mov     [rsp+2D0h+sesid], r15
0x1801883fa  mov     r9d, 460h; unsigned int
0x180188400  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\sto"...
0x180188407  lea     rcx, [rbp+1D0h+var_208]; this
0x18018840b  call    ?LockWrite@CAutoSectionLock@@QEAAJKPEB_WK@Z; CAutoSectionLock::LockWrite(ulong,wchar_t const *,ulong)
0x180188410  mov     ebx, eax
0x180188412  mov     dword ptr [rsp+2D0h+var_278], eax
0x180188416  xor     r8d, r8d
0x180188419  test    eax, eax
0x18018841b  js      loc_1801885D1
0x180188421  lea     rax, [rdi+28h]
0x180188425  test    rax, rax
0x180188428  jz      short loc_180188442
0x18018842a  mov     rcx, rax; lpCriticalSection
0x18018842d  call    cs:__imp_EnterCriticalSection
0x180188433  mov     eax, 1
0x180188438  mov     [rsp+2D0h+var_258], eax
0x18018843c  mov     dword ptr [rbp+1D0h+lpCriticalSection+8], eax
0x18018843f  xor     r8d, r8d
0x180188442  mov     esi, r8d
0x180188445  cmp     [rdi+14h], r8d
0x180188449  jbe     short loc_180188476
0x18018844b  mov     rdx, [rdi+8]
0x18018844f  mov     eax, esi
0x180188451  mov     rcx, [rdx+rax*8]
0x180188455  mov     rax, [rcx]
0x180188458  sub     rax, [r13+0]
0x18018845c  jnz     short loc_180188466
0x18018845e  mov     rax, [rcx+8]
0x180188462  sub     rax, [r13+8]
0x180188466  test    rax, rax
0x180188469  jz      loc_1801886C5
0x18018846f  inc     esi
0x180188471  cmp     esi, [rdi+14h]
0x180188474  jb      short loc_18018844F
0x180188476  lea     r8, [rbp+1D0h+var_230]; unsigned __int64 *
0x18018847a  lea     rdx, ?c_szTbSvcData@@3QBDB; "tbServiceData"
0x180188481  mov     rcx, [rbp+1D0h+var_248]; this
0x180188485  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x18018848a  mov     ebx, eax
0x18018848c  mov     dword ptr [rsp+2D0h+var_278], eax
0x180188490  test    eax, eax
0x180188492  js      loc_1801885D1
0x180188498  mov     rdx, qword ptr [rbp+1D0h+var_240.Data1]; struct ISusEseSession *
0x18018849c  lea     rcx, [rbp+1D0h+var_228]; this
0x1801884a0  call    ?Begin@CSusEseTransaction@@QEAAJPEAUISusEseSession@@@Z; CSusEseTransaction::Begin(ISusEseSession *)
0x1801884a5  mov     ebx, eax
0x1801884a7  mov     dword ptr [rsp+2D0h+var_278], eax
0x1801884ab  test    eax, eax
0x1801884ad  js      loc_1801885D1
0x1801884b3  mov     rax, [rbp+1D0h+var_248]
0x1801884b7  mov     r13d, [rax+88h]
0x1801884be  mov     qword ptr [rsp+2D0h+var_2A8], r14; unsigned int
0x1801884c3  mov     dword ptr [rsp+2D0h+var_2B0], r12d; int
0x1801884c8  mov     r9, [rsp+2D0h+rguid]
0x1801884cd  mov     r8d, 1Fh
0x1801884d3  mov     rdx, [rbp+1D0h+var_230]
0x1801884d7  mov     rcx, r15; sesid
0x1801884da  call    SetServiceProps
0x1801884df  mov     ebx, eax
0x1801884e1  mov     dword ptr [rsp+2D0h+var_278], eax
0x1801884e5  xor     r8d, r8d
0x1801884e8  test    eax, eax
0x1801884ea  js      loc_1801885CC
0x1801884f0  cmp     esi, [rdi+14h]
0x1801884f3  jnb     loc_180188858
0x1801884f9  mov     eax, esi
0x1801884fb  lea     r12, ds:0[rax*8]
0x180188503  lea     r15, [rdi+8]
0x180188507  mov     rax, [r15]
0x18018850a  mov     r9, [r12+rax]
0x18018850e  lea     rax, [r9+0B4h]
0x180188515  mov     [rbp+1D0h+szTableName], rax
0x180188519  lea     rax, [r9+0E3h]
0x180188520  mov     [rbp+1D0h+var_1C0], rax
0x180188524  add     r9, 18h; unsigned int *
0x180188528  lea     r8, [rbp+1D0h+szTableName]; struct tagSusTableCreate *
0x18018852c  mov     edx, r13d; dbid
0x18018852f  mov     rcx, [rsp+2D0h+sesid]; sesid
0x180188534  call    ?DSValidateTableAndSetColumnids@@YAJ_KKPEBUtagSusTableCreate@@PEAK@Z; DSValidateTableAndSetColumnids(unsigned __int64,ulong,tagSusTableCreate const *,ulong *)
0x180188539  mov     ebx, eax
0x18018853b  mov     dword ptr [rsp+2D0h+var_278], eax
0x18018853f  mov     eax, 80248004h
0x180188544  test    ebx, ebx
0x180188546  jns     loc_1801887AB
0x18018854c  cmp     ebx, eax
0x18018854e  jnz     short loc_1801885C7
0x180188550  mov     edx, eax; int
0x180188552  mov     ecx, 86h; int
0x180188557  call    ?Fire@AsimovTelemetryEventFactory@@SAJJJ@Z; AsimovTelemetryEventFactory::Fire(long,long)
0x18018855c  mov     r8, [rbp+1D0h+szTableName]; szTableName
0x180188560  mov     edx, r13d; dbid
0x180188563  mov     rcx, [rsp+2D0h+sesid]; sesid
0x180188568  call    cs:__imp_JetDeleteTableA
0x18018856e  test    eax, eax
0x180188570  jz      loc_1801887A0
0x180188576  mov     ecx, eax; int
0x180188578  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18018857d  mov     ebx, eax
0x18018857f  mov     [rsp+2D0h+var_288], r13d
0x180188584  mov     rax, [rsp+2D0h+sesid]
0x180188589  mov     [rsp+2D0h+var_290], rax
0x18018858e  mov     rax, [rbp+1D0h+szTableName]
0x180188592  mov     dword ptr [rsp+2D0h+var_278], ebx
0x180188596  mov     [rsp+2D0h+var_298], rax
0x18018859b  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x18018859f  lea     rax, a0x08xJetdelete; "0x%08x: JetDeleteTable failed for table"...
0x1801885a6  mov     qword ptr [rsp+2D0h+var_2A8], rax
0x1801885ab  mov     [rsp+2D0h+var_2B0], 0
0x1801885b4  xor     edx, edx
0x1801885b6  xor     ecx, ecx
0x1801885b8  lea     r9d, [rdx+1]
0x1801885bc  mov     r8d, 2000h
0x1801885c2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801885c7  mov     r12d, [rsp+2D0h+var_280]
0x1801885cc  mov     r13, [rsp+2D0h+rguid]
0x1801885d1  mov     rdx, [rbp+1D0h+var_230]; unsigned __int64
0x1801885d5  mov     rcx, [rbp+1D0h+var_248]; this
0x1801885d9  call    ?CloseTable@CSusEseSession@@QEAAJ_K@Z; CSusEseSession::CloseTable(unsigned __int64)
0x1801885de  test    ebx, ebx
0x1801885e0  jns     loc_180188666
0x1801885e6  test    r12d, r12d
0x1801885e9  jz      short loc_180188666
0x1801885eb  mov     r8d, 27h ; '''; cchMax
0x1801885f1  lea     rdx, [rbp+1D0h+sz]; lpsz
0x1801885f8  mov     rcx, r13; rguid
0x1801885fb  call    cs:__imp_StringFromGUID2
0x180188601  xor     r12d, r12d
0x180188604  mov     [rbp+1D0h+var_56], r12w
0x18018860c  mov     dword ptr [rsp+2D0h+var_298], ebx
0x180188610  lea     rax, [rbp+1D0h+var_9E]
0x180188617  mov     [rsp+2D0h+var_2A0], rax
0x18018861c  lea     rax, aFailedToAddSer_0; "Failed to add service %ls: 0x%08lX"
0x180188623  mov     qword ptr [rsp+2D0h+var_2A8], rax
0x180188628  mov     [rsp+2D0h+var_2B0], r12
0x18018862d  xor     edx, edx
0x18018862f  xor     ecx, ecx
0x180188631  lea     r9d, [r12+3]
0x180188636  mov     r8d, 2000h
0x18018863c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180188641  mov     r8d, esi
0x180188644  mov     rax, [rdi+8]
0x180188648  cmp     [rax+r8*8], r12
0x18018864c  jz      short loc_180188666
0x18018864e  cmp     esi, [rdi+14h]
0x180188651  jnb     short loc_180188666
0x180188653  lea     r9d, [r12+1]
0x180188658  mov     r8d, esi
0x18018865b  mov     edx, esi
0x18018865d  mov     rcx, rdi
0x180188660  call    ?RemoveArraySection@?$CSusArrayList@PEAUtagDSServiceInfo@@V?$CSusArrayListItemOpDelete@PEAUtagDSServiceInfo@@@@@@IEAAXKKH@Z; CSusArrayList<tagDSServiceInfo *,CSusArrayListItemOpDelete<tagDSServiceInfo *>>::RemoveArraySection(ulong,ulong,int)
0x180188665  nop
0x180188666  lea     rcx, [rbp+1D0h+var_228]; this
0x18018866a  call    ??1CSusEseTransaction@@UEAA@XZ; CSusEseTransaction::~CSusEseTransaction(void)
0x18018866f  nop
0x180188670  lea     rax, [rdi+28h]
0x180188674  test    rax, rax
0x180188677  jz      short loc_180188697
0x180188679  mov     edi, [rsp+2D0h+var_258]
0x18018867d  test    edi, edi
0x18018867f  jz      short loc_180188697
0x180188681  mov     rbx, [rbp+1D0h+lpCriticalSection]
0x180188685  mov     rcx, rbx; lpCriticalSection
0x180188688  call    cs:__imp_LeaveCriticalSection
0x18018868e  add     edi, 0FFFFFFFFh
0x180188691  jnz     short loc_180188685
0x180188693  mov     ebx, dword ptr [rsp+2D0h+var_278]
0x180188697  lea     rcx, [rbp+1D0h+var_208]; this
0x18018869b  call    ??1CAutoSectionLock@@QEAA@XZ; CAutoSectionLock::~CAutoSectionLock(void)
0x1801886a0  mov     eax, ebx
0x1801886a2  mov     rcx, [rbp+1D0h+var_50]
0x1801886a9  xor     rcx, rsp; StackCookie
0x1801886ac  call    __security_check_cookie
0x1801886b1  add     rsp, 298h
0x1801886b8  pop     r15
0x1801886ba  pop     r14
0x1801886bc  pop     r13
0x1801886be  pop     r12
0x1801886c0  pop     rdi
0x1801886c1  pop     rsi
0x1801886c2  pop     rbx
0x1801886c3  pop     rbp
0x1801886c4  retn
0x1801886c5  cmp     [rcx+0B0h], r8d
0x1801886cc  jnz     loc_180188476
0x1801886d2  lea     rax, [rbp+1D0h+var_190]
0x1801886d6  movups  xmm0, xmmword ptr [r14]
0x1801886da  movups  xmmword ptr [rax], xmm0
0x1801886dd  movups  xmm1, xmmword ptr [r14+10h]
0x1801886e2  movups  xmmword ptr [rax+10h], xmm1
0x1801886e6  movups  xmm0, xmmword ptr [r14+20h]
0x1801886eb  movups  xmmword ptr [rax+20h], xmm0
0x1801886ef  movups  xmm1, xmmword ptr [r14+30h]
0x1801886f4  movups  xmmword ptr [rax+30h], xmm1
0x1801886f8  movups  xmm0, xmmword ptr [r14+40h]
0x1801886fd  movups  xmmword ptr [rax+40h], xmm0
0x180188701  movups  xmm1, xmmword ptr [r14+50h]
0x180188706  movups  xmmword ptr [rax+50h], xmm1
0x18018870a  movups  xmm0, xmmword ptr [r14+60h]
0x18018870f  movups  xmmword ptr [rax+60h], xmm0
0x180188713  mov     edx, 80h
0x180188718  add     rax, rdx
0x18018871b  movups  xmm0, xmmword ptr [r14+70h]
0x180188720  movups  xmmword ptr [rax-10h], xmm0
0x180188724  add     r14, rdx
0x180188727  movups  xmm1, xmmword ptr [r14]
0x18018872b  movups  xmmword ptr [rax], xmm1
0x18018872e  movups  xmm0, xmmword ptr [r14+10h]
0x180188733  movups  xmmword ptr [rax+10h], xmm0
0x180188737  movups  xmm1, xmmword ptr [r14+20h]
0x18018873c  movups  xmmword ptr [rax+20h], xmm1
0x180188740  movups  xmm0, xmmword ptr [r14+30h]
0x180188745  movups  xmmword ptr [rax+30h], xmm0
0x180188749  movups  xmm1, xmmword ptr [r14+40h]
0x18018874e  movups  xmmword ptr [rax+40h], xmm1
0x180188752  movups  xmm0, xmmword ptr [r14+50h]
0x180188757  movups  xmmword ptr [rax+50h], xmm0
0x18018875b  movups  xmm1, xmmword ptr [r14+60h]
0x180188760  movups  xmmword ptr [rax+60h], xmm1
0x180188764  mov     eax, r8d
0x180188767  lea     r15d, [rdx-7Eh]
0x18018876b  cmp     byte ptr [rcx+11Bh], 1
0x180188772  cmovz   eax, r15d
0x180188776  mov     [rbp+1D0h+var_178], eax
0x180188779  lea     rax, [rbp+1D0h+var_190]
0x18018877d  mov     [rsp+2D0h+var_2B0], rax; struct tagDSServicePropsAll *
0x180188782  mov     r9, r13; struct _GUID *
0x180188785  lea     r8d, [rdx-61h]; unsigned int
0x180188789  mov     rdx, [rbp+1D0h+var_248]; struct CSusEseSession *
0x18018878d  mov     rcx, rdi; this
0x180188790  call    ?UpdateService@CServiceCache@@QEAAJPEAVCSusEseSession@@KAEBU_GUID@@PEBUtagDSServicePropsAll@@@Z; CServiceCache::UpdateService(CSusEseSession *,ulong,_GUID const &,tagDSServicePropsAll const *)
0x180188795  mov     ebx, eax
0x180188797  mov     dword ptr [rsp+2D0h+var_278], eax
0x18018879b  jmp     loc_1801885D1
0x1801887a0  mov     eax, 1
0x1801887a5  mov     [rsp+2D0h+var_268], eax
0x1801887a9  jmp     short loc_1801887AF
0x1801887ab  mov     eax, [rsp+2D0h+var_268]
0x1801887af  mov     [rsp+2D0h+var_254], eax
  ... truncated ...
```
