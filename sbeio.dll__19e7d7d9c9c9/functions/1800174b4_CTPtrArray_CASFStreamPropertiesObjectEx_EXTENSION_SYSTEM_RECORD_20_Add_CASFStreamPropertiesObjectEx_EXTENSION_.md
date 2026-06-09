# CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::Add(CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,ulong *)

- ea: `0x1800174b4`
- end: `0x1800174e0`
- name: `?Add@?$CTPtrArray@U_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@QEAAHPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@PEAK@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017588`
- `0x180023760`

## callees

- `0x1800174b4`
- `0x180025614`

## pseudocode

```c
_BOOL8 __fastcall CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::Add(
        _DWORD *a1,
        __int64 (__fastcall **a2)(_QWORD, _QWORD *))
{
  int v3; // eax

  v3 = CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(
         a1,
         a1[54],
         a2);
  if ( v3 >= 0 )
    ++a1[54];
  return v3 >= 0;
}

```

## disassembly

```asm
0x1800174b4  push    rbx
0x1800174b6  sub     rsp, 20h
0x1800174ba  mov     r8, rdx
0x1800174bd  mov     rbx, rcx
0x1800174c0  mov     edx, [rcx+0D8h]
0x1800174c6  call    ?SetValue@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@QEAAJKPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *)
0x1800174cb  test    eax, eax
0x1800174cd  js      short loc_1800174D5
0x1800174cf  inc     dword ptr [rbx+0D8h]
0x1800174d5  not     eax
0x1800174d7  shr     eax, 1Fh
0x1800174da  add     rsp, 20h
0x1800174de  pop     rbx
0x1800174df  retn
```
