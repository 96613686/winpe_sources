# TmCreateEnlistmentExt

- ea: `0x14001a870`
- end: `0x14001aa83`
- name: `TmCreateEnlistmentExt`
- size: `531`
- prototype: `NTSTATUS __stdcall(PHANDLE EnlistmentHandle, KPROCESSOR_MODE PreviousMode, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PRKRESOURCEMANAGER ResourceManager, PKTRANSACTION Transaction, ULONG CreateOptions, NOTIFICATION_MASK NotificationMask, PVOID EnlistmentKey)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012e50`

## callees

- `0x1400024e0`
- `0x1400025c0`
- `0x14000d274`
- `0x14001a870`
- `0x14001ab8c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001a997`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a997`
- `ntoskrnl!ObfReferenceObject` at `0x14001a9aa`
- `ntoskrnl!ObfReferenceObject` at `0x14001a9aa`
- `ntoskrnl!ExUuidCreate` at `0x14001a94e`
- `ntoskrnl!ExUuidCreate` at `0x14001a94e`
- `ntoskrnl!ObCreateObject` at `0x14001a925`
- `ntoskrnl!ObCreateObject` at `0x14001a925`
- `ntoskrnl!ObInsertObject` at `0x14001a9d6`
- `ntoskrnl!ObInsertObject` at `0x14001a9d6`
- `ntoskrnl!ObCloseHandle` at `0x14001aa1f`
- `ntoskrnl!ObCloseHandle` at `0x14001aa1f`

## pseudocode

```c
NTSTATUS __stdcall TmCreateEnlistmentExt(
        PHANDLE EnlistmentHandle,
        KPROCESSOR_MODE PreviousMode,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PRKRESOURCEMANAGER ResourceManager,
        PKTRANSACTION Transaction,
        ULONG CreateOptions,
        NOTIFICATION_MASK NotificationMask,
        PVOID EnlistmentKey)
{
  POBJECT_ATTRIBUTES v9; // r10
  __int64 v13; // rcx
  int Object; // ebx
  HANDLE Handle; // [rsp+70h] [rbp-68h] BYREF
  __int64 v17; // [rsp+78h] [rbp-60h]
  UUID Uuid; // [rsp+88h] [rbp-50h] BYREF

  v9 = ObjectAttributes;
  v17 = (__int64)EnlistmentKey;
  v13 = 0;
  Handle = 0;
  Uuid = 0;
  if ( CreateOptions > 1 || (NotificationMask & 0xC0000000) != 0 )
    return -1073741811;
  LOBYTE(ObjectAttributes) = PreviousMode;
  LOBYTE(v13) = PreviousMode;
  Object = ObCreateObject(v13, TmEnlistmentObjectType, v9, ObjectAttributes);
  if ( Object >= 0 )
  {
    MEMORY[0xA8] = 0;
    ExUuidCreate(&Uuid);
    Object = TmpInitializeEnlistment(0, CreateOptions, NotificationMask, v17);
    if ( Object >= 0 )
    {
      ObfReferenceObject(0);
      Object = ObInsertObject(0, 0, DesiredAccess, 0, 0, &Handle);
      if ( Object < 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, __int64, __int64))TmEnlistmentObjectType[16])(0, 0, 1, 1);
      }
      else
      {
        _InterlockedOr((volatile signed __int32 *)0xAC, 0x100u);
        if ( PreviousMode )
          RtlWriteULong64ToUser(EnlistmentHandle, Handle);
        else
          *EnlistmentHandle = Handle;
      }
    }
    ObfDereferenceObject(0);
  }
  return Object;
}

