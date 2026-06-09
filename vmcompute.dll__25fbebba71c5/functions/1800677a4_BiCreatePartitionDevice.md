# BiCreatePartitionDevice

- ea: `0x1800677a4`
- end: `0x180067c6a`
- name: `BiCreatePartitionDevice`
- size: `1222`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066c7c`

## callees

- `0x180003bdc`
- `0x180003c78`
- `0x180004829`
- `0x180066c7c`
- `0x1800675b8`
- `0x1800677a4`
- `0x180067c70`
- `0x180068178`
- `0x180068740`
- `0x1800688f4`
- `0x180068d58`
- `0x18006b964`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800678d0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800678d0`
- `ntdll!ZwClose` at `0x180067c1d`
- `ntdll!ZwClose` at `0x180067c1d`
- `ntdll!ZwOpenFile` at `0x180067a4e`
- `ntdll!ZwOpenFile` at `0x180067a4e`
- `ntdll!RtlAllocateHeap` at `0x180067acd`
- `ntdll!RtlAllocateHeap` at `0x180067acd`
- `ntdll!RtlFreeHeap` at `0x180067924`
- `ntdll!RtlFreeHeap` at `0x180067b99`
- `ntdll!RtlFreeHeap` at `0x180067bc1`
- `ntdll!RtlFreeHeap` at `0x180067be4`
- `ntdll!RtlFreeHeap` at `0x180067c07`
- `ntdll!RtlFreeHeap` at `0x180067c40`
- `ntdll!RtlFreeHeap` at `0x180067924`
- `ntdll!RtlFreeHeap` at `0x180067b99`
- `ntdll!RtlFreeHeap` at `0x180067bc1`
- `ntdll!RtlFreeHeap` at `0x180067be4`
- `ntdll!RtlFreeHeap` at `0x180067c07`
- `ntdll!RtlFreeHeap` at `0x180067c40`
- `ntdll!RtlInitUnicodeString` at `0x1800679fa`
- `ntdll!RtlInitUnicodeString` at `0x1800679fa`

## string_xrefs

- `0x180067901`: `BiCreatePartitionDevice: NestedVhd detected %ws`

## pseudocode

