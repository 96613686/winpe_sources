# WimOpenOverlayConfig

- ea: `0x14003ca60`
- end: `0x14003cce8`
- name: `WimOpenOverlayConfig`
- size: `648`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002bdec`
- `0x14003c578`

## callees

- `0x14000fb60`
- `0x14000fce4`
- `0x1400119c0`
- `0x14002b348`
- `0x14003ca60`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb29`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb3c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb29`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003cb3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ccc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ccc5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cad0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cad0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003cb12`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003cb12`
- `FLTMGR!FltCreateFileEx` at `0x14003cbcf`
- `FLTMGR!FltCreateFileEx` at `0x14003cc7e`
- `FLTMGR!FltCreateFileEx` at `0x14003cbcf`
- `FLTMGR!FltCreateFileEx` at `0x14003cc7e`

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
0x14003ca60  push    rbp
0x14003ca62  push    rbx
0x14003ca63  push    rsi
0x14003ca64  push    rdi
0x14003ca65  push    r12
0x14003ca67  push    r13
0x14003ca69  push    r14
0x14003ca6b  push    r15
0x14003ca6d  lea     rbp, [rsp-17h]
0x14003ca72  sub     rsp, 0D8h
0x14003ca79  xorps   xmm0, xmm0
0x14003ca7c  lea     rdi, [rcx+40h]
0x14003ca80  xor     eax, eax
0x14003ca82  xorps   xmm1, xmm1
0x14003ca85  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ca89  mov     rsi, rcx
0x14003ca8c  movups  xmmword ptr [rbp+4Fh+var_70.ObjectName], xmm0
0x14003ca90  xor     ecx, ecx
0x14003ca92  mov     r13, r9
0x14003ca95  mov     r15b, r8b
0x14003ca98  mov     rbx, rdx
0x14003ca9b  movups  xmmword ptr [rbp+4Fh+var_70.Length], xmm0
0x14003ca9f  movups  xmmword ptr [rbp+4Fh+var_70+1Ch], xmm0
0x14003caa3  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x14003caa7  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x14003caab  inc     rax
0x14003caae  cmp     [rdx+rax*2], cx
0x14003cab2  jnz     short loc_14003CAAB
0x14003cab4  add     ax, 1Ch
0x14003cab8  mov     r8d, 66637077h; Tag
0x14003cabe  add     ax, ax
0x14003cac1  mov     ecx, 1; PoolType
0x14003cac6  add     ax, [rdi]
0x14003cac9  movzx   r12d, ax
0x14003cacd  mov     edx, r12d; NumberOfBytes
0x14003cad0  call    cs:__imp_ExAllocatePoolWithTag
0x14003cad7  nop     dword ptr [rax+rax+00h]
0x14003cadc  mov     r14, rax
0x14003cadf  test    rax, rax
0x14003cae2  jnz     short loc_14003CAEE
0x14003cae4  mov     eax, 0C000009Ah
0x14003cae9  jmp     loc_14003CCD3
0x14003caee  mov     r8, r12; Size
0x14003caf1  xor     edx, edx; Val
0x14003caf3  mov     rcx, r14; void *
0x14003caf6  call    memset
0x14003cafb  xorps   xmm0, xmm0
0x14003cafe  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14003cb02  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14003cb06  mov     rdx, rdi; SourceString
0x14003cb09  mov     [rbp+4Fh+DestinationString.MaximumLength], r12w
0x14003cb0e  mov     [rbp+4Fh+DestinationString.Buffer], r14
0x14003cb12  call    cs:__imp_RtlCopyUnicodeString
0x14003cb19  nop     dword ptr [rax+rax+00h]
0x14003cb1e  lea     rdx, Source; "\\System Volume Information\\"
0x14003cb25  lea     rcx, [rbp+4Fh+DestinationString]; Destination
0x14003cb29  call    cs:__imp_RtlAppendUnicodeToString
0x14003cb30  nop     dword ptr [rax+rax+00h]
0x14003cb35  mov     rdx, rbx; Source
0x14003cb38  lea     rcx, [rbp+4Fh+DestinationString]; Destination
0x14003cb3c  call    cs:__imp_RtlAppendUnicodeToString
0x14003cb43  nop     dword ptr [rax+rax+00h]
0x14003cb48  mov     r9, [rbp+4Fh+FileObject]; FileObject
0x14003cb4c  lea     rax, [rbp+4Fh+DestinationString]
0x14003cb50  mov     rdx, [rsi+78h]; Instance
0x14003cb54  xor     ecx, ecx
0x14003cb56  mov     [rsp+110h+Flags], ecx; Flags
0x14003cb5a  xorps   xmm0, xmm0
0x14003cb5d  mov     [rsp+110h+EaLength], ecx; EaLength
0x14003cb61  mov     r8, r13; FileHandle
0x14003cb64  mov     [rsp+110h+EaBuffer], rcx; EaBuffer
0x14003cb69  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14003cb71  mov     [rbp+4Fh+var_70.ObjectName], rax
0x14003cb75  mov     al, r15b
0x14003cb78  neg     al
0x14003cb7a  mov     [rbp+4Fh+var_70.RootDirectory], rcx
0x14003cb7e  lea     rax, [rbp+4Fh+var_80]
0x14003cb82  mov     [rbp+4Fh+var_70.Length], 30h ; '0'
0x14003cb89  sbb     r12d, r12d
0x14003cb8c  mov     [rbp+4Fh+var_70.Attributes], 240h
0x14003cb93  and     r12d, 4
0x14003cb97  inc     r12d
0x14003cb9a  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x14003cb9f  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x14003cba7  mov     [rsp+110h+FileAttributes], ecx; FileAttributes
0x14003cbab  mov     [rsp+110h+AllocationSize], rcx; AllocationSize
0x14003cbb0  mov     rcx, [rsi+68h]; Filter
0x14003cbb4  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14003cbb9  lea     rax, [rbp+4Fh+var_70]
0x14003cbbd  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14003cbc2  mov     [rsp+110h+DesiredAccess], 13019Fh; DesiredAccess
0x14003cbca  movdqu  xmmword ptr [rbp+4Fh+var_70.SecurityDescriptor], xmm0
0x14003cbcf  call    cs:__imp_FltCreateFileEx
0x14003cbd6  nop     dword ptr [rax+rax+00h]
0x14003cbdb  mov     ebx, eax
0x14003cbdd  cmp     eax, 0C000003Ah
0x14003cbe2  jnz     loc_14003CCC0
0x14003cbe8  test    r15b, r15b
0x14003cbeb  jz      loc_14003CCC0
0x14003cbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cbf8  mov     eax, [rcx+2Ch]
0x14003cbfb  test    al, 8
0x14003cbfd  jz      short loc_14003CC1A
0x14003cbff  cmp     byte ptr [rcx+29h], 3
0x14003cc03  jb      short loc_14003CC1A
0x14003cc05  mov     rcx, [rcx+18h]
0x14003cc09  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003cc10  mov     edx, 1Ah
0x14003cc15  call    WPP_SF_
0x14003cc1a  mov     rcx, rdi
0x14003cc1d  call    WimCreateSystemVolumeInformationFolder
0x14003cc22  mov     ebx, eax
0x14003cc24  xor     eax, eax
0x14003cc26  test    ebx, ebx
0x14003cc28  js      short loc_14003CC8E
0x14003cc2a  mov     r9, [rbp+4Fh+FileObject]; FileObject
0x14003cc2e  mov     r8, r13; FileHandle
0x14003cc31  mov     rdx, [rsi+78h]; Instance
0x14003cc35  mov     rcx, [rsi+68h]; Filter
0x14003cc39  mov     [rsp+110h+Flags], eax; Flags
0x14003cc3d  mov     [rsp+110h+EaLength], eax; EaLength
0x14003cc41  mov     [rsp+110h+EaBuffer], rax; EaBuffer
0x14003cc46  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14003cc4e  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x14003cc53  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x14003cc5b  mov     [rsp+110h+FileAttributes], eax; FileAttributes
0x14003cc5f  mov     [rsp+110h+AllocationSize], rax; AllocationSize
0x14003cc64  lea     rax, [rbp+4Fh+var_80]
0x14003cc68  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14003cc6d  lea     rax, [rbp+4Fh+var_70]
0x14003cc71  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14003cc76  mov     [rsp+110h+DesiredAccess], 13019Fh; DesiredAccess
0x14003cc7e  call    cs:__imp_FltCreateFileEx
0x14003cc85  nop     dword ptr [rax+rax+00h]
0x14003cc8a  mov     ebx, eax
0x14003cc8c  jmp     short loc_14003CCC0
0x14003cc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc95  test    dword ptr [rcx+2Ch], 400h
0x14003cc9c  jz      short loc_14003CCC0
0x14003cc9e  cmp     byte ptr [rcx+29h], 2
0x14003cca2  jb      short loc_14003CCC0
0x14003cca4  mov     rcx, [rcx+18h]
0x14003cca8  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003ccaf  mov     edx, 1Bh
0x14003ccb4  mov     [rsp+110h+DesiredAccess], ebx
0x14003ccb8  mov     r9, rdi
0x14003ccbb  call    WPP_SF_Zd
0x14003ccc0  xor     edx, edx; Tag
0x14003ccc2  mov     rcx, r14; P
0x14003ccc5  call    cs:__imp_ExFreePoolWithTag
0x14003cccc  nop     dword ptr [rax+rax+00h]
0x14003ccd1  mov     eax, ebx
0x14003ccd3  add     rsp, 0D8h
0x14003ccda  pop     r15
0x14003ccdc  pop     r14
0x14003ccde  pop     r13
0x14003cce0  pop     r12
0x14003cce2  pop     rdi
0x14003cce3  pop     rsi
0x14003cce4  pop     rbx
0x14003cce5  pop     rbp
0x14003cce6  retn
```
