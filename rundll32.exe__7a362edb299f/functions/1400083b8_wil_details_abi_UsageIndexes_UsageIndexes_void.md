# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1400083b8`
- end: `0x140008478`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140008574`
- `0x14000897c`
- `0x1400097cc`
- `0x14000a168`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this)
{
  wil::details_abi::UsageIndexes *result; // rax

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  result = this;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 28) = 0;
  *((_BYTE *)this + 58) = 0;
  *((_WORD *)this + 3) = 4;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = 4;
  *((_DWORD *)this + 16) = 0x40000;
  *((_BYTE *)this + 68) = 1;
  *((_WORD *)this + 35) = 4;
  *((_BYTE *)this + 72) = 2;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = 8;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 122) = 0;
  *((_DWORD *)this + 32) = 0x40000;
  *((_BYTE *)this + 132) = 1;
  *((_WORD *)this + 67) = 0;
  *((_BYTE *)this + 136) = 1;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_WORD *)this + 92) = 0;
  *((_BYTE *)this + 186) = 0;
  return result;
}

```

## disassembly

```asm
0x1400083b8  mov     dword ptr [rcx], 40000h
0x1400083be  xor     r8d, r8d
0x1400083c1  mov     byte ptr [rcx+4], 1
0x1400083c5  mov     rax, rcx
0x1400083c8  mov     [rcx+8], r8b
0x1400083cc  mov     [rcx+38h], r8w
0x1400083d1  mov     [rcx+3Ah], r8b
0x1400083d5  lea     edx, [r8+4]
0x1400083d9  mov     [rcx+6], dx
0x1400083dd  mov     [rcx+18h], r8
0x1400083e1  mov     [rcx+20h], r8
0x1400083e5  mov     [rcx+28h], r8
0x1400083e9  mov     [rcx+30h], r8
0x1400083ed  mov     [rcx+10h], rdx
0x1400083f1  mov     dword ptr [rcx+40h], 40000h
0x1400083f8  mov     byte ptr [rcx+44h], 1
0x1400083fc  mov     [rcx+46h], dx
0x140008400  mov     byte ptr [rcx+48h], 2
0x140008404  mov     [rcx+58h], r8
0x140008408  mov     [rcx+60h], r8
0x14000840c  mov     [rcx+68h], r8
0x140008410  mov     [rcx+70h], r8
0x140008414  mov     qword ptr [rcx+50h], 8
0x14000841c  mov     [rcx+78h], r8w
0x140008421  mov     [rcx+7Ah], r8b
0x140008425  mov     dword ptr [rcx+80h], 40000h
0x14000842f  mov     byte ptr [rcx+84h], 1
0x140008436  mov     [rcx+86h], r8w
0x14000843e  mov     byte ptr [rcx+88h], 1
0x140008445  mov     [rcx+98h], r8
0x14000844c  mov     [rcx+0A0h], r8
0x140008453  mov     [rcx+0A8h], r8
0x14000845a  mov     [rcx+0B0h], r8
0x140008461  mov     [rcx+90h], r8
0x140008468  mov     [rcx+0B8h], r8w
0x140008470  mov     [rcx+0BAh], r8b
0x140008477  retn
```
