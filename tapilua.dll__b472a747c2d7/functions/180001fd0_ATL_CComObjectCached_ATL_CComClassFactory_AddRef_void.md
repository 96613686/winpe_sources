# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180001fd0`
- end: `0x180002006`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001fd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // r8d
  signed __int32 v2; // r9d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      if ( v2 == 1 )
        _InterlockedIncrement(&dword_18000A288);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180001fd0  mov     r8d, 7FFFFFFFh
0x180001fd6  jmp     short loc_180001FE6
0x180001fd8  lea     edx, [r9+1]
0x180001fdc  mov     eax, r9d
0x180001fdf  lock cmpxchg [rcx+8], edx
0x180001fe4  jz      short loc_180001FF1
0x180001fe6  mov     r9d, [rcx+8]
0x180001fea  cmp     r9d, r8d
0x180001fed  jnz     short loc_180001FD8
0x180001fef  jmp     short loc_180002002
0x180001ff1  lea     r8d, [r9+1]
0x180001ff5  cmp     r8d, 2
0x180001ff9  jnz     short loc_180002002
0x180001ffb  lock inc cs:dword_18000A288
0x180002002  mov     eax, r8d
0x180002005  retn
```
