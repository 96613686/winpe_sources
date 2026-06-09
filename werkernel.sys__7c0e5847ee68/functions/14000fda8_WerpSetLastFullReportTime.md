# WerpSetLastFullReportTime

- ea: `0x14000fda8`
- end: `0x1400100ed`
- name: `WerpSetLastFullReportTime`
- size: `837`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400100f4`

## callees

- `0x14000d174`
- `0x14000f3e0`
- `0x14000f6d8`
- `0x14000fda8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000ffb8`
- `ntoskrnl!DbgPrintEx` at `0x140010017`
- `ntoskrnl!DbgPrintEx` at `0x140010072`
- `ntoskrnl!DbgPrintEx` at `0x1400100d1`
- `ntoskrnl!DbgPrintEx` at `0x14000ffb8`
- `ntoskrnl!DbgPrintEx` at `0x140010017`
- `ntoskrnl!DbgPrintEx` at `0x140010072`
- `ntoskrnl!DbgPrintEx` at `0x1400100d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fed4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fed4`
- `ntoskrnl!ZwClose` at `0x140010087`
- `ntoskrnl!ZwClose` at `0x14001009c`
- `ntoskrnl!ZwClose` at `0x1400100b1`
- `ntoskrnl!ZwClose` at `0x140010087`
- `ntoskrnl!ZwClose` at `0x14001009c`
- `ntoskrnl!ZwClose` at `0x1400100b1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000fe4c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000fe4c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe16`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe35`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe16`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe35`
- `ntoskrnl!ZwSetValueKey` at `0x14000ffeb`
- `ntoskrnl!ZwSetValueKey` at `0x14001004c`
- `ntoskrnl!ZwSetValueKey` at `0x14000ffeb`
- `ntoskrnl!ZwSetValueKey` at `0x14001004c`

## string_xrefs

- `0x140010065`: `WERKERNELHOST: Could not open NT_FULL_LIVE_KERNEL_REG_KEY_PATH, status 0x%X\n`
- `0x1400100c4`: `WERKERNELHOST: Could not open NT_FULL_LIVE_KERNEL_REG_KEY_PATH, status 0x%X\n`
- `0x14000ffae`: `WERKERNELHOST: Could not open report type key %ws, status 0x%X\n`
- `0x14000feff`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 __fastcall WerpSetLastFullReportTime(__int64 a1)
{
  WCHAR *v1; // r14
  __int64 v2; // rbx
  PCWSTR v3; // rdi
  PCWSTR *v4; // rsi
  WCHAR *Mem; // rax
  WCHAR *v6; // r8
  __int64 v7; // rcx
  WCHAR *v8; // r9
  __int64 v9; // rdx
  WCHAR *v10; // rcx
  char v11; // si
  int RegistryKey; // eax
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  NTSTATUS v17; // eax
  PVOID Data; // [rsp+20h] [rbp-58h]
  HANDLE v20; // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  char v25; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+40h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp+48h] BYREF
  HANDLE KeyHandle; // [rsp+C8h] [rbp+50h] BYREF

  *(_QWORD *)&ValueName.Length = 2490404;
  v1 = (WCHAR *)(a1 + 24);
  Handle = 0;
  ValueName.Buffer = L"LastFullLiveReport";
  KeyHandle = 0;
  v20 = 0;
  DestinationString = 0;
  String2 = 0;
  v2 = WerKernelThrottlePolicy;
  v26 = MEMORY[0xFFFFF78000000014];
  WerKernelThrottlePolicy = MEMORY[0xFFFFF78000000014];
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 24));
  v3 = SourceString;
  if ( SourceString )
  {
    while ( 1 )
    {
      RtlInitUnicodeString(&String2, v3);
      if ( RtlEqualUnicodeString(&DestinationString, &String2, 0) )
        break;
      v4 = (PCWSTR *)(v3 + 20);
      v3 = (PCWSTR)*((_QWORD *)v3 + 5);
      if ( !v3 )
        goto LABEL_7;
    }
    *((_QWORD *)v3 + 4) = v26;
  }
  else
  {
    v4 = &SourceString;
LABEL_7:
    Mem = (WCHAR *)WerpAllocateMem(48);
    v6 = Mem;
    if ( Mem )
    {
      v7 = 2147483646;
      v8 = v1;
      v9 = 16;
      do
      {
        if ( !v7 )
          break;
        if ( !*v8 )
          break;
        *Mem++ = *v8++;
        --v7;
        --v9;
      }
      while ( v9 );
      v10 = Mem - 1;
      if ( v9 )
        v10 = Mem;
      *v10 = 0;
      if ( v9 )
      {
        *((_QWORD *)v6 + 4) = v26;
        *v4 = v6;
      }
      else
      {
        ExFreePoolWithTag(v6, 0);
      }
    }
  }
  KeyHandle = 0;
  Handle = 0;
  v20 = 0;
  v21 = 0;
  v11 = 0;
  v25 = 0;
  RegistryKey = WerpGetRegistryKey(0, g_wszLiveKernelReportsQueueRoot, 0x20006u, &v20);
  v13 = RegistryKey;
  if ( RegistryKey < 0 || !v20 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not open NT_FULL_LIVE_KERNEL_REG_KEY_PATH, status 0x%X\n", RegistryKey);
    return v13;
  }
  v14 = WerpGetRegistryKey(v20, L"FullLiveKernelReports", 0x20006u, &KeyHandle);
  v13 = v14;
  if ( v14 < 0 || !KeyHandle )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not open NT_FULL_LIVE_KERNEL_REG_KEY_PATH, status 0x%X\n", v14);
    goto LABEL_33;
  }
  v15 = WerpGetRegistryKey(KeyHandle, v1, 0x20006u, &Handle);
  v13 = v15;
  if ( v15 < 0 || !Handle )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not open report type key %ws, status 0x%X\n", v1, v15);