```c
__int64 __fastcall BiCreatePartitionDevice(PCWSTR SourceString, int a2, _QWORD *a3, _DWORD *a4)
{
  PVOID v5; // r12
  WCHAR *v6; // r14
  int v7; // esi
  PVOID v8; // r15
  int PhysicalDriveName; // eax
  NTSTATUS DriveLayoutInformation; // ebx
  __int64 v11; // rdi
  const wchar_t *PartitionVhdFilePath; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  __int64 v15; // rax
  void *v16; // rsi
  int FileDeviceElement; // eax
  __int64 v18; // xmm0_8
  unsigned int v19; // r13d
  SIZE_T v20; // r8
  struct _PEB *v21; // rcx
  _OWORD *Heap; // rax
  _OWORD *v23; // rsi
  size_t v24; // r8
  __int128 v25; // xmm1
  int v26; // eax
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  _DWORD *v29; // rcx
  char v31; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-C0h]
  _DWORD Size[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v35; // [rsp+50h] [rbp-B0h]
  PVOID v36; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v39; // [rsp+70h] [rbp-90h]
  _DWORD *v40; // [rsp+78h] [rbp-88h]
  __int128 v41; // [rsp+80h] [rbp-80h] BYREF
  __int128 v42; // [rsp+90h] [rbp-70h]
  __m256i v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v48[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int128 v50; // [rsp+150h] [rbp+50h]

  v39 = a3;
  v35 = a2;
  v40 = a4;
  v48[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset_0(v48, 0, 0x8Cu);
  FileHandle = 0;
  DestinationString = 0;
  Src = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  memset(Size, 0, sizeof(Size));
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v36 = 0;
  memset_0(&v41, 0, 0x48u);
  if ( (int)BiGetDriveLayoutInformation(SourceString) < 0 )
  {
    PhysicalDriveName = BiGetPhysicalDriveName(SourceString, &v36);
    v8 = v36;
    DriveLayoutInformation = PhysicalDriveName;
    if ( PhysicalDriveName < 0 )
      goto LABEL_43;
    DriveLayoutInformation = BiGetDriveLayoutInformation((PCWSTR)v36);
    if ( DriveLayoutInformation < 0 )
      goto LABEL_43;
  }
  v31 = 0;
  v11 = *(_QWORD *)&Size[1];
  if ( (v35 & 0x40) == 0 )
  {
    PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(SourceString);
    v6 = (WCHAR *)PartitionVhdFilePath;
    if ( PartitionVhdFilePath )
    {
      if ( !wcsnicmp(PartitionVhdFilePath, L"\\Device\\HarddiskVolume", 0x16u) )
      {
        v13 = wcschr(v6 + 22, 0x5Cu);
        v14 = v13;
        if ( v13 )
        {
          *v13 = 0;
          v15 = BiGetPartitionVhdFilePath(v6);
          *v14 = 92;
          v16 = (void *)v15;
          if ( v15 )
          {
            BiLogMessage(3, L"BiCreatePartitionDevice: NestedVhd detected %ws", v15);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          }
        }
      }
      if ( wcsnicmp(v6, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}", 0x35u) )
      {
        FileDeviceElement = BiCreateFileDeviceElement(v6);
        v5 = P;
        DriveLayoutInformation = FileDeviceElement;
        if ( FileDeviceElement < 0 )
          goto LABEL_41;
        DriveLayoutInformation = BiConvertNtDeviceToBootEnvironment(P, v33, 64, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_41;
      }
      else
      {
        DriveLayoutInformation = BiCreateVhdRamdiskBootDevice(v6, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_43;
        v31 = 1;
      }
      v43.m256i_i32[0] = 6;
      v7 = *((_DWORD *)Src + 2);
      Size[0] = v7;
    }
  }
  if ( *(_DWORD *)v11 )
  {
    if ( *(_DWORD *)v11 != 1 )
    {
LABEL_40:
      DriveLayoutInformation = -1073741811;
      goto LABEL_41;
    }
    v18 = *(_QWORD *)(v11 + 12);
    v43.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v43.m256i_i32[5] = *(_DWORD *)(v11 + 20);
    v43.m256i_i32[1] = 0;
    *(__int64 *)((char *)&v43.m256i_i64[1] + 4) = v18;
  }
  else
  {
    v43.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v43.m256i_i32[1] = 1;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DriveLayoutInformation = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutInformation >= 0 )
  {
    DriveLayoutInformation = BiGetPartitionInformation(FileHandle, *(_DWORD *)v11);
    if ( DriveLayoutInformation >= 0 )
    {
      if ( !v48[0] )
      {
        *(_QWORD *)&v42 = v49;
LABEL_27:
        v19 = v7 + 56;
        v20 = 72;
        v21 = NtCurrentPeb();
        if ( (unsigned int)(v7 + 56) > 0x48 )
          v20 = (unsigned int)(v7 + 56);
        Heap = RtlAllocateHeap(v21->ProcessHeap, 0, v20);
        v23 = Heap;
        if ( Heap )
        {
          v24 = 72;
          if ( v19 > 0x48 )
            v24 = v19;
          memset_0(Heap, 0, v24);
          v25 = v42;
          v26 = 72;
          LODWORD(v41) = 6;
          if ( v19 > 0x48 )
            v26 = v19;
          DWORD2(v41) = v26;
          *v23 = v41;
          v27 = *(_OWORD *)v43.m256i_i8;
          v23[1] = v25;
          v28 = *(_OWORD *)&v43.m256i_u64[2];
          v23[2] = v27;
          *(_QWORD *)&v27 = v44;
          v23[3] = v28;
          *((_QWORD *)v23 + 8) = v27;
          if ( v6 )
            memcpy_0((char *)v23 + 56, Src, Size[0]);
          if ( v31 )
            *((_DWORD *)v23 + 1) |= 8u;
          v29 = v40;
          *v39 = v23;
          *v29 = *(_DWORD *)(v11 + 4);
        }
        else
        {
          DriveLayoutInformation = -1073741670;
        }
        goto LABEL_41;
      }
      if ( v48[0] == 1 )
      {
        v42 = v50;
        goto LABEL_27;
      }
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_43:
  if ( Src )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DriveLayoutInformation;
}

```

