# YReader::ProcessAttributesN(void)

- ea: `0x10040ae50`
- end: `0x10040b222`
- name: `?ProcessAttributesN@YReader@@AEAAXXZ`
- size: `978`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x100407840`
- `0x1004079d0`

## callees

- `0x100401780`
- `0x10040ae50`
- `0x10040c550`
- `0x10040c7b0`
- `0x1004157a0`
- `0x100425d50`
- `0x1004277a0`
- `0x1004394f0`

## pseudocode

```c
void __fastcall YReader::ProcessAttributesN(YReader *this)
{
  __int64 v1; // r12
  __int64 v3; // rsi
  unsigned int v4; // ecx
  const void *v5; // rbp
  unsigned int v6; // edx
  void *v7; // rcx
  size_t v8; // r8
  const void *v9; // rdx
  unsigned __int64 v10; // r15
  unsigned int *v11; // rsi
  unsigned __int64 v12; // r12
  _DWORD *v13; // rdi
  __int64 v14; // rdx
  int v15; // ebp
  unsigned int *v16; // rbx
  unsigned int v17; // ecx
  unsigned int v18; // ebx
  unsigned int v19; // ebp
  __int64 v20; // rdi
  __int64 v21; // rdx
  unsigned __int16 *v22; // rcx
  int v23; // r8d
  int v24; // edx
  unsigned __int16 *i; // r9
  int v26; // eax
  unsigned __int16 *v27; // rax
  __int64 v28; // r15
  unsigned __int16 *j; // r9
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rsi
  __int64 v35; // rbx
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // [rsp+60h] [rbp+8h]
  int v39; // [rsp+68h] [rbp+10h]
  __int64 v40; // [rsp+70h] [rbp+18h]

  v1 = *((unsigned int *)this + 710);
  if ( (_DWORD)v1 )
  {
    if ( (unsigned int)v1 > 0x14 )
    {
      v18 = v1 + ((unsigned int)v1 >> 2);
      v38 = v18;
      if ( v18 < (unsigned int)v1 || !v18 )
      {
        v18 = -1;
        v38 = -1;
        if ( (_DWORD)v1 == -1 )
        {
          MXRRaiseException(-2147352566);
          __debugbreak();
        }
      }
      memset(*((void **)this + 1022), 0, 4LL * *((unsigned int *)this + 2047));
      if ( *((_DWORD *)this + 2047) < v18 )
      {
        _mm_lfence();
        _stack<unsigned int,16>::grow((char *)this + 8160, v18);
      }
      _mm_lfence();
      v19 = 0;
      do
      {
        v20 = *((_QWORD *)this + 354) + 152LL * v19;
        v21 = *(unsigned int *)(v20 + 24);
        if ( (_DWORD)v21 )
        {
          *(_QWORD *)(v20 + 48) = *(_QWORD *)v20 + 2 * (v21 + 1);
          *(_DWORD *)(v20 + 56) = *(_DWORD *)(v20 + 8) - v21 - 1;
          if ( !NamespaceSupport::ProcessPrefix(
                  (YReader *)((char *)this + 512),
                  (struct StringPtr *)(v20 + 16),
                  (struct StringPtr *)(v20 + 32)) )
          {
LABEL_53:
            MXRRaiseException(-1072894363);
            JUMPOUT(0x10040B221LL);
          }
        }
        else
        {
          *(_OWORD *)(v20 + 48) = *(_OWORD *)v20;
          *(_OWORD *)(v20 + 32) = CodeStringPtr::empty;
        }
        v22 = *(unsigned __int16 **)(v20 + 48);
        v23 = *((_DWORD *)this + 702);
        v24 = v23;
        for ( i = &v22[*(unsigned int *)(v20 + 56)]; v22 < i; v24 = v26 ^ (33 * v24) )
          v26 = *v22++;
        v27 = *(unsigned __int16 **)(v20 + 32);
        v28 = *(unsigned int *)(v20 + 40);
        for ( j = &v27[v28]; v27 < j; v23 = v30 ^ (33 * v23) )
          v30 = *v27++;
        v31 = (v24 ^ (unsigned int)v23) % v18;
        v32 = 4 * v31;
        v33 = *(_DWORD *)(4LL * (unsigned int)v31 + *((_QWORD *)this + 1022));
        v40 = 4LL * (unsigned int)v31;
        v39 = v33;
        if ( v33 )
        {
          v34 = *((_QWORD *)this + 354);
          do
          {
            v35 = v34 + 152LL * (unsigned int)(v33 - 1);
            v36 = *(_DWORD *)(v35 + 40);
            if ( v36 == (_DWORD)v28 && !memcmp(*(const void **)(v35 + 32), *(const void **)(v20 + 32), 2LL * v36) )
            {
              v37 = *(_DWORD *)(v35 + 56);
              if ( v37 == *(_DWORD *)(v20 + 56)
                && !memcmp(*(const void **)(v35 + 48), *(const void **)(v20 + 48), 2LL * v37) )
              {
                goto LABEL_52;
              }
            }
            v33 = *(_DWORD *)(v35 + 144);
          }
          while ( v33 );
          v18 = v38;
          v32 = v40;
        }
        ++v19;
        *(_DWORD *)(v20 + 144) = v39;
        *(_DWORD *)(v32 + *((_QWORD *)this + 1022)) = v19;
      }
      while ( v19 < (unsigned int)v1 );
    }
    else
    {
      v10 = *((_QWORD *)this + 354);
      v11 = (unsigned int *)v10;
      v12 = v10 + 152 * v1;
      if ( v10 < v12 )
      {
        v13 = (_DWORD *)(v10 + 56);
        while ( 1 )
        {
          v14 = (unsigned int)*(v13 - 8);
          if ( (_DWORD)v14 )
          {
            *((_QWORD *)v13 - 1) = *(_QWORD *)v11 + 2 * (v14 + 1);
            *v13 = *(v13 - 12) - v14 - 1;
            if ( !NamespaceSupport::ProcessPrefix(
                    (YReader *)((char *)this + 512),
                    (struct StringPtr *)(v13 - 10),
                    (struct StringPtr *)(v13 - 6)) )
              goto LABEL_53;
          }
          else
          {
            *(_OWORD *)(v13 - 2) = *(_OWORD *)v11;
            *(_OWORD *)(v13 - 6) = CodeStringPtr::empty;
          }
          if ( v10 < (unsigned __int64)v11 )
            break;
LABEL_23:
          v11 += 38;
          v13 += 38;
          if ( (unsigned __int64)v11 >= v12 )
            goto LABEL_3;
        }
        v15 = *v13;
        v16 = (unsigned int *)(v10 + 40);
        while ( 1 )
        {
          v17 = v16[4];
          if ( v17 == v15
            && !memcmp(*((const void **)v16 + 1), *((const void **)v13 - 1), 2LL * v17)
            && *v16 == *(v13 - 4)
            && !memcmp(*((const void **)v16 - 1), *((const void **)v13 - 3), 2LL * *v16) )
          {
            break;
          }
          v16 += 38;
          if ( v16 - 10 >= v11 )
            goto LABEL_23;
        }
LABEL_52:
        MXRRaiseException(-1072894404);
        __debugbreak();
      }
    }
  }
  else if ( !*((_DWORD *)this + 1326) )
  {
    return;
  }
LABEL_3:
  v3 = *((unsigned int *)this + 1326);
  if ( (_DWORD)v3 )
  {
    v4 = *((_DWORD *)this + 710);
    v5 = (const void *)*((_QWORD *)this + 662);
    v6 = v4 + v3;
    if ( *((_BYTE *)this + 1792) )
    {
      if ( *((_DWORD *)this + 711) < v6 )
      {
        _mm_lfence();
        _stack<Attribute,16>::grow((char *)this + 2816);
        v4 = *((_DWORD *)this + 710);
      }
      memmove((void *)(152 * v3 + *((_QWORD *)this + 354)), *((const void **)this + 354), 152LL * v4);
      v7 = (void *)*((_QWORD *)this + 354);
      v8 = 152 * v3;
      v9 = v5;
    }
    else
    {
      if ( *((_DWORD *)this + 711) < v6 )
      {
        _mm_lfence();
        _stack<Attribute,16>::grow((char *)this + 2816);
        v4 = *((_DWORD *)this + 710);
      }
      v9 = v5;
      v8 = 152 * v3;
      v7 = (void *)(*((_QWORD *)this + 354) + 152LL * v4);
    }
    memmove(v7, v9, v8);
    *((_DWORD *)this + 710) += v3;
  }
}

