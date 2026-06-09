# CServiceCache::RemoveService(CSusEseSession *,_GUID const &)

- ea: `0x1801893ec`
- end: `0x180189f75`
- name: `?RemoveService@CServiceCache@@QEAAJPEAVCSusEseSession@@AEBU_GUID@@@Z`
- size: `2953`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CSusEseSession *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018b340`

## callees

- `0x18005328c`
- `0x18012b618`
- `0x18018339c`
- `0x180183724`
- `0x1801844a0`
- `0x1801844ec`
- `0x18018457c`
- `0x180184634`
- `0x180184708`
- `0x1801853f0`
- `0x180188c88`
- `0x1801893ec`
- `0x18018c830`
- `0x18018fef8`
- `0x1801900ec`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180189590`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180189590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180189f32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180189f32`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801896d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18018974e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180189aa6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180189e46`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801896d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18018974e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180189aa6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180189e46`
- `ESENT!JetDeleteTableA` at `0x180189c94`
- `ESENT!JetDeleteTableA` at `0x180189d4b`
- `ESENT!JetDeleteTableA` at `0x180189c94`
- `ESENT!JetDeleteTableA` at `0x180189d4b`
- `ESENT!JetMove` at `0x180189bf5`
- `ESENT!JetMove` at `0x180189d0a`
- `ESENT!JetMove` at `0x180189bf5`
- `ESENT!JetMove` at `0x180189d0a`
- `ESENT!JetDelete` at `0x180189b06`
- `ESENT!JetDelete` at `0x180189bdb`
- `ESENT!JetDelete` at `0x180189c27`
- `ESENT!JetDelete` at `0x180189cf0`
- `ESENT!JetDelete` at `0x180189b06`
- `ESENT!JetDelete` at `0x180189bdb`
- `ESENT!JetDelete` at `0x180189c27`
- `ESENT!JetDelete` at `0x180189cf0`

## string_xrefs

- `0x180189c14`: `JetMove`
- `0x180189b34`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`
- `0x180189b23`: `JetDelete`
- `0x180189562`: `C:\__w\1\s\src\Client\Engine\store\dsqservice.cpp`
- `0x180189cda`: `0x%08x: JetDeleteTable failed for table %hs. sesid: %Ix. dbid: %lx`
- `0x1801894db`: `Cannot delete the Windows Update service`
- `0x180189ac1`: `Service %ls pending remove`
- `0x180189e61`: `Service %ls removed`
- `0x180189523`: `Invalid attempt to delete the policy driven service`
- `0x1801896eb`: `Attempted to delete service %ls which does not exist`
- `0x180189767`: `Attempted to delete service %ls which is pending delete`
- `0x1801895f0`: `tbServerConfig`
- `0x1801895a8`: `tbServiceData`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CServiceCache::RemoveService(
        struct _RTL_CRITICAL_SECTION *this,
        struct CSusEseSession *a2,
        const struct _GUID *a3)
{
  CSusEseSession *v3; // r13
  int v5; // edi
  JET_TABLEID v6; // r12
  JET_SESID v7; // rsi
  int updated; // ebx
  int v9; // r9d
  int v10; // r9d
  int v11; // eax
  int v12; // r9d
  int v13; // r9d
  unsigned int v14; // r13d
  unsigned int OwningThread_high; // edx
  __int64 v16; // rcx
  unsigned int v17; // eax
  const struct _GUID *v18; // rsi
  __int64 v19; // rcx
  int v20; // eax
  char *v21; // r12
  __int64 v22; // r9
  __int64 v23; // rbx
  JET_ERR v24; // eax
  JET_TABLEID v25; // rax
  const char *v26; // rax
  const wchar_t *v27; // rax
  int v28; // eax
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  JET_ERR v31; // eax
  int v32; // eax
  JET_ERR v33; // eax
  __int64 v34; // rcx
  JET_TABLEID v35; // rbx
  JET_ERR v36; // eax
  JET_ERR v37; // eax
  JET_ERR v38; // eax
  struct _RTL_CRITICAL_SECTION *v39; // rbx
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45[2]; // [rsp+30h] [rbp-D0h]
  int v46[2]; // [rsp+38h] [rbp-C8h]
  JET_SESID v47; // [rsp+40h] [rbp-C0h]
  JET_TABLEID v48; // [rsp+48h] [rbp-B8h]
  int v49; // [rsp+50h] [rbp-B0h]
  char v51; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+64h] [rbp-9Ch]
  int v53; // [rsp+68h] [rbp-98h]
  JET_TABLEID tableid; // [rsp+78h] [rbp-88h] BYREF
  JET_TABLEID v56; // [rsp+80h] [rbp-80h] BYREF
  JET_TABLEID v57; // [rsp+88h] [rbp-78h] BYREF
  char *v58; // [rsp+90h] [rbp-70h]
  const struct _GUID *v59; // [rsp+98h] [rbp-68h] BYREF
  int v60; // [rsp+A0h] [rbp-60h]
  _QWORD v61[2]; // [rsp+A8h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+B8h] [rbp-48h]
  _QWORD v63[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v64; // [rsp+E0h] [rbp-20h] BYREF
  JET_TABLEID v65; // [rsp+E8h] [rbp-18h] BYREF
  int v66; // [rsp+F0h] [rbp-10h] BYREF
  struct ISusEseSession *v67; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v68[76]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v70[72]; // [rsp+362h] [rbp+262h] BYREF
  __int16 v71; // [rsp+3AAh] [rbp+2AAh]

  v3 = a2;
  v58 = (char *)a2 + 8;
  v67 = (struct ISusEseSession *)(((unsigned __int64)a2 + 8) & -(__int64)(a2 != 0));
  v63[0] = 0;
  v63[1] = v67;
  v63[2] = 0;
  lpCriticalSection[0] = this + 1;
  v5 = 0;
  v52 = 0;
  lpCriticalSection[1] = 0;
  v61[0] = &CSusEseTransaction::`vftable';
  v61[1] = 0;
  v59 = a3;
  v60 = 16;
  tableid = -1;
  v6 = -1;
  v65 = -1;
  v57 = -1;
  v56 = -1;
  v53 = 0;
  v49 = 0;
  v66 = 0;
  v7 = *((_QWORD *)a2 + 16);
  if ( *(_OWORD *)a3 == *(_OWORD *)&c_idSrvWU )
  {
    updated = -2145091559;
    v64 = -2145091559;
    WUTrace(0, 0, 0x2000, 1, 0, L"Cannot delete the Windows Update service");
LABEL_97:
    v5 = v52;
    goto LABEL_98;
  }
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&c_idSrvPolicyDriven.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)c_idSrvPolicyDriven.Data4 )
  {
    updated = -2145091558;
    v64 = -2145091558;
    WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %ws", -2145091558, L"Invalid attempt to delete the policy driven service");
    goto LABEL_97;
  }
  updated = CAutoSectionLock::LockWrite(
              (CAutoSectionLock *)v63,
              (unsigned int)a2,
              L"C:\\__w\\1\\s\\src\\Client\\Engine\\store\\dsqservice.cpp",
              0x6E7u);
  v64 = updated;
  if ( updated >= 0 )
  {
    if ( this != (struct _RTL_CRITICAL_SECTION *)-40LL )
    {
      EnterCriticalSection(this + 1);
      v52 = 1;
      LODWORD(lpCriticalSection[1]) = 1;
    }
    LODWORD(this[2].OwningThread) = 1;
    updated = CSusEseSession::OpenTable(v3, "tbServiceData", &tableid, v9, v41);
    v64 = updated;
    v11 = 0;
    if ( updated < 0 )
    {
      v18 = a3;
      goto LABEL_28;
    }
    updated = CSusEseSession::OpenTable(v3, "tbScanTransInfo", &v65, v10, v42);
    v64 = updated;
    if ( updated < 0 )
      goto LABEL_92;
    updated = CSusEseSession::OpenTable(v3, "tbServerConfig", &v57, v12, v43);
    v64 = updated;
    if ( updated < 0 )
      goto LABEL_92;
    updated = CSusEseSession::OpenTable(v3, "tbServerCookies", &v56, v13, v44);
    v64 = updated;
    if ( updated < 0 )
      goto LABEL_92;
    updated = CSusEseTransaction::Begin((CSusEseTransaction *)v61, v67);
    v64 = updated;
    if ( updated < 0 )
      goto LABEL_92;
    v14 = 0;
    OwningThread_high = HIDWORD(this->OwningThread);
    if ( OwningThread_high )
    {
      while ( 1 )
      {
        v16 = *(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14);
        if ( *(_QWORD *)v16 == *(_QWORD *)&a3->Data1 && *(_QWORD *)(v16 + 8) == *(_QWORD *)a3->Data4 )
          break;
        if ( ++v14 >= OwningThread_high )
          goto LABEL_23;
      }
      if ( !*(_DWORD *)(v16 + 176) )
        goto LABEL_32;
      v49 = 1;
      v17 = HIDWORD(this->OwningThread);
      if ( *(int *)(v16 + 172) <= 0 )
        v17 = v14;
      v14 = v17;
    }
LABEL_23:
    if ( v14 == OwningThread_high )
    {
      v18 = a3;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl'::`2'::impl) )
      {
        StringFromGUID2(a3, &sz, 39);
        v71 = 0;
        WUTrace(0, 0, 0x2000, 3, 0, L"Attempted to delete service %ls which does not exist", v70);
        updated = -2145091542;
      }
      else
      {
        updated = -2145091564;
      }
      v64 = updated;
      v6 = v65;
      goto LABEL_27;
    }
