# CWinSATResultsInfo::GetAssessmentInfo(__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003,IProvideWinSATAssessmentInfo * *)

- ea: `0x180005c50`
- end: `0x180005f43`
- name: `?GetAssessmentInfo@CWinSATResultsInfo@@UEAAJW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003@@PEAPEAUIProvideWinSATAssessmentInfo@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(CWinSATResultsInfo *__hidden this, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003, struct IProvideWinSATAssessmentInfo **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c50`
- `0x180005f50`
- `0x1800071d0`
- `0x18001055c`
- `0x180013220`
- `0x180013290`
- `0x180013fb6`
- `0x18001df40`
- `0x18001e03c`
- `0x18001e0c4`
- `0x18001e2e8`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005df1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005dfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e15`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e1e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005df1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005dfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e15`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e1e`

## pseudocode

```c
__int64 __fastcall CWinSATResultsInfo::GetAssessmentInfo(
        CWinSATResultsInfo *this,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003 a2,
        struct IProvideWinSATAssessmentInfo **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rax
  __int64 v9; // r8
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  void *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int GraphicsStrings; // ebx
  int v16; // xmm6_4
  __int64 v17; // rsi
  _QWORD *v18; // rbx
  _QWORD *v19; // rdi
  int v20; // esi
  bool v21; // zf
  void *v22; // rcx
  void *v23; // rcx
  int v25; // edi
  int v26; // edi
  int v27; // edi
  _QWORD *v28; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v29[3]; // [rsp+28h] [rbp-30h] BYREF
  _QWORD *v30; // [rsp+A8h] [rbp+50h] BYREF

  v29[1] = -2;
  v6 = operator new(0x28u);
  v7 = v6;
  if ( !v6 )
    goto LABEL_47;
  v6[2] = 1;
  v6[3] = 0;
  *v6 = 0;
  v6[1] = 0;
  v8 = operator new(2u);
  if ( !v8 )
    goto LABEL_47;
  v7[3] = v8;
  if ( *v7 )
    memcpy_0(v8, 0, 2LL * *v7);
  v9 = v7[3];
  if ( v9 )
    *(_WORD *)(v9 + 2LL * *v7) = 0;
  v28 = v7;
  v10 = operator new(0x28u);
  v11 = v10;
  if ( !v10 || (v10[2] = 1, v10[3] = 0, *v10 = 0, v10[1] = 0, (v12 = operator new(2u)) == 0) )
LABEL_47:
    std::_Xbad_alloc();
  v11[3] = v12;
  if ( *v11 )
    memcpy_0(v12, 0, 2LL * *v11);
  v14 = v11[3];
  if ( v14 )
  {
    v13 = *v11;
    *(_WORD *)(v14 + 2LL * *v11) = 0;
  }
  v30 = v11;
  if ( a2 )
  {
    v25 = a2 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          if ( v27 != 1 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v30);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v28);
            return 2147745813LL;
          }
          GraphicsStrings = CWinSATResultsInfo::GetGraphicsStrings(this, &v30, &v28);
          if ( GraphicsStrings < 0 )
            goto LABEL_45;
          v16 = *((_DWORD *)this + 116);
        }
        else
        {
          GraphicsStrings = CWinSATResultsInfo::GetD3DStrings(this, &v30, &v28);
          if ( GraphicsStrings < 0 )
            goto LABEL_45;
          v16 = *((_DWORD *)this + 117);
        }
      }
      else
      {
        GraphicsStrings = CWinSATResultsInfo::GetDiskStrings(v13, &v30, &v28);
        if ( GraphicsStrings < 0 )
          goto LABEL_45;
        v16 = *((_DWORD *)this + 115);
      }
    }
    else
    {
      GraphicsStrings = CWinSATResultsInfo::GetCPUStrings(v13, &v30, &v28);
      if ( GraphicsStrings < 0 )
        goto LABEL_45;
      v16 = *((_DWORD *)this + 113);
    }
  }
  else
  {
    GraphicsStrings = CWinSATResultsInfo::GetMemoryStrings(v13, &v30, &v28);
    if ( GraphicsStrings < 0 )
    {
LABEL_45:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v30);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v28);
      return (unsigned int)GraphicsStrings;
    }
    v16 = *((_DWORD *)this + 114);
  }
  v29[0] = 0;
  GraphicsStrings = ATL::CComObject<CWinSATAssessmentInfo>::CreateInstance(v29);
  if ( GraphicsStrings < 0 )
    goto LABEL_45;
  v17 = v29[0];
  *(_DWORD *)(v29[0] + 88LL) = v16;
  v18 = v28;
  if ( *(_QWORD *)(v17 + 72) )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v17 + 72);
  *(_QWORD *)(v17 + 72) = v18;
  ++v18[2];
  v19 = v30;
  if ( *(_QWORD *)(v17 + 80) )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v17 + 80);
  *(_QWORD *)(v17 + 80) = v19;
  ++v19[2];
  v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IProvideWinSATAssessmentInfo **))v17)(
          v17,
          &GUID_0cd1c380_52d3_4678_ac6f_e929e480be9e,
          a3);
  if ( v20 >= 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v30);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v28);
    return 0;
  }
  else
  {
    v21 = v19[2]-- == 1;
    if ( v21 )
    {
      v22 = (void *)v19[3];
      if ( v22 )
        operator delete(v22);
      operator delete(v19);
    }
    v21 = v18[2]-- == 1;
    if ( v21 && v18 )
    {
      v23 = (void *)v18[3];
      if ( v23 )
        operator delete(v23);
      operator delete(v18);
    }
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x180005c50  push    rbp
0x180005c52  push    rbx
0x180005c53  push    rsi
0x180005c54  push    rdi
0x180005c55  push    r14
0x180005c57  push    r15
0x180005c59  mov     rbp, rsp
0x180005c5c  sub     rsp, 58h
0x180005c60  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180005c68  movaps  [rsp+58h+var_18], xmm6
0x180005c6d  mov     r15, r8
0x180005c70  mov     edi, edx
0x180005c72  mov     rsi, rcx
0x180005c75  mov     ecx, 28h ; '('; Size
0x180005c7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c7f  mov     rbx, rax
0x180005c82  test    rax, rax
0x180005c85  jz      loc_180005F3D
0x180005c8b  mov     qword ptr [rax+10h], 1
0x180005c93  xor     r14d, r14d
0x180005c96  mov     [rax+18h], r14
0x180005c9a  mov     [rax], r14
0x180005c9d  mov     [rax+8], r14
0x180005ca1  mov     ecx, 2; Size
0x180005ca6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cab  test    rax, rax
0x180005cae  jz      loc_180005F3D
0x180005cb4  mov     [rbx+18h], rax
0x180005cb8  mov     r8, [rbx]
0x180005cbb  test    r8, r8
0x180005cbe  jz      short loc_180005CCD
0x180005cc0  add     r8, r8; Size
0x180005cc3  xor     edx, edx; Src
0x180005cc5  mov     rcx, rax; void *
0x180005cc8  call    memcpy_0
0x180005ccd  mov     r8, [rbx+18h]
0x180005cd1  test    r8, r8
0x180005cd4  jz      short loc_180005CDE
0x180005cd6  mov     rdx, [rbx]
0x180005cd9  mov     [r8+rdx*2], r14w
0x180005cde  mov     [rbp+var_38], rbx
0x180005ce2  mov     ecx, 28h ; '('; Size
0x180005ce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cec  mov     rbx, rax
0x180005cef  test    rax, rax
0x180005cf2  jz      loc_180005F3D
0x180005cf8  mov     qword ptr [rax+10h], 1
0x180005d00  mov     [rax+18h], r14
0x180005d04  mov     [rax], r14
0x180005d07  mov     [rax+8], r14
0x180005d0b  mov     ecx, 2; Size
0x180005d10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d15  test    rax, rax
0x180005d18  jz      loc_180005F3D
0x180005d1e  mov     [rbx+18h], rax
0x180005d22  mov     r8, [rbx]
0x180005d25  test    r8, r8
0x180005d28  jz      short loc_180005D37
0x180005d2a  add     r8, r8; Size
0x180005d2d  xor     edx, edx; Src
0x180005d2f  mov     rcx, rax; void *
0x180005d32  call    memcpy_0
0x180005d37  mov     rdx, [rbx+18h]
0x180005d3b  test    rdx, rdx
0x180005d3e  jz      short loc_180005D48
0x180005d40  mov     rcx, [rbx]
0x180005d43  mov     [rdx+rcx*2], r14w
0x180005d48  mov     [rbp+arg_18], rbx
0x180005d4c  test    edi, edi
0x180005d4e  jnz     loc_180005E54
0x180005d54  lea     r8, [rbp+var_38]
0x180005d58  lea     rdx, [rbp+arg_18]
0x180005d5c  call    ?GetMemoryStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetMemoryStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180005d61  mov     ebx, eax
0x180005d63  test    eax, eax
0x180005d65  js      loc_180005F0B
0x180005d6b  movss   xmm6, dword ptr [rsi+1C8h]
0x180005d73  mov     [rbp+var_30], r14
0x180005d77  lea     rcx, [rbp+var_30]
0x180005d7b  call    ?CreateInstance@?$CComObject@VCWinSATAssessmentInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWinSATAssessmentInfo>::CreateInstance(ATL::CComObject<CWinSATAssessmentInfo> * *)
0x180005d80  mov     ebx, eax
0x180005d82  test    eax, eax
0x180005d84  js      loc_180005F0B
0x180005d8a  mov     rsi, [rbp+var_30]
0x180005d8e  movss   dword ptr [rsi+58h], xmm6
0x180005d93  mov     rbx, [rbp+var_38]
0x180005d97  cmp     [rsi+48h], r14
0x180005d9b  jnz     loc_180005E38
0x180005da1  mov     [rsi+48h], rbx
0x180005da5  inc     qword ptr [rbx+10h]
0x180005da9  mov     rdi, [rbp+arg_18]
0x180005dad  cmp     [rsi+50h], r14
0x180005db1  jnz     loc_180005E46
0x180005db7  mov     [rsi+50h], rdi
0x180005dbb  inc     qword ptr [rdi+10h]
0x180005dbf  mov     rax, [rsi]
0x180005dc2  mov     r8, r15
0x180005dc5  lea     rdx, _GUID_0cd1c380_52d3_4678_ac6f_e929e480be9e
0x180005dcc  mov     rcx, rsi
0x180005dcf  mov     rax, [rax]
0x180005dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd7  mov     esi, eax
0x180005dd9  test    eax, eax
0x180005ddb  jns     loc_180005F24
0x180005de1  sub     qword ptr [rdi+10h], 1
0x180005de6  jnz     short loc_180005E00
0x180005de8  mov     rcx, [rdi+18h]
0x180005dec  test    rcx, rcx
0x180005def  jz      short loc_180005DF7
0x180005df1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005df7  mov     rcx, rdi
0x180005dfa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005e00  sub     qword ptr [rbx+10h], 1
0x180005e05  jnz     short loc_180005E24
0x180005e07  test    rbx, rbx
0x180005e0a  jz      short loc_180005E24
0x180005e0c  mov     rcx, [rbx+18h]
0x180005e10  test    rcx, rcx
0x180005e13  jz      short loc_180005E1B
0x180005e15  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005e1b  mov     rcx, rbx
0x180005e1e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005e24  mov     eax, esi
0x180005e26  movaps  xmm6, [rsp+58h+var_18]
0x180005e2b  add     rsp, 58h
0x180005e2f  pop     r15
0x180005e31  pop     r14
0x180005e33  pop     rdi
0x180005e34  pop     rsi
0x180005e35  pop     rbx
0x180005e36  pop     rbp
0x180005e37  retn
0x180005e38  lea     rcx, [rsi+48h]
0x180005e3c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005e41  jmp     loc_180005DA1
0x180005e46  lea     rcx, [rsi+50h]
0x180005e4a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005e4f  jmp     loc_180005DB7
0x180005e54  sub     edi, 1
0x180005e57  jz      loc_180005EEB
0x180005e5d  sub     edi, 1
0x180005e60  jz      short loc_180005ECB
0x180005e62  sub     edi, 1
0x180005e65  jz      short loc_180005EA8
0x180005e67  cmp     edi, 1
0x180005e6a  jz      short loc_180005E85
0x180005e6c  lea     rcx, [rbp+arg_18]
0x180005e70  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005e75  lea     rcx, [rbp+var_38]
0x180005e79  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005e7e  mov     eax, 80040015h
0x180005e83  jmp     short loc_180005E26
0x180005e85  lea     r8, [rbp+var_38]
0x180005e89  lea     rdx, [rbp+arg_18]
0x180005e8d  mov     rcx, rsi
0x180005e90  call    ?GetGraphicsStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetGraphicsStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180005e95  mov     ebx, eax
0x180005e97  test    eax, eax
0x180005e99  js      short loc_180005F0B
0x180005e9b  movss   xmm6, dword ptr [rsi+1D0h]
0x180005ea3  jmp     loc_180005D73
0x180005ea8  lea     r8, [rbp+var_38]
0x180005eac  lea     rdx, [rbp+arg_18]
0x180005eb0  mov     rcx, rsi
0x180005eb3  call    ?GetD3DStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetD3DStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180005eb8  mov     ebx, eax
0x180005eba  test    eax, eax
0x180005ebc  js      short loc_180005F0B
0x180005ebe  movss   xmm6, dword ptr [rsi+1D4h]
0x180005ec6  jmp     loc_180005D73
0x180005ecb  lea     r8, [rbp+var_38]
0x180005ecf  lea     rdx, [rbp+arg_18]
0x180005ed3  call    ?GetDiskStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetDiskStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180005ed8  mov     ebx, eax
0x180005eda  test    eax, eax
0x180005edc  js      short loc_180005F0B
0x180005ede  movss   xmm6, dword ptr [rsi+1CCh]
0x180005ee6  jmp     loc_180005D73
0x180005eeb  lea     r8, [rbp+var_38]
0x180005eef  lea     rdx, [rbp+arg_18]
0x180005ef3  call    ?GetCPUStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetCPUStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180005ef8  mov     ebx, eax
0x180005efa  test    eax, eax
0x180005efc  js      short loc_180005F0B
0x180005efe  movss   xmm6, dword ptr [rsi+1C4h]
0x180005f06  jmp     loc_180005D73
0x180005f0b  lea     rcx, [rbp+arg_18]
0x180005f0f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005f14  lea     rcx, [rbp+var_38]
0x180005f18  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005f1d  mov     eax, ebx
0x180005f1f  jmp     loc_180005E26
0x180005f24  lea     rcx, [rbp+arg_18]
0x180005f28  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005f2d  lea     rcx, [rbp+var_38]
0x180005f31  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005f36  xor     eax, eax
0x180005f38  jmp     loc_180005E26
0x180005f3d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
