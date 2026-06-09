# NtCreateTransactionManagerExt

- ea: `0x1400172f0`
- end: `0x1400175c0`
- name: `NtCreateTransactionManagerExt`
- size: `720`
- prototype: `NTSTATUS __stdcall(PHANDLE TmHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PUNICODE_STRING LogFileName, ULONG CreateOptions, ULONG CommitStrength)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400014d4`
- `0x14000d1fc`
- `0x14000d238`
- `0x14000d274`
- `0x140014c50`
- `0x1400172f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400175ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022813`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400175ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022813`
- `ntoskrnl!ObfDereferenceObject` at `0x14001753a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001753a`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017414`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017414`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400227a5`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400227a5`
- `ntoskrnl!ObCreateObject` at `0x1400174f1`
- `ntoskrnl!ObCreateObject` at `0x1400174f1`
- `ntoskrnl!ObInsertObject` at `0x140017562`
- `ntoskrnl!ObInsertObject` at `0x140017562`
- `ntoskrnl!ProbeForRead` at `0x1400173f8`
- `ntoskrnl!ProbeForRead` at `0x1400173f8`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017338`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017338`

## pseudocode

```c
NTSTATUS __stdcall NtCreateTransactionManagerExt(
        PHANDLE TmHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PUNICODE_STRING LogFileName,
        ULONG CreateOptions,
        ULONG CommitStrength)
{
  ACCESS_MASK v7; // r13d
  const UNICODE_STRING *v9; // r14
  PVOID PoolWithQuotaTag; // rsi
  __int64 v11; // rcx
  __int64 v12; // r9
  char v14; // r15
  __int64 ULong64FromUser; // rax
  int ULongFromUser; // eax
  __int16 v17; // r13
  int Object; // ebx
  volatile void *Address[2]; // [rsp+70h] [rbp-68h] BYREF
  void *Handle; // [rsp+88h] [rbp-50h] BYREF
  void *v21; // [rsp+90h] [rbp-48h]
  __int128 v22; // [rsp+A0h] [rbp-38h]

  v7 = DesiredAccess;
  Handle = 0;
  *(_OWORD *)Address = 0;
  v9 = 0;
  PoolWithQuotaTag = 0;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  v14 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v14 )
  {
    ULong64FromUser = RtlReadULong64FromUser(TmHandle);
    RtlWriteULong64ToUser(TmHandle, ULong64FromUser);
    if ( LogFileName )
    {
      DWORD1(v22) = 0;
      ULongFromUser = RtlReadULongFromUser(LogFileName);
      v17 = ULongFromUser;
      LODWORD(v22) = ULongFromUser;
      *((_QWORD *)&v22 + 1) = RtlReadULong64FromUser(&LogFileName->Buffer);
      *(_OWORD *)Address = v22;
      if ( v17 )
      {
        WORD1(Address[0]) = v17;
        ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
        PoolWithQuotaTag = ExAllocatePoolWithQuotaTag(PagedPool, LOWORD(Address[0]), 0x73436D54u);
        RtlCopyFromUser(PoolWithQuotaTag, (void *)Address[1], LOWORD(Address[0]));
        Address[1] = PoolWithQuotaTag;
        v9 = (const UNICODE_STRING *)Address;
        v21 = Address;
      }
      v7 = DesiredAccess;
    }
  }
  else
  {
    v9 = LogFileName;
    v21 = LogFileName;
  }
  if ( CreateOptions > 0x3F || v14 == 1 && (CreateOptions & 6) != 0 )
    goto LABEL_11;
  if ( (CreateOptions & 1) != 0 )
  {
    if ( v9 )
      goto LABEL_11;
  }
  else if ( v9 )
  {
    goto LABEL_19;
  }
  if ( (CreateOptions & 1) != 0 )
  {
LABEL_19:
    LOBYTE(v12) = v14;
    LOBYTE(v11) = v14;
    Object = ObCreateObject(v11, TmTransactionManagerObjectType, ObjectAttributes, v12);
    if ( Object >= 0 )
    {
      MEMORY[0x40] = 0;
      Object = TmInitializeTransactionManagerExt(0, v9, 0, CreateOptions);
      if ( Object >= 0 )
      {
        Object = ObInsertObject(0, 0, v7, 0, 0, &Handle);
        if ( Object >= 0 )
        {
          if ( v14 )
            RtlWriteULong64ToUser(TmHandle, Handle);
          else
            *TmHandle = Handle;
        }
      }
      else
      {
        ObfDereferenceObject(0);
      }
    }
    goto LABEL_26;
  }
