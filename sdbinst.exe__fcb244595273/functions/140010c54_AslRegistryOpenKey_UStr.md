# AslRegistryOpenKey_UStr

- ea: `0x140010c54`
- end: `0x140010c96`
- name: `AslRegistryOpenKey_UStr`
- size: `66`
- prototype: `NTSTATUS __fastcall(void **, struct _UNICODE_STRING *, ACCESS_MASK)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140010bd8`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x140010c8b`
- `ntdll!ZwOpenKey` at `0x140010c8b`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenKey_UStr(void **a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.ObjectName = a2;
  *(_QWORD *)&v4.Length = 48;
  v4.RootDirectory = 0;
  *a1 = 0;
  *(_QWORD *)&v4.Attributes = 64;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a1, a3, &v4);
}

```

## disassembly

```asm
0x140010c54  mov     r11, rsp
0x140010c57  sub     rsp, 58h
0x140010c5b  mov     eax, r8d
0x140010c5e  mov     [r11-28h], rdx
0x140010c62  xor     r8d, r8d
0x140010c65  mov     qword ptr [r11-38h], 30h ; '0'
0x140010c6d  mov     [r11-30h], r8
0x140010c71  xorps   xmm0, xmm0
0x140010c74  mov     [rcx], r8
0x140010c77  mov     edx, eax; DesiredAccess
0x140010c79  mov     qword ptr [r11-20h], 40h ; '@'
0x140010c81  lea     r8, [r11-38h]; ObjectAttributes
0x140010c85  movdqu  [rsp+58h+var_18], xmm0
0x140010c8b  call    cs:__imp_ZwOpenKey
0x140010c91  add     rsp, 58h
0x140010c95  retn
```
