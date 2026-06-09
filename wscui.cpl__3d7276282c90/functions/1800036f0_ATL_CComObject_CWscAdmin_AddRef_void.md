# ATL::CComObject<CWscAdmin>::AddRef(void)

- ea: `0x1800036f0`
- end: `0x180003703`
- name: `?AddRef@?$CComObject@VCWscAdmin@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800036f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWscAdmin>::AddRef(__int64 a1)
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
0x1800036f0  mov     edx, [rcx+8]
0x1800036f3  mov     eax, 7FFFFFFFh
0x1800036f8  cmp     edx, eax
0x1800036fa  jz      short locret_180003702
0x1800036fc  lea     eax, [rdx+1]
0x1800036ff  mov     [rcx+8], eax
0x180003702  retn
```
