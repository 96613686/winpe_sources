# Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)

- ea: `0x180018e3c`
- end: `0x1800190b6`
- name: `?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z`
- size: `634`
- prototype: `__int64 __fastcall(Parser *__hidden this, struct ExecBody **, struct COleScript *, const unsigned __int16 *, unsigned int, LPCSTR, UINT, struct CompileScriptException *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001707c`
- `0x18001787c`
- `0x1800180dc`

## callees

- `0x18000d4dc`
- `0x180016940`
- `0x180016f18`
- `0x180016f98`
- `0x18001700c`
- `0x180018e3c`
- `0x1800191c0`
- `0x18002a3d0`
- `0x18003f238`
- `0x180045490`
- `0x1800766b6`
- `0x180076746`

## import_xrefs

- `msvcrt!_controlfp` at `0x180018e71`
- `msvcrt!_controlfp` at `0x180018e84`
- `msvcrt!_controlfp` at `0x1800190a3`
- `msvcrt!_controlfp` at `0x180018e71`
- `msvcrt!_controlfp` at `0x180018e84`
- `msvcrt!_controlfp` at `0x1800190a3`
- `msvcrt!free` at `0x180019047`
- `msvcrt!free` at `0x180019047`

## pseudocode

```c
__int64 __fastcall Parser::ParseSource(
        Parser *this,
        struct ExecBody **a2,
        struct COleScript *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        CHAR *psz,
        UINT len,
        struct CompileScriptException *a8,
        unsigned __int16 *a9,
        const unsigned __int16 *a10,
        const unsigned __int16 *a11)
{
  unsigned int v14; // ecx
  struct HashTbl *v15; // rax
  struct Scanner *v16; // rax
  struct ParseNode *v17; // rax
  __int64 v18; // r8
  struct ParseNode *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // rbx
  Scanner *v22; // rcx
  struct ExecBody *v23; // rax
  struct ExecBody *v24; // rdx
  unsigned int v25; // ebx
  void *v26; // rcx
  unsigned int NewValue; // [rsp+40h] [rbp-10h]

  NewValue = _controlfp(0, 0);
  _controlfp(0x1Fu, 0x30F031Fu);
  *(_QWORD *)this = *((_QWORD *)a3 + 17);
  *((_QWORD *)this + 61) = a10;
  *a2 = 0;
  if ( a8 )
    memset_0(a8, 0, 0x68u);
  if ( setjmp_0((_JBTYPE *)this + 3) )
  {
    v26 = (void *)*((_QWORD *)this + 40);
    *((_QWORD *)this + 82) = 0;
    if ( v26 )
    {
      free(v26);
      *((_QWORD *)this + 40) = 0;
    }
    NoRelAlloc::FreeAll((Parser *)((char *)this + 16));
    v25 = CompileScriptException::ProcessError(
            a8,
            a3,
            *((struct Scanner **)this + 44),
            (Parser *)((char *)this + 48),
            0,
            len,
            psz,
            a4);
  }
  else
  {
    v15 = HashTbl::Create(v14, (Parser *)((char *)this + 48));
    *((_QWORD *)this + 1) = v15;
    if ( !v15 )
      Parser::Error(this, 1001);
    v16 = Scanner::Create(v15, (Parser *)((char *)this + 336), (Parser *)((char *)this + 48));
    *((_QWORD *)this + 44) = v16;
    if ( !v16 )
      Parser::Error(this, 1001);
    *((_QWORD *)this + 82) = a11;
    v17 = Parser::Parse(this, a4, a5);
    v18 = *((_QWORD *)this + 44);
    v19 = v17;
    *((_QWORD *)this + 82) = 0;
    v20 = *(_QWORD *)(v18 + 360);
    v21 = (__int64)(*(_QWORD *)(v18 + 32) - *(_QWORD *)(v18 + 16)) >> 1;
    *((_DWORD *)this + 168) = *(_DWORD *)(v18 + 368) - v20;
    *(_QWORD *)(v18 + 376) = 0;
    *(_QWORD *)(v18 + 368) = 0;
    *(_QWORD *)(v18 + 360) = 0;
    v22 = (Scanner *)*((_QWORD *)this + 44);
    *((_QWORD *)this + 83) = v20;
    Scanner::Release(v22);
    *((_QWORD *)this + 44) = 0;
    Parser::GenerateCode(this, v19, psz, len, a4, v21, a9);
    v23 = (struct ExecBody *)operator new(0x10u);
    v24 = v23;
    if ( v23 )
    {
      *(_QWORD *)v23 = *((_QWORD *)this + 40);
      *((_DWORD *)v23 + 2) = 1;
    }
    else
    {
      v24 = 0;
    }
    *a2 = v24;
    if ( !v24 )
      Parser::Error(this, 1001);
    *((_QWORD *)this + 40) = 0;
    v25 = 0;
  }
  _controlfp(NewValue, 0xFFFFFFFF);
  return v25;
}

```

