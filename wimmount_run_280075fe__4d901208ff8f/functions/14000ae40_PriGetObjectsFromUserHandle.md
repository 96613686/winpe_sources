# PriGetObjectsFromUserHandle

- ea: `0x14000ae40`
- end: `0x14000b069`
- name: `PriGetObjectsFromUserHandle`
- size: `553`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, ACCESS_MASK DesiredAccess@<edx>, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000223c`
- `0x14000b418`
- `0x14000b614`
- `0x14000b784`

## callees

- `0x14000ae40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b04b`
- `ntoskrnl!ZwClose` at `0x14000b04b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000af7e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000af7e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000aecc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000aecc`
- `ntoskrnl!IoFileObjectType` at `0x14000aea1`
- `ntoskrnl!IoFileObjectType` at `0x14000af61`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b00c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b00c`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000aefb`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000aefb`
- `FLTMGR!FltObjectReference` at `0x14000ae8b`
- `FLTMGR!FltObjectReference` at `0x14000ae8b`
- `FLTMGR!FltObjectDereference` at `0x14000aff7`
- `FLTMGR!FltObjectDereference` at `0x14000b021`
- `FLTMGR!FltObjectDereference` at `0x14000b036`
- `FLTMGR!FltObjectDereference` at `0x14000aff7`
- `FLTMGR!FltObjectDereference` at `0x14000b021`
- `FLTMGR!FltObjectDereference` at `0x14000b036`
- `FLTMGR!FltEnumerateInstances` at `0x14000af30`
- `FLTMGR!FltEnumerateInstances` at `0x14000af30`

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
0x14000ae40  push    rbp
0x14000ae42  push    rbx
0x14000ae43  push    rsi
0x14000ae44  push    rdi
0x14000ae45  push    r12
0x14000ae47  push    r14
0x14000ae49  push    r15
0x14000ae4b  mov     rbp, rsp
0x14000ae4e  sub     rsp, 70h
0x14000ae52  mov     r15, rcx
0x14000ae55  mov     [rbp+var_10], 0
0x14000ae5d  mov     rcx, cs:gFilterHandle; FltObject
0x14000ae64  mov     r14, r9
0x14000ae67  mov     r12, r8
0x14000ae6a  mov     [rbp+var_28], 0
0x14000ae72  mov     esi, edx
0x14000ae74  mov     [rbp+RetVolume], 0
0x14000ae7c  mov     [rbp+InstanceList], 0
0x14000ae84  mov     [rbp+NumberInstancesReturned], 0
0x14000ae8b  call    cs:__imp_FltObjectReference
0x14000ae92  nop     dword ptr [rax+rax+00h]
0x14000ae97  mov     ebx, eax
0x14000ae99  test    eax, eax
0x14000ae9b  js      loc_14000B003
0x14000aea1  mov     r8, cs:__imp_IoFileObjectType
0x14000aea8  lea     rax, [rbp+var_28]
0x14000aeac  mov     rdi, cs:gFilterHandle
0x14000aeb3  mov     r9b, 1; AccessMode
0x14000aeb6  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x14000aebf  mov     edx, esi; DesiredAccess
0x14000aec1  mov     rcx, r15; Handle
0x14000aec4  mov     [rsp+70h+Object], rax; Object
0x14000aec9  mov     r8, [r8]; ObjectType
0x14000aecc  call    cs:__imp_ObReferenceObjectByHandle
0x14000aed3  nop     dword ptr [rax+rax+00h]
0x14000aed8  mov     ebx, eax
0x14000aeda  test    eax, eax
0x14000aedc  js      loc_14000AFEF
0x14000aee2  mov     r15, [rbp+arg_20]
0x14000aee6  test    r15, r15
0x14000aee9  jnz     short loc_14000AEF0
0x14000aeeb  test    r14, r14
0x14000aeee  jz      short loc_14000AF46
0x14000aef0  mov     rdx, [rbp+var_28]; FileObject
0x14000aef4  lea     r8, [rbp+RetVolume]; RetVolume
0x14000aef8  mov     rcx, rdi; Filter
0x14000aefb  call    cs:__imp_FltGetVolumeFromFileObject
0x14000af02  nop     dword ptr [rax+rax+00h]
0x14000af07  mov     ebx, eax
0x14000af09  test    eax, eax
0x14000af0b  js      loc_14000AFEF
0x14000af11  test    r14, r14
0x14000af14  jz      short loc_14000AF46
0x14000af16  mov     rcx, [rbp+RetVolume]; Volume
0x14000af1a  lea     rax, [rbp+NumberInstancesReturned]
0x14000af1e  mov     r9d, 1; InstanceListSize
0x14000af24  mov     [rsp+70h+Object], rax; NumberInstancesReturned
0x14000af29  lea     r8, [rbp+InstanceList]; InstanceList
0x14000af2d  mov     rdx, rdi; Filter
0x14000af30  call    cs:__imp_FltEnumerateInstances
0x14000af37  nop     dword ptr [rax+rax+00h]
0x14000af3c  mov     ebx, eax
0x14000af3e  test    eax, eax
0x14000af40  js      loc_14000AFEF
0x14000af46  mov     rsi, [rbp+arg_28]
0x14000af4a  test    rsi, rsi
0x14000af4d  jz      short loc_14000AF90
0x14000af4f  lea     rax, [rbp+var_10]
0x14000af53  mov     r9d, 0F0000h; DesiredAccess
0x14000af59  mov     [rsp+70h+Handle], rax; Handle
0x14000af5e  xor     r8d, r8d; PassedAccessState
0x14000af61  mov     rax, cs:__imp_IoFileObjectType
0x14000af68  mov     edx, 200h; HandleAttributes
0x14000af6d  mov     byte ptr [rsp+70h+HandleInformation], 0; AccessMode
0x14000af72  mov     rcx, [rax]
0x14000af75  mov     [rsp+70h+Object], rcx; ObjectType
0x14000af7a  mov     rcx, [rbp+var_28]; Object
0x14000af7e  call    cs:__imp_ObOpenObjectByPointer
0x14000af85  nop     dword ptr [rax+rax+00h]
0x14000af8a  mov     ebx, eax
0x14000af8c  test    eax, eax
0x14000af8e  js      short loc_14000AFEF
0x14000af90  test    r12, r12
0x14000af93  jz      short loc_14000AF9B
0x14000af95  mov     [r12], rdi
0x14000af99  xor     edi, edi
0x14000af9b  test    r14, r14
0x14000af9e  jz      short loc_14000AFAF
0x14000afa0  mov     rax, [rbp+InstanceList]
0x14000afa4  mov     [r14], rax
0x14000afa7  mov     [rbp+InstanceList], 0
0x14000afaf  test    r15, r15
0x14000afb2  jz      short loc_14000AFC3
0x14000afb4  mov     rax, [rbp+RetVolume]
0x14000afb8  mov     [r15], rax
0x14000afbb  mov     [rbp+RetVolume], 0
0x14000afc3  test    rsi, rsi
0x14000afc6  jz      short loc_14000AFD7
0x14000afc8  mov     rax, [rbp+var_10]
0x14000afcc  mov     [rsi], rax
0x14000afcf  mov     [rbp+var_10], 0
0x14000afd7  mov     rcx, [rbp+arg_30]
0x14000afdb  test    rcx, rcx
0x14000afde  jz      short loc_14000AFEF
0x14000afe0  mov     rax, [rbp+var_28]
0x14000afe4  mov     [rcx], rax
0x14000afe7  mov     [rbp+var_28], 0
0x14000afef  test    rdi, rdi
0x14000aff2  jz      short loc_14000B003
0x14000aff4  mov     rcx, rdi; FltObject
0x14000aff7  call    cs:__imp_FltObjectDereference
0x14000affe  nop     dword ptr [rax+rax+00h]
0x14000b003  mov     rcx, [rbp+var_28]; Object
0x14000b007  test    rcx, rcx
0x14000b00a  jz      short loc_14000B018
0x14000b00c  call    cs:__imp_ObfDereferenceObject
0x14000b013  nop     dword ptr [rax+rax+00h]
0x14000b018  mov     rcx, [rbp+RetVolume]; FltObject
0x14000b01c  test    rcx, rcx
0x14000b01f  jz      short loc_14000B02D
0x14000b021  call    cs:__imp_FltObjectDereference
0x14000b028  nop     dword ptr [rax+rax+00h]
0x14000b02d  mov     rcx, [rbp+InstanceList]; FltObject
0x14000b031  test    rcx, rcx
0x14000b034  jz      short loc_14000B042
0x14000b036  call    cs:__imp_FltObjectDereference
0x14000b03d  nop     dword ptr [rax+rax+00h]
0x14000b042  mov     rcx, [rbp+var_10]; Handle
0x14000b046  test    rcx, rcx
0x14000b049  jz      short loc_14000B057
0x14000b04b  call    cs:__imp_ZwClose
0x14000b052  nop     dword ptr [rax+rax+00h]
0x14000b057  mov     eax, ebx
0x14000b059  add     rsp, 70h
0x14000b05d  pop     r15
0x14000b05f  pop     r14
0x14000b061  pop     r12
0x14000b063  pop     rdi
0x14000b064  pop     rsi
0x14000b065  pop     rbx
0x14000b066  pop     rbp
0x14000b067  retn
```
