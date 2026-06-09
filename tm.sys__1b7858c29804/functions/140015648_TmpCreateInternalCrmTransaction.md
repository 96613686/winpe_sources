# TmpCreateInternalCrmTransaction

- ea: `0x140015648`
- end: `0x14001590b`
- name: `TmpCreateInternalCrmTransaction`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400114ac`
- `0x140015c8c`

## callees

- `0x1400024e0`
- `0x14000c584`
- `0x140015648`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400158c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400225f7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400158c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400225f7`
- `ntoskrnl!ZwClose` at `0x140015888`
- `ntoskrnl!ZwClose` at `0x1400158a9`
- `ntoskrnl!ZwClose` at `0x1400225b7`
- `ntoskrnl!ZwClose` at `0x1400225da`
- `ntoskrnl!ZwClose` at `0x140015888`
- `ntoskrnl!ZwClose` at `0x1400158a9`
- `ntoskrnl!ZwClose` at `0x1400225b7`
- `ntoskrnl!ZwClose` at `0x1400225da`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001570e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001570e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140015815`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140015815`
- `ntoskrnl!ZwCreateTransaction` at `0x1400157da`
- `ntoskrnl!ZwCreateTransaction` at `0x1400157da`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400156c7`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400156c7`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140015872`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400225a1`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140015872`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400225a1`
- `ntoskrnl!ExUuidCreate` at `0x140015772`
- `ntoskrnl!ExUuidCreate` at `0x140015772`

## pseudocode

