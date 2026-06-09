# ATL::CComObject<CTapiLuaLib>::AddRef(void)

- ea: `0x180001fb0`
- end: `0x180001fc3`
- name: `?AddRef@?$CComObject@VCTapiLuaLib@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001fb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTapiLuaLib>::AddRef(__int64 a1)
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
0x180001fb0  mov     edx, [rcx+8]
0x180001fb3  mov     eax, 7FFFFFFFh
0x180001fb8  cmp     edx, eax
0x180001fba  jz      short locret_180001FC2
0x180001fbc  lea     eax, [rdx+1]
0x180001fbf  mov     [rcx+8], eax
0x180001fc2  retn
```
