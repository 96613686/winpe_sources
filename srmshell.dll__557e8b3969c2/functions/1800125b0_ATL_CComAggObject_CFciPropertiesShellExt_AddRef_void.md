# ATL::CComAggObject<CFciPropertiesShellExt>::AddRef(void)

- ea: `0x1800125b0`
- end: `0x1800125c3`
- name: `?AddRef@?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800125b0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CFciPropertiesShellExt>::AddRef(__int64 a1)
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
0x1800125b0  mov     edx, [rcx+8]
0x1800125b3  mov     eax, 7FFFFFFFh
0x1800125b8  cmp     edx, eax
0x1800125ba  jz      short locret_1800125C2
0x1800125bc  lea     eax, [rdx+1]
0x1800125bf  mov     [rcx+8], eax
0x1800125c2  retn
```
