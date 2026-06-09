# Tpm20ResourceMgr::GetCachedResponse(void *,uint,void *,uint *)

- ea: `0x140009400`
- end: `0x140009658`
- name: `?GetCachedResponse@Tpm20ResourceMgr@@AEAAHPEAXI0PEAI@Z`
- size: `600`
- prototype: `int(Tpm20ResourceMgr *__hidden this, void *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016afc`

## callees

- `0x140009400`
- `0x140009d00`
- `0x140039840`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::GetCachedResponse(
        Tpm20ResourceMgr *this,
        char *a2,
        int a3,
        char *a4,
        unsigned int *a5)
{
  unsigned int v5; // ebx
  unsigned __int16 v7; // di
  unsigned __int32 v11; // eax
  int i; // edx
  __int64 v13; // rax
  const void *v14; // rdx
  __int64 v15; // r15
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  __int64 v20; // r8
  const void *v21; // rdx
  unsigned int v22; // eax
  char *v23; // [rsp+30h] [rbp-48h] BYREF
  __int64 v24; // [rsp+38h] [rbp-40h]

  v5 = 0;
  v7 = a3;
  if ( a3 == 14 )
  {
    if ( __ROR2__(*(_WORD *)a2, 8) == 0x8001
      && _byteswap_ulong(*(_DWORD *)(a2 + 6)) == 371
      && _byteswap_ulong(*(_DWORD *)(a2 + 2)) == 14 )
    {
      v11 = _byteswap_ulong(*(_DWORD *)(a2 + 10));
      if ( (v11 & 0xFF000000) == 0x81000000 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 5 )
          {
            for ( i = 0; i < 5; ++i )
            {
              v20 = 4LL * i;
              if ( !*(_DWORD *)((char *)this + v20 + 136) )
              {
                *(_DWORD *)((char *)this + v20 + 136) = v11;
                goto LABEL_11;
              }
            }
            return v5;
          }
          if ( *((_DWORD *)this + i + 34) == v11 )
            break;
        }
LABEL_11:
        if ( i != -1 )
        {
          v13 = i;
          v14 = (const void *)*((_QWORD *)this + i + 12);
          if ( v14 )
          {
            v15 = 4 * v13;
            v16 = *((_DWORD *)this + v13 + 18);
            if ( v16 )
            {
              if ( *a5 >= v16 )
              {
                memmove(a4, v14, v16);
                v17 = *(_DWORD *)((char *)this + v15 + 72);
                goto LABEL_16;
              }
            }
          }
        }
      }
    }
  }
  else if ( a3 == 10
         && __ROR2__(*(_WORD *)a2, 8) == 0x8001
         && _byteswap_ulong(*(_DWORD *)(a2 + 6)) == 380
         && _byteswap_ulong(*(_DWORD *)(a2 + 2)) == 10 )
  {
    v21 = (const void *)*((_QWORD *)this + 20);
    if ( v21 )
    {
      v22 = *((_DWORD *)this + 39);
      if ( v22 )
      {
        if ( *a5 >= v22 )
        {
          memmove(a4, v21, v22);
          v17 = *((_DWORD *)this + 39);
LABEL_16:
          v5 = 1;
          *a5 = v17;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              v18 = *(_DWORD *)(a2 + 6);
              v23 = a2;
              v24 = v7;
              WPP_SF_L_HEX_(
                WPP_GLOBAL_Control->AttachedDevice,
                49,
                (unsigned int)WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
                _byteswap_ulong(v18),
                (__int64)&v23);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              v19 = *(_DWORD *)(a2 + 6);
              v24 = *(unsigned __int16 *)a5;
              v23 = a4;
              WPP_SF_L_HEX_(
                WPP_GLOBAL_Control->AttachedDevice,
                50,
                (unsigned int)WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
                _byteswap_ulong(v19),
                (__int64)&v23);
            }
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140009400  push    rbx
0x140009402  push    rbp
0x140009403  push    rsi
0x140009404  push    rdi
0x140009405  push    r12
0x140009407  push    r14
0x140009409  push    r15
0x14000940b  sub     rsp, 40h
0x14000940f  mov     r14, [rsp+78h+arg_20]
0x140009417  xor     ebx, ebx
0x140009419  mov     r12, r9
0x14000941c  mov     edi, r8d
0x14000941f  mov     rsi, rdx
0x140009422  mov     rbp, rcx
0x140009425  cmp     r8d, 0Eh
0x140009429  jz      short loc_140009447
0x14000942b  cmp     r8d, 0Ah
0x14000942f  jz      loc_1400095E8
0x140009435  mov     eax, ebx
0x140009437  add     rsp, 40h
0x14000943b  pop     r15
0x14000943d  pop     r14
0x14000943f  pop     r12
0x140009441  pop     rdi
0x140009442  pop     rsi
0x140009443  pop     rbp
0x140009444  pop     rbx
0x140009445  retn
0x140009447  movzx   eax, word ptr [rdx]
0x14000944a  mov     ecx, 8001h
0x14000944f  ror     ax, 8
0x140009453  cmp     ax, cx
0x140009456  jnz     short loc_140009435
0x140009458  mov     eax, [rdx+6]
0x14000945b  bswap   eax
0x14000945d  cmp     eax, 173h
0x140009462  jnz     short loc_140009435
0x140009464  mov     eax, [rdx+2]
0x140009467  bswap   eax
0x140009469  cmp     eax, 0Eh
0x14000946c  jnz     short loc_140009435
0x14000946e  mov     eax, [rdx+0Ah]
0x140009471  bswap   eax
0x140009473  mov     ecx, eax
0x140009475  and     ecx, 0FF000000h
0x14000947b  cmp     ecx, 81000000h
0x140009481  jnz     short loc_140009435
0x140009483  xor     edx, edx
0x140009485  cmp     edx, 5
0x140009488  jge     loc_1400095B7
0x14000948e  movsxd  rcx, edx
0x140009491  cmp     [rbp+rcx*4+88h], eax
0x140009498  jnz     loc_1400095B0
0x14000949e  cmp     edx, 0FFFFFFFFh
0x1400094a1  jz      short loc_140009435
0x1400094a3  movsxd  rax, edx
0x1400094a6  mov     rdx, [rbp+rax*8+60h]; Src
0x1400094ab  test    rdx, rdx
0x1400094ae  jz      short loc_140009435
0x1400094b0  lea     r15, ds:0[rax*4]
0x1400094b8  mov     eax, [r15+rbp+48h]
0x1400094bd  test    eax, eax
0x1400094bf  jz      loc_140009435
0x1400094c5  cmp     [r14], eax
0x1400094c8  jb      loc_140009435
0x1400094ce  mov     r8d, eax; Size
0x1400094d1  mov     rcx, r12; void *
0x1400094d4  call    memmove
0x1400094d9  mov     eax, [r15+rbp+48h]
0x1400094de  mov     rcx, r14
0x1400094e1  mov     ebx, 1
0x1400094e6  mov     [rcx], eax
0x1400094e8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400094ef  lea     rbp, WPP_GLOBAL_Control
0x1400094f6  cmp     rcx, rbp
0x1400094f9  jz      loc_140009435
0x1400094ff  mov     eax, [rcx+2Ch]
0x140009502  test    al, 10h
0x140009504  jz      short loc_140009549
0x140009506  mov     r9d, [rsi+6]
0x14000950a  lea     rax, [rsp+78h+var_48]
0x14000950f  xorps   xmm0, xmm0
0x140009512  mov     [rsp+78h+var_58], rax
0x140009517  movups  [rsp+78h+var_48], xmm0
0x14000951c  mov     qword ptr [rsp+78h+var_48], rsi
0x140009521  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140009528  mov     word ptr [rsp+78h+var_48+8], di
0x14000952d  mov     edx, 31h ; '1'
0x140009532  movaps  xmm0, [rsp+78h+var_48]
0x140009537  movdqa  [rsp+78h+var_48], xmm0
0x14000953d  mov     rcx, [rcx+18h]
0x140009541  bswap   r9d
0x140009544  call    WPP_SF_L_HEX_
0x140009549  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009550  cmp     rcx, rbp
0x140009553  jz      loc_140009435
0x140009559  mov     eax, [rcx+2Ch]
0x14000955c  test    al, 10h
0x14000955e  jz      loc_140009435
0x140009564  movzx   eax, word ptr [r14]
0x140009568  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000956f  mov     r9d, [rsi+6]
0x140009573  xorps   xmm0, xmm0
0x140009576  movups  [rsp+78h+var_48], xmm0
0x14000957b  mov     word ptr [rsp+78h+var_48+8], ax
0x140009580  mov     edx, 32h ; '2'
0x140009585  mov     qword ptr [rsp+78h+var_48], r12
0x14000958a  lea     rax, [rsp+78h+var_48]
0x14000958f  movaps  xmm0, [rsp+78h+var_48]
0x140009594  movdqa  [rsp+78h+var_48], xmm0
0x14000959a  mov     rcx, [rcx+18h]
0x14000959e  bswap   r9d
0x1400095a1  mov     [rsp+78h+var_58], rax
0x1400095a6  call    WPP_SF_L_HEX_
0x1400095ab  jmp     loc_140009435
0x1400095b0  inc     edx
0x1400095b2  jmp     loc_140009485
0x1400095b7  xor     edx, edx
0x1400095b9  cmp     edx, 5
0x1400095bc  jge     loc_140009435
0x1400095c2  movsxd  rcx, edx
0x1400095c5  lea     r8, ds:0[rcx*4]
0x1400095cd  cmp     [r8+rbp+88h], ebx
0x1400095d5  jz      short loc_1400095DB
0x1400095d7  inc     edx
0x1400095d9  jmp     short loc_1400095B9
0x1400095db  mov     [r8+rbp+88h], eax
0x1400095e3  jmp     loc_14000949E
0x1400095e8  movzx   eax, word ptr [rdx]
0x1400095eb  mov     ecx, 8001h
0x1400095f0  ror     ax, 8
0x1400095f4  cmp     ax, cx
0x1400095f7  jnz     loc_140009435
0x1400095fd  mov     eax, [rdx+6]
0x140009600  bswap   eax
0x140009602  cmp     eax, 17Ch
0x140009607  jnz     loc_140009435
0x14000960d  mov     eax, [rdx+2]
0x140009610  bswap   eax
0x140009612  cmp     eax, 0Ah
0x140009615  jnz     loc_140009435
0x14000961b  mov     rdx, [rbp+0A0h]; Src
0x140009622  test    rdx, rdx
0x140009625  jz      loc_140009435
0x14000962b  mov     eax, [rbp+9Ch]
0x140009631  test    eax, eax
0x140009633  jz      loc_140009435
0x140009639  cmp     [r14], eax
0x14000963c  jb      loc_140009435
0x140009642  mov     r8d, eax; Size
0x140009645  mov     rcx, r12; void *
0x140009648  call    memmove
0x14000964d  mov     eax, [rbp+9Ch]
0x140009653  jmp     loc_1400094DE
```
