# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180034390`
- end: `0x1800343bd`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002deec`
- `0x18002dfdc`
- `0x18002e298`
- `0x180037f28`
- `0x18003a160`

## callees

- `0x180034390`
- `0x180036264`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180034390  cmp     rdx, 1000h
0x180034397  jb      short loc_1800343B1
0x180034399  mov     rax, [rcx-8]
0x18003439d  sub     rcx, rax
0x1800343a0  sub     rcx, 8
0x1800343a4  cmp     rcx, 1Fh
0x1800343a8  ja      short loc_1800343B6
0x1800343aa  add     rdx, 27h ; '''; unsigned __int64
0x1800343ae  mov     rcx, rax; void *
0x1800343b1  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800343b6  mov     ecx, 5
0x1800343bb  int     29h; Win8: RtlFailFast(ecx)
```
