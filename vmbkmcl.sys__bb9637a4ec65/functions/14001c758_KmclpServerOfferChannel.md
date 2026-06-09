# KmclpServerOfferChannel

- ea: `0x14001c758`
- end: `0x14001cdcb`
- name: `KmclpServerOfferChannel`
- size: `1651`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ed00`

## callees

- `0x14000a9bc`
- `0x14000ab90`
- `0x14000cbc8`
- `0x14000cf30`
- `0x14000e310`
- `0x14000ec34`
- `0x14000f5c4`
- `0x140011e90`
- `0x140012280`
- `0x14001c758`
- `0x14001cdd4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14001ca79`
- `ntoskrnl!ObfReferenceObject` at `0x14001ca79`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001c8fe`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001c8fe`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14001c8d2`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14001c8d2`
- `ntoskrnl!ObIsKernelHandle` at `0x14001c843`
- `ntoskrnl!ObIsKernelHandle` at `0x14001c843`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001ca63`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14001ca63`
- `ntoskrnl!IoFileObjectType` at `0x14001ca0e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ca34`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ca34`
- `ntoskrnl!ZwOpenFile` at `0x14001c9f8`
- `ntoskrnl!ZwOpenFile` at `0x14001c9f8`
- `ntoskrnl!ZwClose` at `0x14001ca50`
- `ntoskrnl!ZwClose` at `0x14001ca50`

## pseudocode

