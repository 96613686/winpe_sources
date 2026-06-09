# CTDCArr::VariantFromBSTR(tagVARIANT *,ushort *,CTDCColInfo *,ulong)

- ea: `0x18000d2b0`
- end: `0x18000d45b`
- name: `?VariantFromBSTR@CTDCArr@@AEAAJPEAUtagVARIANT@@PEAGPEAVCTDCColInfo@@K@Z`
- size: `427`
- prototype: `int(CTDCArr *__hidden this, struct tagVARIANT *, unsigned __int16 *, struct CTDCColInfo *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b190`
- `0x18000baa0`
- `0x18000c30c`

## callees

- `0x18000d2b0`
- `0x18000d5c0`
- `0x180014270`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d304`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d304`
- `OLEAUT32!__imp_VariantInit` at `0x18000d2d8`
- `OLEAUT32!__imp_VariantInit` at `0x18000d411`
- `OLEAUT32!__imp_VariantInit` at `0x18000d2d8`
- `OLEAUT32!__imp_VariantInit` at `0x18000d411`
- `OLEAUT32!__imp_VariantClear` at `0x18000d3d9`
- `OLEAUT32!__imp_VariantClear` at `0x18000d3d9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000d43a`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000d43a`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000d3e7`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18000d3e7`

## pseudocode

```c
__int64 __fastcall CTDCArr::VariantFromBSTR(
        CTDCArr *this,
        struct tagVARIANT *a2,
        unsigned __int16 *a3,
        struct CTDCColInfo *a4,
        LCID lcid)
{
  BSTR v8; // rax
  unsigned int v9; // ebx
  int v10; // r11d
  WORD v11; // di
  WORD v12; // si
  VARTYPE v13; // ax
  int v14; // r11d
  int v15; // r11d
  int v16; // r11d
  int v17; // r11d
  int v18; // r11d
  int v19; // r11d
  unsigned __int16 *v21; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG SystemTime; // [rsp+38h] [rbp-28h] BYREF

  VariantInit(a2);
  if ( *(_WORD *)a4 == 3 || *(_WORD *)a4 == 5 )
    goto LABEL_27;
  if ( *(_WORD *)a4 == 7 )
  {
    v10 = *((_DWORD *)a4 + 1);
    v9 = 0;
    *(_OWORD *)&SystemTime.vt = 0;
    if ( !v10 )
    {
LABEL_28:
      SystemTime.pRecInfo = 0;
      VariantInit(&SystemTime);
      SystemTime.llVal = (LONGLONG)a3;
      SystemTime.vt = 8;
      return (unsigned int)VariantChangeTypeEx(a2, &SystemTime, lcid, 0, *(_WORD *)a4);
    }
    v21 = a3;
    v11 = extract_num(&v21);
    v12 = extract_num(&v21);
    v13 = extract_num(&v21);
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( !v17 )
        {
          SystemTime.wReserved3 = v12;
          SystemTime.wReserved1 = v11;
          SystemTime.vt = v13;
          goto LABEL_24;
        }
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            if ( v19 == 1 )
            {
              SystemTime.wReserved3 = v12;
              SystemTime.wReserved1 = v13;
              SystemTime.vt = v11;
            }
            goto LABEL_24;
          }
          SystemTime.wReserved3 = v13;
          SystemTime.vt = v11;
          goto LABEL_23;
        }
        SystemTime.wReserved3 = v13;
        SystemTime.wReserved1 = v11;
      }
      else
      {
        SystemTime.wReserved3 = v11;
        SystemTime.wReserved1 = v13;
      }
      SystemTime.vt = v12;
      goto LABEL_24;
    }
    SystemTime.wReserved3 = v11;
    SystemTime.vt = v13;
LABEL_23:
    SystemTime.wReserved1 = v12;
LABEL_24:
    VariantClear(a2);
    if ( SystemTimeToVariantTime((LPSYSTEMTIME)&SystemTime, &a2->dblVal) )
      a2->vt = 7;
    else
      return (unsigned int)-2147221487;
    return v9;
  }
  if ( *(_WORD *)a4 != 8 )
  {
LABEL_27:
    *(_OWORD *)&SystemTime.vt = 0;
    goto LABEL_28;
  }
  v8 = SysAllocString(a3);
  v9 = 0;
  a2->llVal = (LONGLONG)v8;
  if ( !a3 || v8 )
    a2->vt = 8;
  else
    return (unsigned int)-2147024882;
  return v9;
}

