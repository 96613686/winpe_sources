# WimOpenOverlayConfig

- ea: `0x14003cab0`
- end: `0x14003cd38`
- name: `WimOpenOverlayConfig`
- size: `648`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002be3c`
- `0x14003c5c8`

## callees

- `0x14000fb60`
- `0x14000fce4`
- `0x1400119c0`
- `0x14002b398`
- `0x14003cab0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb79`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb8c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb79`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cd15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cd15`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cb20`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cb20`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003cb62`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003cb62`
- `FLTMGR!FltCreateFileEx` at `0x14003cc1f`
- `FLTMGR!FltCreateFileEx` at `0x14003ccce`
- `FLTMGR!FltCreateFileEx` at `0x14003cc1f`
- `FLTMGR!FltCreateFileEx` at `0x14003ccce`

## pseudocode

```c
__int64 __fastcall WimOpenOverlayConfig(__int64 a1, const WCHAR *a2, char a3, void **a4, PFILE_OBJECT *FileObject)
{
  const UNICODE_STRING *v5; // rdi
  __int64 v6; // rax
  SIZE_T v11; // r12
  WCHAR *PoolWithTag; // rax
  WCHAR *v13; // r14
  struct _FLT_INSTANCE *v15; // rdx
  struct _FLT_FILTER *v16; // rcx
  NTSTATUS SystemVolumeInformationFolder; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-21h] BYREF

  v5 = (const UNICODE_STRING *)(a1 + 64);
  v6 = -1;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  do
    ++v6;
  while ( a2[v6] );
  v11 = (unsigned __int16)(v5->Length + 2 * (v6 + 28));
  PoolWithTag = (WCHAR *)ExAllocatePoolWithTag(PagedPool, v11, 0x66637077u);
  v13 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, v11);
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.MaximumLength = v11;
  DestinationString.Buffer = v13;
  RtlCopyUnicodeString(&DestinationString, v5);
  RtlAppendUnicodeToString(&DestinationString, L"\\System Volume Information\\");
  RtlAppendUnicodeToString(&DestinationString, a2);
  v15 = *(struct _FLT_INSTANCE **)(a1 + 120);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  v16 = *(struct _FLT_FILTER **)(a1 + 104);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  SystemVolumeInformationFolder = FltCreateFileEx(
                                    v16,
                                    v15,
                                    a4,
                                    FileObject,
                                    0x13019Fu,
                                    &ObjectAttributes,
                                    &IoStatusBlock,
                                    0,
                                    0,
                                    1u,
                                    a3 != 0 ? 5 : 1,
                                    0x60u,
                                    0,
                                    0,
                                    0);
  if ( SystemVolumeInformationFolder == -1073741766 && a3 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids);
    SystemVolumeInformationFolder = WimCreateSystemVolumeInformationFolder(v5);
    if ( SystemVolumeInformationFolder < 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
          (_DWORD)v5,
          SystemVolumeInformationFolder);
    }
    else
    {
      SystemVolumeInformationFolder = FltCreateFileEx(
                                        *(PFLT_FILTER *)(a1 + 104),
                                        *(PFLT_INSTANCE *)(a1 + 120),
                                        a4,
                                        FileObject,
                                        0x13019Fu,
                                        &ObjectAttributes,
                                        &IoStatusBlock,
                                        0,
                                        0,
                                        1u,
                                        a3 != 0 ? 5 : 1,
                                        0x60u,
                                        0,
                                        0,
                                        0);
    }
  }
  ExFreePoolWithTag(v13, 0);
  return (unsigned int)SystemVolumeInformationFolder;
}

