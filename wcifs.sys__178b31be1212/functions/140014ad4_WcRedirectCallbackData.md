# WcRedirectCallbackData

- ea: `0x140014ad4`
- end: `0x140014c88`
- name: `WcRedirectCallbackData`
- size: `436`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x140026260`
- `0x140026cec`

## callees

- `0x1400024d4`
- `0x140014ad4`
- `0x14002ac50`
- `0x14002ee60`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140014b98`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140014b98`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014b10`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014b10`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014bd0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014be9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014bd0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014be9`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140014c0c`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140014c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c68`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140014c37`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140014c37`

## pseudocode

```c
__int64 __fastcall WcRedirectCallbackData(PFLT_CALLBACK_DATA Data, __int64 a2, const UNICODE_STRING *a3)
{
  struct _FLT_TAG_DATA_BUFFER *TagData; // rsi
  NTSTATUS appended; // ebx
  __int64 v8; // r14
  USHORT TagDataLength; // ax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+90h] [rbp+48h] BYREF

  TagData = Data->TagData;
  v13 = 0;
  DestinationString = 0;
  Source = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  appended = WcLookupLayer(a2, a2 + 168, TagData->GenericGUIDReparseBuffer.TagGuid.Data4, &v13);
  if ( appended >= 0 )
  {
    v8 = v13;
    appended = RtlUShortAdd(*(_WORD *)(v13 + 24), TagData[1].TagDataLength, &DestinationString.MaximumLength);
    if ( appended >= 0 )
    {
      appended = RtlUShortAdd(DestinationString.MaximumLength, a3->Length, &DestinationString.MaximumLength);
      if ( appended >= 0 )
      {
        appended = WcAllocateUnicodeString(1852195671, &DestinationString);
        if ( appended >= 0 )
        {
          RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v8 + 24));
          TagDataLength = TagData[1].TagDataLength;
          if ( TagDataLength )
          {
            Source.MaximumLength = TagData[1].TagDataLength;
            Source.Length = TagDataLength;
            Source.Buffer = &TagData[1].UnparsedNameLength;
            appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
            if ( appended < 0 )
              goto LABEL_11;
          }
          else
          {
            DestinationString.Length -= 2;
          }
          appended = RtlAppendUnicodeStringToString(&DestinationString, a3);
          if ( appended >= 0 )
          {
            appended = IoReplaceFileObjectName(
                         Data->Iopb->TargetFileObject,
                         DestinationString.Buffer,
                         DestinationString.Length);
            if ( appended >= 0 )
            {
              ExFreePoolWithTag(Data->TagData, 0);
              Data->TagData = 0;
              FltSetCallbackDataDirty(Data);
              Data->IoStatus.Status = 260;
              Data->IoStatus.Information = ~*(_BYTE *)(a2 + 32) & 2;
            }
          }
        }
      }
    }
  }
LABEL_11:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140014ad4  push    rbp
0x140014ad6  push    rbx
0x140014ad7  push    rsi
0x140014ad8  push    rdi
0x140014ad9  push    r12
0x140014adb  push    r13
0x140014add  push    r14
0x140014adf  push    r15
0x140014ae1  mov     rbp, rsp
0x140014ae4  sub     rsp, 48h
0x140014ae8  mov     rsi, [rcx+28h]
0x140014aec  mov     r13, rdx
0x140014aef  mov     rdi, rcx
0x140014af2  xorps   xmm0, xmm0
0x140014af5  xorps   xmm1, xmm1
0x140014af8  lea     rcx, [rbp+DestinationString]; DestinationString
0x140014afc  xor     r12d, r12d
0x140014aff  xor     edx, edx; SourceString
0x140014b01  mov     [rbp+arg_0], r12
0x140014b05  mov     r15, r8
0x140014b08  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140014b0c  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140014b10  call    cs:__imp_RtlInitUnicodeString
0x140014b17  nop     dword ptr [rax+rax+00h]
0x140014b1c  lea     r8, [rsi+10h]
0x140014b20  mov     rcx, r13
0x140014b23  lea     rdx, [r13+0A8h]
0x140014b2a  lea     r9, [rbp+arg_0]
0x140014b2e  call    WcLookupLayer
0x140014b33  mov     ebx, eax
0x140014b35  test    eax, eax
0x140014b37  js      loc_140014C5A
0x140014b3d  mov     r14, [rbp+arg_0]
0x140014b41  lea     r8, [rbp+DestinationString.MaximumLength]; pusResult
0x140014b45  movzx   edx, word ptr [rsi+20h]; usAddend
0x140014b49  movzx   ecx, word ptr [r14+18h]; usAugend
0x140014b4e  call    RtlUShortAdd
0x140014b53  mov     ebx, eax
0x140014b55  test    eax, eax
0x140014b57  js      loc_140014C5A
0x140014b5d  movzx   edx, word ptr [r15]; usAddend
0x140014b61  lea     r8, [rbp+DestinationString.MaximumLength]; pusResult
0x140014b65  movzx   ecx, [rbp+DestinationString.MaximumLength]; usAugend
0x140014b69  call    RtlUShortAdd
0x140014b6e  mov     ebx, eax
0x140014b70  test    eax, eax
0x140014b72  js      loc_140014C5A
0x140014b78  lea     rdx, [rbp+DestinationString]
0x140014b7c  mov     ecx, 6E664357h
0x140014b81  call    WcAllocateUnicodeString
0x140014b86  mov     ebx, eax
0x140014b88  test    eax, eax
0x140014b8a  js      loc_140014C5A
0x140014b90  lea     rdx, [r14+18h]; SourceString
0x140014b94  lea     rcx, [rbp+DestinationString]; DestinationString
0x140014b98  call    cs:__imp_RtlCopyUnicodeString
0x140014b9f  nop     dword ptr [rax+rax+00h]
0x140014ba4  movzx   eax, word ptr [rsi+20h]
0x140014ba8  test    ax, ax
0x140014bab  jnz     short loc_140014BB8
0x140014bad  mov     eax, 0FFFEh
0x140014bb2  add     [rbp+DestinationString.Length], ax
0x140014bb6  jmp     short loc_140014BE2
0x140014bb8  mov     [rbp+Source.MaximumLength], ax
0x140014bbc  lea     rdx, [rbp+Source]; Source
0x140014bc0  mov     [rbp+Source.Length], ax
0x140014bc4  lea     rcx, [rbp+DestinationString]; Destination
0x140014bc8  lea     rax, [rsi+22h]
0x140014bcc  mov     [rbp+Source.Buffer], rax
0x140014bd0  call    cs:__imp_RtlAppendUnicodeStringToString
0x140014bd7  nop     dword ptr [rax+rax+00h]
0x140014bdc  mov     ebx, eax
0x140014bde  test    eax, eax
0x140014be0  js      short loc_140014C5A
0x140014be2  mov     rdx, r15; Source
0x140014be5  lea     rcx, [rbp+DestinationString]; Destination
0x140014be9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140014bf0  nop     dword ptr [rax+rax+00h]
0x140014bf5  mov     ebx, eax
0x140014bf7  test    eax, eax
0x140014bf9  js      short loc_140014C5A
0x140014bfb  mov     rcx, [rdi+10h]
0x140014bff  movzx   r8d, [rbp+DestinationString.Length]; FileNameLength
0x140014c04  mov     rdx, [rbp+DestinationString.Buffer]; NewFileName
0x140014c08  mov     rcx, [rcx+8]; FileObject
0x140014c0c  call    cs:__imp_IoReplaceFileObjectName
0x140014c13  nop     dword ptr [rax+rax+00h]
0x140014c18  mov     ebx, eax
0x140014c1a  test    eax, eax
0x140014c1c  js      short loc_140014C5A
0x140014c1e  mov     rcx, [rdi+28h]; P
0x140014c22  xor     edx, edx; Tag
0x140014c24  call    cs:__imp_ExFreePoolWithTag
0x140014c2b  nop     dword ptr [rax+rax+00h]
0x140014c30  mov     rcx, rdi; Data
0x140014c33  mov     [rdi+28h], r12
0x140014c37  call    cs:__imp_FltSetCallbackDataDirty
0x140014c3e  nop     dword ptr [rax+rax+00h]
0x140014c43  mov     dword ptr [rdi+18h], 104h
0x140014c4a  mov     al, [r13+20h]
0x140014c4e  not     al
0x140014c50  movzx   ecx, al
0x140014c53  and     ecx, 2
0x140014c56  mov     [rdi+20h], rcx
0x140014c5a  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140014c5e  test    rcx, rcx
0x140014c61  jz      short loc_140014C74
0x140014c63  mov     edx, 6E664357h; Tag
0x140014c68  call    cs:__imp_ExFreePoolWithTag
0x140014c6f  nop     dword ptr [rax+rax+00h]
0x140014c74  mov     eax, ebx
0x140014c76  add     rsp, 48h
0x140014c7a  pop     r15
0x140014c7c  pop     r14
0x140014c7e  pop     r13
0x140014c80  pop     r12
0x140014c82  pop     rdi
0x140014c83  pop     rsi
0x140014c84  pop     rbx
0x140014c85  pop     rbp
0x140014c86  retn
```
