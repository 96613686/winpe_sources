# NtCreateResourceManagerExt

- ea: `0x140013ff0`
- end: `0x140014470`
- name: `NtCreateResourceManagerExt`
- size: `1152`
- prototype: `NTSTATUS __stdcall(PHANDLE ResourceManagerHandle, ACCESS_MASK DesiredAccess, HANDLE TmHandle, LPGUID RmGuid, POBJECT_ATTRIBUTES ObjectAttributes, ULONG CreateOptions, PUNICODE_STRING Description)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1400014d4`
- `0x1400024e0`
- `0x1400025c0`
- `0x14000d1fc`
- `0x14000d238`
- `0x14000d274`
- `0x140011dbc`
- `0x140013ff0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014226`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022301`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014226`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022301`
- `ntoskrnl!ObfDereferenceObject` at `0x14001438b`
- `ntoskrnl!ObfDereferenceObject` at `0x140014447`
- `ntoskrnl!ObfDereferenceObject` at `0x14001445f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400222d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400222e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001438b`
- `ntoskrnl!ObfDereferenceObject` at `0x140014447`
- `ntoskrnl!ObfDereferenceObject` at `0x14001445f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400222d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400222e9`
- `ntoskrnl!ObfReferenceObject` at `0x14001439c`
- `ntoskrnl!ObfReferenceObject` at `0x14001439c`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001415a`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001415a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400142e0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400142e0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022266`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022266`
- `ntoskrnl!ObCreateObject` at `0x140014338`
- `ntoskrnl!ObCreateObject` at `0x140014338`
- `ntoskrnl!ObInsertObject` at `0x1400143ce`
- `ntoskrnl!ObInsertObject` at `0x1400143ce`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400141ac`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400141ac`
- `ntoskrnl!ProbeForRead` at `0x14001413d`
- `ntoskrnl!ProbeForRead` at `0x14001413d`

## pseudocode

