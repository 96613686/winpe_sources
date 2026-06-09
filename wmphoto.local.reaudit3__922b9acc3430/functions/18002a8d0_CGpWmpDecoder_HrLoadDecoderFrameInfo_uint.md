# CGpWmpDecoder::HrLoadDecoderFrameInfo(uint)

- ea: `0x18002a8d0`
- end: `0x18002ab91`
- name: `?HrLoadDecoderFrameInfo@CGpWmpDecoder@@MEAAJI@Z`
- size: `705`
- prototype: `__int64 __fastcall(CGpWmpDecoder *this, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180028cb0`
- `0x180029770`
- `0x18002a750`
- `0x180038980`

## callees

- `0x18002a8d0`
- `0x18002ab98`
- `0x18002ae40`
- `0x18002e400`
- `0x180036444`
- `0x180038534`
- `0x18003855c`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CGpWmpDecoder::HrLoadDecoderFrameInfo(CGpWmpDecoder *this, int a2)
{
  int v2; // eax
  int v4; // edi
  int v5; // r8d
  __int64 *v6; // r15
  __int64 v7; // r12
  CWmpDecoderFrame *v8; // r14
  __int64 v9; // r9
  __m128i v10; // xmm0
  unsigned __int64 v11; // rdx
  unsigned int v12; // ecx
  __int64 v13; // rbx
  int v14; // eax
  CWmpDecoderFrame *v15; // rax
  CWmpDecoderFrame *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r10
  unsigned int v22; // edx
  __m128i v23; // [rsp+30h] [rbp-48h] BYREF
  int v24; // [rsp+80h] [rbp+8h] BYREF
  int v25; // [rsp+88h] [rbp+10h]
  int v26; // [rsp+90h] [rbp+18h] BYREF
  CWmpDecoderFrame *v27; // [rsp+98h] [rbp+20h]

  v25 = a2;
  v2 = a2;
  v4 = 0;
  v5 = *((_DWORD *)this + 36);
  v6 = (__int64 *)((char *)this + 104);
  if ( v5 )
  {
    if ( *((_QWORD *)this + 14) - *((_QWORD *)this + 13) == 32 )
      return (unsigned int)v4;
    v2 = v25;
  }
  v7 = (__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 13)) >> 4;
  while ( 1 )
  {
    v27 = 0;
    v8 = 0;
    if ( (unsigned int)v7 >= v2 + 2 )
      return (unsigned int)v4;
    v9 = *v6;
    v10 = *(__m128i *)(*v6 + 16LL * (unsigned int)(v7 - 1));
    v23 = v10;
    v11 = (v6[1] - v9) >> 4;
    if ( v11 > 0x100 )
      goto LABEL_19;
    v12 = _mm_cvtsi128_si32(v10);
    if ( !v5 )
    {
      if ( !v12 )
        goto LABEL_19;
      if ( v11 > 1 )
      {
        if ( v12 - 8 > 0xFFFFFFCD )
        {
LABEL_33:
          v4 = -2003292409;
          goto LABEL_19;
        }
        v20 = 0;
        v21 = v11 - 1;
        while ( v20 < v21 )
        {
          v22 = *(_DWORD *)(v9 + 16 * v20);
          if ( v12 < v22 )
            goto LABEL_29;
          if ( v12 <= v22 + 42 )
            goto LABEL_33;
          if ( v12 <= v22 )
          {
LABEL_29:
            if ( v22 <= v12 + 42 )
              goto LABEL_33;
          }
          ++v20;
        }
      }
    }
    v13 = v12;
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
            *((_QWORD *)this + 12),
            v12,
            0,
            0);
    v4 = v14;
    if ( v14 < 0 )
      goto LABEL_19;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v15 = (CWmpDecoderFrame *)operator new(0x104E0u);
      v16 = CWmpDecoderFrame::CWmpDecoderFrame(v15, this);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v24 = -2147024882;
        v4 = -2147024882;
        v8 = v27;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002AB7D);
