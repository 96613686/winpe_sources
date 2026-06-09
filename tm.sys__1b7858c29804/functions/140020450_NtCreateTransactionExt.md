# NtCreateTransactionExt

- ea: `0x140020450`
- end: `0x140020954`
- name: `NtCreateTransactionExt`
- size: `1284`
- prototype: `NTSTATUS __stdcall(PHANDLE TransactionHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, LPGUID Uow, HANDLE TmHandle, ULONG CreateOptions, ULONG IsolationLevel, ULONG IsolationFlags, PLARGE_INTEGER Timeout, PUNICODE_STRING Description)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1400010bc`
- `0x1400014d4`
- `0x1400024e0`
- `0x1400025c0`
- `0x14000d1fc`
- `0x14000d238`
- `0x14000d274`
- `0x1400109a4`
- `0x140020450`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002090e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002090e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ab7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400208f8`
- `ntoskrnl!ObfDereferenceObject` at `0x140020922`
- `ntoskrnl!ObfDereferenceObject` at `0x140021a9f`
- `ntoskrnl!ObfDereferenceObject` at `0x140021acd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400208f8`
- `ntoskrnl!ObfDereferenceObject` at `0x140020922`
- `ntoskrnl!ObfDereferenceObject` at `0x140021a9f`
- `ntoskrnl!ObfDereferenceObject` at `0x140021acd`
- `ntoskrnl!ObfReferenceObject` at `0x140020816`
- `ntoskrnl!ObfReferenceObject` at `0x140020816`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14002063e`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14002063e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140020722`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140020722`
- `ntoskrnl!ExUuidCreate` at `0x1400207b2`
- `ntoskrnl!ExUuidCreate` at `0x1400207b2`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021a55`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021a55`
- `ntoskrnl!ObCreateObject` at `0x14002077a`
- `ntoskrnl!ObCreateObject` at `0x14002077a`
- `ntoskrnl!ObInsertObject` at `0x140020843`
- `ntoskrnl!ObInsertObject` at `0x140020843`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140020578`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140020578`
- `ntoskrnl!ProbeForRead` at `0x14002061f`
- `ntoskrnl!ProbeForRead` at `0x14002061f`

## pseudocode

