# SmpInit

- ea: `0x1400146ac`
- end: `0x140014c66`
- name: `SmpInit`
- size: `1466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140005f64`

## callees

- `0x1400010ec`
- `0x14000b110`
- `0x14000b930`
- `0x14000c638`
- `0x14000d4c0`
- `0x14000e080`
- `0x14000e620`
- `0x1400146ac`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140014bc5`
- `ntdll!NtClose` at `0x140014bc5`
- `ntdll!NtQuerySystemInformation` at `0x1400147ae`
- `ntdll!NtQuerySystemInformation` at `0x140014806`
- `ntdll!NtQuerySystemInformation` at `0x1400148a0`
- `ntdll!NtQuerySystemInformation` at `0x14001491d`
- `ntdll!NtQuerySystemInformation` at `0x140014a8d`
- `ntdll!NtQuerySystemInformation` at `0x1400147ae`
- `ntdll!NtQuerySystemInformation` at `0x1400147ba`
- `ntdll!NtQuerySystemInformation` at `0x140014806`
- `ntdll!NtQuerySystemInformation` at `0x1400148a0`
- `ntdll!NtQuerySystemInformation` at `0x14001491d`
- `ntdll!NtQuerySystemInformation` at `0x140014941`
- `ntdll!NtQuerySystemInformation` at `0x140014a8d`
- `ntdll!NtQuerySystemInformation` at `0x140014a99`
- `ntdll!NtQuerySystemInformation` at `0x140014bfd`
- `ntdll!NtQuerySystemInformation` at `0x140014c18`
- `ntdll!RtlAllocateHeap` at `0x1400148d3`
- `ntdll!RtlAllocateHeap` at `0x1400148d3`
- `ntdll!RtlAllocateHeap` at `0x1400148e1`
- `ntdll!RtlFreeHeap` at `0x14001493b`
- `ntdll!RtlFreeHeap` at `0x140014980`
- `ntdll!RtlFreeHeap` at `0x14001493b`
- `ntdll!RtlFreeHeap` at `0x140014980`
- `ntdll!RtlCreateTagHeap` at `0x140014792`
- `ntdll!RtlCreateTagHeap` at `0x140014792`
- `ntdll!NtSetInformationProcess` at `0x14001484c`
- `ntdll!NtSetInformationProcess` at `0x14001484c`
- `ntdll!NtAlpcCreatePort` at `0x140014a29`
- `ntdll!NtAlpcCreatePort` at `0x140014a29`
- `ntdll!NtAlpcCreatePort` at `0x140014a35`
- `ntdll!RtlInitializeBitMap` at `0x140014ae0`
- `ntdll!RtlInitializeBitMap` at `0x140014ae0`
- `ntdll!RtlClearAllBits` at `0x140014ae9`
- `ntdll!RtlClearAllBits` at `0x140014ae9`
- `ntdll!RtlSetBits` at `0x140014b13`
- `ntdll!RtlSetBits` at `0x140014b13`
- `ntdll!NtOpenEvent` at `0x140014b60`
- `ntdll!NtOpenEvent` at `0x140014b60`

## string_xrefs

- `0x140014734`: `\Device\VolumesSafeForWriteAccess`

## pseudocode

```c
__int64 SmpInit()
{
  NTSTATUS v0; // eax
  int SecurityDescriptors; // edi
  __int64 v2; // rdx
  NTSTATUS v4; // eax
  __int64 (*v5)(void); // rax
  NTSTATUS v6; // eax
  _BYTE *Heap; // rax
  _BYTE *v8; // rdi
  NTSTATUS v9; // esi
  void *v10; // rcx
  int v11; // eax
  NTSTATUS v12; // eax
  unsigned int v13; // ecx
  ULONG i; // edi
  NTSTATUS v15; // eax
  int v16; // esi
  ULONG ReturnLength; // [rsp+20h] [rbp-E0h] BYREF
  int ProcessInformation; // [rsp+24h] [rbp-DCh] BYREF
  void *EventHandle; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v21; // [rsp+38h] [rbp-C8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD SystemInformation[260]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v25[4]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v26; // [rsp+4A0h] [rbp+3A0h]
  __int64 v27; // [rsp+4B0h] [rbp+3B0h]

  memset(&ObjectAttributes, 0, 44);
  memset_0(v25, 0, 0x48u);
  ProcessInformation = 0;
  memset_0(SystemInformation, 0, 0x408u);
  ReturnLength = 0;
  v23[1] = L"\\SmApiPort";
  EventHandle = 0;
  v21 = L"\\Device\\VolumesSafeForWriteAccess";
  v23[0] = 1441812;
  v20 = 4456514;
  SmpInitSaveGlobals = (__int64)&SmpInitLastCall;
  SmBaseTag = RtlCreateTagHeap(
                *(HANDLE *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                0,
                (PWSTR)L"SMSS!",
                (PWSTR)L"INIT");
  v0 = NtQuerySystemInformation(SystemBasicInformation, &SmpSystemInfo, 0x40u, 0);
  SecurityDescriptors = v0;
  if ( v0 < 0 )
  {
    v2 = 1702;
    SmpInitProgressByLine = 1700;
    SmpInitReturnStatus = v0;
    SmpInitLastCall = (__int64)NtQuerySystemInformation;
LABEL_3:
    SmpLogFailure("SmpInit", v2, (unsigned int)SecurityDescriptors);
    return (unsigned int)SecurityDescriptors;
  }
  v4 = NtQuerySystemInformation(SystemSessionPoolTagInformation|0x80, &SmpSystemWriteConstraintInfo, 8u, 0);
  if ( v4 < 0 )
  {
    SmpLogFailure("SmpInit", 1718, (unsigned int)v4);
    SmpSystemWriteConstraintInfo = 0;
  }
  ProcessInformation = 1;
  NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDefaultHardErrorMode, &ProcessInformation, 4u);
  SecurityDescriptors = SmpInitializeKnownSubSystems();
  if ( SecurityDescriptors < 0 )
  {
    SmpInitProgressByLine = 1739;
    v5 = SmpInitializeKnownSubSystems;
    v2 = 1740;
LABEL_9:
    SmpInitReturnStatus = SecurityDescriptors;
    SmpInitLastCall = (__int64)v5;
    goto LABEL_3;
  }
  SmpManufacturingMode = 0;
  v6 = NtQuerySystemInformation(SystemSummaryMemoryInformation|0x80, 0, 0, &ReturnLength);
  SecurityDescriptors = v6;
  if ( v6 >= 0 )
  {
    SmpInitProgressByLine = 1797;
    SmpInitReturnStatus = v6;
    SmpInitLastCall = (__int64)NtQuerySystemInformation;
    SmpLogFailure("SmpInit", 1798, (unsigned int)v6);
    return 3221225473LL;
  }
  else
  {
    if ( v6 != -1073741820 )
    {
      v5 = (__int64 (*)(void))NtQuerySystemInformation;
      v2 = 1791;
      SmpInitProgressByLine = 1789;
      goto LABEL_9;
    }
    Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, ReturnLength);
    v8 = Heap;
    if ( !Heap )
    {
      SecurityDescriptors = -1073741670;
      SmpInitProgressByLine = 1763;
      v2 = 1764;
      SmpInitReturnStatus = -1073741670;
      SmpInitLastCall = (__int64)RtlAllocateHeap;
      goto LABEL_3;
    }
    v9 = NtQuerySystemInformation(SystemSummaryMemoryInformation|0x80, Heap, ReturnLength, &ReturnLength);
    v10 = *(void **)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL);
    if ( v9 >= 0 )
    {
      SmpManufacturingMode = *v8 & 1;
      RtlFreeHeap(v10, 0, v8);
      SecurityDescriptors = SmpCreateSecurityDescriptors();
      if ( SecurityDescriptors >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v23;
        ObjectAttributes.Attributes = 0;
        ObjectAttributes.SecurityDescriptor = SmpApiPortSecurityDescriptor;
        ObjectAttributes.SecurityQualityOfService = 0;
        memset_0(v25, 0, 0x48u);
        v25[0] = 0x20000;
        v26 = 328;
        v27 = 1000000;
        v11 = NtAlpcCreatePort(&SmpApiConnectionPort, &ObjectAttributes, v25);
        SecurityDescriptors = v11;
        if ( v11 < 0 )
        {
          v2 = 1834;
          SmpInitProgressByLine = 1833;
          SmpInitReturnStatus = v11;
          SmpInitLastCall = (__int64)NtAlpcCreatePort;
          goto LABEL_3;
        }
        SmpUniqueProcessId = (unsigned int)KeGetPcr()->Unused[0];
        SmpActiveProcessorCount = MEMORY[0x7FFE03C0];
        v12 = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, 0);
        SecurityDescriptors = v12;
        if ( v12 < 0 )
        {
          v2 = 1853;
          SmpInitProgressByLine = 1852;
          SmpInitReturnStatus = v12;
          SmpInitLastCall = (__int64)NtQuerySystemInformation;
          goto LABEL_3;
        }
        SmpMaximumNodeCount = SystemInformation[0] + 1;
        RtlInitializeBitMap(&SmpNodeBitmap, &SmpNodeBitmapBuffer, SystemInformation[0] + 1);
        RtlClearAllBits(&SmpNodeBitmap);
        v13 = SmpMaximumNodeCount;
        for ( i = 0; i < v13; ++i )
        {
          if ( *(_QWORD *)&SystemInformation[4 * i + 2] )
          {
            RtlSetBits(&SmpNodeBitmap, i, 1u);
            v13 = SmpMaximumNodeCount;
          }
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v15 = NtOpenEvent(&EventHandle, 0x1F0003u, &ObjectAttributes);
        v16 = v15;
        if ( v15 < 0 )
        {
          SmpLogFailureString("SmpInit", 1895, v21, (unsigned int)v15);
          EventHandle = 0;
        }
        SecurityDescriptors = SmpInitializePendingRename();
        if ( SecurityDescriptors >= 0 )
        {
          SecurityDescriptors = SmpLoadDataFromRegistry(EventHandle);
          if ( v16 >= 0 )
            NtClose(EventHandle);
          if ( SecurityDescriptors < 0 )
            return (unsigned int)SecurityDescriptors;
          SecurityDescriptors = InitializeWow64OnBoot();
          if ( SecurityDescriptors >= 0 )
            return (unsigned int)SecurityDescriptors;
          SmpInitProgressByLine = 1934;
          v5 = InitializeWow64OnBoot;
          v2 = 1936;
        }
        else
        {
          SmpInitProgressByLine = 1907;
          v5 = SmpInitializePendingRename;
          v2 = 1909;
        }
      }
      else
      {
        SmpInitProgressByLine = 1809;
        v5 = SmpCreateSecurityDescriptors;
        v2 = 1810;
      }
      goto LABEL_9;
    }
    RtlFreeHeap(v10, 0, v8);
    SmpInitProgressByLine = 1776;
    SmpInitReturnStatus = v9;
    SmpInitLastCall = (__int64)NtQuerySystemInformation;
    SmpLogFailure("SmpInit", 1778, (unsigned int)v9);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1400146ac  push    rbp
