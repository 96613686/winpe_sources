# WcSetupVolumeInformationHandler

- ea: `0x140002520`
- end: `0x140002a82`
- name: `WcSetupVolumeInformationHandler`
- size: `1378`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140031e90`

## callees

- `0x1400020c4`
- `0x140002520`
- `0x140004198`
- `0x14002ca2c`
- `0x14002ee60`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002899`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002899`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400026c6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400026c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002579`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002579`
- `ntoskrnl!ObfDereferenceObject` at `0x140002a28`
- `ntoskrnl!ObfDereferenceObject` at `0x140002a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a13`
- `FLTMGR!FltCreateFileEx` at `0x140002953`
- `FLTMGR!FltCreateFileEx` at `0x140002953`
- `FLTMGR!FltGetVolumeFromName` at `0x1400027bf`
- `FLTMGR!FltGetVolumeFromName` at `0x1400027bf`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140002773`
- `FLTMGR!FltCreateSystemVolumeInformationFolder` at `0x140002773`
- `FLTMGR!FltWriteFile` at `0x1400029c2`
- `FLTMGR!FltWriteFile` at `0x1400029c2`
- `FLTMGR!FltGetVolumeName` at `0x140002806`
- `FLTMGR!FltGetVolumeName` at `0x140002878`
- `FLTMGR!FltGetVolumeName` at `0x140002806`
- `FLTMGR!FltGetVolumeName` at `0x140002878`
- `FLTMGR!FltClose` at `0x140002a3d`
- `FLTMGR!FltClose` at `0x140002a3d`
- `FLTMGR!FltObjectDereference` at `0x140002a52`
- `FLTMGR!FltObjectDereference` at `0x140002a67`
- `FLTMGR!FltObjectDereference` at `0x140002a52`
- `FLTMGR!FltObjectDereference` at `0x140002a67`

## pseudocode

