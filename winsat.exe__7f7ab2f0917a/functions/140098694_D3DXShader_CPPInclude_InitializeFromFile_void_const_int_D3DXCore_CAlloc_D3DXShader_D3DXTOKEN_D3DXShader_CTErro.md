# D3DXShader::CPPInclude::InitializeFromFile(void const *,int,D3DXCore::CAlloc *,D3DXShader::D3DXTOKEN *,D3DXShader::CTErrors *,ID3DXInclude *,_D3DXINCLUDE_TYPE,void const *)

- ea: `0x140098694`
- end: `0x1400988d7`
- name: `?InitializeFromFile@CPPInclude@D3DXShader@@QEAAJPEBXHPEAVCAlloc@D3DXCore@@PEAUD3DXTOKEN@2@PEAVCTErrors@2@PEAUID3DXInclude@@W4_D3DXINCLUDE_TYPE@@0@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140096f98`

## callees

- `0x140003560`
- `0x140098694`
- `0x1400a96b4`
- `0x1400a9b18`
- `0x1400aae30`
- `0x1400accf8`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetFullPathNameA` at `0x1400987a4`
- `KERNEL32!GetFullPathNameA` at `0x140098808`
- `KERNEL32!GetFullPathNameA` at `0x1400987a4`
- `KERNEL32!GetFullPathNameA` at `0x140098808`

## string_xrefs

- `0x140098773`: `failed to open source file: '%s'`
- `0x140098857`: `failed to open source file: '%s'`

## pseudocode

```c
__int64 __fastcall D3DXShader::CPPInclude::InitializeFromFile(
        __int64 a1,
        const CHAR *a2,
        __int64 a3,
        D3DXCore::CAlloc *a4,
        struct D3DXShader::D3DXTOKEN *a5,
        D3DXShader::CTErrors *a6,
        __int64 a7,
        unsigned int a8,
        CHAR *a9)
{
  __int64 v12; // rax
  unsigned int v13; // r14d
  unsigned __int8 *v14; // rax
  unsigned int *v15; // r14
  const void **v16; // r15
  DWORD FullPathNameA; // eax
  __int64 v19; // r14
  unsigned int v20; // ebp
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rax
  CHAR *v23; // r8
  int v24; // r8d
  int v25; // ebp
  int v26; // eax
  unsigned int v27; // ecx
  LPSTR FilePart; // [rsp+40h] [rbp-48h] BYREF
  struct D3DXShader::D3DXTOKEN *v29; // [rsp+48h] [rbp-40h]

  FilePart = a9;
  v29 = a5;
  *(_QWORD *)(a1 + 152) = a7;
  if ( !a7 )
  {
    FullPathNameA = GetFullPathNameA(a2, 0, 0, 0);
    v19 = FullPathNameA;
    v20 = FullPathNameA + 1;
    v21 = D3DXCore::CAlloc::Alloc(a4, FullPathNameA + 1, 1);
    *(_QWORD *)(a1 + 168) = v21;
    if ( v21 )
    {
      v22 = D3DXCore::CAlloc::Alloc(a4, v20, 1);
      *(_QWORD *)(a1 + 160) = v22;
      if ( v22 )
      {
        v23 = *(CHAR **)(a1 + 168);
        FilePart = 0;
        GetFullPathNameA(a2, v19, v23, &FilePart);
        *(_BYTE *)(v19 + *(_QWORD *)(a1 + 168)) = 0;
        memcpy_0(*(void **)(a1 + 160), *(const void **)(a1 + 168), v20);
        if ( FilePart )
          *FilePart = 0;
        v25 = D3DXCore::CFile::Open((D3DXCore::CFile *)(a1 + 96), *(const void **)(a1 + 160), v24);
        if ( v25 < 0 )
        {
          D3DXShader::CTErrors::Error(a6, v29, 0x5E3u, "failed to open source file: '%s'", a2);
          return (unsigned int)v25;
        }
        v16 = (const void **)(a1 + 176);
        *(_QWORD *)(a1 + 176) = *(_QWORD *)(a1 + 112);
        v15 = (unsigned int *)(a1 + 184);
        *(_DWORD *)(a1 + 184) = *(_DWORD *)(a1 + 120);
        goto LABEL_14;
      }
    }
    return 2147942414LL;
  }
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = v12 + 1;
  v14 = D3DXCore::CAlloc::Alloc(a4, (int)v12 + 1, 1);
  *(_QWORD *)(a1 + 160) = v14;
  if ( !v14 )
    return 2147942414LL;
  memcpy_0(v14, a2, v13);
  v15 = (unsigned int *)(a1 + 184);
  v16 = (const void **)(a1 + 176);
  LODWORD(FilePart) = (***(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, LPSTR, __int64, __int64))(a1 + 152))(
                        *(_QWORD *)(a1 + 152),
                        a8,
                        *(_QWORD *)(a1 + 160),
                        FilePart,
                        a1 + 176,
                        a1 + 184);
  if ( (int)FilePart < 0 )
  {
    D3DXShader::CTErrors::Error(a6, a5, 0x5E3u, "failed to open source file: '%s'", a2);
    return (unsigned int)FilePart;
  }
