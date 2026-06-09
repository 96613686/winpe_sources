# CLogFileHeader::RaiseIfNotOpen(void)

- ea: `0x18000cfd0`
- end: `0x18000cff2`
- name: `?RaiseIfNotOpen@CLogFileHeader@@AEBAXXZ`
- size: `34`
- prototype: `void __fastcall(CLogFileHeader *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b50`
- `0x1800033b0`
- `0x180007f90`
- `0x180009ce8`
- `0x18000c3d4`
- `0x18000cd40`
- `0x18000cf34`
- `0x18000cf58`
- `0x18000e784`
- `0x18000eac0`
- `0x18000edb0`

## callees

- `0x18000cfd0`
- `0x18000d038`

## pseudocode

```c
void __fastcall CLogFileHeader::RaiseIfNotOpen(CLogFileHeader *this)
{
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 1) )
    TrkRaiseWin32Error(110);
}

```

## disassembly

```asm
0x18000cfd0  sub     rsp, 28h
0x18000cfd4  cmp     qword ptr [rcx+10h], 0
0x18000cfd9  jz      short loc_18000CFE7
0x18000cfdb  cmp     qword ptr [rcx+8], 0
0x18000cfe0  jz      short loc_18000CFE7
0x18000cfe2  add     rsp, 28h
0x18000cfe6  retn
0x18000cfe7  mov     ecx, 6Eh ; 'n'; int
0x18000cfec  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
