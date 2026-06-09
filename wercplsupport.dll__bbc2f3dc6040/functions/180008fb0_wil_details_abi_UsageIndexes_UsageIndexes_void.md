# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180008fb0`
- end: `0x180009070`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000934c`
- `0x180009f58`
- `0x18000ccc0`
- `0x18000d784`

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
0x180008fb0  mov     dword ptr [rcx], 40000h
0x180008fb6  xor     r8d, r8d
0x180008fb9  mov     byte ptr [rcx+4], 1
0x180008fbd  mov     rax, rcx
0x180008fc0  mov     [rcx+8], r8b
0x180008fc4  mov     [rcx+38h], r8w
0x180008fc9  mov     [rcx+3Ah], r8b
0x180008fcd  lea     edx, [r8+4]
0x180008fd1  mov     [rcx+6], dx
0x180008fd5  mov     [rcx+18h], r8
0x180008fd9  mov     [rcx+20h], r8
0x180008fdd  mov     [rcx+28h], r8
0x180008fe1  mov     [rcx+30h], r8
0x180008fe5  mov     [rcx+10h], rdx
0x180008fe9  mov     dword ptr [rcx+40h], 40000h
0x180008ff0  mov     byte ptr [rcx+44h], 1
0x180008ff4  mov     [rcx+46h], dx
0x180008ff8  mov     byte ptr [rcx+48h], 2
0x180008ffc  mov     [rcx+58h], r8
0x180009000  mov     [rcx+60h], r8
0x180009004  mov     [rcx+68h], r8
0x180009008  mov     [rcx+70h], r8
0x18000900c  mov     qword ptr [rcx+50h], 8
0x180009014  mov     [rcx+78h], r8w
0x180009019  mov     [rcx+7Ah], r8b
0x18000901d  mov     dword ptr [rcx+80h], 40000h
0x180009027  mov     byte ptr [rcx+84h], 1
0x18000902e  mov     [rcx+86h], r8w
0x180009036  mov     byte ptr [rcx+88h], 1
0x18000903d  mov     [rcx+98h], r8
0x180009044  mov     [rcx+0A0h], r8
0x18000904b  mov     [rcx+0A8h], r8
0x180009052  mov     [rcx+0B0h], r8
0x180009059  mov     [rcx+90h], r8
0x180009060  mov     [rcx+0B8h], r8w
0x180009068  mov     [rcx+0BAh], r8b
0x18000906f  retn
```
