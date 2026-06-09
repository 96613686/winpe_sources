# WiaTrace::InitThreadData(void)

- ea: `0x1800022b0`
- end: `0x1800022f1`
- name: `?InitThreadData@WiaTrace@@YAXXZ`
- size: `65`
- prototype: `void __fastcall(WiaTrace *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023e4`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x1800022bc`
- `KERNEL32!TlsSetValue` at `0x1800022ca`
- `KERNEL32!TlsSetValue` at `0x1800022d8`
- `KERNEL32!TlsSetValue` at `0x1800022bc`
- `KERNEL32!TlsSetValue` at `0x1800022ca`
- `KERNEL32!TlsSetValue` at `0x1800022d8`
- `KERNEL32!TlsSetValue` at `0x1800022ea`

## pseudocode

```c
void __fastcall WiaTrace::InitThreadData(WiaTrace *this)
{
  TlsSetValue(WiaTrace::g_tls_idx_ulTraceMask, 0);
  TlsSetValue(WiaTrace::g_tls_idx_ulTraceLevel, 0);
  TlsSetValue(WiaTrace::g_tls_idx_ulIndentLevel, 0);
  TlsSetValue(WiaTrace::g_tls_idx_bActivated, 0);
}

```

## disassembly

```asm
0x1800022b0  sub     rsp, 28h
0x1800022b4  mov     ecx, cs:?g_tls_idx_ulTraceMask@WiaTrace@@3KA; dwTlsIndex
0x1800022ba  xor     edx, edx; lpTlsValue
0x1800022bc  call    cs:__imp_TlsSetValue
0x1800022c2  mov     ecx, cs:?g_tls_idx_ulTraceLevel@WiaTrace@@3KA; dwTlsIndex
0x1800022c8  xor     edx, edx; lpTlsValue
0x1800022ca  call    cs:__imp_TlsSetValue
0x1800022d0  mov     ecx, cs:?g_tls_idx_ulIndentLevel@WiaTrace@@3KA; dwTlsIndex
0x1800022d6  xor     edx, edx; lpTlsValue
0x1800022d8  call    cs:__imp_TlsSetValue
0x1800022de  mov     ecx, cs:?g_tls_idx_bActivated@WiaTrace@@3KA; ulong WiaTrace::g_tls_idx_bActivated
0x1800022e4  xor     edx, edx
0x1800022e6  add     rsp, 28h
0x1800022ea  jmp     cs:__imp_TlsSetValue
```
