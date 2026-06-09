# mmioWrite

- ea: `0x1800085a0`
- end: `0x180008797`
- name: `mmioWrite`
- size: `503`
- prototype: `LONG __stdcall(HMMIO hmmio, const char *pch, LONG cch)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e550`
- `0x18000e660`

## callees

- `0x180007560`
- `0x1800085a0`
- `0x180009300`
- `0x18000e4e8`
- `0x180011bcc`
- `0x1800207bc`
- `0x180021010`

## pseudocode

```c
LONG __stdcall mmioWrite(HMMIO hmmio, const char *pch, LONG cch)
{
  LONG v6; // r14d
  LONG v7; // esi
  bool v8; // cc
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  LONG v11; // ebx
  int v12; // eax
  int v14; // ebx
  __int64 v15; // rax

  if ( !(unsigned int)ValidateHandle(hmmio, 5) || !pch )
    return -1;
  v6 = 0;
  while ( 1 )
  {
    v7 = *((_DWORD *)hmmio + 14) - *((_DWORD *)hmmio + 10);
    v8 = v7 <= cch;
    if ( v7 < cch )
    {
      if ( *((_DWORD *)hmmio + 1) == 541934925 )
      {
        if ( (unsigned int)mmioExpandMemFile(hmmio, (unsigned int)(cch - v7)) )
          return -1;
        v7 = *((_DWORD *)hmmio + 14) - *((_DWORD *)hmmio + 10);
      }
      v8 = v7 <= cch;
    }
    if ( !v8 )
      v7 = cch;
    if ( v7 > 0 )
    {
      memcpy_0(*((void **)hmmio + 5), pch, v7);
      *(_DWORD *)hmmio |= 0x10000000u;
      pch += v7;
      *((_QWORD *)hmmio + 5) += v7;
      cch -= v7;
      v6 += v7;
    }
    v9 = *((_QWORD *)hmmio + 5);
    if ( *((_QWORD *)hmmio + 6) < v9 )
      *((_QWORD *)hmmio + 6) = v9;
    if ( !cch )
      return v6;
    if ( cch > *((_DWORD *)hmmio + 7) )
      break;
    if ( !(unsigned int)ValidateHandle(hmmio, 5) || !*((_QWORD *)hmmio + 4) )
      return -1;
    if ( *((_DWORD *)hmmio + 1) == 541934925 )
    {
      if ( (unsigned int)(*((_DWORD *)hmmio + 14) - *((_DWORD *)hmmio + 10)) >= *((_DWORD *)hmmio + 18)
        || (unsigned int)mmioExpandMemFile(hmmio, 1) )
      {
        return -1;
      }
    }
    else if ( mmioFlush(hmmio, 0x10u) )
    {
      return -1;
    }
  }
  if ( !(unsigned int)ValidateHandle(hmmio, 5) )
    return -1;
  if ( *((_DWORD *)hmmio + 1) != 541934925 )
  {
    v10 = *((_QWORD *)hmmio + 4);
    if ( v10 )
    {
      if ( (*(_DWORD *)hmmio & 0x10000000) != 0 )
      {
        v14 = *((_DWORD *)hmmio + 12) - *((_DWORD *)hmmio + 8);
        if ( (unsigned int)mmioDiskIO((__int64)hmmio, 5u, v10, v14) != v14 )
          return -1;
        *(_DWORD *)hmmio &= ~0x10000000u;
      }
      *((_DWORD *)hmmio + 16) += *((_DWORD *)hmmio + 10) - *((_DWORD *)hmmio + 8);
      v15 = *((_QWORD *)hmmio + 4);
      *((_QWORD *)hmmio + 6) = v15;
      *((_QWORD *)hmmio + 5) = v15;
    }
  }
  v11 = -1;
  if ( *((_DWORD *)hmmio + 17) == *((_DWORD *)hmmio + 16)
    || (*((__int64 (__fastcall **)(HMMIO, __int64, _QWORD))hmmio + 1))(hmmio, 2, *((int *)hmmio + 16)) != -1 )
  {
    v12 = (*((__int64 (__fastcall **)(HMMIO, __int64, const char *, _QWORD))hmmio + 1))(hmmio, 1, pch, cch);
  }
  else
  {
    v12 = -1;
  }
  hmmio[16] = hmmio[17];
  if ( v12 != -1 )
    return v12 + v6;
  return v11;
}

```

## disassembly