```c
__int64 __fastcall KmclpServerOfferChannel(ULONG_PTR BugCheckParameter2)
{
  void *v2; // rcx
  __int128 v3; // xmm1
  int v4; // ebx
  __int64 v5; // r8
  void *v7; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int128 v9; // xmm0
  __int64 v10; // rcx
  __int128 v11; // xmm1
  __int16 v12; // cx
  __int16 v13; // ax
  __int16 v14; // cx
  __int16 v15; // ax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int64 v22; // r8
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-88h] BYREF
  __int64 FsInformation; // [rsp+88h] [rbp-78h] BYREF
  PVOID Object; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v33[12]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v34[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t v35; // [rsp+1D0h] [rbp+D0h]
  char v36; // [rsp+1E0h] [rbp+E0h] BYREF

  v35 = aDosdevicesVmbu[24];
  v34[0] = *(_OWORD *)L"\\DosDevices\\VMBus\\offer\\";
  Destination.Buffer = (PWSTR)&v36;
  *(_QWORD *)&Destination.Length = 8257536;
  FsInformation = 0;
  v34[2] = *(_OWORD *)L"s\\offer\\";
  FileHandle = 0;
  v34[1] = *(_OWORD *)L"ces\\VMBus\\offer\\";
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(v33, 0, sizeof(v33));
  v2 = *(void **)(BugCheckParameter2 + 1952);
  v3 = *(_OWORD *)(BugCheckParameter2 + 1772);
  *(_OWORD *)(BugCheckParameter2 + 2736) = *(_OWORD *)(BugCheckParameter2 + 1756);
  *(_OWORD *)(BugCheckParameter2 + 2752) = v3;
  if ( v2 )
  {
    if ( !ObIsKernelHandle(v2) )
      goto LABEL_3;
    v4 = ZwQueryVolumeInformationFile(
           *(HANDLE *)(BugCheckParameter2 + 1952),
           &IoStatusBlock,
           &FsInformation,
           8u,
           FileFsDeviceInformation);
    if ( v4 < 0 )
      goto LABEL_4;
    if ( (_DWORD)FsInformation != 62 )
    {
LABEL_3:
      v4 = -1073741811;
      goto LABEL_4;
    }
    RtlAppendUnicodeToString(&Destination, L"offer");
    ObjectAttributes.RootDirectory = *(HANDLE *)(BugCheckParameter2 + 1952);
  }
  else
  {
    RtlUnicodeStringPrintf(
      &Destination,
      L"%s{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      v34,
      *(unsigned int *)(BugCheckParameter2 + 1808),
      *(unsigned __int16 *)(BugCheckParameter2 + 1812),
      *(unsigned __int16 *)(BugCheckParameter2 + 1814),
      *(unsigned __int8 *)(BugCheckParameter2 + 1816),
      *(unsigned __int8 *)(BugCheckParameter2 + 1817),
      *(unsigned __int8 *)(BugCheckParameter2 + 1818),
      *(unsigned __int8 *)(BugCheckParameter2 + 1819),
      *(unsigned __int8 *)(BugCheckParameter2 + 1820),
      *(unsigned __int8 *)(BugCheckParameter2 + 1821),
      *(unsigned __int8 *)(BugCheckParameter2 + 1822),
      *(unsigned __int8 *)(BugCheckParameter2 + 1823));
    ObjectAttributes.RootDirectory = 0;
  }
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &IoStatusBlock, 0, 0x40u);
  if ( v4 < 0 )
    goto LABEL_4;
  Object = 0;
  ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  v7 = FileHandle;
  *(_QWORD *)(BugCheckParameter2 + 2728) = Object;
  ZwClose(v7);
  RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(BugCheckParameter2 + 2728));
  *(_QWORD *)(BugCheckParameter2 + 2720) = RelatedDeviceObject;
  ObfReferenceObject(RelatedDeviceObject);
  memset(v33, 0, sizeof(v33));
  v9 = *(_OWORD *)(BugCheckParameter2 + 1756);
  v10 = *(unsigned __int16 *)(BugCheckParameter2 + 1800);
  *(_DWORD *)((char *)&v33[2] + 10) = *(_DWORD *)(BugCheckParameter2 + 1802);
  LOBYTE(v33[3]) = *(_BYTE *)(BugCheckParameter2 + 1987);
  v11 = *(_OWORD *)(BugCheckParameter2 + 1772);
  v33[0] = v9;
  v33[1] = v11;
  if ( (_WORD)v10 )
  {
    *(_QWORD *)&v33[2] = v10;
    WORD4(v33[2]) = 1024;
  }
  v12 = (_WORD)v10 != 0 ? 0x400 : 0;
  v13 = v12 | 0x10;
  if ( *(_BYTE *)(BugCheckParameter2 + 1795) )
    WORD4(v33[2]) = v12 | 0x10;
  else
    v13 = v12;
  v14 = v13 | 1;
  if ( *(_BYTE *)(BugCheckParameter2 + 1794) )
    WORD4(v33[2]) = v13 | 1;
  else
    v14 = v13;
  v15 = v14 | 0x1000;
  if ( *(_BYTE *)(BugCheckParameter2 + 1796) )
    WORD4(v33[2]) = v14 | 0x1000;
  else
    v15 = v14;
  if ( *(_BYTE *)(BugCheckParameter2 + 1797) )
    WORD4(v33[2]) = v15 | 0x2000;
  if ( *(_BYTE *)(BugCheckParameter2 + 3168) )
    HIWORD(v33[2]) = *(_WORD *)(BugCheckParameter2 + 3280);
  v16 = *(_OWORD *)(BugCheckParameter2 + 1840);
  *(_OWORD *)((char *)&v33[3] + 8) = *(_OWORD *)(BugCheckParameter2 + 1824);
  v17 = *(_OWORD *)(BugCheckParameter2 + 1856);
  *(_OWORD *)((char *)&v33[4] + 8) = v16;
  v18 = *(_OWORD *)(BugCheckParameter2 + 1872);
  *(_OWORD *)((char *)&v33[5] + 8) = v17;
  v19 = *(_OWORD *)(BugCheckParameter2 + 1888);
  *(_OWORD *)((char *)&v33[6] + 8) = v18;
  v20 = *(_OWORD *)(BugCheckParameter2 + 1904);
  *(_OWORD *)((char *)&v33[7] + 8) = v19;
  v21 = *(_OWORD *)(BugCheckParameter2 + 1920);
  *(_OWORD *)((char *)&v33[8] + 8) = v20;
  *(_QWORD *)&v20 = *(_QWORD *)(BugCheckParameter2 + 1936);
  *(_OWORD *)((char *)&v33[9] + 8) = v21;
  *((_QWORD *)&v33[10] + 1) = v20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      64,
      WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
      BugCheckParameter2);
  }
  v4 = KmclpSynchronousIoControl(BugCheckParameter2, 4112412, v33, 192, 0, 0);
  if ( v4 < 0 )
    goto LABEL_4;
  v4 = VmbusSendInterfaceQuery(BugCheckParameter2);
  if ( v4 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_4;
    }
    v24 = 65;
    goto LABEL_40;
  }
  v4 = KmclpInitializeVmbusConnection(BugCheckParameter2);
  if ( v4 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_4;
    }
    v24 = 66;
LABEL_40:
    WPP_SF_qd(v23->AttachedDevice, v24, v22, BugCheckParameter2, v4);
    goto LABEL_4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      67,
      WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
      BugCheckParameter2);
  }
  *(_DWORD *)(BugCheckParameter2 + 2200) = 3;
  v25 = _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter2 + 3296)) % 24;
  v26 = v25 + 207;
  v25 *= 2;
  *(_QWORD *)(BugCheckParameter2 + 8 * v25 + 3304) = MEMORY[0xFFFFF78000000008];
  *(_BYTE *)(BugCheckParameter2 + 16 * v26) = *(_BYTE *)(BugCheckParameter2 + 2200);
  *(_BYTE *)(BugCheckParameter2 + 8 * v25 + 3313) = *(_BYTE *)(BugCheckParameter2 + 2204);
  *(_WORD *)(BugCheckParameter2 + 8 * v25 + 3314) = *(_DWORD *)(BugCheckParameter2 + 2216);
  *(_WORD *)(BugCheckParameter2 + 8 * v25 + 3316) = 2609;
  v4 = KmclpServerOpenChannel(BugCheckParameter2, v25, v22);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 68, v5, BugCheckParameter2, v4);
  }
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741661 )
  {
    v4 = 0;
    goto LABEL_5;
  }
LABEL_4:
  KmclpDisableClosedChannel(BugCheckParameter2);
LABEL_5:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 69, v5, BugCheckParameter2, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001c758  push    rbp
0x14001c75a  push    rbx
0x14001c75b  push    rsi
0x14001c75c  push    rdi
0x14001c75d  push    r12
0x14001c75f  push    r13
0x14001c761  push    r14
0x14001c763  push    r15
0x14001c765  lea     rbp, [rsp-178h]
0x14001c76d  sub     rsp, 278h
0x14001c774  mov     rax, cs:__security_cookie
0x14001c77b  xor     rax, rsp
0x14001c77e  mov     [rbp+1B0h+var_50], rax
0x14001c785  movups  xmm0, xmmword ptr cs:aDosdevicesVmbu
0x14001c78c  movzx   eax, word ptr cs:aDosdevicesVmbu+30h
0x14001c793  mov     r14, rcx
0x14001c796  movups  xmm1, xmmword ptr cs:aDosdevicesVmbu+10h
0x14001c79d  mov     [rbp+1B0h+var_E0], ax
0x14001c7a4  lea     rax, [rbp+1B0h+var_D0]
0x14001c7ab  movups  [rbp+1B0h+var_110], xmm0
0x14001c7b2  xor     r15d, r15d
0x14001c7b5  mov     [rbp+1B0h+Destination.Buffer], rax
0x14001c7b9  movups  xmm0, xmmword ptr cs:aDosdevicesVmbu+20h
0x14001c7c0  xor     eax, eax
0x14001c7c2  mov     qword ptr [rsp+2B0h+Destination.Length], 7E0000h
0x14001c7cb  xor     edx, edx; Val
0x14001c7cd  mov     [rbp+1B0h+FsInformation], r15
0x14001c7d1  movups  [rbp+1B0h+var_F0], xmm0
0x14001c7d8  mov     [rsp+2B0h+FileHandle], r15
0x14001c7dd  mov     r8d, 0C0h; Size
0x14001c7e3  xorps   xmm0, xmm0
0x14001c7e6  lea     rcx, [rbp+1B0h+var_1D0]; void *
0x14001c7ea  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.ObjectName], xmm0
0x14001c7ee  movups  xmmword ptr [rbp+1B0h+ObjectAttributes+1Ch], xmm0
0x14001c7f2  movups  [rbp+1B0h+var_100], xmm1
0x14001c7f9  movups  xmmword ptr [rbp+1B0h+IoStatusBlock], xmm0
0x14001c7fd  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.Length], xmm0
0x14001c801  call    memset
0x14001c806  movups  xmm0, xmmword ptr [r14+6DCh]
0x14001c80e  mov     rcx, [r14+7A0h]; Handle
0x14001c815  lea     r12d, [r15+1]
0x14001c819  lea     r13, WPP_GLOBAL_Control
0x14001c820  movups  xmm1, xmmword ptr [r14+6ECh]
0x14001c828  movdqu  xmmword ptr [r14+0AB0h], xmm0
0x14001c831  movdqu  xmmword ptr [r14+0AC0h], xmm1
0x14001c83a  test    rcx, rcx
0x14001c83d  jz      loc_14001C91A
0x14001c843  call    cs:__imp_ObIsKernelHandle
0x14001c84a  nop     dword ptr [rax+rax+00h]
0x14001c84f  test    al, al
0x14001c851  jnz     short loc_14001C8B5
0x14001c853  mov     ebx, 0C000000Dh
0x14001c858  mov     rcx, r14; BugCheckParameter2
0x14001c85b  call    KmclpDisableClosedChannel
0x14001c860  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c867  cmp     rcx, r13
0x14001c86a  jz      short loc_14001C88F
0x14001c86c  mov     eax, [rcx+2Ch]
0x14001c86f  test    r12b, al
0x14001c872  jz      short loc_14001C88F
0x14001c874  cmp     byte ptr [rcx+29h], 4
0x14001c878  jb      short loc_14001C88F
0x14001c87a  mov     rcx, [rcx+18h]
0x14001c87e  mov     edx, 45h ; 'E'
0x14001c883  mov     r9, r14
0x14001c886  mov     [rsp+2B0h+FsInformationClass], ebx
0x14001c88a  call    WPP_SF_qd
0x14001c88f  mov     eax, ebx
0x14001c891  mov     rcx, [rbp+1B0h+var_50]
0x14001c898  xor     rcx, rsp; StackCookie
0x14001c89b  call    __security_check_cookie
0x14001c8a0  add     rsp, 278h
0x14001c8a7  pop     r15
0x14001c8a9  pop     r14
0x14001c8ab  pop     r13
0x14001c8ad  pop     r12
0x14001c8af  pop     rdi
0x14001c8b0  pop     rsi
0x14001c8b1  pop     rbx
0x14001c8b2  pop     rbp
0x14001c8b3  retn
0x14001c8b5  mov     rcx, [r14+7A0h]; FileHandle
0x14001c8bc  lea     r8, [rbp+1B0h+FsInformation]; FsInformation
0x14001c8c0  mov     r9d, 8; Length
0x14001c8c6  mov     [rsp+2B0h+FsInformationClass], 4; FsInformationClass
0x14001c8ce  lea     rdx, [rbp+1B0h+IoStatusBlock]; IoStatusBlock
0x14001c8d2  call    cs:__imp_ZwQueryVolumeInformationFile
0x14001c8d9  nop     dword ptr [rax+rax+00h]
0x14001c8de  mov     ebx, eax
0x14001c8e0  test    eax, eax
0x14001c8e2  js      loc_14001C858
0x14001c8e8  cmp     dword ptr [rbp+1B0h+FsInformation], 3Eh ; '>'
0x14001c8ec  jnz     loc_14001C853
0x14001c8f2  lea     rdx, Source
0x14001c8f9  lea     rcx, [rsp+2B0h+Destination]; Destination
0x14001c8fe  call    cs:__imp_RtlAppendUnicodeToString
0x14001c905  nop     dword ptr [rax+rax+00h]
0x14001c90a  mov     rax, [r14+7A0h]
0x14001c911  mov     [rbp+1B0h+ObjectAttributes.RootDirectory], rax
0x14001c915  jmp     loc_14001C9B9
0x14001c91a  movzx   ecx, byte ptr [r14+71Eh]
0x14001c922  movzx   edx, byte ptr [r14+71Dh]
0x14001c92a  movzx   r8d, byte ptr [r14+71Ch]
0x14001c932  movzx   r9d, byte ptr [r14+71Bh]
0x14001c93a  movzx   eax, byte ptr [r14+71Fh]
0x14001c942  movzx   r10d, byte ptr [r14+71Ah]
0x14001c94a  movzx   r11d, byte ptr [r14+719h]
0x14001c952  movzx   ebx, byte ptr [r14+718h]
0x14001c95a  movzx   edi, word ptr [r14+716h]
0x14001c962  movzx   esi, word ptr [r14+714h]
0x14001c96a  mov     [rsp+2B0h+var_248], eax
0x14001c96e  mov     [rsp+2B0h+var_250], ecx
0x14001c972  lea     rcx, [rsp+2B0h+Destination]; DestinationString
0x14001c977  mov     [rsp+2B0h+var_258], edx
0x14001c97b  lea     rdx, aS08lx04x04x02x
0x14001c982  mov     [rsp+2B0h+var_260], r8d
0x14001c987  lea     r8, [rbp+1B0h+var_110]
0x14001c98e  mov     [rsp+2B0h+var_268], r9d
0x14001c993  mov     r9d, [r14+710h]
0x14001c99a  mov     [rsp+2B0h+var_270], r10d
0x14001c99f  mov     [rsp+2B0h+var_278], r11d
0x14001c9a4  mov     [rsp+2B0h+var_280], ebx
0x14001c9a8  mov     [rsp+2B0h+OpenOptions], edi
0x14001c9ac  mov     [rsp+2B0h+FsInformationClass], esi
0x14001c9b0  call    RtlUnicodeStringPrintf
0x14001c9b5  mov     [rbp+1B0h+ObjectAttributes.RootDirectory], r15
0x14001c9b9  xorps   xmm0, xmm0
0x14001c9bc  mov     [rbp+1B0h+ObjectAttributes.Attributes], 240h
0x14001c9c3  lea     rax, [rsp+2B0h+Destination]
0x14001c9c8  mov     [rbp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x14001c9cf  mov     edi, 40h ; '@'
0x14001c9d4  mov     [rbp+1B0h+ObjectAttributes.ObjectName], rax
0x14001c9d8  mov     [rsp+2B0h+OpenOptions], edi; OpenOptions
0x14001c9dc  lea     r9, [rbp+1B0h+IoStatusBlock]; IoStatusBlock
0x14001c9e0  lea     r8, [rbp+1B0h+ObjectAttributes]; ObjectAttributes
0x14001c9e4  mov     [rsp+2B0h+FsInformationClass], r15d; ShareAccess
0x14001c9e9  mov     edx, 1F01FFh; DesiredAccess
0x14001c9ee  lea     rcx, [rsp+2B0h+FileHandle]; FileHandle
0x14001c9f3  movdqu  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001c9f8  call    cs:__imp_ZwOpenFile
0x14001c9ff  nop     dword ptr [rax+rax+00h]
0x14001ca04  mov     ebx, eax
0x14001ca06  test    eax, eax
0x14001ca08  js      loc_14001C858
0x14001ca0e  mov     r8, cs:__imp_IoFileObjectType
0x14001ca15  lea     rax, [rbp+1B0h+Object]
0x14001ca19  mov     rcx, [rsp+2B0h+FileHandle]; Handle
0x14001ca1e  xor     r9d, r9d; AccessMode
0x14001ca21  mov     qword ptr [rsp+2B0h+OpenOptions], r15; HandleInformation
0x14001ca26  xor     edx, edx; DesiredAccess
0x14001ca28  mov     [rbp+1B0h+Object], r15
0x14001ca2c  mov     r8, [r8]; ObjectType
0x14001ca2f  mov     qword ptr [rsp+2B0h+FsInformationClass], rax; Object
0x14001ca34  call    cs:__imp_ObReferenceObjectByHandle
0x14001ca3b  nop     dword ptr [rax+rax+00h]
0x14001ca40  mov     rax, [rbp+1B0h+Object]
0x14001ca44  mov     rcx, [rsp+2B0h+FileHandle]; Handle
0x14001ca49  mov     [r14+0AA8h], rax
0x14001ca50  call    cs:__imp_ZwClose
0x14001ca57  nop     dword ptr [rax+rax+00h]
0x14001ca5c  mov     rcx, [r14+0AA8h]; FileObject
0x14001ca63  call    cs:__imp_IoGetRelatedDeviceObject
0x14001ca6a  nop     dword ptr [rax+rax+00h]
0x14001ca6f  mov     rcx, rax; Object
0x14001ca72  mov     [r14+0AA0h], rax
0x14001ca79  call    cs:__imp_ObfReferenceObject
0x14001ca80  nop     dword ptr [rax+rax+00h]
0x14001ca85  xor     edx, edx; Val
0x14001ca87  lea     rcx, [rbp+1B0h+var_1D0]; void *
0x14001ca8b  mov     r8d, 0C0h; Size
0x14001ca91  call    memset
0x14001ca96  movzx   eax, word ptr [r14+70Ah]
0x14001ca9e  mov     edx, 400h
0x14001caa3  movups  xmm0, xmmword ptr [r14+6DCh]
0x14001caab  movzx   ecx, word ptr [r14+708h]
0x14001cab3  mov     [rbp+1B0h+var_1A6], ax
0x14001cab7  movzx   eax, word ptr [r14+70Ch]
0x14001cabf  mov     [rbp+1B0h+var_1A4], ax
0x14001cac3  mov     al, [r14+7C3h]
0x14001caca  mov     [rbp+1B0h+var_1A0], al
0x14001cacd  movups  xmm1, xmmword ptr [r14+6ECh]
0x14001cad5  movdqu  [rbp+1B0h+var_1D0], xmm0
0x14001cada  movdqu  [rbp+1B0h+var_1C0], xmm1
0x14001cadf  test    cx, cx
0x14001cae2  jz      short loc_14001CAEC
0x14001cae4  mov     [rbp+1B0h+var_1B0], rcx
0x14001cae8  mov     [rbp+1B0h+var_1A8], dx
0x14001caec  xor     eax, eax
0x14001caee  cmp     ax, cx
0x14001caf1  sbb     cx, cx
0x14001caf4  and     cx, dx
0x14001caf7  mov     dl, [r14+703h]
0x14001cafe  movzx   eax, cx
0x14001cb01  or      ax, 10h
0x14001cb05  test    dl, dl
0x14001cb07  jz      short loc_14001CB0D
0x14001cb09  mov     [rbp+1B0h+var_1A8], ax
0x14001cb0d  mov     dl, [r14+702h]
0x14001cb14  cmovz   ax, cx
0x14001cb18  movzx   ecx, ax
0x14001cb1b  or      cx, r12w
0x14001cb1f  test    dl, dl
0x14001cb21  jz      short loc_14001CB27
0x14001cb23  mov     [rbp+1B0h+var_1A8], cx
0x14001cb27  mov     dl, [r14+704h]
0x14001cb2e  cmovz   cx, ax
0x14001cb32  movzx   eax, cx
0x14001cb35  or      ax, 1000h
0x14001cb39  test    dl, dl
0x14001cb3b  jz      short loc_14001CB41
0x14001cb3d  mov     [rbp+1B0h+var_1A8], ax
0x14001cb41  cmovz   ax, cx
0x14001cb45  cmp     [r14+705h], r15b
0x14001cb4c  jz      short loc_14001CB56
0x14001cb4e  or      ax, 2000h
0x14001cb52  mov     [rbp+1B0h+var_1A8], ax
0x14001cb56  cmp     [r14+0C60h], r15b
0x14001cb5d  jz      short loc_14001CB6B
0x14001cb5f  movzx   eax, word ptr [r14+0CD0h]
0x14001cb67  mov     [rbp+1B0h+var_1A2], ax
0x14001cb6b  movups  xmm0, xmmword ptr [r14+720h]
0x14001cb73  movups  xmm1, xmmword ptr [r14+730h]
0x14001cb7b  movups  [rbp+1B0h+var_198], xmm0
0x14001cb7f  movups  xmm0, xmmword ptr [r14+740h]
0x14001cb87  movups  [rbp+1B0h+var_188], xmm1
0x14001cb8b  movups  xmm1, xmmword ptr [r14+750h]
0x14001cb93  movups  [rbp+1B0h+var_178], xmm0
0x14001cb97  movups  xmm0, xmmword ptr [r14+760h]
0x14001cb9f  movups  [rbp+1B0h+var_168], xmm1
0x14001cba3  movups  xmm1, xmmword ptr [r14+770h]
0x14001cbab  movups  [rbp+1B0h+var_158], xmm0
0x14001cbaf  movups  xmm0, xmmword ptr [r14+780h]
0x14001cbb7  movups  [rbp+1B0h+var_148], xmm1
0x14001cbbb  movsd   xmm1, qword ptr [r14+790h]
0x14001cbc4  movups  [rbp+1B0h+var_138], xmm0
0x14001cbc8  movsd   [rbp+1B0h+var_128], xmm1
0x14001cbd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbd7  cmp     rcx, r13
0x14001cbda  jz      short loc_14001CBFF
0x14001cbdc  mov     eax, [rcx+2Ch]
0x14001cbdf  test    r12b, al
0x14001cbe2  jz      short loc_14001CBFF
0x14001cbe4  cmp     byte ptr [rcx+29h], 4
0x14001cbe8  jb      short loc_14001CBFF
0x14001cbea  mov     rcx, [rcx+18h]
0x14001cbee  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14001cbf5  mov     edx, edi
0x14001cbf7  mov     r9, r14
0x14001cbfa  call    WPP_SF_q
0x14001cbff  mov     [rsp+2B0h+OpenOptions], r15d
0x14001cc04  lea     r8, [rbp+1B0h+var_1D0]
0x14001cc08  mov     r9d, 0C0h
0x14001cc0e  mov     qword ptr [rsp+2B0h+FsInformationClass], r15
0x14001cc13  mov     edx, 3EC01Ch
0x14001cc18  mov     rcx, r14
0x14001cc1b  call    KmclpSynchronousIoControl
0x14001cc20  mov     ebx, eax
0x14001cc22  test    eax, eax
0x14001cc24  js      loc_14001C858
0x14001cc2a  mov     rcx, r14
0x14001cc2d  call    VmbusSendInterfaceQuery
0x14001cc32  mov     ebx, eax
0x14001cc34  test    eax, eax
0x14001cc36  jns     short loc_14001CC78
0x14001cc38  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc3f  cmp     rcx, r13
0x14001cc42  jz      loc_14001C858
0x14001cc48  mov     eax, [rcx+2Ch]
0x14001cc4b  test    r12b, al
0x14001cc4e  jz      loc_14001C858
0x14001cc54  cmp     byte ptr [rcx+29h], 2
0x14001cc58  jb      loc_14001C858
0x14001cc5e  mov     edx, 41h ; 'A'
0x14001cc63  mov     rcx, [rcx+18h]
0x14001cc67  mov     r9, r14
0x14001cc6a  mov     [rsp+2B0h+FsInformationClass], ebx
0x14001cc6e  call    WPP_SF_qd
0x14001cc73  jmp     loc_14001C858
0x14001cc78  mov     rcx, r14
0x14001cc7b  call    KmclpInitializeVmbusConnection
0x14001cc80  mov     ebx, eax
0x14001cc82  test    eax, eax
0x14001cc84  jns     short loc_14001CCB3
0x14001cc86  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc8d  cmp     rcx, r13
0x14001cc90  jz      loc_14001C858
0x14001cc96  mov     eax, [rcx+2Ch]
0x14001cc99  test    r12b, al
0x14001cc9c  jz      loc_14001C858
0x14001cca2  cmp     byte ptr [rcx+29h], 2
0x14001cca6  jb      loc_14001C858
0x14001ccac  mov     edx, 42h ; 'B'
0x14001ccb1  jmp     short loc_14001CC63
0x14001ccb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ccba  cmp     rcx, r13
0x14001ccbd  jz      short loc_14001CCE5
0x14001ccbf  mov     eax, [rcx+2Ch]
0x14001ccc2  test    r12b, al
0x14001ccc5  jz      short loc_14001CCE5
0x14001ccc7  cmp     byte ptr [rcx+29h], 4
  ... truncated ...
```
