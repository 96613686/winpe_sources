# IsWin32kRefreshed(void)

- ea: `0x1401dff00`
- end: `0x1401e0159`
- name: `?IsWin32kRefreshed@@YA_NXZ`
- size: `601`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402d9400`

## callees

- `0x14013ea20`
- `0x1401dff00`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1401dffe3`
- `ntoskrnl!ZwOpenKey` at `0x1401dffe3`
- `ntoskrnl!ZwQueryValueKey` at `0x1401e005a`
- `ntoskrnl!ZwQueryValueKey` at `0x1401e005a`
- `ntoskrnl!ZwClose` at `0x1401e0131`
- `ntoskrnl!ZwClose` at `0x1401e0131`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e011b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e011b`
- `ntoskrnl!ZwSetValueKey` at `0x1401e00f5`
- `ntoskrnl!ZwSetValueKey` at `0x1401e00f5`
- `ntoskrnl!ExAllocatePool2` at `0x1401e0020`
- `ntoskrnl!ExAllocatePool2` at `0x1401e0020`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401e00ac`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401e00ac`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401dff88`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401dff88`
- `ntoskrnl!ZwFlushKey` at `0x1401e010a`
- `ntoskrnl!ZwFlushKey` at `0x1401e010a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dffa7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e0002`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e0095`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dffa7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e0002`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e0095`

## string_xrefs

