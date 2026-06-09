# Smb2BreakOplockAndContinue

- ea: `0x140068c10`
- end: `0x140068e88`
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
- `0x140068c10`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068ca7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068ca7`
- `ntoskrnl!ZwClose` at `0x140068e3a`
- `ntoskrnl!ZwClose` at `0x140068e4a`
- `ntoskrnl!ZwClose` at `0x140068e3a`
- `ntoskrnl!ZwClose` at `0x140068e4a`
- `ntoskrnl!IoCreateFile` at `0x140068d34`
- `ntoskrnl!IoCreateFile` at `0x140068e26`
- `ntoskrnl!IoCreateFile` at `0x140068d34`
- `ntoskrnl!IoCreateFile` at `0x140068e26`

## string_xrefs

- `0x140068c88`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2BreakOplockAndContinue(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  bool v4; // zf
  void *v5; // rcx
  __int64 v6; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v9; // rdx
  NTSTATUS v10; // edi
  __int64 v11; // r8
  __int64 v12; // r9
  char AllocationSize; // [rsp+20h] [rbp-59h]
  _QWORD v14[2]; // [rsp+70h] [rbp-9h] BYREF
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
  v14[0] = 0;
  v14[1] = 0;
  if ( v4 )
  {
    ObjectAttributes.RootDirectory = v5;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = IoCreateFile(
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
    if ( v10 >= 0 )
    {
      Smb2ReferenceObjectFromHandle(a1, v9, v11, v12);
      Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
      *(_QWORD *)(v2 + 80) = 0;
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
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
          (unsigned int)v10);
      }
      Smb2SetError(a1, (unsigned int)v10, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\chunk.c", 768);
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
0x140068c10  mov     [rsp-8+arg_10], rbx
0x140068c15  mov     [rsp-8+arg_18], rsi
0x140068c1a  push    rbp
0x140068c1b  push    rdi
0x140068c1c  push    r14
0x140068c1e  lea     rbp, [rsp-47h]
0x140068c23  sub     rsp, 0C0h
0x140068c2a  mov     rsi, [rcx+230h]
0x140068c31  xor     r14d, r14d
0x140068c34  mov     rbx, rcx
0x140068c37  xorps   xmm0, xmm0
0x140068c3a  mov     rax, [rsi+50h]
0x140068c3e  cmp     dword ptr [rbx+48h], 1
0x140068c42  mov     rcx, [rax+58h]
0x140068c46  mov     [rbp+57h+FileHandle], r14
0x140068c4a  mov     [rbp+57h+Handle], r14
0x140068c4e  mov     dword ptr [rbp+57h+ObjectAttributes+4], r14d
0x140068c52  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r14d
0x140068c56  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140068c5a  mov     [rbp+57h+var_60], r14
0x140068c5e  mov     [rbp+57h+var_58], r14
0x140068c62  jz      short loc_140068CCC
0x140068c64  cmp     dword ptr [rbx+8], 5
0x140068c68  lea     rax, Smb2BreakOplockAndContinue
0x140068c6f  mov     [rbx+30h], rax
0x140068c73  mov     dword ptr [rbx+48h], 1
0x140068c7a  jnz     short loc_140068C9C
0x140068c7c  lea     rcx, [rbx+248h]
0x140068c83  mov     byte ptr [rsp+0D0h+AllocationSize], 1
0x140068c88  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140068c8f  mov     r8d, 187h
0x140068c95  mov     dl, 1
0x140068c97  call    SRV2_PERF_ENTER_EX
0x140068c9c  mov     rax, [rbx+40h]
0x140068ca0  mov     rdi, [rax+90h]
0x140068ca7  call    cs:__imp_KeGetCurrentNodeNumber
0x140068cae  nop     dword ptr [rax+rax+00h]
0x140068cb3  movzx   ecx, ax
0x140068cb6  xor     r8d, r8d
0x140068cb9  lea     rdx, [rbx+20h]
0x140068cbd  mov     rcx, [rdi+rcx*8+8]
0x140068cc2  call    RfspThreadPoolNodeQueueWorkItem
0x140068cc7  jmp     loc_140068E6F
0x140068ccc  mov     [rsp+0D0h+Options], r14d; Options
0x140068cd1  lea     rax, [rbp+57h+var_60]
0x140068cd5  mov     [rsp+0D0h+InternalParameters], r14; InternalParameters
0x140068cda  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140068cde  mov     [rsp+0D0h+CreateFileType], r14d; CreateFileType
0x140068ce3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140068ce7  mov     [rsp+0D0h+EaLength], r14d; EaLength
0x140068cec  mov     edx, 80h; DesiredAccess
0x140068cf1  mov     [rsp+0D0h+EaBuffer], r14; EaBuffer
0x140068cf6  mov     [rsp+0D0h+CreateOptions], r14d; CreateOptions
0x140068cfb  mov     [rsp+0D0h+Disposition], 1; Disposition
0x140068d03  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x140068d0b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140068d0f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140068d13  mov     [rsp+0D0h+FileAttributes], r14d; FileAttributes
0x140068d18  mov     [rsp+0D0h+AllocationSize], r14; AllocationSize
0x140068d1d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140068d24  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140068d2b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140068d2f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068d34  call    cs:__imp_IoCreateFile
0x140068d3b  nop     dword ptr [rax+rax+00h]
0x140068d40  mov     edi, eax
0x140068d42  test    eax, eax
0x140068d44  jns     short loc_140068DA6
0x140068d46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068d4d  lea     rax, WPP_GLOBAL_Control
0x140068d54  cmp     rcx, rax
0x140068d57  jz      short loc_140068D80
0x140068d59  test    dword ptr [rcx+2Ch], 20000000h
0x140068d60  jz      short loc_140068D80
0x140068d62  cmp     byte ptr [rcx+29h], 1
0x140068d66  jb      short loc_140068D80
0x140068d68  mov     rcx, [rcx+18h]
0x140068d6c  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140068d73  mov     edx, 15h
0x140068d78  mov     r9d, edi
0x140068d7b  call    WPP_SF_d
0x140068d80  mov     r9d, 300h
0x140068d86  lea     r8, aOnecoreBaseFsR_16; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140068d8d  mov     edx, edi
0x140068d8f  mov     rcx, rbx
0x140068d92  call    _Smb2SetError
0x140068d97  xor     edx, edx
0x140068d99  mov     rcx, rbx
0x140068d9c  call    Srv2CompleteWorkItem
0x140068da1  jmp     loc_140068E6F
0x140068da6  mov     rcx, rbx
0x140068da9  call    Smb2ReferenceObjectFromHandle
0x140068dae  mov     rcx, [rsi+50h]; P
0x140068db2  call    Smb2DereferenceHandle
0x140068db7  mov     [rsp+0D0h+Options], r14d; Options
0x140068dbc  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140068dc0  mov     [rsp+0D0h+InternalParameters], r14; InternalParameters
0x140068dc5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140068dc9  mov     [rsp+0D0h+CreateFileType], r14d; CreateFileType
0x140068dce  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140068dd2  mov     [rsi+50h], r14
0x140068dd6  mov     edx, 3; DesiredAccess
0x140068ddb  mov     rax, [rbp+57h+FileHandle]
0x140068ddf  xorps   xmm0, xmm0
0x140068de2  mov     [rsp+0D0h+EaLength], r14d; EaLength
0x140068de7  mov     [rsp+0D0h+EaBuffer], r14; EaBuffer
0x140068dec  mov     [rsp+0D0h+CreateOptions], r14d; CreateOptions
0x140068df1  mov     [rsp+0D0h+Disposition], 1; Disposition
0x140068df9  mov     [rsp+0D0h+ShareAccess], edx; ShareAccess
0x140068dfd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140068e01  lea     rax, [rbp+57h+var_60]
0x140068e05  mov     [rsp+0D0h+FileAttributes], r14d; FileAttributes
0x140068e0a  mov     [rsp+0D0h+AllocationSize], r14; AllocationSize
0x140068e0f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140068e16  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140068e1d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140068e21  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140068e26  call    cs:__imp_IoCreateFile
0x140068e2d  nop     dword ptr [rax+rax+00h]
0x140068e32  test    eax, eax
0x140068e34  js      short loc_140068E46
0x140068e36  mov     rcx, [rbp+57h+Handle]; Handle
0x140068e3a  call    cs:__imp_ZwClose
0x140068e41  nop     dword ptr [rax+rax+00h]
0x140068e46  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140068e4a  call    cs:__imp_ZwClose
0x140068e51  nop     dword ptr [rax+rax+00h]
0x140068e56  mov     rax, ds:0FFFFF78000000014h
0x140068e60  mov     rcx, rbx
0x140068e63  mov     [rbx+178h], rax
0x140068e6a  call    Smb2PerformCopyChunkWorker
0x140068e6f  lea     r11, [rsp+0D0h+var_10]
0x140068e77  mov     rbx, [r11+30h]
0x140068e7b  mov     rsi, [r11+38h]
0x140068e7f  mov     rsp, r11
0x140068e82  pop     r14
0x140068e84  pop     rdi
0x140068e85  pop     rbp
0x140068e86  retn
```
