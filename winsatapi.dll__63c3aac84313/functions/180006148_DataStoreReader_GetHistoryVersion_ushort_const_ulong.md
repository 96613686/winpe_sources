# DataStoreReader::GetHistoryVersion(ushort const *,ulong &)

- ea: `0x180006148`
- end: `0x180006571`
- name: `?GetHistoryVersion@DataStoreReader@@CAJPEBGAEAK@Z`
- size: `1065`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004e00`

## callees

- `0x180002350`
- `0x180006070`
- `0x180006148`
- `0x1800071d0`
- `0x18001040c`
- `0x180013220`
- `0x180013290`
- `0x180013fa3`
- `0x180013fb6`
- `0x18002c9a0`
- `0x180031010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006238`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006371`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006238`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180006371`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000647e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006487`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006514`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000651d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006534`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000653d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000647e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006487`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006514`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000651d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006534`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000653d`

## string_xrefs

- `0x1800062e4`: `HistoryVersionRead`
- `0x1800062f2`: `HistoryVersionRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DataStoreReader::GetHistoryVersion(const char *a1, unsigned int *a2)
{
  __int64 *v3; // rax
  __int64 *v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rcx
  const wchar_t *i; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rax
  __int64 *v13; // rdi
  const wchar_t *j; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  void *v17; // rax
  __int64 v18; // r8
  const wchar_t *v19; // rdx
  __int64 v20; // rdx
  _QWORD *v21; // rsi
  bool v22; // zf
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  __int64 pExceptionObject; // [rsp+28h] [rbp-69h] BYREF
  _QWORD *v28[3]; // [rsp+30h] [rbp-61h] BYREF
  _QWORD v29[2]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v30; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-31h] BYREF
  _QWORD *v32; // [rsp+70h] [rbp-21h] BYREF
  _QWORD v33[2]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v34; // [rsp+88h] [rbp-9h]
  char v35; // [rsp+8Ah] [rbp-7h]
  __int64 v36; // [rsp+90h] [rbp-1h]
  __int64 v37; // [rsp+98h] [rbp+7h]
  _QWORD v38[9]; // [rsp+A0h] [rbp+Fh] BYREF
  const char *v39; // [rsp+F8h] [rbp+67h] BYREF
  __int64 *v40; // [rsp+108h] [rbp+77h]
  __int64 *v41; // [rsp+110h] [rbp+7Fh]

  v39 = a1;
  v37 = -2;
  v3 = (__int64 *)operator new(0x28u);
  v4 = v3;
  if ( !v3 )
    std::_Xbad_alloc();
  v40 = v3;
  *v3 = 0;
  v3[1] = 0;
  v3[2] = 1;
  v3[3] = 0;
  v5 = 0x10000;
  v6 = 0x10000;
  for ( i = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT"; ; ++i )
  {
    if ( !v6 )
      goto LABEL_60;
    if ( !*i )
      break;
    --v6;
  }
  if ( !i )
LABEL_60:
    throw (mlib::CStringTooBig *)&v39;
  v8 = i - L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT";
  *v4 = v8;
  v4[1] = v8;
  v9 = v8 + 1;
  v10 = 0;
  if ( v9 )
  {
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
      std::_Xbad_alloc();
  }
  v4[3] = (__int64)v10;
  if ( !v10 )
  {
    v39 = "bad allocation";
    exception::exception((exception *)&pExceptionObject, &v39, 1);
    pExceptionObject = (__int64)&std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  if ( *v4 )
    memcpy_0(v10, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT", 2 * *v4);
  v11 = v4[3];
  if ( v11 )
    *(_WORD *)(v11 + 2 * *v4) = 0;
  v40 = v4;
  pExceptionObject = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v28);
  if ( v28[0] )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v28);
  v28[0] = v4;
  ++v4[2];
  mlib::RegistryBaseKey::cleanup(v28);
  pExceptionObject = -2147483646;
  v12 = (__int64 *)operator new(0x28u);
  v13 = v12;
  if ( !v12 )
    std::_Xbad_alloc();
  v41 = v12;
  *v12 = 0;
  v12[1] = 0;
  v12[2] = 1;
  v12[3] = 0;
  if ( !aHistoryversion[0] )
  {
    v17 = operator new(2u);
    if ( v17 )
    {
      v13[3] = (__int64)v17;
      v18 = *v13;
      if ( !*v13 )
        goto LABEL_41;
      v19 = 0;
      goto LABEL_40;
    }
LABEL_37:
    std::_Xbad_alloc();
  }
  for ( j = L"HistoryVersionRead"; ; ++j )
  {
    if ( !v5 )
      goto LABEL_35;
    if ( !*j )
      break;
    --v5;
  }
  if ( !j )
LABEL_35:
    throw (mlib::CStringTooBig *)&v39;
  v15 = j - L"HistoryVersionRead";
  *v13 = v15;
  v13[1] = v15;
  v16 = v15 + 1;
  v17 = 0;
  if ( v16 )
  {
    if ( v16 > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_37;
    v17 = operator new(2 * v16);
    if ( !v17 )
      goto LABEL_37;
  }
  v13[3] = (__int64)v17;
  if ( !v17 )
  {
    v39 = "bad allocation";
    exception::exception((exception *)v38, &v39, 1);
    v38[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)v38;
  }
  v18 = *v13;
  if ( *v13 )
  {
    v19 = L"HistoryVersionRead";
LABEL_40:
    memcpy_0(v17, v19, 2 * v18);
  }
LABEL_41:
  v20 = v13[3];
  if ( v20 )
    *(_WORD *)(v20 + 2 * *v13) = 0;
  v41 = v13;
  v29[0] = &mlib::RegistryKey::`vftable';
  v29[1] = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v30);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31);
  v31[1] = -2147483646;
  v21 = v28[0];
  v32 = v28[0];
  ++v28[0][2];
  v29[0] = &mlib::RegistryValue::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v33);
  v39 = (const char *)v13;
  ++v13[2];
  mlib::RegistryValue::parse_names(v29, &v39);
  v34 = 256;
  v35 = 0;
  v29[0] = &mlib::DWORDReg::`vftable';
  v36 = 0;
  v22 = v13[2]-- == 1;
  if ( v22 )
  {
    v23 = (void *)v13[3];
    if ( v23 )
      operator delete(v23);
    operator delete(v13);
  }
  v36 = (_BYTE)v34 != 0 ? (unsigned int)v36 : 0;
  (*(void (__fastcall **)(_QWORD *))(v29[0] + 8LL))(v29);
  *a2 = v36;
  v29[0] = &mlib::DWORDReg::`vftable';
  if ( !HIBYTE(v34) || v35 )
    mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v29);
  v29[0] = &mlib::RegistryValue::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v33);
  v29[0] = &mlib::RegistryKey::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v32);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v31);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v30);
  v22 = v21[2]-- == 1;
  if ( v22 && v21 )
  {
    v24 = (void *)v21[3];
    if ( v24 )
      operator delete(v24);
    operator delete(v21);
  }
  v22 = v4[2]-- == 1;
  if ( v22 )
  {
    v25 = (void *)v4[3];
    if ( v25 )
      operator delete(v25);
    operator delete(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180006148  mov     rax, rsp
0x18000614b  mov     [rax+8], rcx
0x18000614f  push    rbp
0x180006150  push    rsi
0x180006151  push    rdi
0x180006152  push    r12
0x180006154  push    r13
0x180006156  push    r14
0x180006158  push    r15
0x18000615a  lea     rbp, [rax-5Fh]
0x18000615e  sub     rsp, 0B0h
0x180006165  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18000616d  mov     [rax+10h], rbx
0x180006171  mov     r14, rdx
0x180006174  mov     r13d, 28h ; '('
0x18000617a  mov     ecx, r13d; Size
0x18000617d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006182  mov     rbx, rax
0x180006185  xor     r15d, r15d
0x180006188  test    rax, rax
0x18000618b  jnz     short loc_180006193
0x18000618d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006193  mov     [rbp+57h+arg_10], rbx
0x180006197  mov     [rax], r15
0x18000619a  mov     [rax+8], r15
0x18000619e  mov     r12d, 1
0x1800061a4  mov     [rax+10h], r12
0x1800061a8  mov     [rax+18h], r15
0x1800061ac  mov     esi, 10000h
0x1800061b1  mov     ecx, esi
0x1800061b3  lea     rdi, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800061ba  mov     rax, rdi
0x1800061bd  test    rcx, rcx
0x1800061c0  jz      loc_180006560
0x1800061c6  cmp     [rax], r15w
0x1800061ca  jz      short loc_1800061D5
0x1800061cc  add     rax, 2
0x1800061d0  sub     rcx, r12
0x1800061d3  jmp     short loc_1800061BD
0x1800061d5  test    rax, rax
0x1800061d8  jz      loc_180006560
0x1800061de  sub     rax, rdi
0x1800061e1  sar     rax, 1
0x1800061e4  mov     [rbx], rax
0x1800061e7  mov     [rbx+8], rax
0x1800061eb  lea     rcx, [rax+1]
0x1800061ef  mov     rax, r15
0x1800061f2  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800061fc  test    rcx, rcx
0x1800061ff  jz      short loc_180006219
0x180006201  cmp     rcx, rdx
0x180006204  ja      short loc_180006213
0x180006206  add     rcx, rcx; Size
0x180006209  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000620e  test    rax, rax
0x180006211  jnz     short loc_180006219
0x180006213  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006219  mov     [rbx+18h], rax
0x18000621d  test    rax, rax
0x180006220  jnz     short loc_18000625A
0x180006222  lea     rax, aBadAllocation; "bad allocation"
0x180006229  mov     [rbp+57h+arg_0], rax
0x18000622d  mov     r8d, r12d
0x180006230  lea     rdx, [rbp+57h+arg_0]
0x180006234  lea     rcx, [rbp+57h+pExceptionObject]
0x180006238  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000623e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006245  mov     [rbp+57h+pExceptionObject], rax
0x180006249  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006250  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180006254  call    _CxxThrowException_0
0x18000625a  mov     r8, [rbx]
0x18000625d  test    r8, r8
0x180006260  jz      short loc_180006270
0x180006262  add     r8, r8; Size
0x180006265  mov     rdx, rdi; Src
0x180006268  mov     rcx, rax; void *
0x18000626b  call    memcpy_0
0x180006270  mov     rdx, [rbx+18h]
0x180006274  test    rdx, rdx
0x180006277  jz      short loc_180006281
0x180006279  mov     rcx, [rbx]
0x18000627c  mov     [rdx+rcx*2], r15w
0x180006281  mov     [rbp+57h+arg_10], rbx
0x180006285  mov     [rbp+57h+pExceptionObject], r15
0x180006289  lea     rcx, [rbp+57h+var_B8]
0x18000628d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180006292  nop
0x180006293  cmp     [rbp+57h+var_B8], r15
0x180006297  jz      short loc_1800062A2
0x180006299  lea     rcx, [rbp+57h+var_B8]
0x18000629d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800062a2  mov     [rbp+57h+var_B8], rbx
0x1800062a6  add     [rbx+10h], r12
0x1800062aa  lea     rcx, [rbp+57h+var_B8]
0x1800062ae  call    ?cleanup@RegistryBaseKey@mlib@@SAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryBaseKey::cleanup(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x1800062b3  mov     [rbp+57h+pExceptionObject], 0FFFFFFFF80000002h
0x1800062bb  mov     rcx, r13; Size
0x1800062be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062c3  mov     rdi, rax
0x1800062c6  test    rax, rax
0x1800062c9  jnz     short loc_1800062D1
0x1800062cb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800062d1  mov     [rbp+57h+arg_18], rdi
0x1800062d5  mov     [rax], r15
0x1800062d8  mov     [rax+8], r15
0x1800062dc  mov     [rax+10h], r12
0x1800062e0  mov     [rax+18h], r15
0x1800062e4  cmp     word ptr cs:aHistoryversion, r15w; "HistoryVersionRead"
0x1800062ec  jz      loc_1800063B1
0x1800062f2  lea     r13, aHistoryversion; "HistoryVersionRead"
0x1800062f9  mov     rax, r13
0x1800062fc  test    rsi, rsi
0x1800062ff  jz      loc_1800063A0
0x180006305  cmp     [rax], r15w
0x180006309  jz      short loc_180006314
0x18000630b  add     rax, 2
0x18000630f  sub     rsi, r12
0x180006312  jmp     short loc_1800062FC
0x180006314  test    rax, rax
0x180006317  jz      loc_1800063A0
0x18000631d  sub     rax, r13
0x180006320  sar     rax, 1
0x180006323  mov     [rdi], rax
0x180006326  mov     [rdi+8], rax
0x18000632a  lea     rcx, [rax+1]
0x18000632e  mov     rax, r15
0x180006331  test    rcx, rcx
0x180006334  jz      short loc_180006352
0x180006336  mov     rax, 7FFFFFFFFFFFFFFFh
0x180006340  cmp     rcx, rax
0x180006343  ja      short loc_1800063C0
0x180006345  add     rcx, rcx; Size
0x180006348  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000634d  test    rax, rax
0x180006350  jz      short loc_1800063C0
0x180006352  mov     [rdi+18h], rax
0x180006356  test    rax, rax
0x180006359  jnz     short loc_180006393
0x18000635b  lea     rax, aBadAllocation; "bad allocation"
0x180006362  mov     [rbp+57h+arg_0], rax
0x180006366  mov     r8d, r12d
0x180006369  lea     rdx, [rbp+57h+arg_0]
0x18000636d  lea     rcx, [rbp+57h+var_48]
0x180006371  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180006377  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000637e  mov     [rbp+57h+var_48], rax
0x180006382  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006389  lea     rcx, [rbp+57h+var_48]; pExceptionObject
0x18000638d  call    _CxxThrowException_0
0x180006393  mov     r8, [rdi]
0x180006396  test    r8, r8
0x180006399  jz      short loc_1800063DF
0x18000639b  mov     rdx, r13
0x18000639e  jmp     short loc_1800063D4
0x1800063a0  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x1800063a7  lea     rcx, [rbp+57h+arg_0]; pExceptionObject
0x1800063ab  call    _CxxThrowException_0
0x1800063b1  mov     ecx, 2; Size
0x1800063b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063bb  test    rax, rax
0x1800063be  jnz     short loc_1800063C6
0x1800063c0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800063c6  mov     [rdi+18h], rax
0x1800063ca  mov     r8, [rdi]
0x1800063cd  test    r8, r8
0x1800063d0  jz      short loc_1800063DF
0x1800063d2  xor     edx, edx; Src
0x1800063d4  add     r8, r8; Size
0x1800063d7  mov     rcx, rax; void *
0x1800063da  call    memcpy_0
0x1800063df  mov     rdx, [rdi+18h]
0x1800063e3  test    rdx, rdx
0x1800063e6  jz      short loc_1800063F0
0x1800063e8  mov     rcx, [rdi]
0x1800063eb  mov     [rdx+rcx*2], r15w
0x1800063f0  mov     [rbp+57h+arg_18], rdi
0x1800063f4  lea     r13, ??_7RegistryKey@mlib@@6B@; const mlib::RegistryKey::`vftable'
0x1800063fb  mov     [rbp+57h+var_A0], r13
0x1800063ff  mov     [rbp+57h+var_98], r15
0x180006403  lea     rcx, [rbp+57h+var_90]
0x180006407  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18000640c  nop
0x18000640d  lea     rcx, [rbp+57h+var_88]
0x180006411  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180006416  mov     [rbp+57h+var_80], 0FFFFFFFF80000002h
0x18000641e  mov     rsi, [rbp+57h+var_B8]
0x180006422  mov     [rbp+57h+var_78], rsi
0x180006426  add     [rsi+10h], r12
0x18000642a  lea     rax, ??_7RegistryValue@mlib@@6B@; const mlib::RegistryValue::`vftable'
0x180006431  mov     [rbp+57h+var_A0], rax
0x180006435  lea     rcx, [rbp+57h+var_70]
0x180006439  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18000643e  nop
0x18000643f  mov     [rbp+57h+arg_0], rdi
0x180006443  add     [rdi+10h], r12
0x180006447  lea     rdx, [rbp+57h+arg_0]
0x18000644b  lea     rcx, [rbp+57h+var_A0]
0x18000644f  call    ?parse_names@RegistryValue@mlib@@IEAAHV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryValue::parse_names(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x180006454  nop
0x180006455  mov     [rbp+57h+var_60], 100h
0x18000645b  mov     [rbp+57h+var_5E], r15b
0x18000645f  lea     r12, ??_7DWORDReg@mlib@@6B@; const mlib::DWORDReg::`vftable'
0x180006466  mov     [rbp+57h+var_A0], r12
0x18000646a  mov     [rbp+57h+var_58], r15
0x18000646e  sub     qword ptr [rdi+10h], 1
0x180006473  jnz     short loc_18000648D
0x180006475  mov     rcx, [rdi+18h]
0x180006479  test    rcx, rcx
0x18000647c  jz      short loc_180006484
0x18000647e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006484  mov     rcx, rdi
0x180006487  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000648d  mov     dword ptr [rbp+57h+var_58+4], r15d
0x180006491  mov     al, byte ptr [rbp+57h+var_60]
0x180006494  neg     al
0x180006496  sbb     ecx, ecx
0x180006498  and     dword ptr [rbp+57h+var_58], ecx
0x18000649b  mov     rax, [rbp+57h+var_A0]
0x18000649f  lea     rcx, [rbp+57h+var_A0]
0x1800064a3  mov     rax, [rax+8]
0x1800064a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ac  mov     eax, dword ptr [rbp+57h+var_58]
0x1800064af  mov     [r14], eax
0x1800064b2  mov     [rbp+57h+var_A0], r12
0x1800064b6  cmp     byte ptr [rbp+57h+var_60+1], r15b
0x1800064ba  jz      short loc_1800064C2
0x1800064bc  cmp     [rbp+57h+var_5E], r15b
0x1800064c0  jz      short loc_1800064CB
0x1800064c2  lea     rcx, [rbp+57h+var_A0]; this
0x1800064c6  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x1800064cb  lea     rax, ??_7RegistryValue@mlib@@6B@; const mlib::RegistryValue::`vftable'
0x1800064d2  mov     [rbp+57h+var_A0], rax
0x1800064d6  lea     rcx, [rbp+57h+var_70]
0x1800064da  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800064df  mov     [rbp+57h+var_A0], r13
0x1800064e3  lea     rcx, [rbp+57h+var_78]
0x1800064e7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800064ec  lea     rcx, [rbp+57h+var_88]
0x1800064f0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800064f5  lea     rcx, [rbp+57h+var_90]
0x1800064f9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800064fe  nop
0x1800064ff  sub     qword ptr [rsi+10h], 1
0x180006504  jnz     short loc_180006524
0x180006506  test    rsi, rsi
0x180006509  jz      short loc_180006524
0x18000650b  mov     rcx, [rsi+18h]
0x18000650f  test    rcx, rcx
0x180006512  jz      short loc_18000651A
0x180006514  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000651a  mov     rcx, rsi
0x18000651d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006523  nop
0x180006524  sub     qword ptr [rbx+10h], 1
0x180006529  jnz     short loc_180006543
0x18000652b  mov     rcx, [rbx+18h]
0x18000652f  test    rcx, rcx
0x180006532  jz      short loc_18000653A
0x180006534  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000653a  mov     rcx, rbx
0x18000653d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006543  xor     eax, eax
0x180006545  mov     rbx, [rsp+0E0h+arg_8]
0x18000654d  add     rsp, 0B0h
0x180006554  pop     r15
0x180006556  pop     r14
0x180006558  pop     r13
0x18000655a  pop     r12
0x18000655c  pop     rdi
0x18000655d  pop     rsi
0x18000655e  pop     rbp
0x18000655f  retn
0x180006560  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180006567  lea     rcx, [rbp+57h+arg_0]; pExceptionObject
0x18000656b  call    _CxxThrowException_0
```
