# CredentialUpdateRegister(_UNICODE_STRING *)

- ea: `0x180024e80`
- end: `0x180024e98`
- name: `?CredentialUpdateRegister@@YAEPEAU_UNICODE_STRING@@@Z`
- size: `24`
- prototype: `unsigned __int8 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024e8b`
- `ntdll!RtlInitUnicodeString` at `0x180024e8b`

## pseudocode

```c
unsigned __int8 __fastcall CredentialUpdateRegister(struct _UNICODE_STRING *a1)
{
  RtlInitUnicodeString(a1, L"WDigest");
  return 1;
}

```

## disassembly

```asm
0x180024e80  sub     rsp, 28h
0x180024e84  lea     rdx, aWdigest; "WDigest"
0x180024e8b  call    cs:__imp_RtlInitUnicodeString
0x180024e91  mov     al, 1
0x180024e93  add     rsp, 28h
0x180024e97  retn
```
