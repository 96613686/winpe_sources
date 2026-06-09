# BinXmlWriter::ParseTemplateString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)

- ea: `0x18002eebc`
- end: `0x18002f2e3`
- name: `?ParseTemplateString@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z`
- size: `1063`
- prototype: `void __fastcall(BinXmlWriter *this, _QWORD *, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002ebac`

## callees

- `0x1800136d0`
- `0x1800139a0`
- `0x18001fc00`
- `0x180023548`
- `0x18002e300`
- `0x18002eebc`
- `0x18002f41c`
- `0x18002f568`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlWriter::ParseTemplateString(BinXmlWriter *this, _QWORD *a2, char a3)
{
  unsigned __int64 v3; // rbx
  int v6; // r13d
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  int v21; // r8d
  unsigned int v22; // edx
  __int64 v23; // rcx
  int v24; // ecx
  __int64 v25; // r11
  __int128 pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  __int64 v27; // [rsp+40h] [rbp-49h]
  int v28; // [rsp+48h] [rbp-41h]
  int v29; // [rsp+4Ch] [rbp-3Dh]
  int v30; // [rsp+50h] [rbp-39h]
  __int64 v31; // [rsp+58h] [rbp-31h] BYREF
  int v32; // [rsp+60h] [rbp-29h]
  int v33; // [rsp+64h] [rbp-25h]
  __int64 v34; // [rsp+68h] [rbp-21h] BYREF
  int v35; // [rsp+70h] [rbp-19h]
  int v36; // [rsp+74h] [rbp-15h]
  int v37; // [rsp+78h] [rbp-11h]
  char v38; // [rsp+7Ch] [rbp-Dh]
  __int16 v39; // [rsp+7Dh] [rbp-Ch]
  char v40; // [rsp+7Fh] [rbp-Ah]
  __int128 v41; // [rsp+80h] [rbp-9h] BYREF
  char v42[16]; // [rsp+90h] [rbp+7h] BYREF
  char v43; // [rsp+A0h] [rbp+17h] BYREF
  unsigned __int8 v44; // [rsp+F8h] [rbp+6Fh] BYREF
  char v45; // [rsp+100h] [rbp+77h]
  unsigned int v46; // [rsp+108h] [rbp+7Fh] BYREF

  v45 = a3;
  v3 = a2[1];
  v6 = 0;
  v7 = 0;
  v8 = 37;
  v9 = *a2;
  v10 = *a2;
  while ( 1 )
  {
    v11 = utl::_StringTraits<utl::char_traits<wchar_t>>::find(v10, v3, v7, v8);
    v14 = v11;
    if ( v11 == -1 )
      break;
    if ( v11 + 1 >= v3 || (v15 = 2 * v11, v16 = 2 * v11 + v9, *(_WORD *)(v16 + 2) == (_WORD)v8) )
    {
      v20 = 2;
    }
    else
    {
      if ( v13 && v6 > 0 )
      {
        v41 = *(_OWORD *)utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>::substr(a2, v42, v13, v11 - v13);
        BinXmlWriter::StrLenValue(this, &v41, v17);
      }
      v18 = a2[1];
      v46 = 0;
      v44 = 0;
      v19 = utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
              (unsigned int)&v43,
              (int)v16 + 2,
              (int)v9 + 2 * (int)v18,
              (unsigned int)&v46,
              10,
              (__int64)&v44);
      if ( *(_DWORD *)(v19 + 8) || v46 > (unsigned int)v44 + 0x7FFFFFFF )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 87);
        }
        v27 = 0;
        v28 = 87;
        v29 = -1;
        pExceptionObject = 0;
        v30 = 1014;
        throw (EvtException *)&pExceptionObject;
      }
      v20 = (*(_QWORD *)v19 - v15 - v9 - 2) >> 1;
      if ( (unsigned __int64)(v20 - 1) > 1 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 87);
        }
        v27 = 0;
        v28 = 87;
        v29 = -1;
        pExceptionObject = 0;
        v30 = 1021;
        throw (EvtException *)&pExceptionObject;
      }
      v21 = v44 + (v46 ^ -v44);
      if ( v21 <= 0 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 87);
        }
        v27 = 0;
        v28 = 87;
        v29 = -1;
        pExceptionObject = 0;
        v30 = 1026;
        throw (EvtException *)&pExceptionObject;
      }
      v34 = 0;
      v39 = 0;
      v22 = v21 - 1;
      v40 = 0;
      v35 = -1;
      v38 = 0;
      v36 = 8;
      v37 = (v45 != 0) + 13;
      v23 = *((_QWORD *)this + 11);
      if ( v23 )
      {
        if ( v22 >= *((_DWORD *)this + 24) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 87);
          }
          v27 = 0;
          v28 = 87;
          v29 = -1;
          pExceptionObject = 0;
          v30 = 1043;
          throw (EvtException *)&pExceptionObject;
        }
        v24 = *(_DWORD *)(v23 + 4LL * v21 - 4);
        if ( (v24 & 0x80u) != 0 && *((_BYTE *)this + 104) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 50);
          }
          v27 = 0;
          v28 = 50;
          v29 = -1;
          pExceptionObject = 0;
          v30 = 1054;
          throw (EvtException *)&pExceptionObject;
        }
        LODWORD(v34) = v22 | (v24 << 16);
      }
      else
      {
        LODWORD(v34) = v22 | 0x10000;
      }
      ++v6;
      BinXmlWriter::AddToken(this, (const struct BinXmlToken *)&v34);
      v8 = 37;
    }
    v25 = v20 + v14;
    v10 = v9;
    v3 = a2[1];
    v7 = v25;
  }
  if ( !v13 )
  {
    v32 = *((_DWORD *)a2 + 2);
    v33 = 1;
    v31 = v12;
    BinXmlWriter::Value((WriteBuffer **)this, (const struct BinXmlVariant *)&v31);
  }
}

