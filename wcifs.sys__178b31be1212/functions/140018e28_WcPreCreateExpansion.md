# WcPreCreateExpansion

- ea: `0x140018e28`
- end: `0x140019393`
- name: `WcPreCreateExpansion`
- size: `1387`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x140030438`

## callees

- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001fd0`
- `0x140001ffc`
- `0x1400020c4`
- `0x1400024d4`
- `0x140004198`
- `0x1400048a4`
- `0x140004b0c`
- `0x140014008`
- `0x140018e28`
- `0x14001939c`
- `0x140029658`
- `0x14002d648`
- `0x14002ee60`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400190a7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400190a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018e97`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018e97`
- `ntoskrnl!ObfDereferenceObject` at `0x140019330`
- `ntoskrnl!ObfDereferenceObject` at `0x140019330`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400190c9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400190c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019307`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019307`
- `FLTMGR!FltGetVolumeName` at `0x14001900e`
- `FLTMGR!FltGetVolumeName` at `0x140019086`
- `FLTMGR!FltGetVolumeName` at `0x14001900e`
- `FLTMGR!FltGetVolumeName` at `0x140019086`
- `FLTMGR!FltClose` at `0x14001931c`
- `FLTMGR!FltClose` at `0x14001931c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400192ed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400192ed`
- `FLTMGR!FltGetFileNameInformation` at `0x140018eba`
- `FLTMGR!FltGetFileNameInformation` at `0x140018eba`
- `FLTMGR!FltParseFileNameInformation` at `0x140018f29`
- `FLTMGR!FltParseFileNameInformation` at `0x140018f29`
- `FLTMGR!FltReleaseContext` at `0x140019344`
- `FLTMGR!FltReleaseContext` at `0x140019358`
- `FLTMGR!FltReleaseContext` at `0x140019344`
- `FLTMGR!FltReleaseContext` at `0x140019358`

## pseudocode

