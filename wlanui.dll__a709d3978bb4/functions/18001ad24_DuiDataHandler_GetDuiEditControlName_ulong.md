# DuiDataHandler::GetDuiEditControlName(ulong)

- ea: `0x18001ad24`
- end: `0x18001ad5c`
- name: `?GetDuiEditControlName@DuiDataHandler@@QEAAPEAGK@Z`
- size: `56`
- prototype: `unsigned __int16 *__fastcall(DuiDataHandler *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017394`
- `0x1800182a8`
- `0x180018668`
- `0x1800190c0`
- `0x180019284`
- `0x180019710`

## callees

- `0x18001ad24`

## pseudocode

```c
unsigned __int16 *__fastcall DuiDataHandler::GetDuiEditControlName(DuiDataHandler *this, unsigned int a2)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v2 && a2 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v2[1] - *v2) >> 3) )
    return *(unsigned __int16 **)(*v2 + 24LL * a2);
  else
    return 0;
}

```

## disassembly

```asm
0x18001ad24  mov     rcx, [rcx+8]
0x18001ad28  test    rcx, rcx
0x18001ad2b  jz      short loc_18001AD59
0x18001ad2d  mov     r8, [rcx]
0x18001ad30  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001ad3a  mov     rcx, [rcx+8]
0x18001ad3e  sub     rcx, r8
0x18001ad41  mov     edx, edx
0x18001ad43  sar     rcx, 3
0x18001ad47  imul    rcx, rax
0x18001ad4b  cmp     rdx, rcx
0x18001ad4e  jnb     short loc_18001AD59
0x18001ad50  lea     rax, [rdx+rdx*2]
0x18001ad54  mov     rax, [r8+rax*8]
0x18001ad58  retn
0x18001ad59  xor     eax, eax
0x18001ad5b  retn
```