```

## disassembly

```asm
0x18002eebc  mov     [rsp-8+arg_0], rbx
0x18002eec1  mov     [rsp-8+arg_10], r8b
0x18002eec6  push    rbp
0x18002eec7  push    rsi
0x18002eec8  push    rdi
0x18002eec9  push    r12
0x18002eecb  push    r13
0x18002eecd  push    r14
0x18002eecf  push    r15
0x18002eed1  lea     rbp, [rsp-27h]
0x18002eed6  sub     rsp, 0B0h
0x18002eedd  mov     r10, [rdx]
0x18002eee0  xor     r14d, r14d
0x18002eee3  mov     rbx, [rdx+8]
0x18002eee7  mov     r12, rdx
0x18002eeea  mov     rdi, rcx
0x18002eeed  mov     r13d, r14d
0x18002eef0  mov     r11d, r14d
0x18002eef3  mov     r8d, r14d
0x18002eef6  lea     r9d, [r14+25h]
0x18002eefa  mov     r15, r10
0x18002eefd  mov     rax, r10
0x18002ef00  mov     rdx, rbx
0x18002ef03  mov     rcx, rax
0x18002ef06  call    ?find@?$_StringTraits@U?$char_traits@_W@utl@@@utl@@SA_KPEB_W_K1_W@Z; utl::_StringTraits<utl::char_traits<wchar_t>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t)
0x18002ef0b  mov     rsi, rax
0x18002ef0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef12  jz      loc_18002F2A4
0x18002ef18  lea     rcx, [rax+1]
0x18002ef1c  cmp     rcx, rbx
0x18002ef1f  jnb     loc_18002F07B
0x18002ef25  lea     r14, [rax+rax]
0x18002ef29  lea     rbx, [r14+r15]
0x18002ef2d  cmp     [rbx+2], r9w
0x18002ef32  jz      loc_18002F075
0x18002ef38  test    r11, r11
0x18002ef3b  jz      short loc_18002EF6B
0x18002ef3d  test    r13d, r13d
0x18002ef40  jle     short loc_18002EF6B
0x18002ef42  mov     r9, rax
0x18002ef45  lea     rdx, [rbp+57h+var_50]
0x18002ef49  sub     r9, r11
0x18002ef4c  mov     r8, r11
0x18002ef4f  mov     rcx, r12
0x18002ef52  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@QEBA?AV12@_K0@Z; utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>::substr(unsigned __int64,unsigned __int64)
0x18002ef57  lea     rdx, [rbp+57h+var_60]
0x18002ef5b  mov     rcx, rdi; this
0x18002ef5e  movups  xmm0, xmmword ptr [rax]
0x18002ef61  movdqu  [rbp+57h+var_60], xmm0
0x18002ef66  call    ?StrLenValue@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::StrLenValue(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ef6b  mov     rax, [r12+8]
0x18002ef70  lea     r9, [rbp+57h+arg_18]
0x18002ef74  lea     rdx, [rbx+2]
0x18002ef78  mov     [rbp+57h+arg_18], 0
0x18002ef7f  lea     rcx, [rbp+57h+var_40]
0x18002ef83  mov     [rbp+57h+arg_8], 0
0x18002ef87  lea     r8, [r15+rax*2]
0x18002ef8b  lea     rax, [rbp+57h+arg_8]
0x18002ef8f  mov     [rsp+0E0h+var_B8], rax
0x18002ef94  mov     [rsp+0E0h+var_C0], 0Ah
0x18002ef9c  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x18002efa1  cmp     dword ptr [rax+8], 0
0x18002efa5  jnz     loc_18002F238
0x18002efab  movzx   edx, [rbp+57h+arg_8]
0x18002efaf  lea     ecx, [rdx+7FFFFFFFh]
0x18002efb5  cmp     [rbp+57h+arg_18], ecx
0x18002efb8  ja      loc_18002F238
0x18002efbe  mov     rbx, [rax]
0x18002efc1  sub     rbx, r14
0x18002efc4  sub     rbx, r15
0x18002efc7  sub     rbx, 2
0x18002efcb  sar     rbx, 1
0x18002efce  lea     rax, [rbx-1]
0x18002efd2  cmp     rax, 1
0x18002efd6  ja      loc_18002F1CC
0x18002efdc  mov     r8d, edx
0x18002efdf  xor     r14d, r14d
0x18002efe2  neg     r8d
0x18002efe5  xor     r8d, [rbp+57h+arg_18]
0x18002efe9  add     r8d, edx
0x18002efec  test    r8d, r8d
0x18002efef  jle     loc_18002F164
0x18002eff5  xor     eax, eax
0x18002eff7  mov     [rbp+57h+var_78], r14
0x18002effb  mov     [rbp+57h+var_63], ax
0x18002efff  lea     edx, [r8-1]
0x18002f003  mov     [rbp+57h+var_61], al
0x18002f006  mov     al, [rbp+57h+arg_10]
0x18002f009  neg     al
0x18002f00b  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x18002f012  mov     [rbp+57h+var_64], r14b
0x18002f016  sbb     ecx, ecx
0x18002f018  mov     [rbp+57h+var_6C], 8
0x18002f01f  neg     ecx
0x18002f021  add     ecx, 0Dh
0x18002f024  mov     [rbp+57h+var_68], ecx
0x18002f027  mov     rcx, [rdi+58h]
0x18002f02b  test    rcx, rcx
0x18002f02e  jz      short loc_18002F054
0x18002f030  cmp     edx, [rdi+60h]
0x18002f033  jnb     loc_18002F0FC
0x18002f039  movsxd  rax, r8d
0x18002f03c  mov     ecx, [rcx+rax*4-4]
0x18002f040  test    cl, cl
0x18002f042  jns     short loc_18002F04A
0x18002f044  cmp     [rdi+68h], r14b
0x18002f048  jnz     short loc_18002F094
0x18002f04a  shl     ecx, 10h
0x18002f04d  or      ecx, edx
0x18002f04f  mov     dword ptr [rbp+57h+var_78], ecx
0x18002f052  jmp     short loc_18002F05B
0x18002f054  bts     edx, 10h
0x18002f058  mov     dword ptr [rbp+57h+var_78], edx
0x18002f05b  inc     r13d
0x18002f05e  lea     rdx, [rbp+57h+var_78]; struct BinXmlToken *
0x18002f062  mov     rcx, rdi; this
0x18002f065  call    ?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z; BinXmlWriter::AddToken(BinXmlToken const &)
0x18002f06a  mov     r10, r15
0x18002f06d  mov     r9d, 25h ; '%'
0x18002f073  jmp     short loc_18002F080
0x18002f075  mov     r10, r15
0x18002f078  xor     r14d, r14d
0x18002f07b  mov     ebx, 2
0x18002f080  lea     r11, [rbx+rsi]
0x18002f084  mov     rax, r15
0x18002f087  mov     rbx, [r12+8]
0x18002f08c  mov     r8, r11
0x18002f08f  jmp     loc_18002EF00
0x18002f094  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f09b  lea     rax, WPP_GLOBAL_Control
0x18002f0a2  mov     ebx, 32h ; '2'
0x18002f0a7  cmp     rcx, rax
0x18002f0aa  jz      short loc_18002F0CE
0x18002f0ac  test    byte ptr [rcx+1Ch], 2
0x18002f0b0  jz      short loc_18002F0CE
0x18002f0b2  cmp     byte ptr [rcx+19h], 2
0x18002f0b6  jb      short loc_18002F0CE
0x18002f0b8  mov     rcx, [rcx+10h]
0x18002f0bc  lea     edx, [rbx-17h]
0x18002f0bf  mov     r9d, ebx
0x18002f0c2  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f0c9  call    WPP_SF_D
0x18002f0ce  xorps   xmm0, xmm0
0x18002f0d1  mov     [rbp+57h+var_A0], r14
0x18002f0d5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f0dc  mov     [rbp+57h+var_98], ebx
0x18002f0df  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f0e3  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f0ea  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f0ef  mov     [rbp+57h+var_90], 41Eh
0x18002f0f6  call    _CxxThrowException_0
0x18002f0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f103  lea     rax, WPP_GLOBAL_Control
0x18002f10a  mov     ebx, 57h ; 'W'
0x18002f10f  cmp     rcx, rax
0x18002f112  jz      short loc_18002F136
0x18002f114  test    byte ptr [rcx+1Ch], 2
0x18002f118  jz      short loc_18002F136
0x18002f11a  cmp     byte ptr [rcx+19h], 2
0x18002f11e  jb      short loc_18002F136
0x18002f120  mov     rcx, [rcx+10h]
0x18002f124  lea     edx, [rbx-3Dh]
0x18002f127  mov     r9d, ebx
0x18002f12a  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f131  call    WPP_SF_D
0x18002f136  xorps   xmm0, xmm0
0x18002f139  mov     [rbp+57h+var_A0], r14
0x18002f13d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f144  mov     [rbp+57h+var_98], ebx
0x18002f147  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f14b  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f152  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f157  mov     [rbp+57h+var_90], 413h
0x18002f15e  call    _CxxThrowException_0
0x18002f164  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f16b  lea     rax, WPP_GLOBAL_Control
0x18002f172  mov     ebx, 57h ; 'W'
0x18002f177  cmp     rcx, rax
0x18002f17a  jz      short loc_18002F19E
0x18002f17c  test    byte ptr [rcx+1Ch], 2
0x18002f180  jz      short loc_18002F19E
0x18002f182  cmp     byte ptr [rcx+19h], 2
0x18002f186  jb      short loc_18002F19E
0x18002f188  mov     rcx, [rcx+10h]
0x18002f18c  lea     edx, [rbx-3Eh]
0x18002f18f  mov     r9d, ebx
0x18002f192  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f199  call    WPP_SF_D
0x18002f19e  xorps   xmm0, xmm0
0x18002f1a1  mov     [rbp+57h+var_A0], r14
0x18002f1a5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f1ac  mov     [rbp+57h+var_98], ebx
0x18002f1af  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f1b3  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f1ba  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f1bf  mov     [rbp+57h+var_90], 402h
0x18002f1c6  call    _CxxThrowException_0
0x18002f1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1d3  lea     rax, WPP_GLOBAL_Control
0x18002f1da  mov     ebx, 57h ; 'W'
0x18002f1df  cmp     rcx, rax
0x18002f1e2  jz      short loc_18002F206
0x18002f1e4  test    byte ptr [rcx+1Ch], 2
0x18002f1e8  jz      short loc_18002F206
0x18002f1ea  cmp     byte ptr [rcx+19h], 2
0x18002f1ee  jb      short loc_18002F206
0x18002f1f0  mov     rcx, [rcx+10h]
0x18002f1f4  lea     edx, [rbx-3Fh]
0x18002f1f7  mov     r9d, ebx
0x18002f1fa  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f201  call    WPP_SF_D
0x18002f206  xorps   xmm0, xmm0
0x18002f209  mov     [rbp+57h+var_A0], 0
0x18002f211  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f218  mov     [rbp+57h+var_98], ebx
0x18002f21b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f21f  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f226  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f22b  mov     [rbp+57h+var_90], 3FDh
0x18002f232  call    _CxxThrowException_0
0x18002f238  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f23f  lea     rax, WPP_GLOBAL_Control
0x18002f246  mov     ebx, 57h ; 'W'
0x18002f24b  cmp     rcx, rax
0x18002f24e  jz      short loc_18002F272
0x18002f250  test    byte ptr [rcx+1Ch], 2
0x18002f254  jz      short loc_18002F272
0x18002f256  cmp     byte ptr [rcx+19h], 2
0x18002f25a  jb      short loc_18002F272
0x18002f25c  mov     rcx, [rcx+10h]
0x18002f260  lea     edx, [rbx-40h]
0x18002f263  mov     r9d, ebx
0x18002f266  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002f26d  call    WPP_SF_D
0x18002f272  xorps   xmm0, xmm0
0x18002f275  mov     [rbp+57h+var_A0], 0
0x18002f27d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f284  mov     [rbp+57h+var_98], ebx
0x18002f287  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f28b  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f292  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f297  mov     [rbp+57h+var_90], 3F6h
0x18002f29e  call    _CxxThrowException_0
0x18002f2a4  test    r11, r11
0x18002f2a7  jnz     short loc_18002F2C8
0x18002f2a9  mov     eax, [r12+8]
0x18002f2ae  lea     rdx, [rbp+57h+var_88]; struct BinXmlVariant *
0x18002f2b2  mov     rcx, rdi; this
0x18002f2b5  mov     [rbp+57h+var_80], eax
0x18002f2b8  mov     [rbp+57h+var_7C], 1
0x18002f2bf  mov     [rbp+57h+var_88], r10
0x18002f2c3  call    ?Value@BinXmlWriter@@QEAAXAEBUBinXmlVariant@@@Z; BinXmlWriter::Value(BinXmlVariant const &)
0x18002f2c8  mov     rbx, [rsp+0E0h+arg_0]
0x18002f2d0  add     rsp, 0B0h
0x18002f2d7  pop     r15
0x18002f2d9  pop     r14
0x18002f2db  pop     r13
0x18002f2dd  pop     r12
0x18002f2df  pop     rdi
0x18002f2e0  pop     rsi
0x18002f2e1  pop     rbp
0x18002f2e2  retn
```
