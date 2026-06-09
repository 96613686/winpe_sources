# CCipherMill::LoadProviderList(uchar *)

- ea: `0x180044390`
- end: `0x18004451f`
- name: `?LoadProviderList@CCipherMill@@AEAAKPEAE@Z`
- size: `399`
- prototype: `unsigned int __fastcall(CCipherMill *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043f78`

## callees

- `0x180044390`
- `0x180073fe8`

## import_xrefs

- `ncrypt!SslEnumProtocolProviders` at `0x1800443cb`
- `ncrypt!SslEnumProtocolProviders` at `0x1800443cb`
- `ncrypt!SslOpenProvider` at `0x1800444c3`
- `ncrypt!SslOpenProvider` at `0x1800444c3`
- `ncrypt!SslFreeBuffer` at `0x180044500`
- `ncrypt!SslFreeBuffer` at `0x180044500`

## pseudocode

```c
__int64 __fastcall CCipherMill::LoadProviderList(CCipherMill *this, unsigned __int8 *a2)
{
  CCipherMill *v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // r8d
  char i; // r9
  unsigned int v9; // r14d
  unsigned __int16 *v10; // r11
  __int64 v11; // r15
  int v12; // eax
  int v13; // ebp
  __int64 v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v18; // [rsp+50h] [rbp+8h] BYREF
  int v19; // [rsp+54h] [rbp+Ch]
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  v19 = HIDWORD(this);
  *a2 = 0;
  v18 = 0;
  v20 = 0;
  v4 = SslEnumProtocolProviders(&v18, &v20, 0);
  if ( !v4 )
  {
    v3 = (CCipherMill *)v18;
    if ( v18 - 1 <= 0x1F )
    {
      v5 = v4 + 1;
      if ( v18 == qword_1800AE498 )
      {
        v6 = v20;
        v7 = 0;
        for ( i = v4 + 1; v7 < v18; v7 += v5 )
        {
          if ( !i )
            break;
          i = 0;
          if ( qword_1800AE498 )
          {
            v9 = 0;
            do
            {
              if ( i )
                break;
              v10 = *(unsigned __int16 **)(v20 + 16LL * v7);
              v11 = *(_QWORD *)(qword_1800AE490 + 16LL * v9) - (_QWORD)v10;
              do
              {
                v12 = *(unsigned __int16 *)((char *)v10 + v11);
                v13 = *v10 - v12;
                if ( v13 )
                  break;
                ++v10;
              }
              while ( v12 );
              i = 0;
              if ( !v13 )
                i = v4 + 1;
              v9 += v5;
            }
            while ( v9 < qword_1800AE498 );
          }
        }
        if ( v7 != v18 )
          *a2 = v5;
        if ( !*a2 )
        {
LABEL_26:
          v4 = 0;
          goto LABEL_29;
        }
      }
      else
      {
        *a2 = v5;
      }
      CCipherMill::DeleteProviderList(v3);
      v3 = (CCipherMill *)v20;
      v14 = 0;
      v15 = v18;
      qword_1800AE490 = v20;
      qword_1800AE498 = v18;
      v20 = 0;
      while ( (unsigned int)v14 < v15 )
      {
        v16 = *((_QWORD *)v3 + 2 * (unsigned int)v14);
        if ( !v16 )
          goto LABEL_27;
        v4 = SslOpenProvider(&qword_1800AE4A0 + v14, v16, 0);
        if ( v4 )
          goto LABEL_28;
        v15 = qword_1800AE498;
        v14 = v5 + (unsigned int)v14;
        v3 = (CCipherMill *)qword_1800AE490;
      }
      v6 = v20;
      goto LABEL_26;
    }
LABEL_27:
    v4 = 1359;
  }
LABEL_28:
  CCipherMill::DeleteProviderList(v3);
  v6 = v20;
LABEL_29:
  if ( v6 )
    SslFreeBuffer(v6);
  return v4;
}

```

## disassembly

