# SXWriter::startDocument(void)

- ea: `0x100408e10`
- end: `0x1004091ba`
- name: `?startDocument@SXWriter@@UEAAJXZ`
- size: `938`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x100401350`
- `0x100408e10`
- `0x1004091f0`
- `0x100409660`
- `0x100409740`
- `0x100424580`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x100409032`
- `OLEAUT32!__imp_SysStringLen` at `0x100409071`
- `OLEAUT32!__imp_SysStringLen` at `0x1004090ef`
- `OLEAUT32!__imp_SysStringLen` at `0x100409032`
- `OLEAUT32!__imp_SysStringLen` at `0x100409071`
- `OLEAUT32!__imp_SysStringLen` at `0x1004090ef`
- `OLEAUT32!__imp_VariantClear` at `0x100408fde`
- `OLEAUT32!__imp_VariantClear` at `0x100408fde`

## pseudocode

```c
__int64 __fastcall SXWriter::startDocument(SXWriter *this)
{
  unsigned int v2; // r15d
  int (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  OLECHAR *v4; // rbx
  BSTR bstrVal; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r10d
  __int64 v9; // r8
  __int64 v10; // rcx
  OLECHAR v11; // ax
  const wchar_t *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // r9
  UINT v15; // ebx
  unsigned int v16; // r9d
  const wchar_t *v17; // r8
  int v18; // eax
  unsigned __int8 v19; // dl
  BSTR pbstr[2]; // [rsp+58h] [rbp-90h] BYREF
  __int64 v22; // [rsp+68h] [rbp-80h]
  LONGLONG llVal; // [rsp+70h] [rbp-78h]
  __int64 v24; // [rsp+78h] [rbp-70h]
  __int64 v25; // [rsp+80h] [rbp-68h]
  __int128 v26; // [rsp+90h] [rbp-58h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v29; // [rsp+F8h] [rbp+10h] BYREF

  v2 = 0;
  v29 = 0;
  v26 = 0;
  v27 = 0;
  if ( *((_DWORD *)this + 52) != 1200 )
    *((_BYTE *)this + 272) = 1;
  SXWriter::WritePreamble((SXWriter *)((char *)this - 64));
  if ( !*((_BYTE *)this + 186) )
  {
    v3 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 9);
    if ( v3 && (**v3)(v3, &IID_ISAXXMLReader, &v29) >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, void *, __int128 *))(*(_QWORD *)v29 + 40LL))(
             v29,
             CodeStringPtr::xmlDeclEncoding,
             &v26);
      if ( v2 )
        goto LABEL_49;
      v4 = (OLECHAR *)((char *)this + 140);
      if ( !*((_WORD *)this + 70) )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        v2 = (*(__int64 (__fastcall **)(__int64, void *, VARIANTARG *))(*(_QWORD *)v29 + 40LL))(
               v29,
               CodeStringPtr::xmlDeclVersion,
               &pvarg);
        if ( v2 )
          goto LABEL_49;
        bstrVal = pvarg.bstrVal;
        if ( pvarg.llVal )
        {
          v6 = 2147483646;
          v25 = 2147483646;
          llVal = pvarg.llVal;
          v7 = 16;
          v24 = 16;
          v8 = 0;
          v9 = 0;
          while ( v7 )
          {
            if ( !v6 || !*bstrVal )
              goto LABEL_17;
            *v4++ = *bstrVal;
            llVal = (LONGLONG)++bstrVal;
            v24 = --v7;
            v25 = --v6;
            ++v9;
          }
          --v4;
          v8 = -2147024774;
LABEL_17:
          *v4 = 0;
          if ( v8 )
          {
            MXRRaiseException(-2147024809);
            goto LABEL_53;
          }
        }
        VariantClear(&pvarg);
      }
      if ( *((_DWORD *)this + 16) == -1 )
      {
        *(_OWORD *)pbstr = 0;
        v22 = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, void *, BSTR *))(*(_QWORD *)v29 + 40LL))(
               v29,
               CodeStringPtr::xmlDeclStandalone,
               pbstr);
        if ( v2 )
          goto LABEL_49;
        if ( SysStringLen(pbstr[1]) == 3 )
        {
          v10 = 0;
          while ( 1 )
          {
            v11 = pbstr[1][v10++];
            if ( v11 != aYes[v10 - 1] )
              break;
            if ( v10 == 4 )
            {
              *((_DWORD *)this + 16) = 1;
              goto LABEL_31;
            }
          }
        }
        if ( SysStringLen(pbstr[1]) == 2 && *pbstr[1] == 110 && pbstr[1][1] == 111 && !pbstr[1][2] )
          *((_DWORD *)this + 16) = 0;
      }
    }
LABEL_31:
    v12 = L"1.0";
    if ( *((_WORD *)this + 70) )
      v12 = (const wchar_t *)((char *)this + 140);
    SXWriter::WriteByte((SXWriter *)((char *)this - 64), 0xFEu);
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    SXWriter::WriteTextData((SXWriter *)((char *)this - 64), 0, v12, v14);
    if ( (_WORD)v26 )
    {
      v15 = SysStringLen(*((BSTR *)&v26 + 1));
      if ( !v15 )
      {
LABEL_42:
        v18 = *((_DWORD *)this + 16);
        switch ( v18 )
        {
          case -1:
            v19 = 0;
            goto LABEL_48;
          case 0:
            v19 = 2;
            goto LABEL_48;
          case 1:
            v19 = 1;
LABEL_48:
            SXWriter::WriteByte((SXWriter *)((char *)this - 64), v19);
            goto LABEL_49;
        }
LABEL_53:
        MXRRaiseException(-2147467259);
        __debugbreak();
        JUMPOUT(0x1004091BALL);
      }
      SXWriter::WriteByte((SXWriter *)((char *)this - 64), 0xFDu);
      v16 = v15;
      v17 = (const wchar_t *)*((_QWORD *)&v26 + 1);
    }
    else
    {
      SXWriter::WriteByte((SXWriter *)((char *)this - 64), 0xFDu);
      v17 = (const wchar_t *)*((_QWORD *)this + 16);
      do
        ++v13;
      while ( v17[v13] );
      v16 = v13;
    }
    SXWriter::WriteTextData((SXWriter *)((char *)this - 64), 0, v17, v16);
    goto LABEL_42;
  }
LABEL_49:
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return v2;
}

```

