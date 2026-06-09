# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::GetConnectionPointContainer(IConnectionPointContainer * *)

- ea: `0x180005ac0`
- end: `0x180005ae8`
- name: `?GetConnectionPointContainer@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_IPropertyNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIConnectionPointContainer@@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::GetConnectionPointContainer(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9

  v2 = a1 - 80;
  if ( !a1 )
    v2 = 176;
  return (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v2)(v2, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, a2);
}

```

## disassembly

```asm
0x180005ac0  test    rcx, rcx
0x180005ac3  lea     r9, [rcx-50h]
0x180005ac7  mov     eax, 0B0h
0x180005acc  mov     r8, rdx
0x180005acf  cmovz   r9, rax
0x180005ad3  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x180005ada  mov     rcx, r9
0x180005add  mov     rax, [r9]
0x180005ae0  mov     rax, [rax]
0x180005ae3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
