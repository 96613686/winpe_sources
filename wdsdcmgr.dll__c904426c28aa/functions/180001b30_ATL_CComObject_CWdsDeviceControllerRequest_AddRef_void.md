# ATL::CComObject<CWdsDeviceControllerRequest>::AddRef(void)

- ea: `0x180001b30`
- end: `0x180001b63`
- name: `?AddRef@?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@UEAAKXZ`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsDeviceControllerRequest>::AddRef(__int64 a1)
{
  signed __int32 v1; // r8d
  unsigned int v2; // r9d

  v1 = *(_DWORD *)(a1 + 8);
  v2 = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    do
    {
      if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v1 + 1, v1) )
        break;
      v1 = *(_DWORD *)(a1 + 8);
    }
    while ( v1 != 0x7FFFFFFF );
    if ( v1 != 0x7FFFFFFF )
      return (unsigned int)(v1 + 1);
  }
  return v2;
}

```

## disassembly

```asm
0x180001b30  mov     r8d, [rcx+8]
0x180001b34  mov     r9d, 7FFFFFFFh
0x180001b3a  cmp     r8d, r9d
0x180001b3d  jz      short loc_180001B5F
0x180001b3f  lea     edx, [r8+1]
0x180001b43  mov     eax, r8d
0x180001b46  lock cmpxchg [rcx+8], edx
0x180001b4b  jz      short loc_180001B56
0x180001b4d  mov     r8d, [rcx+8]
0x180001b51  cmp     r8d, r9d
0x180001b54  jnz     short loc_180001B3F
0x180001b56  cmp     r8d, r9d
0x180001b59  jz      short loc_180001B5F
0x180001b5b  lea     r9d, [r8+1]
0x180001b5f  mov     eax, r9d
0x180001b62  retn
```
