# BiCreatePartitionDevice

- ea: `0x1400306fc`
- end: `0x140030b33`
- name: `BiCreatePartitionDevice`
- size: `1079`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002fc98`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x14000db18`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002fc98`
- `0x140030528`
- `0x1400306fc`
- `0x140030b3c`
- `0x140030e14`
- `0x140031330`
- `0x1400314d0`
- `0x140031774`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400309f5`
- `ntoskrnl!ExAllocatePool2` at `0x1400309f5`
- `ntoskrnl!wcschr` at `0x14003082e`
- `ntoskrnl!wcschr` at `0x14003082e`
- `ntoskrnl!_wcsnicmp` at `0x140030815`
- `ntoskrnl!_wcsnicmp` at `0x140030874`
- `ntoskrnl!_wcsnicmp` at `0x140030815`
- `ntoskrnl!_wcsnicmp` at `0x140030874`

## pseudocode

```c
__int64 __fastcall BiCreatePartitionDevice(PCWSTR SourceString, int a2, _QWORD *a3, _DWORD *a4)
{
  PVOID v5; // r12
  WCHAR *v6; // r14
  unsigned int v7; // esi
  PVOID v8; // r15
  int PhysicalDriveName; // eax
  NTSTATUS DriveLayoutInformation; // ebx
  const wchar_t *PartitionVhdFilePath; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  void *v14; // rax
  int FileDeviceElement; // eax
  unsigned int v16; // r13d
  __int64 v17; // rdx
  _OWORD *Pool2; // rax
  _OWORD *v19; // rsi
  size_t v20; // r8
  __int128 v21; // xmm1
  int v22; // eax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  _DWORD *v25; // rcx
  char v27; // [rsp+30h] [rbp-D0h]
  unsigned int Size; // [rsp+38h] [rbp-C8h]
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+50h] [rbp-B0h]
  PVOID v31; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v34; // [rsp+70h] [rbp-90h]
  _DWORD *v35; // [rsp+78h] [rbp-88h]
  _OWORD v36[5]; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v40[9]; // [rsp+120h] [rbp+20h] BYREF

  v34 = a3;
  v30 = a2;
  v35 = a4;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v40, 0, sizeof(v40));
  FileHandle = 0;
  DestinationString = 0;
  Src = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  Size = 0;
  v7 = 0;
  v8 = 0;
  v31 = 0;
  memset(v36, 0, 0x48u);
  if ( (int)BiGetDriveLayoutInformation(SourceString) < 0 )
  {
    PhysicalDriveName = BiGetPhysicalDriveName(SourceString, &v31);
    v8 = v31;
    DriveLayoutInformation = PhysicalDriveName;
    if ( PhysicalDriveName < 0 )
      goto LABEL_43;
    DriveLayoutInformation = BiGetDriveLayoutInformation((PCWSTR)v31);
    if ( DriveLayoutInformation < 0 )
      goto LABEL_43;
  }
  v27 = 0;
  if ( (v30 & 0x40) == 0 )
  {
    PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(SourceString);
    v6 = (WCHAR *)PartitionVhdFilePath;
    if ( PartitionVhdFilePath )
    {
      if ( !_wcsnicmp(PartitionVhdFilePath, L"\\Device\\HarddiskVolume", 0x16u) )
      {
        v12 = wcschr(v6 + 22, 0x5Cu);
        v13 = v12;
        if ( v12 )
        {
          *v12 = 0;
          v14 = (void *)BiGetPartitionVhdFilePath(v6);
          *v13 = 92;
          if ( v14 )
            ExFreePoolWithTag_0(v14, 0x4B444342u);
        }
      }
      if ( _wcsnicmp(v6, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}", 0x35u) )
      {
        FileDeviceElement = BiCreateFileDeviceElement(v6);
        v5 = P;
        DriveLayoutInformation = FileDeviceElement;
        if ( FileDeviceElement < 0 )
          goto LABEL_41;
        DriveLayoutInformation = BiConvertNtDeviceToBootEnvironment(P, 0, 64, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_41;
      }
      else
      {
        DriveLayoutInformation = BiCreateVhdRamdiskBootDevice(v6, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_43;
        v27 = 1;
      }
      LODWORD(v36[2]) = 6;
      v7 = *((_DWORD *)Src + 2);
      Size = v7;
    }
  }
  if ( MEMORY[0] )
  {
    if ( MEMORY[0] != 1 )
    {
LABEL_40:
      DriveLayoutInformation = -1073741811;
      goto LABEL_41;
    }
    DWORD2(v36[2]) = MEMORY[8];
    DWORD1(v36[3]) = MEMORY[0x14];
    DWORD1(v36[2]) = 0;
    *(_QWORD *)((char *)&v36[2] + 12) = MEMORY[0xC];
  }
  else
  {
    DWORD2(v36[2]) = MEMORY[8];
    DWORD1(v36[2]) = 1;
  }
  RtlInitUnicodeString_0(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DriveLayoutInformation = ZwOpenFile_0(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutInformation >= 0 )
  {
    DriveLayoutInformation = BiGetPartitionInformation(FileHandle, MEMORY[0]);
    if ( DriveLayoutInformation >= 0 )
    {
      if ( !LODWORD(v40[0]) )
      {
        *(_QWORD *)&v36[1] = *((_QWORD *)&v40[0] + 1);
LABEL_27:
        v16 = v7 + 56;
        v17 = 72;
        if ( v7 + 56 > 0x48 )
          v17 = v7 + 56;
        Pool2 = (_OWORD *)ExAllocatePool2(258, v17, 1262764866);
        v19 = Pool2;
        if ( Pool2 )
        {
          v20 = 72;
          if ( v16 > 0x48 )
            v20 = v16;
          memset(Pool2, 0, v20);
          v21 = v36[1];
          v22 = 72;
          LODWORD(v36[0]) = 6;
          if ( v16 > 0x48 )
            v22 = v16;
          DWORD2(v36[0]) = v22;
          *v19 = v36[0];
          v23 = v36[2];
          v19[1] = v21;
          v24 = v36[3];
          v19[2] = v23;
          *(_QWORD *)&v23 = *(_QWORD *)&v36[4];
          v19[3] = v24;
          *((_QWORD *)v19 + 8) = v23;
          if ( v6 )
            memmove((char *)v19 + 56, Src, Size);
          if ( v27 )
            *((_DWORD *)v19 + 1) |= 8u;
          v25 = v35;
          *v34 = v19;
          *v25 = MEMORY[4];
        }
        else
        {
          DriveLayoutInformation = -1073741670;
        }
        goto LABEL_41;
      }
      if ( LODWORD(v40[0]) == 1 )
      {
        v36[1] = v40[3];
        goto LABEL_27;
      }
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v5 )
    ExFreePoolWithTag_0(v5, 0x4B444342u);
LABEL_43:
  if ( Src )
    ExFreePoolWithTag_0(Src, 0x4B444342u);
  if ( v6 )
    ExFreePoolWithTag_0(v6, 0x4B444342u);
  if ( v8 )
    ExFreePoolWithTag_0(v8, 0x4B444342u);
  if ( FileHandle )
    ZwClose_0(FileHandle);
  return (unsigned int)DriveLayoutInformation;
}

```

