# PriGetObjectsFromUserHandle

- ea: `0x14000aee0`
- end: `0x14000b109`
- name: `PriGetObjectsFromUserHandle`
- size: `553`
- prototype: `__int64 __fastcall(HANDLE Handle, ACCESS_MASK DesiredAccess, struct _FLT_FILTER **, PFLT_INSTANCE *, PFLT_VOLUME *, HANDLE *, PVOID *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000223c`
- `0x14000b4b8`
- `0x14000b6b4`
- `0x14000b824`

## callees

- `0x14000aee0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b0eb`
- `ntoskrnl!ZwClose` at `0x14000b0eb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b01e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000b01e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000af6c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000af6c`
- `ntoskrnl!IoFileObjectType` at `0x14000af41`
- `ntoskrnl!IoFileObjectType` at `0x14000b001`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b0ac`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b0ac`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000af9b`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000af9b`
- `FLTMGR!FltObjectReference` at `0x14000af2b`
- `FLTMGR!FltObjectReference` at `0x14000af2b`
- `FLTMGR!FltObjectDereference` at `0x14000b097`
- `FLTMGR!FltObjectDereference` at `0x14000b0c1`
- `FLTMGR!FltObjectDereference` at `0x14000b0d6`
- `FLTMGR!FltObjectDereference` at `0x14000b097`
- `FLTMGR!FltObjectDereference` at `0x14000b0c1`
- `FLTMGR!FltObjectDereference` at `0x14000b0d6`
- `FLTMGR!FltEnumerateInstances` at `0x14000afd0`
- `FLTMGR!FltEnumerateInstances` at `0x14000afd0`

## pseudocode

```c
__int64 __fastcall PriGetObjectsFromUserHandle(
        HANDLE Handle,
        ACCESS_MASK DesiredAccess,
        struct _FLT_FILTER **a3,
        PFLT_INSTANCE *a4,
        PFLT_VOLUME *a5,
        HANDLE *a6,
        PVOID *a7)
{
  NTSTATUS VolumeFromFileObject; // ebx
  struct _FLT_FILTER *v12; // rdi
  ULONG NumberInstancesReturned; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+48h] [rbp-28h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+50h] [rbp-20h] BYREF
  PFLT_INSTANCE InstanceList; // [rsp+58h] [rbp-18h] BYREF
  HANDLE v18; // [rsp+60h] [rbp-10h] BYREF

  v18 = 0;
  Object = 0;
  RetVolume = 0;
  InstanceList = 0;
  NumberInstancesReturned = 0;
  VolumeFromFileObject = FltObjectReference(gFilterHandle);
  if ( VolumeFromFileObject >= 0 )
  {
    v12 = gFilterHandle;
    VolumeFromFileObject = ObReferenceObjectByHandle(
                             Handle,
                             DesiredAccess,
                             (POBJECT_TYPE)IoFileObjectType,
                             1,
                             &Object,
                             0);
    if ( VolumeFromFileObject >= 0 )
    {
      if ( !a5 && !a4
        || (VolumeFromFileObject = FltGetVolumeFromFileObject(v12, (PFILE_OBJECT)Object, &RetVolume),
            VolumeFromFileObject >= 0)
        && (!a4
         || (VolumeFromFileObject = FltEnumerateInstances(RetVolume, v12, &InstanceList, 1u, &NumberInstancesReturned),
             VolumeFromFileObject >= 0)) )
      {
        if ( !a6
          || (VolumeFromFileObject = ObOpenObjectByPointer(
                                       Object,
                                       0x200u,
                                       0,
                                       0xF0000u,
                                       (POBJECT_TYPE)IoFileObjectType,
                                       0,
                                       &v18),
              VolumeFromFileObject >= 0) )
        {
          if ( a3 )
          {
            *a3 = v12;
            v12 = 0;
          }
          if ( a4 )
          {
            *a4 = InstanceList;
            InstanceList = 0;
          }
          if ( a5 )
          {
            *a5 = RetVolume;
            RetVolume = 0;
          }
          if ( a6 )
          {
            *a6 = v18;
            v18 = 0;
          }
          if ( a7 )
          {
            *a7 = Object;
            Object = 0;
          }
        }
      }
    }
    if ( v12 )
      FltObjectDereference(v12);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( InstanceList )
    FltObjectDereference(InstanceList);
  if ( v18 )
    ZwClose(v18);
  return (unsigned int)VolumeFromFileObject;
}

```

