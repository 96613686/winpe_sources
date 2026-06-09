# RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)

- ea: `0x180029c94`
- end: `0x180029cc1`
- name: `?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z`
- size: `45`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *const, unsigned int, unsigned int, PHKEY)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800272bc`
- `0x180028714`
- `0x180028950`
- `0x180028d58`
- `0x18004f580`
- `0x1800504c0`
- `0x18005138c`
- `0x1800515a4`
- `0x180051efc`

## callees

- `0x180029c94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029caa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029caa`

## pseudocode

```c
LSTATUS __fastcall RegWow64Helpers::OpenKey(HKEY a1, const WCHAR *a2, __int64 a3, int a4, PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(a1, a2, 0, a4 | 0x100, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029c94  sub     rsp, 38h
0x180029c98  mov     rax, [rsp+38h+arg_20]
0x180029c9d  bts     r9d, 8; samDesired
0x180029ca2  xor     r8d, r8d; ulOptions
0x180029ca5  mov     [rsp+38h+phkResult], rax; phkResult
0x180029caa  call    cs:__imp_RegOpenKeyExW
0x180029cb0  test    eax, eax
0x180029cb2  jle     short loc_180029CBC
0x180029cb4  movzx   eax, ax
0x180029cb7  or      eax, 80070000h
0x180029cbc  add     rsp, 38h
0x180029cc0  retn
```
