# XMLScrSite::QueryContinue(void)

- ea: `0x14000c4c0`
- end: `0x14000c4d5`
- name: `?QueryContinue@XMLScrSite@@UEAAJXZ`
- size: `21`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall XMLScrSite::QueryContinue(XMLScrSite *this)
{
  return _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)this + 3) + 40LL), 0, 0) < 0;
}

```

## disassembly

```asm
0x14000c4c0  mov     rdx, [rcx+18h]
0x14000c4c4  xor     ecx, ecx
0x14000c4c6  xor     eax, eax
0x14000c4c8  lock cmpxchg [rdx+28h], ecx
0x14000c4cd  test    eax, eax
0x14000c4cf  sets    cl
0x14000c4d2  mov     eax, ecx
0x14000c4d4  retn
```
