# CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)

- ea: `0x18000de90`
- end: `0x18000dede`
- name: `?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z`
- size: `78`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, REGSAM, struct CUwfRegKey *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008730`
- `0x18000def0`
- `0x180015bb4`
- `0x180015e74`

## callees

- `0x18000d5a0`
- `0x18000de90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000deb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000deb5`

## pseudocode

```c
LSTATUS __fastcall CUwfRegKey::OpenSubKey(HKEY *this, const unsigned __int16 *a2, REGSAM a3, struct CUwfRegKey *a4)
{
  HKEY v4; // rcx
  LSTATUS result; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  v4 = *this;
  phkResult = 0;
  result = RegOpenKeyExW(v4, a2, 0, a3, &phkResult);
  if ( !result )
    return CUwfRegKey::Attach(a4, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000de90  push    rbx
0x18000de92  sub     rsp, 30h
0x18000de96  mov     rcx, [rcx]; hKey
0x18000de99  lea     rax, [rsp+38h+arg_0]
0x18000de9e  mov     rbx, r9
0x18000dea1  mov     [rsp+38h+arg_0], 0
0x18000deaa  mov     r9d, r8d; samDesired
0x18000dead  mov     [rsp+38h+phkResult], rax; phkResult
0x18000deb2  xor     r8d, r8d; ulOptions
0x18000deb5  call    cs:__imp_RegOpenKeyExW
0x18000debb  test    eax, eax
0x18000debd  jz      short loc_18000DECB
0x18000debf  jle     short loc_18000DED8
0x18000dec1  movzx   eax, ax
0x18000dec4  or      eax, 80070000h
0x18000dec9  jmp     short loc_18000DED8
0x18000decb  mov     rdx, [rsp+38h+arg_0]; HKEY
0x18000ded0  mov     rcx, rbx; this
0x18000ded3  call    ?Attach@CUwfRegKey@@QEAAJPEAUHKEY__@@@Z; CUwfRegKey::Attach(HKEY__ *)
0x18000ded8  add     rsp, 30h
0x18000dedc  pop     rbx
0x18000dedd  retn
```
