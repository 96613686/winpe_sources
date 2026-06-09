# FindHandlerForForeignException___FrameHandler4_

- ea: `0x140003b64`
- end: `0x140003e6a`
- name: `FindHandlerForForeignException___FrameHandler4_`
- size: `774`
- prototype: `__int64 __usercall@<rax>(struct EHExceptionRecord *@<rcx>, struct FH4::FuncInfo4 *, int, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003624`

## callees

- `0x140001500`
- `0x140002348`
- `0x140002544`
- `0x140002a80`
- `0x140003008`
- `0x140003540`
- `0x140003b64`
- `0x1400043e0`
- `0x140004468`
- `0x1400048bc`
- `0x1400056be`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140003bd8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140003bd8`

## pseudocode

```c
__int64 __fastcall FindHandlerForForeignException___FrameHandler4_(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        struct FH4::FuncInfo4 *a5,
        int a6,
        int a7,
        __int64 a8)
{
  bool v8; // zf
  __int64 result; // rax
  PVOID v13; // rbx
  __int64 v14; // xmm1_8
  int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rax
  _BYTE *v20; // r10
  __int64 v21; // rcx
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r8
  _BYTE *v26; // rdx
  __int64 v27; // rcx
  _DWORD *v28; // r10
  int v29; // [rsp+50h] [rbp-B0h]
  unsigned int v30; // [rsp+60h] [rbp-A0h]
  __int64 v32[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 *v33; // [rsp+88h] [rbp-78h]
  __m128i v34; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v40; // [rsp+D0h] [rbp-30h]
  _DWORD v41[10]; // [rsp+100h] [rbp+0h] BYREF

  v8 = a1->ExceptionCode == -2147483645;
  result = a8;
  v33 = a2;
  if ( !v8 )
  {
    if ( !*(_QWORD *)(_vcrt_getptd() + 16)
      || (v13 = EncodePointer(0), *(PVOID *)(_vcrt_getptd() + 16) == v13)
      || a1->ExceptionCode == -532459699
      || a1->ExceptionCode == -532462766
      || (result = _CallSETranslator<__FrameHandler4>(a1, a2, a3, a4, a5, a7, a8, a6), !(_DWORD)result) )
    {
      FH4::TryBlockMap4::TryBlockMap4((FH4::TryBlockMap4 *)v41, a5, *(_QWORD *)(a4 + 8));
      if ( !v41[0] )
        abort();
      __FrameHandler4::GetRangeOfTrysToCheck(&v34, v41, (unsigned int)a6, a4, a5, a7);
      v14 = v34.m128i_i64[0];
      result = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v34, 8));
      *(__m128i *)v32 = v34;
      if ( (unsigned int)result < v35 )
      {
        v30 = v32[1];
        do
        {
          *(_OWORD *)v32 = *(_OWORD *)(v14 + 24);
          if ( SLODWORD(v32[0]) <= a6 && a6 <= SHIDWORD(v32[0]) )
          {
            FH4::HandlerMap4::HandlerMap4(
              (FH4::HandlerMap4 *)&v36,
              (const struct FH4::TryBlockMapEntry4 *)v32,
              *(_QWORD *)(a4 + 8),
              **(_DWORD **)(a4 + 16));
            v37 = v38;
            FH4::HandlerMap4::DecompHandler((FH4::HandlerMap4 *)&v36);
            v15 = v36;
            v37 = v38;
            FH4::HandlerMap4::DecompHandler((FH4::HandlerMap4 *)&v36);
            v16 = (unsigned int)(v15 - 1);
            if ( (_DWORD)v16 )
            {
              do
              {
                FH4::HandlerMap4::DecompHandler((FH4::HandlerMap4 *)&v36);
                --v16;
              }
              while ( v16 );
            }
            v17 = v40;
            if ( !v40
              || !(v17 + GetImageBase())
              || ((v18 = v40) == 0 ? (v19 = 0) : (v19 = v18 + GetImageBase()), !*(_BYTE *)(v19 + 16)) )
            {
              if ( (v39[4] & 0x40) == 0 )
              {
                LOBYTE(v29) = 1;
                CatchIt___FrameHandler4_(a1, v33, a5, (struct FH4::HandlerType4 *)v39, 0, (__int64)v32, a7, a8, v29, 0);
              }
            }
          }
          v20 = *(_BYTE **)(v14 + 8);
          v21 = *v20 & 0xF;
          v22 = *((char *)&FH4::s_negLengthTab + v21);
          v23 = *(_DWORD *)&v20[-v22 - 4] >> *((_BYTE *)&FH4::s_shiftTab + v21);
          *(_QWORD *)(v14 + 8) = &v20[-v22];
          *(_DWORD *)(v14 + 24) = v23;
          v24 = v20[-v22] & 0xF;
          v25 = *((char *)&FH4::s_negLengthTab + v24);
          v26 = &v20[-v25 - v22];
          *(_DWORD *)(v14 + 28) = *((_DWORD *)v26 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v24);
          *(_QWORD *)(v14 + 8) = v26;
          v27 = *v26 & 0xF;
          v28 = &v20[-*((char *)&FH4::s_negLengthTab + v27) - v25 - v22];
          *(_DWORD *)(v14 + 32) = *(v28 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v27);
          result = (__int64)(v28 + 1);
          *(_QWORD *)(v14 + 8) = v28;
          *(_DWORD *)(v14 + 36) = *v28;
          *(_QWORD *)(v14 + 8) = v28 + 1;
          ++v30;
        }
        while ( v30 < v35 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003b64  push    rbp
0x140003b66  push    rbx
0x140003b67  push    rsi
0x140003b68  push    rdi
0x140003b69  push    r12
0x140003b6b  push    r13
0x140003b6d  push    r14
0x140003b6f  push    r15
0x140003b71  lea     rbp, [rsp-38h]
0x140003b76  sub     rsp, 138h
0x140003b7d  mov     rax, cs:__security_cookie
0x140003b84  xor     rax, rsp
0x140003b87  mov     [rbp+70h+var_48], rax
0x140003b8b  cmp     dword ptr [rcx], 80000003h
0x140003b91  mov     rdi, r9
0x140003b94  mov     rax, [rbp+70h+arg_38]
0x140003b9b  mov     r13, rdx
0x140003b9e  mov     r15, [rbp+70h+arg_20]
0x140003ba5  mov     rsi, rcx
0x140003ba8  mov     qword ptr [rsp+170h+var_108], rax
0x140003bad  mov     [rsp+170h+var_100], r8
0x140003bb2  mov     [rbp+70h+var_E8], rdx
0x140003bb6  jz      loc_140003E44
0x140003bbc  call    __vcrt_getptd
0x140003bc1  mov     r12d, [rbp+70h+arg_30]
0x140003bc8  mov     r14d, [rbp+70h+arg_28]
0x140003bcf  cmp     qword ptr [rax+10h], 0
0x140003bd4  jz      short loc_140003C30
0x140003bd6  xor     ecx, ecx; Ptr
0x140003bd8  call    cs:__imp_EncodePointer
0x140003bde  mov     rbx, rax
0x140003be1  call    __vcrt_getptd
0x140003be6  cmp     [rax+10h], rbx
0x140003bea  jz      short loc_140003C30
0x140003bec  cmp     dword ptr [rsi], 0E0434F4Dh
0x140003bf2  jz      short loc_140003C30
0x140003bf4  cmp     dword ptr [rsi], 0E0434352h
0x140003bfa  jz      short loc_140003C30
0x140003bfc  mov     rax, qword ptr [rsp+170h+var_108]
0x140003c01  mov     r9, rdi
0x140003c04  mov     r8, [rsp+170h+var_100]
0x140003c09  mov     rdx, r13
0x140003c0c  mov     dword ptr [rsp+170h+var_138], r14d
0x140003c11  mov     rcx, rsi
0x140003c14  mov     [rsp+170h+var_140], rax
0x140003c19  mov     dword ptr [rsp+170h+var_148], r12d
0x140003c1e  mov     [rsp+170h+var_150], r15
0x140003c23  call    ??$_CallSETranslator@V__FrameHandler4@@@@YAHPEAUEHExceptionRecord@@PEA_KPEAU_CONTEXT@@PEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@K1H@Z; _CallSETranslator<__FrameHandler4>(EHExceptionRecord *,unsigned __int64 *,_CONTEXT *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,ulong,unsigned __int64 *,int)
0x140003c28  test    eax, eax
0x140003c2a  jnz     loc_140003E44
0x140003c30  mov     r8, [rdi+8]; unsigned __int64
0x140003c34  lea     rcx, [rbp+70h+var_70]; this
0x140003c38  mov     rdx, r15; struct FH4::FuncInfo4 *
0x140003c3b  call    ??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z; FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)
0x140003c40  cmp     [rbp+70h+var_70], 0
0x140003c44  jbe     loc_140003E64
0x140003c4a  mov     dword ptr [rsp+170h+var_148], r12d
0x140003c4f  lea     rdx, [rbp+70h+var_70]
0x140003c53  mov     r9, rdi
0x140003c56  mov     [rsp+170h+var_150], r15
0x140003c5b  mov     r8d, r14d
0x140003c5e  lea     rcx, [rbp+70h+var_E0]
0x140003c62  call    ?GetRangeOfTrysToCheck@__FrameHandler4@@SA?AU?$pair@Viterator@TryBlockMap4@FH4@@V123@@std@@AEAVTryBlockMap4@FH4@@HPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@5@H@Z; __FrameHandler4::GetRangeOfTrysToCheck(FH4::TryBlockMap4 &,int,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)
0x140003c67  movups  xmm1, [rbp+70h+var_E0]
0x140003c6b  movdqa  xmm0, xmm1
0x140003c6f  psrldq  xmm0, 8
0x140003c74  movd    eax, xmm0
0x140003c78  movdqu  xmmword ptr [rsp+170h+var_F8], xmm1
0x140003c7e  cmp     eax, [rbp+70h+var_C8]
0x140003c81  jnb     loc_140003E44
0x140003c87  mov     eax, dword ptr [rbp+70h+var_F8+8]
0x140003c8a  lea     r11, cs:140000000h
0x140003c91  mov     [rsp+170h+var_110], eax
0x140003c95  movq    r13, xmm1
0x140003c9a  movups  xmm0, xmmword ptr [r13+18h]
0x140003c9f  movq    rax, xmm0
0x140003ca4  movups  xmmword ptr [rsp+170h+var_F8], xmm0
0x140003ca9  cmp     eax, r14d
0x140003cac  jg      loc_140003D98
0x140003cb2  shr     rax, 20h
0x140003cb6  cmp     r14d, eax
0x140003cb9  jg      loc_140003D98
0x140003cbf  mov     r9, [rdi+10h]
0x140003cc3  lea     rdx, [rsp+170h+var_F8]; struct FH4::TryBlockMapEntry4 *
0x140003cc8  mov     r8, [rdi+8]; unsigned __int64
0x140003ccc  lea     rcx, [rbp+70h+var_C0]; this
0x140003cd0  mov     r9d, [r9]; int
0x140003cd3  call    ??0HandlerMap4@FH4@@QEAA@PEBUTryBlockMapEntry4@1@_KH@Z; FH4::HandlerMap4::HandlerMap4(FH4::TryBlockMapEntry4 const *,unsigned __int64,int)
0x140003cd8  mov     rax, [rbp+70h+var_B0]
0x140003cdc  lea     rcx, [rbp+70h+var_C0]; this
0x140003ce0  mov     [rbp+70h+var_B8], rax
0x140003ce4  call    ?DecompHandler@HandlerMap4@FH4@@AEAAXXZ; FH4::HandlerMap4::DecompHandler(void)
0x140003ce9  mov     rax, [rbp+70h+var_B0]
0x140003ced  lea     rcx, [rbp+70h+var_C0]; this
0x140003cf1  mov     ebx, [rbp+70h+var_C0]
0x140003cf4  mov     [rbp+70h+var_B8], rax
0x140003cf8  call    ?DecompHandler@HandlerMap4@FH4@@AEAAXXZ; FH4::HandlerMap4::DecompHandler(void)
0x140003cfd  sub     ebx, 1
0x140003d00  jz      short loc_140003D11
0x140003d02  lea     rcx, [rbp+70h+var_C0]; this
0x140003d06  call    ?DecompHandler@HandlerMap4@FH4@@AEAAXXZ; FH4::HandlerMap4::DecompHandler(void)
0x140003d0b  sub     rbx, 1
0x140003d0f  jnz     short loc_140003D02
0x140003d11  movsxd  rbx, [rbp+70h+var_A0]
0x140003d15  test    ebx, ebx
0x140003d17  jz      short loc_140003D3D
0x140003d19  call    _GetImageBase
0x140003d1e  add     rax, rbx
0x140003d21  jz      short loc_140003D3D
0x140003d23  movsxd  rbx, [rbp+70h+var_A0]
0x140003d27  test    ebx, ebx
0x140003d29  jz      short loc_140003D35
0x140003d2b  call    _GetImageBase
0x140003d30  add     rax, rbx
0x140003d33  jmp     short loc_140003D37
0x140003d35  xor     eax, eax
0x140003d37  cmp     byte ptr [rax+10h], 0
0x140003d3b  jnz     short loc_140003D91
0x140003d3d  test    [rbp+70h+var_A4], 40h
0x140003d41  jnz     short loc_140003D91
0x140003d43  mov     rax, qword ptr [rsp+170h+var_108]
0x140003d48  mov     r9, rdi
0x140003d4b  mov     r8, [rsp+170h+var_100]
0x140003d50  mov     rcx, rsi; struct EHExceptionRecord *
0x140003d53  mov     rdx, [rbp+70h+var_E8]; unsigned __int64 *
0x140003d57  mov     [rsp+170h+var_118], 0; char
0x140003d5c  mov     byte ptr [rsp+170h+var_120], 1; int
0x140003d61  mov     qword ptr [rsp+170h+var_128], rax; int
0x140003d66  lea     rax, [rsp+170h+var_F8]
0x140003d6b  mov     [rsp+170h+var_130], r12d; int
0x140003d70  mov     [rsp+170h+var_138], rax; __int64
0x140003d75  lea     rax, [rbp+70h+var_A8]
0x140003d79  mov     [rsp+170h+var_140], 0; __int64
0x140003d82  mov     [rsp+170h+var_148], rax; struct FH4::HandlerType4 *
0x140003d87  mov     [rsp+170h+var_150], r15; struct FH4::FuncInfo4 *
0x140003d8c  call    CatchIt___FrameHandler4_
0x140003d91  lea     r11, cs:140000000h
0x140003d98  mov     r10, [r13+8]
0x140003d9c  mov     rdx, r10
0x140003d9f  movzx   ecx, byte ptr [r10]
0x140003da3  and     ecx, 0Fh
0x140003da6  movsx   r9, byte ptr [rcx+r11+7460h]
0x140003daf  mov     cl, [rcx+r11+7470h]
0x140003db7  sub     rdx, r9
0x140003dba  mov     eax, [rdx-4]
0x140003dbd  shr     eax, cl
0x140003dbf  mov     [r13+8], rdx
0x140003dc3  mov     [r13+18h], eax
0x140003dc7  movzx   ecx, byte ptr [rdx]
0x140003dca  mov     rdx, r10
0x140003dcd  and     ecx, 0Fh
0x140003dd0  movsx   r8, byte ptr [rcx+r11+7460h]
0x140003dd9  mov     cl, [rcx+r11+7470h]
0x140003de1  sub     rdx, r8
0x140003de4  sub     rdx, r9
0x140003de7  mov     eax, [rdx-4]
0x140003dea  shr     eax, cl
0x140003dec  mov     [r13+1Ch], eax
0x140003df0  mov     [r13+8], rdx
0x140003df4  movzx   ecx, byte ptr [rdx]
0x140003df7  and     ecx, 0Fh
0x140003dfa  movsx   rax, byte ptr [rcx+r11+7460h]
0x140003e03  mov     cl, [rcx+r11+7470h]
0x140003e0b  sub     r10, rax
0x140003e0e  sub     r10, r8
0x140003e11  sub     r10, r9
0x140003e14  mov     eax, [r10-4]
0x140003e18  shr     eax, cl
0x140003e1a  mov     [r13+20h], eax
0x140003e1e  lea     rax, [r10+4]
0x140003e22  mov     [r13+8], r10
0x140003e26  mov     ecx, [r10]
0x140003e29  mov     [r13+24h], ecx
0x140003e2d  mov     ecx, [rsp+170h+var_110]
0x140003e31  inc     ecx
0x140003e33  mov     [r13+8], rax
0x140003e37  mov     [rsp+170h+var_110], ecx
0x140003e3b  cmp     ecx, [rbp+70h+var_C8]
0x140003e3e  jb      loc_140003C9A
0x140003e44  mov     rcx, [rbp+70h+var_48]
0x140003e48  xor     rcx, rsp; StackCookie
0x140003e4b  call    __security_check_cookie
0x140003e50  add     rsp, 138h
0x140003e57  pop     r15
0x140003e59  pop     r14
0x140003e5b  pop     r13
0x140003e5d  pop     r12
0x140003e5f  pop     rdi
0x140003e60  pop     rsi
0x140003e61  pop     rbx
0x140003e62  pop     rbp
0x140003e63  retn
0x140003e64  call    abort
```
