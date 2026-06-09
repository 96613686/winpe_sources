# ReadGeneric

- ea: `0x180015190`
- end: `0x1800153c9`
- name: `ReadGeneric`
- size: `569`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee80`
- `0x180010018`
- `0x18001009c`
- `0x1800106c8`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800120bc`
- `0x1800121e4`
- `0x180012a18`
- `0x180013514`
- `0x18001357c`
- `0x180013b44`
- `0x180013dac`
- `0x180013ea8`
- `0x18001400c`
- `0x180014cd4`
- `0x180014f98`
- `0x1800153d0`
- `0x1800156e8`
- `0x180016770`
- `0x180016f54`
- `0x180017330`
- `0x180017480`
- `0x1800190a4`
- `0x18001a874`
- `0x18001d5f8`
- `0x180027c1c`
- `0x180027d28`
- `0x1800281d0`
- `0x180028388`
- `0x180028c2c`
- `0x180029228`
- `0x1800297f8`
- `0x180029d3c`
- `0x180029ea4`
- `0x180029f48`

## callees

- `0x180015190`
- `0x18001cd3c`

## pseudocode

```c
__int64 __fastcall ReadGeneric(
        __int64 *a1,
        __int64 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        _WORD *a6)
{
  unsigned __int16 v6; // r13
  unsigned __int16 v7; // bx
  unsigned __int64 v8; // rdi
  __int64 *v11; // r11
  __int64 v12; // r8
  unsigned __int16 v13; // r10
  unsigned __int8 v14; // dl
  int v15; // eax
  __int64 v16; // rcx
  bool v17; // zf
  unsigned int v18; // edx
  __int64 result; // rax
  int v20; // eax
  unsigned int v21; // edx
  __int64 v22; // rax
  int v23; // r12d
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // r12
  int v28; // r8d

  v6 = *a4;
  v7 = 1;
  v8 = a3;
  v11 = a1;
  v12 = a5;
  v13 = 0;
  while ( v7 <= v6 )
  {
    v14 = a4[v7];
    v15 = v14 & 7;
    if ( v15 == 2 )
    {
      if ( (unsigned __int64)v13 + 2 > v8 )
        return 1003;
      if ( (v14 & 0x10) != 0 )
      {
        v26 = 0;
      }
      else
      {
        v16 = *v11;
        if ( !*v11 )
          return 1001;
        v17 = (v14 & 0x20) == 0;
        v18 = v12 + 2;
        if ( v17 )
        {
          if ( v18 < (unsigned int)v12 || v18 > *((_DWORD *)v11 + 2) )
            return 1001;
          v27 = _byteswap_ushort(*(_WORD *)((unsigned int)v12 + v16));
        }
        else
        {
          if ( v18 < (unsigned int)v12 || v18 > *((_DWORD *)v11 + 2) )
            return 1001;
          v27 = *(_WORD *)((unsigned int)v12 + v16);
        }
        v26 = v27;
        v12 = v18;
      }
      *(_WORD *)(v13 + a2) = v26;
      ++v7;
      v13 += 2;
    }
    else
    {
      v20 = v15 - 1;
      if ( v20 )
      {
        if ( v20 != 3 || (unsigned __int64)v13 + 4 > v8 )
          return 1003;
        if ( (v14 & 0x10) != 0 )
        {
          v23 = 0;
        }
        else if ( (v14 & 0x20) != 0 )
        {
          if ( !*v11 )
            return 1001;
          v24 = v12 + 4;
          if ( (int)v12 + 4 < (unsigned int)v12 || v24 > *((_DWORD *)v11 + 2) )
            return 1001;
          v25 = (unsigned int)v12;
          v12 = v24;
          v23 = *(_DWORD *)(v25 + *v11);
        }
        else
        {
          if ( !*v11 )
            return 1001;
          v21 = v12 + 4;
          if ( (int)v12 + 4 < (unsigned int)v12 || v21 > *((_DWORD *)v11 + 2) )
            return 1001;
          v22 = (unsigned int)v12;
          v12 = v21;
          v23 = *(unsigned __int8 *)(v22 + *v11 + 3)
              | ((*(unsigned __int8 *)(v22 + *v11 + 2)
                | (((*(unsigned __int8 *)(v22 + *v11) << 8) | *(unsigned __int8 *)(v22 + *v11 + 1)) << 8)) << 8);
        }
        *(_DWORD *)(v13 + a2) = v23;
        ++v7;
        v13 += 4;
      }
      else
      {
        if ( (unsigned __int64)v13 + 1 > v8 )
          return 1003;
        if ( (v14 & 0x10) != 0 )
        {
          *(_BYTE *)(v13 + a2) = 0;
        }
        else
        {
          result = ReadByte(v11, v13 + a2, v12);
          if ( (_WORD)result )
            return result;
          v12 = (unsigned int)(v28 + 1);
        }
        ++v7;
        ++v13;
      }
    }
  }
  if ( v13 >= (unsigned __int16)v8 )
  {
    *a6 = v12 - a5;
    return 0;
  }
  return 1003;
}

```

