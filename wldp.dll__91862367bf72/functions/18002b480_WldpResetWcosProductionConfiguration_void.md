# WldpResetWcosProductionConfiguration(void)

- ea: `0x18002b480`
- end: `0x18002b4e0`
- name: `?WldpResetWcosProductionConfiguration@@YAJXZ`
- size: `96`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002af60`

## callees

- `0x18002a480`
- `0x18002a940`
- `0x18002b480`

## string_xrefs

- `0x18002b494`: `Microsoft\WatermarkHSTITestComplete.bin`
- `0x18002b4ba`: `Microsoft\WatermarkSBTestComplete.bin`

## pseudocode

```c
__int64 WldpResetWcosProductionConfiguration(void)
{
  __int64 result; // rax
  int v1; // ecx

  result = InitializeWcosWatermarkPath();
  if ( (int)result >= 0 )
  {
    result = DeleteWatermarkState(L"Microsoft\\WatermarkHSTITestComplete.bin", qword_18005ADE0);
    if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -2147024894 )
    {
      v1 = DeleteWatermarkState(L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0);
      if ( v1 >= 0 )
      {
        return 0;
      }
      else
      {
        result = 0;
        if ( v1 != -2147024894 )
          return (unsigned int)v1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b480  sub     rsp, 28h
0x18002b484  call    ?InitializeWcosWatermarkPath@@YAJXZ; InitializeWcosWatermarkPath(void)
0x18002b489  test    eax, eax
0x18002b48b  js      short loc_18002B4DB
0x18002b48d  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b494  lea     rcx, aMicrosoftWater_0; "Microsoft\\WatermarkHSTITestComplete.bi"...
0x18002b49b  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b4a0  mov     edx, 80000000h
0x18002b4a5  lea     ecx, [rax+rdx]
0x18002b4a8  test    edx, ecx
0x18002b4aa  jnz     short loc_18002B4B3
0x18002b4ac  cmp     eax, 80070002h
0x18002b4b1  jnz     short loc_18002B4DB
0x18002b4b3  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b4ba  lea     rcx, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b4c1  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b4c6  mov     ecx, eax
0x18002b4c8  test    eax, eax
0x18002b4ca  jns     short loc_18002B4D9
0x18002b4cc  xor     eax, eax
0x18002b4ce  cmp     ecx, 80070002h
0x18002b4d4  cmovnz  eax, ecx
0x18002b4d7  jmp     short loc_18002B4DB
0x18002b4d9  xor     eax, eax
0x18002b4db  add     rsp, 28h
0x18002b4df  retn
```
