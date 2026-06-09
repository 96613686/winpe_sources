# WerpGetRegistryKey

- ea: `0x14000f3e0`
- end: `0x14000f4b1`
- name: `WerpGetRegistryKey`
- size: `209`
- prototype: `__int64 __fastcall(void *, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `8`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d68c`
- `0x14000f6d8`
- `0x14000f8bc`
- `0x14000fba0`
- `0x14000fda8`
- `0x1400100f4`
- `0x1400122c0`
- `0x140012588`

## callees

- `0x14000f3e0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000f473`
- `ntoskrnl!DbgPrintEx` at `0x14000f496`
- `ntoskrnl!DbgPrintEx` at `0x14000f473`
- `ntoskrnl!DbgPrintEx` at `0x14000f496`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f418`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f418`
- `ntoskrnl!ZwOpenKey` at `0x14000f44f`
- `ntoskrnl!ZwOpenKey` at `0x14000f44f`

## string_xrefs

- `0x14000f466`: `WERKERNELHOST: ZwOpenKey failed with scode 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryKey(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a2 && a4 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(a4, a3, &ObjectAttributes);
    v8 = v7;
    if ( v7 >= 0 )
      return 0;
    else
      DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwOpenKey failed with scode 0x%x\n", v7);
    return v8;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Invalid params\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000f3e0  push    rbp
0x14000f3e2  push    rbx
0x14000f3e3  push    rsi
0x14000f3e4  push    rdi
0x14000f3e5  mov     rbp, rsp
0x14000f3e8  sub     rsp, 68h
0x14000f3ec  xorps   xmm0, xmm0
0x14000f3ef  xor     eax, eax
0x14000f3f1  mov     rbx, r9
0x14000f3f4  mov     edi, r8d
0x14000f3f7  mov     rsi, rcx
0x14000f3fa  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000f3fe  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000f402  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000f406  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000f40a  test    rdx, rdx
0x14000f40d  jz      short loc_14000F487
0x14000f40f  test    rbx, rbx
0x14000f412  jz      short loc_14000F487
0x14000f414  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f418  call    cs:__imp_RtlInitUnicodeString
0x14000f41f  nop     dword ptr [rax+rax+00h]
0x14000f424  lea     rax, [rbp+DestinationString]
0x14000f428  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000f42f  xorps   xmm0, xmm0
0x14000f432  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000f436  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000f43a  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14000f43e  mov     edx, edi; DesiredAccess
0x14000f440  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000f447  mov     rcx, rbx; KeyHandle
0x14000f44a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f44f  call    cs:__imp_ZwOpenKey
0x14000f456  nop     dword ptr [rax+rax+00h]
0x14000f45b  mov     ebx, eax
0x14000f45d  test    eax, eax
0x14000f45f  jns     short loc_14000F481
0x14000f461  mov     edx, 1; Level
0x14000f466  lea     r8, aWerkernelhostZ_0; "WERKERNELHOST: ZwOpenKey failed with sc"...
0x14000f46d  mov     r9d, eax
0x14000f470  lea     ecx, [rdx+4]; ComponentId
0x14000f473  call    cs:__imp_DbgPrintEx
0x14000f47a  nop     dword ptr [rax+rax+00h]
0x14000f47f  jmp     short loc_14000F483
0x14000f481  xor     ebx, ebx
0x14000f483  mov     eax, ebx
0x14000f485  jmp     short loc_14000F4A7
0x14000f487  mov     edx, 1; Level
0x14000f48c  lea     r8, aWerkernelhostI_0; "WERKERNELHOST: Invalid params\n"
0x14000f493  lea     ecx, [rdx+4]; ComponentId
0x14000f496  call    cs:__imp_DbgPrintEx
0x14000f49d  nop     dword ptr [rax+rax+00h]
0x14000f4a2  mov     eax, 0C000000Dh
0x14000f4a7  add     rsp, 68h
0x14000f4ab  pop     rdi
0x14000f4ac  pop     rsi
0x14000f4ad  pop     rbx
0x14000f4ae  pop     rbp
0x14000f4af  retn
```
