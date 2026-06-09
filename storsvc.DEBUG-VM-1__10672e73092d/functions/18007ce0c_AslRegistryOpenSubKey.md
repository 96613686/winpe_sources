# AslRegistryOpenSubKey

- ea: `0x18007ce0c`
- end: `0x18007ceac`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180079f08`

## callees

- `0x18007ce0c`
- `0x18007d3a0`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18007ce9d`
- `ntdll!ZwOpenKey` at `0x18007ce9d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007ce3d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18007ce3d`

## string_xrefs

- `0x18007ce5a`: `AslRegistryOpenSubKey`
- `0x18007ce49`: `AslRegistryOpenSubKey passed bad Path [%x]`

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
0x18007ce0c  push    rbp
0x18007ce0e  push    rbx
0x18007ce0f  push    rsi
0x18007ce10  push    rdi
0x18007ce11  mov     rbp, rsp
0x18007ce14  sub     rsp, 78h
0x18007ce18  xorps   xmm0, xmm0
0x18007ce1b  xor     eax, eax
0x18007ce1d  mov     [rcx], rax
0x18007ce20  mov     rsi, rdx
0x18007ce23  mov     rdi, rcx
0x18007ce26  mov     rdx, r8; SourceString
0x18007ce29  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007ce2d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007ce31  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007ce35  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007ce39  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18007ce3d  call    cs:__imp_RtlInitUnicodeStringEx
0x18007ce43  mov     ebx, eax
0x18007ce45  test    eax, eax
0x18007ce47  jns     short loc_18007CE6F
0x18007ce49  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18007ce50  mov     [rsp+78h+var_58], eax
0x18007ce54  mov     r8d, 3BEh
0x18007ce5a  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18007ce61  mov     ecx, 1
0x18007ce66  call    AslLogCallPrintf
0x18007ce6b  mov     eax, ebx
0x18007ce6d  jmp     short loc_18007CEA3
0x18007ce6f  lea     rax, [rbp+DestinationString]
0x18007ce73  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007ce7a  xorps   xmm0, xmm0
0x18007ce7d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007ce81  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007ce85  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18007ce89  mov     edx, 20019h; DesiredAccess
0x18007ce8e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007ce95  mov     rcx, rdi; KeyHandle
0x18007ce98  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007ce9d  call    cs:__imp_ZwOpenKey
0x18007cea3  add     rsp, 78h
0x18007cea7  pop     rdi
0x18007cea8  pop     rsi
0x18007cea9  pop     rbx
0x18007ceaa  pop     rbp
0x18007ceab  retn
```
