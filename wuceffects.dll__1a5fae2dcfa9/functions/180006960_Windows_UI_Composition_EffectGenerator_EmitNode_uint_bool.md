# Windows::UI::Composition::EffectGenerator::EmitNode(uint,bool)

- ea: `0x180006960`
- end: `0x180006e15`
- name: `?EmitNode@EffectGenerator@Composition@UI@Windows@@AEAAXI_N@Z`
- size: `1205`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006960`
- `0x180008320`

## callees

- `0x180006410`
- `0x180006960`
- `0x180006e1c`
- `0x180007100`
- `0x180007bc0`
- `0x180021060`
- `0x180021084`
- `0x1800257b8`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180006d13`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180006d13`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectGenerator::EmitNode(
        Windows::UI::Composition::EffectGenerator *this,
        unsigned int a2,
        bool a3)
{
  unsigned __int64 v4; // r13
  _DWORD *v5; // rcx
  unsigned int *v7; // rbp
  __int64 v8; // rbx
  unsigned int v9; // esi
  __int64 v10; // rdi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi
  const char *v13; // rbx
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // r15
  __int64 v18; // r12
  __int64 v19; // rcx
  _QWORD *v20; // rsi
  __int64 v21; // rbx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned __int64 v25; // rbx
  __int64 v26; // r14
  void *v27; // rcx
  unsigned __int64 v28; // rdx
  void *v29; // rcx
  unsigned __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 v32; // r15
  void *v33; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v34; // [rsp+38h] [rbp-70h] BYREF
  unsigned int v35; // [rsp+40h] [rbp-68h]
  void *v36; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int64 v37; // [rsp+60h] [rbp-48h]

  v4 = a2;
  v5 = *(_DWORD **)this;
  v35 = a2;
  if ( (__int64)(*((_QWORD *)v5 + 7) - *((_QWORD *)v5 + 6)) >> 3 <= (unsigned __int64)a2 )
    goto LABEL_37;
  _mm_lfence();
  v7 = *(unsigned int **)(*((_QWORD *)v5 + 6) + 8LL * a2);
  v8 = *(_QWORD *)v7;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 72LL))(*(_QWORD *)v7) )
  {
    **((_DWORD **)this + 1) |= 2u;
  }
  else if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 64LL))(v8) )
  {
    **((_DWORD **)this + 1) |= 4u;
  }
  else if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8) )
  {
    **((_DWORD **)this + 1) |= 0x10u;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 96LL))(v8) )
    **((_DWORD **)this + 1) |= 0x20u;
  v9 = v7[5];
  if ( v9 > 1 && !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 104LL))(v8, *((_QWORD *)v7 + 3)) )
  {
    a3 = 1;
    v10 = 0;
    while ( 1 )
    {
LABEL_10:
      v11 = (_DWORD *)(*((_QWORD *)v7 + 1) + 8 * v10);
      if ( *v11 == 1 )
      {
        Windows::UI::Composition::EffectGenerator::EmitNode(this, v11[1], a3);
      }
      else if ( *v11 == 2 )
      {
        v31 = *((_QWORD *)this + 3);
        v32 = (unsigned int)v11[1];
        *(_WORD *)((char *)&v33 + 1) = 0;
        BYTE3(v33) = 0;
        if ( (*((_QWORD *)this + 4) - v31) >> 3 <= v32 )
          goto LABEL_37;
        *(_BYTE *)(v31 + 8 * v32 + 6) |= a3;
      }
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= v9 )
        goto LABEL_13;
    }
  }
  v10 = 0;
  if ( v9 )
    goto LABEL_10;
LABEL_13:
  v12 = (_QWORD *)((char *)this + 224);
  v13 = (const char *)(**(__int64 (__fastcall ***)(__int64))v8)(v8);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    "    ",
    4u);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    "// ",
    3u);
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    v13,
    v14);
  v15 = *((_QWORD *)this + 32);
  if ( ((*((_BYTE *)this + 248) + (_BYTE)v15) & 0xF) == 0 && *((_QWORD *)this + 30) <= (unsigned __int64)(v15 + 16) >> 4 )
    std::deque<char>::_Growmap((char *)this + 224);
  v16 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 31) &= 16 * v16 - 1;
  v17 = *((_QWORD *)this + 32) + *((_QWORD *)this + 31);
  v18 = 8 * ((v17 >> 4) & (v16 - 1));
  if ( !*(_QWORD *)(v18 + *((_QWORD *)this + 29)) )
    *(_QWORD *)(v18 + *((_QWORD *)this + 29)) = operator new(0x10u);
  *(_BYTE *)((v17 & 0xF) + *(_QWORD *)(*((_QWORD *)this + 29) + 8 * ((v17 >> 4) & (*((_QWORD *)this + 30) - 1LL)))) = 10;
  ++*((_QWORD *)this + 32);
  v19 = *((_QWORD *)this + 6);
  if ( (*((_QWORD *)this + 7) - v19) >> 5 <= v4 )
  {
LABEL_37:
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  v20 = (_QWORD *)(v19 + 32 * v4);
  v21 = Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal((int)this + 88, (int)&v36, 69, (int)v13, 0);
  if ( v20 != (_QWORD *)v21 )
  {
    v22 = v20[3];
    if ( v22 > 0xF )
    {
      v27 = (void *)*v20;
      v28 = v22 + 1;
      v34 = v22 + 1;
      v33 = v27;
      if ( v22 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v33, &v34);
        v28 = v34;
        v27 = v33;
      }
      operator delete(v27, v28);
    }
    v20[2] = 0;
    v20[3] = 15;
    *(_BYTE *)v20 = 0;
    *(_OWORD *)v20 = *(_OWORD *)v21;
    *((_OWORD *)v20 + 1) = *(_OWORD *)(v21 + 16);
    *(_QWORD *)(v21 + 16) = 0;
    *(_QWORD *)(v21 + 24) = 15;
    *(_BYTE *)v21 = 0;
  }
  if ( v37 > 0xF )
  {
    v29 = v36;
    v30 = v37 + 1;
    v34 = v37 + 1;
    v33 = v36;
    if ( v37 + 1 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v33, &v34);
      v29 = v33;
      v30 = v34;
    }
    operator delete(v29, v30);
  }
  *((_DWORD *)this + 4) = v35;
  if ( v20[3] > 0xFu )
    v20 = (_QWORD *)*v20;
  (*(void (__fastcall **)(_QWORD, unsigned int *, Windows::UI::Composition::EffectGenerator *, _QWORD *))(**(_QWORD **)v7 + 160LL))(
    *(_QWORD *)v7,
    v7,
    this,
    v20);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    "    ",
    4u);
  v23 = *((_QWORD *)this + 32);
  if ( ((*((_BYTE *)this + 248) + (_BYTE)v23) & 0xF) == 0 && *((_QWORD *)this + 30) <= (unsigned __int64)(v23 + 16) >> 4 )
    std::deque<char>::_Growmap((char *)this + 224);
  v24 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 31) &= 16 * v24 - 1;
  v25 = *((_QWORD *)this + 32) + *((_QWORD *)this + 31);
  v26 = 8 * ((v25 >> 4) & (v24 - 1));
  if ( !*(_QWORD *)(v26 + v12[1]) )
    *(_QWORD *)(v26 + v12[1]) = operator new(0x10u);
  *(_BYTE *)((v25 & 0xF) + *(_QWORD *)(v12[1] + 8 * ((v25 >> 4) & (v12[2] - 1LL)))) = 10;
  ++v12[4];
}

```

