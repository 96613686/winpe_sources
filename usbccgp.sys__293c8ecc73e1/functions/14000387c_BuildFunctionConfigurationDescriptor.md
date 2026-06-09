# BuildFunctionConfigurationDescriptor

- ea: `0x14000387c`
- end: `0x140003b33`
- name: `BuildFunctionConfigurationDescriptor`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003470`

## callees

- `0x14000387c`
- `0x14000d240`
- `0x140014e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003afe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003afe`
- `ntoskrnl!ExAllocatePool2` at `0x140003947`
- `ntoskrnl!ExAllocatePool2` at `0x140003947`

## pseudocode

```c
__int64 __fastcall BuildFunctionConfigurationDescriptor(__int64 a1, void *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v6; // rdi
  unsigned __int16 v7; // bp
  __int64 v8; // r13
  unsigned int v9; // r9d
  __int64 v10; // rbx
  __int64 v11; // r8
  unsigned __int8 *v12; // rdx
  _BYTE *v13; // r10
  __int64 v14; // rcx
  __int64 Pool2; // rax
  __int64 v16; // rdi
  unsigned int v17; // ebx
  void *v18; // r9
  unsigned __int16 v19; // r12
  __int64 v20; // r15
  unsigned __int8 *v21; // r13
  unsigned __int8 *v22; // rbx
  __int64 v23; // rcx
  char v24; // cl
  char v25; // cl
  unsigned int v26; // eax
  int v27; // edx
  int v28; // r8d
  __int64 v30; // [rsp+30h] [rbp-58h]
  unsigned __int64 v31; // [rsp+38h] [rbp-50h]
  _QWORD v32[9]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v33; // [rsp+90h] [rbp+8h]

  if ( a3 >= 9 && a2 )
  {
    v6 = *(_QWORD *)(a1 + 232);
    v7 = 9;
    v8 = *(_QWORD *)(a1 + 240);
    v9 = *(_DWORD *)(a1 + 12);
    v30 = v6;
    v10 = *(_QWORD *)(v6 + 56);
    v32[0] = v8;
    v31 = v10 + *(unsigned __int16 *)(v10 + 2);
    if ( v9 )
    {
      v11 = 0;
      do
      {
        v12 = **(unsigned __int8 ***)(*(_QWORD *)(v8 + 8) + 8 * v11);
        v13 = v12 + 2;
        do
        {
          v14 = *v12;
          if ( (unsigned __int8)v14 < 2u )
            break;
          if ( v12[1] != 11 || (*(_DWORD *)(v6 + 1224) & 2) != 0 )
            v7 += v14;
          v12 += v14;
          if ( (unsigned __int64)v12 >= v10 + (unsigned __int64)*(unsigned __int16 *)(v10 + 2) )
            break;
        }
        while ( v12[1] != 4 || v12[2] == *v13 );
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < v9 );
    }
    Pool2 = ExAllocatePool2(64, v7, 1130525525);
    v16 = Pool2;
    if ( Pool2 )
    {
      if ( v7 >= 9u )
      {
        v18 = (void *)(Pool2 + 9);
        *(_QWORD *)Pool2 = *(_QWORD *)v10;
        v19 = v7 - 9;
        v20 = 0;
        *(_BYTE *)(Pool2 + 8) = *(_BYTE *)(v10 + 8);
        v33 = Pool2 + 9;
        while ( (unsigned int)v20 < *(_DWORD *)(a1 + 12) )
        {
          v21 = **(unsigned __int8 ***)(*(_QWORD *)(v8 + 8) + 8 * v20);
          v22 = v21;
          do
          {
            LOWORD(v23) = *v22;
            if ( (unsigned __int8)v23 < 2u )
              break;
            if ( v22[1] != 11 || (*(_DWORD *)(v30 + 1224) & 2) != 0 )
            {
              if ( v19 < (unsigned __int16)v23 )
                goto LABEL_29;
              memmove(v18, v22, *v22);
              v23 = *v22;
              v18 = (void *)(v23 + v33);
              v33 += v23;
              v19 -= v23;
            }
            v22 += (unsigned __int8)v23;
            if ( (unsigned __int64)v22 >= v31 )
              break;
          }
          while ( v22[1] != 4 || v22[2] == v21[2] );
          v8 = v32[0];
          v20 = (unsigned int)(v20 + 1);
        }
        *(_BYTE *)(v16 + 4) = *(_BYTE *)(a1 + 12);
        *(_WORD *)(v16 + 2) = v7;
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 232) + 1362LL) )
        {
          v24 = *(_BYTE *)(v16 + 7);
          if ( *(_BYTE *)(*(_QWORD *)(a1 + 384) + 57LL) )
            v25 = v24 | 0x20;
          else
            v25 = v24 & 0xDF;
          *(_BYTE *)(v16 + 7) = v25;
        }
        v26 = v7;
        if ( a3 <= v7 )
          v26 = a3;
        *a4 = v26;
        memmove(a2, (const void *)v16, v26);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v32[1] = *(unsigned __int16 *)a4;
          v32[0] = a2;
          WPP_RECORDER_SF__HEX_(
            *(_QWORD *)(v30 + 1368),
            v27,
            v28,
            26,
            (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
            (__int64)v32);
        }
        v17 = 0;
LABEL_42:
        ExFreePoolWithTag((PVOID)v16, 0x43627355u);
        return v17;
      }
