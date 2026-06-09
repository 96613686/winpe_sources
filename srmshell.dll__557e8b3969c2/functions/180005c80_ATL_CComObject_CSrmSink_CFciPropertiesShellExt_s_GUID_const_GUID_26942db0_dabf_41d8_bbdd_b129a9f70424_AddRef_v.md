# ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::AddRef(void)

- ea: `0x180005c80`
- end: `0x180005ca9`
- name: `?AddRef@?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c80`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::AddRef(
        __int64 a1)
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
0x180005c80  mov     r9d, 7FFFFFFFh
0x180005c86  jmp     short loc_180005C96
0x180005c88  lea     edx, [r8+1]
0x180005c8c  mov     eax, r8d
0x180005c8f  lock cmpxchg [rcx+8], edx
0x180005c94  jz      short loc_180005CA1
0x180005c96  mov     r8d, [rcx+8]
0x180005c9a  cmp     r8d, r9d
0x180005c9d  jnz     short loc_180005C88
0x180005c9f  jmp     short loc_180005CA5
0x180005ca1  lea     r9d, [r8+1]
0x180005ca5  mov     eax, r9d
0x180005ca8  retn
```
