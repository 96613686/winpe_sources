# PktMonAttachProvider

- ea: `0x1401b63b0`
- end: `0x1401b64fa`
- name: `PktMonAttachProvider`
- size: `330`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400a5634`
- `0x1401b63b0`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401b6445`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401b6445`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401b6464`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401b6464`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401b63fb`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401b63fb`
- `ntoskrnl!KeReleaseMutex` at `0x1401b64e9`
- `ntoskrnl!KeReleaseMutex` at `0x1401b64e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b64bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b64bc`
- `NETIO!NmrClientAttachProvider` at `0x1401b648e`
- `NETIO!NmrClientAttachProvider` at `0x1401b648e`

## pseudocode

```c
__int64 __fastcall PktMonAttachProvider(HANDLE NmrBindingHandle, PVOID ClientBindingContext, __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  PVOID ProviderBindingContext; // [rsp+58h] [rbp+20h] BYREF

  ProviderBindingContext = 0;
  if ( (unsigned int)Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline()
    && (v6 = *(_QWORD *)(a3 + 32)) != 0
    && *(_WORD *)(v6 + 4) != 1
    || *((_QWORD *)&xmmword_1401FB3E0 + 1) )
  {
    v7 = -1073741127;
    goto LABEL_5;
  }
  if ( RunRef )
  {
    ExReInitializeRundownProtectionCacheAware(RunRef);
  }
  else
  {
    RunRef = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x72644D50u);
    if ( !RunRef )
    {
      v7 = -1073741801;
      goto LABEL_5;
    }
  }
  v7 = NmrClientAttachProvider(
         NmrBindingHandle,
         ClientBindingContext,
         &PktMonClientDispatch,
         &ProviderBindingContext,
         (const void **)&xmmword_1401FB3E0 + 1);
  if ( !v7 )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    *(_QWORD *)&xmmword_1401FB3E0 = ProviderBindingContext;
    ((void (*)(void))qword_1401FB3C8)();
    KeReleaseMutex(&PktMonCompMutex, 0);
    return v7;
  }
LABEL_5:
  if ( RunRef )
  {
    ExFreeCacheAwareRundownProtection(RunRef);
    RunRef = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1401b63b0  mov     [rsp+arg_0], rbx
0x1401b63b5  mov     [rsp+arg_8], rsi
0x1401b63ba  push    rdi
0x1401b63bb  sub     rsp, 30h
0x1401b63bf  mov     rbx, r8
0x1401b63c2  mov     [rsp+38h+ProviderBindingContext], 0
0x1401b63cb  mov     rdi, rdx
0x1401b63ce  mov     rsi, rcx
0x1401b63d1  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x1401b63d6  test    eax, eax
0x1401b63d8  jz      short loc_1401B6425
0x1401b63da  mov     rax, [rbx+20h]
0x1401b63de  test    rax, rax
0x1401b63e1  jz      short loc_1401B6425
0x1401b63e3  cmp     word ptr [rax+4], 1
0x1401b63e8  jz      short loc_1401B6425
0x1401b63ea  mov     ebx, 0C00002B9h
0x1401b63ef  mov     rcx, cs:RunRef; RunRefCacheAware
0x1401b63f6  test    rcx, rcx
0x1401b63f9  jz      short loc_1401B6412
0x1401b63fb  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401b6402  nop     dword ptr [rax+rax+00h]
0x1401b6407  mov     cs:RunRef, 0
0x1401b6412  mov     rsi, [rsp+38h+arg_8]
0x1401b6417  mov     eax, ebx
0x1401b6419  mov     rbx, [rsp+38h+arg_0]
0x1401b641e  add     rsp, 30h
0x1401b6422  pop     rdi
0x1401b6423  retn
0x1401b6425  cmp     qword ptr cs:xmmword_1401FB3E0+8, 0
0x1401b642d  jnz     short loc_1401B63EA
0x1401b642f  mov     rcx, cs:RunRef; RunRefCacheAware
0x1401b6436  test    rcx, rcx
0x1401b6439  jnz     short loc_1401B6464
0x1401b643b  mov     edx, 72644D50h; PoolTag
0x1401b6440  mov     ecx, 200h; PoolType
0x1401b6445  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401b644c  nop     dword ptr [rax+rax+00h]
0x1401b6451  mov     cs:RunRef, rax
0x1401b6458  test    rax, rax
0x1401b645b  jnz     short loc_1401B6470
0x1401b645d  mov     ebx, 0C0000017h
0x1401b6462  jmp     short loc_1401B63EF
0x1401b6464  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1401b646b  nop     dword ptr [rax+rax+00h]
0x1401b6470  lea     rax, xmmword_1401FB3E0+8
0x1401b6477  mov     rdx, rdi; ClientBindingContext
0x1401b647a  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x1401b647f  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x1401b6484  lea     r8, PktMonClientDispatch; ClientDispatch
0x1401b648b  mov     rcx, rsi; NmrBindingHandle
0x1401b648e  call    cs:__imp_NmrClientAttachProvider
0x1401b6495  nop     dword ptr [rax+rax+00h]
0x1401b649a  mov     ebx, eax
0x1401b649c  test    eax, eax
0x1401b649e  jnz     loc_1401B63EF
0x1401b64a4  xor     r9d, r9d; Alertable
0x1401b64a7  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x1401b64b0  xor     r8d, r8d; WaitMode
0x1401b64b3  lea     rcx, PktMonCompMutex; Object
0x1401b64ba  xor     edx, edx; WaitReason
0x1401b64bc  call    cs:__imp_KeWaitForSingleObject
0x1401b64c3  nop     dword ptr [rax+rax+00h]
0x1401b64c8  mov     rdx, [rsp+38h+ProviderBindingContext]
0x1401b64cd  mov     rax, cs:qword_1401FB3C8
0x1401b64d4  mov     qword ptr cs:xmmword_1401FB3E0, rdx
0x1401b64db  call    _guard_dispatch_icall
0x1401b64e0  xor     edx, edx; Wait
0x1401b64e2  lea     rcx, PktMonCompMutex; Mutex
0x1401b64e9  call    cs:__imp_KeReleaseMutex
0x1401b64f0  nop     dword ptr [rax+rax+00h]
0x1401b64f5  jmp     loc_1401B6412
```
