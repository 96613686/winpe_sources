# NtOpenTransactionExt

- ea: `0x140016c00`
- end: `0x140016e8d`
- name: `NtOpenTransactionExt`
- size: `653`
- prototype: `NTSTATUS __stdcall(PHANDLE TransactionHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, LPGUID Uow, HANDLE TmHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400014d4`
- `0x140002128`
- `0x1400024e0`
- `0x14000d1fc`
- `0x14000d274`
- `0x140016c00`
- `0x140020a6c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140016de7`
- `ntoskrnl!ObfDereferenceObject` at `0x140016e33`
- `ntoskrnl!ObfDereferenceObject` at `0x140016e47`
- `ntoskrnl!ObfDereferenceObject` at `0x14002276c`
- `ntoskrnl!ObfDereferenceObject` at `0x140022782`
- `ntoskrnl!ObfDereferenceObject` at `0x140016de7`
- `ntoskrnl!ObfDereferenceObject` at `0x140016e33`
- `ntoskrnl!ObfDereferenceObject` at `0x140016e47`
- `ntoskrnl!ObfDereferenceObject` at `0x14002276c`
- `ntoskrnl!ObfDereferenceObject` at `0x140022782`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140016dcd`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140016dcd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016d31`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016d31`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022728`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022728`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140016caf`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140016caf`

## pseudocode

```c
NTSTATUS __stdcall NtOpenTransactionExt(
        PHANDLE TransactionHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        LPGUID Uow,
        HANDLE TmHandle)
{
  LPGUID p_Buffer; // r14
  struct _KTHREAD *CurrentThread; // r15
  char *v8; // rsi
  ULONG Attributes; // r13d
  KPROCESSOR_MODE v10; // r15
  __int64 ULong64FromUser; // rax
  int v12; // edi
  struct _RTL_AVL_TABLE *v13; // rcx
  PVOID Object[2]; // [rsp+70h] [rbp-78h] BYREF
  void *Handle; // [rsp+80h] [rbp-68h] BYREF
  __int128 Buffer; // [rsp+90h] [rbp-58h] BYREF

  p_Buffer = Uow;
  Handle = 0;
  Buffer = 0;
  CurrentThread = KeGetCurrentThread();
  if ( !DesiredAccess || !Uow )
    return -1073741811;
  v8 = 0;
  Attributes = 0;
  v10 = *((_BYTE *)CurrentThread + 562);
  if ( v10 )
  {
    ULong64FromUser = RtlReadULong64FromUser(TransactionHandle);
    RtlWriteULong64ToUser(TransactionHandle, ULong64FromUser);
    *(_OWORD *)Object = 0;
    if ( ((unsigned __int8)p_Buffer & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(Object, p_Buffer, 0x10u);
    Buffer = *(_OWORD *)Object;
    p_Buffer = (LPGUID)&Buffer;
  }
  else if ( ObjectAttributes )
  {
    Attributes = ObjectAttributes->Attributes;
  }
  if ( !TmHandle
    || (Object[0] = 0,
        v12 = ObReferenceObjectByHandle(TmHandle, 1u, (POBJECT_TYPE)TmTransactionManagerObjectType, v10, Object, 0),
        v8 = (char *)Object[0],
        v12 >= 0) )
  {
    if ( !v8 )
    {
      v13 = &TmpTransactionsNamespace;
      goto LABEL_16;
    }
    if ( (unsigned __int8)TmpIsOnlineTransactionManager(v8) )
    {
      v13 = (struct _RTL_AVL_TABLE *)(v8 + 176);
LABEL_16:
      v12 = TmpNamespaceLookup(v13, p_Buffer);
      if ( v12 >= 0 )
      {
        v12 = ObOpenObjectByPointer(
                0,
                Attributes,
                0,
                DesiredAccess,
                (POBJECT_TYPE)TmTransactionObjectType,
                v10,
                &Handle);
        if ( v8 )
        {
          ObfDereferenceObject(v8);
          v8 = 0;
        }
        if ( v12 >= 0 )
        {
          if ( v10 )
            RtlWriteULong64ToUser(TransactionHandle, Handle);
          else
            *TransactionHandle = Handle;
        }
      }
      goto LABEL_23;
    }
    v12 = -1072103342;
  }
LABEL_23:
  if ( v8 )
    ObfDereferenceObject(v8);
  if ( v12 == -1073741772 )
    return -1072103346;
  return v12;
}

```

## disassembly

```asm
0x140016c00  mov     r11, rsp
0x140016c03  push    rsi
0x140016c04  push    rdi
0x140016c05  push    r12
0x140016c07  push    r13
0x140016c09  push    r14
0x140016c0b  push    r15
0x140016c0d  sub     rsp, 0B8h
0x140016c14  mov     rax, cs:__security_cookie
0x140016c1b  xor     rax, rsp
0x140016c1e  mov     [rsp+0E8h+var_48], rax
0x140016c26  mov     r14, r9
0x140016c29  mov     eax, edx
0x140016c2b  mov     [rsp+0E8h+DesiredAccess], edx
0x140016c2f  mov     r12, rcx
0x140016c32  mov     rdi, [rsp+0E8h+TmHandle]
0x140016c3a  mov     qword ptr [r11-68h], 0
0x140016c42  xorps   xmm0, xmm0
0x140016c45  movups  xmmword ptr [r11-58h], xmm0
0x140016c4a  mov     [rsp+0E8h+var_88], 0
0x140016c53  mov     [rsp+0E8h+var_A0], 0
0x140016c5c  mov     r15, gs:188h
0x140016c65  test    edx, edx
0x140016c67  jz      loc_140016E65
0x140016c6d  test    r9, r9
0x140016c70  jz      loc_140016E65
0x140016c76  xor     esi, esi
0x140016c78  mov     [rsp+0E8h+var_98], rsi
0x140016c7d  xor     r13d, r13d
0x140016c80  mov     r15b, [r15+232h]
0x140016c87  mov     [rsp+0E8h+var_A8], r15b
0x140016c8c  test    r15b, r15b
0x140016c8f  jz      short loc_140016CF0
0x140016c91  call    RtlReadULong64FromUser
0x140016c96  mov     rdx, rax
0x140016c99  mov     rcx, r12
0x140016c9c  call    RtlWriteULong64ToUser
0x140016ca1  xorps   xmm0, xmm0
0x140016ca4  movups  xmmword ptr [rsp+0E8h+var_78], xmm0
0x140016ca9  test    r14b, 3
0x140016cad  jz      short loc_140016CBB
0x140016caf  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140016cb6  nop     dword ptr [rax+rax+00h]
0x140016cbb  mov     r8d, 10h; Size
0x140016cc1  mov     rdx, r14; Src
0x140016cc4  lea     rcx, [rsp+0E8h+var_78]; void *
0x140016cc9  call    RtlCopyFromUser
0x140016cce  movaps  xmm0, xmmword ptr [rsp+0E8h+var_78]
0x140016cd3  movdqa  [rsp+0E8h+Buffer], xmm0
0x140016cdc  lea     r14, [rsp+0E8h+Buffer]
0x140016ce4  mov     [rsp+0E8h+var_88], r14
0x140016ce9  jmp     short loc_140016CFE
0x140016ceb  jmp     loc_140016E6A
0x140016cf0  mov     [rsp+0E8h+var_88], r14
0x140016cf5  test    r8, r8
0x140016cf8  jz      short loc_140016CFE
0x140016cfa  mov     r13d, [r8+18h]
0x140016cfe  test    rdi, rdi
0x140016d01  jz      short loc_140016D55
0x140016d03  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x140016d0a  mov     [rsp+0E8h+var_78], 0
0x140016d13  mov     [rsp+0E8h+HandleInformation], 0; HandleInformation
0x140016d1c  lea     rax, [rsp+0E8h+var_78]
0x140016d21  mov     [rsp+0E8h+Object], rax; Object
0x140016d26  mov     r9b, r15b; AccessMode
0x140016d29  mov     edx, 1; DesiredAccess
0x140016d2e  mov     rcx, rdi; Handle
0x140016d31  call    cs:__imp_ObReferenceObjectByHandle
0x140016d38  nop     dword ptr [rax+rax+00h]
0x140016d3d  mov     edi, eax
0x140016d3f  mov     rsi, [rsp+0E8h+var_78]
0x140016d44  mov     [rsp+0E8h+var_98], rsi
0x140016d49  mov     [rsp+0E8h+var_A4], eax
0x140016d4d  test    eax, eax
0x140016d4f  js      loc_140016E29
0x140016d55  test    rsi, rsi
0x140016d58  jnz     short loc_140016D63
0x140016d5a  lea     rcx, TmpTransactionsNamespace
0x140016d61  jmp     short loc_140016D84
0x140016d63  mov     rcx, rsi
0x140016d66  call    TmpIsOnlineTransactionManager
0x140016d6b  test    al, al
0x140016d6d  jnz     short loc_140016D7D
0x140016d6f  mov     edi, 0C0190052h
0x140016d74  mov     [rsp+0E8h+var_A4], edi
0x140016d78  jmp     loc_140016E29
0x140016d7d  lea     rcx, [rsi+0B0h]; Table
0x140016d84  lea     r8, [rsp+0E8h+var_A0]
0x140016d89  mov     rdx, r14; Buffer
0x140016d8c  call    TmpNamespaceLookup
0x140016d91  mov     [rsp+0E8h+var_A4], eax
0x140016d95  mov     edi, eax
0x140016d97  test    eax, eax
0x140016d99  js      loc_140016E29
0x140016d9f  lea     rax, [rsp+0E8h+var_68]
0x140016da7  mov     [rsp+0E8h+Handle], rax; Handle
0x140016dac  mov     byte ptr [rsp+0E8h+HandleInformation], r15b; AccessMode
0x140016db1  mov     rax, cs:TmTransactionObjectType
0x140016db8  mov     [rsp+0E8h+Object], rax; ObjectType
0x140016dbd  mov     r9d, [rsp+0E8h+DesiredAccess]; DesiredAccess
0x140016dc2  xor     r8d, r8d; PassedAccessState
0x140016dc5  mov     edx, r13d; HandleAttributes
0x140016dc8  mov     rcx, [rsp+0E8h+var_A0]; Object
0x140016dcd  call    cs:__imp_ObOpenObjectByPointer
0x140016dd4  nop     dword ptr [rax+rax+00h]
0x140016dd9  mov     edi, eax
0x140016ddb  mov     [rsp+0E8h+var_A4], eax
0x140016ddf  test    rsi, rsi
0x140016de2  jz      short loc_140016DFA
0x140016de4  mov     rcx, rsi; Object
0x140016de7  call    cs:__imp_ObfDereferenceObject
0x140016dee  nop     dword ptr [rax+rax+00h]
0x140016df3  xor     esi, esi
0x140016df5  mov     [rsp+0E8h+var_98], rsi
0x140016dfa  test    edi, edi
0x140016dfc  js      short loc_140016E29
0x140016dfe  mov     rax, [rsp+0E8h+var_68]
0x140016e06  test    r15b, r15b
0x140016e09  jz      short loc_140016E18
0x140016e0b  mov     rdx, rax
0x140016e0e  mov     rcx, r12
0x140016e11  call    RtlWriteULong64ToUser
0x140016e16  jmp     short loc_140016E1C
0x140016e18  mov     [r12], rax
0x140016e1c  jmp     short loc_140016E29
0x140016e1e  mov     edi, eax
0x140016e20  mov     [rsp+0E8h+var_A4], eax
0x140016e24  mov     rsi, [rsp+0E8h+var_98]
0x140016e29  mov     rcx, [rsp+0E8h+var_A0]; Object
0x140016e2e  test    rcx, rcx
0x140016e31  jz      short loc_140016E3F
0x140016e33  call    cs:__imp_ObfDereferenceObject
0x140016e3a  nop     dword ptr [rax+rax+00h]
0x140016e3f  test    rsi, rsi
0x140016e42  jz      short loc_140016E53
0x140016e44  mov     rcx, rsi; Object
0x140016e47  call    cs:__imp_ObfDereferenceObject
0x140016e4e  nop     dword ptr [rax+rax+00h]
0x140016e53  mov     eax, 0C019004Eh
0x140016e58  cmp     edi, 0C0000034h
0x140016e5e  cmovz   edi, eax
0x140016e61  mov     eax, edi
0x140016e63  jmp     short loc_140016E6A
0x140016e65  mov     eax, 0C000000Dh
0x140016e6a  mov     rcx, [rsp+0E8h+var_48]
0x140016e72  xor     rcx, rsp; StackCookie
0x140016e75  call    __security_check_cookie
0x140016e7a  add     rsp, 0B8h
0x140016e81  pop     r15
0x140016e83  pop     r14
0x140016e85  pop     r13
0x140016e87  pop     r12
0x140016e89  pop     rdi
0x140016e8a  pop     rsi
0x140016e8b  retn
0x14002271f  push    rbp
0x140022721  sub     rsp, 40h
0x140022725  mov     rbp, rdx
0x140022728  call    cs:__imp_ExSystemExceptionFilter
0x14002272f  nop     dword ptr [rax+rax+00h]
0x140022734  nop
0x140022735  add     rsp, 40h
0x140022739  pop     rbp
0x14002273a  retn
0x14002273c  push    rbp
0x14002273e  sub     rsp, 40h
0x140022742  mov     rbp, rdx
0x140022745  xor     eax, eax
0x140022747  cmp     [rbp+40h], al
0x14002274a  setnz   al
0x14002274d  mov     [rbp+5Ch], eax
0x140022750  mov     eax, [rbp+5Ch]
0x140022753  add     rsp, 40h
0x140022757  pop     rbp
0x140022758  retn
0x14002275a  push    rbp
0x14002275c  sub     rsp, 40h
0x140022760  mov     rbp, rdx
0x140022763  mov     rcx, [rbp+48h]; Object
0x140022767  test    rcx, rcx
0x14002276a  jz      short loc_140022779
0x14002276c  call    cs:__imp_ObfDereferenceObject
0x140022773  nop     dword ptr [rax+rax+00h]
0x140022778  nop
0x140022779  mov     rcx, [rbp+50h]; Object
0x14002277d  test    rcx, rcx
0x140022780  jz      short loc_14002278F
0x140022782  call    cs:__imp_ObfDereferenceObject
0x140022789  nop     dword ptr [rax+rax+00h]
0x14002278e  nop
0x14002278f  add     rsp, 40h
0x140022793  pop     rbp
0x140022794  retn
```
