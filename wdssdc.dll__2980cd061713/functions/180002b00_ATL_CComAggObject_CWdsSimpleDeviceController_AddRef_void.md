# ATL::CComAggObject<CWdsSimpleDeviceController>::AddRef(void)

- ea: `0x180002b00`
- end: `0x180002b29`
- name: `?AddRef@?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b00`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWdsSimpleDeviceController>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180002b00  mov     r9d, 7FFFFFFFh
0x180002b06  jmp     short loc_180002B16
0x180002b08  lea     edx, [r8+1]
0x180002b0c  mov     eax, r8d
0x180002b0f  lock cmpxchg [rcx+8], edx
0x180002b14  jz      short loc_180002B21
0x180002b16  mov     r8d, [rcx+8]
0x180002b1a  cmp     r8d, r9d
0x180002b1d  jnz     short loc_180002B08
0x180002b1f  jmp     short loc_180002B25
0x180002b21  lea     r9d, [r8+1]
0x180002b25  mov     eax, r9d
0x180002b28  retn
```
