# IsWin32kRefreshed(void)

- ea: `0x1401df3c0`
- end: `0x1401df619`
- name: `?IsWin32kRefreshed@@YA_NXZ`
- size: `601`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402d9400`

## callees

- `0x14013c840`
- `0x1401df3c0`
- `0x140238160`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1401df4a3`
- `ntoskrnl!ZwOpenKey` at `0x1401df4a3`
- `ntoskrnl!ZwQueryValueKey` at `0x1401df51a`
- `ntoskrnl!ZwQueryValueKey` at `0x1401df51a`
- `ntoskrnl!ZwClose` at `0x1401df5f1`
- `ntoskrnl!ZwClose` at `0x1401df5f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401df5db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401df5db`
- `ntoskrnl!ZwSetValueKey` at `0x1401df5b5`
- `ntoskrnl!ZwSetValueKey` at `0x1401df5b5`
- `ntoskrnl!ExAllocatePool2` at `0x1401df4e0`
- `ntoskrnl!ExAllocatePool2` at `0x1401df4e0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401df56c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401df56c`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401df448`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1401df448`
- `ntoskrnl!ZwFlushKey` at `0x1401df5ca`
- `ntoskrnl!ZwFlushKey` at `0x1401df5ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df467`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df4c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df555`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df467`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df4c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401df555`

## string_xrefs

- `0x1401df45c`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION\WINDOWS`
- `0x1401df3e8`: `\systemroot\system32\win32kbase.sys`
- `0x1401df4b7`: `Win32kLastWriteTime`

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
0x1401df3c0  push    rbp
0x1401df3c2  push    rbx
0x1401df3c3  push    rsi
0x1401df3c4  push    rdi
0x1401df3c5  lea     rbp, [rsp-3Fh]
0x1401df3ca  sub     rsp, 0F8h
0x1401df3d1  mov     rax, cs:__security_cookie
0x1401df3d8  xor     rax, rsp
0x1401df3db  mov     [rbp+57h+var_30], rax
0x1401df3df  xorps   xmm0, xmm0
0x1401df3e2  lea     rdx, [rbp+57h+Value]
0x1401df3e6  xor     esi, esi
0x1401df3e8  lea     rcx, aSystemrootSyst_4; "\\systemroot\\system32\\win32kbase.sys"
0x1401df3ef  xorps   xmm1, xmm1
0x1401df3f2  mov     [rsp+110h+KeyHandle], rsi
0x1401df3f7  xor     r8d, r8d
0x1401df3fa  mov     [rsp+110h+var_E0], esi
0x1401df3fe  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1401df402  lea     edi, [rsi+1]
0x1401df405  mov     [rbp+57h+Value], rsi
0x1401df409  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1401df40d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401df411  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401df415  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1401df419  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x1401df41d  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x1401df421  call    Win32FileInfo
0x1401df426  test    eax, eax
0x1401df428  jz      loc_1401DF5E7
0x1401df42e  mov     rcx, [rbp+57h+Value]; Value
0x1401df432  lea     rax, [rbp+57h+Data]
0x1401df436  lea     r8, [rbp+57h+String]; String
0x1401df43a  mov     [rbp+57h+String.Buffer], rax
0x1401df43e  lea     edx, [rsi+10h]; Base
0x1401df441  mov     dword ptr [rbp+57h+String.Length], 220000h
0x1401df448  call    cs:__imp_RtlInt64ToUnicodeString
0x1401df44f  nop     dword ptr [rax+rax+00h]
0x1401df454  test    eax, eax
0x1401df456  js      loc_1401DF5E7
0x1401df45c  lea     rdx, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x1401df463  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401df467  call    cs:__imp_RtlInitUnicodeString
0x1401df46e  nop     dword ptr [rax+rax+00h]
0x1401df473  lea     rax, [rbp+57h+DestinationString]
0x1401df477  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401df47e  xorps   xmm0, xmm0
0x1401df481  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401df485  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1401df489  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1401df48d  mov     edx, 2001Fh; DesiredAccess
0x1401df492  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1401df499  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401df49e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401df4a3  call    cs:__imp_ZwOpenKey
0x1401df4aa  nop     dword ptr [rax+rax+00h]
0x1401df4af  test    eax, eax
0x1401df4b1  js      loc_1401DF5E7
0x1401df4b7  lea     rdx, aWin32klastwrit; "Win32kLastWriteTime"
0x1401df4be  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1401df4c2  call    cs:__imp_RtlInitUnicodeString
0x1401df4c9  nop     dword ptr [rax+rax+00h]
0x1401df4ce  lea     edx, [rsi+2Eh]
0x1401df4d1  mov     ecx, 100h
0x1401df4d6  mov     r8d, 746C7355h
0x1401df4dc  mov     [rsp+110h+var_E0], edx
0x1401df4e0  call    cs:__imp_ExAllocatePool2
0x1401df4e7  nop     dword ptr [rax+rax+00h]
0x1401df4ec  mov     rbx, rax
0x1401df4ef  test    rax, rax
0x1401df4f2  jz      loc_1401DF5E7
0x1401df4f8  mov     ecx, [rsp+110h+var_E0]
0x1401df4fc  lea     rax, [rsp+110h+var_E0]
0x1401df501  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1401df506  lea     r8d, [rsi+2]; KeyValueInformationClass
0x1401df50a  mov     [rsp+110h+Length], ecx; Length
0x1401df50e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401df512  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401df517  mov     r9, rbx; KeyValueInformation
0x1401df51a  call    cs:__imp_ZwQueryValueKey
0x1401df521  nop     dword ptr [rax+rax+00h]
0x1401df526  test    eax, eax
0x1401df528  js      short loc_1401DF581
0x1401df52a  mov     ecx, [rsp+110h+var_E0]
0x1401df52e  mov     eax, [rbx+8]
0x1401df531  shr     eax, 1
0x1401df533  cmp     eax, ecx
0x1401df535  cmovb   ecx, eax
0x1401df538  mov     [rsp+110h+var_E0], ecx
0x1401df53c  cmp     ecx, edi
0x1401df53e  jbe     short loc_1401DF581
0x1401df540  lea     rdx, [rbx+0Ch]; SourceString
0x1401df544  cmp     [rdx], si
0x1401df547  jz      short loc_1401DF581
0x1401df549  lea     eax, [rcx-1]
0x1401df54c  lea     rcx, [rbp+57h+String1]; DestinationString
0x1401df550  mov     [rbx+rax*2+0Ch], si
0x1401df555  call    cs:__imp_RtlInitUnicodeString
0x1401df55c  nop     dword ptr [rax+rax+00h]
0x1401df561  xor     r8d, r8d; CaseInSensitive
0x1401df564  lea     rdx, [rbp+57h+String]; String2
0x1401df568  lea     rcx, [rbp+57h+String1]; String1
0x1401df56c  call    cs:__imp_RtlCompareUnicodeString
0x1401df573  nop     dword ptr [rax+rax+00h]
0x1401df578  test    eax, eax
0x1401df57a  jnz     short loc_1401DF581
0x1401df57c  mov     dil, sil
0x1401df57f  jmp     short loc_1401DF5D6
0x1401df581  lea     rcx, [rbp+57h+Data]
0x1401df585  or      rax, 0FFFFFFFFFFFFFFFFh
0x1401df589  inc     rax
0x1401df58c  cmp     [rcx+rax*2], si
0x1401df590  jnz     short loc_1401DF589
0x1401df592  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401df597  lea     eax, ds:2[rax*2]
0x1401df59e  mov     dword ptr [rsp+110h+ResultLength], eax; DataSize
0x1401df5a2  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1401df5a6  lea     rax, [rbp+57h+Data]
0x1401df5aa  mov     r9d, edi; Type
0x1401df5ad  xor     r8d, r8d; TitleIndex
0x1401df5b0  mov     qword ptr [rsp+110h+Length], rax; Data
0x1401df5b5  call    cs:__imp_ZwSetValueKey
0x1401df5bc  nop     dword ptr [rax+rax+00h]
0x1401df5c1  test    eax, eax
0x1401df5c3  js      short loc_1401DF5D6
0x1401df5c5  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1401df5ca  call    cs:__imp_ZwFlushKey
0x1401df5d1  nop     dword ptr [rax+rax+00h]
0x1401df5d6  xor     edx, edx; Tag
0x1401df5d8  mov     rcx, rbx; P
0x1401df5db  call    cs:__imp_ExFreePoolWithTag
0x1401df5e2  nop     dword ptr [rax+rax+00h]
0x1401df5e7  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x1401df5ec  test    rcx, rcx
0x1401df5ef  jz      short loc_1401DF5FD
0x1401df5f1  call    cs:__imp_ZwClose
0x1401df5f8  nop     dword ptr [rax+rax+00h]
0x1401df5fd  mov     al, dil
0x1401df600  mov     rcx, [rbp+57h+var_30]
0x1401df604  xor     rcx, rsp; StackCookie
0x1401df607  call    __security_check_cookie
0x1401df60c  add     rsp, 0F8h
0x1401df613  pop     rdi
0x1401df614  pop     rsi
0x1401df615  pop     rbx
0x1401df616  pop     rbp
0x1401df617  retn
```