```

## disassembly

```asm
0x14001a870  mov     r11, rsp
0x14001a873  push    rbx
0x14001a874  push    rsi
0x14001a875  push    rdi
0x14001a876  push    r12
0x14001a878  push    r13
0x14001a87a  push    r14
0x14001a87c  push    r15
0x14001a87e  sub     rsp, 0A0h
0x14001a885  mov     rax, cs:__security_cookie
0x14001a88c  xor     rax, rsp
0x14001a88f  mov     [rsp+0D8h+var_40], rax
0x14001a897  mov     r10, r9
0x14001a89a  mov     r15d, r8d
0x14001a89d  mov     sil, dl
0x14001a8a0  mov     rdi, rcx
0x14001a8a3  mov     [rsp+0D8h+PreviousMode], dl
0x14001a8a7  mov     r12, [rsp+0D8h+ResourceManager]
0x14001a8af  mov     r13, [rsp+0D8h+Transaction]
0x14001a8b7  mov     rax, [rsp+0D8h+EnlistmentKey]
0x14001a8bf  mov     [rsp+0D8h+var_60], rax
0x14001a8c4  xor     ecx, ecx
0x14001a8c6  mov     [r11-78h], rcx
0x14001a8ca  mov     [r11-68h], rcx
0x14001a8ce  xorps   xmm0, xmm0
0x14001a8d1  movups  xmmword ptr [r11-50h], xmm0
0x14001a8d6  mov     r14d, [rsp+0D8h+CreateOptions]
0x14001a8de  cmp     r14d, 1
0x14001a8e2  ja      loc_14001AA5A
0x14001a8e8  mov     eax, [r11+40h]
0x14001a8ec  test    eax, 0C0000000h
0x14001a8f1  jnz     loc_14001AA5A
0x14001a8f7  lea     rax, [r11-78h]
0x14001a8fb  mov     [rsp+0D8h+var_98], rax
0x14001a900  mov     [rsp+0D8h+var_A0], ecx
0x14001a904  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x14001a908  mov     dword ptr [rsp+0D8h+Handle], 1E0h
0x14001a910  mov     [rsp+0D8h+NewObject], rcx
0x14001a915  mov     r9b, dl
0x14001a918  mov     r8, r10
0x14001a91b  mov     rdx, cs:TmEnlistmentObjectType
0x14001a922  mov     cl, r9b
0x14001a925  call    cs:__imp_ObCreateObject
0x14001a92c  nop     dword ptr [rax+rax+00h]
0x14001a931  mov     ebx, eax
0x14001a933  test    eax, eax
0x14001a935  js      short loc_14001A9A3
0x14001a937  mov     rax, [rsp+0D8h+Object]
0x14001a93c  mov     dword ptr [rax+0A8h], 0
0x14001a946  lea     rcx, [rsp+0D8h+Uuid]; Uuid
0x14001a94e  call    cs:__imp_ExUuidCreate
0x14001a955  nop     dword ptr [rax+rax+00h]
0x14001a95a  mov     rax, [rsp+0D8h+var_60]
0x14001a95f  mov     [rsp+0D8h+var_A8], rax; __int64
0x14001a964  mov     eax, [rsp+0D8h+NotificationMask]
0x14001a96b  mov     dword ptr [rsp+0D8h+Handle], eax; int
0x14001a96f  mov     dword ptr [rsp+0D8h+NewObject], r14d; int
0x14001a974  lea     r9, [rsp+0D8h+Uuid]
0x14001a97c  mov     r8, r13
0x14001a97f  mov     rdx, r12
0x14001a982  mov     rcx, [rsp+0D8h+Object]; Object
0x14001a987  call    TmpInitializeEnlistment
0x14001a98c  mov     ebx, eax
0x14001a98e  mov     rcx, [rsp+0D8h+Object]; Object
0x14001a993  test    eax, eax
0x14001a995  jns     short loc_14001A9AA
0x14001a997  call    cs:__imp_ObfDereferenceObject
0x14001a99e  nop     dword ptr [rax+rax+00h]
0x14001a9a3  mov     eax, ebx
0x14001a9a5  jmp     loc_14001AA5F
0x14001a9aa  call    cs:__imp_ObfReferenceObject
0x14001a9b1  nop     dword ptr [rax+rax+00h]
0x14001a9b6  lea     rax, [rsp+0D8h+var_68]
0x14001a9bb  mov     [rsp+0D8h+Handle], rax; Handle
0x14001a9c0  mov     [rsp+0D8h+NewObject], 0; NewObject
0x14001a9c9  xor     r9d, r9d; ObjectPointerBias
0x14001a9cc  mov     r8d, r15d; DesiredAccess
0x14001a9cf  xor     edx, edx; PassedAccessState
0x14001a9d1  mov     rcx, [rsp+0D8h+Object]; Object
0x14001a9d6  call    cs:__imp_ObInsertObject
0x14001a9dd  nop     dword ptr [rax+rax+00h]
0x14001a9e2  mov     ebx, eax
0x14001a9e4  test    eax, eax
0x14001a9e6  js      short loc_14001AA2D
0x14001a9e8  mov     rax, [rsp+0D8h+Object]
0x14001a9ed  lock or dword ptr [rax+0ACh], 100h
0x14001a9f8  mov     rax, [rsp+0D8h+var_68]
0x14001a9fd  test    sil, sil
0x14001aa00  jz      short loc_14001AA0F
0x14001aa02  mov     rdx, rax
0x14001aa05  mov     rcx, rdi
0x14001aa08  call    RtlWriteULong64ToUser
0x14001aa0d  jmp     short loc_14001AA12
0x14001aa0f  mov     [rdi], rax
0x14001aa12  jmp     short loc_14001AA50
0x14001aa14  mov     ebx, eax
0x14001aa16  mov     dl, [rsp+0D8h+PreviousMode]; PreviousMode
0x14001aa1a  mov     rcx, [rsp+0D8h+var_68]; Handle
0x14001aa1f  call    cs:__imp_ObCloseHandle
0x14001aa26  nop     dword ptr [rax+rax+00h]
0x14001aa2b  jmp     short loc_14001AA50
0x14001aa2d  mov     rax, cs:TmEnlistmentObjectType
0x14001aa34  mov     rax, [rax+80h]
0x14001aa3b  mov     r8d, 1
0x14001aa41  mov     r9d, r8d
0x14001aa44  mov     rdx, [rsp+0D8h+Object]
0x14001aa49  xor     ecx, ecx
0x14001aa4b  call    _guard_dispatch_icall
0x14001aa50  mov     rcx, [rsp+0D8h+Object]
0x14001aa55  jmp     loc_14001A997
0x14001aa5a  mov     eax, 0C000000Dh
0x14001aa5f  mov     rcx, [rsp+0D8h+var_40]
0x14001aa67  xor     rcx, rsp; StackCookie
0x14001aa6a  call    __security_check_cookie
0x14001aa6f  add     rsp, 0A0h
0x14001aa76  pop     r15
0x14001aa78  pop     r14
0x14001aa7a  pop     r13
0x14001aa7c  pop     r12
0x14001aa7e  pop     rdi
0x14001aa7f  pop     rsi
0x14001aa80  pop     rbx
0x14001aa81  retn
0x140021426  push    rbp
0x140021428  sub     rsp, 50h
0x14002142c  mov     rbp, rdx
0x14002142f  mov     rax, gs:188h
0x140021438  mov     [rbp+80h], rax
0x14002143f  mov     rax, [rbp+80h]
0x140021446  mov     cl, [rax+232h]
0x14002144c  mov     [rbp+50h], cl
0x14002144f  mov     al, [rbp+50h]
0x140021452  xor     ecx, ecx
0x140021454  test    al, al
0x140021456  setnz   cl
0x140021459  mov     [rbp+68h], ecx
0x14002145c  mov     eax, [rbp+68h]
0x14002145f  add     rsp, 50h
0x140021463  pop     rbp
0x140021464  retn
```
