# CXmlContentFilter::IsDirty(void)

- ea: `0x180011c20`
- end: `0x180011c35`
- name: `?IsDirty@CXmlContentFilter@@UEAAJXZ`
- size: `21`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180011c40`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::IsDirty(CXmlContentFilter *this)
{
  return *((_BYTE *)this + 512) != 0 ? 1 : -2147215600;
}

```

## disassembly

```asm
0x180011c20  mov     al, [rcx+200h]
0x180011c26  neg     al
0x180011c28  sbb     eax, eax
0x180011c2a  and     eax, 7FFBE8F1h
0x180011c2f  add     eax, 80041710h
0x180011c34  retn
```
