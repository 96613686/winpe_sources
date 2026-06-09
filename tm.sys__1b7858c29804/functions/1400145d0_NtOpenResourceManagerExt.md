# NtOpenResourceManagerExt

- ea: `0x1400145d0`
- end: `0x1400147cb`
- name: `NtOpenResourceManagerExt`
- size: `507`
- prototype: `NTSTATUS __stdcall(PHANDLE ResourceManagerHandle, ACCESS_MASK DesiredAccess, HANDLE TmHandle, LPGUID ResourceManagerGuid, POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400014d4`
- `0x140002128`
- `0x1400024e0`
- `0x14000d1fc`
- `0x14000d274`
- `0x1400145d0`
- `0x140019a5c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140014780`
- `ntoskrnl!ObfDereferenceObject` at `0x140014796`
- `ntoskrnl!ObfDereferenceObject` at `0x140022367`
- `ntoskrnl!ObfDereferenceObject` at `0x14002237d`
- `ntoskrnl!ObfDereferenceObject` at `0x140014780`
- `ntoskrnl!ObfDereferenceObject` at `0x140014796`
- `ntoskrnl!ObfDereferenceObject` at `0x140022367`
- `ntoskrnl!ObfDereferenceObject` at `0x14002237d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001474d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001474d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400146d0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400146d0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022324`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022341`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022324`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022341`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140014668`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140014668`

## pseudocode

```c
NTSTATUS __stdcall NtOpenResourceManagerExt(
        PHANDLE ResourceManagerHandle,
        ACCESS_MASK DesiredAccess,
        HANDLE TmHandle,
        LPGUID ResourceManagerGuid,
        POBJECT_ATTRIBUTES ObjectAttributes)
{
  ULONG Attributes; // r12d
  KPROCESSOR_MODE v10; // r14
  __int64 ULong64FromUser; // rax
  int ResourceManagerTm; // edi
  PVOID v13; // rsi
  __int64 v14; // rcx
  PVOID v16; // [rsp+48h] [rbp-70h] BYREF
  PVOID v17; // [rsp+50h] [rbp-68h]
  PVOID Object; // [rsp+58h] [rbp-60h] BYREF
  void *Handle; // [rsp+60h] [rbp-58h] BYREF
  GUID v20; // [rsp+68h] [rbp-50h] BYREF

  Handle = 0;
  v16 = 0;
  v20 = 0;
  if ( !DesiredAccess || !ResourceManagerGuid )
    return -1073741811;
  v17 = 0;
  Attributes = 0;
  v10 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v10 )
  {
    ULong64FromUser = RtlReadULong64FromUser(ResourceManagerHandle);
    RtlWriteULong64ToUser(ResourceManagerHandle, ULong64FromUser);
    if ( ((unsigned __int8)ResourceManagerGuid & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v20, ResourceManagerGuid, 0x10u);
  }
  else
  {
    v20 = *ResourceManagerGuid;
    if ( ObjectAttributes )
      Attributes = ObjectAttributes->Attributes;
  }
  Object = 0;
  ResourceManagerTm = ObReferenceObjectByHandle(
                        TmHandle,
                        1u,
                        (POBJECT_TYPE)TmTransactionManagerObjectType,
                        v10,
                        &Object,
                        0);
  v13 = Object;
  v17 = Object;
  if ( ResourceManagerTm >= 0 )
  {
    if ( (unsigned __int8)TmpIsOnlineTransactionManager(Object) )
    {
      ResourceManagerTm = TmpFindResourceManagerTm(v14, &v20, &v16);
      if ( ResourceManagerTm >= 0 )
      {
        ResourceManagerTm = ObOpenObjectByPointer(
                              v16,
                              Attributes,
                              0,
                              DesiredAccess,
                              (POBJECT_TYPE)TmResourceManagerObjectType,
                              v10,
                              &Handle);
        if ( ResourceManagerTm >= 0 )
          *ResourceManagerHandle = Handle;
      }
    }
    else
    {
      ResourceManagerTm = -1072103342;
    }
  }
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( v16 )
    ObfDereferenceObject(v16);
  return ResourceManagerTm;
}

