# CreateDoConnectMsgForWin32

- ea: `0x18000e6b4`
- end: `0x18000e91f`
- name: `CreateDoConnectMsgForWin32`
- size: `619`
- prototype: `__int64 __fastcall(char *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ff10`

## callees

- `0x18000e6b4`
- `0x18000fa90`
- `0x1800138c5`

## pseudocode

```c
__int64 __fastcall CreateDoConnectMsgForWin32(char *a1, unsigned __int8 *a2)
{
  _WORD *v4; // rdx
  int v5; // ecx
  __int64 v6; // r11
  __int64 result; // rax

  memset_0(a1, 0, 0x140u);
  v4 = a2 + 194;
  if ( !a2[6]
    || (v5 = 1, *v4 == 1)
    && gHRes == *((_WORD *)a2 + 94)
    && gVRes == *((_WORD *)a2 + 95)
    && gColorDepth == *((_WORD *)a2 + 96) )
  {
    v5 = 0;
  }
  *((_DWORD *)a1 + 70) = v5;
  *((_DWORD *)a1 + 1) = a2[1];
  *((_QWORD *)a1 + 5) = *((_QWORD *)a2 + 4);
  *((_DWORD *)a1 + 5) = *((_DWORD *)a2 + 57);
  *((_DWORD *)a1 + 6) = *((_DWORD *)a2 + 58);
  *((_QWORD *)a1 + 4) = *((_QWORD *)a2 + 1);
  *((_QWORD *)a1 + 6) = *((_QWORD *)a2 + 2);
  *((_DWORD *)a1 + 61) = a2[197];
  *((_QWORD *)a1 + 7) = *((_QWORD *)a2 + 3);
  *((_QWORD *)a1 + 8) = *((_QWORD *)a2 + 6);
  *((_DWORD *)a1 + 60) = a2[196];
  *((_QWORD *)a1 + 9) = *((_QWORD *)a2 + 7);
  *((_DWORD *)a1 + 67) = *((_DWORD *)a2 + 50);
  *((_DWORD *)a1 + 68) = *((_DWORD *)a2 + 51);
  *((_DWORD *)a1 + 69) = *((_DWORD *)a2 + 52);
  *((_OWORD *)a1 + 5) = G_WinStationName;
  *((_OWORD *)a1 + 6) = xmmword_18001D9F0;
  *((_OWORD *)a1 + 7) = xmmword_18001DA00;
  *((_OWORD *)a1 + 8) = xmmword_18001DA10;
  *((_WORD *)a1 + 132) = *v4;
  *((_DWORD *)a1 + 64) = *((unsigned __int16 *)a2 + 95);
  *((_DWORD *)a1 + 63) = *((unsigned __int16 *)a2 + 94);
  *((_DWORD *)a1 + 62) = *((unsigned __int16 *)a2 + 96);
  *((_DWORD *)a1 + 71) = *((_DWORD *)a2 + 69);
  *((_DWORD *)a1 + 72) = *((_DWORD *)a2 + 70);
  *((_DWORD *)a1 + 73) = *((_DWORD *)a2 + 71);
  *((_QWORD *)a1 + 37) = *((_QWORD *)a2 + 36);
  *((_QWORD *)a1 + 38) = *((_QWORD *)a2 + 137);
  *((_DWORD *)a1 + 78) = *((_DWORD *)a2 + 276);
  StringCopyNoNull(a1 + 144, 18, a2 + 134, 18);
  StringCopyNoNull(a1 + 162, 40, a2 + 236, 40);
  StringCopyNoNull(a1 + 202, 18, a2 + 152, 18);
  StringCopyNoNull(a1 + 220, 20, a2 + 170, 18);
  StringCopyNoNull(a1 + 202, 18, a2 + 152, 18);
  result = StringCopyNoNull(a1 + 220, 20, v6, 18);
  *(_DWORD *)a1 = *a2;
  return result;
}

```

## disassembly

