# AdjustReceiveBufferLists

- ea: `0x14000c624`
- end: `0x14000c8b6`
- name: `AdjustReceiveBufferLists`
- size: `658`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d414`
- `0x14000e03c`
- `0x14000f2d8`
- `0x140012efc`

## callees

- `0x14000c624`
- `0x14000ef98`
- `0x1400156d0`

## pseudocode

```c
__int64 __fastcall AdjustReceiveBufferLists(__int64 a1)
{
  unsigned int v2; // r12d
  __int64 v3; // rcx
  int v4; // r13d
  __int64 v5; // rcx
  __int64 *v6; // rbx
  int v7; // edx
  unsigned __int8 *v8; // r15
  int v9; // esi
  unsigned int v10; // r8d
  int v11; // eax
  bool v12; // zf
  unsigned __int8 v13; // si
  unsigned __int8 v14; // bp
  __int64 *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int8 v18; // dl
  unsigned __int8 i; // r8
  __int64 v20; // rax
  unsigned __int8 j; // r8
  __int64 v22; // rax
  __int64 *v23; // rcx
  __int64 **v24; // rax
  __int64 v25; // rax
  __int64 **v26; // rcx
  __int64 result; // rax

  v2 = 0;
  v3 = *(_QWORD *)(a1 + 48);
  v4 = 0;
  if ( *(_QWORD *)(v3 + 120) == v3 + 120 )
    *(_QWORD *)(v3 + 112) = WPP_MAIN_CB.Dpc.SystemArgument1;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 56LL) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 60LL) + *(unsigned __int8 *)(a1 + 160);
  while ( 1 )
  {
    v5 = *(_QWORD *)(a1 + 48);
    v6 = *(__int64 **)(v5 + 136);
    if ( v6 == (__int64 *)(v5 + 136) )
      break;
    v7 = *((unsigned __int8 *)v6 + 58);
    v8 = (unsigned __int8 *)v6 + 63;
    v9 = *((unsigned __int8 *)v6 + 59);
    v10 = *((unsigned __int8 *)v6 + 57);
    if ( v7 + v9 < v10 && v7 + (unsigned int)*v8 < v10 )
    {
      *(_DWORD *)(v5 + 56) = *((_DWORD *)v6 + 4);
      break;
    }
    v11 = *v8;
    if ( (_BYTE)v11 && (_BYTE)v9 && v7 + v11 >= v10 )
    {
      v12 = (_BYTE)v7 + (_BYTE)v9 == 0;
      v13 = v7 + v9;
      v14 = v13;
      if ( !v12 )
      {
        do
        {
          if ( !*((_BYTE *)v6 + 59) )
            break;
          if ( BYTE4(v6[5 * --v14 + 14]) >= *((_BYTE *)v6 + 62) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              WPP_SF_ddddd(
                WPP_GLOBAL_Control->AttachedDevice,
                39,
                *((unsigned __int8 *)v6 + 59),
                v14,
                *v8,
                *((unsigned __int8 *)v6 + 58),
                *((unsigned __int8 *)v6 + 59),
                *((unsigned __int8 *)v6 + 57));
            }
            v15 = &v6[5 * v14];
            FreeDataBuffer(a1, v15 + 12);
            if ( v14 != v13 - 1 )
            {
              *((_OWORD *)v15 + 6) = *(_OWORD *)&v6[5 * v13 + 7];
              *((_OWORD *)v15 + 7) = *(_OWORD *)&v6[5 * v13 + 9];
              v15[16] = v6[5 * v13 + 11];
            }
            v16 = v13--;
            v17 = 5 * v16;
            *(_OWORD *)&v6[v17 + 7] = 0;
            *(_OWORD *)&v6[v17 + 9] = 0;
            v6[v17 + 11] = 0;
            --*((_BYTE *)v6 + 59);
            --*(_DWORD *)(*(_QWORD *)(a1 + 48) + 268LL);
            --*(_DWORD *)(*(_QWORD *)(a1 + 48) + 260LL);
          }
        }
        while ( v14 );
      }
      v18 = *((_BYTE *)v6 + 62);
      if ( v18 )
      {
        for ( i = 0; i < v18; ++i )
        {
          v20 = i;
          BYTE5(v6[5 * v20 + 14]) = v18;
          v18 = *((_BYTE *)v6 + 62);
        }
      }
      if ( v13 )
      {
        for ( j = 0; j < v13; ++j )
        {
          v22 = BYTE4(v6[5 * j + 14]);
          if ( (unsigned __int8)v22 < v18 )
          {
            BYTE5(v6[5 * v22 + 14]) = j;
            v18 = *((_BYTE *)v6 + 62);
          }
        }
      }
    }
    v23 = (__int64 *)*v6;
    if ( *(__int64 **)(*v6 + 8) != v6
      || (v24 = (__int64 **)v6[1], *v24 != v6)
      || (*v24 = v23,
          v23[1] = (__int64)v24,
          v25 = *(_QWORD *)(a1 + 48) + 120LL,
          v26 = *(__int64 ***)(*(_QWORD *)(a1 + 48) + 128LL),
          *v26 != (__int64 *)v25) )
    {
      __fastfail(3u);
    }
    *v6 = v25;
    ++v2;
    v6[1] = (__int64)v26;
    *v26 = v6;
    *(_QWORD *)(v25 + 8) = v6;
    v4 += *((unsigned __int8 *)v6 + 59) + *((unsigned __int8 *)v6 + 58);
  }
  result = v2;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 272LL) += v2;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 264LL) += v4;
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 268LL) -= v4;
  return result;
}