```

## disassembly

```asm
0x10040ae50  mov     [rsp+arg_18], rbx
0x10040ae55  push    rbp
0x10040ae56  push    rsi
0x10040ae57  push    rdi
0x10040ae58  push    r12
0x10040ae5a  push    r13
0x10040ae5c  push    r14
0x10040ae5e  push    r15
0x10040ae60  sub     rsp, 20h
0x10040ae64  mov     r12d, [rcx+0B18h]
0x10040ae6b  mov     r13, rcx
0x10040ae6e  test    r12d, r12d
0x10040ae71  jnz     loc_10040AF04
0x10040ae77  cmp     [rcx+14B8h], r12d
0x10040ae7e  jz      short loc_10040AEEF
0x10040ae80  mov     esi, [r13+14B8h]
0x10040ae87  test    esi, esi
0x10040ae89  jz      short loc_10040AEEF
0x10040ae8b  cmp     byte ptr [r13+700h], 0
0x10040ae93  lea     rdi, [r13+0B00h]
0x10040ae9a  mov     ecx, [rdi+18h]
0x10040ae9d  mov     rbp, [r13+14B0h]
0x10040aea4  lea     edx, [rcx+rsi]
0x10040aea7  jz      loc_10040B1D2
0x10040aead  cmp     [rdi+1Ch], edx
0x10040aeb0  jnb     short loc_10040AEC0
0x10040aeb2  lfence
0x10040aeb5  mov     rcx, rdi
0x10040aeb8  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040aebd  mov     ecx, [rdi+18h]
0x10040aec0  mov     rdx, [rdi+10h]; Src
0x10040aec4  mov     eax, ecx
0x10040aec6  imul    rbx, rsi, 98h
0x10040aecd  imul    r8, rax, 98h; Size
0x10040aed4  lea     rcx, [rbx+rdx]; void *
0x10040aed8  call    memmove
0x10040aedd  mov     rcx, [rdi+10h]; void *
0x10040aee1  mov     r8, rbx; Size
0x10040aee4  mov     rdx, rbp; Src
0x10040aee7  call    memmove
0x10040aeec  add     [rdi+18h], esi
0x10040aeef  mov     rbx, [rsp+58h+arg_18]
0x10040aef4  add     rsp, 20h
0x10040aef8  pop     r15
0x10040aefa  pop     r14
0x10040aefc  pop     r13
0x10040aefe  pop     r12
0x10040af00  pop     rdi
0x10040af01  pop     rsi
0x10040af02  pop     rbp
0x10040af03  retn
0x10040af04  cmp     r12d, 14h
0x10040af08  ja      loc_10040AFFC
0x10040af0e  mov     r15, [rcx+0B10h]
0x10040af15  imul    r12, 98h
0x10040af1c  mov     rsi, r15
0x10040af1f  add     r12, r15
0x10040af22  cmp     r15, r12
0x10040af25  jnb     loc_10040AE80
0x10040af2b  lea     rdi, [r15+38h]
0x10040af2f  nop
0x10040af30  mov     edx, [rdi-20h]
0x10040af33  test    edx, edx
0x10040af35  jnz     short loc_10040AF4B
0x10040af37  movups  xmm0, xmmword ptr [rsi]
0x10040af3a  movups  xmmword ptr [rdi-8], xmm0
0x10040af3e  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040af45  movups  xmmword ptr [rdi-18h], xmm1
0x10040af49  jmp     short loc_10040AF7F
0x10040af4b  mov     rax, [rsi]
0x10040af4e  lea     rcx, [rdx+1]
0x10040af52  lea     r8, [rdi-18h]; struct StringPtr *
0x10040af56  lea     rcx, [rax+rcx*2]
0x10040af5a  mov     [rdi-8], rcx
0x10040af5e  lea     rcx, [r13+200h]; this
0x10040af65  mov     eax, [rdi-30h]
0x10040af68  sub     eax, edx
0x10040af6a  lea     rdx, [rdi-28h]; struct StringPtr *
0x10040af6e  dec     eax
0x10040af70  mov     [rdi], eax
0x10040af72  call    ?ProcessPrefix@NamespaceSupport@@QEAA_NPEAUStringPtr@@0@Z; NamespaceSupport::ProcessPrefix(StringPtr *,StringPtr *)
0x10040af77  test    al, al
0x10040af79  jz      loc_10040B217
0x10040af7f  cmp     r15, rsi
0x10040af82  jnb     short loc_10040AFE0
0x10040af84  mov     ebp, [rdi]
0x10040af86  lea     rbx, [r15+28h]
0x10040af8a  nop     word ptr [rax+rax+00h]
0x10040af90  mov     ecx, [rbx+10h]
0x10040af93  cmp     ecx, ebp
0x10040af95  jnz     short loc_10040AFD0
0x10040af97  mov     rdx, [rdi-8]; Buf2
0x10040af9b  mov     r8d, ecx
0x10040af9e  mov     rcx, [rbx+8]; Buf1
0x10040afa2  add     r8, r8; Size
0x10040afa5  call    memcmp
0x10040afaa  test    eax, eax
0x10040afac  jnz     short loc_10040AFD0
0x10040afae  mov     ecx, [rbx]
0x10040afb0  cmp     ecx, [rdi-10h]
0x10040afb3  jnz     short loc_10040AFD0
0x10040afb5  mov     rdx, [rdi-18h]; Buf2
0x10040afb9  mov     r8d, ecx
0x10040afbc  mov     rcx, [rbx-8]; Buf1
0x10040afc0  add     r8, r8; Size
0x10040afc3  call    memcmp
0x10040afc8  test    eax, eax
0x10040afca  jz      loc_10040B20C
0x10040afd0  add     rbx, 98h
0x10040afd7  lea     rax, [rbx-28h]
0x10040afdb  cmp     rax, rsi
0x10040afde  jb      short loc_10040AF90
0x10040afe0  add     rsi, 98h
0x10040afe7  add     rdi, 98h
0x10040afee  cmp     rsi, r12
0x10040aff1  jb      loc_10040AF30
0x10040aff7  jmp     loc_10040AE80
0x10040affc  mov     ebx, r12d
0x10040afff  shr     ebx, 2
0x10040b002  add     ebx, r12d
0x10040b005  mov     [rsp+58h+arg_0], ebx
0x10040b009  cmp     ebx, r12d
0x10040b00c  jb      short loc_10040B012
0x10040b00e  test    ebx, ebx
0x10040b010  jnz     short loc_10040B024
0x10040b012  mov     ebx, 0FFFFFFFFh
0x10040b017  mov     [rsp+58h+arg_0], ebx
0x10040b01b  cmp     r12d, ebx
0x10040b01e  jnb     loc_10040B201
0x10040b024  mov     r8d, [rcx+1FFCh]
0x10040b02b  xor     edx, edx; Val
0x10040b02d  mov     rcx, [rcx+1FF0h]; void *
0x10040b034  shl     r8, 2; Size
0x10040b038  call    memset
0x10040b03d  lea     rcx, [r13+1FE0h]
0x10040b044  cmp     [rcx+1Ch], ebx
0x10040b047  jnb     short loc_10040B053
0x10040b049  lfence
0x10040b04c  mov     edx, ebx
0x10040b04e  call    ?grow@?$_stack@I$0BA@@@AEAAXI@Z; _stack<uint,16>::grow(uint)
0x10040b053  lfence
0x10040b056  xor     ebp, ebp
0x10040b058  nop     dword ptr [rax+rax+00000000h]
0x10040b060  mov     eax, ebp
0x10040b062  imul    rdi, rax, 98h
0x10040b069  add     rdi, [r13+0B10h]
0x10040b070  mov     edx, [rdi+18h]
0x10040b073  test    edx, edx
0x10040b075  jnz     short loc_10040B08B
0x10040b077  movups  xmm0, xmmword ptr [rdi]
0x10040b07a  movups  xmmword ptr [rdi+30h], xmm0
0x10040b07e  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040b085  movups  xmmword ptr [rdi+20h], xmm1
0x10040b089  jmp     short loc_10040B0C0
0x10040b08b  mov     rax, [rdi]
0x10040b08e  lea     rcx, [rdx+1]
0x10040b092  lea     r8, [rdi+20h]; struct StringPtr *
0x10040b096  lea     rcx, [rax+rcx*2]
0x10040b09a  mov     [rdi+30h], rcx
0x10040b09e  lea     rcx, [r13+200h]; this
0x10040b0a5  mov     eax, [rdi+8]
0x10040b0a8  sub     eax, edx
0x10040b0aa  lea     rdx, [rdi+10h]; struct StringPtr *
0x10040b0ae  dec     eax
0x10040b0b0  mov     [rdi+38h], eax
0x10040b0b3  call    ?ProcessPrefix@NamespaceSupport@@QEAA_NPEAUStringPtr@@0@Z; NamespaceSupport::ProcessPrefix(StringPtr *,StringPtr *)
0x10040b0b8  test    al, al
0x10040b0ba  jz      loc_10040B217
0x10040b0c0  mov     rcx, [rdi+30h]
0x10040b0c4  mov     eax, [rdi+38h]
0x10040b0c7  mov     r8d, [r13+0AF8h]
0x10040b0ce  mov     edx, r8d
0x10040b0d1  lea     r9, [rcx+rax*2]
0x10040b0d5  cmp     rcx, r9
0x10040b0d8  jnb     short loc_10040B0F1
0x10040b0da  nop     word ptr [rax+rax+00h]
0x10040b0e0  movzx   eax, word ptr [rcx]
0x10040b0e3  add     rcx, 2
0x10040b0e7  imul    edx, 21h ; '!'
0x10040b0ea  xor     edx, eax
0x10040b0ec  cmp     rcx, r9
0x10040b0ef  jb      short loc_10040B0E0
0x10040b0f1  mov     rax, [rdi+20h]
0x10040b0f5  mov     r15d, [rdi+28h]
0x10040b0f9  lea     r9, [rax+r15*2]
0x10040b0fd  cmp     rax, r9
0x10040b100  jnb     short loc_10040B115
0x10040b102  movzx   ecx, word ptr [rax]
0x10040b105  add     rax, 2
0x10040b109  imul    r8d, 21h ; '!'
0x10040b10d  xor     r8d, ecx
0x10040b110  cmp     rax, r9
0x10040b113  jb      short loc_10040B102
0x10040b115  xor     r8d, edx
0x10040b118  xor     edx, edx
0x10040b11a  mov     eax, r8d
0x10040b11d  div     ebx
0x10040b11f  mov     rax, [r13+1FF0h]
0x10040b126  lea     rcx, ds:0[rdx*4]
0x10040b12e  mov     eax, [rcx+rax]
0x10040b131  mov     [rsp+58h+arg_10], rcx
0x10040b136  mov     [rsp+58h+arg_8], eax
0x10040b13a  test    eax, eax
0x10040b13c  jz      short loc_10040B1AE
0x10040b13e  mov     rsi, [r13+0B10h]
0x10040b145  nop     word ptr [rax+rax+00000000h]
0x10040b150  lea     ecx, [rax-1]
0x10040b153  imul    rbx, rcx, 98h
0x10040b15a  add     rbx, rsi
0x10040b15d  mov     eax, [rbx+28h]
0x10040b160  cmp     eax, r15d
0x10040b163  jnz     short loc_10040B19B
0x10040b165  mov     rdx, [rdi+20h]; Buf2
0x10040b169  mov     r8d, eax
0x10040b16c  mov     rcx, [rbx+20h]; Buf1
0x10040b170  add     r8, r8; Size
0x10040b173  call    memcmp
0x10040b178  test    eax, eax
0x10040b17a  jnz     short loc_10040B19B
0x10040b17c  mov     eax, [rbx+38h]
0x10040b17f  cmp     eax, [rdi+38h]
0x10040b182  jnz     short loc_10040B19B
0x10040b184  mov     rdx, [rdi+30h]; Buf2
0x10040b188  mov     r8d, eax
0x10040b18b  mov     rcx, [rbx+30h]; Buf1
0x10040b18f  add     r8, r8; Size
0x10040b192  call    memcmp
0x10040b197  test    eax, eax
0x10040b199  jz      short loc_10040B20C
0x10040b19b  mov     eax, [rbx+90h]
0x10040b1a1  test    eax, eax
0x10040b1a3  jnz     short loc_10040B150
0x10040b1a5  mov     ebx, [rsp+58h+arg_0]
0x10040b1a9  mov     rcx, [rsp+58h+arg_10]
0x10040b1ae  mov     eax, [rsp+58h+arg_8]
0x10040b1b2  inc     ebp
0x10040b1b4  mov     [rdi+90h], eax
0x10040b1ba  mov     rax, [r13+1FF0h]
0x10040b1c1  mov     [rcx+rax], ebp
0x10040b1c4  cmp     ebp, r12d
0x10040b1c7  jb      loc_10040B060
0x10040b1cd  jmp     loc_10040AE80
0x10040b1d2  cmp     [rdi+1Ch], edx
0x10040b1d5  jnb     short loc_10040B1E5
0x10040b1d7  lfence
0x10040b1da  mov     rcx, rdi
0x10040b1dd  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040b1e2  mov     ecx, [rdi+18h]
0x10040b1e5  mov     eax, ecx
0x10040b1e7  mov     rdx, rbp
0x10040b1ea  imul    rcx, rax, 98h
0x10040b1f1  imul    r8, rsi, 98h
0x10040b1f8  add     rcx, [rdi+10h]
0x10040b1fc  jmp     loc_10040AEE7
0x10040b201  mov     ecx, 8002000Ah; int
0x10040b206  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040b20b  int     3; Trap to Debugger
0x10040b20c  mov     ecx, 0C00CEE3Ch; int
0x10040b211  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040b216  int     3; Trap to Debugger
0x10040b217  mov     ecx, 0C00CEE65h; int
0x10040b21c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
