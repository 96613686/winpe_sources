# IsWin32kRefreshed(void)

- ea: `0x1401df920`
- end: `0x1401dfb79`
- name: `?IsWin32kRefreshed@@YA_NXZ`
- size: `601`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402db400`

## callees

- `0x14013c260`
- `0x1401df920`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1401dfa03`
- `ntoskrnl!ZwOpenKey` at `0x1401dfa03`
- `ntoskrnl!ZwQueryValueKey` at `0x1401dfa7a`
- `ntoskrnl!ZwQueryValueKey` at `0x1401dfa7a`
- `ntoskrnl!ZwClose` at `0x1401dfb51`
- `ntoskrnl!ZwClose` at `0x1401dfb51`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401dfb3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401dfb3b`
- `ntoskrnl!ZwSetValueKey` at `0x1401dfb15`
- `ntoskrnl!ZwSetValueKey` at `0x1401dfb15`
- `ntoskrnl!ExAllocatePool2` at `0x1401dfa40`
- `ntoskrnl!ExAllocatePool2` at `0x1401dfa40`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401dfacc`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401dfacc`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401df9a8`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401df9a8`
- `ntoskrnl!ZwFlushKey` at `0x1401dfb2a`
- `ntoskrnl!ZwFlushKey` at `0x1401dfb2a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df9c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dfa22`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dfab5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df9c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dfa22`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401dfab5`

## string_xrefs

- `0x1401df9bc`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION\WINDOWS`
- `0x1401df948`: `\systemroot\system32\win32kbase.sys`
- `0x1401dfa17`: `Win32kLastWriteTime`

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
  ULONGLONG Value; // [rsp+40h] [rbp-79h]
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
  if ( (unsigned int)Win32FileInfo(L"\\systemroot\\system32\\win32kbase.sys") )
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
0x1401df920  push    rbp
0x1401df922  push    rbx
0x1401df923  push    rsi
0x1401df924  push    rdi
0x1401df925  lea     rbp, [rsp-3Fh]
0x1401df92a  sub     rsp, 0F8h
0x1401df931  mov     rax, cs:__security_cookie
0x1401df938  xor     rax, rsp
0x1401df93b  mov     [rbp+57h+var_30], rax
0x1401df93f  xorps   xmm0, xmm0
0x1401df942  lea     rdx, [rbp+57h+Value]
0x1401df946  xor     esi, esi
0x1401df948  lea     rcx, aSystemrootSyst_4; "\\systemroot\\system32\\win32kbase.sys"
0x1401df94f  xorps   xmm1, xmm1
0x1401df952  mov     [rsp+110h+KeyHandle], rsi
0x1401df957  xor     r8d, r8d
0x1401df95a  mov     [rsp+110h+var_E0], esi
0x1401df95e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1401df962  lea     edi, [rsi+1]
0x1401df965  mov     [rbp+57h+Value], rsi
0x1401df969  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1401df96d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401df971  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401df975  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1401df979  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x1401df97d  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x1401df981  call    Win32FileInfo
0x1401df986  test    eax, eax
0x1401df988  jz      loc_1401DFB47
0x1401df98e  mov     rcx, [rbp+57h+Value]; Value
0x1401df992  lea     rax, [rbp+57h+Data]
0x1401df996  lea     r8, [rbp+57h+String]; String
0x1401df99a  mov     [rbp+57h+String.Buffer], rax
0x1401df99e  lea     edx, [rsi+10h]; Base
0x1401df9a1  mov     dword ptr [rbp+57h+String.Length], 220000h
0x1401df9a8  call    cs:__imp_RtlInt64ToUnicodeString
0x1401df9af  nop     dword ptr [rax+rax+00h]
0x1401df9b4  test    eax, eax
0x1401df9b6  js      loc_1401DFB47
0x1401df9bc  lea     rdx, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x1401df9c3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401df9c7  call    cs:__imp_RtlInitUnicodeString
0x1401df9ce  nop     dword ptr [rax+rax+00h]
0x1401df9d3  lea     rax, [rbp+57h+DestinationString]
0x1401df9d7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401df9de  xorps   xmm0, xmm0
0x1401df9e1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401df9e5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401df9e9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1401df9ed  mov     edx, 2001Fh; DesiredAccess
0x1401df9f2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1401df9f9  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401df9fe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401dfa03  call    cs:__imp_ZwOpenKey
0x1401dfa0a  nop     dword ptr [rax+rax+00h]
0x1401dfa0f  test    eax, eax
0x1401dfa11  js      loc_1401DFB47
0x1401dfa17  lea     rdx, aWin32klastwrit; "Win32kLastWriteTime"
0x1401dfa1e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1401dfa22  call    cs:__imp_RtlInitUnicodeString
0x1401dfa29  nop     dword ptr [rax+rax+00h]
0x1401dfa2e  lea     edx, [rsi+2Eh]
0x1401dfa31  mov     ecx, 100h
0x1401dfa36  mov     r8d, 746C7355h
0x1401dfa3c  mov     [rsp+110h+var_E0], edx
0x1401dfa40  call    cs:__imp_ExAllocatePool2
0x1401dfa47  nop     dword ptr [rax+rax+00h]
0x1401dfa4c  mov     rbx, rax
0x1401dfa4f  test    rax, rax
0x1401dfa52  jz      loc_1401DFB47
0x1401dfa58  mov     ecx, [rsp+110h+var_E0]
0x1401dfa5c  lea     rax, [rsp+110h+var_E0]
0x1401dfa61  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401dfa66  lea     r8d, [rsi+2]; KeyValueInformationClass
0x1401dfa6a  mov     [rsp+110h+Length], ecx; Length
0x1401dfa6e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401dfa72  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401dfa77  mov     r9, rbx; KeyValueInformation
0x1401dfa7a  call    cs:__imp_ZwQueryValueKey
0x1401dfa81  nop     dword ptr [rax+rax+00h]
0x1401dfa86  test    eax, eax
0x1401dfa88  js      short loc_1401DFAE1
0x1401dfa8a  mov     ecx, [rsp+110h+var_E0]
0x1401dfa8e  mov     eax, [rbx+8]
0x1401dfa91  shr     eax, 1
0x1401dfa93  cmp     eax, ecx
0x1401dfa95  cmovb   ecx, eax
0x1401dfa98  mov     [rsp+110h+var_E0], ecx
0x1401dfa9c  cmp     ecx, edi
0x1401dfa9e  jbe     short loc_1401DFAE1
0x1401dfaa0  lea     rdx, [rbx+0Ch]; SourceString
0x1401dfaa4  cmp     [rdx], si
0x1401dfaa7  jz      short loc_1401DFAE1
0x1401dfaa9  lea     eax, [rcx-1]
0x1401dfaac  lea     rcx, [rbp+57h+String1]; DestinationString
0x1401dfab0  mov     [rbx+rax*2+0Ch], si
0x1401dfab5  call    cs:__imp_RtlInitUnicodeString
0x1401dfabc  nop     dword ptr [rax+rax+00h]
0x1401dfac1  xor     r8d, r8d; CaseInSensitive
0x1401dfac4  lea     rdx, [rbp+57h+String]; String2
0x1401dfac8  lea     rcx, [rbp+57h+String1]; String1
0x1401dfacc  call    cs:__imp_RtlCompareUnicodeString
0x1401dfad3  nop     dword ptr [rax+rax+00h]
0x1401dfad8  test    eax, eax
0x1401dfada  jnz     short loc_1401DFAE1
0x1401dfadc  mov     dil, sil
0x1401dfadf  jmp     short loc_1401DFB36
0x1401dfae1  lea     rcx, [rbp+57h+Data]
0x1401dfae5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401dfae9  inc     rax
0x1401dfaec  cmp     [rcx+rax*2], si
0x1401dfaf0  jnz     short loc_1401DFAE9
0x1401dfaf2  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401dfaf7  lea     eax, ds:2[rax*2]
0x1401dfafe  mov     dword ptr [rsp+110h+ResultLength], eax; DataSize
0x1401dfb02  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401dfb06  lea     rax, [rbp+57h+Data]
0x1401dfb0a  mov     r9d, edi; Type
0x1401dfb0d  xor     r8d, r8d; TitleIndex
0x1401dfb10  mov     qword ptr [rsp+110h+Length], rax; Data
0x1401dfb15  call    cs:__imp_ZwSetValueKey
0x1401dfb1c  nop     dword ptr [rax+rax+00h]
0x1401dfb21  test    eax, eax
0x1401dfb23  js      short loc_1401DFB36
0x1401dfb25  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401dfb2a  call    cs:__imp_ZwFlushKey
0x1401dfb31  nop     dword ptr [rax+rax+00h]
0x1401dfb36  xor     edx, edx; Tag
0x1401dfb38  mov     rcx, rbx; P
0x1401dfb3b  call    cs:__imp_ExFreePoolWithTag
0x1401dfb42  nop     dword ptr [rax+rax+00h]
0x1401dfb47  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x1401dfb4c  test    rcx, rcx
0x1401dfb4f  jz      short loc_1401DFB5D
0x1401dfb51  call    cs:__imp_ZwClose
0x1401dfb58  nop     dword ptr [rax+rax+00h]
0x1401dfb5d  mov     al, dil
0x1401dfb60  mov     rcx, [rbp+57h+var_30]
0x1401dfb64  xor     rcx, rsp; StackCookie
0x1401dfb67  call    __security_check_cookie
0x1401dfb6c  add     rsp, 0F8h
0x1401dfb73  pop     rdi
0x1401dfb74  pop     rsi
0x1401dfb75  pop     rbx
0x1401dfb76  pop     rbp
0x1401dfb77  retn
```