```c
__int64 __fastcall WcSetupVolumeInformationHandler(__int64 a1, unsigned int a2)
{
  unsigned int v4; // edx
  NTSTATUS InstanceFromVolumeName; // ebx
  int v6; // r9d
  int v7; // ecx
  int v8; // edx
  unsigned int v9; // eax
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+90h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING String1; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING VolumeName; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK v19; // [rsp+F0h] [rbp-10h] BYREF
  PFLT_INSTANCE Instance; // [rsp+130h] [rbp+30h] BYREF
  ULONG BufferSizeNeeded; // [rsp+138h] [rbp+38h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+140h] [rbp+40h] BYREF
  PFILE_OBJECT FileObject; // [rsp+148h] [rbp+48h] BYREF

  Instance = 0;
  FileHandle = 0;
  FileObject = 0;
  BufferSizeNeeded = 0;
  RetVolume = 0;
  ByteOffset.QuadPart = 0;
  VolumeName = 0;
  String1 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v19 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v4 = *(_DWORD *)(a1 + 4);
  if ( v4 > a2 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    AllocationSize = 13;
    v6 = 59;
    IoStatusBlock = -48;
    goto LABEL_4;
  }
  if ( *(_DWORD *)a1 == 120 )
  {
    if ( v4 >= 0x74 )
    {
      v7 = *(unsigned __int16 *)(a1 + 114);
      if ( v4 >= v7 + 116 )
      {
        VolumeName.Length = *(_WORD *)(a1 + 114);
        VolumeName.Buffer = (PWSTR)(a1 + 116);
        String1.Length = *(_WORD *)(a1 + 112);
        String1.MaximumLength = String1.Length;
        VolumeName.MaximumLength = v7;
        String1.Buffer = (PWSTR)(a1 + 12);
        if ( RtlCompareUnicodeString(&String1, &String2, 0) )
        {
          InstanceFromVolumeName = 0;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v8) = 3;
            WPP_RECORDER_SF_sD(
              wil_details_featureDescriptors_a->DeviceExtension,
              v8,
              14,
              63,
              (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
              250);
          }
        }
        else
        {
          InstanceFromVolumeName = WcGetInstanceFromVolumeName(&VolumeName, &String1, &Instance);
          if ( InstanceFromVolumeName >= 0 )
          {
            InstanceFromVolumeName = FltCreateSystemVolumeInformationFolder(Instance);
            if ( InstanceFromVolumeName >= 0 )
            {
              InstanceFromVolumeName = FltGetVolumeFromName(Globals, &VolumeName, &RetVolume);
              if ( InstanceFromVolumeName >= 0 )
              {
                if ( FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded) == -1073741789 )
                {
                  v9 = 2 * (unsigned __int16)BufferSizeNeeded;
                  if ( v9 > 0xFFFF
                    || (unsigned __int16)(v9 + 8) < (unsigned __int16)v9
                    || (unsigned __int16)(v9 + 80) < (unsigned __int16)(v9 + 8) )
                  {
                    DestinationString.MaximumLength = -1;
                    InstanceFromVolumeName = -1073741675;
                  }
                  else
                  {
                    DestinationString.MaximumLength = v9 + 80;
                    InstanceFromVolumeName = WcAllocateUnicodeString(1852195671, &DestinationString);
                    if ( InstanceFromVolumeName >= 0 )
                    {
                      InstanceFromVolumeName = FltGetVolumeName(RetVolume, &DestinationString, &BufferSizeNeeded);
                      if ( InstanceFromVolumeName >= 0 )
                      {
                        InstanceFromVolumeName = RtlAppendUnicodeToString(
                                                   &DestinationString,
                                                   L"\\System Volume Information\\Wcifs.md");
                        if ( InstanceFromVolumeName >= 0 )
                        {
                          ObjectAttributes.ObjectName = &DestinationString;
                          ObjectAttributes.Length = 48;
                          ObjectAttributes.RootDirectory = 0;
                          ObjectAttributes.Attributes = 512;
                          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                          InstanceFromVolumeName = FltCreateFileEx(
                                                     Globals,
                                                     Instance,
                                                     &FileHandle,
                                                     &FileObject,
                                                     0x1F01FFu,
                                                     &ObjectAttributes,
                                                     &v19,
                                                     0,
                                                     6u,
                                                     1u,
                                                     3u,
                                                     0,
                                                     0,
                                                     0,
                                                     0);
                          if ( InstanceFromVolumeName >= 0 )
                          {
                            ByteOffset.QuadPart = 0;
                            InstanceFromVolumeName = FltWriteFile(
                                                       Instance,
                                                       FileObject,
                                                       &ByteOffset,
                                                       4u,
                                                       (PVOID)(a1 + 8),
                                                       0,
                                                       0,
                                                       0,
                                                       0);
                            if ( InstanceFromVolumeName < 0
                              && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                            {
                              AllocationSize = InstanceFromVolumeName;
                              v6 = 69;
                              IoStatusBlock = 107;
                              goto LABEL_4;
                            }
                          }
                          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                          {
                            AllocationSize = InstanceFromVolumeName;
                            v6 = 68;
                            IoStatusBlock = 90;
                            goto LABEL_4;
                          }
                        }
                        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          AllocationSize = InstanceFromVolumeName;
                          v6 = 67;
                          IoStatusBlock = 63;
                          goto LABEL_4;
                        }
                      }
                    }
                  }
                }
                else
                {
                  InstanceFromVolumeName = -1073741808;
                }
              }
              else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                AllocationSize = InstanceFromVolumeName;
                v6 = 66;
                IoStatusBlock = 17;
                goto LABEL_4;
              }
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              AllocationSize = InstanceFromVolumeName;
              v6 = 65;
              IoStatusBlock = 10;
              goto LABEL_4;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            AllocationSize = InstanceFromVolumeName;
            v6 = 64;
            IoStatusBlock = 3;
            goto LABEL_4;
          }
        }
      }
      else
      {
        InstanceFromVolumeName = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          AllocationSize = 13;
          v6 = 62;
          IoStatusBlock = -29;
          goto LABEL_4;
        }
      }
    }
    else
    {
      InstanceFromVolumeName = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        AllocationSize = 13;
        v6 = 61;
        IoStatusBlock = -36;
        goto LABEL_4;
      }
    }
  }
  else
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      AllocationSize = 13;
      v6 = 60;
      IoStatusBlock = -42;
LABEL_4:
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v4,
        14,
        v6,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        IoStatusBlock,
        AllocationSize);
    }
  }
LABEL_43:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Instance )
    FltObjectDereference(Instance);
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  return (unsigned int)InstanceFromVolumeName;
}

```

## disassembly

