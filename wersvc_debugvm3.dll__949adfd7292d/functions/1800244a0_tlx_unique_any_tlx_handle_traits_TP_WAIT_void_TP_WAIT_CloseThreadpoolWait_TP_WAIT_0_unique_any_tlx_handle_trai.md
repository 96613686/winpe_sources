# tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>>(void)

- ea: `0x1800244a0`
- end: `0x1800244b7`
- name: `??1?$unique_any@U?$handle_traits@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800244a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800244ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800244ac`

## pseudocode

```c
void __fastcall tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>(
        struct _TP_WAIT **a1)
{
  struct _TP_WAIT *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolWait(v1);
}

```

## disassembly

```asm
0x1800244a0  sub     rsp, 28h
0x1800244a4  mov     rcx, [rcx]; pwa
0x1800244a7  test    rcx, rcx
0x1800244aa  jz      short loc_1800244B2
0x1800244ac  call    cs:__imp_CloseThreadpoolWait
0x1800244b2  add     rsp, 28h
0x1800244b6  retn
```
