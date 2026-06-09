# CUwfStaticConfiguration::ReOpen(ulong)

- ea: `0x180008c00`
- end: `0x180008c24`
- name: `?ReOpen@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `36`
- prototype: `int __fastcall(HKEY *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180008b3c`
- `0x180008c00`

## string_xrefs

- `0x180008c18`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy0`
- `0x180008c0f`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy1`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::ReOpen(HKEY *this, int a2)
{
  const unsigned __int16 *v3; // rdx

  if ( a2 )
  {
    if ( a2 != 1 )
      return -2147024809;
    v3 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy1";
  }
  else
  {
    v3 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy0";
  }
  return CUwfStaticConfiguration::ReOpen(this, v3);
}

```

## disassembly

```asm
0x180008c00  test    edx, edx
0x180008c02  jz      short loc_180008C18
0x180008c04  cmp     edx, 1
0x180008c07  jz      short loc_180008C0F
0x180008c09  mov     eax, 80070057h
0x180008c0e  retn
0x180008c0f  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008c16  jmp     short loc_180008C1F
0x180008c18  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008c1f  jmp     ?ReOpen@CUwfStaticConfiguration@@AEAAJPEBG@Z; CUwfStaticConfiguration::ReOpen(ushort const *)
```