```asm
0x1800085a0  push    rbx
0x1800085a2  push    rbp
0x1800085a3  push    rsi
0x1800085a4  push    rdi
0x1800085a5  push    r14
0x1800085a7  push    r15
0x1800085a9  sub     rsp, 38h
0x1800085ad  mov     r15, rdx
0x1800085b0  mov     ebp, r8d
0x1800085b3  mov     edx, 5
0x1800085b8  mov     rdi, rcx
0x1800085bb  call    ValidateHandle
0x1800085c0  test    eax, eax
0x1800085c2  jz      loc_1800086DB
0x1800085c8  test    r15, r15
0x1800085cb  jz      loc_1800086DB
0x1800085d1  xor     r14d, r14d
0x1800085d4  mov     esi, [rdi+38h]
0x1800085d7  sub     esi, [rdi+28h]
0x1800085da  cmp     esi, ebp
0x1800085dc  jge     short loc_1800085ED
0x1800085de  cmp     dword ptr [rdi+4], 204D454Dh
0x1800085e5  jz      loc_1800086E1
0x1800085eb  cmp     esi, ebp
0x1800085ed  cmovg   esi, ebp
0x1800085f0  test    esi, esi
0x1800085f2  jg      loc_1800086FC
0x1800085f8  mov     rax, [rdi+28h]
0x1800085fc  cmp     [rdi+30h], rax
0x180008600  jb      loc_180008723
0x180008606  test    ebp, ebp
0x180008608  jz      loc_18000878F
0x18000860e  mov     edx, 5
0x180008613  mov     rcx, rdi
0x180008616  cmp     ebp, [rdi+1Ch]
0x180008619  jle     loc_1800086A2
0x18000861f  call    ValidateHandle
0x180008624  test    eax, eax
0x180008626  jz      loc_1800086DB
0x18000862c  cmp     dword ptr [rdi+4], 204D454Dh
0x180008633  jz      short loc_180008642
0x180008635  mov     r8, [rdi+20h]
0x180008639  test    r8, r8
0x18000863c  jnz     loc_180008742
0x180008642  movsxd  rax, dword ptr [rdi+40h]
0x180008646  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000864a  cmp     [rdi+44h], eax
0x18000864d  jnz     short loc_180008683
0x18000864f  mov     rax, [rdi+8]
0x180008653  mov     r8, r15
0x180008656  movsxd  r9, ebp
0x180008659  mov     edx, 1
0x18000865e  mov     rcx, rdi
0x180008661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008666  mov     ecx, [rdi+44h]
0x180008669  mov     [rdi+40h], ecx
0x18000866c  cmp     eax, ebx
0x18000866e  jnz     loc_180008786
0x180008674  mov     eax, ebx
0x180008676  add     rsp, 38h
0x18000867a  pop     r15
0x18000867c  pop     r14
0x18000867e  pop     rdi
0x18000867f  pop     rsi
0x180008680  pop     rbp
0x180008681  pop     rbx
0x180008682  retn
0x180008683  xor     r9d, r9d
0x180008686  mov     r8, rax
0x180008689  mov     rax, [rdi+8]
0x18000868d  mov     rcx, rdi
0x180008690  lea     edx, [r9+2]
0x180008694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008699  cmp     rax, rbx
0x18000869c  jnz     short loc_18000864F
0x18000869e  mov     eax, ebx
0x1800086a0  jmp     short loc_180008666
0x1800086a2  call    ValidateHandle
0x1800086a7  test    eax, eax
0x1800086a9  jz      short loc_1800086DB
0x1800086ab  cmp     qword ptr [rdi+20h], 0
0x1800086b0  jz      short loc_1800086DB
0x1800086b2  cmp     dword ptr [rdi+4], 204D454Dh
0x1800086b9  jnz     short loc_18000872C
0x1800086bb  mov     eax, [rdi+38h]
0x1800086be  sub     eax, [rdi+28h]
0x1800086c1  cmp     eax, [rdi+48h]
0x1800086c4  jnb     short loc_1800086DB
0x1800086c6  mov     edx, 1
0x1800086cb  mov     rcx, rdi
0x1800086ce  call    mmioExpandMemFile
0x1800086d3  test    eax, eax
0x1800086d5  jz      loc_1800085D4
0x1800086db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800086df  jmp     short loc_180008676
0x1800086e1  mov     edx, ebp
0x1800086e3  mov     rcx, rdi
0x1800086e6  sub     edx, esi
0x1800086e8  call    mmioExpandMemFile
0x1800086ed  test    eax, eax
0x1800086ef  jnz     short loc_1800086DB
0x1800086f1  mov     esi, [rdi+38h]
0x1800086f4  sub     esi, [rdi+28h]
0x1800086f7  jmp     loc_1800085EB
0x1800086fc  mov     rcx, [rdi+28h]; void *
0x180008700  mov     rdx, r15; Src
0x180008703  movsxd  rbx, esi
0x180008706  mov     r8, rbx; Size
0x180008709  call    memcpy_0
0x18000870e  bts     dword ptr [rdi], 1Ch
0x180008712  add     r15, rbx
0x180008715  add     [rdi+28h], rbx
0x180008719  sub     ebp, esi
0x18000871b  add     r14d, esi
0x18000871e  jmp     loc_1800085F8
0x180008723  mov     [rdi+30h], rax
0x180008727  jmp     loc_180008606
0x18000872c  mov     edx, 10h; fuFlush
0x180008731  mov     rcx, rdi; hmmio
0x180008734  call    mmioFlush
0x180008739  test    eax, eax
0x18000873b  jnz     short loc_1800086DB
0x18000873d  jmp     loc_1800085D4
0x180008742  test    dword ptr [rdi], 10000000h
0x180008748  jz      short loc_18000876C
0x18000874a  mov     ebx, [rdi+30h]
0x18000874d  mov     edx, 5
0x180008752  sub     ebx, [rdi+20h]
0x180008755  mov     rcx, rdi
0x180008758  mov     r9d, ebx
0x18000875b  call    mmioDiskIO
0x180008760  cmp     eax, ebx
0x180008762  jnz     loc_1800086DB
0x180008768  btr     dword ptr [rdi], 1Ch
0x18000876c  mov     eax, [rdi+28h]
0x18000876f  sub     eax, [rdi+20h]
0x180008772  add     [rdi+40h], eax
0x180008775  mov     rax, [rdi+20h]
0x180008779  mov     [rdi+30h], rax
0x18000877d  mov     [rdi+28h], rax
0x180008781  jmp     loc_180008642
0x180008786  lea     ebx, [rax+r14]
0x18000878a  jmp     loc_180008674
0x18000878f  mov     eax, r14d
0x180008792  jmp     loc_180008676
```
