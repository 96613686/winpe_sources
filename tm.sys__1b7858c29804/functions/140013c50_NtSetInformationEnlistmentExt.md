# NtSetInformationEnlistmentExt

- ea: `0x140013c50`
- end: `0x140013f0d`
- name: `NtSetInformationEnlistmentExt`
- size: `701`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass, PVOID EnlistmentInformation, ULONG EnlistmentInformationLength)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400014d4`
- `0x140002510`
- `0x140013c50`
- `0x14001b338`
- `0x14001b570`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140013da2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013da2`
- `ntoskrnl!KeReleaseMutex` at `0x140013ecd`
- `ntoskrnl!KeReleaseMutex` at `0x140013ee6`
- `ntoskrnl!KeReleaseMutex` at `0x140022210`
- `ntoskrnl!KeReleaseMutex` at `0x14002222d`
- `ntoskrnl!KeReleaseMutex` at `0x140013ecd`
- `ntoskrnl!KeReleaseMutex` at `0x140013ee6`
- `ntoskrnl!KeReleaseMutex` at `0x140022210`
- `ntoskrnl!KeReleaseMutex` at `0x14002222d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e92`
- `ntoskrnl!ObfDereferenceObject` at `0x140013efa`
- `ntoskrnl!ObfDereferenceObject` at `0x140022243`
- `ntoskrnl!ObfDereferenceObject` at `0x140013efa`
- `ntoskrnl!ObfDereferenceObject` at `0x140022243`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140013e17`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140013e17`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013d50`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013d50`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400221be`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400221be`
- `ntoskrnl!ProbeForRead` at `0x140013cff`
- `ntoskrnl!ProbeForRead` at `0x140013e56`
- `ntoskrnl!ProbeForRead` at `0x140013cff`
- `ntoskrnl!ProbeForRead` at `0x140013e56`

## pseudocode

```c
NTSTATUS __stdcall NtSetInformationEnlistmentExt(
        HANDLE EnlistmentHandle,
        ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass,
        PVOID EnlistmentInformation,
        ULONG EnlistmentInformationLength)
{
  SIZE_T v4; // r12
  __int64 v7; // r14
  KPROCESSOR_MODE v8; // r15
  int v9; // esi
  char *v10; // rdi
  void *v11; // rcx
  PVOID PoolWithQuotaTag; // rax
  void *v13; // rcx
  int v14; // [rsp+38h] [rbp-50h]
  int v15; // [rsp+3Ch] [rbp-4Ch]
  PVOID Object; // [rsp+58h] [rbp-30h] BYREF

  v4 = EnlistmentInformationLength;
  if ( EnlistmentInformationClass != EnlistmentRecoveryInformation )
    return -1073741821;
  if ( !EnlistmentInformationLength )
    return -1073741811;
  v15 = 0;
  v14 = 0;
  v7 = 0;
  if ( EnlistmentInformationLength > 0x10000 )
    return -1073740784;
  v8 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v8 )
    ProbeForRead(EnlistmentInformation, EnlistmentInformationLength, 1u);
  Object = 0;
  v9 = ObReferenceObjectByHandle(EnlistmentHandle, 2u, (POBJECT_TYPE)TmEnlistmentObjectType, v8, &Object, 0);
  v10 = (char *)Object;
  if ( v9 >= 0 )
  {
    v7 = *((_QWORD *)Object + 20);
    TmpAcquireTransactionMutex(v7);
    v14 = 1;
    KeWaitForSingleObject(v10 + 64, Executive, 0, 0, 0);
    v15 = 1;
    if ( TmIsTransactionActiveExt((PKTRANSACTION)v7) || *(_DWORD *)(v7 + 192) == 10 )
    {
      v11 = (void *)*((_QWORD *)v10 + 25);
      if ( v11 )
      {
        ExFreePoolWithTag(v11, 0);
        *((_QWORD *)v10 + 25) = 0;
        *((_DWORD *)v10 + 52) = 0;
      }
      PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)9, v4, 0x69526D54u);
      *((_QWORD *)v10 + 25) = PoolWithQuotaTag;
      if ( PoolWithQuotaTag )
      {
        *((_DWORD *)v10 + 52) = v4;
        if ( v8 )
          ProbeForRead(EnlistmentInformation, v4, 1u);
        v13 = (void *)*((_QWORD *)v10 + 25);
        if ( v8 )
          RtlCopyFromUser(v13, EnlistmentInformation, v4);
        else
          RtlCopyVolatileMemory(v13, EnlistmentInformation, v4);
      }
      else
      {
        v9 = -1073741670;
      }
    }
    else
    {
      v9 = -1072103421;
    }
  }
  if ( v14 )
    KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v7 + 88) + 32LL), 0);
  if ( v15 )
    KeReleaseMutex((PRKMUTEX)(v10 + 64), 0);
  if ( v10 )
    ObfDereferenceObject(v10);
  return v9;
}

```

