# CBlbRestoreFilesAsync::InitializeExclusions(IBlbsrvRestoreFiles *)

- ea: `0x140071f1c`
- end: `0x140072687`
- name: `?InitializeExclusions@CBlbRestoreFilesAsync@@AEAAJPEAUIBlbsrvRestoreFiles@@@Z`
- size: `1899`
- prototype: `__int64 __fastcall(CBlbRestoreFilesAsync *__hidden this, struct IBlbsrvRestoreFiles *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140070400`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400701e0`
- `0x140071874`
- `0x140071f1c`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x1400f59d0`
- `0x14010240c`
- `0x140102560`
- `0x140104e8c`
- `0x1401104d8`
- `0x14012458c`
- `0x140137010`

## import_xrefs

- `KERNEL32!FindClose` at `0x140072215`
- `KERNEL32!FindClose` at `0x140072215`
- `ole32!CoTaskMemFree` at `0x14007212f`
- `ole32!CoTaskMemFree` at `0x140072146`
- `ole32!CoTaskMemFree` at `0x14007215d`
- `ole32!CoTaskMemFree` at `0x140072177`
- `ole32!CoTaskMemFree` at `0x140072185`
- `ole32!CoTaskMemFree` at `0x140072199`
- `ole32!CoTaskMemFree` at `0x1400721a7`
- `ole32!CoTaskMemFree` at `0x1400721b5`
- `ole32!CoTaskMemFree` at `0x1400721d4`
- `ole32!CoTaskMemFree` at `0x1400721e6`
- `ole32!CoTaskMemFree` at `0x1400721f9`
- `ole32!CoTaskMemFree` at `0x140072206`
- `ole32!CoTaskMemFree` at `0x140072540`
- `ole32!CoTaskMemFree` at `0x1400725bb`
- `ole32!CoTaskMemFree` at `0x14007212f`
- `ole32!CoTaskMemFree` at `0x140072146`
- `ole32!CoTaskMemFree` at `0x14007215d`
- `ole32!CoTaskMemFree` at `0x140072177`
- `ole32!CoTaskMemFree` at `0x140072185`
- `ole32!CoTaskMemFree` at `0x140072199`
- `ole32!CoTaskMemFree` at `0x1400721a7`
- `ole32!CoTaskMemFree` at `0x1400721b5`
- `ole32!CoTaskMemFree` at `0x1400721d4`
- `ole32!CoTaskMemFree` at `0x1400721e6`
- `ole32!CoTaskMemFree` at `0x1400721f9`
- `ole32!CoTaskMemFree` at `0x140072206`
- `ole32!CoTaskMemFree` at `0x140072540`
- `ole32!CoTaskMemFree` at `0x1400725bb`

## string_xrefs

- `0x140071f87`: `base\stor\blb\engine\service\restorefiles.cpp`

## pseudocode

