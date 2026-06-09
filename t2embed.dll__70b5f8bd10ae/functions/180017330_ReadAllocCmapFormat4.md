# ReadAllocCmapFormat4

- ea: `0x180017330`
- end: `0x180017479`
- name: `ReadAllocCmapFormat4`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f298`

## callees

- `0x1800132ac`
- `0x180015190`
- `0x180017330`
- `0x180017480`
- `0x18001a6c4`
- `0x18001ce6c`
- `0x18001d224`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7,
        _WORD *a8)
{
  unsigned int CmapSubtable; // eax
  unsigned int v10; // r14d
  __int64 result; // rax
  unsigned int v12; // r14d
  unsigned __int16 v13; // r15
  unsigned __int16 AllocCmapFormat4Ids; // di
  _WORD v15[2]; // [rsp+40h] [rbp-18h] BYREF
  int v16; // [rsp+44h] [rbp-14h] BYREF
  int v17; // [rsp+48h] [rbp-10h] BYREF
  __int16 v18; // [rsp+4Ch] [rbp-Ch]

  v18 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  v15[0] = 0;
  v16 = 0;
  v17 = 0;
  CmapSubtable = FindCmapSubtable(a1, a2, a3, a4);
  v10 = CmapSubtable;
  if ( !CmapSubtable )
    return 1006;
  result = ReadCmapLength(a1, &v17, CmapSubtable, v15);
  if ( (_WORD)result )
    return result;
  if ( (_WORD)v17 != 4 )
    return 1006;
  result = ReadGeneric(a1, a5, 0xEu, (unsigned __int8 *)&CMAP_FORMAT4_CONTROL, v10, v15);
  if ( !(_WORD)result )
  {
    v12 = v15[0] + v10;
    v13 = *(_WORD *)(a5 + 6) >> 1;
    result = ReadAllocCmapFormat4Segs((_DWORD)a1, v13, (_DWORD)a6, v12, (__int64)&v16);
    if ( !(_WORD)result )
    {
      if ( v16
        && (AllocCmapFormat4Ids = ReadAllocCmapFormat4Ids(
                                    (_DWORD)a1,
                                    v13,
                                    *a6,
                                    (_DWORD)a7,
                                    (__int64)a8,
                                    v12 + v16,
                                    (__int64)&v16)) != 0 )
      {
        FreeCmapFormat4(*a6, *a7);
        result = AllocCmapFormat4Ids;
        *a6 = 0;
        *a7 = 0;
        *a8 = 0;
      }
      else
      {
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017330  push    rbp
0x180017332  push    rbx
0x180017333  push    rsi
0x180017334  push    rdi
0x180017335  push    r12
0x180017337  push    r13
0x180017339  push    r14
0x18001733b  push    r15
0x18001733d  mov     rbp, rsp
0x180017340  sub     rsp, 58h
0x180017344  mov     rbx, [rbp+arg_28]
0x180017348  xor     r13d, r13d
0x18001734b  mov     rsi, [rbp+arg_30]
0x18001734f  xor     eax, eax
0x180017351  mov     r12, [rbp+arg_38]
0x180017358  mov     rdi, rcx
0x18001735b  mov     dword ptr [rbp+var_E], eax
0x18001735e  mov     [rbx], r13
0x180017361  mov     [rsi], r13
0x180017364  mov     [r12], r13w
0x180017369  mov     [rbp+var_18], r13w
0x18001736e  mov     [rbp+var_14], r13d
0x180017372  mov     [rbp-10h], eax
0x180017375  call    FindCmapSubtable
0x18001737a  mov     r14d, eax
0x18001737d  test    eax, eax
0x18001737f  jz      loc_180017463
0x180017385  lea     r9, [rbp+var_18]
0x180017389  mov     r8d, eax
0x18001738c  lea     rdx, [rbp+var_10]
0x180017390  mov     rcx, rdi
0x180017393  call    ReadCmapLength
0x180017398  test    ax, ax
0x18001739b  jnz     loc_180017468
0x1800173a1  cmp     [rbp+var_10], 4
0x1800173a6  jnz     loc_180017463
0x1800173ac  mov     r15, [rbp+arg_20]
0x1800173b0  lea     rax, [rbp+var_18]
0x1800173b4  mov     [rsp+58h+var_30], rax
0x1800173b9  lea     r8d, [r13+0Eh]
0x1800173bd  mov     rdx, r15
0x1800173c0  mov     dword ptr [rsp+58h+var_38], r14d
0x1800173c5  lea     r9, CMAP_FORMAT4_CONTROL
0x1800173cc  mov     rcx, rdi
0x1800173cf  call    ReadGeneric
0x1800173d4  test    ax, ax
0x1800173d7  jnz     loc_180017468
0x1800173dd  movzx   r15d, word ptr [r15+6]
0x1800173e2  mov     r8, rbx
0x1800173e5  movzx   eax, [rbp+var_18]
0x1800173e9  mov     rcx, rdi
0x1800173ec  add     r14d, eax
0x1800173ef  shr     r15w, 1
0x1800173f3  lea     rax, [rbp+var_14]
0x1800173f7  mov     r9d, r14d
0x1800173fa  movzx   edx, r15w
0x1800173fe  mov     [rsp+58h+var_38], rax
0x180017403  call    ReadAllocCmapFormat4Segs
0x180017408  test    ax, ax
0x18001740b  jnz     short loc_180017468
0x18001740d  mov     eax, [rbp+var_14]
0x180017410  test    eax, eax
0x180017412  jz      short loc_18001745E
0x180017414  mov     r8, [rbx]
0x180017417  lea     rcx, [rbp+var_14]
0x18001741b  mov     [rsp+58h+var_28], rcx
0x180017420  add     eax, r14d
0x180017423  mov     dword ptr [rsp+58h+var_30], eax
0x180017427  mov     rcx, rdi
0x18001742a  mov     r9, rsi
0x18001742d  mov     [rsp+58h+var_38], r12
0x180017432  movzx   edx, r15w
0x180017436  call    ReadAllocCmapFormat4Ids
0x18001743b  movzx   edi, ax
0x18001743e  test    ax, ax
0x180017441  jz      short loc_18001745E
0x180017443  mov     rdx, [rsi]
0x180017446  mov     rcx, [rbx]
0x180017449  call    FreeCmapFormat4
0x18001744e  movzx   eax, di
0x180017451  mov     [rbx], r13
0x180017454  mov     [rsi], r13
0x180017457  mov     [r12], r13w
0x18001745c  jmp     short loc_180017468
0x18001745e  mov     eax, r13d
0x180017461  jmp     short loc_180017468
0x180017463  mov     eax, 3EEh
0x180017468  add     rsp, 58h
0x18001746c  pop     r15
0x18001746e  pop     r14
0x180017470  pop     r13
0x180017472  pop     r12
0x180017474  pop     rdi
0x180017475  pop     rsi
0x180017476  pop     rbx
0x180017477  pop     rbp
0x180017478  retn
```
