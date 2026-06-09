# SetJpegQuantizationTableOptions(JpegQuantizationTableTypes,IPropertyBag2 *)

- ea: `0x1800059a8`
- end: `0x180005b34`
- name: `?SetJpegQuantizationTableOptions@@YAJW4JpegQuantizationTableTypes@@PEAUIPropertyBag2@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800067ec`

## callees

- `0x1800059a8`
- `0x180005b3c`
- `0x180035830`
- `0x1800364ac`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005a25`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005a45`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005a25`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005a45`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005afd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005b0c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005afd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180005b0c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005a76`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005aaa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005a76`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005aaa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005a96`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005aca`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005a96`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005aca`

## pseudocode

```c
__int64 __fastcall SetJpegQuantizationTableOptions(__int64 a1, __int64 a2)
{
  SAFEARRAY *v3; // rax
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rcx
  rsize_t v6; // rdx
  HRESULT v7; // ebx
  rsize_t v8; // r9
  rsize_t v9; // rdx
  rsize_t v10; // r9
  void *ppvData; // [rsp+30h] [rbp-79h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-71h] BYREF
  SAFEARRAYBOUND v14; // [rsp+40h] [rbp-69h] BYREF
  SAFEARRAY *psa[2]; // [rsp+48h] [rbp-61h] BYREF
  __int128 v16; // [rsp+58h] [rbp-51h]
  SAFEARRAY *v17[2]; // [rsp+68h] [rbp-41h]
  _BYTE v18[4]; // [rsp+80h] [rbp-29h] BYREF
  __int16 v19; // [rsp+84h] [rbp-25h]
  const wchar_t *v20; // [rsp+90h] [rbp-19h]
  __int16 v21; // [rsp+ACh] [rbp+3h]
  const wchar_t *v22; // [rsp+B8h] [rbp+Fh]

  memset_0(v18, 0, 0x50u);
  rgsabound = (SAFEARRAYBOUND)64LL;
  v20 = L"Luminance";
  v19 = 8195;
  v22 = L"Chrominance";
  v21 = 8195;
  *(_OWORD *)psa = 0;
  v16 = 0;
  *(_OWORD *)v17 = 0;
  v3 = SafeArrayCreate(3u, 1u, &rgsabound);
  LOWORD(psa[0]) = 8195;
  psa[1] = v3;
  v14 = (SAFEARRAYBOUND)64LL;
  v4 = SafeArrayCreate(3u, 1u, &v14);
  v5 = psa[1];
  v17[0] = v4;
  WORD4(v16) = 8195;
  if ( psa[1] && v4 )
  {
    ppvData = 0;
    v7 = SafeArrayAccessData(psa[1], &ppvData);
    if ( v7 >= 0 )
    {
      memcpy_s(ppvData, v6, &unk_18004E2C4, v8);
      v7 = SafeArrayUnaccessData(psa[1]);
      if ( v7 >= 0 )
      {
        v7 = SafeArrayAccessData(v17[0], &ppvData);
        if ( v7 >= 0 )
        {
          memcpy_s(ppvData, v9, &unk_18004E3C4, v10);
          v7 = SafeArrayUnaccessData(v17[0]);
          if ( v7 >= 0 )
            v7 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, SAFEARRAY **))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   2,
                   v18,
                   psa);
        }
      }
    }
    v5 = psa[1];
  }
  else
  {
    v7 = -2147024882;
  }
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( v17[0] )
    SafeArrayDestroy(v17[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800059a8  push    rbp
0x1800059aa  push    rbx
0x1800059ab  push    rdi
0x1800059ac  push    r15
0x1800059ae  lea     rbp, [rsp-3Fh]
0x1800059b3  sub     rsp, 0E8h
0x1800059ba  mov     rax, cs:__security_cookie
0x1800059c1  xor     rax, rsp
0x1800059c4  mov     [rbp+57h+var_30], rax
0x1800059c8  mov     rdi, rdx
0x1800059cb  lea     rcx, [rbp+57h+var_80]; void *
0x1800059cf  xor     edx, edx; Val
0x1800059d1  lea     r8d, [rdx+50h]; Size
0x1800059d5  call    memset_0
0x1800059da  xorps   xmm0, xmm0
0x1800059dd  mov     qword ptr [rbp+57h+rgsabound.cElements], 40h ; '@'
0x1800059e5  mov     ecx, 3; vt
0x1800059ea  lea     rax, aLuminance; "Luminance"
0x1800059f1  mov     [rbp+57h+var_70], rax
0x1800059f5  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800059f9  mov     r15d, 2003h
0x1800059ff  lea     rax, aChrominance; "Chrominance"
0x180005a06  mov     [rbp+57h+var_7C], r15w
0x180005a0b  lea     ebx, [rcx-2]
0x180005a0e  mov     [rbp+57h+var_48], rax
0x180005a12  mov     edx, ebx; cDims
0x180005a14  mov     [rbp+57h+var_54], r15w
0x180005a19  movups  xmmword ptr [rbp+57h+psa], xmm0
0x180005a1d  movups  [rbp+57h+var_A8], xmm0
0x180005a21  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180005a25  call    cs:__imp_SafeArrayCreate
0x180005a2b  lea     ecx, [rbx+2]; vt
0x180005a2e  mov     word ptr [rbp+57h+psa], r15w
0x180005a33  lea     r8, [rbp+57h+var_C0]; rgsabound
0x180005a37  mov     [rbp+57h+psa+8], rax
0x180005a3b  mov     edx, ebx; cDims
0x180005a3d  mov     qword ptr [rbp+57h+var_C0.cElements], 40h ; '@'
0x180005a45  call    cs:__imp_SafeArrayCreate
0x180005a4b  mov     rcx, [rbp+57h+psa+8]; psa
0x180005a4f  mov     [rbp+57h+var_98], rax
0x180005a53  mov     word ptr [rbp+57h+var_A8+8], r15w
0x180005a58  test    rcx, rcx
0x180005a5b  jz      loc_180005B2D
0x180005a61  test    rax, rax
0x180005a64  jz      loc_180005B2D
0x180005a6a  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180005a6e  mov     [rbp+57h+ppvData], 0
0x180005a76  call    cs:__imp_SafeArrayAccessData
0x180005a7c  mov     ebx, eax
0x180005a7e  test    eax, eax
0x180005a80  js      short loc_180005AF4
0x180005a82  mov     rcx, [rbp+57h+ppvData]; Destination
0x180005a86  lea     r8, unk_18004E2C4; Source
0x180005a8d  call    memcpy_s
0x180005a92  mov     rcx, [rbp+57h+psa+8]; psa
0x180005a96  call    cs:__imp_SafeArrayUnaccessData
0x180005a9c  mov     ebx, eax
0x180005a9e  test    eax, eax
0x180005aa0  js      short loc_180005AF4
0x180005aa2  mov     rcx, [rbp+57h+var_98]; psa
0x180005aa6  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180005aaa  call    cs:__imp_SafeArrayAccessData
0x180005ab0  mov     ebx, eax
0x180005ab2  test    eax, eax
0x180005ab4  js      short loc_180005AF4
0x180005ab6  mov     rcx, [rbp+57h+ppvData]; Destination
0x180005aba  lea     r8, unk_18004E3C4; Source
0x180005ac1  call    memcpy_s
0x180005ac6  mov     rcx, [rbp+57h+var_98]; psa
0x180005aca  call    cs:__imp_SafeArrayUnaccessData
0x180005ad0  mov     ebx, eax
0x180005ad2  test    eax, eax
0x180005ad4  js      short loc_180005AF4
0x180005ad6  mov     rax, [rdi]
0x180005ad9  lea     r9, [rbp+57h+psa]
0x180005add  lea     r8, [rbp+57h+var_80]
0x180005ae1  mov     edx, 2
0x180005ae6  mov     rcx, rdi
0x180005ae9  mov     rax, [rax+20h]
0x180005aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af2  mov     ebx, eax
0x180005af4  mov     rcx, [rbp+57h+psa+8]; psa
0x180005af8  test    rcx, rcx
0x180005afb  jz      short loc_180005B03
0x180005afd  call    cs:__imp_SafeArrayDestroy
0x180005b03  mov     rcx, [rbp+57h+var_98]; psa
0x180005b07  test    rcx, rcx
0x180005b0a  jz      short loc_180005B12
0x180005b0c  call    cs:__imp_SafeArrayDestroy
0x180005b12  mov     eax, ebx
0x180005b14  mov     rcx, [rbp+57h+var_30]
0x180005b18  xor     rcx, rsp; StackCookie
0x180005b1b  call    __security_check_cookie
0x180005b20  add     rsp, 0E8h
0x180005b27  pop     r15
0x180005b29  pop     rdi
0x180005b2a  pop     rbx
0x180005b2b  pop     rbp
0x180005b2c  retn
0x180005b2d  mov     ebx, 8007000Eh
0x180005b32  jmp     short loc_180005AF8
```