## disassembly

```asm
0x14000aee0  push    rbp
0x14000aee2  push    rbx
0x14000aee3  push    rsi
0x14000aee4  push    rdi
0x14000aee5  push    r12
0x14000aee7  push    r14
0x14000aee9  push    r15
0x14000aeeb  mov     rbp, rsp
0x14000aeee  sub     rsp, 70h
0x14000aef2  mov     r15, rcx
0x14000aef5  mov     [rbp+var_10], 0
0x14000aefd  mov     rcx, cs:gFilterHandle; FltObject
0x14000af04  mov     r14, r9
0x14000af07  mov     r12, r8
0x14000af0a  mov     [rbp+var_28], 0
0x14000af12  mov     esi, edx
0x14000af14  mov     [rbp+RetVolume], 0
0x14000af1c  mov     [rbp+InstanceList], 0
0x14000af24  mov     [rbp+NumberInstancesReturned], 0
0x14000af2b  call    cs:__imp_FltObjectReference
0x14000af32  nop     dword ptr [rax+rax+00h]
0x14000af37  mov     ebx, eax
0x14000af39  test    eax, eax
0x14000af3b  js      loc_14000B0A3
0x14000af41  mov     r8, cs:__imp_IoFileObjectType
0x14000af48  lea     rax, [rbp+var_28]
0x14000af4c  mov     rdi, cs:gFilterHandle
0x14000af53  mov     r9b, 1; AccessMode
0x14000af56  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x14000af5f  mov     edx, esi; DesiredAccess
0x14000af61  mov     rcx, r15; Handle
0x14000af64  mov     [rsp+70h+Object], rax; Object
0x14000af69  mov     r8, [r8]; ObjectType
0x14000af6c  call    cs:__imp_ObReferenceObjectByHandle
0x14000af73  nop     dword ptr [rax+rax+00h]
0x14000af78  mov     ebx, eax
0x14000af7a  test    eax, eax
0x14000af7c  js      loc_14000B08F
0x14000af82  mov     r15, [rbp+arg_20]
0x14000af86  test    r15, r15
0x14000af89  jnz     short loc_14000AF90
0x14000af8b  test    r14, r14
0x14000af8e  jz      short loc_14000AFE6
0x14000af90  mov     rdx, [rbp+var_28]; FileObject
0x14000af94  lea     r8, [rbp+RetVolume]; RetVolume
0x14000af98  mov     rcx, rdi; Filter
0x14000af9b  call    cs:__imp_FltGetVolumeFromFileObject
0x14000afa2  nop     dword ptr [rax+rax+00h]
0x14000afa7  mov     ebx, eax
0x14000afa9  test    eax, eax
0x14000afab  js      loc_14000B08F
0x14000afb1  test    r14, r14
0x14000afb4  jz      short loc_14000AFE6
0x14000afb6  mov     rcx, [rbp+RetVolume]; Volume
0x14000afba  lea     rax, [rbp+NumberInstancesReturned]
0x14000afbe  mov     r9d, 1; InstanceListSize
0x14000afc4  mov     [rsp+70h+Object], rax; NumberInstancesReturned
0x14000afc9  lea     r8, [rbp+InstanceList]; InstanceList
0x14000afcd  mov     rdx, rdi; Filter
0x14000afd0  call    cs:__imp_FltEnumerateInstances
0x14000afd7  nop     dword ptr [rax+rax+00h]
0x14000afdc  mov     ebx, eax
0x14000afde  test    eax, eax
0x14000afe0  js      loc_14000B08F
0x14000afe6  mov     rsi, [rbp+arg_28]
0x14000afea  test    rsi, rsi
0x14000afed  jz      short loc_14000B030
0x14000afef  lea     rax, [rbp+var_10]
0x14000aff3  mov     r9d, 0F0000h; DesiredAccess
0x14000aff9  mov     [rsp+70h+Handle], rax; Handle
0x14000affe  xor     r8d, r8d; PassedAccessState
0x14000b001  mov     rax, cs:__imp_IoFileObjectType
0x14000b008  mov     edx, 200h; HandleAttributes
0x14000b00d  mov     byte ptr [rsp+70h+HandleInformation], 0; AccessMode
0x14000b012  mov     rcx, [rax]
0x14000b015  mov     [rsp+70h+Object], rcx; ObjectType
0x14000b01a  mov     rcx, [rbp+var_28]; Object
0x14000b01e  call    cs:__imp_ObOpenObjectByPointer
0x14000b025  nop     dword ptr [rax+rax+00h]
0x14000b02a  mov     ebx, eax
0x14000b02c  test    eax, eax
0x14000b02e  js      short loc_14000B08F
0x14000b030  test    r12, r12
0x14000b033  jz      short loc_14000B03B
0x14000b035  mov     [r12], rdi
0x14000b039  xor     edi, edi
0x14000b03b  test    r14, r14
0x14000b03e  jz      short loc_14000B04F
0x14000b040  mov     rax, [rbp+InstanceList]
0x14000b044  mov     [r14], rax
0x14000b047  mov     [rbp+InstanceList], 0
0x14000b04f  test    r15, r15
0x14000b052  jz      short loc_14000B063
0x14000b054  mov     rax, [rbp+RetVolume]
0x14000b058  mov     [r15], rax
0x14000b05b  mov     [rbp+RetVolume], 0
0x14000b063  test    rsi, rsi
0x14000b066  jz      short loc_14000B077
0x14000b068  mov     rax, [rbp+var_10]
0x14000b06c  mov     [rsi], rax
0x14000b06f  mov     [rbp+var_10], 0
0x14000b077  mov     rcx, [rbp+arg_30]
0x14000b07b  test    rcx, rcx
0x14000b07e  jz      short loc_14000B08F
0x14000b080  mov     rax, [rbp+var_28]
0x14000b084  mov     [rcx], rax
0x14000b087  mov     [rbp+var_28], 0
0x14000b08f  test    rdi, rdi
0x14000b092  jz      short loc_14000B0A3
0x14000b094  mov     rcx, rdi; FltObject
0x14000b097  call    cs:__imp_FltObjectDereference
0x14000b09e  nop     dword ptr [rax+rax+00h]
0x14000b0a3  mov     rcx, [rbp+var_28]; Object
0x14000b0a7  test    rcx, rcx
0x14000b0aa  jz      short loc_14000B0B8
0x14000b0ac  call    cs:__imp_ObfDereferenceObject
0x14000b0b3  nop     dword ptr [rax+rax+00h]
0x14000b0b8  mov     rcx, [rbp+RetVolume]; FltObject
0x14000b0bc  test    rcx, rcx
0x14000b0bf  jz      short loc_14000B0CD
0x14000b0c1  call    cs:__imp_FltObjectDereference
0x14000b0c8  nop     dword ptr [rax+rax+00h]
0x14000b0cd  mov     rcx, [rbp+InstanceList]; FltObject
0x14000b0d1  test    rcx, rcx
0x14000b0d4  jz      short loc_14000B0E2
0x14000b0d6  call    cs:__imp_FltObjectDereference
0x14000b0dd  nop     dword ptr [rax+rax+00h]
0x14000b0e2  mov     rcx, [rbp+var_10]; Handle
0x14000b0e6  test    rcx, rcx
0x14000b0e9  jz      short loc_14000B0F7
0x14000b0eb  call    cs:__imp_ZwClose
0x14000b0f2  nop     dword ptr [rax+rax+00h]
0x14000b0f7  mov     eax, ebx
0x14000b0f9  add     rsp, 70h
0x14000b0fd  pop     r15
0x14000b0ff  pop     r14
0x14000b101  pop     r12
0x14000b103  pop     rdi
0x14000b104  pop     rsi
0x14000b105  pop     rbx
0x14000b106  pop     rbp
0x14000b107  retn
```
