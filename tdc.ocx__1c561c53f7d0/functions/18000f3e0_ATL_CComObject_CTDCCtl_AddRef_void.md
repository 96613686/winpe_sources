# ATL::CComObject<CTDCCtl>::AddRef(void)

- ea: `0x18000f3e0`
- end: `0x18000f3f9`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ`
- size: `25`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f400`
- `0x18000f410`
- `0x18000f420`
- `0x18000f430`
- `0x18000f440`
- `0x18000f450`
- `0x18000f460`
- `0x18000f470`
- `0x18000f480`
- `0x18000f490`
- `0x18000f4a0`

## callees

- `0x18000f3e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 128);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 128) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000f3e0  mov     edx, [rcx+80h]
0x18000f3e6  mov     eax, 7FFFFFFFh
0x18000f3eb  cmp     edx, eax
0x18000f3ed  jz      short locret_18000F3F8
0x18000f3ef  lea     eax, [rdx+1]
0x18000f3f2  mov     [rcx+80h], eax
0x18000f3f8  retn
```
