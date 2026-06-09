# UdfInvalidateVolumes

- ea: `0x140035ca4`
- end: `0x140035f3d`
- name: `UdfInvalidateVolumes`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x14000ca54`
- `0x1400132c0`
- `0x140035ca4`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140035ed1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035f09`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035ed1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035f09`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035df9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035df9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035e29`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035e29`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035e7d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035eed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035e7d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035eed`
- `ntoskrnl!IoIs32bitProcess` at `0x140035d2b`
- `ntoskrnl!IoIs32bitProcess` at `0x140035d2b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140035d81`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140035d81`
- `ntoskrnl!IoFileObjectType` at `0x140035d5f`
- `ntoskrnl!ObfDereferenceObject` at `0x140035dd8`
- `ntoskrnl!ObfDereferenceObject` at `0x140035dd8`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140035d0b`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140035d0b`

## pseudocode

```c
__int64 __fastcall UdfInvalidateVolumes(_DWORD *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PIRP v3; // rbx
  _DWORD *v4; // rdi
  struct _DEVICE_OBJECT *DeviceObject; // rax
  int v6; // esi
  BOOLEAN v8; // al
  ULONG Options; // ecx
  void *v10; // rcx
  PVOID v11; // rdx
  __int64 v12; // rbp
  __int64 *v13; // r14
  __int64 v14; // rsi
  __int64 v15; // rdx
  PVOID Object; // [rsp+68h] [rbp+10h] BYREF
  LUID PrivilegeValue; // [rsp+70h] [rbp+18h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = Irp;
  Object = 0;
  v4 = a1;
  PrivilegeValue = (LUID)7LL;
  DeviceObject = CurrentStackLocation->DeviceObject;
  if ( DeviceObject != qword_140025B10 && DeviceObject != ::DeviceObject )
  {
    v6 = -1073741808;
LABEL_4:
    UdfCompleteRequest(a1, Irp, v6);
    return (unsigned int)v6;
  }
  if ( !SeSinglePrivilegeCheck(PrivilegeValue, Irp->RequestorMode) )
  {
    v6 = -1073741727;
LABEL_7:
    Irp = v3;
    a1 = v4;
    goto LABEL_4;
  }
  v8 = IoIs32bitProcess(v3);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v8 )
  {
    if ( Options == 4 )
    {
      v10 = (void *)*(int *)v3->AssociatedIrp.MasterIrp;
      goto LABEL_14;
    }
LABEL_12:
    v6 = -1073741811;
    goto LABEL_7;
  }
  if ( Options != 8 )
    goto LABEL_12;
  v10 = *(void **)v3->AssociatedIrp.MasterIrp;
LABEL_14:
  v6 = ObReferenceObjectByHandle(v10, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v6 < 0 )
    goto LABEL_7;
  v11 = Object;
  v12 = *((_QWORD *)Object + 1);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      16,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      *((_QWORD *)Object + 1));
    v11 = Object;
  }
  ObfDereferenceObject(v11);
  v4[7] = v4[7] & 0xFFFFFFF3 | 4;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v13 = (__int64 *)qword_140025B20;
  while ( v13 != &qword_140025B20 )
  {
    v14 = (__int64)(v13 - 4);
    v13 = (__int64 *)*v13;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v14 + 1584));
    v15 = *(_QWORD *)(v14 + 8);
    *(_QWORD *)(v14 + 1640) = KeGetCurrentThread();
    if ( *(_QWORD *)(v15 + 16) == v12 )
    {
      UdfRemoveVpbIfMounted(v12, v15, v14 + 1848);
      if ( *(_DWORD *)(v14 + 52) != 4 )
        *(_DWORD *)(v14 + 52) = 3;
      *(_QWORD *)(v14 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v14 + 1584));
      UdfAcquireResource(v4, v14 + 1480, 0, 0);
      UdfFlushVolume((__int64)v4, v14, 0, 0, 1, 1);
      if ( (unsigned __int8)UdfCheckForDismount(v4, v14, 0) )
        ExReleaseResourceLite((PERESOURCE)(v14 + 1480));
    }
    else
    {
      *(_QWORD *)(v14 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v14 + 1584));
    }
  }
  ExReleaseResourceLite(&Resource);
  UdfCompleteRequest(v4, v3, 0);
  return 0;
}

