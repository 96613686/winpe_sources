# CDlpActionLayoutUsb::RecoverOemPartition(void)

- ea: `0x180026054`
- end: `0x180026f22`
- name: `?RecoverOemPartition@CDlpActionLayoutUsb@@AEAAJXZ`
- size: `3790`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016460`

## callees

- `0x18000aba4`
- `0x18000abc4`
- `0x180012f5c`
- `0x180019b00`
- `0x18001fd60`
- `0x180026054`
- `0x180028640`
- `0x180029424`
- `0x180029700`
- `0x180029780`
- `0x180039394`
- `0x18003e3c0`
- `0x18003ee54`
- `0x18003f2f0`
- `0x18003f9f8`
- `0x180040140`
- `0x1800417a8`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002618f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002618f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002650c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026bd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002650c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026bd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002651a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026c85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002651a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e68`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800262eb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800262eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026541`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026541`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026389`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026389`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetVolumeLabelW` at `0x180026e5e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetVolumeLabelW` at `0x180026e5e`

## string_xrefs

- `0x180026395`: `InitVDSServiceNoStatic:Loading VDS service... `
- `0x180026351`: `InitVDSServiceNoStatic:Creating VDS loader...`
- `0x180026409`: `InitVDSServiceNoStatic: Failed to load VDS service; hr = 0x%x.`
- `0x1800263e2`: `InitVDSServiceNoStatic:Successfully launched service.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpActionLayoutUsb::RecoverOemPartition(const unsigned __int16 **this)
{
  int v2; // ebx
  struct IVdsService *v3; // r15
  int DiskAndOffsetFromPath; // eax
  int Disk; // esi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  signed int LastError; // eax
  int v11; // eax
  struct IVdsAdvancedDisk *v12; // r14
  int v13; // r13d
  int v14; // eax
  struct IVdsDisk *v15; // r12
  HRESULT v16; // eax
  int v17; // eax
  unsigned __int64 v18; // r15
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  WCHAR *v22; // rdi
  HANDLE v23; // rax
  unsigned __int64 v25; // r12
  BOOL v26; // r15d
  __int64 v27; // rcx
  unsigned int v28; // r12d
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // r13d
  __int64 v33; // rcx
  struct IVdsDisk *v34; // r15
  int v35; // eax
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  LPVOID v41; // r12
  char *v42; // r15
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // r8
  int v48; // eax
  int Partition; // eax
  int v50; // eax
  const wchar_t *v51; // rsi
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // eax
  int v55; // r9d
  struct IVdsAdvancedDisk *v56; // r13
  int v57; // eax
  int v58; // eax
  int v59; // eax
  unsigned __int16 v60; // r15
  unsigned __int16 v61; // cx
  HANDLE ProcessHeap; // rax
  void *v63; // r8
  unsigned int i; // edx
  int v65; // edx
  int v66; // ecx
  HANDLE v67; // rax
  unsigned __int16 v68; // dx
  unsigned __int16 v69; // cx
  unsigned __int16 v70; // ax
  int v71; // eax
  int v72; // eax
  __int64 v73; // rcx
  int v74; // eax
  signed int v75; // eax
  int v76; // eax
  struct IVdsAdvancedDisk *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v78; // [rsp+28h] [rbp-D8h]
  struct IVdsService *v79; // [rsp+30h] [rbp-D0h]
  __int64 v80; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v81; // [rsp+40h] [rbp-C0h] BYREF
  struct IVdsAdvancedDisk *v82; // [rsp+48h] [rbp-B8h] BYREF
  struct IVdsDisk *v83; // [rsp+50h] [rbp-B0h] BYREF
  int v84[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v85; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v87; // [rsp+70h] [rbp-90h] BYREF
  int v88; // [rsp+78h] [rbp-88h]
  unsigned __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpRootPathName; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v91; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 0;
  v88 = 0;
  v3 = 0;
  lpRootPathName = 0;
  LODWORD(v80) = 0;
  LODWORD(v81) = 0;
  v84[0] = 0;
  v82 = 0;
  v87 = 0;
  v83 = 0;
  v91 = 0;
  lpMem = 0;
  v89 = 0;
  v85 = 0;
  DiskAndOffsetFromPath = CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(
                            (CDlpActionLayoutUsb *)this,
                            this[111],
                            (int *)&v80,
                            (unsigned __int64 *)&v82,
                            &v87);
  Disk = DiskAndOffsetFromPath;
  if ( DiskAndOffsetFromPath < 0 )
  {
    v6 = (__int64)this[11];
    if ( !v6 )
      goto LABEL_63;
    LODWORD(v78) = DiskAndOffsetFromPath;
    LODWORD(ppv) = 3330;
    goto LABEL_4;
  }
  v9 = CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(
         (CDlpActionLayoutUsb *)this,
         this[110],
         v84,
         (unsigned __int64 *)&v85,
         0);
  Disk = v9;
  if ( v9 >= 0 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      Disk = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          Disk = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        Disk = -2147467259;
      }
      if ( !this[11] )
        goto LABEL_63;
      v8 = 0;
      if ( Disk >= 0 )
      {
LABEL_6:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
        goto LABEL_63;
      }
      LODWORD(v78) = Disk;
      LODWORD(ppv) = 3339;
      v6 = (__int64)this[11];
LABEL_4:
      v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v6,
             4u,
             (__int64)L"%s(%d): Result = 0x%X",
             L"CDlpActionLayoutUsb::RecoverOemPartition",
             ppv,
             v78);
      v8 = (unsigned int)v7;
      if ( v7 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      goto LABEL_6;
    }
    v11 = CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(
            (CDlpActionLayoutUsb *)this,
            Buffer,
            (int *)&v81,
            (unsigned __int64 *)&v83,
            &v91);
    Disk = v11;
    if ( v11 < 0 )
    {
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = v11;
      LODWORD(ppv) = 3340;
      goto LABEL_4;
    }
    v12 = v82;
    v13 = v80;
    v14 = CDlpActionLayoutUsb::SendOemMessage(this, 7, 0, (unsigned int)v80, v82, v87, 0);
    Disk = v14;
    if ( v14 < 0 )
    {
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = v14;
      LODWORD(ppv) = 3344;
      goto LABEL_4;
    }
    v15 = v83;
    if ( v13 == (_DWORD)v81 && v12 == (struct IVdsAdvancedDisk *)v83 )
    {
      Disk = -1048575727;
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = -1048575727;
      LODWORD(ppv) = 3349;
      goto LABEL_4;
    }
    if ( v13 == v84[0] && v12 == v85 )
    {
      Disk = -1048575726;
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = -1048575726;
      LODWORD(ppv) = 3354;
      goto LABEL_4;
    }
    if ( ((_BYTE)this[171] & 2) != 0 )
      goto LABEL_63;
    Disk = 0;
    v16 = CoInitializeEx(0, 0);
    if ( v16 < 0 )
    {
      if ( v16 != -2147417850 )
      {
        Disk = v16;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
      }
    }
    else
    {
      v2 = 1;
      v88 = 1;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Disk);
    if ( Disk < 0 )
    {
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = Disk;
      LODWORD(ppv) = 3360;
      goto LABEL_4;
    }
    v85 = 0;
    *(_QWORD *)v84 = 0;
    v3 = 0;
    v79 = 0;
    LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Creating VDS loader...");
    Disk = CoCreateInstance(&CLSID_VdsLoader, 0, 0x10004u, &IID_IVdsServiceLoader, &v85);
    if ( Disk < 0
      || (LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Loading VDS service... "),
          Disk = (*(__int64 (__fastcall **)(LPVOID, _QWORD, int *))(*(_QWORD *)v85 + 24LL))(v85, 0, v84),
          Disk < 0)
      || (Disk = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v84 + 32LL))(*(_QWORD *)v84), Disk < 0) )
    {
      LibLog(
        &g_VdsLibLog,
        0x2000000,
        L"InitVDSServiceNoStatic: Failed to load VDS service; hr = 0x%x.",
        (unsigned int)Disk);
    }
    else
    {
      LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Successfully launched service.");
      v3 = *(struct IVdsService **)v84;
      v79 = *(struct IVdsService **)v84;
    }
    if ( v85 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v85 + 16LL))(v85);
    if ( Disk < 0 )
    {
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = Disk;
      LODWORD(ppv) = 3364;
      goto LABEL_4;
    }
    v17 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
    Disk = v17;
    if ( v17 < 0 )
    {
      v6 = (__int64)this[11];
      if ( !v6 )
        goto LABEL_63;
      LODWORD(v78) = v17;
      LODWORD(ppv) = 3365;
      goto LABEL_4;
    }
    v18 = (unsigned __int64)v15 + v91;
    if ( (struct IVdsDisk *)((char *)v15 + v91) < v15 )
    {
      v18 = 0;
      Disk = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    else
    {
      Disk = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Disk);
    if ( Disk < 0 )
    {
      v19 = (__int64)this[11];
      if ( v19 )
      {
        LODWORD(v78) = Disk;
        LODWORD(ppv) = 3369;
        goto LABEL_59;
      }
LABEL_62:
      v3 = v79;
      goto LABEL_63;
    }
    v25 = v18 + 0x2000000;
    if ( v18 + 0x2000000 < v18 )
    {
      v25 = 0;
      Disk = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    else
    {
      Disk = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Disk);
    if ( Disk < 0 )
    {
      v19 = (__int64)this[11];
      if ( !v19 )
        goto LABEL_62;
      LODWORD(v78) = Disk;
      LODWORD(ppv) = 3373;
      goto LABEL_59;
    }
    v26 = v13 == (_DWORD)v81 && (unsigned __int64)v12 >= v18 && (unsigned __int64)v12 <= v25;
    v27 = (__int64)this[11];
    v28 = v80;
    if ( v27 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v27,
        2u,
        (__int64)L"RecoverOem: Deleting the partition on disk [%d] at offset [0x%I64X]",
        (unsigned int)v80,
        v12);
    v29 = CDlpActionLayoutUsb::SendOemMessage(this, 5);
    Disk = v29;
    if ( v29 < 0 )
    {
      v19 = (__int64)this[11];
      if ( !v19 )
        goto LABEL_62;
      LODWORD(v78) = v29;
      LODWORD(ppv) = 3384;
      goto LABEL_59;
    }
    v30 = DeletePartition(v79, v28, (unsigned __int64)v12);
    Disk = v30;
    if ( v30 < 0 )
    {
      v19 = (__int64)this[11];
      if ( !v19 )
        goto LABEL_62;
      LODWORD(v78) = v30;
      LODWORD(ppv) = 3385;
      goto LABEL_59;
    }
    v31 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
    Disk = v31;
    if ( v31 < 0 )
    {
      v19 = (__int64)this[11];
      if ( !v19 )
        goto LABEL_62;
      LODWORD(v78) = v31;
      LODWORD(ppv) = 3386;
      goto LABEL_59;
    }
    v32 = 3;
    if ( v26 )
    {
      v33 = (__int64)this[11];
      v34 = v83;
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v33,
          2u,
          (__int64)L"RecoverOem: Extending the system partition on disk [%d] at offset [0x%I64X]",
          (unsigned int)v81,
          v83);
      v35 = CDlpActionLayoutUsb::SendOemMessage(this, 6);
      Disk = v35;
      if ( v35 < 0 )
      {
        v19 = (__int64)this[11];
        if ( !v19 )
          goto LABEL_62;
        LODWORD(v78) = v35;
        LODWORD(ppv) = 3391;
        goto LABEL_59;
      }
      v36 = (__int64)v34;
      v3 = v79;
      v37 = ExtendPartition(v79, v81, v36);
      v38 = (__int64)this[11];
      if ( v37 < 0 )
      {
        if ( v38 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v38,
            3u,
            (__int64)L"RecoverOem: Extending the system partition failed!  hr = [0x%X]",
            (unsigned int)v37);
        v48 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
        Disk = v48;
        if ( v48 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v48;
          LODWORD(ppv) = 3426;
          goto LABEL_4;
        }
LABEL_122:
        v45 = (__int64)this[11];
        if ( v45 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v45,
            2u,
            (__int64)L"RecoverOem: Creating partition on disk [%d] at offset [0x%I64X]",
            v28,
            v12);
        v46 = CDlpActionLayoutUsb::SendActionMessage(this, 4);
        Disk = v46;
        if ( v46 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v46;
          LODWORD(ppv) = 3433;
          goto LABEL_4;
        }
        Partition = CreatePartition(v3, v28, v47, 1, (unsigned __int64 *)&v82, v87);
        Disk = Partition;
        if ( Partition < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = Partition;
          LODWORD(ppv) = 3434;
          goto LABEL_4;
        }
        v50 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
        Disk = v50;
        if ( v50 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v50;
          LODWORD(ppv) = 3435;
          goto LABEL_4;
        }
        v51 = L"NTFS";
        if ( !*((_DWORD *)this + 341) )
        {
          *((_DWORD *)this + 341) = 1;
          v52 = (__int64)this[11];
          if ( v52 )
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v52,
              2u,
              (__int64)L"RecoverOem: Automatic file system selection: [%s]",
              L"NTFS");
        }
        if ( *((_DWORD *)this + 341) != 1 )
        {
          if ( *((_DWORD *)this + 341) == 2 )
          {
            v32 = 4;
            v51 = L"FAT32";
          }
          else
          {
            if ( *((_DWORD *)this + 341) != 3 )
            {
              Disk = -2147024883;
              v6 = (__int64)this[11];
              if ( !v6 )
                goto LABEL_63;
              LODWORD(v78) = -2147024883;
              LODWORD(ppv) = 3454;
              goto LABEL_4;
            }
            v32 = 8;
            v51 = L"EXFAT";
          }
        }
        v53 = (__int64)this[11];
        if ( v53 )
        {
          HIDWORD(v78) = HIDWORD(v51);
          ppv = v82;
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v53,
            2u,
            (__int64)L"RecoverOem: Formatting the partition on disk [%d] at offset [0x%I64X] with filesystem [%s]",
            v28);
        }
        v54 = CDlpActionLayoutUsb::SendOemMessage(this, 9);
        Disk = v54;
        if ( v54 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v54;
          LODWORD(ppv) = 3458;
          goto LABEL_4;
        }
        v55 = v32;
        v56 = v82;
        v57 = FormatPartitionEx(v3, v28, (__int64)v82, v55, (int)ppv);
        Disk = v57;
        if ( v57 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v57;
          LODWORD(ppv) = 3459;
          goto LABEL_4;
        }
        v58 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
        Disk = v58;
        v6 = (__int64)this[11];
        if ( v58 < 0 )
        {
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v58;
          LODWORD(ppv) = 3460;
          goto LABEL_4;
        }
        if ( v6 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v6,
            2u,
            (__int64)L"RecoverOem: Assigning drive letter to partition at offset [0x%I64X]",
            v56);
        v59 = CDlpActionLayoutUsb::SendOemMessage(this, 10);
        Disk = v59;
        if ( v59 < 0 )
        {
          v6 = (__int64)this[11];
          if ( !v6 )
            goto LABEL_63;
          LODWORD(v78) = v59;
          LODWORD(ppv) = 3465;
          goto LABEL_4;
        }
        v83 = 0;
        v82 = 0;
        LOWORD(v80) = 0;
        if ( !v3 || (v28 & 0x80000000) != 0 || !v56 )
        {
          Disk = -2147024809;
          goto LABEL_233;
        }
        v60 = 0;
        Disk = GetDisk(v79, v28, &v83, &v82, 0);
        if ( Disk >= 0 )
        {
          if ( !v83 || !v82 )
            goto LABEL_199;
          Disk = InternalGetSetDriveLetter(
                   v79,
                   (__int64 *)v83,
                   (__int64 *)v82,
                   v28,
                   (struct IVdsDiskVtbl *)v56,
                   (unsigned __int16 *)&v80);
          if ( Disk >= 0 )
          {
            v61 = v80;
            if ( (unsigned __int16)(v80 - 97) <= 0x19u )
              v61 = v80 - 32;
            LOWORD(v80) = v61;
            if ( (unsigned __int16)(v61 - 67) <= 0x17u )
            {
              Disk = 0;
              v60 = v61;
              goto LABEL_200;
            }
            ProcessHeap = GetProcessHeap();
            v63 = HeapAlloc(ProcessHeap, 8u, 0x2A0u);
            lpMem = v63;
            if ( !v63 )
            {
              Disk = -2147024882;
              goto LABEL_200;
            }
            v84[0] = 0;
            Disk = ((__int64 (__fastcall *)(struct IVdsService *, __int64, __int64, void *))v79->lpVtbl->QueryDriveLetters)(
                     v79,
                     67,
                     24,
                     v63);
            if ( Disk >= 0 )
            {
              for ( i = 0; i < 0x18; ++i )
              {
                if ( *((_DWORD *)lpMem + 7 * (int)i + 6) != 1 )
                  break;
              }
              if ( i >= 0x18 )
              {
                Disk = -2147467259;
              }
              else
              {
                v65 = *((unsigned __int16 *)lpMem + 14 * (int)i);
                v66 = v65 - 32;
                if ( (unsigned __int16)(v65 - 97) > 0x19u )
                  LOWORD(v66) = v65;
                v84[0] = v66;
              }
            }
            v67 = GetProcessHeap();
            HeapFree(v67, 0, lpMem);
            if ( Disk < 0 )
              goto LABEL_200;
            v68 = LOWORD(v84[0]) - 97;
            v69 = v84[0];
            v70 = LOWORD(v84[0]) - 32;
            if ( (unsigned __int16)(LOWORD(v84[0]) - 97) > 0x19u )
              v70 = v84[0];
            if ( v70 >= 0x61u )
            {
              v60 = v84[0];
              if ( v68 <= 0x19u )
                v60 = LOWORD(v84[0]) - 32;
              if ( v60 <= 0x7Au )
                goto LABEL_198;
            }
            v60 = v84[0];
            if ( v68 <= 0x19u )
              v60 = LOWORD(v84[0]) - 32;
            if ( v60 >= 0x41u )
            {
              if ( v68 <= 0x19u )
                v69 = LOWORD(v84[0]) - 32;
              v60 = v69;
              if ( v69 <= 0x5Au )
              {
LABEL_198:
                LOWORD(v81) = v60;
                Disk = InternalGetSetDriveLetter(
                         v79,
                         (__int64 *)v83,
                         (__int64 *)v82,
                         v28,
                         (struct IVdsDiskVtbl *)v56,
                         (unsigned __int16 *)&v81);
                goto LABEL_200;
              }
            }
LABEL_199:
            Disk = -2147024883;
          }
        }
LABEL_200:
        if ( v82 )
        {
          ((void (__fastcall *)(struct IVdsAdvancedDisk *))v82->lpVtbl->Release)(v82);
          v82 = 0;
        }
        if ( v83 )
          ((void (__fastcall *)(struct IVdsDisk *))v83->lpVtbl->Release)(v83);
        if ( Disk >= 0 )
        {
          v71 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
          Disk = v71;
          v19 = (__int64)this[11];
          if ( v71 < 0 )
          {
            if ( !v19 )
              goto LABEL_62;
            LODWORD(v78) = v71;
            LODWORD(ppv) = 3468;
            goto LABEL_59;
          }
          if ( v19 )
          {
            LODWORD(ppv) = v60;
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v19,
              2u,
              (__int64)L"RecoverOem: Partition at offset [0x%I64X] has drive letter [%c]",
              v56,
              ppv);
          }
          v72 = STRAPI_Format((unsigned __int16 **)&lpRootPathName, L"%c:\\", v60);
          Disk = v72;
          if ( v72 < 0 )
          {
            v19 = (__int64)this[11];
            if ( !v19 )
              goto LABEL_62;
            LODWORD(v78) = v72;
            LODWORD(ppv) = 3471;
            goto LABEL_59;
          }
          if ( !this[120] )
            goto LABEL_229;
          v73 = (__int64)this[11];
          if ( v73 )
            CDlpLogT<CEmptyType>::DlpLogFormat(v73, 2u, (__int64)L"RecoverOem: Setting volume label to: [%s]");
          v74 = CDlpActionLayoutUsb::SendOemMessage(this, 11);
          Disk = v74;
          if ( v74 < 0 )
          {
            v19 = (__int64)this[11];
            if ( !v19 )
              goto LABEL_62;
            LODWORD(v78) = v74;
            LODWORD(ppv) = 3481;
            goto LABEL_59;
          }
          if ( SetVolumeLabelW(lpRootPathName, this[120]) )
          {
LABEL_229:
            v76 = CDlpActionLayoutUsb::SendOemMessage(this, 12, v60, v28, v56, v87, v79);
            Disk = v76;
            if ( v76 >= 0 )
              goto LABEL_62;
            v19 = (__int64)this[11];
            if ( !v19 )
              goto LABEL_62;
            LODWORD(v78) = v76;
            LODWORD(ppv) = 3487;
          }
          else
          {
            v75 = GetLastError();
            Disk = v75;
            if ( v75 )
            {
              if ( v75 > 0 )
                Disk = (unsigned __int16)v75 | 0x80070000;
            }
            else
            {
              Disk = -2147467259;
            }
            if ( !this[11] )
              goto LABEL_62;
            v21 = 0;
            if ( Disk >= 0 )
              goto LABEL_61;
            LODWORD(v78) = Disk;
            LODWORD(ppv) = 3482;
            v19 = (__int64)this[11];
          }
          goto LABEL_59;
        }
        v3 = v79;
