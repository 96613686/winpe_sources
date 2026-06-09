# _SecurityLogicControl::GetString_::_1_::catch$8

- ea: `0x18000ac7e`
- end: `0x18000acc6`
- name: `_SecurityLogicControl::GetString_::_1_::catch$8`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004c48`
- `0x18000ac7e`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aca7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000aca7`

## pseudocode

```c
__int64 __fastcall SecurityLogicControl::GetString_::_1_::catch_8(__int64 a1, __int64 a2)
{
  HMODULE v3; // rcx

  ATL::CSimpleStringT<unsigned short,0>::SetString((char **)(a2 + 32), byte_18000F684, 0);
  v3 = *(HMODULE *)(a2 + 40);
  if ( v3 )
  {
    FreeLibrary(v3);
    *(_QWORD *)(a2 + 40) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ac7e  mov     [rsp+arg_8], rdx
0x18000ac83  push    rbp
0x18000ac84  sub     rsp, 20h
0x18000ac88  mov     rbp, rdx
0x18000ac8b  xor     r8d, r8d
0x18000ac8e  lea     rdx, byte_18000F684
0x18000ac95  lea     rcx, [rbp+20h]
0x18000ac99  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ac9e  mov     rcx, [rbp+28h]; hLibModule
0x18000aca2  test    rcx, rcx
0x18000aca5  jz      short loc_18000ACB5
0x18000aca7  call    cs:__imp_FreeLibrary
0x18000acad  mov     qword ptr [rbp+28h], 0
0x18000acb5  mov     rax, 0
0x18000acbf  add     rsp, 20h
0x18000acc3  pop     rbp
0x18000acc4  retn
```
