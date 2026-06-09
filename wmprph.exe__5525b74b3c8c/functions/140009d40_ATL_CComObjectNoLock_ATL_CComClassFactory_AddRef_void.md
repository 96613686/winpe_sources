# ATL::CComObjectNoLock<ATL::CComClassFactory>::AddRef(void)

- ea: `0x140009d40`
- end: `0x140009d69`
- name: `?AddRef@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009d40`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::AddRef(__int64 a1)
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
0x140009d40  mov     r9d, 7FFFFFFFh
0x140009d46  jmp     short loc_140009D56
0x140009d48  lea     edx, [r8+1]
0x140009d4c  mov     eax, r8d
0x140009d4f  lock cmpxchg [rcx+8], edx
0x140009d54  jz      short loc_140009D61
0x140009d56  mov     r8d, [rcx+8]
0x140009d5a  cmp     r8d, r9d
0x140009d5d  jnz     short loc_140009D48
0x140009d5f  jmp     short loc_140009D65
0x140009d61  lea     r9d, [r8+1]
0x140009d65  mov     eax, r9d
0x140009d68  retn
```
