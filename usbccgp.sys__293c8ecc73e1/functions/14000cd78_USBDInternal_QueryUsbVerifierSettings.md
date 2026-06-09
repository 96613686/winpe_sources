# USBDInternal_QueryUsbVerifierSettings

- ea: `0x14000cd78`
- end: `0x14000d0e9`
- name: `USBDInternal_QueryUsbVerifierSettings`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000c7e8`

## callees

- `0x14000cd78`
- `0x14000d0f0`
- `0x140014d50`
- `0x140015100`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000cddc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d034`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000cddc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d034`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d095`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d095`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0ae`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000cdb1`
- `ntoskrnl!MmIsDriverVerifying` at `0x14000cdb1`
- `ntoskrnl!ZwClose` at `0x14000d0c3`
- `ntoskrnl!ZwClose` at `0x14000d0c3`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000d055`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cdcc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d024`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cdcc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d024`
- `ntoskrnl!DbgPrintEx` at `0x14000ce2e`
- `ntoskrnl!DbgPrintEx` at `0x14000ce96`
- `ntoskrnl!DbgPrintEx` at `0x14000d081`
- `ntoskrnl!DbgPrintEx` at `0x14000ce2e`
- `ntoskrnl!DbgPrintEx` at `0x14000ce96`
- `ntoskrnl!DbgPrintEx` at `0x14000d081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ce6a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ce6a`

## string_xrefs

