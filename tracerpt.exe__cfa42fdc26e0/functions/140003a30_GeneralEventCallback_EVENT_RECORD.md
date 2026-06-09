# GeneralEventCallback(_EVENT_RECORD *)

- ea: `0x140003a30`
- end: `0x140004695`
- name: `?GeneralEventCallback@@YAXPEAU_EVENT_RECORD@@@Z`
- size: `3173`
- prototype: `void __fastcall(struct _EVENT_RECORD *)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x140002c20`
- `0x1400032c0`
- `0x1400033c0`
- `0x140003a30`
- `0x140004778`
- `0x140004afc`
- `0x140004c2c`
- `0x140004cac`
- `0x140004f08`
- `0x140005914`
- `0x140005acc`
- `0x140006588`
- `0x1400069c8`
- `0x140006db8`
- `0x140006f6c`
- `0x140007658`
- `0x1400078ec`
- `0x140007ec4`
- `0x140008d14`
- `0x140009258`
- `0x140009880`
- `0x140009d78`
- `0x140009ea8`
- `0x14000a0d4`
- `0x14000a3a4`
- `0x14000ae40`
- `0x140011a0c`
- `0x14001ceb0`
- `0x14001d51c`
- `0x14002e0b8`
- `0x1400400d6`
- `0x140040130`

## import_xrefs

- `tdh!TdhLoadManifestFromBinary` at `0x140003b42`
- `tdh!TdhLoadManifestFromBinary` at `0x140003b42`

## string_xrefs

- `0x14000411b`: `TaskId`
- `0x14000423f`: `IssuingThreadId`
- `0x140003b2d`: `BinaryPath`

## pseudocode