LABEL_32:
    v67 = (struct ISusEseSession *)v14;
    v19 = *(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14);
    v51 = *(_BYTE *)(v19 + 283);
    if ( *(int *)(v19 + 172) > 0 )
      v66 = 1;
    v20 = DsqSeekToRow(v7, tableid, 0, (struct tagDsqSearchKey *)&v59, 1u, 0, 0, 0);
    updated = v20;
    v64 = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -2145091577 )
        goto LABEL_92;
      v53 = 1;
    }
    v21 = v58;
    updated = (*(__int64 (__fastcall **)(char *, const struct _GUID *))(*(_QWORD *)v58 + 424LL))(v58, a3);
    v64 = updated;
    if ( updated >= 0 )
    {
      updated = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v21 + 272LL))(v21);
      v64 = updated;
      if ( updated >= 0 )
      {
        v6 = v65;
        if ( v66 )
        {
          memset(v68, 0, 0x258u);
          LODWORD(v68[0]) = dword_1803385FC;
          v68[1] = &v66;
          LODWORD(v68[2]) = 4;
          HIDWORD(v68[3]) = 1;
          v22 = 1;
          if ( v53 )
          {
            LODWORD(v68[5]) = dword_1803385D0;
            v68[6] = a3;
            LODWORD(v68[7]) = 16;
            HIDWORD(v68[8]) = 1;
            LODWORD(v68[10]) = dword_1803385E0;
            v68[11] = &v65;
            LODWORD(v68[12]) = 4;
            HIDWORD(v68[13]) = 1;
            LODWORD(v68[15]) = dword_1803385E8;
            v68[16] = &v67;
            LODWORD(v68[17]) = 8;
            HIDWORD(v68[18]) = 1;
            LODWORD(v68[20]) = dword_1803385EC;
            v68[21] = &v67;
            LODWORD(v68[22]) = 8;
            HIDWORD(v68[23]) = 1;
            LODWORD(v68[25]) = dword_1803385F0;
            v68[26] = &v65;
            LODWORD(v68[27]) = 4;
            HIDWORD(v68[28]) = 1;
            LODWORD(v68[30]) = dword_1803385D4;
            v68[31] = &v64;
            LODWORD(v68[32]) = 2;
            HIDWORD(v68[33]) = 1;
            LODWORD(v68[35]) = dword_180338600;
            v68[36] = &v64;
            LODWORD(v68[37]) = 2;
            HIDWORD(v68[38]) = 1;
            LODWORD(v68[40]) = dword_1803385E4;
            v68[41] = &v64;
            LODWORD(v68[42]) = 2;
            HIDWORD(v68[43]) = 1;
            LODWORD(v68[45]) = dword_1803385F8;
            v68[46] = &v64;
            LODWORD(v68[47]) = 2;
            HIDWORD(v68[48]) = 1;
            LODWORD(v68[50]) = dword_1803385F4;
            v68[51] = &v64;
            LODWORD(v68[52]) = 2;
            HIDWORD(v68[53]) = 1;
            LODWORD(v68[55]) = dword_1803385DC;
            v68[56] = &v64;
            LODWORD(v68[57]) = 2;
            HIDWORD(v68[58]) = 1;
            LODWORD(v68[60]) = dword_1803385D8;
            v68[61] = &v64;
            LODWORD(v68[62]) = 2;
            HIDWORD(v68[63]) = 1;
            LODWORD(v68[65]) = dword_180338624;
            v68[66] = &v65;
            LODWORD(v68[67]) = 4;
            HIDWORD(v68[68]) = 1;
            LODWORD(v68[70]) = dword_180338628;
            v68[71] = &v65;
            LODWORD(v68[72]) = 4;
            HIDWORD(v68[73]) = 1;
            v22 = 15;
          }
          updated = DsqSetData(v7, tableid, v68, v22, 0, 0);
          v64 = updated;
          v18 = a3;
          if ( updated < 0 )
            goto LABEL_27;
          StringFromGUID2(a3, &sz, 39);
          v71 = 0;
          WUTrace(0, 0, 0x2000, 4, 0, L"Service %ls pending remove", v70);
          v23 = v14;
          goto LABEL_79;
        }
        LODWORD(v65) = *((_DWORD *)a2 + 34);
        if ( !v53 )
        {
          v24 = JetDelete(v7, tableid);
          if ( v24 )
          {
            updated = JETErrToHRESULTAndAttemptRecovery(v24);
            v25 = tableid;
            goto LABEL_47;
          }
        }
        v28 = DsqSeekToRow(v7, v6, 0, (struct tagDsqSearchKey *)&v59, 1u, 1, 1, 0);
        updated = v28;
        v64 = v28;
        if ( v28 >= 0 )
        {
          do
          {
            v29 = JetDelete(v7, v6);
            if ( v29 )
            {
              updated = JETErrToHRESULTAndAttemptRecovery(v29);
              v48 = v6;
              goto LABEL_48;
            }
            v30 = JetMove(v7, v6, 1, 0);
          }
          while ( !v30 );
          if ( v30 == -1603 )
            goto LABEL_54;
          updated = JETErrToHRESULTAndAttemptRecovery(v30);
          v48 = v6;
        }
        else
        {
          if ( v28 != -2145091577 )
            goto LABEL_51;
LABEL_54:
          updated = DsqSeekToRow(v7, v57, 0, (struct tagDsqSearchKey *)&v59, 1u, 0, 0, 0);
          v64 = updated;
          if ( updated >= 0 )
          {
            v31 = JetDelete(v7, v57);
            if ( v31 )
            {
              updated = JETErrToHRESULTAndAttemptRecovery(v31);
              v25 = v57;
LABEL_47:
              v48 = v25;
LABEL_48:
              v26 = "JetDelete";
              goto LABEL_49;
            }
          }
          else if ( updated != -2145091577 )
          {
            goto LABEL_51;
          }
          v32 = DsqSeekToRow(v7, v56, 0, (struct tagDsqSearchKey *)&v59, 1u, 1, 1, 0);
          updated = v32;
          v64 = v32;
          if ( v32 < 0 )
          {
            if ( v32 != -2145091577 )
              goto LABEL_51;
LABEL_66:
            v23 = v14;
            v33 = JetDeleteTableA(v7, v65, (JET_PCSTR)(*(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14) + 180LL));
            if ( !v33 || v33 == -1305 )
            {
              v38 = JetDeleteTableA(v7, v65, (JET_PCSTR)(*(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14) + 227LL));
              if ( !v38 || v38 == -1305 )
              {
                v18 = a3;
LABEL_79:
                if ( v51 )
                {
                  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&this->LockCount + 8 * v23) + 282LL) )
                  {
                    *(struct _GUID *)&this[2].DebugInfo = c_idSrvNone;
                    updated = CServiceCache::UpdateService(
                                (CServiceCache *)this,
                                a2,
                                1u,
                                &c_idSrvWU,
                                (const struct tagDSServicePropsAll *)&c_svcWU);
                    v64 = updated;
                    if ( updated < 0 )
                    {
                      *(struct _GUID *)&this[2].DebugInfo = *v18;
                      goto LABEL_27;
                    }
                  }
                }
                updated = CSusEseTransaction::Commit((CSusEseTransaction *)v61);
                v64 = updated;
                if ( updated < 0 )
                  goto LABEL_27;
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14) + 176LL) = v66;
                if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * v14) + 176LL) )
                {
                  if ( v14 < HIDWORD(this->OwningThread) )
                    CSusArrayList<tagDSServiceInfo *,CSusArrayListItemOpDelete<tagDSServiceInfo *>>::RemoveArraySection(
                      this,
                      v14,
                      v14,
                      1);
                  StringFromGUID2(v18, &sz, 39);
                  v71 = 0;
                  WUTrace(0, 0, 0x2000, 4, 0, L"Service %ls removed", v70);
                }
                v11 = v49;
                if ( !v49 )
                {
                  --g_cServices;
                  LODWORD(this[2].OwningThread) = 0;
LABEL_96:
                  v3 = a2;
                  goto LABEL_97;
                }
