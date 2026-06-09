# ATL::CComObject<ATL::CAxUIWindow>::AddRef(void)

- ea: `0x140002aa0`
- end: `0x140002ab3`
- name: `?AddRef@?$CComObject@VCAxUIWindow@ATL@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002aa0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CAxUIWindow>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 8);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 8) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140002aa0  mov     edx, [rcx+8]
0x140002aa3  mov     eax, 7FFFFFFFh
0x140002aa8  cmp     edx, eax
0x140002aaa  jz      short locret_140002AB2
0x140002aac  lea     eax, [rdx+1]
0x140002aaf  mov     [rcx+8], eax
0x140002ab2  retn
```
