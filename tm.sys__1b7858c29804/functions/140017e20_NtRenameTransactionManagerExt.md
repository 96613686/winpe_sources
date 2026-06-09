# NtRenameTransactionManagerExt

- ea: `0x140017e20`
- end: `0x140017fc6`
- name: `NtRenameTransactionManagerExt`
- size: `422`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING LogFileName, LPGUID ExistingTransactionManagerGuid)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400024c2`
- `0x14000d198`
- `0x14000d1fc`
- `0x14000d238`
- `0x140015030`
- `0x140017e20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017fb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017fb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229e5`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017ef6`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140017ef6`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400229bd`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400229bd`
- `ntoskrnl!ProbeForRead` at `0x140017edc`
- `ntoskrnl!ProbeForRead` at `0x140017f46`
- `ntoskrnl!ProbeForRead` at `0x140017edc`
- `ntoskrnl!ProbeForRead` at `0x140017f46`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017e55`
- `ntoskrnl!PsIsComponentEnabled` at `0x140017e55`

## pseudocode

```c
NTSTATUS __stdcall NtRenameTransactionManagerExt(PUNICODE_STRING LogFileName, LPGUID ExistingTransactionManagerGuid)
{
  PVOID PoolWithQuotaTag; // rdi
  UNICODE_STRING *v5; // rsi
  int ULongFromUser; // eax
  __int16 v8; // r12
  NTSTATUS v9; // esi
  __int64 v10; // [rsp+0h] [rbp-A8h] BYREF
  PVOID P; // [rsp+20h] [rbp-88h]
  __int64 v12; // [rsp+28h] [rbp-80h]
  void *v13; // [rsp+30h] [rbp-78h]
  __int64 *v14; // [rsp+38h] [rbp-70h]
  volatile void *Address[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v16; // [rsp+50h] [rbp-58h]
  GUID ExistingTransactionManagerGuida; // [rsp+60h] [rbp-48h] BYREF

  v14 = &v10;
  *(_OWORD *)Address = 0;
  PoolWithQuotaTag = 0;
  P = 0;
  v5 = 0;
  if ( !(unsigned __int8)PsIsComponentEnabled(1) )
    return -1073741790;
  if ( *((_BYTE *)KeGetCurrentThread() + 562) )
  {
    v16 = 0;
    ULongFromUser = RtlReadULongFromUser(LogFileName);
    v8 = ULongFromUser;
    LODWORD(v16) = ULongFromUser;
    *((_QWORD *)&v16 + 1) = RtlReadULong64FromUser(&LogFileName->Buffer);
    *(_OWORD *)Address = v16;
    if ( v8 )
    {
      WORD1(Address[0]) = v8;
      ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
      PoolWithQuotaTag = ExAllocatePoolWithQuotaTag(PagedPool, LOWORD(Address[0]), 0x73436D54u);
      P = PoolWithQuotaTag;
      RtlCopyToUser(PoolWithQuotaTag, (void *)Address[1], LOWORD(Address[0]));
      Address[1] = PoolWithQuotaTag;
      v5 = (UNICODE_STRING *)Address;
      v13 = Address;
    }
    v12 = 1;
    ProbeForRead(ExistingTransactionManagerGuid, 1u, 4u);
    ExistingTransactionManagerGuida = *ExistingTransactionManagerGuid;
  }
  else
  {
    v5 = LogFileName;
    v13 = LogFileName;
    ExistingTransactionManagerGuida = *ExistingTransactionManagerGuid;
  }
  if ( v5 )
  {
    v9 = TmRenameTransactionManagerExt(v5, &ExistingTransactionManagerGuida);
    if ( PoolWithQuotaTag )
      ExFreePoolWithTag(PoolWithQuotaTag, 0);
    return v9;
  }
  else
  {
    local_unwind_0(v14, &loc_140017F90);
    return -1073741811;
  }
}

```

## disassembly