```c
void __fastcall GeneralEventCallback(struct _EVENT_RECORD *a1)
{
  unsigned int v2; // r12d
  char v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rax
  GUID *p_ProviderId; // rbx
  __int64 v7; // r15
  __int64 v8; // r8
  int v9; // ecx
  struct _MOF_INFO *v10; // rax
  struct _MOF_INFO *v11; // rsi
  struct _MOF_VERSION *v12; // rax
  struct _MOF_VERSION *v13; // r15
  struct _MOF_COUNT *v14; // rax
  GUID *v15; // rbx
  __int64 v16; // r10
  int v17; // edx
  bool v18; // cf
  bool v19; // zf
  unsigned int v20; // r10d
  unsigned int v21; // r9d
  int v22; // ecx
  struct _MOF_INFO *MofInfoHead; // rax
  struct _MOF_INFO *v24; // rsi
  struct _MOF_VERSION *MofVersion; // rax
  struct _MOF_VERSION *v26; // r15
  struct _MOF_COUNT *MofCount; // rax
  struct _THREAD_RECORD *GlobalThreadById; // rsi
  __int64 v29; // r13
  UCHAR Opcode; // al
  ULONG ProcessId; // ebx
  int v32; // ecx
  struct _SERVICE_RECORD *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  UCHAR v36; // al
  unsigned int v37; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  _BYTE v39[528]; // [rsp+30h] [rbp-D0h] BYREF

  if ( !a1 || !g_TraceContext )
    return;
  v2 = 0;
  v38[0] = 0;
  v37 = 0;
  if ( *((_BYTE *)g_TraceContext + 8505) && (*((_BYTE *)g_TraceContext + 6416) & 8) != 0 )
  {
    GetEventCategory(a1);
    v2 = v37;
    v3 = 1;
  }
  else
  {
    v3 = 1;
  }
  ++TotalEventCount;
  v4 = *(_QWORD *)&EventTraceGuid.Data1;
  qword_1400820B0 = a1->EventHeader.TimeStamp.QuadPart;
  v5 = *(_QWORD *)EventTraceGuid.Data4;
  if ( !XPorHigher )
  {
    v7 = FileIoGuid;
LABEL_37:
    v8 = ProcessGuid;
    goto LABEL_38;
  }
  p_ProviderId = &a1->EventHeader.ProviderId;
  if ( *(_QWORD *)&a1->EventHeader.ProviderId.Data1 == *(_QWORD *)&EventTraceGuid.Data1
    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == *(_QWORD *)EventTraceGuid.Data4
    && a1->EventHeader.EventDescriptor.Opcode == 67 )
  {
    memset_0(v39, 0, 0x208u);
    v38[0] = 520;
    if ( !GetMofData(a1, L"BinaryPath", v39, v38) )
      TdhLoadManifestFromBinary(v39);
    v4 = *(_QWORD *)&EventTraceGuid.Data1;
    v5 = *(_QWORD *)EventTraceGuid.Data4;
  }
  v7 = FileIoGuid;
  if ( *(_QWORD *)&p_ProviderId->Data1 == FileIoGuid
    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xE36404F80000F484uLL
    || *(_QWORD *)&p_ProviderId->Data1 == DiskIoGuid
    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL )
  {
    goto LABEL_37;
  }
  v8 = ProcessGuid;
  if ( *(_QWORD *)&p_ProviderId->Data1 == ProcessGuid
    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL
    || a1->EventHeader.ThreadId != -1 && (a1->EventHeader.Flags & 0x10) == 0 )
  {
LABEL_38:
    v15 = &a1->EventHeader.ProviderId;
    if ( *(_QWORD *)&a1->EventHeader.ProviderId.Data1 == v4 && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == v5 )
    {
      LogHeaderCallback(a1);
      v8 = ProcessGuid;
      v7 = FileIoGuid;
    }
    if ( a1->EventHeader.EventDescriptor.Opcode == 3 )
    {
      if ( byte_140060AD0 )
      {
        v16 = ThreadGuid;
        if ( *(_QWORD *)&v15->Data1 == ThreadGuid
          && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL
          && a1->EventHeader.ThreadId )
        {
          v17 = dword_140062004;
          qword_140083440[dword_140062004] = a1->EventHeader.ThreadId;
          v18 = a1->UserDataLength < 8u;
          dword_140062004 = v17 + 1;
          a1->EventHeader.ThreadId = 0;
          if ( !v18 )
            *(_QWORD *)a1->UserData = 0;
          v16 = ThreadGuid;
          v8 = ProcessGuid;
          v7 = FileIoGuid;
        }
        v19 = dword_140062000++ == dword_140062008;
        if ( v19 )
          byte_140060AD0 = 0;
LABEL_60:
        if ( byte_1400820F0 && *(unsigned __int64 *)&SystemTimeAsFileTime < a1->EventHeader.TimeStamp.QuadPart )
          SystemTimeAsFileTime = (struct _FILETIME)a1->EventHeader.TimeStamp.QuadPart;
        v22 = *((_DWORD *)g_TraceContext + 1604);
        if ( (v22 & 0x20000480) != 0 )
        {
          DumpEvent(a1, v2);
        }
        else
        {
          if ( (v22 & 8) == 0 )
            goto LABEL_73;
          MofInfoHead = GetMofInfoHead(&a1->EventHeader.ProviderId);
          v24 = MofInfoHead;
          if ( !MofInfoHead )
            return;
          ++*((_DWORD *)MofInfoHead + 11);
          MofVersion = GetMofVersion(a1, MofInfoHead, 0);
          v26 = MofVersion;
          if ( !MofVersion )
            return;
          *((_WORD *)v24 + 3124) = a1->EventHeader.Flags;
          if ( (*((_DWORD *)g_TraceContext + 1604) & 0x4000000) != 0 )
            StoreEvent(a1, v24, MofVersion);
          MofCount = GetMofCount(a1, v24, v26);
          if ( !MofCount )
            return;
          ++*((_DWORD *)MofCount + 5);
        }
        v16 = ThreadGuid;
        v8 = ProcessGuid;
        v7 = FileIoGuid;
LABEL_73:
        if ( (*((_BYTE *)g_TraceContext + 6416) & 8) == 0 )
          return;
        if ( *(_QWORD *)&v15->Data1 == ImageLoadGuid
          && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x18F511C9A000E1ABLL )
        {
          ModuleLoadCallback(a1);
          return;
        }
        if ( !a1->EventHeader.ThreadId
          && (unsigned __int8)(a1->EventHeader.EventDescriptor.Opcode - 1) > 3u
          && (unsigned __int8)(a1->EventHeader.EventDescriptor.Opcode - 7) > 1u )
        {
          return;
        }
        GlobalThreadById = 0;
        if ( (*(_QWORD *)&v15->Data1 != v7 || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xE36404F80000F484uLL)
          && (*(_QWORD *)&v15->Data1 != TcpIpGuid || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xA298B94FC000E284uLL) )
        {
          v29 = UdpIpGuid;
          if ( *(_QWORD *)&v15->Data1 == UdpIpGuid
            && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x800FC8B7F02D05A0uLL )
          {
LABEL_88:
            if ( *(_QWORD *)&v15->Data1 == v8 && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL )
            {
              AdjustThreadTime(a1, GlobalThreadById, v8, 0x7CBAD74FC000DA9DLL);
              if ( ((a1->EventHeader.EventDescriptor.Opcode - 1) & 0xFD) != 0 )
              {
                if ( ((a1->EventHeader.EventDescriptor.Opcode - 2) & 0xFD) == 0 )
                  PsEndCallback(a1);
              }
              else
              {
                PsStartCallback(a1);
              }
              return;
            }
            if ( *(_QWORD *)&v15->Data1 == v16 && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL )
            {
              if ( a1->EventHeader.EventDescriptor.Opcode == 1 )
                AdjustThreadTime(a1, GlobalThreadById, v8, 0x7CBAD74FC000DA9DLL);
              if ( ((a1->EventHeader.EventDescriptor.Opcode - 1) & 0xFD) != 0 )
              {
                if ( ((a1->EventHeader.EventDescriptor.Opcode - 2) & 0xFD) == 0 )
                  ThEndCallback(a1);
              }
              else
              {
                ThStartCallback(a1);
              }
              return;
            }
            if ( *(_QWORD *)&v15->Data1 == ThreadPoolGuid
              && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x123A94AB0B979C9FLL )
            {
              if ( GlobalThreadById && *((_DWORD *)GlobalThreadById + 20) )
              {
                if ( *((_QWORD *)GlobalThreadById + 12) )
                  *((_QWORD *)GlobalThreadById + 12) = 0;
                Opcode = a1->EventHeader.EventDescriptor.Opcode;
                if ( Opcode == 52 )
                {
                  ThreadPoolStartCallback(a1);
                }
                else if ( Opcode == 53 )
                {
                  ProcessId = a1->EventHeader.ProcessId;
                  v37 = 0;
                  v38[0] = 4;
                  if ( !GetMofData(a1, L"TaskId", &v37, v38) && v37 == *((_DWORD *)GlobalThreadById + 138) )
                  {
                    v32 = *((_DWORD *)GlobalThreadById + 137);
                    *(_QWORD *)((char *)GlobalThreadById + 548) = 0;
                    v33 = FindOrAddService(v32, ProcessId);
                    if ( v33 )
                    {
                      *((_DWORD *)v33 + 18) += a1->EventHeader.KernelTime - *((_DWORD *)GlobalThreadById + 139);
                      *((_DWORD *)v33 + 19) += a1->EventHeader.UserTime - *((_DWORD *)GlobalThreadById + 140);
                    }
                  }
                }
              }
              return;
            }
            if ( !a1->EventHeader.ThreadId )
              return;
            if ( *(_QWORD *)&v15->Data1 != v7 || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xE36404F80000F484uLL )
            {
              v34 = TcpIpGuid;
              if ( *(_QWORD *)&v15->Data1 == TcpIpGuid
                && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xA298B94FC000E284uLL
                || *(_QWORD *)&v15->Data1 == v29 && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x800FC8B7F02D05A0uLL )
              {
LABEL_124:
                if ( *(_QWORD *)&v15->Data1 == DiskIoGuid
                  && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL )
                {
                  if ( (unsigned __int8)(a1->EventHeader.EventDescriptor.Opcode - 10) > 1u )
                    return;
                  if ( a1->EventHeader.EventDescriptor.Version >= 3u )
                  {
                    v37 = 0;
                    v38[0] = 4;
                    if ( GetMofData(a1, L"IssuingThreadId", &v37, v38) )
                      return;
                    FindGlobalThreadById(v37, a1);
                  }
                  if ( a1->EventHeader.EventDescriptor.Opcode == 10 )
                    IoReadCallback(a1);
                  else
                    IoWriteCallback(a1);
                }
                else if ( *(_QWORD *)&v15->Data1 == v7
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xE36404F80000F484uLL )
                {
                  if ( a1->EventHeader.EventDescriptor.Opcode <= 0x24u )
                  {
                    v35 = 0x1900000001LL;
                    if ( _bittest64(&v35, a1->EventHeader.EventDescriptor.Opcode) )
                      HotFileCallback(a1);
                  }
                }
                else if ( *(_QWORD *)&v15->Data1 == v34
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xA298B94FC000E284uLL
                       || *(_QWORD *)&v15->Data1 == v29
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x800FC8B7F02D05A0uLL )
                {
                  TcpIpCallback(a1);
                }
                else if ( *(_QWORD *)&v15->Data1 == PageFaultGuid
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x7CBAD74FC000DA9DLL )
                {
                  PageFaultCallback(a1);
                }
                else if ( *(_QWORD *)&v15->Data1 == *(_QWORD *)&EventTraceConfigGuid.Data1
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == *(_QWORD *)EventTraceConfigGuid.Data4 )
                {
                  v36 = a1->EventHeader.EventDescriptor.Opcode;
                  switch ( v36 )
                  {
                    case 0xCu:
                      LogDriveCallback(a1);
                      break;
                    case 0xAu:
                      CpuCallback(a1);
                      break;
                    case 0xFu:
                      ServicesCallback(a1);
                      break;
                  }
                }
                else if ( *(_QWORD *)&v15->Data1 == 0x415B1D183C419E3DLL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x4BDE3889559B1AA9LL
                       || *(_QWORD *)&v15->Data1 == 0x47A46398DD5EF90ALL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x5F79EFCDCE4D34ADLL
                       || *(_QWORD *)&v15->Data1 == 0x473EDE92D42CF7EFLL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x3A1163A61E626C8BLL
                       || *(_QWORD *)&v15->Data1 == 0x4BCF73EB00237F0DLL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x47585993661232A2LL
                       || *(_QWORD *)&v15->Data1 == 0x46090D2EE2E55403LL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xC01340A00DBE70A4uLL
                       || *(_QWORD *)&v15->Data1 == 0x42B03627E3642ACCLL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x73B03AA7B867283LL
                       || *(_QWORD *)&v15->Data1 == 0x4B73EDA02E94E6C7LL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x271CCEED29251090LL
                       || *(_QWORD *)&v15->Data1 == 0x4C373FC41FC299FALL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x70021D915BDE0D91LL
                       || *(_QWORD *)&v15->Data1 == 0x459479D306A01367LL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x79463C6021C7B38ELL
                       || *(_QWORD *)&v15->Data1 == 0x4EAE663C71BDA656LL
                       && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xCD0FFAF149A77A97uLL )
                {
                  if ( *(_QWORD *)&v15->Data1 == 0x415B1D183C419E3DLL
                    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x4BDE3889559B1AA9LL
                    || *(_QWORD *)&v15->Data1 == 0x47A46398DD5EF90ALL
                    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x5F79EFCDCE4D34ADLL )
                  {
                    byte_140061FFC = 1;
                  }
                  else
                  {
                    v3 = byte_140061FFC;
                  }
                  if ( v3 )
                    IISEventCallback(a1);
                }
                else if ( (*(_QWORD *)&v15->Data1 != 0x4B7771150ECF983BLL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x44EE38D19543A5LL)
                       && (*(_QWORD *)&v15->Data1 != 0x4B883E55D353DC2DLL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xA36283363C18ACA4uLL)
                       && (*(_QWORD *)&v15->Data1 != 0x4339B7D7ACADE3B2LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x241BDB4E1B816C95LL)
                       && (*(_QWORD *)&v15->Data1 != 0x4BEC7BBEE1AF7C2ALL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xDA771D4E06BAE0B5uLL)
                       && (*(_QWORD *)&v15->Data1 != 0x4CA0BF33AC1D69F1LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xDCE17338A1BC1393uLL)
                       && (*(_QWORD *)&v15->Data1 != 0x4080985BC33BBE8FLL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xE2B9061A5F00E681uLL)
                       && (*(_QWORD *)&v15->Data1 != 0x44F898CF08247298LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xEADD6E405A74F79EuLL)
                       && (*(_QWORD *)&v15->Data1 != 0x4AD2D4A7E44D0EC7LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x494A298CD44678CLL)
                       && (*(_QWORD *)&v15->Data1 != 0x47E9FE5935646E78LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x160864FCF5EE17A6LL)
                       && (*(_QWORD *)&v15->Data1 != 0x448D4472E60CEE96LL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xEC2082B170213CA1uLL)
                       && (*(_QWORD *)&v15->Data1 != 0x41E6BA4829347FFBLL
                        || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0xA53C545E9C46FDBFuLL) )
                {
                  if ( *(_QWORD *)&v15->Data1 == RegistryGuid
                    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xA121A34FC0005986uLL )
                  {
                    if ( GlobalThreadById )
                      ++*((_DWORD *)GlobalThreadById + 141);
                  }
                  else
                  {
                    if ( *(_QWORD *)&v15->Data1 == *(_QWORD *)&PrintJobGuid.Data1
                      && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintJobGuid.Data4
                      || *(_QWORD *)&v15->Data1 == 0x485A92A61D32B239LL
                      && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0x3E80FB5936DCD296LL
                      || *(_QWORD *)&v15->Data1 == *(_QWORD *)&PrintSpoolerGuid.Data1
                      && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == *(_QWORD *)PrintSpoolerGuid.Data4 )
                    {
                      PrintJobCallback(a1);
                    }
                    EventCallback(a1);
                  }
                }
                return;
              }
              AdjustThreadTime(a1, GlobalThreadById, v8, 0x7CBAD74FC000DA9DLL);
              v7 = FileIoGuid;
              v29 = UdpIpGuid;
            }
            v34 = TcpIpGuid;
            goto LABEL_124;
          }
          GlobalThreadById = FindGlobalThreadById(a1->EventHeader.ThreadId, a1);
          v8 = ProcessGuid;
          v16 = ThreadGuid;
          v7 = FileIoGuid;
        }
        v29 = UdpIpGuid;
        goto LABEL_88;
      }
    }
    else
    {
      v20 = dword_140062004;
      if ( dword_140062004 )
      {
        v21 = 0;
        do
        {
          if ( a1->EventHeader.ThreadId == qword_140083440[v21] )
          {
            v19 = a1->EventHeader.EventDescriptor.Opcode == 4;
            a1->EventHeader.ThreadId = 0;
            if ( v19 && a1->UserDataLength >= 8u )
              *(_QWORD *)a1->UserData = 0;
          }
          ++v21;
        }
        while ( v21 < v20 );
        v7 = FileIoGuid;
        v8 = ProcessGuid;
      }
    }
    v16 = ThreadGuid;
    goto LABEL_60;
  }
  v9 = *((_DWORD *)g_TraceContext + 1604);
  if ( (v9 & 0x20000480) != 0 )
  {
    DumpEvent(a1, v2);
LABEL_31:
    if ( (*((_BYTE *)g_TraceContext + 6416) & 8) != 0
      && *(_QWORD *)&p_ProviderId->Data1 == PerfinfoGuid
      && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == 0xBC2C10AA593FB087uLL
      && (unsigned __int8)(a1->EventHeader.EventDescriptor.Opcode - 67) <= 2u )
    {
      DpcIsrCallback(a1);
    }
    return;
  }
  if ( (v9 & 8) == 0 )
    goto LABEL_31;
  v10 = GetMofInfoHead(&a1->EventHeader.ProviderId);
  v11 = v10;
  if ( v10 )
  {
    ++*((_DWORD *)v10 + 11);
    v12 = GetMofVersion(a1, v10, 0);
    v13 = v12;
    if ( v12 )
    {
      *((_WORD *)v11 + 3124) = a1->EventHeader.Flags;
      if ( (*((_DWORD *)g_TraceContext + 1604) & 0x4000000) != 0 )
        StoreEvent(a1, v11, v12);
      v14 = GetMofCount(a1, v11, v13);
      if ( v14 )
      {
        ++*((_DWORD *)v14 + 5);
        goto LABEL_31;
      }
    }
  }
}

```