LABEL_28:
                LODWORD(this[2].OwningThread) = 0;
                if ( v11 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl'::`2'::impl) )
                  {
                    StringFromGUID2(v18, &sz, 39);
                    v71 = 0;
                    WUTrace(0, 0, 0x2000, 3, 0, L"Attempted to delete service %ls which is pending delete", v70);
                    updated = -2145091541;
                  }
                  else
                  {
                    updated = -2145091564;
                  }
                  v64 = updated;
                }
                goto LABEL_96;
              }
              updated = JETErrToHRESULTAndAttemptRecovery(v38);
              v34 = *(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * (_QWORD)v67) + 227LL;
            }
            else
            {
              updated = JETErrToHRESULTAndAttemptRecovery(v33);
              v34 = *(_QWORD *)(*(_QWORD *)&this->LockCount + 8LL * (_QWORD)v67) + 180LL;
            }
            LODWORD(v48) = v65;
            v47 = v7;
            *(_QWORD *)v46 = v34;
            v27 = L"0x%08x: JetDeleteTable failed for table %hs. sesid: %Ix. dbid: %lx";
            goto LABEL_50;
          }
          v35 = v56;
          do
          {
            v36 = JetDelete(v7, v35);
            if ( v36 )
            {
              updated = JETErrToHRESULTAndAttemptRecovery(v36);
              v25 = v56;
              goto LABEL_47;
            }
            v37 = JetMove(v7, v35, 1, 0);
          }
          while ( !v37 );
          if ( v37 == -1603 )
            goto LABEL_66;
          updated = JETErrToHRESULTAndAttemptRecovery(v37);
          v48 = v56;
        }
        v26 = "JetMove";
