# WcReopenFile

- ea: `0x140020434`
- end: `0x14002074e`
- name: `WcReopenFile`
- size: `794`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PHANDLE FileHandle, PFILE_OBJECT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001cff0`
- `0x14001f08c`
- `0x14001fc48`

## callees

- `0x1400024d4`
- `0x1400048a4`
- `0x140020434`
- `0x14002ee10`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002059a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002059a`
- `ntoskrnl!IoGetSilo` at `0x1400205fb`
- `ntoskrnl!IoGetSilo` at `0x1400205fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400204a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400204a7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400205c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400205c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002072d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002072d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400204f1`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400204f1`
- `FLTMGR!FltCreateFileEx2` at `0x14002069f`
- `FLTMGR!FltCreateFileEx2` at `0x14002069f`
- `FLTMGR!FltGetVolumeName` at `0x140020511`
- `FLTMGR!FltGetVolumeName` at `0x140020579`
- `FLTMGR!FltGetVolumeName` at `0x140020511`
- `FLTMGR!FltGetVolumeName` at `0x140020579`
- `FLTMGR!FltObjectDereference` at `0x140020713`
- `FLTMGR!FltObjectDereference` at `0x140020713`
- `FLTMGR!FltQueryInformationFile` at `0x1400204d4`
- `FLTMGR!FltQueryInformationFile` at `0x1400204d4`

## pseudocode

```c
__int64 __fastcall WcReopenFile(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PHANDLE FileHandle, PFILE_OBJECT *a4)
{
  NTSTATUS VolumeFromInstance; // ebx
  int v9; // edx
  ULONG BufferSizeNeeded; // [rsp+80h] [rbp-80h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  ULONG LengthReturned; // [rsp+A0h] [rbp-60h] BYREF
  __int64 FileInformation; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING Source; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+C0h] [rbp-40h] BYREF
  __int64 Silo; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF

  FileInformation = 0;
  LengthReturned = 0;
  RetVolume = 0;
  BufferSizeNeeded = 0;
  LOWORD(Silo) = 0;
  DestinationString = 0;
  Source = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&DriverContext, 0, sizeof(DriverContext));
  RtlInitUnicodeString(&DestinationString, 0);
  VolumeFromInstance = FltQueryInformationFile(
                         Instance,
                         FileObject,
                         &FileInformation,
                         8u,
                         FileInternalInformation,
                         &LengthReturned);
  if ( VolumeFromInstance >= 0 )
  {
    VolumeFromInstance = FltGetVolumeFromInstance(Instance, &RetVolume);
    if ( VolumeFromInstance >= 0 )
    {
      VolumeFromInstance = FltGetVolumeName(RetVolume, 0, &BufferSizeNeeded);
      if ( (int)(VolumeFromInstance + 0x80000000) < 0 || VolumeFromInstance == -1073741789 )
      {
        VolumeFromInstance = RtlUShortAdd(BufferSizeNeeded, 0xAu, &DestinationString.MaximumLength);
        if ( VolumeFromInstance >= 0 )
        {
          VolumeFromInstance = WcAllocateUnicodeString(1852195671, &DestinationString);
          if ( VolumeFromInstance >= 0 )
          {
            VolumeFromInstance = FltGetVolumeName(RetVolume, &DestinationString, &BufferSizeNeeded);
            if ( VolumeFromInstance >= 0 )
            {
              VolumeFromInstance = RtlAppendUnicodeToString(&DestinationString, L"\\");
              if ( VolumeFromInstance >= 0 )
              {
                *(_DWORD *)&Source.Length = 524296;
                Source.Buffer = (PWSTR)&FileInformation;
                VolumeFromInstance = RtlAppendUnicodeStringToString(&DestinationString, &Source);
                if ( VolumeFromInstance >= 0 )
                {
                  memset(&DriverContext, 0, sizeof(DriverContext));
                  DriverContext.Size = 40;
                  Silo = 1;
                  Silo = IoGetSilo(FileObject);
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = &DestinationString;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 512;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  VolumeFromInstance = FltCreateFileEx2(
                                         Globals,
                                         Instance,
                                         FileHandle,
                                         a4,
                                         0x80000000,
                                         &ObjectAttributes,
                                         &IoStatusBlock,
                                         0,
                                         0,
                                         7u,
                                         1u,
                                         0x202028u,
                                         0,
                                         0,
                                         0x800u,
                                         &DriverContext);
                  if ( VolumeFromInstance < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v9) = 2;
                    WPP_RECORDER_SF_sDZd(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v9,
                      10,
                      106,
                      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
                      237,
                      (__int64)&DestinationString,
                      VolumeFromInstance);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  return (unsigned int)VolumeFromInstance;
}

```

## disassembly

```asm
0x140020434  push    rbp
0x140020436  push    rbx
0x140020437  push    rsi
0x140020438  push    rdi
0x140020439  push    r13
0x14002043b  push    r14
0x14002043d  push    r15
0x14002043f  lea     rbp, [rsp-30h]
0x140020444  sub     rsp, 130h
0x14002044b  xorps   xmm0, xmm0
0x14002044e  mov     [rbp+60h+FileInformation], 0
0x140020456  mov     rsi, rdx
0x140020459  mov     [rbp+60h+var_C0], 0
0x140020460  mov     rdi, rcx
0x140020463  mov     [rbp+60h+RetVolume], 0
0x14002046b  xorps   xmm1, xmm1
0x14002046e  mov     [rbp+60h+BufferSizeNeeded], 0
0x140020475  xor     eax, eax
0x140020477  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x14002047b  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14002047f  xor     edx, edx; SourceString
0x140020481  mov     word ptr [rbp+60h+var_80], ax
0x140020485  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140020489  mov     r14, r9
0x14002048c  mov     r15, r8
0x14002048f  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140020493  movups  xmmword ptr [rbp+60h+Source.Length], xmm0
0x140020497  movups  xmmword ptr [rbp+60h+var_48], xmm1
0x14002049b  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14002049f  movups  xmmword ptr [rbp+60h+var_A0.Size], xmm0
0x1400204a3  movups  xmmword ptr [rbp+60h+var_A0.DeviceObjectHint], xmm0
0x1400204a7  call    cs:__imp_RtlInitUnicodeString
0x1400204ae  nop     dword ptr [rax+rax+00h]
0x1400204b3  lea     rax, [rbp+60h+var_C0]
0x1400204b7  mov     r9d, 8; Length
0x1400204bd  mov     [rsp+160h+LengthReturned], rax; LengthReturned
0x1400204c2  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1400204c6  mov     rdx, rsi; FileObject
0x1400204c9  mov     [rsp+160h+FileInformationClass], 6; FileInformationClass
0x1400204d1  mov     rcx, rdi; Instance
0x1400204d4  call    cs:__imp_FltQueryInformationFile
0x1400204db  nop     dword ptr [rax+rax+00h]
0x1400204e0  mov     ebx, eax
0x1400204e2  test    eax, eax
0x1400204e4  js      loc_14002070A
0x1400204ea  lea     rdx, [rbp+60h+RetVolume]; RetVolume
0x1400204ee  mov     rcx, rdi; Instance
0x1400204f1  call    cs:__imp_FltGetVolumeFromInstance
0x1400204f8  nop     dword ptr [rax+rax+00h]
0x1400204fd  mov     ebx, eax
0x1400204ff  test    eax, eax
0x140020501  js      loc_14002070A
0x140020507  mov     rcx, [rbp+60h+RetVolume]; Volume
0x14002050b  lea     r8, [rbp+60h+BufferSizeNeeded]; BufferSizeNeeded
0x14002050f  xor     edx, edx; VolumeName
0x140020511  call    cs:__imp_FltGetVolumeName
0x140020518  nop     dword ptr [rax+rax+00h]
0x14002051d  mov     r13d, 80000000h
0x140020523  mov     ebx, eax
0x140020525  add     eax, r13d
0x140020528  test    r13d, eax
0x14002052b  jnz     short loc_140020539
0x14002052d  cmp     ebx, 0C0000023h
0x140020533  jnz     loc_14002070A
0x140020539  movzx   ecx, word ptr [rbp+60h+BufferSizeNeeded]; usAugend
0x14002053d  lea     r8, [rbp+60h+DestinationString.MaximumLength]; pusResult
0x140020541  mov     edx, 0Ah; usAddend
0x140020546  call    RtlUShortAdd
0x14002054b  mov     ebx, eax
0x14002054d  test    eax, eax
0x14002054f  js      loc_14002070A
0x140020555  lea     rdx, [rbp+60h+DestinationString]
0x140020559  mov     ecx, 6E664357h
0x14002055e  call    WcAllocateUnicodeString
0x140020563  mov     ebx, eax
0x140020565  test    eax, eax
0x140020567  js      loc_14002070A
0x14002056d  mov     rcx, [rbp+60h+RetVolume]; Volume
0x140020571  lea     r8, [rbp+60h+BufferSizeNeeded]; BufferSizeNeeded
0x140020575  lea     rdx, [rbp+60h+DestinationString]; VolumeName
0x140020579  call    cs:__imp_FltGetVolumeName
0x140020580  nop     dword ptr [rax+rax+00h]
0x140020585  mov     ebx, eax
0x140020587  test    eax, eax
0x140020589  js      loc_14002070A
0x14002058f  lea     rdx, Source2; "\\"
0x140020596  lea     rcx, [rbp+60h+DestinationString]; Destination
0x14002059a  call    cs:__imp_RtlAppendUnicodeToString
0x1400205a1  nop     dword ptr [rax+rax+00h]
0x1400205a6  mov     ebx, eax
0x1400205a8  test    eax, eax
0x1400205aa  js      loc_14002070A
0x1400205b0  lea     rax, [rbp+60h+FileInformation]
0x1400205b4  mov     dword ptr [rbp+60h+Source.Length], 80008h
0x1400205bb  lea     rdx, [rbp+60h+Source]; Source
0x1400205bf  mov     [rbp+60h+Source.Buffer], rax
0x1400205c3  lea     rcx, [rbp+60h+DestinationString]; Destination
0x1400205c7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400205ce  nop     dword ptr [rax+rax+00h]
0x1400205d3  mov     ebx, eax
0x1400205d5  test    eax, eax
0x1400205d7  js      loc_14002070A
0x1400205dd  mov     eax, 28h ; '('
0x1400205e2  xorps   xmm0, xmm0
0x1400205e5  movups  xmmword ptr [rbp+60h+var_A0.Size], xmm0
0x1400205e9  mov     rcx, rsi
0x1400205ec  mov     [rbp+60h+var_A0.Size], ax
0x1400205f0  movups  xmmword ptr [rbp+60h+var_A0.DeviceObjectHint], xmm0
0x1400205f4  lea     ebx, [rax-27h]
0x1400205f7  mov     [rbp+60h+var_80], rbx
0x1400205fb  call    cs:__imp_IoGetSilo
0x140020602  nop     dword ptr [rax+rax+00h]
0x140020607  mov     rcx, cs:Globals; Filter
0x14002060e  xorps   xmm0, xmm0
0x140020611  mov     [rbp+60h+var_80], rax
0x140020615  mov     r9, r14; FileObject
0x140020618  lea     rax, [rbp+60h+DestinationString]
0x14002061c  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x140020623  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140020627  mov     r8, r15; FileHandle
0x14002062a  lea     rax, [rbp+60h+var_A0]
0x14002062e  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x140020636  mov     [rsp+160h+DriverContext], rax; DriverContext
0x14002063b  mov     rdx, rdi; Instance
0x14002063e  mov     [rsp+160h+Flags], 800h; Flags
0x140020646  lea     rax, [rbp+60h+var_48]
0x14002064a  mov     [rsp+160h+EaLength], 0; EaLength
0x140020652  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x14002065b  mov     [rsp+160h+CreateOptions], 202028h; CreateOptions
0x140020663  mov     [rsp+160h+CreateDisposition], ebx; CreateDisposition
0x140020667  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x14002066f  mov     [rsp+160h+FileAttributes], 0; FileAttributes
0x140020677  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x140020680  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140020685  lea     rax, [rbp+60h+ObjectAttributes]
0x140020689  mov     [rsp+160h+LengthReturned], rax; ObjectAttributes
0x14002068e  mov     [rsp+160h+FileInformationClass], r13d; DesiredAccess
0x140020693  mov     [rbp+60h+ObjectAttributes.Attributes], 200h
0x14002069a  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002069f  call    cs:__imp_FltCreateFileEx2
0x1400206a6  nop     dword ptr [rax+rax+00h]
0x1400206ab  mov     ebx, eax
0x1400206ad  test    eax, eax
0x1400206af  jns     short loc_14002070A
0x1400206b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400206b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400206bf  jz      short loc_14002070A
0x1400206c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206c8  lea     rax, [rbp+60h+DestinationString]
0x1400206cc  mov     [rsp+160h+FileAttributes], ebx
0x1400206d0  mov     r9d, 6Ah ; 'j'
0x1400206d6  mov     [rsp+160h+AllocationSize], rax
0x1400206db  mov     dl, 2
0x1400206dd  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x1400206e4  mov     dword ptr [rsp+160h+IoStatusBlock], 0BEDh
0x1400206ec  mov     rcx, [rcx+40h]
0x1400206f0  mov     [rsp+160h+LengthReturned], rax
0x1400206f5  lea     r8d, [r9-60h]
0x1400206f9  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140020700  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140020705  call    WPP_RECORDER_SF_sDZd
0x14002070a  mov     rcx, [rbp+60h+RetVolume]; FltObject
0x14002070e  test    rcx, rcx
0x140020711  jz      short loc_14002071F
0x140020713  call    cs:__imp_FltObjectDereference
0x14002071a  nop     dword ptr [rax+rax+00h]
0x14002071f  mov     rcx, [rbp+60h+DestinationString.Buffer]; P
0x140020723  test    rcx, rcx
0x140020726  jz      short loc_140020739
0x140020728  mov     edx, 6E664357h; Tag
0x14002072d  call    cs:__imp_ExFreePoolWithTag
0x140020734  nop     dword ptr [rax+rax+00h]
0x140020739  mov     eax, ebx
0x14002073b  add     rsp, 130h
0x140020742  pop     r15
0x140020744  pop     r14
0x140020746  pop     r13
0x140020748  pop     rdi
0x140020749  pop     rsi
0x14002074a  pop     rbx
0x14002074b  pop     rbp
0x14002074c  retn
```