LABEL_233:
        v6 = (__int64)this[11];
        if ( !v6 )
          goto LABEL_63;
        LODWORD(v78) = Disk;
        LODWORD(ppv) = 3467;
        goto LABEL_4;
      }
      if ( v38 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v38, 2u, (__int64)L"RecoverOem: Extending the system partition succeeded!");
      v39 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt((__int64)this);
      Disk = v39;
      if ( v39 < 0 )
      {
        v6 = (__int64)this[11];
        if ( !v6 )
          goto LABEL_63;
        LODWORD(v78) = v39;
        LODWORD(ppv) = 3399;
        goto LABEL_4;
      }
      v40 = CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(
              (CDlpActionLayoutUsb *)this,
              Buffer,
              (int *)&v81,
              (unsigned __int64 *)&lpMem,
              &v89);
      Disk = v40;
      if ( v40 < 0 )
      {
        v6 = (__int64)this[11];
        if ( !v6 )
          goto LABEL_63;
        LODWORD(v78) = v40;
        LODWORD(ppv) = 3403;
        goto LABEL_4;
      }
      v41 = lpMem;
      v42 = (char *)lpMem + v89;
      if ( (char *)lpMem + v89 < lpMem )
      {
        v42 = 0;
        Disk = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
      }
      else
      {
        Disk = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Disk);
      if ( Disk < 0 )
      {
        v19 = (__int64)this[11];
        if ( !v19 )
          goto LABEL_62;
        LODWORD(v78) = Disk;
        LODWORD(ppv) = 3407;
        goto LABEL_59;
      }
      if ( v42 > (char *)v12 )
      {
        v43 = CDlpActionLayoutUsb::SendOemMessage(this, 12, Buffer[0], (unsigned int)v81, v41, v89, v79);
        Disk = v43;
        if ( v43 >= 0 )
        {
          Disk = 0;
          goto LABEL_62;
        }
        v19 = (__int64)this[11];
        if ( !v19 )
          goto LABEL_62;
        LODWORD(v78) = v43;
        LODWORD(ppv) = 3415;
LABEL_59:
        v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v19,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::RecoverOemPartition",
                ppv,
                v78);
        v21 = (unsigned int)v20;
        if ( v20 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
LABEL_61:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v21);
        goto LABEL_62;
      }
      v44 = (__int64)this[11];
      if ( v44 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v44,
          3u,
          (__int64)L"RecoverOem: System partition was not extended beyond OEM partition!");
      v28 = v80;
    }
    v3 = v79;
    goto LABEL_122;
  }
  v6 = (__int64)this[11];
  if ( v6 )
  {
    LODWORD(v78) = v9;
    LODWORD(ppv) = 3334;
    goto LABEL_4;
  }
