# SXWriter::endAttributesCheck(void)

- ea: `0x10040adb0`
- end: `0x10040adf5`
- name: `?endAttributesCheck@SXWriter@@AEAAXXZ`
- size: `69`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1004089c0`
- `0x1004098d0`
- `0x10040a5c0`
- `0x10040a660`
- `0x10040a700`
- `0x10040a7d0`
- `0x10040a980`
- `0x10040a9e0`
- `0x10040aee0`

## callees

- `0x1004086f0`
- `0x10040adb0`

## pseudocode

```c
void __fastcall SXWriter::endAttributesCheck(SXWriter *this)
{
  _BYTE *v2; // rax

  if ( *((_BYTE *)this + 256) )
  {
    v2 = (_BYTE *)*((_QWORD *)this + 38);
    if ( v2 == *((_BYTE **)this + 39) )
    {
      SXWriter::writeBuffer(this);
      v2 = (_BYTE *)*((_QWORD *)this + 38);
    }
    *v2 = -11;
    ++*((_QWORD *)this + 38);
    *((_BYTE *)this + 256) = 0;
  }
}

```

## disassembly

```asm
0x10040adb0  push    rbx
0x10040adb2  sub     rsp, 20h
0x10040adb6  cmp     byte ptr [rcx+100h], 0
0x10040adbd  mov     rbx, rcx
0x10040adc0  jz      short loc_10040ADEF
0x10040adc2  mov     rax, [rcx+130h]
0x10040adc9  cmp     rax, [rcx+138h]
0x10040add0  jnz     short loc_10040ADDE
0x10040add2  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040add7  mov     rax, [rbx+130h]
0x10040adde  mov     byte ptr [rax], 0F5h
0x10040ade1  inc     qword ptr [rbx+130h]
0x10040ade8  mov     byte ptr [rbx+100h], 0
0x10040adef  add     rsp, 20h
0x10040adf3  pop     rbx
0x10040adf4  retn
```