```c
NTSTATUS __stdcall NtCreateTransactionExt(
        PHANDLE TransactionHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        LPGUID Uow,
        HANDLE TmHandle,
        ULONG CreateOptions,
        ULONG IsolationLevel,
        ULONG IsolationFlags,
        PLARGE_INTEGER Timeout,
        PUNICODE_STRING Description)
{
  LPGUID v10; // rsi
  HANDLE v11; // r10
  HANDLE v12; // r15
  const UNICODE_STRING *StringIn; // r13
  PVOID PoolWithQuotaTag; // r12
  char v15; // r14
  __int64 ULong64FromUser; // rax
  int Object; // ebx
  int v18; // edx
  int v19; // r8d
  ACCESS_MASK DesiredAccessa; // [rsp+64h] [rbp-104h]
  HANDLE Handle; // [rsp+78h] [rbp-F0h] BYREF
  volatile void *Address[2]; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v24; // [rsp+98h] [rbp-D0h]
  PHANDLE v25; // [rsp+A0h] [rbp-C8h]
  __int64 v26; // [rsp+A8h] [rbp-C0h] BYREF
  void *v27; // [rsp+B0h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+C0h] [rbp-A8h]
  void *v29; // [rsp+D0h] [rbp-98h]
  POBJECT_ATTRIBUTES v30; // [rsp+D8h] [rbp-90h]
  LPGUID v31; // [rsp+E0h] [rbp-88h]
  UUID v32; // [rsp+F0h] [rbp-78h] BYREF
  __int64 *v33; // [rsp+100h] [rbp-68h]
  UUID Uuid; // [rsp+110h] [rbp-58h] BYREF

  v10 = Uow;
  v30 = ObjectAttributes;
  DesiredAccessa = DesiredAccess;
  v25 = TransactionHandle;
  v31 = Uow;
  v11 = TmHandle;
  Handle = TmHandle;
  v24 = (__int64)Timeout;
  v12 = 0;
  v27 = 0;
  Uuid = 0;
  v26 = 0;
  *(_OWORD *)Address = 0;
  StringIn = 0;
  PoolWithQuotaTag = 0;
  v15 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v15 )
  {
    ULong64FromUser = RtlReadULong64FromUser(TransactionHandle);
    RtlWriteULong64ToUser(v25, ULong64FromUser);
    if ( v24 )
    {
      v26 = RtlReadULong64FromUser(v24);
      v24 = (__int64)&v26;
      v33 = &v26;
    }
    if ( v10 )
    {
      v32 = 0;
      if ( ((unsigned __int8)v10 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&v32, v10, 0x10u);
      Uuid = v32;
    }
    if ( Description )
    {
      v28 = 0;
      LODWORD(v28) = RtlReadULongFromUser(Description);
      *((_QWORD *)&v28 + 1) = RtlReadULong64FromUser(&Description->Buffer);
      *(_OWORD *)Address = v28;
      if ( (_WORD)v28 )
      {
        WORD1(Address[0]) = v28;
        ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
        PoolWithQuotaTag = ExAllocatePoolWithQuotaTag(PagedPool, LOWORD(Address[0]), 0x73436D54u);
        RtlCopyFromUser(PoolWithQuotaTag, (void *)Address[1], LOWORD(Address[0]));
        Address[1] = PoolWithQuotaTag;
        StringIn = (const UNICODE_STRING *)Address;
        v29 = Address;
      }
    }
    v11 = Handle;
    DesiredAccess = DesiredAccessa;
  }
  else
  {
    if ( Uow )
      Uuid = *Uow;
    StringIn = Description;
    v29 = Description;
  }
  if ( CreateOptions > 1 || !DesiredAccess || StringIn && StringIn->Length > 0x80u )
    goto LABEL_16;
  if ( v11 )
  {
    if ( !v15 )
    {
      Handle = 0;
      Object = ObReferenceObjectByHandle(v11, 1u, (POBJECT_TYPE)TmTransactionManagerObjectType, 0, &Handle, 0);
      v12 = Handle;
      if ( Object < 0 )
        goto LABEL_35;
      goto LABEL_23;
    }
LABEL_16:
    Object = -1073741811;
    goto LABEL_35;
  }
LABEL_23:
  LOBYTE(Uow) = v15;
  LOBYTE(TransactionHandle) = v15;
  Object = ObCreateObject(TransactionHandle, TmTransactionObjectType, v30, Uow);
  if ( Object >= 0 )
  {
    MEMORY[0xC0] = 0;
    if ( !v10 )
      ExUuidCreate(&Uuid);
    Object = TmInitializeTransaction(0, v12, 0, IsolationLevel, IsolationFlags, v24, StringIn);
    if ( Object >= 0 )
    {
      ObfReferenceObject(0);
      Object = ObInsertObject(0, 0, DesiredAccessa, 0, 0, &v27);
      if ( Object < 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, __int64))TmTransactionObjectType[16])(0, 0, 1);
      }
      else
      {
        if ( v15 )
          RtlWriteULong64ToUser(v25, v27);
        else
          *v25 = v27;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
          WPP_SF__guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 3), v18, v19, (_DWORD)v10, (__int64)&Uuid);
      }
    }
  }
LABEL_35:
  if ( PoolWithQuotaTag )
    ExFreePoolWithTag(PoolWithQuotaTag, 0);
  if ( v12 )
    ObfDereferenceObject(v12);
  return Object;
}

```

## disassembly

