# Smb2BreakOplockAndContinue

- ea: `0x140068bc0`
- end: `0x140068e38`
- name: `Smb2BreakOplockAndContinue`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x140012c30`
- `0x140013660`
- `0x140013810`
- `0x1400224b8`
- `0x14005a50c`
- `0x140068bc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068c57`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068c57`
- `ntoskrnl!ZwClose` at `0x140068dea`
- `ntoskrnl!ZwClose` at `0x140068dfa`
- `ntoskrnl!ZwClose` at `0x140068dea`
- `ntoskrnl!ZwClose` at `0x140068dfa`
- `ntoskrnl!IoCreateFile` at `0x140068ce4`
- `ntoskrnl!IoCreateFile` at `0x140068dd6`
- `ntoskrnl!IoCreateFile` at `0x140068ce4`
- `ntoskrnl!IoCreateFile` at `0x140068dd6`

## string_xrefs

- `0x140068c38`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2BreakOplockAndContinue(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  bool v4; // zf
  void *v5; // rcx
  __int64 v6; // rdi
  USHORT CurrentNodeNumber; // ax
  NTSTATUS v9; // edi
  char AllocationSize; // [rsp+20h] [rbp-59h]
  _QWORD v11[2]; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+E8h] [rbp+6Fh] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v4 = *(_DWORD *)(a1 + 72) == 1;
  v5 = *(void **)(*(_QWORD *)(v2 + 80) + 88LL);
  FileHandle = 0;
  Handle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  v11[0] = 0;
  v11[1] = 0;
  if ( v4 )
  {
    ObjectAttributes.RootDirectory = v5;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = IoCreateFile(
           &FileHandle,
           0x80u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           1u,
           1u,
           0,
           0,
           0,
           CreateFileTypeNone,
           0,
           0);
    if ( v9 >= 0 )
    {
      Smb2ReferenceObjectFromHandle(a1);
      Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
      *(_QWORD *)(v2 + 80) = 0;
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( IoCreateFile(&Handle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 1u, 0, 0, 0, CreateFileTypeNone, 0, 0) >= 0 )
        ZwClose(Handle);
      ZwClose(FileHandle);
      *(_QWORD *)(a1 + 376) = MEMORY[0xFFFFF78000000014];
      return Smb2PerformCopyChunkWorker(a1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
          (unsigned int)v9);
      }
      Smb2SetError(a1, (unsigned int)v9, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\chunk.c", 768);
      return Srv2CompleteWorkItem(a1, 0);
    }
  }
  else
  {
    v4 = *(_DWORD *)(a1 + 8) == 5;
    *(_QWORD *)(a1 + 48) = Smb2BreakOplockAndContinue;
    *(_DWORD *)(a1 + 72) = 1;
    if ( v4 )
    {
      AllocationSize = 1;
      LOBYTE(a2) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", AllocationSize);
    }
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 144LL);
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    return RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v6 + 8LL * CurrentNodeNumber + 8), a1 + 32, 0);
  }
}

