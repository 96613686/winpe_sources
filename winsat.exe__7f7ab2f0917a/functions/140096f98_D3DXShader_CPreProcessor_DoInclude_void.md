# D3DXShader::CPreProcessor::DoInclude(void)

- ea: `0x140096f98`
- end: `0x140097207`
- name: `?DoInclude@CPreProcessor@D3DXShader@@IEAAJXZ`
- size: `623`
- prototype: `__int64 __fastcall(D3DXShader::CPreProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140098b38`

## callees

- `0x14008c0e0`
- `0x1400950ec`
- `0x140095928`
- `0x140095d10`
- `0x140096f98`
- `0x140097d60`
- `0x140098694`
- `0x1400a96b4`
- `0x1400a98b4`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetFullPathNameA` at `0x1400970ba`
- `KERNEL32!GetFullPathNameA` at `0x140097125`
- `KERNEL32!GetFullPathNameA` at `0x1400970ba`
- `KERNEL32!GetFullPathNameA` at `0x140097125`

## pseudocode

```c
__int64 __fastcall D3DXShader::CPreProcessor::DoInclude(D3DXShader::CPreProcessor *this)
{
  struct D3DXShader::D3DXTOKEN *v1; // rsi
  __int64 result; // rax
  unsigned int v4; // r15d
  const struct D3DX9MEMORY::CD3DXNEW *v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // ecx
  CHAR *v8; // rbp
  __int64 v9; // r9
  CHAR *v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  CHAR *v13; // r14
  D3DXShader::CPPInclude *v14; // rax
  __int64 v15; // rax
  D3DXShader::CPPInclude *v16; // rdi
  unsigned int v17; // edx
  int v18; // esi
  LPSTR FilePart[2]; // [rsp+50h] [rbp-268h] BYREF
  CHAR Buffer[272]; // [rsp+60h] [rbp-258h] BYREF
  CHAR FileName[272]; // [rsp+170h] [rbp-148h] BYREF

  v1 = (D3DXShader::CPreProcessor *)((char *)this + 1200);
  result = D3DXShader::CTokenize::GetToken(
             *((D3DXShader::CTokenize **)this + 148),
             *((_DWORD *)this + 312) | 0xCu,
             (D3DXShader::CPreProcessor *)((char *)this + 1200));
  if ( (int)result >= 0 )
  {
    if ( *(_DWORD *)v1 == 10 )
    {
      v4 = 0;
    }
    else
    {
      if ( *(_DWORD *)v1 != 11 )
      {
        D3DXShader::CPreProcessor::Error(this, "syntax error");
        return 2147500037LL;
      }
      v4 = 1;
    }
    v5 = (const struct D3DX9MEMORY::CD3DXNEW *)*((_QWORD *)this + 149);
    if ( !v5 && !*(_QWORD *)(*((_QWORD *)this + 148) + 32LL) )
    {
      D3DXShader::CTErrors::Error(
        (D3DXShader::CPreProcessor *)((char *)this + 32),
        v1,
        0x5E1u,
        "include interface required to support #include from resource or memory");
LABEL_11:
      *((_DWORD *)this + 26) = 1;
      *((_DWORD *)this + 25) = 1;
      return 2147500037LL;
    }
    v6 = *((_QWORD *)this + 147);
    v7 = 0;
    if ( v6 )
    {
      do
      {
        v6 = *(_QWORD *)(v6 + 192);
        ++v7;
      }
      while ( v6 );
      if ( v7 >= 0x20 )
      {
        D3DXShader::CTErrors::Error(
          (D3DXShader::CPreProcessor *)((char *)this + 32),
          v1,
          0x5E2u,
          "too many nested #includes");
        goto LABEL_11;
      }
    }
    v8 = (CHAR *)*((_QWORD *)this + 151);
    FilePart[0] = 0;
    if ( !v5 )
    {
      GetFullPathNameA(v8, 0x104u, Buffer, FilePart);
      v9 = *((_QWORD *)this + 147);
      if ( v9 )
      {
        v10 = v8;
        do
        {
          v5 = (const struct D3DX9MEMORY::CD3DXNEW *)(unsigned __int8)v10[Buffer - v8];
          v11 = (unsigned __int8)*v10 - (_DWORD)v5;
          if ( v11 )
            break;
          ++v10;
        }
        while ( (_DWORD)v5 );
        if ( v11 )
        {
          StringCbPrintfA(FileName, 0x104u, "%s%s", *(const char **)(v9 + 168), v8);
          GetFullPathNameA(FileName, 0x104u, Buffer, FilePart);
        }
      }
      v8 = Buffer;
    }
    v12 = *((_QWORD *)this + 147);
    if ( v12 && *(_QWORD *)(v12 + 152) )
      v13 = *(CHAR **)(v12 + 176);
    else
      v13 = 0;
    v14 = (D3DXShader::CPPInclude *)operator new(0xC8u, v5);
    if ( v14 && (v15 = D3DXShader::CPPInclude::CPPInclude(v14), (v16 = (D3DXShader::CPPInclude *)v15) != 0) )
    {
      v18 = D3DXShader::CPPInclude::InitializeFromFile(
              v15,
              v8,
              (__int64)this + 32,
              this,
              v1,
              (D3DXShader::CPreProcessor *)((char *)this + 32),
              *((_QWORD *)this + 149),
              v4,
              v13);
      if ( v18 >= 0 )
      {
        *((_QWORD *)v16 + 24) = *((_QWORD *)this + 147);
        result = 0;
        *((_QWORD *)this + 147) = v16;
      }
      else
      {
        *((_DWORD *)this + 26) = 1;
        *((_DWORD *)this + 25) = 1;
        D3DXShader::CPPInclude::`scalar deleting destructor'(v16, v17);
        return (unsigned int)v18;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140096f98  mov     [rsp+arg_8], rbx
0x140096f9d  mov     [rsp+arg_10], rbp
0x140096fa2  push    rsi
0x140096fa3  push    rdi
0x140096fa4  push    r13
0x140096fa6  push    r14
0x140096fa8  push    r15
0x140096faa  sub     rsp, 290h
0x140096fb1  mov     rax, cs:__security_cookie
0x140096fb8  xor     rax, rsp
0x140096fbb  mov     [rsp+2B8h+var_38], rax
0x140096fc3  mov     edx, [rcx+4E0h]
0x140096fc9  lea     rsi, [rcx+4B0h]
0x140096fd0  mov     rbx, rcx
0x140096fd3  or      edx, 0Ch; unsigned int
0x140096fd6  mov     rcx, [rcx+4A0h]; this
0x140096fdd  mov     r8, rsi; struct D3DXShader::D3DXTOKEN *
0x140096fe0  call    ?GetToken@CTokenize@D3DXShader@@QEAAJKPEAUD3DXTOKEN@2@@Z; D3DXShader::CTokenize::GetToken(ulong,D3DXShader::D3DXTOKEN *)
0x140096fe5  test    eax, eax
0x140096fe7  js      loc_1400971DB
0x140096fed  mov     ecx, [rsi]
0x140096fef  mov     r13d, 1
0x140096ff5  sub     ecx, 0Ah
0x140096ff8  jz      short loc_14009701D
0x140096ffa  cmp     ecx, r13d
0x140096ffd  jz      short loc_140097018
0x140096fff  lea     rdx, aSyntaxError; "syntax error"
0x140097006  mov     rcx, rbx; this
0x140097009  call    ?Error@CPreProcessor@D3DXShader@@IEAAXPEBDZZ; D3DXShader::CPreProcessor::Error(char const *,...)
0x14009700e  mov     eax, 80004005h
0x140097013  jmp     loc_1400971DB
0x140097018  mov     r15d, r13d
0x14009701b  jmp     short loc_140097020
0x14009701d  xor     r15d, r15d
0x140097020  mov     rdx, [rbx+4A8h]
0x140097027  test    rdx, rdx
0x14009702a  jnz     short loc_14009705C
0x14009702c  mov     rax, [rbx+4A0h]
0x140097033  cmp     [rax+20h], rdx
0x140097037  jnz     short loc_14009705C
0x140097039  lea     r9, aIncludeInterfa; "include interface required to support #"...
0x140097040  mov     r8d, 5E1h; unsigned int
0x140097046  lea     rcx, [rbx+20h]; this
0x14009704a  mov     rdx, rsi; struct D3DXShader::D3DXTOKEN *
0x14009704d  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140097052  mov     [rbx+68h], r13d
0x140097056  mov     [rbx+64h], r13d
0x14009705a  jmp     short loc_14009700E
0x14009705c  mov     rax, [rbx+498h]
0x140097063  xor     ecx, ecx
0x140097065  test    rax, rax
0x140097068  jz      short loc_14009708D
0x14009706a  mov     rax, [rax+0C0h]
0x140097071  add     ecx, r13d
0x140097074  test    rax, rax
0x140097077  jnz     short loc_14009706A
0x140097079  cmp     ecx, 20h ; ' '
0x14009707c  jb      short loc_14009708D
0x14009707e  lea     r9, aTooManyNestedI; "too many nested #includes"
0x140097085  mov     r8d, 5E2h
0x14009708b  jmp     short loc_140097046
0x14009708d  mov     rbp, [rbx+4B8h]
0x140097094  mov     [rsp+2B8h+FilePart], 0
0x14009709d  test    rdx, rdx
0x1400970a0  jnz     loc_140097130
0x1400970a6  mov     edi, 104h
0x1400970ab  lea     r9, [rsp+2B8h+FilePart]; lpFilePart
0x1400970b0  mov     edx, edi; nBufferLength
0x1400970b2  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x1400970b7  mov     rcx, rbp; lpFileName
0x1400970ba  call    cs:__imp_GetFullPathNameA
0x1400970c0  mov     r9, [rbx+498h]
0x1400970c7  test    r9, r9
0x1400970ca  jz      short loc_14009712B
0x1400970cc  lea     r8, [rsp+2B8h+Buffer]
0x1400970d1  mov     rax, rbp
0x1400970d4  sub     r8, rbp
0x1400970d7  movzx   ecx, byte ptr [rax]
0x1400970da  movzx   edx, byte ptr [rax+r8]
0x1400970df  sub     ecx, edx
0x1400970e1  jnz     short loc_1400970EA
0x1400970e3  add     rax, r13
0x1400970e6  test    edx, edx
0x1400970e8  jnz     short loc_1400970D7
0x1400970ea  test    ecx, ecx
0x1400970ec  jz      short loc_14009712B
0x1400970ee  mov     r9, [r9+0A8h]
0x1400970f5  lea     r8, aSS_3; "%s%s"
0x1400970fc  mov     rdx, rdi; unsigned __int64
0x1400970ff  mov     [rsp+2B8h+var_298], rbp
0x140097104  lea     rcx, [rsp+2B8h+FileName]; char *
0x14009710c  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x140097111  lea     r9, [rsp+2B8h+FilePart]; lpFilePart
0x140097116  mov     edx, edi; nBufferLength
0x140097118  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x14009711d  lea     rcx, [rsp+2B8h+FileName]; lpFileName
0x140097125  call    cs:__imp_GetFullPathNameA
0x14009712b  lea     rbp, [rsp+2B8h+Buffer]
0x140097130  mov     rax, [rbx+498h]
0x140097137  test    rax, rax
0x14009713a  jz      short loc_14009714F
0x14009713c  cmp     qword ptr [rax+98h], 0
0x140097144  jz      short loc_14009714F
0x140097146  mov     r14, [rax+0B0h]
0x14009714d  jmp     short loc_140097152
0x14009714f  xor     r14d, r14d
0x140097152  mov     ecx, 0C8h; unsigned __int64
0x140097157  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x14009715c  test    rax, rax
0x14009715f  jz      short loc_1400971D6
0x140097161  mov     rcx, rax; this
0x140097164  call    ??0CPPInclude@D3DXShader@@QEAA@XZ; D3DXShader::CPPInclude::CPPInclude(void)
0x140097169  mov     rdi, rax
0x14009716c  test    rax, rax
0x14009716f  jz      short loc_1400971D6
0x140097171  mov     rcx, [rbx+4A8h]
0x140097178  lea     r8, [rbx+20h]
0x14009717c  mov     [rsp+2B8h+var_278], r14
0x140097181  mov     r9, rbx
0x140097184  mov     [rsp+2B8h+var_280], r15d
0x140097189  mov     rdx, rbp
0x14009718c  mov     [rsp+2B8h+var_288], rcx
0x140097191  mov     rcx, rax
0x140097194  mov     [rsp+2B8h+var_290], r8
0x140097199  mov     [rsp+2B8h+var_298], rsi
0x14009719e  call    ?InitializeFromFile@CPPInclude@D3DXShader@@QEAAJPEBXHPEAVCAlloc@D3DXCore@@PEAUD3DXTOKEN@2@PEAVCTErrors@2@PEAUID3DXInclude@@W4_D3DXINCLUDE_TYPE@@0@Z; D3DXShader::CPPInclude::InitializeFromFile(void const *,int,D3DXCore::CAlloc *,D3DXShader::D3DXTOKEN *,D3DXShader::CTErrors *,ID3DXInclude *,_D3DXINCLUDE_TYPE,void const *)
0x1400971a3  mov     esi, eax
0x1400971a5  test    eax, eax
0x1400971a7  jns     short loc_1400971BD
0x1400971a9  mov     rcx, rdi; this
0x1400971ac  mov     [rbx+68h], r13d
0x1400971b0  mov     [rbx+64h], r13d
0x1400971b4  call    ??_GCPPInclude@D3DXShader@@QEAAPEAXI@Z; D3DXShader::CPPInclude::`scalar deleting destructor'(uint)
0x1400971b9  mov     eax, esi
0x1400971bb  jmp     short loc_1400971DB
0x1400971bd  mov     rax, [rbx+498h]
0x1400971c4  mov     [rdi+0C0h], rax
0x1400971cb  xor     eax, eax
0x1400971cd  mov     [rbx+498h], rdi
0x1400971d4  jmp     short loc_1400971DB
0x1400971d6  mov     eax, 8007000Eh
0x1400971db  mov     rcx, [rsp+2B8h+var_38]
0x1400971e3  xor     rcx, rsp; StackCookie
0x1400971e6  call    __security_check_cookie
0x1400971eb  lea     r11, [rsp+2B8h+var_28]
0x1400971f3  mov     rbx, [r11+38h]
0x1400971f7  mov     rbp, [r11+40h]
0x1400971fb  mov     rsp, r11
0x1400971fe  pop     r15
0x140097200  pop     r14
0x140097202  pop     r13
0x140097204  pop     rdi
0x140097205  pop     rsi
0x140097206  retn
```
