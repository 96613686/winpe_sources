# WimpFSFIsIntegrityMandatory

- ea: `0x14002a700`
- end: `0x14002a83f`
- name: `WimpFSFIsIntegrityMandatory`
- size: `319`
- prototype: `__int64 __fastcall(__int64 Val)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140028488`

## callees

- `0x140011560`
- `0x14002a700`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002a774`
- `ntoskrnl!ZwOpenKey` at `0x14002a774`
- `ntoskrnl!ZwClose` at `0x14002a811`
- `ntoskrnl!ZwClose` at `0x14002a811`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a7e5`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a7e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a7b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a7b6`
- `ntoskrnl!_i64tow_s` at `0x14002a797`
- `ntoskrnl!_i64tow_s` at `0x14002a797`

## pseudocode

```c
__int64 __fastcall WimpFSFIsIntegrityMandatory(__int64 Val, _BYTE *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-9h] BYREF
  int v12; // [rsp+90h] [rbp+7h]
  wchar_t DstBuf[20]; // [rsp+98h] [rbp+Fh] BYREF

  KeyHandle = 0;
  v12 = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_IntegrityFilesKeyName;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  DestinationString = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_6;
  if ( _i64tow_s(Val, DstBuf, 0x11u, 10) )
  {
    v5 = -1073741675;
    goto LABEL_8;
  }
  RtlInitUnicodeString(&DestinationString, DstBuf);
  v4 = ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  v5 = v4;
  if ( v4 < 0 )
  {
LABEL_6:
    if ( v4 == -1073741772 )
    {
      v5 = 0;
      *a2 = 0;
    }
  }
  else
  {
    *a2 = 1;
  }
LABEL_8:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x14002a700  mov     [rsp-8+arg_10], rbx
0x14002a705  push    rbp
0x14002a706  push    rsi
0x14002a707  push    rdi
0x14002a708  lea     rbp, [rsp-47h]
0x14002a70d  sub     rsp, 0D0h
0x14002a714  mov     rax, cs:__security_cookie
0x14002a71b  xor     rax, rsp
0x14002a71e  mov     [rbp+57h+var_20], rax
0x14002a722  xor     eax, eax
0x14002a724  mov     [rbp+57h+KeyHandle], 0
0x14002a72c  xorps   xmm0, xmm0
0x14002a72f  mov     [rbp+57h+var_50], eax
0x14002a732  mov     [rbp+57h+var_B0], eax
0x14002a735  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002a739  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002a73d  mov     rsi, rdx
0x14002a740  lea     rax, g_IntegrityFilesKeyName
0x14002a747  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002a74f  mov     rbx, rcx
0x14002a752  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002a756  mov     edx, 20019h; DesiredAccess
0x14002a75b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002a763  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002a767  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002a76b  movups  [rbp+57h+KeyValueInformation], xmm0
0x14002a76f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a774  call    cs:__imp_ZwOpenKey
0x14002a77b  nop     dword ptr [rax+rax+00h]
0x14002a780  mov     edi, eax
0x14002a782  test    eax, eax
0x14002a784  js      short loc_14002A7FC
0x14002a786  mov     r9d, 0Ah; Radix
0x14002a78c  lea     rdx, [rbp+57h+DstBuf]; DstBuf
0x14002a790  mov     rcx, rbx; Val
0x14002a793  lea     r8d, [r9+7]; SizeInWords
0x14002a797  call    cs:__imp__i64tow_s
0x14002a79e  nop     dword ptr [rax+rax+00h]
0x14002a7a3  test    eax, eax
0x14002a7a5  jz      short loc_14002A7AE
0x14002a7a7  mov     edi, 0C0000095h
0x14002a7ac  jmp     short loc_14002A808
0x14002a7ae  lea     rdx, [rbp+57h+DstBuf]; SourceString
0x14002a7b2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002a7b6  call    cs:__imp_RtlInitUnicodeString
0x14002a7bd  nop     dword ptr [rax+rax+00h]
0x14002a7c2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002a7c6  lea     rax, [rbp+57h+var_B0]
0x14002a7ca  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14002a7cf  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14002a7d3  mov     r8d, 2; KeyValueInformationClass
0x14002a7d9  mov     [rsp+0E0h+Length], 14h; Length
0x14002a7e1  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14002a7e5  call    cs:__imp_ZwQueryValueKey
0x14002a7ec  nop     dword ptr [rax+rax+00h]
0x14002a7f1  mov     edi, eax
0x14002a7f3  test    eax, eax
0x14002a7f5  js      short loc_14002A7FC
0x14002a7f7  mov     byte ptr [rsi], 1
0x14002a7fa  jmp     short loc_14002A808
0x14002a7fc  cmp     eax, 0C0000034h
0x14002a801  jnz     short loc_14002A808
0x14002a803  xor     edi, edi
0x14002a805  mov     [rsi], dil
0x14002a808  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002a80c  test    rcx, rcx
0x14002a80f  jz      short loc_14002A81D
0x14002a811  call    cs:__imp_ZwClose
0x14002a818  nop     dword ptr [rax+rax+00h]
0x14002a81d  mov     eax, edi
0x14002a81f  mov     rcx, [rbp+57h+var_20]
0x14002a823  xor     rcx, rsp; StackCookie
0x14002a826  call    __security_check_cookie
0x14002a82b  mov     rbx, [rsp+0E0h+arg_10]
0x14002a833  add     rsp, 0D0h
0x14002a83a  pop     rdi
0x14002a83b  pop     rsi
0x14002a83c  pop     rbp
0x14002a83d  retn
```
