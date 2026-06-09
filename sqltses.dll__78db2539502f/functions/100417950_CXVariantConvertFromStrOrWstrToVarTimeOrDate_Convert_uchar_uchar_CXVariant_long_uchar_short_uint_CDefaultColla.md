# CXVariantConvertFromStrOrWstrToVarTimeOrDate::Convert(uchar,uchar,CXVariant *,long,uchar,short,uint,CDefaultCollation const *,ETimeScale)

- ea: `0x100417950`
- end: `0x100417bdc`
- name: `?Convert@CXVariantConvertFromStrOrWstrToVarTimeOrDate@@SAJEEPEAVCXVariant@@JEFIPEBVCDefaultCollation@@W4ETimeScale@@@Z`
- size: `652`
- prototype: `static int __high(unsigned __int8, unsigned __int8, struct CXVariant *, int, unsigned __int8, __int16, unsigned int, const struct CDefaultCollation *, enum ETimeScale)`
- caller_count: `57`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1004177e0`
- `0x10041dc60`
- `0x1004568e0`
- `0x10070ef20`
- `0x10070f2f0`
- `0x100711610`
- `0x100711860`
- `0x100711ab0`
- `0x100711d00`
- `0x10076dbd0`
- `0x10076dec0`
- `0x10076e220`
- `0x10076e540`
- `0x10076e850`
- `0x10076ebc0`
- `0x10076f0b0`
- `0x10076f3c0`
- `0x10076f740`
- `0x10076fa80`
- `0x10076fda0`
- `0x100770140`
- `0x100770660`
- `0x1007709c0`
- `0x100770da0`
- `0x100771140`
- `0x1007714b0`
- `0x100771890`
- `0x100771e00`
- `0x100772110`
- `0x100772490`
- `0x1007727d0`
- `0x100772af0`
- `0x100772e90`
- `0x10077c420`
- `0x10077c710`
- `0x10077ca70`
- `0x10077cd90`
- `0x10077d0a0`
- `0x10077d410`
- `0x10077d900`
- `0x10077dc10`
- `0x10077df90`
- `0x10077e2d0`
- `0x10077e5f0`
- `0x10077e990`
- `0x10077eeb0`
- `0x10077f210`
- `0x10077f5f0`
- `0x10077f990`
- `0x10077fd00`

## callees

- `0x100401170`
- `0x100401350`
- `0x100401480`
- `0x1004024b0`
- `0x10040ce20`
- `0x10040dfd0`
- `0x100415a60`
- `0x100417500`
- `0x100417950`
- `0x100417bf0`
- `0x10041df10`
- `0x10041e710`
- `0x10042ff20`
- `0x100440c90`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10047d228`
- `sqldk!??_V@YAXPEAX@Z` at `0x10047d228`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047d134`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047d134`
- `sqldk!SystemThread_TlsIndex` at `0x10047d0e5`
- `sqldk!SystemThread_TlsOffset` at `0x10047d0ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047d109`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047d109`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047d21e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047d21e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXVariantConvertFromStrOrWstrToVarTimeOrDate::Convert(
        unsigned __int8 a1,
        unsigned __int8 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        __int16 a6,
        unsigned int a7,
        __int64 a8,
        int a9)
{
  int v11; // r15d
  const char *v12; // rdx
  int v13; // r8d
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  wchar_t *v19; // rsi
  BOOL v20; // r14d
  __int64 result; // rax
  unsigned int v22; // ebx
  __int64 v23; // r9
  int v24; // esi
  __int64 v25; // rsi
  __int64 v26; // rdx
  wchar_t *v27; // rsi
  char *v28; // rcx
  const wchar_t *TypeName; // rax
  const struct CTypeDflt near *const *v30; // rcx
  __int64 v31; // r10
  __int64 v32; // r9
  unsigned __int64 v33; // r9
  const unsigned __int64 *v34; // rcx
  bool v35[8]; // [rsp+20h] [rbp-20h]
  int v36; // [rsp+28h] [rbp-18h]
  __int64 v37; // [rsp+30h] [rbp-10h]
  wchar_t v38; // [rsp+40h] [rbp+0h] BYREF
  __int64 v39; // [rsp+48h] [rbp+8h] BYREF
  int v40; // [rsp+50h] [rbp+10h]
  __int64 v41; // [rsp+5Ch] [rbp+1Ch]
  __int64 v42; // [rsp+64h] [rbp+24h]
  bool v43; // [rsp+6Ch] [rbp+2Ch]
  int v44; // [rsp+6Dh] [rbp+2Dh]
  void **v45; // [rsp+78h] [rbp+38h] BYREF
  const unsigned __int64 *v46; // [rsp+80h] [rbp+40h]
  __int64 v47; // [rsp+88h] [rbp+48h]
  int v48; // [rsp+90h] [rbp+50h]
  __int16 v49; // [rsp+94h] [rbp+54h]
  char v50[8]; // [rsp+98h] [rbp+58h] BYREF
  int v51; // [rsp+A0h] [rbp+60h]
  wchar_t *v52; // [rsp+A8h] [rbp+68h] BYREF
  void **v53; // [rsp+B0h] [rbp+70h] BYREF
  int v54; // [rsp+B8h] [rbp+78h]
  unsigned int v55; // [rsp+BCh] [rbp+7Ch]
  const unsigned __int64 near *v56; // [rsp+C0h] [rbp+80h]
  int v57; // [rsp+C8h] [rbp+88h]
  __int64 v58; // [rsp+D0h] [rbp+90h]
  __int64 *v59; // [rsp+D8h] [rbp+98h]
  char v60; // [rsp+E0h] [rbp+A0h] BYREF
  char v61; // [rsp+E1h] [rbp+A1h]
  unsigned __int16 v62; // [rsp+E2h] [rbp+A2h]
  unsigned int v63; // [rsp+E4h] [rbp+A4h]
  __int16 v64; // [rsp+F0h] [rbp+B0h]
  char v65; // [rsp+F2h] [rbp+B2h]
  char v66; // [rsp+F3h] [rbp+B3h]
  __int64 v67; // [rsp+100h] [rbp+C0h]

  v67 = -2;
  v11 = a2;
  if ( *(_BYTE *)a3 )
    return 0;
  v12 = *(const char **)(a3 + 8);
  v13 = *(_DWORD *)(a3 + 16);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + a1)) )
  {
    v19 = (wchar_t *)v12;
  }
  else
  {
    v14 = 2LL * (unsigned int)v13;
    v15 = v14 + 15;
    if ( v14 + 15 < v14 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
    v17 = alloca(v16);
    v18 = alloca(v16);
    v19 = &v38;
    v13 = 2 * FastDBCSToUnicode(a7, v12, v13, &v38, v13);
  }
  v20 = a4 - 130 <= 1;
  v43 = a4 - 130 <= 1;
  v39 = 1900;
  v40 = 1;
  v41 = 0;
  v42 = 0;
  v44 = 1;
  v53 = (void **)v19;
  v54 = (unsigned __int64)v13 >> 1;
  v55 = a4;
  LODWORD(v56) = 0;
  HIDWORD(v56) = a5;
  LOWORD(v57) = a6;
  v58 = a8;
  v59 = &v39;
  if ( a4 > 0xFF || !*((_BYTE *)&x_rgfValidDateStyles + (unsigned __int8)a4) )
    return 0xFFFFFFFFLL;
  result = yyd8parse((struct CDateParser *)&v53);
  if ( (_DWORD)result )
    return result;
  if ( !dateparts::FValidDate((dateparts *)&v39)
    || (unsigned int)v41 > 0x17
    || HIDWORD(v41) > 0x3B
    || (unsigned int)v42 > 0x3B
    || HIDWORD(v42) >= *((_DWORD *)&x_rgulPowersOfTen + HIBYTE(v44))
    || BYTE1(v44) > 0xEu
    || BYTE2(v44) > 0x3Bu
    || BYTE1(v44) == 14 && BYTE2(v44) )
  {
    return 2;
  }
  v22 = 0;
  (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, wchar_t **))x_pContextProvider)(
    x_pContextProvider,
    &v52);
  if ( (*(unsigned __int8 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, wchar_t *))(*(_QWORD *)x_pContextProvider + 16LL))(
         x_pContextProvider,
         v52)
    && *(_WORD *)((char *)&v44 + 1) )
  {
    v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v26 = *(_QWORD *)(v25 + 256);
    if ( !v26 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v26 = *(_QWORD *)(v25 + 256);
    }
    v27 = (wchar_t *)operator new[](
                       0x704u,
                       *(struct IMemObj **)(v26 + 1000),
                       "sql\\ntdbms\\msql\\typesystem\\tsfnconv.cpp",
                       1575,
                       6u);
    v52 = v27;
    CTypeInfo::Init((CTypeInfo *)&v60, 0x2Bu);
    v61 |= 1u;
    switch ( v60 )
    {
      case ')':
        v30 = &x_rgDfltTime;
        break;
      case '*':
        v30 = &x_rgDfltDatetime2;
        break;
      case '+':
        v30 = &x_rgDfltDatetimeOffset;
        break;
      default:
        v28 = 0;
        goto LABEL_40;
    }
    v28 = (char *)v30 + 4 * HIBYTE(v44);
LABEL_40:
    v64 = *(_WORD *)v28;
    v65 = v28[2];
    v66 = HIBYTE(v44);
    if ( v60 == -13 || v60 == -16 || v63 <= 0xFF )
      TypeName = CTypeInfo::GetTypeName((CTypeInfo *)&v60, v27, 0x382u, 1, 0, 0, 1, 0);
    else
      TypeName = (const wchar_t *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IUdtProvider *, _QWORD, _QWORD, wchar_t *, int, char, _BYTE, _BYTE))(*(_QWORD *)x_pIUdtProvider + 16LL))(
                                    x_pIUdtProvider,
                                    v62,
                                    v63,
                                    v27,
                                    898,
                                    1,
                                    0,
                                    0);
    LODWORD(v37) = 35473;
    *(_DWORD *)v35 = 13040;
    ex_raise(107, 94, 16, 0, *(_QWORD *)v35, TypeName, v37);
    operator delete[](v27);
  }
  if ( v11 == 40 )
  {
    v51 = 0;
    v22 = CDate::FillFromParts(v50, v20, &v39);
    if ( !v22 )
    {
      *(_DWORD *)a3 = 10240;
      *(_QWORD *)(a3 + 8) = 0;
      *(_QWORD *)(a3 + 16) = 0;
      *(_DWORD *)(a3 + 24) = 0;
      *(_WORD *)(a3 + 8) = v51;
      *(_BYTE *)(a3 + 10) = BYTE2(v51);
      *(_BYTE *)(a3 + 27) = 3;
    }
    return v22;
  }
  if ( v11 == 41 )
  {
    v45 = &CTime::`vftable';
    if ( (unsigned int)v41 > 0x17 )
      return 100;
    if ( HIDWORD(v41) > 0x3B )
      return 100;
    if ( (unsigned int)v42 > 0x3B )
      return 100;
    v31 = *((unsigned int *)&x_rgulPowersOfTen + HIBYTE(v44));
    if ( HIDWORD(v42) >= (unsigned int)v31 || HIBYTE(v44) > 9u )
      return 100;
    v32 = HIDWORD(v42) + v31 * ((int)v42 + 60 * (HIDWORD(v41) + 60 * (int)v41));
    if ( HIBYTE(v44) > a9 )
      v33 = (v32
           + (unsigned __int64)(unsigned int)(5
                                            * *((_DWORD *)&x_rgulPowersOfTen + (unsigned __int8)(HIBYTE(v44) - a9 - 1))))
          / *((unsigned int *)&x_rgulPowersOfTen + (unsigned __int8)(HIBYTE(v44) - a9));
    else
      v33 = *((unsigned int *)&x_rgulPowersOfTen + (unsigned __int8)(a9 - HIBYTE(v44))) * v32;
    v34 = (&x_rgullMaxTime)[(unsigned __int8)a9];
    if ( v33 <= (unsigned __int64)v34 )
      v34 = (const unsigned __int64 *)v33;
    v46 = v34;
    LODWORD(v47) = a9;
    if ( v34 > (&x_rgullMaxTime)[a9] )
    {
      return 100;
    }
    else
    {
      CTime::Serialize((CTime *)&v45, (struct CXVariant *)a3);
      return 0;
    }
  }
  else
  {
    if ( v11 != 42 )
    {
      if ( v11 == 43 )
      {
        v45 = &CDatetimeOffset::`vftable';
        LODWORD(v46) = 0;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v22 = CDatetimeOffset::FillFromPartsHelper(&v45, v20, &v39, (unsigned __int8)a9);
        if ( !v22 )
        {
          CDatetimeOffset::Serialize((CDatetimeOffset *)&v45, (struct CXVariant *)a3, (const struct CTypeInfo *)&v53);
          return 0;
        }
      }
      return v22;
    }
    v53 = &CDatetime2::`vftable';
    v51 = 0;
    v45 = &CTime::`vftable';
    v46 = 0;
    LODWORD(v47) = 0;
    v22 = CDate::FillFromParts(v50, v20, &v39);
    if ( v22 )
      return v22;
    v24 = v51;
    v54 = v51;
    LOBYTE(v38) = 0;
    LOBYTE(v36) = 1;
    LOBYTE(v23) = 1;
    v22 = CTime::FillFromParts(&v45, &v39, (unsigned int)a9, v23, &v38, v36);
    if ( v22 )
      return v22;
    v56 = v46;
    v57 = a9;
    if ( (_BYTE)v38 )
    {
      if ( v24 == 3652058 )
        v56 = (&x_rgullMaxTime)[a9];
      else
        v54 = v24 + 1;
    }
    CDatetime2::Serialize((CDatetime2 *)&v53, (struct CXVariant *)a3);
    return 0;
  }
}

```

## disassembly

```asm
0x100417950  push    rbp
0x100417952  push    r12
0x100417954  push    r13
0x100417956  push    r14
0x100417958  push    r15
0x10041795a  sub     rsp, 110h
0x100417961  lea     rbp, [rsp+40h]
0x100417966  mov     [rbp+0F0h+var_30], 0FFFFFFFFFFFFFFFEh
0x100417971  mov     [rbp+0F0h+arg_0], rbx
0x100417978  mov     [rbp+0F0h+arg_8], rsi
0x10041797f  mov     [rbp+0F0h+arg_10], rdi
0x100417986  mov     rax, cs:__security_cookie
0x10041798d  xor     rax, rbp
0x100417990  mov     [rbp+0F0h+var_28], rax
0x100417997  mov     ebx, r9d
0x10041799a  mov     rdi, r8
0x10041799d  movzx   r15d, dl
0x1004179a1  cmp     byte ptr [r8], 0
0x1004179a5  jnz     loc_10047D09A
0x1004179ab  movzx   eax, cl
0x1004179ae  lea     r13, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004179b5  movzx   eax, byte ptr [rax+r13+45AE60h]
0x1004179be  mov     rdx, [r8+8]
0x1004179c2  mov     r8d, [r8+10h]
0x1004179c6  cmp     byte ptr [rax+r13+45AF60h], 0
0x1004179cf  jnz     loc_10047D0B2
0x1004179d5  mov     eax, r8d
0x1004179d8  add     rax, rax
0x1004179db  lea     rcx, [rax+0Fh]
0x1004179df  cmp     rcx, rax
0x1004179e2  jbe     loc_10047D0A2
0x1004179e8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1004179ec  mov     rax, rcx
0x1004179ef  call    _alloca_probe
0x1004179f4  sub     rsp, rcx
0x1004179f7  lea     rsi, [rsp+130h+var_F0]
0x1004179fc  mov     dword ptr [rsp+130h+var_110], r8d; int
0x100417a01  mov     r9, rsi; wchar_t *
0x100417a04  mov     ecx, [rbp+0F0h+arg_30]; unsigned int
0x100417a0a  call    ?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x100417a0f  mov     r8d, eax
0x100417a12  add     r8d, r8d
0x100417a15  jmp     short loc_100417A18
0x100417a18  lea     eax, [rbx-82h]
0x100417a1e  xor     r12d, r12d
0x100417a21  mov     r14d, r12d
0x100417a24  cmp     eax, 1
0x100417a27  setbe   r14b
0x100417a2b  mov     [rbp+0F0h+var_C4], r14b
0x100417a2f  mov     [rbp+0F0h+var_E8], 76Ch
0x100417a37  mov     [rbp+0F0h+var_E0], 1
0x100417a3e  mov     [rbp+0F0h+var_D4], r12
0x100417a42  mov     [rbp+0F0h+var_CC], r12
0x100417a46  mov     [rbp+0F0h+var_C3], 1
0x100417a4d  mov     [rbp+0F0h+var_80], rsi
0x100417a51  movsxd  rax, r8d
0x100417a54  shr     rax, 1
0x100417a57  mov     [rbp+0F0h+var_78], eax
0x100417a5a  mov     [rbp+0F0h+var_74], ebx
0x100417a5d  mov     dword ptr [rbp+0F0h+var_70], r12d
0x100417a64  movzx   eax, [rbp+0F0h+arg_20]
0x100417a6b  mov     dword ptr [rbp+0F0h+var_70+4], eax
0x100417a71  movzx   eax, [rbp+0F0h+arg_28]
0x100417a78  mov     word ptr [rbp+0F0h+var_68], ax
0x100417a7f  mov     rax, [rbp+0F0h+arg_38]
0x100417a86  mov     [rbp+0F0h+var_60], rax
0x100417a8d  lea     rax, [rbp+0F0h+var_E8]
0x100417a91  mov     [rbp+0F0h+var_58], rax
0x100417a98  cmp     ebx, 0FFh
0x100417a9e  ja      loc_10047D424
0x100417aa4  movzx   eax, bl
0x100417aa7  cmp     [rax+r13+469C20h], r12b
0x100417aaf  jz      loc_10047D424
0x100417ab5  lea     rcx, [rbp+0F0h+var_80]; struct CDateParser *
0x100417ab9  call    ?yyd8parse@@YAHPEAVCDateParser@@@Z; yyd8parse(CDateParser *)
0x100417abe  test    eax, eax
0x100417ac0  jnz     loc_100417BA7
0x100417ac6  lea     rcx, [rbp+0F0h+var_E8]; this
0x100417aca  call    ?FValidDate@dateparts@@QEBA_NXZ; dateparts::FValidDate(void)
0x100417acf  test    al, al
0x100417ad1  jz      loc_10047D0C3
0x100417ad7  cmp     dword ptr [rbp+0F0h+var_D4], 17h
0x100417adb  ja      loc_10047D0C3
0x100417ae1  cmp     dword ptr [rbp+0F0h+var_D4+4], 3Bh ; ';'
0x100417ae5  ja      loc_10047D0C3
0x100417aeb  cmp     dword ptr [rbp+0F0h+var_CC], 3Bh ; ';'
0x100417aef  ja      loc_10047D0C3
0x100417af5  movzx   eax, byte ptr [rbp+0F0h+var_C3+3]
0x100417af9  mov     eax, ds:rva ?x_rgulPowersOfTen@@3QBKB[r13+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x100417b01  cmp     dword ptr [rbp+0F0h+var_CC+4], eax
0x100417b04  jnb     loc_10047D0C3
0x100417b0a  movzx   eax, byte ptr [rbp+0F0h+var_C3+1]
0x100417b0e  cmp     al, 0Eh
0x100417b10  ja      loc_10047D0C3
0x100417b16  movzx   ecx, byte ptr [rbp+0F0h+var_C3+2]
0x100417b1a  cmp     cl, 3Bh ; ';'
0x100417b1d  ja      loc_10047D0C3
0x100417b23  cmp     al, 0Eh
0x100417b25  jz      loc_10047D0BB
0x100417b2b  mov     ebx, r12d
0x100417b2e  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100417b35  mov     rax, [rcx]
0x100417b38  lea     rdx, [rbp+0F0h+var_88]
0x100417b3c  call    qword ptr [rax]
0x100417b3e  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100417b45  mov     rax, [rcx]
0x100417b48  mov     rdx, [rbp+0F0h+var_88]
0x100417b4c  call    qword ptr [rax+10h]
0x100417b4f  test    al, al
0x100417b51  jnz     loc_10047D0CE
0x100417b57  mov     ecx, r15d
0x100417b5a  sub     ecx, 28h ; '('
0x100417b5d  jnz     loc_10041DE48
0x100417b63  mov     [rbp+0F0h+var_90], r12d
0x100417b67  lea     r8, [rbp+0F0h+var_E8]
0x100417b6b  mov     edx, r14d
0x100417b6e  lea     rcx, [rbp+0F0h+var_98]
0x100417b72  call    ?FillFromParts@CDate@@QEAAJW4ECalendar@@PEBUdateparts@@@Z; CDate::FillFromParts(ECalendar,dateparts const *)
0x100417b77  mov     ebx, eax
0x100417b79  test    eax, eax
0x100417b7b  jnz     short loc_100417BA2
0x100417b7d  mov     dword ptr [rdi], 2800h
0x100417b83  mov     [rdi+8], r12
0x100417b87  mov     [rdi+10h], r12
0x100417b8b  mov     [rdi+18h], r12d
0x100417b8f  movzx   eax, word ptr [rbp+0F0h+var_90]
0x100417b93  mov     [rdi+8], ax
0x100417b97  movzx   eax, byte ptr [rbp+0F0h+var_90+2]
0x100417b9b  mov     [rdi+0Ah], al
0x100417b9e  mov     byte ptr [rdi+1Bh], 3
0x100417ba2  mov     eax, ebx
0x100417ba4  jmp     short loc_100417BA7
0x100417ba7  mov     rcx, [rbp+0F0h+var_28]
0x100417bae  xor     rcx, rbp; StackCookie
0x100417bb1  call    __security_check_cookie
0x100417bb6  mov     rbx, [rbp+0F0h+arg_0]
0x100417bbd  mov     rsi, [rbp+0F0h+arg_8]
0x100417bc4  mov     rdi, [rbp+0F0h+arg_10]
0x100417bcb  lea     rsp, [rbp+0D0h]
0x100417bd2  pop     r15
0x100417bd4  pop     r14
0x100417bd6  pop     r13
0x100417bd8  pop     r12
0x100417bda  pop     rbp
0x100417bdb  retn
0x10041de48  sub     ecx, 1
0x10041de4b  jz      loc_10047D316
0x10041de51  sub     ecx, 1
0x10041de54  jnz     loc_10047D28F
0x10041de5a  lea     rax, ??_7CDatetime2@@6B@; const CDatetime2::`vftable'
0x10041de61  mov     [rbp+0F0h+var_80], rax
0x10041de65  mov     [rbp+0F0h+var_90], r12d
0x10041de69  lea     rax, ??_7CTime@@6B@; const CTime::`vftable'
0x10041de70  mov     [rbp+0F0h+var_B8], rax
0x10041de74  mov     [rbp+0F0h+var_B0], r12
0x10041de78  mov     dword ptr [rbp+0F0h+var_A8], r12d
0x10041de7c  lea     r8, [rbp+0F0h+var_E8]
0x10041de80  mov     edx, r14d
0x10041de83  lea     rcx, [rbp+0F0h+var_98]
0x10041de87  call    ?FillFromParts@CDate@@QEAAJW4ECalendar@@PEBUdateparts@@@Z; CDate::FillFromParts(ECalendar,dateparts const *)
0x10041de8c  mov     ebx, eax
0x10041de8e  test    eax, eax
0x10041de90  jnz     loc_100417BA2
0x10041de96  mov     esi, [rbp+0F0h+var_90]
0x10041de99  mov     [rbp+0F0h+var_78], esi
0x10041de9c  mov     byte ptr [rbp+0F0h+var_F0], al
0x10041de9f  mov     [rsp+130h+var_108], 1
0x10041dea4  lea     rax, [rbp+0F0h+var_F0]
0x10041dea8  mov     qword ptr [rsp+130h+var_110], rax
0x10041dead  mov     r9b, 1
0x10041deb0  movsxd  r14, [rbp+0F0h+arg_40]
0x10041deb7  mov     r8d, r14d
0x10041deba  lea     rdx, [rbp+0F0h+var_E8]
0x10041debe  lea     rcx, [rbp+0F0h+var_B8]
0x10041dec2  call    ?FillFromParts@CTime@@QEAAJPEBUdateparts@@W4ETimeScale@@_NPEA_N2@Z; CTime::FillFromParts(dateparts const *,ETimeScale,bool,bool *,bool)
0x10041dec7  mov     ebx, eax
0x10041dec9  test    eax, eax
0x10041decb  jnz     loc_100417BA2
0x10041ded1  mov     rax, [rbp+0F0h+var_B0]
0x10041ded5  mov     [rbp+0F0h+var_70], rax
0x10041dedc  mov     [rbp+0F0h+var_68], r14d
0x10041dee3  cmp     byte ptr [rbp+0F0h+var_F0], bl
0x10041dee6  jnz     loc_10047D2EE
0x10041deec  mov     ebx, r12d
0x10041deef  lea     r8, [rbp+0F0h+var_50]
0x10041def6  mov     rdx, rdi; struct CXVariant *
0x10041def9  lea     rcx, [rbp+0F0h+var_80]; this
0x10041defd  call    ?Serialize@CDatetime2@@QEAAXPEAVCXVariant@@@Z; CDatetime2::Serialize(CXVariant *)
0x10041df02  mov     eax, ebx
0x10041df04  jmp     loc_100417BA7
0x10047d09a  xor     eax, eax
0x10047d09c  jmp     loc_100417BA7
0x10047d0a2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10047d0ac  jmp     loc_1004179E8
0x10047d0b2  mov     rsi, rdx
0x10047d0b5  jmp     loc_100417A18
0x10047d0bb  test    cl, cl
0x10047d0bd  jz      loc_100417B2B
0x10047d0c3  mov     eax, 2
0x10047d0c8  jmp     loc_100417BA7
0x10047d0ce  cmp     byte ptr [rbp+0F0h+var_C3+1], bl
0x10047d0d1  ja      short loc_10047D0DC
0x10047d0d3  cmp     byte ptr [rbp+0F0h+var_C3+2], bl
0x10047d0d6  jbe     loc_100417B57
0x10047d0dc  mov     rdx, gs:58h
0x10047d0e5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047d0ec  mov     ecx, [rax]
0x10047d0ee  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047d0f5  mov     esi, [rax]
0x10047d0f7  add     rsi, [rdx+rcx*8]
0x10047d0fb  mov     rdx, [rsi+100h]
0x10047d102  test    rdx, rdx
0x10047d105  jnz     short loc_10047D116
0x10047d107  xor     ecx, ecx
0x10047d109  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10047d10f  mov     rdx, [rsi+100h]
0x10047d116  mov     [rsp+130h+var_110], 6
0x10047d11b  mov     r9d, 627h
0x10047d121  lea     r8, aSqlNtdbmsMsqlT_10; "sql\\ntdbms\\msql\\typesystem\\tsfnconv"...
0x10047d128  mov     rdx, [rdx+3E8h]
0x10047d12f  mov     ecx, 704h
0x10047d134  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047d13a  mov     rsi, rax
0x10047d13d  mov     [rbp+0F0h+var_88], rax
0x10047d141  mov     dl, 2Bh ; '+'; unsigned __int8
0x10047d143  lea     rcx, [rbp+0F0h+var_50]; this
0x10047d14a  call    ?Init@CTypeInfo@@AEAAXE@Z; CTypeInfo::Init(uchar)
0x10047d14f  or      [rbp+0F0h+var_4F], 1
0x10047d156  movzx   r8d, byte ptr [rbp+0F0h+var_C3+3]
0x10047d15b  movzx   r9d, [rbp+0F0h+var_50]
0x10047d163  mov     edx, r9d
0x10047d166  sub     edx, 29h ; ')'
0x10047d169  jz      loc_10047D252
0x10047d16f  sub     edx, 1
0x10047d172  jz      loc_10047D249
0x10047d178  cmp     edx, 1
0x10047d17b  jz      loc_10047D235
0x10047d181  mov     rcx, r12
0x10047d184  jmp     short loc_10047D187
0x10047d187  movzx   eax, word ptr [rcx]
0x10047d18a  mov     [rbp+0F0h+var_40], ax
0x10047d191  movzx   eax, byte ptr [rcx+2]
0x10047d195  mov     [rbp+0F0h+var_3E], al
0x10047d19b  mov     [rbp+0F0h+var_3D], r8b
0x10047d1a2  cmp     r9b, 0F3h
0x10047d1a6  jz      loc_10047D25C
0x10047d1ac  cmp     r9b, 0F0h
0x10047d1b0  jz      loc_10047D25C
0x10047d1b6  mov     r8d, [rbp+0F0h+var_4C]
0x10047d1bd  cmp     r8d, 0FFh
0x10047d1c4  jbe     loc_10047D25C
0x10047d1ca  mov     rcx, cs:?x_pIUdtProvider@@3PEAUISqlTypeSystemExtender_IUdtProvider@@EA; ISqlTypeSystemExtender_IUdtProvider * x_pIUdtProvider
0x10047d1d1  movzx   edx, [rbp+0F0h+var_4E]
0x10047d1d8  mov     rax, [rcx]
0x10047d1db  mov     [rsp+130h+var_F8], 0
0x10047d1e0  mov     [rsp+130h+var_100], 0
0x10047d1e5  mov     [rsp+130h+var_108], 1
0x10047d1ea  mov     dword ptr [rsp+130h+var_110], 382h
0x10047d1f2  mov     r9, rsi
0x10047d1f5  call    qword ptr [rax+10h]
0x10047d1f8  jmp     short loc_10047D1FB
0x10047d1fb  mov     dword ptr [rsp+130h+var_100], 8A91h
0x10047d203  mov     qword ptr [rsp+130h+var_108], rax
0x10047d208  mov     dword ptr [rsp+130h+var_110], 32F0h
0x10047d210  xor     r9d, r9d
0x10047d213  lea     edx, [r9+5Eh]
0x10047d217  lea     ecx, [rdx+0Dh]
0x10047d21a  lea     r8d, [r9+10h]
0x10047d21e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10047d224  nop
0x10047d225  mov     rcx, rsi
0x10047d228  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10047d22e  nop
0x10047d22f  jmp     loc_100417B57
0x10047d235  lea     rcx, rva ?x_rgDfltDatetimeOffset@@3QBUCTypeDflt@@B[r13]; CTypeInfo const CTypeInfo::tiBit
0x10047d23c  jmp     short loc_10047D23F
0x10047d23f  lea     rcx, [rcx+r8*4]
0x10047d243  jmp     loc_10047D187
0x10047d249  lea     rcx, rva ?x_rgDfltDatetime2@@3QBUCTypeDflt@@B[r13]; CTypeInfo const CTypeInfo::tiBit
0x10047d250  jmp     short loc_10047D23F
0x10047d252  lea     rcx, rva ?x_rgDfltTime@@3QBUCTypeDflt@@B[r13]; CTypeInfo const CTypeInfo::tiBit
0x10047d259  jmp     short loc_10047D23F
0x10047d25c  mov     [rsp+130h+var_F8], 0; bool
0x10047d261  mov     [rsp+130h+var_100], 1; bool
0x10047d266  mov     [rsp+130h+var_108], 0; bool
0x10047d26b  mov     [rsp+130h+var_110], 0; bool
0x10047d270  mov     r9b, 1; bool
0x10047d273  mov     r8d, 382h; unsigned int
0x10047d279  mov     rdx, rsi; wchar_t *
0x10047d27c  lea     rcx, [rbp+0F0h+var_50]; this
0x10047d283  call    ?GetTypeName@CTypeInfo@@QEBAPEB_WPEA_WK_N1111@Z; CTypeInfo::GetTypeName(wchar_t *,ulong,bool,bool,bool,bool,bool)
0x10047d288  nop
0x10047d289  jmp     loc_10047D1FB
0x10047d28f  cmp     ecx, 1
0x10047d292  jnz     loc_100417BA2
0x10047d298  lea     rax, ??_7CDatetimeOffset@@6B@; const CDatetimeOffset::`vftable'
0x10047d29f  mov     [rbp+0F0h+var_B8], rax
0x10047d2a3  mov     dword ptr [rbp+0F0h+var_B0], r12d
0x10047d2a7  mov     [rbp+0F0h+var_A8], r12
0x10047d2ab  mov     [rbp+0F0h+var_A0], r12d
  ... truncated ...
```
