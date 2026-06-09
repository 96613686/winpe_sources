# PktMonAttachProvider

- ea: `0x1401b6420`
- end: `0x1401b656a`
- name: `PktMonAttachProvider`
- size: `330`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400a5634`
- `0x1401b6420`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401b64b5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401b64b5`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401b64d4`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401b64d4`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401b646b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401b646b`
- `ntoskrnl!KeReleaseMutex` at `0x1401b6559`
- `ntoskrnl!KeReleaseMutex` at `0x1401b6559`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b652c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b652c`
- `NETIO!NmrClientAttachProvider` at `0x1401b64fe`
- `NETIO!NmrClientAttachProvider` at `0x1401b64fe`

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
0x1401b6420  mov     [rsp+arg_0], rbx
0x1401b6425  mov     [rsp+arg_8], rsi
0x1401b642a  push    rdi
0x1401b642b  sub     rsp, 30h
0x1401b642f  mov     rbx, r8
0x1401b6432  mov     [rsp+38h+ProviderBindingContext], 0
0x1401b643b  mov     rdi, rdx
0x1401b643e  mov     rsi, rcx
0x1401b6441  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x1401b6446  test    eax, eax
0x1401b6448  jz      short loc_1401B6495
0x1401b644a  mov     rax, [rbx+20h]
0x1401b644e  test    rax, rax
0x1401b6451  jz      short loc_1401B6495
0x1401b6453  cmp     word ptr [rax+4], 1
0x1401b6458  jz      short loc_1401B6495
0x1401b645a  mov     ebx, 0C00002B9h
0x1401b645f  mov     rcx, cs:RunRef; RunRefCacheAware
0x1401b6466  test    rcx, rcx
0x1401b6469  jz      short loc_1401B6482
0x1401b646b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401b6472  nop     dword ptr [rax+rax+00h]
0x1401b6477  mov     cs:RunRef, 0
0x1401b6482  mov     rsi, [rsp+38h+arg_8]
0x1401b6487  mov     eax, ebx
0x1401b6489  mov     rbx, [rsp+38h+arg_0]
0x1401b648e  add     rsp, 30h
0x1401b6492  pop     rdi
0x1401b6493  retn
0x1401b6495  cmp     qword ptr cs:xmmword_1401FB3E0+8, 0
0x1401b649d  jnz     short loc_1401B645A
0x1401b649f  mov     rcx, cs:RunRef; RunRefCacheAware
0x1401b64a6  test    rcx, rcx
0x1401b64a9  jnz     short loc_1401B64D4
0x1401b64ab  mov     edx, 72644D50h; PoolTag
0x1401b64b0  mov     ecx, 200h; PoolType
0x1401b64b5  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401b64bc  nop     dword ptr [rax+rax+00h]
0x1401b64c1  mov     cs:RunRef, rax
0x1401b64c8  test    rax, rax
0x1401b64cb  jnz     short loc_1401B64E0
0x1401b64cd  mov     ebx, 0C0000017h
0x1401b64d2  jmp     short loc_1401B645F
0x1401b64d4  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1401b64db  nop     dword ptr [rax+rax+00h]
0x1401b64e0  lea     rax, xmmword_1401FB3E0+8
0x1401b64e7  mov     rdx, rdi; ClientBindingContext
0x1401b64ea  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x1401b64ef  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x1401b64f4  lea     r8, PktMonClientDispatch; ClientDispatch
0x1401b64fb  mov     rcx, rsi; NmrBindingHandle
0x1401b64fe  call    cs:__imp_NmrClientAttachProvider
0x1401b6505  nop     dword ptr [rax+rax+00h]
0x1401b650a  mov     ebx, eax
0x1401b650c  test    eax, eax
0x1401b650e  jnz     loc_1401B645F
0x1401b6514  xor     r9d, r9d; Alertable
0x1401b6517  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x1401b6520  xor     r8d, r8d; WaitMode
0x1401b6523  lea     rcx, PktMonCompMutex; Object
0x1401b652a  xor     edx, edx; WaitReason
0x1401b652c  call    cs:__imp_KeWaitForSingleObject
0x1401b6533  nop     dword ptr [rax+rax+00h]
0x1401b6538  mov     rdx, [rsp+38h+ProviderBindingContext]
0x1401b653d  mov     rax, cs:qword_1401FB3C8
0x1401b6544  mov     qword ptr cs:xmmword_1401FB3E0, rdx
0x1401b654b  call    _guard_dispatch_icall
0x1401b6550  xor     edx, edx; Wait
0x1401b6552  lea     rcx, PktMonCompMutex; Mutex
0x1401b6559  call    cs:__imp_KeReleaseMutex
0x1401b6560  nop     dword ptr [rax+rax+00h]
0x1401b6565  jmp     loc_1401B6482
```
