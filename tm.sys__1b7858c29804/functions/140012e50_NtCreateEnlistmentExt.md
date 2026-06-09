# NtCreateEnlistmentExt

- ea: `0x140012e50`
- end: `0x140012fe1`
- name: `NtCreateEnlistmentExt`
- size: `401`
- prototype: `NTSTATUS __stdcall(PHANDLE EnlistmentHandle, ACCESS_MASK DesiredAccess, HANDLE ResourceManagerHandle, HANDLE TransactionHandle, POBJECT_ATTRIBUTES ObjectAttributes, ULONG CreateOptions, NOTIFICATION_MASK NotificationMask, PVOID EnlistmentKey)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000d1fc`
- `0x14000d274`
- `0x140012e50`
- `0x14001a870`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012fb3`
- `ntoskrnl!ObfDereferenceObject` at `0x140012fc2`
- `ntoskrnl!ObfDereferenceObject` at `0x140012fb3`
- `ntoskrnl!ObfDereferenceObject` at `0x140012fc2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012f0b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012f54`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012f0b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012f54`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002205f`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002205f`

## pseudocode

```c
NTSTATUS __stdcall NtCreateEnlistmentExt(
        PHANDLE EnlistmentHandle,
        ACCESS_MASK DesiredAccess,
        HANDLE ResourceManagerHandle,
        HANDLE TransactionHandle,
        POBJECT_ATTRIBUTES ObjectAttributes,
        ULONG CreateOptions,
        NOTIFICATION_MASK NotificationMask,
        PVOID EnlistmentKey)
{
  KPROCESSOR_MODE v12; // si
  __int64 ULong64FromUser; // rax
  int EnlistmentExt; // edi
  struct _KRESOURCEMANAGER *v15; // r15
  PVOID v16; // rbx
  PVOID Object; // [rsp+58h] [rbp-50h] BYREF
  PVOID v19; // [rsp+60h] [rbp-48h] BYREF

  v12 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v12 )
  {
    ULong64FromUser = RtlReadULong64FromUser(EnlistmentHandle);
    RtlWriteULong64ToUser(EnlistmentHandle, ULong64FromUser);
  }
  Object = 0;
  EnlistmentExt = ObReferenceObjectByHandle(
                    ResourceManagerHandle,
                    8u,
                    (POBJECT_TYPE)TmResourceManagerObjectType,
                    v12,
                    &Object,
                    0);
  if ( EnlistmentExt >= 0 )
  {
    v15 = (struct _KRESOURCEMANAGER *)Object;
    v19 = 0;
    EnlistmentExt = ObReferenceObjectByHandle(
                      TransactionHandle,
                      4u,
                      (POBJECT_TYPE)TmTransactionObjectType,
                      v12,
                      &v19,
                      0);
    if ( EnlistmentExt >= 0 )
    {
      v16 = v19;
      EnlistmentExt = TmCreateEnlistmentExt(
                        EnlistmentHandle,
                        v12,
                        DesiredAccess,
                        ObjectAttributes,
                        v15,
                        (PKTRANSACTION)v19,
                        CreateOptions,
                        NotificationMask,
                        EnlistmentKey);
      ObfDereferenceObject(v16);
    }
    ObfDereferenceObject(v15);
  }
  return EnlistmentExt;
}

```

## disassembly