```

## disassembly

```asm
0x140035ca4  mov     [rsp+arg_0], rbx
0x140035ca9  mov     [rsp+arg_18], rbp
0x140035cae  push    rsi
0x140035caf  push    rdi
0x140035cb0  push    r13
0x140035cb2  push    r14
0x140035cb4  push    r15
0x140035cb6  sub     rsp, 30h
0x140035cba  mov     rsi, [rdx+0B8h]
0x140035cc1  mov     rbx, rdx
0x140035cc4  mov     [rsp+58h+arg_8], 0
0x140035ccd  mov     rdi, rcx
0x140035cd0  mov     qword ptr [rsp+58h+PrivilegeValue.LowPart], 7
0x140035cd9  mov     rax, [rsi+28h]
0x140035cdd  cmp     rax, cs:qword_140025B10
0x140035ce4  jz      short loc_140035D03
0x140035ce6  cmp     rax, cs:DeviceObject
0x140035ced  jz      short loc_140035D03
0x140035cef  mov     esi, 0C0000010h
0x140035cf4  mov     r8d, esi
0x140035cf7  call    UdfCompleteRequest
0x140035cfc  mov     eax, esi
0x140035cfe  jmp     loc_140035F25
0x140035d03  mov     dl, [rdx+40h]; PreviousMode
0x140035d06  mov     rcx, qword ptr [rsp+58h+PrivilegeValue.LowPart]; PrivilegeValue
0x140035d0b  call    cs:__imp_SeSinglePrivilegeCheck
0x140035d12  nop     dword ptr [rax+rax+00h]
0x140035d17  test    al, al
0x140035d19  jnz     short loc_140035D28
0x140035d1b  mov     esi, 0C0000061h
0x140035d20  mov     rdx, rbx
0x140035d23  mov     rcx, rdi
0x140035d26  jmp     short loc_140035CF4
0x140035d28  mov     rcx, rbx; Irp
0x140035d2b  call    cs:__imp_IoIs32bitProcess
0x140035d32  nop     dword ptr [rax+rax+00h]
0x140035d37  mov     ecx, [rsi+10h]
0x140035d3a  test    al, al
0x140035d3c  jz      short loc_140035D4C
0x140035d3e  cmp     ecx, 4
0x140035d41  jnz     short loc_140035D51
0x140035d43  mov     rax, [rbx+18h]
0x140035d47  movsxd  rcx, dword ptr [rax]
0x140035d4a  jmp     short loc_140035D5F
0x140035d4c  cmp     ecx, 8
0x140035d4f  jz      short loc_140035D58
0x140035d51  mov     esi, 0C000000Dh
0x140035d56  jmp     short loc_140035D20
0x140035d58  mov     rax, [rbx+18h]
0x140035d5c  mov     rcx, [rax]; Handle
0x140035d5f  mov     r8, cs:__imp_IoFileObjectType
0x140035d66  lea     rax, [rsp+58h+arg_8]
0x140035d6b  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140035d74  xor     r9d, r9d; AccessMode
0x140035d77  xor     edx, edx; DesiredAccess
0x140035d79  mov     [rsp+58h+Object], rax; Object
0x140035d7e  mov     r8, [r8]; ObjectType
0x140035d81  call    cs:__imp_ObReferenceObjectByHandle
0x140035d88  nop     dword ptr [rax+rax+00h]
0x140035d8d  mov     esi, eax
0x140035d8f  test    eax, eax
0x140035d91  js      short loc_140035D20
0x140035d93  mov     rdx, [rsp+58h+arg_8]
0x140035d98  mov     rbp, [rdx+8]
0x140035d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035da3  lea     rax, WPP_GLOBAL_Control
0x140035daa  cmp     rcx, rax
0x140035dad  jz      short loc_140035DD5
0x140035daf  test    dword ptr [rcx+2Ch], 800h
0x140035db6  jz      short loc_140035DD5
0x140035db8  mov     rcx, [rcx+18h]
0x140035dbc  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x140035dc3  mov     edx, 10h
0x140035dc8  mov     r9, rbp
0x140035dcb  call    WPP_SF_q
0x140035dd0  mov     rdx, [rsp+58h+arg_8]
0x140035dd5  mov     rcx, rdx; Object
0x140035dd8  call    cs:__imp_ObfDereferenceObject
0x140035ddf  nop     dword ptr [rax+rax+00h]
0x140035de4  mov     eax, [rdi+1Ch]
0x140035de7  lea     rcx, Resource; Resource
0x140035dee  and     eax, 0FFFFFFF7h
0x140035df1  mov     dl, 1; Wait
0x140035df3  or      eax, 4
0x140035df6  mov     [rdi+1Ch], eax
0x140035df9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140035e00  nop     dword ptr [rax+rax+00h]
0x140035e05  mov     r14, cs:qword_140025B20
0x140035e0c  lea     r13, qword_140025B20
0x140035e13  jmp     loc_140035EF9
0x140035e18  lea     rsi, [r14-20h]
0x140035e1c  mov     r14, [r14]
0x140035e1f  lea     r15, [rsi+630h]
0x140035e26  mov     rcx, r15; FastMutex
0x140035e29  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140035e30  nop     dword ptr [rax+rax+00h]
0x140035e35  mov     rax, gs:188h
0x140035e3e  mov     rdx, [rsi+8]
0x140035e42  mov     [rsi+668h], rax
0x140035e49  cmp     [rdx+10h], rbp
0x140035e4d  jnz     loc_140035EDF
0x140035e53  lea     r8, [rsi+738h]
0x140035e5a  mov     rcx, rbp
0x140035e5d  call    UdfRemoveVpbIfMounted
0x140035e62  cmp     dword ptr [rsi+34h], 4
0x140035e66  jz      short loc_140035E6F
0x140035e68  mov     dword ptr [rsi+34h], 3
0x140035e6f  mov     rcx, r15; FastMutex
0x140035e72  mov     qword ptr [rsi+668h], 0
0x140035e7d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140035e84  nop     dword ptr [rax+rax+00h]
0x140035e89  lea     r15, [rsi+5C8h]
0x140035e90  xor     r9d, r9d
0x140035e93  mov     rdx, r15
0x140035e96  xor     r8d, r8d
0x140035e99  mov     rcx, rdi
0x140035e9c  call    UdfAcquireResource
0x140035ea1  xor     r9d, r9d
0x140035ea4  mov     byte ptr [rsp+58h+HandleInformation], 1; char
0x140035ea9  xor     r8d, r8d
0x140035eac  mov     byte ptr [rsp+58h+Object], 1; char
0x140035eb1  mov     rdx, rsi
0x140035eb4  mov     rcx, rdi; int
0x140035eb7  call    UdfFlushVolume
0x140035ebc  xor     r8d, r8d
0x140035ebf  mov     rdx, rsi
0x140035ec2  mov     rcx, rdi
0x140035ec5  call    UdfCheckForDismount
0x140035eca  test    al, al
0x140035ecc  jz      short loc_140035EF9
0x140035ece  mov     rcx, r15; Resource
0x140035ed1  call    cs:__imp_ExReleaseResourceLite
0x140035ed8  nop     dword ptr [rax+rax+00h]
0x140035edd  jmp     short loc_140035EF9
0x140035edf  mov     rcx, r15; FastMutex
0x140035ee2  mov     qword ptr [rsi+668h], 0
0x140035eed  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140035ef4  nop     dword ptr [rax+rax+00h]
0x140035ef9  cmp     r14, r13
0x140035efc  jnz     loc_140035E18
0x140035f02  lea     rcx, Resource; Resource
0x140035f09  call    cs:__imp_ExReleaseResourceLite
0x140035f10  nop     dword ptr [rax+rax+00h]
0x140035f15  xor     r8d, r8d
0x140035f18  mov     rdx, rbx
0x140035f1b  mov     rcx, rdi
0x140035f1e  call    UdfCompleteRequest
0x140035f23  xor     eax, eax
0x140035f25  mov     rbx, [rsp+58h+arg_0]
0x140035f2a  mov     rbp, [rsp+58h+arg_18]
0x140035f2f  add     rsp, 30h
0x140035f33  pop     r15
0x140035f35  pop     r14
0x140035f37  pop     r13
0x140035f39  pop     rdi
0x140035f3a  pop     rsi
0x140035f3b  retn
```
