# InitializeThreadInfoIocp(_EPROCESS *,tagTHREADINFO *)

- ea: `0x14011c9d4`
- end: `0x14011cbcd`
- name: `?InitializeThreadInfoIocp@@YAJPEAU_EPROCESS@@PEAUtagTHREADINFO@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(struct _EPROCESS *, struct tagTHREADINFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140036aa4`

## callees

- `0x14011c9d4`

## import_xrefs

- `ntoskrnl!ObSetHandleAttributes` at `0x14011cb1a`
- `ntoskrnl!ObSetHandleAttributes` at `0x14011cb1a`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x14011cb4f`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x14011cb4f`
- `ntoskrnl!ObCloseHandle` at `0x14011cbae`
- `ntoskrnl!ObCloseHandle` at `0x14011cbae`
- `ntoskrnl!ObDuplicateObject` at `0x14011caa6`
- `ntoskrnl!ObDuplicateObject` at `0x14011caa6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011ca5b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011caec`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011ca5b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011caec`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14011cb89`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14011cb89`
- `ntoskrnl!ZwCreateIoCompletion` at `0x14011ca25`
- `ntoskrnl!ZwCreateIoCompletion` at `0x14011ca25`
- `ntoskrnl!ObfDereferenceObject` at `0x14011cb2c`
- `ntoskrnl!ObfDereferenceObject` at `0x14011cb2c`

## pseudocode

```c
__int64 __fastcall InitializeThreadInfoIocp(struct _EPROCESS *a1, void **a2)
{
  _QWORD *v2; // r14
  NTSTATUS v5; // ebx
  void *v6; // rcx
  HANDLE *v7; // rdi
  HANDLE v8; // r15
  __int64 v9; // r8
  char v11; // [rsp+38h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+48h] BYREF
  struct _OBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+C0h] [rbp+50h] BYREF
  PVOID v15; // [rsp+C8h] [rbp+58h] BYREF

  v2 = a2 + 202;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateIoCompletion(a2 + 202, 0x1F0003u, &ObjectAttributes, 0);
  if ( v5 < 0 )
  {
    *v2 = 0;
    return (unsigned int)v5;
  }
  v6 = (void *)*v2;
  Object = 0;
  v5 = ObReferenceObjectByHandle(v6, 0x1F0003u, 0, 0, &Object, 0);
  a2[201] = Object;
  if ( v5 < 0 )
  {
    a2[201] = 0;
    return (unsigned int)v5;
  }
  v7 = a2 + 203;
  v11 = 0;
  v5 = ObDuplicateObject(a1, *v2, a1, a2 + 203, 0, 0, 2, v11);
  if ( v5 < 0 )
    goto LABEL_10;
  v8 = *v7;
  HandleInformation = 0;
  LOWORD(Object) = 0;
  v15 = 0;
  v5 = ObReferenceObjectByHandle(v8, 0x1F0003u, 0, 1, &v15, &HandleInformation);
  if ( v5 < 0
    || (LOBYTE(v9) = 1,
        BYTE1(Object) = 1,
        LOBYTE(Object) = (HandleInformation.HandleAttributes & 2) != 0,
        v5 = ObSetHandleAttributes(v8, &Object, v9),
        ObfDereferenceObject(v15),
        v5 < 0) )
  {
    ObCloseHandle(*v7, 1);
    goto LABEL_10;
  }
  v7 = a2 + 205;
  v5 = ZwCreateWaitCompletionPacket(a2 + 205, 1, &ObjectAttributes);
  if ( v5 < 0 )
  {
LABEL_10:
    *v7 = 0;
    return (unsigned int)v5;
  }
  return (unsigned int)ZwAssociateWaitCompletionPacket(*v7, *v2, a2[204], 0, 0xFFFFFFFF80000000uLL, 0, 0, 0);
}

