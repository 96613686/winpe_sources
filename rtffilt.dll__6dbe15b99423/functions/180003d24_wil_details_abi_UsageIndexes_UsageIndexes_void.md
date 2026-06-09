# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180003d24`
- end: `0x180003de4`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004414`
- `0x180004f48`
- `0x180008810`
- `0x180009c80`

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
0x180003d24  mov     dword ptr [rcx], 40000h
0x180003d2a  xor     r8d, r8d
0x180003d2d  mov     byte ptr [rcx+4], 1
0x180003d31  mov     rax, rcx
0x180003d34  mov     [rcx+8], r8b
0x180003d38  mov     [rcx+38h], r8w
0x180003d3d  mov     [rcx+3Ah], r8b
0x180003d41  lea     edx, [r8+4]
0x180003d45  mov     [rcx+6], dx
0x180003d49  mov     [rcx+18h], r8
0x180003d4d  mov     [rcx+20h], r8
0x180003d51  mov     [rcx+28h], r8
0x180003d55  mov     [rcx+30h], r8
0x180003d59  mov     [rcx+10h], rdx
0x180003d5d  mov     dword ptr [rcx+40h], 40000h
0x180003d64  mov     byte ptr [rcx+44h], 1
0x180003d68  mov     [rcx+46h], dx
0x180003d6c  mov     byte ptr [rcx+48h], 2
0x180003d70  mov     [rcx+58h], r8
0x180003d74  mov     [rcx+60h], r8
0x180003d78  mov     [rcx+68h], r8
0x180003d7c  mov     [rcx+70h], r8
0x180003d80  mov     qword ptr [rcx+50h], 8
0x180003d88  mov     [rcx+78h], r8w
0x180003d8d  mov     [rcx+7Ah], r8b
0x180003d91  mov     dword ptr [rcx+80h], 40000h
0x180003d9b  mov     byte ptr [rcx+84h], 1
0x180003da2  mov     [rcx+86h], r8w
0x180003daa  mov     byte ptr [rcx+88h], 1
0x180003db1  mov     [rcx+98h], r8
0x180003db8  mov     [rcx+0A0h], r8
0x180003dbf  mov     [rcx+0A8h], r8
0x180003dc6  mov     [rcx+0B0h], r8
0x180003dcd  mov     [rcx+90h], r8
0x180003dd4  mov     [rcx+0B8h], r8w
0x180003ddc  mov     [rcx+0BAh], r8b
0x180003de3  retn
```