## disassembly

```asm
0x180006960  mov     [rsp+arg_18], rbx
0x180006965  push    rbp
0x180006966  push    rsi
0x180006967  push    rdi
0x180006968  push    r12
0x18000696a  push    r13
0x18000696c  push    r14
0x18000696e  push    r15
0x180006970  sub     rsp, 70h
0x180006974  mov     rax, cs:__security_cookie
0x18000697b  xor     rax, rsp
0x18000697e  mov     [rsp+0A8h+var_40], rax
0x180006983  mov     r14, rcx
0x180006986  mov     r13d, edx
0x180006989  mov     rcx, [rcx]
0x18000698c  movzx   r12d, r8b
0x180006990  mov     [rsp+0A8h+var_68], edx
0x180006994  mov     rax, [rcx+38h]
0x180006998  sub     rax, [rcx+30h]
0x18000699c  sar     rax, 3
0x1800069a0  cmp     rax, r13
0x1800069a3  jbe     loc_180006D0C
0x1800069a9  lfence
0x1800069ac  mov     rax, [rcx+30h]
0x1800069b0  mov     rbp, [rax+r13*8]
0x1800069b4  mov     rbx, [rbp+0]
0x1800069b8  mov     rcx, rbx
0x1800069bb  mov     rax, [rbx]
0x1800069be  mov     rax, [rax+48h]
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  test    al, al
0x1800069c9  jnz     loc_180006D3F
0x1800069cf  mov     rax, [rbx]
0x1800069d2  mov     rcx, rbx
0x1800069d5  mov     rax, [rax+40h]
0x1800069d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069de  test    al, al
0x1800069e0  jnz     loc_180006DC1
0x1800069e6  mov     rax, [rbx]
0x1800069e9  mov     rcx, rbx
0x1800069ec  mov     rax, [rax+50h]
0x1800069f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f5  test    al, al
0x1800069f7  jnz     loc_180006DCD
0x1800069fd  mov     rax, [rbx]
0x180006a00  mov     rcx, rbx
0x180006a03  mov     rax, [rax+60h]
0x180006a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0c  test    al, al
0x180006a0e  jz      short loc_180006A17
0x180006a10  mov     rax, [r14+8]
0x180006a14  or      dword ptr [rax], 20h
0x180006a17  mov     esi, [rbp+14h]
0x180006a1a  cmp     esi, 1
0x180006a1d  ja      loc_180006D1A
0x180006a23  xor     edi, edi
0x180006a25  test    esi, esi
0x180006a27  jz      short loc_180006A52
0x180006a29  mov     rax, [rbp+8]
0x180006a2d  mov     ecx, [rax+rdi*8]
0x180006a30  lea     rdx, [rax+rdi*8]
0x180006a34  sub     ecx, 1
0x180006a37  jnz     loc_180006CDC
0x180006a3d  mov     edx, [rdx+4]; unsigned int
0x180006a40  movzx   r8d, r12b; bool
0x180006a44  mov     rcx, r14; this
0x180006a47  call    ?EmitNode@EffectGenerator@Composition@UI@Windows@@AEAAXI_N@Z; Windows::UI::Composition::EffectGenerator::EmitNode(uint,bool)
0x180006a4c  inc     edi
0x180006a4e  cmp     edi, esi
0x180006a50  jb      short loc_180006A29
0x180006a52  mov     rax, [rbx]
0x180006a55  mov     rcx, rbx
0x180006a58  mov     rax, [rax]
0x180006a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a60  lea     rdi, [r14+0E0h]
0x180006a67  mov     r8d, 4; unsigned __int64
0x180006a6d  mov     rcx, rdi; this
0x180006a70  lea     rdx, asc_18003403C; "    "
0x180006a77  mov     rbx, rax
0x180006a7a  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD_K@Z; Windows::UI::Composition::StringBuilder::Append(char const *,unsigned __int64)
0x180006a7f  mov     r8d, 3; unsigned __int64
0x180006a85  lea     rdx, asc_180034044; "// "
0x180006a8c  mov     rcx, rdi; this
0x180006a8f  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD_K@Z; Windows::UI::Composition::StringBuilder::Append(char const *,unsigned __int64)
0x180006a94  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006a9b  nop     dword ptr [rax+rax+00h]
0x180006aa0  inc     r8; unsigned __int64
0x180006aa3  cmp     byte ptr [rbx+r8], 0
0x180006aa8  jnz     short loc_180006AA0
0x180006aaa  mov     rdx, rbx; char *
0x180006aad  mov     rcx, rdi; this
0x180006ab0  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD_K@Z; Windows::UI::Composition::StringBuilder::Append(char const *,unsigned __int64)
0x180006ab5  mov     rcx, [rdi+20h]
0x180006ab9  movzx   eax, cl
0x180006abc  add     al, [rdi+18h]
0x180006abf  test    al, 0Fh
0x180006ac1  jz      loc_180006D79
0x180006ac7  mov     rdx, [rdi+10h]
0x180006acb  mov     rax, rdx
0x180006ace  shl     rax, 4
0x180006ad2  dec     rax
0x180006ad5  and     [rdi+18h], rax
0x180006ad9  lea     rax, [rdx-1]
0x180006add  mov     r15, [rdi+18h]
0x180006ae1  add     r15, [rdi+20h]
0x180006ae5  mov     rsi, r15
0x180006ae8  shr     rsi, 4
0x180006aec  and     rax, rsi
0x180006aef  lea     r12, ds:0[rax*8]
0x180006af7  mov     rax, [rdi+8]
0x180006afb  cmp     qword ptr [r12+rax], 0
0x180006b00  jz      loc_180006D4B
0x180006b06  mov     rcx, [rdi+10h]
0x180006b0a  and     r15d, 0Fh
0x180006b0e  mov     rax, [rdi+8]
0x180006b12  dec     rcx
0x180006b15  and     rcx, rsi
0x180006b18  mov     rax, [rax+rcx*8]
0x180006b1c  mov     byte ptr [r15+rax], 0Ah
0x180006b21  inc     qword ptr [rdi+20h]
0x180006b25  mov     rcx, [r14+30h]
0x180006b29  mov     rax, [r14+38h]
0x180006b2d  sub     rax, rcx
0x180006b30  sar     rax, 5
0x180006b34  cmp     rax, r13
0x180006b37  jbe     loc_180006D0C
0x180006b3d  shl     r13, 5
0x180006b41  lea     rdx, [rsp+0A8h+var_60]; int
0x180006b46  xor     r12d, r12d
0x180006b49  mov     r9, rbx; int
0x180006b4c  mov     r8d, 45h ; 'E'; int
0x180006b52  mov     [rsp+0A8h+var_88], r12; char *
0x180006b57  lea     rsi, [rcx+r13]
0x180006b5b  lea     rcx, [r14+58h]; int
0x180006b5f  call    ?DeclareLocal@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBD1@Z; Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal(DCOMPOSITION_EXPRESSION_TYPE,char const *,char const *)
0x180006b64  mov     rbx, rax
0x180006b67  cmp     rsi, rax
0x180006b6a  jz      short loc_180006BA6
0x180006b6c  mov     rax, [rsi+18h]
0x180006b70  cmp     rax, 0Fh
0x180006b74  ja      loc_180006C8A
0x180006b7a  mov     [rsi+10h], r12
0x180006b7e  mov     qword ptr [rsi+18h], 0Fh
0x180006b86  mov     [rsi], r12b
0x180006b89  movups  xmm0, xmmword ptr [rbx]
0x180006b8c  movups  xmmword ptr [rsi], xmm0
0x180006b8f  movups  xmm1, xmmword ptr [rbx+10h]
0x180006b93  movups  xmmword ptr [rsi+10h], xmm1
0x180006b97  mov     [rbx+10h], r12
0x180006b9b  mov     qword ptr [rbx+18h], 0Fh
0x180006ba3  mov     [rbx], r12b
0x180006ba6  mov     rax, [rsp+0A8h+var_48]
0x180006bab  cmp     rax, 0Fh
0x180006baf  ja      loc_180006CB2
0x180006bb5  mov     eax, [rsp+0A8h+var_68]
0x180006bb9  mov     [r14+10h], eax
0x180006bbd  cmp     qword ptr [rsi+18h], 0Fh
0x180006bc2  mov     rcx, [rbp+0]
0x180006bc6  mov     rax, [rcx]
0x180006bc9  jbe     short loc_180006BCE
0x180006bcb  mov     rsi, [rsi]
0x180006bce  mov     rax, [rax+0A0h]
0x180006bd5  mov     r9, rsi
0x180006bd8  mov     r8, r14
0x180006bdb  mov     rdx, rbp
0x180006bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be3  mov     r8d, 4; unsigned __int64
0x180006be9  lea     rdx, asc_18003403C; "    "
0x180006bf0  mov     rcx, rdi; this
0x180006bf3  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD_K@Z; Windows::UI::Composition::StringBuilder::Append(char const *,unsigned __int64)
0x180006bf8  mov     rcx, [rdi+20h]
0x180006bfc  movzx   eax, cl
0x180006bff  add     al, [rdi+18h]
0x180006c02  test    al, 0Fh
0x180006c04  jz      loc_180006D98
0x180006c0a  mov     r8, [rdi+10h]
0x180006c0e  mov     rax, r8
0x180006c11  shl     rax, 4
0x180006c15  dec     rax
0x180006c18  and     [rdi+18h], rax
0x180006c1c  lea     rax, [r8-1]
0x180006c20  mov     rbx, [rdi+18h]
0x180006c24  add     rbx, [rdi+20h]
0x180006c28  mov     rsi, rbx
0x180006c2b  shr     rsi, 4
0x180006c2f  and     rax, rsi
0x180006c32  lea     r14, ds:0[rax*8]
0x180006c3a  mov     rax, [rdi+8]
0x180006c3e  cmp     [r14+rax], r12
0x180006c42  jz      loc_180006D62
0x180006c48  mov     rcx, [rdi+10h]
0x180006c4c  and     ebx, 0Fh
0x180006c4f  mov     rax, [rdi+8]
0x180006c53  dec     rcx
0x180006c56  and     rcx, rsi
0x180006c59  mov     rax, [rax+rcx*8]
0x180006c5d  mov     byte ptr [rbx+rax], 0Ah
0x180006c61  inc     qword ptr [rdi+20h]
0x180006c65  mov     rcx, [rsp+0A8h+var_40]
0x180006c6a  xor     rcx, rsp; StackCookie
0x180006c6d  call    __security_check_cookie
0x180006c72  mov     rbx, [rsp+0A8h+arg_18]
0x180006c7a  add     rsp, 70h
0x180006c7e  pop     r15
0x180006c80  pop     r14
0x180006c82  pop     r13
0x180006c84  pop     r12
0x180006c86  pop     rdi
0x180006c87  pop     rsi
0x180006c88  pop     rbp
0x180006c89  retn
0x180006c8a  mov     rcx, [rsi]; void *
0x180006c8d  lea     rdx, [rax+1]; unsigned __int64
0x180006c91  mov     [rsp+0A8h+var_70], rdx
0x180006c96  mov     [rsp+0A8h+var_78], rcx
0x180006c9b  cmp     rdx, 1000h
0x180006ca2  jnb     loc_180006DD9
0x180006ca8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006cad  jmp     loc_180006B7A
0x180006cb2  mov     rcx, [rsp+0A8h+var_60]; void *
0x180006cb7  lea     rdx, [rax+1]; unsigned __int64
0x180006cbb  mov     [rsp+0A8h+var_70], rdx
0x180006cc0  mov     [rsp+0A8h+var_78], rcx
0x180006cc5  cmp     rdx, 1000h
0x180006ccc  jnb     loc_180006DF7
0x180006cd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006cd7  jmp     loc_180006BB5
0x180006cdc  cmp     ecx, 1
0x180006cdf  jnz     loc_180006A4C
0x180006ce5  mov     rcx, [r14+18h]
0x180006ce9  xor     eax, eax
0x180006ceb  mov     r15d, [rdx+4]
0x180006cef  mov     word ptr [rsp+0A8h+var_78+1], ax
0x180006cf4  mov     byte ptr [rsp+0A8h+var_78+3], al
0x180006cf8  mov     rax, [r14+20h]
0x180006cfc  sub     rax, rcx
0x180006cff  sar     rax, 3
0x180006d03  cmp     rax, r15
0x180006d06  ja      loc_180006DB7
0x180006d0c  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180006d13  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180006d19  int     3; Trap to Debugger
0x180006d1a  mov     rax, [rbx]
0x180006d1d  mov     rcx, rbx
0x180006d20  mov     rdx, [rbp+18h]
0x180006d24  mov     rax, [rax+68h]
0x180006d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2d  test    al, al
0x180006d2f  jnz     loc_180006A23
0x180006d35  mov     r12b, 1
0x180006d38  xor     edi, edi
0x180006d3a  jmp     loc_180006A29
0x180006d3f  mov     rax, [r14+8]
0x180006d43  or      dword ptr [rax], 2
0x180006d46  jmp     loc_1800069FD
0x180006d4b  mov     ecx, 10h; dwBytes
0x180006d50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d55  mov     rcx, [rdi+8]
0x180006d59  mov     [r12+rcx], rax
0x180006d5d  jmp     loc_180006B06
0x180006d62  mov     ecx, 10h; dwBytes
0x180006d67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d6c  mov     rcx, [rdi+8]
0x180006d70  mov     [r14+rcx], rax
0x180006d74  jmp     loc_180006C48
0x180006d79  lea     rax, [rcx+10h]
0x180006d7d  shr     rax, 4
0x180006d81  cmp     [rdi+10h], rax
0x180006d85  ja      loc_180006AC7
0x180006d8b  mov     rcx, rdi
0x180006d8e  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180006d93  jmp     loc_180006AC7
0x180006d98  lea     rax, [rcx+10h]
0x180006d9c  shr     rax, 4
0x180006da0  cmp     [rdi+10h], rax
0x180006da4  ja      loc_180006C0A
0x180006daa  mov     rcx, rdi
0x180006dad  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180006db2  jmp     loc_180006C0A
0x180006db7  or      [rcx+r15*8+6], r12b
0x180006dbc  jmp     loc_180006A4C
0x180006dc1  mov     rax, [r14+8]
0x180006dc5  or      dword ptr [rax], 4
0x180006dc8  jmp     loc_1800069FD
0x180006dcd  mov     rax, [r14+8]
0x180006dd1  or      dword ptr [rax], 10h
0x180006dd4  jmp     loc_1800069FD
0x180006dd9  lea     rdx, [rsp+0A8h+var_70]; unsigned __int64 *
0x180006dde  lea     rcx, [rsp+0A8h+var_78]; void **
0x180006de3  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180006de8  mov     rdx, [rsp+0A8h+var_70]
0x180006ded  mov     rcx, [rsp+0A8h+var_78]
0x180006df2  jmp     loc_180006CA8
0x180006df7  lea     rdx, [rsp+0A8h+var_70]; unsigned __int64 *
0x180006dfc  lea     rcx, [rsp+0A8h+var_78]; void **
0x180006e01  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180006e06  mov     rcx, [rsp+0A8h+var_78]
0x180006e0b  mov     rdx, [rsp+0A8h+var_70]
0x180006e10  jmp     loc_180006CD2
```
