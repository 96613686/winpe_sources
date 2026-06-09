# utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)

- ea: `0x1400046cc`
- end: `0x140004703`
- name: `??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z`
- size: `55`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c798`
- `0x14001bb34`

## callees

- `0x140003254`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique_for_overwrite<wchar_t [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rax

  v3 = 2 * a2;
  if ( !is_mul_ok(a2, 2u) )
    v3 = -1;
  *a1 = operator new[](v3, (const struct std::nothrow_t *)&std::nothrow);
  return a1;
}

```

## disassembly

```asm
0x1400046cc  push    rbx
0x1400046ce  sub     rsp, 20h
0x1400046d2  mov     rbx, rcx
0x1400046d5  mov     eax, 2
0x1400046da  mul     rdx
0x1400046dd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400046e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400046eb  cmovb   rax, rcx
0x1400046ef  mov     rcx, rax; unsigned __int64
0x1400046f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400046f7  mov     [rbx], rax
0x1400046fa  mov     rax, rbx
0x1400046fd  add     rsp, 20h
0x140004701  pop     rbx
0x140004702  retn
```
