# RfsRegQueryValue

- ea: `0x14004a978`
- end: `0x14004ab35`
- name: `RfsRegQueryValue`
- size: `445`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a460`
- `0x14004a868`

## callees

- `0x14002a540`
- `0x14004a978`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004aa6e`
- `ntoskrnl!ExAllocatePool2` at `0x14004aa6e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a9be`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a9d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a9be`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a9d1`
- `ntoskrnl!ZwQueryValueKey` at `0x14004aa47`
- `ntoskrnl!ZwQueryValueKey` at `0x14004aaad`
- `ntoskrnl!ZwQueryValueKey` at `0x14004aa47`
- `ntoskrnl!ZwQueryValueKey` at `0x14004aaad`
- `ntoskrnl!ZwOpenKey` at `0x14004aa12`
- `ntoskrnl!ZwOpenKey` at `0x14004aa12`
- `ntoskrnl!ZwClose` at `0x14004ab18`
- `ntoskrnl!ZwClose` at `0x14004ab18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ab03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ab03`

## pseudocode

```c
__int64 __fastcall RfsRegQueryValue(PCWSTR SourceString, PCWSTR a2, int a3, void *a4, ULONG *a5)
{
  NTSTATUS v8; // ebx
  _DWORD *Pool2; // rdi
  ULONG v10; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-31h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  ValueName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
    if ( v8 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(258, ResultLength, 1383294546);
      if ( Pool2 )
      {
        v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
        if ( v8 >= 0 )
        {
          if ( Pool2[1] == a3 )
          {
            v10 = Pool2[3];
            ResultLength = v10;
            if ( v10 <= *a5 )
            {
              memmove(a4, (char *)Pool2 + (unsigned int)Pool2[2], (unsigned int)Pool2[3]);
              *a5 = Pool2[3];
              v8 = 0;
            }
            else
            {
              *a5 = v10;
              v8 = -1073741789;
            }
          }
          else
          {
            v8 = -1073741788;
          }
        }
        ExFreePoolWithTag(Pool2, 0x52736652u);
      }
      else
      {
        v8 = -1073741670;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004a978  push    rbp
0x14004a97a  push    rbx
0x14004a97b  push    rsi
0x14004a97c  push    rdi
0x14004a97d  push    r14
0x14004a97f  lea     rbp, [rsp-2Fh]
0x14004a984  sub     rsp, 90h
0x14004a98b  xorps   xmm0, xmm0
0x14004a98e  xor     eax, eax
0x14004a990  mov     rbx, rdx
0x14004a993  mov     [rbp+4Fh+KeyHandle], rax
0x14004a997  mov     rdx, rcx; SourceString
0x14004a99a  mov     [rbp+4Fh+var_80], eax
0x14004a99d  xorps   xmm1, xmm1
0x14004a9a0  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14004a9a4  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14004a9a8  mov     r14, r9
0x14004a9ab  mov     esi, r8d
0x14004a9ae  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14004a9b2  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x14004a9b6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x14004a9ba  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14004a9be  call    cs:__imp_RtlInitUnicodeString
0x14004a9c5  nop     dword ptr [rax+rax+00h]
0x14004a9ca  mov     rdx, rbx; SourceString
0x14004a9cd  lea     rcx, [rbp+4Fh+ValueName]; DestinationString
0x14004a9d1  call    cs:__imp_RtlInitUnicodeString
0x14004a9d8  nop     dword ptr [rax+rax+00h]
0x14004a9dd  lea     rax, [rbp+4Fh+DestinationString]
0x14004a9e1  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14004a9e8  xorps   xmm0, xmm0
0x14004a9eb  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14004a9ef  mov     edi, 1
0x14004a9f4  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x14004a9fc  mov     edx, edi; DesiredAccess
0x14004a9fe  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14004aa05  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14004aa09  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004aa0d  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14004aa12  call    cs:__imp_ZwOpenKey
0x14004aa19  nop     dword ptr [rax+rax+00h]
0x14004aa1e  mov     ebx, eax
0x14004aa20  test    eax, eax
0x14004aa22  js      loc_14004AB0F
0x14004aa28  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004aa2c  lea     rax, [rbp+4Fh+var_80]
0x14004aa30  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14004aa35  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14004aa39  xor     r9d, r9d; KeyValueInformation
0x14004aa3c  mov     [rsp+0B0h+Length], 0; Length
0x14004aa44  mov     r8d, edi; KeyValueInformationClass
0x14004aa47  call    cs:__imp_ZwQueryValueKey
0x14004aa4e  nop     dword ptr [rax+rax+00h]
0x14004aa53  mov     ebx, eax
0x14004aa55  cmp     eax, 0C0000023h
0x14004aa5a  jnz     loc_14004AB0F
0x14004aa60  mov     edx, [rbp+4Fh+var_80]
0x14004aa63  mov     ecx, 102h
0x14004aa68  mov     r8d, 52736652h
0x14004aa6e  call    cs:__imp_ExAllocatePool2
0x14004aa75  nop     dword ptr [rax+rax+00h]
0x14004aa7a  mov     rdi, rax
0x14004aa7d  test    rax, rax
0x14004aa80  jnz     short loc_14004AA8C
0x14004aa82  mov     ebx, 0C000009Ah
0x14004aa87  jmp     loc_14004AB0F
0x14004aa8c  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004aa90  lea     rax, [rbp+4Fh+var_80]
0x14004aa94  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14004aa99  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14004aa9d  mov     eax, [rbp+4Fh+var_80]
0x14004aaa0  mov     r9, rdi; KeyValueInformation
0x14004aaa3  mov     r8d, 1; KeyValueInformationClass
0x14004aaa9  mov     [rsp+0B0h+Length], eax; Length
0x14004aaad  call    cs:__imp_ZwQueryValueKey
0x14004aab4  nop     dword ptr [rax+rax+00h]
0x14004aab9  mov     ebx, eax
0x14004aabb  test    eax, eax
0x14004aabd  js      short loc_14004AAFB
0x14004aabf  cmp     [rdi+4], esi
0x14004aac2  jz      short loc_14004AACB
0x14004aac4  mov     ebx, 0C0000024h
0x14004aac9  jmp     short loc_14004AAFB
0x14004aacb  mov     eax, [rdi+0Ch]
0x14004aace  mov     rbx, [rbp+4Fh+arg_20]
0x14004aad2  mov     [rbp+4Fh+var_80], eax
0x14004aad5  cmp     eax, [rbx]
0x14004aad7  jbe     short loc_14004AAE2
0x14004aad9  mov     [rbx], eax
0x14004aadb  mov     ebx, 0C0000023h
0x14004aae0  jmp     short loc_14004AAFB
0x14004aae2  mov     edx, [rdi+8]
0x14004aae5  mov     rcx, r14; void *
0x14004aae8  mov     r8d, [rdi+0Ch]; Size
0x14004aaec  add     rdx, rdi; Src
0x14004aaef  call    memmove
0x14004aaf4  mov     eax, [rdi+0Ch]
0x14004aaf7  mov     [rbx], eax
0x14004aaf9  xor     ebx, ebx
0x14004aafb  mov     edx, 52736652h; Tag
0x14004ab00  mov     rcx, rdi; P
0x14004ab03  call    cs:__imp_ExFreePoolWithTag
0x14004ab0a  nop     dword ptr [rax+rax+00h]
0x14004ab0f  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14004ab13  test    rcx, rcx
0x14004ab16  jz      short loc_14004AB24
0x14004ab18  call    cs:__imp_ZwClose
0x14004ab1f  nop     dword ptr [rax+rax+00h]
0x14004ab24  mov     eax, ebx
0x14004ab26  add     rsp, 90h
0x14004ab2d  pop     r14
0x14004ab2f  pop     rdi
0x14004ab30  pop     rsi
0x14004ab31  pop     rbx
0x14004ab32  pop     rbp
0x14004ab33  retn
```