```

## disassembly

```asm
0x14000c624  push    rbx
0x14000c626  push    rbp
0x14000c627  push    rsi
0x14000c628  push    rdi
0x14000c629  push    r12
0x14000c62b  push    r13
0x14000c62d  push    r14
0x14000c62f  push    r15
0x14000c631  sub     rsp, 48h
0x14000c635  mov     rdi, rcx
0x14000c638  xor     r12d, r12d
0x14000c63b  mov     rcx, [rcx+30h]
0x14000c63f  xor     r13d, r13d
0x14000c642  lea     rax, [rcx+78h]
0x14000c646  cmp     [rax], rax
0x14000c649  jnz     short loc_14000C656
0x14000c64b  mov     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000c652  mov     [rcx+70h], rax
0x14000c656  mov     rcx, [rdi+30h]
0x14000c65a  movzx   eax, byte ptr [rdi+0A0h]
0x14000c661  add     eax, [rcx+3Ch]
0x14000c664  mov     [rcx+38h], eax
0x14000c667  mov     rcx, [rdi+30h]
0x14000c66b  lea     rax, [rcx+88h]
0x14000c672  mov     rbx, [rax]
0x14000c675  cmp     rbx, rax
0x14000c678  jz      loc_14000C879
0x14000c67e  movzx   edx, byte ptr [rbx+3Ah]
0x14000c682  lea     r15, [rbx+3Fh]
0x14000c686  movzx   esi, byte ptr [rbx+3Bh]
0x14000c68a  movzx   r8d, byte ptr [rbx+39h]
0x14000c68f  lea     eax, [rdx+rsi]
0x14000c692  cmp     eax, r8d
0x14000c695  jnb     short loc_14000C6A6
0x14000c697  movzx   eax, byte ptr [r15]
0x14000c69b  add     eax, edx
0x14000c69d  cmp     eax, r8d
0x14000c6a0  jb      loc_14000C873
0x14000c6a6  movzx   eax, byte ptr [r15]
0x14000c6aa  test    al, al
0x14000c6ac  jz      loc_14000C821
0x14000c6b2  test    sil, sil
0x14000c6b5  jz      loc_14000C821
0x14000c6bb  add     eax, edx
0x14000c6bd  cmp     eax, r8d
0x14000c6c0  jb      loc_14000C821
0x14000c6c6  add     sil, dl
0x14000c6c9  mov     bpl, sil
0x14000c6cc  jz      loc_14000C7D3
0x14000c6d2  movzx   edx, byte ptr [rbx+3Bh]
0x14000c6d6  test    dl, dl
0x14000c6d8  jz      loc_14000C7D3
0x14000c6de  add     bpl, 0FFh
0x14000c6e2  movzx   eax, bpl
0x14000c6e6  lea     r14, [rax+rax*4]
0x14000c6ea  mov     al, [rbx+3Eh]
0x14000c6ed  cmp     [rbx+r14*8+74h], al
0x14000c6f2  jb      loc_14000C7CA
0x14000c6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6ff  lea     rax, WPP_GLOBAL_Control
0x14000c706  cmp     rcx, rax
0x14000c709  jz      short loc_14000C747
0x14000c70b  mov     eax, [rcx+2Ch]
0x14000c70e  test    al, 10h
0x14000c710  jz      short loc_14000C747
0x14000c712  movzx   eax, byte ptr [rbx+39h]
0x14000c716  mov     r8d, edx
0x14000c719  movzx   r10d, byte ptr [rbx+3Ah]
0x14000c71e  mov     edx, 27h ; '''
0x14000c723  movzx   r11d, byte ptr [r15]
0x14000c727  mov     rcx, [rcx+18h]
0x14000c72b  mov     [rsp+88h+var_50], eax
0x14000c72f  mov     [rsp+88h+var_58], r8d
0x14000c734  mov     [rsp+88h+var_60], r10d
0x14000c739  movzx   r9d, bpl
0x14000c73d  mov     [rsp+88h+var_68], r11d
0x14000c742  call    WPP_SF_ddddd
0x14000c747  lea     r14, [rbx+r14*8]
0x14000c74b  mov     rcx, rdi
0x14000c74e  lea     rdx, [r14+60h]
0x14000c752  call    FreeDataBuffer
0x14000c757  movzx   edx, sil
0x14000c75b  movzx   eax, bpl
0x14000c75f  lea     ecx, [rdx-1]
0x14000c762  cmp     eax, ecx
0x14000c764  jz      short loc_14000C78D
0x14000c766  lea     rcx, [rdx+rdx*4]
0x14000c76a  movups  xmm0, xmmword ptr [rbx+rcx*8+38h]
0x14000c76f  movups  xmmword ptr [r14+60h], xmm0
0x14000c774  movups  xmm1, xmmword ptr [rbx+rcx*8+48h]
0x14000c779  movups  xmmword ptr [r14+70h], xmm1
0x14000c77e  movsd   xmm0, qword ptr [rbx+rcx*8+58h]
0x14000c784  movsd   qword ptr [r14+80h], xmm0
0x14000c78d  movzx   eax, sil
0x14000c791  xorps   xmm0, xmm0
0x14000c794  or      r9d, 0FFFFFFFFh
0x14000c798  add     sil, 0FFh
0x14000c79c  lea     rcx, [rax+rax*4]
0x14000c7a0  xor     eax, eax
0x14000c7a2  movups  xmmword ptr [rbx+rcx*8+38h], xmm0
0x14000c7a7  movups  xmmword ptr [rbx+rcx*8+48h], xmm0
0x14000c7ac  mov     [rbx+rcx*8+58h], rax
0x14000c7b1  dec     byte ptr [rbx+3Bh]
0x14000c7b4  mov     rax, [rdi+30h]
0x14000c7b8  add     [rax+10Ch], r9d
0x14000c7bf  mov     rax, [rdi+30h]
0x14000c7c3  add     [rax+104h], r9d
0x14000c7ca  test    bpl, bpl
0x14000c7cd  jnz     loc_14000C6D2
0x14000c7d3  mov     dl, [rbx+3Eh]
0x14000c7d6  test    dl, dl
0x14000c7d8  jz      short loc_14000C7F4
0x14000c7da  xor     r8b, r8b
0x14000c7dd  movzx   eax, r8b
0x14000c7e1  inc     r8b
0x14000c7e4  lea     rcx, [rax+rax*4]
0x14000c7e8  mov     [rbx+rcx*8+75h], dl
0x14000c7ec  mov     dl, [rbx+3Eh]
0x14000c7ef  cmp     r8b, dl
0x14000c7f2  jb      short loc_14000C7DD
0x14000c7f4  test    sil, sil
0x14000c7f7  jz      short loc_14000C821
0x14000c7f9  xor     r8b, r8b
0x14000c7fc  movzx   eax, r8b
0x14000c800  lea     rcx, [rax+rax*4]
0x14000c804  movzx   eax, byte ptr [rbx+rcx*8+74h]
0x14000c809  cmp     al, dl
0x14000c80b  jnb     short loc_14000C819
0x14000c80d  lea     rcx, [rax+rax*4]
0x14000c811  mov     [rbx+rcx*8+75h], r8b
0x14000c816  mov     dl, [rbx+3Eh]
0x14000c819  inc     r8b
0x14000c81c  cmp     r8b, sil
0x14000c81f  jb      short loc_14000C7FC
0x14000c821  mov     rcx, [rbx]
0x14000c824  cmp     [rcx+8], rbx
0x14000c828  jnz     loc_14000C8AF
0x14000c82e  mov     rax, [rbx+8]
0x14000c832  cmp     [rax], rbx
0x14000c835  jnz     short loc_14000C8AF
0x14000c837  mov     [rax], rcx
0x14000c83a  mov     [rcx+8], rax
0x14000c83e  mov     rax, [rdi+30h]
0x14000c842  add     rax, 78h ; 'x'
0x14000c846  mov     rcx, [rax+8]
0x14000c84a  cmp     [rcx], rax
0x14000c84d  jnz     short loc_14000C8AF
0x14000c84f  mov     [rbx], rax
0x14000c852  inc     r12d
0x14000c855  mov     [rbx+8], rcx
0x14000c859  mov     [rcx], rbx
0x14000c85c  mov     [rax+8], rbx
0x14000c860  movzx   eax, byte ptr [rbx+3Ah]
0x14000c864  movzx   ecx, byte ptr [rbx+3Bh]
0x14000c868  add     r13d, eax
0x14000c86b  add     r13d, ecx
0x14000c86e  jmp     loc_14000C667
0x14000c873  mov     eax, [rbx+10h]
0x14000c876  mov     [rcx+38h], eax
0x14000c879  mov     rcx, [rdi+30h]
0x14000c87d  mov     eax, r12d
0x14000c880  add     [rcx+110h], r12d
0x14000c887  mov     rcx, [rdi+30h]
0x14000c88b  add     [rcx+108h], r13d
0x14000c892  mov     rcx, [rdi+30h]
0x14000c896  sub     [rcx+10Ch], r13d
0x14000c89d  add     rsp, 48h
0x14000c8a1  pop     r15
0x14000c8a3  pop     r14
0x14000c8a5  pop     r13
0x14000c8a7  pop     r12
0x14000c8a9  pop     rdi
0x14000c8aa  pop     rsi
0x14000c8ab  pop     rbp
0x14000c8ac  pop     rbx
0x14000c8ad  retn
0x14000c8af  mov     ecx, 3
0x14000c8b4  int     29h; Win8: RtlFailFast(ecx)
```
