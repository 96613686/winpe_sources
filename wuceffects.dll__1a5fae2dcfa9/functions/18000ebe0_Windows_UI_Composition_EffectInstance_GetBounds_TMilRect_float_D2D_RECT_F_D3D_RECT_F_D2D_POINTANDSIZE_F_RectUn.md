# Windows::UI::Composition::EffectInstance::GetBounds(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,uint,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *)

- ea: `0x18000ebe0`
- end: `0x18000efb1`
- name: `?GetBounds@EffectInstance@Composition@UI@Windows@@UEBAJPEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@IPEAV5@@Z`
- size: `977`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800096f0`
- `0x180009ee8`
- `0x18000ebe0`
- `0x18000fb90`
- `0x18000fba4`
- `0x18001f204`
- `0x180021060`
- `0x180021084`
- `0x1800257b8`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ed15`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ee1b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ee99`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ed15`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ee1b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ee99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed90`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectInstance::GetBounds(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rbx
  SIZE_T v7; // rdi
  HANDLE ProcessHeap; // rax
  _OWORD *v9; // rax
  _OWORD *v10; // rdi
  char *v11; // rsi
  unsigned int i; // ecx
  int v13; // r12d
  const char *v14; // r9
  __int64 v15; // r15
  __int64 v16; // rcx
  void *v17; // rcx
  unsigned __int64 v18; // rdx
  HANDLE v19; // rax
  __int64 result; // rax
  unsigned __int64 v21; // r8
  unsigned int v22; // ecx
  char *v23; // rdx
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rdx
  _DWORD *v27; // r9
  _OWORD *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r10
  unsigned __int64 v31; // r11
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r8
  unsigned __int64 v36; // [rsp+30h] [rbp-98h] BYREF
  void *v37; // [rsp+38h] [rbp-90h] BYREF
  char *v38; // [rsp+40h] [rbp-88h]
  char *v39; // [rsp+48h] [rbp-80h]
  void *v40; // [rsp+50h] [rbp-78h] BYREF
  _OWORD *v41; // [rsp+58h] [rbp-70h] BYREF
  __int64 v42; // [rsp+60h] [rbp-68h]
  _OWORD *v43; // [rsp+68h] [rbp-60h]
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp-58h] BYREF
  char v45[16]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    v43 = a4;
    v42 = a2;
    v5 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 80LL))(*(_QWORD *)(a1 + 16) + 16LL);
    v6 = v5;
    v41 = (_OWORD *)v5;
    v7 = 16 * v5;
    if ( !is_mul_ok(v5, 0x10u) )
      v7 = -1;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, v7);
    v10 = v9;
    if ( !v9 )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v36 = (unsigned __int64)v9;
    v11 = (char *)v9;
    while ( v6 )
    {
      --v6;
      TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(v11);
      v11 += 16;
    }
    v41 = v10;
    for ( i = 0; i < (unsigned int)v5; ++i )
      v10[i] = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty;
    v13 = 0;
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(&v37);
    v15 = 0;
LABEL_12:
    if ( (unsigned int)v15 >= (unsigned int)v5 )
      goto LABEL_16;
    v16 = *(_QWORD *)(a1 + 16);
    if ( (__int64)(*(_QWORD *)(v16 + 56) - *(_QWORD *)(v16 + 48)) >> 3 <= (unsigned __int64)(unsigned int)v15 )
    {
      std::_Xout_of_range("invalid vector subscript");
LABEL_15:
      v13 = -2147024809;
      DoStackCaptureDirect(-2147024809, 0x24Fu);
LABEL_16:
      v17 = v37;
      if ( v37 )
      {
        v18 = (v39 - (_BYTE *)v37) & 0xFFFFFFFFFFFFFFF0uLL;
        v36 = v18;
        v40 = v37;
        if ( v18 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v40, &v36);
          v18 = v36;
          v17 = v40;
        }
        operator delete(v17, v18);
      }
      if ( v13 < 0 )
      {
        DoStackCaptureDirect(v13, 0x18Bu);
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v41);
      }
      else
      {
        *v43 = v10[(unsigned int)(v5 - 1)];
        if ( v10 )
        {
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v10);
        }
      }
      return (unsigned int)v13;
    }
    _mm_lfence();
    v21 = *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8 * v15);
    v36 = v21;
    v22 = *(_DWORD *)(v21 + 20);
    LODWORD(v40) = v22;
    v23 = v38;
    if ( v37 != v38 )
    {
      v23 = (char *)v37;
      v38 = (char *)v37;
    }
    v24 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( (unsigned int)v24 >= v22 )
        {
          v25 = *(_QWORD *)(a1 + 16);
          v26 = *(_QWORD *)(v25 + 48);
          if ( (*(_QWORD *)(v25 + 56) - v26) >> 3 > (unsigned __int64)(unsigned int)v15 )
          {
            v33 = *(_QWORD *)v21;
            v34 = *(_QWORD *)(a1 + 32);
            if ( !v34 || (v35 = *(_QWORD *)(v34 + 8 * v15)) == 0 )
              v35 = *(_QWORD *)(*(_QWORD *)(v26 + 8 * v15) + 24LL);
            v10[(unsigned int)v15] = *(_OWORD *)(*(__int64 (__fastcall **)(__int64, char *, __int64, void **))(*(_QWORD *)v33 + 120LL))(
                                                  v33,
                                                  v45,
                                                  v35,
                                                  &v37);
            v15 = (unsigned int)(v15 + 1);
            goto LABEL_12;
          }
          std::_Xout_of_range("invalid vector subscript");
        }
        v27 = (_DWORD *)(*(_QWORD *)(v21 + 8) + 8 * v24);
        if ( *v27 != 2 )
          break;
        v28 = (_OWORD *)(16LL * (unsigned int)v27[1] + v42);
        if ( v23 != v39 )
        {
          *(_OWORD *)v23 = *v28;
          v23 = v38 + 16;
          v38 += 16;
          goto LABEL_33;
        }
LABEL_38:
        std::vector<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>>::_Emplace_reallocate<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &>(
          &v37,
          v23,
          v28);
        v23 = v38;
        v21 = v36;
LABEL_33:
        v24 = (unsigned int)(v24 + 1);
        v22 = (unsigned int)v40;
      }
      if ( *v27 == 1 )
      {
        v32 = (unsigned int)v27[1];
      }
      else
      {
        if ( *v27 != 3 )
          goto LABEL_15;
        v29 = *(_QWORD *)(a1 + 16);
        v30 = *(_QWORD *)(v29 + 24);
        v31 = (unsigned int)v27[1];
        if ( (*(_QWORD *)(v29 + 32) - v30) >> 3 <= v31 )
        {
          std::_Xout_of_range("invalid vector subscript");
          goto LABEL_38;
        }
        v32 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v30 + 8 * v31) + 8LL) - 4LL);
      }
      v28 = &v10[v32];
      if ( v23 == v39 )
        goto LABEL_38;
      *(_OWORD *)v23 = *v28;
      v23 = v38 + 16;
      v38 += 16;
      v24 = (unsigned int)(v24 + 1);
      v22 = (unsigned int)v40;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x18E,
                           (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectinstance.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000ebe0  mov     [rsp+arg_8], rbx
0x18000ebe5  mov     [rsp+arg_10], rsi
0x18000ebea  push    rdi
0x18000ebeb  push    r12
0x18000ebed  push    r13
0x18000ebef  push    r14
0x18000ebf1  push    r15
0x18000ebf3  sub     rsp, 0A0h
0x18000ebfa  mov     rax, cs:__security_cookie
0x18000ec01  xor     rax, rsp
0x18000ec04  mov     [rsp+0C8h+var_30], rax
0x18000ec0c  mov     [rsp+0C8h+var_60], r9
0x18000ec11  mov     [rsp+0C8h+var_68], rdx
0x18000ec16  mov     r13, rcx
0x18000ec19  mov     rcx, [rcx+10h]
0x18000ec1d  add     rcx, 10h
0x18000ec21  mov     rax, [rcx]
0x18000ec24  mov     rax, [rax+50h]
0x18000ec28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec2d  mov     r14d, eax
0x18000ec30  mov     ebx, r14d
0x18000ec33  mov     [rsp+0C8h+var_70], rbx
0x18000ec38  mov     eax, 10h
0x18000ec3d  mul     r14
0x18000ec40  mov     rdi, rax
0x18000ec43  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ec4a  cmovb   rdi, rax
0x18000ec4e  call    cs:__imp_GetProcessHeap
0x18000ec54  mov     rcx, rax; hHeap
0x18000ec57  mov     r8, rdi; dwBytes
0x18000ec5a  xor     edx, edx; dwFlags
0x18000ec5c  call    cs:__imp_HeapAlloc
0x18000ec62  mov     rdi, rax
0x18000ec65  test    rax, rax
0x18000ec68  jnz     short loc_18000EC9B
0x18000ec6a  xorps   xmm0, xmm0
0x18000ec6d  movups  [rsp+0C8h+var_50], xmm0
0x18000ec72  lea     rax, aBadAllocation; "bad allocation"
0x18000ec79  mov     qword ptr [rsp+0C8h+var_50], rax
0x18000ec7e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000ec85  mov     [rsp+0C8h+pExceptionObject], rax
0x18000ec8a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000ec91  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000ec96  call    _CxxThrowException_0
0x18000ec9b  mov     [rsp+0C8h+var_98], rdi
0x18000eca0  mov     rsi, rdi
0x18000eca3  test    rbx, rbx
0x18000eca6  jz      short loc_18000ECB9
0x18000eca8  dec     rbx
0x18000ecab  mov     rcx, rsi
0x18000ecae  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000ecb3  add     rsi, 10h
0x18000ecb7  jmp     short loc_18000ECA3
0x18000ecb9  mov     [rsp+0C8h+var_70], rdi
0x18000ecbe  xor     ecx, ecx
0x18000ecc0  test    r14d, r14d
0x18000ecc3  jz      short loc_18000ECDC
0x18000ecc5  movups  xmm0, cs:?sc_rcEmpty@?$TMilRect@MUD2D_RECT_F@@UD3D_RECT_F@@UNotNeeded@RectUniqueness@@@@2V1@B; TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded> const TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::sc_rcEmpty
0x18000eccc  mov     eax, ecx
0x18000ecce  add     rax, rax
0x18000ecd1  movups  xmmword ptr [rdi+rax*8], xmm0
0x18000ecd5  inc     ecx
0x18000ecd7  cmp     ecx, r14d
0x18000ecda  jb      short loc_18000ECC5
0x18000ecdc  xor     r12d, r12d
0x18000ecdf  lea     rcx, [rsp+0C8h+var_90]
0x18000ece4  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000ece9  nop
0x18000ecea  xor     r15d, r15d
0x18000eced  cmp     r15d, r14d
0x18000ecf0  jnb     short loc_18000ED2F
0x18000ecf2  mov     rcx, [r13+10h]
0x18000ecf6  mov     ebx, r15d
0x18000ecf9  mov     rax, [rcx+38h]
0x18000ecfd  sub     rax, [rcx+30h]
0x18000ed01  sar     rax, 3
0x18000ed05  cmp     rax, rbx
0x18000ed08  ja      loc_18000EDC7
0x18000ed0e  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000ed15  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000ed1b  mov     edx, 24Fh; unsigned int
0x18000ed20  mov     r12d, 80070057h
0x18000ed26  mov     ecx, r12d; int
0x18000ed29  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000ed2e  nop
0x18000ed2f  mov     rcx, [rsp+0C8h+var_90]; void *
0x18000ed34  test    rcx, rcx
0x18000ed37  jz      short loc_18000ED61
0x18000ed39  mov     rdx, [rsp+0C8h+var_80]
0x18000ed3e  sub     rdx, rcx
0x18000ed41  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18000ed45  mov     [rsp+0C8h+var_98], rdx
0x18000ed4a  mov     [rsp+0C8h+var_78], rcx
0x18000ed4f  cmp     rdx, 1000h
0x18000ed56  jnb     loc_18000EF6C
0x18000ed5c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ed61  test    r12d, r12d
0x18000ed64  js      loc_18000EF8A
0x18000ed6a  lea     ecx, [r14-1]
0x18000ed6e  add     rcx, rcx
0x18000ed71  movups  xmm0, xmmword ptr [rdi+rcx*8]
0x18000ed75  mov     rax, [rsp+0C8h+var_60]
0x18000ed7a  movups  xmmword ptr [rax], xmm0
0x18000ed7d  test    rdi, rdi
0x18000ed80  jz      short loc_18000ED97
0x18000ed82  call    cs:__imp_GetProcessHeap
0x18000ed88  mov     rcx, rax; hHeap
0x18000ed8b  mov     r8, rdi; lpMem
0x18000ed8e  xor     edx, edx; dwFlags
0x18000ed90  call    cs:__imp_HeapFree
0x18000ed96  nop
0x18000ed97  mov     eax, r12d
0x18000ed9a  mov     rcx, [rsp+0C8h+var_30]
0x18000eda2  xor     rcx, rsp; StackCookie
0x18000eda5  call    __security_check_cookie
0x18000edaa  lea     r11, [rsp+0C8h+var_28]
0x18000edb2  mov     rbx, [r11+38h]
0x18000edb6  mov     rsi, [r11+40h]
0x18000edba  mov     rsp, r11
0x18000edbd  pop     r15
0x18000edbf  pop     r14
0x18000edc1  pop     r13
0x18000edc3  pop     r12
0x18000edc5  pop     rdi
0x18000edc6  retn
0x18000edc7  lfence
0x18000edca  mov     rax, [rcx+30h]
0x18000edce  mov     r8, [rax+r15*8]
0x18000edd2  mov     [rsp+0C8h+var_98], r8
0x18000edd7  mov     ecx, [r8+14h]
0x18000eddb  mov     dword ptr [rsp+0C8h+var_78], ecx
0x18000eddf  mov     rax, [rsp+0C8h+var_90]
0x18000ede4  mov     rdx, [rsp+0C8h+var_88]
0x18000ede9  cmp     rax, rdx
0x18000edec  jnz     loc_18000EEE9
0x18000edf2  xor     esi, esi
0x18000edf4  cmp     esi, ecx
0x18000edf6  jb      short loc_18000EE21
0x18000edf8  mov     rax, [r13+10h]
0x18000edfc  mov     rdx, [rax+30h]
0x18000ee00  mov     rcx, [rax+38h]
0x18000ee04  sub     rcx, rdx
0x18000ee07  sar     rcx, 3
0x18000ee0b  cmp     rcx, rbx
0x18000ee0e  ja      loc_18000EEF6
0x18000ee14  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000ee1b  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000ee21  mov     rax, [r8+8]
0x18000ee25  lea     r9, [rax+rsi*8]
0x18000ee29  mov     ecx, [r9]
0x18000ee2c  cmp     ecx, 2
0x18000ee2f  jnz     short loc_18000EE64
0x18000ee31  mov     eax, [r9+4]
0x18000ee35  shl     rax, 4
0x18000ee39  mov     rcx, [rsp+0C8h+var_68]
0x18000ee3e  add     rcx, rax
0x18000ee41  cmp     rdx, [rsp+0C8h+var_80]
0x18000ee46  jz      short loc_18000EE9F
0x18000ee48  movups  xmm0, xmmword ptr [rcx]
0x18000ee4b  movups  xmmword ptr [rdx], xmm0
0x18000ee4e  mov     rdx, [rsp+0C8h+var_88]
0x18000ee53  add     rdx, 10h
0x18000ee57  mov     [rsp+0C8h+var_88], rdx
0x18000ee5c  inc     esi
0x18000ee5e  mov     ecx, dword ptr [rsp+0C8h+var_78]
0x18000ee62  jmp     short loc_18000EDF4
0x18000ee64  sub     ecx, 1
0x18000ee67  jz      short loc_18000EEB8
0x18000ee69  cmp     ecx, 2
0x18000ee6c  jnz     loc_18000ED1B
0x18000ee72  mov     rax, [r13+10h]
0x18000ee76  mov     r10, [rax+18h]
0x18000ee7a  mov     r11d, [r9+4]
0x18000ee7e  mov     rcx, [rax+20h]
0x18000ee82  sub     rcx, r10
0x18000ee85  sar     rcx, 3
0x18000ee89  cmp     rcx, r11
0x18000ee8c  ja      loc_18000EF5C
0x18000ee92  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000ee99  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000ee9f  mov     r8, rcx
0x18000eea2  lea     rcx, [rsp+0C8h+var_90]
0x18000eea7  call    ??$_Emplace_reallocate@AEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@?$vector@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@V?$allocator@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@std@@@std@@AEAAPEAV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAV2@AEBV2@@Z; std::vector<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>>::_Emplace_reallocate<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &>(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> * const,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &)
0x18000eeac  mov     rdx, [rsp+0C8h+var_88]
0x18000eeb1  mov     r8, [rsp+0C8h+var_98]
0x18000eeb6  jmp     short loc_18000EE5C
0x18000eeb8  mov     ecx, [r9+4]
0x18000eebc  shl     rcx, 4
0x18000eec0  add     rcx, rdi
0x18000eec3  cmp     rdx, [rsp+0C8h+var_80]
0x18000eec8  jz      short loc_18000EF40
0x18000eeca  movups  xmm0, xmmword ptr [rcx]
0x18000eecd  movups  xmmword ptr [rdx], xmm0
0x18000eed0  mov     rdx, [rsp+0C8h+var_88]
0x18000eed5  add     rdx, 10h
0x18000eed9  mov     [rsp+0C8h+var_88], rdx
0x18000eede  inc     esi
0x18000eee0  mov     ecx, dword ptr [rsp+0C8h+var_78]
0x18000eee4  jmp     loc_18000EDF4
0x18000eee9  mov     rdx, rax
0x18000eeec  mov     [rsp+0C8h+var_88], rax
0x18000eef1  jmp     loc_18000EDF2
0x18000eef6  mov     rcx, [r8]
0x18000eef9  mov     r8, [r13+20h]
0x18000eefd  test    r8, r8
0x18000ef00  jnz     short loc_18000EF35
0x18000ef02  mov     rax, [rdx+r15*8]
0x18000ef06  mov     r8, [rax+18h]
0x18000ef0a  mov     rax, [rcx]
0x18000ef0d  lea     r9, [rsp+0C8h+var_90]
0x18000ef12  lea     rdx, [rsp+0C8h+var_40]
0x18000ef1a  mov     rax, [rax+78h]
0x18000ef1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef23  add     rbx, rbx
0x18000ef26  movups  xmm0, xmmword ptr [rax]
0x18000ef29  movups  xmmword ptr [rdi+rbx*8], xmm0
0x18000ef2d  inc     r15d
0x18000ef30  jmp     loc_18000ECED
0x18000ef35  mov     r8, [r8+r15*8]
0x18000ef39  test    r8, r8
0x18000ef3c  jnz     short loc_18000EF0A
0x18000ef3e  jmp     short loc_18000EF02
0x18000ef40  mov     r8, rcx
0x18000ef43  lea     rcx, [rsp+0C8h+var_90]
0x18000ef48  call    ??$_Emplace_reallocate@AEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@?$vector@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@V?$allocator@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@std@@@std@@AEAAPEAV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAV2@AEBV2@@Z; std::vector<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>>::_Emplace_reallocate<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &>(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> * const,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &)
0x18000ef4d  mov     rdx, [rsp+0C8h+var_88]
0x18000ef52  mov     r8, [rsp+0C8h+var_98]
0x18000ef57  jmp     loc_18000EE5C
0x18000ef5c  mov     rax, [r10+r11*8]
0x18000ef60  mov     rcx, [rax+8]
0x18000ef64  mov     ecx, [rcx-4]
0x18000ef67  jmp     loc_18000EEBC
0x18000ef6c  lea     rdx, [rsp+0C8h+var_98]; unsigned __int64 *
0x18000ef71  lea     rcx, [rsp+0C8h+var_78]; void **
0x18000ef76  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000ef7b  mov     rdx, [rsp+0C8h+var_98]
0x18000ef80  mov     rcx, [rsp+0C8h+var_78]
0x18000ef85  jmp     loc_18000ED5C
0x18000ef8a  mov     edx, 18Bh; unsigned int
0x18000ef8f  mov     ecx, r12d; int
0x18000ef92  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000ef97  nop
0x18000ef98  lea     rcx, [rsp+0C8h+var_70]; void *
0x18000ef9d  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18000efa2  nop
0x18000efa3  jmp     loc_18000ED97
0x18000efa8  mov     eax, dword ptr [rsp+0C8h+var_78]
0x18000efac  jmp     loc_18000ED9A
```