```

## disassembly

```asm
0x18000d2b0  push    rbp
0x18000d2b2  push    rbx
0x18000d2b3  push    rsi
0x18000d2b4  push    rdi
0x18000d2b5  push    r14
0x18000d2b7  mov     rbp, rsp
0x18000d2ba  sub     rsp, 60h
0x18000d2be  mov     rax, cs:__security_cookie
0x18000d2c5  xor     rax, rsp
0x18000d2c8  mov     [rbp+var_10], rax
0x18000d2cc  mov     rcx, rdx; pvarg
0x18000d2cf  mov     rsi, r9
0x18000d2d2  mov     rdi, r8
0x18000d2d5  mov     r14, rdx
0x18000d2d8  call    cs:__imp_VariantInit
0x18000d2de  movzx   ecx, word ptr [rsi]
0x18000d2e1  sub     ecx, 3
0x18000d2e4  jz      loc_18000D400
0x18000d2ea  sub     ecx, 2
0x18000d2ed  jz      loc_18000D400
0x18000d2f3  sub     ecx, 2
0x18000d2f6  jz      short loc_18000D32F
0x18000d2f8  cmp     ecx, 1
0x18000d2fb  jnz     loc_18000D400
0x18000d301  mov     rcx, rdi; psz
0x18000d304  call    cs:__imp_SysAllocString
0x18000d30a  xor     ebx, ebx
0x18000d30c  mov     [r14+8], rax
0x18000d310  test    rdi, rdi
0x18000d313  jz      short loc_18000D324
0x18000d315  test    rax, rax
0x18000d318  jnz     short loc_18000D324
0x18000d31a  mov     ebx, 8007000Eh
0x18000d31f  jmp     loc_18000D442
0x18000d324  mov     word ptr [r14], 8
0x18000d32a  jmp     loc_18000D442
0x18000d32f  mov     r11d, [rsi+4]
0x18000d333  xor     ebx, ebx
0x18000d335  xorps   xmm0, xmm0
0x18000d338  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000d33c  test    r11d, r11d
0x18000d33f  jz      loc_18000D407
0x18000d345  lea     rcx, [rbp+var_30]
0x18000d349  mov     [rbp+var_30], rdi
0x18000d34d  call    extract_num
0x18000d352  lea     rcx, [rbp+var_30]
0x18000d356  mov     edi, eax
0x18000d358  call    extract_num
0x18000d35d  lea     rcx, [rbp+var_30]
0x18000d361  mov     esi, eax
0x18000d363  call    extract_num
0x18000d368  sub     r11d, 1
0x18000d36c  jz      short loc_18000D3CA
0x18000d36e  sub     r11d, 1
0x18000d372  jz      short loc_18000D3BC
0x18000d374  sub     r11d, 1
0x18000d378  jz      short loc_18000D3AE
0x18000d37a  sub     r11d, 1
0x18000d37e  jz      short loc_18000D3A4
0x18000d380  sub     r11d, 1
0x18000d384  jz      short loc_18000D39A
0x18000d386  cmp     r11d, 1
0x18000d38a  jnz     short loc_18000D3D6
0x18000d38c  mov     [rbp+SystemTime.wDay], si
0x18000d390  mov     [rbp+SystemTime.wMonth], ax
0x18000d394  mov     [rbp+SystemTime.wYear], di
0x18000d398  jmp     short loc_18000D3D6
0x18000d39a  mov     [rbp+SystemTime.wDay], ax
0x18000d39e  mov     [rbp+SystemTime.wYear], di
0x18000d3a2  jmp     short loc_18000D3D2
0x18000d3a4  mov     [rbp+SystemTime.wDay], ax
0x18000d3a8  mov     [rbp+SystemTime.wMonth], di
0x18000d3ac  jmp     short loc_18000D3C4
0x18000d3ae  mov     [rbp+SystemTime.wDay], si
0x18000d3b2  mov     [rbp+SystemTime.wMonth], di
0x18000d3b6  mov     [rbp+SystemTime.wYear], ax
0x18000d3ba  jmp     short loc_18000D3D6
0x18000d3bc  mov     [rbp+SystemTime.wDay], di
0x18000d3c0  mov     [rbp+SystemTime.wMonth], ax
0x18000d3c4  mov     [rbp+SystemTime.wYear], si
0x18000d3c8  jmp     short loc_18000D3D6
0x18000d3ca  mov     [rbp+SystemTime.wDay], di
0x18000d3ce  mov     [rbp+SystemTime.wYear], ax
0x18000d3d2  mov     [rbp+SystemTime.wMonth], si
0x18000d3d6  mov     rcx, r14; pvarg
0x18000d3d9  call    cs:__imp_VariantClear
0x18000d3df  lea     rdx, [r14+8]; pvtime
0x18000d3e3  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d3e7  call    cs:__imp_SystemTimeToVariantTime
0x18000d3ed  test    eax, eax
0x18000d3ef  jz      short loc_18000D3F9
0x18000d3f1  mov     word ptr [r14], 7
0x18000d3f7  jmp     short loc_18000D442
0x18000d3f9  mov     ebx, 80040011h
0x18000d3fe  jmp     short loc_18000D442
0x18000d400  xorps   xmm0, xmm0
0x18000d403  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000d407  xor     eax, eax
0x18000d409  lea     rcx, [rbp+SystemTime]; pvarg
0x18000d40d  mov     [rbp+var_18], rax
0x18000d411  call    cs:__imp_VariantInit
0x18000d417  mov     r8d, [rbp+lcid]; lcid
0x18000d41b  lea     rdx, [rbp+SystemTime]; pvarSrc
0x18000d41f  mov     eax, 8
0x18000d424  mov     qword ptr [rbp+SystemTime.wHour], rdi
0x18000d428  mov     [rbp+SystemTime.wYear], ax
0x18000d42c  xor     r9d, r9d; wFlags
0x18000d42f  movzx   eax, word ptr [rsi]
0x18000d432  mov     rcx, r14; pvargDest
0x18000d435  mov     [rsp+60h+vt], ax; vt
0x18000d43a  call    cs:__imp_VariantChangeTypeEx
0x18000d440  mov     ebx, eax
0x18000d442  mov     eax, ebx
0x18000d444  mov     rcx, [rbp+var_10]
0x18000d448  xor     rcx, rsp; StackCookie
0x18000d44b  call    __security_check_cookie
0x18000d450  add     rsp, 60h
0x18000d454  pop     r14
0x18000d456  pop     rdi
0x18000d457  pop     rsi
0x18000d458  pop     rbx
0x18000d459  pop     rbp
0x18000d45a  retn
```