```c
__int64 __fastcall TmpCreateInternalCrmTransaction(__int64 a1, char a2, __int64 a3, _QWORD *a4, void **a5)
{
  PVOID v9; // rdi
  NTSTATUS ObjectSecurity; // ebx
  UNICODE_STRING *Description; // rcx
  unsigned __int8 MemoryAllocated[4]; // [rsp+50h] [rbp-B8h] BYREF
  NTSTATUS v14; // [rsp+54h] [rbp-B4h]
  void *TransactionHandle; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE TmHandle; // [rsp+60h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-A0h] BYREF
  PVOID v18; // [rsp+70h] [rbp-98h]
  PVOID Object; // [rsp+78h] [rbp-90h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-88h] BYREF
  UUID Uuid; // [rsp+B0h] [rbp-58h] BYREF

  memset(&ObjectAttributes, 0, 44);
  TmHandle = 0;
  v14 = 0;
  SecurityDescriptor = 0;
  Uuid = 0;
  MemoryAllocated[0] = 0;
  v9 = 0;
  v18 = 0;
  TransactionHandle = 0;
  ObjectSecurity = ObGetObjectSecurity((PVOID)a1, &SecurityDescriptor, MemoryAllocated);
  v14 = ObjectSecurity;
  if ( ObjectSecurity >= 0 )
  {
    ObjectSecurity = ObOpenObjectByPointer(
                       (PVOID)a3,
                       0x200u,
                       0,
                       0xF003Fu,
                       (POBJECT_TYPE)TmTransactionManagerObjectType,
                       0,
                       &TmHandle);
    v14 = ObjectSecurity;
    if ( ObjectSecurity >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      if ( a2 )
        ExUuidCreate(&Uuid);
      else
        Uuid = *(UUID *)(a1 + 176);
      Description = (UNICODE_STRING *)(a1 + 304);
      if ( !*(_WORD *)(a1 + 304) )
        Description = 0;
      ObjectSecurity = ZwCreateTransaction(
                         &TransactionHandle,
                         0x1F003Fu,
                         &ObjectAttributes,
                         &Uuid,
                         TmHandle,
                         0,
                         0,
                         0,
                         0,
                         Description);
      v14 = ObjectSecurity;
      if ( ObjectSecurity >= 0 )
      {
        Object = 0;
        ObjectSecurity = ObReferenceObjectByHandle(
                           TransactionHandle,
                           0,
                           (POBJECT_TYPE)TmTransactionObjectType,
                           0,
                           &Object,
                           0);
        v9 = Object;
        v18 = Object;
        v14 = ObjectSecurity;
        if ( ObjectSecurity >= 0 )
        {
          *((_QWORD *)Object + 86) = TransactionHandle;
          if ( a2 )
          {
            TmpNamespaceReplace((PRTL_AVL_TABLE)(a3 + 176), (PVOID)a3);
            *(_QWORD *)(a1 + 512) = 0;
          }
        }
      }
    }
  }
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
  if ( TmHandle )
  {
    ZwClose(TmHandle);
    TmHandle = 0;
  }
  if ( ObjectSecurity >= 0 )
  {
    *a5 = TransactionHandle;
    *a4 = v9;
  }
  else
  {
    if ( TransactionHandle )
    {
      ZwClose(TransactionHandle);
      TransactionHandle = 0;
    }
    if ( v9 )
      ObfDereferenceObject(v9);
  }
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x140015648  mov     r11, rsp
0x14001564b  push    rbx
0x14001564c  push    rsi
0x14001564d  push    rdi
0x14001564e  push    r12
0x140015650  push    r13
0x140015652  push    r14
0x140015654  push    r15
0x140015656  sub     rsp, 0D0h
0x14001565d  mov     rax, cs:__security_cookie
0x140015664  xor     rax, rsp
0x140015667  mov     [rsp+108h+var_48], rax
0x14001566f  mov     r12, r9
0x140015672  mov     r14, r8
0x140015675  mov     r15b, dl
0x140015678  mov     rsi, rcx
0x14001567b  mov     r13, [rsp+108h+arg_20]
0x140015683  xor     eax, eax
0x140015685  xorps   xmm0, xmm0
0x140015688  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x140015690  movups  xmmword ptr [r11-78h], xmm0
0x140015695  movups  xmmword ptr [r11-6Ch], xmm0
0x14001569a  mov     [rsp+108h+TmHandle], rax
0x14001569f  mov     [rsp+108h+var_B4], eax
0x1400156a3  mov     [rsp+108h+SecurityDescriptor], rax
0x1400156a8  movups  xmmword ptr [r11-58h], xmm0
0x1400156ad  mov     [rsp+108h+MemoryAllocated], al
0x1400156b1  mov     edi, eax
0x1400156b3  mov     [rsp+108h+var_98], rax
0x1400156b8  mov     [rsp+108h+TransactionHandle], rax
0x1400156bd  lea     r8, [rsp+108h+MemoryAllocated]; MemoryAllocated
0x1400156c2  lea     rdx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x1400156c7  call    cs:__imp_ObGetObjectSecurity
0x1400156ce  nop     dword ptr [rax+rax+00h]
0x1400156d3  mov     ebx, eax
0x1400156d5  mov     [rsp+108h+var_B4], eax
0x1400156d9  xor     edx, edx
0x1400156db  test    eax, eax
0x1400156dd  js      loc_140015864
0x1400156e3  lea     rax, [rsp+108h+TmHandle]
0x1400156e8  mov     [rsp+108h+Handle], rax; Handle
0x1400156ed  mov     [rsp+108h+AccessMode], dl; AccessMode
0x1400156f1  mov     rax, cs:TmTransactionManagerObjectType
0x1400156f8  mov     [rsp+108h+ObjectType], rax; ObjectType
0x1400156fd  mov     r9d, 0F003Fh; DesiredAccess
0x140015703  xor     r8d, r8d; PassedAccessState
0x140015706  mov     edx, 200h; HandleAttributes
0x14001570b  mov     rcx, r14; Object
0x14001570e  call    cs:__imp_ObOpenObjectByPointer
0x140015715  nop     dword ptr [rax+rax+00h]
0x14001571a  mov     ebx, eax
0x14001571c  mov     [rsp+108h+var_B4], eax
0x140015720  xor     edx, edx
0x140015722  test    eax, eax
0x140015724  js      loc_140015864
0x14001572a  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x140015735  mov     [rsp+108h+ObjectAttributes.RootDirectory], rdx
0x14001573d  mov     [rsp+108h+ObjectAttributes.Attributes], 200h
0x140015748  mov     [rsp+108h+ObjectAttributes.ObjectName], rdx
0x140015750  mov     rax, [rsp+108h+SecurityDescriptor]
0x140015755  mov     [rsp+108h+ObjectAttributes.SecurityDescriptor], rax
0x14001575d  mov     [rsp+108h+ObjectAttributes.SecurityQualityOfService], rdx
0x140015765  test    r15b, r15b
0x140015768  jz      short loc_140015782
0x14001576a  lea     rcx, [rsp+108h+Uuid]; Uuid
0x140015772  call    cs:__imp_ExUuidCreate
0x140015779  nop     dword ptr [rax+rax+00h]
0x14001577e  xor     edx, edx
0x140015780  jmp     short loc_140015792
0x140015782  movups  xmm0, xmmword ptr [rsi+0B0h]
0x140015789  movdqu  xmmword ptr [rsp+108h+Uuid.Data1], xmm0
0x140015792  lea     rcx, [rsi+130h]
0x140015799  cmp     [rcx], dx
0x14001579c  cmovbe  rcx, rdx
0x1400157a0  mov     [rsp+108h+Description], rcx; Description
0x1400157a5  mov     [rsp+108h+Timeout], rdx; Timeout
0x1400157aa  mov     [rsp+108h+IsolationFlags], edx; IsolationFlags
0x1400157ae  mov     dword ptr [rsp+108h+Handle], edx; IsolationLevel
0x1400157b2  mov     dword ptr [rsp+108h+AccessMode], edx; CreateOptions
0x1400157b6  mov     rax, [rsp+108h+TmHandle]
0x1400157bb  mov     [rsp+108h+ObjectType], rax; TmHandle
0x1400157c0  lea     r9, [rsp+108h+Uuid]; Uow
0x1400157c8  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x1400157d0  mov     edx, 1F003Fh; DesiredAccess
0x1400157d5  lea     rcx, [rsp+108h+TransactionHandle]; TransactionHandle
0x1400157da  call    cs:__imp_ZwCreateTransaction
0x1400157e1  nop     dword ptr [rax+rax+00h]
0x1400157e6  mov     ebx, eax
0x1400157e8  mov     [rsp+108h+var_B4], eax
0x1400157ec  xor     edx, edx; DesiredAccess
0x1400157ee  test    eax, eax
0x1400157f0  js      short loc_140015864
0x1400157f2  mov     r8, cs:TmTransactionObjectType; ObjectType
0x1400157f9  mov     [rsp+108h+Object], rdx
0x1400157fe  mov     qword ptr [rsp+108h+AccessMode], rdx; HandleInformation
0x140015803  lea     rax, [rsp+108h+Object]
0x140015808  mov     [rsp+108h+ObjectType], rax; Object
0x14001580d  xor     r9d, r9d; AccessMode
0x140015810  mov     rcx, [rsp+108h+TransactionHandle]; Handle
0x140015815  call    cs:__imp_ObReferenceObjectByHandle
0x14001581c  nop     dword ptr [rax+rax+00h]
0x140015821  mov     ebx, eax
0x140015823  mov     rdi, [rsp+108h+Object]
0x140015828  mov     [rsp+108h+var_98], rdi
0x14001582d  mov     [rsp+108h+var_B4], eax
0x140015831  test    eax, eax
0x140015833  js      short loc_140015864
0x140015835  mov     rax, [rsp+108h+TransactionHandle]
0x14001583a  mov     [rdi+2B0h], rax
0x140015841  test    r15b, r15b
0x140015844  jz      short loc_140015864
0x140015846  lea     rcx, [r14+0B0h]; Table
0x14001584d  mov     r9, rdi
0x140015850  mov     r8, rsi
0x140015853  mov     rdx, r14; Object
0x140015856  call    TmpNamespaceReplace
0x14001585b  xor     edx, edx
0x14001585d  mov     [rsi+200h], rdx
0x140015864  mov     rcx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x140015869  test    rcx, rcx
0x14001586c  jz      short loc_14001587E
0x14001586e  mov     dl, [rsp+108h+MemoryAllocated]; MemoryAllocated
0x140015872  call    cs:__imp_ObReleaseObjectSecurity
0x140015879  nop     dword ptr [rax+rax+00h]
0x14001587e  mov     rcx, [rsp+108h+TmHandle]; Handle
0x140015883  test    rcx, rcx
0x140015886  jz      short loc_14001589B
0x140015888  call    cs:__imp_ZwClose
0x14001588f  nop     dword ptr [rax+rax+00h]
0x140015894  xor     edx, edx
0x140015896  mov     [rsp+108h+TmHandle], rdx
0x14001589b  test    ebx, ebx
0x14001589d  jns     short loc_1400158D8
0x14001589f  mov     rcx, [rsp+108h+TransactionHandle]; Handle
0x1400158a4  test    rcx, rcx
0x1400158a7  jz      short loc_1400158BC
0x1400158a9  call    cs:__imp_ZwClose
0x1400158b0  nop     dword ptr [rax+rax+00h]
0x1400158b5  xor     edx, edx
0x1400158b7  mov     [rsp+108h+TransactionHandle], rdx
0x1400158bc  test    rdi, rdi
0x1400158bf  jz      short loc_1400158D4
0x1400158c1  mov     rcx, rdi; Object
0x1400158c4  call    cs:__imp_ObfDereferenceObject
0x1400158cb  nop     dword ptr [rax+rax+00h]
0x1400158d0  xor     edx, edx
0x1400158d2  mov     edi, edx
0x1400158d4  test    ebx, ebx
0x1400158d6  js      short loc_1400158E5
0x1400158d8  mov     rax, [rsp+108h+TransactionHandle]
0x1400158dd  mov     [r13+0], rax
0x1400158e1  mov     [r12], rdi
0x1400158e5  mov     eax, ebx
0x1400158e7  mov     rcx, [rsp+108h+var_48]
0x1400158ef  xor     rcx, rsp; StackCookie
0x1400158f2  call    __security_check_cookie
0x1400158f7  add     rsp, 0D0h
0x1400158fe  pop     r15
0x140015900  pop     r14
0x140015902  pop     r13
0x140015904  pop     r12
0x140015906  pop     rdi
0x140015907  pop     rsi
0x140015908  pop     rbx
0x140015909  retn
0x14002258c  push    rbp
0x14002258e  sub     rsp, 50h
0x140022592  mov     rbp, rdx
0x140022595  mov     rcx, [rbp+68h]; SecurityDescriptor
0x140022599  test    rcx, rcx
0x14002259c  jz      short loc_1400225AE
0x14002259e  mov     dl, [rbp+50h]; MemoryAllocated
0x1400225a1  call    cs:__imp_ObReleaseObjectSecurity
0x1400225a8  nop     dword ptr [rax+rax+00h]
0x1400225ad  nop
0x1400225ae  mov     rcx, [rbp+60h]; Handle
0x1400225b2  test    rcx, rcx
0x1400225b5  jz      short loc_1400225CB
0x1400225b7  call    cs:__imp_ZwClose
0x1400225be  nop     dword ptr [rax+rax+00h]
0x1400225c3  mov     qword ptr [rbp+60h], 0
0x1400225cb  cmp     dword ptr [rbp+54h], 0
0x1400225cf  jge     short loc_14002260B
0x1400225d1  mov     rcx, [rbp+58h]; Handle
0x1400225d5  test    rcx, rcx
0x1400225d8  jz      short loc_1400225EE
0x1400225da  call    cs:__imp_ZwClose
0x1400225e1  nop     dword ptr [rax+rax+00h]
0x1400225e6  mov     qword ptr [rbp+58h], 0
0x1400225ee  mov     rcx, [rbp+70h]; Object
0x1400225f2  test    rcx, rcx
0x1400225f5  jz      short loc_14002260B
0x1400225f7  call    cs:__imp_ObfDereferenceObject
0x1400225fe  nop     dword ptr [rax+rax+00h]
0x140022603  mov     qword ptr [rbp+70h], 0
0x14002260b  add     rsp, 50h
0x14002260f  pop     rbp
0x140022610  retn
```
