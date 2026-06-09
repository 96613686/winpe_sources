# NtOpenTransactionManagerExt

- ea: `0x1400175d0`
- end: `0x14001793e`
- name: `NtOpenTransactionManagerExt`
- size: `878`
- prototype: `NTSTATUS __stdcall(PHANDLE TmHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PUNICODE_STRING LogFileName, LPGUID TmIdentity, ULONG OpenOptions)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400014d4`
- `0x1400024e0`
- `0x14000d1fc`
- `0x14000d238`
- `0x14000d274`
- `0x14000e3c4`
- `0x1400175d0`
- `0x140020a6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001791d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002287b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001791d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002287b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400178e9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400178e9`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017739`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017739`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400178d4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400178d4`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022836`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022853`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022836`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022853`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017788`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017788`
- `ntoskrnl!ProbeForRead` at `0x14001771d`
- `ntoskrnl!ProbeForRead` at `0x14001771d`
- `ntoskrnl!PsIsComponentEnabled` at `0x14001763e`
- `ntoskrnl!PsIsComponentEnabled` at `0x14001763e`
- `ntoskrnl!ObOpenObjectByName` at `0x140017829`
- `ntoskrnl!ObOpenObjectByName` at `0x140017829`

## pseudocode

```c
NTSTATUS __stdcall NtOpenTransactionManagerExt(
        PHANDLE TmHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PUNICODE_STRING LogFileName,
        LPGUID TmIdentity,
        ULONG OpenOptions)
{
  PVOID PoolWithQuotaTag; // rsi
  const UNICODE_STRING *v9; // r14
  LPGUID v10; // rbx
  __int64 v11; // r8
  NTSTATUS v13; // ebx
  KPROCESSOR_MODE AccessMode; // r12
  __int64 ULong64FromUser; // rax
  PVOID v16; // r14
  ULONG Attributes; // edx
  volatile void *Address[2]; // [rsp+50h] [rbp-C8h] BYREF
  void *Handle; // [rsp+60h] [rbp-B8h] BYREF
  PHANDLE v21; // [rsp+68h] [rbp-B0h]
  PVOID Object; // [rsp+70h] [rbp-A8h]
  POBJECT_ATTRIBUTES v23; // [rsp+78h] [rbp-A0h]
  __int128 v24; // [rsp+80h] [rbp-98h]
  void *v25; // [rsp+90h] [rbp-88h]
  LPGUID v26; // [rsp+98h] [rbp-80h]
  __int128 v27; // [rsp+A0h] [rbp-78h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v29; // [rsp+C0h] [rbp-58h] BYREF

  v23 = ObjectAttributes;
  v21 = TmHandle;
  Handle = 0;
  *(_OWORD *)Address = 0;
  PoolWithQuotaTag = 0;
  v9 = 0;
  v29 = 0;
  v28 = 0;
  v10 = 0;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  if ( DesiredAccess )
  {
    AccessMode = *((_BYTE *)KeGetCurrentThread() + 562);
    if ( AccessMode )
    {
      ULong64FromUser = RtlReadULong64FromUser(v21);
      RtlWriteULong64ToUser(v21, ULong64FromUser);
      if ( LogFileName )
      {
        DWORD1(v24) = 0;
        LODWORD(v24) = RtlReadULongFromUser(LogFileName);
        *((_QWORD *)&v24 + 1) = RtlReadULong64FromUser(&LogFileName->Buffer);
        *(_OWORD *)Address = v24;
        if ( (_WORD)v24 )
        {
          WORD1(Address[0]) = v24;
          ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
          PoolWithQuotaTag = ExAllocatePoolWithQuotaTag(PagedPool, LOWORD(Address[0]), 0x73436D54u);
          RtlCopyFromUser(PoolWithQuotaTag, (void *)Address[1], LOWORD(Address[0]));
          Address[1] = PoolWithQuotaTag;
          v9 = (const UNICODE_STRING *)Address;
          v25 = Address;
        }
      }
      if ( TmIdentity )
      {
        v27 = 0;
        if ( ((unsigned __int8)TmIdentity & 3) != 0 )
          ExRaiseDatatypeMisalignment();
        RtlCopyFromUser(&v27, TmIdentity, 0x10u);
        v28 = v27;
        v10 = (LPGUID)&v28;
        v26 = (LPGUID)&v28;
      }
    }
    else
    {
      v9 = LogFileName;
      v25 = LogFileName;
      v10 = TmIdentity;
      v26 = TmIdentity;
    }
    if ( v9 )
    {
      if ( !v10 )
      {
        v13 = TmpExtractTmIdentityFromExistingLogFile(v9, &v29);
        if ( v13 < 0 )
          goto LABEL_30;
        v10 = (LPGUID)&v29;
      }
    }
    else if ( !v10 )
    {
      LOBYTE(v11) = AccessMode;
      v13 = ObOpenObjectByName(v23, TmTransactionManagerObjectType, v11, 0, DesiredAccess, 0, &Handle);
      goto LABEL_28;
    }
    Object = 0;
    TmpNamespaceLookup(&TmpTmNamespace, v10);
    v16 = Object;
    if ( !Object )
    {
      v13 = -1073741772;
      goto LABEL_30;
    }
    if ( AccessMode || !v23 )
      Attributes = 0;
    else
      Attributes = v23->Attributes;
    v13 = ObOpenObjectByPointer(
            Object,
            Attributes,
            0,
            DesiredAccess,
            (POBJECT_TYPE)TmTransactionManagerObjectType,
            AccessMode,
            &Handle);
    ObfDereferenceObject(v16);
LABEL_28:
    if ( v13 >= 0 )
      *v21 = Handle;
    goto LABEL_30;
  }
  v13 = -1073741811;
LABEL_30:
  if ( PoolWithQuotaTag )
    ExFreePoolWithTag(PoolWithQuotaTag, 0);
  if ( v13 == -1073741772 )
    return -1072103343;
  return v13;
}

