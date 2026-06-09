# ATL::CComObjectNoLock<ATL::CComClassFactory>::AddRef(void)

- ea: `0x140003aa0`
- end: `0x140003ac9`
- name: `?AddRef@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003aa0`

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
0x140003aa0  mov     r9d, 7FFFFFFFh
0x140003aa6  jmp     short loc_140003AB6
0x140003aa8  lea     edx, [r8+1]
0x140003aac  mov     eax, r8d
0x140003aaf  lock cmpxchg [rcx+8], edx
0x140003ab4  jz      short loc_140003AC1
0x140003ab6  mov     r8d, [rcx+8]
0x140003aba  cmp     r8d, r9d
0x140003abd  jnz     short loc_140003AA8
0x140003abf  jmp     short loc_140003AC5
0x140003ac1  lea     r9d, [r8+1]
0x140003ac5  mov     eax, r9d
0x140003ac8  retn
```