0x1400146ae  push    rbx
0x1400146af  push    rsi
0x1400146b0  push    rdi
0x1400146b1  lea     rbp, [rsp-3F8h]
0x1400146b9  sub     rsp, 4F8h
0x1400146c0  mov     rax, cs:__security_cookie
0x1400146c7  xor     rax, rsp
0x1400146ca  mov     [rbp+410h+var_30], rax
0x1400146d1  xorps   xmm0, xmm0
0x1400146d4  lea     rcx, [rbp+410h+var_80]; void *
0x1400146db  xor     eax, eax
0x1400146dd  xor     edx, edx; Val
0x1400146df  movups  xmmword ptr [rsp+510h+ObjectAttributes.ObjectName], xmm0
0x1400146e4  movups  xmmword ptr [rsp+510h+ObjectAttributes.Length], xmm0
0x1400146e9  lea     r8d, [rax+48h]; Size
0x1400146ed  movups  xmmword ptr [rsp+510h+ObjectAttributes+1Ch], xmm0
0x1400146f2  call    memset_0
0x1400146f7  xor     edx, edx; Val
0x1400146f9  mov     [rsp+510h+ProcessInformation], 0
0x140014701  mov     r8d, 408h; Size
0x140014707  lea     rcx, [rbp+410h+SystemInformation]; void *
0x14001470b  call    memset_0
0x140014710  mov     [rsp+510h+ReturnLength], 0
0x140014718  lea     rax, aSmapiport; "\\SmApiPort"
0x14001471f  mov     [rsp+510h+var_498], rax
0x140014724  lea     r9, aInit; "INIT"
0x14001472b  mov     [rsp+510h+EventHandle], 0
0x140014734  lea     rax, aDeviceVolumess; "\\Device\\VolumesSafeForWriteAccess"
0x14001473b  mov     [rsp+510h+var_4D8], rax
0x140014740  lea     r8, aSmss; "SMSS!"
0x140014747  mov     [rsp+510h+var_4A0], 160014h
0x140014750  lea     rax, SmpInitProgressByLine
0x140014757  mov     [rsp+510h+var_4E0], 440042h
0x140014760  xor     edx, edx; Flags
0x140014762  mov     cs:SmpInitSaveGlobals, rax
0x140014769  lea     rax, SmpInitReturnStatus
0x140014770  mov     cs:SmpInitSaveGlobals, rax
0x140014777  lea     rax, SmpInitLastCall
0x14001477e  mov     cs:SmpInitSaveGlobals, rax
0x140014785  mov     rcx, gs:60h
0x14001478e  mov     rcx, [rcx+30h]; HeapHandle
0x140014792  call    cs:__imp_RtlCreateTagHeap
0x140014798  xor     r9d, r9d; ReturnLength
0x14001479b  lea     rdx, SmpSystemInfo; SystemInformation
0x1400147a2  xor     ecx, ecx; SystemInformationClass
0x1400147a4  mov     cs:SmBaseTag, eax
0x1400147aa  lea     r8d, [r9+40h]; SystemInformationLength
0x1400147ae  call    cs:__imp_NtQuerySystemInformation
0x1400147b4  mov     edi, eax
0x1400147b6  test    eax, eax
0x1400147b8  jns     short loc_1400147F3
0x1400147ba  mov     rcx, cs:__imp_NtQuerySystemInformation
0x1400147c1  mov     edx, 6A6h
0x1400147c6  mov     cs:SmpInitProgressByLine, 6A4h
0x1400147d0  mov     cs:SmpInitReturnStatus, eax
0x1400147d6  mov     cs:SmpInitLastCall, rcx
0x1400147dd  lea     rcx, aSmpinit; "SmpInit"
0x1400147e4  mov     r8d, edi
0x1400147e7  call    SmpLogFailure
0x1400147ec  mov     eax, edi
0x1400147ee  jmp     loc_140014C4B
0x1400147f3  xor     r9d, r9d; ReturnLength
0x1400147f6  lea     rdx, SmpSystemWriteConstraintInfo; SystemInformation
0x1400147fd  mov     ecx, 0C3h; SystemInformationClass
0x140014802  lea     r8d, [r9+8]; SystemInformationLength
0x140014806  call    cs:__imp_NtQuerySystemInformation
0x14001480c  lea     rbx, aSmpinit; "SmpInit"
0x140014813  test    eax, eax
0x140014815  jns     short loc_140014831
0x140014817  mov     r8d, eax
0x14001481a  mov     edx, 6B6h
0x14001481f  mov     rcx, rbx
0x140014822  call    SmpLogFailure
0x140014827  mov     cs:SmpSystemWriteConstraintInfo, 0
0x140014831  mov     r9d, 4; ProcessInformationLength
0x140014837  mov     [rsp+510h+ProcessInformation], 1
0x14001483f  lea     r8, [rsp+510h+ProcessInformation]; ProcessInformation
0x140014844  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140014848  lea     edx, [r9+8]; ProcessInformationClass
0x14001484c  call    cs:__imp_NtSetInformationProcess
0x140014852  call    SmpInitializeKnownSubSystems
0x140014857  mov     edi, eax
0x140014859  test    eax, eax
0x14001485b  jns     short loc_140014888
0x14001485d  mov     cs:SmpInitProgressByLine, 6CBh
0x140014867  lea     rax, SmpInitializeKnownSubSystems
0x14001486e  mov     edx, 6CCh
0x140014873  mov     cs:SmpInitReturnStatus, edi
0x140014879  mov     cs:SmpInitLastCall, rax
0x140014880  mov     rcx, rbx
0x140014883  jmp     loc_1400147E4
0x140014888  mov     esi, 9Dh
0x14001488d  mov     cs:SmpManufacturingMode, 0
0x140014894  mov     ecx, esi; SystemInformationClass
0x140014896  lea     r9, [rsp+510h+ReturnLength]; ReturnLength
0x14001489b  xor     r8d, r8d; SystemInformationLength
0x14001489e  xor     edx, edx; SystemInformation
0x1400148a0  call    cs:__imp_NtQuerySystemInformation
0x1400148a6  mov     edi, eax
0x1400148a8  test    eax, eax
0x1400148aa  jns     loc_140014C18
0x1400148b0  cmp     eax, 0C0000004h
0x1400148b5  jnz     loc_140014BFD
0x1400148bb  mov     rcx, gs:60h
0x1400148c4  mov     r8d, [rsp+510h+ReturnLength]; Size
0x1400148c9  mov     edx, cs:SmBaseTag; Flags
0x1400148cf  mov     rcx, [rcx+30h]; HeapHandle
0x1400148d3  call    cs:__imp_RtlAllocateHeap
0x1400148d9  mov     rdi, rax
0x1400148dc  test    rax, rax
0x1400148df  jnz     short loc_14001490E
0x1400148e1  mov     rcx, cs:__imp_RtlAllocateHeap
0x1400148e8  mov     edi, 0C000009Ah
0x1400148ed  mov     cs:SmpInitProgressByLine, 6E3h
0x1400148f7  mov     edx, 6E4h
0x1400148fc  mov     cs:SmpInitReturnStatus, edi
0x140014902  mov     cs:SmpInitLastCall, rcx
0x140014909  jmp     loc_140014880
0x14001490e  mov     r8d, [rsp+510h+ReturnLength]; SystemInformationLength
0x140014913  lea     r9, [rsp+510h+ReturnLength]; ReturnLength
0x140014918  mov     rdx, rdi; SystemInformation
0x14001491b  mov     ecx, esi; SystemInformationClass
0x14001491d  call    cs:__imp_NtQuerySystemInformation
0x140014923  mov     rcx, gs:60h
0x14001492c  xor     edx, edx; Flags
0x14001492e  mov     esi, eax
0x140014930  mov     r8, rdi; BaseAddress
0x140014933  mov     rcx, [rcx+30h]; HeapHandle
0x140014937  test    eax, eax
0x140014939  jns     short loc_140014976
0x14001493b  call    cs:__imp_RtlFreeHeap
0x140014941  mov     rcx, cs:__imp_NtQuerySystemInformation
0x140014948  mov     r8d, esi
0x14001494b  mov     cs:SmpInitProgressByLine, 6F0h
0x140014955  mov     edx, 6F2h
0x14001495a  mov     cs:SmpInitReturnStatus, esi
0x140014960  mov     cs:SmpInitLastCall, rcx
0x140014967  mov     rcx, rbx
0x14001496a  call    SmpLogFailure
0x14001496f  mov     eax, esi
0x140014971  jmp     loc_140014C4B
0x140014976  mov     al, [rdi]
0x140014978  and     al, 1
0x14001497a  mov     cs:SmpManufacturingMode, al
0x140014980  call    cs:__imp_RtlFreeHeap
0x140014986  call    SmpCreateSecurityDescriptors
0x14001498b  mov     edi, eax
0x14001498d  test    eax, eax
0x14001498f  jns     short loc_1400149AC
0x140014991  mov     cs:SmpInitProgressByLine, 711h
0x14001499b  lea     rax, SmpCreateSecurityDescriptors
0x1400149a2  mov     edx, 712h
0x1400149a7  jmp     loc_140014873
0x1400149ac  xor     edx, edx; Val
0x1400149ae  mov     [rsp+510h+ObjectAttributes.Length], 30h ; '0'
0x1400149b6  lea     rax, [rsp+510h+var_4A0]
0x1400149bb  mov     [rsp+510h+ObjectAttributes.RootDirectory], 0
0x1400149c4  mov     [rsp+510h+ObjectAttributes.ObjectName], rax
0x1400149c9  lea     rcx, [rbp+410h+var_80]; void *
0x1400149d0  mov     rax, cs:SmpApiPortSecurityDescriptor
0x1400149d7  lea     r8d, [rdx+48h]; Size
0x1400149db  mov     [rsp+510h+ObjectAttributes.Attributes], 0
0x1400149e3  mov     [rsp+510h+ObjectAttributes.SecurityDescriptor], rax
0x1400149e8  mov     [rsp+510h+ObjectAttributes.SecurityQualityOfService], 0
0x1400149f1  call    memset_0
0x1400149f6  lea     r8, [rbp+410h+var_80]
0x1400149fd  mov     [rbp+410h+var_80], 20000h
0x140014a07  lea     rdx, [rsp+510h+ObjectAttributes]
0x140014a0c  mov     [rbp+410h+var_70], 148h
0x140014a17  lea     rcx, SmpApiConnectionPort
0x140014a1e  mov     [rbp+410h+var_60], 0F4240h
0x140014a29  call    cs:__imp_NtAlpcCreatePort
0x140014a2f  mov     edi, eax
0x140014a31  test    eax, eax
0x140014a33  jns     short loc_140014A5D
0x140014a35  mov     rcx, cs:__imp_NtAlpcCreatePort
0x140014a3c  mov     edx, 72Ah
0x140014a41  mov     cs:SmpInitProgressByLine, 729h
0x140014a4b  mov     cs:SmpInitReturnStatus, eax
0x140014a51  mov     cs:SmpInitLastCall, rcx
0x140014a58  jmp     loc_140014880
0x140014a5d  mov     rax, gs:40h
0x140014a66  lea     rdx, [rbp+410h+SystemInformation]; SystemInformation
0x140014a6a  mov     ecx, eax
0x140014a6c  xor     r9d, r9d; ReturnLength
0x140014a6f  mov     eax, ds:7FFE03C0h
0x140014a76  mov     r8d, 408h; SystemInformationLength
0x140014a7c  mov     cs:SmpUniqueProcessId, rcx
0x140014a83  mov     cs:SmpActiveProcessorCount, eax
0x140014a89  lea     ecx, [r9+37h]; SystemInformationClass
0x140014a8d  call    cs:__imp_NtQuerySystemInformation
0x140014a93  mov     edi, eax
0x140014a95  test    eax, eax
0x140014a97  jns     short loc_140014AC1
0x140014a99  mov     rcx, cs:__imp_NtQuerySystemInformation
0x140014aa0  mov     edx, 73Dh
0x140014aa5  mov     cs:SmpInitProgressByLine, 73Ch
0x140014aaf  mov     cs:SmpInitReturnStatus, eax
0x140014ab5  mov     cs:SmpInitLastCall, rcx
0x140014abc  jmp     loc_140014880
0x140014ac1  mov     r8d, [rbp+410h+SystemInformation]
0x140014ac5  lea     rsi, SmpNodeBitmap
0x140014acc  inc     r8d; SizeOfBitMap
0x140014acf  lea     rdx, SmpNodeBitmapBuffer; BitMapBuffer
0x140014ad6  mov     rcx, rsi; BitMapHeader
0x140014ad9  mov     cs:SmpMaximumNodeCount, r8d
0x140014ae0  call    cs:__imp_RtlInitializeBitMap
0x140014ae6  mov     rcx, rsi; BitMapHeader
0x140014ae9  call    cs:__imp_RtlClearAllBits
0x140014aef  mov     ecx, cs:SmpMaximumNodeCount
0x140014af5  xor     edi, edi
0x140014af7  test    ecx, ecx
0x140014af9  jz      short loc_140014B25
0x140014afb  mov     eax, edi
0x140014afd  add     rax, rax
0x140014b00  cmp     [rbp+rax*8+410h+var_488], 0
0x140014b06  jz      short loc_140014B1F
0x140014b08  mov     r8d, 1; NumberToSet
0x140014b0e  mov     edx, edi; StartingIndex
0x140014b10  mov     rcx, rsi; BitMapHeader
0x140014b13  call    cs:__imp_RtlSetBits
0x140014b19  mov     ecx, cs:SmpMaximumNodeCount
0x140014b1f  inc     edi
0x140014b21  cmp     edi, ecx
0x140014b23  jb      short loc_140014AFB
0x140014b25  lea     rax, [rsp+510h+var_4E0]
0x140014b2a  mov     [rsp+510h+ObjectAttributes.Length], 30h ; '0'
0x140014b32  xorps   xmm0, xmm0
0x140014b35  mov     [rsp+510h+ObjectAttributes.ObjectName], rax
0x140014b3a  lea     r8, [rsp+510h+ObjectAttributes]; ObjectAttributes
0x140014b3f  mov     [rsp+510h+ObjectAttributes.RootDirectory], 0
0x140014b48  mov     edx, 1F0003h; DesiredAccess
0x140014b4d  mov     [rsp+510h+ObjectAttributes.Attributes], 40h ; '@'
0x140014b55  lea     rcx, [rsp+510h+EventHandle]; EventHandle
0x140014b5a  movdqu  xmmword ptr [rsp+510h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014b60  call    cs:__imp_NtOpenEvent
0x140014b66  mov     esi, eax
0x140014b68  test    eax, eax
0x140014b6a  jns     short loc_140014B8A
0x140014b6c  mov     r8, [rsp+510h+var_4D8]
0x140014b71  mov     r9d, eax
0x140014b74  mov     edx, 767h
0x140014b79  mov     rcx, rbx
0x140014b7c  call    SmpLogFailureString
0x140014b81  mov     [rsp+510h+EventHandle], 0
0x140014b8a  call    SmpInitializePendingRename
0x140014b8f  mov     edi, eax
0x140014b91  test    eax, eax
0x140014b93  jns     short loc_140014BB0
0x140014b95  mov     cs:SmpInitProgressByLine, 773h
0x140014b9f  lea     rax, SmpInitializePendingRename
0x140014ba6  mov     edx, 775h
0x140014bab  jmp     loc_140014873
0x140014bb0  mov     rcx, [rsp+510h+EventHandle]; EventHandle
0x140014bb5  call    SmpLoadDataFromRegistry
0x140014bba  mov     edi, eax
0x140014bbc  test    esi, esi
0x140014bbe  js      short loc_140014BCB
0x140014bc0  mov     rcx, [rsp+510h+EventHandle]; Handle
0x140014bc5  call    cs:__imp_NtClose
0x140014bcb  test    edi, edi
0x140014bcd  js      loc_1400147EC
0x140014bd3  call    InitializeWow64OnBoot
0x140014bd8  mov     edi, eax
0x140014bda  test    eax, eax
0x140014bdc  jns     loc_1400147EC
0x140014be2  mov     cs:SmpInitProgressByLine, 78Eh
0x140014bec  lea     rax, InitializeWow64OnBoot
0x140014bf3  mov     edx, 790h
0x140014bf8  jmp     loc_140014873
0x140014bfd  mov     rax, cs:__imp_NtQuerySystemInformation
0x140014c04  mov     edx, 6FFh
0x140014c09  mov     cs:SmpInitProgressByLine, 6FDh
0x140014c13  jmp     loc_140014873
0x140014c18  mov     rax, cs:__imp_NtQuerySystemInformation
0x140014c1f  mov     r8d, edi
0x140014c22  mov     cs:SmpInitProgressByLine, 705h
0x140014c2c  mov     edx, 706h
0x140014c31  mov     cs:SmpInitReturnStatus, edi
0x140014c37  mov     rcx, rbx
0x140014c3a  mov     cs:SmpInitLastCall, rax
0x140014c41  call    SmpLogFailure
0x140014c46  mov     eax, 0C0000001h
0x140014c4b  mov     rcx, [rbp+410h+var_30]
0x140014c52  xor     rcx, rsp; StackCookie
0x140014c55  call    __security_check_cookie
0x140014c5a  add     rsp, 4F8h
0x140014c61  pop     rdi
0x140014c62  pop     rsi
0x140014c63  pop     rbx
0x140014c64  pop     rbp
0x140014c65  retn
```
