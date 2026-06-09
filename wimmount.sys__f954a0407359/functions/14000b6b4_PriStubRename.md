# PriStubRename

- ea: `0x14000b6b4`
- end: `0x14000b81c`
- name: `PriStubRename`
- size: `360`
- prototype: `__int64 __fastcall(HANDLE Handle, __int64, ULONG, FILE_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000b110`

## callees

- `0x14000ae54`
- `0x14000aee0`
- `0x14000b6b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b7db`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b7db`
- `FLTMGR!FltObjectDereference` at `0x14000b7b0`
- `FLTMGR!FltObjectDereference` at `0x14000b7c7`
- `FLTMGR!FltObjectDereference` at `0x14000b7b0`
- `FLTMGR!FltObjectDereference` at `0x14000b7c7`
- `FLTMGR!FltSetInformationFile` at `0x14000b799`
- `FLTMGR!FltSetInformationFile` at `0x14000b799`

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
0x14000b6b4  mov     [rsp-18h+arg_0], rbx
0x14000b6b9  mov     [rsp-18h+arg_10], rsi
0x14000b6be  push    rbp
0x14000b6bf  push    r12
0x14000b6c1  push    r15
0x14000b6c3  mov     rbp, rsp
0x14000b6c6  sub     rsp, 60h
0x14000b6ca  mov     r10d, [rdx+10h]
0x14000b6ce  mov     r12d, r9d
0x14000b6d1  add     r10, 14h
0x14000b6d5  mov     eax, r8d
0x14000b6d8  add     r10, rdx
0x14000b6db  mov     r15d, r8d
0x14000b6de  add     rax, rdx
0x14000b6e1  mov     [rbp+FileInformation], 0
0x14000b6e9  mov     [rbp+FltObject], 0
0x14000b6f1  mov     rsi, rcx
0x14000b6f4  mov     [rbp+Instance], 0
0x14000b6fc  mov     [rbp+FileObject], 0
0x14000b704  cmp     r10, rax
0x14000b707  jbe     short loc_14000B713
0x14000b709  mov     ebx, 80000005h
0x14000b70e  jmp     loc_14000B803
0x14000b713  mov     eax, r12d
0x14000b716  sub     eax, 0Ah
0x14000b719  jz      short loc_14000B72F
0x14000b71b  sub     eax, 1
0x14000b71e  jz      short loc_14000B72F
0x14000b720  cmp     eax, 36h ; '6'
0x14000b723  jz      short loc_14000B72F
0x14000b725  mov     ebx, 0C000000Dh
0x14000b72a  jmp     loc_14000B803
0x14000b72f  cmp     qword ptr [rdx+8], 0
0x14000b734  jnz     short loc_14000B725
0x14000b736  mov     r8d, r15d
0x14000b739  lea     rcx, [rbp+FileInformation]
0x14000b73d  call    PriDuplicateBufferFromUser
0x14000b742  mov     ebx, eax
0x14000b744  test    eax, eax
0x14000b746  js      loc_14000B7E7
0x14000b74c  lea     rax, [rbp+FileObject]
0x14000b750  mov     edx, 10000h; DesiredAccess
0x14000b755  mov     [rsp+60h+var_30], rax; __int64
0x14000b75a  lea     r9, [rbp+Instance]
0x14000b75e  mov     [rsp+60h+var_38], 0; __int64
0x14000b767  lea     r8, [rbp+FltObject]
0x14000b76b  mov     rcx, rsi; Handle
0x14000b76e  mov     qword ptr [rsp+60h+FileInformationClass], 0; __int64
0x14000b777  call    PriGetObjectsFromUserHandle
0x14000b77c  mov     rsi, [rbp+FileObject]
0x14000b780  mov     ebx, eax
0x14000b782  test    eax, eax
0x14000b784  js      short loc_14000B7A7
0x14000b786  mov     r8, [rbp+FileInformation]; FileInformation
0x14000b78a  mov     r9d, r15d; Length
0x14000b78d  mov     rcx, [rbp+Instance]; Instance
0x14000b791  mov     rdx, rsi; FileObject
0x14000b794  mov     [rsp+60h+FileInformationClass], r12d; FileInformationClass
0x14000b799  call    cs:__imp_FltSetInformationFile
0x14000b7a0  nop     dword ptr [rax+rax+00h]
0x14000b7a5  mov     ebx, eax
0x14000b7a7  mov     rcx, [rbp+FltObject]; FltObject
0x14000b7ab  test    rcx, rcx
0x14000b7ae  jz      short loc_14000B7BC
0x14000b7b0  call    cs:__imp_FltObjectDereference
0x14000b7b7  nop     dword ptr [rax+rax+00h]
0x14000b7bc  cmp     [rbp+Instance], 0
0x14000b7c1  jz      short loc_14000B7D3
0x14000b7c3  mov     rcx, [rbp+Instance]; FltObject
0x14000b7c7  call    cs:__imp_FltObjectDereference
0x14000b7ce  nop     dword ptr [rax+rax+00h]
0x14000b7d3  test    rsi, rsi
0x14000b7d6  jz      short loc_14000B7E7
0x14000b7d8  mov     rcx, rsi; Object
0x14000b7db  call    cs:__imp_ObfDereferenceObject
0x14000b7e2  nop     dword ptr [rax+rax+00h]
0x14000b7e7  cmp     [rbp+FileInformation], 0
0x14000b7ec  jz      short loc_14000B803
0x14000b7ee  mov     rcx, [rbp+FileInformation]; P
0x14000b7f2  mov     edx, 574D6365h; Tag
0x14000b7f7  call    cs:__imp_ExFreePoolWithTag
0x14000b7fe  nop     dword ptr [rax+rax+00h]
0x14000b803  lea     r11, [rsp+60h+var_s0]
0x14000b808  mov     eax, ebx
0x14000b80a  mov     rbx, [r11+20h]
0x14000b80e  mov     rsi, [r11+30h]
0x14000b812  mov     rsp, r11
0x14000b815  pop     r15
0x14000b817  pop     r12
0x14000b819  pop     rbp
0x14000b81a  retn
```
