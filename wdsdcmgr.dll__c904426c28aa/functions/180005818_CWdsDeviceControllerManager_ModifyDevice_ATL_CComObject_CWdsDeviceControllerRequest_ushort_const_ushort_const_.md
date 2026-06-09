# CWdsDeviceControllerManager::ModifyDevice(ATL::CComObject<CWdsDeviceControllerRequest> *,ushort const *,ushort const *,IWdsDeviceControllerClient::DeviceModificationType,CWdsMetadata const *)

- ea: `0x180005818`
- end: `0x180006004`
- name: `?ModifyDevice@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBG1W4DeviceModificationType@IWdsDeviceControllerClient@@PEBVCWdsMetadata@@@Z`
- size: `2028`
- prototype: `__int64 __fastcall(CWdsDeviceControllerManager *this, CWdsDeviceControllerRequest *, unsigned __int16 *, unsigned __int16 *, int, struct CWdsMetadata *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x1800013d0`
- `0x180004f98`
- `0x180005818`
- `0x1800062f0`
- `0x1800068b8`
- `0x180007310`
- `0x18000a5e8`
- `0x18000b834`
- `0x18000e194`
- `0x18000e504`
- `0x18000e65c`
- `0x180013314`
- `0x1800133ec`
- `0x1800134f4`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `WDSSRV!WdsPerfCounterAdd` at `0x180005f8f`
- `WDSSRV!WdsPerfCounterAdd` at `0x180005f8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fa2`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fa2`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::ModifyDevice(
        CWdsDeviceControllerManager *this,
        CWdsDeviceControllerRequest *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        struct CWdsMetadata *a6)
{
  struct CWdsComMetadataBuilder *v10; // r15
  int ManagementEntry; // ebx
  const char *v12; // rdx
  int v13; // edi
  const char *v14; // rdx
  const char *v15; // rdx
  bool v16; // zf
  struct CWdsDeviceControllerManager::CManagementEntry *v17; // r13
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  const char *v23; // rdx
  CWdsDeviceControllerManager *v24; // rcx
  const char *v25; // rdx
  int Instance; // esi
  const char *v27; // rdx
  int v28; // esi
  CWdsDeviceControllerManager *v29; // rcx
  const char *v30; // rdx
  int v31; // eax
  const char *v32; // rdx
  unsigned int v33; // r9d
  struct CWdsDeviceControllerManager::CManagementEntry *v34; // r13
  const char *v35; // rdx
  const char *v36; // rdx
  const char *v37; // rdx
  const char *v38; // rdx
  const char *v39; // rdx
  const char *v40; // rdx
  const char *v41; // rdx
  CWdsDeviceControllerManager *v42; // rcx
  const char *v43; // rdx
  bool v44; // zf
  struct CWdsDeviceControllerManager::CManagementEntry *v45; // r13
  struct _RTL_CRITICAL_SECTION *v46; // rsi
  int v47; // edi
  const char *v48; // rdx
  CWdsDeviceControllerManager *v49; // rcx
  const char *v50; // rdx
  const char *v51; // rdx
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  CWdsComMetadataBuilder *v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-48h]
  __int64 v63; // [rsp+C8h] [rbp-38h]
  __int64 v64; // [rsp+D0h] [rbp-30h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h]
  CMRSWLock *v67; // [rsp+100h] [rbp+0h] BYREF
  int v68; // [rsp+108h] [rbp+8h]
  struct CWdsDeviceControllerManager::CManagementEntry *v69; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v70; // [rsp+168h] [rbp+68h]

  v70 = a4;
  v67 = (CWdsDeviceControllerManager *)((char *)this + 40);
  v68 = 0;
  CAutoReaderLock::Lock((CAutoReaderLock *)&v67);
  v54 = 0;
  v69 = 0;
  bstrString = 0;
  v10 = 0;
  ManagementEntry = CWdsDeviceControllerManager::GetManagementEntry(this, a3, &v69);
  if ( ElValidateWin32(
         ManagementEntry,
         v12,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0x952u) )
  {
    goto LABEL_67;
  }
  v13 = SysAllocStringHr(a4, &bstrString);
  if ( (int)ElValidateHr(v13, v14, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x955u) < 0 )
    goto LABEL_3;
  if ( a5 != 1 )
  {
    if ( a5 == 2 )
    {
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v34 = v69;
      v18 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v69 + 1) + 24LL);
      CMRSWLock::WriterLock(v18);
      LOWORD(v69) = 0;
      ManagementEntry = CWdsComMetadataBuilder::CreateInstance((struct CWdsMetadata *)&v61);
      if ( (int)ElValidateHr(
                  ManagementEntry,
                  v35,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x962u) >= 0 )
      {
        v10 = v54;
        ManagementEntry = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, CWdsComMetadataBuilder *, struct CWdsDeviceControllerManager::CManagementEntry **))(**(_QWORD **)v34 + 40LL))(
                            *(_QWORD *)v34,
                            a2,
                            bstrString,
                            v54,
                            &v69);
        CWdsDeviceControllerManager::LogDeviceManagement(
          0,
          7u,
          *(const unsigned __int16 **)(*((_QWORD *)v34 + 1) + 8LL),
          a4,
          v10,
          0,
          ManagementEntry);
        if ( (int)ElValidateHr(
                    ManagementEntry,
                    v36,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0x975u) >= 0 )
        {
          ManagementEntry = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
          if ( (int)ElValidateHr(
                      ManagementEntry,
                      v37,
                      "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                      0x978u) >= 0 )
          {
            if ( (_WORD)v69 != 0xFFFF )
            {
              ManagementEntry = 2;
              if ( ElValidateWin32(
                     2u,
                     v38,
                     "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                     0x97Du) )
              {
                goto LABEL_42;
              }
            }
            ManagementEntry = CWdsComMetadataBuilder::GetMetadata(v10, (struct CWdsMetadata *)&v55);
            if ( ElValidateWin32(
                   ManagementEntry,
                   v39,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x981u) )
            {
              goto LABEL_42;
            }
            ManagementEntry = CWdsMetadata::AppendAll((CWdsMetadata *)&v55, a6);
            if ( ElValidateWin32(
                   ManagementEntry,
                   v40,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x984u) )
            {
              goto LABEL_42;
            }
            Instance = CWdsComMetadata::CreateInstance((struct CWdsMetadata *)&v55);
            if ( (int)ElValidateHr(
                        Instance,
                        v41,
                        "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                        0x98Du) >= 0 )
            {
              v28 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, _QWORD))(**(_QWORD **)v34 + 48LL))(
                      *(_QWORD *)v34,
                      a2,
                      bstrString,
                      0);
              CWdsDeviceControllerManager::LogDeviceManagement(
                v42,
                6u,
                *(const unsigned __int16 **)(*((_QWORD *)v34 + 1) + 8LL),
                v70,
                0,
                0,
                v28);
              if ( (int)ElValidateHr(
                          v28,
                          v43,
                          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                          0x998u) >= 0 )
              {
                v31 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
                v33 = 2459;
                goto LABEL_49;
              }
LABEL_44:
              if ( v28 < 0 )
              {
                v44 = (v28 & 0x1FFF0000) == 458752;
                goto LABEL_46;
              }
LABEL_47:
              ManagementEntry = v28;
LABEL_42:
              CMRSWLock::WriterRelease((CMRSWLock *)v18);
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v55);
              CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v61);
              goto LABEL_63;
            }
LABEL_39:
            if ( Instance >= 0 || (ManagementEntry = (unsigned __int16)Instance, (Instance & 0x1FFF0000) != 0x70000) )
              ManagementEntry = Instance;
            goto LABEL_42;
          }
        }
LABEL_29:
        if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
          ManagementEntry = (unsigned __int16)ManagementEntry;
        goto LABEL_42;
      }
    }
    else
    {
      if ( a5 != 3 )
      {
        ManagementEntry = 87;
        if ( ElValidateWin32(
               0x57u,
               v15,
               "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
               0xA01u) )
        {
          goto LABEL_63;
        }
        goto LABEL_62;
      }
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v17 = v69;
      v18 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v69 + 1) + 24LL);
      CMRSWLock::WriterLock(v18);
      LOWORD(v69) = 0;
      ManagementEntry = CWdsComMetadataBuilder::CreateInstance((struct CWdsMetadata *)&v61);
      if ( (int)ElValidateHr(
                  ManagementEntry,
                  v19,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x9A8u) >= 0 )
      {
        v10 = v54;
        ManagementEntry = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, CWdsComMetadataBuilder *, struct CWdsDeviceControllerManager::CManagementEntry **))(**(_QWORD **)v17 + 40LL))(
                            *(_QWORD *)v17,
                            a2,
                            bstrString,
                            v54,
                            &v69);
        CWdsDeviceControllerManager::LogDeviceManagement(
          0,
          7u,
          *(const unsigned __int16 **)(*((_QWORD *)v17 + 1) + 8LL),
          a4,
          v10,
          0,
          ManagementEntry);
        if ( (int)ElValidateHr(
                    ManagementEntry,
                    v20,
                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                    0x9BBu) >= 0 )
        {
          ManagementEntry = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
          if ( (int)ElValidateHr(
                      ManagementEntry,
                      v21,
                      "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                      0x9BEu) >= 0 )
          {
            if ( (_WORD)v69 != 0xFFFF )
            {
              ManagementEntry = 2;
              if ( ElValidateWin32(
                     2u,
                     v22,
                     "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                     0x9C3u) )
              {
                goto LABEL_42;
              }
            }
            ManagementEntry = CWdsComMetadataBuilder::GetMetadata(v10, (struct CWdsMetadata *)&v55);
            if ( ElValidateWin32(
                   ManagementEntry,
                   v23,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x9C7u) )
            {
              goto LABEL_42;
            }
            ManagementEntry = CWdsDeviceControllerManager::ModifyMetadata(v24, (struct CWdsMetadata *)&v55, a6);
            if ( ElValidateWin32(
                   ManagementEntry,
                   v25,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x9CAu) )
            {
              goto LABEL_42;
            }
            Instance = CWdsComMetadata::CreateInstance((struct CWdsMetadata *)&v55);
            if ( (int)ElValidateHr(
                        Instance,
                        v27,
                        "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                        0x9D2u) >= 0 )
            {
              v28 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, _QWORD))(**(_QWORD **)v17 + 48LL))(
                      *(_QWORD *)v17,
                      a2,
                      bstrString,
                      0);
              CWdsDeviceControllerManager::LogDeviceManagement(
                v29,
                6u,
                *(const unsigned __int16 **)(*((_QWORD *)v17 + 1) + 8LL),
                v70,
                0,
                0,
                v28);
              if ( (int)ElValidateHr(
                          v28,
                          v30,
                          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                          0x9DDu) >= 0 )
              {
                v31 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
                v33 = 2528;
LABEL_49:
                v28 = v31;
                if ( (int)ElValidateHr(
                            v31,
                            v32,
                            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                            v33) < 0 )
                {
                  if ( v28 < 0 )
                  {
                    v44 = (v28 & 0x1FFF0000) == 458752;
LABEL_46:
                    ManagementEntry = (unsigned __int16)v28;
                    if ( v44 )
                      goto LABEL_42;
                    goto LABEL_47;
                  }
                  goto LABEL_47;
                }
                CMRSWLock::WriterRelease((CMRSWLock *)v18);
                CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v55);
                CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v61);
LABEL_62:
                WdsPerfCounterAdd(58);
                goto LABEL_63;
              }
              goto LABEL_44;
            }
            goto LABEL_39;
          }
        }
        goto LABEL_29;
      }
    }
    if ( ManagementEntry < 0 && (ManagementEntry & 0x1FFF0000) == 0x70000 )
      ManagementEntry = (unsigned __int16)ManagementEntry;
    CMRSWLock::WriterRelease((CMRSWLock *)v18);
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v55);
    CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v61);
    v10 = v54;
    goto LABEL_63;
  }
  v45 = v69;
  v46 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v69 + 1) + 24LL);
  CMRSWLock::WriterLock(v46);
  v47 = CWdsComMetadata::CreateInstance(a6);
  if ( (int)ElValidateHr(v47, v48, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x9EAu) < 0 )
  {
    if ( v47 >= 0 || (ManagementEntry = (unsigned __int16)v47, (v47 & 0x1FFF0000) != 0x70000) )
      ManagementEntry = v47;
    CMRSWLock::WriterRelease((CMRSWLock *)v46);
    goto LABEL_63;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, BSTR, _QWORD))(**(_QWORD **)v45 + 48LL))(
          *(_QWORD *)v45,
          a2,
          bstrString,
          0);
  CMRSWLock::WriterRelease((CMRSWLock *)v46);
  CWdsDeviceControllerManager::LogDeviceManagement(
    v49,
    6u,
    *(const unsigned __int16 **)(*((_QWORD *)v45 + 1) + 8LL),
    v70,
    0,
    0,
    v13);
  if ( (int)ElValidateHr(v13, v50, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x9F7u) < 0 )
  {
    if ( v13 >= 0 )
      goto LABEL_7;
    v16 = (v13 & 0x1FFF0000) == 458752;
    goto LABEL_5;
  }
  v13 = CWdsDeviceControllerRequest::CleanupImpersonation(a2);
  if ( (int)ElValidateHr(v13, v51, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x9FAu) >= 0 )
    goto LABEL_62;
LABEL_3:
  if ( v13 >= 0 )
  {
LABEL_7:
    ManagementEntry = v13;
    goto LABEL_63;
  }
  v16 = (v13 & 0x1FFF0000) == 458752;
LABEL_5:
  if ( !v16 )
    goto LABEL_7;
  ManagementEntry = (unsigned __int16)v13;
LABEL_63:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v10 )
    (*(void (__fastcall **)(struct CWdsComMetadataBuilder *))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_67:
  if ( v68 == 1 )
    CMRSWLock::ReaderRelease(v67);
  return (unsigned int)ManagementEntry;
}

```

