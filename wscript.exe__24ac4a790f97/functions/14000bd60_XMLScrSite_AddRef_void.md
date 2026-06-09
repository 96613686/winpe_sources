# XMLScrSite::AddRef(void)

- ea: `0x14000bd60`
- end: `0x14000bd6d`
- name: `?AddRef@XMLScrSite@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(XMLScrSite *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000bd80`
- `0x14000bd90`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRef(XMLScrSite *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x14000bd60  mov     eax, 1
0x14000bd65  lock xadd [rcx+18h], eax
0x14000bd6a  inc     eax
0x14000bd6c  retn
```
