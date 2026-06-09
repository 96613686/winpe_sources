# VhdmpiEnumerateVolumes(_VHD_COMPACT_CONTEXT *)

- ea: `0x14009ffd8`
- end: `0x1400a05ab`
- name: `?VhdmpiEnumerateVolumes@@YAJPEAU_VHD_COMPACT_CONTEXT@@@Z`
- size: `1491`
- prototype: `__int64 __fastcall(struct _VHD_COMPACT_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14009f940`

## callees

- `0x140023980`
- `0x140029778`
- `0x140033214`
- `0x140036284`
- `0x14005dae8`
- `0x14005dbb0`
- `0x14009ff2c`
- `0x14009ffd8`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400a02ee`
- `ntoskrnl!ZwFsControlFile` at `0x1400a02ee`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400a030b`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400a030b`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400a037b`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400a03cc`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400a037b`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400a03cc`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400a006f`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400a006f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a0185`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a0185`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a009c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a052c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a009c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a052c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a00ff`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a00ff`
- `ntoskrnl!ZwClose` at `0x1400a00b5`
- `ntoskrnl!ZwClose` at `0x1400a0513`
- `ntoskrnl!ZwClose` at `0x1400a00b5`
- `ntoskrnl!ZwClose` at `0x1400a0513`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a00d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a00e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a021c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a0542`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a0558`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a057c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a00d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a00e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a021c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a0542`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a0558`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a057c`
- `ntoskrnl!ZwOpenFile` at `0x1400a014d`
- `ntoskrnl!ZwOpenFile` at `0x1400a014d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a01ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400a0347`
- `ntoskrnl!ExAllocatePool2` at `0x1400a01ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400a0347`

## pseudocode

```c
__int64 __fastcall VhdmpiEnumerateVolumes(struct _VHD_COMPACT_CONTEXT *a1)
{
  PVOID v2; // r15
  _DWORD *v3; // rsi
  _QWORD *v4; // rdi
  NTSTATUS DeviceInterfaces; // eax
  const WCHAR *v6; // r14
  int v7; // ebx
  NTSTATUS v8; // eax
  unsigned int v9; // r12d
  __int64 Pool2; // rax
  int v11; // eax
  int v12; // ecx
  __int64 i; // r12
  int v14; // eax
  NTSTATUS Status; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  struct _VHD_COMPACT_CONTEXT **v19; // rcx
  __int64 v20; // rax
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  PZZWSTR SymbolicLinkList; // [rsp+68h] [rbp-98h] BYREF
  PVOID Object; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _OWORD OutputBuffer[3]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE InputBuffer[36]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE FsInformation[12]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t Str2[8]; // [rsp+12Ch] [rbp+2Ch] BYREF
  __int128 v34; // [rsp+13Ch] [rbp+3Ch]
  __int16 v35; // [rsp+14Ch] [rbp+4Ch]

  SymbolicLinkList = 0;
  v2 = 0;
  memset(InputBuffer, 0, sizeof(InputBuffer));
  Handle = 0;
  v3 = 0;
  v4 = 0;
  memset(OutputBuffer, 0, 44);
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  VhdmpiDeallocateVolumeList(a1);
  if ( *((_BYTE *)a1 + 177) )
  {
    v7 = 0;
  }
  else
  {
    DeviceInterfaces = IoGetDeviceInterfaces(&GUID_DEVINTERFACE_VOLUME, 0, 0, &SymbolicLinkList);
    v6 = SymbolicLinkList;
    v7 = DeviceInterfaces;
    if ( DeviceInterfaces >= 0 && *SymbolicLinkList )
    {
      do
      {
        if ( v2 )
        {
          ObfDereferenceObject(v2);
          v2 = 0;
        }
        if ( Handle )
        {
          ZwClose(Handle);
          Handle = 0;
        }
        if ( v3 )
        {
          ExFreePoolWithTag(v3, 0);
          v3 = 0;
        }
        if ( v4 )
        {
          ExFreePoolWithTag(v4, 0);
          v4 = 0;
        }
        RtlInitUnicodeString(&DestinationString, v6);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 1600;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenFile(&Handle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0) >= 0 )
        {
          Object = 0;
          v8 = ObReferenceObjectByHandle(Handle, 0x80000000, 0, 0, &Object, 0);
          v2 = Object;
          if ( v8 >= 0 )
          {
            v9 = 32;
            v23 = 0;
            while ( 1 )
            {
              Pool2 = ExAllocatePool2(256, v9, 1449357379);
              v3 = (_DWORD *)Pool2;
              if ( !Pool2 )
              {
LABEL_41:
                v7 = -1073741670;
                goto LABEL_48;
              }
              v11 = VhdmpiSendSyncDeviceIoControlToFile(0, 5636096, v2, 0, 0, Pool2, v9, 0);
              LODWORD(v24) = v11;
              if ( v11 != -2147483643 )
                break;
              v9 = 24 * *v3 + 8;
              ExFreePoolWithTag(v3, 0);
              v3 = 0;
              v12 = v23++;
              if ( v12 == 10 )
              {
                v11 = v24;
                break;
              }
            }
            if ( v11 >= 0 && 24 * (unsigned __int64)(unsigned int)(*v3 - 1) + 32 <= v9 )
            {
              for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
              {
                v14 = *((_DWORD *)a1 + 48);
                v24 = 3 * i;
                if ( v3[6 * i + 2] == v14 )
                {
                  *(_QWORD *)&InputBuffer[4] = 36;
                  *(_OWORD *)&InputBuffer[20] = 0;
                  *(_DWORD *)InputBuffer = 128;
                  *(_QWORD *)&InputBuffer[12] = 4;
                  Status = ZwFsControlFile(
                             Handle,
                             0,
                             0,
                             0,
                             &IoStatusBlock,
                             0x90260u,
                             InputBuffer,
                             0x24u,
                             OutputBuffer,
                             0x2Cu);
                  if ( Status == 259 )
                  {
                    ZwWaitForSingleObject(Handle, 0, 0);
                    Status = IoStatusBlock.Status;
                  }
                  if ( Status < 0 || (BYTE8(OutputBuffer[1]) & 0x1F) != 0 || (BYTE12(OutputBuffer[1]) & 2) == 0 )
                    break;
                  v16 = ExAllocatePool2(256, 80, 1449357379);
                  v4 = (_QWORD *)v16;
                  if ( !v16 )
                    goto LABEL_41;
                  if ( ZwQueryVolumeInformationFile(
                         Handle,
                         &IoStatusBlock,
                         (PVOID)(v16 + 32),
                         0x18u,
                         FileFsSizeInformation) < 0 )
                    break;
                  v35 = 0;
                  *(__m128i *)Str2 = _mm_shuffle_epi32(_mm_cvtsi32_si128(0), 0);
                  v34 = *(_OWORD *)Str2;
                  if ( ZwQueryVolumeInformationFile(
                         Handle,
                         &IoStatusBlock,
                         FsInformation,
                         0x2Cu,
                         FileFsAttributeInformation) < 0 )
                    break;
                  if ( wcsncmp_0(L"NTFS", Str2, 0x10u) )
                    break;
                  v17 = *((_DWORD *)v4 + 12) * *((_DWORD *)v4 + 13);
                  *((_DWORD *)v4 + 14) = v17;
                  if ( !v17 )
                    break;
                  v18 = v24;
                  v4[8] = *(_QWORD *)&v3[2 * v24 + 4];
                  v4[9] = *(_QWORD *)&v3[2 * v18 + 4] + *(_QWORD *)&v3[2 * v18 + 6];
                  v4[2] = Handle;
                  v4[3] = v2;
                  v19 = (struct _VHD_COMPACT_CONTEXT **)*((_QWORD *)a1 + 26);
                  Handle = 0;
                  if ( *v19 != (struct _VHD_COMPACT_CONTEXT *)((char *)a1 + 200) )
                    __fastfail(3u);
                  *v4 = (char *)a1 + 200;
                  v2 = 0;
                  v4[1] = v19;
                  *v19 = (struct _VHD_COMPACT_CONTEXT *)v4;
                  *((_QWORD *)a1 + 26) = v4;
                  ++*((_DWORD *)a1 + 49);
                  v4 = 0;
                }
              }
            }
          }
        }
        v20 = -1;
        do
          ++v20;
        while ( v6[v20] );
        v6 += v20 + 1;
      }
      while ( *v6 );
      VhdmpiSortCompactionDiskExtents(a1);
    }
    else
    {
      if ( SymbolicLinkList )
        v7 = -1073741823;
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
        TraceEvents("VhdmpiEnumerateVolumes", 0x107u, 2u, 4u, "get Device volume interface failed 0x%08x", v7);
    }
  }
