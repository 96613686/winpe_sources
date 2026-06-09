# SdpStrCpy(ushort * *,ushort const *)

- ea: `0x140006050`
- end: `0x14000617a`
- name: `?SdpStrCpy@@YAJPEAPEAGPEBG@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400027a4`
- `0x1400055d8`
- `0x140005a50`

## callees

- `0x140001ed8`
- `0x140005964`
- `0x140006050`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14000614e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000614e`

## pseudocode

```c
__int64 __fastcall SdpStrCpy(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rdi
  unsigned int v4; // r8d
  __int64 v5; // rcx
  int v6; // r9d
  unsigned int v7; // ebx
  __int64 v8; // rbx
  unsigned __int64 v9; // rbx
  _WORD *v10; // rax
  void *v11; // rsi
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx

  v2 = a2;
  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 134;
      goto LABEL_3;
    }
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = v8 + 1;
    v10 = operator new[](saturated_mul(v9, 2u));
    v11 = v10;
    if ( !v10 )
    {
      v7 = -2147024882;
      v4 = 139;
      v6 = -2147024882;
      goto LABEL_4;
    }
    if ( v9 )
    {
      if ( v9 > 0x7FFFFFFF )
      {
        v12 = 2147942487LL;
        v13 = -2147024809;
        *v10 = 0;
        v7 = -2147024809;
LABEL_22:
        SdpDebugTrace(v12, (const char *)L"SdpStrCpy", 0x8Eu, v13);
        operator delete[](v11);
        return v7;
      }
      v14 = 2147483646;
      do
      {
        if ( !v14 )
          break;
        if ( !*v2 )
          break;
        *v10++ = *v2++;
        --v14;
        --v9;
      }
      while ( v9 );
      v12 = (__int64)(v10 - 1);
      if ( v9 )
        v12 = (__int64)v10;
      v13 = v9 == 0 ? 0x8007007A : 0;
      *(_WORD *)v12 = 0;
    }
    else
    {
      v12 = 2147942487LL;
      v13 = -2147024809;
    }
    v7 = v13;
    if ( v13 >= 0 )
    {
      *a1 = (unsigned __int16 *)v11;
      return v7;
    }
    goto LABEL_22;
  }
  v4 = 133;
LABEL_3:
  v5 = 2147942487LL;
  v6 = -2147024809;
  v7 = -2147024809;
LABEL_4:
  SdpDebugTrace(v5, (const char *)L"SdpStrCpy", v4, v6);
  return v7;
}

```

## disassembly

```asm
0x140006050  push    rbx
0x140006052  push    rbp
0x140006053  push    rsi
0x140006054  push    rdi
0x140006055  push    r14
0x140006057  sub     rsp, 20h
0x14000605b  xor     ebp, ebp
0x14000605d  mov     rdi, rdx
0x140006060  mov     r14, rcx
0x140006063  test    rcx, rcx
0x140006066  jnz     short loc_140006089
0x140006068  mov     r8d, 85h; int
0x14000606e  mov     ecx, 80070057h; unsigned int
0x140006073  mov     r9d, ecx; int
0x140006076  mov     ebx, ecx
0x140006078  lea     rdx, aSdpstrcpy; "SdpStrCpy"
0x14000607f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140006084  jmp     loc_14000616D
0x140006089  test    rdx, rdx
0x14000608c  jnz     short loc_140006096
0x14000608e  mov     r8d, 86h
0x140006094  jmp     short loc_14000606E
0x140006096  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000609a  mov     rbx, rcx
0x14000609d  inc     rbx
0x1400060a0  cmp     [rdx+rbx*2], bp
0x1400060a4  jnz     short loc_14000609D
0x1400060a6  inc     rbx
0x1400060a9  mov     eax, 2
0x1400060ae  mul     rbx
0x1400060b1  cmovb   rax, rcx
0x1400060b5  mov     rcx, rax; unsigned __int64
0x1400060b8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400060bd  mov     rsi, rax
0x1400060c0  test    rax, rax
0x1400060c3  jnz     short loc_1400060D5
0x1400060c5  mov     ebx, 8007000Eh
0x1400060ca  mov     r8d, 8Bh
0x1400060d0  mov     r9d, ebx
0x1400060d3  jmp     short loc_140006078
0x1400060d5  test    rbx, rbx
0x1400060d8  jz      short loc_140006156
0x1400060da  cmp     rbx, 7FFFFFFFh
0x1400060e1  jbe     short loc_1400060ED
0x1400060e3  mov     ecx, 80070057h
0x1400060e8  mov     r9d, ecx
0x1400060eb  jmp     short loc_140006163
0x1400060ed  mov     ecx, 7FFFFFFEh
0x1400060f2  test    rcx, rcx
0x1400060f5  jz      short loc_140006113
0x1400060f7  movzx   edx, word ptr [rdi]
0x1400060fa  test    dx, dx
0x1400060fd  jz      short loc_140006113
0x1400060ff  mov     [rax], dx
0x140006102  add     rdi, 2
0x140006106  add     rax, 2
0x14000610a  dec     rcx
0x14000610d  sub     rbx, 1
0x140006111  jnz     short loc_1400060F2
0x140006113  test    rbx, rbx
0x140006116  lea     rcx, [rax-2]
0x14000611a  cmovnz  rcx, rax; unsigned int
0x14000611e  neg     rbx
0x140006121  sbb     r9d, r9d
0x140006124  not     r9d
0x140006127  and     r9d, 8007007Ah; int
0x14000612e  mov     [rcx], bp
0x140006131  mov     ebx, r9d
0x140006134  test    r9d, r9d
0x140006137  jns     short loc_14000616A
0x140006139  mov     r8d, 8Eh; int
0x14000613f  lea     rdx, aSdpstrcpy; "SdpStrCpy"
0x140006146  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x14000614b  mov     rcx, rsi
0x14000614e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140006154  jmp     short loc_14000616D
0x140006156  mov     ecx, 80070057h
0x14000615b  mov     r9d, ecx
0x14000615e  test    rbx, rbx
0x140006161  jz      short loc_140006131
0x140006163  mov     [rax], bp
0x140006166  mov     ebx, ecx
0x140006168  jmp     short loc_140006139
0x14000616a  mov     [r14], rsi
0x14000616d  mov     eax, ebx
0x14000616f  add     rsp, 20h
0x140006173  pop     r14
0x140006175  pop     rdi
0x140006176  pop     rsi
0x140006177  pop     rbp
0x140006178  pop     rbx
0x140006179  retn
```
