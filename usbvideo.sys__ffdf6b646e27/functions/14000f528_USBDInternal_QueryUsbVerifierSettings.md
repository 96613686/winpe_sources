# USBDInternal_QueryUsbVerifierSettings

- ea: `0x14000f528`
- end: `0x14000f899`
- name: `USBDInternal_QueryUsbVerifierSettings`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000efa4`

## callees

- `0x14000f528`
- `0x14001aba0`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x14000f805`
- `ntoskrnl!ZwClose` at `0x14000f873`
- `ntoskrnl!ZwClose` at `0x14000f873`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f57c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f7d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f57c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f7d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f845`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f85e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f845`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f85e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f61a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f61a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f58c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f7e4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f58c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f7e4`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000f561`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000f561`
- `ntoskrnl!DbgPrintEx` at `0x14000f5de`
- `ntoskrnl!DbgPrintEx` at `0x14000f646`
- `ntoskrnl!DbgPrintEx` at `0x14000f831`
- `ntoskrnl!DbgPrintEx` at `0x14000f5de`
- `ntoskrnl!DbgPrintEx` at `0x14000f646`
- `ntoskrnl!DbgPrintEx` at `0x14000f831`

## string_xrefs

- `0x14000f56d`: `IoOpenDriverRegistryKey`
- `0x14000f7ab`: `RtlQueryRegistryValuesEx`
- `0x14000f5d1`: `IoOpenDriverRegistryKey failed with 0x%x\n`
- `0x14000f824`: `RtlQueryRegistrySettings failed, ignoring this error0x%x\n`

## pseudocode

```c
void __fastcall USBDInternal_QueryUsbVerifierSettings(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  struct _DRIVER_OBJECT *v4; // rcx
  PVOID v5; // r14
  PVOID SystemRoutineAddress; // rax
  PVOID v8; // r15
  int v9; // eax
  int v10; // eax
  _QWORD *PoolWithTag; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rax
  HANDLE v14; // rdi
  PVOID v15; // rax
  int v16; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-10h] BYREF
  PVOID P; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+38h] BYREF

  v3 = a2 + 72;
  v4 = *(struct _DRIVER_OBJECT **)(a1 + 8);
  v5 = 0;
  P = 0;
  Handle = 0;
  DestinationString = 0;
  *(_DWORD *)(a2 + 72) = MmIsDriverVerifying(v4);
  RtlInitUnicodeString(&DestinationString, L"IoOpenDriverRegistryKey");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  v8 = SystemRoutineAddress;
  if ( SystemRoutineAddress )
  {
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))SystemRoutineAddress)(
           *(_QWORD *)(a1 + 8),
           0,
           1,
           0,
           &Handle);
    if ( v9 < 0 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "IoOpenDriverRegistryKey failed with 0x%x\n", v9);
      goto LABEL_19;
    }
    goto LABEL_6;
  }
  v10 = USBDInternal_BuildServicePath(a1, &P);
  v5 = P;
  if ( v10 >= 0 )
  {
LABEL_6:
    PoolWithTag = ExAllocatePoolWithTag(PoolType, 0x1C0u, 0x56425355u);
    v12 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x1C0u);
      v12[3] = v3;
      *v12 = USBD_VerifierSettingsCallback;
      v12[2] = L"UsbVerifierEnabled";
      *((_DWORD *)v12 + 8) = 4;
      *((_DWORD *)v12 + 12) = 4;
      v12[5] = v3;
      v12[9] = L"UsbVerifierFailRegistration";
      v12[10] = a2 + 76;
      v12[12] = a2 + 76;
      v12[7] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 22) = 4;
      *((_DWORD *)v12 + 26) = 4;
      v12[16] = L"UsbVerifierFailChainedMdlSupport";
      v12[17] = a2 + 80;
      v12[19] = a2 + 80;
      v12[14] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 36) = 4;
      *((_DWORD *)v12 + 40) = 4;
      v12[23] = L"UsbVerifierFailStaticStreamSupport";
      v12[24] = a2 + 84;
      v12[26] = a2 + 84;
      v12[21] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 50) = 4;
      *((_DWORD *)v12 + 54) = 4;
      v12[30] = L"UsbVerifierStaticStreamCountOverride";
      v12[31] = a2 + 88;
      v12[33] = a2 + 88;
      v12[28] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 64) = 4;
      *((_DWORD *)v12 + 68) = 4;
      v12[37] = L"UsbVerifierFailEnableStaticStreams";
      v12[38] = a2 + 92;
      v12[40] = a2 + 92;
      v12[35] = USBD_VerifierSettingsCallback;
      *((_DWORD *)v12 + 78) = 4;
      *((_DWORD *)v12 + 82) = 4;
      v12[44] = L"UsbVerifierFailSecureTransferSupport";
      v13 = a2 + 160;
      v12[42] = USBD_VerifierSettingsCallback;
      v14 = v5;
      *((_DWORD *)v12 + 92) = 4;
      *((_DWORD *)v12 + 96) = 4;
      v12[45] = v13;
      v12[47] = v13;
      if ( v8 )
        v14 = Handle;
      SystemRoutineName = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      v15 = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !v15 )
        v15 = RtlQueryRegistryValues;
      v16 = ((__int64 (__fastcall *)(_QWORD, HANDLE, _QWORD *, _QWORD, _QWORD))v15)(
              v8 != 0 ? 0x40000000 : 1,
              v14,
              v12,
              0,
              0);
      if ( v16 < 0 && g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "RtlQueryRegistrySettings failed, ignoring this error0x%x\n", v16);
      ExFreePoolWithTag(v12, 0x56425355u);
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "ExAllocatePoolWithTag for USBDInternal_QueryUsbVerifierSettings failed\n");
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x56425355u);
LABEL_19:
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x14000f528  mov     [rsp-28h+arg_10], rbx
0x14000f52d  mov     [rsp-28h+arg_18], rsi
0x14000f532  push    rbp
0x14000f533  push    rdi
0x14000f534  push    r12
0x14000f536  push    r14
0x14000f538  push    r15
0x14000f53a  mov     rbp, rsp
0x14000f53d  sub     rsp, 50h
0x14000f541  mov     rbx, rcx
0x14000f544  lea     r12, [rdx+48h]
0x14000f548  mov     rcx, [rcx+8]; DriverObject
0x14000f54c  xor     r14d, r14d
0x14000f54f  xorps   xmm0, xmm0
0x14000f552  mov     [rbp+P], r14
0x14000f556  mov     [rbp+Handle], r14
0x14000f55a  mov     rdi, rdx
0x14000f55d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000f561  call    cs:__imp_MmIsDriverVerifying
0x14000f568  nop     dword ptr [rax+rax+00h]
0x14000f56d  lea     rdx, SourceString; "IoOpenDriverRegistryKey"
0x14000f574  mov     [r12], eax
0x14000f578  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f57c  call    cs:__imp_RtlInitUnicodeString
0x14000f583  nop     dword ptr [rax+rax+00h]
0x14000f588  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f58c  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f593  nop     dword ptr [rax+rax+00h]
0x14000f598  mov     r15, rax
0x14000f59b  test    rax, rax
0x14000f59e  jz      short loc_14000F5EF
0x14000f5a0  mov     rcx, [rbx+8]
0x14000f5a4  lea     rax, [rbp+Handle]
0x14000f5a8  mov     [rsp+50h+var_30], rax
0x14000f5ad  lea     r8d, [r14+1]
0x14000f5b1  mov     rax, r15
0x14000f5b4  xor     r9d, r9d
0x14000f5b7  xor     edx, edx
0x14000f5b9  call    _guard_dispatch_icall
0x14000f5be  test    eax, eax
0x14000f5c0  jns     short loc_14000F607
0x14000f5c2  cmp     cs:g_EnableDbgPrints, r14b
0x14000f5c9  jz      loc_14000F86A
0x14000f5cf  xor     edx, edx; Level
0x14000f5d1  lea     r8, aIoopendriverre; "IoOpenDriverRegistryKey failed with 0x%"...
0x14000f5d8  mov     r9d, eax
0x14000f5db  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f5de  call    cs:__imp_DbgPrintEx
0x14000f5e5  nop     dword ptr [rax+rax+00h]
0x14000f5ea  jmp     loc_14000F86A
0x14000f5ef  lea     rdx, [rbp+P]
0x14000f5f3  mov     rcx, rbx
0x14000f5f6  call    USBDInternal_BuildServicePath
0x14000f5fb  mov     r14, [rbp+P]
0x14000f5ff  test    eax, eax
0x14000f601  js      loc_14000F851
0x14000f607  mov     ecx, cs:PoolType; PoolType
0x14000f60d  mov     ebx, 1C0h
0x14000f612  mov     edx, ebx; NumberOfBytes
0x14000f614  mov     r8d, 56425355h; Tag
0x14000f61a  call    cs:__imp_ExAllocatePoolWithTag
0x14000f621  nop     dword ptr [rax+rax+00h]
0x14000f626  mov     rsi, rax
0x14000f629  test    rax, rax
0x14000f62c  jnz     short loc_14000F657
0x14000f62e  cmp     cs:g_EnableDbgPrints, al
0x14000f634  jz      loc_14000F851
0x14000f63a  lea     r8, aExallocatepool; "ExAllocatePoolWithTag for USBDInternal_"...
0x14000f641  xor     edx, edx; Level
0x14000f643  lea     ecx, [rax+4Dh]; ComponentId
0x14000f646  call    cs:__imp_DbgPrintEx
0x14000f64d  nop     dword ptr [rax+rax+00h]
0x14000f652  jmp     loc_14000F851
0x14000f657  mov     r8, rbx; Size
0x14000f65a  xor     edx, edx; Val
0x14000f65c  mov     rcx, rsi; void *
0x14000f65f  call    memset
0x14000f664  mov     [rsi+18h], r12
0x14000f668  lea     rcx, USBD_VerifierSettingsCallback
0x14000f66f  mov     [rsi], rcx
0x14000f672  lea     rax, aUsbverifierena; "UsbVerifierEnabled"
0x14000f679  mov     [rsi+10h], rax
0x14000f67d  mov     edx, 4
0x14000f682  mov     [rsi+20h], edx
0x14000f685  lea     rax, aUsbverifierfai_3; "UsbVerifierFailRegistration"
0x14000f68c  mov     [rsi+30h], edx
0x14000f68f  test    r15, r15
0x14000f692  mov     [rsi+28h], r12
0x14000f696  xorps   xmm0, xmm0
0x14000f699  mov     [rsi+48h], rax
0x14000f69d  lea     rax, [rdi+4Ch]
0x14000f6a1  mov     [rsi+50h], rax
0x14000f6a5  mov     [rsi+60h], rax
0x14000f6a9  lea     rax, aUsbverifierfai_1; "UsbVerifierFailChainedMdlSupport"
0x14000f6b0  mov     [rsi+38h], rcx
0x14000f6b4  mov     [rsi+58h], edx
0x14000f6b7  mov     [rsi+68h], edx
0x14000f6ba  mov     [rsi+80h], rax
0x14000f6c1  lea     rax, [rdi+50h]
0x14000f6c5  mov     [rsi+88h], rax
0x14000f6cc  mov     [rsi+98h], rax
0x14000f6d3  lea     rax, aUsbverifierfai_2; "UsbVerifierFailStaticStreamSupport"
0x14000f6da  mov     [rsi+70h], rcx
0x14000f6de  mov     [rsi+90h], edx
0x14000f6e4  mov     [rsi+0A0h], edx
0x14000f6ea  mov     [rsi+0B8h], rax
0x14000f6f1  lea     rax, [rdi+54h]
0x14000f6f5  mov     [rsi+0C0h], rax
0x14000f6fc  mov     [rsi+0D0h], rax
0x14000f703  lea     rax, aUsbverifiersta; "UsbVerifierStaticStreamCountOverride"
0x14000f70a  mov     [rsi+0A8h], rcx
0x14000f711  mov     [rsi+0C8h], edx
0x14000f717  mov     [rsi+0D8h], edx
0x14000f71d  mov     [rsi+0F0h], rax
0x14000f724  lea     rax, [rdi+58h]
0x14000f728  mov     [rsi+0F8h], rax
0x14000f72f  mov     [rsi+108h], rax
0x14000f736  lea     rax, aUsbverifierfai_0; "UsbVerifierFailEnableStaticStreams"
0x14000f73d  mov     [rsi+0E0h], rcx
0x14000f744  mov     [rsi+100h], edx
0x14000f74a  mov     [rsi+110h], edx
0x14000f750  mov     [rsi+128h], rax
0x14000f757  lea     rax, [rdi+5Ch]
0x14000f75b  mov     [rsi+130h], rax
0x14000f762  mov     [rsi+140h], rax
0x14000f769  lea     rax, aUsbverifierfai; "UsbVerifierFailSecureTransferSupport"
0x14000f770  mov     [rsi+118h], rcx
0x14000f777  mov     [rsi+138h], edx
0x14000f77d  mov     [rsi+148h], edx
0x14000f783  mov     [rsi+160h], rax
0x14000f78a  lea     rax, [rdi+0A0h]
0x14000f791  mov     [rsi+150h], rcx
0x14000f798  mov     rdi, r14
0x14000f79b  mov     [rsi+170h], edx
0x14000f7a1  lea     rcx, [rbp+SystemRoutineName]; DestinationString
0x14000f7a5  mov     [rsi+180h], edx
0x14000f7ab  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000f7b2  mov     [rsi+168h], rax
0x14000f7b9  mov     [rsi+178h], rax
0x14000f7c0  cmovnz  rdi, [rbp+Handle]
0x14000f7c5  neg     r15
0x14000f7c8  movups  xmmword ptr [rbp+SystemRoutineName.Length], xmm0
0x14000f7cc  sbb     ebx, ebx
0x14000f7ce  and     ebx, 3FFFFFFFh
0x14000f7d4  call    cs:__imp_RtlInitUnicodeString
0x14000f7db  nop     dword ptr [rax+rax+00h]
0x14000f7e0  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000f7e4  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f7eb  nop     dword ptr [rax+rax+00h]
0x14000f7f0  mov     [rsp+50h+var_30], 0
0x14000f7f9  lea     ecx, [rbx+1]
0x14000f7fc  test    rax, rax
0x14000f7ff  mov     r8, rsi
0x14000f802  mov     rdx, rdi
0x14000f805  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000f80d  xor     r9d, r9d
0x14000f810  call    _guard_dispatch_icall
0x14000f815  test    eax, eax
0x14000f817  jns     short loc_14000F83D
0x14000f819  cmp     cs:g_EnableDbgPrints, 0
0x14000f820  jz      short loc_14000F83D
0x14000f822  xor     edx, edx; Level
0x14000f824  lea     r8, aRtlqueryregist_0; "RtlQueryRegistrySettings failed, ignori"...
0x14000f82b  mov     r9d, eax
0x14000f82e  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f831  call    cs:__imp_DbgPrintEx
0x14000f838  nop     dword ptr [rax+rax+00h]
0x14000f83d  mov     edx, 56425355h; Tag
0x14000f842  mov     rcx, rsi; P
0x14000f845  call    cs:__imp_ExFreePoolWithTag
0x14000f84c  nop     dword ptr [rax+rax+00h]
0x14000f851  test    r14, r14
0x14000f854  jz      short loc_14000F86A
0x14000f856  mov     edx, 56425355h; Tag
0x14000f85b  mov     rcx, r14; P
0x14000f85e  call    cs:__imp_ExFreePoolWithTag
0x14000f865  nop     dword ptr [rax+rax+00h]
0x14000f86a  mov     rcx, [rbp+Handle]; Handle
0x14000f86e  test    rcx, rcx
0x14000f871  jz      short loc_14000F87F
0x14000f873  call    cs:__imp_ZwClose
0x14000f87a  nop     dword ptr [rax+rax+00h]
0x14000f87f  lea     r11, [rsp+50h+var_s0]
0x14000f884  mov     rbx, [r11+40h]
0x14000f888  mov     rsi, [r11+48h]
0x14000f88c  mov     rsp, r11
0x14000f88f  pop     r15
0x14000f891  pop     r14
0x14000f893  pop     r12
0x14000f895  pop     rdi
0x14000f896  pop     rbp
0x14000f897  retn
```