## disassembly

```asm
0x1800677a4  mov     [rsp-8+arg_8], rbx
0x1800677a9  push    rbp
0x1800677aa  push    rsi
0x1800677ab  push    rdi
0x1800677ac  push    r12
0x1800677ae  push    r13
0x1800677b0  push    r14
0x1800677b2  push    r15
0x1800677b4  lea     rbp, [rsp-0B0h]
0x1800677bc  sub     rsp, 1B0h
0x1800677c3  xorps   xmm0, xmm0
0x1800677c6  mov     [rsp+1E0h+var_170], r8
0x1800677cb  mov     [rsp+1E0h+var_190], edx
0x1800677cf  mov     r13, rcx
0x1800677d2  xor     eax, eax
0x1800677d4  mov     [rsp+1E0h+var_168], r9
0x1800677d9  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x1800677dd  xor     edx, edx; Val
0x1800677df  mov     [rbp+0E0h+var_BC], eax
0x1800677e2  mov     r8d, 8Ch; Size
0x1800677e8  lea     rcx, [rbp+0E0h+var_C0]; void *
0x1800677ec  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x1800677f0  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x1800677f4  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x1800677f8  call    memset_0
0x1800677fd  xor     edi, edi
0x1800677ff  lea     rcx, [rbp+0E0h+var_160]; void *
0x180067803  xorps   xmm0, xmm0
0x180067806  mov     qword ptr [rsp+1E0h+Size+4], rdi
0x18006780b  xor     edx, edx; Val
0x18006780d  mov     [rsp+1E0h+FileHandle], rdi
0x180067812  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x180067816  lea     r8d, [rdi+48h]; Size
0x18006781a  mov     [rsp+1E0h+Src], rdi
0x18006781f  mov     r12d, edi
0x180067822  mov     [rsp+1E0h+P], rdi
0x180067827  mov     r14d, edi
0x18006782a  mov     dword ptr [rsp+1E0h+Size], edi
0x18006782e  mov     esi, edi
0x180067830  mov     [rsp+1E0h+var_1A0], edi
0x180067834  mov     r15d, edi
0x180067837  mov     [rsp+1E0h+var_188], rdi
0x18006783c  call    memset_0
0x180067841  lea     rdx, [rsp+1E0h+Size+4]
0x180067846  mov     rcx, r13; SourceString
0x180067849  call    BiGetDriveLayoutInformation
0x18006784e  test    eax, eax
0x180067850  jns     short loc_180067887
0x180067852  lea     rdx, [rsp+1E0h+var_188]
0x180067857  mov     rcx, r13
0x18006785a  call    BiGetPhysicalDriveName
0x18006785f  mov     r15, [rsp+1E0h+var_188]
0x180067864  mov     ebx, eax
0x180067866  test    eax, eax
0x180067868  js      short loc_18006787D
0x18006786a  lea     rdx, [rsp+1E0h+Size+4]
0x18006786f  mov     rcx, r15; SourceString
0x180067872  call    BiGetDriveLayoutInformation
0x180067877  mov     ebx, eax
0x180067879  test    eax, eax
0x18006787b  jns     short loc_180067887
0x18006787d  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x180067882  jmp     loc_180067BA5
0x180067887  test    byte ptr [rsp+1E0h+var_190], 40h
0x18006788c  mov     [rsp+1E0h+var_1B0], dil
0x180067891  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x180067896  jnz     loc_1800679B9
0x18006789c  mov     rcx, r13; SourceString
0x18006789f  call    BiGetPartitionVhdFilePath
0x1800678a4  mov     r14, rax
0x1800678a7  test    rax, rax
0x1800678aa  jz      loc_1800679B9
0x1800678b0  mov     r8d, 16h; MaxCount
0x1800678b6  lea     rdx, aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x1800678bd  mov     rcx, rax; String1
0x1800678c0  call    _wcsnicmp
0x1800678c5  test    eax, eax
0x1800678c7  jnz     short loc_180067930
0x1800678c9  lea     edx, [rax+5Ch]; Ch
0x1800678cc  lea     rcx, [r14+2Ch]; Str
0x1800678d0  call    cs:__imp_wcschr
0x1800678d7  nop     dword ptr [rax+rax+00h]
0x1800678dc  mov     rbx, rax
0x1800678df  test    rax, rax
0x1800678e2  jz      short loc_180067930
0x1800678e4  xor     ecx, ecx
0x1800678e6  mov     [rax], cx
0x1800678e9  mov     rcx, r14; SourceString
0x1800678ec  call    BiGetPartitionVhdFilePath
0x1800678f1  mov     word ptr [rbx], 5Ch ; '\'
0x1800678f6  mov     rsi, rax
0x1800678f9  test    rax, rax
0x1800678fc  jz      short loc_180067930
0x1800678fe  mov     r8, rax
0x180067901  lea     rdx, aBicreatepartit; "BiCreatePartitionDevice: NestedVhd dete"...
0x180067908  mov     ecx, 3
0x18006790d  call    BiLogMessage
0x180067912  mov     rcx, gs:60h
0x18006791b  mov     r8, rsi; P
0x18006791e  xor     edx, edx; Flags
0x180067920  mov     rcx, [rcx+30h]; HeapHandle
0x180067924  call    cs:__imp_RtlFreeHeap
0x18006792b  nop     dword ptr [rax+rax+00h]
0x180067930  mov     r8d, 35h ; '5'; MaxCount
0x180067936  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x18006793d  mov     rcx, r14; String1
0x180067940  call    _wcsnicmp
0x180067945  mov     rcx, r14; Src
0x180067948  test    eax, eax
0x18006794a  jnz     short loc_180067967
0x18006794c  lea     rdx, [rsp+1E0h+Src]
0x180067951  call    BiCreateVhdRamdiskBootDevice
0x180067956  mov     ebx, eax
0x180067958  test    eax, eax
0x18006795a  js      loc_180067BA5
0x180067960  mov     [rsp+1E0h+var_1B0], 1
0x180067965  jmp     short loc_1800679A6
0x180067967  lea     r8, [rsp+1E0h+var_1A0]
0x18006796c  lea     rdx, [rsp+1E0h+P]
0x180067971  call    BiCreateFileDeviceElement
0x180067976  mov     r12, [rsp+1E0h+P]
0x18006797b  mov     ebx, eax
0x18006797d  test    eax, eax
0x18006797f  js      loc_180067B82
0x180067985  mov     edx, [rsp+1E0h+var_1A0]
0x180067989  lea     r9, [rsp+1E0h+Src]
0x18006798e  mov     r8d, 40h ; '@'
0x180067994  mov     rcx, r12
0x180067997  call    BiConvertNtDeviceToBootEnvironment
0x18006799c  mov     ebx, eax
0x18006799e  test    eax, eax
0x1800679a0  js      loc_180067B82
0x1800679a6  mov     rax, [rsp+1E0h+Src]
0x1800679ab  mov     dword ptr [rbp+0E0h+var_140], 6
0x1800679b2  mov     esi, [rax+8]
0x1800679b5  mov     dword ptr [rsp+1E0h+Size], esi
0x1800679b9  cmp     dword ptr [rdi], 0
0x1800679bc  jnz     short loc_1800679CD
0x1800679be  mov     eax, [rdi+8]
0x1800679c1  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x1800679c4  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x1800679cb  jmp     short loc_1800679F3
0x1800679cd  cmp     dword ptr [rdi], 1
0x1800679d0  jnz     loc_180067B7D
0x1800679d6  mov     eax, [rdi+8]
0x1800679d9  movsd   xmm0, qword ptr [rdi+0Ch]
0x1800679de  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x1800679e1  mov     eax, [rdi+14h]
0x1800679e4  mov     [rbp+0E0h+var_12C], eax
0x1800679e7  mov     dword ptr [rbp+0E0h+var_140+4], 0
0x1800679ee  movsd   qword ptr [rbp+0E0h+var_140+0Ch], xmm0
0x1800679f3  mov     rdx, r13; SourceString
0x1800679f6  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1800679fa  call    cs:__imp_RtlInitUnicodeString
0x180067a01  nop     dword ptr [rax+rax+00h]
0x180067a06  lea     rax, [rbp+0E0h+DestinationString]
0x180067a0a  mov     [rsp+1E0h+OpenOptions], 20h ; ' '; OpenOptions
0x180067a12  xorps   xmm0, xmm0
0x180067a15  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x180067a19  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x180067a1d  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x180067a24  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x180067a28  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], 0
0x180067a30  mov     edx, 80100000h; DesiredAccess
0x180067a35  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180067a3c  lea     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x180067a41  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x180067a49  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180067a4e  call    cs:__imp_ZwOpenFile
0x180067a55  nop     dword ptr [rax+rax+00h]
0x180067a5a  mov     ebx, eax
0x180067a5c  test    eax, eax
0x180067a5e  js      loc_180067B82
0x180067a64  mov     edx, [rdi]; InputBufferLength
0x180067a66  lea     r8, [rbp+0E0h+var_C0]
0x180067a6a  mov     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x180067a6f  call    BiGetPartitionInformation
0x180067a74  mov     ebx, eax
0x180067a76  test    eax, eax
0x180067a78  js      loc_180067B82
0x180067a7e  mov     eax, [rbp+0E0h+var_C0]
0x180067a81  test    eax, eax
0x180067a83  jnz     short loc_180067A8F
0x180067a85  mov     rax, [rbp+0E0h+var_B8]
0x180067a89  mov     qword ptr [rbp+0E0h+var_150], rax
0x180067a8d  jmp     short loc_180067AA8
0x180067a8f  cmp     eax, 1
0x180067a92  jnz     loc_180067B7D
0x180067a98  mov     rax, qword ptr [rbp+0E0h+var_90]
0x180067a9c  mov     qword ptr [rbp+0E0h+var_150], rax
0x180067aa0  mov     rax, qword ptr [rbp+0E0h+var_90+8]
0x180067aa4  mov     qword ptr [rbp+0E0h+var_150+8], rax
0x180067aa8  mov     ecx, 48h ; 'H'
0x180067aad  lea     r13d, [rsi+38h]
0x180067ab1  mov     r8d, ecx
0x180067ab4  mov     eax, r13d
0x180067ab7  cmp     r13d, ecx
0x180067aba  mov     rcx, gs:60h
0x180067ac3  cmova   r8d, eax; Size
0x180067ac7  xor     edx, edx; Flags
0x180067ac9  mov     rcx, [rcx+30h]; HeapHandle
0x180067acd  call    cs:__imp_RtlAllocateHeap
0x180067ad4  nop     dword ptr [rax+rax+00h]
0x180067ad9  mov     rsi, rax
0x180067adc  test    rax, rax
0x180067adf  jnz     short loc_180067AEB
0x180067ae1  mov     ebx, 0C000009Ah
0x180067ae6  jmp     loc_180067B82
0x180067aeb  mov     eax, 48h ; 'H'
0x180067af0  mov     rcx, rsi; void *
0x180067af3  mov     r8d, eax
0x180067af6  cmp     r13d, eax
0x180067af9  mov     eax, r13d
0x180067afc  cmova   r8d, eax; Size
0x180067b00  xor     edx, edx; Val
0x180067b02  call    memset_0
0x180067b07  movaps  xmm1, [rbp+0E0h+var_150]
0x180067b0b  mov     eax, 48h ; 'H'
0x180067b10  cmp     r13d, eax
0x180067b13  mov     dword ptr [rbp+0E0h+var_160], 6
0x180067b1a  cmova   eax, r13d
0x180067b1e  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x180067b21  movaps  xmm0, [rbp+0E0h+var_160]
0x180067b25  movups  xmmword ptr [rsi], xmm0
0x180067b28  movaps  xmm0, [rbp+0E0h+var_140]
0x180067b2c  movups  xmmword ptr [rsi+10h], xmm1
0x180067b30  movaps  xmm1, xmmword ptr [rbp-50h]
0x180067b34  movups  xmmword ptr [rsi+20h], xmm0
0x180067b38  movsd   xmm0, [rbp+0E0h+var_120]
0x180067b3d  movups  xmmword ptr [rsi+30h], xmm1
0x180067b41  movsd   qword ptr [rsi+40h], xmm0
0x180067b46  test    r14, r14
0x180067b49  jz      short loc_180067B5E
0x180067b4b  mov     r8d, dword ptr [rsp+1E0h+Size]; Size
0x180067b50  lea     rcx, [rsi+38h]; void *
0x180067b54  mov     rdx, [rsp+1E0h+Src]; Src
0x180067b59  call    memcpy_0
0x180067b5e  cmp     [rsp+1E0h+var_1B0], 0
0x180067b63  jz      short loc_180067B69
0x180067b65  or      dword ptr [rsi+4], 8
0x180067b69  mov     rax, [rsp+1E0h+var_170]
0x180067b6e  mov     rcx, [rsp+1E0h+var_168]
0x180067b73  mov     [rax], rsi
0x180067b76  mov     eax, [rdi+4]
0x180067b79  mov     [rcx], eax
0x180067b7b  jmp     short loc_180067B82
0x180067b7d  mov     ebx, 0C000000Dh
0x180067b82  test    r12, r12
0x180067b85  jz      short loc_180067BA5
0x180067b87  mov     rcx, gs:60h
0x180067b90  mov     r8, r12; P
0x180067b93  xor     edx, edx; Flags
0x180067b95  mov     rcx, [rcx+30h]; HeapHandle
0x180067b99  call    cs:__imp_RtlFreeHeap
0x180067ba0  nop     dword ptr [rax+rax+00h]
0x180067ba5  cmp     [rsp+1E0h+Src], 0
0x180067bab  jz      short loc_180067BCD
0x180067bad  mov     rcx, gs:60h
0x180067bb6  xor     edx, edx; Flags
0x180067bb8  mov     r8, [rsp+1E0h+Src]; P
0x180067bbd  mov     rcx, [rcx+30h]; HeapHandle
0x180067bc1  call    cs:__imp_RtlFreeHeap
0x180067bc8  nop     dword ptr [rax+rax+00h]
0x180067bcd  test    r14, r14
0x180067bd0  jz      short loc_180067BF0
0x180067bd2  mov     rcx, gs:60h
0x180067bdb  mov     r8, r14; P
0x180067bde  xor     edx, edx; Flags
0x180067be0  mov     rcx, [rcx+30h]; HeapHandle
0x180067be4  call    cs:__imp_RtlFreeHeap
0x180067beb  nop     dword ptr [rax+rax+00h]
0x180067bf0  test    r15, r15
0x180067bf3  jz      short loc_180067C13
0x180067bf5  mov     rcx, gs:60h
0x180067bfe  mov     r8, r15; P
0x180067c01  xor     edx, edx; Flags
0x180067c03  mov     rcx, [rcx+30h]; HeapHandle
0x180067c07  call    cs:__imp_RtlFreeHeap
0x180067c0e  nop     dword ptr [rax+rax+00h]
0x180067c13  mov     rcx, [rsp+1E0h+FileHandle]; Handle
0x180067c18  test    rcx, rcx
0x180067c1b  jz      short loc_180067C29
0x180067c1d  call    cs:__imp_ZwClose
0x180067c24  nop     dword ptr [rax+rax+00h]
0x180067c29  test    rdi, rdi
0x180067c2c  jz      short loc_180067C4C
0x180067c2e  mov     rcx, gs:60h
0x180067c37  mov     r8, rdi; P
0x180067c3a  xor     edx, edx; Flags
0x180067c3c  mov     rcx, [rcx+30h]; HeapHandle
0x180067c40  call    cs:__imp_RtlFreeHeap
0x180067c47  nop     dword ptr [rax+rax+00h]
0x180067c4c  mov     eax, ebx
0x180067c4e  mov     rbx, [rsp+1E0h+arg_8]
0x180067c56  add     rsp, 1B0h
0x180067c5d  pop     r15
0x180067c5f  pop     r14
0x180067c61  pop     r13
0x180067c63  pop     r12
0x180067c65  pop     rdi
  ... truncated ...
```
