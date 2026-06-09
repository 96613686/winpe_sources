# VmsScIpsecOffloadSaLookupAndDeleteFromSadb

- ea: `0x14014f564`
- end: `0x14014f82f`
- name: `VmsScIpsecOffloadSaLookupAndDeleteFromSadb`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14013ecfc`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14008a258`
- `0x1400953e8`
- `0x1400f2f38`
- `0x14014f490`
- `0x14014f564`
- `0x140150cc0`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014f608`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014f608`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f690`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f6e9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f73b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f690`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f6e9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f73b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014f5d4`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014f5d4`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014f80b`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014f80b`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014f5b9`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014f5b9`

## pseudocode

```c
__int64 __fastcall VmsScIpsecOffloadSaLookupAndDeleteFromSadb(
        _LIST_ENTRY *a1,
        __int64 a2,
        __int64 a3,
        PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // rsi
  ULONG_PTR v7; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  int v9; // r8d
  int v10; // edx
  unsigned int v11; // r14d
  int v12; // edx
  int v13; // edx
  int v14; // edx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+50h] [rbp-48h] BYREF
  _LIST_ENTRY *v17; // [rsp+A0h] [rbp+8h] BYREF
  struct _LOCK_STATE LockState; // [rsp+B0h] [rbp+18h] BYREF

  v17 = a1;
  LockState = 0;
  memset(&Context, 0, sizeof(Context));
  v6 = 0;
  v7 = VmsScpIpsecOffloadSaComputeHandlePlusPortSignature(&v17);
  NdisAcquireReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, 1u, &LockState);
  for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredRoutine, v7, &Context);
        ;
        i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredRoutine, &Context) )
  {
    v10 = (int)v17;
    if ( !i )
      break;
    v6 = i;
    if ( i[4].Linkage.Flink == v17 && i[4].Signature == a2 )
    {
      *a4 = i;
      break;
    }
  }
  if ( *a4 )
  {
    v11 = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v6[4].Linkage.Blink);
    _InterlockedIncrement((volatile signed __int32 *)&v6[7].Signature + 1);
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_qqq(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        21,
        27,
        (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
        (char)(*a4)[4].Linkage.Flink,
        (*a4)[3].Signature,
        a2);
    if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredRoutine, *a4, 0) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        v12,
        19,
        28,
        (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
        (__int64)"success");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    VmsScIpsecOffloadSaDeRef(*a4);
    if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredContext, *a4 + 2, 0) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        v13,
        19,
        29,
        (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
        (__int64)"success");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    VmsScIpsecOffloadSaDeRef(*a4);
    if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.SystemArgument1, *a4 + 1, 0) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        v14,
        19,
        30,
        (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
        (__int64)"success");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    VmsScIpsecOffloadSaDeRef(*a4);
  }
  else
  {
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        21,
        26,
        (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
        v10,
        a2);
    v11 = -1073741816;
    WPP_RECORDER_SF_qqLd(
      VmsIfrPortLog,
      v10,
      v9,
      31,
      (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
      (char)&v17,
      a2,
      6,
      8);
  }
  NdisReleaseReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, &LockState);
  return v11;
}

```

## disassembly

