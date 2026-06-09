# AutoCalloutParameterLock::Pin(bool)

- ea: `0x18002c730`
- end: `0x18002c986`
- name: `?Pin@AutoCalloutParameterLock@@AEAAJ_N@Z`
- size: `598`
- prototype: `__int64 __fastcall(AutoCalloutParameterLock *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001924c`
- `0x180021540`

## callees

- `0x180007d78`
- `0x18002c730`
- `0x180067f50`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x18002c7e0`
- `OLE32!CoTaskMemAlloc` at `0x18002c7e0`
- `OLE32!CoTaskMemFree` at `0x18002c96b`
- `OLE32!CoTaskMemFree` at `0x18002c96b`

## pseudocode

```c
__int64 __fastcall AutoCalloutParameterLock::Pin(AutoCalloutParameterLock *this, char a2)
{
  unsigned int v2; // r15d
  unsigned int v3; // ebx
  __int128 v6; // xmm6
  AutoVariantRef *v7; // rdi
  __int16 *v8; // rax
  __int16 v9; // cx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  char *v14; // rax
  _QWORD *v15; // rsi
  int v17; // r14d
  int v18; // r9d
  int v19; // r9d
  bool v20; // al
  __int64 *v21; // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int128 v24; // [rsp+20h] [rbp-58h]
  __int128 v25; // [rsp+30h] [rbp-48h]

  v2 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 6) )
  {
    while ( 1 )
    {
      v6 = 0;
      v7 = (AutoVariantRef *)(*((_QWORD *)this + 2) + 32LL * v3);
      DWORD1(v24) = 0;
      v25 = 0;
      if ( *(_WORD *)v7 != 16396 )
        break;
      v8 = (__int16 *)*((_QWORD *)v7 + 1);
      v9 = *v8;
      if ( *v8 == 8 )
      {
        v10 = *((_QWORD *)v8 + 1);
        if ( !v10 )
          goto LABEL_9;
        v11 = 0;
        v12 = 0;
      }
      else
      {
        if ( v9 != 9 && v9 != 13 )
        {
          if ( v9 == 24588 )
          {
            v21 = (__int64 *)*((_QWORD *)v8 + 1);
            if ( !v21 )
              goto LABEL_9;
            v10 = *v21;
            if ( !v10 )
              goto LABEL_9;
          }
          else
          {
            if ( (v9 & 0x6000) != 0x2000 )
              goto LABEL_9;
            v10 = *((_QWORD *)v8 + 1);
            if ( !v10 )
              goto LABEL_9;
          }
          goto LABEL_34;
        }
        v10 = *((_QWORD *)v8 + 1);
        if ( !v10 )
          goto LABEL_9;
        v11 = 2;
        v12 = 0;
      }
LABEL_6:
      v13 = *((_QWORD *)v7 + 3);
      *((_QWORD *)&v24 + 1) = v10;
      LODWORD(v24) = v11;
      if ( !v13 || (v18 = *(_DWORD *)(v13 + 8), v18 != v11) )
      {
LABEL_7:
        v14 = (char *)CoTaskMemAlloc(0x28u);
        v15 = v14;
        if ( v14 )
        {
          *(_OWORD *)(v14 + 8) = v24;
          *(_OWORD *)(v14 + 24) = v6;
          v17 = AutoVariantRef::PinnableData::Pin((AutoVariantRef::PinnableData *)(v14 + 8));
          if ( v17 < 0 )
          {
            CoTaskMemFree(v15);
            if ( a2 )
              AutoVariantRef::ClearCurrentPinnableData(v7);
            v2 = v17;
          }
          else
          {
            *v15 = *((_QWORD *)v7 + 3);
            *((_QWORD *)v7 + 3) = v15;
          }
        }
        else
        {
          v2 = -2147024882;
        }
        goto LABEL_9;
      }
      if ( !v18 )
        goto LABEL_17;
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          goto LABEL_7;
LABEL_17:
        v20 = *(_QWORD *)(v13 + 16) == v10;
        goto LABEL_18;
      }
      v23 = *(_QWORD *)(v13 + 16);
      v20 = v23 == v10 && (!v23 || *(_QWORD *)(v13 + 24) == v12);
LABEL_18:
      if ( !v20 )
        goto LABEL_7;
LABEL_9:
      if ( ++v3 >= *((_DWORD *)this + 6) )
        return v2;
    }
    if ( *(_WORD *)v7 != 24588 )
      goto LABEL_9;
    v22 = (__int64 *)*((_QWORD *)v7 + 1);
    if ( !v22 )
      goto LABEL_9;
    v10 = *v22;
    if ( !v10 )
      goto LABEL_9;