```

## disassembly

```asm
0x1400175d0  mov     r11, rsp
0x1400175d3  push    rbx
0x1400175d4  push    rsi
0x1400175d5  push    rdi
0x1400175d6  push    r12
0x1400175d8  push    r13
0x1400175da  push    r14
0x1400175dc  push    r15
0x1400175de  sub     rsp, 0E0h
0x1400175e5  mov     rax, cs:__security_cookie
0x1400175ec  xor     rax, rsp
0x1400175ef  mov     [rsp+118h+var_48], rax
0x1400175f7  mov     r13, r9
0x1400175fa  mov     [rsp+118h+var_A0], r8
0x1400175ff  mov     r12d, edx
0x140017602  mov     [rsp+118h+DesiredAccess], edx
0x140017606  mov     [rsp+118h+var_B0], rcx
0x14001760b  mov     r15, [rsp+118h+TmIdentity]
0x140017613  xor     edi, edi
0x140017615  mov     [rsp+118h+var_B8], rdi
0x14001761a  xorps   xmm0, xmm0
0x14001761d  movups  xmmword ptr [rsp+118h+Address], xmm0
0x140017622  mov     esi, edi
0x140017624  mov     [rsp+118h+var_D0], rdi
0x140017629  mov     r14d, edi
0x14001762c  movups  xmmword ptr [r11-58h], xmm0
0x140017631  xorps   xmm1, xmm1
0x140017634  movups  xmmword ptr [r11-68h], xmm1
0x140017639  mov     ebx, edi
0x14001763b  lea     ecx, [rdi+1]
0x14001763e  call    cs:__imp_PsIsComponentEnabled
0x140017645  nop     dword ptr [rax+rax+00h]
0x14001764a  test    al, al
0x14001764c  jnz     short loc_140017677
0x14001764e  mov     eax, 0C0000022h
0x140017653  mov     rcx, [rsp+118h+var_48]
0x14001765b  xor     rcx, rsp; StackCookie
0x14001765e  call    __security_check_cookie
0x140017663  add     rsp, 0E0h
0x14001766a  pop     r15
0x14001766c  pop     r14
0x14001766e  pop     r13
0x140017670  pop     r12
0x140017672  pop     rdi
0x140017673  pop     rsi
0x140017674  pop     rbx
0x140017675  retn
0x140017677  test    r12d, r12d
0x14001767a  jnz     short loc_14001768A
0x14001767c  mov     ebx, 0C000000Dh
0x140017681  mov     [rsp+118h+var_D8], ebx
0x140017685  jmp     loc_140017913
0x14001768a  mov     rax, gs:188h
0x140017693  mov     r12b, [rax+232h]
0x14001769a  test    r12b, r12b
0x14001769d  jz      loc_1400177DE
0x1400176a3  mov     rcx, [rsp+118h+var_B0]
0x1400176a8  call    RtlReadULong64FromUser
0x1400176ad  mov     rdx, rax
0x1400176b0  mov     rcx, [rsp+118h+var_B0]
0x1400176b5  call    RtlWriteULong64ToUser
0x1400176ba  test    r13, r13
0x1400176bd  jz      loc_140017772
0x1400176c3  xorps   xmm0, xmm0
0x1400176c6  movups  [rsp+118h+var_98], xmm0
0x1400176ce  mov     rcx, r13
0x1400176d1  call    RtlReadULongFromUser
0x1400176d6  mov     dword ptr [rsp+118h+var_98], eax
0x1400176dd  lea     rcx, [r13+8]
0x1400176e1  call    RtlReadULong64FromUser
0x1400176e6  mov     qword ptr [rsp+118h+var_98+8], rax
0x1400176ee  movaps  xmm0, [rsp+118h+var_98]
0x1400176f6  movdqa  xmmword ptr [rsp+118h+Address], xmm0
0x1400176fc  mov     eax, dword ptr [rsp+118h+var_98]
0x140017703  test    ax, ax
0x140017706  jz      short loc_140017772
0x140017708  mov     word ptr [rsp+118h+Address+2], ax
0x14001770d  movzx   edx, word ptr [rsp+118h+Address]; Length
0x140017712  mov     r8d, 2; Alignment
0x140017718  mov     rcx, [rsp+118h+Address+8]; Address
0x14001771d  call    cs:__imp_ProbeForRead
0x140017724  nop     dword ptr [rax+rax+00h]
0x140017729  movzx   edx, word ptr [rsp+118h+Address]; NumberOfBytes
0x14001772e  mov     ecx, 1; PoolType
0x140017733  mov     r8d, 73436D54h; Tag
0x140017739  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140017740  nop     dword ptr [rax+rax+00h]
0x140017745  mov     rsi, rax
0x140017748  mov     [rsp+118h+var_D0], rax
0x14001774d  movzx   r8d, word ptr [rsp+118h+Address]; Size
0x140017753  mov     rdx, [rsp+118h+Address+8]; Src
0x140017758  mov     rcx, rax; void *
0x14001775b  call    RtlCopyFromUser
0x140017760  mov     [rsp+118h+Address+8], rsi
0x140017765  lea     r14, [rsp+118h+Address]
0x14001776a  mov     [rsp+118h+var_88], r14
0x140017772  test    r15, r15
0x140017775  jz      short loc_1400177CC
0x140017777  xorps   xmm0, xmm0
0x14001777a  movups  [rsp+118h+var_78], xmm0
0x140017782  test    r15b, 3
0x140017786  jz      short loc_140017795
0x140017788  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001778f  nop     dword ptr [rax+rax+00h]
0x140017794  int     3; Trap to Debugger
0x140017795  mov     r8d, 10h; Size
0x14001779b  mov     rdx, r15; Src
0x14001779e  lea     rcx, [rsp+118h+var_78]; void *
0x1400177a6  call    RtlCopyFromUser
0x1400177ab  movaps  xmm0, [rsp+118h+var_78]
0x1400177b3  movdqa  [rsp+118h+var_68], xmm0
0x1400177bc  lea     rbx, [rsp+118h+var_68]
0x1400177c4  mov     [rsp+118h+var_80], rbx
0x1400177cc  jmp     short loc_1400177F4
0x1400177ce  mov     ebx, eax
0x1400177d0  mov     [rsp+118h+var_D8], eax
0x1400177d4  mov     rsi, [rsp+118h+var_D0]
0x1400177d9  jmp     loc_140017913
0x1400177de  mov     r14, r13
0x1400177e1  mov     [rsp+118h+var_88], r13
0x1400177e9  mov     rbx, r15
0x1400177ec  mov     [rsp+118h+var_80], rbx
0x1400177f4  test    r14, r14
0x1400177f7  jnz     short loc_140017840
0x1400177f9  test    rbx, rbx
0x1400177fc  jnz     short loc_14001786B
0x1400177fe  lea     rax, [rsp+118h+var_B8]
0x140017803  mov     [rsp+118h+Handle], rax
0x140017808  mov     qword ptr [rsp+118h+AccessMode], rdi
0x14001780d  mov     r9d, [rsp+118h+DesiredAccess]
0x140017812  mov     dword ptr [rsp+118h+ObjectType], r9d
0x140017817  xor     r9d, r9d
0x14001781a  mov     r8b, r12b
0x14001781d  mov     rdx, cs:TmTransactionManagerObjectType
0x140017824  mov     rcx, [rsp+118h+var_A0]
0x140017829  call    cs:__imp_ObOpenObjectByName
0x140017830  nop     dword ptr [rax+rax+00h]
0x140017835  mov     ebx, eax
0x140017837  mov     [rsp+118h+var_D8], eax
0x14001783b  jmp     loc_1400178F5
0x140017840  test    rbx, rbx
0x140017843  jnz     short loc_14001786B
0x140017845  lea     rdx, [rsp+118h+var_58]
0x14001784d  mov     rcx, r14; Source
0x140017850  call    TmpExtractTmIdentityFromExistingLogFile
0x140017855  mov     ebx, eax
0x140017857  mov     [rsp+118h+var_D8], eax
0x14001785b  test    eax, eax
0x14001785d  js      loc_140017913
0x140017863  lea     rbx, [rsp+118h+var_58]
0x14001786b  mov     [rsp+118h+Object], rdi
0x140017870  lea     r8, [rsp+118h+Object]
0x140017875  mov     rdx, rbx; Buffer
0x140017878  lea     rcx, TmpTmNamespace; Table
0x14001787f  call    TmpNamespaceLookup
0x140017884  mov     r14, [rsp+118h+Object]
0x140017889  test    r14, r14
0x14001788c  jnz     short loc_140017898
0x14001788e  mov     ebx, 0C0000034h
0x140017893  jmp     loc_140017681
0x140017898  test    r12b, r12b
0x14001789b  jnz     short loc_1400178AC
0x14001789d  mov     rax, [rsp+118h+var_A0]
0x1400178a2  test    rax, rax
0x1400178a5  jz      short loc_1400178AC
0x1400178a7  mov     edx, [rax+18h]
0x1400178aa  jmp     short loc_1400178AE
0x1400178ac  mov     edx, edi; HandleAttributes
0x1400178ae  lea     rax, [rsp+118h+var_B8]
0x1400178b3  mov     [rsp+118h+Handle], rax; Handle
0x1400178b8  mov     [rsp+118h+AccessMode], r12b; AccessMode
0x1400178bd  mov     rax, cs:TmTransactionManagerObjectType
0x1400178c4  mov     [rsp+118h+ObjectType], rax; ObjectType
0x1400178c9  mov     r9d, [rsp+118h+DesiredAccess]; DesiredAccess
0x1400178ce  xor     r8d, r8d; PassedAccessState
0x1400178d1  mov     rcx, r14; Object
0x1400178d4  call    cs:__imp_ObOpenObjectByPointer
0x1400178db  nop     dword ptr [rax+rax+00h]
0x1400178e0  mov     ebx, eax
0x1400178e2  mov     [rsp+118h+var_D8], eax
0x1400178e6  mov     rcx, r14; Object
0x1400178e9  call    cs:__imp_ObfDereferenceObject
0x1400178f0  nop     dword ptr [rax+rax+00h]
0x1400178f5  test    ebx, ebx
0x1400178f7  js      short loc_140017913
0x1400178f9  mov     rax, [rsp+118h+var_B8]
0x1400178fe  mov     rcx, [rsp+118h+var_B0]
0x140017903  mov     [rcx], rax
0x140017906  jmp     short loc_140017913
0x140017908  mov     ebx, eax
0x14001790a  mov     [rsp+118h+var_D8], eax
0x14001790e  mov     rsi, [rsp+118h+var_D0]
0x140017913  test    rsi, rsi
0x140017916  jz      short loc_140017929
0x140017918  xor     edx, edx; Tag
0x14001791a  mov     rcx, rsi; P
0x14001791d  call    cs:__imp_ExFreePoolWithTag
0x140017924  nop     dword ptr [rax+rax+00h]
0x140017929  mov     eax, 0C0190051h
0x14001792e  cmp     ebx, 0C0000034h
0x140017934  cmovz   ebx, eax
0x140017937  mov     eax, ebx
0x140017939  jmp     loc_140017653
0x14002282d  push    rbp
0x14002282f  sub     rsp, 40h
0x140022833  mov     rbp, rdx
0x140022836  call    cs:__imp_ExSystemExceptionFilter
0x14002283d  nop     dword ptr [rax+rax+00h]
0x140022842  nop
0x140022843  add     rsp, 40h
0x140022847  pop     rbp
0x140022848  retn
0x14002284a  push    rbp
0x14002284c  sub     rsp, 40h
0x140022850  mov     rbp, rdx
0x140022853  call    cs:__imp_ExSystemExceptionFilter
0x14002285a  nop     dword ptr [rax+rax+00h]
0x14002285f  nop
0x140022860  add     rsp, 40h
0x140022864  pop     rbp
0x140022865  retn
0x140022867  push    rbp
0x140022869  sub     rsp, 40h
0x14002286d  mov     rbp, rdx
0x140022870  mov     rcx, [rbp+48h]; P
0x140022874  test    rcx, rcx
0x140022877  jz      short loc_140022888
0x140022879  xor     edx, edx; Tag
0x14002287b  call    cs:__imp_ExFreePoolWithTag
0x140022882  nop     dword ptr [rax+rax+00h]
0x140022887  nop
0x140022888  add     rsp, 40h
0x14002288c  pop     rbp
0x14002288d  retn
```