LABEL_11:
  Object = -1073741811;
LABEL_26:
  if ( PoolWithQuotaTag )
    ExFreePoolWithTag(PoolWithQuotaTag, 0);
  return Object;
}

```

## disassembly

```asm
0x1400172f0  mov     rax, rsp
0x1400172f3  mov     [rax+8], rbx
0x1400172f7  mov     [rax+20h], rsi
0x1400172fb  mov     [rax+18h], r8
0x1400172ff  mov     [rax+10h], edx
0x140017302  push    rdi
0x140017303  push    r12
0x140017305  push    r13
0x140017307  push    r14
0x140017309  push    r15
0x14001730b  sub     rsp, 0B0h
0x140017312  mov     rbx, r9
0x140017315  mov     r13d, edx
0x140017318  mov     r12, rcx
0x14001731b  xor     edi, edi
0x14001731d  mov     [rax-80h], rdi
0x140017321  mov     [rax-50h], rdi
0x140017325  xorps   xmm0, xmm0
0x140017328  movups  xmmword ptr [rax-68h], xmm0
0x14001732c  mov     r14d, edi
0x14001732f  mov     esi, edi
0x140017331  mov     [rax-78h], rdi
0x140017335  lea     ecx, [rdi+1]
0x140017338  call    cs:__imp_PsIsComponentEnabled
0x14001733f  nop     dword ptr [rax+rax+00h]
0x140017344  test    al, al
0x140017346  jnz     short loc_14001736B
0x140017348  mov     eax, 0C0000022h
0x14001734d  lea     r11, [rsp+0D8h+var_28]
0x140017355  mov     rbx, [r11+30h]
0x140017359  mov     rsi, [r11+48h]
0x14001735d  mov     rsp, r11
0x140017360  pop     r15
0x140017362  pop     r14
0x140017364  pop     r13
0x140017366  pop     r12
0x140017368  pop     rdi
0x140017369  retn
0x14001736b  mov     rax, gs:188h
0x140017374  mov     r15b, [rax+232h]
0x14001737b  test    r15b, r15b
0x14001737e  jz      loc_140017467
0x140017384  mov     rcx, r12
0x140017387  call    RtlReadULong64FromUser
0x14001738c  mov     rdx, rax
0x14001738f  mov     rcx, r12
0x140017392  call    RtlWriteULong64ToUser
0x140017397  test    rbx, rbx
0x14001739a  jz      loc_140017455
0x1400173a0  xorps   xmm0, xmm0
0x1400173a3  movups  [rsp+0D8h+var_38], xmm0
0x1400173ab  mov     rcx, rbx
0x1400173ae  call    RtlReadULongFromUser
0x1400173b3  mov     r13d, eax
0x1400173b6  mov     dword ptr [rsp+0D8h+var_38], eax
0x1400173bd  lea     rcx, [rbx+8]
0x1400173c1  call    RtlReadULong64FromUser
0x1400173c6  mov     qword ptr [rsp+0D8h+var_38+8], rax
0x1400173ce  movaps  xmm0, [rsp+0D8h+var_38]
0x1400173d6  movdqa  xmmword ptr [rsp+0D8h+Address], xmm0
0x1400173dc  test    r13w, r13w
0x1400173e0  jz      short loc_14001744D
0x1400173e2  mov     word ptr [rsp+0D8h+Address+2], r13w
0x1400173e8  movzx   edx, word ptr [rsp+0D8h+Address]; Length
0x1400173ed  mov     r8d, 2; Alignment
0x1400173f3  mov     rcx, [rsp+0D8h+Address+8]; Address
0x1400173f8  call    cs:__imp_ProbeForRead
0x1400173ff  nop     dword ptr [rax+rax+00h]
0x140017404  movzx   edx, word ptr [rsp+0D8h+Address]; NumberOfBytes
0x140017409  mov     ecx, 1; PoolType
0x14001740e  mov     r8d, 73436D54h; Tag
0x140017414  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14001741b  nop     dword ptr [rax+rax+00h]
0x140017420  mov     rsi, rax
0x140017423  mov     [rsp+0D8h+P], rax
0x140017428  movzx   r8d, word ptr [rsp+0D8h+Address]; Size
0x14001742e  mov     rdx, [rsp+0D8h+Address+8]; Src
0x140017433  mov     rcx, rax; void *
0x140017436  call    RtlCopyFromUser
0x14001743b  mov     [rsp+0D8h+Address+8], rsi
0x140017440  lea     r14, [rsp+0D8h+Address]
0x140017445  mov     [rsp+0D8h+var_48], r14
0x14001744d  mov     r13d, [rsp+0D8h+arg_8]
0x140017455  jmp     short loc_140017472
0x140017457  mov     ebx, eax
0x140017459  mov     [rsp+0D8h+var_88], eax
0x14001745d  mov     rsi, [rsp+0D8h+P]
0x140017462  jmp     loc_1400175A3
0x140017467  mov     r14, rbx
0x14001746a  mov     [rsp+0D8h+var_48], rbx
0x140017472  cmp     [rsp+0D8h+CreateOptions], 3Fh ; '?'
0x14001747a  jbe     short loc_14001748A
0x14001747c  mov     ebx, 0C000000Dh
0x140017481  mov     [rsp+0D8h+var_88], ebx
0x140017485  jmp     loc_1400175A3
0x14001748a  cmp     r15b, 1
0x14001748e  jnz     short loc_14001749B
0x140017490  mov     eax, [rsp+0D8h+CreateOptions]
0x140017497  test    al, 6
0x140017499  jnz     short loc_14001747C
0x14001749b  mov     eax, [rsp+0D8h+CreateOptions]
0x1400174a2  test    al, 1
0x1400174a4  jz      short loc_1400174AD
0x1400174a6  test    r14, r14
0x1400174a9  jz      short loc_1400174B2
0x1400174ab  jmp     short loc_14001747C
0x1400174ad  test    r14, r14
0x1400174b0  jnz     short loc_1400174BD
0x1400174b2  mov     eax, [rsp+0D8h+CreateOptions]
0x1400174b9  test    al, 1
0x1400174bb  jz      short loc_14001747C
0x1400174bd  lea     rax, [rsp+0D8h+TransactionManager]
0x1400174c2  mov     [rsp+0D8h+var_98], rax
0x1400174c7  mov     [rsp+0D8h+var_A0], edi
0x1400174cb  mov     [rsp+0D8h+var_A8], edi
0x1400174cf  mov     dword ptr [rsp+0D8h+Handle], 3C0h
0x1400174d7  mov     [rsp+0D8h+NewObject], rdi
0x1400174dc  mov     r9b, r15b
0x1400174df  mov     r8, [rsp+0D8h+arg_10]
0x1400174e7  mov     rdx, cs:TmTransactionManagerObjectType
0x1400174ee  mov     cl, r15b
0x1400174f1  call    cs:__imp_ObCreateObject
0x1400174f8  nop     dword ptr [rax+rax+00h]
0x1400174fd  mov     ebx, eax
0x1400174ff  mov     [rsp+0D8h+var_88], eax
0x140017503  test    eax, eax
0x140017505  js      loc_1400175A3
0x14001750b  mov     rax, [rsp+0D8h+TransactionManager]
0x140017510  mov     [rax+40h], edi
0x140017513  mov     r9d, [rsp+0D8h+CreateOptions]; CreateOptions
0x14001751b  xor     r8d, r8d; TmId
0x14001751e  mov     rdx, r14; LogFileName
0x140017521  mov     rcx, [rsp+0D8h+TransactionManager]; TransactionManager
0x140017526  call    TmInitializeTransactionManagerExt
0x14001752b  mov     ebx, eax
0x14001752d  mov     [rsp+0D8h+var_88], eax
0x140017531  mov     rcx, [rsp+0D8h+TransactionManager]; Object
0x140017536  test    eax, eax
0x140017538  jns     short loc_140017548
0x14001753a  call    cs:__imp_ObfDereferenceObject
0x140017541  nop     dword ptr [rax+rax+00h]
0x140017546  jmp     short loc_1400175A3
0x140017548  lea     rax, [rsp+0D8h+var_50]
0x140017550  mov     [rsp+0D8h+Handle], rax; Handle
0x140017555  mov     [rsp+0D8h+NewObject], rdi; NewObject
0x14001755a  xor     r9d, r9d; ObjectPointerBias
0x14001755d  mov     r8d, r13d; DesiredAccess
0x140017560  xor     edx, edx; PassedAccessState
0x140017562  call    cs:__imp_ObInsertObject
0x140017569  nop     dword ptr [rax+rax+00h]
0x14001756e  mov     ebx, eax
0x140017570  mov     [rsp+0D8h+var_88], eax
0x140017574  test    eax, eax
0x140017576  js      short loc_1400175A3
0x140017578  mov     rax, [rsp+0D8h+var_50]
0x140017580  test    r15b, r15b
0x140017583  jz      short loc_140017592
0x140017585  mov     rdx, rax
0x140017588  mov     rcx, r12
0x14001758b  call    RtlWriteULong64ToUser
0x140017590  jmp     short loc_140017596
0x140017592  mov     [r12], rax
0x140017596  jmp     short loc_1400175A3
0x140017598  mov     ebx, eax
0x14001759a  mov     [rsp+0D8h+var_88], eax
0x14001759e  mov     rsi, [rsp+0D8h+P]
0x1400175a3  test    rsi, rsi
0x1400175a6  jz      short loc_1400175B9
0x1400175a8  xor     edx, edx; Tag
0x1400175aa  mov     rcx, rsi; P
0x1400175ad  call    cs:__imp_ExFreePoolWithTag
0x1400175b4  nop     dword ptr [rax+rax+00h]
0x1400175b9  mov     eax, ebx
0x1400175bb  jmp     loc_14001734D
0x14002279c  push    rbp
0x14002279e  sub     rsp, 50h
0x1400227a2  mov     rbp, rdx
0x1400227a5  call    cs:__imp_ExSystemExceptionFilter
0x1400227ac  nop     dword ptr [rax+rax+00h]
0x1400227b1  nop
0x1400227b2  add     rsp, 50h
0x1400227b6  pop     rbp
0x1400227b7  retn
0x1400227b9  push    rbp
0x1400227bb  sub     rsp, 50h
0x1400227bf  mov     rbp, rdx
0x1400227c2  mov     rax, gs:188h
0x1400227cb  mov     [rbp+98h], rax
0x1400227d2  mov     rax, [rbp+98h]
0x1400227d9  mov     cl, [rax+232h]
0x1400227df  mov     [rbp+54h], cl
0x1400227e2  mov     al, [rbp+54h]
0x1400227e5  xor     ecx, ecx
0x1400227e7  test    al, al
0x1400227e9  setnz   cl
0x1400227ec  mov     [rbp+80h], ecx
0x1400227f2  mov     eax, [rbp+80h]
0x1400227f8  add     rsp, 50h
0x1400227fc  pop     rbp
0x1400227fd  retn
0x1400227ff  push    rbp
0x140022801  sub     rsp, 50h
0x140022805  mov     rbp, rdx
0x140022808  mov     rcx, [rbp+60h]; P
0x14002280c  test    rcx, rcx
0x14002280f  jz      short loc_140022820
0x140022811  xor     edx, edx; Tag
0x140022813  call    cs:__imp_ExFreePoolWithTag
0x14002281a  nop     dword ptr [rax+rax+00h]
0x14002281f  nop
0x140022820  add     rsp, 50h
0x140022824  pop     rbp
0x140022825  retn
```
