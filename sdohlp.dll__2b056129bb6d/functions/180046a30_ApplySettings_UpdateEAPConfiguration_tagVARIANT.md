# ApplySettings::UpdateEAPConfiguration(tagVARIANT &)

- ea: `0x180046a30`
- end: `0x180046de7`
- name: `?UpdateEAPConfiguration@ApplySettings@@AEAAJAEAUtagVARIANT@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(ApplySettings *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18004520c`

## callees

- `0x18002f240`
- `0x180046a30`
- `0x180047e34`
- `0x180055030`

## import_xrefs

- `msvcrt!wcstol` at `0x180046aeb`
- `msvcrt!wcstol` at `0x180046b6d`
- `msvcrt!wcstol` at `0x180046d25`
- `msvcrt!wcstol` at `0x180046aeb`
- `msvcrt!wcstol` at `0x180046b6d`
- `msvcrt!wcstol` at `0x180046d25`
- `KERNEL32!LocalFree` at `0x180046bb1`
- `KERNEL32!LocalFree` at `0x180046c4f`
- `KERNEL32!LocalFree` at `0x180046d8f`
- `KERNEL32!LocalFree` at `0x180046bb1`
- `KERNEL32!LocalFree` at `0x180046c4f`
- `KERNEL32!LocalFree` at `0x180046d8f`
- `KERNEL32!LocalAlloc` at `0x180046b1f`
- `KERNEL32!LocalAlloc` at `0x180046b1f`
- `OLEAUT32!__imp_VariantInit` at `0x180046ac2`
- `OLEAUT32!__imp_VariantInit` at `0x180046ac2`
- `OLEAUT32!__imp_VariantClear` at `0x180046db6`
- `OLEAUT32!__imp_VariantClear` at `0x180046db6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180046a86`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180046a86`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180046d9d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180046d9d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046d5f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046d5f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046bcd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046c80`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046bcd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046c80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplySettings::UpdateEAPConfiguration(ApplySettings *this, struct tagVARIANT *a2)
{
  ApplySettings *v2; // r14
  LONGLONG llVal; // rax
  __int64 v4; // rsi
  __int64 v5; // rdi
  SAFEARRAY *v6; // r13
  int v8; // ebx
  __int64 v9; // rax
  wchar_t *v10; // r12
  unsigned __int8 v11; // r15
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned __int8 *v15; // rdi
  int v16; // r14d
  unsigned __int64 i; // rbx
  unsigned __int64 v18; // rcx
  unsigned int v19; // esi
  SAFEARRAY *Vector; // rax
  LONGLONG v21; // rdi
  int v22; // r9d
  unsigned int j; // edx
  __int64 k; // r8
  unsigned int v25; // r10d
  _BYTE *m; // rcx
  LONG *v27; // rdx
  SAFEARRAY *v28; // rax
  LONGLONG v29; // r14
  int v30; // edi
  unsigned int n; // edx
  unsigned __int64 v32; // rax
  __int64 ii; // r8
  unsigned __int64 jj; // rsi
  unsigned __int64 v35; // rax
  VARIANTARG *v36; // rsi
  unsigned int v37; // [rsp+30h] [rbp-59h] BYREF
  LONG v38; // [rsp+34h] [rbp-55h]
  HLOCAL hMem; // [rsp+38h] [rbp-51h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v41[2]; // [rsp+48h] [rbp-41h] BYREF
  LONG rgIndices[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v43; // [rsp+58h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-29h] BYREF
  __int64 v45; // [rsp+78h] [rbp-11h]
  ApplySettings *v46; // [rsp+80h] [rbp-9h]
  VARIANTARG *v47; // [rsp+88h] [rbp-1h]
  wchar_t String; // [rsp+90h] [rbp+7h] BYREF
  wchar_t v49; // [rsp+92h] [rbp+9h]
  __int16 v50; // [rsp+94h] [rbp+Bh]

  v47 = a2;
  v2 = this;
  v46 = this;
  llVal = a2->llVal;
  v4 = *(_QWORD *)(llVal + 16);
  v43 = v4;
  v5 = *(unsigned int *)(llVal + 24);
  rgsabound.cElements = *(_DWORD *)(llVal + 24);
  rgsabound.lLbound = 0;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( !v6 )
    return 2147942414LL;
  v8 = 0;
  v9 = v4 + 24 * v5;
  v45 = v9;
  v38 = 0;
  while ( v4 != v9 )
  {
    v10 = *(wchar_t **)(v4 + 8);
    VariantInit(&pvarg);
    String = *v10;
    v49 = v10[1];
    v50 = 0;
    v11 = wcstol(&String, 0, 16);
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    v13 = v12 >> 1;
    if ( *((_BYTE *)v2 + 148) )
    {
      v14 = v13 - 8;
      v15 = (unsigned __int8 *)LocalAlloc(0x40u, (unsigned int)(v13 - 8));
      if ( !v15 )
        goto LABEL_38;
      v16 = 0;
      for ( i = 16; ; i += 2LL )
      {
        v18 = -1;
        do
          ++v18;
        while ( v10[v18] );
        if ( i >= v18 )
          break;
        String = v10[i];
        v49 = v10[i + 1];
        v50 = 0;
        v15[v16++] = wcstol(&String, 0, 16);
      }
      v37 = 0;
      hMem = 0;
      v8 = MigrateEAPBlob(v11, 0, v15, v14, (unsigned __int8 **)&hMem, &v37);
      LocalFree(v15);
      if ( v8 < 0 )
        goto LABEL_39;
      v19 = v37;
      Vector = SafeArrayCreateVector(0x11u, 0, v37 + 20);
      v21 = (LONGLONG)Vector;
      if ( !Vector )
      {
        LocalFree(hMem);
LABEL_38:
        v8 = -2147024882;
LABEL_39:
        SafeArrayDestroy(v6);
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        return (unsigned int)v8;
      }
      *(_BYTE *)Vector->pvData = v11;
      v22 = 1;
      for ( j = 0; j < 0xF; ++j )
        *((_BYTE *)Vector->pvData + v22++) = 0;
      v37 = v19;
      for ( k = 0; k != 4; ++k )
        *((_BYTE *)Vector->pvData + v22++) = *((_BYTE *)&v37 + k);
      v25 = 0;
      for ( m = hMem; v25 < v19; ++v25 )
        *((_BYTE *)Vector->pvData + v22++) = m[v25];
      LocalFree(m);
      pvarg.llVal = v21;
      pvarg.vt = 8209;
      v41[1] = 0;
      v41[0] = v38;
      v27 = v41;
    }
    else
    {
      v28 = SafeArrayCreateVector(0x11u, 0, (int)v13 + 12);
      v29 = (LONGLONG)v28;
      if ( !v28 )
        goto LABEL_38;
      *(_BYTE *)v28->pvData = v11;
      v30 = 1;
      for ( n = 0; n < 0xF; ++n )
        *((_BYTE *)v28->pvData + v30++) = 0;
      v32 = -1;
      do
        ++v32;
      while ( v10[v32] );
      v37 = (v32 >> 1) - 8;
      for ( ii = 0; ii != 4; ++ii )
        *(_BYTE *)(v30++ + *(_QWORD *)(v29 + 16)) = *((_BYTE *)&v37 + ii);
      for ( jj = 16; ; jj += 2LL )
      {
        v35 = -1;
        do
          ++v35;
        while ( v10[v35] );
        if ( jj >= v35 )
          break;
        String = v10[jj];
        v49 = v10[jj + 1];
        v50 = 0;
        *(_BYTE *)(v30++ + *(_QWORD *)(v29 + 16)) = wcstol(&String, 0, 16);
      }
      pvarg.llVal = v29;
      pvarg.vt = 8209;
      rgIndices[1] = 0;
      rgIndices[0] = v38;
      v27 = rgIndices;
    }
    SafeArrayPutElement(v6, v27, &pvarg);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    v4 = v43 + 24;
    v43 += 24;
    ++v38;
    v9 = v45;
    v2 = v46;
  }
  v36 = v47;
  VariantClear(v47);
  v36->vt = 8204;
  v36->llVal = (LONGLONG)v6;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180046a30  push    rbp
0x180046a32  push    rbx
0x180046a33  push    rsi
0x180046a34  push    rdi
0x180046a35  push    r12
0x180046a37  push    r13
0x180046a39  push    r14
0x180046a3b  push    r15
0x180046a3d  lea     rbp, [rsp-1Fh]
0x180046a42  sub     rsp, 0A8h
0x180046a49  mov     rax, cs:__security_cookie
0x180046a50  xor     rax, rsp
0x180046a53  mov     [rbp+57h+var_48], rax
0x180046a57  mov     [rbp+57h+var_58], rdx
0x180046a5b  mov     r14, rcx
0x180046a5e  mov     [rbp+57h+var_60], rcx
0x180046a62  mov     rax, [rdx+8]
0x180046a66  mov     rsi, [rax+10h]
0x180046a6a  mov     [rbp+57h+var_88], rsi
0x180046a6e  mov     edi, [rax+18h]
0x180046a71  mov     [rbp+57h+rgsabound.cElements], edi
0x180046a74  xor     r15d, r15d
0x180046a77  mov     [rbp+57h+rgsabound.lLbound], r15d
0x180046a7b  lea     ecx, [r15+0Ch]; vt
0x180046a7f  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180046a83  lea     edx, [rcx-0Bh]; cDims
0x180046a86  call    cs:__imp_SafeArrayCreate
0x180046a8c  mov     r13, rax
0x180046a8f  test    rax, rax
0x180046a92  jnz     short loc_180046A9E
0x180046a94  mov     eax, 8007000Eh
0x180046a99  jmp     loc_180046DC7
0x180046a9e  mov     ebx, r15d
0x180046aa1  lea     rcx, [rdi+rdi*2]
0x180046aa5  lea     rax, [rsi+rcx*8]
0x180046aa9  mov     [rbp+57h+var_68], rax
0x180046aad  mov     [rbp+57h+var_AC], r15d
0x180046ab1  cmp     rsi, rax
0x180046ab4  jz      loc_180046DAF
0x180046aba  mov     r12, [rsi+8]
0x180046abe  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180046ac2  call    cs:__imp_VariantInit
0x180046ac8  nop
0x180046ac9  movzx   eax, word ptr [r12]
0x180046ace  mov     [rbp+57h+String], ax
0x180046ad2  movzx   eax, word ptr [r12+2]
0x180046ad8  mov     [rbp+57h+var_4E], ax
0x180046adc  mov     [rbp+57h+var_4C], r15w
0x180046ae1  xor     edx, edx; EndPtr
0x180046ae3  lea     r8d, [rdx+10h]; Radix
0x180046ae7  lea     rcx, [rbp+57h+String]; String
0x180046aeb  call    cs:__imp_wcstol
0x180046af1  mov     r15d, eax
0x180046af4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046af8  xor     edi, edi
0x180046afa  inc     r8
0x180046afd  cmp     [r12+r8*2], di
0x180046b02  jnz     short loc_180046AFA
0x180046b04  shr     r8, 1
0x180046b07  cmp     [r14+94h], dil
0x180046b0e  jz      loc_180046C75
0x180046b14  lea     esi, [r8-8]
0x180046b18  mov     edx, esi; uBytes
0x180046b1a  mov     ecx, 40h ; '@'; uFlags
0x180046b1f  call    cs:__imp_LocalAlloc
0x180046b25  mov     rdi, rax
0x180046b28  xor     edx, edx; int
0x180046b2a  test    rax, rax
0x180046b2d  jz      loc_180046D95
0x180046b33  mov     r14d, edx
0x180046b36  lea     ebx, [rdx+10h]
0x180046b39  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180046b3d  inc     rcx
0x180046b40  cmp     [r12+rcx*2], dx
0x180046b45  jnz     short loc_180046B3D
0x180046b47  cmp     rbx, rcx
0x180046b4a  jnb     short loc_180046B84
0x180046b4c  movzx   eax, word ptr [r12+rbx*2]
0x180046b51  mov     [rbp+57h+String], ax
0x180046b55  movzx   eax, word ptr [r12+rbx*2+2]
0x180046b5b  mov     [rbp+57h+var_4E], ax
0x180046b5f  mov     [rbp+57h+var_4C], dx
0x180046b63  xor     edx, edx; EndPtr
0x180046b65  lea     r8d, [rdx+10h]; Radix
0x180046b69  lea     rcx, [rbp+57h+String]; String
0x180046b6d  call    cs:__imp_wcstol
0x180046b73  movsxd  rcx, r14d
0x180046b76  mov     [rcx+rdi], al
0x180046b79  inc     r14d
0x180046b7c  add     rbx, 2
0x180046b80  xor     edx, edx
0x180046b82  jmp     short loc_180046B39
0x180046b84  mov     [rbp+57h+var_B0], edx
0x180046b87  mov     [rbp+57h+hMem], rdx
0x180046b8b  movzx   ecx, r15b; int
0x180046b8f  lea     rax, [rbp+57h+var_B0]
0x180046b93  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x180046b98  lea     rax, [rbp+57h+hMem]
0x180046b9c  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 **
0x180046ba1  mov     r9d, esi; unsigned int
0x180046ba4  mov     r8, rdi; unsigned __int8 *
0x180046ba7  call    ?MigrateEAPBlob@@YAJHHPEAEKPEAPEAEPEAK@Z; MigrateEAPBlob(int,int,uchar *,ulong,uchar * *,ulong *)
0x180046bac  mov     ebx, eax
0x180046bae  mov     rcx, rdi; hMem
0x180046bb1  call    cs:__imp_LocalFree
0x180046bb7  test    ebx, ebx
0x180046bb9  js      loc_180046D9A
0x180046bbf  mov     esi, [rbp+57h+var_B0]
0x180046bc2  lea     r8d, [rsi+14h]; cElements
0x180046bc6  mov     ecx, 11h; vt
0x180046bcb  xor     edx, edx; lLbound
0x180046bcd  call    cs:__imp_SafeArrayCreateVector
0x180046bd3  mov     rdi, rax
0x180046bd6  test    rax, rax
0x180046bd9  jz      loc_180046D8B
0x180046bdf  mov     rcx, [rax+10h]
0x180046be3  mov     [rcx], r15b
0x180046be6  mov     r9d, 1
0x180046bec  xor     r15d, r15d
0x180046bef  mov     edx, r15d
0x180046bf2  movsxd  rcx, r9d
0x180046bf5  mov     rax, [rdi+10h]
0x180046bf9  mov     [rcx+rax], r15b
0x180046bfd  inc     r9d
0x180046c00  inc     edx
0x180046c02  cmp     edx, 0Fh
0x180046c05  jb      short loc_180046BF2
0x180046c07  mov     [rbp+57h+var_B0], esi
0x180046c0a  mov     r8, r15
0x180046c0d  movsxd  rdx, r9d
0x180046c10  mov     rcx, [rdi+10h]
0x180046c14  mov     al, byte ptr [rbp+r8+57h+var_B0]
0x180046c19  mov     [rdx+rcx], al
0x180046c1c  inc     r9d
0x180046c1f  inc     r8
0x180046c22  cmp     r8, 4
0x180046c26  jnz     short loc_180046C0D
0x180046c28  mov     r10d, r15d
0x180046c2b  mov     rcx, [rbp+57h+hMem]; hMem
0x180046c2f  test    esi, esi
0x180046c31  jz      short loc_180046C4F
0x180046c33  mov     eax, r10d
0x180046c36  movsxd  r8, r9d
0x180046c39  mov     rdx, [rdi+10h]
0x180046c3d  mov     al, [rax+rcx]
0x180046c40  mov     [r8+rdx], al
0x180046c44  inc     r9d
0x180046c47  inc     r10d
0x180046c4a  cmp     r10d, esi
0x180046c4d  jb      short loc_180046C33
0x180046c4f  call    cs:__imp_LocalFree
0x180046c55  mov     qword ptr [rbp+57h+pvarg+8], rdi
0x180046c59  mov     eax, 2011h
0x180046c5e  mov     word ptr [rbp+57h+pvarg], ax
0x180046c62  mov     [rbp+57h+var_94], r15d
0x180046c66  mov     eax, [rbp+57h+var_AC]
0x180046c69  mov     [rbp+57h+var_98], eax
0x180046c6c  lea     rdx, [rbp+57h+var_98]
0x180046c70  jmp     loc_180046D58
0x180046c75  add     r8d, 0Ch; cElements
0x180046c79  mov     ecx, 11h; vt
0x180046c7e  xor     edx, edx; lLbound
0x180046c80  call    cs:__imp_SafeArrayCreateVector
0x180046c86  mov     r14, rax
0x180046c89  test    rax, rax
0x180046c8c  jz      loc_180046D95
0x180046c92  mov     rcx, [rax+10h]
0x180046c96  mov     [rcx], r15b
0x180046c99  mov     edi, 1
0x180046c9e  xor     r15d, r15d
0x180046ca1  mov     edx, r15d
0x180046ca4  movsxd  rcx, edi
0x180046ca7  mov     rax, [r14+10h]
0x180046cab  mov     [rcx+rax], r15b
0x180046caf  inc     edi
0x180046cb1  inc     edx
0x180046cb3  cmp     edx, 0Fh
0x180046cb6  jb      short loc_180046CA4
0x180046cb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046cbc  inc     rax
0x180046cbf  cmp     [r12+rax*2], r15w
0x180046cc4  jnz     short loc_180046CBC
0x180046cc6  shr     rax, 1
0x180046cc9  sub     eax, 8
0x180046ccc  mov     [rbp+57h+var_B0], eax
0x180046ccf  mov     r8, r15
0x180046cd2  movsxd  rdx, edi
0x180046cd5  mov     rcx, [r14+10h]
0x180046cd9  mov     al, byte ptr [rbp+r8+57h+var_B0]
0x180046cde  mov     [rdx+rcx], al
0x180046ce1  inc     edi
0x180046ce3  inc     r8
0x180046ce6  cmp     r8, 4
0x180046cea  jnz     short loc_180046CD2
0x180046cec  lea     esi, [r8+0Ch]
0x180046cf0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046cf4  inc     rax
0x180046cf7  cmp     [r12+rax*2], r15w
0x180046cfc  jnz     short loc_180046CF4
0x180046cfe  cmp     rsi, rax
0x180046d01  jnb     short loc_180046D3D
0x180046d03  movzx   eax, word ptr [r12+rsi*2]
0x180046d08  mov     [rbp+57h+String], ax
0x180046d0c  movzx   eax, word ptr [r12+rsi*2+2]
0x180046d12  mov     [rbp+57h+var_4E], ax
0x180046d16  mov     [rbp+57h+var_4C], r15w
0x180046d1b  xor     edx, edx; EndPtr
0x180046d1d  lea     r8d, [rdx+10h]; Radix
0x180046d21  lea     rcx, [rbp+57h+String]; String
0x180046d25  call    cs:__imp_wcstol
0x180046d2b  movsxd  rdx, edi
0x180046d2e  mov     rcx, [r14+10h]
0x180046d32  mov     [rdx+rcx], al
0x180046d35  inc     edi
0x180046d37  add     rsi, 2
0x180046d3b  jmp     short loc_180046CF0
0x180046d3d  mov     qword ptr [rbp+57h+pvarg+8], r14
0x180046d41  mov     eax, 2011h
0x180046d46  mov     word ptr [rbp+57h+pvarg], ax
0x180046d4a  mov     [rbp+57h+var_8C], r15d
0x180046d4e  mov     eax, [rbp+57h+var_AC]
0x180046d51  mov     [rbp+57h+rgIndices], eax
0x180046d54  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180046d58  lea     r8, [rbp+57h+pvarg]; pv
0x180046d5c  mov     rcx, r13; psa
0x180046d5f  call    cs:__imp_SafeArrayPutElement
0x180046d65  nop
0x180046d66  lea     rcx, [rbp+57h+pvarg]; this
0x180046d6a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180046d6f  mov     rsi, [rbp+57h+var_88]
0x180046d73  add     rsi, 18h
0x180046d77  mov     [rbp+57h+var_88], rsi
0x180046d7b  inc     [rbp+57h+var_AC]
0x180046d7e  mov     rax, [rbp+57h+var_68]
0x180046d82  mov     r14, [rbp+57h+var_60]
0x180046d86  jmp     loc_180046AB1
0x180046d8b  mov     rcx, [rbp+57h+hMem]; hMem
0x180046d8f  call    cs:__imp_LocalFree
0x180046d95  mov     ebx, 8007000Eh
0x180046d9a  mov     rcx, r13; psa
0x180046d9d  call    cs:__imp_SafeArrayDestroy
0x180046da3  nop
0x180046da4  lea     rcx, [rbp+57h+pvarg]; this
0x180046da8  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180046dad  jmp     short loc_180046DC5
0x180046daf  mov     rsi, [rbp+57h+var_58]
0x180046db3  mov     rcx, rsi; pvarg
0x180046db6  call    cs:__imp_VariantClear
0x180046dbc  mov     word ptr [rsi], 200Ch
0x180046dc1  mov     [rsi+8], r13
0x180046dc5  mov     eax, ebx
0x180046dc7  mov     rcx, [rbp+57h+var_48]
0x180046dcb  xor     rcx, rsp; StackCookie
0x180046dce  call    __security_check_cookie
0x180046dd3  add     rsp, 0A8h
0x180046dda  pop     r15
0x180046ddc  pop     r14
0x180046dde  pop     r13
0x180046de0  pop     r12
0x180046de2  pop     rdi
0x180046de3  pop     rsi
0x180046de4  pop     rbx
0x180046de5  pop     rbp
0x180046de6  retn
```