```asm
0x140017e20  push    rbx
0x140017e22  push    rsi
0x140017e23  push    rdi
0x140017e24  push    r12
0x140017e26  push    r13
0x140017e28  push    r14
0x140017e2a  push    r15
0x140017e2c  sub     rsp, 70h
0x140017e30  mov     [rsp+0A8h+var_70], rsp
0x140017e35  mov     r14, rdx
0x140017e38  mov     r15, rcx
0x140017e3b  xorps   xmm0, xmm0
0x140017e3e  movups  xmmword ptr [rsp+0A8h+Address], xmm0
0x140017e43  xor     ebx, ebx
0x140017e45  mov     edi, ebx
0x140017e47  mov     [rsp+0A8h+P], rbx
0x140017e4c  mov     esi, ebx
0x140017e4e  lea     r13d, [rbx+1]
0x140017e52  mov     ecx, r13d
0x140017e55  call    cs:__imp_PsIsComponentEnabled
0x140017e5c  nop     dword ptr [rax+rax+00h]
0x140017e61  test    al, al
0x140017e63  jnz     short loc_140017E7B
0x140017e65  mov     eax, 0C0000022h
0x140017e6a  add     rsp, 70h
0x140017e6e  pop     r15
0x140017e70  pop     r14
0x140017e72  pop     r13
0x140017e74  pop     r12
0x140017e76  pop     rdi
0x140017e77  pop     rsi
0x140017e78  pop     rbx
0x140017e79  retn
0x140017e7b  mov     rax, gs:188h
0x140017e84  cmp     [rax+232h], bl
0x140017e8a  jz      loc_140017F67
0x140017e90  xorps   xmm0, xmm0
0x140017e93  movups  [rsp+0A8h+var_58], xmm0
0x140017e98  mov     rcx, r15
0x140017e9b  call    RtlReadULongFromUser
0x140017ea0  mov     r12d, eax
0x140017ea3  mov     dword ptr [rsp+0A8h+var_58], eax
0x140017ea7  lea     rcx, [r15+8]
0x140017eab  call    RtlReadULong64FromUser
0x140017eb0  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x140017eb5  movaps  xmm0, [rsp+0A8h+var_58]
0x140017eba  movdqa  xmmword ptr [rsp+0A8h+Address], xmm0
0x140017ec0  test    r12w, r12w
0x140017ec4  jz      short loc_140017F2C
0x140017ec6  mov     word ptr [rsp+0A8h+Address+2], r12w
0x140017ecc  movzx   edx, word ptr [rsp+0A8h+Address]; Length
0x140017ed1  mov     r8d, 2; Alignment
0x140017ed7  mov     rcx, [rsp+0A8h+Address+8]; Address
0x140017edc  call    cs:__imp_ProbeForRead
0x140017ee3  nop     dword ptr [rax+rax+00h]
0x140017ee8  movzx   edx, word ptr [rsp+0A8h+Address]; NumberOfBytes
0x140017eed  mov     r8d, 73436D54h; Tag
0x140017ef3  mov     ecx, r13d; PoolType
0x140017ef6  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140017efd  nop     dword ptr [rax+rax+00h]
0x140017f02  mov     rdi, rax
0x140017f05  mov     [rsp+0A8h+P], rax
0x140017f0a  movzx   r8d, word ptr [rsp+0A8h+Address]; Size
0x140017f10  mov     rdx, [rsp+0A8h+Address+8]; Src
0x140017f15  mov     rcx, rax; void *
0x140017f18  call    RtlCopyToUser
0x140017f1d  mov     [rsp+0A8h+Address+8], rdi
0x140017f22  lea     rsi, [rsp+0A8h+Address]
0x140017f27  mov     [rsp+0A8h+var_78], rsi
0x140017f2c  mov     [rsp+0A8h+var_80], 10h
0x140017f35  mov     [rsp+0A8h+var_80], r13
0x140017f3a  mov     r8d, 4; Alignment
0x140017f40  mov     rdx, r13; Length
0x140017f43  mov     rcx, r14; Address
0x140017f46  call    cs:__imp_ProbeForRead
0x140017f4d  nop     dword ptr [rax+rax+00h]
0x140017f52  movups  xmm0, xmmword ptr [r14]
0x140017f56  movdqu  xmmword ptr [rsp+0A8h+ExistingTransactionManagerGuid.Data1], xmm0
0x140017f5c  jmp     short loc_140017F79
0x140017f5e  mov     esi, eax
0x140017f60  mov     rdi, [rsp+0A8h+P]
0x140017f65  jmp     short loc_140017FA9
0x140017f67  mov     rsi, r15
0x140017f6a  mov     [rsp+0A8h+var_78], r15
0x140017f6f  movups  xmm0, xmmword ptr [r14]
0x140017f73  movdqu  xmmword ptr [rsp+0A8h+ExistingTransactionManagerGuid.Data1], xmm0
0x140017f79  test    rsi, rsi
0x140017f7c  jnz     short loc_140017F9A
0x140017f7e  lea     rdx, loc_140017F90
0x140017f85  mov     rcx, [rsp+0A8h+var_70]
0x140017f8a  call    _local_unwind_0
0x140017f8f  nop
0x140017f90  mov     eax, 0C000000Dh
0x140017f95  jmp     loc_140017E6A
0x140017f9a  lea     rdx, [rsp+0A8h+ExistingTransactionManagerGuid]; ExistingTransactionManagerGuid
0x140017f9f  mov     rcx, rsi; LogFileName
0x140017fa2  call    TmRenameTransactionManagerExt
0x140017fa7  mov     esi, eax
0x140017fa9  test    rdi, rdi
0x140017fac  jz      short loc_140017FBF
0x140017fae  xor     edx, edx; Tag
0x140017fb0  mov     rcx, rdi; P
0x140017fb3  call    cs:__imp_ExFreePoolWithTag
0x140017fba  nop     dword ptr [rax+rax+00h]
0x140017fbf  mov     eax, esi
0x140017fc1  jmp     loc_140017E6A
0x1400229b4  push    rbp
0x1400229b6  sub     rsp, 20h
0x1400229ba  mov     rbp, rdx
0x1400229bd  call    cs:__imp_ExSystemExceptionFilter
0x1400229c4  nop     dword ptr [rax+rax+00h]
0x1400229c9  nop
0x1400229ca  add     rsp, 20h
0x1400229ce  pop     rbp
0x1400229cf  retn
0x1400229d1  push    rbp
0x1400229d3  sub     rsp, 20h
0x1400229d7  mov     rbp, rdx
0x1400229da  mov     rcx, [rbp+20h]; P
0x1400229de  test    rcx, rcx
0x1400229e1  jz      short loc_1400229F2
0x1400229e3  xor     edx, edx; Tag
0x1400229e5  call    cs:__imp_ExFreePoolWithTag
0x1400229ec  nop     dword ptr [rax+rax+00h]
0x1400229f1  nop
0x1400229f2  add     rsp, 20h
0x1400229f6  pop     rbp
0x1400229f7  retn
```