## disassembly

```asm
0x1400306fc  mov     [rsp-8+arg_8], rbx
0x140030701  push    rbp
0x140030702  push    rsi
0x140030703  push    rdi
0x140030704  push    r12
0x140030706  push    r13
0x140030708  push    r14
0x14003070a  push    r15
0x14003070c  lea     rbp, [rsp-0B0h]
0x140030714  sub     rsp, 1B0h
0x14003071b  xorps   xmm0, xmm0
0x14003071e  mov     [rsp+1E0h+var_170], r8
0x140030723  mov     [rsp+1E0h+var_190], edx
0x140030727  mov     r13, rcx
0x14003072a  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x14003072e  xor     eax, eax
0x140030730  mov     [rsp+1E0h+var_168], r9
0x140030735  xor     edx, edx; Val
0x140030737  lea     rcx, [rbp+0E0h+var_C0]; void *
0x14003073b  mov     r8d, 90h; Size
0x140030741  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x140030745  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x140030749  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x14003074d  call    memset
0x140030752  xor     edi, edi
0x140030754  lea     rcx, [rbp+0E0h+var_160]; void *
0x140030758  xorps   xmm0, xmm0
0x14003075b  mov     [rsp+1E0h+var_1A0], rdi
0x140030760  xor     edx, edx; Val
0x140030762  mov     [rsp+1E0h+FileHandle], rdi
0x140030767  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x14003076b  lea     r8d, [rdi+48h]; Size
0x14003076f  mov     [rsp+1E0h+Src], rdi
0x140030774  mov     r12d, edi
0x140030777  mov     [rsp+1E0h+P], rdi
0x14003077c  mov     r14d, edi
0x14003077f  mov     dword ptr [rsp+1E0h+Size], edi
0x140030783  mov     esi, edi
0x140030785  mov     [rsp+1E0h+var_1AC], edi
0x140030789  mov     r15d, edi
0x14003078c  mov     [rsp+1E0h+var_188], rdi
0x140030791  call    memset
0x140030796  lea     rdx, [rsp+1E0h+var_1A0]
0x14003079b  mov     rcx, r13; SourceString
0x14003079e  call    BiGetDriveLayoutInformation
0x1400307a3  test    eax, eax
0x1400307a5  jns     short loc_1400307DC
0x1400307a7  lea     rdx, [rsp+1E0h+var_188]
0x1400307ac  mov     rcx, r13
0x1400307af  call    BiGetPhysicalDriveName
0x1400307b4  mov     r15, [rsp+1E0h+var_188]
0x1400307b9  mov     ebx, eax
0x1400307bb  test    eax, eax
0x1400307bd  js      short loc_1400307D2
0x1400307bf  lea     rdx, [rsp+1E0h+var_1A0]
0x1400307c4  mov     rcx, r15; SourceString
0x1400307c7  call    BiGetDriveLayoutInformation
0x1400307cc  mov     ebx, eax
0x1400307ce  test    eax, eax
0x1400307d0  jns     short loc_1400307DC
0x1400307d2  mov     rdi, [rsp+1E0h+var_1A0]
0x1400307d7  jmp     loc_140030ABC
0x1400307dc  test    byte ptr [rsp+1E0h+var_190], 40h
0x1400307e1  mov     [rsp+1E0h+var_1B0], dil
0x1400307e6  mov     rdi, [rsp+1E0h+var_1A0]
0x1400307eb  jnz     loc_1400308F4
0x1400307f1  mov     rcx, r13; SourceString
0x1400307f4  call    BiGetPartitionVhdFilePath
0x1400307f9  mov     r14, rax
0x1400307fc  test    rax, rax
0x1400307ff  jz      loc_1400308F4
0x140030805  mov     r8d, 16h; MaxCount
0x14003080b  lea     rdx, aDeviceHarddisk_1; "\\Device\\HarddiskVolume"
0x140030812  mov     rcx, rax; Str1
0x140030815  call    cs:__imp__wcsnicmp
0x14003081c  nop     dword ptr [rax+rax+00h]
0x140030821  test    eax, eax
0x140030823  jnz     short loc_140030864
0x140030825  lea     esi, [rax+5Ch]
0x140030828  mov     edx, esi; Ch
0x14003082a  lea     rcx, [r14+2Ch]; Str
0x14003082e  call    cs:__imp_wcschr
0x140030835  nop     dword ptr [rax+rax+00h]
0x14003083a  mov     rbx, rax
0x14003083d  test    rax, rax
0x140030840  jz      short loc_140030864
0x140030842  xor     ecx, ecx
0x140030844  mov     [rax], cx
0x140030847  mov     rcx, r14; SourceString
0x14003084a  call    BiGetPartitionVhdFilePath
0x14003084f  mov     [rbx], si
0x140030852  test    rax, rax
0x140030855  jz      short loc_140030864
0x140030857  mov     edx, 4B444342h; Tag
0x14003085c  mov     rcx, rax; P
0x14003085f  call    ExFreePoolWithTag_0
0x140030864  mov     r8d, 35h ; '5'; MaxCount
0x14003086a  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140030871  mov     rcx, r14; Str1
0x140030874  call    cs:__imp__wcsnicmp
0x14003087b  nop     dword ptr [rax+rax+00h]
0x140030880  mov     rcx, r14; Src
0x140030883  test    eax, eax
0x140030885  jnz     short loc_1400308A2
0x140030887  lea     rdx, [rsp+1E0h+Src]
0x14003088c  call    BiCreateVhdRamdiskBootDevice
0x140030891  mov     ebx, eax
0x140030893  test    eax, eax
0x140030895  js      loc_140030ABC
0x14003089b  mov     [rsp+1E0h+var_1B0], 1
0x1400308a0  jmp     short loc_1400308E1
0x1400308a2  lea     r8, [rsp+1E0h+var_1AC]
0x1400308a7  lea     rdx, [rsp+1E0h+P]
0x1400308ac  call    BiCreateFileDeviceElement
0x1400308b1  mov     r12, [rsp+1E0h+P]
0x1400308b6  mov     ebx, eax
0x1400308b8  test    eax, eax
0x1400308ba  js      loc_140030AAA
0x1400308c0  mov     edx, [rsp+1E0h+var_1AC]
0x1400308c4  lea     r9, [rsp+1E0h+Src]
0x1400308c9  mov     r8d, 40h ; '@'
0x1400308cf  mov     rcx, r12
0x1400308d2  call    BiConvertNtDeviceToBootEnvironment
0x1400308d7  mov     ebx, eax
0x1400308d9  test    eax, eax
0x1400308db  js      loc_140030AAA
0x1400308e1  mov     rax, [rsp+1E0h+Src]
0x1400308e6  mov     dword ptr [rbp+0E0h+var_140], 6
0x1400308ed  mov     esi, [rax+8]
0x1400308f0  mov     dword ptr [rsp+1E0h+Size], esi
0x1400308f4  mov     eax, [rdi]
0x1400308f6  test    eax, eax
0x1400308f8  jnz     short loc_140030909
0x1400308fa  mov     eax, [rdi+8]
0x1400308fd  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x140030900  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x140030907  jmp     short loc_14003092F
0x140030909  cmp     eax, 1
0x14003090c  jnz     loc_140030AA5
0x140030912  mov     eax, [rdi+8]
0x140030915  movsd   xmm0, qword ptr [rdi+0Ch]
0x14003091a  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x14003091d  mov     eax, [rdi+14h]
0x140030920  mov     [rbp+0E0h+var_12C], eax
0x140030923  mov     dword ptr [rbp+0E0h+var_140+4], 0
0x14003092a  movsd   qword ptr [rbp+0E0h+var_140+0Ch], xmm0
0x14003092f  mov     rdx, r13; SourceString
0x140030932  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x140030936  call    RtlInitUnicodeString_0
0x14003093b  lea     rax, [rbp+0E0h+DestinationString]
0x14003093f  mov     [rsp+1E0h+OpenOptions], 20h ; ' '; OpenOptions
0x140030947  xorps   xmm0, xmm0
0x14003094a  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x14003094e  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x140030952  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x140030959  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x14003095d  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], 0
0x140030965  mov     edx, 80100000h; DesiredAccess
0x14003096a  mov     [rbp+0E0h+ObjectAttributes.Attributes], 240h
0x140030971  lea     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x140030976  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x14003097e  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140030983  call    ZwOpenFile_0
0x140030988  mov     ebx, eax
0x14003098a  test    eax, eax
0x14003098c  js      loc_140030AAA
0x140030992  mov     edx, [rdi]; InputBufferLength
0x140030994  lea     r8, [rbp+0E0h+var_C0]
0x140030998  mov     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x14003099d  call    BiGetPartitionInformation
0x1400309a2  mov     ebx, eax
0x1400309a4  test    eax, eax
0x1400309a6  js      loc_140030AAA
0x1400309ac  mov     eax, [rbp+0E0h+var_C0]
0x1400309af  test    eax, eax
0x1400309b1  jnz     short loc_1400309BD
0x1400309b3  mov     rax, [rbp+0E0h+var_B8]
0x1400309b7  mov     qword ptr [rbp+0E0h+var_150], rax
0x1400309bb  jmp     short loc_1400309D6
0x1400309bd  cmp     eax, 1
0x1400309c0  jnz     loc_140030AA5
0x1400309c6  mov     rax, qword ptr [rbp+0E0h+var_90]
0x1400309ca  mov     qword ptr [rbp+0E0h+var_150], rax
0x1400309ce  mov     rax, qword ptr [rbp+0E0h+var_90+8]
0x1400309d2  mov     qword ptr [rbp+0E0h+var_150+8], rax
0x1400309d6  mov     ecx, 48h ; 'H'
0x1400309db  lea     r13d, [rsi+38h]
0x1400309df  cmp     r13d, ecx
0x1400309e2  mov     eax, r13d
0x1400309e5  mov     edx, ecx
0x1400309e7  mov     r8d, 4B444342h
0x1400309ed  cmova   edx, eax
0x1400309f0  mov     ecx, 102h
0x1400309f5  call    cs:__imp_ExAllocatePool2
0x1400309fc  nop     dword ptr [rax+rax+00h]
0x140030a01  mov     rsi, rax
0x140030a04  test    rax, rax
0x140030a07  jnz     short loc_140030A13
0x140030a09  mov     ebx, 0C000009Ah
0x140030a0e  jmp     loc_140030AAA
0x140030a13  mov     eax, 48h ; 'H'
0x140030a18  mov     rcx, rsi; void *
0x140030a1b  mov     r8d, eax
0x140030a1e  cmp     r13d, eax
0x140030a21  mov     eax, r13d
0x140030a24  cmova   r8d, eax; Size
0x140030a28  xor     edx, edx; Val
0x140030a2a  call    memset
0x140030a2f  movaps  xmm1, [rbp+0E0h+var_150]
0x140030a33  mov     eax, 48h ; 'H'
0x140030a38  cmp     r13d, eax
0x140030a3b  mov     dword ptr [rbp+0E0h+var_160], 6
0x140030a42  cmova   eax, r13d
0x140030a46  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x140030a49  movaps  xmm0, [rbp+0E0h+var_160]
0x140030a4d  movups  xmmword ptr [rsi], xmm0
0x140030a50  movaps  xmm0, [rbp+0E0h+var_140]
0x140030a54  movups  xmmword ptr [rsi+10h], xmm1
0x140030a58  movaps  xmm1, xmmword ptr [rbp-50h]
0x140030a5c  movups  xmmword ptr [rsi+20h], xmm0
0x140030a60  movsd   xmm0, [rbp+0E0h+var_120]
0x140030a65  movups  xmmword ptr [rsi+30h], xmm1
0x140030a69  movsd   qword ptr [rsi+40h], xmm0
0x140030a6e  test    r14, r14
0x140030a71  jz      short loc_140030A86
0x140030a73  mov     r8d, dword ptr [rsp+1E0h+Size]; Size
0x140030a78  lea     rcx, [rsi+38h]; void *
0x140030a7c  mov     rdx, [rsp+1E0h+Src]; Src
0x140030a81  call    memmove
0x140030a86  cmp     [rsp+1E0h+var_1B0], 0
0x140030a8b  jz      short loc_140030A91
0x140030a8d  or      dword ptr [rsi+4], 8
0x140030a91  mov     rax, [rsp+1E0h+var_170]
0x140030a96  mov     rcx, [rsp+1E0h+var_168]
0x140030a9b  mov     [rax], rsi
0x140030a9e  mov     eax, [rdi+4]
0x140030aa1  mov     [rcx], eax
0x140030aa3  jmp     short loc_140030AAA
0x140030aa5  mov     ebx, 0C000000Dh
0x140030aaa  test    r12, r12
0x140030aad  jz      short loc_140030ABC
0x140030aaf  mov     edx, 4B444342h; Tag
0x140030ab4  mov     rcx, r12; P
0x140030ab7  call    ExFreePoolWithTag_0
0x140030abc  mov     rcx, [rsp+1E0h+Src]; P
0x140030ac1  test    rcx, rcx
0x140030ac4  jz      short loc_140030AD0
0x140030ac6  mov     edx, 4B444342h; Tag
0x140030acb  call    ExFreePoolWithTag_0
0x140030ad0  test    r14, r14
0x140030ad3  jz      short loc_140030AE2
0x140030ad5  mov     edx, 4B444342h; Tag
0x140030ada  mov     rcx, r14; P
0x140030add  call    ExFreePoolWithTag_0
0x140030ae2  test    r15, r15
0x140030ae5  jz      short loc_140030AF4
0x140030ae7  mov     edx, 4B444342h; Tag
0x140030aec  mov     rcx, r15; P
0x140030aef  call    ExFreePoolWithTag_0
0x140030af4  mov     rcx, [rsp+1E0h+FileHandle]; Handle
0x140030af9  test    rcx, rcx
0x140030afc  jz      short loc_140030B03
0x140030afe  call    ZwClose_0
0x140030b03  test    rdi, rdi
0x140030b06  jz      short loc_140030B15
0x140030b08  mov     edx, 4B444342h; Tag
0x140030b0d  mov     rcx, rdi; P
0x140030b10  call    ExFreePoolWithTag_0
0x140030b15  mov     eax, ebx
0x140030b17  mov     rbx, [rsp+1E0h+arg_8]
0x140030b1f  add     rsp, 1B0h
0x140030b26  pop     r15
0x140030b28  pop     r14
0x140030b2a  pop     r13
0x140030b2c  pop     r12
0x140030b2e  pop     rdi
0x140030b2f  pop     rsi
0x140030b30  pop     rbp
0x140030b31  retn
```
