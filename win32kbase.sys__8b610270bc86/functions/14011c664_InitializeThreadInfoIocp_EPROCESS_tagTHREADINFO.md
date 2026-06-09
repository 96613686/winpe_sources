# InitializeThreadInfoIocp(_EPROCESS *,tagTHREADINFO *)

- ea: `0x14011c664`
- end: `0x14011c85d`
- name: `?InitializeThreadInfoIocp@@YAJPEAU_EPROCESS@@PEAUtagTHREADINFO@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(struct _EPROCESS *, struct tagTHREADINFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002d824`

## callees

- `0x14011c664`

## import_xrefs

- `ntoskrnl!ObSetHandleAttributes` at `0x14011c7aa`
- `ntoskrnl!ObSetHandleAttributes` at `0x14011c7aa`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x14011c7df`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x14011c7df`
- `ntoskrnl!ObCloseHandle` at `0x14011c83e`
- `ntoskrnl!ObCloseHandle` at `0x14011c83e`
- `ntoskrnl!ObDuplicateObject` at `0x14011c736`
- `ntoskrnl!ObDuplicateObject` at `0x14011c736`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011c6eb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011c77c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011c6eb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14011c77c`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14011c819`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14011c819`
- `ntoskrnl!ZwCreateIoCompletion` at `0x14011c6b5`
- `ntoskrnl!ZwCreateIoCompletion` at `0x14011c6b5`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c7bc`
- `ntoskrnl!ObfDereferenceObject` at `0x14011c7bc`

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
0x14011c664  push    rbp
0x14011c666  push    rbx
0x14011c667  push    rsi
0x14011c668  push    rdi
0x14011c669  push    r12
0x14011c66b  push    r14
0x14011c66d  push    r15
0x14011c66f  mov     rbp, rsp
0x14011c672  sub     rsp, 70h
0x14011c676  lea     r14, [rdx+650h]
0x14011c67d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14011c685  mov     rsi, rdx
0x14011c688  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14011c690  mov     r15, rcx
0x14011c693  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14011c697  xor     r12d, r12d
0x14011c69a  xorps   xmm0, xmm0
0x14011c69d  mov     rcx, r14; IoCompletionHandle
0x14011c6a0  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x14011c6a4  xor     r9d, r9d; NumberOfConcurrentThreads
0x14011c6a7  mov     [rbp+ObjectAttributes.ObjectName], r12
0x14011c6ab  mov     edx, 1F0003h; DesiredAccess
0x14011c6b0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14011c6b5  call    cs:__imp_ZwCreateIoCompletion
0x14011c6bc  nop     dword ptr [rax+rax+00h]
0x14011c6c1  mov     ebx, eax
0x14011c6c3  test    eax, eax
0x14011c6c5  js      loc_14011C84F
0x14011c6cb  mov     rcx, [r14]; Handle
0x14011c6ce  lea     rax, [rbp+arg_8]
0x14011c6d2  mov     [rsp+70h+HandleInformation], r12; HandleInformation
0x14011c6d7  xor     r9d, r9d; AccessMode
0x14011c6da  xor     r8d, r8d; ObjectType
0x14011c6dd  mov     [rsp+70h+Object], rax; Object
0x14011c6e2  mov     edx, 1F0003h; DesiredAccess
0x14011c6e7  mov     [rbp+arg_8], r12
0x14011c6eb  call    cs:__imp_ObReferenceObjectByHandle
0x14011c6f2  nop     dword ptr [rax+rax+00h]
0x14011c6f7  mov     ebx, eax
0x14011c6f9  mov     rax, [rbp+arg_8]
0x14011c6fd  mov     [rsi+648h], rax
0x14011c704  test    ebx, ebx
0x14011c706  js      loc_14011C854
0x14011c70c  mov     rdx, [r14]
0x14011c70f  lea     rdi, [rsi+658h]
0x14011c716  mov     byte ptr [rsp+70h+var_38], r12b
0x14011c71b  mov     r9, rdi
0x14011c71e  mov     dword ptr [rsp+70h+var_40], 2
0x14011c726  mov     r8, r15
0x14011c729  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x14011c72e  mov     rcx, r15
0x14011c731  mov     dword ptr [rsp+70h+Object], r12d
0x14011c736  call    cs:__imp_ObDuplicateObject
0x14011c73d  nop     dword ptr [rax+rax+00h]
0x14011c742  mov     ebx, eax
0x14011c744  test    eax, eax
0x14011c746  js      loc_14011C84A
0x14011c74c  mov     r15, [rdi]
0x14011c74f  lea     rax, [rbp+arg_10]
0x14011c753  mov     [rsp+70h+HandleInformation], rax; HandleInformation
0x14011c758  mov     r9b, 1; AccessMode
0x14011c75b  lea     rax, [rbp+arg_18]
0x14011c75f  mov     qword ptr [rbp+arg_10.HandleAttributes], r12
0x14011c763  xor     r8d, r8d; ObjectType
0x14011c766  mov     [rsp+70h+Object], rax; Object
0x14011c76b  mov     edx, 1F0003h; DesiredAccess
0x14011c770  mov     word ptr [rbp+arg_8], r12w
0x14011c775  mov     rcx, r15; Handle
0x14011c778  mov     [rbp+arg_18], r12
0x14011c77c  call    cs:__imp_ObReferenceObjectByHandle
0x14011c783  nop     dword ptr [rax+rax+00h]
0x14011c788  mov     ebx, eax
0x14011c78a  test    eax, eax
0x14011c78c  js      loc_14011C839
0x14011c792  mov     al, byte ptr [rbp+arg_10.HandleAttributes]
0x14011c795  lea     rdx, [rbp+arg_8]
0x14011c799  shr     al, 1
0x14011c79b  mov     r8b, 1
0x14011c79e  and     al, 1
0x14011c7a0  mov     byte ptr [rbp+arg_8+1], 1
0x14011c7a4  mov     rcx, r15
0x14011c7a7  mov     byte ptr [rbp+arg_8], al
0x14011c7aa  call    cs:__imp_ObSetHandleAttributes
0x14011c7b1  nop     dword ptr [rax+rax+00h]
0x14011c7b6  mov     rcx, [rbp+arg_18]; Object
0x14011c7ba  mov     ebx, eax
0x14011c7bc  call    cs:__imp_ObfDereferenceObject
0x14011c7c3  nop     dword ptr [rax+rax+00h]
0x14011c7c8  test    ebx, ebx
0x14011c7ca  js      short loc_14011C839
0x14011c7cc  lea     rdi, [rsi+668h]
0x14011c7d3  mov     rcx, rdi
0x14011c7d6  lea     r8, [rbp+ObjectAttributes]
0x14011c7da  lea     edx, [r12+1]
0x14011c7df  call    cs:__imp_ZwCreateWaitCompletionPacket
0x14011c7e6  nop     dword ptr [rax+rax+00h]
0x14011c7eb  mov     ebx, eax
0x14011c7ed  test    eax, eax
0x14011c7ef  js      short loc_14011C84A
0x14011c7f1  mov     r8, [rsi+660h]
0x14011c7f8  xor     r9d, r9d
0x14011c7fb  mov     rdx, [r14]
0x14011c7fe  mov     rcx, [rdi]
0x14011c801  mov     [rsp+70h+var_38], r12
0x14011c806  mov     [rsp+70h+var_40], r12
0x14011c80b  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x14011c810  mov     [rsp+70h+Object], 0FFFFFFFF80000000h
0x14011c819  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14011c820  nop     dword ptr [rax+rax+00h]
0x14011c825  mov     ebx, eax
0x14011c827  mov     eax, ebx
0x14011c829  add     rsp, 70h
0x14011c82d  pop     r15
0x14011c82f  pop     r14
0x14011c831  pop     r12
0x14011c833  pop     rdi
0x14011c834  pop     rsi
0x14011c835  pop     rbx
0x14011c836  pop     rbp
0x14011c837  retn
0x14011c839  mov     rcx, [rdi]; Handle
0x14011c83c  mov     dl, 1; PreviousMode
0x14011c83e  call    cs:__imp_ObCloseHandle
0x14011c845  nop     dword ptr [rax+rax+00h]
0x14011c84a  mov     [rdi], r12
0x14011c84d  jmp     short loc_14011C827
0x14011c84f  mov     [r14], r12
0x14011c852  jmp     short loc_14011C827
0x14011c854  mov     [rsi+648h], r12
0x14011c85b  jmp     short loc_14011C827
```
