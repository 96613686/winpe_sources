# WimFSFQueryIntegrityStatusOfWim

- ea: `0x1400288d4`
- end: `0x140028b28`
- name: `WimFSFQueryIntegrityStatusOfWim`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140026f60`

## callees

- `0x140011560`
- `0x1400288d4`
- `0x140029a90`
- `0x14002a040`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028a73`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140028a73`
- `ntoskrnl!ObfDereferenceObject` at `0x1400289ff`
- `ntoskrnl!ObfDereferenceObject` at `0x140028ae0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400289ff`
- `ntoskrnl!ObfDereferenceObject` at `0x140028ae0`
- `FLTMGR!FltCreateFileEx` at `0x1400289a9`
- `FLTMGR!FltCreateFileEx` at `0x1400289a9`
- `FLTMGR!FltQueryInformationFile` at `0x1400289e2`
- `FLTMGR!FltQueryInformationFile` at `0x1400289e2`
- `FLTMGR!FltClose` at `0x140028a13`
- `FLTMGR!FltClose` at `0x140028af9`
- `FLTMGR!FltClose` at `0x140028a13`
- `FLTMGR!FltClose` at `0x140028af9`

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
0x1400288d4  push    rbp
0x1400288d6  push    rbx
0x1400288d7  push    rsi
0x1400288d8  push    rdi
0x1400288d9  push    r12
0x1400288db  push    r13
0x1400288dd  push    r14
0x1400288df  push    r15
0x1400288e1  lea     rbp, [rsp-8]
0x1400288e6  sub     rsp, 108h
0x1400288ed  mov     rax, cs:__security_cookie
0x1400288f4  xor     rax, rsp
0x1400288f7  mov     [rbp+40h+var_50], rax
0x1400288fb  mov     r12, [rbp+40h+arg_20]
0x1400288ff  xor     eax, eax
0x140028901  mov     r14, [rbp+40h+arg_28]
0x140028905  xorps   xmm0, xmm0
0x140028908  mov     rsi, [rbp+40h+arg_30]
0x14002890f  mov     r15, rcx
0x140028912  xor     ecx, ecx
0x140028914  mov     [rbp+40h+var_58], rax
0x140028918  mov     [rsp+140h+Flags], ecx; Flags
0x14002891c  lea     rax, [rbp+40h+var_78]
0x140028920  mov     [rsp+140h+EaLength], ecx; EaLength
0x140028924  mov     r13, rdx
0x140028927  mov     rdx, [rdx+78h]; Instance
0x14002892b  mov     rbx, r8
0x14002892e  mov     [rsp+140h+EaBuffer], rcx; EaBuffer
0x140028933  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x140028937  mov     [rsp+140h+CreateOptions], 40h ; '@'; CreateOptions
0x14002893f  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x140028947  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x14002894f  mov     [rsp+140h+FileAttributes], ecx; FileAttributes
0x140028953  mov     [rsp+140h+AllocationSize], rcx; AllocationSize
0x140028958  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14002895d  lea     rax, [rbp+40h+var_A8]
0x140028961  mov     [rbp+40h+FileHandle], rcx
0x140028965  mov     [rbp+40h+FileObject], rcx
0x140028969  mov     [rbp+40h+var_BF], cl
0x14002896c  mov     [rbp+40h+var_C0], cl
0x14002896f  mov     [rbp+40h+var_A8.RootDirectory], rcx
0x140028973  mov     rcx, [r13+68h]; Filter
0x140028977  mov     [rbp+40h+var_A8.ObjectName], r9
0x14002897b  lea     r9, [rbp+40h+FileObject]; FileObject
0x14002897f  mov     [rsp+140h+ObjectAttributes], rax; ObjectAttributes
0x140028984  mov     [rsp+140h+DesiredAccess], 120089h; DesiredAccess
0x14002898c  movups  [rbp+40h+FileInformation], xmm0
0x140028990  mov     qword ptr [rbp+40h+var_A8.Length], 30h ; '0'
0x140028998  movups  xmmword ptr [rbp+40h+var_78], xmm0
0x14002899c  mov     qword ptr [rbp+40h+var_A8.Attributes], 240h
0x1400289a4  movdqu  xmmword ptr [rbp+40h+var_A8.SecurityDescriptor], xmm0
0x1400289a9  call    cs:__imp_FltCreateFileEx
0x1400289b0  nop     dword ptr [rax+rax+00h]
0x1400289b5  mov     edi, eax
0x1400289b7  test    eax, eax
0x1400289b9  js      loc_140028AD4
0x1400289bf  mov     rdx, [rbp+40h+FileObject]; FileObject
0x1400289c3  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x1400289c7  mov     rcx, [r13+78h]; Instance
0x1400289cb  mov     r9d, 18h; Length
0x1400289d1  mov     [rsp+140h+ObjectAttributes], 0; LengthReturned
0x1400289da  mov     [rsp+140h+DesiredAccess], 5; FileInformationClass
0x1400289e2  call    cs:__imp_FltQueryInformationFile
0x1400289e9  nop     dword ptr [rax+rax+00h]
0x1400289ee  xor     r13d, r13d
0x1400289f1  mov     edi, eax
0x1400289f3  test    eax, eax
0x1400289f5  js      loc_140028AD7
0x1400289fb  mov     rcx, [rbp+40h+FileObject]; Object
0x1400289ff  call    cs:__imp_ObfDereferenceObject
0x140028a06  nop     dword ptr [rax+rax+00h]
0x140028a0b  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140028a0f  mov     [rbp+40h+FileObject], r13
0x140028a13  call    cs:__imp_FltClose
0x140028a1a  nop     dword ptr [rax+rax+00h]
0x140028a1f  mov     rax, qword ptr [rbp+40h+FileInformation+8]
0x140028a23  mov     [rbp+40h+FileHandle], r13
0x140028a27  test    rax, rax
0x140028a2a  js      loc_140028AC6
0x140028a30  lea     r9, [rbp+40h+FileObject]
0x140028a34  mov     [rsi], rax
0x140028a37  lea     r8, [rbp+40h+FileHandle]
0x140028a3b  mov     rdx, rbx
0x140028a3e  mov     rcx, r15
0x140028a41  call    WimpFSFIntegrityOpenIntegrityFile
0x140028a46  mov     edi, eax
0x140028a48  test    eax, eax
0x140028a4a  jns     short loc_140028A5F
0x140028a4c  cmp     eax, 0C000000Fh
0x140028a51  jnz     loc_140028AD7
0x140028a57  mov     [r14], r13
0x140028a5a  mov     edi, r13d
0x140028a5d  jmp     short loc_140028AD7
0x140028a5f  xor     r9d, r9d; Context
0x140028a62  lea     rdx, WimpFSFInitializeIntegrity; InitFn
0x140028a69  xor     r8d, r8d; Parameter
0x140028a6c  lea     rcx, g_WimIntegrityRunOnce; RunOnce
0x140028a73  call    cs:__imp_RtlRunOnceExecuteOnce
0x140028a7a  nop     dword ptr [rax+rax+00h]
0x140028a7f  mov     edi, eax
0x140028a81  test    eax, eax
0x140028a83  js      short loc_140028AD7
0x140028a85  mov     r9, [rsi]
0x140028a88  lea     rax, [rbp+40h+var_BF]
0x140028a8c  mov     rdx, [rbp+40h+FileObject]
0x140028a90  mov     r8, r12
0x140028a93  mov     [rsp+140h+AllocationSize], r14
0x140028a98  mov     rcx, r15
0x140028a9b  mov     [rsp+140h+IoStatusBlock], r13
0x140028aa0  mov     [rsp+140h+ObjectAttributes], rax
0x140028aa5  lea     rax, [rbp+40h+var_C0]
0x140028aa9  mov     qword ptr [rsp+140h+DesiredAccess], rax
0x140028aae  call    WimpFSFIntegrityValidateIntegrityFile
0x140028ab3  mov     edi, eax
0x140028ab5  test    eax, eax
0x140028ab7  js      short loc_140028AD7
0x140028ab9  cmp     [rbp+40h+var_C0], r13b
0x140028abd  jnz     short loc_140028AD7
0x140028abf  mov     edi, 0C00002C4h
0x140028ac4  jmp     short loc_140028AD7
0x140028ac6  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140028acd  mov     edi, 0C0000095h
0x140028ad2  jmp     short loc_140028AD7
0x140028ad4  xor     r13d, r13d
0x140028ad7  mov     rcx, [rbp+40h+FileObject]; Object
0x140028adb  test    rcx, rcx
0x140028ade  jz      short loc_140028AF0
0x140028ae0  call    cs:__imp_ObfDereferenceObject
0x140028ae7  nop     dword ptr [rax+rax+00h]
0x140028aec  mov     [rbp+40h+FileObject], r13
0x140028af0  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140028af4  test    rcx, rcx
0x140028af7  jz      short loc_140028B05
0x140028af9  call    cs:__imp_FltClose
0x140028b00  nop     dword ptr [rax+rax+00h]
0x140028b05  mov     eax, edi
0x140028b07  mov     rcx, [rbp+40h+var_50]
0x140028b0b  xor     rcx, rsp; StackCookie
0x140028b0e  call    __security_check_cookie
0x140028b13  add     rsp, 108h
0x140028b1a  pop     r15
0x140028b1c  pop     r14
0x140028b1e  pop     r13
0x140028b20  pop     r12
0x140028b22  pop     rdi
0x140028b23  pop     rsi
0x140028b24  pop     rbx
0x140028b25  pop     rbp
0x140028b26  retn
```
