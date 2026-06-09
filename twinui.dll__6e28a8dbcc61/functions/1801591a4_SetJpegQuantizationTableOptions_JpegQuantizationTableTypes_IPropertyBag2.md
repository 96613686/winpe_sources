# SetJpegQuantizationTableOptions(JpegQuantizationTableTypes,IPropertyBag2 *)

- ea: `0x1801591a4`
- end: `0x180159330`
- name: `?SetJpegQuantizationTableOptions@@YAJW4JpegQuantizationTableTypes@@PEAUIPropertyBag2@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180133490`

## callees

- `0x18013d330`
- `0x18013df8c`
- `0x1801591a4`
- `0x18015a76c`
- `0x1803a3010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180159221`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180159241`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180159221`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180159241`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180159300`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015930f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180159300`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015930f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180159272`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801592a6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180159272`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801592a6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180159292`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801592c6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180159292`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801592c6`

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
      memcpy_s_1(ppvData, v6, &dword_180407344, v8);
      v7 = SafeArrayUnaccessData(psa[1]);
      if ( v7 >= 0 )
      {
        v7 = SafeArrayAccessData(v17[0], &ppvData);
        if ( v7 >= 0 )
        {
          memcpy_s_1(ppvData, v9, &dword_180407444, v10);
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
0x1801591a4  push    rbp
0x1801591a6  push    rbx
0x1801591a7  push    rdi
0x1801591a8  push    r15
0x1801591aa  lea     rbp, [rsp-3Fh]
0x1801591af  sub     rsp, 0E8h
0x1801591b6  mov     rax, cs:__security_cookie
0x1801591bd  xor     rax, rsp
0x1801591c0  mov     [rbp+57h+var_30], rax
0x1801591c4  mov     rdi, rdx
0x1801591c7  lea     rcx, [rbp+57h+var_80]; void *
0x1801591cb  xor     edx, edx; Val
0x1801591cd  lea     r8d, [rdx+50h]; Size
0x1801591d1  call    memset_0
0x1801591d6  xorps   xmm0, xmm0
0x1801591d9  mov     qword ptr [rbp+57h+rgsabound.cElements], 40h ; '@'
0x1801591e1  mov     ecx, 3; vt
0x1801591e6  lea     rax, aLuminance; "Luminance"
0x1801591ed  mov     [rbp+57h+var_70], rax
0x1801591f1  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1801591f5  mov     r15d, 2003h
0x1801591fb  lea     rax, aChrominance; "Chrominance"
0x180159202  mov     [rbp+57h+var_7C], r15w
0x180159207  lea     ebx, [rcx-2]
0x18015920a  mov     [rbp+57h+var_48], rax
0x18015920e  mov     edx, ebx; cDims
0x180159210  mov     [rbp+57h+var_54], r15w
0x180159215  movups  xmmword ptr [rbp+57h+psa], xmm0
0x180159219  movups  [rbp+57h+var_A8], xmm0
0x18015921d  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180159221  call    cs:__imp_SafeArrayCreate
0x180159227  lea     ecx, [rbx+2]; vt
0x18015922a  mov     word ptr [rbp+57h+psa], r15w
0x18015922f  lea     r8, [rbp+57h+var_C0]; rgsabound
0x180159233  mov     [rbp+57h+psa+8], rax
0x180159237  mov     edx, ebx; cDims
0x180159239  mov     qword ptr [rbp+57h+var_C0.cElements], 40h ; '@'
0x180159241  call    cs:__imp_SafeArrayCreate
0x180159247  mov     rcx, [rbp+57h+psa+8]; psa
0x18015924b  mov     [rbp+57h+var_98], rax
0x18015924f  mov     word ptr [rbp+57h+var_A8+8], r15w
0x180159254  test    rcx, rcx
0x180159257  jz      loc_1801592F6
0x18015925d  test    rax, rax
0x180159260  jz      loc_1801592F6
0x180159266  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18015926a  mov     [rbp+57h+ppvData], 0
0x180159272  call    cs:__imp_SafeArrayAccessData
0x180159278  mov     ebx, eax
0x18015927a  test    eax, eax
0x18015927c  js      short loc_1801592F0
0x18015927e  mov     rcx, [rbp+57h+ppvData]; Destination
0x180159282  lea     r8, dword_180407344; Source
0x180159289  call    memcpy_s_1
0x18015928e  mov     rcx, [rbp+57h+psa+8]; psa
0x180159292  call    cs:__imp_SafeArrayUnaccessData
0x180159298  mov     ebx, eax
0x18015929a  test    eax, eax
0x18015929c  js      short loc_1801592F0
0x18015929e  mov     rcx, [rbp+57h+var_98]; psa
0x1801592a2  lea     rdx, [rbp+57h+ppvData]; ppvData
0x1801592a6  call    cs:__imp_SafeArrayAccessData
0x1801592ac  mov     ebx, eax
0x1801592ae  test    eax, eax
0x1801592b0  js      short loc_1801592F0
0x1801592b2  mov     rcx, [rbp+57h+ppvData]; Destination
0x1801592b6  lea     r8, dword_180407444; Source
0x1801592bd  call    memcpy_s_1
0x1801592c2  mov     rcx, [rbp+57h+var_98]; psa
0x1801592c6  call    cs:__imp_SafeArrayUnaccessData
0x1801592cc  mov     ebx, eax
0x1801592ce  test    eax, eax
0x1801592d0  js      short loc_1801592F0
0x1801592d2  mov     rax, [rdi]
0x1801592d5  lea     r9, [rbp+57h+psa]
0x1801592d9  lea     r8, [rbp+57h+var_80]
0x1801592dd  mov     edx, 2
0x1801592e2  mov     rcx, rdi
0x1801592e5  mov     rax, [rax+20h]
0x1801592e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801592ee  mov     ebx, eax
0x1801592f0  mov     rcx, [rbp+57h+psa+8]
0x1801592f4  jmp     short loc_1801592FB
0x1801592f6  mov     ebx, 8007000Eh
0x1801592fb  test    rcx, rcx
0x1801592fe  jz      short loc_180159306
0x180159300  call    cs:__imp_SafeArrayDestroy
0x180159306  mov     rcx, [rbp+57h+var_98]; psa
0x18015930a  test    rcx, rcx
0x18015930d  jz      short loc_180159315
0x18015930f  call    cs:__imp_SafeArrayDestroy
0x180159315  mov     eax, ebx
0x180159317  mov     rcx, [rbp+57h+var_30]
0x18015931b  xor     rcx, rsp; StackCookie
0x18015931e  call    __security_check_cookie
0x180159323  add     rsp, 0E8h
0x18015932a  pop     r15
0x18015932c  pop     rdi
0x18015932d  pop     rbx
0x18015932e  pop     rbp
0x18015932f  retn
```