```

## disassembly

```asm
0x14003cab0  push    rbp
0x14003cab2  push    rbx
0x14003cab3  push    rsi
0x14003cab4  push    rdi
0x14003cab5  push    r12
0x14003cab7  push    r13
0x14003cab9  push    r14
0x14003cabb  push    r15
0x14003cabd  lea     rbp, [rsp-17h]
0x14003cac2  sub     rsp, 0D8h
0x14003cac9  xorps   xmm0, xmm0
0x14003cacc  lea     rdi, [rcx+40h]
0x14003cad0  xor     eax, eax
0x14003cad2  xorps   xmm1, xmm1
0x14003cad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003cad9  mov     rsi, rcx
0x14003cadc  movups  xmmword ptr [rbp+4Fh+var_70.ObjectName], xmm0
0x14003cae0  xor     ecx, ecx
0x14003cae2  mov     r13, r9
0x14003cae5  mov     r15b, r8b
0x14003cae8  mov     rbx, rdx
0x14003caeb  movups  xmmword ptr [rbp+4Fh+var_70.Length], xmm0
0x14003caef  movups  xmmword ptr [rbp+4Fh+var_70+1Ch], xmm0
0x14003caf3  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x14003caf7  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x14003cafb  inc     rax
0x14003cafe  cmp     [rdx+rax*2], cx
0x14003cb02  jnz     short loc_14003CAFB
0x14003cb04  add     ax, 1Ch
0x14003cb08  mov     r8d, 66637077h; Tag
0x14003cb0e  add     ax, ax
0x14003cb11  mov     ecx, 1; PoolType
0x14003cb16  add     ax, [rdi]
0x14003cb19  movzx   r12d, ax
0x14003cb1d  mov     edx, r12d; NumberOfBytes
0x14003cb20  call    cs:__imp_ExAllocatePoolWithTag
0x14003cb27  nop     dword ptr [rax+rax+00h]
0x14003cb2c  mov     r14, rax
0x14003cb2f  test    rax, rax
0x14003cb32  jnz     short loc_14003CB3E
0x14003cb34  mov     eax, 0C000009Ah
0x14003cb39  jmp     loc_14003CD23
0x14003cb3e  mov     r8, r12; Size
0x14003cb41  xor     edx, edx; Val
0x14003cb43  mov     rcx, r14; void *
0x14003cb46  call    memset
0x14003cb4b  xorps   xmm0, xmm0
0x14003cb4e  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14003cb52  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14003cb56  mov     rdx, rdi; SourceString
0x14003cb59  mov     [rbp+4Fh+DestinationString.MaximumLength], r12w
0x14003cb5e  mov     [rbp+4Fh+DestinationString.Buffer], r14
0x14003cb62  call    cs:__imp_RtlCopyUnicodeString
0x14003cb69  nop     dword ptr [rax+rax+00h]
0x14003cb6e  lea     rdx, Source; "\\System Volume Information\\"
0x14003cb75  lea     rcx, [rbp+4Fh+DestinationString]; Destination
0x14003cb79  call    cs:__imp_RtlAppendUnicodeToString
0x14003cb80  nop     dword ptr [rax+rax+00h]
0x14003cb85  mov     rdx, rbx; Source
0x14003cb88  lea     rcx, [rbp+4Fh+DestinationString]; Destination
0x14003cb8c  call    cs:__imp_RtlAppendUnicodeToString
0x14003cb93  nop     dword ptr [rax+rax+00h]
0x14003cb98  mov     r9, [rbp+4Fh+FileObject]; FileObject
0x14003cb9c  lea     rax, [rbp+4Fh+DestinationString]
0x14003cba0  mov     rdx, [rsi+78h]; Instance
0x14003cba4  xor     ecx, ecx
0x14003cba6  mov     [rsp+110h+Flags], ecx; Flags
0x14003cbaa  xorps   xmm0, xmm0
0x14003cbad  mov     [rsp+110h+EaLength], ecx; EaLength
0x14003cbb1  mov     r8, r13; FileHandle
0x14003cbb4  mov     [rsp+110h+EaBuffer], rcx; EaBuffer
0x14003cbb9  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14003cbc1  mov     [rbp+4Fh+var_70.ObjectName], rax
0x14003cbc5  mov     al, r15b
0x14003cbc8  neg     al
0x14003cbca  mov     [rbp+4Fh+var_70.RootDirectory], rcx
0x14003cbce  lea     rax, [rbp+4Fh+var_80]
0x14003cbd2  mov     [rbp+4Fh+var_70.Length], 30h ; '0'
0x14003cbd9  sbb     r12d, r12d
0x14003cbdc  mov     [rbp+4Fh+var_70.Attributes], 240h
0x14003cbe3  and     r12d, 4
0x14003cbe7  inc     r12d
0x14003cbea  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x14003cbef  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x14003cbf7  mov     [rsp+110h+FileAttributes], ecx; FileAttributes
0x14003cbfb  mov     [rsp+110h+AllocationSize], rcx; AllocationSize
0x14003cc00  mov     rcx, [rsi+68h]; Filter
0x14003cc04  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14003cc09  lea     rax, [rbp+4Fh+var_70]
0x14003cc0d  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14003cc12  mov     [rsp+110h+DesiredAccess], 13019Fh; DesiredAccess
0x14003cc1a  movdqu  xmmword ptr [rbp+4Fh+var_70.SecurityDescriptor], xmm0
0x14003cc1f  call    cs:__imp_FltCreateFileEx
0x14003cc26  nop     dword ptr [rax+rax+00h]
0x14003cc2b  mov     ebx, eax
0x14003cc2d  cmp     eax, 0C000003Ah
0x14003cc32  jnz     loc_14003CD10
0x14003cc38  test    r15b, r15b
0x14003cc3b  jz      loc_14003CD10
0x14003cc41  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc48  mov     eax, [rcx+2Ch]
0x14003cc4b  test    al, 8
0x14003cc4d  jz      short loc_14003CC6A
0x14003cc4f  cmp     byte ptr [rcx+29h], 3
0x14003cc53  jb      short loc_14003CC6A
0x14003cc55  mov     rcx, [rcx+18h]
0x14003cc59  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003cc60  mov     edx, 1Ah
0x14003cc65  call    WPP_SF_
0x14003cc6a  mov     rcx, rdi
0x14003cc6d  call    WimCreateSystemVolumeInformationFolder
0x14003cc72  mov     ebx, eax
0x14003cc74  xor     eax, eax
0x14003cc76  test    ebx, ebx
0x14003cc78  js      short loc_14003CCDE
0x14003cc7a  mov     r9, [rbp+4Fh+FileObject]; FileObject
0x14003cc7e  mov     r8, r13; FileHandle
0x14003cc81  mov     rdx, [rsi+78h]; Instance
0x14003cc85  mov     rcx, [rsi+68h]; Filter
0x14003cc89  mov     [rsp+110h+Flags], eax; Flags
0x14003cc8d  mov     [rsp+110h+EaLength], eax; EaLength
0x14003cc91  mov     [rsp+110h+EaBuffer], rax; EaBuffer
0x14003cc96  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14003cc9e  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x14003cca3  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x14003ccab  mov     [rsp+110h+FileAttributes], eax; FileAttributes
0x14003ccaf  mov     [rsp+110h+AllocationSize], rax; AllocationSize
0x14003ccb4  lea     rax, [rbp+4Fh+var_80]
0x14003ccb8  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14003ccbd  lea     rax, [rbp+4Fh+var_70]
0x14003ccc1  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14003ccc6  mov     [rsp+110h+DesiredAccess], 13019Fh; DesiredAccess
0x14003ccce  call    cs:__imp_FltCreateFileEx
0x14003ccd5  nop     dword ptr [rax+rax+00h]
0x14003ccda  mov     ebx, eax
0x14003ccdc  jmp     short loc_14003CD10
0x14003ccde  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cce5  test    dword ptr [rcx+2Ch], 400h
0x14003ccec  jz      short loc_14003CD10
0x14003ccee  cmp     byte ptr [rcx+29h], 2
0x14003ccf2  jb      short loc_14003CD10
0x14003ccf4  mov     rcx, [rcx+18h]
0x14003ccf8  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003ccff  mov     edx, 1Bh
0x14003cd04  mov     [rsp+110h+DesiredAccess], ebx
0x14003cd08  mov     r9, rdi
0x14003cd0b  call    WPP_SF_Zd
0x14003cd10  xor     edx, edx; Tag
0x14003cd12  mov     rcx, r14; P
0x14003cd15  call    cs:__imp_ExFreePoolWithTag
0x14003cd1c  nop     dword ptr [rax+rax+00h]
0x14003cd21  mov     eax, ebx
0x14003cd23  add     rsp, 0D8h
0x14003cd2a  pop     r15
0x14003cd2c  pop     r14
0x14003cd2e  pop     r13
0x14003cd30  pop     r12
0x14003cd32  pop     rdi
0x14003cd33  pop     rsi
0x14003cd34  pop     rbx
0x14003cd35  pop     rbp
0x14003cd36  retn
```