```asm
0x140012e50  mov     rax, rsp
0x140012e53  mov     [rax+20h], r9
0x140012e57  mov     [rax+18h], r8
0x140012e5b  mov     [rax+10h], edx
0x140012e5e  mov     [rax+8], rcx
0x140012e62  push    rbx
0x140012e63  push    rsi
0x140012e64  push    rdi
0x140012e65  push    r12
0x140012e67  push    r13
0x140012e69  push    r14
0x140012e6b  push    r15
0x140012e6d  sub     rsp, 70h
0x140012e71  mov     r12, r9
0x140012e74  mov     rdi, r8
0x140012e77  mov     r13d, edx
0x140012e7a  mov     r14, rcx
0x140012e7d  xor     ebx, ebx
0x140012e7f  mov     rax, gs:188h
0x140012e88  mov     sil, [rax+232h]
0x140012e8f  mov     [rsp+0A8h+var_58], sil
0x140012e94  test    sil, sil
0x140012e97  jz      short loc_140012EDD
0x140012e99  call    RtlReadULong64FromUser
0x140012e9e  mov     rdx, rax
0x140012ea1  mov     rcx, r14
0x140012ea4  call    RtlWriteULong64ToUser
0x140012ea9  jmp     short loc_140012ED2
0x140012eab  mov     ebx, eax
0x140012ead  mov     r12, [rsp+0A8h+arg_18]
0x140012eb5  mov     rdi, [rsp+0A8h+arg_10]
0x140012ebd  mov     r13d, [rsp+0A8h+arg_8]
0x140012ec5  mov     r14, [rsp+0A8h+arg_0]
0x140012ecd  mov     sil, [rsp+0A8h+var_58]
0x140012ed2  test    ebx, ebx
0x140012ed4  jns     short loc_140012EDD
0x140012ed6  mov     eax, ebx
0x140012ed8  jmp     loc_140012FD0
0x140012edd  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x140012ee4  mov     [rsp+0A8h+var_50], 0
0x140012eed  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x140012ef6  lea     rax, [rsp+0A8h+var_50]
0x140012efb  mov     [rsp+0A8h+Object], rax; Object
0x140012f00  mov     r9b, sil; AccessMode
0x140012f03  mov     edx, 8; DesiredAccess
0x140012f08  mov     rcx, rdi; Handle
0x140012f0b  call    cs:__imp_ObReferenceObjectByHandle
0x140012f12  nop     dword ptr [rax+rax+00h]
0x140012f17  mov     edi, eax
0x140012f19  test    eax, eax
0x140012f1b  js      loc_140012FCE
0x140012f21  mov     r15, [rsp+0A8h+var_50]
0x140012f26  mov     r8, cs:TmTransactionObjectType; ObjectType
0x140012f2d  mov     [rsp+0A8h+var_48], 0
0x140012f36  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x140012f3f  lea     rax, [rsp+0A8h+var_48]
0x140012f44  mov     [rsp+0A8h+Object], rax; Object
0x140012f49  mov     r9b, sil; AccessMode
0x140012f4c  mov     edx, 4; DesiredAccess
0x140012f51  mov     rcx, r12; Handle
0x140012f54  call    cs:__imp_ObReferenceObjectByHandle
0x140012f5b  nop     dword ptr [rax+rax+00h]
0x140012f60  mov     edi, eax
0x140012f62  test    eax, eax
0x140012f64  js      short loc_140012FBF
0x140012f66  mov     rbx, [rsp+0A8h+var_48]
0x140012f6b  mov     rax, [rsp+0A8h+EnlistmentKey]
0x140012f73  mov     [rsp+0A8h+var_68], rax; EnlistmentKey
0x140012f78  mov     eax, [rsp+0A8h+NotificationMask]
0x140012f7f  mov     [rsp+0A8h+var_70], eax; NotificationMask
0x140012f83  mov     eax, [rsp+0A8h+CreateOptions]
0x140012f8a  mov     [rsp+0A8h+var_78], eax; CreateOptions
0x140012f8e  mov     [rsp+0A8h+HandleInformation], rbx; Transaction
0x140012f93  mov     [rsp+0A8h+Object], r15; ResourceManager
0x140012f98  mov     r9, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x140012fa0  mov     r8d, r13d; DesiredAccess
0x140012fa3  mov     dl, sil; PreviousMode
0x140012fa6  mov     rcx, r14; EnlistmentHandle
0x140012fa9  call    TmCreateEnlistmentExt
0x140012fae  mov     edi, eax
0x140012fb0  mov     rcx, rbx; Object
0x140012fb3  call    cs:__imp_ObfDereferenceObject
0x140012fba  nop     dword ptr [rax+rax+00h]
0x140012fbf  mov     rcx, r15; Object
0x140012fc2  call    cs:__imp_ObfDereferenceObject
0x140012fc9  nop     dword ptr [rax+rax+00h]
0x140012fce  mov     eax, edi
0x140012fd0  add     rsp, 70h
0x140012fd4  pop     r15
0x140012fd6  pop     r14
0x140012fd8  pop     r13
0x140012fda  pop     r12
0x140012fdc  pop     rdi
0x140012fdd  pop     rsi
0x140012fde  pop     rbx
0x140012fdf  retn
0x140022056  push    rbp
0x140022058  sub     rsp, 50h
0x14002205c  mov     rbp, rdx
0x14002205f  call    cs:__imp_ExSystemExceptionFilter
0x140022066  nop     dword ptr [rax+rax+00h]
0x14002206b  nop
0x14002206c  add     rsp, 50h
0x140022070  pop     rbp
0x140022071  retn
```