```

## disassembly

```asm
0x14011c9d4  push    rbp
0x14011c9d6  push    rbx
0x14011c9d7  push    rsi
0x14011c9d8  push    rdi
0x14011c9d9  push    r12
0x14011c9db  push    r14
0x14011c9dd  push    r15
0x14011c9df  mov     rbp, rsp
0x14011c9e2  sub     rsp, 70h
0x14011c9e6  lea     r14, [rdx+650h]
0x14011c9ed  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14011c9f5  mov     rsi, rdx
0x14011c9f8  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14011ca00  mov     r15, rcx
0x14011ca03  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14011ca07  xor     r12d, r12d
0x14011ca0a  xorps   xmm0, xmm0
0x14011ca0d  mov     rcx, r14; IoCompletionHandle
0x14011ca10  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x14011ca14  xor     r9d, r9d; NumberOfConcurrentThreads
0x14011ca17  mov     [rbp+ObjectAttributes.ObjectName], r12
0x14011ca1b  mov     edx, 1F0003h; DesiredAccess
0x14011ca20  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14011ca25  call    cs:__imp_ZwCreateIoCompletion
0x14011ca2c  nop     dword ptr [rax+rax+00h]
0x14011ca31  mov     ebx, eax
0x14011ca33  test    eax, eax
0x14011ca35  js      loc_14011CBBF
0x14011ca3b  mov     rcx, [r14]; Handle
0x14011ca3e  lea     rax, [rbp+arg_8]
0x14011ca42  mov     [rsp+70h+HandleInformation], r12; HandleInformation
0x14011ca47  xor     r9d, r9d; AccessMode
0x14011ca4a  xor     r8d, r8d; ObjectType
0x14011ca4d  mov     [rsp+70h+Object], rax; Object
0x14011ca52  mov     edx, 1F0003h; DesiredAccess
0x14011ca57  mov     [rbp+arg_8], r12
0x14011ca5b  call    cs:__imp_ObReferenceObjectByHandle
0x14011ca62  nop     dword ptr [rax+rax+00h]
0x14011ca67  mov     ebx, eax
0x14011ca69  mov     rax, [rbp+arg_8]
0x14011ca6d  mov     [rsi+648h], rax
0x14011ca74  test    ebx, ebx
0x14011ca76  js      loc_14011CBC4
0x14011ca7c  mov     rdx, [r14]
0x14011ca7f  lea     rdi, [rsi+658h]
0x14011ca86  mov     byte ptr [rsp+70h+var_38], r12b
0x14011ca8b  mov     r9, rdi
0x14011ca8e  mov     dword ptr [rsp+70h+var_40], 2
0x14011ca96  mov     r8, r15
0x14011ca99  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x14011ca9e  mov     rcx, r15
0x14011caa1  mov     dword ptr [rsp+70h+Object], r12d
0x14011caa6  call    cs:__imp_ObDuplicateObject
0x14011caad  nop     dword ptr [rax+rax+00h]
0x14011cab2  mov     ebx, eax
0x14011cab4  test    eax, eax
0x14011cab6  js      loc_14011CBBA
0x14011cabc  mov     r15, [rdi]
0x14011cabf  lea     rax, [rbp+arg_10]
0x14011cac3  mov     [rsp+70h+HandleInformation], rax; HandleInformation
0x14011cac8  mov     r9b, 1; AccessMode
0x14011cacb  lea     rax, [rbp+arg_18]
0x14011cacf  mov     qword ptr [rbp+arg_10.HandleAttributes], r12
0x14011cad3  xor     r8d, r8d; ObjectType
0x14011cad6  mov     [rsp+70h+Object], rax; Object
0x14011cadb  mov     edx, 1F0003h; DesiredAccess
0x14011cae0  mov     word ptr [rbp+arg_8], r12w
0x14011cae5  mov     rcx, r15; Handle
0x14011cae8  mov     [rbp+arg_18], r12
0x14011caec  call    cs:__imp_ObReferenceObjectByHandle
0x14011caf3  nop     dword ptr [rax+rax+00h]
0x14011caf8  mov     ebx, eax
0x14011cafa  test    eax, eax
0x14011cafc  js      loc_14011CBA9
0x14011cb02  mov     al, byte ptr [rbp+arg_10.HandleAttributes]
0x14011cb05  lea     rdx, [rbp+arg_8]
0x14011cb09  shr     al, 1
0x14011cb0b  mov     r8b, 1
0x14011cb0e  and     al, 1
0x14011cb10  mov     byte ptr [rbp+arg_8+1], 1
0x14011cb14  mov     rcx, r15
0x14011cb17  mov     byte ptr [rbp+arg_8], al
0x14011cb1a  call    cs:__imp_ObSetHandleAttributes
0x14011cb21  nop     dword ptr [rax+rax+00h]
0x14011cb26  mov     rcx, [rbp+arg_18]; Object
0x14011cb2a  mov     ebx, eax
0x14011cb2c  call    cs:__imp_ObfDereferenceObject
0x14011cb33  nop     dword ptr [rax+rax+00h]
0x14011cb38  test    ebx, ebx
0x14011cb3a  js      short loc_14011CBA9
0x14011cb3c  lea     rdi, [rsi+668h]
0x14011cb43  mov     rcx, rdi
0x14011cb46  lea     r8, [rbp+ObjectAttributes]
0x14011cb4a  lea     edx, [r12+1]
0x14011cb4f  call    cs:__imp_ZwCreateWaitCompletionPacket
0x14011cb56  nop     dword ptr [rax+rax+00h]
0x14011cb5b  mov     ebx, eax
0x14011cb5d  test    eax, eax
0x14011cb5f  js      short loc_14011CBBA
0x14011cb61  mov     r8, [rsi+660h]
0x14011cb68  xor     r9d, r9d
0x14011cb6b  mov     rdx, [r14]
0x14011cb6e  mov     rcx, [rdi]
0x14011cb71  mov     [rsp+70h+var_38], r12
0x14011cb76  mov     [rsp+70h+var_40], r12
0x14011cb7b  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x14011cb80  mov     [rsp+70h+Object], 0FFFFFFFF80000000h
0x14011cb89  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14011cb90  nop     dword ptr [rax+rax+00h]
0x14011cb95  mov     ebx, eax
0x14011cb97  mov     eax, ebx
0x14011cb99  add     rsp, 70h
0x14011cb9d  pop     r15
0x14011cb9f  pop     r14
0x14011cba1  pop     r12
0x14011cba3  pop     rdi
0x14011cba4  pop     rsi
0x14011cba5  pop     rbx
0x14011cba6  pop     rbp
0x14011cba7  retn
0x14011cba9  mov     rcx, [rdi]; Handle
0x14011cbac  mov     dl, 1; PreviousMode
0x14011cbae  call    cs:__imp_ObCloseHandle
0x14011cbb5  nop     dword ptr [rax+rax+00h]
0x14011cbba  mov     [rdi], r12
0x14011cbbd  jmp     short loc_14011CB97
0x14011cbbf  mov     [r14], r12
0x14011cbc2  jmp     short loc_14011CB97
0x14011cbc4  mov     [rsi+648h], r12
0x14011cbcb  jmp     short loc_14011CB97
```
