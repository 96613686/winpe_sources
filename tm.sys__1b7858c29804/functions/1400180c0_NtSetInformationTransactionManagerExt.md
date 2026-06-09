# NtSetInformationTransactionManagerExt

- ea: `0x1400180c0`
- end: `0x1400181ad`
- name: `NtSetInformationTransactionManagerExt`
- size: `237`
- prototype: `NTSTATUS __stdcall(HANDLE TmHandle, TRANSACTIONMANAGER_INFORMATION_CLASS TransactionManagerInformationClass, PVOID TransactionManagerInformation, ULONG TransactionManagerInformationLength)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140016340`
- `0x1400180c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140018194`
- `ntoskrnl!ObfDereferenceObject` at `0x140018194`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140018170`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140018170`
- `ntoskrnl!ProbeForRead` at `0x140018132`
- `ntoskrnl!ProbeForRead` at `0x140018132`
- `ntoskrnl!PsIsComponentEnabled` at `0x1400180da`
- `ntoskrnl!PsIsComponentEnabled` at `0x1400180da`

## pseudocode

```c
NTSTATUS __stdcall NtSetInformationTransactionManagerExt(
        HANDLE TmHandle,
        TRANSACTIONMANAGER_INFORMATION_CLASS TransactionManagerInformationClass,
        PVOID TransactionManagerInformation,
        ULONG TransactionManagerInformationLength)
{
  SIZE_T v4; // rbx
  KPROCESSOR_MODE v9; // di
  int IsLogWritableTransactionManager; // edi
  PVOID v11; // rbx
  PVOID Object; // [rsp+30h] [rbp-38h] BYREF

  v4 = TransactionManagerInformationLength;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  if ( TransactionManagerInformationClass != (TransactionManagerLogPathInformation|TransactionManagerLogInformation) )
    return -1073741821;
  if ( (_DWORD)v4 )
    return -1073741820;
  v9 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v9 )
    ProbeForRead(TransactionManagerInformation, v4, 4u);
  Object = 0;
  IsLogWritableTransactionManager = ObReferenceObjectByHandle(
                                      TmHandle,
                                      2u,
                                      (POBJECT_TYPE)TmTransactionManagerObjectType,
                                      v9,
                                      &Object,
                                      0);
  if ( IsLogWritableTransactionManager >= 0 )
  {
    v11 = Object;
    IsLogWritableTransactionManager = TmpIsLogWritableTransactionManager(Object);
    ObfDereferenceObject(v11);
  }
  return IsLogWritableTransactionManager;
}

```

## disassembly

```asm
0x1400180c0  push    rbx
0x1400180c2  push    rsi
0x1400180c3  push    rdi
0x1400180c4  push    r14
0x1400180c6  sub     rsp, 48h
0x1400180ca  mov     ebx, r9d
0x1400180cd  mov     rsi, r8
0x1400180d0  mov     edi, edx
0x1400180d2  mov     r14, rcx
0x1400180d5  mov     ecx, 1
0x1400180da  call    cs:__imp_PsIsComponentEnabled
0x1400180e1  nop     dword ptr [rax+rax+00h]
0x1400180e6  test    al, al
0x1400180e8  jnz     short loc_1400180F4
0x1400180ea  mov     eax, 0C0000022h
0x1400180ef  jmp     loc_1400181A2
0x1400180f4  cmp     edi, 3
0x1400180f7  jz      short loc_140018103
0x1400180f9  mov     eax, 0C0000003h
0x1400180fe  jmp     loc_1400181A2
0x140018103  test    ebx, ebx
0x140018105  jz      short loc_140018111
0x140018107  mov     eax, 0C0000004h
0x14001810c  jmp     loc_1400181A2
0x140018111  mov     rax, gs:188h
0x14001811a  mov     dil, [rax+232h]
0x140018121  test    dil, dil
0x140018124  jz      short loc_140018142
0x140018126  mov     rdx, rbx; Length
0x140018129  mov     r8d, 4; Alignment
0x14001812f  mov     rcx, rsi; Address
0x140018132  call    cs:__imp_ProbeForRead
0x140018139  nop     dword ptr [rax+rax+00h]
0x14001813e  jmp     short loc_140018142
0x140018140  jmp     short loc_1400181A2
0x140018142  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x140018149  mov     [rsp+68h+var_38], 0
0x140018152  mov     [rsp+68h+HandleInformation], 0; HandleInformation
0x14001815b  lea     rax, [rsp+68h+var_38]
0x140018160  mov     [rsp+68h+Object], rax; Object
0x140018165  mov     r9b, dil; AccessMode
0x140018168  mov     edx, 2; DesiredAccess
0x14001816d  mov     rcx, r14; Handle
0x140018170  call    cs:__imp_ObReferenceObjectByHandle
0x140018177  nop     dword ptr [rax+rax+00h]
0x14001817c  mov     edi, eax
0x14001817e  test    eax, eax
0x140018180  js      short loc_1400181A0
0x140018182  mov     rbx, [rsp+68h+var_38]
0x140018187  mov     rcx, rbx
0x14001818a  call    TmpIsLogWritableTransactionManager
0x14001818f  mov     edi, eax
0x140018191  mov     rcx, rbx; Object
0x140018194  call    cs:__imp_ObfDereferenceObject
0x14001819b  nop     dword ptr [rax+rax+00h]
0x1400181a0  mov     eax, edi
0x1400181a2  add     rsp, 48h
0x1400181a6  pop     r14
0x1400181a8  pop     rdi
0x1400181a9  pop     rsi
0x1400181aa  pop     rbx
0x1400181ab  retn
0x140022033  push    rbp
0x140022035  sub     rsp, 30h
0x140022039  mov     rbp, rdx
0x14002203c  call    cs:__imp_ExSystemExceptionFilter
0x140022043  nop     dword ptr [rax+rax+00h]
0x140022048  nop
0x140022049  add     rsp, 30h
0x14002204d  pop     rbp
0x14002204e  retn
```
