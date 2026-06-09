# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180009a4c`
- end: `0x180009b02`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `182`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180009cb8`
- `0x18000a5fc`
- `0x18000d70c`
- `0x18000e7dc`

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
0x180009a4c  mov     dword ptr [rcx], 40000h
0x180009a52  xor     edx, edx
0x180009a54  mov     byte ptr [rcx+4], 1
0x180009a58  mov     [rcx+8], dl
0x180009a5b  mov     [rcx+38h], dx
0x180009a5f  mov     [rcx+3Ah], dl
0x180009a62  lea     eax, [rdx+4]
0x180009a65  mov     [rcx+6], ax
0x180009a69  mov     [rcx+10h], rax
0x180009a6d  mov     [rcx+18h], rdx
0x180009a71  mov     [rcx+20h], rdx
0x180009a75  mov     [rcx+28h], rdx
0x180009a79  mov     [rcx+30h], rdx
0x180009a7d  mov     [rcx+46h], ax
0x180009a81  mov     rax, rcx
0x180009a84  mov     dword ptr [rcx+40h], 40000h
0x180009a8b  mov     byte ptr [rcx+44h], 1
0x180009a8f  mov     byte ptr [rcx+48h], 2
0x180009a93  mov     [rcx+58h], rdx
0x180009a97  mov     [rcx+60h], rdx
0x180009a9b  mov     [rcx+68h], rdx
0x180009a9f  mov     [rcx+70h], rdx
0x180009aa3  mov     qword ptr [rcx+50h], 8
0x180009aab  mov     [rcx+78h], dx
0x180009aaf  mov     [rcx+7Ah], dl
0x180009ab2  mov     dword ptr [rcx+80h], 40000h
0x180009abc  mov     byte ptr [rcx+84h], 1
0x180009ac3  mov     [rcx+86h], dx
0x180009aca  mov     byte ptr [rcx+88h], 1
0x180009ad1  mov     [rcx+98h], rdx
0x180009ad8  mov     [rcx+0A0h], rdx
0x180009adf  mov     [rcx+0A8h], rdx
0x180009ae6  mov     [rcx+0B0h], rdx
0x180009aed  mov     [rcx+90h], rdx
0x180009af4  mov     [rcx+0B8h], dx
0x180009afb  mov     [rcx+0BAh], dl
0x180009b01  retn
```