## disassembly

```asm
0x180005818  mov     [rsp-8+arg_8], rbx
0x18000581d  mov     [rsp-8+arg_18], r9
0x180005822  push    rbp
0x180005823  push    rsi
0x180005824  push    rdi
0x180005825  push    r12
0x180005827  push    r13
0x180005829  push    r14
0x18000582b  push    r15
0x18000582d  lea     rbp, [rsp-10h]
0x180005832  sub     rsp, 110h
0x180005839  lea     rax, [rcx+28h]
0x18000583d  mov     rbx, rcx
0x180005840  xor     r13d, r13d
0x180005843  mov     [rbp+40h+var_40], rax
0x180005847  lea     rcx, [rbp+40h+var_40]; this
0x18000584b  mov     [rbp+40h+var_38], r13d
0x18000584f  mov     rsi, r9
0x180005852  mov     rdi, r8
0x180005855  mov     r12, rdx
0x180005858  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x18000585d  lea     r8, [rbp+40h+arg_0]; struct CWdsDeviceControllerManager::CManagementEntry **
0x180005861  mov     [rsp+140h+var_100], r13
0x180005866  mov     rdx, rdi; unsigned __int16 *
0x180005869  mov     [rsp+140h+var_F0], r13
0x18000586e  mov     rcx, rbx; this
0x180005871  mov     [rbp+40h+arg_0], r13
0x180005875  mov     r14d, r13d
0x180005878  mov     [rsp+140h+bstrString], r13
0x18000587d  mov     r15d, r13d
0x180005880  call    ?GetManagementEntry@CWdsDeviceControllerManager@@AEAAKPEBGPEAPEAUCManagementEntry@1@@Z; CWdsDeviceControllerManager::GetManagementEntry(ushort const *,CWdsDeviceControllerManager::CManagementEntry * *)
0x180005885  mov     r9d, 952h; unsigned int
0x18000588b  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005892  mov     ecx, eax; unsigned int
0x180005894  mov     ebx, eax
0x180005896  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000589b  test    eax, eax
0x18000589d  jnz     loc_180005FD2
0x1800058a3  lea     rdx, [rsp+140h+bstrString]; unsigned __int16 **
0x1800058a8  mov     rcx, rsi; unsigned __int16 *
0x1800058ab  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800058b0  mov     r9d, 955h; unsigned int
0x1800058b6  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800058bd  mov     ecx, eax; int
0x1800058bf  mov     edi, eax
0x1800058c1  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800058c6  test    eax, eax
0x1800058c8  jns     short loc_1800058ED
0x1800058ca  test    edi, edi
0x1800058cc  jns     short loc_1800058E6
0x1800058ce  mov     ecx, edi
0x1800058d0  and     ecx, 1FFF0000h
0x1800058d6  cmp     ecx, 70000h
0x1800058dc  jnz     short loc_1800058E6
0x1800058de  movzx   ebx, di
0x1800058e1  jmp     loc_180005F95
0x1800058e6  mov     ebx, edi
0x1800058e8  jmp     loc_180005F95
0x1800058ed  mov     ecx, [rbp+40h+arg_20]
0x1800058f0  sub     ecx, 1
0x1800058f3  jz      loc_180005E7D
0x1800058f9  sub     ecx, 1
0x1800058fc  jz      loc_180005B59
0x180005902  cmp     ecx, 1
0x180005905  jz      short loc_18000592D
0x180005907  mov     ebx, 57h ; 'W'
0x18000590c  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005913  mov     ecx, ebx; unsigned int
0x180005915  mov     r9d, 0A01h; unsigned int
0x18000591b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005920  test    eax, eax
0x180005922  jz      loc_180005F87
0x180005928  jmp     loc_180005F95
0x18000592d  mov     [rbp+40h+var_90], r13
0x180005931  mov     [rbp+40h+var_88], r13
0x180005935  mov     [rbp+40h+var_78], r13
0x180005939  mov     [rbp+40h+var_70], r13
0x18000593d  mov     [rbp+40h+var_60], r13
0x180005941  mov     [rbp+40h+var_58], r13
0x180005945  mov     [rsp+140h+var_E0], r13
0x18000594a  mov     [rsp+140h+var_D8], r13
0x18000594f  mov     [rsp+140h+var_C8], r13
0x180005954  mov     [rbp+40h+var_C0], r13
0x180005958  mov     [rbp+40h+var_B0], r13
0x18000595c  mov     [rbp+40h+var_A8], r13
0x180005960  mov     r13, [rbp+40h+arg_0]
0x180005964  mov     rdi, [r13+8]
0x180005968  add     rdi, 18h
0x18000596c  mov     rcx, rdi; lpCriticalSection
0x18000596f  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x180005974  lea     rdx, [rsp+140h+var_F0]
0x180005979  mov     word ptr [rbp+40h+arg_0], r15w
0x18000597e  lea     rcx, [rbp+40h+var_90]; struct CWdsMetadata *
0x180005982  call    ?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z; CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)
0x180005987  mov     r9d, 9A8h; unsigned int
0x18000598d  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005994  mov     ecx, eax; int
0x180005996  mov     ebx, eax
0x180005998  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000599d  test    eax, eax
0x18000599f  js      loc_180005BCD
0x1800059a5  mov     rcx, [r13+0]
0x1800059a9  lea     rdx, [rbp+40h+arg_0]
0x1800059ad  mov     r15, [rsp+140h+var_F0]
0x1800059b2  mov     r8, [rsp+140h+bstrString]
0x1800059b7  mov     r9, r15
0x1800059ba  mov     [rsp+140h+var_120], rdx
0x1800059bf  mov     rdx, r12
0x1800059c2  mov     rax, [rcx]
0x1800059c5  mov     rax, [rax+28h]
0x1800059c9  call    cs:__guard_dispatch_icall_fptr
0x1800059cf  mov     r8, [r13+8]
0x1800059d3  xor     ecx, ecx; this
0x1800059d5  mov     [rsp+140h+var_110], eax; int
0x1800059d9  mov     r9, rsi; unsigned __int16 *
0x1800059dc  mov     [rsp+140h+var_118], ecx; unsigned int
0x1800059e0  mov     ebx, eax
0x1800059e2  mov     [rsp+140h+var_120], r15; struct CWdsComMetadataBuilder *
0x1800059e7  mov     r8, [r8+8]; unsigned __int16 *
0x1800059eb  lea     edx, [rcx+7]; unsigned int
0x1800059ee  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x1800059f3  mov     r9d, 9BBh; unsigned int
0x1800059f9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005a00  mov     ecx, ebx; int
0x180005a02  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005a07  test    eax, eax
0x180005a09  js      loc_180005C6D
0x180005a0f  mov     rcx, r12; this
0x180005a12  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180005a17  mov     r9d, 9BEh; unsigned int
0x180005a1d  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005a24  mov     ecx, eax; int
0x180005a26  mov     ebx, eax
0x180005a28  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005a2d  test    eax, eax
0x180005a2f  js      loc_180005C6D
0x180005a35  cmp     word ptr [rbp+40h+arg_0], 0FFFFh
0x180005a3a  jz      short loc_180005A5D
0x180005a3c  mov     ecx, 2; unsigned int
0x180005a41  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005a48  mov     r9d, 9C3h; unsigned int
0x180005a4e  mov     ebx, ecx
0x180005a50  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005a55  test    eax, eax
0x180005a57  jnz     loc_180005C82
0x180005a5d  lea     rdx, [rsp+140h+var_E0]; struct CWdsMetadata *
0x180005a62  mov     rcx, r15; this
0x180005a65  call    ?GetMetadata@CWdsComMetadataBuilder@@QEAAKPEAVCWdsMetadata@@@Z; CWdsComMetadataBuilder::GetMetadata(CWdsMetadata *)
0x180005a6a  mov     r9d, 9C7h; unsigned int
0x180005a70  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005a77  mov     ecx, eax; unsigned int
0x180005a79  mov     ebx, eax
0x180005a7b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005a80  test    eax, eax
0x180005a82  jnz     loc_180005C82
0x180005a88  mov     r8, [rbp+40h+arg_28]; struct CWdsMetadata *
0x180005a8c  lea     rdx, [rsp+140h+var_E0]; struct CWdsMetadata *
0x180005a91  call    ?ModifyMetadata@CWdsDeviceControllerManager@@AEAAKPEAVCWdsMetadata@@PEBV2@@Z; CWdsDeviceControllerManager::ModifyMetadata(CWdsMetadata *,CWdsMetadata const *)
0x180005a96  mov     r9d, 9CAh; unsigned int
0x180005a9c  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005aa3  mov     ecx, eax; unsigned int
0x180005aa5  mov     ebx, eax
0x180005aa7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005aac  test    eax, eax
0x180005aae  jnz     loc_180005C82
0x180005ab4  lea     rdx, [rsp+140h+var_100]
0x180005ab9  lea     rcx, [rsp+140h+var_E0]; struct CWdsMetadata *
0x180005abe  call    ?CreateInstance@CWdsComMetadata@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadata@@@ATL@@@Z; CWdsComMetadata::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadata> * *)
0x180005ac3  mov     r9d, 9D2h; unsigned int
0x180005ac9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005ad0  mov     ecx, eax; int
0x180005ad2  mov     esi, eax
0x180005ad4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005ad9  test    eax, eax
0x180005adb  js      loc_180005D68
0x180005ae1  mov     rcx, [r13+0]
0x180005ae5  mov     rdx, r12
0x180005ae8  mov     r14, [rsp+140h+var_100]
0x180005aed  mov     r8, [rsp+140h+bstrString]
0x180005af2  mov     r9, r14
0x180005af5  mov     rax, [rcx]
0x180005af8  mov     rax, [rax+30h]
0x180005afc  call    cs:__guard_dispatch_icall_fptr
0x180005b02  mov     r8, [r13+8]
0x180005b06  xor     r13d, r13d
0x180005b09  mov     r9, [rbp+40h+arg_18]; unsigned __int16 *
0x180005b0d  mov     esi, eax
0x180005b0f  mov     [rsp+140h+var_110], eax; int
0x180005b13  mov     [rsp+140h+var_118], r13d; unsigned int
0x180005b18  mov     r8, [r8+8]; unsigned __int16 *
0x180005b1c  lea     edx, [r13+6]; unsigned int
0x180005b20  mov     [rsp+140h+var_120], r14; struct CWdsComMetadataBuilder *
0x180005b25  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x180005b2a  mov     r9d, 9DDh; unsigned int
0x180005b30  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005b37  mov     ecx, esi; int
0x180005b39  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005b3e  test    eax, eax
0x180005b40  js      loc_180005E07
0x180005b46  mov     rcx, r12; this
0x180005b49  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180005b4e  mov     r9d, 9E0h
0x180005b54  jmp     loc_180005E35
0x180005b59  mov     [rbp+40h+var_90], r13
0x180005b5d  mov     [rbp+40h+var_88], r13
0x180005b61  mov     [rbp+40h+var_78], r13
0x180005b65  mov     [rbp+40h+var_70], r13
0x180005b69  mov     [rbp+40h+var_60], r13
0x180005b6d  mov     [rbp+40h+var_58], r13
0x180005b71  mov     [rsp+140h+var_E0], r13
0x180005b76  mov     [rsp+140h+var_D8], r13
0x180005b7b  mov     [rsp+140h+var_C8], r13
0x180005b80  mov     [rbp+40h+var_C0], r13
0x180005b84  mov     [rbp+40h+var_B0], r13
0x180005b88  mov     [rbp+40h+var_A8], r13
0x180005b8c  mov     r13, [rbp+40h+arg_0]
0x180005b90  mov     rdi, [r13+8]
0x180005b94  add     rdi, 18h
0x180005b98  mov     rcx, rdi; lpCriticalSection
0x180005b9b  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x180005ba0  lea     rdx, [rsp+140h+var_F0]
0x180005ba5  mov     word ptr [rbp+40h+arg_0], r15w
0x180005baa  lea     rcx, [rbp+40h+var_90]; struct CWdsMetadata *
0x180005bae  call    ?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z; CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)
0x180005bb3  mov     r9d, 962h; unsigned int
0x180005bb9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005bc0  mov     ecx, eax; int
0x180005bc2  mov     ebx, eax
0x180005bc4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005bc9  test    eax, eax
0x180005bcb  jns     short loc_180005C07
0x180005bcd  test    ebx, ebx
0x180005bcf  jns     short loc_180005BE2
0x180005bd1  mov     eax, ebx
0x180005bd3  and     eax, 1FFF0000h
0x180005bd8  cmp     eax, 70000h
0x180005bdd  jnz     short loc_180005BE2
0x180005bdf  movzx   ebx, bx
0x180005be2  mov     rcx, rdi; this
0x180005be5  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005bea  lea     rcx, [rsp+140h+var_E0]; this
0x180005bef  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005bf4  lea     rcx, [rbp+40h+var_90]; this
0x180005bf8  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005bfd  mov     r15, [rsp+140h+var_F0]
0x180005c02  jmp     loc_180005F95
0x180005c07  mov     rcx, [r13+0]
0x180005c0b  lea     rdx, [rbp+40h+arg_0]
0x180005c0f  mov     r15, [rsp+140h+var_F0]
0x180005c14  mov     r8, [rsp+140h+bstrString]
0x180005c19  mov     r9, r15
0x180005c1c  mov     [rsp+140h+var_120], rdx
0x180005c21  mov     rdx, r12
0x180005c24  mov     rax, [rcx]
0x180005c27  mov     rax, [rax+28h]
0x180005c2b  call    cs:__guard_dispatch_icall_fptr
0x180005c31  mov     r8, [r13+8]
0x180005c35  xor     ecx, ecx; this
0x180005c37  mov     [rsp+140h+var_110], eax; int
0x180005c3b  mov     r9, rsi; unsigned __int16 *
0x180005c3e  mov     [rsp+140h+var_118], ecx; unsigned int
0x180005c42  mov     ebx, eax
0x180005c44  mov     [rsp+140h+var_120], r15; struct CWdsComMetadataBuilder *
0x180005c49  mov     r8, [r8+8]; unsigned __int16 *
0x180005c4d  lea     edx, [rcx+7]; unsigned int
0x180005c50  call    ?LogDeviceManagement@CWdsDeviceControllerManager@@AEAAXKPEBG0PEAVCWdsComMetadataBuilder@@KJ@Z; CWdsDeviceControllerManager::LogDeviceManagement(ulong,ushort const *,ushort const *,CWdsComMetadataBuilder *,ulong,long)
0x180005c55  mov     r9d, 975h; unsigned int
0x180005c5b  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005c62  mov     ecx, ebx; int
0x180005c64  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005c69  test    eax, eax
0x180005c6b  jns     short loc_180005CA2
0x180005c6d  test    ebx, ebx
0x180005c6f  jns     short loc_180005C82
0x180005c71  mov     eax, ebx
0x180005c73  and     eax, 1FFF0000h
0x180005c78  cmp     eax, 70000h
0x180005c7d  jnz     short loc_180005C82
0x180005c7f  movzx   ebx, bx
0x180005c82  mov     rcx, rdi; this
0x180005c85  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005c8a  lea     rcx, [rsp+140h+var_E0]; this
0x180005c8f  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005c94  lea     rcx, [rbp+40h+var_90]; this
0x180005c98  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180005c9d  jmp     loc_180005F95
0x180005ca2  mov     rcx, r12; this
0x180005ca5  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180005caa  mov     r9d, 978h; unsigned int
0x180005cb0  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005cb7  mov     ecx, eax; int
0x180005cb9  mov     ebx, eax
0x180005cbb  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180005cc0  test    eax, eax
0x180005cc2  js      short loc_180005C6D
0x180005cc4  cmp     word ptr [rbp+40h+arg_0], 0FFFFh
0x180005cc9  jz      short loc_180005CE8
0x180005ccb  mov     ecx, 2; unsigned int
0x180005cd0  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180005cd7  mov     r9d, 97Dh; unsigned int
  ... truncated ...
```
