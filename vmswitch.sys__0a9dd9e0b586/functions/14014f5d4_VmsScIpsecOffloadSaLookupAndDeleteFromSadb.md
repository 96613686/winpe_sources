# VmsScIpsecOffloadSaLookupAndDeleteFromSadb

- ea: `0x14014f5d4`
- end: `0x14014f89f`
- name: `VmsScIpsecOffloadSaLookupAndDeleteFromSadb`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14013ed6c`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14008a258`
- `0x1400953e8`
- `0x1400f2fa8`
- `0x14014f500`
- `0x14014f5d4`
- `0x140150d30`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014f678`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014f678`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f700`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f759`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f7ab`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f700`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f759`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014f7ab`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014f644`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014f644`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014f87b`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014f87b`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014f629`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014f629`

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
0x14014f5d4  mov     r11, rsp
0x14014f5d7  mov     [r11+10h], rbx
0x14014f5db  mov     [r11+18h], r8d
0x14014f5df  mov     [r11+8], rcx
0x14014f5e3  push    rbp
0x14014f5e4  push    rsi
0x14014f5e5  push    rdi
0x14014f5e6  push    r14
0x14014f5e8  push    r15
0x14014f5ea  sub     rsp, 70h
0x14014f5ee  xor     r15d, r15d
0x14014f5f1  lea     rcx, [r11+8]
0x14014f5f5  xor     eax, eax
0x14014f5f7  mov     [r11+18h], r15d
0x14014f5fb  xorps   xmm0, xmm0
0x14014f5fe  mov     rdi, r9
0x14014f601  movups  xmmword ptr [rsp+98h+Context.ChainHead], xmm0
0x14014f606  mov     [r11-38h], rax
0x14014f60a  mov     rbp, rdx
0x14014f60d  mov     esi, r15d
0x14014f610  call    VmsScpIpsecOffloadSaComputeHandlePlusPortSignature
0x14014f615  lea     r8, [rsp+98h+LockState]; LockState
0x14014f61d  mov     dl, 1; fWrite
0x14014f61f  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f626  mov     rbx, rax
0x14014f629  call    cs:__imp_NdisAcquireReadWriteLock
0x14014f630  nop     dword ptr [rax+rax+00h]
0x14014f635  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f63c  lea     r8, [rsp+98h+Context]; Context
0x14014f641  mov     rdx, rbx; Signature
0x14014f644  call    cs:__imp_RtlLookupEntryHashTable
0x14014f64b  nop     dword ptr [rax+rax+00h]
0x14014f650  mov     rdx, [rsp+98h+arg_0]
0x14014f658  test    rax, rax
0x14014f65b  jz      short loc_14014F689
0x14014f65d  mov     rsi, rax
0x14014f660  cmp     [rax+60h], rdx
0x14014f664  jnz     short loc_14014F66C
0x14014f666  cmp     [rax+70h], rbp
0x14014f66a  jz      short loc_14014F686
0x14014f66c  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f673  lea     rdx, [rsp+98h+Context]; Context
0x14014f678  call    cs:__imp_RtlGetNextEntryHashTable
0x14014f67f  nop     dword ptr [rax+rax+00h]
0x14014f684  jmp     short loc_14014F650
0x14014f686  mov     [rdi], rax
0x14014f689  cmp     [rdi], r15
0x14014f68c  jz      loc_14014F7EE
0x14014f692  mov     r14d, r15d
0x14014f695  lock inc dword ptr [rsi+68h]
0x14014f699  lock inc dword ptr [rsi+0BCh]
0x14014f6a0  mov     r10, cs:WPP_GLOBAL_Control
0x14014f6a7  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f6ae  mov     al, [r10+29h]
0x14014f6b2  dec     al
0x14014f6b4  cmp     al, 2
0x14014f6b6  ja      short loc_14014F6BF
0x14014f6b8  cmp     [r10+48h], r15w
0x14014f6bd  jz      short loc_14014F6F3
0x14014f6bf  mov     rcx, [rdi]
0x14014f6c2  mov     r9d, 1Bh
0x14014f6c8  mov     [rsp+98h+var_60], rbp
0x14014f6cd  xor     edx, edx
0x14014f6cf  mov     rax, [rcx+58h]
0x14014f6d3  lea     r8d, [r9-6]
0x14014f6d7  mov     [rsp+98h+var_68], rax
0x14014f6dc  mov     rax, [rcx+60h]
0x14014f6e0  mov     rcx, [r10+40h]
0x14014f6e4  mov     [rsp+98h+var_70], rax
0x14014f6e9  mov     [rsp+98h+var_78], rbx
0x14014f6ee  call    WPP_RECORDER_SF_qqq
0x14014f6f3  mov     rdx, [rdi]; Entry
0x14014f6f6  xor     r8d, r8d; Context
0x14014f6f9  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014f700  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f707  nop     dword ptr [rax+rax+00h]
0x14014f70c  lea     rbp, aSuccess; "success"
0x14014f713  mov     esi, 13h
0x14014f718  test    al, al
0x14014f71a  jnz     short loc_14014F73E
0x14014f71c  mov     rcx, cs:VmsIfrPortLog
0x14014f723  lea     r9d, [rsi+9]
0x14014f727  mov     [rsp+98h+var_70], rbp
0x14014f72c  mov     r8d, esi
0x14014f72f  mov     [rsp+98h+var_78], rbx
0x14014f734  call    WPP_RECORDER_SF_s
0x14014f739  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f73e  mov     rcx, [rdi]; P
0x14014f741  xor     edx, edx
0x14014f743  call    VmsScIpsecOffloadSaDeRef
0x14014f748  mov     rdx, [rdi]
0x14014f74b  xor     r8d, r8d; Context
0x14014f74e  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014f755  add     rdx, 30h ; '0'; Entry
0x14014f759  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f760  nop     dword ptr [rax+rax+00h]
0x14014f765  test    al, al
0x14014f767  jnz     short loc_14014F78D
0x14014f769  mov     rcx, cs:VmsIfrPortLog
0x14014f770  mov     r9d, 1Dh
0x14014f776  mov     [rsp+98h+var_70], rbp
0x14014f77b  mov     r8d, esi
0x14014f77e  mov     [rsp+98h+var_78], rbx
0x14014f783  call    WPP_RECORDER_SF_s
0x14014f788  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f78d  mov     rcx, [rdi]; P
0x14014f790  mov     edx, 1
0x14014f795  call    VmsScIpsecOffloadSaDeRef
0x14014f79a  mov     rdx, [rdi]
0x14014f79d  xor     r8d, r8d; Context
0x14014f7a0  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014f7a7  add     rdx, 18h; Entry
0x14014f7ab  call    cs:__imp_RtlRemoveEntryHashTable
0x14014f7b2  nop     dword ptr [rax+rax+00h]
0x14014f7b7  test    al, al
0x14014f7b9  jnz     short loc_14014F7DF
0x14014f7bb  mov     rcx, cs:VmsIfrPortLog
0x14014f7c2  mov     r9d, 1Eh
0x14014f7c8  mov     [rsp+98h+var_70], rbp
0x14014f7cd  mov     r8d, esi
0x14014f7d0  mov     [rsp+98h+var_78], rbx
0x14014f7d5  call    WPP_RECORDER_SF_s
0x14014f7da  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014f7df  mov     rcx, [rdi]; P
0x14014f7e2  mov     edx, 2
0x14014f7e7  call    VmsScIpsecOffloadSaDeRef
0x14014f7ec  jmp     short loc_14014F86C
0x14014f7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14014f7f5  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f7fc  mov     al, [rcx+29h]
0x14014f7ff  dec     al
0x14014f801  cmp     al, 2
0x14014f803  ja      short loc_14014F80C
0x14014f805  cmp     [rcx+48h], r15w
0x14014f80a  jz      short loc_14014F830
0x14014f80c  mov     rcx, [rcx+40h]
0x14014f810  mov     r9d, 1Ah
0x14014f816  mov     [rsp+98h+var_68], rbp
0x14014f81b  mov     [rsp+98h+var_70], rdx
0x14014f820  xor     edx, edx
0x14014f822  mov     [rsp+98h+var_78], rbx
0x14014f827  lea     r8d, [r9-5]
0x14014f82b  call    WPP_RECORDER_SF_qq
0x14014f830  mov     r14d, 0C0000008h
0x14014f836  mov     rcx, cs:VmsIfrPortLog
0x14014f83d  lea     rax, [rsp+98h+arg_0]
0x14014f845  mov     [rsp+98h+var_58], r14d
0x14014f84a  mov     r9d, 1Fh
0x14014f850  mov     dword ptr [rsp+98h+var_60], 6
0x14014f858  mov     [rsp+98h+var_68], rbp
0x14014f85d  mov     [rsp+98h+var_70], rax
0x14014f862  mov     [rsp+98h+var_78], rbx
0x14014f867  call    WPP_RECORDER_SF_qqLd
0x14014f86c  lea     rdx, [rsp+98h+LockState]; LockState
0x14014f874  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f87b  call    cs:__imp_NdisReleaseReadWriteLock
0x14014f882  nop     dword ptr [rax+rax+00h]
0x14014f887  mov     rbx, [rsp+98h+arg_8]
0x14014f88f  mov     eax, r14d
0x14014f892  add     rsp, 70h
0x14014f896  pop     r15
0x14014f898  pop     r14
0x14014f89a  pop     rdi
0x14014f89b  pop     rsi
0x14014f89c  pop     rbp
0x14014f89d  retn
```