```c
__int64 __fastcall WcPreCreateExpansion(PFLT_CALLBACK_DATA CallbackData, __int64 a2, unsigned int a3, int a4)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FILE_OBJECT *v7; // r14
  void *v8; // rdi
  ULONG Options; // r12d
  void *v10; // rsi
  int v11; // edx
  NTSTATUS VolumeName; // ebx
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  UNICODE_STRING *p_Name; // r13
  int v17; // eax
  int v18; // edx
  int SetContextFileObject; // eax
  int v20; // edx
  char IsExpanded; // al
  NTSTATUS v22; // eax
  int v24; // [rsp+28h] [rbp-59h]
  char v25; // [rsp+38h] [rbp-49h]
  char v26; // [rsp+40h] [rbp-41h]
  char FsInformationClass_high; // [rsp+58h] [rbp-29h]
  __int64 v28; // [rsp+60h] [rbp-21h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-19h] BYREF
  ULONG BufferSizeNeeded; // [rsp+70h] [rbp-11h] BYREF
  __int64 v31; // [rsp+78h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-1h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp+Fh] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp+17h] BYREF
  __int64 UnionContext; // [rsp+A0h] [rbp+1Fh]
  int v38; // [rsp+100h] [rbp+7Fh] BYREF

  v38 = a4;
  Iopb = CallbackData->Iopb;
  FileNameInformation = 0;
  v7 = 0;
  v8 = 0;
  Options = Iopb->Parameters.Create.Options;
  v10 = 0;
  FsInformationClass_high = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
  FileHandle = 0;
  FileObject = 0;
  LOBYTE(v38) = 0;
  DestinationString = 0;
  BufferSizeNeeded = 0;
  UnionContext = 0;
  v31 = 0;
  v28 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( (Options & 0x2000) == 0 )
  {
    VolumeName = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
    if ( VolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_51;
      v26 = VolumeName;
      v13 = 38;
      v25 = -108;
      goto LABEL_5;
    }
    VolumeName = FltParseFileNameInformation(FileNameInformation);
    if ( VolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v26 = VolumeName;
        v13 = 39;
        v25 = -100;
LABEL_5:
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v11,
          5,
          v13,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          v25,
          v26);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    v14 = WcPrePopulatePath(CallbackData, a2, a3, FileNameInformation);
    VolumeName = v14;
    if ( v14 < 0 )
    {
      if ( v14 == -1073741772 || v14 == -1073741766 )
      {
        VolumeName = 0;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_sDZd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v15,
          10,
          40,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          177,
          (__int64)&FileNameInformation->Name,
          v14);
      }
      goto LABEL_51;
    }
    p_Name = &FileNameInformation->Name;
LABEL_25:
    if ( FsInformationClass_high == 2 )
      goto LABEL_51;
    v17 = WcOpenPlaceHolder(
            *(struct _FLT_INSTANCE **)(a2 + 24),
            (__int64)p_Name,
            Options & 0x2041 | 0x28,
            a3,
            &FileHandle,
            (PVOID *)&FileObject,
            &v38);
    if ( v17 < 0 )
    {
      VolumeName = 0;
      if ( v17 != -1073741191 )
        VolumeName = v17;
      goto LABEL_50;
    }
    if ( !(_BYTE)v38 )
    {
      VolumeName = v17;
LABEL_50:
      v7 = FileObject;
      goto LABEL_51;
    }
    v7 = FileObject;
    UnionContext = WcGetUnionContext(0, *(_QWORD *)(a2 + 24), FileObject);
    if ( !UnionContext )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v18,
          10,
          41,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          24);
      }
      VolumeName = -1073741823;
      goto LABEL_51;
    }
    SetContextFileObject = WcGetSetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), v7, v24, (__int64)&v31, (__int64)&v28);
    VolumeName = SetContextFileObject;
    if ( SetContextFileObject < 0 )
    {
      if ( SetContextFileObject != -1073741195 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v20) = 2;
          WPP_RECORDER_SF_sDdZ(
            wil_details_featureDescriptors_a->DeviceExtension,
            v20,
            10,
            42,
            (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
            52,
            SetContextFileObject,
            (__int64)p_Name);
        }
        goto LABEL_47;
      }
    }
    else if ( SetContextFileObject != 260 )
    {
      v8 = (void *)v31;
      IsExpanded = WcIsExpanded(v31);
      v10 = (void *)v28;
      if ( IsExpanded )
        goto LABEL_51;
      if ( (unsigned __int8)WcIsPlaceHolderDirectory(v8, v28) && (unsigned __int8)WcIsSourcedStream(v10) )
      {
        v22 = WcExpandAndWait(CallbackData, *(PVOID *)(a2 + 24), v7, 2, 17);
      }
      else
      {
        if ( !(unsigned __int8)WcIsPlaceHolderStream(v8, v10) )
          goto LABEL_51;
        v22 = WcExpandAndWait(CallbackData, *(PVOID *)(a2 + 24), v7, 1, 17);
      }
      VolumeName = v22;
      goto LABEL_51;
    }
    VolumeName = 0;
LABEL_47:
    v8 = (void *)v31;
    v10 = (void *)v28;
    goto LABEL_51;
  }
  if ( FltGetVolumeName(*(PFLT_VOLUME *)(a2 + 16), 0, &BufferSizeNeeded) != -1073741789 )
  {
    VolumeName = -1073741808;
    goto LABEL_51;
  }
  VolumeName = RtlUShortAdd(BufferSizeNeeded, 2u, &DestinationString.MaximumLength);
  if ( VolumeName >= 0 )
  {
    VolumeName = RtlUShortAdd(DestinationString.MaximumLength, 8u, &DestinationString.MaximumLength);
    if ( VolumeName >= 0 )
    {
      VolumeName = WcAllocateUnicodeString(1852195671, &DestinationString);
      if ( VolumeName >= 0 )
      {
        VolumeName = FltGetVolumeName(*(PFLT_VOLUME *)(a2 + 16), &DestinationString, 0);
        if ( VolumeName >= 0 )
        {
          VolumeName = RtlAppendUnicodeToString(&DestinationString, L"\\");
          if ( VolumeName >= 0 )
          {
            VolumeName = RtlAppendUnicodeStringToString(
                           &DestinationString,
                           (PCUNICODE_STRING)(*(_QWORD *)(a2 + 32) + 88LL));
            if ( VolumeName >= 0 )
            {
              p_Name = &DestinationString;
              goto LABEL_25;
            }
          }
        }
      }
    }
  }
LABEL_51:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( v8 )
    FltReleaseContext(v8);
  if ( v10 )
    FltReleaseContext(v10);
  if ( UnionContext )
    WcReleaseUnionContext(UnionContext);
  return (unsigned int)VolumeName;
}

```

