# utl::unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>::~unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>(void)

- ea: `0x1400151c8`
- end: `0x1400151e3`
- name: `??1?$unique_ptr@U_WER_REPORT_INFORMATION_V5@@U?$default_delete@U_WER_REPORT_INFORMATION_V5@@@utl@@@utl@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001cd7f`

## callees

- `0x140003224`
- `0x1400151c8`

## pseudocode

```c
void __fastcall utl::unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>::~unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x9C8);
}

```

## disassembly

```asm
0x1400151c8  sub     rsp, 28h
0x1400151cc  mov     rcx, [rcx]; void *
0x1400151cf  test    rcx, rcx
0x1400151d2  jz      short loc_1400151DE
0x1400151d4  mov     edx, 9C8h; struct std::nothrow_t *
0x1400151d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400151de  add     rsp, 28h
0x1400151e2  retn
```
