# WerpCreateReportFull

- ea: `0x14000e464`
- end: `0x14000e723`
- name: `WerpCreateReportFull`
- size: `703`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000e194`

## callees

- `0x1400015ec`
- `0x14000d68c`
- `0x14000dfd0`
- `0x14000e464`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e4da`
- `ntoskrnl!DbgPrintEx` at `0x14000e5ca`
- `ntoskrnl!DbgPrintEx` at `0x14000e649`
- `ntoskrnl!DbgPrintEx` at `0x14000e4da`
- `ntoskrnl!DbgPrintEx` at `0x14000e5ca`
- `ntoskrnl!DbgPrintEx` at `0x14000e649`
- `ntoskrnl!ZwClose` at `0x14000e673`
- `ntoskrnl!ZwClose` at `0x14000e68c`
- `ntoskrnl!ZwClose` at `0x14000e6a5`
- `ntoskrnl!ZwClose` at `0x14000e6c5`
- `ntoskrnl!ZwClose` at `0x14000e6e3`
- `ntoskrnl!ZwClose` at `0x14000e705`
- `ntoskrnl!ZwClose` at `0x14000e673`
- `ntoskrnl!ZwClose` at `0x14000e68c`
- `ntoskrnl!ZwClose` at `0x14000e6a5`
- `ntoskrnl!ZwClose` at `0x14000e6c5`
- `ntoskrnl!ZwClose` at `0x14000e6e3`
- `ntoskrnl!ZwClose` at `0x14000e705`
- `ntoskrnl!ZwFlushKey` at `0x14000e65b`
- `ntoskrnl!ZwFlushKey` at `0x14000e65b`

## string_xrefs

