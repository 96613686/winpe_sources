# CGpWmpDecoder::HrLoadDecoderFrameInfo(uint)

- ea: `0x18002a720`
- end: `0x18002a9e0`
- name: `?HrLoadDecoderFrameInfo@CGpWmpDecoder@@MEAAJI@Z`
- size: `704`
- prototype: `__int64 __fastcall(CGpWmpDecoder *this, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180028cb0`
- `0x180029620`
- `0x18002a5c0`
- `0x180038340`

## callees

- `0x18002a720`
- `0x18002a9e8`
- `0x18002ac90`
- `0x18002e0e0`
- `0x180035e74`
- `0x180037f00`
- `0x180037f28`
- `0x180044010`

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
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002A9CC);
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
0x18002a720  mov     [rsp+arg_8], edx
0x18002a724  push    rbx
0x18002a725  push    rsi
0x18002a726  push    rdi
0x18002a727  push    r12
0x18002a729  push    r13
0x18002a72b  push    r14
0x18002a72d  push    r15
0x18002a72f  sub     rsp, 40h
0x18002a733  mov     eax, edx
0x18002a735  mov     r13, rcx
0x18002a738  xor     esi, esi
0x18002a73a  mov     edi, esi
0x18002a73c  mov     r8d, [rcx+90h]
0x18002a743  lea     r15, [rcx+68h]
0x18002a747  test    r8d, r8d
0x18002a74a  jnz     loc_18002A96F
0x18002a750  mov     r12, [r15+8]
0x18002a754  sub     r12, [r15]
0x18002a757  sar     r12, 4
0x18002a75b  mov     [rsp+78h+arg_18], rsi
0x18002a763  mov     r14, rsi
0x18002a766  add     eax, 2
0x18002a769  cmp     r12d, eax
0x18002a76c  jnb     loc_18002A912
0x18002a772  mov     r9, [r15]
0x18002a775  lea     ecx, [r12-1]
0x18002a77a  add     rcx, rcx
0x18002a77d  movups  xmm0, xmmword ptr [r9+rcx*8]
0x18002a782  movups  [rsp+78h+var_48], xmm0
0x18002a787  mov     rdx, [r15+8]
0x18002a78b  sub     rdx, r9
0x18002a78e  sar     rdx, 4
0x18002a792  cmp     rdx, 100h
0x18002a799  ja      loc_18002A909
0x18002a79f  movd    ecx, xmm0
0x18002a7a3  test    r8d, r8d
0x18002a7a6  jz      loc_18002A924
0x18002a7ac  mov     ebx, ecx
0x18002a7ae  mov     rcx, [r13+60h]
0x18002a7b2  mov     rax, [rcx]
0x18002a7b5  xor     r9d, r9d
0x18002a7b8  xor     r8d, r8d
0x18002a7bb  mov     edx, ebx
0x18002a7bd  mov     rax, [rax+28h]
0x18002a7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c6  mov     edi, eax
0x18002a7c8  test    eax, eax
0x18002a7ca  js      loc_18002A909
0x18002a7d0  mov     ecx, 104E0h; Size
0x18002a7d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a7da  mov     rdx, r13; struct CGpWmpDecoder *
0x18002a7dd  mov     rcx, rax; this
0x18002a7e0  call    ??0CWmpDecoderFrame@@QEAA@PEAVCGpWmpDecoder@@@Z; CWmpDecoderFrame::CWmpDecoderFrame(CGpWmpDecoder *)
0x18002a7e5  mov     r14, rax
0x18002a7e8  mov     [rsp+78h+arg_18], rax
0x18002a7f0  test    r14, r14
0x18002a7f3  jz      loc_18002A9C2
0x18002a7f9  mov     eax, [r13+90h]
0x18002a800  mov     [r14+104C4h], eax
0x18002a807  mov     rdx, [r13+60h]; struct IStream *
0x18002a80b  mov     rcx, r14; this
0x18002a80e  call    ?HrInit@CWmpDecoderFrame@@UEAAJPEAUIStream@@@Z; CWmpDecoderFrame::HrInit(IStream *)
0x18002a813  mov     edi, eax
0x18002a815  test    eax, eax
0x18002a817  js      loc_18002A9B0
0x18002a81d  mov     eax, esi
0x18002a81f  mov     [rsp+78h+arg_10], eax
0x18002a826  cmp     [r13+90h], esi
0x18002a82d  jnz     loc_18002A8C9
0x18002a833  mov     word ptr [rsp+78h+arg_0], si
0x18002a83b  mov     rcx, [r13+60h]
0x18002a83f  mov     rax, [rcx]
0x18002a842  xor     r9d, r9d
0x18002a845  lea     r8d, [r9+2]
0x18002a849  lea     rdx, [rsp+78h+arg_0]
0x18002a851  mov     rax, [rax+18h]
0x18002a855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a85a  mov     edi, eax
0x18002a85c  test    eax, eax
0x18002a85e  js      loc_18002A9B0
0x18002a864  movzx   eax, word ptr [rsp+78h+arg_0]
0x18002a86c  lea     ecx, [rax+rax*2]
0x18002a86f  lea     edx, ds:2[rcx*4]
0x18002a876  add     rdx, rbx
0x18002a879  mov     rcx, [r13+60h]
0x18002a87d  mov     rax, [rcx]
0x18002a880  xor     r9d, r9d
0x18002a883  xor     r8d, r8d
0x18002a886  mov     rax, [rax+28h]
0x18002a88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a88f  mov     edi, eax
0x18002a891  test    eax, eax
0x18002a893  js      loc_18002A9B0
0x18002a899  mov     rcx, [r13+60h]
0x18002a89d  mov     rax, [rcx]
0x18002a8a0  xor     r9d, r9d
0x18002a8a3  lea     r8d, [r9+4]
0x18002a8a7  lea     rdx, [rsp+78h+arg_10]
0x18002a8af  mov     rax, [rax+18h]
0x18002a8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8b8  mov     edi, eax
0x18002a8ba  test    eax, eax
0x18002a8bc  js      loc_18002A9B0
0x18002a8c2  mov     eax, [rsp+78h+arg_10]
0x18002a8c9  mov     dword ptr [rsp+78h+var_48], eax
0x18002a8cd  mov     qword ptr [rsp+78h+var_48+8], r14
0x18002a8d2  mov     rdx, [r15+8]
0x18002a8d6  mov     rcx, r15
0x18002a8d9  cmp     rdx, [r15+10h]
0x18002a8dd  jnz     loc_18002A992
0x18002a8e3  lea     r8, [rsp+78h+var_48]
0x18002a8e8  call    ??$_Emplace_reallocate@AEBUCWmpDecoderFrameInfo@CGpWmpDecoder@@@?$vector@UCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@AEAAPEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@QEAU23@AEBU23@@Z; std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_reallocate<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(CGpWmpDecoder::CWmpDecoderFrameInfo * const,CGpWmpDecoder::CWmpDecoderFrameInfo const &)
0x18002a8ed  nop
0x18002a8ee  mov     r8d, [r13+90h]
0x18002a8f5  test    r8d, r8d
0x18002a8f8  jnz     short loc_18002A912
0x18002a8fa  inc     r12d
0x18002a8fd  mov     eax, [rsp+78h+arg_8]
0x18002a904  jmp     loc_18002A75B
0x18002a909  test    r14, r14
0x18002a90c  jnz     loc_18002A9B0
0x18002a912  mov     eax, edi
0x18002a914  add     rsp, 40h
0x18002a918  pop     r15
0x18002a91a  pop     r14
0x18002a91c  pop     r13
0x18002a91e  pop     r12
0x18002a920  pop     rdi
0x18002a921  pop     rsi
0x18002a922  pop     rbx
0x18002a923  retn
0x18002a924  test    ecx, ecx
0x18002a926  jz      short loc_18002A909
0x18002a928  cmp     rdx, 1
0x18002a92c  jbe     loc_18002A7AC
0x18002a932  lea     eax, [rcx-8]
0x18002a935  cmp     eax, 0FFFFFFCDh
0x18002a938  ja      short loc_18002A988
0x18002a93a  mov     r8, rsi
0x18002a93d  lea     r10, [rdx-1]
0x18002a941  cmp     r8, r10
0x18002a944  jnb     loc_18002A7AC
0x18002a94a  mov     rax, r8
0x18002a94d  add     rax, rax
0x18002a950  mov     edx, [r9+rax*8]
0x18002a954  cmp     ecx, edx
0x18002a956  jb      short loc_18002A963
0x18002a958  lea     eax, [rdx+2Ah]
0x18002a95b  cmp     ecx, eax
0x18002a95d  jbe     short loc_18002A988
0x18002a95f  cmp     ecx, edx
0x18002a961  ja      short loc_18002A96A
0x18002a963  lea     eax, [rcx+2Ah]
0x18002a966  cmp     edx, eax
0x18002a968  jbe     short loc_18002A988
0x18002a96a  inc     r8
0x18002a96d  jmp     short loc_18002A941
0x18002a96f  mov     rax, [r15+8]
0x18002a973  sub     rax, [r15]
0x18002a976  cmp     rax, 20h ; ' '
0x18002a97a  jz      short loc_18002A912
0x18002a97c  mov     eax, [rsp+78h+arg_8]
0x18002a983  jmp     loc_18002A750
0x18002a988  mov     edi, 88982F07h
0x18002a98d  jmp     loc_18002A909
0x18002a992  lea     rdx, [rsp+78h+var_48]
0x18002a997  call    ??$_Emplace_back_with_unused_capacity@AEBUCWmpDecoderFrameInfo@CGpWmpDecoder@@@?$vector@UCWmpDecoderFrameInfo@CGpWmpDecoder@@V?$allocator@UCWmpDecoderFrameInfo@CGpWmpDecoder@@@std@@@std@@AEAAAEAUCWmpDecoderFrameInfo@CGpWmpDecoder@@AEBU23@@Z; std::vector<CGpWmpDecoder::CWmpDecoderFrameInfo>::_Emplace_back_with_unused_capacity<CGpWmpDecoder::CWmpDecoderFrameInfo const &>(CGpWmpDecoder::CWmpDecoderFrameInfo const &)
0x18002a99c  jmp     loc_18002A8EE
0x18002a9a1  mov     edi, [rsp+78h+arg_0]
0x18002a9a8  mov     r14, [rsp+78h+arg_18]
0x18002a9b0  mov     edx, 1; unsigned int
0x18002a9b5  mov     rcx, r14; this
0x18002a9b8  call    ??_GCWmpDecoderFrame@@UEAAPEAXI@Z; CWmpDecoderFrame::`scalar deleting destructor'(uint)
0x18002a9bd  jmp     loc_18002A912
0x18002a9c2  mov     edi, 8007000Eh
0x18002a9c7  jmp     loc_18002A912
0x18002a9cc  mov     edi, [rsp+78h+arg_0]
0x18002a9d3  mov     r14, [rsp+78h+arg_18]
0x18002a9db  jmp     loc_18002A909
```
