# ReadRegistryValue

- ea: `0x14000b908`
- end: `0x14000bb03`
- name: `ReadRegistryValue`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000b854`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x1400015c0`
- `0x14000164c`
- `0x14000b908`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000b9fd`
- `ntoskrnl!ZwQueryValueKey` at `0x14000ba6a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b9fd`
- `ntoskrnl!ZwQueryValueKey` at `0x14000ba6a`
- `ntoskrnl!ZwOpenKey` at `0x14000b9bf`
- `ntoskrnl!ZwOpenKey` at `0x14000b9bf`
- `ntoskrnl!ZwClose` at `0x14000baac`
- `ntoskrnl!ZwClose` at `0x14000bcd6`
- `ntoskrnl!ZwClose` at `0x14000baac`
- `ntoskrnl!ZwClose` at `0x14000bcd6`

## string_xrefs

- `0x14000b957`: `UevFilter.ReadRegistryValue: Entry\n`
- `0x14000ba8d`: `UevFilter.ReadRegistryValue: Invalid parameter specified\n`
- `0x14000badb`: `UevFilter.ReadRegistryValue: Exit, status = 0x%X\n`

## pseudocode

```c
__int64 __fastcall ReadRegistryValue(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3, PVOID *a4)
{
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  __int64 v9; // rcx
  _DWORD *v10; // rdi
  void *KeyHandle; // [rsp+38h] [rbp-60h] BYREF
  PVOID KeyValueInformation; // [rsp+40h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-50h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+18h] BYREF
  PVOID *v16; // [rsp+B8h] [rbp+20h]

  v16 = a4;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  ResultLength = 0;
  DbgTrace(2, "UevFilter.ReadRegistryValue: Entry\n");
  if ( a1 && a2 && a4 )
  {
    *a4 = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v7 >= 0 )
    {
      v8 = ZwQueryValueKey(KeyHandle, a2, KeyValueFullInformation, 0, 0, &ResultLength);
      v7 = v8;
      if ( v8 == -1073741789 || v8 == -2147483643 )
      {
        v7 = AllocateGenericBuffer(v9, ResultLength, &KeyValueInformation);
        if ( v7 >= 0 )
        {
          v10 = KeyValueInformation;
          v7 = ZwQueryValueKey(KeyHandle, a2, KeyValueFullInformation, KeyValueInformation, ResultLength, &ResultLength);
          if ( v7 >= 0 && v10[1] != 4 )
            v7 = -1073741823;
        }
      }
    }
  }
  else
  {
    DbgTraceErr("UevFilter.ReadRegistryValue: Invalid parameter specified\n");
    v7 = -1073741811;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( KeyValueInformation )
  {
    if ( v7 >= 0 )
      *a4 = KeyValueInformation;
    else
      FreeGenericBuffer(KeyValueInformation);
  }
  DbgTraceFrmt(2, "UevFilter.ReadRegistryValue: Exit, status = 0x%X\n", v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000b908  mov     r11, rsp
0x14000b90b  mov     [r11+8], rbx
0x14000b90f  mov     [r11+20h], r9
0x14000b913  mov     [r11+18h], r8d
0x14000b917  push    rsi
0x14000b918  push    rdi
0x14000b919  push    r14
0x14000b91b  sub     rsp, 80h
0x14000b922  mov     rsi, r9
0x14000b925  mov     r14, rdx
0x14000b928  mov     rbx, rcx
0x14000b92b  mov     [rsp+98h+var_68], 0C0000001h
0x14000b933  mov     qword ptr [r11-60h], 0
0x14000b93b  xor     eax, eax
0x14000b93d  xorps   xmm0, xmm0
0x14000b940  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x14000b945  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x14000b94a  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x14000b94f  mov     [r11-58h], rax
0x14000b953  mov     [r11+18h], eax
0x14000b957  lea     rdx, aUevfilterReadr; "UevFilter.ReadRegistryValue: Entry\n"
0x14000b95e  lea     ecx, [rax+2]
0x14000b961  call    DbgTrace
0x14000b966  nop
0x14000b967  test    rbx, rbx
0x14000b96a  jz      loc_14000BA8D
0x14000b970  test    r14, r14
0x14000b973  jz      loc_14000BA8D
0x14000b979  test    rsi, rsi
0x14000b97c  jz      loc_14000BA8D
0x14000b982  mov     qword ptr [rsi], 0
0x14000b989  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x14000b991  mov     [rsp+98h+ObjectAttributes.RootDirectory], 0
0x14000b99a  mov     [rsp+98h+ObjectAttributes.Attributes], 240h
0x14000b9a2  mov     [rsp+98h+ObjectAttributes.ObjectName], rbx
0x14000b9a7  xorps   xmm0, xmm0
0x14000b9aa  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b9b0  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x14000b9b5  mov     edx, 20019h; DesiredAccess
0x14000b9ba  lea     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x14000b9bf  call    cs:__imp_ZwOpenKey
0x14000b9c6  nop     dword ptr [rax+rax+00h]
0x14000b9cb  mov     ebx, eax
0x14000b9cd  mov     [rsp+98h+var_68], eax
0x14000b9d1  test    eax, eax
0x14000b9d3  js      loc_14000BAA2
0x14000b9d9  lea     rax, [rsp+98h+arg_10]
0x14000b9e1  mov     [rsp+98h+ResultLength], rax; ResultLength
0x14000b9e6  mov     [rsp+98h+Length], 0; Length
0x14000b9ee  xor     r9d, r9d; KeyValueInformation
0x14000b9f1  lea     r8d, [r9+1]; KeyValueInformationClass
0x14000b9f5  mov     rdx, r14; ValueName
0x14000b9f8  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x14000b9fd  call    cs:__imp_ZwQueryValueKey
0x14000ba04  nop     dword ptr [rax+rax+00h]
0x14000ba09  mov     ebx, eax
0x14000ba0b  mov     [rsp+98h+var_68], eax
0x14000ba0f  cmp     eax, 0C0000023h
0x14000ba14  jz      short loc_14000BA21
0x14000ba16  cmp     eax, 80000005h
0x14000ba1b  jnz     loc_14000BAA2
0x14000ba21  mov     edx, [rsp+98h+arg_10]
0x14000ba28  lea     r8, [rsp+98h+KeyValueInformation]
0x14000ba2d  call    AllocateGenericBuffer
0x14000ba32  mov     ebx, eax
0x14000ba34  mov     [rsp+98h+var_68], eax
0x14000ba38  test    eax, eax
0x14000ba3a  js      short loc_14000BAA2
0x14000ba3c  mov     eax, [rsp+98h+arg_10]
0x14000ba43  lea     rcx, [rsp+98h+arg_10]
0x14000ba4b  mov     [rsp+98h+ResultLength], rcx; ResultLength
0x14000ba50  mov     [rsp+98h+Length], eax; Length
0x14000ba54  mov     rdi, [rsp+98h+KeyValueInformation]
0x14000ba59  mov     r9, rdi; KeyValueInformation
0x14000ba5c  mov     r8d, 1; KeyValueInformationClass
0x14000ba62  mov     rdx, r14; ValueName
0x14000ba65  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x14000ba6a  call    cs:__imp_ZwQueryValueKey
0x14000ba71  nop     dword ptr [rax+rax+00h]
0x14000ba76  mov     ebx, eax
0x14000ba78  mov     [rsp+98h+var_68], eax
0x14000ba7c  test    eax, eax
0x14000ba7e  js      short loc_14000BAA2
0x14000ba80  cmp     dword ptr [rdi+4], 4
0x14000ba84  jz      short loc_14000BAA2
0x14000ba86  mov     ebx, 0C0000001h
0x14000ba8b  jmp     short loc_14000BA9E
0x14000ba8d  lea     rcx, aUevfilterReadr_1; "UevFilter.ReadRegistryValue: Invalid pa"...
0x14000ba94  call    DbgTraceErr
0x14000ba99  mov     ebx, 0C000000Dh
0x14000ba9e  mov     [rsp+98h+var_68], ebx
0x14000baa2  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x14000baa7  test    rcx, rcx
0x14000baaa  jz      short loc_14000BAB8
0x14000baac  call    cs:__imp_ZwClose
0x14000bab3  nop     dword ptr [rax+rax+00h]
0x14000bab8  mov     rdi, [rsp+98h+KeyValueInformation]
0x14000babd  test    rdi, rdi
0x14000bac0  jz      short loc_14000BAD8
0x14000bac2  test    ebx, ebx
0x14000bac4  jns     short loc_14000BAD0
0x14000bac6  mov     rcx, rdi; P
0x14000bac9  call    FreeGenericBuffer
0x14000bace  jmp     short loc_14000BAD8
0x14000bad0  mov     rax, [rsp+98h+KeyValueInformation]
0x14000bad5  mov     [rsi], rax
0x14000bad8  mov     r8d, ebx
0x14000badb  lea     rdx, aUevfilterReadr_4; "UevFilter.ReadRegistryValue: Exit, stat"...
0x14000bae2  mov     ecx, 2
0x14000bae7  call    DbgTraceFrmt
0x14000baec  mov     eax, ebx
0x14000baee  mov     rbx, [rsp+98h+arg_0]
0x14000baf6  add     rsp, 80h
0x14000bafd  pop     r14
0x14000baff  pop     rdi
0x14000bb00  pop     rsi
0x14000bb01  retn
0x14000bcc4  push    rbp
0x14000bcc6  sub     rsp, 30h
0x14000bcca  mov     rbp, rdx
0x14000bccd  mov     rcx, [rbp+38h]; Handle
0x14000bcd1  test    rcx, rcx
0x14000bcd4  jz      short loc_14000BCE3
0x14000bcd6  call    cs:__imp_ZwClose
0x14000bcdd  nop     dword ptr [rax+rax+00h]
0x14000bce2  nop
0x14000bce3  mov     rcx, [rbp+40h]; P
0x14000bce7  test    rcx, rcx
0x14000bcea  jz      short loc_14000BD03
0x14000bcec  cmp     dword ptr [rbp+30h], 0
0x14000bcf0  jge     short loc_14000BCF9
0x14000bcf2  call    FreeGenericBuffer
0x14000bcf7  jmp     short loc_14000BD03
0x14000bcf9  mov     rax, [rbp+0B8h]
0x14000bd00  mov     [rax], rcx
0x14000bd03  add     rsp, 30h
0x14000bd07  pop     rbp
0x14000bd08  retn
```
