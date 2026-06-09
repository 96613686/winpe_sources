# utl::make_unique<CWsmLogConfig,,0>(void)

- ea: `0x140008a18`
- end: `0x140008a83`
- name: `??$make_unique@VCWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmLogConfig@@U?$default_delete@VCWsmLogConfig@@@utl@@@0@XZ`
- size: `107`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001a94`
- `0x14000a4b0`
- `0x14000a680`
- `0x14000bb50`

## callees

- `0x14000894c`
- `0x140008a18`
- `0x140009368`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<CWsmLogConfig,,0>(_QWORD *a1, const struct std::nothrow_t *a2)
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
    *v3 = &CWsmLogConfig::`vftable'{for `IWsmStableLogConfig'};
    v3[1] = &CWsmLogConfig::`vftable'{for `IWsmLogConfig'};
    utl::make_unique<CWsmLogConfig::CLogConfig,,0>(v3 + 5);
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
0x140008a18  mov     [rsp+arg_0], rbx
0x140008a1d  push    rdi
0x140008a1e  sub     rsp, 20h
0x140008a22  mov     rdi, rcx
0x140008a25  mov     ecx, 30h ; '0'; NumberOfBytes
0x140008a2a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140008a2f  mov     rbx, rax
0x140008a32  test    rax, rax
0x140008a35  jz      short loc_140008A6F
0x140008a37  mov     qword ptr [rax+28h], 0
0x140008a3f  lea     rcx, [rbx+28h]
0x140008a43  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008a47  mov     [rbx+10h], rax
0x140008a4b  mov     [rbx+18h], rax
0x140008a4f  mov     [rbx+20h], rax
0x140008a53  lea     rax, ??_7CWsmLogConfig@@6BIWsmStableLogConfig@@@; const CWsmLogConfig::`vftable'{for `IWsmStableLogConfig'}
0x140008a5a  mov     [rbx], rax
0x140008a5d  lea     rax, ??_7CWsmLogConfig@@6BIWsmLogConfig@@@; const CWsmLogConfig::`vftable'{for `IWsmLogConfig'}
0x140008a64  mov     [rbx+8], rax
0x140008a68  call    ??$make_unique@VCLogConfig@CWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCLogConfig@CWsmLogConfig@@U?$default_delete@VCLogConfig@CWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig::CLogConfig,,0>(void)
0x140008a6d  jmp     short loc_140008A71
0x140008a6f  xor     ebx, ebx
0x140008a71  mov     [rdi], rbx
0x140008a74  mov     rax, rdi
0x140008a77  mov     rbx, [rsp+28h+arg_0]
0x140008a7c  add     rsp, 20h
0x140008a80  pop     rdi
0x140008a81  retn
```
