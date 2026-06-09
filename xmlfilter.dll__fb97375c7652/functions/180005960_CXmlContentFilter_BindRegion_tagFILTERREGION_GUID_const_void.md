# CXmlContentFilter::BindRegion(tagFILTERREGION,_GUID const &,void * *)

- ea: `0x180005960`
- end: `0x180005966`
- name: `?BindRegion@CXmlContentFilter@@UEAAJUtagFILTERREGION@@AEBU_GUID@@PEAPEAX@Z`
- size: `6`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, struct tagFILTERREGION *__struct_ptr, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::BindRegion(
        CXmlContentFilter *this,
        struct tagFILTERREGION *a2,
        const struct _GUID *a3,
        void **a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180005960  mov     eax, 80004001h
0x180005965  retn
```
