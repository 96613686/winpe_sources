# OpenVirtualDiskInternal

- ea: `0x180003930`
- end: `0x180003d25`
- name: `OpenVirtualDiskInternal`
- size: `1013`
- prototype: `__int64 __fastcall(unsigned int *, void *, int, int, __int64, int *, HANDLE *, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002740`
- `0x180004f60`
- `0x180005200`

## callees

- `0x180003930`
- `0x180003d30`
- `0x180004060`
- `0x180005730`
- `0x180005fd6`
- `0x18000981c`
- `0x180009890`
- `0x18000ac64`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ca1`
- `ntdll!NtCreateFile` at `0x180003c5d`
- `ntdll!NtCreateFile` at `0x180003c5d`
- `ntdll!RtlNtStatusToDosError` at `0x180003c7b`
- `ntdll!RtlNtStatusToDosError` at `0x180003c7b`
- `ntdll!RtlFreeHeap` at `0x180003cc4`
- `ntdll!RtlFreeHeap` at `0x180003cc4`
- `ntdll!RtlInitUnicodeString` at `0x180003bd8`
- `ntdll!RtlInitUnicodeString` at `0x180003bd8`

## pseudocode

```c
__int64 __fastcall OpenVirtualDiskInternal(
        unsigned int *a1,
        void *a2,
        int a3,
        int a4,
        __int64 a5,
        int *a6,
        HANDLE *a7,
        char a8)
{
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r9
  __int128 v15; // xmm0
  ULONG VirtualDiskShimForFile; // ebx
  int v17; // ebx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // ecx
  __int128 v23; // xmm0
  char v24; // al
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // eax
  int Status; // eax
  __int64 v29; // rdx
  HANDLE v30; // rcx
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[20]; // [rsp+78h] [rbp-88h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE TokenHandle[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD EaBuffer[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v40; // [rsp+F8h] [rbp-8h]
  GUID v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+110h] [rbp+10h]
  __int128 v43; // [rsp+114h] [rbp+14h]
  int v44; // [rsp+124h] [rbp+24h]
  int v45; // [rsp+128h] [rbp+28h]
  int v46; // [rsp+12Ch] [rbp+2Ch]
  int v47; // [rsp+130h] [rbp+30h] BYREF
  int v48; // [rsp+134h] [rbp+34h]
  int v49; // [rsp+138h] [rbp+38h]
  int v50; // [rsp+13Ch] [rbp+3Ch]
  __int128 v51; // [rsp+140h] [rbp+40h]
  char v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+154h] [rbp+54h]
  int v54; // [rsp+158h] [rbp+58h]
  char v55[29]; // [rsp+15Ch] [rbp+5Ch] BYREF
  __int64 v56; // [rsp+179h] [rbp+79h]
  __int64 v57; // [rsp+181h] [rbp+81h]

  FileHandle = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(EaBuffer, 0, 0x9Cu);
  *(_OWORD *)TokenHandle = 0;
  if ( (Microsoft_Windows_VIRTDISKEnableBits & 1) != 0 )
  {
    v14 = 0;
    if ( a1 )
      v14 = *a1;
    McTemplateU0zq_EventWriteTransfer(v13, v12, a2, v14);
  }
  v15 = *(_OWORD *)a1;
  *(_DWORD *)&v34[16] = a1[4];
  *(_OWORD *)v34 = v15;
  VirtualDiskShimForFile = FindVirtualDiskShimForFile(a2, (__int64)&hObject);
  if ( !VirtualDiskShimForFile )
  {
    v17 = *(_DWORD *)v34;
    if ( a8 )
      *a1 = *(_DWORD *)v34;
    memset_0(&v47, 0, 0x5Cu);
    v40 = 0x4B534454524956LL;
    v41 = GUID_DEVINTERFACE_SURFACE_VIRTUAL_DRIVE;
    EaBuffer[0] = 0;
    EaBuffer[1] = 5506944;
    v42 = v17;
    v44 = 84;
    v45 = a4;
    v46 = a3;
    v43 = *(_OWORD *)&v34[4];
    if ( !a6 || (v18 = *a6, *a6 == 1) )
    {
      v48 = 1;
      if ( (a3 & 0x320000) != 0 )
      {
        if ( a6 )
          v27 = a6[1];
        else
          v27 = 1;
      }
      else if ( a6 )
      {
        v27 = a6[1];
      }
      else
      {
        v27 = 0;
      }
      v47 = v27;
    }
    else
    {
      if ( v18 == 2 )
      {
        v48 = 2;
        v49 = a6[1];
        v50 = a6[2];
        v19 = *(_QWORD *)(a6 + 3);
        v47 = 0;
        v20 = v19 - v56;
        if ( !v20 )
          v20 = *(_QWORD *)(a6 + 5) - v57;
        if ( !v20 )
          goto LABEL_30;
      }
      else
      {
        if ( v18 != 3 )
          goto LABEL_30;
        v22 = a6[2];
        v23 = *(_OWORD *)(a6 + 7);
        v49 = a6[1];
        v24 = 1;
        if ( !v22 )
          v24 = 4;
        v48 = 2;
        v52 = v24;
        v25 = *(_QWORD *)(a6 + 3);
        v47 = 0;
        v50 = v22;
        v51 = v23;
        v26 = v25 - v56;
        if ( !v26 )
          v26 = *(_QWORD *)(a6 + 5) - v57;
        if ( !v26 )
          goto LABEL_30;
      }
      v56 = *(_QWORD *)(a6 + 3);
      v21 = *(_QWORD *)(a6 + 5);
      strcpy(v55, "ClusteredApplicationInstance");
      v57 = v21;
      v53 = 0;
      v54 = 1055744;
      EaBuffer[0] = 100;
    }
LABEL_30:
    RtlInitUnicodeString(&DestinationString, 0);
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    if ( v48 == 1 )
      TryEnableManageVolumePrivilege(TokenHandle);
    Status = NtCreateFile(
               &FileHandle,
               0xC0100000,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0x80u,
               1u,
               1u,
               0x48u,
               EaBuffer,
               0x9Cu);
    if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
      VirtualDiskShimForFile = RtlNtStatusToDosError(Status);
    else
      VirtualDiskShimForFile = 0;
  }
  RevertManageVolumePrivilege(TokenHandle);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v30 = FileHandle;
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    *a7 = FileHandle;
  if ( (Microsoft_Windows_VIRTDISKEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(v30, v29, *a7, VirtualDiskShimForFile);
  return VirtualDiskShimForFile;
}

```

## disassembly

```asm
0x180003930  mov     [rsp-8+arg_10], rbx
0x180003935  push    rbp
0x180003936  push    rsi
0x180003937  push    rdi
0x180003938  push    r12
0x18000393a  push    r13
0x18000393c  push    r14
0x18000393e  push    r15
0x180003940  lea     rbp, [rsp-0A0h]
0x180003948  sub     rsp, 1A0h
0x18000394f  mov     rax, cs:__security_cookie
0x180003956  xor     rax, rsp
0x180003959  mov     [rbp+0D0h+var_40], rax
0x180003960  mov     r12, [rbp+0D0h+arg_30]
0x180003967  xorps   xmm0, xmm0
0x18000396a  mov     r14d, r8d
0x18000396d  mov     [rsp+1D0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180003976  mov     rbx, rdx
0x180003979  mov     [rsp+1D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180003982  mov     rsi, rcx
0x180003985  xorps   xmm1, xmm1
0x180003988  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.ObjectName], xmm0
0x18000398c  xor     r13d, r13d
0x18000398f  lea     rcx, [rbp+0D0h+var_E0]; void *
0x180003993  xor     eax, eax
0x180003995  mov     [rsp+1D0h+SourceString], r13
0x18000399a  xor     edx, edx; Val
0x18000399c  mov     r8d, 9Ch; Size
0x1800039a2  movups  xmmword ptr [rbp+0D0h+ObjectAttributes+1Ch], xmm0
0x1800039a6  mov     r15d, r9d
0x1800039a9  movups  xmmword ptr [rbp+0D0h+DestinationString.Length], xmm0
0x1800039ad  movups  xmmword ptr [rbp+0D0h+IoStatusBlock], xmm1
0x1800039b1  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.Length], xmm0
0x1800039b5  call    memset_0
0x1800039ba  test    cs:Microsoft_Windows_VIRTDISKEnableBits, 1
0x1800039c1  xorps   xmm0, xmm0
0x1800039c4  movups  xmmword ptr [rbp+0D0h+TokenHandle], xmm0
0x1800039c8  jz      short loc_1800039DD
0x1800039ca  mov     r9d, r13d
0x1800039cd  test    rsi, rsi
0x1800039d0  jz      short loc_1800039D5
0x1800039d2  mov     r9d, [rsi]
0x1800039d5  mov     r8, rbx
0x1800039d8  call    McTemplateU0zq_EventWriteTransfer
0x1800039dd  mov     eax, [rsi+10h]
0x1800039e0  lea     r9, [rsp+1D0h+var_158]
0x1800039e5  movups  xmm0, xmmword ptr [rsi]
0x1800039e8  mov     edx, [rbp+0D0h+arg_20]
0x1800039ee  lea     r8, [rsp+1D0h+SourceString]
0x1800039f3  mov     [rbp+0D0h+var_148], eax
0x1800039f6  mov     rcx, rbx; Src
0x1800039f9  lea     rax, [rsp+1D0h+hObject]
0x1800039fe  movups  [rsp+1D0h+var_158], xmm0
0x180003a03  mov     [rsp+1D0h+AllocationSize], rax; __int64
0x180003a08  call    FindVirtualDiskShimForFile
0x180003a0d  mov     rdi, [rsp+1D0h+SourceString]
0x180003a12  mov     ebx, eax
0x180003a14  test    eax, eax
0x180003a16  jnz     loc_180003C89
0x180003a1c  mov     ebx, dword ptr [rsp+1D0h+var_158]
0x180003a20  cmp     [rbp+0D0h+arg_38], r13b
0x180003a27  jz      short loc_180003A2B
0x180003a29  mov     [rsi], ebx
0x180003a2b  xor     edx, edx; Val
0x180003a2d  lea     rcx, [rbp+0D0h+var_A0]; void *
0x180003a31  mov     r8d, 5Ch ; '\'; Size
0x180003a37  call    memset_0
0x180003a3c  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_SURFACE_VIRTUAL_DRIVE.Data1
0x180003a43  mov     rdx, [rbp+0D0h+arg_28]
0x180003a4a  mov     rax, 4B534454524956h
0x180003a54  mov     [rbp+0D0h+var_D8], rax
0x180003a58  mov     eax, 54h ; 'T'
0x180003a5d  movaps  [rbp+0D0h+var_D0], xmm0
0x180003a61  mov     [rbp+0D0h+var_E0], r13d
0x180003a65  mov     [rbp+0D0h+var_DC], 540780h
0x180003a6c  mov     [rbp+0D0h+var_C0], ebx
0x180003a6f  mov     [rbp+0D0h+var_AC], eax
0x180003a72  mov     [rbp+0D0h+var_A8], r15d
0x180003a76  mov     [rbp+0D0h+var_A4], r14d
0x180003a7a  movups  xmm0, [rsp+1D0h+var_158+4]
0x180003a7f  movups  [rbp+0D0h+var_BC], xmm0
0x180003a83  test    rdx, rdx
0x180003a86  jz      loc_180003BA0
0x180003a8c  mov     eax, [rdx]
0x180003a8e  cmp     eax, 1
0x180003a91  jz      loc_180003BA0
0x180003a97  cmp     eax, 2
0x180003a9a  jnz     short loc_180003B0D
0x180003a9c  mov     [rbp+0D0h+var_9C], eax
0x180003a9f  mov     eax, [rdx+4]
0x180003aa2  mov     [rbp+0D0h+var_98], eax
0x180003aa5  mov     eax, [rdx+8]
0x180003aa8  mov     [rbp+0D0h+var_94], eax
0x180003aab  mov     rax, [rdx+0Ch]
0x180003aaf  mov     [rbp+0D0h+var_A0], r13d
0x180003ab3  sub     rax, [rbp+0D0h+var_57]
0x180003ab7  jnz     short loc_180003AC4
0x180003ab9  mov     rax, [rdx+14h]
0x180003abd  sub     rax, [rbp+0D0h+var_4F]
0x180003ac4  test    rax, rax
0x180003ac7  jz      loc_180003BD1
0x180003acd  mov     rax, [rdx+0Ch]
0x180003ad1  movups  xmm0, xmmword ptr cs:aClusteredappli; "ClusteredApplicationInstance"
0x180003ad8  mov     [rbp+0D0h+var_57], rax
0x180003adc  movups  xmm1, xmmword ptr cs:aClusteredappli+0Dh; "icationInstance"
0x180003ae3  mov     rax, [rdx+14h]
0x180003ae7  movups  xmmword ptr [rbp+0D0h+var_74], xmm0
0x180003aeb  mov     [rbp+0D0h+var_4F], rax
0x180003af2  movups  xmmword ptr [rbp+0D0h+var_74+0Dh], xmm1
0x180003af6  mov     [rbp+0D0h+var_7C], r13d
0x180003afa  mov     [rbp+0D0h+var_78], 101C00h
0x180003b01  mov     [rbp+0D0h+var_E0], 64h ; 'd'
0x180003b08  jmp     loc_180003BD1
0x180003b0d  cmp     eax, 3
0x180003b10  jnz     loc_180003BD1
0x180003b16  mov     eax, [rdx+4]
0x180003b19  mov     r8d, 4
0x180003b1f  mov     ecx, [rdx+8]
0x180003b22  test    ecx, ecx
0x180003b24  movups  xmm0, xmmword ptr [rdx+1Ch]
0x180003b28  mov     [rbp+0D0h+var_98], eax
0x180003b2b  mov     eax, 1
0x180003b30  cmovz   eax, r8d
0x180003b34  mov     [rbp+0D0h+var_9C], 2
0x180003b3b  mov     [rbp+0D0h+var_80], al
0x180003b3e  mov     rax, [rdx+0Ch]
0x180003b42  mov     [rbp+0D0h+var_A0], r13d
0x180003b46  mov     [rbp+0D0h+var_94], ecx
0x180003b49  movaps  [rbp+0D0h+var_90], xmm0
0x180003b4d  sub     rax, [rbp+0D0h+var_57]
0x180003b51  jnz     short loc_180003B5E
0x180003b53  mov     rax, [rdx+14h]
0x180003b57  sub     rax, [rbp+0D0h+var_4F]
0x180003b5e  test    rax, rax
0x180003b61  jz      short loc_180003BD1
0x180003b63  mov     rax, [rdx+0Ch]
0x180003b67  movups  xmm0, xmmword ptr cs:aClusteredappli; "ClusteredApplicationInstance"
0x180003b6e  mov     [rbp+0D0h+var_57], rax
0x180003b72  movups  xmm1, xmmword ptr cs:aClusteredappli+0Dh; "icationInstance"
0x180003b79  mov     rax, [rdx+14h]
0x180003b7d  movups  xmmword ptr [rbp+0D0h+var_74], xmm0
0x180003b81  mov     [rbp+0D0h+var_4F], rax
0x180003b88  movups  xmmword ptr [rbp+0D0h+var_74+0Dh], xmm1
0x180003b8c  mov     [rbp+0D0h+var_7C], r13d
0x180003b90  mov     [rbp+0D0h+var_78], 101C00h
0x180003b97  mov     [rbp+0D0h+var_E0], 64h ; 'd'
0x180003b9e  jmp     short loc_180003BD1
0x180003ba0  mov     [rbp+0D0h+var_9C], 1
0x180003ba7  test    r14d, 320000h
0x180003bae  jz      short loc_180003BC1
0x180003bb0  test    rdx, rdx
0x180003bb3  jz      short loc_180003BBA
0x180003bb5  mov     eax, [rdx+4]
0x180003bb8  jmp     short loc_180003BCE
0x180003bba  mov     eax, 1
0x180003bbf  jmp     short loc_180003BCE
0x180003bc1  test    rdx, rdx
0x180003bc4  jz      short loc_180003BCB
0x180003bc6  mov     eax, [rdx+4]
0x180003bc9  jmp     short loc_180003BCE
0x180003bcb  mov     eax, r13d
0x180003bce  mov     [rbp+0D0h+var_A0], eax
0x180003bd1  mov     rdx, rdi; SourceString
0x180003bd4  lea     rcx, [rbp+0D0h+DestinationString]; DestinationString
0x180003bd8  call    cs:__imp_RtlInitUnicodeString
0x180003bdf  nop     dword ptr [rax+rax+00h]
0x180003be4  cmp     [rbp+0D0h+var_9C], 1
0x180003be8  lea     rax, [rbp+0D0h+DestinationString]
0x180003bec  xorps   xmm0, xmm0
0x180003bef  mov     [rbp+0D0h+ObjectAttributes.ObjectName], rax
0x180003bf3  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003bf8  mov     [rbp+0D0h+ObjectAttributes.Length], 30h ; '0'
0x180003bff  mov     [rbp+0D0h+ObjectAttributes.RootDirectory], r13
0x180003c03  mov     [rbp+0D0h+ObjectAttributes.Attributes], 40h ; '@'
0x180003c0a  jnz     short loc_180003C15
0x180003c0c  lea     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x180003c10  call    TryEnableManageVolumePrivilege
0x180003c15  mov     [rsp+1D0h+EaLength], 9Ch; EaLength
0x180003c1d  lea     rax, [rbp+0D0h+var_E0]
0x180003c21  mov     [rsp+1D0h+EaBuffer], rax; EaBuffer
0x180003c26  lea     r9, [rbp+0D0h+IoStatusBlock]; IoStatusBlock
0x180003c2a  mov     [rsp+1D0h+CreateOptions], 48h ; 'H'; CreateOptions
0x180003c32  lea     r8, [rbp+0D0h+ObjectAttributes]; ObjectAttributes
0x180003c36  mov     [rsp+1D0h+CreateDisposition], 1; CreateDisposition
0x180003c3e  lea     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x180003c43  mov     [rsp+1D0h+ShareAccess], 1; ShareAccess
0x180003c4b  mov     edx, 0C0100000h; DesiredAccess
0x180003c50  mov     [rsp+1D0h+FileAttributes], 80h; FileAttributes
0x180003c58  mov     [rsp+1D0h+AllocationSize], r13; AllocationSize
0x180003c5d  call    cs:__imp_NtCreateFile
0x180003c64  nop     dword ptr [rax+rax+00h]
0x180003c69  test    eax, eax
0x180003c6b  js      short loc_180003C79
0x180003c6d  mov     eax, dword ptr [rbp+0D0h+IoStatusBlock]
0x180003c70  test    eax, eax
0x180003c72  js      short loc_180003C79
0x180003c74  mov     ebx, r13d
0x180003c77  jmp     short loc_180003C89
0x180003c79  mov     ecx, eax; Status
0x180003c7b  call    cs:__imp_RtlNtStatusToDosError
0x180003c82  nop     dword ptr [rax+rax+00h]
0x180003c87  mov     ebx, eax
0x180003c89  lea     rcx, [rbp+0D0h+TokenHandle]
0x180003c8d  call    RevertManageVolumePrivilege
0x180003c92  mov     rcx, [rsp+1D0h+hObject]; hObject
0x180003c97  lea     rax, [rcx-1]
0x180003c9b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003c9f  ja      short loc_180003CAD
0x180003ca1  call    cs:__imp_CloseHandle
0x180003ca8  nop     dword ptr [rax+rax+00h]
0x180003cad  test    rdi, rdi
0x180003cb0  jz      short loc_180003CD0
0x180003cb2  mov     rcx, gs:60h
0x180003cbb  mov     r8, rdi; P
0x180003cbe  xor     edx, edx; Flags
0x180003cc0  mov     rcx, [rcx+30h]; HeapHandle
0x180003cc4  call    cs:__imp_RtlFreeHeap
0x180003ccb  nop     dword ptr [rax+rax+00h]
0x180003cd0  mov     rcx, [rsp+1D0h+FileHandle]
0x180003cd5  lea     rax, [rcx-1]
0x180003cd9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003cdd  ja      short loc_180003CE3
0x180003cdf  mov     [r12], rcx
0x180003ce3  test    cs:Microsoft_Windows_VIRTDISKEnableBits, 1
0x180003cea  jz      short loc_180003CF8
0x180003cec  mov     r8, [r12]
0x180003cf0  mov     r9d, ebx
0x180003cf3  call    McTemplateU0pq_EventWriteTransfer
0x180003cf8  mov     eax, ebx
0x180003cfa  mov     rcx, [rbp+0D0h+var_40]
0x180003d01  xor     rcx, rsp; StackCookie
0x180003d04  call    __security_check_cookie
0x180003d09  mov     rbx, [rsp+1D0h+arg_10]
0x180003d11  add     rsp, 1A0h
0x180003d18  pop     r15
0x180003d1a  pop     r14
0x180003d1c  pop     r13
0x180003d1e  pop     r12
0x180003d20  pop     rdi
0x180003d21  pop     rsi
0x180003d22  pop     rbp
0x180003d23  retn
```
