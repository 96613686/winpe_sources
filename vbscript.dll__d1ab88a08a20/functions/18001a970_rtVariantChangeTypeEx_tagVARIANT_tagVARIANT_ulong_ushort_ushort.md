# rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)

- ea: `0x18001a970`
- end: `0x18001ad8b`
- name: `?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z`
- size: `1051`
- prototype: `__int64 __usercall@<rax>(VARIANTARG *pvargDest@<rcx>, VARIANTARG *pvarSrc@<rdx>, unsigned int@<r8d>, unsigned __int16@<r9w>, unsigned __int16)`
- caller_count: `19`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002890`
- `0x1800162c0`
- `0x18001a260`
- `0x18001a350`
- `0x18001c028`
- `0x180023970`
- `0x180024010`
- `0x1800254d0`
- `0x180026b5c`
- `0x180031360`
- `0x180053d60`
- `0x18005f1bc`
- `0x18006a164`
- `0x18006aca0`
- `0x18006fe80`
- `0x180072b58`
- `0x18007335c`
- `0x180073530`
- `0x180077800`

## callees

- `0x180014b00`
- `0x180014c8c`
- `0x180017138`
- `0x18001a970`
- `0x1800439c8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001aaae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad01`
- `OLEAUT32!__imp_SysFreeString` at `0x18001aaae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001acd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad01`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aa44`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aa57`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ac92`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aca4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aa44`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aa57`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ac92`
- `OLEAUT32!__imp_SysStringLen` at `0x18001aca4`
- `OLEAUT32!__imp_VariantClear` at `0x18001aabd`
- `OLEAUT32!__imp_VariantClear` at `0x18001aae9`
- `OLEAUT32!__imp_VariantClear` at `0x18001ace3`
- `OLEAUT32!__imp_VariantClear` at `0x18001aabd`
- `OLEAUT32!__imp_VariantClear` at `0x18001aae9`
- `OLEAUT32!__imp_VariantClear` at `0x18001ace3`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001a9d9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ad46`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001a9d9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001ad46`
- `KERNEL32!CompareStringA` at `0x18001ac42`
- `KERNEL32!CompareStringA` at `0x18001ac42`
- `KERNEL32!CompareStringW` at `0x18001aa93`
- `KERNEL32!CompareStringW` at `0x18001aa93`
- `KERNEL32!WideCharToMultiByte` at `0x18001abcf`
- `KERNEL32!WideCharToMultiByte` at `0x18001ac0b`
- `KERNEL32!WideCharToMultiByte` at `0x18001abcf`
- `KERNEL32!WideCharToMultiByte` at `0x18001ac0b`
- `KERNEL32!SetLastError` at `0x18001ac58`
- `KERNEL32!SetLastError` at `0x18001ac58`

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
0x18001a970  mov     [rsp+arg_10], rbx
0x18001a975  push    rbp
0x18001a976  push    rsi
0x18001a977  push    rdi
0x18001a978  push    r14
0x18001a97a  push    r15
0x18001a97c  sub     rsp, 60h
0x18001a980  movzx   edi, word ptr [rsp+88h+cchCount1]
0x18001a988  mov     ebx, 8
0x18001a98d  movzx   r15d, r9w
0x18001a991  mov     ebp, r8d
0x18001a994  mov     rsi, rdx
0x18001a997  mov     r14, rcx
0x18001a99a  cmp     bx, di
0x18001a99d  jz      short loc_18001AA12
0x18001a99f  cmp     bx, [rdx]
0x18001a9a2  jz      short loc_18001AA12
0x18001a9a4  mov     eax, 0Bh
0x18001a9a9  mov     [rsp+88h+arg_0], r12
0x18001a9b1  mov     [rsp+88h+arg_8], r13
0x18001a9b9  cmp     ax, di
0x18001a9bc  jz      short loc_18001AA24
0x18001a9be  cmp     bx, di
0x18001a9c1  jz      loc_18001AADD
0x18001a9c7  movzx   r9d, r15w; wFlags
0x18001a9cb  mov     [rsp+88h+vt], di; vt
0x18001a9d0  mov     r8d, ebp; lcid
0x18001a9d3  mov     rdx, rsi; pvarSrc
0x18001a9d6  mov     rcx, r14; pvargDest
0x18001a9d9  call    cs:__imp_VariantChangeTypeEx
0x18001a9e0  nop     dword ptr [rax+rax+00h]
0x18001a9e5  test    eax, eax
0x18001a9e7  js      loc_18001AD17
0x18001a9ed  mov     r13, [rsp+88h+arg_8]
0x18001a9f5  mov     r12, [rsp+88h+arg_0]
0x18001a9fd  mov     rbx, [rsp+88h+arg_10]
0x18001aa05  add     rsp, 60h
0x18001aa09  pop     r15
0x18001aa0b  pop     r14
0x18001aa0d  pop     rdi
0x18001aa0e  pop     rsi
0x18001aa0f  pop     rbp
0x18001aa10  retn
0x18001aa12  cmp     r8d, 400h
0x18001aa19  jnz     short loc_18001A9A4
0x18001aa1b  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x18001aa20  mov     ebp, eax
0x18001aa22  jmp     short loc_18001A9A4
0x18001aa24  cmp     bx, [rsi]
0x18001aa27  jnz     short loc_18001A9C7
0x18001aa29  mov     edx, ebp; unsigned int
0x18001aa2b  mov     ecx, 7FFEh; int
0x18001aa30  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001aa35  mov     rbx, rax
0x18001aa38  test    rax, rax
0x18001aa3b  jz      loc_18001AC78
0x18001aa41  mov     rcx, rax; pbstr
0x18001aa44  call    cs:__imp_SysStringLen
0x18001aa4b  nop     dword ptr [rax+rax+00h]
0x18001aa50  mov     rcx, [rsi+8]; pbstr
0x18001aa54  mov     r13d, eax
0x18001aa57  call    cs:__imp_SysStringLen
0x18001aa5e  nop     dword ptr [rax+rax+00h]
0x18001aa63  cmp     cs:?g_fAnsiOs@@3HA, 0; int g_fAnsiOs
0x18001aa6a  mov     r12d, eax
0x18001aa6d  mov     rax, [rsi+8]
0x18001aa71  mov     [rsp+88h+lpWideCharStr], rax
0x18001aa76  jnz     loc_18001AB27
0x18001aa7c  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x18001aa81  mov     r9d, r12d; cchCount1
0x18001aa84  mov     r8, rax; lpString1
0x18001aa87  mov     qword ptr [rsp+88h+vt], rbx; lpString2
0x18001aa8c  mov     edx, 1; dwCmpFlags
0x18001aa91  mov     ecx, ebp; Locale
0x18001aa93  call    cs:__imp_CompareStringW
0x18001aa9a  nop     dword ptr [rax+rax+00h]
0x18001aa9f  xor     r12d, r12d
0x18001aaa2  cmp     eax, 2
0x18001aaa5  jnz     loc_18001AC67
0x18001aaab  mov     rcx, rbx; bstrString
0x18001aaae  call    cs:__imp_SysFreeString
0x18001aab5  nop     dword ptr [rax+rax+00h]
0x18001aaba  mov     rcx, r14; pvarg
0x18001aabd  call    cs:__imp_VariantClear
0x18001aac4  nop     dword ptr [rax+rax+00h]
0x18001aac9  xor     eax, eax
0x18001aacb  mov     word ptr [r14], 0Bh
0x18001aad1  mov     word ptr [r14+8], 0FFFFh
0x18001aad8  jmp     loc_18001A9ED
0x18001aadd  cmp     ax, [rsi]
0x18001aae0  jnz     loc_18001A9C7
0x18001aae6  mov     rcx, r14; pvarg
0x18001aae9  call    cs:__imp_VariantClear
0x18001aaf0  nop     dword ptr [rax+rax+00h]
0x18001aaf5  mov     [r14], bx
0x18001aaf9  mov     edx, ebp; unsigned int
0x18001aafb  xor     ebx, ebx
0x18001aafd  cmp     bx, [rsi+8]
0x18001ab01  mov     ecx, ebx
0x18001ab03  setz    cl
0x18001ab06  add     ecx, 7FFEh; int
0x18001ab0c  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ab11  test    rax, rax
0x18001ab14  mov     [r14+8], rax
0x18001ab18  mov     ecx, 800A0007h
0x18001ab1d  cmovz   ebx, ecx
0x18001ab20  mov     eax, ebx
0x18001ab22  jmp     loc_18001A9ED
0x18001ab27  test    r12d, r12d
0x18001ab2a  jz      loc_18001AC53
0x18001ab30  test    r13d, r13d
0x18001ab33  jz      loc_18001AC53
0x18001ab39  cmp     r12d, 0FFFFFFFFh
0x18001ab3d  jnz     short loc_18001AB51
0x18001ab3f  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18001ab46  inc     r12
0x18001ab49  cmp     word ptr [rax+r12*2], 0
0x18001ab4f  jnz     short loc_18001AB46
0x18001ab51  cmp     r13d, 0FFFFFFFFh
0x18001ab55  jnz     short loc_18001AB69
0x18001ab57  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001ab5e  inc     r13
0x18001ab61  cmp     word ptr [rbx+r13*2], 0
0x18001ab67  jnz     short loc_18001AB5E
0x18001ab69  lea     ecx, ds:0[r13*2]
0x18001ab71  lea     eax, [r12+r12]
0x18001ab75  mov     [rsp+88h+cbMultiByte], ecx
0x18001ab79  add     ecx, eax; unsigned int
0x18001ab7b  mov     [rsp+88h+cchCount1], eax
0x18001ab82  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x18001ab87  mov     [rsp+88h+lpString1], rax
0x18001ab8c  mov     rcx, rax
0x18001ab8f  test    rax, rax
0x18001ab92  jnz     short loc_18001AB9E
0x18001ab94  mov     ecx, 0Eh
0x18001ab99  jmp     loc_18001AC58
0x18001ab9e  movsxd  rdx, [rsp+88h+cchCount1]
0x18001aba6  mov     r9d, r12d; cchWideChar
0x18001aba9  mov     r8, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x18001abae  add     rax, rdx
0x18001abb1  mov     [rsp+88h+lpMultiByteStr], rax
0x18001abb6  xor     eax, eax
0x18001abb8  mov     [rsp+88h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18001abbd  mov     [rsp+88h+lpDefaultChar], rax; lpDefaultChar
0x18001abc2  mov     [rsp+88h+cchCount2], edx; cbMultiByte
0x18001abc6  xor     edx, edx; dwFlags
0x18001abc8  mov     qword ptr [rsp+88h+vt], rcx; lpMultiByteStr
0x18001abcd  xor     ecx, ecx; CodePage
0x18001abcf  call    cs:__imp_WideCharToMultiByte
0x18001abd6  nop     dword ptr [rax+rax+00h]
0x18001abdb  mov     ecx, [rsp+88h+cbMultiByte]
0x18001abdf  xor     r12d, r12d
0x18001abe2  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18001abe7  mov     r9d, r13d; cchWideChar
0x18001abea  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x18001abef  mov     r8, rbx; lpWideCharStr
0x18001abf2  mov     [rsp+88h+cchCount2], ecx; cbMultiByte
0x18001abf6  xor     edx, edx; dwFlags
0x18001abf8  mov     rcx, [rsp+88h+lpMultiByteStr]
0x18001abfd  mov     qword ptr [rsp+88h+vt], rcx; lpMultiByteStr
0x18001ac02  xor     ecx, ecx; CodePage
0x18001ac04  mov     [rsp+88h+cchCount1], eax
0x18001ac0b  call    cs:__imp_WideCharToMultiByte
0x18001ac12  nop     dword ptr [rax+rax+00h]
0x18001ac17  mov     r9d, [rsp+88h+cchCount1]; cchCount1
0x18001ac1f  test    r9d, r9d
0x18001ac22  jz      short loc_18001AC67
0x18001ac24  test    eax, eax
0x18001ac26  jz      short loc_18001AC67
0x18001ac28  mov     r8, [rsp+88h+lpString1]; lpString1
0x18001ac2d  mov     edx, 1; dwCmpFlags
0x18001ac32  mov     [rsp+88h+cchCount2], eax; cchCount2
0x18001ac36  mov     ecx, ebp; Locale
0x18001ac38  mov     rax, [rsp+88h+lpMultiByteStr]
0x18001ac3d  mov     qword ptr [rsp+88h+vt], rax; lpString2
0x18001ac42  call    cs:__imp_CompareStringA
0x18001ac49  nop     dword ptr [rax+rax+00h]
0x18001ac4e  jmp     loc_18001AAA2
0x18001ac53  mov     ecx, 57h ; 'W'; dwErrCode
0x18001ac58  call    cs:__imp_SetLastError
0x18001ac5f  nop     dword ptr [rax+rax+00h]
0x18001ac64  xor     r12d, r12d
0x18001ac67  mov     rcx, rbx; bstrString
0x18001ac6a  call    cs:__imp_SysFreeString
0x18001ac71  nop     dword ptr [rax+rax+00h]
0x18001ac76  jmp     short loc_18001AC7B
0x18001ac78  xor     r12d, r12d
0x18001ac7b  mov     edx, ebp; unsigned int
0x18001ac7d  mov     ecx, 7FFFh; int
0x18001ac82  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18001ac87  mov     r13, rax
0x18001ac8a  test    rax, rax
0x18001ac8d  jz      short loc_18001AD0D
0x18001ac8f  mov     rcx, rax; pbstr
0x18001ac92  call    cs:__imp_SysStringLen
0x18001ac99  nop     dword ptr [rax+rax+00h]
0x18001ac9e  mov     rcx, [rsi+8]; pbstr
0x18001aca2  mov     ebx, eax
0x18001aca4  call    cs:__imp_SysStringLen
0x18001acab  nop     dword ptr [rax+rax+00h]
0x18001acb0  mov     r8, [rsi+8]; unsigned __int16 *
0x18001acb4  mov     edx, 1; unsigned int
0x18001acb9  mov     r9d, eax; int
0x18001acbc  mov     [rsp+88h+cchCount2], ebx; int
0x18001acc0  mov     ecx, ebp; unsigned int
0x18001acc2  mov     qword ptr [rsp+88h+vt], r13; unsigned __int16 *
0x18001acc7  call    ?oCompareString@@YAHKKPEAGH0H@Z; oCompareString(ulong,ulong,ushort *,int,ushort *,int)
0x18001accc  mov     rcx, r13; bstrString
0x18001accf  cmp     eax, 2
0x18001acd2  jnz     short loc_18001AD01
0x18001acd4  call    cs:__imp_SysFreeString
0x18001acdb  nop     dword ptr [rax+rax+00h]
0x18001ace0  mov     rcx, r14; pvarg
0x18001ace3  call    cs:__imp_VariantClear
0x18001acea  nop     dword ptr [rax+rax+00h]
0x18001acef  xor     eax, eax
0x18001acf1  mov     word ptr [r14], 0Bh
0x18001acf7  mov     [r14+8], r12w
0x18001acfc  jmp     loc_18001A9ED
0x18001ad01  call    cs:__imp_SysFreeString
0x18001ad08  nop     dword ptr [rax+rax+00h]
0x18001ad0d  mov     ebx, 8
0x18001ad12  jmp     loc_18001A9C7
0x18001ad17  mov     r15d, 7
0x18001ad1d  cmp     r15w, di
0x18001ad21  jnz     loc_18001A9ED
0x18001ad27  cmp     bx, [rsi]
0x18001ad2a  jnz     loc_18001A9ED
0x18001ad30  mov     r9d, 2; wFlags
0x18001ad36  mov     [rsp+88h+vt], 5; vt
0x18001ad3d  mov     r8d, ebp; lcid
0x18001ad40  mov     rdx, rsi; pvarSrc
0x18001ad43  mov     rcx, r14; pvargDest
0x18001ad46  call    cs:__imp_VariantChangeTypeEx
0x18001ad4d  nop     dword ptr [rax+rax+00h]
0x18001ad52  test    eax, eax
0x18001ad54  js      loc_18001A9ED
0x18001ad5a  movsd   xmm1, qword ptr [r14+8]
0x18001ad60  comisd  xmm1, cs:?MaxDateR8@@3TIEEEdouble@@B; IEEEdouble const MaxDateR8
0x18001ad68  ja      short loc_18001AD81
0x18001ad6a  movsd   xmm0, cs:?MinDateR8@@3TIEEEdouble@@B; IEEEdouble const MinDateR8
0x18001ad72  comisd  xmm0, xmm1
0x18001ad76  ja      short loc_18001AD81
0x18001ad78  mov     [r14], r15w
0x18001ad7c  jmp     loc_18001A9ED
0x18001ad81  mov     eax, 800A000Dh
0x18001ad86  jmp     loc_18001A9ED
```
