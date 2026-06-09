# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180006f88`
- end: `0x18000703e`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `182`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007384`
- `0x180007d44`
- `0x18000ba34`
- `0x18000c620`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this)
{
  wil::details_abi::UsageIndexes *result; // rax

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 28) = 0;
  *((_BYTE *)this + 58) = 0;
  *((_WORD *)this + 3) = 4;
  *((_QWORD *)this + 2) = 4;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 35) = 4;
  result = this;
  *((_DWORD *)this + 16) = 0x40000;
  *((_BYTE *)this + 68) = 1;
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
0x180006f88  mov     dword ptr [rcx], 40000h
0x180006f8e  xor     edx, edx
0x180006f90  mov     byte ptr [rcx+4], 1
0x180006f94  mov     [rcx+8], dl
0x180006f97  mov     [rcx+38h], dx
0x180006f9b  mov     [rcx+3Ah], dl
0x180006f9e  lea     eax, [rdx+4]
0x180006fa1  mov     [rcx+6], ax
0x180006fa5  mov     [rcx+10h], rax
0x180006fa9  mov     [rcx+18h], rdx
0x180006fad  mov     [rcx+20h], rdx
0x180006fb1  mov     [rcx+28h], rdx
0x180006fb5  mov     [rcx+30h], rdx
0x180006fb9  mov     [rcx+46h], ax
0x180006fbd  mov     rax, rcx
0x180006fc0  mov     dword ptr [rcx+40h], 40000h
0x180006fc7  mov     byte ptr [rcx+44h], 1
0x180006fcb  mov     byte ptr [rcx+48h], 2
0x180006fcf  mov     [rcx+58h], rdx
0x180006fd3  mov     [rcx+60h], rdx
0x180006fd7  mov     [rcx+68h], rdx
0x180006fdb  mov     [rcx+70h], rdx
0x180006fdf  mov     qword ptr [rcx+50h], 8
0x180006fe7  mov     [rcx+78h], dx
0x180006feb  mov     [rcx+7Ah], dl
0x180006fee  mov     dword ptr [rcx+80h], 40000h
0x180006ff8  mov     byte ptr [rcx+84h], 1
0x180006fff  mov     [rcx+86h], dx
0x180007006  mov     byte ptr [rcx+88h], 1
0x18000700d  mov     [rcx+98h], rdx
0x180007014  mov     [rcx+0A0h], rdx
0x18000701b  mov     [rcx+0A8h], rdx
0x180007022  mov     [rcx+0B0h], rdx
0x180007029  mov     [rcx+90h], rdx
0x180007030  mov     [rcx+0B8h], dx
0x180007037  mov     [rcx+0BAh], dl
0x18000703d  retn
```
