# WerpCreateReportMini

- ea: `0x14000e83c`
- end: `0x14000eb00`
- name: `WerpCreateReportMini`
- size: `708`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000e194`

## callees

- `0x1400015ec`
- `0x14000d558`
- `0x14000dfd0`
- `0x14000e83c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e8ad`
- `ntoskrnl!DbgPrintEx` at `0x14000e93c`
- `ntoskrnl!DbgPrintEx` at `0x14000e9a9`
- `ntoskrnl!DbgPrintEx` at `0x14000ea28`
- `ntoskrnl!DbgPrintEx` at `0x14000e8ad`
- `ntoskrnl!DbgPrintEx` at `0x14000e93c`
- `ntoskrnl!DbgPrintEx` at `0x14000e9a9`
- `ntoskrnl!DbgPrintEx` at `0x14000ea28`
- `ntoskrnl!ZwClose` at `0x14000ea52`
- `ntoskrnl!ZwClose` at `0x14000ea6b`
- `ntoskrnl!ZwClose` at `0x14000ea84`
- `ntoskrnl!ZwClose` at `0x14000eaa4`
- `ntoskrnl!ZwClose` at `0x14000eac2`
- `ntoskrnl!ZwClose` at `0x14000eae4`
- `ntoskrnl!ZwClose` at `0x14000ea52`
- `ntoskrnl!ZwClose` at `0x14000ea6b`
- `ntoskrnl!ZwClose` at `0x14000ea84`
- `ntoskrnl!ZwClose` at `0x14000eaa4`
- `ntoskrnl!ZwClose` at `0x14000eac2`
- `ntoskrnl!ZwClose` at `0x14000eae4`
- `ntoskrnl!ZwFlushKey` at `0x14000ea3a`
- `ntoskrnl!ZwFlushKey` at `0x14000ea3a`

## string_xrefs

- `0x14000e89b`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n`
- `0x14000e914`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report type\n`
- `0x14000e980`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report id\n`
- `0x14000e997`: `WERKERNELHOST: Report id %S already exists\n`
- `0x14000ea1b`: `WERKERNELHOST: WerpCreateRegistryKey failed with status 0x%x for report pending\n`
- `0x14000e87b`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 __fastcall WerpCreateReportMini(__int64 a1, const wchar_t *a2, HANDLE *a3)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // r9
  int RegistryKey; // eax
  HANDLE KeyHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v15; // [rsp+38h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v17; // [rsp+48h] [rbp-20h] BYREF
  HANDLE v18; // [rsp+50h] [rbp-18h] BYREF
  HANDLE v19[2]; // [rsp+58h] [rbp-10h] BYREF
  char v20; // [rsp+B8h] [rbp+50h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v17 = 0;
  v18 = 0;
  v19[0] = 0;
  v15 = 0;
  v6 = WerpCreateRegistryKey(0, g_wszLiveKernelReportsQueueRoot, 131076, 0, &v15, 0);
  v7 = v6;
  if ( v6 < 0 || (v6 = WerpCreateRegistryKey(v15, L"LiveKernelReports", 131076, 0, &Handle, 0), v7 = v6, v6 < 0) )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the root\n", (unsigned int)v6);
  }
  else
  {
    v8 = WerpCreateRegistryKey(Handle, a1, 131101, 0, &KeyHandle, 0);
    v7 = v8;
    if ( v8 < 0 )
    {
LABEL_6:
      DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report type\n", (unsigned int)v8);
      goto LABEL_19;
    }
    if ( (unsigned int)WerpCheckSpaceAvailable(KeyHandle) )
    {
      v20 = 0;
      v9 = WerpCreateRegistryKey(KeyHandle, a2, 196612, 0, &v17, &v20);
      v7 = v9;
      if ( v9 >= 0 )
      {
        if ( v20 )
        {
          LOBYTE(v10) = 1;
          v8 = WerpCreateRegistryKey(v17, L"Busy", 196612, v10, &v18, 0);
          v7 = v8;
          if ( v8 < 0 )
            goto LABEL_6;
          if ( (unsigned int)Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline() )
          {
            LOBYTE(v11) = 1;
            RegistryKey = WerpCreateRegistryKey(v15, L"LiveReportPending", 0, v11, v19, 0);
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
        }
        else
        {
          v7 = -1073741771;
          DbgPrintEx(5u, 1u, "WERKERNELHOST: Report id %S already exists\n", a2);
        }
      }
      else
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwCreateKey failed with scode 0x%x for the report id\n", (unsigned int)v9);
      }
    }
    else
    {
      v7 = -1073741671;
      DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckSpaceAvailable returned no more space available\n");
    }
  }