```c
NTSTATUS __stdcall NtCreateResourceManagerExt(
        PHANDLE ResourceManagerHandle,
        ACCESS_MASK DesiredAccess,
        HANDLE TmHandle,
        LPGUID RmGuid,
        POBJECT_ATTRIBUTES ObjectAttributes,
        ULONG CreateOptions,
        PUNICODE_STRING Description)
{
  HANDLE v7; // r10
  POBJECT_ATTRIBUTES v9; // rcx
  PVOID v10; // rsi
  const UNICODE_STRING *v11; // r15
  PVOID PoolWithQuotaTag; // r14
  KPROCESSOR_MODE v13; // r12
  __int64 ULong64FromUser; // rax
  int inserted; // edi
  char v17; // [rsp+50h] [rbp-E8h]
  PVOID Object; // [rsp+70h] [rbp-C8h] BYREF
  PVOID v20; // [rsp+78h] [rbp-C0h]
  volatile void *Address[2]; // [rsp+80h] [rbp-B8h] BYREF
  int v22; // [rsp+90h] [rbp-A8h]
  void *v23; // [rsp+98h] [rbp-A0h]
  POBJECT_ATTRIBUTES v24; // [rsp+A0h] [rbp-98h]
  void *v25; // [rsp+A8h] [rbp-90h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-88h]
  LPGUID v27; // [rsp+C0h] [rbp-78h]
  HANDLE Handle; // [rsp+C8h] [rbp-70h]
  PHANDLE v29; // [rsp+D0h] [rbp-68h]
  HANDLE v30; // [rsp+D8h] [rbp-60h]
  GUID v31; // [rsp+E8h] [rbp-50h] BYREF

  v27 = RmGuid;
  v7 = TmHandle;
  Handle = TmHandle;
  v29 = ResourceManagerHandle;
  LODWORD(Object) = DesiredAccess;
  v30 = TmHandle;
  v9 = ObjectAttributes;
  v24 = ObjectAttributes;
  v10 = 0;
  v31 = 0;
  v25 = 0;
  v22 = 0;
  *(_OWORD *)Address = 0;
  v11 = 0;
  v23 = 0;
  PoolWithQuotaTag = 0;
  v20 = 0;
  v17 = 0;
  v13 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( !v13 )
  {
    v11 = Description;
    v23 = Description;
    v31 = *RmGuid;
    goto LABEL_12;
  }
  ULong64FromUser = RtlReadULong64FromUser(ResourceManagerHandle);
  RtlWriteULong64ToUser(ResourceManagerHandle, ULong64FromUser);
  if ( Description )
  {
    DWORD1(v26) = 0;
    LODWORD(v26) = RtlReadULongFromUser(Description);
    *((_QWORD *)&v26 + 1) = RtlReadULong64FromUser(&Description->Buffer);
    *(_OWORD *)Address = v26;
    if ( (_WORD)v26 )
    {
      WORD1(Address[0]) = v26;
      ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
      PoolWithQuotaTag = ExAllocatePoolWithQuotaTag(PagedPool, LOWORD(Address[0]), 0x73436D54u);
      v20 = PoolWithQuotaTag;
      RtlCopyFromUser(PoolWithQuotaTag, (void *)Address[1], LOWORD(Address[0]));
      Address[1] = PoolWithQuotaTag;
      v11 = (const UNICODE_STRING *)Address;
      v23 = Address;
    }
  }
  if ( ((unsigned __int8)v27 & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(&v31, v27, 0x10u);
  inserted = v22;
  v7 = Handle;
  if ( v22 >= 0 )
  {
LABEL_12:
    if ( CreateOptions <= 3 )
    {
      if ( v7 == (HANDLE)-2LL && v13 )
      {
        inserted = -1073741816;
        goto LABEL_30;
      }
      if ( !v11 || v11->Length <= 0x80u )
      {
        if ( v7 == (HANDLE)-2LL )
        {
          v10 = 0;
        }
        else
        {
          Object = 0;
          inserted = ObReferenceObjectByHandle(v7, 0x10u, (POBJECT_TYPE)TmTransactionManagerObjectType, v13, &Object, 0);
          v10 = Object;
          if ( inserted < 0 )
            goto LABEL_30;
        }
        LOBYTE(RmGuid) = v13;
        LOBYTE(v9) = v13;
        inserted = ObCreateObject(v9, TmResourceManagerObjectType, v24, RmGuid);
        if ( inserted >= 0 )
        {
          MEMORY[0x1C] = 0;
          inserted = TmInitializeResourceManager(0, v11);
          if ( inserted >= 0 )
          {
            ObfReferenceObject(0);
            v17 = 1;
            inserted = ObInsertObject(0, 0, DesiredAccess, 0, 0, &v25);
            if ( inserted < 0 )
            {
              ((void (__fastcall *)(_QWORD, _QWORD, __int64))TmResourceManagerObjectType[16])(0, 0, 1);
            }
            else if ( v13 )
            {
              RtlWriteULong64ToUser(ResourceManagerHandle, v25);
            }
            else
            {
              *ResourceManagerHandle = v25;
            }
          }
          else
          {
            ObfDereferenceObject(0);
          }
        }
        goto LABEL_30;
      }
    }
    inserted = -1073741811;
LABEL_30:
    if ( v17 )
      ObfDereferenceObject(0);
    if ( v10 )
      ObfDereferenceObject(v10);
  }
  if ( PoolWithQuotaTag )
    ExFreePoolWithTag(PoolWithQuotaTag, 0);
  return inserted;
}

```

## disassembly

