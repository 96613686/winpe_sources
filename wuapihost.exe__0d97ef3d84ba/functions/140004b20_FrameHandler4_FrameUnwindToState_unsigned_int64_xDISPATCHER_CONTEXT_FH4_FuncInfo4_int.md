# __FrameHandler4::FrameUnwindToState(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)

- ea: `0x140004b20`
- end: `0x140004e2c`
- name: `?FrameUnwindToState@__FrameHandler4@@SAXPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H@Z`
- size: `780`
- prototype: `static void(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, struct FH4::FuncInfo4 *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x1400024e4`
- `0x1400040e0`

## callees

- `0x140001500`
- `0x140002a80`
- `0x140002ab0`
- `0x140002cac`
- `0x140003008`
- `0x140003178`
- `0x140004b20`
- `0x140004fb4`
- `0x140005080`
- `0x140005154`
- `0x140005350`
- `0x140005400`
- `0x1400056be`

## pseudocode

```c
void __fastcall __FrameHandler4::FrameUnwindToState(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        struct FH4::FuncInfo4 *a3,
        int a4)
{
  int StateFromIterators; // edi
  struct _xDISPATCHER_CONTEXT *v9; // r14
  __int64 v10; // rax
  __int64 *p_ImageBase; // rsi
  __int64 v12; // rcx
  FH4::UWMap4 *v13; // rdx
  _BYTE *v14; // rdx
  __int64 v15; // rcx
  FH4::UWMap4 *v16; // r15
  FH4::UWMap4 *v17; // rbx
  __m128i v18; // xmm6
  int v19; // r9d
  int v20; // eax
  int v21; // ecx
  unsigned __int64 v22; // rdx
  __m128i v23; // xmm6
  unsigned __int64 v24; // r8
  __int64 v25; // rax
  FH4::UWMap4 *v26[2]; // [rsp+30h] [rbp-108h] BYREF
  int v27; // [rsp+40h] [rbp-F8h]
  int v28; // [rsp+44h] [rbp-F4h]
  int v29; // [rsp+48h] [rbp-F0h]
  int *v30; // [rsp+50h] [rbp-E8h] BYREF
  FH4::UWMap4 *v31; // [rsp+58h] [rbp-E0h]
  unsigned __int64 *v32; // [rsp+60h] [rbp-D8h]
  __int64 ImageBase; // [rsp+68h] [rbp-D0h]
  struct _xDISPATCHER_CONTEXT *v34; // [rsp+70h] [rbp-C8h]
  unsigned __int64 *v35; // [rsp+78h] [rbp-C0h]
  __int64 *v36; // [rsp+80h] [rbp-B8h]
  int *v37; // [rsp+88h] [rbp-B0h]
  FH4::UWMap4 *v38; // [rsp+90h] [rbp-A8h]
  __int128 v39; // [rsp+A0h] [rbp-98h] BYREF
  __m128i v40; // [rsp+B0h] [rbp-88h]
  int v41; // [rsp+C0h] [rbp-78h] BYREF
  FH4::UWMap4 *v42; // [rsp+C8h] [rbp-70h]
  __int128 v43; // [rsp+D0h] [rbp-68h]

  v35 = a1;
  v32 = a1;
  v29 = a4;
  ImageBase = GetImageBase();
  StateFromIterators = __FrameHandler4::StateFromControlPc(a3, a2);
  v9 = a2 + 1;
  v34 = a2 + 1;
  if ( LODWORD(a2[1].ControlPc) )
  {
    if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
      abort();
    StateFromIterators = LODWORD(v9->ControlPc) - 2;
  }
  else if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
  {
    StateFromIterators = *(_DWORD *)(_vcrt_getptd() + 120);
    *(_DWORD *)(_vcrt_getptd() + 120) = -2;
  }
  v10 = _vcrt_getptd();
  ++*(_DWORD *)(v10 + 48);
  p_ImageBase = &a2->ImageBase;
  v36 = p_ImageBase;
  v12 = *p_ImageBase;
  v13 = 0;
  v42 = 0;
  v43 = 0;
  if ( *((_DWORD *)a3 + 2) )
  {
    v14 = (_BYTE *)(v12 + *((int *)a3 + 2));
    v15 = *v14 & 0xF;
    v13 = (FH4::UWMap4 *)&v14[-*((char *)&FH4::s_negLengthTab + v15)];
    v41 = *((_DWORD *)v13 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v15);
    v42 = v13;
  }
  else
  {
    v41 = 0;
  }
  v26[0] = (FH4::UWMap4 *)&v41;
  v26[1] = v13;
  v30 = &v41;
  v31 = v13;
  FH4::UWMap4::getStartStop(
    (FH4::UWMap4 *)&v41,
    StateFromIterators,
    a4,
    (struct FH4::UWMap4::iterator *)v26,
    (struct FH4::UWMap4::iterator *)&v30);
  while ( 1 )
  {
    v37 = &v41;
    v38 = v42;
    v16 = v26[1];
    if ( v26[1] < v42 || v26[1] <= v31 )
      break;
    FH4::UWMap4::ReadEntry(v26[0], (unsigned __int8 **)&v26[1]);
    v26[1] = v16;
    v17 = v26[0];
    v40 = *((__m128i *)v26[0] + 1);
    v18 = v40;
    v39 = *(_OWORD *)v26;
    FH4::UWMap4::ReadEntry(v26[0], (unsigned __int8 **)&v26[1]);
    v26[1] = (FH4::UWMap4 *)((char *)v16 - *((unsigned int *)v17 + 4));
    StateFromIterators = FH4::UWMap4::getStateFromIterators(
                           (const struct FH4::UWMap4::iterator *)&v30,
                           a4,
                           (const struct FH4::UWMap4::iterator *)&v39,
                           StateFromIterators,
                           (const struct FH4::UWMap4::iterator *)v26);
    v28 = StateFromIterators;
    v27 = 0;
    v19 = 0;
    v20 = _mm_cvtsi128_si32(_mm_srli_si128(v18, 8));
    v21 = _mm_cvtsi128_si32(_mm_srli_si128(v18, 4));
    if ( v21 )
      v19 = v20;
    v27 = v19;
    if ( v19 )
    {
      LODWORD(v9->ControlPc) = StateFromIterators + 2;
      if ( (unsigned int)(v21 - 1) <= 1 )
      {
        v22 = *v32;
        v23 = _mm_srli_si128(v18, 12);
        if ( v21 == 2 )
          v24 = *(_QWORD *)((unsigned int)_mm_cvtsi128_si32(v23) + v22);
        else
          v24 = v22 + (unsigned int)_mm_cvtsi128_si32(v23);
        CallSettingFrameEncoded(*p_ImageBase + v19, v22, v24, 259);
      }
      else
      {
        CallSettingFrame(*p_ImageBase + v19, a1, 259);
      }
      SetImageBase(ImageBase);
    }
  }
  if ( *(int *)(_vcrt_getptd() + 48) > 0 )
  {
    v25 = _vcrt_getptd();
    --*(_DWORD *)(v25 + 48);
  }
}

```

