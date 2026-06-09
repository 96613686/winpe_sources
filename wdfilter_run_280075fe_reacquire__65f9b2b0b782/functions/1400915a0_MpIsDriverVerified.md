# MpIsDriverVerified

- ea: `0x1400915a0`
- end: `0x14009176c`
- name: `MpIsDriverVerified`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400118d0`
- `0x1400915a0`

## import_xrefs

- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x1400915fb`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x1400915fb`
- `ntoskrnl!ZwOpenKey` at `0x14009167f`
- `ntoskrnl!ZwOpenKey` at `0x14009167f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400916f3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400916f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091635`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400916c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091635`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400916c1`
- `ntoskrnl!ZwClose` at `0x140091737`
- `ntoskrnl!ZwClose` at `0x140094c9c`
- `ntoskrnl!ZwClose` at `0x140091737`
- `ntoskrnl!ZwClose` at `0x140094c9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091721`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094c86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091721`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094c86`

## string_xrefs

- `0x140091626`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management`

## pseudocode

```c
char __fastcall MpIsDriverVerified(_DWORD *a1)
{
  _DWORD *PoolWithTag; // rbx
  char v3; // di
  void *KeyHandle; // [rsp+40h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-60h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-28h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  KeyHandle = 0;
  PoolWithTag = 0;
  ResultLength = 0;
  *a1 = 0;
  if ( (unsigned __int8)MmIsDriverVerifyingByAddress(MpIsDriverVerified) )
  {
    v3 = 1;
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      PoolWithTag = (_DWORD *)MpAllocatePoolWithTag(1, 274, 1450332237);
      if ( PoolWithTag )
      {
        RtlInitUnicodeString(&DestinationString, L"VerifyDriverLevel");
        if ( ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               PoolWithTag,
               0x112u,
               &ResultLength) >= 0
          && PoolWithTag[1] == 4
          && PoolWithTag[2] == 4 )
        {
          *a1 = PoolWithTag[3];
        }
      }
    }
  }
  else
  {
    v3 = 0;
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x5672504Du);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x1400915a0  mov     r11, rsp
0x1400915a3  mov     [r11+10h], rbx
0x1400915a7  mov     [r11+18h], rsi
0x1400915ab  push    rdi
0x1400915ac  sub     rsp, 0A0h
0x1400915b3  mov     rax, cs:__security_cookie
0x1400915ba  xor     rax, rsp
0x1400915bd  mov     [rsp+0A8h+var_18], rax
0x1400915c5  mov     rsi, rcx
0x1400915c8  xor     eax, eax
0x1400915ca  xorps   xmm0, xmm0
0x1400915cd  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1400915d2  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1400915d7  mov     [r11-40h], rax
0x1400915db  mov     dword ptr [rsp+0A8h+ObjectAttributes.SecurityQualityOfService], eax
0x1400915df  movups  xmmword ptr [r11-28h], xmm0
0x1400915e4  mov     [r11-68h], rax
0x1400915e8  xor     ebx, ebx
0x1400915ea  mov     [r11-70h], rbx
0x1400915ee  mov     [rsp+0A8h+var_30], eax
0x1400915f2  mov     [rcx], eax
0x1400915f4  lea     rcx, MpIsDriverVerified; AddressWithinSection
0x1400915fb  call    cs:__imp_MmIsDriverVerifyingByAddress
0x140091602  nop     dword ptr [rax+rax+00h]
0x140091607  mov     [rsp+0A8h+var_78], al
0x14009160b  test    al, al
0x14009160d  jnz     short loc_14009161C
0x14009160f  xor     dil, dil
0x140091612  mov     [rsp+0A8h+var_78], dil
0x140091617  jmp     loc_140091714
0x14009161c  mov     edi, 1
0x140091621  mov     [rsp+0A8h+var_78], dil
0x140091626  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14009162d  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140091635  call    cs:__imp_RtlInitUnicodeString
0x14009163c  nop     dword ptr [rax+rax+00h]
0x140091641  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x140091649  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], 0
0x140091652  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x14009165a  lea     rax, [rsp+0A8h+DestinationString]
0x140091662  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x140091667  xorps   xmm0, xmm0
0x14009166a  movdqu  xmmword ptr [rsp+68h], xmm0
0x140091670  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x140091675  mov     edx, 20019h; DesiredAccess
0x14009167a  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x14009167f  call    cs:__imp_ZwOpenKey
0x140091686  nop     dword ptr [rax+rax+00h]
0x14009168b  test    eax, eax
0x14009168d  js      loc_140091714
0x140091693  mov     edx, 112h
0x140091698  mov     r8d, 5672504Dh
0x14009169e  mov     ecx, edi
0x1400916a0  call    MpAllocatePoolWithTag
0x1400916a5  mov     rbx, rax
0x1400916a8  mov     [rsp+0A8h+var_70], rax
0x1400916ad  test    rax, rax
0x1400916b0  jz      short loc_140091714
0x1400916b2  lea     rdx, aVerifydriverle; "VerifyDriverLevel"
0x1400916b9  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1400916c1  call    cs:__imp_RtlInitUnicodeString
0x1400916c8  nop     dword ptr [rax+rax+00h]
0x1400916cd  lea     rax, [rsp+0A8h+var_30]
0x1400916d2  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1400916d7  mov     [rsp+0A8h+Length], 112h; Length
0x1400916df  mov     r9, rbx; KeyValueInformation
0x1400916e2  lea     r8d, [rdi+1]; KeyValueInformationClass
0x1400916e6  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x1400916ee  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400916f3  call    cs:__imp_ZwQueryValueKey
0x1400916fa  nop     dword ptr [rax+rax+00h]
0x1400916ff  test    eax, eax
0x140091701  js      short loc_140091714
0x140091703  cmp     dword ptr [rbx+4], 4
0x140091707  jnz     short loc_140091714
0x140091709  cmp     dword ptr [rbx+8], 4
0x14009170d  jnz     short loc_140091714
0x14009170f  mov     eax, [rbx+0Ch]
0x140091712  mov     [rsi], eax
0x140091714  test    rbx, rbx
0x140091717  jz      short loc_14009172D
0x140091719  mov     edx, 5672504Dh; Tag
0x14009171e  mov     rcx, rbx; P
0x140091721  call    cs:__imp_ExFreePoolWithTag
0x140091728  nop     dword ptr [rax+rax+00h]
0x14009172d  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x140091732  test    rcx, rcx
0x140091735  jz      short loc_140091743
0x140091737  call    cs:__imp_ZwClose
0x14009173e  nop     dword ptr [rax+rax+00h]
0x140091743  mov     al, dil
0x140091746  mov     rcx, [rsp+0A8h+var_18]
0x14009174e  xor     rcx, rsp; StackCookie
0x140091751  call    __security_check_cookie
0x140091756  lea     r11, [rsp+0A8h+var_8]
0x14009175e  mov     rbx, [r11+18h]
0x140091762  mov     rsi, [r11+20h]
0x140091766  mov     rsp, r11
0x140091769  pop     rdi
0x14009176a  retn
0x140094c6f  push    rbp
0x140094c71  sub     rsp, 30h
0x140094c75  mov     rbp, rdx
0x140094c78  mov     rcx, [rbp+38h]; P
0x140094c7c  test    rcx, rcx
0x140094c7f  jz      short loc_140094C93
0x140094c81  mov     edx, 5672504Dh; Tag
0x140094c86  call    cs:__imp_ExFreePoolWithTag
0x140094c8d  nop     dword ptr [rax+rax+00h]
0x140094c92  nop
0x140094c93  mov     rcx, [rbp+40h]; Handle
0x140094c97  test    rcx, rcx
0x140094c9a  jz      short loc_140094CA9
0x140094c9c  call    cs:__imp_ZwClose
0x140094ca3  nop     dword ptr [rax+rax+00h]
0x140094ca8  nop
0x140094ca9  add     rsp, 30h
0x140094cad  pop     rbp
0x140094cae  retn
```