## disassembly

```asm
0x140003a30  test    rcx, rcx
0x140003a33  jz      locret_140004694
0x140003a39  push    rbp
0x140003a3a  push    rbx
0x140003a3b  push    rsi
0x140003a3c  push    rdi
0x140003a3d  push    r12
0x140003a3f  push    r13
0x140003a41  push    r14
0x140003a43  push    r15
0x140003a45  lea     rbp, [rsp-158h]
0x140003a4d  sub     rsp, 258h
0x140003a54  mov     rax, cs:__security_cookie
0x140003a5b  xor     rax, rsp
0x140003a5e  mov     [rbp+190h+var_50], rax
0x140003a65  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003a6c  xor     r13d, r13d
0x140003a6f  mov     rdi, rcx
0x140003a72  test    rax, rax
0x140003a75  jz      loc_140004672
0x140003a7b  mov     r12d, r13d
0x140003a7e  mov     [rsp+290h+var_26C], r13d
0x140003a83  mov     [rsp+290h+var_270], r13d
0x140003a88  cmp     [rax+2139h], r13b
0x140003a8f  jz      short loc_140003AC0
0x140003a91  test    byte ptr [rax+1910h], 8
0x140003a98  jz      short loc_140003AC0
0x140003a9a  lea     r8, [rsp+290h+var_26C]
0x140003a9f  lea     rdx, [rsp+290h+var_270]
0x140003aa4  call    GetEventCategory
0x140003aa9  mov     r12d, [rsp+290h+var_270]
0x140003aae  lea     r14d, [r13+1]
0x140003ab2  test    r12d, r12d
0x140003ab5  jz      short loc_140003AC6
0x140003ab7  add     cs:?TotalEventSkipped@@3KA, r14d; ulong TotalEventSkipped
0x140003abe  jmp     short loc_140003ACD
0x140003ac0  mov     r14d, 1
0x140003ac6  add     cs:?TotalEventCount@@3KA, r14d; ulong TotalEventCount
0x140003acd  cmp     cs:?XPorHigher@@3EA, r13b; uchar XPorHigher
0x140003ad4  mov     rax, [rdi+10h]
0x140003ad8  mov     rcx, qword ptr cs:EventTraceGuid.Data1
0x140003adf  mov     cs:qword_1400820B0, rax
0x140003ae6  mov     rax, qword ptr cs:EventTraceGuid.Data4
0x140003aed  jz      loc_140003CBD
0x140003af3  lea     rbx, [rdi+18h]
0x140003af7  cmp     [rbx], rcx
0x140003afa  jnz     short loc_140003B56
0x140003afc  cmp     [rbx+8], rax
0x140003b00  jnz     short loc_140003B56
0x140003b02  cmp     byte ptr [rdi+2Dh], 43h ; 'C'
0x140003b06  jnz     short loc_140003B56
0x140003b08  mov     esi, 208h
0x140003b0d  lea     rcx, [rsp+290h+var_260]; void *
0x140003b12  mov     r8d, esi; Size
0x140003b15  xor     edx, edx; Val
0x140003b17  call    memset_0
0x140003b1c  lea     r9, [rsp+290h+var_26C]; unsigned int *
0x140003b21  mov     [rsp+290h+var_26C], esi
0x140003b25  lea     r8, [rsp+290h+var_260]; void *
0x140003b2a  mov     rcx, rdi; Event
0x140003b2d  lea     rdx, aBinarypath; "BinaryPath"
0x140003b34  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140003b39  test    eax, eax
0x140003b3b  jnz     short loc_140003B48
0x140003b3d  lea     rcx, [rsp+290h+var_260]
0x140003b42  call    cs:__imp_TdhLoadManifestFromBinary
0x140003b48  mov     rcx, qword ptr cs:EventTraceGuid.Data1
0x140003b4f  mov     rax, qword ptr cs:EventTraceGuid.Data4
0x140003b56  mov     r15, cs:FileIoGuid
0x140003b5d  mov     r11, cs:qword_1400431C0
0x140003b64  cmp     [rbx], r15
0x140003b67  jnz     short loc_140003B73
0x140003b69  cmp     [rbx+8], r11
0x140003b6d  jz      loc_140003CCB
0x140003b73  mov     rdx, cs:DiskIoGuid
0x140003b7a  cmp     [rbx], rdx
0x140003b7d  jnz     short loc_140003B90
0x140003b7f  mov     rdx, cs:qword_140043230
0x140003b86  cmp     [rbx+8], rdx
0x140003b8a  jz      loc_140003CCB
0x140003b90  mov     r8, cs:ProcessGuid
0x140003b97  mov     rdx, cs:qword_140043210
0x140003b9e  cmp     [rbx], r8
0x140003ba1  jnz     short loc_140003BAD
0x140003ba3  cmp     [rbx+8], rdx
0x140003ba7  jz      loc_140003CD9
0x140003bad  cmp     dword ptr [rdi+8], 0FFFFFFFFh
0x140003bb1  jz      short loc_140003BBD
0x140003bb3  test    byte ptr [rdi+4], 10h
0x140003bb7  jz      loc_140003CD9
0x140003bbd  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003bc4  mov     ecx, [rax+1910h]
0x140003bca  test    ecx, 20000480h
0x140003bd0  jz      short loc_140003BE2
0x140003bd2  mov     edx, r12d
0x140003bd5  mov     rcx, rdi
0x140003bd8  call    ?DumpEvent@@YAXPEAU_EVENT_RECORD@@W4EVENT_CATEGORY@@@Z; DumpEvent(_EVENT_RECORD *,EVENT_CATEGORY)
0x140003bdd  jmp     loc_140003C65
0x140003be2  test    cl, 8
0x140003be5  jz      short loc_140003C65
0x140003be7  test    r12d, r12d
0x140003bea  jnz     short loc_140003C65
0x140003bec  mov     rcx, rbx; struct _GUID *
0x140003bef  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140003bf4  mov     rsi, rax
0x140003bf7  test    rax, rax
0x140003bfa  jz      loc_140004672
0x140003c00  add     [rax+2Ch], r14d
0x140003c04  xor     r8d, r8d; unsigned __int8
0x140003c07  mov     rdx, rax; struct _MOF_INFO *
0x140003c0a  mov     rcx, rdi; Event
0x140003c0d  call    ?GetMofVersion@@YAPEAU_MOF_VERSION@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@E@Z; GetMofVersion(_EVENT_RECORD *,_MOF_INFO *,uchar)
0x140003c12  mov     r15, rax
0x140003c15  test    rax, rax
0x140003c18  jz      loc_140004672
0x140003c1e  movzx   ecx, word ptr [rdi+4]
0x140003c22  mov     [rsi+1868h], cx
0x140003c29  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003c30  test    dword ptr [rcx+1910h], 4000000h
0x140003c3a  jz      short loc_140003C4A
0x140003c3c  mov     r8, rax; struct _MOF_VERSION *
0x140003c3f  mov     rdx, rsi; struct _MOF_INFO *
0x140003c42  mov     rcx, rdi; struct _EVENT_RECORD *
0x140003c45  call    ?StoreEvent@@YAXPEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; StoreEvent(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140003c4a  mov     r8, r15; struct _MOF_VERSION *
0x140003c4d  mov     rdx, rsi; struct _MOF_INFO *
0x140003c50  mov     rcx, rdi; struct _EVENT_RECORD *
0x140003c53  call    ?GetMofCount@@YAPEAU_MOF_COUNT@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; GetMofCount(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140003c58  test    rax, rax
0x140003c5b  jz      loc_140004672
0x140003c61  add     [rax+14h], r14d
0x140003c65  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003c6c  test    byte ptr [rax+1910h], 8
0x140003c73  jz      loc_140004672
0x140003c79  test    r12d, r12d
0x140003c7c  jnz     loc_140004672
0x140003c82  mov     rax, [rbx]
0x140003c85  cmp     rax, cs:PerfinfoGuid
0x140003c8c  jnz     loc_140004672
0x140003c92  mov     rax, [rbx+8]
0x140003c96  cmp     rax, cs:qword_1400431A0
0x140003c9d  jnz     loc_140004672
0x140003ca3  mov     al, [rdi+2Dh]
0x140003ca6  sub     al, 43h ; 'C'
0x140003ca8  cmp     al, 2
0x140003caa  ja      loc_140004672
0x140003cb0  mov     rcx, rdi; struct _EVENT_RECORD *
0x140003cb3  call    ?DpcIsrCallback@@YAXPEAU_EVENT_RECORD@@@Z; DpcIsrCallback(_EVENT_RECORD *)
0x140003cb8  jmp     loc_140004672
0x140003cbd  mov     r11, cs:qword_1400431C0
0x140003cc4  mov     r15, cs:FileIoGuid
0x140003ccb  mov     rdx, cs:qword_140043210
0x140003cd2  mov     r8, cs:ProcessGuid
0x140003cd9  lea     rbx, [rdi+18h]
0x140003cdd  cmp     [rbx], rcx
0x140003ce0  jnz     short loc_140003D0C
0x140003ce2  cmp     [rbx+8], rax
0x140003ce6  jnz     short loc_140003D0C
0x140003ce8  mov     rcx, rdi; Event
0x140003ceb  call    LogHeaderCallback
0x140003cf0  mov     r11, cs:qword_1400431C0
0x140003cf7  mov     rdx, cs:qword_140043210
0x140003cfe  mov     r8, cs:ProcessGuid
0x140003d05  mov     r15, cs:FileIoGuid
0x140003d0c  cmp     byte ptr [rdi+2Dh], 3
0x140003d10  jnz     loc_140003DBD
0x140003d16  cmp     cs:byte_140060AD0, r13b
0x140003d1d  jz      loc_140003E1B
0x140003d23  mov     r10, cs:ThreadGuid
0x140003d2a  mov     r9, cs:qword_1400431B0
0x140003d31  cmp     [rbx], r10
0x140003d34  jnz     short loc_140003D9B
0x140003d36  cmp     [rbx+8], r9
0x140003d3a  jnz     short loc_140003D9B
0x140003d3c  cmp     [rdi+8], r13d
0x140003d40  jz      short loc_140003D9B
0x140003d42  mov     edx, cs:dword_140062004
0x140003d48  lea     r8, qword_140083440
0x140003d4f  mov     ecx, [rdi+8]
0x140003d52  mov     [r8+rdx*8], rcx
0x140003d56  add     edx, r14d
0x140003d59  cmp     word ptr [rdi+56h], 8
0x140003d5e  mov     cs:dword_140062004, edx
0x140003d64  mov     [rdi+8], r13d
0x140003d68  jb      short loc_140003D71
0x140003d6a  mov     rax, [rdi+60h]
0x140003d6e  mov     [rax], r13
0x140003d71  mov     r10, cs:ThreadGuid
0x140003d78  mov     r9, cs:qword_1400431B0
0x140003d7f  mov     r8, cs:ProcessGuid
0x140003d86  mov     rdx, cs:qword_140043210
0x140003d8d  mov     r15, cs:FileIoGuid
0x140003d94  mov     r11, cs:qword_1400431C0
0x140003d9b  mov     eax, cs:dword_140062000
0x140003da1  mov     ecx, eax
0x140003da3  add     eax, r14d
0x140003da6  cmp     ecx, cs:dword_140062008
0x140003dac  mov     cs:dword_140062000, eax
0x140003db2  jnz     short loc_140003E29
0x140003db4  mov     cs:byte_140060AD0, r13b
0x140003dbb  jmp     short loc_140003E29
0x140003dbd  mov     r10d, cs:dword_140062004
0x140003dc4  test    r10d, r10d
0x140003dc7  jz      short loc_140003E1B
0x140003dc9  mov     r9d, r13d
0x140003dcc  lea     r8, qword_140083440
0x140003dd3  mov     eax, [rdi+8]
0x140003dd6  mov     ecx, r9d
0x140003dd9  cmp     rax, [r8+rcx*8]
0x140003ddd  jnz     short loc_140003DF7
0x140003ddf  cmp     byte ptr [rdi+2Dh], 4
0x140003de3  mov     [rdi+8], r13d
0x140003de7  jnz     short loc_140003DF7
0x140003de9  cmp     word ptr [rdi+56h], 8
0x140003dee  jb      short loc_140003DF7
0x140003df0  mov     rax, [rdi+60h]
0x140003df4  mov     [rax], r13
0x140003df7  add     r9d, r14d
0x140003dfa  cmp     r9d, r10d
0x140003dfd  jb      short loc_140003DD3
0x140003dff  mov     r11, cs:qword_1400431C0
0x140003e06  mov     r15, cs:FileIoGuid
0x140003e0d  mov     rdx, cs:qword_140043210
0x140003e14  mov     r8, cs:ProcessGuid
0x140003e1b  mov     r10, cs:ThreadGuid
0x140003e22  mov     r9, cs:qword_1400431B0
0x140003e29  cmp     cs:byte_1400820F0, r13b
0x140003e30  jz      short loc_140003E46
0x140003e32  mov     rax, [rdi+10h]
0x140003e36  cmp     qword ptr cs:SystemTimeAsFileTime.dwLowDateTime, rax
0x140003e3d  jnb     short loc_140003E46
0x140003e3f  mov     qword ptr cs:SystemTimeAsFileTime.dwLowDateTime, rax
0x140003e46  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003e4d  mov     ecx, [rax+1910h]
0x140003e53  test    ecx, 20000480h
0x140003e59  jz      short loc_140003E6B
0x140003e5b  mov     edx, r12d
0x140003e5e  mov     rcx, rdi
0x140003e61  call    ?DumpEvent@@YAXPEAU_EVENT_RECORD@@W4EVENT_CATEGORY@@@Z; DumpEvent(_EVENT_RECORD *,EVENT_CATEGORY)
0x140003e66  jmp     loc_140003EF6
0x140003e6b  test    cl, 8
0x140003e6e  jz      loc_140003F20
0x140003e74  test    r12d, r12d
0x140003e77  jnz     loc_140003F20
0x140003e7d  mov     rcx, rbx; struct _GUID *
0x140003e80  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140003e85  mov     rsi, rax
0x140003e88  test    rax, rax
0x140003e8b  jz      loc_140004672
0x140003e91  add     [rax+2Ch], r14d
0x140003e95  xor     r8d, r8d; unsigned __int8
0x140003e98  mov     rdx, rax; struct _MOF_INFO *
0x140003e9b  mov     rcx, rdi; Event
0x140003e9e  call    ?GetMofVersion@@YAPEAU_MOF_VERSION@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@E@Z; GetMofVersion(_EVENT_RECORD *,_MOF_INFO *,uchar)
0x140003ea3  mov     r15, rax
0x140003ea6  test    rax, rax
0x140003ea9  jz      loc_140004672
0x140003eaf  movzx   ecx, word ptr [rdi+4]
0x140003eb3  mov     [rsi+1868h], cx
0x140003eba  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003ec1  test    dword ptr [rcx+1910h], 4000000h
0x140003ecb  jz      short loc_140003EDB
0x140003ecd  mov     r8, rax; struct _MOF_VERSION *
0x140003ed0  mov     rdx, rsi; struct _MOF_INFO *
0x140003ed3  mov     rcx, rdi; struct _EVENT_RECORD *
0x140003ed6  call    ?StoreEvent@@YAXPEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; StoreEvent(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140003edb  mov     r8, r15; struct _MOF_VERSION *
0x140003ede  mov     rdx, rsi; struct _MOF_INFO *
0x140003ee1  mov     rcx, rdi; struct _EVENT_RECORD *
0x140003ee4  call    ?GetMofCount@@YAPEAU_MOF_COUNT@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; GetMofCount(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140003ee9  test    rax, rax
0x140003eec  jz      loc_140004672
0x140003ef2  add     [rax+14h], r14d
0x140003ef6  mov     r10, cs:ThreadGuid
0x140003efd  mov     r9, cs:qword_1400431B0
0x140003f04  mov     r8, cs:ProcessGuid
0x140003f0b  mov     rdx, cs:qword_140043210
0x140003f12  mov     r15, cs:FileIoGuid
0x140003f19  mov     r11, cs:qword_1400431C0
0x140003f20  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140003f27  test    byte ptr [rax+1910h], 8
0x140003f2e  jz      loc_140004672
0x140003f34  mov     rax, [rbx]
0x140003f37  cmp     rax, cs:ImageLoadGuid
0x140003f3e  jnz     short loc_140003F5A
0x140003f40  mov     rax, [rbx+8]
0x140003f44  cmp     rax, cs:qword_1400431F0
0x140003f4b  jnz     short loc_140003F5A
0x140003f4d  mov     rcx, rdi; Event
0x140003f50  call    ModuleLoadCallback
0x140003f55  jmp     loc_140004672
0x140003f5a  cmp     [rdi+8], r13d
0x140003f5e  jnz     short loc_140003F78
0x140003f60  mov     cl, [rdi+2Dh]
0x140003f63  mov     al, cl
0x140003f65  sub     al, r14b
0x140003f68  cmp     al, 3
0x140003f6a  jbe     short loc_140003F78
0x140003f6c  sub     cl, 7
0x140003f6f  cmp     cl, r14b
  ... truncated ...
```
