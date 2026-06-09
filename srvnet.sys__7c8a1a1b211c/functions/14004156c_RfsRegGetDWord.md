# RfsRegGetDWord

- ea: `0x14004156c`
- end: `0x1400416a5`
- name: `RfsRegGetDWord`
- size: `313`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14004dc10`
- `0x140056534`
- `0x140056ad0`

## callees

- `0x14002a3e0`
- `0x14004156c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400415c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400415d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400415c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400415d4`
- `ntoskrnl!ZwQueryValueKey` at `0x140041646`
- `ntoskrnl!ZwQueryValueKey` at `0x140041646`
- `ntoskrnl!ZwOpenKey` at `0x140041613`
- `ntoskrnl!ZwOpenKey` at `0x140041613`
- `ntoskrnl!ZwClose` at `0x140041658`
- `ntoskrnl!ZwClose` at `0x140041658`

## pseudocode

```c
NTSTATUS __fastcall RfsRegGetDWord(PCWSTR SourceString, PCWSTR a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+17h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+27h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  *a3 = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ValueName = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    ZwClose(KeyHandle);
    if ( v6 >= 0 )
    {
      if ( DWORD1(KeyValueInformation) == 4 )
      {
        if ( DWORD2(KeyValueInformation) >= 4 )
        {
          *a3 = HIDWORD(KeyValueInformation);
          return 0;
        }
        else
        {
          return -1073741789;
        }
      }
      else
      {
        return -1073741788;
      }
    }
    else
    {
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004156c  push    rbp
0x14004156e  push    rbx
0x14004156f  push    rdi
0x140041570  lea     rbp, [rsp-47h]
0x140041575  sub     rsp, 0B0h
0x14004157c  mov     rax, cs:__security_cookie
0x140041583  xor     rax, rsp
0x140041586  mov     [rbp+57h+var_20], rax
0x14004158a  xorps   xmm0, xmm0
0x14004158d  xor     eax, eax
0x14004158f  mov     rbx, rdx
0x140041592  mov     [rbp+57h+KeyHandle], rax
0x140041596  mov     rdx, rcx; SourceString
0x140041599  mov     [rbp+57h+var_90], eax
0x14004159c  xorps   xmm1, xmm1
0x14004159f  mov     [r8], eax
0x1400415a2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400415a6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400415aa  mov     rdi, r8
0x1400415ad  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400415b1  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1400415b5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1400415b9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400415bd  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400415c1  call    cs:__imp_RtlInitUnicodeString
0x1400415c8  nop     dword ptr [rax+rax+00h]
0x1400415cd  mov     rdx, rbx; SourceString
0x1400415d0  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400415d4  call    cs:__imp_RtlInitUnicodeString
0x1400415db  nop     dword ptr [rax+rax+00h]
0x1400415e0  lea     rax, [rbp+57h+DestinationString]
0x1400415e4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400415eb  xorps   xmm0, xmm0
0x1400415ee  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400415f2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400415f6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400415fe  mov     edx, 1; DesiredAccess
0x140041603  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004160a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004160e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140041613  call    cs:__imp_ZwOpenKey
0x14004161a  nop     dword ptr [rax+rax+00h]
0x14004161f  test    eax, eax
0x140041621  js      short loc_14004168D
0x140041623  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140041627  lea     rax, [rbp+57h+var_90]
0x14004162b  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140041630  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140041634  mov     r8d, 2; KeyValueInformationClass
0x14004163a  mov     [rsp+0C0h+Length], 10h; Length
0x140041642  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140041646  call    cs:__imp_ZwQueryValueKey
0x14004164d  nop     dword ptr [rax+rax+00h]
0x140041652  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140041656  mov     ebx, eax
0x140041658  call    cs:__imp_ZwClose
0x14004165f  nop     dword ptr [rax+rax+00h]
0x140041664  test    ebx, ebx
0x140041666  jns     short loc_14004166C
0x140041668  mov     eax, ebx
0x14004166a  jmp     short loc_14004168D
0x14004166c  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140041670  jz      short loc_140041679
0x140041672  mov     eax, 0C0000024h
0x140041677  jmp     short loc_14004168D
0x140041679  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14004167d  jnb     short loc_140041686
0x14004167f  mov     eax, 0C0000023h
0x140041684  jmp     short loc_14004168D
0x140041686  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140041689  mov     [rdi], eax
0x14004168b  xor     eax, eax
0x14004168d  mov     rcx, [rbp+57h+var_20]
0x140041691  xor     rcx, rsp; StackCookie
0x140041694  call    __security_check_cookie
0x140041699  add     rsp, 0B0h
0x1400416a0  pop     rdi
0x1400416a1  pop     rbx
0x1400416a2  pop     rbp
0x1400416a3  retn
```
