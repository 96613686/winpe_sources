# WbclApiMoveToNextElement

- ea: `0x14000af28`
- end: `0x14000b0a0`
- name: `WbclApiMoveToNextElement`
- size: `376`
- prototype: `__int64 __fastcall(struct _WBCL_Iterator *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aa98`
- `0x14000ae4c`
- `0x14000b3d8`

## callees

- `0x14000af28`
- `0x14000c590`
- `0x140032fe8`

## pseudocode

```c
__int64 __fastcall WbclApiMoveToNextElement(struct _WBCL_Iterator *a1)
{
  unsigned int v2; // r15d
  unsigned __int64 v3; // rcx
  __int64 v4; // rax
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r13
  unsigned __int64 v7; // rsi
  signed int v8; // edx
  __int16 v9; // cx
  __int64 v10; // rax
  unsigned int v11; // ebp
  int v12; // esi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned int DigestSizeUnchecked; // eax
  unsigned __int64 v17; // r9
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  unsigned int v20; // r14d
  unsigned __int16 *v21; // r9
  unsigned int v22; // r12d
  unsigned int v23; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v3 = *(_QWORD *)((char *)a1 + 12);
  if ( v3 )
  {
    v4 = *((unsigned int *)a1 + 5);
    if ( (_DWORD)v4 )
    {
      v5 = v3 + v4;
      if ( v3 + v4 < v3 )
        goto LABEL_16;
      v6 = -1;
      v7 = *(_QWORD *)a1 + *((unsigned int *)a1 + 2);
      if ( v7 >= *(_QWORD *)a1 )
        v6 = *(_QWORD *)a1 + *((unsigned int *)a1 + 2);
      v8 = v7 < *(_QWORD *)a1 ? 0xC0000095 : 0;
      if ( v7 < *(_QWORD *)a1 )
        goto LABEL_16;
      v9 = *((_WORD *)a1 + 13);
      v10 = 32;
      if ( v9 == 2 )
        v10 = *((unsigned __int16 *)a1 + 12) + 18LL;
      if ( v5 + v10 < v5 || v5 + v10 > v6 )
        goto LABEL_16;
      *(_QWORD *)((char *)a1 + 12) = v5;
      v23 = 0;
      if ( v9 == 1 )
      {
        v12 = 20;
      }
      else
      {
        if ( v9 == 2 )
        {
          v21 = (unsigned __int16 *)(v5 + 12);
          if ( v5 + 12 > v7 )
            goto LABEL_16;
          v22 = *(_DWORD *)(v5 + 8);
          if ( v22 > 5 )
            goto LABEL_16;
          v11 = 4;
          v20 = 0;
          while ( v20 < v22 )
          {
            if ( (unsigned __int64)(v21 + 1) > v7 )
              goto LABEL_16;
            DigestSizeUnchecked = WbclGetDigestSizeUnchecked(a1, *v21);
            v18 = DigestSizeUnchecked + 2;
            if ( DigestSizeUnchecked + 2 < DigestSizeUnchecked )
              goto LABEL_16;
            v19 = (unsigned __int16 *)(v17 + v18);
            if ( (unsigned __int64)v19 < v17 || (unsigned __int64)v19 > v7 || v18 + v11 < v11 )
              goto LABEL_16;
            ++v20;
            v11 += v18;
            v8 = 0;
            v21 = v19;
          }
        }
        else
        {
          v8 = 0;
          v11 = 0;
        }
        if ( v8 < 0 )
        {
LABEL_16:
          *(_QWORD *)((char *)a1 + 12) = 0;
          *((_DWORD *)a1 + 5) = 0;
          return 1;
        }
        v12 = v11;
      }
      if ( (int)WbclGetCurrentElementDataSize(a1, &v23) >= 0 )
      {
        v14 = v12 + v23 + 12;
        *((_DWORD *)a1 + 5) = v14;
        v15 = v5 + v14;
        if ( v15 <= v6 && v15 >= v5 )
          return v2;
      }
      goto LABEL_16;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000af28  push    rbx
0x14000af2a  push    rbp
0x14000af2b  push    rsi
0x14000af2c  push    rdi
0x14000af2d  push    r12
0x14000af2f  push    r13
0x14000af31  push    r14
0x14000af33  push    r15
0x14000af35  sub     rsp, 28h
0x14000af39  mov     rbx, rcx
0x14000af3c  xor     r15d, r15d
0x14000af3f  mov     rcx, [rcx+0Ch]
0x14000af43  test    rcx, rcx
0x14000af46  jz      loc_14000AFE1
0x14000af4c  mov     eax, [rbx+14h]
0x14000af4f  test    eax, eax
0x14000af51  jz      loc_14000AFE1
0x14000af57  lea     rdi, [rcx+rax]
0x14000af5b  lea     r9d, [r15+1]
0x14000af5f  cmp     rdi, rcx
0x14000af62  jb      short loc_14000AFD3
0x14000af64  mov     rcx, [rbx]
0x14000af67  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000af6b  mov     esi, [rbx+8]
0x14000af6e  add     rsi, rcx
0x14000af71  cmp     rsi, rcx
0x14000af74  cmovnb  r13, rsi
0x14000af78  sbb     edx, edx
0x14000af7a  and     edx, 0C0000095h
0x14000af80  cmp     rsi, rcx
0x14000af83  jb      short loc_14000AFD3
0x14000af85  movzx   ecx, word ptr [rbx+1Ah]
0x14000af89  lea     eax, [r15+20h]
0x14000af8d  cmp     cx, 2
0x14000af91  jnz     short loc_14000AF9B
0x14000af93  movzx   eax, word ptr [rbx+18h]
0x14000af97  add     rax, 12h
0x14000af9b  lea     r8, [rdi+rax]
0x14000af9f  cmp     r8, rdi
0x14000afa2  jb      short loc_14000AFD3
0x14000afa4  cmp     r8, r13
0x14000afa7  ja      short loc_14000AFD3
0x14000afa9  mov     [rbx+0Ch], rdi
0x14000afad  mov     [rsp+68h+arg_0], r15d
0x14000afb2  cmp     cx, r9w
0x14000afb6  jz      loc_14000B046
0x14000afbc  cmp     cx, 2
0x14000afc0  jz      loc_14000B062
0x14000afc6  xor     edx, edx
0x14000afc8  xor     ebp, ebp
0x14000afca  xor     esi, esi
0x14000afcc  test    edx, edx
0x14000afce  cmovns  esi, ebp
0x14000afd1  jns     short loc_14000B04B
0x14000afd3  mov     [rbx+0Ch], r15
0x14000afd7  mov     [rbx+14h], r15d
0x14000afdb  mov     r15d, 1
0x14000afe1  mov     eax, r15d
0x14000afe4  add     rsp, 28h
0x14000afe8  pop     r15
0x14000afea  pop     r14
0x14000afec  pop     r13
0x14000afee  pop     r12
0x14000aff0  pop     rdi
0x14000aff1  pop     rsi
0x14000aff2  pop     rbp
0x14000aff3  pop     rbx
0x14000aff4  retn
0x14000aff6  mov     ecx, [rsp+68h+arg_0]
0x14000affa  add     ecx, 0Ch
0x14000affd  add     ecx, esi
0x14000afff  mov     [rbx+14h], ecx
0x14000b002  add     rcx, rdi
0x14000b005  cmp     rcx, r13
0x14000b008  ja      short loc_14000AFD3
0x14000b00a  cmp     rcx, rdi
0x14000b00d  jb      short loc_14000AFD3
0x14000b00f  jmp     short loc_14000AFE1
0x14000b011  movzx   edx, word ptr [r9]; unsigned __int16
0x14000b015  mov     rcx, rbx; struct _WBCL_Iterator *
0x14000b018  call    ?WbclGetDigestSizeUnchecked@@YAIPEAU_WBCL_Iterator@@G@Z; WbclGetDigestSizeUnchecked(_WBCL_Iterator *,ushort)
0x14000b01d  lea     edx, [rax+2]
0x14000b020  cmp     edx, eax
0x14000b022  jb      short loc_14000AFD3
0x14000b024  mov     ecx, edx
0x14000b026  add     rcx, r9
0x14000b029  cmp     rcx, r9
0x14000b02c  jb      short loc_14000AFD3
0x14000b02e  cmp     rcx, rsi
0x14000b031  ja      short loc_14000AFD3
0x14000b033  lea     eax, [rdx+rbp]
0x14000b036  cmp     eax, ebp
0x14000b038  jb      short loc_14000AFD3
0x14000b03a  inc     r14d
0x14000b03d  mov     ebp, eax
0x14000b03f  xor     edx, edx
0x14000b041  mov     r9, rcx
0x14000b044  jmp     short loc_14000B085
0x14000b046  mov     esi, 14h
0x14000b04b  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x14000b050  mov     rcx, rbx; struct _WBCL_Iterator *
0x14000b053  call    ?WbclGetCurrentElementDataSize@@YAJPEAU_WBCL_Iterator@@PEAI@Z; WbclGetCurrentElementDataSize(_WBCL_Iterator *,uint *)
0x14000b058  test    eax, eax
0x14000b05a  js      loc_14000AFD3
0x14000b060  jmp     short loc_14000AFF6
0x14000b062  lea     r9, [rdi+0Ch]
0x14000b066  cmp     r9, rsi
0x14000b069  ja      loc_14000AFD3
0x14000b06f  mov     r12d, [rdi+8]
0x14000b073  cmp     r12d, 5
0x14000b077  ja      loc_14000AFD3
0x14000b07d  mov     ebp, 4
0x14000b082  xor     r14d, r14d
0x14000b085  cmp     r14d, r12d
0x14000b088  jnb     loc_14000AFCA
0x14000b08e  lea     rax, [r9+2]
0x14000b092  cmp     rax, rsi
0x14000b095  ja      loc_14000AFD3
0x14000b09b  jmp     loc_14000B011
```