```

## disassembly

```asm
0x1400145d0  push    rsi
0x1400145d2  push    rdi
0x1400145d3  push    r12
0x1400145d5  push    r13
0x1400145d7  push    r14
0x1400145d9  push    r15
0x1400145db  sub     rsp, 88h
0x1400145e2  mov     rax, cs:__security_cookie
0x1400145e9  xor     rax, rsp
0x1400145ec  mov     [rsp+0B8h+var_40], rax
0x1400145f1  mov     rdi, r9
0x1400145f4  mov     rsi, r8
0x1400145f7  mov     r13d, edx
0x1400145fa  mov     r15, rcx
0x1400145fd  mov     rdx, [rsp+0B8h+ObjectAttributes]
0x140014605  mov     [rsp+0B8h+var_58], 0
0x14001460e  mov     [rsp+0B8h+var_70], 0
0x140014617  xorps   xmm0, xmm0
0x14001461a  movups  [rsp+0B8h+var_50], xmm0
0x14001461f  test    r13d, r13d
0x140014622  jz      loc_1400147A6
0x140014628  test    r9, r9
0x14001462b  jz      loc_1400147A6
0x140014631  mov     [rsp+0B8h+var_68], 0
0x14001463a  xor     r12d, r12d
0x14001463d  mov     rax, gs:188h
0x140014646  mov     r14b, [rax+232h]
0x14001464d  test    r14b, r14b
0x140014650  jz      short loc_14001468F
0x140014652  call    RtlReadULong64FromUser
0x140014657  mov     rdx, rax
0x14001465a  mov     rcx, r15
0x14001465d  call    RtlWriteULong64ToUser
0x140014662  test    dil, 3
0x140014666  jz      short loc_140014675
0x140014668  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001466f  nop     dword ptr [rax+rax+00h]
0x140014674  int     3; Trap to Debugger
0x140014675  mov     r8d, 10h; Size
0x14001467b  mov     rdx, rdi; Src
0x14001467e  lea     rcx, [rsp+0B8h+var_50]; void *
0x140014683  call    RtlCopyFromUser
0x140014688  jmp     short loc_1400146A2
0x14001468a  jmp     loc_1400147AB
0x14001468f  movups  xmm0, xmmword ptr [r9]
0x140014693  movdqu  [rsp+0B8h+var_50], xmm0
0x140014699  test    rdx, rdx
0x14001469c  jz      short loc_1400146A2
0x14001469e  mov     r12d, [rdx+18h]
0x1400146a2  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x1400146a9  mov     [rsp+0B8h+var_60], 0
0x1400146b2  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x1400146bb  lea     rax, [rsp+0B8h+var_60]
0x1400146c0  mov     [rsp+0B8h+Object], rax; Object
0x1400146c5  mov     r9b, r14b; AccessMode
0x1400146c8  mov     edx, 1; DesiredAccess
0x1400146cd  mov     rcx, rsi; Handle
0x1400146d0  call    cs:__imp_ObReferenceObjectByHandle
0x1400146d7  nop     dword ptr [rax+rax+00h]
0x1400146dc  mov     edi, eax
0x1400146de  mov     rsi, [rsp+0B8h+var_60]
0x1400146e3  mov     [rsp+0B8h+var_68], rsi
0x1400146e8  mov     [rsp+0B8h+var_78], eax
0x1400146ec  test    eax, eax
0x1400146ee  js      loc_140014778
0x1400146f4  mov     rcx, rsi
0x1400146f7  call    TmpIsOnlineTransactionManager
0x1400146fc  test    al, al
0x1400146fe  jnz     short loc_14001470B
0x140014700  mov     edi, 0C0190052h
0x140014705  mov     [rsp+0B8h+var_78], edi
0x140014709  jmp     short loc_140014778
0x14001470b  lea     r8, [rsp+0B8h+var_70]
0x140014710  lea     rdx, [rsp+0B8h+var_50]
0x140014715  call    TmpFindResourceManagerTm
0x14001471a  mov     edi, eax
0x14001471c  mov     [rsp+0B8h+var_78], eax
0x140014720  test    eax, eax
0x140014722  js      short loc_140014778
0x140014724  lea     rax, [rsp+0B8h+var_58]
0x140014729  mov     [rsp+0B8h+Handle], rax; Handle
0x14001472e  mov     byte ptr [rsp+0B8h+HandleInformation], r14b; AccessMode
0x140014733  mov     rax, cs:TmResourceManagerObjectType
0x14001473a  mov     [rsp+0B8h+Object], rax; ObjectType
0x14001473f  mov     r9d, r13d; DesiredAccess
0x140014742  xor     r8d, r8d; PassedAccessState
0x140014745  mov     edx, r12d; HandleAttributes
0x140014748  mov     rcx, [rsp+0B8h+var_70]; Object
0x14001474d  call    cs:__imp_ObOpenObjectByPointer
0x140014754  nop     dword ptr [rax+rax+00h]
0x140014759  mov     edi, eax
0x14001475b  mov     [rsp+0B8h+var_78], eax
0x14001475f  test    eax, eax
0x140014761  js      short loc_140014778
0x140014763  mov     rax, [rsp+0B8h+var_58]
0x140014768  mov     [r15], rax
0x14001476b  jmp     short loc_140014778
0x14001476d  mov     edi, eax
0x14001476f  mov     [rsp+0B8h+var_78], eax
0x140014773  mov     rsi, [rsp+0B8h+var_68]
0x140014778  test    rsi, rsi
0x14001477b  jz      short loc_14001478C
0x14001477d  mov     rcx, rsi; Object
0x140014780  call    cs:__imp_ObfDereferenceObject
0x140014787  nop     dword ptr [rax+rax+00h]
0x14001478c  mov     rcx, [rsp+0B8h+var_70]; Object
0x140014791  test    rcx, rcx
0x140014794  jz      short loc_1400147A2
0x140014796  call    cs:__imp_ObfDereferenceObject
0x14001479d  nop     dword ptr [rax+rax+00h]
0x1400147a2  mov     eax, edi
0x1400147a4  jmp     short loc_1400147AB
0x1400147a6  mov     eax, 0C000000Dh
0x1400147ab  mov     rcx, [rsp+0B8h+var_40]
0x1400147b0  xor     rcx, rsp; StackCookie
0x1400147b3  call    __security_check_cookie
0x1400147b8  add     rsp, 88h
0x1400147bf  pop     r15
0x1400147c1  pop     r14
0x1400147c3  pop     r13
0x1400147c5  pop     r12
0x1400147c7  pop     rdi
0x1400147c8  pop     rsi
0x1400147c9  retn
0x14002231b  push    rbp
0x14002231d  sub     rsp, 40h
0x140022321  mov     rbp, rdx
0x140022324  call    cs:__imp_ExSystemExceptionFilter
0x14002232b  nop     dword ptr [rax+rax+00h]
0x140022330  nop
0x140022331  add     rsp, 40h
0x140022335  pop     rbp
0x140022336  retn
0x140022338  push    rbp
0x14002233a  sub     rsp, 40h
0x14002233e  mov     rbp, rdx
0x140022341  call    cs:__imp_ExSystemExceptionFilter
0x140022348  nop     dword ptr [rax+rax+00h]
0x14002234d  nop
0x14002234e  add     rsp, 40h
0x140022352  pop     rbp
0x140022353  retn
0x140022355  push    rbp
0x140022357  sub     rsp, 40h
0x14002235b  mov     rbp, rdx
0x14002235e  mov     rcx, [rbp+50h]; Object
0x140022362  test    rcx, rcx
0x140022365  jz      short loc_140022374
0x140022367  call    cs:__imp_ObfDereferenceObject
0x14002236e  nop     dword ptr [rax+rax+00h]
0x140022373  nop
0x140022374  mov     rcx, [rbp+48h]; Object
0x140022378  test    rcx, rcx
0x14002237b  jz      short loc_14002238A
0x14002237d  call    cs:__imp_ObfDereferenceObject
0x140022384  nop     dword ptr [rax+rax+00h]
0x140022389  nop
0x14002238a  add     rsp, 40h
0x14002238e  pop     rbp
0x14002238f  retn
```
