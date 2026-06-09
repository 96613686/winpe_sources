# WimFSFQueryIntegrityStatusOfWim

- ea: `0x140028924`
- end: `0x140028b78`
- name: `WimFSFQueryIntegrityStatusOfWim`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140026fb0`

## callees

- `0x140011560`
- `0x140028924`
- `0x140029ae0`
- `0x14002a090`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028ac3`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028ac3`
- `ntoskrnl!ObfDereferenceObject` at `0x140028a4f`
- `ntoskrnl!ObfDereferenceObject` at `0x140028b30`
- `ntoskrnl!ObfDereferenceObject` at `0x140028a4f`
- `ntoskrnl!ObfDereferenceObject` at `0x140028b30`
- `FLTMGR!FltCreateFileEx` at `0x1400289f9`
- `FLTMGR!FltCreateFileEx` at `0x1400289f9`
- `FLTMGR!FltQueryInformationFile` at `0x140028a32`
- `FLTMGR!FltQueryInformationFile` at `0x140028a32`
- `FLTMGR!FltClose` at `0x140028a63`
- `FLTMGR!FltClose` at `0x140028b49`
- `FLTMGR!FltClose` at `0x140028a63`
- `FLTMGR!FltClose` at `0x140028b49`

## pseudocode

```c
__int64 __fastcall WimFSFQueryIntegrityStatusOfWim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        void *a5,
        _QWORD *a6,
        unsigned __int64 *a7)
{
  struct _FLT_INSTANCE *v9; // rdx
  struct _FLT_FILTER *v11; // rcx
  int v12; // edi
  int v13; // eax
  char v15; // [rsp+80h] [rbp-80h] BYREF
  char v16[7]; // [rsp+81h] [rbp-7Fh] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-18h]

  v22 = 0;
  v9 = *(struct _FLT_INSTANCE **)(a2 + 120);
  FileHandle = 0;
  FileObject = 0;
  v16[0] = 0;
  v15 = 0;
  ObjectAttributes.RootDirectory = 0;
  v11 = *(struct _FLT_FILTER **)(a2 + 104);
  ObjectAttributes.ObjectName = a4;
  FileInformation = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = FltCreateFileEx(
          v11,
          v9,
          &FileHandle,
          &FileObject,
          0x120089u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          7u,
          1u,
          0x40u,
          0,
          0,
          0);
  if ( v12 >= 0 )
  {
    v12 = FltQueryInformationFile(
            *(PFLT_INSTANCE *)(a2 + 120),
            FileObject,
            &FileInformation,
            0x18u,
            FileStandardInformation,
            0);
    if ( v12 >= 0 )
    {
      ObfDereferenceObject(FileObject);
      FileObject = 0;
      FltClose(FileHandle);
      FileHandle = 0;
      if ( FileInformation < 0 )
      {
        *a7 = -1;
        v12 = -1073741675;
      }
      else
      {
        *a7 = *((_QWORD *)&FileInformation + 1);
        v13 = WimpFSFIntegrityOpenIntegrityFile(a1, a3, &FileHandle, &FileObject);
        v12 = v13;
        if ( v13 >= 0 )
        {
          v12 = RtlRunOnceExecuteOnce(&g_WimIntegrityRunOnce, WimpFSFInitializeIntegrity, 0, 0);
          if ( v12 >= 0 )
          {
            v12 = WimpFSFIntegrityValidateIntegrityFile(a1, FileObject, a5, *a7, &v15, v16, 0, a6);
            if ( v12 >= 0 && !v15 )
              v12 = -1073741116;
          }
        }
        else if ( v13 == -1073741809 )
        {
          *a6 = 0;
          v12 = 0;
        }
      }
    }
  }
  if ( FileObject )
  {
    ObfDereferenceObject(FileObject);
    FileObject = 0;
  }
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028924  push    rbp
0x140028926  push    rbx
0x140028927  push    rsi
0x140028928  push    rdi
0x140028929  push    r12
0x14002892b  push    r13
0x14002892d  push    r14
0x14002892f  push    r15
0x140028931  lea     rbp, [rsp-8]
0x140028936  sub     rsp, 108h
0x14002893d  mov     rax, cs:__security_cookie
0x140028944  xor     rax, rsp
0x140028947  mov     [rbp+40h+var_50], rax
0x14002894b  mov     r12, [rbp+40h+arg_20]
0x14002894f  xor     eax, eax
0x140028951  mov     r14, [rbp+40h+arg_28]
0x140028955  xorps   xmm0, xmm0
0x140028958  mov     rsi, [rbp+40h+arg_30]
0x14002895f  mov     r15, rcx
0x140028962  xor     ecx, ecx
0x140028964  mov     [rbp+40h+var_58], rax
0x140028968  mov     [rsp+140h+Flags], ecx; Flags
0x14002896c  lea     rax, [rbp+40h+var_78]
0x140028970  mov     [rsp+140h+EaLength], ecx; EaLength
0x140028974  mov     r13, rdx
0x140028977  mov     rdx, [rdx+78h]; Instance
0x14002897b  mov     rbx, r8
0x14002897e  mov     [rsp+140h+EaBuffer], rcx; EaBuffer
0x140028983  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x140028987  mov     [rsp+140h+CreateOptions], 40h ; '@'; CreateOptions
0x14002898f  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x140028997  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x14002899f  mov     [rsp+140h+FileAttributes], ecx; FileAttributes
0x1400289a3  mov     [rsp+140h+AllocationSize], rcx; AllocationSize
0x1400289a8  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x1400289ad  lea     rax, [rbp+40h+var_A8]
0x1400289b1  mov     [rbp+40h+FileHandle], rcx
0x1400289b5  mov     [rbp+40h+FileObject], rcx
0x1400289b9  mov     [rbp+40h+var_BF], cl
0x1400289bc  mov     [rbp+40h+var_C0], cl
0x1400289bf  mov     [rbp+40h+var_A8.RootDirectory], rcx
0x1400289c3  mov     rcx, [r13+68h]; Filter
0x1400289c7  mov     [rbp+40h+var_A8.ObjectName], r9
0x1400289cb  lea     r9, [rbp+40h+FileObject]; FileObject
0x1400289cf  mov     [rsp+140h+ObjectAttributes], rax; ObjectAttributes
0x1400289d4  mov     [rsp+140h+DesiredAccess], 120089h; DesiredAccess
0x1400289dc  movups  [rbp+40h+FileInformation], xmm0
0x1400289e0  mov     qword ptr [rbp+40h+var_A8.Length], 30h ; '0'
0x1400289e8  movups  xmmword ptr [rbp+40h+var_78], xmm0
0x1400289ec  mov     qword ptr [rbp+40h+var_A8.Attributes], 240h
0x1400289f4  movdqu  xmmword ptr [rbp+40h+var_A8.SecurityDescriptor], xmm0
0x1400289f9  call    cs:__imp_FltCreateFileEx
0x140028a00  nop     dword ptr [rax+rax+00h]
0x140028a05  mov     edi, eax
0x140028a07  test    eax, eax
0x140028a09  js      loc_140028B24
0x140028a0f  mov     rdx, [rbp+40h+FileObject]; FileObject
0x140028a13  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140028a17  mov     rcx, [r13+78h]; Instance
0x140028a1b  mov     r9d, 18h; Length
0x140028a21  mov     [rsp+140h+ObjectAttributes], 0; LengthReturned
0x140028a2a  mov     [rsp+140h+DesiredAccess], 5; FileInformationClass
0x140028a32  call    cs:__imp_FltQueryInformationFile
0x140028a39  nop     dword ptr [rax+rax+00h]
0x140028a3e  xor     r13d, r13d
0x140028a41  mov     edi, eax
0x140028a43  test    eax, eax
0x140028a45  js      loc_140028B27
0x140028a4b  mov     rcx, [rbp+40h+FileObject]; Object
0x140028a4f  call    cs:__imp_ObfDereferenceObject
0x140028a56  nop     dword ptr [rax+rax+00h]
0x140028a5b  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140028a5f  mov     [rbp+40h+FileObject], r13
0x140028a63  call    cs:__imp_FltClose
0x140028a6a  nop     dword ptr [rax+rax+00h]
0x140028a6f  mov     rax, qword ptr [rbp+40h+FileInformation+8]
0x140028a73  mov     [rbp+40h+FileHandle], r13
0x140028a77  test    rax, rax
0x140028a7a  js      loc_140028B16
0x140028a80  lea     r9, [rbp+40h+FileObject]
0x140028a84  mov     [rsi], rax
0x140028a87  lea     r8, [rbp+40h+FileHandle]
0x140028a8b  mov     rdx, rbx
0x140028a8e  mov     rcx, r15
0x140028a91  call    WimpFSFIntegrityOpenIntegrityFile
0x140028a96  mov     edi, eax
0x140028a98  test    eax, eax
0x140028a9a  jns     short loc_140028AAF
0x140028a9c  cmp     eax, 0C000000Fh
0x140028aa1  jnz     loc_140028B27
0x140028aa7  mov     [r14], r13
0x140028aaa  mov     edi, r13d
0x140028aad  jmp     short loc_140028B27
0x140028aaf  xor     r9d, r9d; Context
0x140028ab2  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x140028ab9  xor     r8d, r8d; Parameter
0x140028abc  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x140028ac3  call    cs:__imp_RtlRunOnceExecuteOnce
0x140028aca  nop     dword ptr [rax+rax+00h]
0x140028acf  mov     edi, eax
0x140028ad1  test    eax, eax
0x140028ad3  js      short loc_140028B27
0x140028ad5  mov     r9, [rsi]
0x140028ad8  lea     rax, [rbp+40h+var_BF]
0x140028adc  mov     rdx, [rbp+40h+FileObject]
0x140028ae0  mov     r8, r12
0x140028ae3  mov     [rsp+140h+AllocationSize], r14
0x140028ae8  mov     rcx, r15
0x140028aeb  mov     [rsp+140h+IoStatusBlock], r13
0x140028af0  mov     [rsp+140h+ObjectAttributes], rax
0x140028af5  lea     rax, [rbp+40h+var_C0]
0x140028af9  mov     qword ptr [rsp+140h+DesiredAccess], rax
0x140028afe  call    WimpFSFIntegrityValidateIntegrityFile
0x140028b03  mov     edi, eax
0x140028b05  test    eax, eax
0x140028b07  js      short loc_140028B27
0x140028b09  cmp     [rbp+40h+var_C0], r13b
0x140028b0d  jnz     short loc_140028B27
0x140028b0f  mov     edi, 0C00002C4h
0x140028b14  jmp     short loc_140028B27
0x140028b16  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140028b1d  mov     edi, 0C0000095h
0x140028b22  jmp     short loc_140028B27
0x140028b24  xor     r13d, r13d
0x140028b27  mov     rcx, [rbp+40h+FileObject]; Object
0x140028b2b  test    rcx, rcx
0x140028b2e  jz      short loc_140028B40
0x140028b30  call    cs:__imp_ObfDereferenceObject
0x140028b37  nop     dword ptr [rax+rax+00h]
0x140028b3c  mov     [rbp+40h+FileObject], r13
0x140028b40  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140028b44  test    rcx, rcx
0x140028b47  jz      short loc_140028B55
0x140028b49  call    cs:__imp_FltClose
0x140028b50  nop     dword ptr [rax+rax+00h]
0x140028b55  mov     eax, edi
0x140028b57  mov     rcx, [rbp+40h+var_50]
0x140028b5b  xor     rcx, rsp; StackCookie
0x140028b5e  call    __security_check_cookie
0x140028b63  add     rsp, 108h
0x140028b6a  pop     r15
0x140028b6c  pop     r14
0x140028b6e  pop     r13
0x140028b70  pop     r12
0x140028b72  pop     rdi
0x140028b73  pop     rsi
0x140028b74  pop     rbx
0x140028b75  pop     rbp
0x140028b76  retn
```