LABEL_14:
  v26 = D3DXShader::CTokenize::Initialize(
          (D3DXShader::CTokenize *)a1,
          *v16,
          *v15,
          *(const char **)(a1 + 160),
          1u,
          a4,
          a6);
  v27 = 0;
  if ( v26 < 0 )
    return (unsigned int)v26;
  return v27;
}

```

## disassembly

```asm
0x140098694  push    rbx
0x140098696  push    rbp
0x140098697  push    rdi
0x140098698  push    r12
0x14009869a  push    r13
0x14009869c  push    r14
0x14009869e  push    r15
0x1400986a0  sub     rsp, 50h
0x1400986a4  mov     rax, [rsp+88h+arg_40]
0x1400986ac  xor     r15d, r15d
0x1400986af  mov     rbp, [rsp+88h+arg_20]
0x1400986b7  mov     r12, r9
0x1400986ba  mov     r13, [rsp+88h+arg_28]
0x1400986c2  mov     rdi, rdx
0x1400986c5  mov     [rsp+88h+FilePart], rax
0x1400986ca  mov     rbx, rcx
0x1400986cd  mov     rax, [rsp+88h+arg_30]
0x1400986d5  mov     [rsp+88h+var_40], rbp
0x1400986da  mov     [rcx+98h], rax
0x1400986e1  test    rax, rax
0x1400986e4  jz      loc_140098799
0x1400986ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400986ee  inc     rax
0x1400986f1  cmp     [rdx+rax], r15b
0x1400986f5  jnz     short loc_1400986EE
0x1400986f7  lea     r14d, [rax+1]
0x1400986fb  mov     r8d, 1; unsigned int
0x140098701  mov     edx, r14d; unsigned int
0x140098704  mov     rcx, r12; this
0x140098707  call    ?Alloc@CAlloc@D3DXCore@@QEAAPEAEII@Z; D3DXCore::CAlloc::Alloc(uint,uint)
0x14009870c  mov     [rbx+0A0h], rax
0x140098713  test    rax, rax
0x140098716  jz      loc_1400988C2
0x14009871c  mov     r8d, r14d; Size
0x14009871f  mov     rdx, rdi; Src
0x140098722  mov     rcx, rax; void *
0x140098725  call    memcpy_0
0x14009872a  mov     rcx, [rbx+98h]
0x140098731  lea     r14, [rbx+0B8h]
0x140098738  mov     r9, [rsp+88h+FilePart]
0x14009873d  lea     r15, [rbx+0B0h]
0x140098744  mov     r8, [rbx+0A0h]
0x14009874b  mov     edx, [rsp+88h+arg_38]
0x140098752  mov     rax, [rcx]
0x140098755  mov     [rsp+88h+var_60], r14
0x14009875a  mov     qword ptr [rsp+88h+var_68], r15
0x14009875f  mov     rax, [rax]
0x140098762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098767  mov     dword ptr [rsp+88h+FilePart], eax
0x14009876b  test    eax, eax
0x14009876d  jns     loc_140098890
0x140098773  lea     r9, aFailedToOpenSo; "failed to open source file: '%s'"
0x14009877a  mov     qword ptr [rsp+88h+var_68], rdi
0x14009877f  mov     r8d, 5E3h; unsigned int
0x140098785  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x140098788  mov     rcx, r13; this
0x14009878b  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140098790  mov     eax, dword ptr [rsp+88h+FilePart]
0x140098794  jmp     loc_1400988C7
0x140098799  xor     r9d, r9d; lpFilePart
0x14009879c  xor     r8d, r8d; lpBuffer
0x14009879f  xor     edx, edx; nBufferLength
0x1400987a1  mov     rcx, rdi; lpFileName
0x1400987a4  call    cs:__imp_GetFullPathNameA
0x1400987aa  mov     r14d, eax
0x1400987ad  mov     r8d, 1; unsigned int
0x1400987b3  mov     rcx, r12; this
0x1400987b6  lea     ebp, [r14+1]
0x1400987ba  mov     edx, ebp; unsigned int
0x1400987bc  call    ?Alloc@CAlloc@D3DXCore@@QEAAPEAEII@Z; D3DXCore::CAlloc::Alloc(uint,uint)
0x1400987c1  mov     [rbx+0A8h], rax
0x1400987c8  test    rax, rax
0x1400987cb  jz      loc_1400988C2
0x1400987d1  mov     r8d, 1; unsigned int
0x1400987d7  mov     edx, ebp; unsigned int
0x1400987d9  mov     rcx, r12; this
0x1400987dc  call    ?Alloc@CAlloc@D3DXCore@@QEAAPEAEII@Z; D3DXCore::CAlloc::Alloc(uint,uint)
0x1400987e1  mov     [rbx+0A0h], rax
0x1400987e8  test    rax, rax
0x1400987eb  jz      loc_1400988C2
0x1400987f1  mov     r8, [rbx+0A8h]; lpBuffer
0x1400987f8  lea     r9, [rsp+88h+FilePart]; lpFilePart
0x1400987fd  mov     edx, r14d; nBufferLength
0x140098800  mov     [rsp+88h+FilePart], r15
0x140098805  mov     rcx, rdi; lpFileName
0x140098808  call    cs:__imp_GetFullPathNameA
0x14009880e  mov     rax, [rbx+0A8h]
0x140098815  mov     r8d, ebp; Size
0x140098818  mov     [r14+rax], r15b
0x14009881c  mov     rdx, [rbx+0A8h]; Src
0x140098823  mov     rcx, [rbx+0A0h]; void *
0x14009882a  call    memcpy_0
0x14009882f  mov     rax, [rsp+88h+FilePart]
0x140098834  test    rax, rax
0x140098837  jz      short loc_14009883C
0x140098839  mov     [rax], r15b
0x14009883c  mov     rdx, [rbx+0A0h]; void *
0x140098843  lea     rcx, [rbx+60h]; this
0x140098847  call    ?Open@CFile@D3DXCore@@QEAAJPEBXH@Z; D3DXCore::CFile::Open(void const *,int)
0x14009884c  mov     ebp, eax
0x14009884e  test    eax, eax
0x140098850  jns     short loc_140098875
0x140098852  mov     rdx, [rsp+88h+var_40]; struct D3DXShader::D3DXTOKEN *
0x140098857  lea     r9, aFailedToOpenSo; "failed to open source file: '%s'"
0x14009885e  mov     r8d, 5E3h; unsigned int
0x140098864  mov     qword ptr [rsp+88h+var_68], rdi
0x140098869  mov     rcx, r13; this
0x14009886c  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140098871  mov     eax, ebp
0x140098873  jmp     short loc_1400988C7
0x140098875  mov     rax, [rbx+70h]
0x140098879  lea     r15, [rbx+0B0h]
0x140098880  mov     [r15], rax
0x140098883  lea     r14, [rbx+0B8h]
0x14009888a  mov     eax, [rbx+78h]
0x14009888d  mov     [r14], eax
0x140098890  mov     r9, [rbx+0A0h]; char *
0x140098897  mov     rcx, rbx; this
0x14009889a  mov     rdx, [r15]; void *
0x14009889d  mov     r8d, [r14]; unsigned int
0x1400988a0  mov     [rsp+88h+var_58], r13; struct D3DXShader::CTErrors *
0x1400988a5  mov     [rsp+88h+var_60], r12; struct D3DXCore::CAlloc *
0x1400988aa  mov     [rsp+88h+var_68], 1; unsigned int
0x1400988b2  call    ?Initialize@CTokenize@D3DXShader@@QEAAJPEBXIPEBDIPEAVCAlloc@D3DXCore@@PEAVCTErrors@2@@Z; D3DXShader::CTokenize::Initialize(void const *,uint,char const *,uint,D3DXCore::CAlloc *,D3DXShader::CTErrors *)
0x1400988b7  xor     ecx, ecx
0x1400988b9  test    eax, eax
0x1400988bb  cmovs   ecx, eax
0x1400988be  mov     eax, ecx
0x1400988c0  jmp     short loc_1400988C7
0x1400988c2  mov     eax, 8007000Eh
0x1400988c7  add     rsp, 50h
0x1400988cb  pop     r15
0x1400988cd  pop     r14
0x1400988cf  pop     r13
0x1400988d1  pop     r12
0x1400988d3  pop     rdi
0x1400988d4  pop     rbp
0x1400988d5  pop     rbx
0x1400988d6  retn
```
