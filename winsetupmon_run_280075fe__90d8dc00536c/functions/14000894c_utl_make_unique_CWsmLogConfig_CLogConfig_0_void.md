# utl::make_unique<CWsmLogConfig::CLogConfig,,0>(void)

- ea: `0x14000894c`
- end: `0x140008995`
- name: `??$make_unique@VCLogConfig@CWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCLogConfig@CWsmLogConfig@@U?$default_delete@VCLogConfig@CWsmLogConfig@@@utl@@@0@XZ`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140008a18`
- `0x14000b064`

## callees

- `0x14000894c`
- `0x140009368`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<CWsmLogConfig::CLogConfig,,0>(_QWORD *a1, const struct std::nothrow_t *a2)
{
  char *v3; // rax

  v3 = (char *)operator new(0x28u, a2);
  if ( v3 )
  {
    *(_QWORD *)v3 = &CWsmLogConfig::CLogConfig::`vftable';
    *(_OWORD *)(v3 + 8) = 0;
    *((_QWORD *)v3 + 3) = &wsm_stable_path::`vftable';
    *((_QWORD *)v3 + 4) = 0;
  }
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x14000894c  push    rbx
0x14000894e  sub     rsp, 20h
0x140008952  mov     rbx, rcx
0x140008955  mov     ecx, 28h ; '('; NumberOfBytes
0x14000895a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000895f  test    rax, rax
0x140008962  jz      short loc_140008988
0x140008964  lea     rcx, ??_7CLogConfig@CWsmLogConfig@@6B@; const CWsmLogConfig::CLogConfig::`vftable'
0x14000896b  xorps   xmm0, xmm0
0x14000896e  mov     [rax], rcx
0x140008971  lea     rcx, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x140008978  movups  xmmword ptr [rax+8], xmm0
0x14000897c  mov     [rax+18h], rcx
0x140008980  mov     qword ptr [rax+20h], 0
0x140008988  mov     [rbx], rax
0x14000898b  mov     rax, rbx
0x14000898e  add     rsp, 20h
0x140008992  pop     rbx
0x140008993  retn
```
