# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180034940`
- end: `0x18003496d`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002e20c`
- `0x18002e2fc`
- `0x18002e5c8`
- `0x18003855c`
- `0x18003a8ac`

## callees

- `0x180034940`
- `0x180036834`

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
0x180034940  cmp     rdx, 1000h
0x180034947  jb      short loc_180034961
0x180034949  mov     rax, [rcx-8]
0x18003494d  sub     rcx, rax
0x180034950  sub     rcx, 8
0x180034954  cmp     rcx, 1Fh
0x180034958  ja      short loc_180034966
0x18003495a  add     rdx, 27h ; '''; unsigned __int64
0x18003495e  mov     rcx, rax; void *
0x180034961  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180034966  mov     ecx, 5
0x18003496b  int     29h; Win8: RtlFailFast(ecx)
```