```asm
0x140002520  push    rbp
0x140002522  push    rbx
0x140002523  push    rsi
0x140002524  push    rdi
0x140002525  lea     rbp, [rsp-8]
0x14000252a  sub     rsp, 108h
0x140002531  xorps   xmm0, xmm0
0x140002534  xor     esi, esi
0x140002536  mov     ebx, edx
0x140002538  mov     [rbp+20h+Instance], rsi
0x14000253c  mov     rdi, rcx
0x14000253f  mov     [rbp+20h+FileHandle], rsi
0x140002543  xorps   xmm1, xmm1
0x140002546  mov     [rbp+20h+FileObject], rsi
0x14000254a  movups  xmmword ptr [rbp+20h+var_60.ObjectName], xmm0
0x14000254e  xor     eax, eax
0x140002550  mov     [rbp+20h+BufferSizeNeeded], esi
0x140002553  xor     edx, edx; SourceString
0x140002555  mov     [rbp+20h+RetVolume], rsi
0x140002559  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x14000255d  mov     qword ptr [rbp+20h+ByteOffset], rsi
0x140002561  movups  xmmword ptr [rbp+20h+var_60+1Ch], xmm0
0x140002565  movups  xmmword ptr [rbp+20h+VolumeName.Length], xmm0
0x140002569  movups  xmmword ptr [rbp+20h+String1.Length], xmm1
0x14000256d  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x140002571  movups  xmmword ptr [rbp+20h+var_60.Length], xmm0
0x140002575  movups  xmmword ptr [rbp+20h+var_30], xmm0
0x140002579  call    cs:__imp_RtlInitUnicodeString
0x140002580  nop     dword ptr [rax+rax+00h]
0x140002585  mov     edx, [rdi+4]
0x140002588  cmp     edx, ebx
0x14000258a  jbe     short loc_1400025EC
0x14000258c  mov     ecx, 0C000000Dh
0x140002591  mov     ebx, ecx
0x140002593  lea     rax, WPP_RECORDER_INITIALIZED
0x14000259a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400025a1  jz      loc_140002A05
0x1400025a7  mov     dword ptr [rsp+120h+AllocationSize], ecx
0x1400025ab  lea     r9d, [rsi+3Bh]
0x1400025af  mov     dword ptr [rsp+120h+IoStatusBlock], 3D0h
0x1400025b7  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400025be  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x1400025c5  mov     [rsp+120h+ObjectAttributes], rax
0x1400025ca  mov     r8d, 0Eh
0x1400025d0  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x1400025d7  mov     dl, 2
0x1400025d9  mov     qword ptr [rsp+120h+DesiredAccess], rax
0x1400025de  mov     rcx, [rcx+40h]
0x1400025e2  call    WPP_RECORDER_SF_sDd
0x1400025e7  jmp     loc_140002A05
0x1400025ec  cmp     dword ptr [rdi], 78h ; 'x'
0x1400025ef  jz      short loc_140002620
0x1400025f1  mov     ecx, 0C000000Dh
0x1400025f6  mov     ebx, ecx
0x1400025f8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400025ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002606  jz      loc_140002A05
0x14000260c  mov     dword ptr [rsp+120h+AllocationSize], ecx
0x140002610  mov     r9d, 3Ch ; '<'
0x140002616  mov     dword ptr [rsp+120h+IoStatusBlock], 3D6h
0x14000261e  jmp     short loc_1400025B7
0x140002620  cmp     edx, 74h ; 't'
0x140002623  jnb     short loc_140002657
0x140002625  mov     ecx, 0C000000Dh
0x14000262a  mov     ebx, ecx
0x14000262c  lea     rax, WPP_RECORDER_INITIALIZED
0x140002633  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000263a  jz      loc_140002A05
0x140002640  mov     dword ptr [rsp+120h+AllocationSize], ecx
0x140002644  mov     r9d, 3Dh ; '='
0x14000264a  mov     dword ptr [rsp+120h+IoStatusBlock], 3DCh
0x140002652  jmp     loc_1400025B7
0x140002657  movzx   ecx, word ptr [rdi+72h]
0x14000265b  lea     eax, [rcx+74h]
0x14000265e  cmp     edx, eax
0x140002660  jnb     short loc_140002694
0x140002662  mov     ecx, 0C000000Dh
0x140002667  mov     ebx, ecx
0x140002669  lea     rax, WPP_RECORDER_INITIALIZED
0x140002670  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002677  jz      loc_140002A05
0x14000267d  mov     dword ptr [rsp+120h+AllocationSize], ecx
0x140002681  mov     r9d, 3Eh ; '>'
0x140002687  mov     dword ptr [rsp+120h+IoStatusBlock], 3E3h
0x14000268f  jmp     loc_1400025B7
0x140002694  lea     rax, [rdi+74h]
0x140002698  mov     [rbp+20h+VolumeName.Length], cx
0x14000269c  mov     [rbp+20h+VolumeName.Buffer], rax
0x1400026a0  lea     rdx, String2; String2
0x1400026a7  movzx   eax, word ptr [rdi+70h]
0x1400026ab  xor     r8d, r8d; CaseInSensitive
0x1400026ae  mov     [rbp+20h+String1.Length], ax
0x1400026b2  mov     [rbp+20h+String1.MaximumLength], ax
0x1400026b6  lea     rax, [rdi+0Ch]
0x1400026ba  mov     [rbp+20h+VolumeName.MaximumLength], cx
0x1400026be  lea     rcx, [rbp+20h+String1]; String1
0x1400026c2  mov     [rbp+20h+String1.Buffer], rax
0x1400026c6  call    cs:__imp_RtlCompareUnicodeString
0x1400026cd  nop     dword ptr [rax+rax+00h]
0x1400026d2  test    eax, eax
0x1400026d4  jz      short loc_14000272D
0x1400026d6  mov     ebx, esi
0x1400026d8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400026df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400026e6  jz      loc_140002A05
0x1400026ec  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400026f3  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x1400026fa  mov     r9d, 3Fh ; '?'
0x140002700  mov     dword ptr [rsp+120h+IoStatusBlock], 3FAh
0x140002708  mov     [rsp+120h+ObjectAttributes], rax
0x14000270d  mov     dl, 3
0x14000270f  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x140002716  mov     rcx, [rcx+40h]
0x14000271a  lea     r8d, [r9-31h]
0x14000271e  mov     qword ptr [rsp+120h+DesiredAccess], rax
0x140002723  call    WPP_RECORDER_SF_sD
0x140002728  jmp     loc_140002A05
0x14000272d  lea     r8, [rbp+20h+Instance]; RetInstance
0x140002731  lea     rdx, [rbp+20h+String1]; InstanceName
0x140002735  lea     rcx, [rbp+20h+VolumeName]; VolumeName
0x140002739  call    WcGetInstanceFromVolumeName
0x14000273e  mov     ebx, eax
0x140002740  test    eax, eax
0x140002742  jns     short loc_14000276F
0x140002744  lea     rax, WPP_RECORDER_INITIALIZED
0x14000274b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002752  jz      loc_140002A05
0x140002758  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x14000275c  mov     r9d, 40h ; '@'
0x140002762  mov     dword ptr [rsp+120h+IoStatusBlock], 403h
0x14000276a  jmp     loc_1400025B7
0x14000276f  mov     rcx, [rbp+20h+Instance]; Instance
0x140002773  call    cs:__imp_FltCreateSystemVolumeInformationFolder
0x14000277a  nop     dword ptr [rax+rax+00h]
0x14000277f  mov     ebx, eax
0x140002781  test    eax, eax
0x140002783  jns     short loc_1400027B0
0x140002785  lea     rax, WPP_RECORDER_INITIALIZED
0x14000278c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002793  jz      loc_140002A05
0x140002799  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x14000279d  mov     r9d, 41h ; 'A'
0x1400027a3  mov     dword ptr [rsp+120h+IoStatusBlock], 40Ah
0x1400027ab  jmp     loc_1400025B7
0x1400027b0  mov     rcx, cs:Globals; Filter
0x1400027b7  lea     r8, [rbp+20h+RetVolume]; RetVolume
0x1400027bb  lea     rdx, [rbp+20h+VolumeName]; VolumeName
0x1400027bf  call    cs:__imp_FltGetVolumeFromName
0x1400027c6  nop     dword ptr [rax+rax+00h]
0x1400027cb  mov     ebx, eax
0x1400027cd  test    eax, eax
0x1400027cf  jns     short loc_1400027FC
0x1400027d1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400027d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400027df  jz      loc_140002A05
0x1400027e5  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x1400027e9  mov     r9d, 42h ; 'B'
0x1400027ef  mov     dword ptr [rsp+120h+IoStatusBlock], 411h
0x1400027f7  jmp     loc_1400025B7
0x1400027fc  mov     rcx, [rbp+20h+RetVolume]; Volume
0x140002800  lea     r8, [rbp+20h+BufferSizeNeeded]; BufferSizeNeeded
0x140002804  xor     edx, edx; VolumeName
0x140002806  call    cs:__imp_FltGetVolumeName
0x14000280d  nop     dword ptr [rax+rax+00h]
0x140002812  cmp     eax, 0C0000023h
0x140002817  jz      short loc_140002823
0x140002819  mov     ebx, 0C0000010h
0x14000281e  jmp     loc_140002A05
0x140002823  movzx   eax, word ptr [rbp+20h+BufferSizeNeeded]
0x140002827  mov     r8d, 0FFFFh
0x14000282d  add     eax, eax
0x14000282f  cmp     eax, r8d
0x140002832  ja      loc_1400029FB
0x140002838  lea     ecx, [rax+8]
0x14000283b  cmp     cx, ax
0x14000283e  jb      loc_1400029FB
0x140002844  lea     eax, [rcx+48h]
0x140002847  cmp     ax, cx
0x14000284a  jb      loc_1400029FB
0x140002850  lea     rdx, [rbp+20h+DestinationString]
0x140002854  mov     [rbp+20h+DestinationString.MaximumLength], ax
0x140002858  mov     ecx, 6E664357h
0x14000285d  call    WcAllocateUnicodeString
0x140002862  mov     ebx, eax
0x140002864  test    eax, eax
0x140002866  js      loc_140002A05
0x14000286c  mov     rcx, [rbp+20h+RetVolume]; Volume
0x140002870  lea     r8, [rbp+20h+BufferSizeNeeded]; BufferSizeNeeded
0x140002874  lea     rdx, [rbp+20h+DestinationString]; VolumeName
0x140002878  call    cs:__imp_FltGetVolumeName
0x14000287f  nop     dword ptr [rax+rax+00h]
0x140002884  mov     ebx, eax
0x140002886  test    eax, eax
0x140002888  js      loc_140002A05
0x14000288e  lea     rdx, Source; "\\System Volume Information\\Wcifs.md"
0x140002895  lea     rcx, [rbp+20h+DestinationString]; Destination
0x140002899  call    cs:__imp_RtlAppendUnicodeToString
0x1400028a0  nop     dword ptr [rax+rax+00h]
0x1400028a5  mov     ebx, eax
0x1400028a7  test    eax, eax
0x1400028a9  jns     short loc_1400028D6
0x1400028ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400028b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400028b9  jz      loc_140002A05
0x1400028bf  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x1400028c3  mov     r9d, 43h ; 'C'
0x1400028c9  mov     dword ptr [rsp+120h+IoStatusBlock], 43Fh
0x1400028d1  jmp     loc_1400025B7
0x1400028d6  mov     rdx, [rbp+20h+Instance]; Instance
0x1400028da  lea     rax, [rbp+20h+DestinationString]
0x1400028de  mov     rcx, cs:Globals; Filter
0x1400028e5  lea     r9, [rbp+20h+FileObject]; FileObject
0x1400028e9  mov     [rsp+120h+Flags], esi; Flags
0x1400028ed  lea     r8, [rbp+20h+FileHandle]; FileHandle
0x1400028f1  mov     [rsp+120h+EaLength], esi; EaLength
0x1400028f5  xorps   xmm0, xmm0
0x1400028f8  mov     [rsp+120h+EaBuffer], rsi; EaBuffer
0x1400028fd  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x140002901  mov     [rsp+120h+CreateDisposition], 3; CreateDisposition
0x140002909  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x140002911  mov     [rsp+120h+FileAttributes], 6; FileAttributes
0x140002919  mov     [rbp+20h+var_60.ObjectName], rax
0x14000291d  lea     rax, [rbp+20h+var_30]
0x140002921  mov     [rsp+120h+AllocationSize], rsi; AllocationSize
0x140002926  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000292b  lea     rax, [rbp+20h+var_60]
0x14000292f  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140002934  mov     [rsp+120h+DesiredAccess], 1F01FFh; DesiredAccess
0x14000293c  mov     [rbp+20h+var_60.Length], 30h ; '0'
0x140002943  mov     [rbp+20h+var_60.RootDirectory], rsi
0x140002947  mov     [rbp+20h+var_60.Attributes], 200h
0x14000294e  movdqu  xmmword ptr [rbp+20h+var_60.SecurityDescriptor], xmm0
0x140002953  call    cs:__imp_FltCreateFileEx
0x14000295a  nop     dword ptr [rax+rax+00h]
0x14000295f  mov     ebx, eax
0x140002961  test    eax, eax
0x140002963  jns     short loc_140002990
0x140002965  lea     rax, WPP_RECORDER_INITIALIZED
0x14000296c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002973  jz      loc_140002A05
0x140002979  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x14000297d  mov     r9d, 44h ; 'D'
0x140002983  mov     dword ptr [rsp+120h+IoStatusBlock], 45Ah
0x14000298b  jmp     loc_1400025B7
0x140002990  mov     rdx, [rbp+20h+FileObject]; FileObject
0x140002994  lea     rax, [rdi+8]
0x140002998  mov     rcx, [rbp+20h+Instance]; InitiatingInstance
0x14000299c  lea     r8, [rbp+20h+ByteOffset]; ByteOffset
0x1400029a0  mov     qword ptr [rsp+120h+FileAttributes], rsi; CallbackContext
0x1400029a5  mov     r9d, 4; Length
0x1400029ab  mov     [rsp+120h+AllocationSize], rsi; CallbackRoutine
0x1400029b0  mov     [rsp+120h+IoStatusBlock], rsi; BytesWritten
0x1400029b5  mov     dword ptr [rsp+120h+ObjectAttributes], esi; Flags
0x1400029b9  mov     qword ptr [rsp+120h+DesiredAccess], rax; Buffer
0x1400029be  mov     qword ptr [rbp+20h+ByteOffset], rsi
0x1400029c2  call    cs:__imp_FltWriteFile
0x1400029c9  nop     dword ptr [rax+rax+00h]
0x1400029ce  mov     ebx, eax
0x1400029d0  test    eax, eax
0x1400029d2  jns     short loc_140002A05
0x1400029d4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400029db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400029e2  jz      short loc_140002A05
0x1400029e4  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x1400029e8  mov     r9d, 45h ; 'E'
0x1400029ee  mov     dword ptr [rsp+120h+IoStatusBlock], 46Bh
0x1400029f6  jmp     loc_1400025B7
0x1400029fb  mov     [rbp+20h+DestinationString.MaximumLength], r8w
0x140002a00  mov     ebx, 0C0000095h
0x140002a05  mov     rcx, [rbp+20h+DestinationString.Buffer]; P
0x140002a09  test    rcx, rcx
0x140002a0c  jz      short loc_140002A1F
0x140002a0e  mov     edx, 6E664357h; Tag
0x140002a13  call    cs:__imp_ExFreePoolWithTag
0x140002a1a  nop     dword ptr [rax+rax+00h]
0x140002a1f  mov     rcx, [rbp+20h+FileObject]; Object
0x140002a23  test    rcx, rcx
0x140002a26  jz      short loc_140002A34
0x140002a28  call    cs:__imp_ObfDereferenceObject
0x140002a2f  nop     dword ptr [rax+rax+00h]
0x140002a34  mov     rcx, [rbp+20h+FileHandle]; FileHandle
0x140002a38  test    rcx, rcx
0x140002a3b  jz      short loc_140002A49
0x140002a3d  call    cs:__imp_FltClose
0x140002a44  nop     dword ptr [rax+rax+00h]
0x140002a49  mov     rcx, [rbp+20h+Instance]; FltObject
0x140002a4d  test    rcx, rcx
0x140002a50  jz      short loc_140002A5E
0x140002a52  call    cs:__imp_FltObjectDereference
0x140002a59  nop     dword ptr [rax+rax+00h]
0x140002a5e  mov     rcx, [rbp+20h+RetVolume]; FltObject
0x140002a62  test    rcx, rcx
0x140002a65  jz      short loc_140002A73
0x140002a67  call    cs:__imp_FltObjectDereference
0x140002a6e  nop     dword ptr [rax+rax+00h]
0x140002a73  mov     eax, ebx
0x140002a75  add     rsp, 108h
0x140002a7c  pop     rdi
0x140002a7d  pop     rsi
0x140002a7e  pop     rbx
  ... truncated ...
```
