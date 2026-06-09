# ATL::CComObject<CFciPropertiesShellExt>::AddRef(void)

- ea: `0x180005cb0`
- end: `0x180005cc3`
- name: `?AddRef@?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005cd0`

## callees

- `0x180005cb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 16);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180005cb0  mov     edx, [rcx+10h]
0x180005cb3  mov     eax, 7FFFFFFFh
0x180005cb8  cmp     edx, eax
0x180005cba  jz      short locret_180005CC2
0x180005cbc  lea     eax, [rdx+1]
0x180005cbf  mov     [rcx+10h], eax
0x180005cc2  retn
```