LABEL_49:
        v47 = v7;
        *(_QWORD *)v46 = v26;
        v27 = L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix";
LABEL_50:
        v64 = updated;
        v45[0] = updated;
        WUTrace(0, 0, 0x2000, 1, 0, v27, *(_QWORD *)v45, *(_QWORD *)v46, v47, v48);
LABEL_51:
        v18 = a3;
LABEL_27:
        v11 = v49;
        goto LABEL_28;
      }
    }
LABEL_92:
    v6 = v65;
    goto LABEL_51;
  }
LABEL_98:
  CSusEseSession::CloseTable(v3, v6);
  CSusEseSession::CloseTable(v3, tableid);
  CSusEseSession::CloseTable(v3, v57);
  CSusEseSession::CloseTable(v3, v56);
  CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)v61);
  if ( lpCriticalSection[0] && v5 )
  {
    v39 = lpCriticalSection[0];
    do
    {
      LeaveCriticalSection(v39);
      --v5;
    }
    while ( v5 );
    updated = v64;
  }
  CAutoSectionLock::~CAutoSectionLock((CAutoSectionLock *)v63);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801893ec  mov     [rsp-8+arg_18], rbx
0x1801893f1  push    rbp
0x1801893f2  push    rsi
0x1801893f3  push    rdi
0x1801893f4  push    r12
0x1801893f6  push    r13
0x1801893f8  push    r14
0x1801893fa  push    r15
0x1801893fc  lea     rbp, [rsp-2C0h]
0x180189404  sub     rsp, 3C0h
0x18018940b  mov     rax, cs:__security_cookie
0x180189412  xor     rax, rsp
0x180189415  mov     [rbp+2F0h+var_40], rax
0x18018941c  mov     [rsp+3F0h+rguid], r8
0x180189421  mov     r13, rdx
0x180189424  mov     [rsp+3F0h+var_380], rdx
0x180189429  mov     r14, rcx
0x18018942c  xorps   xmm0, xmm0
0x18018942f  xor     eax, eax
0x180189431  movups  [rbp+2F0h+var_328], xmm0
0x180189435  mov     [rbp+2F0h+var_318], rax
0x180189439  lea     rcx, [rdx+8]
0x18018943d  mov     [rbp+2F0h+var_360], rcx
0x180189441  mov     rax, rdx
0x180189444  neg     rax
0x180189447  sbb     rax, rax
0x18018944a  and     rax, rcx
0x18018944d  mov     [rbp+2F0h+var_2F8], rax
0x180189451  xor     ecx, ecx
0x180189453  mov     dword ptr [rbp+2F0h+var_328], ecx
0x180189456  mov     qword ptr [rbp+2F0h+var_328+8], rax
0x18018945a  mov     dword ptr [rbp+2F0h+var_318], ecx
0x18018945d  movups  xmmword ptr [rbp+2F0h+lpCriticalSection], xmm0
0x180189461  lea     rax, [r14+28h]
0x180189465  mov     [rbp+2F0h+lpCriticalSection], rax
0x180189469  mov     edi, ecx
0x18018946b  mov     [rsp+3F0h+var_38C], ecx
0x18018946f  mov     dword ptr [rbp+2F0h+lpCriticalSection+8], ecx
0x180189472  movups  [rbp+2F0h+var_348], xmm0
0x180189476  lea     rax, ??_7CSusEseTransaction@@6B@; const CSusEseTransaction::`vftable'
0x18018947d  mov     qword ptr [rbp+2F0h+var_348], rax
0x180189481  mov     qword ptr [rbp+2F0h+var_348+8], rcx
0x180189485  mov     [rbp+2F0h+var_358], r8
0x180189489  mov     [rbp+2F0h+var_350], 10h
0x180189490  or      rax, 0FFFFFFFFFFFFFFFFh
0x180189494  mov     [rsp+3F0h+tableid], rax
0x180189499  mov     r12, rax
0x18018949c  mov     [rbp+2F0h+var_308], rax
0x1801894a0  mov     [rbp+2F0h+var_368], rax
0x1801894a4  mov     [rbp+2F0h+var_370], rax
0x1801894a8  mov     [rsp+3F0h+var_388], ecx
0x1801894ac  mov     [rsp+3F0h+var_3A0], ecx
0x1801894b0  mov     [rbp+2F0h+var_300], ecx
0x1801894b3  mov     rsi, [rdx+80h]
0x1801894ba  mov     rax, [r8]
0x1801894bd  cmp     rax, qword ptr cs:c_idSrvWU.Data1
0x1801894c4  jnz     short loc_180189502
0x1801894c6  mov     rax, [r8+8]
0x1801894ca  cmp     rax, qword ptr cs:c_idSrvWU.Data4
0x1801894d1  jnz     short loc_180189502
0x1801894d3  mov     ebx, 80248019h
0x1801894d8  mov     [rbp+2F0h+var_310], ebx
0x1801894db  lea     rax, aCannotDeleteTh; "Cannot delete the Windows Update servic"...
0x1801894e2  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x1801894e7  mov     [rsp+3F0h+var_3D0], rcx
0x1801894ec  xor     edx, edx
0x1801894ee  lea     r9d, [rcx+1]
0x1801894f2  mov     r8d, 2000h
0x1801894f8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801894fd  jmp     loc_180189EE0
0x180189502  mov     rax, [r8]
0x180189505  cmp     rax, qword ptr cs:c_idSrvPolicyDriven.Data1
0x18018950c  jnz     short loc_18018955C
0x18018950e  mov     rax, [r8+8]
0x180189512  cmp     rax, qword ptr cs:c_idSrvPolicyDriven.Data4
0x180189519  jnz     short loc_18018955C
0x18018951b  mov     ebx, 8024801Ah
0x180189520  mov     [rbp+2F0h+var_310], ebx
0x180189523  lea     rax, aInvalidAttempt_2; "Invalid attempt to delete the policy dr"...
0x18018952a  mov     qword ptr [rsp+3F0h+var_3B8], rax
0x18018952f  mov     [rsp+3F0h+var_3C0], ebx
0x180189533  lea     rax, aDs0x08xWs; "DS: 0x%08x: %ws"
0x18018953a  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x18018953f  mov     [rsp+3F0h+var_3D0], rcx
0x180189544  xor     edx, edx
0x180189546  xor     ecx, ecx
0x180189548  lea     r9d, [rdx+1]
0x18018954c  mov     r8d, 2000h
0x180189552  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180189557  jmp     loc_180189EE0
0x18018955c  mov     r9d, 6E7h; unsigned int
0x180189562  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\sto"...
0x180189569  lea     rcx, [rbp+2F0h+var_328]; this
0x18018956d  call    ?LockWrite@CAutoSectionLock@@QEAAJKPEB_WK@Z; CAutoSectionLock::LockWrite(ulong,wchar_t const *,ulong)
0x180189572  mov     ebx, eax
0x180189574  mov     [rbp+2F0h+var_310], eax
0x180189577  test    eax, eax
0x180189579  js      loc_180189EE4
0x18018957f  mov     edi, 1
0x180189584  lea     rax, [r14+28h]
0x180189588  test    rax, rax
0x18018958b  jz      short loc_18018959F
0x18018958d  mov     rcx, rax; lpCriticalSection
0x180189590  call    cs:__imp_EnterCriticalSection
0x180189596  mov     eax, edi
0x180189598  mov     [rsp+3F0h+var_38C], eax
0x18018959c  mov     dword ptr [rbp+2F0h+lpCriticalSection+8], eax
0x18018959f  mov     [r14+60h], edi
0x1801895a3  lea     r8, [rsp+3F0h+tableid]; unsigned __int64 *
0x1801895a8  lea     rdx, ?c_szTbSvcData@@3QBDB; "tbServiceData"
0x1801895af  mov     rcx, r13; this
0x1801895b2  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x1801895b7  mov     ebx, eax
0x1801895b9  mov     [rbp+2F0h+var_310], eax
0x1801895bc  xor     eax, eax
0x1801895be  mov     r15d, 2000h
0x1801895c4  test    ebx, ebx
0x1801895c6  js      loc_180189EC9
0x1801895cc  lea     r8, [rbp+2F0h+var_308]; unsigned __int64 *
0x1801895d0  lea     rdx, ?c_szTbScanTransInfo@@3QBDB; "tbScanTransInfo"
0x1801895d7  mov     rcx, r13; this
0x1801895da  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x1801895df  mov     ebx, eax
0x1801895e1  mov     [rbp+2F0h+var_310], eax
0x1801895e4  test    eax, eax
0x1801895e6  js      loc_180189EC0
0x1801895ec  lea     r8, [rbp+2F0h+var_368]; unsigned __int64 *
0x1801895f0  lea     rdx, ?c_szTbSrvConfig@@3QBDB; "tbServerConfig"
0x1801895f7  mov     rcx, r13; this
0x1801895fa  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x1801895ff  mov     ebx, eax
0x180189601  mov     [rbp+2F0h+var_310], eax
0x180189604  test    eax, eax
0x180189606  js      loc_180189EC0
0x18018960c  lea     r8, [rbp+2F0h+var_370]; unsigned __int64 *
0x180189610  lea     rdx, ?c_szTbSrvCookies@@3QBDB; "tbServerCookies"
0x180189617  mov     rcx, r13; this
0x18018961a  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x18018961f  mov     ebx, eax
0x180189621  mov     [rbp+2F0h+var_310], eax
0x180189624  test    eax, eax
0x180189626  js      loc_180189EC0
0x18018962c  mov     rdx, [rbp+2F0h+var_2F8]; struct ISusEseSession *
0x180189630  lea     rcx, [rbp+2F0h+var_348]; this
0x180189634  call    ?Begin@CSusEseTransaction@@QEAAJPEAUISusEseSession@@@Z; CSusEseTransaction::Begin(ISusEseSession *)
0x180189639  mov     ebx, eax
0x18018963b  mov     [rbp+2F0h+var_310], eax
0x18018963e  test    eax, eax
0x180189640  js      loc_180189EC0
0x180189646  xor     ebx, ebx
0x180189648  mov     r13d, ebx
0x18018964b  mov     edx, [r14+14h]
0x18018964f  mov     r12, [rsp+3F0h+rguid]
0x180189654  test    edx, edx
0x180189656  jz      short loc_1801896A0
0x180189658  mov     r8, [r14+8]
0x18018965c  mov     eax, r13d
0x18018965f  mov     rcx, [r8+rax*8]
0x180189663  mov     rax, [rcx]
0x180189666  cmp     rax, [r12]
0x18018966a  jnz     short loc_180189677
0x18018966c  mov     rax, [rcx+8]
0x180189670  cmp     rax, [r12+8]
0x180189675  jz      short loc_180189681
0x180189677  add     r13d, edi
0x18018967a  cmp     r13d, edx
0x18018967d  jb      short loc_18018965C
0x18018967f  jmp     short loc_1801896A0
0x180189681  cmp     [rcx+0B0h], ebx
0x180189687  jz      loc_18018979C
0x18018968d  mov     [rsp+3F0h+var_3A0], edi
0x180189691  mov     eax, edx
0x180189693  cmp     [rcx+0ACh], ebx
0x180189699  cmovle  eax, r13d
0x18018969d  mov     r13d, eax
0x1801896a0  cmp     r13d, edx
0x1801896a3  jnz     loc_18018979C
0x1801896a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl(void)'::`2'::impl
0x1801896b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(void)
0x1801896b5  mov     rsi, [rsp+3F0h+rguid]
0x1801896ba  test    al, al
0x1801896bc  jz      loc_180189792
0x1801896c2  mov     r8d, 27h ; '''; cchMax
0x1801896c8  lea     rdx, [rbp+2F0h+sz]; lpsz
0x1801896cf  mov     rcx, rsi; rguid
0x1801896d2  call    cs:__imp_StringFromGUID2
0x1801896d8  mov     [rbp+2F0h+var_46], bx
0x1801896df  lea     rax, [rbp+2F0h+var_8E]
0x1801896e6  mov     qword ptr [rsp+3F0h+var_3C0], rax
0x1801896eb  lea     rax, aAttemptedToDel_0; "Attempted to delete service %ls which d"...
0x1801896f2  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x1801896f7  mov     [rsp+3F0h+var_3D0], rbx
0x1801896fc  mov     r9d, 3
0x180189702  mov     r8d, r15d
0x180189705  xor     edx, edx
0x180189707  xor     ecx, ecx
0x180189709  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18018970e  mov     ebx, 8024802Ah
0x180189713  mov     [rbp+2F0h+var_310], ebx
0x180189716  mov     r12, [rbp+2F0h+var_308]
0x18018971a  mov     eax, [rsp+3F0h+var_3A0]
0x18018971e  xor     edi, edi
0x180189720  mov     [r14+60h], edi
0x180189724  test    eax, eax
0x180189726  jz      loc_180189EDB
0x18018972c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl(void)'::`2'::impl
0x180189733  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(void)
0x180189738  test    al, al
0x18018973a  jz      loc_180189ED3
0x180189740  lea     r8d, [rdi+27h]; cchMax
0x180189744  lea     rdx, [rbp+2F0h+sz]; lpsz
0x18018974b  mov     rcx, rsi; rguid
0x18018974e  call    cs:__imp_StringFromGUID2
0x180189754  mov     [rbp+2F0h+var_46], di
0x18018975b  lea     rax, [rbp+2F0h+var_8E]
0x180189762  mov     qword ptr [rsp+3F0h+var_3C0], rax
0x180189767  lea     rax, aAttemptedToDel; "Attempted to delete service %ls which i"...
0x18018976e  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x180189773  mov     [rsp+3F0h+var_3D0], rdi
0x180189778  lea     r9d, [rdi+3]
0x18018977c  mov     r8d, r15d
0x18018977f  xor     edx, edx
0x180189781  xor     ecx, ecx
0x180189783  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180189788  mov     ebx, 8024802Bh
0x18018978d  jmp     loc_180189ED8
0x180189792  mov     ebx, 80248014h
0x180189797  jmp     loc_180189713
0x18018979c  mov     ecx, r13d
0x18018979f  mov     [rbp+2F0h+var_2F8], rcx
0x1801897a3  mov     rax, [r14+8]
0x1801897a7  mov     rcx, [rax+rcx*8]
0x1801897ab  mov     al, [rcx+11Bh]
0x1801897b1  mov     [rsp+3F0h+var_390], al
0x1801897b5  cmp     [rcx+0ACh], ebx
0x1801897bb  jle     short loc_1801897C0
0x1801897bd  mov     [rbp+2F0h+var_300], edi
0x1801897c0  mov     [rsp+3F0h+var_3B8], ebx; int
0x1801897c4  mov     [rsp+3F0h+var_3C0], ebx; int
0x1801897c8  mov     [rsp+3F0h+var_3C8], ebx; int
0x1801897cc  mov     dword ptr [rsp+3F0h+var_3D0], edi; unsigned int
0x1801897d0  lea     r9, [rbp+2F0h+var_358]; struct tagDsqSearchKey *
0x1801897d4  xor     r8d, r8d; char *
0x1801897d7  mov     rdx, [rsp+3F0h+tableid]; tableid
0x1801897dc  mov     rcx, rsi; sesid
0x1801897df  call    ?DsqSeekToRow@@YAJ_K0PEBDPEAUtagDsqSearchKey@@KHHH@Z; DsqSeekToRow(unsigned __int64,unsigned __int64,char const *,tagDsqSearchKey *,ulong,int,int,int)
0x1801897e4  mov     ebx, eax
0x1801897e6  mov     [rbp+2F0h+var_310], eax
0x1801897e9  test    eax, eax
0x1801897eb  jns     short loc_1801897FC
0x1801897ed  cmp     eax, 80248007h
0x1801897f2  jnz     loc_180189EC0
0x1801897f8  mov     [rsp+3F0h+var_388], edi
0x1801897fc  mov     rax, [rbp+2F0h+var_360]
0x180189800  mov     rax, [rax]
0x180189803  mov     rdx, r12
0x180189806  mov     r12, [rbp+2F0h+var_360]
0x18018980a  mov     rcx, r12
0x18018980d  mov     rax, [rax+1A8h]
0x180189814  call    _guard_dispatch_icall
0x180189819  mov     ebx, eax
0x18018981b  mov     [rbp+2F0h+var_310], eax
0x18018981e  test    eax, eax
0x180189820  js      loc_180189EC0
0x180189826  mov     rax, [r12]
0x18018982a  mov     rcx, r12
0x18018982d  mov     rax, [rax+110h]
0x180189834  call    _guard_dispatch_icall
0x180189839  mov     ebx, eax
0x18018983b  mov     [rbp+2F0h+var_310], eax
0x18018983e  test    eax, eax
0x180189840  js      loc_180189EC0
0x180189846  mov     r12, [rbp+2F0h+var_308]
0x18018984a  xor     ebx, ebx
0x18018984c  cmp     [rbp+2F0h+var_300], ebx
0x18018984f  jz      loc_180189AEA
0x180189855  xor     edx, edx; Val
0x180189857  mov     r8d, 258h; Size
0x18018985d  lea     rcx, [rbp+2F0h+var_2F0]; void *
0x180189861  call    memset
0x180189866  mov     eax, cs:dword_1803385FC
0x18018986c  mov     [rbp+2F0h+var_2F0], eax
0x18018986f  lea     rax, [rbp+2F0h+var_300]
0x180189873  mov     [rbp+2F0h+var_2E8], rax
0x180189877  lea     edx, [rbx+4]
0x18018987a  mov     [rbp+2F0h+var_2E0], edx
0x18018987d  mov     [rbp+2F0h+var_2D4], edi
0x180189880  mov     r9d, edi
0x180189883  cmp     [rsp+3F0h+var_388], ebx
0x180189887  jz      loc_180189A6B
0x18018988d  mov     eax, cs:dword_1803385D0
0x180189893  mov     [rbp+2F0h+var_2C8], eax
0x180189896  mov     rax, [rsp+3F0h+rguid]
0x18018989b  mov     [rbp+2F0h+var_2C0], rax
0x18018989f  mov     [rbp+2F0h+var_2B8], 10h
0x1801898a6  mov     [rbp+2F0h+var_2AC], edi
0x1801898a9  mov     eax, cs:dword_1803385E0
0x1801898af  mov     [rbp+2F0h+var_2A0], eax
0x1801898b2  lea     rax, [rbp+2F0h+var_308]
0x1801898b6  mov     [rbp+2F0h+var_298], rax
  ... truncated ...
```
