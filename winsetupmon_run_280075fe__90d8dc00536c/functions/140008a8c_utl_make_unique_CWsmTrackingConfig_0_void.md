# utl::make_unique<CWsmTrackingConfig,,0>(void)

- ea: `0x140008a8c`
- end: `0x140008af7`
- name: `??$make_unique@VCWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmTrackingConfig@@U?$default_delete@VCWsmTrackingConfig@@@utl@@@0@XZ`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001a94`
- `0x14000a598`

## callees

- `0x14000899c`
- `0x140008a8c`
- `0x140009368`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<CWsmTrackingConfig,,0>(_QWORD *a1, const struct std::nothrow_t *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx

  v3 = operator new(0x30u, a2);
  v4 = v3;
  if ( v3 )
  {
    v3[5] = 0;
    v3[2] = -1;
    v3[3] = -1;
    v3[4] = -1;
    *v3 = &CWsmTrackingConfig::`vftable'{for `IWsmStableTrackingConfig'};
    v3[1] = &CWsmTrackingConfig::`vftable'{for `IWsmTrackingConfig'};
    utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(v3 + 5);
  }
  else
  {
    v4 = 0;
  }
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x140008a8c  mov     [rsp+arg_0], rbx
0x140008a91  push    rdi
0x140008a92  sub     rsp, 20h
0x140008a96  mov     rdi, rcx
0x140008a99  mov     ecx, 30h ; '0'; NumberOfBytes
0x140008a9e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140008aa3  mov     rbx, rax
0x140008aa6  test    rax, rax
0x140008aa9  jz      short loc_140008AE3
0x140008aab  mov     qword ptr [rax+28h], 0
0x140008ab3  lea     rcx, [rbx+28h]
0x140008ab7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008abb  mov     [rbx+10h], rax
0x140008abf  mov     [rbx+18h], rax
0x140008ac3  mov     [rbx+20h], rax
0x140008ac7  lea     rax, ??_7CWsmTrackingConfig@@6BIWsmStableTrackingConfig@@@; const CWsmTrackingConfig::`vftable'{for `IWsmStableTrackingConfig'}
0x140008ace  mov     [rbx], rax
0x140008ad1  lea     rax, ??_7CWsmTrackingConfig@@6BIWsmTrackingConfig@@@; const CWsmTrackingConfig::`vftable'{for `IWsmTrackingConfig'}
0x140008ad8  mov     [rbx+8], rax
0x140008adc  call    ??$make_unique@VCTrackingConfig@CWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@XZ; utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(void)
0x140008ae1  jmp     short loc_140008AE5
0x140008ae3  xor     ebx, ebx
0x140008ae5  mov     [rdi], rbx
0x140008ae8  mov     rax, rdi
0x140008aeb  mov     rbx, [rsp+28h+arg_0]
0x140008af0  add     rsp, 20h
0x140008af4  pop     rdi
0x140008af5  retn
```
