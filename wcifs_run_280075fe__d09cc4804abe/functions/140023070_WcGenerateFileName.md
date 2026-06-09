# WcGenerateFileName

- ea: `0x140023070`
- end: `0x14002313c`
- name: `WcGenerateFileName`
- size: `204`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CALLBACK_DATA CallbackData@<r8>, __int64, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140023070`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400230e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400230e5`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x1400230c7`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x1400230c7`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002312b`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002312b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023108`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023108`
- `FLTMGR!FltGetFileNameInformation` at `0x14002309f`
- `FLTMGR!FltGetFileNameInformation` at `0x14002309f`

## pseudocode

```c
__int64 __fastcall WcGenerateFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        _BYTE *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  FLT_FILE_NAME_OPTIONS v6; // eax
  NTSTATUS FileNameInformationUnsafe; // eax
  NTSTATUS v8; // ebx
  PFLT_NAME_CONTROL v9; // rdi
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp+18h] BYREF

  FileNameInformation = 0;
  v6 = a4 & 0xFEFFFFFF;
  if ( CallbackData )
    FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v6, &FileNameInformation);
  else
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, v6, &FileNameInformation);
  v8 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe >= 0 )
  {
    v9 = NameCtrl;
    v8 = FltCheckAndGrowNameControl(NameCtrl, FileNameInformation->Name.Length);
    if ( v8 >= 0 )
    {
      RtlCopyUnicodeString(&v9->Name, &FileNameInformation->Name);
      *a5 = 0;
    }
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140023070  push    rbx
0x140023072  sub     rsp, 20h
0x140023076  mov     eax, r9d
0x140023079  mov     [rsp+28h+FileNameInformation], 0
0x140023082  btr     eax, 18h
0x140023086  mov     r9, r8
0x140023089  mov     r10, rdx
0x14002308c  test    r8, r8
0x14002308f  jz      loc_14002311D
0x140023095  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x14002309a  mov     edx, eax; NameOptions
0x14002309c  mov     rcx, r9; CallbackData
0x14002309f  call    cs:__imp_FltGetFileNameInformation
0x1400230a6  nop     dword ptr [rax+rax+00h]
0x1400230ab  mov     ebx, eax
0x1400230ad  test    eax, eax
0x1400230af  js      short loc_1400230FE
0x1400230b1  mov     rdx, [rsp+28h+FileNameInformation]
0x1400230b6  mov     [rsp+28h+arg_0], rdi
0x1400230bb  mov     rdi, [rsp+28h+NameCtrl]
0x1400230c0  mov     rcx, rdi; NameCtrl
0x1400230c3  movzx   edx, word ptr [rdx+8]; NewSize
0x1400230c7  call    cs:__imp_FltCheckAndGrowNameControl
0x1400230ce  nop     dword ptr [rax+rax+00h]
0x1400230d3  mov     ebx, eax
0x1400230d5  test    eax, eax
0x1400230d7  js      short loc_1400230F9
0x1400230d9  mov     rdx, [rsp+28h+FileNameInformation]
0x1400230de  mov     rcx, rdi; DestinationString
0x1400230e1  add     rdx, 8; SourceString
0x1400230e5  call    cs:__imp_RtlCopyUnicodeString
0x1400230ec  nop     dword ptr [rax+rax+00h]
0x1400230f1  mov     rax, [rsp+28h+arg_20]
0x1400230f6  mov     byte ptr [rax], 0
0x1400230f9  mov     rdi, [rsp+28h+arg_0]
0x1400230fe  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x140023103  test    rcx, rcx
0x140023106  jz      short loc_140023114
0x140023108  call    cs:__imp_FltReleaseFileNameInformation
0x14002310f  nop     dword ptr [rax+rax+00h]
0x140023114  mov     eax, ebx
0x140023116  add     rsp, 20h
0x14002311a  pop     rbx
0x14002311b  retn
0x14002311d  mov     rdx, rcx; Instance
0x140023120  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x140023125  mov     rcx, r10; FileObject
0x140023128  mov     r8d, eax; NameOptions
0x14002312b  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140023132  nop     dword ptr [rax+rax+00h]
0x140023137  jmp     loc_1400230AB
```
