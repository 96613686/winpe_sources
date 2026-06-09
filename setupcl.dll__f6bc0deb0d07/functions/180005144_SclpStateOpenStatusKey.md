# SclpStateOpenStatusKey

- ea: `0x180005144`
- end: `0x1800051cf`
- name: `SclpStateOpenStatusKey`
- size: `139`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000438c`
- `0x1800065f8`

## callees

- `0x1800014e8`
- `0x180005144`
- `0x18000a524`

## string_xrefs

- `0x1800051b5`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL`
- `0x18000515e`: `Manipulating SetupCl status in offline mode requires access to the offline SYSTEM hive.`
- `0x180005177`: `SclpStateOpenStatusKey`

## pseudocode

```c
__int64 __fastcall SclpStateOpenStatusKey(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v5; // rcx
  const WCHAR *v6; // rdx

  if ( !a1 )
  {
    v3 = 1;
    goto LABEL_8;
  }
  v3 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 == 2 )
  {
    if ( !*(_QWORD *)(a1 + 56) )
    {
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        1655,
        (__int64)"SclpStateOpenStatusKey",
        "Manipulating SetupCl status in offline mode requires access to the offline SYSTEM hive.");
      return 3221225485LL;
    }
    goto LABEL_6;
  }
  if ( v3 == 1 )
  {
LABEL_8:
    v5 = 0;
    goto LABEL_9;
  }
LABEL_6:
  v5 = *(_QWORD *)(a1 + 56);
LABEL_9:
  v6 = L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL";
  if ( v3 != 1 )
    v6 = L"SETUP\\SETUPCL";
  return SclCreateKey(v5, v6, 0xF003Fu, a2);
}

```

## disassembly

```asm
0x180005144  sub     rsp, 38h
0x180005148  mov     r9, rdx
0x18000514b  test    rcx, rcx
0x18000514e  jz      short loc_1800051A4
0x180005150  mov     eax, [rcx]
0x180005152  cmp     eax, 2
0x180005155  jnz     short loc_180005199
0x180005157  cmp     qword ptr [rcx+38h], 0
0x18000515c  jnz     short loc_18000519E
0x18000515e  lea     rax, aManipulatingSe; "Manipulating SetupCl status in offline "...
0x180005165  mov     r9d, 677h
0x18000516b  mov     [rsp+38h+var_10], rax
0x180005170  lea     r8, SclEvent_Generic_Error
0x180005177  lea     rax, aSclpstateopens; "SclpStateOpenStatusKey"
0x18000517e  mov     edx, 3
0x180005183  xor     ecx, ecx
0x180005185  mov     [rsp+38h+var_18], rax
0x18000518a  call    SclLogGenericMessage
0x18000518f  mov     eax, 0C000000Dh
0x180005194  add     rsp, 38h
0x180005198  retn
0x180005199  cmp     eax, 1
0x18000519c  jz      short loc_1800051A9
0x18000519e  mov     rcx, [rcx+38h]
0x1800051a2  jmp     short loc_1800051AB
0x1800051a4  mov     eax, 1
0x1800051a9  xor     ecx, ecx
0x1800051ab  lea     r8, aSetupSetupcl; "SETUP\\SETUPCL"
0x1800051b2  cmp     eax, 1
0x1800051b5  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x1800051bc  cmovnz  rdx, r8
0x1800051c0  mov     r8d, 0F003Fh
0x1800051c6  add     rsp, 38h
0x1800051ca  jmp     SclCreateKey
```
