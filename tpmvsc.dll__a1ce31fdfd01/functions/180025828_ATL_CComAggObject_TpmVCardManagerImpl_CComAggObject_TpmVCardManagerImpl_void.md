# ATL::CComAggObject<TpmVCardManagerImpl>::~CComAggObject<TpmVCardManagerImpl>(void)

- ea: `0x180025828`
- end: `0x18002584c`
- name: `??1?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@UEAA@XZ`
- size: `36`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025fb0`

## callees

- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<TpmVCardManagerImpl>::~CComAggObject<TpmVCardManagerImpl>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<TpmVCardManagerImpl>::`vftable';
  return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
}

```

## disassembly

```asm
0x180025828  mov     dword ptr [rcx+8], 0C0000001h
0x18002582f  lea     rax, ??_7?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@6B@; const ATL::CComAggObject<TpmVCardManagerImpl>::`vftable'
0x180025836  mov     [rcx], rax
0x180025839  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180025840  mov     rax, [rcx]
0x180025843  mov     rax, [rax+10h]
0x180025847  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