```c
__int64 __fastcall CBlbRestoreFilesAsync::InitializeExclusions(
        CBlbRestoreFilesAsync *this,
        struct IBlbsrvRestoreFiles *a2)
{
  __int64 v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r13
  unsigned __int16 *v7; // r12
  int VolumeMap; // eax
  struct _BLBSRV_VOLUME_MAP *v9; // r15
  int ExcludedComponentsFromCatalog; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  CBlbRestoreFilesAsync *v13; // rax
  const struct _BLBCAT_COMPONENT_INFO *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  CBlbRestoreFilesAsync *v17; // r14
  void *v18; // rcx
  void *v19; // rcx
  CBlbImpersonationHelper *v21; // rsi
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  PVOID *v25; // rcx
  int v26; // eax
  struct IBlbsrvRestoreFiles *v27; // rdx
  unsigned __int16 *v28; // [rsp+40h] [rbp-39h] BYREF
  union _LARGE_INTEGER v29; // [rsp+48h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-1h] BYREF
  struct _BLBSRV_COMPONENT_INFO *v36; // [rsp+80h] [rbp+7h] BYREF
  struct _BLBSRV_VOLUME_MAP *v37; // [rsp+88h] [rbp+Fh] BYREF
  unsigned int v39; // [rsp+E8h] [rbp+6Fh] BYREF
  HANDLE hFindFile; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int16 *v41; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x897u, "pRestoreFiles != NULL");
  v4 = -1;
  pv = 0;
  hFindFile = (HANDLE)-1LL;
  v33 = 0;
  v34 = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v41 = 0;
  v7 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  v29.QuadPart = 0;
  v37 = 0;
  v36 = 0;
  v39 = 0;
  VolumeMap = CBlbRestoreFilesAsync::GetVolumeMap(this, &v37);
  v9 = v37;
  ExcludedComponentsFromCatalog = VolumeMap;
  if ( VolumeMap < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v12 = 67;
    goto LABEL_12;
  }
  ExcludedComponentsFromCatalog = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, __int64, struct _BLBSRV_VOLUME_MAP *))(*(_QWORD *)a2 + 48LL))(
                                    a2,
                                    1,
                                    v37);
  if ( ExcludedComponentsFromCatalog >= 0 )
  {
    v13 = this;
    v14 = (const struct _BLBCAT_COMPONENT_INFO *)*((_QWORD *)this + 51);
    if ( v14 )
    {
      ExcludedComponentsFromCatalog = BlbGetExcludedComponentsFromCatalog(v14, *((_DWORD *)this + 100), &v36, &v39);
      if ( ExcludedComponentsFromCatalog < 0 )
      {
LABEL_27:
        v4 = (__int64)hFindFile;
        goto LABEL_28;
      }
      if ( v36 )
      {
        ExcludedComponentsFromCatalog = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, __int64, struct _BLBSRV_VOLUME_MAP *, _QWORD, struct _BLBSRV_COMPONENT_INFO *))(*(_QWORD *)a2 + 56LL))(
                                          a2,
                                          1,
                                          v9,
                                          v39,
                                          v36);
        if ( ExcludedComponentsFromCatalog < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_27;
          }
          v16 = 69;
          goto LABEL_26;
        }
      }
      v13 = this;
    }
    v21 = (CBlbRestoreFilesAsync *)((char *)v13 + 32);
    ExcludedComponentsFromCatalog = BlbGetTargetPathForBackupSet(
                                      *((unsigned __int16 **)v13 + 37),
                                      0,
                                      (CBlbRestoreFilesAsync *)((char *)this + 320),
                                      (CBlbRestoreFilesAsync *)((char *)v13 + 32),
                                      &v33,
                                      &v34,
                                      (unsigned __int16 **)&pv);
    if ( ExcludedComponentsFromCatalog < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v23 = 70;
      goto LABEL_66;
    }
    ExcludedComponentsFromCatalog = CBlbImpersonationHelper::ImpersonateCaller(v21, 0);
    if ( ExcludedComponentsFromCatalog < 0 )
      goto LABEL_67;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    }
    ExcludedComponentsFromCatalog = BlbAppendRegistryExcludesFile(
                                      (unsigned __int16 *)pv,
                                      (UUID *)((char *)this + 252),
                                      0,
                                      &v41);
    if ( ExcludedComponentsFromCatalog < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v23 = 72;
LABEL_66:
      WPP_SF_d(v22[2], v23, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
LABEL_67:
      v5 = v41;
      goto LABEL_27;
    }
    v5 = v41;
    v29.QuadPart = 0;
    v24 = BlbReadFileFromTarget(v41, &v35, &v29);
    if ( v24 >= 0 )
    {
      ExcludedComponentsFromCatalog = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, unsigned __int16 *))(*(_QWORD *)a2 + 64LL))(
                                        a2,
                                        v35);
      if ( ExcludedComponentsFromCatalog < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_27;
        }
        v16 = 74;
LABEL_26:
        WPP_SF_d(v15[2], v16, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
        goto LABEL_27;
      }
    }
    else
    {
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_93;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_89:
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
          WPP_SF_(v25[2], 75, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
LABEL_93:
        ExcludedComponentsFromCatalog = BlbAppendWriterMetadataFile(
                                          (unsigned __int16 *)pv,
                                          (UUID *)((char *)this + 252),
                                          0,
                                          0,
                                          &v32);
        if ( ExcludedComponentsFromCatalog >= 0 )
        {
          v6 = v32;
          ExcludedComponentsFromCatalog = BlbFindFirstFile(v32, (LPVOID *)&v28, &hFindFile, 0);
          if ( ExcludedComponentsFromCatalog >= 0 )
          {
            v4 = (__int64)hFindFile;
            while ( 1 )
            {
              v7 = v28;
              if ( !v28 )
              {
                v27 = a2;
                v17 = this;
                ExcludedComponentsFromCatalog = CBlbRestoreFilesAsync::AddDedupPathToExcludes(
                                                  this,
                                                  v27,
                                                  *(unsigned __int16 **)v9);
                if ( ExcludedComponentsFromCatalog < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
                }
                goto LABEL_29;
              }
              v29.QuadPart = 0;
              if ( v31 )
              {
                CoTaskMemFree(v31);
                v31 = 0;
              }
              v26 = BlbReadFileFromTarget(v7, &v31, &v29);
              if ( v26 >= 0 )
              {
                ExcludedComponentsFromCatalog = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, unsigned __int16 *))(*(_QWORD *)a2 + 72LL))(
                                                  a2,
                                                  v31);
                if ( ExcludedComponentsFromCatalog < 0 )
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v12 = 79;
                    goto LABEL_12;
                  }
                  goto LABEL_28;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  78,
                  (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
                  (_DWORD)v7,
                  v26);
              }
              CoTaskMemFree(v7);
              v28 = 0;
              ExcludedComponentsFromCatalog = BlbFindNextFile(v6, (HANDLE)v4, (LPVOID *)&v28, 0);
              if ( ExcludedComponentsFromCatalog < 0 )
              {
                v7 = v28;
                goto LABEL_28;
              }
            }
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              77,
              (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
              (_DWORD)v6,
              ExcludedComponentsFromCatalog);
          }
          v7 = v28;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
          }
          v6 = v32;
        }
        goto LABEL_27;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
        (_DWORD)v5,
        v24);
    }
    v25 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_89;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_28;
  }
  v12 = 68;
LABEL_12:
  WPP_SF_d(v11[2], v12, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
LABEL_28:
  v17 = this;
LABEL_29:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v33 )
  {
    CoTaskMemFree(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    CoTaskMemFree(v34);
    v34 = 0;
  }
  if ( v35 )
    CoTaskMemFree(v35);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v31 )
    CoTaskMemFree(v31);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
    CoTaskMemFree(v7);
  BlbFreeSrvComponentInfo(&v36, v39);
  if ( v9 )
  {
    if ( *(_QWORD *)v9 )
    {
      CoTaskMemFree(*(LPVOID *)v9);
      *(_QWORD *)v9 = 0;
    }
    v18 = (void *)*((_QWORD *)v9 + 2);
    if ( v18 )
    {
      CoTaskMemFree(v18);
      *((_QWORD *)v9 + 2) = 0;
    }
    v19 = (void *)*((_QWORD *)v9 + 1);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      *((_QWORD *)v9 + 1) = 0;
    }
    CoTaskMemFree(v9);
  }
  if ( v4 != -1 )
    FindClose((HANDLE)v4);
  CBlbImpersonationHelper::Revert((CBlbRestoreFilesAsync *)((char *)v17 + 32));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return (unsigned int)ExcludedComponentsFromCatalog;
}

```