```asm
0x14014f564  mov     r11, rsp
0x14014f567  mov     [r11+10h], rbx
0x14014f56b  mov     [r11+18h], r8d
0x14014f56f  mov     [r11+8], rcx
0x14014f573  push    rbp
0x14014f574  push    rsi
0x14014f575  push    rdi
0x14014f576  push    r14
0x14014f578  push    r15
0x14014f57a  sub     rsp, 70h
0x14014f57e  xor     r15d, r15d
0x14014f581  lea     rcx, [r11+8]
0x14014f585  xor     eax, eax
0x14014f587  mov     [r11+18h], r15d
0x14014f58b  xorps   xmm0, xmm0
0x14014f58e  mov     rdi, r9
0x14014f591  movups  xmmword ptr [rsp+98h+Context.ChainHead], xmm0
0x14014f596  mov     [r11-38h], rax
0x14014f59a  mov     rbp, rdx
0x14014f59d  mov     esi, r15d
0x14014f5a0  call    VmsScpIpsecOffloadSaComputeHandlePlusPortSignature
0x14014f5a5  lea     r8, [rsp+98h+LockState]; LockState
0x14014f5ad  mov     dl, 1; fWrite
0x14014f5af  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f5b6  mov     rbx, rax
0x14014f5b9  call    cs:__imp_NdisAcquireReadWriteLock
0x14014f5c0  nop     dword ptr [rax+rax+00h]
0x14014f5c5  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f5cc  lea     r8, [rsp+98h+Context]; Context
0x14014f5d1  mov     rdx, rbx; Signature
0x14014f5d4  call    cs:__imp_RtlLookupEntryHashTable
0x14014f5db  nop     dword ptr [rax+rax+00h]
0x14014f5e0  mov     rdx, [rsp+98h+arg_0]
0x14014f5e8  test    rax, rax
0x14014f5eb  jz      short loc_14014F619
0x14014f5ed  mov     rsi, rax
0x14014f5f0  cmp     [rax+60h], rdx
0x14014f5f4  jnz     short loc_14014F5FC
0x14014f5f6  cmp     [rax+70h], rbp
0x14014f5fa  jz      short loc_14014F616
0x14014f5fc  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f603  lea     rdx, [rsp+98h+Context]; Context
0x14014f608  call    cs:__imp_RtlGetNextEntryHashTable
0x14014f60f  nop     dword ptr [rax+rax+00h]
0x14014f614  jmp     short loc_14014F5E0
0x14014f616  mov     [rdi], rax
0x14014f619  cmp     [rdi], r15
0x14014f61c  jz      loc_14014F77E
0x14014f622  mov     r14d, r15d
0x14014f625  lock inc dword ptr [rsi+68h]
0x14014f629  lock inc dword ptr [rsi+0BCh]
0x14014f630  mov     r10, cs:WPP_GLOBAL_Control
0x14014f637  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f63e  mov     al, [r10+29h]
0x14014f642  dec     al
0x14014f644  cmp     al, 2
0x14014f646  ja      short loc_14014F64F
0x14014f648  cmp     [r10+48h], r15w
0x14014f64d  jz      short loc_14014F683
0x14014f64f  mov     rcx, [rdi]
0x14014f652  mov     r9d, 1Bh
0x14014f658  mov     [rsp+98h+var_60], rbp
0x14014f65d  xor     edx, edx
0x14014f65f  mov     rax, [rcx+58h]
0x14014f663  lea     r8d, [r9-6]
0x14014f667  mov     [rsp+98h+var_68], rax
0x14014f66c  mov     rax, [rcx+60h]
0x14014f670  mov     rcx, [r10+40h]
0x14014f674  mov     [rsp+98h+var_70], rax
0x14014f679  mov     [rsp+98h+var_78], rbx
0x14014f67e  call    WPP_RECORDER_SF_qqq
0x14014f683  mov     rdx, [rdi]; Entry
0x14014f686  xor     r8d, r8d; Context
0x14014f689  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f690  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f697  nop     dword ptr [rax+rax+00h]
0x14014f69c  lea     rbp, aSuccess; "success"
0x14014f6a3  mov     esi, 13h
0x14014f6a8  test    al, al
0x14014f6aa  jnz     short loc_14014F6CE
0x14014f6ac  mov     rcx, cs:VmsIfrPortLog
0x14014f6b3  lea     r9d, [rsi+9]
0x14014f6b7  mov     [rsp+98h+var_70], rbp
0x14014f6bc  mov     r8d, esi
0x14014f6bf  mov     [rsp+98h+var_78], rbx
0x14014f6c4  call    WPP_RECORDER_SF_s
0x14014f6c9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f6ce  mov     rcx, [rdi]; P
0x14014f6d1  xor     edx, edx
0x14014f6d3  call    VmsScIpsecOffloadSaDeRef
0x14014f6d8  mov     rdx, [rdi]
0x14014f6db  xor     r8d, r8d; Context
0x14014f6de  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014f6e5  add     rdx, 30h ; '0'; Entry
0x14014f6e9  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f6f0  nop     dword ptr [rax+rax+00h]
0x14014f6f5  test    al, al
0x14014f6f7  jnz     short loc_14014F71D
0x14014f6f9  mov     rcx, cs:VmsIfrPortLog
0x14014f700  mov     r9d, 1Dh
0x14014f706  mov     [rsp+98h+var_70], rbp
0x14014f70b  mov     r8d, esi
0x14014f70e  mov     [rsp+98h+var_78], rbx
0x14014f713  call    WPP_RECORDER_SF_s
0x14014f718  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f71d  mov     rcx, [rdi]; P
0x14014f720  mov     edx, 1
0x14014f725  call    VmsScIpsecOffloadSaDeRef
0x14014f72a  mov     rdx, [rdi]
0x14014f72d  xor     r8d, r8d; Context
0x14014f730  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014f737  add     rdx, 18h; Entry
0x14014f73b  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f742  nop     dword ptr [rax+rax+00h]
0x14014f747  test    al, al
0x14014f749  jnz     short loc_14014F76F
0x14014f74b  mov     rcx, cs:VmsIfrPortLog
0x14014f752  mov     r9d, 1Eh
0x14014f758  mov     [rsp+98h+var_70], rbp
0x14014f75d  mov     r8d, esi
0x14014f760  mov     [rsp+98h+var_78], rbx
0x14014f765  call    WPP_RECORDER_SF_s
0x14014f76a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f76f  mov     rcx, [rdi]; P
0x14014f772  mov     edx, 2
0x14014f777  call    VmsScIpsecOffloadSaDeRef
0x14014f77c  jmp     short loc_14014F7FC
0x14014f77e  mov     rcx, cs:WPP_GLOBAL_Control
0x14014f785  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f78c  mov     al, [rcx+29h]
0x14014f78f  dec     al
0x14014f791  cmp     al, 2
0x14014f793  ja      short loc_14014F79C
0x14014f795  cmp     [rcx+48h], r15w
0x14014f79a  jz      short loc_14014F7C0
0x14014f79c  mov     rcx, [rcx+40h]
0x14014f7a0  mov     r9d, 1Ah
0x14014f7a6  mov     [rsp+98h+var_68], rbp
0x14014f7ab  mov     [rsp+98h+var_70], rdx
0x14014f7b0  xor     edx, edx
0x14014f7b2  mov     [rsp+98h+var_78], rbx
0x14014f7b7  lea     r8d, [r9-5]
0x14014f7bb  call    WPP_RECORDER_SF_qq
0x14014f7c0  mov     r14d, 0C0000008h
0x14014f7c6  mov     rcx, cs:VmsIfrPortLog
0x14014f7cd  lea     rax, [rsp+98h+arg_0]
0x14014f7d5  mov     [rsp+98h+var_58], r14d
0x14014f7da  mov     r9d, 1Fh
0x14014f7e0  mov     dword ptr [rsp+98h+var_60], 6
0x14014f7e8  mov     [rsp+98h+var_68], rbp
0x14014f7ed  mov     [rsp+98h+var_70], rax
0x14014f7f2  mov     [rsp+98h+var_78], rbx
0x14014f7f7  call    WPP_RECORDER_SF_qqLd
0x14014f7fc  lea     rdx, [rsp+98h+LockState]; LockState
0x14014f804  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f80b  call    cs:__imp_NdisReleaseReadWriteLock
0x14014f812  nop     dword ptr [rax+rax+00h]
0x14014f817  mov     rbx, [rsp+98h+arg_8]
0x14014f81f  mov     eax, r14d
0x14014f822  add     rsp, 70h
0x14014f826  pop     r15
0x14014f828  pop     r14
0x14014f82a  pop     rdi
0x14014f82b  pop     rsi
0x14014f82c  pop     rbp
0x14014f82d  retn
```
