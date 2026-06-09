# WcGenerateFileName

- ea: `0x1400230c0`
- end: `0x14002318c`
- name: `WcGenerateFileName`
- size: `204`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData, int, _BYTE *, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400230c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140023135`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023135`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140023117`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140023117`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002317b`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002317b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023158`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023158`
- `FLTMGR!FltGetFileNameInformation` at `0x1400230ef`
- `FLTMGR!FltGetFileNameInformation` at `0x1400230ef`

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
0x1400230c0  push    rbx
0x1400230c2  sub     rsp, 20h
0x1400230c6  mov     eax, r9d
0x1400230c9  mov     [rsp+28h+FileNameInformation], 0
0x1400230d2  btr     eax, 18h
0x1400230d6  mov     r9, r8
0x1400230d9  mov     r10, rdx
0x1400230dc  test    r8, r8
0x1400230df  jz      loc_14002316D
0x1400230e5  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x1400230ea  mov     edx, eax; NameOptions
0x1400230ec  mov     rcx, r9; CallbackData
0x1400230ef  call    cs:__imp_FltGetFileNameInformation
0x1400230f6  nop     dword ptr [rax+rax+00h]
0x1400230fb  mov     ebx, eax
0x1400230fd  test    eax, eax
0x1400230ff  js      short loc_14002314E
0x140023101  mov     rdx, [rsp+28h+FileNameInformation]
0x140023106  mov     [rsp+28h+arg_0], rdi
0x14002310b  mov     rdi, [rsp+28h+NameCtrl]
0x140023110  mov     rcx, rdi; NameCtrl
0x140023113  movzx   edx, word ptr [rdx+8]; NewSize
0x140023117  call    cs:__imp_FltCheckAndGrowNameControl
0x14002311e  nop     dword ptr [rax+rax+00h]
0x140023123  mov     ebx, eax
0x140023125  test    eax, eax
0x140023127  js      short loc_140023149
0x140023129  mov     rdx, [rsp+28h+FileNameInformation]
0x14002312e  mov     rcx, rdi; DestinationString
0x140023131  add     rdx, 8; SourceString
0x140023135  call    cs:__imp_RtlCopyUnicodeString
0x14002313c  nop     dword ptr [rax+rax+00h]
0x140023141  mov     rax, [rsp+28h+arg_20]
0x140023146  mov     byte ptr [rax], 0
0x140023149  mov     rdi, [rsp+28h+arg_0]
0x14002314e  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x140023153  test    rcx, rcx
0x140023156  jz      short loc_140023164
0x140023158  call    cs:__imp_FltReleaseFileNameInformation
0x14002315f  nop     dword ptr [rax+rax+00h]
0x140023164  mov     eax, ebx
0x140023166  add     rsp, 20h
0x14002316a  pop     rbx
0x14002316b  retn
0x14002316d  mov     rdx, rcx; Instance
0x140023170  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x140023175  mov     rcx, r10; FileObject
0x140023178  mov     r8d, eax; NameOptions
0x14002317b  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140023182  nop     dword ptr [rax+rax+00h]
0x140023187  jmp     loc_1400230FB
```