- `0x1401dff9c`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION\WINDOWS`
- `0x1401dff28`: `\systemroot\system32\win32kbase.sys`
- `0x1401dfff7`: `Win32kLastWriteTime`

## pseudocode

```c
char IsWin32kRefreshed(void)
{
  char v0; // di
  __int64 Pool2; // rbx
  ULONG v2; // ecx
  __int64 v3; // rax
  ULONG Length; // [rsp+30h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-81h] BYREF
  ULONGLONG Value; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING String; // [rsp+48h] [rbp-71h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-51h] BYREF
  UNICODE_STRING String1; // [rsp+78h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-31h] BYREF
  _WORD Data[20]; // [rsp+B8h] [rbp-1h] BYREF

  KeyHandle = 0;
  Length = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v0 = 1;
  Value = 0;
  DestinationString = 0;
  ValueName = 0;
  String = 0;
  String1 = 0;
  if ( Win32FileInfo(L"\\systemroot\\system32\\win32kbase.sys", &Value, 0) )
  {
    String.Buffer = Data;
    *(_DWORD *)&String.Length = 2228224;
    if ( RtlInt64ToUnicodeString(Value, 0x10u, &String) >= 0 )
    {
      RtlInitUnicodeString(
        &DestinationString,
        L"\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOFT\\WINDOWS NT\\CURRENTVERSION\\WINDOWS");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes) >= 0 )
      {
        RtlInitUnicodeString(&ValueName, L"Win32kLastWriteTime");
        Length = 46;
        Pool2 = ExAllocatePool2(256, 46, 1953264469);
        if ( Pool2 )
        {
          if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, Length, &Length) < 0 )
            goto LABEL_12;
          v2 = Length;
          if ( *(_DWORD *)(Pool2 + 8) >> 1 < Length )
            v2 = *(_DWORD *)(Pool2 + 8) >> 1;
          Length = v2;
          if ( v2 <= 1
            || !*(_WORD *)(Pool2 + 12)
            || (*(_WORD *)(Pool2 + 2LL * (v2 - 1) + 12) = 0,
                RtlInitUnicodeString(&String1, (PCWSTR)(Pool2 + 12)),
                RtlCompareUnicodeString(&String1, &String, 0)) )
          {
LABEL_12:
            v3 = -1;
            do
              ++v3;
            while ( Data[v3] );
            if ( ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, 2 * v3 + 2) >= 0 )
              ZwFlushKey(KeyHandle);
          }
          else
          {
            v0 = 0;
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x1401dff00  push    rbp
0x1401dff02  push    rbx
0x1401dff03  push    rsi
0x1401dff04  push    rdi
0x1401dff05  lea     rbp, [rsp-3Fh]
0x1401dff0a  sub     rsp, 0F8h
0x1401dff11  mov     rax, cs:__security_cookie
0x1401dff18  xor     rax, rsp
0x1401dff1b  mov     [rbp+57h+var_30], rax
0x1401dff1f  xorps   xmm0, xmm0
0x1401dff22  lea     rdx, [rbp+57h+Value]
0x1401dff26  xor     esi, esi
0x1401dff28  lea     rcx, aSystemrootSyst_4; "\\systemroot\\system32\\win32kbase.sys"
0x1401dff2f  xorps   xmm1, xmm1
0x1401dff32  mov     [rsp+110h+KeyHandle], rsi
0x1401dff37  xor     r8d, r8d
0x1401dff3a  mov     [rsp+110h+var_E0], esi
0x1401dff3e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1401dff42  lea     edi, [rsi+1]
0x1401dff45  mov     [rbp+57h+Value], rsi
0x1401dff49  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1401dff4d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401dff51  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401dff55  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1401dff59  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x1401dff5d  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x1401dff61  call    Win32FileInfo
0x1401dff66  test    eax, eax
0x1401dff68  jz      loc_1401E0127
0x1401dff6e  mov     rcx, [rbp+57h+Value]; Value
0x1401dff72  lea     rax, [rbp+57h+Data]
0x1401dff76  lea     r8, [rbp+57h+String]; String
0x1401dff7a  mov     [rbp+57h+String.Buffer], rax
0x1401dff7e  lea     edx, [rsi+10h]; Base
0x1401dff81  mov     dword ptr [rbp+57h+String.Length], 220000h
0x1401dff88  call    cs:__imp_RtlInt64ToUnicodeString
0x1401dff8f  nop     dword ptr [rax+rax+00h]
0x1401dff94  test    eax, eax
0x1401dff96  js      loc_1401E0127
0x1401dff9c  lea     rdx, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x1401dffa3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401dffa7  call    cs:__imp_RtlInitUnicodeString
0x1401dffae  nop     dword ptr [rax+rax+00h]
0x1401dffb3  lea     rax, [rbp+57h+DestinationString]
0x1401dffb7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401dffbe  xorps   xmm0, xmm0
0x1401dffc1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401dffc5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401dffc9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1401dffcd  mov     edx, 2001Fh; DesiredAccess
0x1401dffd2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1401dffd9  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401dffde  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401dffe3  call    cs:__imp_ZwOpenKey
0x1401dffea  nop     dword ptr [rax+rax+00h]
0x1401dffef  test    eax, eax
0x1401dfff1  js      loc_1401E0127
0x1401dfff7  lea     rdx, aWin32klastwrit; "Win32kLastWriteTime"
0x1401dfffe  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1401e0002  call    cs:__imp_RtlInitUnicodeString
0x1401e0009  nop     dword ptr [rax+rax+00h]
0x1401e000e  lea     edx, [rsi+2Eh]
0x1401e0011  mov     ecx, 100h
0x1401e0016  mov     r8d, 746C7355h
0x1401e001c  mov     [rsp+110h+var_E0], edx
0x1401e0020  call    cs:__imp_ExAllocatePool2
0x1401e0027  nop     dword ptr [rax+rax+00h]
0x1401e002c  mov     rbx, rax
0x1401e002f  test    rax, rax
0x1401e0032  jz      loc_1401E0127
0x1401e0038  mov     ecx, [rsp+110h+var_E0]
0x1401e003c  lea     rax, [rsp+110h+var_E0]
0x1401e0041  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401e0046  lea     r8d, [rsi+2]; KeyValueInformationClass
0x1401e004a  mov     [rsp+110h+Length], ecx; Length
0x1401e004e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401e0052  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401e0057  mov     r9, rbx; KeyValueInformation
0x1401e005a  call    cs:__imp_ZwQueryValueKey
0x1401e0061  nop     dword ptr [rax+rax+00h]
0x1401e0066  test    eax, eax
0x1401e0068  js      short loc_1401E00C1
0x1401e006a  mov     ecx, [rsp+110h+var_E0]
0x1401e006e  mov     eax, [rbx+8]
0x1401e0071  shr     eax, 1
0x1401e0073  cmp     eax, ecx
0x1401e0075  cmovb   ecx, eax
0x1401e0078  mov     [rsp+110h+var_E0], ecx
0x1401e007c  cmp     ecx, edi
0x1401e007e  jbe     short loc_1401E00C1
0x1401e0080  lea     rdx, [rbx+0Ch]; SourceString
0x1401e0084  cmp     [rdx], si
0x1401e0087  jz      short loc_1401E00C1
0x1401e0089  lea     eax, [rcx-1]
0x1401e008c  lea     rcx, [rbp+57h+String1]; DestinationString
0x1401e0090  mov     [rbx+rax*2+0Ch], si
0x1401e0095  call    cs:__imp_RtlInitUnicodeString
0x1401e009c  nop     dword ptr [rax+rax+00h]
0x1401e00a1  xor     r8d, r8d; CaseInSensitive
0x1401e00a4  lea     rdx, [rbp+57h+String]; String2
0x1401e00a8  lea     rcx, [rbp+57h+String1]; String1
0x1401e00ac  call    cs:__imp_RtlCompareUnicodeString
0x1401e00b3  nop     dword ptr [rax+rax+00h]
0x1401e00b8  test    eax, eax
0x1401e00ba  jnz     short loc_1401E00C1
0x1401e00bc  mov     dil, sil
0x1401e00bf  jmp     short loc_1401E0116
0x1401e00c1  lea     rcx, [rbp+57h+Data]
0x1401e00c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401e00c9  inc     rax
0x1401e00cc  cmp     [rcx+rax*2], si
0x1401e00d0  jnz     short loc_1401E00C9
0x1401e00d2  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401e00d7  lea     eax, ds:2[rax*2]
0x1401e00de  mov     dword ptr [rsp+110h+ResultLength], eax; DataSize
0x1401e00e2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401e00e6  lea     rax, [rbp+57h+Data]
0x1401e00ea  mov     r9d, edi; Type
0x1401e00ed  xor     r8d, r8d; TitleIndex
0x1401e00f0  mov     qword ptr [rsp+110h+Length], rax; Data
0x1401e00f5  call    cs:__imp_ZwSetValueKey
0x1401e00fc  nop     dword ptr [rax+rax+00h]
0x1401e0101  test    eax, eax
0x1401e0103  js      short loc_1401E0116
0x1401e0105  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401e010a  call    cs:__imp_ZwFlushKey
0x1401e0111  nop     dword ptr [rax+rax+00h]
0x1401e0116  xor     edx, edx; Tag
0x1401e0118  mov     rcx, rbx; P
0x1401e011b  call    cs:__imp_ExFreePoolWithTag
0x1401e0122  nop     dword ptr [rax+rax+00h]
0x1401e0127  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x1401e012c  test    rcx, rcx
0x1401e012f  jz      short loc_1401E013D
0x1401e0131  call    cs:__imp_ZwClose
0x1401e0138  nop     dword ptr [rax+rax+00h]
0x1401e013d  mov     al, dil
0x1401e0140  mov     rcx, [rbp+57h+var_30]
0x1401e0144  xor     rcx, rsp; StackCookie
0x1401e0147  call    __security_check_cookie
0x1401e014c  add     rsp, 0F8h
0x1401e0153  pop     rdi
0x1401e0154  pop     rsi
0x1401e0155  pop     rbx
0x1401e0156  pop     rbp
0x1401e0157  retn
```