LABEL_26:
    if ( v11 )
      goto LABEL_29;
    goto LABEL_27;
  }
  v16 = WerpQueryComponentOverridePolicy(v1, &v25, &v21);
  v11 = v25;
  v13 = v16;
  if ( v25 )
  {
    WerKernelThrottlePolicy = v2;
    goto LABEL_26;
  }
LABEL_27:
  v17 = ZwSetValueKey(KeyHandle, &ValueName, 0, 0xBu, &v26, 8u);
  v13 = v17;
  if ( v17 < 0 )
  {
LABEL_28:
    LODWORD(Data) = v17;
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Could not set value %ws, status 0x%X\n", L"LastFullLiveReport", Data);
    goto LABEL_33;
  }
LABEL_29:
  if ( Handle )
  {
    v17 = ZwSetValueKey(Handle, &ValueName, 0, 0xBu, &v26, 8u);
    v13 = v17;
    if ( v17 < 0 )
      goto LABEL_28;
LABEL_33:
    if ( Handle )
      ZwClose(Handle);
  }
  if ( v20 )
    ZwClose(v20);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v13;
}

```

## disassembly

```asm
0x14000fda8  push    rbp
0x14000fdaa  push    rbx
0x14000fdab  push    rsi
0x14000fdac  push    rdi
0x14000fdad  push    r14
0x14000fdaf  push    r15
0x14000fdb1  mov     rbp, rsp
0x14000fdb4  sub     rsp, 78h
0x14000fdb8  xor     r15d, r15d
0x14000fdbb  mov     qword ptr [rbp+ValueName.Length], 260024h
0x14000fdc3  mov     [rbp+arg_8], r15
0x14000fdc7  lea     r14, [rcx+18h]
0x14000fdcb  lea     rax, aLastfulllivere; "LastFullLiveReport"
0x14000fdd2  mov     [rbp+Handle], r15
0x14000fdd6  mov     [rbp+ValueName.Buffer], rax
0x14000fdda  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000fdde  xorps   xmm0, xmm0
0x14000fde1  mov     [rbp+KeyHandle], r15
0x14000fde5  xorps   xmm1, xmm1
0x14000fde8  mov     [rbp+var_48], r15
0x14000fdec  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000fdf0  mov     rax, 0FFFFF78000000014h
0x14000fdfa  mov     rdx, r14; SourceString
0x14000fdfd  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14000fe01  mov     rax, [rax]
0x14000fe04  mov     rbx, cs:WerKernelThrottlePolicy
0x14000fe0b  mov     [rbp+arg_8], rax
0x14000fe0f  mov     cs:WerKernelThrottlePolicy, rax
0x14000fe16  call    cs:__imp_RtlInitUnicodeString
0x14000fe1d  nop     dword ptr [rax+rax+00h]
0x14000fe22  mov     rdi, cs:SourceString
0x14000fe29  test    rdi, rdi
0x14000fe2c  jz      short loc_14000FE74
0x14000fe2e  mov     rdx, rdi; SourceString
0x14000fe31  lea     rcx, [rbp+String2]; DestinationString
0x14000fe35  call    cs:__imp_RtlInitUnicodeString
0x14000fe3c  nop     dword ptr [rax+rax+00h]
0x14000fe41  xor     r8d, r8d; CaseInSensitive
0x14000fe44  lea     rdx, [rbp+String2]; String2
0x14000fe48  lea     rcx, [rbp+DestinationString]; String1
0x14000fe4c  call    cs:__imp_RtlEqualUnicodeString
0x14000fe53  nop     dword ptr [rax+rax+00h]
0x14000fe58  test    al, al
0x14000fe5a  jnz     short loc_14000FE6A
0x14000fe5c  lea     rsi, [rdi+28h]
0x14000fe60  mov     rdi, [rsi]
0x14000fe63  test    rdi, rdi
0x14000fe66  jnz     short loc_14000FE2E
0x14000fe68  jmp     short loc_14000FE7B
0x14000fe6a  mov     rax, [rbp+arg_8]
0x14000fe6e  mov     [rdi+20h], rax
0x14000fe72  jmp     short loc_14000FEED
0x14000fe74  lea     rsi, SourceString
0x14000fe7b  mov     ecx, 30h ; '0'
0x14000fe80  call    WerpAllocateMem
0x14000fe85  mov     r8, rax
0x14000fe88  test    rax, rax
0x14000fe8b  jz      short loc_14000FEED
0x14000fe8d  mov     ecx, 7FFFFFFEh
0x14000fe92  mov     r9, r14
0x14000fe95  mov     edx, 10h
0x14000fe9a  test    rcx, rcx
0x14000fe9d  jz      short loc_14000FEBE
0x14000fe9f  movzx   r10d, word ptr [r9]
0x14000fea3  test    r10w, r10w
0x14000fea7  jz      short loc_14000FEBE
0x14000fea9  mov     [rax], r10w
0x14000fead  add     r9, 2
0x14000feb1  add     rax, 2
0x14000feb5  dec     rcx
0x14000feb8  sub     rdx, 1
0x14000febc  jnz     short loc_14000FE9A
0x14000febe  test    rdx, rdx
0x14000fec1  lea     rcx, [rax-2]
0x14000fec5  cmovnz  rcx, rax
0x14000fec9  mov     [rcx], r15w
0x14000fecd  jnz     short loc_14000FEE2
0x14000fecf  xor     edx, edx; Tag
0x14000fed1  mov     rcx, r8; P
0x14000fed4  call    cs:__imp_ExFreePoolWithTag
0x14000fedb  nop     dword ptr [rax+rax+00h]
0x14000fee0  jmp     short loc_14000FEED
0x14000fee2  mov     rax, [rbp+arg_8]
0x14000fee6  mov     [r8+20h], rax
0x14000feea  mov     [rsi], r8
0x14000feed  lea     r9, [rbp+var_48]
0x14000fef1  mov     [rbp+KeyHandle], r15
0x14000fef5  mov     r8d, 20006h
0x14000fefb  mov     [rbp+Handle], r15
0x14000feff  lea     rdx, g_wszLiveKernelReportsQueueRoot; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000ff06  mov     [rbp+var_48], r15
0x14000ff0a  xor     ecx, ecx
0x14000ff0c  mov     [rbp+var_40], r15
0x14000ff10  mov     sil, r15b
0x14000ff13  mov     [rbp+arg_0], r15b
0x14000ff17  call    WerpGetRegistryKey
0x14000ff1c  mov     edi, eax
0x14000ff1e  test    eax, eax
0x14000ff20  js      loc_1400100BF
0x14000ff26  mov     rcx, [rbp+var_48]
0x14000ff2a  test    rcx, rcx
0x14000ff2d  jz      loc_1400100BF
0x14000ff33  lea     r9, [rbp+KeyHandle]
0x14000ff37  mov     r8d, 20006h
0x14000ff3d  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x14000ff44  call    WerpGetRegistryKey
0x14000ff49  mov     edi, eax
0x14000ff4b  test    eax, eax
0x14000ff4d  js      loc_140010060
0x14000ff53  mov     rcx, [rbp+KeyHandle]
0x14000ff57  test    rcx, rcx
0x14000ff5a  jz      loc_140010060
0x14000ff60  lea     r9, [rbp+Handle]
0x14000ff64  mov     r8d, 20006h
0x14000ff6a  mov     rdx, r14
0x14000ff6d  call    WerpGetRegistryKey
0x14000ff72  mov     edi, eax
0x14000ff74  test    eax, eax
0x14000ff76  js      short loc_14000FFA2
0x14000ff78  cmp     [rbp+Handle], r15
0x14000ff7c  jz      short loc_14000FFA2
0x14000ff7e  lea     r8, [rbp+var_40]
0x14000ff82  mov     rcx, r14
0x14000ff85  lea     rdx, [rbp+arg_0]
0x14000ff89  call    WerpQueryComponentOverridePolicy
0x14000ff8e  mov     sil, [rbp+arg_0]
0x14000ff92  mov     edi, eax
0x14000ff94  test    sil, sil
0x14000ff97  jz      short loc_14000FFC9
0x14000ff99  mov     cs:WerKernelThrottlePolicy, rbx
0x14000ffa0  jmp     short loc_14000FFC4
0x14000ffa2  mov     edx, 1; Level
0x14000ffa7  mov     dword ptr [rsp+78h+Data], eax
0x14000ffab  mov     r9, r14
0x14000ffae  lea     r8, aWerkernelhostC_6; "WERKERNELHOST: Could not open report ty"...
0x14000ffb5  lea     ecx, [rdx+4]; ComponentId
0x14000ffb8  call    cs:__imp_DbgPrintEx
0x14000ffbf  nop     dword ptr [rax+rax+00h]
0x14000ffc4  test    sil, sil
0x14000ffc7  jnz     short loc_140010025
0x14000ffc9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000ffcd  lea     rax, [rbp+arg_8]
0x14000ffd1  mov     [rsp+78h+DataSize], 8; DataSize
0x14000ffd9  lea     rdx, [rbp+ValueName]; ValueName
0x14000ffdd  mov     r9d, 0Bh; Type
0x14000ffe3  mov     [rsp+78h+Data], rax; Data
0x14000ffe8  xor     r8d, r8d; TitleIndex
0x14000ffeb  call    cs:__imp_ZwSetValueKey
0x14000fff2  nop     dword ptr [rax+rax+00h]
0x14000fff7  mov     edi, eax
0x14000fff9  test    eax, eax
0x14000fffb  jns     short loc_140010025
0x14000fffd  mov     edx, 1; Level
0x140010002  mov     dword ptr [rsp+78h+Data], eax
0x140010006  lea     r9, aLastfulllivere; "LastFullLiveReport"
0x14001000d  lea     r8, aWerkernelhostC_9; "WERKERNELHOST: Could not set value %ws,"...
0x140010014  lea     ecx, [rdx+4]; ComponentId
0x140010017  call    cs:__imp_DbgPrintEx
0x14001001e  nop     dword ptr [rax+rax+00h]
0x140010023  jmp     short loc_14001007E
0x140010025  mov     rcx, [rbp+Handle]; KeyHandle
0x140010029  test    rcx, rcx
0x14001002c  jz      short loc_140010093
0x14001002e  lea     rax, [rbp+arg_8]
0x140010032  mov     [rsp+78h+DataSize], 8; DataSize
0x14001003a  mov     r9d, 0Bh; Type
0x140010040  mov     [rsp+78h+Data], rax; Data
0x140010045  xor     r8d, r8d; TitleIndex
0x140010048  lea     rdx, [rbp+ValueName]; ValueName
0x14001004c  call    cs:__imp_ZwSetValueKey
0x140010053  nop     dword ptr [rax+rax+00h]
0x140010058  mov     edi, eax
0x14001005a  test    eax, eax
0x14001005c  jns     short loc_14001007E
0x14001005e  jmp     short loc_14000FFFD
0x140010060  mov     edx, 1; Level
0x140010065  lea     r8, aWerkernelhostC_4; "WERKERNELHOST: Could not open NT_FULL_L"...
0x14001006c  mov     r9d, eax
0x14001006f  lea     ecx, [rdx+4]; ComponentId
0x140010072  call    cs:__imp_DbgPrintEx
0x140010079  nop     dword ptr [rax+rax+00h]
0x14001007e  mov     rcx, [rbp+Handle]; Handle
0x140010082  test    rcx, rcx
0x140010085  jz      short loc_140010093
0x140010087  call    cs:__imp_ZwClose
0x14001008e  nop     dword ptr [rax+rax+00h]
0x140010093  mov     rcx, [rbp+var_48]; Handle
0x140010097  test    rcx, rcx
0x14001009a  jz      short loc_1400100A8
0x14001009c  call    cs:__imp_ZwClose
0x1400100a3  nop     dword ptr [rax+rax+00h]
0x1400100a8  mov     rcx, [rbp+KeyHandle]; Handle
0x1400100ac  test    rcx, rcx
0x1400100af  jz      short loc_1400100DD
0x1400100b1  call    cs:__imp_ZwClose
0x1400100b8  nop     dword ptr [rax+rax+00h]
0x1400100bd  jmp     short loc_1400100DD
0x1400100bf  mov     edx, 1; Level
0x1400100c4  lea     r8, aWerkernelhostC_4; "WERKERNELHOST: Could not open NT_FULL_L"...
0x1400100cb  mov     r9d, edi
0x1400100ce  lea     ecx, [rdx+4]; ComponentId
0x1400100d1  call    cs:__imp_DbgPrintEx
0x1400100d8  nop     dword ptr [rax+rax+00h]
0x1400100dd  mov     eax, edi
0x1400100df  add     rsp, 78h
0x1400100e3  pop     r15
0x1400100e5  pop     r14
0x1400100e7  pop     rdi
0x1400100e8  pop     rsi
0x1400100e9  pop     rbx
0x1400100ea  pop     rbp
0x1400100eb  retn
```
