# AslRegistryOpenSubKey

- ea: `0x140010c9c`
- end: `0x140010d3c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000a9ec`

## callees

- `0x14001008c`
- `0x140010c9c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140010ccd`
- `ntdll!RtlInitUnicodeStringEx` at `0x140010ccd`
- `ntdll!ZwOpenKey` at `0x140010d2d`
- `ntdll!ZwOpenKey` at `0x140010d2d`

## string_xrefs

- `0x140010cd9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x140010cea`: `AslRegistryOpenSubKey`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  v6 = inited;
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]", inited);
    return v6;
  }
}

```

## disassembly

```asm
0x140010c9c  push    rbp
0x140010c9e  push    rbx
0x140010c9f  push    rsi
0x140010ca0  push    rdi
0x140010ca1  mov     rbp, rsp
0x140010ca4  sub     rsp, 78h
0x140010ca8  xorps   xmm0, xmm0
0x140010cab  xor     eax, eax
0x140010cad  mov     [rcx], rax
0x140010cb0  mov     rsi, rdx
0x140010cb3  mov     rdi, rcx
0x140010cb6  mov     rdx, r8; SourceString
0x140010cb9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140010cbd  lea     rcx, [rbp+DestinationString]; DestinationString
0x140010cc1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140010cc5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140010cc9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140010ccd  call    cs:__imp_RtlInitUnicodeStringEx
0x140010cd3  mov     ebx, eax
0x140010cd5  test    eax, eax
0x140010cd7  jns     short loc_140010CFF
0x140010cd9  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x140010ce0  mov     [rsp+78h+var_58], eax
0x140010ce4  mov     r8d, 3BEh
0x140010cea  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x140010cf1  mov     ecx, 1
0x140010cf6  call    AslLogCallPrintf
0x140010cfb  mov     eax, ebx
0x140010cfd  jmp     short loc_140010D33
0x140010cff  lea     rax, [rbp+DestinationString]
0x140010d03  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140010d0a  xorps   xmm0, xmm0
0x140010d0d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140010d11  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140010d15  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x140010d19  mov     edx, 20019h; DesiredAccess
0x140010d1e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140010d25  mov     rcx, rdi; KeyHandle
0x140010d28  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140010d2d  call    cs:__imp_ZwOpenKey
0x140010d33  add     rsp, 78h
0x140010d37  pop     rdi
0x140010d38  pop     rsi
0x140010d39  pop     rbx
0x140010d3a  pop     rbp
0x140010d3b  retn
```
