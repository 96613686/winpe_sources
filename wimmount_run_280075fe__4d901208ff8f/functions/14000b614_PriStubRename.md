# PriStubRename

- ea: `0x14000b614`
- end: `0x14000b77c`
- name: `PriStubRename`
- size: `360`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000b070`

## callees

- `0x14000adb4`
- `0x14000ae40`
- `0x14000b614`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b757`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b757`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b73b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b73b`
- `FLTMGR!FltObjectDereference` at `0x14000b710`
- `FLTMGR!FltObjectDereference` at `0x14000b727`
- `FLTMGR!FltObjectDereference` at `0x14000b710`
- `FLTMGR!FltObjectDereference` at `0x14000b727`
- `FLTMGR!FltSetInformationFile` at `0x14000b6f9`
- `FLTMGR!FltSetInformationFile` at `0x14000b6f9`

## pseudocode

```c
__int64 __fastcall PriStubRename(HANDLE Handle, __int64 a2, ULONG a3, FILE_INFORMATION_CLASS a4)
{
  unsigned __int64 v5; // r10
  NTSTATUS v8; // ebx
  int ObjectsFromUserHandle; // eax
  PFILE_OBJECT v10; // rsi
  PVOID FileInformation; // [rsp+40h] [rbp-20h] BYREF
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-18h] BYREF
  PVOID FltObject; // [rsp+50h] [rbp-10h] BYREF
  PFLT_INSTANCE Instance; // [rsp+88h] [rbp+28h] BYREF

  v5 = a2 + *(unsigned int *)(a2 + 16) + 20LL;
  FileInformation = 0;
  FltObject = 0;
  Instance = 0;
  FileObject = 0;
  if ( v5 <= a2 + (unsigned __int64)a3 )
  {
    if ( (a4 == FileRenameInformation || a4 == FileLinkInformation || a4 == 65) && !*(_QWORD *)(a2 + 8) )
    {
      v8 = PriDuplicateBufferFromUser(&FileInformation, a2, a3);
      if ( v8 >= 0 )
      {
        ObjectsFromUserHandle = PriGetObjectsFromUserHandle(
                                  Handle,
                                  0x10000u,
                                  (struct _FLT_FILTER **)&FltObject,
                                  &Instance,
                                  0,
                                  0,
                                  (PVOID *)&FileObject);
        v10 = FileObject;
        v8 = ObjectsFromUserHandle;
        if ( ObjectsFromUserHandle >= 0 )
          v8 = FltSetInformationFile(Instance, FileObject, FileInformation, a3, a4);
        if ( FltObject )
          FltObjectDereference(FltObject);
        if ( Instance )
          FltObjectDereference(Instance);
        if ( v10 )
          ObfDereferenceObject(v10);
      }
      if ( FileInformation )
        ExFreePoolWithTag(FileInformation, 0x574D6365u);
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-2147483643;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000b614  mov     [rsp-18h+arg_0], rbx
0x14000b619  mov     [rsp-18h+arg_10], rsi
0x14000b61e  push    rbp
0x14000b61f  push    r12
0x14000b621  push    r15
0x14000b623  mov     rbp, rsp
0x14000b626  sub     rsp, 60h
0x14000b62a  mov     r10d, [rdx+10h]
0x14000b62e  mov     r12d, r9d
0x14000b631  add     r10, 14h
0x14000b635  mov     eax, r8d
0x14000b638  add     r10, rdx
0x14000b63b  mov     r15d, r8d
0x14000b63e  add     rax, rdx
0x14000b641  mov     [rbp+FileInformation], 0
0x14000b649  mov     [rbp+FltObject], 0
0x14000b651  mov     rsi, rcx
0x14000b654  mov     [rbp+Instance], 0
0x14000b65c  mov     [rbp+FileObject], 0
0x14000b664  cmp     r10, rax
0x14000b667  jbe     short loc_14000B673
0x14000b669  mov     ebx, 80000005h
0x14000b66e  jmp     loc_14000B763
0x14000b673  mov     eax, r12d
0x14000b676  sub     eax, 0Ah
0x14000b679  jz      short loc_14000B68F
0x14000b67b  sub     eax, 1
0x14000b67e  jz      short loc_14000B68F
0x14000b680  cmp     eax, 36h ; '6'
0x14000b683  jz      short loc_14000B68F
0x14000b685  mov     ebx, 0C000000Dh
0x14000b68a  jmp     loc_14000B763
0x14000b68f  cmp     qword ptr [rdx+8], 0
0x14000b694  jnz     short loc_14000B685
0x14000b696  mov     r8d, r15d
0x14000b699  lea     rcx, [rbp+FileInformation]
0x14000b69d  call    PriDuplicateBufferFromUser
0x14000b6a2  mov     ebx, eax
0x14000b6a4  test    eax, eax
0x14000b6a6  js      loc_14000B747
0x14000b6ac  lea     rax, [rbp+FileObject]
0x14000b6b0  mov     edx, 10000h; DesiredAccess
0x14000b6b5  mov     [rsp+60h+var_30], rax; __int64
0x14000b6ba  lea     r9, [rbp+Instance]
0x14000b6be  mov     [rsp+60h+var_38], 0; __int64
0x14000b6c7  lea     r8, [rbp+FltObject]
0x14000b6cb  mov     rcx, rsi; Handle
0x14000b6ce  mov     qword ptr [rsp+60h+FileInformationClass], 0; __int64
0x14000b6d7  call    PriGetObjectsFromUserHandle
0x14000b6dc  mov     rsi, [rbp+FileObject]
0x14000b6e0  mov     ebx, eax
0x14000b6e2  test    eax, eax
0x14000b6e4  js      short loc_14000B707
0x14000b6e6  mov     r8, [rbp+FileInformation]; FileInformation
0x14000b6ea  mov     r9d, r15d; Length
0x14000b6ed  mov     rcx, [rbp+Instance]; Instance
0x14000b6f1  mov     rdx, rsi; FileObject
0x14000b6f4  mov     [rsp+60h+FileInformationClass], r12d; FileInformationClass
0x14000b6f9  call    cs:__imp_FltSetInformationFile
0x14000b700  nop     dword ptr [rax+rax+00h]
0x14000b705  mov     ebx, eax
0x14000b707  mov     rcx, [rbp+FltObject]; FltObject
0x14000b70b  test    rcx, rcx
0x14000b70e  jz      short loc_14000B71C
0x14000b710  call    cs:__imp_FltObjectDereference
0x14000b717  nop     dword ptr [rax+rax+00h]
0x14000b71c  cmp     [rbp+Instance], 0
0x14000b721  jz      short loc_14000B733
0x14000b723  mov     rcx, [rbp+Instance]; FltObject
0x14000b727  call    cs:__imp_FltObjectDereference
0x14000b72e  nop     dword ptr [rax+rax+00h]
0x14000b733  test    rsi, rsi
0x14000b736  jz      short loc_14000B747
0x14000b738  mov     rcx, rsi; Object
0x14000b73b  call    cs:__imp_ObfDereferenceObject
0x14000b742  nop     dword ptr [rax+rax+00h]
0x14000b747  cmp     [rbp+FileInformation], 0
0x14000b74c  jz      short loc_14000B763
0x14000b74e  mov     rcx, [rbp+FileInformation]; P
0x14000b752  mov     edx, 574D6365h; Tag
0x14000b757  call    cs:__imp_ExFreePoolWithTag
0x14000b75e  nop     dword ptr [rax+rax+00h]
0x14000b763  lea     r11, [rsp+60h+var_s0]
0x14000b768  mov     eax, ebx
0x14000b76a  mov     rbx, [r11+20h]
0x14000b76e  mov     rsi, [r11+30h]
0x14000b772  mov     rsp, r11
0x14000b775  pop     r15
0x14000b777  pop     r12
0x14000b779  pop     rbp
0x14000b77a  retn
```