```

## disassembly

```asm
0x140068bc0  mov     [rsp-8+arg_10], rbx
0x140068bc5  mov     [rsp-8+arg_18], rsi
0x140068bca  push    rbp
0x140068bcb  push    rdi
0x140068bcc  push    r14
0x140068bce  lea     rbp, [rsp-47h]
0x140068bd3  sub     rsp, 0C0h
0x140068bda  mov     rsi, [rcx+230h]
0x140068be1  xor     r14d, r14d
0x140068be4  mov     rbx, rcx
0x140068be7  xorps   xmm0, xmm0
0x140068bea  mov     rax, [rsi+50h]
0x140068bee  cmp     dword ptr [rbx+48h], 1
0x140068bf2  mov     rcx, [rax+58h]
0x140068bf6  mov     [rbp+57h+FileHandle], r14
0x140068bfa  mov     [rbp+57h+Handle], r14
0x140068bfe  mov     dword ptr [rbp+57h+ObjectAttributes+4], r14d
0x140068c02  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r14d
0x140068c06  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140068c0a  mov     [rbp+57h+var_60], r14
0x140068c0e  mov     [rbp+57h+var_58], r14
0x140068c12  jz      short loc_140068C7C
0x140068c14  cmp     dword ptr [rbx+8], 5
0x140068c18  lea     rax, Smb2BreakOplockAndContinue
0x140068c1f  mov     [rbx+30h], rax
0x140068c23  mov     dword ptr [rbx+48h], 1
0x140068c2a  jnz     short loc_140068C4C
0x140068c2c  lea     rcx, [rbx+248h]
0x140068c33  mov     byte ptr [rsp+0D0h+AllocationSize], 1
0x140068c38  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140068c3f  mov     r8d, 187h
0x140068c45  mov     dl, 1
0x140068c47  call    SRV2_PERF_ENTER_EX
0x140068c4c  mov     rax, [rbx+40h]
0x140068c50  mov     rdi, [rax+90h]
0x140068c57  call    cs:__imp_KeGetCurrentNodeNumber
0x140068c5e  nop     dword ptr [rax+rax+00h]
0x140068c63  movzx   ecx, ax
0x140068c66  xor     r8d, r8d
0x140068c69  lea     rdx, [rbx+20h]
0x140068c6d  mov     rcx, [rdi+rcx*8+8]
0x140068c72  call    RfspThreadPoolNodeQueueWorkItem
0x140068c77  jmp     loc_140068E1F
0x140068c7c  mov     [rsp+0D0h+Options], r14d; Options
0x140068c81  lea     rax, [rbp+57h+var_60]
0x140068c85  mov     [rsp+0D0h+InternalParameters], r14; InternalParameters
0x140068c8a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140068c8e  mov     [rsp+0D0h+CreateFileType], r14d; CreateFileType
0x140068c93  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140068c97  mov     [rsp+0D0h+EaLength], r14d; EaLength
0x140068c9c  mov     edx, 80h; DesiredAccess
0x140068ca1  mov     [rsp+0D0h+EaBuffer], r14; EaBuffer
0x140068ca6  mov     [rsp+0D0h+CreateOptions], r14d; CreateOptions
0x140068cab  mov     [rsp+0D0h+Disposition], 1; Disposition
0x140068cb3  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x140068cbb  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140068cbf  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140068cc3  mov     [rsp+0D0h+FileAttributes], r14d; FileAttributes
0x140068cc8  mov     [rsp+0D0h+AllocationSize], r14; AllocationSize
0x140068ccd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140068cd4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140068cdb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140068cdf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068ce4  call    cs:__imp_IoCreateFile
0x140068ceb  nop     dword ptr [rax+rax+00h]
0x140068cf0  mov     edi, eax
0x140068cf2  test    eax, eax
0x140068cf4  jns     short loc_140068D56
0x140068cf6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068cfd  lea     rax, WPP_GLOBAL_Control
0x140068d04  cmp     rcx, rax
0x140068d07  jz      short loc_140068D30
0x140068d09  test    dword ptr [rcx+2Ch], 20000000h
0x140068d10  jz      short loc_140068D30
0x140068d12  cmp     byte ptr [rcx+29h], 1
0x140068d16  jb      short loc_140068D30
0x140068d18  mov     rcx, [rcx+18h]
0x140068d1c  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140068d23  mov     edx, 15h
0x140068d28  mov     r9d, edi
0x140068d2b  call    WPP_SF_d
0x140068d30  mov     r9d, 300h
0x140068d36  lea     r8, aOnecoreBaseFsR_16; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140068d3d  mov     edx, edi
0x140068d3f  mov     rcx, rbx
0x140068d42  call    _Smb2SetError
0x140068d47  xor     edx, edx
0x140068d49  mov     rcx, rbx
0x140068d4c  call    Srv2CompleteWorkItem
0x140068d51  jmp     loc_140068E1F
0x140068d56  mov     rcx, rbx
0x140068d59  call    Smb2ReferenceObjectFromHandle
0x140068d5e  mov     rcx, [rsi+50h]; P
0x140068d62  call    Smb2DereferenceHandle
0x140068d67  mov     [rsp+0D0h+Options], r14d; Options
0x140068d6c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140068d70  mov     [rsp+0D0h+InternalParameters], r14; InternalParameters
0x140068d75  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140068d79  mov     [rsp+0D0h+CreateFileType], r14d; CreateFileType
0x140068d7e  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140068d82  mov     [rsi+50h], r14
0x140068d86  mov     edx, 3; DesiredAccess
0x140068d8b  mov     rax, [rbp+57h+FileHandle]
0x140068d8f  xorps   xmm0, xmm0
0x140068d92  mov     [rsp+0D0h+EaLength], r14d; EaLength
0x140068d97  mov     [rsp+0D0h+EaBuffer], r14; EaBuffer
0x140068d9c  mov     [rsp+0D0h+CreateOptions], r14d; CreateOptions
0x140068da1  mov     [rsp+0D0h+Disposition], 1; Disposition
0x140068da9  mov     [rsp+0D0h+ShareAccess], edx; ShareAccess
0x140068dad  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140068db1  lea     rax, [rbp+57h+var_60]
0x140068db5  mov     [rsp+0D0h+FileAttributes], r14d; FileAttributes
0x140068dba  mov     [rsp+0D0h+AllocationSize], r14; AllocationSize
0x140068dbf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140068dc6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140068dcd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140068dd1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068dd6  call    cs:__imp_IoCreateFile
0x140068ddd  nop     dword ptr [rax+rax+00h]
0x140068de2  test    eax, eax
0x140068de4  js      short loc_140068DF6
0x140068de6  mov     rcx, [rbp+57h+Handle]; Handle
0x140068dea  call    cs:__imp_ZwClose
0x140068df1  nop     dword ptr [rax+rax+00h]
0x140068df6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140068dfa  call    cs:__imp_ZwClose
0x140068e01  nop     dword ptr [rax+rax+00h]
0x140068e06  mov     rax, ds:0FFFFF78000000014h
0x140068e10  mov     rcx, rbx
0x140068e13  mov     [rbx+178h], rax
0x140068e1a  call    Smb2PerformCopyChunkWorker
0x140068e1f  lea     r11, [rsp+0D0h+var_10]
0x140068e27  mov     rbx, [r11+30h]
0x140068e2b  mov     rsi, [r11+38h]
0x140068e2f  mov     rsp, r11
0x140068e32  pop     r14
0x140068e34  pop     rdi
0x140068e35  pop     rbp
0x140068e36  retn
```
