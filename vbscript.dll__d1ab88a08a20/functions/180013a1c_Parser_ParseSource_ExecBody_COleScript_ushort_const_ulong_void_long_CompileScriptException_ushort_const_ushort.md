# Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)

- ea: `0x180013a1c`
- end: `0x180013caf`
- name: `?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z`
- size: `659`
- prototype: `__int64 __fastcall(Parser *__hidden this, struct ExecBody **, struct COleScript *, const unsigned __int16 *, unsigned int, LPCSTR, UINT, struct CompileScriptException *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180011bac`
- `0x1800123dc`
- `0x180012c58`

## callees

- `0x18000b714`
- `0x180011b30`
- `0x180013a1c`
- `0x180013dd8`
- `0x18002a1ac`
- `0x18002a798`
- `0x18002f95c`
- `0x1800341b8`
- `0x180040b38`
- `0x180046884`
- `0x1800793a6`
- `0x180079436`

## import_xrefs

- `msvcrt!_controlfp` at `0x180013a51`
- `msvcrt!_controlfp` at `0x180013a6a`
- `msvcrt!_controlfp` at `0x180013c95`
- `msvcrt!_controlfp` at `0x180013a51`
- `msvcrt!_controlfp` at `0x180013a6a`
- `msvcrt!_controlfp` at `0x180013c95`
- `msvcrt!free` at `0x180013c33`
- `msvcrt!free` at `0x180013c33`

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
        const unsigned __int16 *a9,
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
0x180013a1c  mov     rax, rsp
0x180013a1f  mov     [rax+20h], r9
0x180013a23  mov     [rax+18h], r8
0x180013a27  mov     [rax+10h], rdx
0x180013a2b  mov     [rax+8], rcx
0x180013a2f  push    rbp
0x180013a30  push    rbx
0x180013a31  push    rsi
0x180013a32  push    rdi
0x180013a33  push    r14
0x180013a35  mov     rbp, rsp
0x180013a38  sub     rsp, 50h
0x180013a3c  mov     rdi, rdx
0x180013a3f  mov     [rbp+var_8], 0
0x180013a47  mov     rsi, rcx
0x180013a4a  xor     edx, edx; Mask
0x180013a4c  xor     ecx, ecx; NewValue
0x180013a4e  mov     rbx, r8
0x180013a51  call    cs:__imp__controlfp
0x180013a58  nop     dword ptr [rax+rax+00h]
0x180013a5d  mov     edx, 30F031Fh; Mask
0x180013a62  mov     ecx, 1Fh; NewValue
0x180013a67  mov     [rbp+NewValue], eax
0x180013a6a  call    cs:__imp__controlfp
0x180013a71  nop     dword ptr [rax+rax+00h]
0x180013a76  mov     rax, [rbx+88h]
0x180013a7d  mov     rcx, [rbp+arg_38]; void *
0x180013a81  mov     [rsi], rax
0x180013a84  mov     rax, [rbp+arg_48]
0x180013a88  mov     [rsi+1E8h], rax
0x180013a8f  mov     qword ptr [rdi], 0
0x180013a96  test    rcx, rcx
0x180013a99  jz      short loc_180013AA6
0x180013a9b  xor     edx, edx; Val
0x180013a9d  lea     r8d, [rdx+68h]; Size
0x180013aa1  call    memset_0
0x180013aa6  lea     rcx, [rsi+30h]; Buf
0x180013aaa  mov     rdx, rsp
0x180013aad  call    _setjmp_0
0x180013ab2  test    eax, eax
0x180013ab4  jnz     loc_180013C18
0x180013aba  mov     r14, [rbp+arg_0]
0x180013abe  lea     rdx, [r14+30h]; struct ErrHandler *
0x180013ac2  call    ?Create@HashTbl@@SAPEAV1@IPEAVErrHandler@@@Z; HashTbl::Create(uint,ErrHandler *)
0x180013ac7  mov     [r14+8], rax
0x180013acb  test    rax, rax
0x180013ace  jnz     short loc_180013ADE
0x180013ad0  mov     edx, 3E9h; int
0x180013ad5  mov     rcx, r14; this
0x180013ad8  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180013ade  lea     rdx, [r14+150h]; struct Token *
0x180013ae5  mov     rcx, rax; struct HashTbl *
0x180013ae8  lea     r8, [r14+30h]; struct ErrHandler *
0x180013aec  call    ?Create@Scanner@@SAPEAV1@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Create(HashTbl *,Token *,ErrHandler *)
0x180013af1  mov     [r14+160h], rax
0x180013af8  mov     rcx, r14; this
0x180013afb  test    rax, rax
0x180013afe  jnz     short loc_180013B0B
0x180013b00  mov     edx, 3E9h; int
0x180013b05  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180013b0b  mov     rax, [rbp+arg_50]
0x180013b12  mov     rsi, [rbp+arg_18]
0x180013b16  mov     r8d, [rbp+arg_20]; unsigned int
0x180013b1a  mov     rdx, rsi; unsigned __int16 *
0x180013b1d  mov     [r14+290h], rax
0x180013b24  call    ?Parse@Parser@@AEAAPEAUParseNode@@PEBGK@Z; Parser::Parse(ushort const *,ulong)
0x180013b29  mov     r8, [r14+160h]
0x180013b30  mov     rdi, rax
0x180013b33  mov     qword ptr [r14+290h], 0
0x180013b3e  mov     [rbp+var_8], rax
0x180013b42  mov     rbx, [r8+20h]
0x180013b46  sub     rbx, [r8+10h]
0x180013b4a  mov     ecx, [r8+170h]
0x180013b51  mov     rdx, [r8+168h]
0x180013b58  sub     ecx, edx
0x180013b5a  sar     rbx, 1
0x180013b5d  mov     [r14+2A0h], ecx
0x180013b64  mov     qword ptr [r8+178h], 0
0x180013b6f  mov     qword ptr [r8+170h], 0
0x180013b7a  mov     qword ptr [r8+168h], 0
0x180013b85  mov     rcx, [r14+160h]; this
0x180013b8c  mov     [r14+298h], rdx
0x180013b93  call    ?Release@Scanner@@QEAAXXZ; Scanner::Release(void)
0x180013b98  mov     rax, [rbp+arg_40]
0x180013b9c  mov     rdx, rdi; struct ParseNode *
0x180013b9f  mov     r9d, [rbp+arg_30]; int
0x180013ba3  mov     rcx, r14; this
0x180013ba6  mov     r8, [rbp+arg_28]; void *
0x180013baa  mov     [rsp+50h+psz], rax; unsigned __int16 *
0x180013baf  mov     [rsp+50h+len], ebx; int
0x180013bb3  mov     [rsp+50h+var_30], rsi; unsigned __int16 *
0x180013bb8  mov     qword ptr [r14+160h], 0
0x180013bc3  call    ?GenerateCode@Parser@@AEAAXPEAUParseNode@@PEAXJPEBGJ2@Z; Parser::GenerateCode(ParseNode *,void *,long,ushort const *,long,ushort const *)
0x180013bc8  mov     ecx, 10h; Size
0x180013bcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013bd2  mov     rdx, rax
0x180013bd5  test    rax, rax
0x180013bd8  jz      short loc_180013BED
0x180013bda  mov     rcx, [r14+140h]
0x180013be1  mov     [rax], rcx
0x180013be4  mov     dword ptr [rax+8], 1
0x180013beb  jmp     short loc_180013BEF
0x180013bed  xor     edx, edx
0x180013bef  mov     rax, [rbp+arg_8]
0x180013bf3  mov     [rax], rdx
0x180013bf6  test    rdx, rdx
0x180013bf9  jnz     short loc_180013C09
0x180013bfb  mov     edx, 3E9h; int
0x180013c00  mov     rcx, r14; this
0x180013c03  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180013c09  mov     qword ptr [r14+140h], 0
0x180013c14  xor     ebx, ebx
0x180013c16  jmp     short loc_180013C8F
0x180013c18  mov     rbx, [rbp+arg_0]
0x180013c1c  mov     rcx, [rbx+140h]; Block
0x180013c23  mov     qword ptr [rbx+290h], 0
0x180013c2e  test    rcx, rcx
0x180013c31  jz      short loc_180013C4A
0x180013c33  call    cs:__imp_free
0x180013c3a  nop     dword ptr [rax+rax+00h]
0x180013c3f  mov     qword ptr [rbx+140h], 0
0x180013c4a  lea     rcx, [rbx+10h]; this
0x180013c4e  call    ?FreeAll@NoRelAlloc@@QEAAXXZ; NoRelAlloc::FreeAll(void)
0x180013c53  mov     rax, [rbp+arg_18]
0x180013c57  lea     r9, [rbx+30h]; struct ErrHandler *
0x180013c5b  mov     r8, [rbx+160h]; struct Scanner *
0x180013c62  mov     rdx, [rbp+arg_10]; struct COleScript *
0x180013c66  mov     rcx, [rbp+arg_38]; this
0x180013c6a  mov     [rsp+50h+var_18], rax; unsigned __int16 *
0x180013c6f  mov     rax, [rbp+arg_28]
0x180013c73  mov     [rsp+50h+psz], rax; psz
0x180013c78  mov     eax, [rbp+arg_30]
0x180013c7b  mov     [rsp+50h+len], eax; len
0x180013c7f  mov     rax, [rbp+var_8]
0x180013c83  mov     [rsp+50h+var_30], rax; struct ParseNode *
0x180013c88  call    ?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z; CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)
0x180013c8d  mov     ebx, eax
0x180013c8f  mov     ecx, [rbp+NewValue]; NewValue
0x180013c92  or      edx, 0FFFFFFFFh; Mask
0x180013c95  call    cs:__imp__controlfp
0x180013c9c  nop     dword ptr [rax+rax+00h]
0x180013ca1  mov     eax, ebx
0x180013ca3  add     rsp, 50h
0x180013ca7  pop     r14
0x180013ca9  pop     rdi
0x180013caa  pop     rsi
0x180013cab  pop     rbx
0x180013cac  pop     rbp
0x180013cad  retn
```
