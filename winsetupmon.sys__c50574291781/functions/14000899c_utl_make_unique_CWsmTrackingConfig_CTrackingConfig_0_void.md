# utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(void)

- ea: `0x14000899c`
- end: `0x140008a11`
- name: `??$make_unique@VCTrackingConfig@CWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@XZ`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140008a8c`
- `0x14000a728`

## callees

- `0x14000899c`
- `0x140009368`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(
        _QWORD *a1,
        const struct std::nothrow_t *a2)
{
  char *v3; // rax

  v3 = (char *)operator new(0x78u, a2);
  if ( v3 )
  {
    *(_QWORD *)v3 = &CWsmTrackingConfig::CTrackingConfig::`vftable';
    *((_QWORD *)v3 + 1) = -1;
    *((_QWORD *)v3 + 2) = -1;
    *((_QWORD *)v3 + 3) = -1;
    *((_QWORD *)v3 + 4) = -1;
    *((_QWORD *)v3 + 5) = -1;
    *((_QWORD *)v3 + 6) = -1;
    *((_QWORD *)v3 + 7) = &wsm_wstring::`vftable';
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 10) = 0;
    *((_QWORD *)v3 + 9) = &wsm_wstring::`vftable';
    *(_OWORD *)(v3 + 88) = 0;
    *(_OWORD *)(v3 + 104) = 0;
  }
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x14000899c  push    rbx
0x14000899e  sub     rsp, 20h
0x1400089a2  mov     rbx, rcx
0x1400089a5  mov     ecx, 78h ; 'x'; NumberOfBytes
0x1400089aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400089af  test    rax, rax
0x1400089b2  jz      short loc_140008A04
0x1400089b4  lea     rcx, ??_7CTrackingConfig@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingConfig::`vftable'
0x1400089bb  xorps   xmm0, xmm0
0x1400089be  mov     [rax], rcx
0x1400089c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400089c5  mov     [rax+8], rcx
0x1400089c9  mov     [rax+10h], rcx
0x1400089cd  mov     [rax+18h], rcx
0x1400089d1  mov     [rax+20h], rcx
0x1400089d5  mov     [rax+28h], rcx
0x1400089d9  mov     [rax+30h], rcx
0x1400089dd  lea     rcx, ??_7wsm_wstring@@6B@; const wsm_wstring::`vftable'
0x1400089e4  mov     [rax+38h], rcx
0x1400089e8  mov     qword ptr [rax+40h], 0
0x1400089f0  mov     qword ptr [rax+50h], 0
0x1400089f8  mov     [rax+48h], rcx
0x1400089fc  movups  xmmword ptr [rax+58h], xmm0
0x140008a00  movups  xmmword ptr [rax+68h], xmm0
0x140008a04  mov     [rbx], rax
0x140008a07  mov     rax, rbx
0x140008a0a  add     rsp, 20h
0x140008a0e  pop     rbx
0x140008a0f  retn
```