## disassembly

```asm
0x140013c50  mov     [rsp+arg_0], rsi
0x140013c55  mov     [rsp+Address], r8
0x140013c5a  push    rdi
0x140013c5b  push    r12
0x140013c5d  push    r13
0x140013c5f  push    r14
0x140013c61  push    r15
0x140013c63  sub     rsp, 60h
0x140013c67  mov     r12d, r9d
0x140013c6a  mov     r9, r8
0x140013c6d  mov     rdi, rcx
0x140013c70  mov     r13d, 1
0x140013c76  cmp     edx, r13d
0x140013c79  jz      short loc_140013C97
0x140013c7b  mov     eax, 0C0000003h
0x140013c80  mov     rsi, [rsp+88h+arg_0]
0x140013c88  add     rsp, 60h
0x140013c8c  pop     r15
0x140013c8e  pop     r14
0x140013c90  pop     r13
0x140013c92  pop     r12
0x140013c94  pop     rdi
0x140013c95  retn
0x140013c97  test    r12d, r12d
0x140013c9a  jnz     short loc_140013CA3
0x140013c9c  mov     eax, 0C000000Dh
0x140013ca1  jmp     short loc_140013C80
0x140013ca3  mov     [rsp+88h+var_40], 0
0x140013cac  mov     [rsp+88h+var_4C], 0
0x140013cb4  mov     [rsp+88h+var_50], 0
0x140013cbc  xor     r14d, r14d
0x140013cbf  mov     [rsp+88h+var_38], r14
0x140013cc4  cmp     r12d, 10000h
0x140013ccb  jbe     short loc_140013CD4
0x140013ccd  mov     eax, 0C0000410h
0x140013cd2  jmp     short loc_140013C80
0x140013cd4  mov     rax, gs:188h
0x140013cdd  mov     r15b, [rax+232h]
0x140013ce4  mov     [rsp+88h+arg_8], r15b
0x140013cec  mov     [rsp+88h+var_58], r15b
0x140013cf1  test    r15b, r15b
0x140013cf4  jz      short loc_140013D22
0x140013cf6  mov     rdx, r12; Length
0x140013cf9  mov     r8d, r13d; Alignment
0x140013cfc  mov     rcx, r9; Address
0x140013cff  call    cs:__imp_ProbeForRead
0x140013d06  nop     dword ptr [rax+rax+00h]
0x140013d0b  jmp     short loc_140013D22
0x140013d0d  mov     esi, eax
0x140013d0f  mov     [rsp+88h+var_54], eax
0x140013d13  mov     rdi, [rsp+88h+var_40]
0x140013d18  mov     r14, [rsp+88h+var_38]
0x140013d1d  jmp     loc_140013EBC
0x140013d22  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x140013d29  mov     [rsp+88h+var_30], 0
0x140013d32  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x140013d3b  lea     rax, [rsp+88h+var_30]
0x140013d40  mov     [rsp+88h+Object], rax; Object
0x140013d45  mov     r9b, r15b; AccessMode
0x140013d48  mov     edx, 2; DesiredAccess
0x140013d4d  mov     rcx, rdi; Handle
0x140013d50  call    cs:__imp_ObReferenceObjectByHandle
0x140013d57  nop     dword ptr [rax+rax+00h]
0x140013d5c  mov     esi, eax
0x140013d5e  mov     rdi, [rsp+88h+var_30]
0x140013d63  mov     [rsp+88h+var_40], rdi
0x140013d68  mov     [rsp+88h+var_54], eax
0x140013d6c  test    eax, eax
0x140013d6e  js      loc_140013EBC
0x140013d74  mov     r14, [rdi+0A0h]
0x140013d7b  mov     [rsp+88h+var_38], r14
0x140013d80  mov     rcx, r14
0x140013d83  call    TmpAcquireTransactionMutex
0x140013d88  mov     [rsp+88h+var_50], r13d
0x140013d8d  lea     rcx, [rdi+40h]; Object
0x140013d91  mov     [rsp+88h+Object], 0; Timeout
0x140013d9a  xor     r9d, r9d; Alertable
0x140013d9d  xor     r8d, r8d; WaitMode
0x140013da0  xor     edx, edx; WaitReason
0x140013da2  call    cs:__imp_KeWaitForSingleObject
0x140013da9  nop     dword ptr [rax+rax+00h]
0x140013dae  mov     [rsp+88h+var_4C], r13d
0x140013db3  mov     rcx, r14; Transaction
0x140013db6  call    TmIsTransactionActiveExt
0x140013dbb  test    al, al
0x140013dbd  jnz     short loc_140013DD7
0x140013dbf  cmp     dword ptr [r14+0C0h], 0Ah
0x140013dc7  jz      short loc_140013DD7
0x140013dc9  mov     esi, 0C0190003h
0x140013dce  mov     [rsp+88h+var_54], esi
0x140013dd2  jmp     loc_140013E80
0x140013dd7  mov     rcx, [rdi+0C8h]; P
0x140013dde  test    rcx, rcx
0x140013de1  jz      short loc_140013E06
0x140013de3  xor     edx, edx; Tag
0x140013de5  call    cs:__imp_ExFreePoolWithTag
0x140013dec  nop     dword ptr [rax+rax+00h]
0x140013df1  mov     qword ptr [rdi+0C8h], 0
0x140013dfc  mov     dword ptr [rdi+0D0h], 0
0x140013e06  mov     r13, r12
0x140013e09  mov     r8d, 69526D54h; Tag
0x140013e0f  mov     rdx, r12; NumberOfBytes
0x140013e12  mov     ecx, 9; PoolType
0x140013e17  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140013e1e  nop     dword ptr [rax+rax+00h]
0x140013e23  mov     [rdi+0C8h], rax
0x140013e2a  test    rax, rax
0x140013e2d  jnz     short loc_140013E36
0x140013e2f  mov     esi, 0C000009Ah
0x140013e34  jmp     short loc_140013DCE
0x140013e36  mov     [rdi+0D0h], r12d
0x140013e3d  mov     r12, [rsp+88h+Address]
0x140013e45  test    r15b, r15b
0x140013e48  jz      short loc_140013E62
0x140013e4a  mov     r8d, 1; Alignment
0x140013e50  mov     rdx, r13; Length
0x140013e53  mov     rcx, r12; Address
0x140013e56  call    cs:__imp_ProbeForRead
0x140013e5d  nop     dword ptr [rax+rax+00h]
0x140013e62  mov     rcx, [rdi+0C8h]; void *
0x140013e69  mov     r8, r13; Size
0x140013e6c  mov     rdx, r12; Src
0x140013e6f  test    r15b, r15b
0x140013e72  jz      short loc_140013E7B
0x140013e74  call    RtlCopyFromUser
0x140013e79  jmp     short loc_140013E80
0x140013e7b  call    RtlCopyVolatileMemory
0x140013e80  jmp     short loc_140013EBC
0x140013e82  mov     esi, eax
0x140013e84  xor     edx, edx; Tag
0x140013e86  mov     rdi, [rsp+88h+var_40]
0x140013e8b  mov     rcx, [rdi+0C8h]; P
0x140013e92  call    cs:__imp_ExFreePoolWithTag
0x140013e99  nop     dword ptr [rax+rax+00h]
0x140013e9e  mov     qword ptr [rdi+0C8h], 0
0x140013ea9  mov     dword ptr [rdi+0D0h], 0
0x140013eb3  mov     [rsp+88h+var_54], esi
0x140013eb7  mov     r14, [rsp+88h+var_38]
0x140013ebc  cmp     [rsp+88h+var_50], 0
0x140013ec1  jz      short loc_140013ED9
0x140013ec3  mov     rcx, [r14+58h]
0x140013ec7  add     rcx, 20h ; ' '; Mutex
0x140013ecb  xor     edx, edx; Wait
0x140013ecd  call    cs:__imp_KeReleaseMutex
0x140013ed4  nop     dword ptr [rax+rax+00h]
0x140013ed9  cmp     [rsp+88h+var_4C], 0
0x140013ede  jz      short loc_140013EF2
0x140013ee0  lea     rcx, [rdi+40h]; Mutex
0x140013ee4  xor     edx, edx; Wait
0x140013ee6  call    cs:__imp_KeReleaseMutex
0x140013eed  nop     dword ptr [rax+rax+00h]
0x140013ef2  test    rdi, rdi
0x140013ef5  jz      short loc_140013F06
0x140013ef7  mov     rcx, rdi; Object
0x140013efa  call    cs:__imp_ObfDereferenceObject
0x140013f01  nop     dword ptr [rax+rax+00h]
0x140013f06  mov     eax, esi
0x140013f08  jmp     loc_140013C80
0x1400221b5  push    rbp
0x1400221b7  sub     rsp, 30h
0x1400221bb  mov     rbp, rdx
0x1400221be  call    cs:__imp_ExSystemExceptionFilter
0x1400221c5  nop     dword ptr [rax+rax+00h]
0x1400221ca  nop
0x1400221cb  add     rsp, 30h
0x1400221cf  pop     rbp
0x1400221d0  retn
0x1400221d2  push    rbp
0x1400221d4  sub     rsp, 30h
0x1400221d8  mov     rbp, rdx
0x1400221db  xor     eax, eax
0x1400221dd  cmp     [rbp+98h], al
0x1400221e3  setnz   al
0x1400221e6  mov     [rbp+40h], eax
0x1400221e9  mov     eax, [rbp+40h]
0x1400221ec  add     rsp, 30h
0x1400221f0  pop     rbp
0x1400221f1  retn
0x1400221f3  push    rbp
0x1400221f5  sub     rsp, 30h
0x1400221f9  mov     rbp, rdx
0x1400221fc  cmp     dword ptr [rbp+38h], 0
0x140022200  jz      short loc_14002221D
0x140022202  mov     rax, [rbp+50h]
0x140022206  mov     rcx, [rax+58h]
0x14002220a  add     rcx, 20h ; ' '; Mutex
0x14002220e  xor     edx, edx; Wait
0x140022210  call    cs:__imp_KeReleaseMutex
0x140022217  nop     dword ptr [rax+rax+00h]
0x14002221c  nop
0x14002221d  cmp     dword ptr [rbp+3Ch], 0
0x140022221  jz      short loc_14002223A
0x140022223  mov     rcx, [rbp+48h]
0x140022227  add     rcx, 40h ; '@'; Mutex
0x14002222b  xor     edx, edx; Wait
0x14002222d  call    cs:__imp_KeReleaseMutex
0x140022234  nop     dword ptr [rax+rax+00h]
0x140022239  nop
0x14002223a  mov     rcx, [rbp+48h]; Object
0x14002223e  test    rcx, rcx
0x140022241  jz      short loc_140022250
0x140022243  call    cs:__imp_ObfDereferenceObject
0x14002224a  nop     dword ptr [rax+rax+00h]
0x14002224f  nop
0x140022250  add     rsp, 30h
0x140022254  pop     rbp
0x140022255  retn
```
