# CEnumImages::FindNext(void)

- ea: `0x1800081b8`
- end: `0x1800083ab`
- name: `?FindNext@CEnumImages@@QEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(CEnumImages *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180007fd4`
- `0x180008950`
- `0x180008b50`
- `0x1800096c0`
- `0x18000a570`
- `0x18000b8b0`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x180007494`
- `0x1800081b8`
- `0x1800086e4`
- `0x18000ae64`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CEnumImages::FindNext(CEnumImages *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  CImage *v6; // rax
  CImage *v7; // rax
  CImage *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  const unsigned __int16 *v13; // rbp
  CImage *v14; // rax
  CImage *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx

  if ( *((_DWORD *)this + 9) )
  {
    while ( 1 )
    {
      v5 = *((_QWORD *)this + 8);
      if ( v5 && *(_DWORD *)(v5 + 132) < *(_DWORD *)(v5 + 128) )
      {
        v6 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v6 || (v7 = CImage::CImage(v6), (v8 = v7) == 0) )
        {
LABEL_25:
          v19 = 2147942414LL;
          LODWORD(v4) = -2147024882;
LABEL_26:
          if ( (*((_BYTE *)this + 48) & 0x40) != 0 )
            return (unsigned int)v4;
          goto LABEL_27;
        }
        v4 = (unsigned int)CImage::Initialize(
                             v7,
                             *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 88LL),
                             *(_DWORD *)(*((_QWORD *)this + 8) + 132LL) + 1,
                             *((_DWORD *)this + 12));
        if ( (int)ElValidateHr_4(v4, v9, v10, 377) >= 0 )
          goto LABEL_19;
        (*(void (__fastcall **)(CImage *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      if ( *((_QWORD *)this + 8) )
      {
        CDynArray<unsigned short *,CDeallocateString>::ClearItem((char *)this + 24);
        v11 = *((_QWORD *)this + 8);
        if ( v11 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          *((_QWORD *)this + 8) = 0;
        }
      }
      if ( !*((_DWORD *)this + 9) )
      {
        LODWORD(v4) = -1056833021;
        goto LABEL_22;
      }
      v13 = (const unsigned __int16 *)**((_QWORD **)this + 3);
      v14 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v14 )
        goto LABEL_25;
      v15 = CImage::CImage(v14);
      v8 = v15;
      if ( !v15 )
        goto LABEL_25;
      v4 = (unsigned int)CImage::Initialize(v15, v13, 1, *((_DWORD *)this + 12));
      if ( (int)ElValidateHr_4(v4, v16, v17, 423) < 0 )
      {
        CDynArray<unsigned short *,CDeallocateString>::ClearItem((char *)this + 24);
        (*(void (__fastcall **)(CImage *))(*(_QWORD *)v8 + 8LL))(v8);
        goto LABEL_22;
      }
LABEL_19:
      v18 = *((_QWORD *)this + 8);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      *((_QWORD *)this + 8) = v8;
LABEL_22:
      v19 = (unsigned int)v4;
      if ( (_DWORD)v4 == -1056833021 )
        return (unsigned int)v4;
      if ( (int)v4 < 0 )
        goto LABEL_26;
LABEL_27:
      if ( (int)ElValidateHr_4(v19, a2, a3, 316) >= 0 )
        return (unsigned int)v4;
    }
  }
  LODWORD(v4) = -1056833021;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800081b8  mov     rax, rsp
0x1800081bb  mov     [rax+8], rbx
0x1800081bf  mov     [rax+10h], rbp
0x1800081c3  mov     [rax+18h], rsi
0x1800081c7  mov     [rax+20h], rdi
0x1800081cb  push    r14
0x1800081cd  sub     rsp, 20h
0x1800081d1  cmp     dword ptr [rcx+24h], 0
0x1800081d5  mov     rdi, rcx
0x1800081d8  jnz     short loc_1800081E4
0x1800081da  mov     ebx, 0C1020203h
0x1800081df  jmp     loc_1800082C4
0x1800081e4  mov     rcx, [rdi+40h]
0x1800081e8  xor     esi, esi
0x1800081ea  xor     ebp, ebp
0x1800081ec  test    rcx, rcx
0x1800081ef  jz      loc_180008277
0x1800081f5  mov     eax, [rcx+80h]
0x1800081fb  cmp     [rcx+84h], eax
0x180008201  jnb     short loc_180008277
0x180008203  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000820a  mov     ecx, 190h; unsigned __int64
0x18000820f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008214  test    rax, rax
0x180008217  jz      loc_180008382
0x18000821d  mov     rcx, rax; this
0x180008220  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x180008225  mov     rsi, rax
0x180008228  test    rax, rax
0x18000822b  jz      loc_180008382
0x180008231  mov     rdx, [rdi+40h]
0x180008235  mov     rcx, rax; this
0x180008238  mov     r9d, [rdi+30h]; unsigned int
0x18000823c  mov     r8d, [rdx+84h]
0x180008243  mov     rdx, [rdx+58h]; unsigned __int16 *
0x180008247  inc     r8d; unsigned int
0x18000824a  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x18000824f  mov     r9d, 179h
0x180008255  mov     ecx, eax
0x180008257  mov     ebx, eax
0x180008259  call    ElValidateHr_4
0x18000825e  test    eax, eax
0x180008260  jns     loc_180008355
0x180008266  mov     rax, [rsi]
0x180008269  mov     rcx, rsi
0x18000826c  mov     rax, [rax+8]
0x180008270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008275  xor     esi, esi
0x180008277  lea     r14, [rdi+18h]
0x18000827b  cmp     [rdi+40h], rbp
0x18000827f  jz      short loc_1800082A2
0x180008281  mov     rcx, r14
0x180008284  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateString>::ClearItem(ulong)
0x180008289  mov     rcx, [rdi+40h]
0x18000828d  test    rcx, rcx
0x180008290  jz      short loc_1800082A2
0x180008292  mov     rax, [rcx]
0x180008295  mov     rax, [rax+8]
0x180008299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829e  and     [rdi+40h], rbp
0x1800082a2  cmp     [rdi+24h], ebp
0x1800082a5  jnz     short loc_1800082E2
0x1800082a7  mov     ebx, 0C1020203h
0x1800082ac  test    rsi, rsi
0x1800082af  jz      loc_18000836E
0x1800082b5  mov     rax, [rsi]
0x1800082b8  mov     rcx, rsi
0x1800082bb  mov     rax, [rax+8]
0x1800082bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c4  mov     rbp, [rsp+28h+arg_8]
0x1800082c9  mov     eax, ebx
0x1800082cb  mov     rbx, [rsp+28h+arg_0]
0x1800082d0  mov     rsi, [rsp+28h+arg_10]
0x1800082d5  mov     rdi, [rsp+28h+arg_18]
0x1800082da  add     rsp, 20h
0x1800082de  pop     r14
0x1800082e0  retn
0x1800082e2  cmp     [r14+0Ch], ebp
0x1800082e6  jbe     short loc_1800082EE
0x1800082e8  mov     rax, [r14]
0x1800082eb  mov     rbp, [rax]
0x1800082ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800082f5  mov     ecx, 190h; unsigned __int64
0x1800082fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800082ff  test    rax, rax
0x180008302  jz      short loc_180008382
0x180008304  mov     rcx, rax; this
0x180008307  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x18000830c  mov     rsi, rax
0x18000830f  test    rax, rax
0x180008312  jz      short loc_180008382
0x180008314  mov     r9d, [rdi+30h]; unsigned int
0x180008318  mov     r8d, 1; unsigned int
0x18000831e  mov     rdx, rbp; unsigned __int16 *
0x180008321  mov     rcx, rax; this
0x180008324  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x180008329  mov     r9d, 1A7h
0x18000832f  mov     ecx, eax
0x180008331  mov     ebx, eax
0x180008333  call    ElValidateHr_4
0x180008338  test    eax, eax
0x18000833a  jns     short loc_180008355
0x18000833c  mov     rcx, r14
0x18000833f  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateString>::ClearItem(ulong)
0x180008344  mov     rax, [rsi]
0x180008347  mov     rcx, rsi
0x18000834a  mov     rax, [rax+8]
0x18000834e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008353  jmp     short loc_18000836E
0x180008355  mov     rcx, [rdi+40h]
0x180008359  test    rcx, rcx
0x18000835c  jz      short loc_18000836A
0x18000835e  mov     rax, [rcx]
0x180008361  mov     rax, [rax+8]
0x180008365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836a  mov     [rdi+40h], rsi
0x18000836e  mov     ecx, ebx
0x180008370  cmp     ebx, 0C1020203h
0x180008376  jz      loc_1800082C4
0x18000837c  test    ebx, ebx
0x18000837e  js      short loc_180008389
0x180008380  jmp     short loc_180008393
0x180008382  mov     ecx, 8007000Eh
0x180008387  mov     ebx, ecx
0x180008389  test    byte ptr [rdi+30h], 40h
0x18000838d  jnz     loc_1800082C4
0x180008393  mov     r9d, 13Ch
0x180008399  call    ElValidateHr_4
0x18000839e  test    eax, eax
0x1800083a0  js      loc_1800081E4
0x1800083a6  jmp     loc_1800082C4
```