LABEL_63:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)Disk);
  if ( lpRootPathName )
  {
    v22 = (WCHAR *)(lpRootPathName - 2);
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
    ((void (__fastcall *)(struct IVdsService *))v3->lpVtbl->Release)(v3);
  if ( v2 )
    CoUninitialize();
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x180026054  push    rbp
0x180026056  push    rbx
0x180026057  push    rsi
0x180026058  push    rdi
0x180026059  push    r12
0x18002605b  push    r13
0x18002605d  push    r14
0x18002605f  push    r15
0x180026061  lea     rbp, [rsp-1C8h]
0x180026069  sub     rsp, 2C8h
0x180026070  mov     rax, cs:__security_cookie
0x180026077  xor     rax, rsp
0x18002607a  mov     [rbp+200h+var_50], rax
0x180026081  mov     rdi, rcx
0x180026084  xor     r14d, r14d
0x180026087  mov     ebx, r14d
0x18002608a  mov     [rsp+300h+var_288], ebx
0x18002608e  mov     r15d, r14d
0x180026091  mov     [rsp+300h+var_2D0], r14
0x180026096  mov     [rbp+200h+lpRootPathName], r14
0x18002609a  mov     dword ptr [rsp+300h+var_2C8], r14d
0x18002609f  mov     dword ptr [rsp+300h+var_2C0], r14d
0x1800260a4  mov     [rsp+300h+var_2A8], r14d
0x1800260a9  mov     [rsp+300h+var_2B8], r14
0x1800260ae  mov     [rsp+300h+var_290], r14
0x1800260b3  mov     [rsp+300h+var_2B0], r14
0x1800260b8  mov     [rbp+200h+var_270], r14
0x1800260bc  mov     [rsp+300h+lpMem], r14
0x1800260c1  mov     [rbp+200h+var_280], r14
0x1800260c5  mov     [rsp+300h+var_2A0], r14
0x1800260ca  lea     rax, [rsp+300h+var_290]
0x1800260cf  mov     [rsp+300h+ppv], rax; unsigned __int64 *
0x1800260d4  lea     r9, [rsp+300h+var_2B8]; unsigned __int64 *
0x1800260d9  lea     r8, [rsp+300h+var_2C8]; int *
0x1800260de  mov     rdx, [rcx+378h]; unsigned __int16 *
0x1800260e5  call    ?GetDiskAndOffsetFromPath@CDlpActionLayoutUsb@@AEAAJPEBGPEAHPEA_K2@Z; CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(ushort const *,int *,unsigned __int64 *,unsigned __int64 *)
0x1800260ea  mov     esi, eax
0x1800260ec  test    eax, eax
0x1800260ee  jns     short loc_180026136
0x1800260f0  mov     rcx, [rdi+58h]
0x1800260f4  test    rcx, rcx
0x1800260f7  jz      loc_1800264F7
0x1800260fd  mov     dword ptr [rsp+300h+var_2D8], eax
0x180026101  mov     dword ptr [rsp+300h+ppv], 0D02h
0x180026109  mov     edx, 4
0x18002610e  lea     r9, aCdlpactionlayo_1; "CDlpActionLayoutUsb::RecoverOemPartitio"...
0x180026115  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002611c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180026121  test    eax, eax
0x180026123  mov     ecx, eax
0x180026125  jns     short loc_18002612C
0x180026127  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002612c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026131  jmp     loc_1800264F7
0x180026136  mov     [rsp+300h+ppv], r14; unsigned __int64 *
0x18002613b  lea     r9, [rsp+300h+var_2A0]; unsigned __int64 *
0x180026140  lea     r8, [rsp+300h+var_2A8]; int *
0x180026145  mov     rdx, [rdi+370h]; unsigned __int16 *
0x18002614c  mov     rcx, rdi; this
0x18002614f  call    ?GetDiskAndOffsetFromPath@CDlpActionLayoutUsb@@AEAAJPEBGPEAHPEA_K2@Z; CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(ushort const *,int *,unsigned __int64 *,unsigned __int64 *)
0x180026154  mov     esi, eax
0x180026156  test    eax, eax
0x180026158  jns     short loc_180026175
0x18002615a  mov     rcx, [rdi+58h]
0x18002615e  test    rcx, rcx
0x180026161  jz      loc_1800264F7
0x180026167  mov     dword ptr [rsp+300h+var_2D8], eax
0x18002616b  mov     dword ptr [rsp+300h+ppv], 0D06h
0x180026173  jmp     short loc_180026109
0x180026175  xor     edx, edx; Val
0x180026177  mov     r8d, 208h; Size
0x18002617d  lea     rcx, [rbp+200h+Buffer]; void *
0x180026181  call    memset_0
0x180026186  mov     edx, 104h; uSize
0x18002618b  lea     rcx, [rbp+200h+Buffer]; lpBuffer
0x18002618f  call    cs:__imp_GetSystemWindowsDirectoryW
0x180026195  test    eax, eax
0x180026197  jnz     short loc_1800261E1
0x180026199  call    cs:__imp_GetLastError
0x18002619f  mov     esi, eax
0x1800261a1  test    eax, eax
0x1800261a3  jnz     short loc_1800261AC
0x1800261a5  mov     esi, 80004005h
0x1800261aa  jmp     short loc_1800261B7
0x1800261ac  jle     short loc_1800261B7
0x1800261ae  movzx   esi, ax
0x1800261b1  or      esi, 80070000h
0x1800261b7  cmp     [rdi+58h], r14
0x1800261bb  jz      loc_1800264F7
0x1800261c1  mov     ecx, r14d
0x1800261c4  test    esi, esi
0x1800261c6  jns     loc_18002612C
0x1800261cc  mov     dword ptr [rsp+300h+var_2D8], esi
0x1800261d0  mov     dword ptr [rsp+300h+ppv], 0D0Bh
0x1800261d8  mov     rcx, [rdi+58h]
0x1800261dc  jmp     loc_180026109
0x1800261e1  lea     rax, [rbp+200h+var_270]
0x1800261e5  mov     [rsp+300h+ppv], rax; unsigned __int64 *
0x1800261ea  lea     r9, [rsp+300h+var_2B0]; unsigned __int64 *
0x1800261ef  lea     r8, [rsp+300h+var_2C0]; int *
0x1800261f4  lea     rdx, [rbp+200h+Buffer]; unsigned __int16 *
0x1800261f8  mov     rcx, rdi; this
0x1800261fb  call    ?GetDiskAndOffsetFromPath@CDlpActionLayoutUsb@@AEAAJPEBGPEAHPEA_K2@Z; CDlpActionLayoutUsb::GetDiskAndOffsetFromPath(ushort const *,int *,unsigned __int64 *,unsigned __int64 *)
0x180026200  mov     esi, eax
0x180026202  test    eax, eax
0x180026204  jns     short loc_180026224
0x180026206  mov     rcx, [rdi+58h]
0x18002620a  test    rcx, rcx
0x18002620d  jz      loc_1800264F7
0x180026213  mov     dword ptr [rsp+300h+var_2D8], eax
0x180026217  mov     dword ptr [rsp+300h+ppv], 0D0Ch
0x18002621f  jmp     loc_180026109
0x180026224  xor     r8d, r8d
0x180026227  mov     rax, [rsp+300h+var_290]
0x18002622c  mov     [rsp+300h+var_2D8], rax
0x180026231  mov     r14, [rsp+300h+var_2B8]
0x180026236  mov     [rsp+300h+ppv], r14
0x18002623b  mov     r13d, dword ptr [rsp+300h+var_2C8]
0x180026240  mov     r9d, r13d
0x180026243  lea     edx, [r8+7]
0x180026247  mov     rcx, rdi
0x18002624a  call    ?SendOemMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@GK_K1@Z; CDlpActionLayoutUsb::SendOemMessage(LAYOUTUSB_ACTION,ushort,ulong,unsigned __int64,unsigned __int64)
0x18002624f  mov     esi, eax
0x180026251  test    eax, eax
0x180026253  jns     short loc_180026273
0x180026255  mov     rcx, [rdi+58h]
0x180026259  test    rcx, rcx
0x18002625c  jz      loc_1800264F7
0x180026262  mov     dword ptr [rsp+300h+var_2D8], eax
0x180026266  mov     dword ptr [rsp+300h+ppv], 0D10h
0x18002626e  jmp     loc_180026109
0x180026273  mov     r12, [rsp+300h+var_2B0]
0x180026278  cmp     r13d, dword ptr [rsp+300h+var_2C0]
0x18002627d  jnz     short loc_1800262A7
0x18002627f  cmp     r14, r12
0x180026282  jnz     short loc_1800262A7
0x180026284  mov     esi, 0C1800111h
0x180026289  mov     rcx, [rdi+58h]
0x18002628d  test    rcx, rcx
0x180026290  jz      loc_1800264F7
0x180026296  mov     dword ptr [rsp+300h+var_2D8], esi
0x18002629a  mov     dword ptr [rsp+300h+ppv], 0D15h
0x1800262a2  jmp     loc_180026109
0x1800262a7  cmp     r13d, [rsp+300h+var_2A8]
0x1800262ac  jnz     short loc_1800262D8
0x1800262ae  cmp     r14, [rsp+300h+var_2A0]
0x1800262b3  jnz     short loc_1800262D8
0x1800262b5  mov     esi, 0C1800112h
0x1800262ba  mov     rcx, [rdi+58h]
0x1800262be  test    rcx, rcx
0x1800262c1  jz      loc_1800264F7
0x1800262c7  mov     dword ptr [rsp+300h+var_2D8], esi
0x1800262cb  mov     dword ptr [rsp+300h+ppv], 0D1Ah
0x1800262d3  jmp     loc_180026109
0x1800262d8  test    byte ptr [rdi+558h], 2
0x1800262df  jnz     loc_1800264F7
0x1800262e5  xor     esi, esi
0x1800262e7  xor     edx, edx; dwCoInit
0x1800262e9  xor     ecx, ecx; pvReserved
0x1800262eb  call    cs:__imp_CoInitializeEx
0x1800262f1  test    eax, eax
0x1800262f3  js      short loc_1800262FE
0x1800262f5  lea     ebx, [rsi+1]
0x1800262f8  mov     [rsp+300h+var_288], ebx
0x1800262fc  jmp     short loc_18002630E
0x1800262fe  cmp     eax, 80010106h
0x180026303  jz      short loc_18002630E
0x180026305  mov     esi, eax
0x180026307  mov     ecx, eax
0x180026309  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002630e  mov     ecx, esi
0x180026310  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026315  test    esi, esi
0x180026317  jns     short loc_180026337
0x180026319  mov     rcx, [rdi+58h]
0x18002631d  test    rcx, rcx
0x180026320  jz      loc_1800264F7
0x180026326  mov     dword ptr [rsp+300h+var_2D8], esi
0x18002632a  mov     dword ptr [rsp+300h+ppv], 0D20h
0x180026332  jmp     loc_180026109
0x180026337  mov     [rsp+300h+var_2A0], 0
0x180026340  mov     qword ptr [rsp+300h+var_2A8], 0
0x180026349  xor     r15d, r15d
0x18002634c  mov     [rsp+300h+var_2D0], r15
0x180026351  lea     r8, aInitvdsservice; "InitVDSServiceNoStatic:Creating VDS loa"...
0x180026358  mov     edx, 4000000h
0x18002635d  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180026364  call    LibLog
0x180026369  lea     rax, [rsp+300h+var_2A0]
0x18002636e  mov     [rsp+300h+ppv], rax; ppv
0x180026373  lea     r9, IID_IVdsServiceLoader; riid
0x18002637a  xor     edx, edx; pUnkOuter
0x18002637c  mov     r8d, 10004h; dwClsContext
0x180026382  lea     rcx, CLSID_VdsLoader; rclsid
0x180026389  call    cs:__imp_CoCreateInstance
0x18002638f  mov     esi, eax
0x180026391  test    eax, eax
0x180026393  js      short loc_180026406
0x180026395  lea     r8, aInitvdsservice_2; "InitVDSServiceNoStatic:Loading VDS serv"...
0x18002639c  mov     edx, 4000000h
0x1800263a1  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x1800263a8  call    LibLog
0x1800263ad  mov     rcx, [rsp+300h+var_2A0]
0x1800263b2  mov     rax, [rcx]
0x1800263b5  lea     r8, [rsp+300h+var_2A8]
0x1800263ba  xor     edx, edx
0x1800263bc  mov     rax, [rax+18h]
0x1800263c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263c5  mov     esi, eax
0x1800263c7  test    eax, eax
0x1800263c9  js      short loc_180026406
0x1800263cb  mov     rcx, qword ptr [rsp+300h+var_2A8]
0x1800263d0  mov     rax, [rcx]
0x1800263d3  mov     rax, [rax+20h]
0x1800263d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263dc  mov     esi, eax
0x1800263de  test    eax, eax
0x1800263e0  js      short loc_180026406
0x1800263e2  lea     r8, aInitvdsservice_1; "InitVDSServiceNoStatic:Successfully lau"...
0x1800263e9  mov     edx, 4000000h
0x1800263ee  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x1800263f5  call    LibLog
0x1800263fa  mov     r15, qword ptr [rsp+300h+var_2A8]
0x1800263ff  mov     [rsp+300h+var_2D0], r15
0x180026404  jmp     short loc_180026421
0x180026406  mov     r9d, esi
0x180026409  lea     r8, aInitvdsservice_0; "InitVDSServiceNoStatic: Failed to load "...
0x180026410  mov     edx, 2000000h
0x180026415  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18002641c  call    LibLog
0x180026421  mov     rcx, [rsp+300h+var_2A0]
0x180026426  test    rcx, rcx
0x180026429  jz      short loc_180026437
0x18002642b  mov     rax, [rcx]
0x18002642e  mov     rax, [rax+10h]
0x180026432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026437  test    esi, esi
0x180026439  jns     short loc_180026459
0x18002643b  mov     rcx, [rdi+58h]
0x18002643f  test    rcx, rcx
0x180026442  jz      loc_1800264F7
0x180026448  mov     dword ptr [rsp+300h+var_2D8], esi
0x18002644c  mov     dword ptr [rsp+300h+ppv], 0D24h
0x180026454  jmp     loc_180026109
0x180026459  mov     rcx, rdi
0x18002645c  call    ?CheckUserInterrupt@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAW4WINDLP_INTERRUPT_REASON@@@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(WINDLP_INTERRUPT_REASON *)
0x180026461  mov     esi, eax
0x180026463  test    eax, eax
0x180026465  jns     short loc_180026485
0x180026467  mov     rcx, [rdi+58h]
0x18002646b  test    rcx, rcx
0x18002646e  jz      loc_1800264F7
0x180026474  mov     dword ptr [rsp+300h+var_2D8], eax
0x180026478  mov     dword ptr [rsp+300h+ppv], 0D25h
0x180026480  jmp     loc_180026109
0x180026485  mov     r15, [rbp+200h+var_270]
0x180026489  add     r15, r12
0x18002648c  mov     eax, 80070216h
0x180026491  cmp     r15, r12
0x180026494  jb      short loc_18002649A
0x180026496  xor     esi, esi
0x180026498  jmp     short loc_1800264A6
0x18002649a  xor     r15d, r15d
0x18002649d  mov     esi, eax
0x18002649f  mov     ecx, eax
0x1800264a1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800264a6  mov     ecx, esi
0x1800264a8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800264ad  test    esi, esi
0x1800264af  jns     loc_18002656C
0x1800264b5  mov     rcx, [rdi+58h]
0x1800264b9  test    rcx, rcx
0x1800264bc  jz      short loc_1800264F2
0x1800264be  mov     dword ptr [rsp+300h+var_2D8], esi
0x1800264c2  mov     dword ptr [rsp+300h+ppv], 0D29h
0x1800264ca  mov     edx, 4
0x1800264cf  lea     r9, aCdlpactionlayo_1; "CDlpActionLayoutUsb::RecoverOemPartitio"...
0x1800264d6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800264dd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800264e2  test    eax, eax
0x1800264e4  mov     ecx, eax
0x1800264e6  jns     short loc_1800264ED
0x1800264e8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800264ed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800264f2  mov     r15, [rsp+300h+var_2D0]
0x1800264f7  mov     ecx, esi
0x1800264f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800264fe  nop
0x1800264ff  mov     rax, [rbp+200h+lpRootPathName]
0x180026503  test    rax, rax
0x180026506  jz      short loc_180026528
0x180026508  lea     rdi, [rax-4]
0x18002650c  call    cs:__imp_GetProcessHeap
0x180026512  mov     rcx, rax; hHeap
0x180026515  mov     r8, rdi; lpMem
0x180026518  xor     edx, edx; dwFlags
0x18002651a  call    cs:__imp_HeapFree
0x180026520  xor     ecx, ecx
0x180026522  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026527  nop
  ... truncated ...
```
