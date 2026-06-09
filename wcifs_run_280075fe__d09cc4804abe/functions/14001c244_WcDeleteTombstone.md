# WcDeleteTombstone

- ea: `0x14001c244`
- end: `0x14001c5d1`
- name: `WcDeleteTombstone`
- size: `909`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001cff0`
- `0x14001f1c8`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bcec`
- `0x14001c244`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14001c2d6`
- `ntoskrnl!IoGetSilo` at `0x14001c2d6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c5a2`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c5a2`
- `FLTMGR!FltSetInformationFile` at `0x14001c523`
- `FLTMGR!FltSetInformationFile` at `0x14001c523`
- `FLTMGR!FltCreateFileEx2` at `0x14001c367`
- `FLTMGR!FltCreateFileEx2` at `0x14001c367`
- `FLTMGR!FltClose` at `0x14001c58d`
- `FLTMGR!FltClose` at `0x14001c58d`
- `FLTMGR!FltQueryInformationFile` at `0x14001c3d5`
- `FLTMGR!FltQueryInformationFile` at `0x14001c3d5`

## pseudocode

```c
__int64 __fastcall WcDeleteTombstone(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        void *a4,
        UNICODE_STRING *a5)
{
  int v9; // edx
  int v10; // ebx
  int v11; // r9d
  int v12; // edx
  __int64 v13; // rcx
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  char v17; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+81h] [rbp-7Fh] BYREF
  char v19; // [rsp+82h] [rbp-7Eh] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  ULONG LengthReturned; // [rsp+90h] [rbp-70h] BYREF
  int v22; // [rsp+94h] [rbp-6Ch] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 Silo; // [rsp+F0h] [rbp-10h]
  struct _IO_STATUS_BLOCK v27; // [rsp+F8h] [rbp-8h] BYREF
  __int128 FileInformation; // [rsp+108h] [rbp+8h] BYREF
  __int64 v29; // [rsp+118h] [rbp+18h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+120h] [rbp+20h] BYREF
  char *v31; // [rsp+140h] [rbp+40h]
  __int64 v32; // [rsp+148h] [rbp+48h]
  char *v33; // [rsp+150h] [rbp+50h]
  __int64 v34; // [rsp+158h] [rbp+58h]
  int *v35; // [rsp+160h] [rbp+60h]
  __int64 v36; // [rsp+168h] [rbp+68h]

  FileHandle = 0;
  FileObject = 0;
  v29 = 0;
  v17 = 0;
  LengthReturned = 0;
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  FileInformation = 0;
  memset(&ObjectAttributes, 0, 44);
  v27 = 0;
  if ( a3 )
    Silo = IoGetSilo(a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a4;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a5;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = FltCreateFileEx2(
          Globals,
          a2,
          &FileHandle,
          &FileObject,
          0x10080u,
          &ObjectAttributes,
          &v27,
          0,
          0,
          3u,
          1u,
          0x200028u,
          0,
          0,
          0,
          &DriverContext);
  if ( v10 == -1073741772 )
  {
    v10 = 0;
    goto LABEL_21;
  }
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    AllocationSize = v10;
    v11 = 10;
    IoStatusBlock = 117;
    goto LABEL_20;
  }
  v10 = FltQueryInformationFile(a2, FileObject, &FileInformation, 0x18u, FileStandardInformation, &LengthReturned);
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    AllocationSize = v10;
    v11 = 11;
    IoStatusBlock = -123;
    goto LABEL_20;
  }
  v10 = WcAddInMemoryTombstone(a1, a2, a5, SBYTE5(v29), a3);
  if ( v10 >= 0 )
  {
    v17 = 1;
    v10 = FltSetInformationFile(a2, FileObject, &v17, 1u, FileDispositionInformation);
    if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      AllocationSize = v10;
      v11 = 13;
      IoStatusBlock = -84;
LABEL_20:
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        19,
        v11,
        (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
        IoStatusBlock,
        AllocationSize);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        19,
        12,
        (__int64)WPP_6c993b8198b53d328fc429e03cc469de_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\tombstone.c",
        148,
        v10);
    }
    if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
    {
      v18 = 3;
      v31 = &v18;
      v32 = 1;
      v33 = &v19;
      v19 = 3;
      v35 = &v22;
      v34 = 1;
      v22 = v10;
      v36 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)byte_14000BB49, 0, 0, 5u, &v30);
    }
  }
LABEL_21:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001c244  push    rbp
0x14001c246  push    rbx
0x14001c247  push    rsi
0x14001c248  push    rdi
0x14001c249  push    r12
0x14001c24b  push    r13
0x14001c24d  push    r14
0x14001c24f  push    r15
0x14001c251  lea     rbp, [rsp-88h]
0x14001c259  sub     rsp, 188h
0x14001c260  mov     rax, cs:__security_cookie
0x14001c267  xor     rax, rsp
0x14001c26a  mov     [rbp+0C0h+var_50], rax
0x14001c26e  mov     r14, [rbp+0C0h+arg_20]
0x14001c275  xor     r12d, r12d
0x14001c278  xorps   xmm0, xmm0
0x14001c27b  mov     [rbp+0C0h+FileHandle], r12
0x14001c27f  xor     eax, eax
0x14001c281  mov     [rbp+0C0h+FileObject], r12
0x14001c285  mov     [rbp+0C0h+var_A8], rax
0x14001c289  xorps   xmm1, xmm1
0x14001c28c  mov     [rbp+0C0h+var_140], r12b
0x14001c290  lea     eax, [r12+28h]
0x14001c295  mov     [rbp+0C0h+LengthReturned], r12d
0x14001c299  lea     r13d, [r12+1]
0x14001c29e  mov     [rbp+0C0h+var_D0], r13
0x14001c2a2  mov     rbx, r9
0x14001c2a5  mov     rsi, r8
0x14001c2a8  mov     rdi, rdx
0x14001c2ab  mov     r15, rcx
0x14001c2ae  movups  xmmword ptr [rbp+0C0h+var_120.ObjectName], xmm0
0x14001c2b2  movups  xmmword ptr [rbp+0C0h+var_F0.Size], xmm1
0x14001c2b6  mov     [rbp+0C0h+var_F0.Size], ax
0x14001c2ba  movups  [rbp+0C0h+FileInformation], xmm0
0x14001c2be  movups  xmmword ptr [rbp+0C0h+var_120.Length], xmm0
0x14001c2c2  movups  xmmword ptr [rbp+0C0h+var_120+1Ch], xmm0
0x14001c2c6  movups  xmmword ptr [rbp+0C0h+var_C8], xmm0
0x14001c2ca  movups  xmmword ptr [rbp+0C0h+var_F0.DeviceObjectHint], xmm1
0x14001c2ce  test    r8, r8
0x14001c2d1  jz      short loc_14001C2E6
0x14001c2d3  mov     rcx, r8
0x14001c2d6  call    cs:__imp_IoGetSilo
0x14001c2dd  nop     dword ptr [rax+rax+00h]
0x14001c2e2  mov     [rbp+0C0h+var_D0], rax
0x14001c2e6  mov     rcx, cs:Globals; Filter
0x14001c2ed  lea     rax, [rbp+0C0h+var_F0]
0x14001c2f1  mov     [rsp+1C0h+DriverContext], rax; DriverContext
0x14001c2f6  lea     r9, [rbp+0C0h+FileObject]; FileObject
0x14001c2fa  mov     [rsp+1C0h+Flags], r12d; Flags
0x14001c2ff  lea     rax, [rbp+0C0h+var_C8]
0x14001c303  mov     [rsp+1C0h+EaLength], r12d; EaLength
0x14001c308  lea     r8, [rbp+0C0h+FileHandle]; FileHandle
0x14001c30c  mov     [rsp+1C0h+EaBuffer], r12; EaBuffer
0x14001c311  xorps   xmm0, xmm0
0x14001c314  mov     [rsp+1C0h+CreateOptions], 200028h; CreateOptions
0x14001c31c  mov     rdx, rdi; Instance
0x14001c31f  mov     [rsp+1C0h+CreateDisposition], r13d; CreateDisposition
0x14001c324  mov     [rsp+1C0h+ShareAccess], 3; ShareAccess
0x14001c32c  mov     [rsp+1C0h+FileAttributes], r12d; FileAttributes
0x14001c331  mov     [rsp+1C0h+AllocationSize], r12; AllocationSize
0x14001c336  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x14001c33b  lea     rax, [rbp+0C0h+var_120]
0x14001c33f  mov     [rsp+1C0h+ObjectAttributes], rax; ObjectAttributes
0x14001c344  mov     [rsp+1C0h+DesiredAccess], 10080h; DesiredAccess
0x14001c34c  mov     [rbp+0C0h+var_120.Length], 30h ; '0'
0x14001c353  mov     [rbp+0C0h+var_120.RootDirectory], rbx
0x14001c357  mov     [rbp+0C0h+var_120.Attributes], 240h
0x14001c35e  mov     [rbp+0C0h+var_120.ObjectName], r14
0x14001c362  movdqu  xmmword ptr [rbp+0C0h+var_120.SecurityDescriptor], xmm0
0x14001c367  call    cs:__imp_FltCreateFileEx2
0x14001c36e  nop     dword ptr [rax+rax+00h]
0x14001c373  mov     ebx, eax
0x14001c375  cmp     eax, 0C0000034h
0x14001c37a  jnz     short loc_14001C384
0x14001c37c  mov     ebx, r12d
0x14001c37f  jmp     loc_14001C584
0x14001c384  test    ebx, ebx
0x14001c386  jns     short loc_14001C3B3
0x14001c388  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c38f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c396  jz      loc_14001C584
0x14001c39c  mov     dword ptr [rsp+1C0h+AllocationSize], ebx
0x14001c3a0  mov     r9d, 0Ah
0x14001c3a6  mov     dword ptr [rsp+1C0h+IoStatusBlock], 175h
0x14001c3ae  jmp     loc_14001C554
0x14001c3b3  mov     rdx, [rbp+0C0h+FileObject]; FileObject
0x14001c3b7  lea     rax, [rbp+0C0h+LengthReturned]
0x14001c3bb  mov     [rsp+1C0h+ObjectAttributes], rax; LengthReturned
0x14001c3c0  lea     r8, [rbp+0C0h+FileInformation]; FileInformation
0x14001c3c4  mov     r9d, 18h; Length
0x14001c3ca  mov     [rsp+1C0h+DesiredAccess], 5; FileInformationClass
0x14001c3d2  mov     rcx, rdi; Instance
0x14001c3d5  call    cs:__imp_FltQueryInformationFile
0x14001c3dc  nop     dword ptr [rax+rax+00h]
0x14001c3e1  mov     ebx, eax
0x14001c3e3  test    eax, eax
0x14001c3e5  jns     short loc_14001C412
0x14001c3e7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c3ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c3f5  jz      loc_14001C584
0x14001c3fb  mov     dword ptr [rsp+1C0h+AllocationSize], ebx
0x14001c3ff  mov     r9d, 0Bh
0x14001c405  mov     dword ptr [rsp+1C0h+IoStatusBlock], 185h
0x14001c40d  jmp     loc_14001C554
0x14001c412  mov     r9b, byte ptr [rbp+0C0h+var_A8+5]
0x14001c416  mov     r8, r14
0x14001c419  mov     rdx, rdi
0x14001c41c  mov     qword ptr [rsp+1C0h+DesiredAccess], rsi
0x14001c421  mov     rcx, r15
0x14001c424  call    WcAddInMemoryTombstone
0x14001c429  mov     ebx, eax
0x14001c42b  test    eax, eax
0x14001c42d  jns     loc_14001C508
0x14001c433  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c43a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c441  jz      short loc_14001C483
0x14001c443  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c44a  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x14001c451  mov     dword ptr [rsp+1C0h+AllocationSize], ebx
0x14001c455  mov     r9d, 0Ch
0x14001c45b  mov     dword ptr [rsp+1C0h+IoStatusBlock], 194h
0x14001c463  mov     dl, 2
0x14001c465  mov     [rsp+1C0h+ObjectAttributes], rax
0x14001c46a  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x14001c471  mov     rcx, [rcx+40h]
0x14001c475  lea     r8d, [r9+7]
0x14001c479  mov     qword ptr [rsp+1C0h+DesiredAccess], rax
0x14001c47e  call    WPP_RECORDER_SF_sDd
0x14001c483  mov     eax, cs:dword_14000E060
0x14001c489  cmp     eax, 5
0x14001c48c  jbe     loc_14001C584
0x14001c492  mov     rdx, 400000000000h
0x14001c49c  lea     rcx, dword_14000E060
0x14001c4a3  call    _tlgKeywordOn
0x14001c4a8  test    al, al
0x14001c4aa  jz      loc_14001C584
0x14001c4b0  lea     rax, [rbp+0C0h+var_13F]
0x14001c4b4  mov     [rbp+0C0h+var_13F], 3
0x14001c4b8  mov     [rbp+0C0h+var_80], rax
0x14001c4bc  lea     rdx, byte_14000BB49
0x14001c4c3  lea     rax, [rbp+0C0h+var_13E]
0x14001c4c7  mov     [rbp+0C0h+var_78], r13
0x14001c4cb  mov     [rbp+0C0h+var_70], rax
0x14001c4cf  xor     r9d, r9d
0x14001c4d2  lea     rax, [rbp+0C0h+var_12C]
0x14001c4d6  mov     [rbp+0C0h+var_13E], 3
0x14001c4da  mov     [rbp+0C0h+var_60], rax
0x14001c4de  xor     r8d, r8d
0x14001c4e1  lea     rax, [rbp+0C0h+var_A0]
0x14001c4e5  mov     [rbp+0C0h+var_68], r13
0x14001c4e9  mov     [rsp+1C0h+ObjectAttributes], rax
0x14001c4ee  mov     [rsp+1C0h+DesiredAccess], 5
0x14001c4f6  mov     [rbp+0C0h+var_12C], ebx
0x14001c4f9  mov     [rbp+0C0h+var_58], 4
0x14001c501  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001c506  jmp     short loc_14001C584
0x14001c508  mov     rdx, [rbp+0C0h+FileObject]; FileObject
0x14001c50c  lea     r8, [rbp+0C0h+var_140]; FileInformation
0x14001c510  mov     esi, 0Dh
0x14001c515  mov     [rbp+0C0h+var_140], r13b
0x14001c519  mov     r9d, r13d; Length
0x14001c51c  mov     [rsp+1C0h+DesiredAccess], esi; FileInformationClass
0x14001c520  mov     rcx, rdi; Instance
0x14001c523  call    cs:__imp_FltSetInformationFile
0x14001c52a  nop     dword ptr [rax+rax+00h]
0x14001c52f  mov     ebx, eax
0x14001c531  test    eax, eax
0x14001c533  jns     short loc_14001C584
0x14001c535  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c53c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c543  jz      short loc_14001C584
0x14001c545  mov     dword ptr [rsp+1C0h+AllocationSize], ebx
0x14001c549  mov     r9d, esi
0x14001c54c  mov     dword ptr [rsp+1C0h+IoStatusBlock], 1ACh
0x14001c554  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c55b  lea     rax, aOnecoreBaseFsW_10; "onecore\\base\\fs\\wci\\wcifs\\tombston"...
0x14001c562  mov     [rsp+1C0h+ObjectAttributes], rax
0x14001c567  mov     r8d, 13h
0x14001c56d  lea     rax, WPP_6c993b8198b53d328fc429e03cc469de_Traceguids
0x14001c574  mov     dl, 2
0x14001c576  mov     qword ptr [rsp+1C0h+DesiredAccess], rax
0x14001c57b  mov     rcx, [rcx+40h]
0x14001c57f  call    WPP_RECORDER_SF_sDd
0x14001c584  mov     rcx, [rbp+0C0h+FileHandle]; FileHandle
0x14001c588  test    rcx, rcx
0x14001c58b  jz      short loc_14001C599
0x14001c58d  call    cs:__imp_FltClose
0x14001c594  nop     dword ptr [rax+rax+00h]
0x14001c599  mov     rcx, [rbp+0C0h+FileObject]; Object
0x14001c59d  test    rcx, rcx
0x14001c5a0  jz      short loc_14001C5AE
0x14001c5a2  call    cs:__imp_ObfDereferenceObject
0x14001c5a9  nop     dword ptr [rax+rax+00h]
0x14001c5ae  mov     eax, ebx
0x14001c5b0  mov     rcx, [rbp+0C0h+var_50]
0x14001c5b4  xor     rcx, rsp; StackCookie
0x14001c5b7  call    __security_check_cookie
0x14001c5bc  add     rsp, 188h
0x14001c5c3  pop     r15
0x14001c5c5  pop     r14
0x14001c5c7  pop     r13
0x14001c5c9  pop     r12
0x14001c5cb  pop     rdi
0x14001c5cc  pop     rsi
0x14001c5cd  pop     rbx
0x14001c5ce  pop     rbp
0x14001c5cf  retn
```
