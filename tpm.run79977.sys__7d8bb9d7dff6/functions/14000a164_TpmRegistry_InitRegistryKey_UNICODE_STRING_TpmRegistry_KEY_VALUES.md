# TpmRegistry::InitRegistryKey(_UNICODE_STRING *,TpmRegistry::KEY_VALUES)

- ea: `0x14000a164`
- end: `0x14000a194`
- name: `?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@W4KEY_VALUES@1@@Z`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005840`
- `0x14000a0a4`
- `0x14000a19c`
- `0x14002f0b0`
- `0x14002fd1c`

## callees

- `0x14000a164`
- `0x14000a19c`

## pseudocode

```c
__int64 __fastcall TpmRegistry::InitRegistryKey(struct _UNICODE_STRING *a1, unsigned int a2)
{
  if ( a2 > 0x22 )
    return 3221225485LL;
  else
    return TpmRegistry::InitRegistryKey(a1, off_140047138[2 * (int)a2], a2);
}

```

## disassembly

```asm
0x14000a164  sub     rsp, 28h
0x14000a168  movsxd  r8, edx
0x14000a16b  cmp     r8d, 22h ; '"'
0x14000a16f  ja      short loc_14000A18D
0x14000a171  mov     rdx, r8
0x14000a174  lea     rax, off_140047138; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000a17b  add     rdx, rdx
0x14000a17e  mov     rdx, [rax+rdx*8]
0x14000a182  call    ?InitRegistryKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEBGW4KEY_VALUES@1@@Z; TpmRegistry::InitRegistryKey(_UNICODE_STRING *,ushort const *,TpmRegistry::KEY_VALUES)
0x14000a187  add     rsp, 28h
0x14000a18b  retn
0x14000a18d  mov     eax, 0C000000Dh
0x14000a192  jmp     short loc_14000A187
```
