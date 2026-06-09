# TmInitializeTransactionManagerExt

- ea: `0x140014c50`
- end: `0x140015029`
- name: `TmInitializeTransactionManagerExt`
- size: `985`
- prototype: `NTSTATUS __stdcall(PRKTM TransactionManager, PCUNICODE_STRING LogFileName, PGUID TmId, ULONG CreateOptions)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400172f0`

## callees

- `0x140014c50`
- `0x140016850`
- `0x14001b390`
- `0x14001b444`
- `0x14001bea0`
- `0x14001e020`
- `0x14001ebb8`

## import_xrefs

- `CLFS!CLFS_LSN_NULL` at `0x140014d87`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ffb`
- `ntoskrnl!ObfDereferenceObject` at `0x140014ffb`
- `ntoskrnl!ZwClose` at `0x140014fdc`
- `ntoskrnl!ZwClose` at `0x140014fdc`
- `ntoskrnl!KeInitializeMutex` at `0x140014c92`
- `ntoskrnl!KeInitializeMutex` at `0x140014dd7`
- `ntoskrnl!KeInitializeMutex` at `0x140014c92`
- `ntoskrnl!KeInitializeMutex` at `0x140014dd7`
- `ntoskrnl!KeInitializeEvent` at `0x140014d7b`
- `ntoskrnl!KeInitializeEvent` at `0x140014dfd`
- `ntoskrnl!KeInitializeEvent` at `0x140014d7b`
- `ntoskrnl!KeInitializeEvent` at `0x140014dfd`
- `ntoskrnl!ZwCreateResourceManager` at `0x140014f44`
- `ntoskrnl!ZwCreateResourceManager` at `0x140014f44`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014f77`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140014f77`
- `ntoskrnl!ExUuidCreate` at `0x140014d0a`
- `ntoskrnl!ExUuidCreate` at `0x140014d0a`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140014eba`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140014eba`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014e10`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014e10`

## pseudocode

```c
NTSTATUS __stdcall TmInitializeTransactionManagerExt(
        PRKTM TransactionManager,
        PCUNICODE_STRING LogFileName,
        PGUID TmId,
        ULONG CreateOptions)
{
  int v7; // edi
  PVOID *v8; // r14
  int v9; // eax
  PVOID v10; // rcx
  NTSTATUS v11; // eax
  struct _KRESOURCEMANAGER *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  ULONG CreateOptionsa; // [rsp+28h] [rbp-48h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+40h] BYREF
  ULONG v19; // [rsp+C8h] [rbp+58h]

  v19 = CreateOptions;
  *(_DWORD *)TransactionManager = -1341456380;
  memset(&ObjectAttributes, 0, 44);
  KeInitializeMutex((PRKMUTEX)((char *)TransactionManager + 8), 0);
  *((_DWORD *)TransactionManager + 16) = 1;
  *((_QWORD *)TransactionManager + 16) = 0;
  *((_DWORD *)TransactionManager + 222) = 0;
  *((_QWORD *)TransactionManager + 19) = 0;
  *((_QWORD *)TransactionManager + 20) = 0;
  *((_QWORD *)TransactionManager + 21) = 0;
  *((_QWORD *)TransactionManager + 18) = 0;
  *((_WORD *)TransactionManager + 68) = 0;
  *((_WORD *)TransactionManager + 69) = 0;
  *((_QWORD *)TransactionManager + 9) = 0;
  *((_BYTE *)TransactionManager + 104) = 0;
  if ( TmId )
  {
    *((GUID *)TransactionManager + 7) = *TmId;
  }
  else
  {
    _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 0x20u);
    ExUuidCreate((UUID *)TransactionManager + 7);
  }
  v7 = TmpNamespaceInitialize((PRTL_AVL_TABLE)((char *)TransactionManager + 176));
  if ( v7 < 0 )
    goto LABEL_29;
  v7 = TmpNamespaceInitialize((PRTL_AVL_TABLE)((char *)TransactionManager + 344));
  if ( v7 < 0 )
    goto LABEL_29;
  *((_QWORD *)TransactionManager + 75) = 0;
  *((_DWORD *)TransactionManager + 148) = 1;
  *((_DWORD *)TransactionManager + 152) = 0;
  KeInitializeEvent((PRKEVENT)((char *)TransactionManager + 616), SynchronizationEvent, 0);
  v8 = (PVOID *)((char *)TransactionManager + 672);
  *((_QWORD *)TransactionManager + 73) = 1;
  *((CLFS_LSN *)TransactionManager + 81) = CLFS_LSN_NULL;
  *((CLFS_LSN *)TransactionManager + 82) = CLFS_LSN_NULL;
  *((CLFS_LSN *)TransactionManager + 113) = CLFS_LSN_NULL;
  *((CLFS_LSN *)TransactionManager + 83) = CLFS_LSN_NULL;
  *((_QWORD *)TransactionManager + 84) = 0;
  *((_QWORD *)TransactionManager + 85) = 0;
  KeInitializeMutex((PRKMUTEX)((char *)TransactionManager + 512), 0);
  *((_QWORD *)TransactionManager + 72) = (char *)TransactionManager + 568;
  *((_QWORD *)TransactionManager + 71) = (char *)TransactionManager + 568;
  KeInitializeEvent((PRKEVENT)((char *)TransactionManager + 688), NotificationEvent, 1u);
  ExInitializeResourceLite((PERESOURCE)((char *)TransactionManager + 784));
  *(_QWORD *)((char *)TransactionManager + 892) = 0;
  *((_QWORD *)TransactionManager + 115) = (char *)TransactionManager + 912;
  *((_QWORD *)TransactionManager + 114) = (char *)TransactionManager + 912;
  if ( (v19 & 2) == 0 )
  {
LABEL_10:
    if ( (v19 & 4) != 0 )
    {
      if ( _InterlockedExchange(&dword_1400071C0, 1) )
        goto LABEL_8;
      _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 4u);
    }
    if ( (v19 & 8) != 0 )
      _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 8u);
    if ( (v19 & 0x10) != 0 )
      _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 0x80u);
    if ( (v19 & 0x20) != 0 )
      _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 0x40u);
    if ( (v19 & 1) != 0 )
    {
      _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 1u);
    }
    else
    {
      v7 = RtlDuplicateUnicodeString(0, LogFileName, (PUNICODE_STRING)((char *)TransactionManager + 136));
      if ( v7 < 0 )
        goto LABEL_29;
    }
    if ( (*((_DWORD *)TransactionManager + 32) & 1) != 0 )
      v9 = TmpTmOnline(TransactionManager);
    else
      v9 = TmpCreateOrOpenLogTransactionManager(TransactionManager);
    v7 = v9;
    if ( v9 >= 0 )
    {
      CreateOptionsa = *((_DWORD *)TransactionManager + 32) & 1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = ZwCreateResourceManager(
             (PHANDLE)TransactionManager + 84,
             0x1F007Fu,
             (HANDLE)0xFFFFFFFFFFFFFFFELL,
             (LPGUID)TransactionManager + 7,
             &ObjectAttributes,
             CreateOptionsa,
             0);
      if ( v7 >= 0 )
      {
        v10 = *v8;
        Object = 0;
        v11 = ObReferenceObjectByHandle(v10, 0, (POBJECT_TYPE)TmResourceManagerObjectType, 0, &Object, 0);
        v12 = (struct _KRESOURCEMANAGER *)Object;
        v7 = v11;
        *((_QWORD *)TransactionManager + 85) = Object;
        if ( v11 >= 0 )
        {
          TmEnableCallbacksExt(v12, (PTM_RM_NOTIFICATION)TmpInternalCrmNotification, *v8);
          TmpInsertResourceManagerTm(*((_QWORD *)TransactionManager + 85), TransactionManager);
          v7 = TmpNamespaceInsert(&TmpTmNamespace, 0);
          if ( v7 >= 0 )
            return v7;
        }
      }
    }
    goto LABEL_29;
  }
  if ( !_InterlockedExchange(&dword_1400071C4, 1) )
  {
    _InterlockedOr((volatile signed __int32 *)TransactionManager + 32, 2u);
    goto LABEL_10;
  }
