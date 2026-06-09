# USBDInternal_QueryUsbVerifierSettings

- ea: `0x140042d48`
- end: `0x1400430b9`
- name: `USBDInternal_QueryUsbVerifierSettings`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1400430c0`

## callees

- `0x140042a0c`
- `0x140042d48`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043065`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004307e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043065`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004307e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042dac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043004`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042dac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043004`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042d9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042ff4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042d9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042ff4`
- `ntoskrnl!DbgPrintEx` at `0x140042dfe`
- `ntoskrnl!DbgPrintEx` at `0x140042e66`
- `ntoskrnl!DbgPrintEx` at `0x140043051`
- `ntoskrnl!DbgPrintEx` at `0x140042dfe`
- `ntoskrnl!DbgPrintEx` at `0x140042e66`
- `ntoskrnl!DbgPrintEx` at `0x140043051`
- `ntoskrnl!ZwClose` at `0x140043093`
- `ntoskrnl!ZwClose` at `0x140043093`
- `ntoskrnl!MmIsDriverVerifying` at `0x140042d81`
- `ntoskrnl!MmIsDriverVerifying` at `0x140042d81`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140043025`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042e3a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140042e3a`

## string_xrefs

- `0x140042d8d`: `IoOpenDriverRegistryKey`
- `0x140042fcb`: `RtlQueryRegistryValuesEx`
- `0x140043044`: `RtlQueryRegistrySettings failed, ignoring this error0x%x\n`
- `0x140042df1`: `IoOpenDriverRegistryKey failed with 0x%x\n`

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
    PoolWithTag = ExAllocatePoolWithTag(PoolType, 0x1C0u, 0x68334855u);
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
      ExFreePoolWithTag(v12, 0x68334855u);
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "ExAllocatePoolWithTag for USBDInternal_QueryUsbVerifierSettings failed\n");
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x68334855u);
LABEL_19:
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x140042d48  mov     [rsp-28h+arg_10], rbx
0x140042d4d  mov     [rsp-28h+arg_18], rsi
0x140042d52  push    rbp
0x140042d53  push    rdi
0x140042d54  push    r12
0x140042d56  push    r14
0x140042d58  push    r15
0x140042d5a  mov     rbp, rsp
0x140042d5d  sub     rsp, 50h
0x140042d61  mov     rbx, rcx
0x140042d64  lea     r12, [rdx+48h]
0x140042d68  mov     rcx, [rcx+8]; DriverObject
0x140042d6c  xor     r14d, r14d
0x140042d6f  xorps   xmm0, xmm0
0x140042d72  mov     [rbp+P], r14
0x140042d76  mov     [rbp+Handle], r14
0x140042d7a  mov     rdi, rdx
0x140042d7d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140042d81  call    cs:__imp_MmIsDriverVerifying
0x140042d88  nop     dword ptr [rax+rax+00h]
0x140042d8d  lea     rdx, aIoopendriverre_0; "IoOpenDriverRegistryKey"
0x140042d94  mov     [r12], eax
0x140042d98  lea     rcx, [rbp+DestinationString]; DestinationString
0x140042d9c  call    cs:__imp_RtlInitUnicodeString
0x140042da3  nop     dword ptr [rax+rax+00h]
0x140042da8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140042dac  call    cs:__imp_MmGetSystemRoutineAddress
0x140042db3  nop     dword ptr [rax+rax+00h]
0x140042db8  mov     r15, rax
0x140042dbb  test    rax, rax
0x140042dbe  jz      short loc_140042E0F
0x140042dc0  mov     rcx, [rbx+8]
0x140042dc4  lea     rax, [rbp+Handle]
0x140042dc8  mov     [rsp+50h+var_30], rax
0x140042dcd  lea     r8d, [r14+1]
0x140042dd1  mov     rax, r15
0x140042dd4  xor     r9d, r9d
0x140042dd7  xor     edx, edx
0x140042dd9  call    _guard_dispatch_icall
0x140042dde  test    eax, eax
0x140042de0  jns     short loc_140042E27
0x140042de2  cmp     cs:g_EnableDbgPrints, r14b
0x140042de9  jz      loc_14004308A
0x140042def  xor     edx, edx; Level
0x140042df1  lea     r8, aIoopendriverre; "IoOpenDriverRegistryKey failed with 0x%"...
0x140042df8  mov     r9d, eax
0x140042dfb  lea     ecx, [rdx+4Dh]; ComponentId
0x140042dfe  call    cs:__imp_DbgPrintEx
0x140042e05  nop     dword ptr [rax+rax+00h]
0x140042e0a  jmp     loc_14004308A
0x140042e0f  lea     rdx, [rbp+P]
0x140042e13  mov     rcx, rbx
0x140042e16  call    USBDInternal_BuildServicePath
0x140042e1b  mov     r14, [rbp+P]
0x140042e1f  test    eax, eax
0x140042e21  js      loc_140043071
0x140042e27  mov     ecx, cs:PoolType; PoolType
0x140042e2d  mov     ebx, 1C0h
0x140042e32  mov     edx, ebx; NumberOfBytes
0x140042e34  mov     r8d, 68334855h; Tag
0x140042e3a  call    cs:__imp_ExAllocatePoolWithTag
0x140042e41  nop     dword ptr [rax+rax+00h]
0x140042e46  mov     rsi, rax
0x140042e49  test    rax, rax
0x140042e4c  jnz     short loc_140042E77
0x140042e4e  cmp     cs:g_EnableDbgPrints, al
0x140042e54  jz      loc_140043071
0x140042e5a  lea     r8, aExallocatepool; "ExAllocatePoolWithTag for USBDInternal_"...
0x140042e61  xor     edx, edx; Level
0x140042e63  lea     ecx, [rax+4Dh]; ComponentId
0x140042e66  call    cs:__imp_DbgPrintEx
0x140042e6d  nop     dword ptr [rax+rax+00h]
0x140042e72  jmp     loc_140043071
0x140042e77  mov     r8, rbx; Size
0x140042e7a  xor     edx, edx; Val
0x140042e7c  mov     rcx, rsi; void *
0x140042e7f  call    memset
0x140042e84  mov     [rsi+18h], r12
0x140042e88  lea     rcx, USBD_VerifierSettingsCallback
0x140042e8f  mov     [rsi], rcx
0x140042e92  lea     rax, aUsbverifierena; "UsbVerifierEnabled"
0x140042e99  mov     [rsi+10h], rax
0x140042e9d  mov     edx, 4
0x140042ea2  mov     [rsi+20h], edx
0x140042ea5  lea     rax, aUsbverifierfai_3; "UsbVerifierFailRegistration"
0x140042eac  mov     [rsi+30h], edx
0x140042eaf  test    r15, r15
0x140042eb2  mov     [rsi+28h], r12
0x140042eb6  xorps   xmm0, xmm0
0x140042eb9  mov     [rsi+48h], rax
0x140042ebd  lea     rax, [rdi+4Ch]
0x140042ec1  mov     [rsi+50h], rax
0x140042ec5  mov     [rsi+60h], rax
0x140042ec9  lea     rax, aUsbverifierfai_1; "UsbVerifierFailChainedMdlSupport"
0x140042ed0  mov     [rsi+38h], rcx
0x140042ed4  mov     [rsi+58h], edx
0x140042ed7  mov     [rsi+68h], edx
0x140042eda  mov     [rsi+80h], rax
0x140042ee1  lea     rax, [rdi+50h]
0x140042ee5  mov     [rsi+88h], rax
0x140042eec  mov     [rsi+98h], rax
0x140042ef3  lea     rax, aUsbverifierfai_2; "UsbVerifierFailStaticStreamSupport"
0x140042efa  mov     [rsi+70h], rcx
0x140042efe  mov     [rsi+90h], edx
0x140042f04  mov     [rsi+0A0h], edx
0x140042f0a  mov     [rsi+0B8h], rax
0x140042f11  lea     rax, [rdi+54h]
0x140042f15  mov     [rsi+0C0h], rax
0x140042f1c  mov     [rsi+0D0h], rax
0x140042f23  lea     rax, aUsbverifiersta; "UsbVerifierStaticStreamCountOverride"
0x140042f2a  mov     [rsi+0A8h], rcx
0x140042f31  mov     [rsi+0C8h], edx
0x140042f37  mov     [rsi+0D8h], edx
0x140042f3d  mov     [rsi+0F0h], rax
0x140042f44  lea     rax, [rdi+58h]
0x140042f48  mov     [rsi+0F8h], rax
0x140042f4f  mov     [rsi+108h], rax
0x140042f56  lea     rax, aUsbverifierfai_0; "UsbVerifierFailEnableStaticStreams"
0x140042f5d  mov     [rsi+0E0h], rcx
0x140042f64  mov     [rsi+100h], edx
0x140042f6a  mov     [rsi+110h], edx
0x140042f70  mov     [rsi+128h], rax
0x140042f77  lea     rax, [rdi+5Ch]
0x140042f7b  mov     [rsi+130h], rax
0x140042f82  mov     [rsi+140h], rax
0x140042f89  lea     rax, aUsbverifierfai; "UsbVerifierFailSecureTransferSupport"
0x140042f90  mov     [rsi+118h], rcx
0x140042f97  mov     [rsi+138h], edx
0x140042f9d  mov     [rsi+148h], edx
0x140042fa3  mov     [rsi+160h], rax
0x140042faa  lea     rax, [rdi+0A0h]
0x140042fb1  mov     [rsi+150h], rcx
0x140042fb8  mov     rdi, r14
0x140042fbb  mov     [rsi+170h], edx
0x140042fc1  lea     rcx, [rbp+SystemRoutineName]; DestinationString
0x140042fc5  mov     [rsi+180h], edx
0x140042fcb  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140042fd2  mov     [rsi+168h], rax
0x140042fd9  mov     [rsi+178h], rax
0x140042fe0  cmovnz  rdi, [rbp+Handle]
0x140042fe5  neg     r15
0x140042fe8  movups  xmmword ptr [rbp+SystemRoutineName.Length], xmm0
0x140042fec  sbb     ebx, ebx
0x140042fee  and     ebx, 3FFFFFFFh
0x140042ff4  call    cs:__imp_RtlInitUnicodeString
0x140042ffb  nop     dword ptr [rax+rax+00h]
0x140043000  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x140043004  call    cs:__imp_MmGetSystemRoutineAddress
0x14004300b  nop     dword ptr [rax+rax+00h]
0x140043010  mov     [rsp+50h+var_30], 0
0x140043019  lea     ecx, [rbx+1]
0x14004301c  test    rax, rax
0x14004301f  mov     r8, rsi
0x140043022  mov     rdx, rdi
0x140043025  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14004302d  xor     r9d, r9d
0x140043030  call    _guard_dispatch_icall
0x140043035  test    eax, eax
0x140043037  jns     short loc_14004305D
0x140043039  cmp     cs:g_EnableDbgPrints, 0
0x140043040  jz      short loc_14004305D
0x140043042  xor     edx, edx; Level
0x140043044  lea     r8, aRtlqueryregist_0; "RtlQueryRegistrySettings failed, ignori"...
0x14004304b  mov     r9d, eax
0x14004304e  lea     ecx, [rdx+4Dh]; ComponentId
0x140043051  call    cs:__imp_DbgPrintEx
0x140043058  nop     dword ptr [rax+rax+00h]
0x14004305d  mov     edx, 68334855h; Tag
0x140043062  mov     rcx, rsi; P
0x140043065  call    cs:__imp_ExFreePoolWithTag
0x14004306c  nop     dword ptr [rax+rax+00h]
0x140043071  test    r14, r14
0x140043074  jz      short loc_14004308A
0x140043076  mov     edx, 68334855h; Tag
0x14004307b  mov     rcx, r14; P
0x14004307e  call    cs:__imp_ExFreePoolWithTag
0x140043085  nop     dword ptr [rax+rax+00h]
0x14004308a  mov     rcx, [rbp+Handle]; Handle
0x14004308e  test    rcx, rcx
0x140043091  jz      short loc_14004309F
0x140043093  call    cs:__imp_ZwClose
0x14004309a  nop     dword ptr [rax+rax+00h]
0x14004309f  lea     r11, [rsp+50h+var_s0]
0x1400430a4  mov     rbx, [r11+40h]
0x1400430a8  mov     rsi, [r11+48h]
0x1400430ac  mov     rsp, r11
0x1400430af  pop     r15
0x1400430b1  pop     r14
0x1400430b3  pop     r12
0x1400430b5  pop     rdi
0x1400430b6  pop     rbp
0x1400430b7  retn
```