## disassembly

```asm
0x100408e10  mov     r11, rsp
0x100408e13  mov     [r11+8], rbx
0x100408e17  mov     [r11+18h], rsi
0x100408e1b  push    rdi
0x100408e1c  push    r14
0x100408e1e  push    r15
0x100408e20  sub     rsp, 0D0h
0x100408e27  mov     rdi, rcx
0x100408e2a  xor     esi, esi
0x100408e2c  mov     r15d, esi
0x100408e2f  mov     [rsp+0E8h+var_B8], esi
0x100408e33  mov     [r11+10h], rsi
0x100408e37  xorps   xmm0, xmm0
0x100408e3a  xor     eax, eax
0x100408e3c  movups  xmmword ptr [r11-58h], xmm0
0x100408e41  mov     [r11-48h], rax
0x100408e45  cmp     dword ptr [rcx+0D0h], 4B0h
0x100408e4f  jz      short loc_100408E58
0x100408e51  mov     byte ptr [rcx+110h], 1
0x100408e58  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x100408e5c  call    ?WritePreamble@SXWriter@@AEAAXXZ; SXWriter::WritePreamble(void)
0x100408e61  cmp     byte ptr [rdi+0BAh], 0
0x100408e68  jnz     loc_100409162
0x100408e6e  mov     rcx, [rdi+48h]
0x100408e72  test    rcx, rcx
0x100408e75  jz      loc_100409098
0x100408e7b  mov     rax, [rcx]
0x100408e7e  lea     r8, [rsp+0E8h+arg_8]
0x100408e86  lea     rdx, IID_ISAXXMLReader
0x100408e8d  mov     rax, [rax]
0x100408e90  call    cs:__guard_dispatch_icall_fptr
0x100408e96  test    eax, eax
0x100408e98  js      loc_100409098
0x100408e9e  mov     rcx, [rsp+0E8h+arg_8]
0x100408ea6  mov     rax, [rcx]
0x100408ea9  lea     r8, [rsp+0E8h+var_58]
0x100408eb1  mov     rdx, cs:?xmlDeclEncoding@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclEncoding
0x100408eb8  mov     rax, [rax+28h]
0x100408ebc  call    cs:__guard_dispatch_icall_fptr
0x100408ec2  mov     r15d, eax
0x100408ec5  mov     [rsp+0E8h+var_B8], eax
0x100408ec9  test    eax, eax
0x100408ecb  jnz     loc_10040916E
0x100408ed1  lea     rbx, [rdi+8Ch]
0x100408ed8  cmp     word ptr [rbx], 0
0x100408edc  jnz     loc_100408FE4
0x100408ee2  xorps   xmm0, xmm0
0x100408ee5  xor     eax, eax
0x100408ee7  movups  xmmword ptr [rsp+0E8h+pvarg], xmm0
0x100408eef  mov     qword ptr [rsp+0E8h+pvarg+10h], rax
0x100408ef7  mov     rcx, [rsp+0E8h+arg_8]
0x100408eff  mov     rax, [rcx]
0x100408f02  lea     r8, [rsp+0E8h+pvarg]
0x100408f0a  mov     rdx, cs:?xmlDeclVersion@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclVersion
0x100408f11  mov     rax, [rax+28h]
0x100408f15  call    cs:__guard_dispatch_icall_fptr
0x100408f1b  mov     r15d, eax
0x100408f1e  mov     [rsp+0E8h+var_B8], eax
0x100408f22  test    eax, eax
0x100408f24  jnz     loc_10040916E
0x100408f2a  mov     rax, qword ptr [rsp+0E8h+pvarg+8]
0x100408f32  test    rax, rax
0x100408f35  jz      loc_100408FD6
0x100408f3b  mov     edx, 7FFFFFFEh
0x100408f40  mov     [rsp+0E8h+var_68], rdx
0x100408f48  mov     [rsp+0E8h+var_78], rax
0x100408f4d  mov     ecx, 10h
0x100408f52  mov     [rsp+0E8h+var_70], rcx
0x100408f57  mov     [rsp+0E8h+var_A0], rbx
0x100408f5c  mov     r10d, esi
0x100408f5f  mov     r8, rsi
0x100408f62  mov     [rsp+0E8h+var_98], rsi
0x100408f67  test    rcx, rcx
0x100408f6a  jz      short loc_100408FB3
0x100408f6c  test    rdx, rdx
0x100408f6f  jz      short loc_100408FAE
0x100408f71  movzx   r9d, word ptr [rax]
0x100408f75  test    r9w, r9w
0x100408f79  jz      short loc_100408FAE
0x100408f7b  mov     [rbx], r9w
0x100408f7f  add     rbx, 2
0x100408f83  mov     [rsp+0E8h+var_A0], rbx
0x100408f88  add     rax, 2
0x100408f8c  mov     [rsp+0E8h+var_78], rax
0x100408f91  dec     rcx
0x100408f94  mov     [rsp+0E8h+var_70], rcx
0x100408f99  dec     rdx
0x100408f9c  mov     [rsp+0E8h+var_68], rdx
0x100408fa4  inc     r8
0x100408fa7  mov     [rsp+0E8h+var_98], r8
0x100408fac  jmp     short loc_100408F67
0x100408fae  test    rcx, rcx
0x100408fb1  jnz     short loc_100408FCA
0x100408fb3  sub     rbx, 2
0x100408fb7  mov     [rsp+0E8h+var_A0], rbx
0x100408fbc  dec     r8
0x100408fbf  mov     [rsp+0E8h+var_98], r8
0x100408fc4  mov     r10d, 8007007Ah
0x100408fca  mov     [rbx], si
0x100408fcd  test    r10d, r10d
0x100408fd0  jnz     loc_1004091A4
0x100408fd6  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x100408fde  call    cs:__imp_VariantClear
0x100408fe4  cmp     dword ptr [rdi+40h], 0FFFFFFFFh
0x100408fe8  jnz     loc_100409098
0x100408fee  xorps   xmm0, xmm0
0x100408ff1  xor     eax, eax
0x100408ff3  movups  xmmword ptr [rsp+0E8h+pbstr], xmm0
0x100408ff8  mov     [rsp+0E8h+var_80], rax
0x100408ffd  mov     rcx, [rsp+0E8h+arg_8]
0x100409005  mov     rax, [rcx]
0x100409008  lea     r8, [rsp+0E8h+pbstr]
0x10040900d  mov     rdx, cs:?xmlDeclStandalone@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlDeclStandalone
0x100409014  mov     rax, [rax+28h]
0x100409018  call    cs:__guard_dispatch_icall_fptr
0x10040901e  mov     r15d, eax
0x100409021  mov     [rsp+0E8h+var_B8], eax
0x100409025  test    eax, eax
0x100409027  jnz     loc_10040916E
0x10040902d  mov     rcx, [rsp+0E8h+pbstr+8]; pbstr
0x100409032  call    cs:__imp_SysStringLen
0x100409038  mov     rdx, [rsp+0E8h+pbstr+8]
0x10040903d  cmp     eax, 3
0x100409040  jnz     short loc_10040906E
0x100409042  mov     rcx, rsi
0x100409045  lea     r8, aYes; "yes"
0x10040904c  nop     dword ptr [rax+00h]
0x100409050  movzx   eax, word ptr [rdx+rcx*2]
0x100409054  inc     rcx
0x100409057  cmp     ax, [r8+rcx*2-2]
0x10040905d  jnz     short loc_10040906E
0x10040905f  cmp     rcx, 4
0x100409063  jnz     short loc_100409050
0x100409065  mov     dword ptr [rdi+40h], 1
0x10040906c  jmp     short loc_100409098
0x10040906e  mov     rcx, rdx; pbstr
0x100409071  call    cs:__imp_SysStringLen
0x100409077  cmp     eax, 2
0x10040907a  jnz     short loc_100409098
0x10040907c  mov     rax, [rsp+0E8h+pbstr+8]
0x100409081  cmp     word ptr [rax], 6Eh ; 'n'
0x100409085  jnz     short loc_100409098
0x100409087  cmp     word ptr [rax+2], 6Fh ; 'o'
0x10040908c  jnz     short loc_100409098
0x10040908e  cmp     word ptr [rax+4], 0
0x100409093  jnz     short loc_100409098
0x100409095  mov     [rdi+40h], esi
0x100409098  lea     rax, [rdi+8Ch]
0x10040909f  lea     rsi, psz; "1.0"
0x1004090a6  cmp     word ptr [rax], 0
0x1004090aa  cmovnz  rsi, rax
0x1004090ae  mov     dl, 0FEh; unsigned __int8
0x1004090b0  lea     rcx, [rdi-40h]; this
0x1004090b4  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x1004090b9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1004090c0  mov     r9, rbx
0x1004090c3  inc     r9; int
0x1004090c6  cmp     word ptr [rsi+r9*2], 0
0x1004090cc  jnz     short loc_1004090C3
0x1004090ce  mov     r8, rsi; wchar_t *
0x1004090d1  xor     edx, edx; bool
0x1004090d3  lea     rcx, [rdi-40h]; this
0x1004090d7  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x1004090dc  cmp     [rsp+0E8h+var_58], 0
0x1004090e5  jz      short loc_100409113
0x1004090e7  mov     rcx, [rsp+0E8h+var_50]; pbstr
0x1004090ef  call    cs:__imp_SysStringLen
0x1004090f5  mov     ebx, eax
0x1004090f7  test    eax, eax
0x1004090f9  jz      short loc_10040913E
0x1004090fb  mov     dl, 0FDh; unsigned __int8
0x1004090fd  lea     rcx, [rdi-40h]; this
0x100409101  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100409106  mov     r9d, ebx
0x100409109  mov     r8, [rsp+0E8h+var_50]
0x100409111  jmp     short loc_100409133
0x100409113  mov     dl, 0FDh; unsigned __int8
0x100409115  lea     rcx, [rdi-40h]; this
0x100409119  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040911e  mov     r8, [rdi+80h]; wchar_t *
0x100409125  inc     rbx
0x100409128  cmp     word ptr [r8+rbx*2], 0
0x10040912e  jnz     short loc_100409125
0x100409130  mov     r9, rbx; int
0x100409133  xor     edx, edx; bool
0x100409135  lea     rcx, [rdi-40h]; this
0x100409139  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x10040913e  mov     eax, [rdi+40h]
0x100409141  cmp     eax, 0FFFFFFFFh
0x100409144  jz      short loc_100409157
0x100409146  test    eax, eax
0x100409148  jz      short loc_100409153
0x10040914a  cmp     eax, 1
0x10040914d  jnz     short loc_1004091AE
0x10040914f  mov     dl, 1
0x100409151  jmp     short loc_100409159
0x100409153  mov     dl, 2
0x100409155  jmp     short loc_100409159
0x100409157  xor     edx, edx; unsigned __int8
0x100409159  lea     rcx, [rdi-40h]; this
0x10040915d  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100409162  jmp     short loc_10040916E
0x100409164  mov     r15d, [rsp+0E8h+var_B4]
0x100409169  mov     [rsp+0E8h+var_B8], r15d
0x10040916e  mov     rcx, [rsp+0E8h+arg_8]
0x100409176  test    rcx, rcx
0x100409179  jz      short loc_100409188
0x10040917b  mov     rax, [rcx]
0x10040917e  mov     rax, [rax+10h]
0x100409182  call    cs:__guard_dispatch_icall_fptr
0x100409188  mov     eax, r15d
0x10040918b  lea     r11, [rsp+0E8h+var_18]
0x100409193  mov     rbx, [r11+20h]
0x100409197  mov     rsi, [r11+30h]
0x10040919b  mov     rsp, r11
0x10040919e  pop     r15
0x1004091a0  pop     r14
0x1004091a2  pop     rdi
0x1004091a3  retn
0x1004091a4  mov     ecx, 80070057h; int
0x1004091a9  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004091ae  mov     ecx, 80004005h; int
0x1004091b3  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004091b8  nop
0x1004091b9  int     3; Trap to Debugger
0x100424850  push    rbp
0x100424852  sub     rsp, 30h
0x100424856  mov     rbp, rdx
0x100424859  mov     [rbp+0C0h], rcx
0x100424860  mov     [rbp+88h], rcx
0x100424867  mov     rax, [rbp+88h]
0x10042486e  mov     rcx, [rax]
0x100424871  mov     [rbp+40h], rcx
0x100424875  mov     rax, [rbp+40h]
0x100424879  mov     eax, [rax]
0x10042487b  cmp     eax, 0C0000005h
0x100424880  jz      short loc_1004248B2
0x100424882  add     eax, 1FFFFFFFh
0x100424887  cmp     eax, 1
0x10042488a  ja      short loc_1004248A2
0x10042488c  mov     rax, [rbp+40h]
0x100424890  cmp     dword ptr [rax+18h], 1
0x100424894  jnz     short loc_1004248A2
0x100424896  mov     rax, [rbp+40h]
0x10042489a  mov     ecx, [rax+20h]
0x10042489d  mov     [rbp+34h], ecx
0x1004248a0  jmp     short loc_1004248A9
0x1004248a2  mov     dword ptr [rbp+34h], 8000FFFFh
0x1004248a9  mov     dword ptr [rbp+38h], 1
0x1004248b0  jmp     short loc_1004248B9
0x1004248b2  mov     dword ptr [rbp+38h], 0
0x1004248b9  mov     eax, [rbp+38h]
0x1004248bc  add     rsp, 30h
0x1004248c0  pop     rbp
0x1004248c1  retn
```
