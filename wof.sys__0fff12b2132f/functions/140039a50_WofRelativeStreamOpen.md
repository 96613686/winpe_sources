# WofRelativeStreamOpen

- ea: `0x140039a50`
- end: `0x140039ebd`
- name: `WofRelativeStreamOpen`
- size: `1133`
- prototype: `NTSTATUS __fastcall(__int64, struct _FILE_OBJECT *, __int64, char, __int64, PFILE_OBJECT *, HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140008d30`
- `0x14000ac54`

## callees

- `0x140009770`
- `0x140011560`
- `0x1400116c0`
- `0x140039a50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140039c33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039c33`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039b49`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039b49`
- `ntoskrnl!ObfDereferenceObject` at `0x140039d09`
- `ntoskrnl!ObfDereferenceObject` at `0x140039eac`
- `ntoskrnl!ObfDereferenceObject` at `0x140039d09`
- `ntoskrnl!ObfDereferenceObject` at `0x140039eac`
- `FLTMGR!FltQueryInformationFile` at `0x140039aed`
- `FLTMGR!FltQueryInformationFile` at `0x140039dab`
- `FLTMGR!FltQueryInformationFile` at `0x140039aed`
- `FLTMGR!FltQueryInformationFile` at `0x140039dab`
- `FLTMGR!FltCreateFileEx2` at `0x140039c1f`
- `FLTMGR!FltCreateFileEx2` at `0x140039ce0`
- `FLTMGR!FltCreateFileEx2` at `0x140039e56`
- `FLTMGR!FltCreateFileEx2` at `0x140039c1f`
- `FLTMGR!FltCreateFileEx2` at `0x140039ce0`
- `FLTMGR!FltCreateFileEx2` at `0x140039e56`
- `FLTMGR!FltSetInformationFile` at `0x140039dea`
- `FLTMGR!FltSetInformationFile` at `0x140039e82`
- `FLTMGR!FltSetInformationFile` at `0x140039dea`
- `FLTMGR!FltSetInformationFile` at `0x140039e82`
- `FLTMGR!FltClose` at `0x140039cf9`
- `FLTMGR!FltClose` at `0x140039e97`
- `FLTMGR!FltClose` at `0x140039cf9`
- `FLTMGR!FltClose` at `0x140039e97`

## pseudocode

