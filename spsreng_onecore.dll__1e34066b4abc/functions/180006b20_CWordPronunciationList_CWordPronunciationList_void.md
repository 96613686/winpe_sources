# CWordPronunciationList::~CWordPronunciationList(void)

- ea: `0x180006b20`
- end: `0x180006b38`
- name: `??1CWordPronunciationList@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(CWordPronunciationList *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cbd8`
- `0x18000d830`
- `0x18001c398`
- `0x1800db250`
- `0x1800ffc45`
- `0x1800ffc8d`
- `0x1800ffe98`
- `0x180100c01`

## callees

- `0x180006b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b2d`

## pseudocode

```c
void __fastcall CWordPronunciationList::~CWordPronunciationList(CWordPronunciationList *this)
{
  void *v1; // rcx

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180006b20  sub     rsp, 28h
0x180006b24  mov     rcx, [rcx+8]; pv
0x180006b28  test    rcx, rcx
0x180006b2b  jz      short loc_180006B33
0x180006b2d  call    cs:__imp_CoTaskMemFree
0x180006b33  add     rsp, 28h
0x180006b37  retn
```