## disassembly

```asm
0x180015190  push    rbx
0x180015192  push    rbp
0x180015193  push    rsi
0x180015194  push    rdi
0x180015195  push    r12
0x180015197  push    r13
0x180015199  push    r14
0x18001519b  push    r15
0x18001519d  sub     rsp, 28h
0x1800151a1  mov     esi, [rsp+68h+arg_20]
0x1800151a8  mov     r12d, 1
0x1800151ae  movzx   r13d, byte ptr [r9]
0x1800151b2  movzx   ebx, r12w
0x1800151b6  movzx   edi, r8w
0x1800151ba  mov     r15, r9
0x1800151bd  mov     r14, rdx
0x1800151c0  mov     r11, rcx
0x1800151c3  mov     r8d, esi
0x1800151c6  xor     r10d, r10d
0x1800151c9  cmp     bx, r13w
0x1800151cd  ja      loc_1800152BB
0x1800151d3  movzx   eax, bx
0x1800151d6  movzx   edx, byte ptr [rax+r15]
0x1800151db  mov     eax, edx
0x1800151dd  and     eax, 7
0x1800151e0  cmp     eax, 2
0x1800151e3  jnz     short loc_18001523D
0x1800151e5  movzx   ecx, r10w
0x1800151e9  lea     rax, [rcx+2]
0x1800151ed  cmp     rax, rdi
0x1800151f0  ja      loc_18001531E
0x1800151f6  lea     r9, [rcx+r14]
0x1800151fa  test    dl, 10h
0x1800151fd  jnz     loc_180015307
0x180015203  mov     rcx, [r11]
0x180015206  test    rcx, rcx
0x180015209  jz      short loc_180015227
0x18001520b  test    dl, 20h
0x18001520e  lea     edx, [r8+2]
0x180015212  jnz     loc_18001534E
0x180015218  cmp     edx, r8d
0x18001521b  jb      short loc_180015227
0x18001521d  cmp     edx, [r11+8]
0x180015221  jbe     loc_1800153A2
0x180015227  mov     eax, 3E9h
0x18001522c  add     rsp, 28h
0x180015230  pop     r15
0x180015232  pop     r14
0x180015234  pop     r13
0x180015236  pop     r12
0x180015238  pop     rdi
0x180015239  pop     rsi
0x18001523a  pop     rbp
0x18001523b  pop     rbx
0x18001523c  retn
0x18001523d  sub     eax, 1
0x180015240  jz      loc_180015328
0x180015246  cmp     eax, 3
0x180015249  jnz     loc_18001531E
0x18001524f  movzx   ecx, r10w
0x180015253  lea     rax, [rcx+4]
0x180015257  cmp     rax, rdi
0x18001525a  ja      loc_18001531E
0x180015260  lea     r9, [rcx+r14]
0x180015264  test    dl, 10h
0x180015267  jnz     loc_18001536B
0x18001526d  test    dl, 20h
0x180015270  jnz     short loc_1800152D8
0x180015272  mov     rcx, [r11]
0x180015275  test    rcx, rcx
0x180015278  jz      short loc_180015227
0x18001527a  lea     edx, [r8+4]
0x18001527e  cmp     edx, r8d
0x180015281  jb      short loc_180015227
0x180015283  cmp     edx, [r11+8]
0x180015287  ja      short loc_180015227
0x180015289  mov     eax, r8d
0x18001528c  mov     r8d, edx
0x18001528f  add     rcx, rax
0x180015292  movzx   eax, byte ptr [rcx]
0x180015295  movzx   r12d, byte ptr [rcx+1]
0x18001529a  shl     eax, 8
0x18001529d  or      r12d, eax
0x1800152a0  movzx   eax, byte ptr [rcx+2]
0x1800152a4  shl     r12d, 8
0x1800152a8  or      r12d, eax
0x1800152ab  movzx   eax, byte ptr [rcx+3]
0x1800152af  shl     r12d, 8
0x1800152b3  or      r12d, eax
0x1800152b6  jmp     loc_18001536E
0x1800152bb  cmp     r10w, di
0x1800152bf  jb      short loc_18001531E
0x1800152c1  mov     rax, [rsp+68h+arg_28]
0x1800152c9  sub     r8w, si
0x1800152cd  mov     [rax], r8w
0x1800152d1  xor     eax, eax
0x1800152d3  jmp     loc_18001522C
0x1800152d8  mov     rdx, [r11]
0x1800152db  test    rdx, rdx
0x1800152de  jz      loc_180015227
0x1800152e4  lea     ecx, [r8+4]
0x1800152e8  cmp     ecx, r8d
0x1800152eb  jb      loc_180015227
0x1800152f1  cmp     ecx, [r11+8]
0x1800152f5  ja      loc_180015227
0x1800152fb  mov     eax, r8d
0x1800152fe  mov     r8d, ecx
0x180015301  mov     r12d, [rax+rdx]
0x180015305  jmp     short loc_18001536E
0x180015307  xor     eax, eax
0x180015309  mov     [r9], ax
0x18001530d  inc     bx
0x180015310  mov     eax, 2
0x180015315  add     r10w, ax
0x180015319  jmp     loc_1800151C9
0x18001531e  mov     eax, 3EBh
0x180015323  jmp     loc_18001522C
0x180015328  movzx   ecx, r10w
0x18001532c  lea     rax, [rcx+1]
0x180015330  cmp     rax, rdi
0x180015333  ja      short loc_18001531E
0x180015335  test    dl, 10h
0x180015338  jz      short loc_180015388
0x18001533a  mov     byte ptr [rcx+r14], 0
0x18001533f  mov     eax, r12d
0x180015342  inc     bx
0x180015345  add     r10w, ax
0x180015349  jmp     loc_1800151C9
0x18001534e  cmp     edx, r8d
0x180015351  jb      loc_180015227
0x180015357  cmp     edx, [r11+8]
0x18001535b  ja      loc_180015227
0x180015361  mov     eax, r8d
0x180015364  movzx   r12d, word ptr [rax+rcx]
0x180015369  jmp     short loc_1800153B7
0x18001536b  xor     r12d, r12d
0x18001536e  mov     eax, 4
0x180015373  mov     [r9], r12d
0x180015376  inc     bx
0x180015379  mov     r12d, 1
0x18001537f  add     r10w, ax
0x180015383  jmp     loc_1800151C9
0x180015388  lea     rdx, [rcx+r14]
0x18001538c  mov     rcx, r11
0x18001538f  call    ReadByte
0x180015394  test    ax, ax
0x180015397  jnz     loc_18001522C
0x18001539d  inc     r8d
0x1800153a0  jmp     short loc_18001533F
0x1800153a2  mov     eax, r8d
0x1800153a5  movzx   r12d, byte ptr [rax+rcx+1]
0x1800153ab  movzx   ecx, byte ptr [rax+rcx]
0x1800153af  shl     cx, 8
0x1800153b3  or      r12w, cx
0x1800153b7  movzx   eax, r12w
0x1800153bb  mov     r8d, edx
0x1800153be  mov     r12d, 1
0x1800153c4  jmp     loc_180015309
```