```c
NTSTATUS __fastcall WofRelativeStreamOpen(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        PFILE_OBJECT *a6,
        HANDLE *a7)
{
  struct _FLT_INSTANCE *v9; // rcx
  NTSTATUS result; // eax
  PVOID PoolWithTag; // rax
  struct _FLT_INSTANCE *v13; // rdx
  struct _FLT_FILTER *v14; // rcx
  NTSTATUS v15; // edi
  struct _FLT_INSTANCE *v16; // rdx
  struct _FLT_FILTER *v17; // rcx
  ULONG CreateDisposition; // esi
  struct _FLT_INSTANCE *v19; // rcx
  struct _FLT_INSTANCE *v20; // rcx
  NTSTATUS v21; // eax
  struct _FLT_INSTANCE *v22; // rcx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v24; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT v25; // [rsp+90h] [rbp-70h] BYREF
  PVOID P[2]; // [rsp+98h] [rbp-68h] BYREF
  ULONG LengthReturned; // [rsp+A8h] [rbp-58h] BYREF
  ULONG v28; // [rsp+ACh] [rbp-54h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+110h] [rbp+10h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v35[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v36; // [rsp+148h] [rbp+48h]

  LOWORD(v33) = 0;
  FileHandle = 0;
  v9 = *(struct _FLT_INSTANCE **)(a1 + 120);
  *(_OWORD *)P = 0;
  FileObject = 0;
  memset(&ObjectAttributes, 0, 44);
  v24 = 0;
  v25 = 0;
  IoStatusBlock = 0;
  LengthReturned = 0;
  FileInformation = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  result = FltQueryInformationFile(v9, a2, &FileInformation, 8u, FileInternalInformation, &LengthReturned);
  if ( result >= 0 )
  {
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    v33 = 1;
    WofPropagateSiloContext(a2, &DriverContext);
    WORD1(P[0]) = *(_WORD *)(a1 + 64) + 10;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, WORD1(P[0]), 0x47666F57u);
    P[1] = PoolWithTag;
    if ( PoolWithTag )
    {
      memmove(PoolWithTag, *(const void **)(a1 + 72), *(unsigned __int16 *)(a1 + 64));
      *((_WORD *)P[1] + ((unsigned __int64)*(unsigned __int16 *)(a1 + 64) >> 1)) = 92;
      *(_QWORD *)((char *)P[1] + *(unsigned __int16 *)(a1 + 64) + 2) = FileInformation;
      v13 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v14 = *(struct _FLT_FILTER **)(a1 + 104);
      LOWORD(P[0]) = WORD1(P[0]);
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = FltCreateFileEx2(
              v14,
              v13,
              &FileHandle,
              &FileObject,
              0x100080u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x202020u,
              0,
              0,
              0,
              &DriverContext);
      ExFreePoolWithTag(P[1], 0);
      if ( v15 < 0 )
        return v15;
      v16 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v17 = *(struct _FLT_FILTER **)(a1 + 104);
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &CompressedStream;
      CreateDisposition = 5;
      ObjectAttributes.Attributes = 512;
      if ( !a4 )
        CreateDisposition = 1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = FltCreateFileEx2(
              v17,
              v16,
              &v24,
              &v25,
              0x100081u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              CreateDisposition,
              0x208020u,
              0,
              0,
              0,
              &DriverContext);
      if ( v15 == -1073741790 )
      {
        if ( a4 )
        {
          v19 = *(struct _FLT_INSTANCE **)(a1 + 120);
          v36 = 0;
          v28 = 0;
          memset(v35, 0, sizeof(v35));
          if ( FltQueryInformationFile(v19, FileObject, v35, 0x28u, FileBasicInformation, &v28) >= 0 && (v36 & 1) != 0 )
          {
            v20 = *(struct _FLT_INSTANCE **)(a1 + 120);
            LODWORD(v36) = v36 & 0xFFFFFFFE;
            FltSetInformationFile(v20, FileObject, v35, 0x28u, FileBasicInformation);
            v21 = FltCreateFileEx2(
                    *(PFLT_FILTER *)(a1 + 104),
                    *(PFLT_INSTANCE *)(a1 + 120),
                    &v24,
                    &v25,
                    0x100081u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    7u,
                    CreateDisposition,
                    0x208020u,
                    0,
                    0,
                    0,
                    &DriverContext);
            v22 = *(struct _FLT_INSTANCE **)(a1 + 120);
            LODWORD(v36) = v36 | 1;
            v15 = v21;
            FltSetInformationFile(v22, FileObject, v35, 0x28u, FileBasicInformation);
          }
        }
      }
      FltClose(FileHandle);
      ObfDereferenceObject(FileObject);
      if ( v15 >= 0 )
      {
        if ( a7 )
          *a7 = v24;
        else
          FltClose(v24);
        if ( a6 )
          *a6 = v25;
        else
          ObfDereferenceObject(v25);
        return 0;
      }
      else
      {
        return v15;
      }
    }
    else
    {
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039a50  push    rbp
0x140039a52  push    rbx
0x140039a53  push    rdi
0x140039a54  push    r12
0x140039a56  push    r13
0x140039a58  push    r14
0x140039a5a  push    r15
0x140039a5c  lea     rbp, [rsp-60h]
0x140039a61  sub     rsp, 160h
0x140039a68  mov     rax, cs:__security_cookie
0x140039a6f  xor     rax, rsp
0x140039a72  mov     [rbp+90h+var_40], rax
0x140039a76  mov     r14, [rbp+90h+arg_28]
0x140039a7d  lea     r8, [rbp+90h+FileInformation]; FileInformation
0x140039a81  mov     r15, [rbp+90h+arg_30]
0x140039a88  xorps   xmm0, xmm0
0x140039a8b  xor     r13d, r13d
0x140039a8e  xor     eax, eax
0x140039a90  mov     word ptr [rbp+90h+var_80], ax
0x140039a94  movzx   r12d, r9b
0x140039a98  lea     rax, [rbp+90h+var_E8]
0x140039a9c  mov     [rbp+90h+FileHandle], r13
0x140039aa0  mov     rbx, rcx
0x140039aa3  mov     [rsp+190h+LengthReturned], rax; LengthReturned
0x140039aa8  mov     rcx, [rcx+78h]; Instance
0x140039aac  mov     r9d, 8; Length
0x140039ab2  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x140039ab6  mov     [rsp+190h+FileInformationClass], 6; FileInformationClass
0x140039abe  mov     rdi, rdx
0x140039ac1  movups  xmmword ptr [rbp+90h+P], xmm0
0x140039ac5  mov     [rbp+90h+FileObject], r13
0x140039ac9  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x140039acd  mov     [rbp+90h+var_108], r13
0x140039ad1  movups  xmmword ptr [rbp+90h+ObjectAttributes+1Ch], xmm0
0x140039ad5  mov     [rbp+90h+var_100], r13
0x140039ad9  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x140039add  mov     [rbp+90h+var_E8], r13d
0x140039ae1  mov     [rbp+90h+FileInformation], r13
0x140039ae5  movups  xmmword ptr [rbp+90h+var_A0.Size], xmm0
0x140039ae9  movups  xmmword ptr [rbp+90h+var_A0.DeviceObjectHint], xmm0
0x140039aed  call    cs:__imp_FltQueryInformationFile
0x140039af4  nop     dword ptr [rax+rax+00h]
0x140039af9  test    eax, eax
0x140039afb  js      loc_140039D23
0x140039b01  xorps   xmm0, xmm0
0x140039b04  mov     [rsp+190h+arg_10], rsi
0x140039b0c  mov     eax, 28h ; '('
0x140039b11  lea     rdx, [rbp+90h+var_A0]
0x140039b15  movups  xmmword ptr [rbp+90h+var_A0.Size], xmm0
0x140039b19  mov     esi, 1
0x140039b1e  mov     [rbp+90h+var_A0.Size], ax
0x140039b22  mov     rcx, rdi
0x140039b25  mov     [rbp+90h+var_80], rsi
0x140039b29  movups  xmmword ptr [rbp+90h+var_A0.DeviceObjectHint], xmm0
0x140039b2d  call    WofPropagateSiloContext
0x140039b32  movzx   eax, word ptr [rbx+40h]
0x140039b36  mov     r8d, 47666F57h; Tag
0x140039b3c  add     ax, 0Ah
0x140039b40  mov     ecx, esi; PoolType
0x140039b42  movzx   edx, ax; NumberOfBytes
0x140039b45  mov     word ptr [rbp+90h+P+2], dx
0x140039b49  call    cs:__imp_ExAllocatePoolWithTag
0x140039b50  nop     dword ptr [rax+rax+00h]
0x140039b55  mov     [rbp+90h+P+8], rax
0x140039b59  test    rax, rax
0x140039b5c  jz      loc_140039D67
0x140039b62  movzx   r8d, word ptr [rbx+40h]; Size
0x140039b67  mov     rcx, rax; void *
0x140039b6a  mov     rdx, [rbx+48h]; Src
0x140039b6e  call    memmove
0x140039b73  movzx   ecx, word ptr [rbx+40h]
0x140039b77  lea     r9, [rbp+90h+FileObject]; FileObject
0x140039b7b  mov     rax, [rbp+90h+P+8]
0x140039b7f  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x140039b83  shr     rcx, 1
0x140039b86  xorps   xmm0, xmm0
0x140039b89  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x140039b8f  mov     rax, [rbp+90h+P+8]
0x140039b93  movzx   edx, word ptr [rbx+40h]
0x140039b97  mov     rcx, [rbp+90h+FileInformation]
0x140039b9b  mov     [rdx+rax+2], rcx
0x140039ba0  movzx   eax, word ptr [rbp+90h+P+2]
0x140039ba4  mov     rdx, [rbx+78h]; Instance
0x140039ba8  mov     rcx, [rbx+68h]; Filter
0x140039bac  mov     word ptr [rbp+90h+P], ax
0x140039bb0  lea     rax, [rbp+90h+P]
0x140039bb4  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140039bb8  lea     rax, [rbp+90h+var_A0]
0x140039bbc  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039bc1  lea     rax, [rbp+90h+var_78]
0x140039bc5  mov     [rsp+190h+Flags], r13d; Flags
0x140039bca  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039bcf  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039bd4  mov     [rsp+190h+CreateOptions], 202020h; CreateOptions
0x140039bdc  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039be0  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039be8  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039bed  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039bf2  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039bf7  lea     rax, [rbp+90h+ObjectAttributes]
0x140039bfb  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039c00  mov     [rsp+190h+FileInformationClass], 100080h; DesiredAccess
0x140039c08  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140039c0f  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x140039c13  mov     [rbp+90h+ObjectAttributes.Attributes], 200h
0x140039c1a  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039c1f  call    cs:__imp_FltCreateFileEx2
0x140039c26  nop     dword ptr [rax+rax+00h]
0x140039c2b  mov     rcx, [rbp+90h+P+8]; P
0x140039c2f  xor     edx, edx; Tag
0x140039c31  mov     edi, eax
0x140039c33  call    cs:__imp_ExFreePoolWithTag
0x140039c3a  nop     dword ptr [rax+rax+00h]
0x140039c3f  test    edi, edi
0x140039c41  js      loc_140039D19
0x140039c47  mov     rax, [rbp+90h+FileHandle]
0x140039c4b  lea     r9, [rbp+90h+var_100]; FileObject
0x140039c4f  mov     rdx, [rbx+78h]; Instance
0x140039c53  lea     r8, [rbp+90h+var_108]; FileHandle
0x140039c57  mov     rcx, [rbx+68h]; Filter
0x140039c5b  xorps   xmm0, xmm0
0x140039c5e  mov     [rbp+90h+ObjectAttributes.RootDirectory], rax
0x140039c62  test    r12b, r12b
0x140039c65  lea     rax, CompressedStream
0x140039c6c  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140039c73  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140039c77  mov     esi, 5
0x140039c7c  mov     eax, 1
0x140039c81  mov     [rbp+90h+ObjectAttributes.Attributes], 200h
0x140039c88  cmovz   esi, eax
0x140039c8b  lea     rax, [rbp+90h+var_A0]
0x140039c8f  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039c94  lea     rax, [rbp+90h+var_78]
0x140039c98  mov     [rsp+190h+Flags], r13d; Flags
0x140039c9d  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039ca2  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039ca7  mov     [rsp+190h+CreateOptions], 208020h; CreateOptions
0x140039caf  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039cb3  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039cbb  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039cc0  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039cc5  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039cca  lea     rax, [rbp+90h+ObjectAttributes]
0x140039cce  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039cd3  mov     [rsp+190h+FileInformationClass], 100081h; DesiredAccess
0x140039cdb  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039ce0  call    cs:__imp_FltCreateFileEx2
0x140039ce7  nop     dword ptr [rax+rax+00h]
0x140039cec  mov     edi, eax
0x140039cee  cmp     eax, 0C0000022h
0x140039cf3  jz      short loc_140039D6E
0x140039cf5  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x140039cf9  call    cs:__imp_FltClose
0x140039d00  nop     dword ptr [rax+rax+00h]
0x140039d05  mov     rcx, [rbp+90h+FileObject]; Object
0x140039d09  call    cs:__imp_ObfDereferenceObject
0x140039d10  nop     dword ptr [rax+rax+00h]
0x140039d15  test    edi, edi
0x140039d17  jns     short loc_140039D43
0x140039d19  mov     eax, edi
0x140039d1b  mov     rsi, [rsp+190h+arg_10]
0x140039d23  mov     rcx, [rbp+90h+var_40]
0x140039d27  xor     rcx, rsp; StackCookie
0x140039d2a  call    __security_check_cookie
0x140039d2f  add     rsp, 160h
0x140039d36  pop     r15
0x140039d38  pop     r14
0x140039d3a  pop     r13
0x140039d3c  pop     r12
0x140039d3e  pop     rdi
0x140039d3f  pop     rbx
0x140039d40  pop     rbp
0x140039d41  retn
0x140039d43  test    r15, r15
0x140039d46  jz      loc_140039E93
0x140039d4c  mov     rax, [rbp+90h+var_108]
0x140039d50  mov     [r15], rax
0x140039d53  test    r14, r14
0x140039d56  jz      loc_140039EA8
0x140039d5c  mov     rax, [rbp+90h+var_100]
0x140039d60  mov     [r14], rax
0x140039d63  xor     eax, eax
0x140039d65  jmp     short loc_140039D1B
0x140039d67  mov     eax, 0C000009Ah
0x140039d6c  jmp     short loc_140039D1B
0x140039d6e  test    r12b, r12b
0x140039d71  jz      short loc_140039CF5
0x140039d73  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039d77  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039d7b  mov     rcx, [rbx+78h]; Instance
0x140039d7f  xor     eax, eax
0x140039d81  xorps   xmm0, xmm0
0x140039d84  mov     [rbp+90h+var_48], rax
0x140039d88  lea     rax, [rbp+90h+var_E4]
0x140039d8c  mov     [rbp+90h+var_E4], r13d
0x140039d90  mov     [rsp+190h+LengthReturned], rax; LengthReturned
0x140039d95  mov     r9d, 28h ; '('; Length
0x140039d9b  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039da3  movups  [rbp+90h+var_68], xmm0
0x140039da7  movups  [rbp+90h+var_58], xmm0
0x140039dab  call    cs:__imp_FltQueryInformationFile
0x140039db2  nop     dword ptr [rax+rax+00h]
0x140039db7  test    eax, eax
0x140039db9  js      loc_140039CF5
0x140039dbf  mov     eax, dword ptr [rbp+90h+var_48]
0x140039dc2  test    al, 1
0x140039dc4  jz      loc_140039CF5
0x140039dca  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039dce  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039dd2  mov     rcx, [rbx+78h]; Instance
0x140039dd6  and     eax, 0FFFFFFFEh
0x140039dd9  mov     r9d, 28h ; '('; Length
0x140039ddf  mov     dword ptr [rbp+90h+var_48], eax
0x140039de2  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039dea  call    cs:__imp_FltSetInformationFile
0x140039df1  nop     dword ptr [rax+rax+00h]
0x140039df6  mov     rdx, [rbx+78h]; Instance
0x140039dfa  lea     rax, [rbp+90h+var_A0]
0x140039dfe  mov     rcx, [rbx+68h]; Filter
0x140039e02  lea     r9, [rbp+90h+var_100]; FileObject
0x140039e06  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039e0b  lea     r8, [rbp+90h+var_108]; FileHandle
0x140039e0f  mov     [rsp+190h+Flags], r13d; Flags
0x140039e14  lea     rax, [rbp+90h+var_78]
0x140039e18  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039e1d  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039e22  mov     [rsp+190h+CreateOptions], 208020h; CreateOptions
0x140039e2a  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039e2e  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039e36  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039e3b  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039e40  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039e45  lea     rax, [rbp+90h+ObjectAttributes]
0x140039e49  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039e4e  mov     [rsp+190h+FileInformationClass], 100081h; DesiredAccess
0x140039e56  call    cs:__imp_FltCreateFileEx2
0x140039e5d  nop     dword ptr [rax+rax+00h]
0x140039e62  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039e66  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039e6a  mov     rcx, [rbx+78h]; Instance
0x140039e6e  mov     r9d, 28h ; '('; Length
0x140039e74  or      dword ptr [rbp+90h+var_48], 1
0x140039e78  mov     edi, eax
0x140039e7a  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039e82  call    cs:__imp_FltSetInformationFile
0x140039e89  nop     dword ptr [rax+rax+00h]
0x140039e8e  jmp     loc_140039CF5
0x140039e93  mov     rcx, [rbp+90h+var_108]; FileHandle
0x140039e97  call    cs:__imp_FltClose
0x140039e9e  nop     dword ptr [rax+rax+00h]
0x140039ea3  jmp     loc_140039D53
0x140039ea8  mov     rcx, [rbp+90h+var_100]; Object
0x140039eac  call    cs:__imp_ObfDereferenceObject
0x140039eb3  nop     dword ptr [rax+rax+00h]
0x140039eb8  jmp     loc_140039D63
```
