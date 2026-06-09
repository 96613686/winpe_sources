# Pca::MergeSdb::Utils::RegUtil::DeleteRegValue(HKEY__ *,ushort const *)

- ea: `0x14002a33c`
- end: `0x14002a3a1`
- name: `?DeleteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG@Z`
- size: `101`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x14002a33c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyValueW` at `0x14002a35d`
- `ADVAPI32!RegDeleteKeyValueW` at `0x14002a35d`

## string_xrefs

- `0x14002a36d`: `RegDeleteKeyValueW failed to delete value '%S' (%d)`
- `0x14002a37f`: `Pca::MergeSdb::Utils::RegUtil::DeleteRegValue`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegUtil::DeleteRegValue(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v4; // eax
  unsigned int v5; // edi

  if ( !a2 )
    return 87;
  v4 = RegDeleteKeyValueW(a1, &Format, a2);
  v5 = v4;
  if ( !v4 )
    return 0;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::RegUtil::DeleteRegValue",
    327,
    "RegDeleteKeyValueW failed to delete value '%S' (%d)",
    a2,
    v4);
  return v5;
}

```

## disassembly

```asm
0x14002a33c  mov     [rsp+arg_0], rbx
0x14002a341  push    rdi
0x14002a342  sub     rsp, 30h
0x14002a346  mov     rbx, rdx
0x14002a349  test    rdx, rdx
0x14002a34c  jnz     short loc_14002A353
0x14002a34e  lea     eax, [rdx+57h]
0x14002a351  jmp     short loc_14002A396
0x14002a353  mov     r8, rbx; lpValueName
0x14002a356  lea     rdx, Format; lpSubKey
0x14002a35d  call    cs:__imp_RegDeleteKeyValueW
0x14002a363  mov     edi, eax
0x14002a365  test    eax, eax
0x14002a367  jz      short loc_14002A394
0x14002a369  mov     [rsp+38h+var_10], eax
0x14002a36d  lea     r9, aRegdeletekeyva; "RegDeleteKeyValueW failed to delete val"...
0x14002a374  mov     r8d, 147h
0x14002a37a  mov     [rsp+38h+var_18], rbx
0x14002a37f  lea     rdx, aPcaMergesdbUti_24; "Pca::MergeSdb::Utils::RegUtil::DeleteRe"...
0x14002a386  mov     ecx, 1
0x14002a38b  call    AslLogCallPrintf
0x14002a390  mov     eax, edi
0x14002a392  jmp     short loc_14002A396
0x14002a394  xor     eax, eax
0x14002a396  mov     rbx, [rsp+38h+arg_0]
0x14002a39b  add     rsp, 30h
0x14002a39f  pop     rdi
0x14002a3a0  retn
```
