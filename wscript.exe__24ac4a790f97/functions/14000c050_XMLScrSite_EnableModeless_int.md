# XMLScrSite::EnableModeless(int)

- ea: `0x14000c050`
- end: `0x14000c061`
- name: `?EnableModeless@XMLScrSite@@UEAAJH@Z`
- size: `17`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall XMLScrSite::EnableModeless(XMLScrSite *this)
{
  return *(_BYTE *)(*((_QWORD *)this + 4) + 68LL) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x14000c050  mov     rax, [rcx+20h]
0x14000c054  mov     cl, [rax+44h]
0x14000c057  neg     cl
0x14000c059  sbb     eax, eax
0x14000c05b  and     eax, 80004005h
0x14000c060  retn
```