```asm
0x180044390  mov     rax, rsp
0x180044393  mov     [rax+18h], rbx
0x180044397  mov     [rax+20h], rbp
0x18004439b  mov     [rax+8], rcx
0x18004439f  push    rsi
0x1800443a0  push    rdi
0x1800443a1  push    r12
0x1800443a3  push    r14
0x1800443a5  push    r15
0x1800443a7  sub     rsp, 20h
0x1800443ab  mov     rsi, rdx
0x1800443ae  mov     byte ptr [rdx], 0
0x1800443b1  lea     rdx, [rax+10h]
0x1800443b5  mov     dword ptr [rax+8], 0
0x1800443bc  xor     r8d, r8d
0x1800443bf  mov     qword ptr [rax+10h], 0
0x1800443c7  lea     rcx, [rax+8]
0x1800443cb  call    cs:__imp_SslEnumProtocolProviders
0x1800443d1  mov     ebx, eax
0x1800443d3  test    eax, eax
0x1800443d5  jnz     loc_1800444EE
0x1800443db  mov     ecx, dword ptr [rsp+48h+arg_0]; this
0x1800443df  lea     eax, [rcx-1]
0x1800443e2  cmp     eax, 1Fh
0x1800443e5  ja      loc_1800444E9
0x1800443eb  mov     r10d, dword ptr cs:qword_1800AE498
0x1800443f2  lea     edi, [rbx+1]
0x1800443f5  cmp     ecx, r10d
0x1800443f8  jz      short loc_1800443FF
0x1800443fa  mov     [rsi], dil
0x1800443fd  jmp     short loc_18004447D
0x1800443ff  mov     rdx, [rsp+48h+arg_8]
0x180044404  xor     r8d, r8d
0x180044407  mov     r9b, dil
0x18004440a  test    ecx, ecx
0x18004440c  jz      short loc_180044470
0x18004440e  mov     r12, cs:qword_1800AE490
0x180044415  test    r9b, r9b
0x180044418  jz      short loc_180044470
0x18004441a  xor     r9b, r9b
0x18004441d  test    r10d, r10d
0x180044420  jz      short loc_180044468
0x180044422  xor     r14d, r14d
0x180044425  mov     ebx, r8d
0x180044428  add     rbx, rbx
0x18004442b  test    r9b, r9b
0x18004442e  jnz     short loc_180044468
0x180044430  mov     r11, [rdx+rbx*8]
0x180044434  mov     eax, r14d
0x180044437  add     rax, rax
0x18004443a  mov     r15, [r12+rax*8]
0x18004443e  sub     r15, r11
0x180044441  movzx   ebp, word ptr [r11]
0x180044445  movzx   eax, word ptr [r11+r15]
0x18004444a  sub     ebp, eax
0x18004444c  jnz     short loc_180044456
0x18004444e  add     r11, 2
0x180044452  test    eax, eax
0x180044454  jnz     short loc_180044441
0x180044456  test    ebp, ebp
0x180044458  movzx   r9d, r9b
0x18004445c  cmovz   r9d, edi
0x180044460  add     r14d, edi
0x180044463  cmp     r14d, r10d
0x180044466  jb      short loc_18004442B
0x180044468  add     r8d, edi
0x18004446b  cmp     r8d, ecx
0x18004446e  jb      short loc_180044415
0x180044470  cmp     r8d, ecx
0x180044473  jz      short loc_180044478
0x180044475  mov     [rsi], dil
0x180044478  cmp     byte ptr [rsi], 0
0x18004447b  jz      short loc_1800444E5
0x18004447d  call    ?DeleteProviderList@CCipherMill@@AEAAXXZ; CCipherMill::DeleteProviderList(void)
0x180044482  mov     rcx, [rsp+48h+arg_8]
0x180044487  xor     esi, esi
0x180044489  mov     eax, dword ptr [rsp+48h+arg_0]
0x18004448d  mov     cs:qword_1800AE490, rcx
0x180044494  mov     dword ptr cs:qword_1800AE498, eax
0x18004449a  mov     [rsp+48h+arg_8], 0
0x1800444a3  cmp     esi, eax
0x1800444a5  jnb     short loc_1800444E0
0x1800444a7  mov     eax, esi
0x1800444a9  add     rax, rax
0x1800444ac  mov     rdx, [rcx+rax*8]
0x1800444b0  test    rdx, rdx
0x1800444b3  jz      short loc_1800444E9
0x1800444b5  lea     rax, qword_1800AE4A0
0x1800444bc  xor     r8d, r8d
0x1800444bf  lea     rcx, [rax+rsi*8]
0x1800444c3  call    cs:__imp_SslOpenProvider
0x1800444c9  mov     ebx, eax
0x1800444cb  test    eax, eax
0x1800444cd  jnz     short loc_1800444EE
0x1800444cf  mov     eax, dword ptr cs:qword_1800AE498
0x1800444d5  add     esi, edi
0x1800444d7  mov     rcx, cs:qword_1800AE490
0x1800444de  jmp     short loc_1800444A3
0x1800444e0  mov     rdx, [rsp+48h+arg_8]
0x1800444e5  xor     ebx, ebx
0x1800444e7  jmp     short loc_1800444F8
0x1800444e9  mov     ebx, 54Fh
0x1800444ee  call    ?DeleteProviderList@CCipherMill@@AEAAXXZ; CCipherMill::DeleteProviderList(void)
0x1800444f3  mov     rdx, [rsp+48h+arg_8]
0x1800444f8  test    rdx, rdx
0x1800444fb  jz      short loc_180044506
0x1800444fd  mov     rcx, rdx
0x180044500  call    cs:__imp_SslFreeBuffer
0x180044506  mov     rbp, [rsp+48h+arg_18]
0x18004450b  mov     eax, ebx
0x18004450d  mov     rbx, [rsp+48h+arg_10]
0x180044512  add     rsp, 20h
0x180044516  pop     r15
0x180044518  pop     r14
0x18004451a  pop     r12
0x18004451c  pop     rdi
0x18004451d  pop     rsi
0x18004451e  retn
```
