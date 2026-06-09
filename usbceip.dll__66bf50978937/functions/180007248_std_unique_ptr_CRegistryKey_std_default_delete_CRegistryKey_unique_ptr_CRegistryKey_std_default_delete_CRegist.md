# std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>>::~unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>>(void)

- ea: `0x180007248`
- end: `0x18000725e`
- name: `??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `28`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003dc4`
- `0x1800045d0`
- `0x1800053e4`
- `0x180006f18`
- `0x1800073b4`
- `0x180008904`
- `0x180008960`
- `0x180008a60`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x1800090d4`
- `0x180009204`
- `0x180009424`
- `0x180009748`
- `0x18000ba28`
- `0x1800100c4`
- `0x180010142`
- `0x180010154`
- `0x180010166`
- `0x1800101c0`
- `0x180010410`
- `0x180010422`
- `0x180010446`
- `0x1800105b0`
- `0x18001062c`
- `0x180010665`
- `0x180010677`

## callees

- `0x180007248`
- `0x180007264`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CRegistryKey>::operator()();
  return result;
}

```

## disassembly

```asm
0x180007248  sub     rsp, 28h
0x18000724c  mov     rdx, [rcx]
0x18000724f  test    rdx, rdx
0x180007252  jz      short loc_180007259
0x180007254  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x180007259  add     rsp, 28h
0x18000725d  retn
```
