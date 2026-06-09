# VelocityDeleteReg(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180034334`
- end: `0x1800343b2`
- name: `?VelocityDeleteReg@@YAHPEAUHKEY__@@PEBG1@Z`
- size: `126`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180034840`
- `0x1800348b0`

## callees

- `0x180034334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003438c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003438c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003437a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003437a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034399`

## pseudocode

```c
__int64 __fastcall VelocityDeleteReg(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // edi
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v5 = RegDeleteValueW(hKey, a3);
    RegCloseKey(hKey);
    LOBYTE(v3) = v5 == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180034334  mov     r11, rsp
0x180034337  mov     [r11+10h], rbx
0x18003433b  mov     [r11+8], rcx
0x18003433f  push    rdi
0x180034340  sub     rsp, 50h
0x180034344  xor     edi, edi
0x180034346  mov     qword ptr [r11+8], 0
0x18003434e  mov     [r11-18h], rdi
0x180034352  lea     rax, [r11+8]
0x180034356  mov     [r11-20h], rax
0x18003435a  mov     rbx, r8
0x18003435d  mov     [r11-28h], rdi
0x180034361  xor     r9d, r9d; lpClass
0x180034364  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18003436c  xor     r8d, r8d; Reserved
0x18003436f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034376  mov     [rsp+58h+dwOptions], edi; dwOptions
0x18003437a  call    cs:__imp_RegCreateKeyExW
0x180034380  test    eax, eax
0x180034382  jnz     short loc_1800343A5
0x180034384  mov     rcx, [rsp+58h+hKey]; hKey
0x180034389  mov     rdx, rbx; lpValueName
0x18003438c  call    cs:__imp_RegDeleteValueW
0x180034392  mov     rcx, [rsp+58h+hKey]; hKey
0x180034397  mov     ebx, eax
0x180034399  call    cs:__imp_RegCloseKey
0x18003439f  test    ebx, ebx
0x1800343a1  setz    dil
0x1800343a5  mov     rbx, [rsp+58h+arg_8]
0x1800343aa  mov     eax, edi
0x1800343ac  add     rsp, 50h
0x1800343b0  pop     rdi
0x1800343b1  retn
```