```asm
0x140020450  mov     r11, rsp
0x140020453  push    rbx
0x140020454  push    rsi
0x140020455  push    rdi
0x140020456  push    r12
0x140020458  push    r13
0x14002045a  push    r14
0x14002045c  push    r15
0x14002045e  sub     rsp, 130h
0x140020465  mov     rax, cs:__security_cookie
0x14002046c  xor     rax, rsp
0x14002046f  mov     [rsp+168h+var_48], rax
0x140020477  mov     rsi, r9
0x14002047a  mov     [rsp+168h+var_90], r8
0x140020482  mov     [rsp+168h+DesiredAccess], edx
0x140020486  mov     [rsp+168h+var_C8], rcx
0x14002048e  mov     [rsp+168h+var_88], r9
0x140020496  mov     r10, [rsp+168h+TmHandle]
0x14002049e  mov     [rsp+168h+Handle], r10
0x1400204a3  mov     rax, [rsp+168h+Timeout]
0x1400204ab  mov     [r11-0D0h], rax
0x1400204b2  mov     rbx, [rsp+168h+Description]
0x1400204ba  xor     edi, edi
0x1400204bc  mov     [rsp+168h+var_110], rdi
0x1400204c1  mov     r15d, edi
0x1400204c4  mov     [rsp+168h+var_F8], rdi
0x1400204c9  mov     [r11-0B8h], rdi
0x1400204d0  xorps   xmm0, xmm0
0x1400204d3  movups  xmmword ptr [r11-58h], xmm0
0x1400204d8  mov     [r11-0C0h], rdi
0x1400204df  xorps   xmm1, xmm1
0x1400204e2  movups  xmmword ptr [rsp+168h+Address], xmm1
0x1400204ea  mov     r13d, edi
0x1400204ed  mov     r12d, edi
0x1400204f0  mov     [rsp+168h+P], rdi
0x1400204f5  mov     rax, gs:188h
0x1400204fe  mov     r14b, [rax+232h]
0x140020505  mov     [rsp+168h+var_114], r14b
0x14002050a  mov     [rsp+168h+var_108], r14b
0x14002050f  test    r14b, r14b
0x140020512  jz      loc_1400206A3
0x140020518  call    RtlReadULong64FromUser
0x14002051d  mov     rdx, rax
0x140020520  mov     rcx, [rsp+168h+var_C8]
0x140020528  call    RtlWriteULong64ToUser
0x14002052d  mov     rax, [rsp+168h+var_D0]
0x140020535  test    rax, rax
0x140020538  jz      short loc_140020562
0x14002053a  mov     rcx, rax
0x14002053d  call    RtlReadULong64FromUser
0x140020542  mov     [rsp+168h+var_C0], rax
0x14002054a  lea     rax, [rsp+168h+var_C0]
0x140020552  mov     [rsp+168h+var_D0], rax
0x14002055a  mov     [rsp+168h+var_68], rax
0x140020562  test    rsi, rsi
0x140020565  jz      short loc_1400205AC
0x140020567  xorps   xmm0, xmm0
0x14002056a  movups  [rsp+168h+var_78], xmm0
0x140020572  test    sil, 3
0x140020576  jz      short loc_140020585
0x140020578  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14002057f  nop     dword ptr [rax+rax+00h]
0x140020584  int     3; Trap to Debugger
0x140020585  mov     r8d, 10h; Size
0x14002058b  mov     rdx, rsi; Src
0x14002058e  lea     rcx, [rsp+168h+var_78]; void *
0x140020596  call    RtlCopyFromUser
0x14002059b  movaps  xmm0, [rsp+168h+var_78]
0x1400205a3  movdqa  xmmword ptr [rsp+168h+Uuid.Data1], xmm0
0x1400205ac  test    rbx, rbx
0x1400205af  jz      loc_140020683
0x1400205b5  xorps   xmm0, xmm0
0x1400205b8  movups  [rsp+168h+var_A8], xmm0
0x1400205c0  mov     rcx, rbx
0x1400205c3  call    RtlReadULongFromUser
0x1400205c8  mov     dword ptr [rsp+168h+var_A8], eax
0x1400205cf  lea     rcx, [rbx+8]
0x1400205d3  call    RtlReadULong64FromUser
0x1400205d8  mov     qword ptr [rsp+168h+var_A8+8], rax
0x1400205e0  movaps  xmm0, [rsp+168h+var_A8]
0x1400205e8  movdqa  xmmword ptr [rsp+168h+Address], xmm0
0x1400205f1  mov     eax, dword ptr [rsp+168h+var_A8]
0x1400205f8  test    ax, ax
0x1400205fb  jz      loc_140020683
0x140020601  mov     word ptr [rsp+168h+Address+2], ax
0x140020609  movzx   edx, word ptr [rsp+168h+Address]; Length
0x140020611  mov     r8d, 2; Alignment
0x140020617  mov     rcx, [rsp+168h+Address+8]; Address
0x14002061f  call    cs:__imp_ProbeForRead
0x140020626  nop     dword ptr [rax+rax+00h]
0x14002062b  movzx   edx, word ptr [rsp+168h+Address]; NumberOfBytes
0x140020633  mov     ecx, 1; PoolType
0x140020638  mov     r8d, 73436D54h; Tag
0x14002063e  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140020645  nop     dword ptr [rax+rax+00h]
0x14002064a  mov     r12, rax
0x14002064d  mov     [rsp+168h+P], rax
0x140020652  movzx   r8d, word ptr [rsp+168h+Address]; Size
0x14002065b  mov     rdx, [rsp+168h+Address+8]; Src
0x140020663  mov     rcx, rax; void *
0x140020666  call    RtlCopyFromUser
0x14002066b  mov     [rsp+168h+Address+8], r12
0x140020673  lea     r13, [rsp+168h+Address]
0x14002067b  mov     [rsp+168h+var_98], r13
0x140020683  mov     r10, [rsp+168h+Handle]
0x140020688  mov     edx, [rsp+168h+DesiredAccess]
0x14002068c  jmp     short loc_1400206C0
0x14002068e  mov     ebx, eax
0x140020690  mov     [rsp+168h+var_118], eax
0x140020694  mov     r15, [rsp+168h+var_F8]
0x140020699  mov     r12, [rsp+168h+P]
0x14002069e  jmp     loc_1400208EE
0x1400206a3  test    rsi, rsi
0x1400206a6  jz      short loc_1400206B5
0x1400206a8  movups  xmm0, xmmword ptr [r9]
0x1400206ac  movdqu  xmmword ptr [rsp+168h+Uuid.Data1], xmm0
0x1400206b5  mov     r13, rbx
0x1400206b8  mov     [rsp+168h+var_98], rbx
0x1400206c0  cmp     [rsp+168h+CreateOptions], 1
0x1400206c8  jbe     short loc_1400206D8
0x1400206ca  mov     ebx, 0C000000Dh
0x1400206cf  mov     [rsp+168h+var_118], ebx
0x1400206d3  jmp     loc_1400208EE
0x1400206d8  test    edx, edx
0x1400206da  jz      short loc_1400206CA
0x1400206dc  test    r13, r13
0x1400206df  jz      short loc_1400206ED
0x1400206e1  mov     eax, 80h
0x1400206e6  cmp     [r13+0], ax
0x1400206eb  ja      short loc_1400206CA
0x1400206ed  test    r10, r10
0x1400206f0  jz      short loc_140020746
0x1400206f2  test    r14b, r14b
0x1400206f5  jnz     short loc_1400206CA
0x1400206f7  test    r10, r10
0x1400206fa  jz      short loc_140020746
0x1400206fc  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x140020703  mov     [rsp+168h+Handle], rdi
0x140020708  mov     [rsp+168h+HandleInformation], rdi; HandleInformation
0x14002070d  lea     rax, [rsp+168h+Handle]
0x140020712  mov     [rsp+168h+Object], rax; Object
0x140020717  mov     r9b, r14b; AccessMode
0x14002071a  mov     edx, 1; DesiredAccess
0x14002071f  mov     rcx, r10; Handle
0x140020722  call    cs:__imp_ObReferenceObjectByHandle
0x140020729  nop     dword ptr [rax+rax+00h]
0x14002072e  mov     ebx, eax
0x140020730  mov     r15, [rsp+168h+Handle]
0x140020735  mov     [rsp+168h+var_F8], r15
0x14002073a  mov     [rsp+168h+var_118], eax
0x14002073e  test    eax, eax
0x140020740  js      loc_1400208EE
0x140020746  lea     rax, [rsp+168h+var_110]
0x14002074b  mov     [rsp+168h+StringIn], rax
0x140020750  mov     dword ptr [rsp+168h+var_130], edi
0x140020754  mov     [rsp+168h+var_138], edi
0x140020758  mov     dword ptr [rsp+168h+HandleInformation], 2D8h
0x140020760  mov     [rsp+168h+Object], rdi; int
0x140020765  mov     r9b, r14b
0x140020768  mov     r8, [rsp+168h+var_90]
0x140020770  mov     rdx, cs:TmTransactionObjectType
0x140020777  mov     cl, r14b
0x14002077a  call    cs:__imp_ObCreateObject
0x140020781  nop     dword ptr [rax+rax+00h]
0x140020786  mov     ebx, eax
0x140020788  mov     [rsp+168h+var_118], eax
0x14002078c  test    eax, eax
0x14002078e  jns     short loc_14002079A
0x140020790  mov     [rsp+168h+var_110], rdi
0x140020795  jmp     loc_1400208EE
0x14002079a  mov     rax, [rsp+168h+var_110]
0x14002079f  mov     [rax+0C0h], edi
0x1400207a5  test    rsi, rsi
0x1400207a8  jnz     short loc_1400207BE
0x1400207aa  lea     rcx, [rsp+168h+Uuid]; Uuid
0x1400207b2  call    cs:__imp_ExUuidCreate
0x1400207b9  nop     dword ptr [rax+rax+00h]
0x1400207be  mov     [rsp+168h+StringIn], r13; StringIn
0x1400207c3  mov     rax, [rsp+168h+var_D0]
0x1400207cb  mov     [rsp+168h+var_130], rax; __int64
0x1400207d0  mov     eax, [rsp+168h+IsolationFlags]
0x1400207d7  mov     [rsp+168h+var_138], eax; int
0x1400207db  mov     eax, [rsp+168h+IsolationLevel]
0x1400207e2  mov     dword ptr [rsp+168h+HandleInformation], eax; int
0x1400207e6  mov     r9d, [rsp+168h+CreateOptions]
0x1400207ee  lea     r8, [rsp+168h+Uuid]
0x1400207f6  mov     rdx, r15; PVOID
0x1400207f9  mov     rcx, [rsp+168h+var_110]; Object
0x1400207fe  call    TmInitializeTransaction
0x140020803  mov     ebx, eax
0x140020805  mov     [rsp+168h+var_118], eax
0x140020809  test    eax, eax
0x14002080b  js      loc_1400208EE
0x140020811  mov     rcx, [rsp+168h+var_110]; Object
0x140020816  call    cs:__imp_ObfReferenceObject
0x14002081d  nop     dword ptr [rax+rax+00h]
0x140020822  lea     rax, [rsp+168h+var_B8]
0x14002082a  mov     [rsp+168h+HandleInformation], rax; Handle
0x14002082f  mov     [rsp+168h+Object], rdi; NewObject
0x140020834  xor     r9d, r9d; ObjectPointerBias
0x140020837  mov     r8d, [rsp+168h+DesiredAccess]; DesiredAccess
0x14002083c  xor     edx, edx; PassedAccessState
0x14002083e  mov     rcx, [rsp+168h+var_110]; Object
0x140020843  call    cs:__imp_ObInsertObject
0x14002084a  nop     dword ptr [rax+rax+00h]
0x14002084f  mov     ebx, eax
0x140020851  mov     [rsp+168h+var_118], eax
0x140020855  test    eax, eax
0x140020857  js      short loc_1400208CA
0x140020859  mov     rax, [rsp+168h+var_B8]
0x140020861  mov     rcx, [rsp+168h+var_C8]
0x140020869  test    r14b, r14b
0x14002086c  jz      short loc_140020878
0x14002086e  mov     rdx, rax
0x140020871  call    RtlWriteULong64ToUser
0x140020876  jmp     short loc_14002087B
0x140020878  mov     [rcx], rax
0x14002087b  jmp     short loc_140020895
0x14002087d  mov     ebx, eax
0x14002087f  mov     [rsp+168h+var_118], eax
0x140020883  mov     r15, [rsp+168h+var_F8]
0x140020888  mov     r12, [rsp+168h+P]
0x14002088d  mov     rsi, [rsp+168h+var_88]
0x140020895  lea     rax, WPP_GLOBAL_Control
0x14002089c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400208a3  cmp     rcx, rax
0x1400208a6  jz      short loc_1400208EE
0x1400208a8  mov     eax, [rcx+2Ch]
0x1400208ab  test    al, 4
0x1400208ad  jz      short loc_1400208EE
0x1400208af  lea     rax, [rsp+168h+Uuid]
0x1400208b7  mov     [rsp+168h+Object], rax
0x1400208bc  mov     r9, rsi
0x1400208bf  mov     rcx, [rcx+18h]
0x1400208c3  call    WPP_SF__guid__guid_
0x1400208c8  jmp     short loc_1400208EE
0x1400208ca  mov     rax, cs:TmTransactionObjectType
0x1400208d1  mov     rax, [rax+80h]
0x1400208d8  mov     r9d, 1
0x1400208de  mov     r8d, r9d
0x1400208e1  mov     rdx, [rsp+168h+var_110]
0x1400208e6  xor     ecx, ecx
0x1400208e8  call    _guard_dispatch_icall
0x1400208ed  nop
0x1400208ee  mov     rcx, [rsp+168h+var_110]; Object
0x1400208f3  test    rcx, rcx
0x1400208f6  jz      short loc_140020904
0x1400208f8  call    cs:__imp_ObfDereferenceObject
0x1400208ff  nop     dword ptr [rax+rax+00h]
0x140020904  test    r12, r12
0x140020907  jz      short loc_14002091A
0x140020909  xor     edx, edx; Tag
0x14002090b  mov     rcx, r12; P
0x14002090e  call    cs:__imp_ExFreePoolWithTag
0x140020915  nop     dword ptr [rax+rax+00h]
0x14002091a  test    r15, r15
0x14002091d  jz      short loc_14002092E
0x14002091f  mov     rcx, r15; Object
0x140020922  call    cs:__imp_ObfDereferenceObject
0x140020929  nop     dword ptr [rax+rax+00h]
0x14002092e  mov     eax, ebx
0x140020930  mov     rcx, [rsp+168h+var_48]
0x140020938  xor     rcx, rsp; StackCookie
0x14002093b  call    __security_check_cookie
0x140020940  add     rsp, 130h
0x140020947  pop     r15
0x140020949  pop     r14
0x14002094b  pop     r13
0x14002094d  pop     r12
0x14002094f  pop     rdi
0x140020950  pop     rsi
0x140020951  pop     rbx
0x140020952  retn
0x140021a4c  push    rbp
0x140021a4e  sub     rsp, 50h
0x140021a52  mov     rbp, rdx
0x140021a55  call    cs:__imp_ExSystemExceptionFilter
0x140021a5c  nop     dword ptr [rax+rax+00h]
0x140021a61  nop
0x140021a62  add     rsp, 50h
0x140021a66  pop     rbp
0x140021a67  retn
0x140021a69  push    rbp
0x140021a6b  sub     rsp, 50h
0x140021a6f  mov     rbp, rdx
0x140021a72  xor     eax, eax
0x140021a74  cmp     [rbp+54h], al
0x140021a77  setnz   al
0x140021a7a  mov     [rbp+90h], eax
0x140021a80  mov     eax, [rbp+90h]
0x140021a86  add     rsp, 50h
0x140021a8a  pop     rbp
0x140021a8b  retn
0x140021a8d  push    rbp
0x140021a8f  sub     rsp, 50h
0x140021a93  mov     rbp, rdx
0x140021a96  mov     rcx, [rbp+58h]; Object
0x140021a9a  test    rcx, rcx
0x140021a9d  jz      short loc_140021AAC
0x140021a9f  call    cs:__imp_ObfDereferenceObject
  ... truncated ...
```