## disassembly

```asm
0x140071f1c  mov     [rsp-8+arg_0], rcx
0x140071f21  push    rbp
0x140071f22  push    rbx
0x140071f23  push    rsi
0x140071f24  push    rdi
0x140071f25  push    r12
0x140071f27  push    r13
0x140071f29  push    r14
0x140071f2b  push    r15
0x140071f2d  lea     rbp, [rsp-1Fh]
0x140071f32  sub     rsp, 98h
0x140071f39  mov     r14, rdx
0x140071f3c  mov     rbx, rcx
0x140071f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140071f46  lea     rax, WPP_GLOBAL_Control
0x140071f4d  cmp     rcx, rax
0x140071f50  jz      short loc_140071F73
0x140071f52  test    byte ptr [rcx+1Ch], 1
0x140071f56  jz      short loc_140071F73
0x140071f58  cmp     byte ptr [rcx+19h], 4
0x140071f5c  jb      short loc_140071F73
0x140071f5e  mov     rcx, [rcx+10h]
0x140071f62  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071f69  mov     edx, 42h ; 'B'
0x140071f6e  call    WPP_SF_
0x140071f73  xor     r15d, r15d
0x140071f76  test    r14, r14
0x140071f79  jnz     short loc_140071F93
0x140071f7b  lea     r8, aPrestorefilesN; "pRestoreFiles != NULL"
0x140071f82  mov     edx, 897h; unsigned int
0x140071f87  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140071f8e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140071f93  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140071f97  mov     [rbp+57h+pv], r15
0x140071f9b  lea     rdx, [rbp+57h+var_48]; struct _BLBSRV_VOLUME_MAP **
0x140071f9f  mov     [rbp+57h+hFindFile], rdi
0x140071fa3  mov     rcx, rbx; this
0x140071fa6  mov     [rbp+57h+var_68], r15
0x140071faa  mov     [rbp+57h+var_60], r15
0x140071fae  mov     rsi, r15
0x140071fb1  mov     [rbp+57h+var_58], r15
0x140071fb5  mov     r13, r15
0x140071fb8  mov     [rbp+57h+arg_18], r15
0x140071fbc  mov     r12, r15
0x140071fbf  mov     [rbp+57h+var_78], r15
0x140071fc3  mov     [rbp+57h+var_70], r15
0x140071fc7  mov     [rbp+57h+var_90], r15
0x140071fcb  mov     qword ptr [rbp+57h+var_88], r15
0x140071fcf  mov     [rbp+57h+var_48], r15
0x140071fd3  mov     [rbp+57h+var_50], r15
0x140071fd7  mov     [rbp+57h+arg_8], r15d
0x140071fdb  call    ?GetVolumeMap@CBlbRestoreFilesAsync@@QEAAJPEAPEAU_BLBSRV_VOLUME_MAP@@@Z; CBlbRestoreFilesAsync::GetVolumeMap(_BLBSRV_VOLUME_MAP * *)
0x140071fe0  mov     r15, [rbp+57h+var_48]
0x140071fe4  mov     ebx, eax
0x140071fe6  test    eax, eax
0x140071fe8  jns     short loc_140072030
0x140071fea  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ff1  lea     rax, WPP_GLOBAL_Control
0x140071ff8  cmp     rcx, rax
0x140071ffb  jz      loc_140072122
0x140072001  test    byte ptr [rcx+1Ch], 1
0x140072005  jz      loc_140072122
0x14007200b  cmp     byte ptr [rcx+19h], 2
0x14007200f  jb      loc_140072122
0x140072015  lea     edx, [rdi+44h]
0x140072018  mov     rcx, [rcx+10h]
0x14007201c  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072023  mov     r9d, ebx
0x140072026  call    WPP_SF_d
0x14007202b  jmp     loc_140072122
0x140072030  mov     rax, [r14]
0x140072033  mov     r8, r15
0x140072036  mov     edx, 1
0x14007203b  mov     rcx, r14
0x14007203e  mov     rax, [rax+30h]
0x140072042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072047  mov     ebx, eax
0x140072049  test    eax, eax
0x14007204b  jns     short loc_14007207F
0x14007204d  mov     rcx, cs:WPP_GLOBAL_Control
0x140072054  lea     rax, WPP_GLOBAL_Control
0x14007205b  cmp     rcx, rax
0x14007205e  jz      loc_140072122
0x140072064  test    byte ptr [rcx+1Ch], 1
0x140072068  jz      loc_140072122
0x14007206e  cmp     byte ptr [rcx+19h], 2
0x140072072  jb      loc_140072122
0x140072078  mov     edx, 44h ; 'D'
0x14007207d  jmp     short loc_140072018
0x14007207f  mov     rax, [rbp+57h+arg_0]
0x140072083  lea     rdi, [rax+140h]
0x14007208a  mov     rcx, [rdi+58h]; struct _BLBCAT_COMPONENT_INFO *
0x14007208e  test    rcx, rcx
0x140072091  jz      loc_140072272
0x140072097  mov     edx, [rax+190h]; unsigned int
0x14007209d  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x1400720a1  lea     r8, [rbp+57h+var_50]; struct _BLBSRV_COMPONENT_INFO **
0x1400720a5  call    ?BlbGetExcludedComponentsFromCatalog@@YAJPEBU_BLBCAT_COMPONENT_INFO@@KPEAPEAU_BLBSRV_COMPONENT_INFO@@PEAK@Z; BlbGetExcludedComponentsFromCatalog(_BLBCAT_COMPONENT_INFO const *,ulong,_BLBSRV_COMPONENT_INFO * *,ulong *)
0x1400720aa  mov     ebx, eax
0x1400720ac  test    eax, eax
0x1400720ae  js      short loc_14007211E
0x1400720b0  mov     rcx, [rbp+57h+var_50]
0x1400720b4  test    rcx, rcx
0x1400720b7  jz      loc_14007226E
0x1400720bd  mov     rax, [r14]
0x1400720c0  mov     r8, r15
0x1400720c3  mov     r9d, [rbp+57h+arg_8]
0x1400720c7  mov     edx, 1
0x1400720cc  mov     [rsp+0D0h+var_B0], rcx
0x1400720d1  mov     rcx, r14
0x1400720d4  mov     rax, [rax+38h]
0x1400720d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400720dd  mov     ebx, eax
0x1400720df  test    eax, eax
0x1400720e1  jns     loc_14007226E
0x1400720e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400720ee  lea     rax, WPP_GLOBAL_Control
0x1400720f5  cmp     rcx, rax
0x1400720f8  jz      short loc_14007211E
0x1400720fa  test    byte ptr [rcx+1Ch], 1
0x1400720fe  jz      short loc_14007211E
0x140072100  cmp     byte ptr [rcx+19h], 2
0x140072104  jb      short loc_14007211E
0x140072106  mov     edx, 45h ; 'E'
0x14007210b  mov     rcx, [rcx+10h]
0x14007210f  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072116  mov     r9d, ebx
0x140072119  call    WPP_SF_d
0x14007211e  mov     rdi, [rbp+57h+hFindFile]
0x140072122  mov     r14, [rbp+57h+arg_0]
0x140072126  mov     rcx, [rbp+57h+pv]; pv
0x14007212a  test    rcx, rcx
0x14007212d  jz      short loc_14007213D
0x14007212f  call    cs:__imp_CoTaskMemFree
0x140072135  mov     [rbp+57h+pv], 0
0x14007213d  mov     rcx, [rbp+57h+var_68]; pv
0x140072141  test    rcx, rcx
0x140072144  jz      short loc_140072154
0x140072146  call    cs:__imp_CoTaskMemFree
0x14007214c  mov     [rbp+57h+var_68], 0
0x140072154  mov     rcx, [rbp+57h+var_60]; pv
0x140072158  test    rcx, rcx
0x14007215b  jz      short loc_14007216B
0x14007215d  call    cs:__imp_CoTaskMemFree
0x140072163  mov     [rbp+57h+var_60], 0
0x14007216b  mov     rax, [rbp+57h+var_58]
0x14007216f  test    rax, rax
0x140072172  jz      short loc_14007217D
0x140072174  mov     rcx, rax; pv
0x140072177  call    cs:__imp_CoTaskMemFree
0x14007217d  test    rsi, rsi
0x140072180  jz      short loc_14007218B
0x140072182  mov     rcx, rsi; pv
0x140072185  call    cs:__imp_CoTaskMemFree
0x14007218b  mov     rax, [rbp+57h+var_78]
0x14007218f  xor     esi, esi
0x140072191  test    rax, rax
0x140072194  jz      short loc_14007219F
0x140072196  mov     rcx, rax; pv
0x140072199  call    cs:__imp_CoTaskMemFree
0x14007219f  test    r13, r13
0x1400721a2  jz      short loc_1400721AD
0x1400721a4  mov     rcx, r13; pv
0x1400721a7  call    cs:__imp_CoTaskMemFree
0x1400721ad  test    r12, r12
0x1400721b0  jz      short loc_1400721BB
0x1400721b2  mov     rcx, r12; pv
0x1400721b5  call    cs:__imp_CoTaskMemFree
0x1400721bb  mov     edx, [rbp+57h+arg_8]; unsigned int
0x1400721be  lea     rcx, [rbp+57h+var_50]; struct _BLBSRV_COMPONENT_INFO **
0x1400721c2  call    ?BlbFreeSrvComponentInfo@@YAXAEAPEAU_BLBSRV_COMPONENT_INFO@@K@Z; BlbFreeSrvComponentInfo(_BLBSRV_COMPONENT_INFO * &,ulong)
0x1400721c7  test    r15, r15
0x1400721ca  jz      short loc_14007220C
0x1400721cc  mov     rcx, [r15]; pv
0x1400721cf  test    rcx, rcx
0x1400721d2  jz      short loc_1400721DD
0x1400721d4  call    cs:__imp_CoTaskMemFree
0x1400721da  mov     [r15], rsi
0x1400721dd  mov     rcx, [r15+10h]; pv
0x1400721e1  test    rcx, rcx
0x1400721e4  jz      short loc_1400721F0
0x1400721e6  call    cs:__imp_CoTaskMemFree
0x1400721ec  mov     [r15+10h], rsi
0x1400721f0  mov     rcx, [r15+8]; pv
0x1400721f4  test    rcx, rcx
0x1400721f7  jz      short loc_140072203
0x1400721f9  call    cs:__imp_CoTaskMemFree
0x1400721ff  mov     [r15+8], rsi
0x140072203  mov     rcx, r15; pv
0x140072206  call    cs:__imp_CoTaskMemFree
0x14007220c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140072210  jz      short loc_14007221B
0x140072212  mov     rcx, rdi; hFindFile
0x140072215  call    cs:__imp_FindClose
0x14007221b  lea     rcx, [r14+20h]; this
0x14007221f  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140072224  mov     rcx, cs:WPP_GLOBAL_Control
0x14007222b  lea     rax, WPP_GLOBAL_Control
0x140072232  cmp     rcx, rax
0x140072235  jz      short loc_140072258
0x140072237  test    byte ptr [rcx+1Ch], 1
0x14007223b  jz      short loc_140072258
0x14007223d  cmp     byte ptr [rcx+19h], 4
0x140072241  jb      short loc_140072258
0x140072243  mov     rcx, [rcx+10h]
0x140072247  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x14007224e  mov     edx, 51h ; 'Q'
0x140072253  call    WPP_SF_
0x140072258  mov     eax, ebx
0x14007225a  add     rsp, 98h
0x140072261  pop     r15
0x140072263  pop     r14
0x140072265  pop     r13
0x140072267  pop     r12
0x140072269  pop     rdi
0x14007226a  pop     rsi
0x14007226b  pop     rbx
0x14007226c  pop     rbp
0x14007226d  retn
0x14007226e  mov     rax, [rbp+57h+arg_0]
0x140072272  lea     rcx, [rbp+57h+pv]
0x140072276  mov     r8, rdi; struct _BLBCAT_BACKUP_SET_INFO *
0x140072279  mov     [rsp+0D0h+var_A0], rcx; unsigned __int16 **
0x14007227e  lea     rsi, [rax+20h]
0x140072282  lea     rcx, [rbp+57h+var_60]
0x140072286  mov     r9, rsi; struct CBlbImpersonationHelper *
0x140072289  mov     [rsp+0D0h+var_A8], rcx; unsigned __int16 **
0x14007228e  xor     edx, edx; unsigned __int8
0x140072290  lea     rcx, [rbp+57h+var_68]
0x140072294  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 **
0x140072299  mov     rcx, [rax+128h]; unsigned __int16 *
0x1400722a0  call    ?BlbGetTargetPathForBackupSet@@YAJPEAGEPEAU_BLBCAT_BACKUP_SET_INFO@@PEAVCBlbImpersonationHelper@@PEAPEAG33@Z; BlbGetTargetPathForBackupSet(ushort *,uchar,_BLBCAT_BACKUP_SET_INFO *,CBlbImpersonationHelper *,ushort * *,ushort * *,ushort * *)
0x1400722a5  mov     ebx, eax
0x1400722a7  test    eax, eax
0x1400722a9  jns     short loc_1400722EB
0x1400722ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400722b2  lea     rax, WPP_GLOBAL_Control
0x1400722b9  cmp     rcx, rax
0x1400722bc  jz      short loc_1400722E2
0x1400722be  test    byte ptr [rcx+1Ch], 1
0x1400722c2  jz      short loc_1400722E2
0x1400722c4  cmp     byte ptr [rcx+19h], 2
0x1400722c8  jb      short loc_1400722E2
0x1400722ca  mov     edx, 46h ; 'F'
0x1400722cf  mov     r9d, ebx
0x1400722d2  mov     rcx, [rcx+10h]
0x1400722d6  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x1400722dd  call    WPP_SF_d
0x1400722e2  mov     rsi, [rbp+57h+arg_18]
0x1400722e6  jmp     loc_14007211E
0x1400722eb  xor     edx, edx; unsigned __int8
0x1400722ed  mov     rcx, rsi; this
0x1400722f0  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x1400722f5  mov     ebx, eax
0x1400722f7  test    eax, eax
0x1400722f9  js      short loc_1400722E2
0x1400722fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140072302  lea     rsi, WPP_GLOBAL_Control
0x140072309  cmp     rcx, rsi
0x14007230c  jz      short loc_14007232F
0x14007230e  test    byte ptr [rcx+1Ch], 1
0x140072312  jz      short loc_14007232F
0x140072314  cmp     byte ptr [rcx+19h], 4
0x140072318  jb      short loc_14007232F
0x14007231a  mov     rcx, [rcx+10h]
0x14007231e  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072325  mov     edx, 47h ; 'G'
0x14007232a  call    WPP_SF_
0x14007232f  mov     rdi, [rbp+57h+arg_0]
0x140072333  lea     r9, [rbp+57h+arg_18]; unsigned __int16 **
0x140072337  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x14007233b  xor     r8d, r8d; unsigned __int8
0x14007233e  lea     rdx, [rdi+0FCh]; Uuid
0x140072345  call    ?BlbAppendRegistryExcludesFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendRegistryExcludesFile(ushort *,_GUID *,uchar,ushort * *)
0x14007234a  mov     ebx, eax
0x14007234c  test    eax, eax
0x14007234e  jns     short loc_140072379
0x140072350  mov     rcx, cs:WPP_GLOBAL_Control
0x140072357  cmp     rcx, rsi
0x14007235a  jz      short loc_1400722E2
0x14007235c  test    byte ptr [rcx+1Ch], 1
0x140072360  jz      short loc_1400722E2
0x140072362  cmp     byte ptr [rcx+19h], 2
0x140072366  jb      loc_1400722E2
0x14007236c  mov     edx, 48h ; 'H'
0x140072371  mov     r9d, eax
0x140072374  jmp     loc_1400722D2
0x140072379  mov     rsi, [rbp+57h+arg_18]
0x14007237d  lea     r8, [rbp+57h+var_88]; union _LARGE_INTEGER *
0x140072381  mov     rcx, rsi; unsigned __int16 *
0x140072384  mov     qword ptr [rbp+57h+var_88], r12
0x140072388  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x14007238c  call    ?BlbReadFileFromTarget@@YAJPEAGPEAPEAGPEAT_LARGE_INTEGER@@@Z; BlbReadFileFromTarget(ushort *,ushort * *,_LARGE_INTEGER *)
0x140072391  test    eax, eax
0x140072393  jns     short loc_1400723DA
0x140072395  mov     rcx, cs:WPP_GLOBAL_Control
0x14007239c  lea     r13, WPP_GLOBAL_Control
0x1400723a3  cmp     rcx, r13
0x1400723a6  jz      loc_14007245C
0x1400723ac  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