- `0x14000cdbd`: `IoOpenDriverRegistryKey`
- `0x14000cffb`: `RtlQueryRegistryValuesEx`
- `0x14000ce21`: `IoOpenDriverRegistryKey failed with 0x%x\n`
- `0x14000d074`: `RtlQueryRegistrySettings failed, ignoring this error0x%x\n`

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
    PoolWithTag = ExAllocatePoolWithTag(PoolType, 0x1C0u, 0x43627355u);
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
      ExFreePoolWithTag(v12, 0x43627355u);
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "ExAllocatePoolWithTag for USBDInternal_QueryUsbVerifierSettings failed\n");
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x43627355u);
LABEL_19:
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x14000cd78  mov     [rsp-28h+arg_10], rbx
0x14000cd7d  mov     [rsp-28h+arg_18], rsi
0x14000cd82  push    rbp
0x14000cd83  push    rdi
0x14000cd84  push    r12
0x14000cd86  push    r14
0x14000cd88  push    r15
0x14000cd8a  mov     rbp, rsp
0x14000cd8d  sub     rsp, 50h
0x14000cd91  mov     rbx, rcx
0x14000cd94  lea     r12, [rdx+48h]
0x14000cd98  mov     rcx, [rcx+8]; DriverObject
0x14000cd9c  xor     r14d, r14d
0x14000cd9f  xorps   xmm0, xmm0
0x14000cda2  mov     [rbp+P], r14
0x14000cda6  mov     [rbp+Handle], r14
0x14000cdaa  mov     rdi, rdx
0x14000cdad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000cdb1  call    cs:__imp_MmIsDriverVerifying
0x14000cdb8  nop     dword ptr [rax+rax+00h]
0x14000cdbd  lea     rdx, SourceString; "IoOpenDriverRegistryKey"
0x14000cdc4  mov     [r12], eax
0x14000cdc8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000cdcc  call    cs:__imp_RtlInitUnicodeString
0x14000cdd3  nop     dword ptr [rax+rax+00h]
0x14000cdd8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000cddc  call    cs:__imp_MmGetSystemRoutineAddress
0x14000cde3  nop     dword ptr [rax+rax+00h]
0x14000cde8  mov     r15, rax
0x14000cdeb  test    rax, rax
0x14000cdee  jz      short loc_14000CE3F
0x14000cdf0  mov     rcx, [rbx+8]
0x14000cdf4  lea     rax, [rbp+Handle]
0x14000cdf8  mov     [rsp+50h+var_30], rax
0x14000cdfd  lea     r8d, [r14+1]
0x14000ce01  mov     rax, r15
0x14000ce04  xor     r9d, r9d
0x14000ce07  xor     edx, edx
0x14000ce09  call    _guard_dispatch_icall
0x14000ce0e  test    eax, eax
0x14000ce10  jns     short loc_14000CE57
0x14000ce12  cmp     cs:g_EnableDbgPrints, r14b
0x14000ce19  jz      loc_14000D0BA
0x14000ce1f  xor     edx, edx; Level
0x14000ce21  lea     r8, aIoopendriverre; "IoOpenDriverRegistryKey failed with 0x%"...
0x14000ce28  mov     r9d, eax
0x14000ce2b  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ce2e  call    cs:__imp_DbgPrintEx
0x14000ce35  nop     dword ptr [rax+rax+00h]
0x14000ce3a  jmp     loc_14000D0BA
0x14000ce3f  lea     rdx, [rbp+P]
0x14000ce43  mov     rcx, rbx
0x14000ce46  call    USBDInternal_BuildServicePath
0x14000ce4b  mov     r14, [rbp+P]
0x14000ce4f  test    eax, eax
0x14000ce51  js      loc_14000D0A1
0x14000ce57  mov     ecx, cs:PoolType; PoolType
0x14000ce5d  mov     ebx, 1C0h
0x14000ce62  mov     edx, ebx; NumberOfBytes
0x14000ce64  mov     r8d, 43627355h; Tag
0x14000ce6a  call    cs:__imp_ExAllocatePoolWithTag
0x14000ce71  nop     dword ptr [rax+rax+00h]
0x14000ce76  mov     rsi, rax
0x14000ce79  test    rax, rax
0x14000ce7c  jnz     short loc_14000CEA7
0x14000ce7e  cmp     cs:g_EnableDbgPrints, al
0x14000ce84  jz      loc_14000D0A1
0x14000ce8a  lea     r8, aExallocatepool; "ExAllocatePoolWithTag for USBDInternal_"...
0x14000ce91  xor     edx, edx; Level
0x14000ce93  lea     ecx, [rax+4Dh]; ComponentId
0x14000ce96  call    cs:__imp_DbgPrintEx
0x14000ce9d  nop     dword ptr [rax+rax+00h]
0x14000cea2  jmp     loc_14000D0A1
0x14000cea7  mov     r8, rbx; Size
0x14000ceaa  xor     edx, edx; Val
0x14000ceac  mov     rcx, rsi; void *
0x14000ceaf  call    memset
0x14000ceb4  mov     [rsi+18h], r12
0x14000ceb8  lea     rcx, USBD_VerifierSettingsCallback
0x14000cebf  mov     [rsi], rcx
0x14000cec2  lea     rax, aUsbverifierena; "UsbVerifierEnabled"
0x14000cec9  mov     [rsi+10h], rax
0x14000cecd  mov     edx, 4
0x14000ced2  mov     [rsi+20h], edx
0x14000ced5  lea     rax, aUsbverifierfai_3; "UsbVerifierFailRegistration"
0x14000cedc  mov     [rsi+30h], edx
0x14000cedf  test    r15, r15
0x14000cee2  mov     [rsi+28h], r12
0x14000cee6  xorps   xmm0, xmm0
0x14000cee9  mov     [rsi+48h], rax
0x14000ceed  lea     rax, [rdi+4Ch]
0x14000cef1  mov     [rsi+50h], rax
0x14000cef5  mov     [rsi+60h], rax
0x14000cef9  lea     rax, aUsbverifierfai_1; "UsbVerifierFailChainedMdlSupport"
0x14000cf00  mov     [rsi+38h], rcx
0x14000cf04  mov     [rsi+58h], edx
0x14000cf07  mov     [rsi+68h], edx
0x14000cf0a  mov     [rsi+80h], rax
0x14000cf11  lea     rax, [rdi+50h]
0x14000cf15  mov     [rsi+88h], rax
0x14000cf1c  mov     [rsi+98h], rax
0x14000cf23  lea     rax, aUsbverifierfai_2; "UsbVerifierFailStaticStreamSupport"
0x14000cf2a  mov     [rsi+70h], rcx
0x14000cf2e  mov     [rsi+90h], edx
0x14000cf34  mov     [rsi+0A0h], edx
0x14000cf3a  mov     [rsi+0B8h], rax
0x14000cf41  lea     rax, [rdi+54h]
0x14000cf45  mov     [rsi+0C0h], rax
0x14000cf4c  mov     [rsi+0D0h], rax
0x14000cf53  lea     rax, aUsbverifiersta; "UsbVerifierStaticStreamCountOverride"
0x14000cf5a  mov     [rsi+0A8h], rcx
0x14000cf61  mov     [rsi+0C8h], edx
0x14000cf67  mov     [rsi+0D8h], edx
0x14000cf6d  mov     [rsi+0F0h], rax
0x14000cf74  lea     rax, [rdi+58h]
0x14000cf78  mov     [rsi+0F8h], rax
0x14000cf7f  mov     [rsi+108h], rax
0x14000cf86  lea     rax, aUsbverifierfai_0; "UsbVerifierFailEnableStaticStreams"
0x14000cf8d  mov     [rsi+0E0h], rcx
0x14000cf94  mov     [rsi+100h], edx
0x14000cf9a  mov     [rsi+110h], edx
0x14000cfa0  mov     [rsi+128h], rax
0x14000cfa7  lea     rax, [rdi+5Ch]
0x14000cfab  mov     [rsi+130h], rax
0x14000cfb2  mov     [rsi+140h], rax
0x14000cfb9  lea     rax, aUsbverifierfai; "UsbVerifierFailSecureTransferSupport"
0x14000cfc0  mov     [rsi+118h], rcx
0x14000cfc7  mov     [rsi+138h], edx
0x14000cfcd  mov     [rsi+148h], edx
0x14000cfd3  mov     [rsi+160h], rax
0x14000cfda  lea     rax, [rdi+0A0h]
0x14000cfe1  mov     [rsi+150h], rcx
0x14000cfe8  mov     rdi, r14
0x14000cfeb  mov     [rsi+170h], edx
0x14000cff1  lea     rcx, [rbp+SystemRoutineName]; DestinationString
0x14000cff5  mov     [rsi+180h], edx
0x14000cffb  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000d002  mov     [rsi+168h], rax
0x14000d009  mov     [rsi+178h], rax
0x14000d010  cmovnz  rdi, [rbp+Handle]
0x14000d015  neg     r15
0x14000d018  movups  xmmword ptr [rbp+SystemRoutineName.Length], xmm0
0x14000d01c  sbb     ebx, ebx
0x14000d01e  and     ebx, 3FFFFFFFh
0x14000d024  call    cs:__imp_RtlInitUnicodeString
0x14000d02b  nop     dword ptr [rax+rax+00h]
0x14000d030  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000d034  call    cs:__imp_MmGetSystemRoutineAddress
0x14000d03b  nop     dword ptr [rax+rax+00h]
0x14000d040  mov     [rsp+50h+var_30], 0
0x14000d049  lea     ecx, [rbx+1]
0x14000d04c  test    rax, rax
0x14000d04f  mov     r8, rsi
0x14000d052  mov     rdx, rdi
0x14000d055  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000d05d  xor     r9d, r9d
0x14000d060  call    _guard_dispatch_icall
0x14000d065  test    eax, eax
0x14000d067  jns     short loc_14000D08D
0x14000d069  cmp     cs:g_EnableDbgPrints, 0
0x14000d070  jz      short loc_14000D08D
0x14000d072  xor     edx, edx; Level
0x14000d074  lea     r8, aRtlqueryregist_0; "RtlQueryRegistrySettings failed, ignori"...
0x14000d07b  mov     r9d, eax
0x14000d07e  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d081  call    cs:__imp_DbgPrintEx
0x14000d088  nop     dword ptr [rax+rax+00h]
0x14000d08d  mov     edx, 43627355h; Tag
0x14000d092  mov     rcx, rsi; P
0x14000d095  call    cs:__imp_ExFreePoolWithTag
0x14000d09c  nop     dword ptr [rax+rax+00h]
0x14000d0a1  test    r14, r14
0x14000d0a4  jz      short loc_14000D0BA
0x14000d0a6  mov     edx, 43627355h; Tag
0x14000d0ab  mov     rcx, r14; P
0x14000d0ae  call    cs:__imp_ExFreePoolWithTag
0x14000d0b5  nop     dword ptr [rax+rax+00h]
0x14000d0ba  mov     rcx, [rbp+Handle]; Handle
0x14000d0be  test    rcx, rcx
0x14000d0c1  jz      short loc_14000D0CF
0x14000d0c3  call    cs:__imp_ZwClose
0x14000d0ca  nop     dword ptr [rax+rax+00h]
0x14000d0cf  lea     r11, [rsp+50h+var_s0]
0x14000d0d4  mov     rbx, [r11+40h]
0x14000d0d8  mov     rsi, [r11+48h]
0x14000d0dc  mov     rsp, r11
0x14000d0df  pop     r15
0x14000d0e1  pop     r14
0x14000d0e3  pop     r12
0x14000d0e5  pop     rdi
0x14000d0e6  pop     rbp
0x14000d0e7  retn
```