LABEL_19:
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
  if ( v15 )
  {
    ZwClose(v15);
    v15 = 0;
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
0x14000e83c  push    rbp
0x14000e83e  push    rbx
0x14000e83f  push    rsi
0x14000e840  push    rdi
0x14000e841  push    r14
0x14000e843  push    r15
0x14000e845  mov     rbp, rsp
0x14000e848  sub     rsp, 68h
0x14000e84c  xor     r15d, r15d
0x14000e84f  lea     rax, [rbp+var_30]
0x14000e853  mov     r14, r8
0x14000e856  mov     [rsp+68h+var_40], r15
0x14000e85b  mov     rdi, rdx
0x14000e85e  mov     [rsp+68h+var_48], rax
0x14000e863  mov     rsi, rcx
0x14000e866  mov     [rbp+Handle], r15
0x14000e86a  xor     r9d, r9d
0x14000e86d  mov     [rbp+KeyHandle], r15
0x14000e871  mov     r8d, 20004h
0x14000e877  mov     [rbp+var_20], r15
0x14000e87b  lea     rdx, g_wszLiveKernelReportsQueueRoot; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000e882  mov     [rbp+var_18], r15
0x14000e886  xor     ecx, ecx
0x14000e888  mov     [rbp+var_10], r15
0x14000e88c  mov     [rbp+var_30], r15
0x14000e890  call    WerpCreateRegistryKey
0x14000e895  mov     ebx, eax
0x14000e897  test    eax, eax
0x14000e899  jns     short loc_14000E8BE
0x14000e89b  lea     r8, aWerkernelhostZ_5; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e8a2  mov     edx, 1; Level
0x14000e8a7  mov     r9d, eax
0x14000e8aa  lea     ecx, [rdx+4]; ComponentId
0x14000e8ad  call    cs:__imp_DbgPrintEx
0x14000e8b4  nop     dword ptr [rax+rax+00h]
0x14000e8b9  jmp     loc_14000EA49
0x14000e8be  mov     rcx, [rbp+var_30]
0x14000e8c2  lea     rax, [rbp+Handle]
0x14000e8c6  mov     [rsp+68h+var_40], r15
0x14000e8cb  lea     rdx, aLivekernelrepo_0; "LiveKernelReports"
0x14000e8d2  xor     r9d, r9d
0x14000e8d5  mov     [rsp+68h+var_48], rax
0x14000e8da  mov     r8d, 20004h
0x14000e8e0  call    WerpCreateRegistryKey
0x14000e8e5  mov     ebx, eax
0x14000e8e7  test    eax, eax
0x14000e8e9  js      short loc_14000E89B
0x14000e8eb  mov     rcx, [rbp+Handle]
0x14000e8ef  lea     rax, [rbp+KeyHandle]
0x14000e8f3  mov     [rsp+68h+var_40], r15
0x14000e8f8  xor     r9d, r9d
0x14000e8fb  mov     r8d, 2001Dh
0x14000e901  mov     [rsp+68h+var_48], rax
0x14000e906  mov     rdx, rsi
0x14000e909  call    WerpCreateRegistryKey
0x14000e90e  mov     ebx, eax
0x14000e910  test    eax, eax
0x14000e912  jns     short loc_14000E91D
0x14000e914  lea     r8, aWerkernelhostZ_6; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e91b  jmp     short loc_14000E8A2
0x14000e91d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e921  call    WerpCheckSpaceAvailable
0x14000e926  test    eax, eax
0x14000e928  jnz     short loc_14000E94D
0x14000e92a  lea     r8, aWerkernelhostW_42; "WERKERNELHOST: WerpCheckSpaceAvailable "...
0x14000e931  mov     ebx, 0C0000099h
0x14000e936  lea     edx, [rax+1]; Level
0x14000e939  lea     ecx, [rax+5]; ComponentId
0x14000e93c  call    cs:__imp_DbgPrintEx
0x14000e943  nop     dword ptr [rax+rax+00h]
0x14000e948  jmp     loc_14000EA49
0x14000e94d  mov     rcx, [rbp+KeyHandle]
0x14000e951  lea     rax, [rbp+arg_18]
0x14000e955  mov     [rsp+68h+var_40], rax
0x14000e95a  mov     esi, 30004h
0x14000e95f  lea     rax, [rbp+var_20]
0x14000e963  mov     [rbp+arg_18], r15b
0x14000e967  xor     r9d, r9d
0x14000e96a  mov     [rsp+68h+var_48], rax
0x14000e96f  mov     r8d, esi
0x14000e972  mov     rdx, rdi
0x14000e975  call    WerpCreateRegistryKey
0x14000e97a  mov     ebx, eax
0x14000e97c  test    eax, eax
0x14000e97e  jns     short loc_14000E98C
0x14000e980  lea     r8, aWerkernelhostZ_11; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e987  jmp     loc_14000E8A2
0x14000e98c  cmp     [rbp+arg_18], r15b
0x14000e990  jnz     short loc_14000E9BA
0x14000e992  mov     edx, 1; Level
0x14000e997  lea     r8, aWerkernelhostR_4; "WERKERNELHOST: Report id %S already exi"...
0x14000e99e  mov     r9, rdi
0x14000e9a1  mov     ebx, 0C0000035h
0x14000e9a6  lea     ecx, [rdx+4]; ComponentId
0x14000e9a9  call    cs:__imp_DbgPrintEx
0x14000e9b0  nop     dword ptr [rax+rax+00h]
0x14000e9b5  jmp     loc_14000EA49
0x14000e9ba  mov     rcx, [rbp+var_20]
0x14000e9be  lea     rax, [rbp+var_18]
0x14000e9c2  mov     [rsp+68h+var_40], r15
0x14000e9c7  lea     rdx, aBusy; "Busy"
0x14000e9ce  mov     r9b, 1
0x14000e9d1  mov     [rsp+68h+var_48], rax
0x14000e9d6  mov     r8d, esi
0x14000e9d9  call    WerpCreateRegistryKey
0x14000e9de  mov     ebx, eax
0x14000e9e0  test    eax, eax
0x14000e9e2  js      loc_14000E914
0x14000e9e8  call    Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline
0x14000e9ed  test    eax, eax
0x14000e9ef  jz      short loc_14000EA36
0x14000e9f1  mov     rcx, [rbp+var_30]
0x14000e9f5  lea     rax, [rbp+var_10]
0x14000e9f9  mov     [rsp+68h+var_40], r15
0x14000e9fe  lea     rdx, aLivereportpend; "LiveReportPending"
0x14000ea05  mov     r9b, 1
0x14000ea08  mov     [rsp+68h+var_48], rax
0x14000ea0d  xor     r8d, r8d
0x14000ea10  call    WerpCreateRegistryKey
0x14000ea15  test    eax, eax
0x14000ea17  jns     short loc_14000EA46
0x14000ea19  xor     edx, edx; Level
0x14000ea1b  lea     r8, aWerkernelhostW_19; "WERKERNELHOST: WerpCreateRegistryKey fa"...
0x14000ea22  mov     r9d, eax
0x14000ea25  lea     ecx, [rdx+5]; ComponentId
0x14000ea28  call    cs:__imp_DbgPrintEx
0x14000ea2f  nop     dword ptr [rax+rax+00h]
0x14000ea34  jmp     short loc_14000EA46
0x14000ea36  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000ea3a  call    cs:__imp_ZwFlushKey
0x14000ea41  nop     dword ptr [rax+rax+00h]
0x14000ea46  mov     ebx, r15d
0x14000ea49  mov     rcx, [rbp+Handle]; Handle
0x14000ea4d  test    rcx, rcx
0x14000ea50  jz      short loc_14000EA62
0x14000ea52  call    cs:__imp_ZwClose
0x14000ea59  nop     dword ptr [rax+rax+00h]
0x14000ea5e  mov     [rbp+Handle], r15
0x14000ea62  mov     rcx, [rbp+KeyHandle]; Handle
0x14000ea66  test    rcx, rcx
0x14000ea69  jz      short loc_14000EA7B
0x14000ea6b  call    cs:__imp_ZwClose
0x14000ea72  nop     dword ptr [rax+rax+00h]
0x14000ea77  mov     [rbp+KeyHandle], r15
0x14000ea7b  mov     rcx, [rbp+var_30]; Handle
0x14000ea7f  test    rcx, rcx
0x14000ea82  jz      short loc_14000EA94
0x14000ea84  call    cs:__imp_ZwClose
0x14000ea8b  nop     dword ptr [rax+rax+00h]
0x14000ea90  mov     [rbp+var_30], r15
0x14000ea94  mov     rax, [rbp+var_20]
0x14000ea98  test    rax, rax
0x14000ea9b  jz      short loc_14000EAB9
0x14000ea9d  test    ebx, ebx
0x14000ea9f  jns     short loc_14000EAB6
0x14000eaa1  mov     rcx, rax; Handle
0x14000eaa4  call    cs:__imp_ZwClose
0x14000eaab  nop     dword ptr [rax+rax+00h]
0x14000eab0  mov     [rbp+var_20], r15
0x14000eab4  jmp     short loc_14000EAB9
0x14000eab6  mov     [r14], rax
0x14000eab9  mov     rcx, [rbp+var_18]; Handle
0x14000eabd  test    rcx, rcx
0x14000eac0  jz      short loc_14000EAD2
0x14000eac2  call    cs:__imp_ZwClose
0x14000eac9  nop     dword ptr [rax+rax+00h]
0x14000eace  mov     [rbp+var_18], r15
0x14000ead2  call    Feature_Servicing_WerReportBootLKD__private_IsEnabledDeviceUsageNoInline
0x14000ead7  test    eax, eax
0x14000ead9  jz      short loc_14000EAF0
0x14000eadb  mov     rcx, [rbp+var_10]; Handle
0x14000eadf  test    rcx, rcx
0x14000eae2  jz      short loc_14000EAF0
0x14000eae4  call    cs:__imp_ZwClose
0x14000eaeb  nop     dword ptr [rax+rax+00h]
0x14000eaf0  mov     eax, ebx
0x14000eaf2  add     rsp, 68h
0x14000eaf6  pop     r15
0x14000eaf8  pop     r14
0x14000eafa  pop     rdi
0x14000eafb  pop     rsi
0x14000eafc  pop     rbx
0x14000eafd  pop     rbp
0x14000eafe  retn
```
