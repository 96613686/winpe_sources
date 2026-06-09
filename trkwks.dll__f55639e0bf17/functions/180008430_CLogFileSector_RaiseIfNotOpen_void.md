# CLogFileSector::RaiseIfNotOpen(void)

- ea: `0x180008430`
- end: `0x180008452`
- name: `?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ`
- size: `34`
- prototype: `void __fastcall(CLogFileSector *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bf0`
- `0x180007cb0`
- `0x180007f90`
- `0x180008230`
- `0x18000833c`
- `0x180008384`
- `0x180008460`
- `0x1800087c0`
- `0x180008960`
- `0x180008d10`
- `0x18000d68c`

## callees

- `0x180008430`
- `0x18000d038`

## pseudocode

```c
void __fastcall CLogFileSector::RaiseIfNotOpen(CLogFileSector *this)
{
  if ( !*((_QWORD *)this + 4) || !*((_QWORD *)this + 1) )
    TrkRaiseWin32Error(110);
}

```

## disassembly

```asm
0x180008430  sub     rsp, 28h
0x180008434  cmp     qword ptr [rcx+20h], 0
0x180008439  jz      short loc_180008442
0x18000843b  cmp     qword ptr [rcx+8], 0
0x180008440  jnz     short loc_18000844D
0x180008442  mov     ecx, 6Eh ; 'n'; int
0x180008447  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000844d  add     rsp, 28h
0x180008451  retn
```