LABEL_8:
  v7 = -1073741811;
LABEL_29:
  v13 = (void *)*((_QWORD *)TransactionManager + 84);
  *((_DWORD *)TransactionManager + 16) = 4;
  if ( v13 )
  {
    ZwClose(v13);
    *((_QWORD *)TransactionManager + 84) = 0;
  }
  v14 = (void *)*((_QWORD *)TransactionManager + 85);
  if ( v14 )
  {
    ObfDereferenceObject(v14);
    *((_QWORD *)TransactionManager + 85) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140014c50  mov     [rsp-38h+arg_8], rbx
0x140014c55  mov     [rsp-38h+arg_18], r9d
0x140014c5a  push    rbp
0x140014c5b  push    rsi
0x140014c5c  push    rdi
0x140014c5d  push    r12
0x140014c5f  push    r13
0x140014c61  push    r14
0x140014c63  push    r15
0x140014c65  mov     rbp, rsp
0x140014c68  sub     rsp, 70h
0x140014c6c  xorps   xmm0, xmm0
0x140014c6f  mov     dword ptr [rcx], 0B00B0004h
0x140014c75  mov     r12, rdx
0x140014c78  mov     rbx, rcx
0x140014c7b  movups  xmmword ptr [rbp+var_30.ObjectName], xmm0
0x140014c7f  xor     eax, eax
0x140014c81  add     rcx, 8; Mutex
0x140014c85  xor     edx, edx; Level
0x140014c87  mov     rdi, r8
0x140014c8a  movups  xmmword ptr [rbp+var_30+1Ch], xmm0
0x140014c8e  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140014c92  call    cs:__imp_KeInitializeMutex
0x140014c99  nop     dword ptr [rax+rax+00h]
0x140014c9e  xor     r13d, r13d
0x140014ca1  mov     dword ptr [rbx+40h], 1
0x140014ca8  mov     [rbx+80h], r13
0x140014caf  lea     r15, [rbx+88h]
0x140014cb6  mov     [rbx+378h], r13d
0x140014cbd  lea     rsi, [rbx+70h]
0x140014cc1  mov     [rbx+98h], r13
0x140014cc8  mov     [rbx+0A0h], r13
0x140014ccf  mov     [rbx+0A8h], r13
0x140014cd6  mov     [rbx+90h], r13
0x140014cdd  mov     [r15], r13w
0x140014ce1  mov     [rbx+8Ah], r13w
0x140014ce9  mov     [rbx+48h], r13
0x140014ced  mov     [rbx+68h], r13b
0x140014cf1  test    rdi, rdi
0x140014cf4  jz      short loc_140014CFF
0x140014cf6  movups  xmm0, xmmword ptr [rdi]
0x140014cf9  movdqu  xmmword ptr [rsi], xmm0
0x140014cfd  jmp     short loc_140014D16
0x140014cff  lock or dword ptr [rbx+80h], 20h
0x140014d07  mov     rcx, rsi; Uuid
0x140014d0a  call    cs:__imp_ExUuidCreate
0x140014d11  nop     dword ptr [rax+rax+00h]
0x140014d16  mov     r8d, 0B0h
0x140014d1c  lea     rcx, [rbx+0B0h]; Table
0x140014d23  lea     r14d, [r8-28h]
0x140014d27  mov     edx, r14d
0x140014d2a  call    TmpNamespaceInitialize
0x140014d2f  mov     edi, eax
0x140014d31  test    eax, eax
0x140014d33  js      loc_140014FC9
0x140014d39  mov     r8d, r14d
0x140014d3c  lea     edx, [r14-28h]
0x140014d40  lea     rcx, [rbx+158h]; Table
0x140014d47  call    TmpNamespaceInitialize
0x140014d4c  mov     edi, eax
0x140014d4e  test    eax, eax
0x140014d50  js      loc_140014FC9
0x140014d56  mov     edi, 1
0x140014d5b  mov     [rbx+258h], r13
0x140014d62  mov     edx, edi; Type
0x140014d64  mov     [rbx+250h], edi
0x140014d6a  lea     rcx, [rbx+268h]; Event
0x140014d71  mov     [rbx+260h], r13d
0x140014d78  xor     r8d, r8d; State
0x140014d7b  call    cs:__imp_KeInitializeEvent
0x140014d82  nop     dword ptr [rax+rax+00h]
0x140014d87  mov     rax, cs:__imp_CLFS_LSN_NULL
0x140014d8e  lea     r14, [rbx+2A0h]
0x140014d95  mov     [rbx+248h], rdi
0x140014d9c  xor     edx, edx; Level
0x140014d9e  mov     rcx, [rax]
0x140014da1  mov     [rbx+288h], rcx
0x140014da8  mov     rcx, [rax]
0x140014dab  mov     [rbx+290h], rcx
0x140014db2  mov     rcx, [rax]
0x140014db5  mov     [rbx+388h], rcx
0x140014dbc  mov     rcx, [rax]
0x140014dbf  mov     [rbx+298h], rcx
0x140014dc6  lea     rcx, [rbx+200h]; Mutex
0x140014dcd  mov     [r14], r13
0x140014dd0  mov     [rbx+2A8h], r13
0x140014dd7  call    cs:__imp_KeInitializeMutex
0x140014dde  nop     dword ptr [rax+rax+00h]
0x140014de3  lea     rax, [rbx+238h]
0x140014dea  mov     r8b, dil; State
0x140014ded  lea     rcx, [rbx+2B0h]; Event
0x140014df4  mov     [rax+8], rax
0x140014df8  xor     edx, edx; Type
0x140014dfa  mov     [rax], rax
0x140014dfd  call    cs:__imp_KeInitializeEvent
0x140014e04  nop     dword ptr [rax+rax+00h]
0x140014e09  lea     rcx, [rbx+310h]; Resource
0x140014e10  call    cs:__imp_ExInitializeResourceLite
0x140014e17  nop     dword ptr [rax+rax+00h]
0x140014e1c  lea     rax, [rbx+390h]
0x140014e23  mov     [rbx+37Ch], r13
0x140014e2a  mov     [rax+8], rax
0x140014e2e  mov     [rax], rax
0x140014e31  mov     eax, [rbp+arg_18]
0x140014e34  test    al, 2
0x140014e36  jz      short loc_140014E56
0x140014e38  mov     eax, edi
0x140014e3a  xchg    eax, cs:dword_1400071C4
0x140014e40  test    eax, eax
0x140014e42  jz      short loc_140014E4E
0x140014e44  mov     edi, 0C000000Dh
0x140014e49  jmp     loc_140014FC9
0x140014e4e  lock or dword ptr [rbx+80h], 2
0x140014e56  mov     eax, [rbp+arg_18]
0x140014e59  test    al, 4
0x140014e5b  jz      short loc_140014E71
0x140014e5d  mov     eax, edi
0x140014e5f  xchg    eax, cs:dword_1400071C0
0x140014e65  test    eax, eax
0x140014e67  jnz     short loc_140014E44
0x140014e69  lock or dword ptr [rbx+80h], 4
0x140014e71  mov     eax, [rbp+arg_18]
0x140014e74  test    al, 8
0x140014e76  jz      short loc_140014E80
0x140014e78  lock or dword ptr [rbx+80h], 8
0x140014e80  mov     eax, [rbp+arg_18]
0x140014e83  test    al, 10h
0x140014e85  jz      short loc_140014E92
0x140014e87  lock or dword ptr [rbx+80h], 80h
0x140014e92  mov     eax, [rbp+arg_18]
0x140014e95  test    al, 20h
0x140014e97  jz      short loc_140014EA1
0x140014e99  lock or dword ptr [rbx+80h], 40h
0x140014ea1  mov     eax, [rbp+arg_18]
0x140014ea4  test    dil, al
0x140014ea7  jz      short loc_140014EB2
0x140014ea9  lock or [rbx+80h], edi
0x140014eb0  jmp     short loc_140014ED5
0x140014eb2  mov     r8, r15; StringOut
0x140014eb5  mov     rdx, r12; StringIn
0x140014eb8  xor     ecx, ecx; Flags
0x140014eba  call    cs:__imp_RtlDuplicateUnicodeString
0x140014ec1  nop     dword ptr [rax+rax+00h]
0x140014ec6  mov     edi, eax
0x140014ec8  test    eax, eax
0x140014eca  js      loc_140014FC9
0x140014ed0  mov     edi, 1
0x140014ed5  mov     eax, [rbx+80h]
0x140014edb  mov     rcx, rbx
0x140014ede  test    dil, al
0x140014ee1  jnz     short loc_140014EEA
0x140014ee3  call    TmpCreateOrOpenLogTransactionManager
0x140014ee8  jmp     short loc_140014EEF
0x140014eea  call    TmpTmOnline
0x140014eef  mov     edi, eax
0x140014ef1  test    eax, eax
0x140014ef3  js      loc_140014FC9
0x140014ef9  mov     eax, [rbx+80h]
0x140014eff  xorps   xmm0, xmm0
0x140014f02  and     eax, 1
0x140014f05  mov     [rsp+70h+Description], r13; Description
0x140014f0a  mov     [rsp+70h+CreateOptions], eax; CreateOptions
0x140014f0e  mov     r9, rsi; ResourceManagerGuid
0x140014f11  lea     rax, [rbp+var_30]
0x140014f15  mov     [rbp+var_30.Length], 30h ; '0'
0x140014f1c  mov     edx, 1F007Fh; DesiredAccess
0x140014f21  mov     [rsp+70h+ObjectAttributes], rax; ObjectAttributes
0x140014f26  mov     r8, 0FFFFFFFFFFFFFFFEh; TmHandle
0x140014f2d  mov     [rbp+var_30.RootDirectory], r13
0x140014f31  mov     rcx, r14; ResourceManagerHandle
0x140014f34  mov     [rbp+var_30.Attributes], 200h
0x140014f3b  mov     [rbp+var_30.ObjectName], r13
0x140014f3f  movdqu  xmmword ptr [rbp+var_30.SecurityDescriptor], xmm0
0x140014f44  call    cs:__imp_ZwCreateResourceManager
0x140014f4b  nop     dword ptr [rax+rax+00h]
0x140014f50  mov     edi, eax
0x140014f52  test    eax, eax
0x140014f54  js      short loc_140014FC9
0x140014f56  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x140014f5d  lea     rax, [rbp+Object]
0x140014f61  mov     rcx, [r14]; Handle
0x140014f64  xor     r9d, r9d; AccessMode
0x140014f67  mov     qword ptr [rsp+70h+CreateOptions], r13; HandleInformation
0x140014f6c  xor     edx, edx; DesiredAccess
0x140014f6e  mov     [rsp+70h+ObjectAttributes], rax; Object
0x140014f73  mov     [rbp+Object], r13
0x140014f77  call    cs:__imp_ObReferenceObjectByHandle
0x140014f7e  nop     dword ptr [rax+rax+00h]
0x140014f83  mov     rcx, [rbp+Object]; ResourceManager
0x140014f87  mov     edi, eax
0x140014f89  mov     [rbx+2A8h], rcx
0x140014f90  test    eax, eax
0x140014f92  js      short loc_140014FC9
0x140014f94  mov     r8, [r14]; RMKey
0x140014f97  lea     rdx, TmpInternalCrmNotification; CallbackRoutine
0x140014f9e  call    TmEnableCallbacksExt
0x140014fa3  mov     rcx, [rbx+2A8h]
0x140014faa  mov     rdx, rbx
0x140014fad  call    TmpInsertResourceManagerTm
0x140014fb2  mov     r8, rbx
0x140014fb5  lea     rcx, TmpTmNamespace; Table
0x140014fbc  xor     edx, edx; Object
0x140014fbe  call    TmpNamespaceInsert
0x140014fc3  mov     edi, eax
0x140014fc5  test    eax, eax
0x140014fc7  jns     short loc_14001500E
0x140014fc9  mov     rcx, [rbx+2A0h]; Handle
0x140014fd0  mov     dword ptr [rbx+40h], 4
0x140014fd7  test    rcx, rcx
0x140014fda  jz      short loc_140014FEF
0x140014fdc  call    cs:__imp_ZwClose
0x140014fe3  nop     dword ptr [rax+rax+00h]
0x140014fe8  mov     [rbx+2A0h], r13
0x140014fef  mov     rcx, [rbx+2A8h]; Object
0x140014ff6  test    rcx, rcx
0x140014ff9  jz      short loc_14001500E
0x140014ffb  call    cs:__imp_ObfDereferenceObject
0x140015002  nop     dword ptr [rax+rax+00h]
0x140015007  mov     [rbx+2A8h], r13
0x14001500e  mov     rbx, [rsp+70h+arg_8]
0x140015016  mov     eax, edi
0x140015018  add     rsp, 70h
0x14001501c  pop     r15
0x14001501e  pop     r14
0x140015020  pop     r13
0x140015022  pop     r12
0x140015024  pop     rdi
0x140015025  pop     rsi
0x140015026  pop     rbp
0x140015027  retn
```
