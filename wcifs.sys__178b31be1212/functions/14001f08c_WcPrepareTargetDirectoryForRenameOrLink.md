# WcPrepareTargetDirectoryForRenameOrLink

- ea: `0x14001f08c`
- end: `0x14001f1c0`
- name: `WcPrepareTargetDirectoryForRenameOrLink`
- size: `308`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140027f74`
- `0x1400285c4`

## callees

- `0x14001f08c`
- `0x14001f1c8`
- `0x140020434`
- `0x14002ef90`

## import_xrefs

- `FLTMGR!FltParseFileName` at `0x14001f11d`
- `FLTMGR!FltParseFileName` at `0x14001f11d`
- `FLTMGR!FltClose` at `0x14001f19c`
- `FLTMGR!FltClose` at `0x14001f19c`

## pseudocode

```c
__int64 __fastcall WcPrepareTargetDirectoryForRenameOrLink(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  struct _FLT_INSTANCE *v5; // rcx
  unsigned __int16 *EaBuffer; // rdi
  NTSTATUS v7; // ebx
  unsigned int v8; // ecx
  int v9; // eax
  UNICODE_STRING FileName; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+40h] [rbp-10h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp+20h] BYREF

  FileHandle = 0;
  Iopb = CallbackData->Iopb;
  v5 = *(struct _FLT_INSTANCE **)(a2 + 24);
  EaBuffer = (unsigned __int16 *)Iopb->Parameters.Create.EaBuffer;
  FileName = 0;
  FinalComponent = 0;
  v7 = WcReopenFile(v5, Iopb->Parameters.SetFileInformation.ParentOfTarget, &FileHandle, 0);
  if ( v7 >= 0 )
  {
    FileName.MaximumLength = EaBuffer[8];
    v8 = EaBuffer[8];
    FileName.Buffer = EaBuffer + 10;
    FileName.Length = v8;
    if ( EaBuffer[((unsigned __int64)v8 >> 1) + 9] == 92 )
      FileName.Length = v8 - 2;
    v7 = FltParseFileName(&FileName, 0, 0, &FinalComponent);
    if ( v7 >= 0 )
    {
      v9 = WcPartiallyExpandDirectory(
             CallbackData,
             *(PVOID *)(a2 + 24),
             CallbackData->Iopb->Parameters.QueryFileInformation.InfoBuffer,
             1,
             &FinalComponent);
      v7 = v9;
      if ( v9 >= 0 || v9 == -1073741267 || v9 == -1073741772 )
      {
        v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WcPrepareTargetForRenameOrLink)(
               CallbackData,
               *(_QWORD *)(a2 + 24),
               (LARGE_INTEGER)CallbackData->Iopb->Parameters.Read.ByteOffset.QuadPart,
               FileHandle,
               &FinalComponent);
        if ( v7 >= 0 )
          v7 = 0;
      }
    }
  }
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001f08c  mov     [rsp-18h+arg_8], rbx
0x14001f091  mov     [rsp-18h+arg_10], rsi
0x14001f096  push    rbp
0x14001f097  push    rdi
0x14001f098  push    r14
0x14001f09a  mov     rbp, rsp
0x14001f09d  sub     rsp, 50h
0x14001f0a1  mov     r14, rdx
0x14001f0a4  mov     [rbp+FileHandle], 0
0x14001f0ac  mov     rdx, [rcx+10h]
0x14001f0b0  lea     r8, [rbp+FileHandle]; FileHandle
0x14001f0b4  xorps   xmm0, xmm0
0x14001f0b7  xorps   xmm1, xmm1
0x14001f0ba  mov     rsi, rcx
0x14001f0bd  xor     r9d, r9d; PFILE_OBJECT *
0x14001f0c0  mov     rcx, [r14+18h]; Instance
0x14001f0c4  mov     rdi, [rdx+38h]
0x14001f0c8  movups  xmmword ptr [rbp+FileName.Length], xmm0
0x14001f0cc  movups  xmmword ptr [rbp+FinalComponent.Length], xmm1
0x14001f0d0  mov     rdx, [rdx+28h]; FileObject
0x14001f0d4  call    WcReopenFile
0x14001f0d9  mov     ebx, eax
0x14001f0db  test    eax, eax
0x14001f0dd  js      loc_14001F193
0x14001f0e3  movzx   eax, word ptr [rdi+10h]
0x14001f0e7  mov     [rbp+FileName.MaximumLength], ax
0x14001f0eb  lea     rax, [rdi+14h]
0x14001f0ef  movzx   ecx, word ptr [rdi+10h]
0x14001f0f3  mov     [rbp+FileName.Buffer], rax
0x14001f0f7  mov     eax, ecx
0x14001f0f9  shr     rax, 1
0x14001f0fc  mov     [rbp+FileName.Length], cx
0x14001f100  cmp     word ptr [rdi+rax*2+12h], 5Ch ; '\'
0x14001f106  jnz     short loc_14001F110
0x14001f108  sub     cx, 2
0x14001f10c  mov     [rbp+FileName.Length], cx
0x14001f110  lea     r9, [rbp+FinalComponent]; FinalComponent
0x14001f114  xor     r8d, r8d; Stream
0x14001f117  xor     edx, edx; Extension
0x14001f119  lea     rcx, [rbp+FileName]; FileName
0x14001f11d  call    cs:__imp_FltParseFileName
0x14001f124  nop     dword ptr [rax+rax+00h]
0x14001f129  mov     ebx, eax
0x14001f12b  test    eax, eax
0x14001f12d  js      short loc_14001F193
0x14001f12f  mov     r8, [rsi+10h]
0x14001f133  lea     rax, [rbp+FinalComponent]
0x14001f137  mov     r9, [rbp+FileHandle]
0x14001f13b  mov     rcx, rsi; CallbackData
0x14001f13e  mov     rdx, [r14+18h]; FltObject
0x14001f142  mov     [rsp+50h+var_28], rax; PUNICODE_STRING
0x14001f147  mov     r8, [r8+28h]; Object
0x14001f14b  mov     [rsp+50h+var_30], 1; char
0x14001f150  call    WcPartiallyExpandDirectory
0x14001f155  mov     ebx, eax
0x14001f157  test    eax, eax
0x14001f159  jns     short loc_14001F169
0x14001f15b  cmp     eax, 0C000022Dh
0x14001f160  jz      short loc_14001F169
0x14001f162  cmp     eax, 0C0000034h
0x14001f167  jnz     short loc_14001F193
0x14001f169  mov     r8, [rsi+10h]
0x14001f16d  lea     rax, [rbp+FinalComponent]
0x14001f171  mov     r9, [rbp+FileHandle]
0x14001f175  mov     rcx, rsi
0x14001f178  mov     rdx, [r14+18h]
0x14001f17c  mov     qword ptr [rsp+50h+var_30], rax
0x14001f181  mov     r8, [r8+28h]
0x14001f185  call    WcPrepareTargetForRenameOrLink
0x14001f18a  mov     ebx, eax
0x14001f18c  xor     eax, eax
0x14001f18e  test    ebx, ebx
0x14001f190  cmovns  ebx, eax
0x14001f193  mov     rcx, [rbp+FileHandle]; FileHandle
0x14001f197  test    rcx, rcx
0x14001f19a  jz      short loc_14001F1A8
0x14001f19c  call    cs:__imp_FltClose
0x14001f1a3  nop     dword ptr [rax+rax+00h]
0x14001f1a8  lea     r11, [rsp+50h+var_s0]
0x14001f1ad  mov     eax, ebx
0x14001f1af  mov     rbx, [r11+28h]
0x14001f1b3  mov     rsi, [r11+30h]
0x14001f1b7  mov     rsp, r11
0x14001f1ba  pop     r14
0x14001f1bc  pop     rdi
0x14001f1bd  pop     rbp
0x14001f1be  retn
```
