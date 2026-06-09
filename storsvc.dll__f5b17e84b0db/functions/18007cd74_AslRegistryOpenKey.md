# AslRegistryOpenKey

- ea: `0x18007cd74`
- end: `0x18007ce06`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180079f08`
- `0x18007a8e8`

## callees

- `0x18007cd74`
- `0x18007d3a0`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18007cdf3`
- `ntdll!ZwOpenKey` at `0x18007cdf3`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007cd91`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007cd91`

## string_xrefs

- `0x18007cdb0`: `AslRegistryOpenKey`
- `0x18007cd9f`: `AslRegistryOpenKey passed bad Path [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  v6 = inited;
  if ( inited >= 0 )
  {
    *KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  }
  return v6;
}

```

## disassembly

```asm
0x18007cd74  push    rbp
0x18007cd76  push    rbx
0x18007cd77  push    rsi
0x18007cd78  push    rdi
0x18007cd79  mov     rbp, rsp
0x18007cd7c  sub     rsp, 78h
0x18007cd80  mov     rdi, rcx
0x18007cd83  xorps   xmm0, xmm0
0x18007cd86  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007cd8a  mov     esi, r8d
0x18007cd8d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007cd91  call    cs:__imp_RtlInitUnicodeStringEx
0x18007cd97  xor     ecx, ecx
0x18007cd99  mov     ebx, eax
0x18007cd9b  test    eax, eax
0x18007cd9d  jns     short loc_18007CDC3
0x18007cd9f  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18007cda6  mov     [rsp+78h+var_58], eax
0x18007cdaa  mov     r8d, 388h
0x18007cdb0  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18007cdb7  mov     ecx, 1
0x18007cdbc  call    AslLogCallPrintf
0x18007cdc1  jmp     short loc_18007CDFB
0x18007cdc3  mov     [rdi], rcx
0x18007cdc6  lea     rax, [rbp+DestinationString]
0x18007cdca  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18007cdce  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007cdd2  xorps   xmm0, xmm0
0x18007cdd5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007cdd9  mov     rcx, rdi; KeyHandle
0x18007cddc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007cde4  mov     edx, esi; DesiredAccess
0x18007cde6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007cdee  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007cdf3  call    cs:__imp_ZwOpenKey
0x18007cdf9  mov     ebx, eax
0x18007cdfb  mov     eax, ebx
0x18007cdfd  add     rsp, 78h
0x18007ce01  pop     rdi
0x18007ce02  pop     rsi
0x18007ce03  pop     rbx
0x18007ce04  pop     rbp
0x18007ce05  retn
```