LABEL_29:
      v17 = -1073741668;
    }
    else
    {
      v17 = -1073741670;
    }
    *a4 = 0;
    if ( !v16 )
      return v17;
    goto LABEL_42;
  }
  *a4 = 0;
  return 3221225990LL;
}

```

## disassembly

```asm
0x14000387c  mov     [rsp+arg_18], rbx
0x140003881  mov     dword ptr [rsp+Size], r8d
0x140003886  mov     [rsp+arg_8], rdx
0x14000388b  push    rbp
0x14000388c  push    rsi
0x14000388d  push    rdi
0x14000388e  push    r12
0x140003890  push    r13
0x140003892  push    r14
0x140003894  push    r15
0x140003896  sub     rsp, 50h
0x14000389a  mov     r12d, 9
0x1400038a0  mov     r14, r9
0x1400038a3  mov     rsi, rcx
0x1400038a6  cmp     r8d, r12d
0x1400038a9  jb      loc_140003B0E
0x1400038af  test    rdx, rdx
0x1400038b2  jz      loc_140003B0E
0x1400038b8  mov     rdi, [rcx+0E8h]
0x1400038bf  movzx   ebp, r12w
0x1400038c3  mov     r13, [rcx+0F0h]
0x1400038ca  mov     r9d, [rcx+0Ch]
0x1400038ce  mov     [rsp+88h+var_58], rdi
0x1400038d3  mov     rbx, [rdi+38h]
0x1400038d7  mov     [rsp+88h+var_48], r13
0x1400038dc  movzx   r15d, word ptr [rbx+2]
0x1400038e1  add     r15, rbx
0x1400038e4  mov     [rsp+88h+var_50], r15
0x1400038e9  test    r9d, r9d
0x1400038ec  jz      short loc_140003939
0x1400038ee  mov     r11, [r13+8]
0x1400038f2  xor     r8d, r8d
0x1400038f5  mov     rcx, [r11+r8*8]
0x1400038f9  mov     rdx, [rcx]
0x1400038fc  lea     r10, [rdx+2]
0x140003900  movzx   ecx, byte ptr [rdx]
0x140003903  cmp     cl, 2
0x140003906  jb      short loc_140003931
0x140003908  cmp     byte ptr [rdx+1], 0Bh
0x14000390c  jnz     short loc_140003918
0x14000390e  mov     eax, [rdi+4C8h]
0x140003914  test    al, 2
0x140003916  jz      short loc_14000391B
0x140003918  add     bp, cx
0x14000391b  add     rdx, rcx
0x14000391e  cmp     rdx, r15
0x140003921  jnb     short loc_140003931
0x140003923  cmp     byte ptr [rdx+1], 4
0x140003927  jnz     short loc_140003900
0x140003929  mov     al, [r10]
0x14000392c  cmp     [rdx+2], al
0x14000392f  jz      short loc_140003900
0x140003931  inc     r8d
0x140003934  cmp     r8d, r9d
0x140003937  jb      short loc_1400038F5
0x140003939  movzx   edx, bp
0x14000393c  mov     ecx, 40h ; '@'
0x140003941  mov     r8d, 43627355h
0x140003947  call    cs:__imp_ExAllocatePool2
0x14000394e  nop     dword ptr [rax+rax+00h]
0x140003953  mov     rdi, rax
0x140003956  test    rax, rax
0x140003959  jnz     short loc_140003965
0x14000395b  mov     ebx, 0C000009Ah
0x140003960  jmp     loc_140003A21
0x140003965  cmp     bp, r12w
0x140003969  jb      loc_140003A1C
0x14000396f  movsd   xmm0, qword ptr [rbx]
0x140003973  lea     r9, [rdi+9]
0x140003977  movsd   qword ptr [rax], xmm0
0x14000397b  lea     r12d, [rbp-9]
0x14000397f  mov     al, [rbx+8]
0x140003982  xor     r15d, r15d
0x140003985  mov     [rdi+8], al
0x140003988  mov     [rsp+88h+arg_0], r9
0x140003990  cmp     r15d, [rsi+0Ch]
0x140003994  jnb     loc_140003A36
0x14000399a  mov     rax, [r13+8]
0x14000399e  mov     rcx, [rax+r15*8]
0x1400039a2  mov     r13, [rcx]
0x1400039a5  mov     rbx, r13
0x1400039a8  movzx   ecx, byte ptr [rbx]
0x1400039ab  cmp     cl, 2
0x1400039ae  jb      short loc_140003A0F
0x1400039b0  cmp     byte ptr [rbx+1], 0Bh
0x1400039b4  jnz     short loc_1400039C5
0x1400039b6  mov     rax, [rsp+88h+var_58]
0x1400039bb  mov     eax, [rax+4C8h]
0x1400039c1  test    al, 2
0x1400039c3  jz      short loc_1400039F3
0x1400039c5  cmp     r12w, cx
0x1400039c9  jb      short loc_140003A1C
0x1400039cb  mov     r8, rcx; Size
0x1400039ce  mov     rdx, rbx; Src
0x1400039d1  mov     rcx, r9; void *
0x1400039d4  call    memmove
0x1400039d9  movzx   ecx, byte ptr [rbx]
0x1400039dc  mov     r9, [rsp+88h+arg_0]
0x1400039e4  add     r9, rcx
0x1400039e7  mov     [rsp+88h+arg_0], r9
0x1400039ef  sub     r12w, cx
0x1400039f3  movzx   eax, cl
0x1400039f6  add     rbx, rax
0x1400039f9  cmp     rbx, [rsp+88h+var_50]
0x1400039fe  jnb     short loc_140003A0F
0x140003a00  cmp     byte ptr [rbx+1], 4
0x140003a04  jnz     short loc_1400039A8
0x140003a06  mov     al, [r13+2]
0x140003a0a  cmp     [rbx+2], al
0x140003a0d  jz      short loc_1400039A8
0x140003a0f  mov     r13, [rsp+88h+var_48]
0x140003a14  inc     r15d
0x140003a17  jmp     loc_140003990
0x140003a1c  mov     ebx, 0C000009Ch
0x140003a21  mov     dword ptr [r14], 0
0x140003a28  test    rdi, rdi
0x140003a2b  jnz     loc_140003AF6
0x140003a31  jmp     loc_140003B0A
0x140003a36  mov     al, [rsi+0Ch]
0x140003a39  mov     [rdi+4], al
0x140003a3c  mov     [rdi+2], bp
0x140003a40  mov     rax, [rsi+0E8h]
0x140003a47  cmp     byte ptr [rax+552h], 0
0x140003a4e  jz      short loc_140003A6B
0x140003a50  mov     rax, [rsi+180h]
0x140003a57  mov     cl, [rdi+7]
0x140003a5a  cmp     byte ptr [rax+39h], 0
0x140003a5e  jz      short loc_140003A65
0x140003a60  or      cl, 20h
0x140003a63  jmp     short loc_140003A68
0x140003a65  and     cl, 0DFh
0x140003a68  mov     [rdi+7], cl
0x140003a6b  mov     r13, [rsp+88h+arg_8]
0x140003a73  mov     rdx, rdi; Src
0x140003a76  movzx   eax, bp
0x140003a79  mov     rcx, r13; void *
0x140003a7c  cmp     dword ptr [rsp+88h+Size], eax
0x140003a83  cmovbe  eax, dword ptr [rsp+88h+Size]
0x140003a8b  mov     r8d, eax; Size
0x140003a8e  mov     [r14], r8d
0x140003a91  call    memmove
0x140003a96  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003a9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003aa4  jz      short loc_140003AF4
0x140003aa6  movzx   eax, word ptr [r14]
0x140003aaa  xorps   xmm0, xmm0
0x140003aad  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x140003ab2  mov     word ptr [rsp+88h+var_48+8], ax
0x140003ab7  mov     r9d, 1Ah
0x140003abd  mov     [rsp+88h+var_48], r13
0x140003ac2  lea     rax, [rsp+88h+var_48]
0x140003ac7  movaps  xmm0, xmmword ptr [rsp+88h+var_48]
0x140003acc  mov     [rsp+88h+var_60], rax
0x140003ad1  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140003ad8  mov     [rsp+88h+var_68], rax
0x140003add  mov     rax, [rsp+88h+var_58]
0x140003ae2  movdqa  xmmword ptr [rsp+88h+var_48], xmm0
0x140003ae8  mov     rcx, [rax+558h]
0x140003aef  call    WPP_RECORDER_SF__HEX_
0x140003af4  xor     ebx, ebx
0x140003af6  mov     edx, 43627355h; Tag
0x140003afb  mov     rcx, rdi; P
0x140003afe  call    cs:__imp_ExFreePoolWithTag
0x140003b05  nop     dword ptr [rax+rax+00h]
0x140003b0a  mov     eax, ebx
0x140003b0c  jmp     short loc_140003B1A
0x140003b0e  mov     dword ptr [r9], 0
0x140003b15  mov     eax, 0C0000206h
0x140003b1a  mov     rbx, [rsp+88h+arg_18]
0x140003b22  add     rsp, 50h
0x140003b26  pop     r15
0x140003b28  pop     r14
0x140003b2a  pop     r13
0x140003b2c  pop     r12
0x140003b2e  pop     rdi
0x140003b2f  pop     rsi
0x140003b30  pop     rbp
0x140003b31  retn
```