LABEL_48:
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( v2 )
    ObfDereferenceObject(v2);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( v7 < 0 )
    VhdmpiDeallocateVolumeList(a1);
  if ( SymbolicLinkList )
    ExFreePoolWithTag(SymbolicLinkList, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14009ffd8  push    rbp
0x14009ffda  push    rbx
0x14009ffdb  push    rsi
0x14009ffdc  push    rdi
0x14009ffdd  push    r12
0x14009ffdf  push    r13
0x14009ffe1  push    r14
0x14009ffe3  push    r15
0x14009ffe5  lea     rbp, [rsp-68h]
0x14009ffea  sub     rsp, 168h
0x14009fff1  mov     rax, cs:__security_cookie
0x14009fff8  xor     rax, rsp
0x14009fffb  mov     [rbp+0A0h+var_50], rax
0x14009ffff  xorps   xmm1, xmm1
0x1400a0002  xorps   xmm0, xmm0
0x1400a0005  xor     r12d, r12d
0x1400a0008  xor     eax, eax
0x1400a000a  movups  xmmword ptr [rbp+0A0h+var_C8], xmm1
0x1400a000e  mov     r13, rcx
0x1400a0011  mov     [rbp+0A0h+var_88], eax
0x1400a0014  movups  xmmword ptr [rbp+0A0h+var_C8+0Ch], xmm1
0x1400a0018  mov     [rsp+1A0h+SymbolicLinkList], r12
0x1400a001d  mov     r15d, r12d
0x1400a0020  movups  [rbp+0A0h+var_A8], xmm0
0x1400a0024  mov     [rsp+1A0h+Handle], r12
0x1400a0029  mov     esi, r12d
0x1400a002c  movups  [rbp+0A0h+var_98], xmm0
0x1400a0030  mov     edi, r12d
0x1400a0033  movups  [rbp+0A0h+var_D8], xmm1
0x1400a0037  movups  xmmword ptr [rsp+1A0h+IoStatusBlock], xmm0
0x1400a003c  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm1
0x1400a0040  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm1
0x1400a0044  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400a0048  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1400a004c  call    ?VhdmpiDeallocateVolumeList@@YAXPEAU_VHD_COMPACT_CONTEXT@@@Z; VhdmpiDeallocateVolumeList(_VHD_COMPACT_CONTEXT *)
0x1400a0051  cmp     [r13+0B1h], r12b
0x1400a0058  jnz     loc_1400A0506
0x1400a005e  lea     r9, [rsp+1A0h+SymbolicLinkList]; SymbolicLinkList
0x1400a0063  xor     r8d, r8d; Flags
0x1400a0066  xor     edx, edx; PhysicalDeviceObject
0x1400a0068  lea     rcx, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x1400a006f  call    cs:__imp_IoGetDeviceInterfaces
0x1400a0076  nop     dword ptr [rax+rax+00h]
0x1400a007b  mov     r14, [rsp+1A0h+SymbolicLinkList]
0x1400a0080  mov     ebx, eax
0x1400a0082  test    eax, eax
0x1400a0084  js      loc_1400A04AE
0x1400a008a  cmp     [r14], r12w
0x1400a008e  jz      loc_1400A04AE
0x1400a0094  test    r15, r15
0x1400a0097  jz      short loc_1400A00AB
0x1400a0099  mov     rcx, r15; Object
0x1400a009c  call    cs:__imp_ObfDereferenceObject
0x1400a00a3  nop     dword ptr [rax+rax+00h]
0x1400a00a8  mov     r15, r12
0x1400a00ab  mov     rcx, [rsp+1A0h+Handle]; Handle
0x1400a00b0  test    rcx, rcx
0x1400a00b3  jz      short loc_1400A00C6
0x1400a00b5  call    cs:__imp_ZwClose
0x1400a00bc  nop     dword ptr [rax+rax+00h]
0x1400a00c1  mov     [rsp+1A0h+Handle], r12
0x1400a00c6  test    rsi, rsi
0x1400a00c9  jz      short loc_1400A00DF
0x1400a00cb  xor     edx, edx; Tag
0x1400a00cd  mov     rcx, rsi; P
0x1400a00d0  call    cs:__imp_ExFreePoolWithTag
0x1400a00d7  nop     dword ptr [rax+rax+00h]
0x1400a00dc  mov     rsi, r12
0x1400a00df  test    rdi, rdi
0x1400a00e2  jz      short loc_1400A00F8
0x1400a00e4  xor     edx, edx; Tag
0x1400a00e6  mov     rcx, rdi; P
0x1400a00e9  call    cs:__imp_ExFreePoolWithTag
0x1400a00f0  nop     dword ptr [rax+rax+00h]
0x1400a00f5  mov     rdi, r12
0x1400a00f8  mov     rdx, r14; SourceString
0x1400a00fb  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1400a00ff  call    cs:__imp_RtlInitUnicodeString
0x1400a0106  nop     dword ptr [rax+rax+00h]
0x1400a010b  lea     rax, [rbp+0A0h+DestinationString]
0x1400a010f  mov     [rsp+1A0h+OpenOptions], r12d; OpenOptions
0x1400a0114  xorps   xmm0, xmm0
0x1400a0117  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1400a011b  lea     r9, [rsp+1A0h+IoStatusBlock]; IoStatusBlock
0x1400a0120  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1400a0127  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1400a012b  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r12
0x1400a012f  mov     edx, 80100000h; DesiredAccess
0x1400a0134  mov     [rbp+0A0h+ObjectAttributes.Attributes], 640h
0x1400a013b  lea     rcx, [rsp+1A0h+Handle]; FileHandle
0x1400a0140  mov     [rsp+1A0h+ShareAccess], 3; ShareAccess
0x1400a0148  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a014d  call    cs:__imp_ZwOpenFile
0x1400a0154  nop     dword ptr [rax+rax+00h]
0x1400a0159  test    eax, eax
0x1400a015b  js      loc_1400A0473
0x1400a0161  mov     rcx, [rsp+1A0h+Handle]; Handle
0x1400a0166  lea     rax, [rsp+1A0h+Object]
0x1400a016b  mov     qword ptr [rsp+1A0h+OpenOptions], r12; HandleInformation
0x1400a0170  xor     r9d, r9d; AccessMode
0x1400a0173  xor     r8d, r8d; ObjectType
0x1400a0176  mov     qword ptr [rsp+1A0h+ShareAccess], rax; Object
0x1400a017b  mov     edx, 80000000h; DesiredAccess
0x1400a0180  mov     [rsp+1A0h+Object], r12
0x1400a0185  call    cs:__imp_ObReferenceObjectByHandle
0x1400a018c  nop     dword ptr [rax+rax+00h]
0x1400a0191  mov     r15, [rsp+1A0h+Object]
0x1400a0196  test    eax, eax
0x1400a0198  js      loc_1400A0473
0x1400a019e  mov     r12d, 20h ; ' '
0x1400a01a4  mov     [rsp+1A0h+var_148], 0
0x1400a01ac  mov     edx, r12d
0x1400a01af  mov     ecx, 100h
0x1400a01b4  mov     r8d, 56637043h
0x1400a01ba  call    cs:__imp_ExAllocatePool2
0x1400a01c1  nop     dword ptr [rax+rax+00h]
0x1400a01c6  mov     rsi, rax
0x1400a01c9  test    rax, rax
0x1400a01cc  jz      loc_1400A04A4
0x1400a01d2  mov     qword ptr [rsp+1A0h+InputBufferLength], 0
0x1400a01db  xor     r9d, r9d
0x1400a01de  mov     dword ptr [rsp+1A0h+InputBuffer], r12d
0x1400a01e3  mov     r8, r15
0x1400a01e6  mov     qword ptr [rsp+1A0h+OpenOptions], rax
0x1400a01eb  mov     edx, 560000h
0x1400a01f0  xor     ecx, ecx
0x1400a01f2  mov     [rsp+1A0h+ShareAccess], 0
0x1400a01fa  call    VhdmpiSendSyncDeviceIoControlToFile
0x1400a01ff  mov     dword ptr [rsp+1A0h+var_140], eax
0x1400a0203  cmp     eax, 80000005h
0x1400a0208  jnz     short loc_1400A0243
0x1400a020a  mov     ecx, [rsi]
0x1400a020c  lea     edx, [rcx+rcx*2]
0x1400a020f  mov     rcx, rsi; P
0x1400a0212  lea     r12d, ds:8[rdx*8]
0x1400a021a  xor     edx, edx; Tag
0x1400a021c  call    cs:__imp_ExFreePoolWithTag
0x1400a0223  nop     dword ptr [rax+rax+00h]
0x1400a0228  mov     eax, [rsp+1A0h+var_148]
0x1400a022c  xor     esi, esi
0x1400a022e  mov     ecx, eax
0x1400a0230  inc     eax
0x1400a0232  mov     [rsp+1A0h+var_148], eax
0x1400a0236  cmp     ecx, 0Ah
0x1400a0239  jnz     loc_1400A01AC
0x1400a023f  mov     eax, dword ptr [rsp+1A0h+var_140]
0x1400a0243  test    eax, eax
0x1400a0245  js      loc_1400A0470
0x1400a024b  mov     edx, [rsi]
0x1400a024d  lea     eax, [rdx-1]
0x1400a0250  lea     rax, [rax+rax*2]
0x1400a0254  lea     rcx, ds:20h[rax*8]
0x1400a025c  mov     eax, r12d
0x1400a025f  cmp     rcx, rax
0x1400a0262  ja      loc_1400A0470
0x1400a0268  xor     r12d, r12d
0x1400a026b  test    edx, edx
0x1400a026d  jz      loc_1400A0473
0x1400a0273  mov     eax, [r13+0C0h]
0x1400a027a  lea     rcx, [r12+r12*2]
0x1400a027e  mov     [rsp+1A0h+var_140], rcx
0x1400a0283  cmp     [rsi+rcx*8+8], eax
0x1400a0287  jnz     loc_1400A0464
0x1400a028d  mov     [rsp+1A0h+OutputBufferLength], 2Ch ; ','; OutputBufferLength
0x1400a0295  lea     rax, [rbp+0A0h+var_D8]
0x1400a0299  mov     [rsp+1A0h+OutputBuffer], rax; OutputBuffer
0x1400a029e  mov     ecx, 24h ; '$'
0x1400a02a3  mov     [rsp+1A0h+InputBufferLength], ecx; InputBufferLength
0x1400a02a7  lea     rax, [rbp+0A0h+var_A8]
0x1400a02ab  mov     rcx, [rsp+1A0h+Handle]; FileHandle
0x1400a02b0  xorps   xmm0, xmm0
0x1400a02b3  mov     [rsp+1A0h+InputBuffer], rax; InputBuffer
0x1400a02b8  xor     r9d, r9d; ApcContext
0x1400a02bb  lea     rax, [rsp+1A0h+IoStatusBlock]
0x1400a02c0  mov     [rsp+1A0h+OpenOptions], 90260h; FsControlCode
0x1400a02c8  xor     r8d, r8d; ApcRoutine
0x1400a02cb  mov     qword ptr [rsp+1A0h+ShareAccess], rax; IoStatusBlock
0x1400a02d0  xor     edx, edx; Event
0x1400a02d2  mov     qword ptr [rbp+0A0h+var_A8+4], 24h ; '$'
0x1400a02da  movdqu  [rbp+0A0h+var_98+4], xmm0
0x1400a02df  mov     dword ptr [rbp+0A0h+var_A8], 80h
0x1400a02e6  mov     qword ptr [rbp+0A0h+var_A8+0Ch], 4
0x1400a02ee  call    cs:__imp_ZwFsControlFile
0x1400a02f5  nop     dword ptr [rax+rax+00h]
0x1400a02fa  cmp     eax, 103h
0x1400a02ff  jnz     short loc_1400A031B
0x1400a0301  mov     rcx, [rsp+1A0h+Handle]; Handle
0x1400a0306  xor     r8d, r8d; Timeout
0x1400a0309  xor     edx, edx; Alertable
0x1400a030b  call    cs:__imp_ZwWaitForSingleObject
0x1400a0312  nop     dword ptr [rax+rax+00h]
0x1400a0317  mov     eax, dword ptr [rsp+1A0h+IoStatusBlock]
0x1400a031b  test    eax, eax
0x1400a031d  js      loc_1400A0470
0x1400a0323  test    [rbp+0A0h+var_C8+8], 1Fh
0x1400a0327  jnz     loc_1400A0470
0x1400a032d  test    [rbp+0A0h+var_C8+0Ch], 2
0x1400a0331  jz      loc_1400A0470
0x1400a0337  mov     edx, 50h ; 'P'
0x1400a033c  mov     ecx, 100h
0x1400a0341  mov     r8d, 56637043h
0x1400a0347  call    cs:__imp_ExAllocatePool2
0x1400a034e  nop     dword ptr [rax+rax+00h]
0x1400a0353  mov     rdi, rax
0x1400a0356  test    rax, rax
0x1400a0359  jz      loc_1400A04A4
0x1400a035f  mov     rcx, [rsp+1A0h+Handle]; FileHandle
0x1400a0364  lea     r8, [rax+20h]; FsInformation
0x1400a0368  mov     r9d, 18h; Length
0x1400a036e  mov     [rsp+1A0h+ShareAccess], 3; FsInformationClass
0x1400a0376  lea     rdx, [rsp+1A0h+IoStatusBlock]; IoStatusBlock
0x1400a037b  call    cs:__imp_ZwQueryVolumeInformationFile
0x1400a0382  nop     dword ptr [rax+rax+00h]
0x1400a0387  test    eax, eax
0x1400a0389  js      loc_1400A0470
0x1400a038f  xor     eax, eax
0x1400a0391  mov     [rsp+1A0h+ShareAccess], 5; FsInformationClass
0x1400a0399  movzx   ecx, ax
0x1400a039c  lea     r8, [rbp+0A0h+FsInformation]; FsInformation
0x1400a03a0  mov     eax, ecx
0x1400a03a2  lea     rdx, [rsp+1A0h+IoStatusBlock]; IoStatusBlock
0x1400a03a7  shl     ecx, 10h
0x1400a03aa  mov     r9d, 2Ch ; ','; Length
0x1400a03b0  or      ecx, eax
0x1400a03b2  mov     [rbp+0A0h+var_54], cx
0x1400a03b6  movd    xmm0, ecx
0x1400a03ba  mov     rcx, [rsp+1A0h+Handle]; FileHandle
0x1400a03bf  pshufd  xmm0, xmm0, 0
0x1400a03c4  movups  xmmword ptr [rbp+0A0h+Str2], xmm0
0x1400a03c8  movups  [rbp+0A0h+var_64], xmm0
0x1400a03cc  call    cs:__imp_ZwQueryVolumeInformationFile
0x1400a03d3  nop     dword ptr [rax+rax+00h]
0x1400a03d8  test    eax, eax
0x1400a03da  js      loc_1400A0470
0x1400a03e0  mov     r8d, 10h; MaxCount
0x1400a03e6  lea     rdx, [rbp+0A0h+Str2]; Str2
0x1400a03ea  lea     rcx, aNtfs; "NTFS"
0x1400a03f1  call    wcsncmp_0
0x1400a03f6  test    eax, eax
0x1400a03f8  jnz     short loc_1400A0470
0x1400a03fa  mov     eax, [rdi+34h]
0x1400a03fd  imul    eax, [rdi+30h]
0x1400a0401  mov     [rdi+38h], eax
0x1400a0404  test    eax, eax
0x1400a0406  jz      short loc_1400A0470
0x1400a0408  mov     rcx, [rsp+1A0h+var_140]
0x1400a040d  mov     rax, [rsi+rcx*8+10h]
0x1400a0412  mov     [rdi+40h], rax
0x1400a0416  mov     rax, [rsi+rcx*8+18h]
0x1400a041b  add     rax, [rsi+rcx*8+10h]
0x1400a0420  mov     [rdi+48h], rax
0x1400a0424  mov     rax, [rsp+1A0h+Handle]
0x1400a0429  mov     [rdi+10h], rax
0x1400a042d  lea     rax, [r13+0C8h]
0x1400a0434  mov     [rdi+18h], r15
0x1400a0438  mov     rcx, [rax+8]
0x1400a043c  mov     [rsp+1A0h+Handle], 0
0x1400a0445  cmp     [rcx], rax
0x1400a0448  jnz     short loc_1400A049D
0x1400a044a  mov     [rdi], rax
0x1400a044d  xor     r15d, r15d
0x1400a0450  mov     [rdi+8], rcx
0x1400a0454  mov     [rcx], rdi
0x1400a0457  mov     [rax+8], rdi
0x1400a045b  inc     dword ptr [r13+0C4h]
0x1400a0462  xor     edi, edi
0x1400a0464  inc     r12d
0x1400a0467  cmp     r12d, [rsi]
0x1400a046a  jb      loc_1400A0273
0x1400a0470  xor     r12d, r12d
0x1400a0473  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400a0477  inc     rax
0x1400a047a  cmp     [r14+rax*2], r12w
0x1400a047f  jnz     short loc_1400A0477
0x1400a0481  lea     r14, [r14+rax*2]
0x1400a0485  add     r14, 2
0x1400a0489  cmp     [r14], r12w
0x1400a048d  jnz     loc_1400A0094
0x1400a0493  mov     rcx, r13; struct _VHD_COMPACT_CONTEXT *
0x1400a0496  call    ?VhdmpiSortCompactionDiskExtents@@YAXPEAU_VHD_COMPACT_CONTEXT@@@Z; VhdmpiSortCompactionDiskExtents(_VHD_COMPACT_CONTEXT *)
0x1400a049b  jmp     short loc_1400A0509
0x1400a049d  mov     ecx, 3
0x1400a04a2  int     29h; Win8: RtlFailFast(ecx)
0x1400a04a4  mov     ebx, 0C000009Ah
0x1400a04a9  xor     r12d, r12d
0x1400a04ac  jmp     short loc_1400A0509
0x1400a04ae  test    r14, r14
0x1400a04b1  mov     eax, 0C0000001h
0x1400a04b6  cmovnz  ebx, eax
0x1400a04b9  mov     eax, cs:dword_1400876D0
0x1400a04bf  cmp     eax, 2
0x1400a04c2  jbe     short loc_1400A0509
0x1400a04c4  mov     edx, 4
0x1400a04c9  lea     rcx, dword_1400876D0
0x1400a04d0  call    _tlgKeywordOn
0x1400a04d5  test    al, al
0x1400a04d7  jz      short loc_1400A0509
0x1400a04d9  mov     r9d, 4; int
0x1400a04df  mov     [rsp+1A0h+OpenOptions], ebx; char
0x1400a04e3  lea     rax, aGetDeviceVolum; "get Device volume interface failed 0x%0"...
  ... truncated ...
```
