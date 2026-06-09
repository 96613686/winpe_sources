# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1800032a0`
- end: `0x180003356`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `182`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035ac`
- `0x180003f2c`
- `0x180008c2c`
- `0x1800097c8`

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
0x1800032a0  mov     dword ptr [rcx], 40000h
0x1800032a6  xor     edx, edx
0x1800032a8  mov     byte ptr [rcx+4], 1
0x1800032ac  mov     [rcx+8], dl
0x1800032af  mov     [rcx+38h], dx
0x1800032b3  mov     [rcx+3Ah], dl
0x1800032b6  lea     eax, [rdx+4]
0x1800032b9  mov     [rcx+6], ax
0x1800032bd  mov     [rcx+10h], rax
0x1800032c1  mov     [rcx+18h], rdx
0x1800032c5  mov     [rcx+20h], rdx
0x1800032c9  mov     [rcx+28h], rdx
0x1800032cd  mov     [rcx+30h], rdx
0x1800032d1  mov     [rcx+46h], ax
0x1800032d5  mov     rax, rcx
0x1800032d8  mov     dword ptr [rcx+40h], 40000h
0x1800032df  mov     byte ptr [rcx+44h], 1
0x1800032e3  mov     byte ptr [rcx+48h], 2
0x1800032e7  mov     [rcx+58h], rdx
0x1800032eb  mov     [rcx+60h], rdx
0x1800032ef  mov     [rcx+68h], rdx
0x1800032f3  mov     [rcx+70h], rdx
0x1800032f7  mov     qword ptr [rcx+50h], 8
0x1800032ff  mov     [rcx+78h], dx
0x180003303  mov     [rcx+7Ah], dl
0x180003306  mov     dword ptr [rcx+80h], 40000h
0x180003310  mov     byte ptr [rcx+84h], 1
0x180003317  mov     [rcx+86h], dx
0x18000331e  mov     byte ptr [rcx+88h], 1
0x180003325  mov     [rcx+98h], rdx
0x18000332c  mov     [rcx+0A0h], rdx
0x180003333  mov     [rcx+0A8h], rdx
0x18000333a  mov     [rcx+0B0h], rdx
0x180003341  mov     [rcx+90h], rdx
0x180003348  mov     [rcx+0B8h], dx
0x18000334f  mov     [rcx+0BAh], dl
0x180003355  retn
```
