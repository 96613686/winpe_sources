# BindOptionalNames

- ea: `0x18001d2a4`
- end: `0x18001d30c`
- name: `BindOptionalNames`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## callers

- `0x1800096d0`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x18001d2fe`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18001d2fe`

## pseudocode

```c
__int64 __fastcall BindOptionalNames(__int64 a1)
{
  __int64 (__fastcall *v2)(int, int, int, int, __int64); // [rsp+30h] [rbp-78h] BYREF
  int v3; // [rsp+38h] [rbp-70h]
  const wchar_t *v4; // [rsp+40h] [rbp-68h]
  __int64 v5; // [rsp+48h] [rbp-60h]
  int v6; // [rsp+50h] [rbp-58h]
  __int64 v7; // [rsp+58h] [rbp-50h]
  int v8; // [rsp+60h] [rbp-48h]
  __int64 v9; // [rsp+68h] [rbp-40h]
  int v10; // [rsp+70h] [rbp-38h]
  __int64 v11; // [rsp+78h] [rbp-30h]

  v2 = BindOptionalNameToTransport;
  v3 = 0;
  v5 = 0;
  v4 = L"OptionalNames";
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  return RtlQueryRegistryValuesEx(2147483649LL, L"LanmanServer\\Parameters", &v2, a1, 0);
}

```

## disassembly

```asm
0x18001d2a4  mov     r11, rsp
0x18001d2a7  sub     rsp, 0A8h
0x18001d2ae  xor     edx, edx
0x18001d2b0  lea     rax, BindOptionalNameToTransport
0x18001d2b7  mov     [r11-78h], rax
0x18001d2bb  lea     r8, [r11-78h]
0x18001d2bf  mov     [rsp+0A8h+var_70], edx
0x18001d2c3  lea     rax, aOptionalnames; "OptionalNames"
0x18001d2ca  mov     [r11-60h], rdx
0x18001d2ce  mov     r9, rcx
0x18001d2d1  mov     [r11-68h], rax
0x18001d2d5  mov     ecx, 80000001h
0x18001d2da  mov     [rsp+0A8h+var_58], edx
0x18001d2de  mov     [r11-50h], rdx
0x18001d2e2  mov     [rsp+0A8h+var_48], edx
0x18001d2e6  mov     [r11-40h], rdx
0x18001d2ea  mov     [rsp+0A8h+var_38], edx
0x18001d2ee  mov     [r11-30h], rdx
0x18001d2f2  mov     [rsp+0A8h+var_88], rdx
0x18001d2f7  lea     rdx, aLanmanserverPa; "LanmanServer\\Parameters"
0x18001d2fe  call    cs:__imp_RtlQueryRegistryValuesEx
0x18001d304  add     rsp, 0A8h
0x18001d30b  retn
```
