# SmpCreateVolumeDescriptor

- ea: `0x14000fed0`
- end: `0x1400101e4`
- name: `SmpCreateVolumeDescriptor`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400101ec`

## callees

- `0x1400010ec`
- `0x140003114`
- `0x14000d4c0`
- `0x14000de78`
- `0x14000e4e0`
- `0x14000e7a0`
- `0x14000e858`
- `0x14000fed0`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14000ff5c`
- `ntdll!NtOpenFile` at `0x140010021`
- `ntdll!NtOpenFile` at `0x14000ff5c`
- `ntdll!NtOpenFile` at `0x140010021`
- `ntdll!NtClose` at `0x1400101b0`
- `ntdll!NtClose` at `0x1400101bf`
- `ntdll!NtClose` at `0x1400101b0`
- `ntdll!NtClose` at `0x1400101bf`
- `ntdll!RtlAllocateHeap` at `0x140010079`
- `ntdll!RtlAllocateHeap` at `0x140010079`
- `ntdll!NtQueryVolumeInformationFile` at `0x14000ffa0`
- `ntdll!NtQueryVolumeInformationFile` at `0x14001004f`
- `ntdll!NtQueryVolumeInformationFile` at `0x14000ffa0`
- `ntdll!NtQueryVolumeInformationFile` at `0x14001004f`

## string_xrefs

- `0x14000ff75`: `SmpCreateVolumeDescriptor`
- `0x14000ffc8`: `SmpCreateVolumeDescriptor`
- `0x14001008c`: `SmpCreateVolumeDescriptor`

## pseudocode

```c
int __fastcall SmpCreateVolumeDescriptor(unsigned __int16 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  int v3; // esi
  NTSTATUS v6; // eax
  int v7; // edx
  __int64 *v8; // rax
  PWSTR Buffer; // r8
  char *Heap; // rax
  __int64 v11; // rbx
  bool v12; // zf
  _DWORD *v13; // rdi
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 *v18; // rdx
  void *FileHandle; // [rsp+30h] [rbp-39h] BYREF
  int v21; // [rsp+38h] [rbp-31h] BYREF
  int v22; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int64 FsInformation; // [rsp+40h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  __int128 v27; // [rsp+90h] [rbp+27h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+37h]

  v3 = a1;
  Handle = 0;
  FileHandle = 0;
  v28 = 0;
  FsInformation = 0;
  v22 = 0;
  v21 = 0;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  v27 = 0;
  ObjectAttributes.ObjectName = a3;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v6 = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v6 < 0 )
  {
    v7 = 1324;
LABEL_3:
    LODWORD(v8) = SmLogFailureInt((unsigned int)"SmpCreateVolumeDescriptor", v7, v3, 0, v6);
    goto LABEL_36;
  }
  v6 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
  if ( v6 < 0 )
  {
    v7 = 1341;
    goto LABEL_3;
  }
  if ( (FsInformation & 0x1700000000LL) == 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = a2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
    if ( v6 < 0 )
    {
      v7 = 1379;
      goto LABEL_3;
    }
    v6 = NtQueryVolumeInformationFile(Handle, &IoStatusBlock, &v27, 0x18u, FileFsSizeInformation);
    if ( v6 < 0 )
    {
      v7 = 1396;
      goto LABEL_3;
    }
    Heap = (char *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 8u, 0x30u);
    v11 = (__int64)Heap;
    if ( !Heap )
    {
      LODWORD(v8) = SmpLogFailure("SmpCreateVolumeDescriptor", 1411, 3221225626LL);
      goto LABEL_36;
    }
    v12 = (_WORD)v3 == (unsigned __int16)SmpOsVolumeLetter;
    v13 = Heap + 16;
    *((_WORD *)Heap + 14) = v3;
    *((_DWORD *)Heap + 6) = HIDWORD(FsInformation);
    if ( v12 )
    {
      *v13 |= 1u;
      SmpOsVolumeDescriptor = (__int64)Heap;
    }
    if ( (int)RtlQueryVolumeDiskSpeedPolicy(FileHandle, &v21) >= 0 && v21 >= 20 )
      *v13 |= 4u;
    if ( (unsigned __int8)SmpIsVolumeOnSCMDevice(FileHandle) )
      *v13 |= 0x40u;
    v14 = *((_QWORD *)&v27 + 1) * (unsigned int)v28 * (unsigned __int64)HIDWORD(v28);
    *(_QWORD *)(v11 + 32) = v14;
    *(_QWORD *)(v11 + 40) = v27 * (unsigned int)v28 * (unsigned __int64)HIDWORD(v28);
    v15 = v14 - 0x2000000;
    if ( v14 <= 0x2000000 )
      v15 = 0;
    *(_QWORD *)(v11 + 32) = v15;
    if ( (unsigned __int8)SmpIsVhdVolume(FileHandle) )
      *v13 |= 2u;
    if ( (int)SmpGetVolumeDiskNumber(FileHandle, &v22) >= 0 )
    {
      v16 = v22;
      *v13 |= 8u;
      *(_DWORD *)(v11 + 20) = v16;
    }
    v8 = &SmpVolumeDescriptorList;
    if ( (*(_BYTE *)v13 & 1) != 0 )
    {
      v17 = SmpVolumeDescriptorList;
      if ( *(__int64 **)(SmpVolumeDescriptorList + 8) == &SmpVolumeDescriptorList )
      {
        *(_QWORD *)v11 = SmpVolumeDescriptorList;
        *(_QWORD *)(v11 + 8) = &SmpVolumeDescriptorList;
        *(_QWORD *)(v17 + 8) = v11;
        SmpVolumeDescriptorList = v11;
        goto LABEL_36;
      }
    }
    else
    {
      v18 = (__int64 *)qword_140030C28;
      if ( *(__int64 **)qword_140030C28 == &SmpVolumeDescriptorList )
      {
        *(_QWORD *)v11 = &SmpVolumeDescriptorList;
        *(_QWORD *)(v11 + 8) = v18;
        *v18 = v11;
        qword_140030C28 = v11;
        goto LABEL_36;
      }
    }
    __fastfail(3u);
  }
  if ( a3 )
    Buffer = a3->Buffer;
  else
    Buffer = 0;
  LODWORD(v8) = SmpLogFailureString("SmpCreateVolumeDescriptor", 1355, Buffer, (unsigned int)v6);
LABEL_36:
  if ( FileHandle )
    LODWORD(v8) = NtClose(FileHandle);
  if ( Handle )
    LODWORD(v8) = NtClose(Handle);
  return (int)v8;
}

```

