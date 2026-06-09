# ATL::CComObject<CWMPRichPreviewExt>::AddRef(void)

- ea: `0x140009cf0`
- end: `0x140009d03`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009d10`
- `0x140009d20`
- `0x140009d30`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 32);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 32) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140009cf0  mov     edx, [rcx+20h]
0x140009cf3  mov     eax, 7FFFFFFFh
0x140009cf8  cmp     edx, eax
0x140009cfa  jz      short locret_140009D02
0x140009cfc  lea     eax, [rdx+1]
0x140009cff  mov     [rcx+20h], eax
0x140009d02  retn
```
