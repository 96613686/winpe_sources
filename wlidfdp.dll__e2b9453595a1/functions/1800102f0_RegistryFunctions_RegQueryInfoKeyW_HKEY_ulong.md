# RegistryFunctions::RegQueryInfoKeyW(HKEY__ *,ulong *)

- ea: `0x1800102f0`
- end: `0x180010332`
- name: `?RegQueryInfoKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEAK@Z`
- size: `66`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010327`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010327`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegQueryInfoKeyW(RegistryFunctions *this, HKEY a2, unsigned int *a3)
{
  return RegQueryInfoKeyW(a2, 0, 0, 0, 0, a3, 0, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x1800102f0  mov     r11, rsp
0x1800102f3  sub     rsp, 68h
0x1800102f7  xor     ecx, ecx
0x1800102f9  mov     rax, rdx
0x1800102fc  mov     [r11-10h], rcx
0x180010300  xor     r9d, r9d; lpReserved
0x180010303  mov     [r11-18h], rcx
0x180010307  xor     edx, edx; lpClass
0x180010309  mov     [r11-20h], rcx
0x18001030d  mov     [r11-28h], rcx
0x180010311  mov     [r11-30h], rcx
0x180010315  mov     [r11-38h], rcx
0x180010319  mov     [r11-40h], r8
0x18001031d  xor     r8d, r8d; lpcchClass
0x180010320  mov     [r11-48h], rcx
0x180010324  mov     rcx, rax; hKey
0x180010327  call    cs:__imp_RegQueryInfoKeyW
0x18001032d  add     rsp, 68h
0x180010331  retn
```