## disassembly

```asm
0x140004b20  mov     rax, rsp
0x140004b23  push    rbx
0x140004b24  push    rsi
0x140004b25  push    rdi
0x140004b26  push    r12
0x140004b28  push    r13
0x140004b2a  push    r14
0x140004b2c  push    r15
0x140004b2e  sub     rsp, 100h
0x140004b35  movaps  xmmword ptr [rax-48h], xmm6
0x140004b39  mov     rax, cs:__security_cookie
0x140004b40  xor     rax, rsp
0x140004b43  mov     [rsp+138h+var_58], rax
0x140004b4b  mov     r13d, r9d
0x140004b4e  mov     rbx, r8
0x140004b51  mov     rsi, rdx
0x140004b54  mov     r12, rcx
0x140004b57  mov     [rsp+138h+var_C0], rcx
0x140004b5c  mov     [rsp+138h+var_D8], rcx
0x140004b61  mov     [rsp+138h+var_F0], r9d
0x140004b66  call    _GetImageBase
0x140004b6b  mov     [rsp+138h+var_D0], rax
0x140004b70  mov     rdx, rsi; struct _xDISPATCHER_CONTEXT *
0x140004b73  mov     rcx, rbx; struct FH4::FuncInfo4 *
0x140004b76  call    ?StateFromControlPc@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler4::StateFromControlPc(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *)
0x140004b7b  mov     edi, eax
0x140004b7d  lea     r14, [rsi+48h]
0x140004b81  mov     [rsp+138h+var_C8], r14
0x140004b86  cmp     dword ptr [r14], 0
0x140004b8a  jz      short loc_140004BA3
0x140004b8c  call    __vcrt_getptd
0x140004b91  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x140004b95  jnz     loc_140004E26
0x140004b9b  mov     edi, [r14]
0x140004b9e  sub     edi, 2
0x140004ba1  jmp     short loc_140004BC2
0x140004ba3  call    __vcrt_getptd
0x140004ba8  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x140004bac  jz      short loc_140004BC2
0x140004bae  call    __vcrt_getptd
0x140004bb3  mov     edi, [rax+78h]
0x140004bb6  call    __vcrt_getptd
0x140004bbb  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x140004bc2  call    __vcrt_getptd
0x140004bc7  inc     dword ptr [rax+30h]
0x140004bca  add     rsi, 8
0x140004bce  mov     [rsp+138h+var_B8], rsi
0x140004bd6  mov     rcx, [rsi]
0x140004bd9  xor     edx, edx
0x140004bdb  mov     [rsp+138h+var_70], rdx
0x140004be3  xorps   xmm0, xmm0
0x140004be6  movups  [rsp+138h+var_68], xmm0
0x140004bee  cmp     [rbx+8], edx
0x140004bf1  jz      short loc_140004C31
0x140004bf3  movsxd  rdx, dword ptr [rbx+8]
0x140004bf7  add     rdx, rcx
0x140004bfa  movzx   ecx, byte ptr [rdx]
0x140004bfd  and     ecx, 0Fh
0x140004c00  lea     r8, cs:140000000h
0x140004c07  movsx   rax, byte ptr [rcx+r8+7460h]
0x140004c10  sub     rdx, rax
0x140004c13  mov     cl, [rcx+r8+7470h]
0x140004c1b  mov     eax, [rdx-4]
0x140004c1e  shr     eax, cl
0x140004c20  mov     [rsp+138h+var_78], eax
0x140004c27  mov     [rsp+138h+var_70], rdx
0x140004c2f  jmp     short loc_140004C38
0x140004c31  mov     [rsp+138h+var_78], edx
0x140004c38  lea     rax, [rsp+138h+var_78]
0x140004c40  mov     [rsp+138h+var_108], rax
0x140004c45  mov     [rsp+138h+var_108+8], rdx
0x140004c4a  lea     rax, [rsp+138h+var_78]
0x140004c52  mov     [rsp+138h+var_E8], rax
0x140004c57  mov     [rsp+138h+var_E0], rdx
0x140004c5c  lea     rax, [rsp+138h+var_E8]
0x140004c61  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x140004c66  lea     r9, [rsp+138h+var_108]; struct FH4::UWMap4::iterator *
0x140004c6b  mov     r8d, r13d; int
0x140004c6e  mov     edx, edi; int
0x140004c70  lea     rcx, [rsp+138h+var_78]; this
0x140004c78  call    ?getStartStop@UWMap4@FH4@@QEAAXHHAEAViterator@12@0@Z; FH4::UWMap4::getStartStop(int,int,FH4::UWMap4::iterator &,FH4::UWMap4::iterator &)
0x140004c7d  nop
0x140004c7e  lea     rax, [rsp+138h+var_78]
0x140004c86  mov     [rsp+138h+var_B0], rax
0x140004c8e  mov     rax, [rsp+138h+var_70]
0x140004c96  mov     [rsp+138h+var_A8], rax
0x140004c9e  mov     r15, [rsp+138h+var_108+8]
0x140004ca3  cmp     r15, rax
0x140004ca6  jb      loc_140004DE8
0x140004cac  cmp     r15, [rsp+138h+var_E0]
0x140004cb1  jbe     loc_140004DE8
0x140004cb7  lea     rdx, [rsp+138h+var_108+8]; unsigned __int8 **
0x140004cbc  mov     rcx, [rsp+138h+var_108]; this
0x140004cc1  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x140004cc6  mov     [rsp+138h+var_108+8], r15
0x140004ccb  mov     rbx, [rsp+138h+var_108]
0x140004cd0  movups  xmm6, xmmword ptr [rbx+10h]
0x140004cd4  movups  [rsp+138h+var_88], xmm6
0x140004cdc  movaps  xmm0, xmmword ptr [rsp+138h+var_108]
0x140004ce1  movdqa  [rsp+138h+var_98], xmm0
0x140004cea  lea     rdx, [rsp+138h+var_108+8]; unsigned __int8 **
0x140004cef  mov     rcx, rbx; this
0x140004cf2  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x140004cf7  mov     eax, [rbx+10h]
0x140004cfa  sub     r15, rax
0x140004cfd  mov     [rsp+138h+var_108+8], r15
0x140004d02  lea     rax, [rsp+138h+var_108]
0x140004d07  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x140004d0c  mov     r9d, edi; int
0x140004d0f  lea     r8, [rsp+138h+var_98]; struct FH4::UWMap4::iterator *
0x140004d17  mov     edx, r13d; int
0x140004d1a  lea     rcx, [rsp+138h+var_E8]; struct FH4::UWMap4::iterator *
0x140004d1f  call    ?getStateFromIterators@UWMap4@FH4@@SAHAEBViterator@12@H0H0@Z; FH4::UWMap4::getStateFromIterators(FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &)
0x140004d24  mov     edi, eax
0x140004d26  mov     [rsp+138h+var_F4], eax
0x140004d2a  mov     [rsp+138h+var_F8], 0
0x140004d32  xor     r9d, r9d
0x140004d35  movdqa  xmm0, xmm6
0x140004d39  psrldq  xmm0, 8
0x140004d3e  movd    eax, xmm0
0x140004d42  movdqa  xmm1, xmm6
0x140004d46  psrldq  xmm1, 4
0x140004d4b  movd    ecx, xmm1
0x140004d4f  test    ecx, ecx
0x140004d51  cmovnz  r9d, eax
0x140004d55  mov     [rsp+138h+var_F8], r9d
0x140004d5a  test    r9d, r9d
0x140004d5d  jz      loc_140004DE3
0x140004d63  lea     eax, [rdi+2]
0x140004d66  mov     [r14], eax
0x140004d69  lea     eax, [rcx-1]
0x140004d6c  cmp     eax, 1
0x140004d6f  jbe     short loc_140004D87
0x140004d71  movsxd  rcx, r9d
0x140004d74  add     rcx, [rsi]
0x140004d77  mov     r8d, 103h
0x140004d7d  mov     rdx, r12
0x140004d80  call    _CallSettingFrame
0x140004d85  jmp     short loc_140004DBC
0x140004d87  mov     rax, [rsp+138h+var_D8]
0x140004d8c  mov     rdx, [rax]
0x140004d8f  psrldq  xmm6, 0Ch
0x140004d94  cmp     ecx, 2
0x140004d97  jnz     short loc_140004DA3
0x140004d99  movd    eax, xmm6
0x140004d9d  mov     r8, [rax+rdx]
0x140004da1  jmp     short loc_140004DAB
0x140004da3  movd    r8d, xmm6
0x140004da8  add     r8, rdx
0x140004dab  movsxd  rcx, r9d
0x140004dae  add     rcx, [rsi]
0x140004db1  mov     r9d, 103h
0x140004db7  call    _CallSettingFrameEncoded
0x140004dbc  mov     rcx, [rsp+138h+var_D0]
0x140004dc1  call    _SetImageBase
0x140004dc6  jmp     short loc_140004DE3
0x140004dc8  mov     edi, [rsp+138h+var_F4]
0x140004dcc  mov     r14, [rsp+138h+var_C8]
0x140004dd1  mov     r12, [rsp+138h+var_C0]
0x140004dd6  mov     r13d, [rsp+138h+var_F0]
0x140004ddb  mov     rsi, [rsp+138h+var_B8]
0x140004de3  jmp     loc_140004C7E
0x140004de8  call    __vcrt_getptd
0x140004ded  cmp     dword ptr [rax+30h], 0
0x140004df1  jle     short loc_140004DFB
0x140004df3  call    __vcrt_getptd
0x140004df8  dec     dword ptr [rax+30h]
0x140004dfb  mov     rcx, [rsp+138h+var_58]
0x140004e03  xor     rcx, rsp; StackCookie
0x140004e06  call    __security_check_cookie
0x140004e0b  movaps  xmm6, [rsp+138h+var_48]
0x140004e13  add     rsp, 100h
0x140004e1a  pop     r15
0x140004e1c  pop     r14
0x140004e1e  pop     r13
0x140004e20  pop     r12
0x140004e22  pop     rdi
0x140004e23  pop     rsi
0x140004e24  pop     rbx
0x140004e25  retn
0x140004e26  call    abort
0x14000671b  push    rbp
0x14000671d  sub     rsp, 30h
0x140006721  mov     rbp, rdx
0x140006724  call    __FrameUnwindFilter
0x140006729  nop
0x14000672a  add     rsp, 30h
0x14000672e  pop     rbp
0x14000672f  retn
0x140006731  push    rbp
0x140006733  sub     rsp, 30h
0x140006737  mov     rbp, rdx
0x14000673a  call    __vcrt_getptd
0x14000673f  cmp     dword ptr [rax+30h], 0
0x140006743  jle     short loc_14000674D
0x140006745  call    __vcrt_getptd
0x14000674a  dec     dword ptr [rax+30h]
0x14000674d  add     rsp, 30h
0x140006751  pop     rbp
0x140006752  retn
```
