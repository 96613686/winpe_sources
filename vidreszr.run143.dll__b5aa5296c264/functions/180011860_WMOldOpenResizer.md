# WMOldOpenResizer

- ea: `0x180011860`
- end: `0x180011926`
- name: `WMOldOpenResizer`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001974`
- `0x180011860`

## pseudocode

```c
__int64 __fastcall WMOldOpenResizer(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdx
  __int64 result; // rax

  v2 = operator new(0x310u);
  v3 = v2;
  if ( v2 )
  {
    v2[95] = 0;
    *v2 = &CMSMtoN::`vftable';
    *((_DWORD *)v2 + 194) = 0;
    *((_DWORD *)v2 + 30) = 0;
    *((_DWORD *)v2 + 176) = 1;
    v2[9] = 0;
    v2[10] = 0;
    v2[11] = 0;
    v2[12] = 0;
    v2[1] = 0;
    v2[3] = 0;
    v2[5] = 0;
    v2[7] = 0;
    v2[2] = 0;
    v2[4] = 0;
    v2[6] = 0;
    v2[8] = 0;
    *((_DWORD *)v2 + 183) = 2;
    v2[83] = 0;
    v2[82] = 0;
    v2[85] = 0;
    v2[84] = 0;
    *((_DWORD *)v2 + 162) = 0;
    *((_DWORD *)v2 + 33) = 0;
  }
  else
  {
    v3 = 0;
  }
  *a1 = v3;
  result = 2147942414LL;
  if ( v3 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180011860  push    rbx
0x180011862  sub     rsp, 20h
0x180011866  mov     rbx, rcx
0x180011869  mov     ecx, 310h; Size
0x18001186e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011873  xor     r8d, r8d
0x180011876  mov     rdx, rax
0x180011879  test    rax, rax
0x18001187c  jz      loc_18001190E
0x180011882  mov     [rdx+2F8h], r8
0x180011889  lea     rax, ??_7CMSMtoN@@6B@; const CMSMtoN::`vftable'
0x180011890  mov     [rdx], rax
0x180011893  mov     [rdx+308h], r8d
0x18001189a  mov     [rdx+78h], r8d
0x18001189e  mov     dword ptr [rdx+2C0h], 1
0x1800118a8  mov     [rdx+48h], r8
0x1800118ac  mov     [rdx+50h], r8
0x1800118b0  mov     [rdx+58h], r8
0x1800118b4  mov     [rdx+60h], r8
0x1800118b8  mov     [rdx+8], r8
0x1800118bc  mov     [rdx+18h], r8
0x1800118c0  mov     [rdx+28h], r8
0x1800118c4  mov     [rdx+38h], r8
0x1800118c8  mov     [rdx+10h], r8
0x1800118cc  mov     [rdx+20h], r8
0x1800118d0  mov     [rdx+30h], r8
0x1800118d4  mov     [rdx+40h], r8
0x1800118d8  mov     dword ptr [rdx+2DCh], 2
0x1800118e2  mov     [rdx+298h], r8
0x1800118e9  mov     [rdx+290h], r8
0x1800118f0  mov     [rdx+2A8h], r8
0x1800118f7  mov     [rdx+2A0h], r8
0x1800118fe  mov     [rdx+288h], r8d
0x180011905  mov     [rdx+84h], r8d
0x18001190c  jmp     short loc_180011911
0x18001190e  mov     rdx, r8
0x180011911  test    rdx, rdx
0x180011914  mov     [rbx], rdx
0x180011917  mov     eax, 8007000Eh
0x18001191c  cmovnz  eax, r8d
0x180011920  add     rsp, 20h
0x180011924  pop     rbx
0x180011925  retn
```