LABEL_19:
        if ( !v8 )
          return (unsigned int)v4;
LABEL_34:
        CWmpDecoderFrame::`scalar deleting destructor'(v8, 1u);
        return (unsigned int)v4;
      }
    }
    v8 = v16;
    v27 = v16;
    if ( !v16 )
      break;
    *((_DWORD *)v16 + 16689) = *((_DWORD *)this + 36);
    v4 = CWmpDecoderFrame::HrInit(v16, *((struct IStream **)this + 12));
    if ( v4 < 0 )
      goto LABEL_34;
    v17 = 0;
    v26 = 0;
    if ( !*((_DWORD *)this + 36) )
    {
      LOWORD(v24) = 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64))(**((_QWORD **)this + 12) + 24LL))(
             *((_QWORD *)this + 12),
             &v24,
             2);
      if ( v4 < 0 )
        goto LABEL_34;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
             *((_QWORD *)this + 12),
             v13 + 12 * (unsigned int)(unsigned __int16)v24 + 2,
             0,
             0);
      if ( v4 < 0 )
        goto LABEL_34;
      v4 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64))(**((_QWORD **)this + 12) + 24LL))(
             *((_QWORD *)this + 12),
             &v26,
             4);
      if ( v4 < 0 )
        goto LABEL_34;
      v17 = v26;
    }
    v23.m128i_i32[0] = v17;
    v23.m128i_i64[1] = (__int64)v8;
    v18 = v6[1];
    if ( v18 == v6[2] )
      std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_reallocate<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(
        v6,
        v18,
        &v23);
    else
      std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_back_with_unused_capacity<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(
        v6,
        &v23);
    v5 = *((_DWORD *)this + 36);
    if ( v5 )
      return (unsigned int)v4;
    LODWORD(v7) = v7 + 1;
    v2 = v25;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18002a8d0  mov     [rsp+arg_8], edx
0x18002a8d4  push    rbx
0x18002a8d5  push    rsi
0x18002a8d6  push    rdi
0x18002a8d7  push    r12
0x18002a8d9  push    r13
0x18002a8db  push    r14
0x18002a8dd  push    r15
0x18002a8df  sub     rsp, 40h
0x18002a8e3  mov     eax, edx
0x18002a8e5  mov     r13, rcx
0x18002a8e8  xor     esi, esi
0x18002a8ea  mov     edi, esi
0x18002a8ec  mov     r8d, [rcx+90h]
0x18002a8f3  lea     r15, [rcx+68h]
0x18002a8f7  test    r8d, r8d
0x18002a8fa  jnz     loc_18002AB20
0x18002a900  mov     r12, [r15+8]
0x18002a904  sub     r12, [r15]
0x18002a907  sar     r12, 4
0x18002a90b  mov     [rsp+78h+arg_18], rsi
0x18002a913  mov     r14, rsi
0x18002a916  add     eax, 2
0x18002a919  cmp     r12d, eax
0x18002a91c  jnb     loc_18002AAC2
0x18002a922  mov     r9, [r15]
0x18002a925  lea     ecx, [r12-1]
0x18002a92a  add     rcx, rcx
0x18002a92d  movups  xmm0, xmmword ptr [r9+rcx*8]
0x18002a932  movups  [rsp+78h+var_48], xmm0
0x18002a937  mov     rdx, [r15+8]
0x18002a93b  sub     rdx, r9
0x18002a93e  sar     rdx, 4
0x18002a942  cmp     rdx, 100h
0x18002a949  ja      loc_18002AAB9
0x18002a94f  movd    ecx, xmm0
0x18002a953  test    r8d, r8d
0x18002a956  jz      loc_18002AAD5
0x18002a95c  mov     ebx, ecx
0x18002a95e  mov     rcx, [r13+60h]
0x18002a962  mov     rax, [rcx]
0x18002a965  xor     r9d, r9d
0x18002a968  xor     r8d, r8d
0x18002a96b  mov     edx, ebx
0x18002a96d  mov     rax, [rax+28h]
0x18002a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a976  mov     edi, eax
0x18002a978  test    eax, eax
0x18002a97a  js      loc_18002AAB9
0x18002a980  mov     ecx, 104E0h; Size
0x18002a985  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a98a  mov     rdx, r13; struct CGpWmpDecoder *
0x18002a98d  mov     rcx, rax; this
0x18002a990  call    ??0CWmpDecoderFrame@@QEAA@PEAVCGpWmpDecoder@@@Z; CWmpDecoderFrame::CWmpDecoderFrame(CGpWmpDecoder *)
0x18002a995  mov     r14, rax
0x18002a998  mov     [rsp+78h+arg_18], rax
0x18002a9a0  test    r14, r14
0x18002a9a3  jz      loc_18002AB73
0x18002a9a9  mov     eax, [r13+90h]
0x18002a9b0  mov     [r14+104C4h], eax
0x18002a9b7  mov     rdx, [r13+60h]; struct IStream *
0x18002a9bb  mov     rcx, r14; this
0x18002a9be  call    ?HrInit@CWmpDecoderFrame@@UEAAJPEAUIStream@@@Z; CWmpDecoderFrame::HrInit(IStream *)
0x18002a9c3  mov     edi, eax
0x18002a9c5  test    eax, eax
0x18002a9c7  js      loc_18002AB61
0x18002a9cd  mov     eax, esi
0x18002a9cf  mov     [rsp+78h+arg_10], eax
0x18002a9d6  cmp     [r13+90h], esi
0x18002a9dd  jnz     loc_18002AA79
0x18002a9e3  mov     word ptr [rsp+78h+arg_0], si
0x18002a9eb  mov     rcx, [r13+60h]
0x18002a9ef  mov     rax, [rcx]
0x18002a9f2  xor     r9d, r9d
0x18002a9f5  lea     r8d, [r9+2]
0x18002a9f9  lea     rdx, [rsp+78h+arg_0]
0x18002aa01  mov     rax, [rax+18h]
0x18002aa05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa0a  mov     edi, eax
0x18002aa0c  test    eax, eax
0x18002aa0e  js      loc_18002AB61
0x18002aa14  movzx   eax, word ptr [rsp+78h+arg_0]
0x18002aa1c  lea     ecx, [rax+rax*2]
0x18002aa1f  lea     edx, ds:2[rcx*4]
0x18002aa26  add     rdx, rbx
0x18002aa29  mov     rcx, [r13+60h]
0x18002aa2d  mov     rax, [rcx]
0x18002aa30  xor     r9d, r9d
0x18002aa33  xor     r8d, r8d
0x18002aa36  mov     rax, [rax+28h]
0x18002aa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa3f  mov     edi, eax
0x18002aa41  test    eax, eax
0x18002aa43  js      loc_18002AB61
0x18002aa49  mov     rcx, [r13+60h]
0x18002aa4d  mov     rax, [rcx]
0x18002aa50  xor     r9d, r9d
0x18002aa53  lea     r8d, [r9+4]
0x18002aa57  lea     rdx, [rsp+78h+arg_10]
0x18002aa5f  mov     rax, [rax+18h]
0x18002aa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa68  mov     edi, eax
0x18002aa6a  test    eax, eax
0x18002aa6c  js      loc_18002AB61
0x18002aa72  mov     eax, [rsp+78h+arg_10]
0x18002aa79  mov     dword ptr [rsp+78h+var_48], eax
0x18002aa7d  mov     qword ptr [rsp+78h+var_48+8], r14
0x18002aa82  mov     rdx, [r15+8]
0x18002aa86  mov     rcx, r15
0x18002aa89  cmp     rdx, [r15+10h]
0x18002aa8d  jnz     loc_18002AB43
0x18002aa93  lea     r8, [rsp+78h+var_48]
0x18002aa98  call    ??$_Emplace_reallocate@AEBUCWmpDecoderFrameInfo@CGpWmpDecoder@@@?$vector@UCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@AEAAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@QEAU23@AEBU23@@Z; std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_reallocate<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo const &)
0x18002aa9d  nop
0x18002aa9e  mov     r8d, [r13+90h]
0x18002aaa5  test    r8d, r8d
0x18002aaa8  jnz     short loc_18002AAC2
0x18002aaaa  inc     r12d
0x18002aaad  mov     eax, [rsp+78h+arg_8]
0x18002aab4  jmp     loc_18002A90B
0x18002aab9  test    r14, r14
0x18002aabc  jnz     loc_18002AB61
0x18002aac2  mov     eax, edi
0x18002aac4  add     rsp, 40h
0x18002aac8  pop     r15
0x18002aaca  pop     r14
0x18002aacc  pop     r13
0x18002aace  pop     r12
0x18002aad0  pop     rdi
0x18002aad1  pop     rsi
0x18002aad2  pop     rbx
0x18002aad3  retn
0x18002aad5  test    ecx, ecx
0x18002aad7  jz      short loc_18002AAB9
0x18002aad9  cmp     rdx, 1
0x18002aadd  jbe     loc_18002A95C
0x18002aae3  lea     eax, [rcx-8]
0x18002aae6  cmp     eax, 0FFFFFFCDh
0x18002aae9  ja      short loc_18002AB39
0x18002aaeb  mov     r8, rsi
0x18002aaee  lea     r10, [rdx-1]
0x18002aaf2  cmp     r8, r10
0x18002aaf5  jnb     loc_18002A95C
0x18002aafb  mov     rax, r8
0x18002aafe  add     rax, rax
0x18002ab01  mov     edx, [r9+rax*8]
0x18002ab05  cmp     ecx, edx
0x18002ab07  jb      short loc_18002AB14
0x18002ab09  lea     eax, [rdx+2Ah]
0x18002ab0c  cmp     ecx, eax
0x18002ab0e  jbe     short loc_18002AB39
0x18002ab10  cmp     ecx, edx
0x18002ab12  ja      short loc_18002AB1B
0x18002ab14  lea     eax, [rcx+2Ah]
0x18002ab17  cmp     edx, eax
0x18002ab19  jbe     short loc_18002AB39
0x18002ab1b  inc     r8
0x18002ab1e  jmp     short loc_18002AAF2
0x18002ab20  mov     rax, [r15+8]
0x18002ab24  sub     rax, [r15]
0x18002ab27  cmp     rax, 20h ; ' '
0x18002ab2b  jz      short loc_18002AAC2
0x18002ab2d  mov     eax, [rsp+78h+arg_8]
0x18002ab34  jmp     loc_18002A900
0x18002ab39  mov     edi, 88982F07h
0x18002ab3e  jmp     loc_18002AAB9
0x18002ab43  lea     rdx, [rsp+78h+var_48]
0x18002ab48  call    ??$_Emplace_back_with_unused_capacity@AEBUCWmpDecoderFrameInfo@CGpWmpDecoder@@@?$vector@UCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@AEAAAEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@AEBU23@@Z; std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_back_with_unused_capacity<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(CGpWmpDecoder::CWmpDecoderFrameInfo const &)
0x18002ab4d  jmp     loc_18002AA9E
0x18002ab52  mov     edi, [rsp+78h+arg_0]
0x18002ab59  mov     r14, [rsp+78h+arg_18]
0x18002ab61  mov     edx, 1; unsigned int
0x18002ab66  mov     rcx, r14; this
0x18002ab69  call    ??_GCWmpDecoderFrame@@UEAAPEAXI@Z; CWmpDecoderFrame::`scalar deleting destructor'(uint)
0x18002ab6e  jmp     loc_18002AAC2
0x18002ab73  mov     edi, 8007000Eh
0x18002ab78  jmp     loc_18002AAC2
0x18002ab7d  mov     edi, [rsp+78h+arg_0]
0x18002ab84  mov     r14, [rsp+78h+arg_18]
0x18002ab8c  jmp     loc_18002AAB9
```
