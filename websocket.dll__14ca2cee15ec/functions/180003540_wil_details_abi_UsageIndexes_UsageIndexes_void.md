# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180003540`
- end: `0x180003600`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003914`
- `0x1800041f0`
- `0x180006f20`
- `0x1800079d0`

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
0x180003540  mov     dword ptr [rcx], 40000h
0x180003546  xor     r8d, r8d
0x180003549  mov     byte ptr [rcx+4], 1
0x18000354d  mov     rax, rcx
0x180003550  mov     [rcx+8], r8b
0x180003554  mov     [rcx+38h], r8w
0x180003559  mov     [rcx+3Ah], r8b
0x18000355d  lea     edx, [r8+4]
0x180003561  mov     [rcx+6], dx
0x180003565  mov     [rcx+18h], r8
0x180003569  mov     [rcx+20h], r8
0x18000356d  mov     [rcx+28h], r8
0x180003571  mov     [rcx+30h], r8
0x180003575  mov     [rcx+10h], rdx
0x180003579  mov     dword ptr [rcx+40h], 40000h
0x180003580  mov     byte ptr [rcx+44h], 1
0x180003584  mov     [rcx+46h], dx
0x180003588  mov     byte ptr [rcx+48h], 2
0x18000358c  mov     [rcx+58h], r8
0x180003590  mov     [rcx+60h], r8
0x180003594  mov     [rcx+68h], r8
0x180003598  mov     [rcx+70h], r8
0x18000359c  mov     qword ptr [rcx+50h], 8
0x1800035a4  mov     [rcx+78h], r8w
0x1800035a9  mov     [rcx+7Ah], r8b
0x1800035ad  mov     dword ptr [rcx+80h], 40000h
0x1800035b7  mov     byte ptr [rcx+84h], 1
0x1800035be  mov     [rcx+86h], r8w
0x1800035c6  mov     byte ptr [rcx+88h], 1
0x1800035cd  mov     [rcx+98h], r8
0x1800035d4  mov     [rcx+0A0h], r8
0x1800035db  mov     [rcx+0A8h], r8
0x1800035e2  mov     [rcx+0B0h], r8
0x1800035e9  mov     [rcx+90h], r8
0x1800035f0  mov     [rcx+0B8h], r8w
0x1800035f8  mov     [rcx+0BAh], r8b
0x1800035ff  retn
```