LABEL_34:
    v12 = *(_QWORD *)(v10 + 16);
    v11 = 1;
    *(_QWORD *)&v25 = v12;
    v6 = v25;
    goto LABEL_6;
  }
  return v2;
}

```

## disassembly

```asm
0x18002c730  mov     rax, rsp
0x18002c733  push    rbx
0x18002c734  push    rbp
0x18002c735  push    r12
0x18002c737  push    r15
0x18002c739  sub     rsp, 58h
0x18002c73d  xor     r15d, r15d
0x18002c740  xor     ebx, ebx
0x18002c742  movzx   r12d, dl
0x18002c746  mov     rbp, rcx
0x18002c749  cmp     [rcx+18h], ebx
0x18002c74c  jbe     loc_18002C832
0x18002c752  mov     [rax+10h], rdi
0x18002c756  mov     edx, 600Ch
0x18002c75b  mov     [rax+18h], r13
0x18002c75f  mov     r8d, 6000h
0x18002c765  movaps  xmmword ptr [rax-38h], xmm6
0x18002c769  mov     r13d, 400Ch
0x18002c76f  mov     [rax+8], rsi
0x18002c773  mov     r9d, 2000h
0x18002c779  mov     [rax-28h], r14
0x18002c77d  nop     dword ptr [rax]
0x18002c780  xorps   xmm6, xmm6
0x18002c783  mov     edi, ebx
0x18002c785  shl     rdi, 5
0x18002c789  add     rdi, [rbp+10h]
0x18002c78d  movups  [rsp+78h+var_58], xmm6
0x18002c792  movups  [rsp+78h+var_48], xmm6
0x18002c797  movzx   eax, word ptr [rdi]
0x18002c79a  cmp     ax, r13w
0x18002c79e  jnz     loc_18002C90C
0x18002c7a4  mov     rax, [rdi+8]
0x18002c7a8  movzx   ecx, word ptr [rax]
0x18002c7ab  cmp     cx, 8
0x18002c7af  jnz     loc_18002C8A7
0x18002c7b5  mov     rcx, [rax+8]
0x18002c7b9  test    rcx, rcx
0x18002c7bc  jz      short loc_18002C805
0x18002c7be  xor     eax, eax
0x18002c7c0  movq    r8, xmm6
0x18002c7c5  mov     rdx, [rdi+18h]
0x18002c7c9  mov     qword ptr [rsp+78h+var_58+8], rcx
0x18002c7ce  mov     dword ptr [rsp+78h+var_58], eax
0x18002c7d2  test    rdx, rdx
0x18002c7d5  jnz     loc_18002C86D
0x18002c7db  mov     ecx, 28h ; '('; cb
0x18002c7e0  call    cs:__imp_CoTaskMemAlloc
0x18002c7e6  mov     rsi, rax
0x18002c7e9  test    rax, rax
0x18002c7ec  jnz     short loc_18002C840
0x18002c7ee  mov     r15d, 8007000Eh
0x18002c7f4  mov     edx, 600Ch
0x18002c7f9  mov     r8d, 6000h
0x18002c7ff  mov     r9d, 2000h
0x18002c805  inc     ebx
0x18002c807  cmp     ebx, [rbp+18h]
0x18002c80a  jb      loc_18002C780
0x18002c810  movaps  xmm6, [rsp+78h+var_38]
0x18002c815  mov     r14, [rsp+78h+var_28]
0x18002c81a  mov     r13, [rsp+78h+arg_10]
0x18002c822  mov     rdi, [rsp+78h+arg_8]
0x18002c82a  mov     rsi, [rsp+78h+arg_0]
0x18002c832  mov     eax, r15d
0x18002c835  add     rsp, 58h
0x18002c839  pop     r15
0x18002c83b  pop     r12
0x18002c83d  pop     rbp
0x18002c83e  pop     rbx
0x18002c83f  retn
0x18002c840  movups  xmm0, [rsp+78h+var_58]
0x18002c845  lea     rcx, [rax+8]; this
0x18002c849  movups  xmmword ptr [rcx], xmm0
0x18002c84c  movups  xmmword ptr [rcx+10h], xmm6
0x18002c850  call    ?Pin@PinnableData@AutoVariantRef@@QEAAJXZ; AutoVariantRef::PinnableData::Pin(void)
0x18002c855  mov     r14d, eax
0x18002c858  test    eax, eax
0x18002c85a  js      loc_18002C968
0x18002c860  mov     rax, [rdi+18h]
0x18002c864  mov     [rsi], rax
0x18002c867  mov     [rdi+18h], rsi
0x18002c86b  jmp     short loc_18002C7F4
0x18002c86d  mov     r9d, [rdx+8]
0x18002c871  cmp     r9d, eax
0x18002c874  jnz     loc_18002C7DB
0x18002c87a  test    r9d, r9d
0x18002c87d  jz      short loc_18002C893
0x18002c87f  sub     r9d, 1
0x18002c883  jz      loc_18002C946
0x18002c889  cmp     r9d, 1
0x18002c88d  jnz     loc_18002C7DB
0x18002c893  cmp     [rdx+10h], rcx
0x18002c897  setz    al
0x18002c89a  test    al, al
0x18002c89c  jz      loc_18002C7DB
0x18002c8a2  jmp     loc_18002C7F4
0x18002c8a7  cmp     cx, 9
0x18002c8ab  jz      short loc_18002C8F0
0x18002c8ad  cmp     cx, 0Dh
0x18002c8b1  jz      short loc_18002C8F0
0x18002c8b3  cmp     cx, dx
0x18002c8b6  jnz     short loc_18002C8D3
0x18002c8b8  mov     rcx, [rax+8]
0x18002c8bc  test    rcx, rcx
0x18002c8bf  jz      loc_18002C805
0x18002c8c5  mov     rcx, [rcx]
0x18002c8c8  test    rcx, rcx
0x18002c8cb  jz      loc_18002C805
0x18002c8d1  jmp     short loc_18002C92E
0x18002c8d3  and     cx, r8w
0x18002c8d7  cmp     cx, r9w
0x18002c8db  jnz     loc_18002C805
0x18002c8e1  mov     rcx, [rax+8]
0x18002c8e5  test    rcx, rcx
0x18002c8e8  jz      loc_18002C805
0x18002c8ee  jmp     short loc_18002C92E
0x18002c8f0  mov     rcx, [rax+8]
0x18002c8f4  test    rcx, rcx
0x18002c8f7  jz      loc_18002C805
0x18002c8fd  mov     eax, 2
0x18002c902  movq    r8, xmm6
0x18002c907  jmp     loc_18002C7C5
0x18002c90c  cmp     ax, dx
0x18002c90f  jnz     loc_18002C805
0x18002c915  mov     rcx, [rdi+8]
0x18002c919  test    rcx, rcx
0x18002c91c  jz      loc_18002C805
0x18002c922  mov     rcx, [rcx]
0x18002c925  test    rcx, rcx
0x18002c928  jz      loc_18002C805
0x18002c92e  mov     r8, [rcx+10h]
0x18002c932  mov     eax, 1
0x18002c937  mov     qword ptr [rsp+78h+var_48], r8
0x18002c93c  movups  xmm6, [rsp+78h+var_48]
0x18002c941  jmp     loc_18002C7C5
0x18002c946  mov     rax, [rdx+10h]
0x18002c94a  cmp     rax, rcx
0x18002c94d  jnz     short loc_18002C961
0x18002c94f  test    rax, rax
0x18002c952  jz      short loc_18002C95A
0x18002c954  cmp     [rdx+18h], r8
0x18002c958  jnz     short loc_18002C961
0x18002c95a  mov     al, 1
0x18002c95c  jmp     loc_18002C89A
0x18002c961  xor     al, al
0x18002c963  jmp     loc_18002C89A
0x18002c968  mov     rcx, rsi; pv
0x18002c96b  call    cs:__imp_CoTaskMemFree
0x18002c971  test    r12b, r12b
0x18002c974  jz      short loc_18002C97E
0x18002c976  mov     rcx, rdi; this
0x18002c979  call    ?ClearCurrentPinnableData@AutoVariantRef@@AEAAXXZ; AutoVariantRef::ClearCurrentPinnableData(void)
0x18002c97e  mov     r15d, r14d
0x18002c981  jmp     loc_18002C7F4
```