## disassembly

```asm
0x140018e28  mov     rax, rsp
0x140018e2b  mov     [rax+10h], rbx
0x140018e2f  mov     [rax+20h], r9d
0x140018e33  mov     [rax+18h], r8d
0x140018e37  mov     [rax+8], rcx
0x140018e3b  push    rbp
0x140018e3c  push    rsi
0x140018e3d  push    rdi
0x140018e3e  push    r12
0x140018e40  push    r13
0x140018e42  push    r14
0x140018e44  push    r15
0x140018e46  lea     rbp, [rax-5Fh]
0x140018e4a  sub     rsp, 0A0h
0x140018e51  mov     rax, [rcx+10h]
0x140018e55  mov     r13, rcx
0x140018e58  mov     r15, rdx
0x140018e5b  xorps   xmm0, xmm0
0x140018e5e  xor     edx, edx; SourceString
0x140018e60  mov     [rbp+57h+FileNameInformation], rdx
0x140018e64  mov     r14d, edx
0x140018e67  mov     cl, [rax+23h]
0x140018e6a  mov     edi, edx
0x140018e6c  mov     r12d, [rax+20h]
0x140018e70  mov     esi, edx
0x140018e72  mov     [rbp+57h+var_80], cl
0x140018e75  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018e79  mov     [rbp+57h+FileHandle], rdx
0x140018e7d  mov     [rbp+57h+FileObject], rdx
0x140018e81  mov     byte ptr [rbp+57h+arg_18], dl
0x140018e84  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140018e88  mov     [rbp+57h+BufferSizeNeeded], edx
0x140018e8b  mov     [rbp+57h+var_38], rdx
0x140018e8f  mov     [rbp+57h+var_60], rdx
0x140018e93  mov     [rbp+57h+var_78], rdx
0x140018e97  call    cs:__imp_RtlInitUnicodeString
0x140018e9e  nop     dword ptr [rax+rax+00h]
0x140018ea3  bt      r12d, 0Dh
0x140018ea8  jb      loc_140019004
0x140018eae  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140018eb2  mov     edx, 102h; NameOptions
0x140018eb7  mov     rcx, r13; CallbackData
0x140018eba  call    cs:__imp_FltGetFileNameInformation
0x140018ec1  nop     dword ptr [rax+rax+00h]
0x140018ec6  mov     ebx, eax
0x140018ec8  test    eax, eax
0x140018eca  jns     short loc_140018F25
0x140018ecc  lea     rax, WPP_RECORDER_INITIALIZED
0x140018ed3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018eda  jz      loc_1400192E4
0x140018ee0  mov     dword ptr [rsp+0D0h+var_98], ebx
0x140018ee4  lea     r9d, [rsi+26h]
0x140018ee8  mov     dword ptr [rsp+0D0h+var_A0], 0C94h
0x140018ef0  mov     rcx, cs:wil_details_featureDescriptors_a
0x140018ef7  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140018efe  mov     [rsp+0D0h+var_A8], rax
0x140018f03  mov     r8d, 5
0x140018f09  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018f10  mov     dl, 2
0x140018f12  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140018f17  mov     rcx, [rcx+40h]
0x140018f1b  call    WPP_RECORDER_SF_sDd
0x140018f20  jmp     loc_1400192E4
0x140018f25  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140018f29  call    cs:__imp_FltParseFileNameInformation
0x140018f30  nop     dword ptr [rax+rax+00h]
0x140018f35  mov     ebx, eax
0x140018f37  test    eax, eax
0x140018f39  jns     short loc_140018F63
0x140018f3b  lea     rax, WPP_RECORDER_INITIALIZED
0x140018f42  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018f49  jz      loc_1400192E4
0x140018f4f  mov     dword ptr [rsp+0D0h+var_98], ebx
0x140018f53  mov     r9d, 27h ; '''
0x140018f59  mov     dword ptr [rsp+0D0h+var_A0], 0C9Ch
0x140018f61  jmp     short loc_140018EF0
0x140018f63  mov     r9, [rbp+57h+FileNameInformation]
0x140018f67  mov     rdx, r15
0x140018f6a  mov     r8d, [rbp+57h+arg_10]
0x140018f6e  mov     rcx, r13
0x140018f71  call    WcPrePopulatePath
0x140018f76  mov     ebx, eax
0x140018f78  test    eax, eax
0x140018f7a  jns     short loc_140018FF7
0x140018f7c  cmp     eax, 0C0000034h
0x140018f81  jz      short loc_140018FF0
0x140018f83  cmp     eax, 0C000003Ah
0x140018f88  jz      short loc_140018FF0
0x140018f8a  lea     rax, WPP_RECORDER_INITIALIZED
0x140018f91  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018f98  jz      loc_1400192E4
0x140018f9e  mov     rax, [rbp+57h+FileNameInformation]
0x140018fa2  mov     r9d, 28h ; '('
0x140018fa8  mov     rcx, cs:wil_details_featureDescriptors_a
0x140018faf  add     rax, 8
0x140018fb3  mov     dword ptr [rsp+0D0h+var_98+8], ebx
0x140018fb7  mov     dl, 2
0x140018fb9  mov     qword ptr [rsp+0D0h+var_98], rax
0x140018fbe  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140018fc5  mov     dword ptr [rsp+0D0h+var_A0], 0CB1h
0x140018fcd  lea     r8d, [r9-1Eh]
0x140018fd1  mov     rcx, [rcx+40h]
0x140018fd5  mov     [rsp+0D0h+var_A8], rax
0x140018fda  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018fe1  mov     qword ptr [rsp+0D0h+var_B0], rax
0x140018fe6  call    WPP_RECORDER_SF_sDZd
0x140018feb  jmp     loc_1400192E4
0x140018ff0  xor     ebx, ebx
0x140018ff2  jmp     loc_1400192E4
0x140018ff7  mov     r13, [rbp+57h+FileNameInformation]
0x140018ffb  add     r13, 8
0x140018fff  jmp     loc_1400190E3
0x140019004  mov     rcx, [r15+10h]; Volume
0x140019008  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x14001900c  xor     edx, edx; VolumeName
0x14001900e  call    cs:__imp_FltGetVolumeName
0x140019015  nop     dword ptr [rax+rax+00h]
0x14001901a  cmp     eax, 0C0000023h
0x14001901f  jz      short loc_14001902B
0x140019021  mov     ebx, 0C0000010h
0x140019026  jmp     loc_1400192E4
0x14001902b  movzx   ecx, word ptr [rbp+57h+BufferSizeNeeded]; usAugend
0x14001902f  lea     r8, [rbp+57h+DestinationString.MaximumLength]; pusResult
0x140019033  mov     edx, 2; usAddend
0x140019038  call    RtlUShortAdd
0x14001903d  mov     ebx, eax
0x14001903f  test    eax, eax
0x140019041  js      loc_1400192E4
0x140019047  movzx   ecx, [rbp+57h+DestinationString.MaximumLength]; usAugend
0x14001904b  lea     r8, [rbp+57h+DestinationString.MaximumLength]; pusResult
0x14001904f  mov     edx, 8; usAddend
0x140019054  call    RtlUShortAdd
0x140019059  mov     ebx, eax
0x14001905b  test    eax, eax
0x14001905d  js      loc_1400192E4
0x140019063  lea     rdx, [rbp+57h+DestinationString]
0x140019067  mov     ecx, 6E664357h
0x14001906c  call    WcAllocateUnicodeString
0x140019071  mov     ebx, eax
0x140019073  test    eax, eax
0x140019075  js      loc_1400192E4
0x14001907b  mov     rcx, [r15+10h]; Volume
0x14001907f  lea     rdx, [rbp+57h+DestinationString]; VolumeName
0x140019083  xor     r8d, r8d; BufferSizeNeeded
0x140019086  call    cs:__imp_FltGetVolumeName
0x14001908d  nop     dword ptr [rax+rax+00h]
0x140019092  mov     ebx, eax
0x140019094  test    eax, eax
0x140019096  js      loc_1400192E4
0x14001909c  lea     rdx, Source2; "\\"
0x1400190a3  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400190a7  call    cs:__imp_RtlAppendUnicodeToString
0x1400190ae  nop     dword ptr [rax+rax+00h]
0x1400190b3  mov     ebx, eax
0x1400190b5  test    eax, eax
0x1400190b7  js      loc_1400192E4
0x1400190bd  mov     rdx, [r15+20h]
0x1400190c1  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400190c5  add     rdx, 58h ; 'X'; Source
0x1400190c9  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400190d0  nop     dword ptr [rax+rax+00h]
0x1400190d5  mov     ebx, eax
0x1400190d7  test    eax, eax
0x1400190d9  js      loc_1400192E4
0x1400190df  lea     r13, [rbp+57h+DestinationString]
0x1400190e3  cmp     [rbp+57h+var_80], 2
0x1400190e7  jz      loc_1400192E4
0x1400190ed  mov     r9d, [rbp+57h+arg_10]
0x1400190f1  lea     rax, [rbp+57h+arg_18]
0x1400190f5  mov     rcx, [r15+18h]
0x1400190f9  and     r12d, 2041h
0x140019100  mov     [rsp+0D0h+var_A0], rax
0x140019105  or      r12d, 28h
0x140019109  lea     rax, [rbp+57h+FileObject]
0x14001910d  mov     r8d, r12d
0x140019110  mov     [rsp+0D0h+var_A8], rax
0x140019115  mov     rdx, r13
0x140019118  lea     rax, [rbp+57h+FileHandle]
0x14001911c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x140019121  call    WcOpenPlaceHolder
0x140019126  test    eax, eax
0x140019128  jns     short loc_140019139
0x14001912a  xor     ebx, ebx
0x14001912c  cmp     eax, 0C0000279h
0x140019131  cmovnz  ebx, eax
0x140019134  jmp     loc_1400192E0
0x140019139  cmp     byte ptr [rbp+57h+arg_18], sil
0x14001913d  jz      loc_1400192DE
0x140019143  mov     r14, [rbp+57h+FileObject]
0x140019147  xor     ecx, ecx
0x140019149  mov     rdx, [r15+18h]
0x14001914d  mov     r8, r14
0x140019150  call    WcGetUnionContext
0x140019155  mov     [rbp+57h+var_38], rax
0x140019159  test    rax, rax
0x14001915c  jnz     short loc_1400191B4
0x14001915e  lea     rax, WPP_RECORDER_INITIALIZED
0x140019165  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001916c  jz      short loc_1400191AA
0x14001916e  mov     rcx, cs:wil_details_featureDescriptors_a
0x140019175  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x14001917c  mov     r9d, 29h ; ')'
0x140019182  mov     dword ptr [rsp+0D0h+var_A0], 0D18h
0x14001918a  mov     [rsp+0D0h+var_A8], rax
0x14001918f  mov     dl, 2
0x140019191  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140019198  mov     rcx, [rcx+40h]
0x14001919c  lea     r8d, [r9-1Fh]
0x1400191a0  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1400191a5  call    WPP_RECORDER_SF_sD
0x1400191aa  mov     ebx, 0C0000001h
0x1400191af  jmp     loc_1400192E4
0x1400191b4  lea     rcx, [rbp+57h+var_78]
0x1400191b8  and     r12d, 41h
0x1400191bc  mov     [rsp+0D0h+var_A0], rcx; __int64
0x1400191c1  mov     r9d, r12d
0x1400191c4  lea     rcx, [rbp+57h+var_60]
0x1400191c8  mov     r8, rax
0x1400191cb  mov     [rsp+0D0h+var_A8], rcx; __int64
0x1400191d0  mov     rdx, r14; FileObject
0x1400191d3  mov     rcx, [r15+18h]; Instance
0x1400191d7  call    WcGetSetContextFileObject
0x1400191dc  mov     ebx, eax
0x1400191de  test    eax, eax
0x1400191e0  js      loc_140019273
0x1400191e6  cmp     eax, 104h
0x1400191eb  jz      loc_1400192DA
0x1400191f1  mov     rdi, [rbp+57h+var_60]
0x1400191f5  mov     rcx, rdi
0x1400191f8  call    WcIsExpanded
0x1400191fd  mov     rsi, [rbp+57h+var_78]
0x140019201  test    al, al
0x140019203  jnz     loc_1400192E4
0x140019209  mov     rdx, rsi
0x14001920c  mov     rcx, rdi
0x14001920f  call    WcIsPlaceHolderDirectory
0x140019214  test    al, al
0x140019216  jz      short loc_14001924E
0x140019218  mov     rcx, rsi
0x14001921b  call    WcIsSourcedStream
0x140019220  test    al, al
0x140019222  jz      short loc_14001924E
0x140019224  mov     dword ptr [rsp+0D0h+var_A8], 11h; int
0x14001922c  mov     [rsp+0D0h+var_B0], 2; int
0x140019234  mov     rdx, [r15+18h]; FltObject
0x140019238  mov     r9, rdi
0x14001923b  mov     rcx, [rbp+57h+CallbackData]; CallbackData
0x14001923f  mov     r8, r14; Object
0x140019242  call    WcExpandAndWait
0x140019247  mov     ebx, eax
0x140019249  jmp     loc_1400192E4
0x14001924e  mov     rdx, rsi
0x140019251  mov     rcx, rdi
0x140019254  call    WcIsPlaceHolderStream
0x140019259  test    al, al
0x14001925b  jz      loc_1400192E4
0x140019261  mov     dword ptr [rsp+0D0h+var_A8], 11h
0x140019269  mov     [rsp+0D0h+var_B0], 1
0x140019271  jmp     short loc_140019234
0x140019273  cmp     ebx, 0C0000275h
0x140019279  jz      short loc_1400192DA
0x14001927b  lea     rax, WPP_RECORDER_INITIALIZED
0x140019282  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019289  jz      short loc_1400192D0
0x14001928b  mov     rcx, cs:wil_details_featureDescriptors_a
0x140019292  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140019299  mov     qword ptr [rsp+0D0h+var_98+8], r13
0x14001929e  mov     r9d, 2Ah ; '*'
0x1400192a4  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1400192a8  mov     dl, 2
0x1400192aa  mov     dword ptr [rsp+0D0h+var_A0], 0D34h
0x1400192b2  mov     rcx, [rcx+40h]
0x1400192b6  mov     [rsp+0D0h+var_A8], rax
0x1400192bb  lea     r8d, [r9-20h]
0x1400192bf  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x1400192c6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1400192cb  call    WPP_RECORDER_SF_sDdZ
0x1400192d0  mov     rdi, [rbp+57h+var_60]
0x1400192d4  mov     rsi, [rbp+57h+var_78]
0x1400192d8  jmp     short loc_1400192E4
0x1400192da  xor     ebx, ebx
0x1400192dc  jmp     short loc_1400192D0
0x1400192de  mov     ebx, eax
0x1400192e0  mov     r14, [rbp+57h+FileObject]
0x1400192e4  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400192e8  test    rcx, rcx
0x1400192eb  jz      short loc_1400192F9
0x1400192ed  call    cs:__imp_FltReleaseFileNameInformation
0x1400192f4  nop     dword ptr [rax+rax+00h]
0x1400192f9  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x1400192fd  test    rcx, rcx
0x140019300  jz      short loc_140019313
0x140019302  mov     edx, 6E664357h; Tag
0x140019307  call    cs:__imp_ExFreePoolWithTag
0x14001930e  nop     dword ptr [rax+rax+00h]
0x140019313  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140019317  test    rcx, rcx
0x14001931a  jz      short loc_140019328
0x14001931c  call    cs:__imp_FltClose
0x140019323  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
