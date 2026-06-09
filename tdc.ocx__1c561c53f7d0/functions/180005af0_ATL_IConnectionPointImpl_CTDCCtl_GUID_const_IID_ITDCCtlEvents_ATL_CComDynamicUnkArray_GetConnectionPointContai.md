# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::GetConnectionPointContainer(IConnectionPointContainer * *)

- ea: `0x180005af0`
- end: `0x180005b18`
- name: `?GetConnectionPointContainer@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_ITDCCtlEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIConnectionPointContainer@@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::GetConnectionPointContainer(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9

  v2 = a1 - 104;
  if ( !a1 )
    v2 = 176;
  return (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v2)(v2, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, a2);
}

```

## disassembly

```asm
0x180005af0  test    rcx, rcx
0x180005af3  lea     r9, [rcx-68h]
0x180005af7  mov     eax, 0B0h
0x180005afc  mov     r8, rdx
0x180005aff  cmovz   r9, rax
0x180005b03  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x180005b0a  mov     rcx, r9
0x180005b0d  mov     rax, [r9]
0x180005b10  mov     rax, [rax]
0x180005b13  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
