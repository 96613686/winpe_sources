# rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)

- ea: `0x18001b960`
- end: `0x18001bd0e`
- name: `?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z`
- size: `942`
- prototype: `__int64 __usercall@<rax>(VARIANTARG *pvargDest@<rcx>, VARIANTARG *pvarSrc@<rdx>, unsigned int@<r8d>, unsigned __int16@<r9w>, unsigned __int16)`
- caller_count: `19`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001f70`
- `0x180002600`
- `0x180004300`
- `0x18001b1a4`
- `0x18001b260`
- `0x18001b350`
- `0x18001c1f0`
- `0x18002055c`
- `0x18002c9c0`
- `0x180039ad0`
- `0x180052520`
- `0x18005d5f0`
- `0x1800680d0`
- `0x180068b70`
- `0x18006dc90`
- `0x1800706cc`
- `0x180070eb0`
- `0x180071070`
- `0x180074c30`

## callees

- `0x180019edc`
- `0x18001b104`
- `0x18001b960`
- `0x18001cf8c`
- `0x180042360`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ba85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc90`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ba85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc90`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ba2d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ba3a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bc39`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bc45`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ba2d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ba3a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bc39`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bc45`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba8e`
- `OLEAUT32!__imp_VariantClear` at `0x18001bab4`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc78`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba8e`
- `OLEAUT32!__imp_VariantClear` at `0x18001bab4`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc78`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001b9c9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001bccf`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001b9c9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001bccf`
- `KERNEL32!CompareStringA` at `0x18001bbfb`
- `KERNEL32!CompareStringA` at `0x18001bbfb`
- `KERNEL32!CompareStringW` at `0x18001ba70`
- `KERNEL32!CompareStringW` at `0x18001ba70`
- `KERNEL32!WideCharToMultiByte` at `0x18001bb94`
- `KERNEL32!WideCharToMultiByte` at `0x18001bbca`
- `KERNEL32!WideCharToMultiByte` at `0x18001bb94`
- `KERNEL32!WideCharToMultiByte` at `0x18001bbca`
- `KERNEL32!SetLastError` at `0x18001bc0b`
- `KERNEL32!SetLastError` at `0x18001bc0b`

## pseudocode

```c
HRESULT __fastcall rtVariantChangeTypeEx(
        VARIANTARG *pvargDest,
        VARIANTARG *pvarSrc,
        unsigned int a3,
        USHORT a4,
        VARTYPE cchCount1)
{
  unsigned int ConversionLocale; // ebp
  HRESULT result; // eax
  OLECHAR *ResourceString; // rax
  WCHAR *v12; // rbx
  __int64 cchCount2; // r13
  __int64 v14; // r12
  const WCHAR *bstrVal; // rax
  int v16; // eax
  int v17; // ebx
  unsigned __int16 *v18; // rax
  CHAR *v19; // rax
  DWORD v20; // ecx
  int v21; // eax
  OLECHAR *v22; // rax
  OLECHAR *v23; // r13
  UINT v24; // ebx
  UINT v25; // eax
  double dblVal; // xmm1_8
  CHAR *lpMultiByteStr; // [rsp+48h] [rbp-40h]
  const WCHAR *lpWideCharStr; // [rsp+50h] [rbp-38h]
  const CHAR *lpString1; // [rsp+58h] [rbp-30h]
  int cchCount1a; // [rsp+B0h] [rbp+28h]
  int cchCount1b; // [rsp+B0h] [rbp+28h]

  ConversionLocale = a3;
  if ( (cchCount1 == 8 || pvarSrc->vt == 8) && a3 == 1024 )
    ConversionLocale = COleScript::GetConversionLocale();
  if ( cchCount1 == 11 )
  {
    if ( pvarSrc->vt != 8 )
      goto LABEL_5;
    ResourceString = BstrGetResourceString(32766, ConversionLocale);
    v12 = ResourceString;
    if ( !ResourceString )
    {
LABEL_35:
      v22 = BstrGetResourceString(0x7FFF, ConversionLocale);
      v23 = v22;
      if ( v22 )
      {
        v24 = SysStringLen(v22);
        v25 = SysStringLen(pvarSrc->bstrVal);
        if ( oCompareString(ConversionLocale, 1u, pvarSrc->bstrVal, v25, v23, v24) == 2 )
        {
          SysFreeString(v23);
          VariantClear(pvargDest);
          result = 0;
          pvargDest->vt = 11;
          pvargDest->iVal = 0;
          return result;
        }
        SysFreeString(v23);
      }
      goto LABEL_5;
    }
    LODWORD(cchCount2) = SysStringLen(ResourceString);
    LODWORD(v14) = SysStringLen(pvarSrc->bstrVal);
    bstrVal = pvarSrc->bstrVal;
    lpWideCharStr = bstrVal;
    if ( !g_fAnsiOs )
    {
      v16 = CompareStringW(ConversionLocale, 1u, bstrVal, v14, v12, cchCount2);
      goto LABEL_13;
    }
    if ( (_DWORD)v14 && (_DWORD)cchCount2 )
    {
      if ( (_DWORD)v14 == -1 )
      {
        v14 = -1;
        do
          ++v14;
        while ( bstrVal[v14] );
      }
      if ( (_DWORD)cchCount2 == -1 )
      {
        cchCount2 = -1;
        do
          ++cchCount2;
        while ( v12[cchCount2] );
      }
      cchCount1a = 2 * v14;
      v19 = (CHAR *)MemAlloc(2 * (int)v14 + 2 * (int)cchCount2);
      lpString1 = v19;
      if ( v19 )
      {
        lpMultiByteStr = &v19[cchCount1a];
        cchCount1b = WideCharToMultiByte(0, 0, lpWideCharStr, v14, v19, cchCount1a, 0, 0);
        v21 = WideCharToMultiByte(0, 0, v12, cchCount2, lpMultiByteStr, 2 * cchCount2, 0, 0);
        if ( cchCount1b && v21 )
        {
          v16 = CompareStringA(ConversionLocale, 1u, lpString1, cchCount1b, lpMultiByteStr, v21);
LABEL_13:
          if ( v16 == 2 )
          {
            SysFreeString(v12);
            VariantClear(pvargDest);
            result = 0;
            pvargDest->vt = 11;
            pvargDest->iVal = -1;
            return result;
          }
        }
LABEL_34:
        SysFreeString(v12);
        goto LABEL_35;
      }
      v20 = 14;
    }
    else
    {
      v20 = 87;
    }
    SetLastError(v20);
    goto LABEL_34;
  }
  if ( cchCount1 == 8 && pvarSrc->vt == 11 )
  {
    VariantClear(pvargDest);
    pvargDest->vt = 8;
    v17 = 0;
    v18 = BstrGetResourceString((unsigned int)(pvarSrc->iVal == 0) + 32766, ConversionLocale);
    pvargDest->llVal = (LONGLONG)v18;
    if ( !v18 )
      return -2146828281;
    return v17;
  }
LABEL_5:
  result = VariantChangeTypeEx(pvargDest, pvarSrc, ConversionLocale, a4, cchCount1);
  if ( result < 0 && cchCount1 == 7 && pvarSrc->vt == 8 )
  {
    result = VariantChangeTypeEx(pvargDest, pvarSrc, ConversionLocale, 2u, 5u);
    if ( result >= 0 )
    {
      dblVal = pvargDest->dblVal;
      if ( dblVal > 2958466.0 || dblVal < -657434.9999999999 )
        return -2146828275;
      else
        pvargDest->vt = 7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b960  mov     [rsp+arg_10], rbx
0x18001b965  push    rbp
0x18001b966  push    rsi
0x18001b967  push    rdi
0x18001b968  push    r14
0x18001b96a  push    r15
0x18001b96c  sub     rsp, 60h
0x18001b970  movzx   edi, word ptr [rsp+88h+cchCount1]
0x18001b978  mov     ebx, 8
0x18001b97d  movzx   r15d, r9w
0x18001b981  mov     ebp, r8d
0x18001b984  mov     rsi, rdx
0x18001b987  mov     r14, rcx
0x18001b98a  cmp     bx, di
0x18001b98d  jz      short loc_18001B9FB
0x18001b98f  cmp     bx, [rdx]
0x18001b992  jz      short loc_18001B9FB
0x18001b994  mov     eax, 0Bh
0x18001b999  mov     [rsp+88h+arg_0], r12
0x18001b9a1  mov     [rsp+88h+arg_8], r13
0x18001b9a9  cmp     ax, di
0x18001b9ac  jz      short loc_18001BA0D
0x18001b9ae  cmp     bx, di
0x18001b9b1  jz      loc_18001BAA8
0x18001b9b7  movzx   r9d, r15w; wFlags
0x18001b9bb  mov     [rsp+88h+vt], di; vt
0x18001b9c0  mov     r8d, ebp; lcid
0x18001b9c3  mov     rdx, rsi; pvarSrc
0x18001b9c6  mov     rcx, r14; pvargDest
0x18001b9c9  call    cs:__imp_VariantChangeTypeEx
0x18001b9cf  test    eax, eax
0x18001b9d1  js      loc_18001BCA0
0x18001b9d7  mov     r13, [rsp+88h+arg_8]
0x18001b9df  mov     r12, [rsp+88h+arg_0]
0x18001b9e7  mov     rbx, [rsp+88h+arg_10]
0x18001b9ef  add     rsp, 60h
0x18001b9f3  pop     r15
0x18001b9f5  pop     r14
0x18001b9f7  pop     rdi
0x18001b9f8  pop     rsi
0x18001b9f9  pop     rbp
0x18001b9fa  retn
0x18001b9fb  cmp     r8d, 400h
0x18001ba02  jnz     short loc_18001B994
0x18001ba04  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18001ba09  mov     ebp, eax
0x18001ba0b  jmp     short loc_18001B994
0x18001ba0d  cmp     bx, [rsi]
0x18001ba10  jnz     short loc_18001B9B7
0x18001ba12  mov     edx, ebp; unsigned int
0x18001ba14  mov     ecx, 7FFEh; int
0x18001ba19  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ba1e  mov     rbx, rax
0x18001ba21  test    rax, rax
0x18001ba24  jz      loc_18001BC1F
0x18001ba2a  mov     rcx, rax; pbstr
0x18001ba2d  call    cs:__imp_SysStringLen
0x18001ba33  mov     rcx, [rsi+8]; pbstr
0x18001ba37  mov     r13d, eax
0x18001ba3a  call    cs:__imp_SysStringLen
0x18001ba40  cmp     cs:?g_fAnsiOs@@3HA, 0; int g_fAnsiOs
0x18001ba47  mov     r12d, eax
0x18001ba4a  mov     rax, [rsi+8]
0x18001ba4e  mov     [rsp+88h+lpWideCharStr], rax
0x18001ba53  jnz     loc_18001BAEC
0x18001ba59  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x18001ba5e  mov     r9d, r12d; cchCount1
0x18001ba61  mov     r8, rax; lpString1
0x18001ba64  mov     qword ptr [rsp+88h+vt], rbx; lpString2
0x18001ba69  mov     edx, 1; dwCmpFlags
0x18001ba6e  mov     ecx, ebp; Locale
0x18001ba70  call    cs:__imp_CompareStringW
0x18001ba76  xor     r12d, r12d
0x18001ba79  cmp     eax, 2
0x18001ba7c  jnz     loc_18001BC14
0x18001ba82  mov     rcx, rbx; bstrString
0x18001ba85  call    cs:__imp_SysFreeString
0x18001ba8b  mov     rcx, r14; pvarg
0x18001ba8e  call    cs:__imp_VariantClear
0x18001ba94  xor     eax, eax
0x18001ba96  mov     word ptr [r14], 0Bh
0x18001ba9c  mov     word ptr [r14+8], 0FFFFh
0x18001baa3  jmp     loc_18001B9D7
0x18001baa8  cmp     ax, [rsi]
0x18001baab  jnz     loc_18001B9B7
0x18001bab1  mov     rcx, r14; pvarg
0x18001bab4  call    cs:__imp_VariantClear
0x18001baba  mov     [r14], bx
0x18001babe  mov     edx, ebp; unsigned int
0x18001bac0  xor     ebx, ebx
0x18001bac2  cmp     bx, [rsi+8]
0x18001bac6  mov     ecx, ebx
0x18001bac8  setz    cl
0x18001bacb  add     ecx, 7FFEh; int
0x18001bad1  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001bad6  test    rax, rax
0x18001bad9  mov     [r14+8], rax
0x18001badd  mov     ecx, 800A0007h
0x18001bae2  cmovz   ebx, ecx
0x18001bae5  mov     eax, ebx
0x18001bae7  jmp     loc_18001B9D7
0x18001baec  test    r12d, r12d
0x18001baef  jz      loc_18001BC06
0x18001baf5  test    r13d, r13d
0x18001baf8  jz      loc_18001BC06
0x18001bafe  cmp     r12d, 0FFFFFFFFh
0x18001bb02  jnz     short loc_18001BB16
0x18001bb04  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18001bb0b  inc     r12
0x18001bb0e  cmp     word ptr [rax+r12*2], 0
0x18001bb14  jnz     short loc_18001BB0B
0x18001bb16  cmp     r13d, 0FFFFFFFFh
0x18001bb1a  jnz     short loc_18001BB2E
0x18001bb1c  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001bb23  inc     r13
0x18001bb26  cmp     word ptr [rbx+r13*2], 0
0x18001bb2c  jnz     short loc_18001BB23
0x18001bb2e  lea     ecx, ds:0[r13*2]
0x18001bb36  lea     eax, [r12+r12]
0x18001bb3a  mov     [rsp+88h+cbMultiByte], ecx
0x18001bb3e  add     ecx, eax; unsigned int
0x18001bb40  mov     [rsp+88h+cchCount1], eax
0x18001bb47  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x18001bb4c  mov     [rsp+88h+lpString1], rax
0x18001bb51  mov     rcx, rax
0x18001bb54  test    rax, rax
0x18001bb57  jnz     short loc_18001BB63
0x18001bb59  mov     ecx, 0Eh
0x18001bb5e  jmp     loc_18001BC0B
0x18001bb63  movsxd  rdx, [rsp+88h+cchCount1]
0x18001bb6b  mov     r9d, r12d; cchWideChar
0x18001bb6e  mov     r8, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x18001bb73  add     rax, rdx
0x18001bb76  mov     [rsp+88h+lpMultiByteStr], rax
0x18001bb7b  xor     eax, eax
0x18001bb7d  mov     [rsp+88h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18001bb82  mov     [rsp+88h+lpDefaultChar], rax; lpDefaultChar
0x18001bb87  mov     [rsp+88h+cchCount2], edx; cbMultiByte
0x18001bb8b  xor     edx, edx; dwFlags
0x18001bb8d  mov     qword ptr [rsp+88h+vt], rcx; lpMultiByteStr
0x18001bb92  xor     ecx, ecx; CodePage
0x18001bb94  call    cs:__imp_WideCharToMultiByte
0x18001bb9a  mov     ecx, [rsp+88h+cbMultiByte]
0x18001bb9e  xor     r12d, r12d
0x18001bba1  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18001bba6  mov     r9d, r13d; cchWideChar
0x18001bba9  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x18001bbae  mov     r8, rbx; lpWideCharStr
0x18001bbb1  mov     [rsp+88h+cchCount2], ecx; cbMultiByte
0x18001bbb5  xor     edx, edx; dwFlags
0x18001bbb7  mov     rcx, [rsp+88h+lpMultiByteStr]
0x18001bbbc  mov     qword ptr [rsp+88h+vt], rcx; lpMultiByteStr
0x18001bbc1  xor     ecx, ecx; CodePage
0x18001bbc3  mov     [rsp+88h+cchCount1], eax
0x18001bbca  call    cs:__imp_WideCharToMultiByte
0x18001bbd0  mov     r9d, [rsp+88h+cchCount1]; cchCount1
0x18001bbd8  test    r9d, r9d
0x18001bbdb  jz      short loc_18001BC14
0x18001bbdd  test    eax, eax
0x18001bbdf  jz      short loc_18001BC14
0x18001bbe1  mov     r8, [rsp+88h+lpString1]; lpString1
0x18001bbe6  mov     edx, 1; dwCmpFlags
0x18001bbeb  mov     [rsp+88h+cchCount2], eax; cchCount2
0x18001bbef  mov     ecx, ebp; Locale
0x18001bbf1  mov     rax, [rsp+88h+lpMultiByteStr]
0x18001bbf6  mov     qword ptr [rsp+88h+vt], rax; lpString2
0x18001bbfb  call    cs:__imp_CompareStringA
0x18001bc01  jmp     loc_18001BA79
0x18001bc06  mov     ecx, 57h ; 'W'; dwErrCode
0x18001bc0b  call    cs:__imp_SetLastError
0x18001bc11  xor     r12d, r12d
0x18001bc14  mov     rcx, rbx; bstrString
0x18001bc17  call    cs:__imp_SysFreeString
0x18001bc1d  jmp     short loc_18001BC22
0x18001bc1f  xor     r12d, r12d
0x18001bc22  mov     edx, ebp; unsigned int
0x18001bc24  mov     ecx, 7FFFh; int
0x18001bc29  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001bc2e  mov     r13, rax
0x18001bc31  test    rax, rax
0x18001bc34  jz      short loc_18001BC96
0x18001bc36  mov     rcx, rax; pbstr
0x18001bc39  call    cs:__imp_SysStringLen
0x18001bc3f  mov     rcx, [rsi+8]; pbstr
0x18001bc43  mov     ebx, eax
0x18001bc45  call    cs:__imp_SysStringLen
0x18001bc4b  mov     r8, [rsi+8]; unsigned __int16 *
0x18001bc4f  mov     edx, 1; unsigned int
0x18001bc54  mov     r9d, eax; int
0x18001bc57  mov     [rsp+88h+cchCount2], ebx; int
0x18001bc5b  mov     ecx, ebp; unsigned int
0x18001bc5d  mov     qword ptr [rsp+88h+vt], r13; unsigned __int16 *
0x18001bc62  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001bc67  mov     rcx, r13; bstrString
0x18001bc6a  cmp     eax, 2
0x18001bc6d  jnz     short loc_18001BC90
0x18001bc6f  call    cs:__imp_SysFreeString
0x18001bc75  mov     rcx, r14; pvarg
0x18001bc78  call    cs:__imp_VariantClear
0x18001bc7e  xor     eax, eax
0x18001bc80  mov     word ptr [r14], 0Bh
0x18001bc86  mov     [r14+8], r12w
0x18001bc8b  jmp     loc_18001B9D7
0x18001bc90  call    cs:__imp_SysFreeString
0x18001bc96  mov     ebx, 8
0x18001bc9b  jmp     loc_18001B9B7
0x18001bca0  mov     r15d, 7
0x18001bca6  cmp     r15w, di
0x18001bcaa  jnz     loc_18001B9D7
0x18001bcb0  cmp     bx, [rsi]
0x18001bcb3  jnz     loc_18001B9D7
0x18001bcb9  mov     r9d, 2; wFlags
0x18001bcbf  mov     [rsp+88h+vt], 5; vt
0x18001bcc6  mov     r8d, ebp; lcid
0x18001bcc9  mov     rdx, rsi; pvarSrc
0x18001bccc  mov     rcx, r14; pvargDest
0x18001bccf  call    cs:__imp_VariantChangeTypeEx
0x18001bcd5  test    eax, eax
0x18001bcd7  js      loc_18001B9D7
0x18001bcdd  movsd   xmm1, qword ptr [r14+8]
0x18001bce3  comisd  xmm1, cs:?MaxDateR8@@3TIEEEdouble@@B; IEEEdouble const MaxDateR8
0x18001bceb  ja      short loc_18001BD04
0x18001bced  movsd   xmm0, cs:?MinDateR8@@3TIEEEdouble@@B; IEEEdouble const MinDateR8
0x18001bcf5  comisd  xmm0, xmm1
0x18001bcf9  ja      short loc_18001BD04
0x18001bcfb  mov     [r14], r15w
0x18001bcff  jmp     loc_18001B9D7
0x18001bd04  mov     eax, 800A000Dh
0x18001bd09  jmp     loc_18001B9D7
```