- `0x14000e4c8`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n`
- `0x14000e562`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report type\n`
- `0x14000e5a1`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report id\n`
- `0x14000e5b8`: `WERKERNELHOST: Report id %S already exists\n`
- `0x14000e63c`: `WERKERNELHOST: WerpCreateRegistryKey failed with status 0x%x for report pending\n`
- `0x14000e4ac`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 __fastcall WerpCreateReportFull(__int64 a1, const wchar_t *a2, HANDLE *a3)
{
  int v6; // eax
  int v7; // ebx
  const CHAR *v8; // r8
  __int64 v9; // r9
  __int64 v10; // r9
  int RegistryKey; // eax
  _BYTE v13[8]; // [rsp+30h] [rbp-40h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-30h] BYREF
  HANDLE v16; // [rsp+48h] [rbp-28h] BYREF
  HANDLE v17; // [rsp+50h] [rbp-20h] BYREF
  HANDLE v18; // [rsp+58h] [rbp-18h] BYREF
  HANDLE v19[2]; // [rsp+60h] [rbp-10h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  v19[0] = 0;
  v6 = WerpCreateRegistryKey(0, g_wszLiveKernelReportsQueueRoot, 131076, 0, &v16, 0);
  v7 = v6;
  if ( v6 < 0 || (v6 = WerpCreateRegistryKey(v16, L"FullLiveKernelReports", 131076, 0, &Handle, 0), v7 = v6, v6 < 0) )
  {
    v8 = "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n";
LABEL_3:
    DbgPrintEx(5u, 1u, v8, (unsigned int)v6);
    goto LABEL_20;
  }
  if ( !(unsigned int)WerpCheckSpaceAvailableFull(Handle) )
  {
    v7 = -1073741671;
    DbgPrintEx(
      5u,
      1u,
      "WERKERNELHOST: WerpCheckSpaceAvailable returned no more space available, status 0x%x\n",
      3221225625LL);
    goto LABEL_20;
  }
  v6 = WerpCreateRegistryKey(Handle, a1, 131101, 0, &KeyHandle, 0);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_9;
  v13[0] = 0;
  v6 = WerpCreateRegistryKey(KeyHandle, a2, 196612, 0, &v17, v13);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report id\n";
    goto LABEL_3;
  }
  if ( !v13[0] )
  {
    v7 = -1073741771;
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Report id %S already exists\n", a2);
    goto LABEL_20;
  }
  LOBYTE(v9) = 1;
  v6 = WerpCreateRegistryKey(v17, L"Busy", 196612, v9, &v18, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
LABEL_9:
    v8 = "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report type\n";
    goto LABEL_3;
  }
  if ( (unsigned int)Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline() )
  {
    LOBYTE(v10) = 1;
    RegistryKey = WerpCreateRegistryKey(v16, L"LiveReportPending", 0, v10, v19, 0);
    if ( RegistryKey < 0 )
      DbgPrintEx(
        5u,
        0,
        "WERKERNELHOST: WerpCreateRegistryKey failed with status 0x%x for report pending\n",
        RegistryKey);
  }
  else
  {
    ZwFlushKey(KeyHandle);
  }
  v7 = 0;
LABEL_20:
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v16 )
  {
    ZwClose(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    if ( v7 >= 0 )
    {
      *a3 = v17;
    }
    else
    {
      ZwClose(v17);
      v17 = 0;
    }
  }
  if ( v18 )
  {
    ZwClose(v18);
    v18 = 0;
  }
  if ( (unsigned int)Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline() && v19[0] )
    ZwClose(v19[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000e464  push    rbp
0x14000e466  push    rbx
0x14000e467  push    rsi
0x14000e468  push    rdi
0x14000e469  push    r12
0x14000e46b  push    r14
0x14000e46d  push    r15
0x14000e46f  mov     rbp, rsp
0x14000e472  sub     rsp, 70h
0x14000e476  xor     r12d, r12d
0x14000e479  lea     rax, [rbp+var_28]
0x14000e47d  mov     rsi, r9
0x14000e480  mov     [rsp+70h+var_48], r12
0x14000e485  mov     r15, r8
0x14000e488  mov     [rsp+70h+var_50], rax
0x14000e48d  mov     rdi, rdx
0x14000e490  mov     [rbp+Handle], r12
0x14000e494  mov     r14, rcx
0x14000e497  mov     [rbp+KeyHandle], r12
0x14000e49b  xor     r9d, r9d
0x14000e49e  mov     [rbp+var_20], r12
0x14000e4a2  mov     r8d, 20004h
0x14000e4a8  mov     [rbp+var_18], r12
0x14000e4ac  lea     rdx, g_wszLiveKernelReportsQueueRoot; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000e4b3  mov     [rbp+var_28], r12
0x14000e4b7  xor     ecx, ecx
0x14000e4b9  mov     [rbp+var_10], r12
0x14000e4bd  call    WerpCreateRegistryKey
0x14000e4c2  mov     ebx, eax
0x14000e4c4  test    eax, eax
0x14000e4c6  jns     short loc_14000E4EB
0x14000e4c8  lea     r8, aWerkernelhostZ_5; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e4cf  mov     r9d, eax
0x14000e4d2  mov     edx, 1; Level
0x14000e4d7  lea     ecx, [rdx+4]; ComponentId
0x14000e4da  call    cs:__imp_DbgPrintEx
0x14000e4e1  nop     dword ptr [rax+rax+00h]
0x14000e4e6  jmp     loc_14000E66A
0x14000e4eb  mov     rcx, [rbp+var_28]
0x14000e4ef  lea     rax, [rbp+Handle]
0x14000e4f3  mov     [rsp+70h+var_48], r12
0x14000e4f8  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x14000e4ff  xor     r9d, r9d
0x14000e502  mov     [rsp+70h+var_50], rax
0x14000e507  mov     r8d, 20004h
0x14000e50d  call    WerpCreateRegistryKey
0x14000e512  mov     ebx, eax
0x14000e514  test    eax, eax
0x14000e516  js      short loc_14000E4C8
0x14000e518  mov     rcx, [rbp+Handle]; KeyHandle
0x14000e51c  mov     rdx, rsi
0x14000e51f  call    WerpCheckSpaceAvailableFull
0x14000e524  test    eax, eax
0x14000e526  jnz     short loc_14000E539
0x14000e528  mov     ebx, 0C0000099h
0x14000e52d  lea     r8, aWerkernelhostW_26; "WERKERNELHOST: WerpCheckSpaceAvailable "...
0x14000e534  mov     r9d, ebx
0x14000e537  jmp     short loc_14000E4D2
0x14000e539  mov     rcx, [rbp+Handle]
0x14000e53d  lea     rax, [rbp+KeyHandle]
0x14000e541  mov     [rsp+70h+var_48], r12
0x14000e546  xor     r9d, r9d
0x14000e549  mov     r8d, 2001Dh
0x14000e54f  mov     [rsp+70h+var_50], rax
0x14000e554  mov     rdx, r14
0x14000e557  call    WerpCreateRegistryKey
0x14000e55c  mov     ebx, eax
0x14000e55e  test    eax, eax
0x14000e560  jns     short loc_14000E56E
0x14000e562  lea     r8, aWerkernelhostZ_6; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e569  jmp     loc_14000E4CF
0x14000e56e  mov     rcx, [rbp+KeyHandle]
0x14000e572  lea     rax, [rbp+var_40]
0x14000e576  mov     [rsp+70h+var_48], rax
0x14000e57b  mov     esi, 30004h
0x14000e580  lea     rax, [rbp+var_20]
0x14000e584  mov     [rbp+var_40], r12b
0x14000e588  xor     r9d, r9d
0x14000e58b  mov     [rsp+70h+var_50], rax
0x14000e590  mov     r8d, esi
0x14000e593  mov     rdx, rdi
0x14000e596  call    WerpCreateRegistryKey
0x14000e59b  mov     ebx, eax
0x14000e59d  test    eax, eax
0x14000e59f  jns     short loc_14000E5AD
0x14000e5a1  lea     r8, aWerkernelhostZ_11; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e5a8  jmp     loc_14000E4CF
0x14000e5ad  cmp     [rbp+var_40], r12b
0x14000e5b1  jnz     short loc_14000E5DB
0x14000e5b3  mov     edx, 1; Level
0x14000e5b8  lea     r8, aWerkernelhostR_4; "WERKERNELHOST: Report id %S already exi"...
0x14000e5bf  mov     r9, rdi
0x14000e5c2  mov     ebx, 0C0000035h
0x14000e5c7  lea     ecx, [rdx+4]; ComponentId
0x14000e5ca  call    cs:__imp_DbgPrintEx
0x14000e5d1  nop     dword ptr [rax+rax+00h]
0x14000e5d6  jmp     loc_14000E66A
0x14000e5db  mov     rcx, [rbp+var_20]
0x14000e5df  lea     rax, [rbp+var_18]
0x14000e5e3  mov     [rsp+70h+var_48], r12
0x14000e5e8  lea     rdx, aBusy; "Busy"
0x14000e5ef  mov     r9b, 1
0x14000e5f2  mov     [rsp+70h+var_50], rax
0x14000e5f7  mov     r8d, esi
0x14000e5fa  call    WerpCreateRegistryKey
0x14000e5ff  mov     ebx, eax
0x14000e601  test    eax, eax
0x14000e603  js      loc_14000E562
0x14000e609  call    Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline
0x14000e60e  test    eax, eax
0x14000e610  jz      short loc_14000E657
0x14000e612  mov     rcx, [rbp+var_28]
0x14000e616  lea     rax, [rbp+var_10]
0x14000e61a  mov     [rsp+70h+var_48], r12
0x14000e61f  lea     rdx, aLivereportpend; "LiveReportPending"
0x14000e626  mov     r9b, 1
0x14000e629  mov     [rsp+70h+var_50], rax
0x14000e62e  xor     r8d, r8d
0x14000e631  call    WerpCreateRegistryKey
0x14000e636  test    eax, eax
0x14000e638  jns     short loc_14000E667
0x14000e63a  xor     edx, edx; Level
0x14000e63c  lea     r8, aWerkernelhostW_19; "WERKERNELHOST: WerpCreateRegistryKey fa"...
0x14000e643  mov     r9d, eax
0x14000e646  lea     ecx, [rdx+5]; ComponentId
0x14000e649  call    cs:__imp_DbgPrintEx
0x14000e650  nop     dword ptr [rax+rax+00h]
0x14000e655  jmp     short loc_14000E667
0x14000e657  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e65b  call    cs:__imp_ZwFlushKey
0x14000e662  nop     dword ptr [rax+rax+00h]
0x14000e667  mov     ebx, r12d
0x14000e66a  mov     rcx, [rbp+Handle]; Handle
0x14000e66e  test    rcx, rcx
0x14000e671  jz      short loc_14000E683
0x14000e673  call    cs:__imp_ZwClose
0x14000e67a  nop     dword ptr [rax+rax+00h]
0x14000e67f  mov     [rbp+Handle], r12
0x14000e683  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e687  test    rcx, rcx
0x14000e68a  jz      short loc_14000E69C
0x14000e68c  call    cs:__imp_ZwClose
0x14000e693  nop     dword ptr [rax+rax+00h]
0x14000e698  mov     [rbp+KeyHandle], r12
0x14000e69c  mov     rcx, [rbp+var_28]; Handle
0x14000e6a0  test    rcx, rcx
0x14000e6a3  jz      short loc_14000E6B5
0x14000e6a5  call    cs:__imp_ZwClose
0x14000e6ac  nop     dword ptr [rax+rax+00h]
0x14000e6b1  mov     [rbp+var_28], r12
0x14000e6b5  mov     rax, [rbp+var_20]
0x14000e6b9  test    rax, rax
0x14000e6bc  jz      short loc_14000E6DA
0x14000e6be  test    ebx, ebx
0x14000e6c0  jns     short loc_14000E6D7
0x14000e6c2  mov     rcx, rax; Handle
0x14000e6c5  call    cs:__imp_ZwClose
0x14000e6cc  nop     dword ptr [rax+rax+00h]
0x14000e6d1  mov     [rbp+var_20], r12
0x14000e6d5  jmp     short loc_14000E6DA
0x14000e6d7  mov     [r15], rax
0x14000e6da  mov     rcx, [rbp+var_18]; Handle
0x14000e6de  test    rcx, rcx
0x14000e6e1  jz      short loc_14000E6F3
0x14000e6e3  call    cs:__imp_ZwClose
0x14000e6ea  nop     dword ptr [rax+rax+00h]
0x14000e6ef  mov     [rbp+var_18], r12
0x14000e6f3  call    Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline
0x14000e6f8  test    eax, eax
0x14000e6fa  jz      short loc_14000E711
0x14000e6fc  mov     rcx, [rbp+var_10]; Handle
0x14000e700  test    rcx, rcx
0x14000e703  jz      short loc_14000E711
0x14000e705  call    cs:__imp_ZwClose
0x14000e70c  nop     dword ptr [rax+rax+00h]
0x14000e711  mov     eax, ebx
0x14000e713  add     rsp, 70h
0x14000e717  pop     r15
0x14000e719  pop     r14
0x14000e71b  pop     r12
0x14000e71d  pop     rdi
0x14000e71e  pop     rsi
0x14000e71f  pop     rbx
0x14000e720  pop     rbp
0x14000e721  retn
```