```asm
0x140013ff0  mov     r11, rsp
0x140013ff3  push    rbx
0x140013ff4  push    rsi
0x140013ff5  push    rdi
0x140013ff6  push    r12
0x140013ff8  push    r13
0x140013ffa  push    r14
0x140013ffc  push    r15
0x140013ffe  sub     rsp, 100h
0x140014005  mov     rax, cs:__security_cookie
0x14001400c  xor     rax, rsp
0x14001400f  mov     [rsp+138h+var_40], rax
0x140014017  mov     [rsp+138h+var_78], r9
0x14001401f  mov     r10, r8
0x140014022  mov     [rsp+138h+Handle], r8
0x14001402a  mov     [rsp+138h+DesiredAccess], edx
0x14001402e  mov     r13, rcx
0x140014031  mov     [rsp+138h+var_68], rcx
0x140014039  mov     dword ptr [rsp+138h+var_C8], edx
0x14001403d  mov     [rsp+138h+var_60], r8
0x140014045  mov     rcx, [rsp+138h+ObjectAttributes]
0x14001404d  mov     [rsp+138h+var_98], rcx
0x140014055  mov     rdi, [rsp+138h+Description]
0x14001405d  xor     ebx, ebx
0x14001405f  mov     esi, ebx
0x140014061  mov     [rsp+138h+var_D0], rbx
0x140014066  mov     [rsp+138h+var_E0], rbx
0x14001406b  xorps   xmm0, xmm0
0x14001406e  movups  xmmword ptr [r11-50h], xmm0
0x140014073  mov     [r11-90h], rbx
0x14001407a  mov     [rsp+138h+var_A8], ebx
0x140014081  movups  xmmword ptr [rsp+138h+Address], xmm0
0x140014089  mov     r15d, ebx
0x14001408c  mov     [r11-0A0h], rbx
0x140014093  mov     r14d, ebx
0x140014096  mov     [rsp+138h+var_C0], rbx
0x14001409b  mov     [rsp+138h+var_E8], bl
0x14001409f  mov     rax, gs:188h
0x1400140a8  mov     r12b, [rax+232h]
0x1400140af  mov     [rsp+138h+var_E7], r12b
0x1400140b4  test    r12b, r12b
0x1400140b7  jz      loc_140014258
0x1400140bd  mov     rcx, r13
0x1400140c0  call    RtlReadULong64FromUser
0x1400140c5  mov     rdx, rax
0x1400140c8  mov     rcx, r13
0x1400140cb  call    RtlWriteULong64ToUser
0x1400140d0  test    rdi, rdi
0x1400140d3  jz      loc_14001419F
0x1400140d9  xorps   xmm0, xmm0
0x1400140dc  movups  [rsp+138h+var_88], xmm0
0x1400140e4  mov     rcx, rdi
0x1400140e7  call    RtlReadULongFromUser
0x1400140ec  mov     dword ptr [rsp+138h+var_88], eax
0x1400140f3  lea     rcx, [rdi+8]
0x1400140f7  call    RtlReadULong64FromUser
0x1400140fc  mov     qword ptr [rsp+138h+var_88+8], rax
0x140014104  movaps  xmm0, [rsp+138h+var_88]
0x14001410c  movdqa  xmmword ptr [rsp+138h+Address], xmm0
0x140014115  mov     eax, dword ptr [rsp+138h+var_88]
0x14001411c  test    ax, ax
0x14001411f  jz      short loc_14001419F
0x140014121  mov     word ptr [rsp+138h+Address+2], ax
0x140014129  movzx   edx, word ptr [rsp+138h+Address]; Length
0x140014131  lea     r8d, [rbx+2]; Alignment
0x140014135  mov     rcx, [rsp+138h+Address+8]; Address
0x14001413d  call    cs:__imp_ProbeForRead
0x140014144  nop     dword ptr [rax+rax+00h]
0x140014149  movzx   edx, word ptr [rsp+138h+Address]; NumberOfBytes
0x140014151  lea     ecx, [rbx+1]; PoolType
0x140014154  mov     r8d, 73436D54h; Tag
0x14001415a  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140014161  nop     dword ptr [rax+rax+00h]
0x140014166  mov     r14, rax
0x140014169  mov     [rsp+138h+var_C0], rax
0x14001416e  movzx   r8d, word ptr [rsp+138h+Address]; Size
0x140014177  mov     rdx, [rsp+138h+Address+8]; Src
0x14001417f  mov     rcx, rax; void *
0x140014182  call    RtlCopyFromUser
0x140014187  mov     [rsp+138h+Address+8], r14
0x14001418f  lea     r15, [rsp+138h+Address]
0x140014197  mov     [rsp+138h+var_A0], r15
0x14001419f  mov     rdx, [rsp+138h+var_78]
0x1400141a7  test    dl, 3
0x1400141aa  jz      short loc_1400141B9
0x1400141ac  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400141b3  nop     dword ptr [rax+rax+00h]
0x1400141b8  int     3; Trap to Debugger
0x1400141b9  mov     r8d, 10h; Size
0x1400141bf  lea     rcx, [rsp+138h+var_50]; void *
0x1400141c7  call    RtlCopyFromUser
0x1400141cc  mov     edi, [rsp+138h+var_A8]
0x1400141d3  mov     r10, [rsp+138h+Handle]
0x1400141db  jmp     short loc_140014218
0x1400141dd  mov     edi, eax
0x1400141df  xor     ebx, ebx
0x1400141e1  mov     rsi, [rsp+138h+var_D0]
0x1400141e6  mov     r12b, [rsp+138h+var_E7]
0x1400141eb  mov     r15, [rsp+138h+var_A0]
0x1400141f3  mov     r14, [rsp+138h+var_C0]
0x1400141f8  mov     r13, [rsp+138h+var_68]
0x140014200  mov     eax, dword ptr [rsp+138h+var_C8]
0x140014204  mov     [rsp+138h+DesiredAccess], eax
0x140014208  mov     r10, [rsp+138h+var_60]
0x140014210  mov     rax, [rsp+138h+var_98]
0x140014218  test    edi, edi
0x14001421a  jns     short loc_140014270
0x14001421c  test    r14, r14
0x14001421f  jz      short loc_140014232
0x140014221  xor     edx, edx; Tag
0x140014223  mov     rcx, r14; P
0x140014226  call    cs:__imp_ExFreePoolWithTag
0x14001422d  nop     dword ptr [rax+rax+00h]
0x140014232  mov     eax, edi
0x140014234  mov     rcx, [rsp+138h+var_40]
0x14001423c  xor     rcx, rsp; StackCookie
0x14001423f  call    __security_check_cookie
0x140014244  add     rsp, 100h
0x14001424b  pop     r15
0x14001424d  pop     r14
0x14001424f  pop     r13
0x140014251  pop     r12
0x140014253  pop     rdi
0x140014254  pop     rsi
0x140014255  pop     rbx
0x140014256  retn
0x140014258  mov     r15, rdi
0x14001425b  mov     [rsp+138h+var_A0], rdi
0x140014263  movups  xmm0, xmmword ptr [r9]
0x140014267  movdqu  [rsp+138h+var_50], xmm0
0x140014270  cmp     [rsp+138h+CreateOptions], 3
0x140014278  jbe     short loc_140014288
0x14001427a  mov     edi, 0C000000Dh
0x14001427f  mov     [rsp+138h+var_E4], edi
0x140014283  jmp     loc_14001443C
0x140014288  cmp     r10, 0FFFFFFFFFFFFFFFEh
0x14001428c  jnz     short loc_14001429A
0x14001428e  test    r12b, r12b
0x140014291  jz      short loc_14001429A
0x140014293  mov     edi, 0C0000008h
0x140014298  jmp     short loc_14001427F
0x14001429a  test    r15, r15
0x14001429d  jz      short loc_1400142AA
0x14001429f  mov     eax, 80h
0x1400142a4  cmp     [r15], ax
0x1400142a8  ja      short loc_14001427A
0x1400142aa  cmp     r10, 0FFFFFFFFFFFFFFFEh
0x1400142ae  jnz     short loc_1400142BA
0x1400142b0  mov     rsi, rbx
0x1400142b3  mov     [rsp+138h+var_D0], rbx
0x1400142b8  jmp     short loc_140014304
0x1400142ba  mov     r8, cs:TmTransactionManagerObjectType; ObjectType
0x1400142c1  mov     [rsp+138h+var_C8], rbx
0x1400142c6  mov     [rsp+138h+HandleInformation], rbx; HandleInformation
0x1400142cb  lea     rax, [rsp+138h+var_C8]
0x1400142d0  mov     [rsp+138h+Object], rax; Object
0x1400142d5  mov     r9b, r12b; AccessMode
0x1400142d8  mov     edx, 10h; DesiredAccess
0x1400142dd  mov     rcx, r10; Handle
0x1400142e0  call    cs:__imp_ObReferenceObjectByHandle
0x1400142e7  nop     dword ptr [rax+rax+00h]
0x1400142ec  mov     edi, eax
0x1400142ee  mov     rsi, [rsp+138h+var_C8]
0x1400142f3  mov     [rsp+138h+var_D0], rsi
0x1400142f8  mov     [rsp+138h+var_E4], eax
0x1400142fc  test    eax, eax
0x1400142fe  js      loc_14001443C
0x140014304  lea     rax, [rsp+138h+var_E0]
0x140014309  mov     [rsp+138h+var_F8], rax
0x14001430e  mov     [rsp+138h+var_100], ebx
0x140014312  mov     [rsp+138h+var_108], ebx
0x140014316  mov     dword ptr [rsp+138h+HandleInformation], 250h
0x14001431e  mov     [rsp+138h+Object], rbx
0x140014323  mov     r9b, r12b
0x140014326  mov     r8, [rsp+138h+var_98]
0x14001432e  mov     rdx, cs:TmResourceManagerObjectType
0x140014335  mov     cl, r12b
0x140014338  call    cs:__imp_ObCreateObject
0x14001433f  nop     dword ptr [rax+rax+00h]
0x140014344  mov     edi, eax
0x140014346  mov     [rsp+138h+var_E4], eax
0x14001434a  test    eax, eax
0x14001434c  js      loc_14001443C
0x140014352  mov     rax, [rsp+138h+var_E0]
0x140014357  mov     [rax+1Ch], ebx
0x14001435a  mov     [rsp+138h+Object], r15; StringIn
0x14001435f  mov     r9, rsi
0x140014362  mov     r8d, [rsp+138h+CreateOptions]
0x14001436a  lea     rdx, [rsp+138h+var_50]
0x140014372  mov     rcx, [rsp+138h+var_E0]; Event
0x140014377  call    TmInitializeResourceManager
0x14001437c  mov     edi, eax
0x14001437e  mov     [rsp+138h+var_E4], eax
0x140014382  mov     rcx, [rsp+138h+var_E0]; Object
0x140014387  test    eax, eax
0x140014389  jns     short loc_14001439C
0x14001438b  call    cs:__imp_ObfDereferenceObject
0x140014392  nop     dword ptr [rax+rax+00h]
0x140014397  jmp     loc_14001443C
0x14001439c  call    cs:__imp_ObfReferenceObject
0x1400143a3  nop     dword ptr [rax+rax+00h]
0x1400143a8  mov     [rsp+138h+var_E8], 1
0x1400143ad  lea     rax, [rsp+138h+var_90]
0x1400143b5  mov     [rsp+138h+HandleInformation], rax; Handle
0x1400143ba  mov     [rsp+138h+Object], rbx; NewObject
0x1400143bf  xor     r9d, r9d; ObjectPointerBias
0x1400143c2  mov     r8d, [rsp+138h+DesiredAccess]; DesiredAccess
0x1400143c7  xor     edx, edx; PassedAccessState
0x1400143c9  mov     rcx, [rsp+138h+var_E0]; Object
0x1400143ce  call    cs:__imp_ObInsertObject
0x1400143d5  nop     dword ptr [rax+rax+00h]
0x1400143da  mov     edi, eax
0x1400143dc  mov     [rsp+138h+var_E4], eax
0x1400143e0  test    eax, eax
0x1400143e2  js      short loc_140014418
0x1400143e4  mov     rax, [rsp+138h+var_90]
0x1400143ec  test    r12b, r12b
0x1400143ef  jz      short loc_1400143FE
0x1400143f1  mov     rdx, rax
0x1400143f4  mov     rcx, r13
0x1400143f7  call    RtlWriteULong64ToUser
0x1400143fc  jmp     short loc_140014402
0x1400143fe  mov     [r13+0], rax
0x140014402  jmp     short loc_140014416
0x140014404  mov     edi, eax
0x140014406  mov     [rsp+138h+var_E4], eax
0x14001440a  xor     ebx, ebx
0x14001440c  mov     rsi, [rsp+138h+var_D0]
0x140014411  mov     r14, [rsp+138h+var_C0]
0x140014416  jmp     short loc_14001443C
0x140014418  mov     rax, cs:TmResourceManagerObjectType
0x14001441f  mov     rax, [rax+80h]
0x140014426  mov     r9d, 1
0x14001442c  mov     r8d, r9d
0x14001442f  mov     rdx, [rsp+138h+var_E0]
0x140014434  xor     ecx, ecx
0x140014436  call    _guard_dispatch_icall
0x14001443b  nop
0x14001443c  cmp     [rsp+138h+var_E8], bl
0x140014440  jz      short loc_140014453
0x140014442  mov     rcx, [rsp+138h+var_E0]; Object
0x140014447  call    cs:__imp_ObfDereferenceObject
0x14001444e  nop     dword ptr [rax+rax+00h]
0x140014453  test    rsi, rsi
0x140014456  jz      loc_14001421C
0x14001445c  mov     rcx, rsi; Object
0x14001445f  call    cs:__imp_ObfDereferenceObject
0x140014466  nop     dword ptr [rax+rax+00h]
0x14001446b  jmp     loc_14001421C
0x14002225d  push    rbp
0x14002225f  sub     rsp, 50h
0x140022263  mov     rbp, rdx
0x140022266  call    cs:__imp_ExSystemExceptionFilter
0x14002226d  nop     dword ptr [rax+rax+00h]
0x140022272  nop
0x140022273  add     rsp, 50h
0x140022277  pop     rbp
0x140022278  retn
0x14002227a  push    rbp
0x14002227c  sub     rsp, 50h
0x140022280  mov     rbp, rdx
0x140022283  mov     rax, gs:188h
0x14002228c  mov     [rbp+0E0h], rax
0x140022293  mov     rax, [rbp+0E0h]
0x14002229a  mov     cl, [rax+232h]
0x1400222a0  mov     [rbp+52h], cl
0x1400222a3  mov     al, [rbp+52h]
0x1400222a6  xor     ecx, ecx
0x1400222a8  test    al, al
0x1400222aa  setnz   cl
0x1400222ad  mov     [rbp+94h], ecx
0x1400222b3  mov     eax, [rbp+94h]
0x1400222b9  add     rsp, 50h
0x1400222bd  pop     rbp
0x1400222be  retn
0x1400222c0  push    rbp
0x1400222c2  sub     rsp, 50h
0x1400222c6  mov     rbp, rdx
0x1400222c9  cmp     byte ptr [rbp+50h], 0
0x1400222cd  jz      short loc_1400222E0
0x1400222cf  mov     rcx, [rbp+58h]; Object
0x1400222d3  call    cs:__imp_ObfDereferenceObject
0x1400222da  nop     dword ptr [rax+rax+00h]
0x1400222df  nop
0x1400222e0  mov     rcx, [rbp+68h]; Object
0x1400222e4  test    rcx, rcx
0x1400222e7  jz      short loc_1400222F6
0x1400222e9  call    cs:__imp_ObfDereferenceObject
0x1400222f0  nop     dword ptr [rax+rax+00h]
0x1400222f5  nop
0x1400222f6  mov     rcx, [rbp+78h]; P
0x1400222fa  test    rcx, rcx
0x1400222fd  jz      short loc_14002230E
0x1400222ff  xor     edx, edx; Tag
0x140022301  call    cs:__imp_ExFreePoolWithTag
0x140022308  nop     dword ptr [rax+rax+00h]
0x14002230d  nop
0x14002230e  add     rsp, 50h
0x140022312  pop     rbp
0x140022313  retn
  ... truncated ...
```