## disassembly

```asm
0x14000fed0  mov     [rsp-8+arg_18], rbx
0x14000fed5  push    rbp
0x14000fed6  push    rsi
0x14000fed7  push    rdi
0x14000fed8  lea     rbp, [rsp-47h]
0x14000fedd  sub     rsp, 0B0h
0x14000fee4  mov     rax, cs:__security_cookie
0x14000feeb  xor     rax, rsp
0x14000feee  mov     [rbp+57h+var_18], rax
0x14000fef2  xor     eax, eax
0x14000fef4  movzx   esi, cx
0x14000fef7  xorps   xmm0, xmm0
0x14000fefa  mov     [rsp+0C0h+OpenOptions], 20h ; ' '; OpenOptions
0x14000ff02  mov     rbx, r8
0x14000ff05  mov     [rbp+57h+Handle], rax
0x14000ff09  mov     rdi, rdx
0x14000ff0c  mov     [rbp+57h+FileHandle], rax
0x14000ff10  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000ff14  mov     [rbp+57h+var_20], rax
0x14000ff18  mov     edx, 120089h; DesiredAccess
0x14000ff1d  mov     [rbp+57h+FsInformation], rax
0x14000ff21  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000ff25  mov     [rbp+57h+var_84], eax
0x14000ff28  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000ff2c  mov     [rbp+57h+var_88], eax
0x14000ff2f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000ff33  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000ff37  movups  [rbp+57h+var_30], xmm0
0x14000ff3b  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x14000ff3f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ff44  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000ff4c  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14000ff54  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x14000ff5c  call    cs:__imp_NtOpenFile
0x14000ff62  test    eax, eax
0x14000ff64  jns     short loc_14000FF86
0x14000ff66  mov     edx, 52Ch
0x14000ff6b  xor     r9d, r9d
0x14000ff6e  mov     [rsp+0C0h+ShareAccess], eax
0x14000ff72  mov     r8, rsi
0x14000ff75  lea     rcx, aSmpcreatevolum; "SmpCreateVolumeDescriptor"
0x14000ff7c  call    SmLogFailureInt
0x14000ff81  jmp     loc_1400101A7
0x14000ff86  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000ff8a  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14000ff8e  mov     r9d, 8; Length
0x14000ff94  mov     [rsp+0C0h+ShareAccess], 4; FsInformationClass
0x14000ff9c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000ffa0  call    cs:__imp_NtQueryVolumeInformationFile
0x14000ffa6  test    eax, eax
0x14000ffa8  jns     short loc_14000FFB1
0x14000ffaa  mov     edx, 53Dh
0x14000ffaf  jmp     short loc_14000FF6B
0x14000ffb1  test    byte ptr [rbp+57h+FsInformation+4], 17h
0x14000ffb5  jz      short loc_14000FFDE
0x14000ffb7  test    rbx, rbx
0x14000ffba  jz      short loc_14000FFC2
0x14000ffbc  mov     r8, [rbx+8]
0x14000ffc0  jmp     short loc_14000FFC5
0x14000ffc2  xor     r8d, r8d
0x14000ffc5  mov     r9d, eax
0x14000ffc8  lea     rcx, aSmpcreatevolum; "SmpCreateVolumeDescriptor"
0x14000ffcf  mov     edx, 54Bh
0x14000ffd4  call    SmpLogFailureString
0x14000ffd9  jmp     loc_1400101A7
0x14000ffde  xorps   xmm0, xmm0
0x14000ffe1  mov     [rsp+0C0h+OpenOptions], 21h ; '!'; OpenOptions
0x14000ffe9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000ffed  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000fff4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fff8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140010000  mov     edx, 100080h; DesiredAccess
0x140010005  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14001000c  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140010010  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x140010014  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140010019  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x140010021  call    cs:__imp_NtOpenFile
0x140010027  test    eax, eax
0x140010029  jns     short loc_140010035
0x14001002b  mov     edx, 563h
0x140010030  jmp     loc_14000FF6B
0x140010035  mov     rcx, [rbp+57h+Handle]; FileHandle
0x140010039  lea     r8, [rbp+57h+var_30]; FsInformation
0x14001003d  mov     r9d, 18h; Length
0x140010043  mov     [rsp+0C0h+ShareAccess], 3; FsInformationClass
0x14001004b  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001004f  call    cs:__imp_NtQueryVolumeInformationFile
0x140010055  test    eax, eax
0x140010057  jns     short loc_140010063
0x140010059  mov     edx, 574h
0x14001005e  jmp     loc_14000FF6B
0x140010063  mov     rcx, gs:60h
0x14001006c  mov     edx, 8; Flags
0x140010071  mov     rcx, [rcx+30h]; HeapHandle
0x140010075  lea     r8d, [rdx+28h]; Size
0x140010079  call    cs:__imp_RtlAllocateHeap
0x14001007f  mov     rbx, rax
0x140010082  test    rax, rax
0x140010085  jnz     short loc_1400100A3
0x140010087  mov     edx, 583h
0x14001008c  lea     rcx, aSmpcreatevolum; "SmpCreateVolumeDescriptor"
0x140010093  mov     r8d, 0C000009Ah
0x140010099  call    SmpLogFailure
0x14001009e  jmp     loc_1400101A7
0x1400100a3  cmp     si, cs:SmpOsVolumeLetter
0x1400100aa  lea     rdi, [rbx+10h]
0x1400100ae  mov     [rax+1Ch], si
0x1400100b2  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1400100b5  mov     [rbx+18h], eax
0x1400100b8  jnz     short loc_1400100C4
0x1400100ba  or      dword ptr [rdi], 1
0x1400100bd  mov     cs:SmpOsVolumeDescriptor, rbx
0x1400100c4  mov     rcx, [rbp+57h+FileHandle]
0x1400100c8  lea     rdx, [rbp+57h+var_88]
0x1400100cc  call    RtlQueryVolumeDiskSpeedPolicy
0x1400100d1  test    eax, eax
0x1400100d3  js      short loc_1400100DE
0x1400100d5  cmp     [rbp+57h+var_88], 14h
0x1400100d9  jl      short loc_1400100DE
0x1400100db  or      dword ptr [rdi], 4
0x1400100de  mov     rcx, [rbp+57h+FileHandle]
0x1400100e2  call    SmpIsVolumeOnSCMDevice
0x1400100e7  test    al, al
0x1400100e9  jz      short loc_1400100EE
0x1400100eb  or      dword ptr [rdi], 40h
0x1400100ee  mov     eax, dword ptr [rbp+57h+var_20]
0x1400100f1  mov     edx, dword ptr [rbp+57h+var_20+4]
0x1400100f4  imul    rdx, rax
0x1400100f8  imul    rdx, qword ptr [rbp+57h+var_30+8]
0x1400100fd  mov     [rbx+20h], rdx
0x140010101  mov     eax, dword ptr [rbp+57h+var_20]
0x140010104  mov     ecx, dword ptr [rbp+57h+var_20+4]
0x140010107  imul    rcx, rax
0x14001010b  xor     eax, eax
0x14001010d  imul    rcx, qword ptr [rbp+57h+var_30]
0x140010112  cmp     rdx, 2000000h
0x140010119  mov     [rbx+28h], rcx
0x14001011d  lea     rcx, [rdx-2000000h]
0x140010124  cmovbe  rcx, rax
0x140010128  mov     [rbx+20h], rcx
0x14001012c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140010130  call    SmpIsVhdVolume
0x140010135  test    al, al
0x140010137  jz      short loc_14001013C
0x140010139  or      dword ptr [rdi], 2
0x14001013c  mov     rcx, [rbp+57h+FileHandle]
0x140010140  lea     rdx, [rbp+57h+var_84]
0x140010144  call    SmpGetVolumeDiskNumber
0x140010149  test    eax, eax
0x14001014b  js      short loc_140010156
0x14001014d  mov     eax, [rbp+57h+var_84]
0x140010150  or      dword ptr [rdi], 8
0x140010153  mov     [rbx+14h], eax
0x140010156  test    byte ptr [rdi], 1
0x140010159  lea     rax, SmpVolumeDescriptorList
0x140010160  jz      short loc_140010183
0x140010162  mov     rcx, cs:SmpVolumeDescriptorList
0x140010169  cmp     [rcx+8], rax
0x14001016d  jnz     short loc_14001018F
0x14001016f  mov     [rbx], rcx
0x140010172  mov     [rbx+8], rax
0x140010176  mov     [rcx+8], rbx
0x14001017a  mov     cs:SmpVolumeDescriptorList, rbx
0x140010181  jmp     short loc_1400101A7
0x140010183  mov     rdx, cs:qword_140030C28
0x14001018a  cmp     [rdx], rax
0x14001018d  jz      short loc_140010196
0x14001018f  mov     ecx, 3
0x140010194  int     29h; Win8: RtlFailFast(ecx)
0x140010196  mov     [rbx], rax
0x140010199  mov     [rbx+8], rdx
0x14001019d  mov     [rdx], rbx
0x1400101a0  mov     cs:qword_140030C28, rbx
0x1400101a7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400101ab  test    rcx, rcx
0x1400101ae  jz      short loc_1400101B6
0x1400101b0  call    cs:__imp_NtClose
0x1400101b6  mov     rcx, [rbp+57h+Handle]; Handle
0x1400101ba  test    rcx, rcx
0x1400101bd  jz      short loc_1400101C5
0x1400101bf  call    cs:__imp_NtClose
0x1400101c5  mov     rcx, [rbp+57h+var_18]
0x1400101c9  xor     rcx, rsp; StackCookie
0x1400101cc  call    __security_check_cookie
0x1400101d1  mov     rbx, [rsp+0C0h+arg_18]
0x1400101d9  add     rsp, 0B0h
0x1400101e0  pop     rdi
0x1400101e1  pop     rsi
0x1400101e2  pop     rbp
0x1400101e3  retn
```
