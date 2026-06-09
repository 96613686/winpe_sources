# InitializeThreadInfoIocp(_EPROCESS *,tagTHREADINFO *)

- ea: `0x140120154`
- end: `0x14012034d`
- name: `?InitializeThreadInfoIocp@@YAJPEAU_EPROCESS@@PEAUtagTHREADINFO@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(struct _EPROCESS *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400d8314`

## callees

- `0x140120154`

## import_xrefs

- `ntoskrnl!ObSetHandleAttributes` at `0x14012029a`
- `ntoskrnl!ObSetHandleAttributes` at `0x14012029a`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x1401202cf`
- `ntoskrnl!ZwCreateWaitCompletionPacket` at `0x1401202cf`
- `ntoskrnl!ObCloseHandle` at `0x14012032e`
- `ntoskrnl!ObCloseHandle` at `0x14012032e`
- `ntoskrnl!ObDuplicateObject` at `0x140120226`
- `ntoskrnl!ObDuplicateObject` at `0x140120226`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401201db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14012026c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401201db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14012026c`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140120309`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140120309`
- `ntoskrnl!ZwCreateIoCompletion` at `0x1401201a5`
- `ntoskrnl!ZwCreateIoCompletion` at `0x1401201a5`
- `ntoskrnl!ObfDereferenceObject` at `0x1401202ac`
- `ntoskrnl!ObfDereferenceObject` at `0x1401202ac`

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
0x140120154  push    rbp
0x140120156  push    rbx
0x140120157  push    rsi
0x140120158  push    rdi
0x140120159  push    r12
0x14012015b  push    r14
0x14012015d  push    r15
0x14012015f  mov     rbp, rsp
0x140120162  sub     rsp, 70h
0x140120166  lea     r14, [rdx+650h]
0x14012016d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140120175  mov     rsi, rdx
0x140120178  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x140120180  mov     r15, rcx
0x140120183  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140120187  xor     r12d, r12d
0x14012018a  xorps   xmm0, xmm0
0x14012018d  mov     rcx, r14; IoCompletionHandle
0x140120190  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x140120194  xor     r9d, r9d; NumberOfConcurrentThreads
0x140120197  mov     [rbp+ObjectAttributes.ObjectName], r12
0x14012019b  mov     edx, 1F0003h; DesiredAccess
0x1401201a0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1401201a5  call    cs:__imp_ZwCreateIoCompletion
0x1401201ac  nop     dword ptr [rax+rax+00h]
0x1401201b1  mov     ebx, eax
0x1401201b3  test    eax, eax
0x1401201b5  js      loc_14012033F
0x1401201bb  mov     rcx, [r14]; Handle
0x1401201be  lea     rax, [rbp+arg_8]
0x1401201c2  mov     [rsp+70h+HandleInformation], r12; HandleInformation
0x1401201c7  xor     r9d, r9d; AccessMode
0x1401201ca  xor     r8d, r8d; ObjectType
0x1401201cd  mov     [rsp+70h+Object], rax; Object
0x1401201d2  mov     edx, 1F0003h; DesiredAccess
0x1401201d7  mov     [rbp+arg_8], r12
0x1401201db  call    cs:__imp_ObReferenceObjectByHandle
0x1401201e2  nop     dword ptr [rax+rax+00h]
0x1401201e7  mov     ebx, eax
0x1401201e9  mov     rax, [rbp+arg_8]
0x1401201ed  mov     [rsi+648h], rax
0x1401201f4  test    ebx, ebx
0x1401201f6  js      loc_140120344
0x1401201fc  mov     rdx, [r14]
0x1401201ff  lea     rdi, [rsi+658h]
0x140120206  mov     byte ptr [rsp+70h+var_38], r12b
0x14012020b  mov     r9, rdi
0x14012020e  mov     dword ptr [rsp+70h+var_40], 2
0x140120216  mov     r8, r15
0x140120219  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x14012021e  mov     rcx, r15
0x140120221  mov     dword ptr [rsp+70h+Object], r12d
0x140120226  call    cs:__imp_ObDuplicateObject
0x14012022d  nop     dword ptr [rax+rax+00h]
0x140120232  mov     ebx, eax
0x140120234  test    eax, eax
0x140120236  js      loc_14012033A
0x14012023c  mov     r15, [rdi]
0x14012023f  lea     rax, [rbp+arg_10]
0x140120243  mov     [rsp+70h+HandleInformation], rax; HandleInformation
0x140120248  mov     r9b, 1; AccessMode
0x14012024b  lea     rax, [rbp+arg_18]
0x14012024f  mov     qword ptr [rbp+arg_10.HandleAttributes], r12
0x140120253  xor     r8d, r8d; ObjectType
0x140120256  mov     [rsp+70h+Object], rax; Object
0x14012025b  mov     edx, 1F0003h; DesiredAccess
0x140120260  mov     word ptr [rbp+arg_8], r12w
0x140120265  mov     rcx, r15; Handle
0x140120268  mov     [rbp+arg_18], r12
0x14012026c  call    cs:__imp_ObReferenceObjectByHandle
0x140120273  nop     dword ptr [rax+rax+00h]
0x140120278  mov     ebx, eax
0x14012027a  test    eax, eax
0x14012027c  js      loc_140120329
0x140120282  mov     al, byte ptr [rbp+arg_10.HandleAttributes]
0x140120285  lea     rdx, [rbp+arg_8]
0x140120289  shr     al, 1
0x14012028b  mov     r8b, 1
0x14012028e  and     al, 1
0x140120290  mov     byte ptr [rbp+arg_8+1], 1
0x140120294  mov     rcx, r15
0x140120297  mov     byte ptr [rbp+arg_8], al
0x14012029a  call    cs:__imp_ObSetHandleAttributes
0x1401202a1  nop     dword ptr [rax+rax+00h]
0x1401202a6  mov     rcx, [rbp+arg_18]; Object
0x1401202aa  mov     ebx, eax
0x1401202ac  call    cs:__imp_ObfDereferenceObject
0x1401202b3  nop     dword ptr [rax+rax+00h]
0x1401202b8  test    ebx, ebx
0x1401202ba  js      short loc_140120329
0x1401202bc  lea     rdi, [rsi+668h]
0x1401202c3  mov     rcx, rdi
0x1401202c6  lea     r8, [rbp+ObjectAttributes]
0x1401202ca  lea     edx, [r12+1]
0x1401202cf  call    cs:__imp_ZwCreateWaitCompletionPacket
0x1401202d6  nop     dword ptr [rax+rax+00h]
0x1401202db  mov     ebx, eax
0x1401202dd  test    eax, eax
0x1401202df  js      short loc_14012033A
0x1401202e1  mov     r8, [rsi+660h]
0x1401202e8  xor     r9d, r9d
0x1401202eb  mov     rdx, [r14]
0x1401202ee  mov     rcx, [rdi]
0x1401202f1  mov     [rsp+70h+var_38], r12
0x1401202f6  mov     [rsp+70h+var_40], r12
0x1401202fb  mov     dword ptr [rsp+70h+HandleInformation], r12d
0x140120300  mov     [rsp+70h+Object], 0FFFFFFFF80000000h
0x140120309  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x140120310  nop     dword ptr [rax+rax+00h]
0x140120315  mov     ebx, eax
0x140120317  mov     eax, ebx
0x140120319  add     rsp, 70h
0x14012031d  pop     r15
0x14012031f  pop     r14
0x140120321  pop     r12
0x140120323  pop     rdi
0x140120324  pop     rsi
0x140120325  pop     rbx
0x140120326  pop     rbp
0x140120327  retn
0x140120329  mov     rcx, [rdi]; Handle
0x14012032c  mov     dl, 1; PreviousMode
0x14012032e  call    cs:__imp_ObCloseHandle
0x140120335  nop     dword ptr [rax+rax+00h]
0x14012033a  mov     [rdi], r12
0x14012033d  jmp     short loc_140120317
0x14012033f  mov     [r14], r12
0x140120342  jmp     short loc_140120317
0x140120344  mov     [rsi+648h], r12
0x14012034b  jmp     short loc_140120317
```