## disassembly

```asm
0x180018e3c  mov     rax, rsp
0x180018e3f  mov     [rax+20h], r9
0x180018e43  mov     [rax+18h], r8
0x180018e47  mov     [rax+10h], rdx
0x180018e4b  mov     [rax+8], rcx
0x180018e4f  push    rbp
0x180018e50  push    rbx
0x180018e51  push    rsi
0x180018e52  push    rdi
0x180018e53  push    r14
0x180018e55  mov     rbp, rsp
0x180018e58  sub     rsp, 50h
0x180018e5c  mov     rdi, rdx
0x180018e5f  mov     [rbp+var_8], 0
0x180018e67  mov     rsi, rcx
0x180018e6a  xor     edx, edx; Mask
0x180018e6c  xor     ecx, ecx; NewValue
0x180018e6e  mov     rbx, r8
0x180018e71  call    cs:__imp__controlfp
0x180018e77  mov     edx, 30F031Fh; Mask
0x180018e7c  mov     ecx, 1Fh; NewValue
0x180018e81  mov     [rbp+NewValue], eax
0x180018e84  call    cs:__imp__controlfp
0x180018e8a  mov     rax, [rbx+88h]
0x180018e91  mov     rcx, [rbp+arg_38]; void *
0x180018e95  mov     [rsi], rax
0x180018e98  mov     rax, [rbp+arg_48]
0x180018e9c  mov     [rsi+1E8h], rax
0x180018ea3  mov     qword ptr [rdi], 0
0x180018eaa  test    rcx, rcx
0x180018ead  jz      short loc_180018EBA
0x180018eaf  xor     edx, edx; Val
0x180018eb1  lea     r8d, [rdx+68h]; Size
0x180018eb5  call    memset_0
0x180018eba  lea     rcx, [rsi+30h]; Buf
0x180018ebe  mov     rdx, rsp
0x180018ec1  call    _setjmp_0
0x180018ec6  test    eax, eax
0x180018ec8  jnz     loc_18001902C
0x180018ece  mov     r14, [rbp+arg_0]
0x180018ed2  lea     rdx, [r14+30h]; struct ErrHandler *
0x180018ed6  call    ?Create@HashTbl@@SAPEAV1@IPEAVErrHandler@@@Z; HashTbl::Create(uint,ErrHandler *)
0x180018edb  mov     [r14+8], rax
0x180018edf  test    rax, rax
0x180018ee2  jnz     short loc_180018EF2
0x180018ee4  mov     edx, 3E9h; int
0x180018ee9  mov     rcx, r14; this
0x180018eec  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180018ef2  lea     rdx, [r14+150h]; struct Token *
0x180018ef9  mov     rcx, rax; struct HashTbl *
0x180018efc  lea     r8, [r14+30h]; struct ErrHandler *
0x180018f00  call    ?Create@Scanner@@SAPEAV1@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Create(HashTbl *,Token *,ErrHandler *)
0x180018f05  mov     [r14+160h], rax
0x180018f0c  mov     rcx, r14; this
0x180018f0f  test    rax, rax
0x180018f12  jnz     short loc_180018F1F
0x180018f14  mov     edx, 3E9h; int
0x180018f19  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180018f1f  mov     rax, [rbp+arg_50]
0x180018f26  mov     rsi, [rbp+arg_18]
0x180018f2a  mov     r8d, [rbp+arg_20]; unsigned int
0x180018f2e  mov     rdx, rsi; unsigned __int16 *
0x180018f31  mov     [r14+290h], rax
0x180018f38  call    ?Parse@Parser@@AEAAPEAUParseNode@@PEBGK@Z; Parser::Parse(ushort const *,ulong)
0x180018f3d  mov     r8, [r14+160h]
0x180018f44  mov     rdi, rax
0x180018f47  mov     qword ptr [r14+290h], 0
0x180018f52  mov     [rbp+var_8], rax
0x180018f56  mov     rbx, [r8+20h]
0x180018f5a  sub     rbx, [r8+10h]
0x180018f5e  mov     ecx, [r8+170h]
0x180018f65  mov     rdx, [r8+168h]
0x180018f6c  sub     ecx, edx
0x180018f6e  sar     rbx, 1
0x180018f71  mov     [r14+2A0h], ecx
0x180018f78  mov     qword ptr [r8+178h], 0
0x180018f83  mov     qword ptr [r8+170h], 0
0x180018f8e  mov     qword ptr [r8+168h], 0
0x180018f99  mov     rcx, [r14+160h]; this
0x180018fa0  mov     [r14+298h], rdx
0x180018fa7  call    ?Release@Scanner@@QEAAXXZ; Scanner::Release(void)
0x180018fac  mov     rax, [rbp+arg_40]
0x180018fb0  mov     rdx, rdi; struct ParseNode *
0x180018fb3  mov     r9d, [rbp+arg_30]; int
0x180018fb7  mov     rcx, r14; this
0x180018fba  mov     r8, [rbp+arg_28]; void *
0x180018fbe  mov     [rsp+50h+psz], rax; unsigned __int16 *
0x180018fc3  mov     [rsp+50h+len], ebx; int
0x180018fc7  mov     [rsp+50h+var_30], rsi; unsigned __int16 *
0x180018fcc  mov     qword ptr [r14+160h], 0
0x180018fd7  call    ?GenerateCode@Parser@@AEAAXPEAUParseNode@@PEAXJPEBGJ2@Z; Parser::GenerateCode(ParseNode *,void *,long,ushort const *,long,ushort const *)
0x180018fdc  mov     ecx, 10h; Size
0x180018fe1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018fe6  mov     rdx, rax
0x180018fe9  test    rax, rax
0x180018fec  jz      short loc_180019001
0x180018fee  mov     rcx, [r14+140h]
0x180018ff5  mov     [rax], rcx
0x180018ff8  mov     dword ptr [rax+8], 1
0x180018fff  jmp     short loc_180019003
0x180019001  xor     edx, edx
0x180019003  mov     rax, [rbp+arg_8]
0x180019007  mov     [rax], rdx
0x18001900a  test    rdx, rdx
0x18001900d  jnz     short loc_18001901D
0x18001900f  mov     edx, 3E9h; int
0x180019014  mov     rcx, r14; this
0x180019017  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18001901d  mov     qword ptr [r14+140h], 0
0x180019028  xor     ebx, ebx
0x18001902a  jmp     short loc_18001909D
0x18001902c  mov     rbx, [rbp+arg_0]
0x180019030  mov     rcx, [rbx+140h]; Block
0x180019037  mov     qword ptr [rbx+290h], 0
0x180019042  test    rcx, rcx
0x180019045  jz      short loc_180019058
0x180019047  call    cs:__imp_free
0x18001904d  mov     qword ptr [rbx+140h], 0
0x180019058  lea     rcx, [rbx+10h]; this
0x18001905c  call    ?FreeAll@NoRelAlloc@@QEAAXXZ; NoRelAlloc::FreeAll(void)
0x180019061  mov     rax, [rbp+arg_18]
0x180019065  lea     r9, [rbx+30h]; struct ErrHandler *
0x180019069  mov     r8, [rbx+160h]; struct Scanner *
0x180019070  mov     rdx, [rbp+arg_10]; struct COleScript *
0x180019074  mov     rcx, [rbp+arg_38]; this
0x180019078  mov     [rsp+50h+var_18], rax; unsigned __int16 *
0x18001907d  mov     rax, [rbp+arg_28]
0x180019081  mov     [rsp+50h+psz], rax; psz
0x180019086  mov     eax, [rbp+arg_30]
0x180019089  mov     [rsp+50h+len], eax; len
0x18001908d  mov     rax, [rbp+var_8]
0x180019091  mov     [rsp+50h+var_30], rax; struct ParseNode *
0x180019096  call    ?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z; CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)
0x18001909b  mov     ebx, eax
0x18001909d  mov     ecx, [rbp+NewValue]; NewValue
0x1800190a0  or      edx, 0FFFFFFFFh; Mask
0x1800190a3  call    cs:__imp__controlfp
0x1800190a9  mov     eax, ebx
0x1800190ab  add     rsp, 50h
0x1800190af  pop     r14
0x1800190b1  pop     rdi
0x1800190b2  pop     rsi
0x1800190b3  pop     rbx
0x1800190b4  pop     rbp
0x1800190b5  retn
```
