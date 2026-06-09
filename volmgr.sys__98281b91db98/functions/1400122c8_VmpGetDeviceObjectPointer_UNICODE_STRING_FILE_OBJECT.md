# VmpGetDeviceObjectPointer(_UNICODE_STRING *,_FILE_OBJECT * *)

- ea: `0x1400122c8`
- end: `0x1400123e2`
- name: `?VmpGetDeviceObjectPointer@@YAJPEAU_UNICODE_STRING@@PEAPEAU_FILE_OBJECT@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, PVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000f820`

## callees

- `0x1400122c8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140012314`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012314`
- `ntoskrnl!ObfDereferenceObject` at `0x1400123a0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400123a0`
- `ntoskrnl!IoFileObjectType` at `0x140012353`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012380`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012380`
- `ntoskrnl!ZwOpenFile` at `0x140012341`
- `ntoskrnl!ZwOpenFile` at `0x140012341`
- `ntoskrnl!ZwClose` at `0x1400123b5`
- `ntoskrnl!ZwClose` at `0x1400123b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400123c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400123c1`

## pseudocode

```c
__int64 __fastcall VmpGetDeviceObjectPointer(struct _UNICODE_STRING *a1, PVOID *a2)
{
  NTSTATUS v3; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF
  PVOID Object; // [rsp+88h] [rbp+18h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *a2 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  KeEnterCriticalRegion();
  v3 = ZwOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x40040u);
  if ( v3 >= 0 )
  {
    Object = 0;
    v3 = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    if ( v3 < 0 )
    {
      if ( Object )
        ObfDereferenceObject(Object);
    }
    else
    {
      *a2 = Object;
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  KeLeaveCriticalRegion();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400122c8  mov     [rsp-8+arg_10], rbx
0x1400122cd  mov     [rsp-8+arg_18], rdi
0x1400122d2  push    rbp
0x1400122d3  mov     rbp, rsp
0x1400122d6  sub     rsp, 70h
0x1400122da  xorps   xmm0, xmm0
0x1400122dd  mov     [rbp+FileHandle], 0
0x1400122e5  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400122e9  mov     rdi, rdx
0x1400122ec  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400122f4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400122f9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140012301  mov     qword ptr [rdx], 0
0x140012308  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012310  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140012314  call    cs:__imp_KeEnterCriticalRegion
0x14001231b  nop     dword ptr [rax+rax+00h]
0x140012320  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140012324  mov     [rsp+70h+OpenOptions], 40040h; OpenOptions
0x14001232c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012330  mov     [rsp+70h+ShareAccess], 0; ShareAccess
0x140012338  mov     edx, 80h; DesiredAccess
0x14001233d  lea     rcx, [rbp+FileHandle]; FileHandle
0x140012341  call    cs:__imp_ZwOpenFile
0x140012348  nop     dword ptr [rax+rax+00h]
0x14001234d  mov     ebx, eax
0x14001234f  test    eax, eax
0x140012351  js      short loc_1400123AC
0x140012353  mov     r8, cs:__imp_IoFileObjectType
0x14001235a  lea     rax, [rbp+Object]
0x14001235e  mov     rcx, [rbp+FileHandle]; Handle
0x140012362  xor     r9d, r9d; AccessMode
0x140012365  mov     qword ptr [rsp+70h+OpenOptions], 0; HandleInformation
0x14001236e  xor     edx, edx; DesiredAccess
0x140012370  mov     [rbp+Object], 0
0x140012378  mov     r8, [r8]; ObjectType
0x14001237b  mov     qword ptr [rsp+70h+ShareAccess], rax; Object
0x140012380  call    cs:__imp_ObReferenceObjectByHandle
0x140012387  nop     dword ptr [rax+rax+00h]
0x14001238c  mov     rcx, [rbp+Object]; Object
0x140012390  mov     ebx, eax
0x140012392  test    eax, eax
0x140012394  js      short loc_14001239B
0x140012396  mov     [rdi], rcx
0x140012399  jmp     short loc_1400123AC
0x14001239b  test    rcx, rcx
0x14001239e  jz      short loc_1400123AC
0x1400123a0  call    cs:__imp_ObfDereferenceObject
0x1400123a7  nop     dword ptr [rax+rax+00h]
0x1400123ac  mov     rcx, [rbp+FileHandle]; Handle
0x1400123b0  test    rcx, rcx
0x1400123b3  jz      short loc_1400123C1
0x1400123b5  call    cs:__imp_ZwClose
0x1400123bc  nop     dword ptr [rax+rax+00h]
0x1400123c1  call    cs:__imp_KeLeaveCriticalRegion
0x1400123c8  nop     dword ptr [rax+rax+00h]
0x1400123cd  lea     r11, [rsp+70h+var_s0]
0x1400123d2  mov     eax, ebx
0x1400123d4  mov     rbx, [r11+20h]
0x1400123d8  mov     rdi, [r11+28h]
0x1400123dc  mov     rsp, r11
0x1400123df  pop     rbp
0x1400123e0  retn
```