```asm
0x18000e6b4  push    rbx
0x18000e6b6  push    rbp
0x18000e6b7  push    rsi
0x18000e6b8  push    rdi
0x18000e6b9  push    r12
0x18000e6bb  push    r14
0x18000e6bd  sub     rsp, 28h
0x18000e6c1  mov     rbp, rdx
0x18000e6c4  mov     r8d, 140h; Size
0x18000e6ca  xor     edx, edx; Val
0x18000e6cc  mov     r14, rcx
0x18000e6cf  call    memset_0
0x18000e6d4  cmp     byte ptr [rbp+6], 0
0x18000e6d8  lea     rdx, [rbp+0C2h]
0x18000e6df  jz      short loc_18000E71B
0x18000e6e1  mov     ecx, 1
0x18000e6e6  cmp     [rdx], cx
0x18000e6e9  jnz     short loc_18000E71D
0x18000e6eb  movzx   eax, word ptr [rbp+0BCh]
0x18000e6f2  cmp     cs:gHRes, ax
0x18000e6f9  jnz     short loc_18000E71D
0x18000e6fb  movzx   eax, word ptr [rbp+0BEh]
0x18000e702  cmp     cs:gVRes, ax
0x18000e709  jnz     short loc_18000E71D
0x18000e70b  movzx   eax, word ptr [rbp+0C0h]
0x18000e712  cmp     cs:gColorDepth, ax
0x18000e719  jnz     short loc_18000E71D
0x18000e71b  xor     ecx, ecx
0x18000e71d  mov     [r14+118h], ecx
0x18000e724  lea     r8, [rbp+86h]
0x18000e72b  movzx   eax, byte ptr [rbp+1]
0x18000e72f  lea     rcx, [r14+90h]
0x18000e736  mov     [r14+4], eax
0x18000e73a  mov     r12d, 12h
0x18000e740  mov     rax, [rbp+20h]
0x18000e744  mov     r9d, r12d
0x18000e747  mov     [r14+28h], rax
0x18000e74b  mov     eax, [rbp+0E4h]
0x18000e751  mov     [r14+14h], eax
0x18000e755  mov     eax, [rbp+0E8h]
0x18000e75b  mov     [r14+18h], eax
0x18000e75f  mov     rax, [rbp+8]
0x18000e763  mov     [r14+20h], rax
0x18000e767  mov     rax, [rbp+10h]
0x18000e76b  mov     [r14+30h], rax
0x18000e76f  movzx   eax, byte ptr [rbp+0C5h]
0x18000e776  mov     [r14+0F4h], eax
0x18000e77d  mov     rax, [rbp+18h]
0x18000e781  mov     [r14+38h], rax
0x18000e785  mov     rax, [rbp+30h]
0x18000e789  mov     [r14+40h], rax
0x18000e78d  movzx   eax, byte ptr [rbp+0C4h]
0x18000e794  mov     [r14+0F0h], eax
0x18000e79b  mov     rax, [rbp+38h]
0x18000e79f  mov     [r14+48h], rax
0x18000e7a3  mov     eax, [rbp+0C8h]
0x18000e7a9  mov     [r14+10Ch], eax
0x18000e7b0  mov     eax, [rbp+0CCh]
0x18000e7b6  mov     [r14+110h], eax
0x18000e7bd  mov     eax, [rbp+0D0h]
0x18000e7c3  mov     [r14+114h], eax
0x18000e7ca  movups  xmm0, cs:G_WinStationName
0x18000e7d1  movups  xmmword ptr [r14+50h], xmm0
0x18000e7d6  movups  xmm1, cs:xmmword_18001D9F0
0x18000e7dd  movups  xmmword ptr [r14+60h], xmm1
0x18000e7e2  movups  xmm0, cs:xmmword_18001DA00
0x18000e7e9  movups  xmmword ptr [r14+70h], xmm0
0x18000e7ee  movups  xmm1, cs:xmmword_18001DA10
0x18000e7f5  movups  xmmword ptr [r14+80h], xmm1
0x18000e7fd  movzx   eax, word ptr [rdx]
0x18000e800  mov     edx, r12d
0x18000e803  mov     [r14+108h], ax
0x18000e80b  movzx   eax, word ptr [rbp+0BEh]
0x18000e812  mov     [r14+100h], eax
0x18000e819  movzx   eax, word ptr [rbp+0BCh]
0x18000e820  mov     [r14+0FCh], eax
0x18000e827  movzx   eax, word ptr [rbp+0C0h]
0x18000e82e  mov     [r14+0F8h], eax
0x18000e835  mov     eax, [rbp+114h]
0x18000e83b  mov     [r14+11Ch], eax
0x18000e842  mov     eax, [rbp+118h]
0x18000e848  mov     [r14+120h], eax
0x18000e84f  mov     eax, [rbp+11Ch]
0x18000e855  mov     [r14+124h], eax
0x18000e85c  mov     rax, [rbp+120h]
0x18000e863  mov     [r14+128h], rax
0x18000e86a  mov     rax, [rbp+448h]
0x18000e871  mov     [r14+130h], rax
0x18000e878  mov     eax, [rbp+450h]
0x18000e87e  mov     [r14+138h], eax
0x18000e885  call    StringCopyNoNull
0x18000e88a  lea     edx, [r12+16h]
0x18000e88f  mov     r9d, edx
0x18000e892  lea     r8, [rbp+0ECh]
0x18000e899  lea     rcx, [r14+0A2h]
0x18000e8a0  call    StringCopyNoNull
0x18000e8a5  lea     rdi, [rbp+98h]
0x18000e8ac  mov     r9d, r12d
0x18000e8af  lea     rsi, [r14+0CAh]
0x18000e8b6  mov     r8, rdi
0x18000e8b9  mov     rcx, rsi
0x18000e8bc  mov     edx, r12d
0x18000e8bf  call    StringCopyNoNull
0x18000e8c4  lea     r11, [rbp+0AAh]
0x18000e8cb  mov     r9d, r12d
0x18000e8ce  lea     rbx, [r14+0DCh]
0x18000e8d5  mov     r8, r11
0x18000e8d8  mov     rcx, rbx
0x18000e8db  lea     edx, [r12+2]
0x18000e8e0  call    StringCopyNoNull
0x18000e8e5  mov     r9d, r12d
0x18000e8e8  mov     r8, rdi
0x18000e8eb  mov     edx, r12d
0x18000e8ee  mov     rcx, rsi
0x18000e8f1  call    StringCopyNoNull
0x18000e8f6  mov     r9d, r12d
0x18000e8f9  lea     edx, [r12+2]
0x18000e8fe  mov     r8, r11
0x18000e901  mov     rcx, rbx
0x18000e904  call    StringCopyNoNull
0x18000e909  movzx   r11d, byte ptr [rbp+0]
0x18000e90e  mov     [r14], r11d
0x18000e911  add     rsp, 28h
0x18000e915  pop     r14
0x18000e917  pop     r12
0x18000e919  pop     rdi
0x18000e91a  pop     rsi
0x18000e91b  pop     rbp
0x18000e91c  pop     rbx
0x18000e91d  retn
```
