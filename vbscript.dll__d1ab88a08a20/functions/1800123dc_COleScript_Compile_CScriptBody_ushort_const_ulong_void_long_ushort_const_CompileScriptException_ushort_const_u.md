# COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *,ushort const *,ushort const *)

- ea: `0x1800123dc`
- end: `0x180012628`
- name: `?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@11@Z`
- size: `588`
- prototype: `int(COleScript *__hidden this, struct CScriptBody **, const unsigned __int16 *, unsigned int, void *, int, const unsigned __int16 *, struct CompileScriptException *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800566b4`
- `0x18006ba64`

## callees

- `0x18001176c`
- `0x18001199c`
- `0x1800123dc`
- `0x180013840`
- `0x1800139b4`
- `0x180013a1c`
- `0x180013cb8`
- `0x18001cb34`
- `0x18001eef0`
- `0x180046884`
- `0x180079490`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800125f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800125f5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800125d4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800125d4`

## pseudocode

```c
__int64 __fastcall COleScript::Compile(
        COleScript *this,
        struct CScriptBody **a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        CHAR *a5,
        UINT a6,
        const unsigned __int16 *a7,
        struct CompileScriptException *a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10)
{
  unsigned __int16 *v10; // rbx
  OLECHAR *v14; // rax
  const unsigned __int16 *v16; // r8
  int v17; // edi
  struct CScriptBody *v18; // rax
  struct CScriptBody *v19; // rdx
  ExecBody *v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  char *v23; // rax
  _QWORD *v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // ebx
  _QWORD *v27; // r9
  UINT v28; // eax
  ExecBody *v29; // [rsp+60h] [rbp-318h] BYREF
  _BYTE v30[704]; // [rsp+70h] [rbp-308h] BYREF

  v10 = 0;
  v29 = 0;
  if ( (a4 & 0x201) == 1 )
  {
    v14 = _SysAllocString(a3);
    v10 = v14;
    if ( !v14 )
      return 2147942414LL;
    v28 = SysStringLen(v14);
    RemoveHTMLCommentSuffix(v10, v28);
  }
  Parser::Parser((Parser *)v30);
  v17 = Parser::ParseSource((Parser *)v30, &v29, this, v16, a4, a5, a6, a8, a7, a9, a10);
  if ( v10 )
    SysFreeString(v10);
  if ( v17 < 0 )
  {
    if ( v17 == -2040119292 && *((int *)a8 + 16) >= 0 )
      *((_DWORD *)a8 + 16) = -2147467259;
    Parser::~Parser((Parser *)v30);
    return (unsigned int)v17;
  }
  else
  {
    Parser::~Parser((Parser *)v30);
    v18 = (struct CScriptBody *)operator new(0x50u);
    v19 = v18;
    if ( v18 )
    {
      v20 = v29;
      *(_DWORD *)v18 = 1;
      *((_QWORD *)v18 + 1) = 0;
      *((_QWORD *)v18 + 2) = 0;
      *((_QWORD *)v18 + 3) = 0;
      *((_QWORD *)v18 + 4) = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 37);
      *((_QWORD *)v18 + 5) = 0;
      *((_QWORD *)v18 + 6) = 0;
      *((_QWORD *)v18 + 7) = v20;
      _InterlockedIncrement((volatile signed __int32 *)v20 + 2);
      v21 = (__int64 *)*((_QWORD *)v18 + 7);
      v22 = *v21;
      *((_QWORD *)v19 + 8) = *v21;
      *((_QWORD *)v19 + 9) = v22;
      *a2 = v19;
      if ( (unsigned int)MUTX::Enter((COleScript *)((char *)this + 808)) )
      {
        v23 = (char *)*a2;
        v24 = (_QWORD *)((char *)this + 864);
        v25 = *((_QWORD *)this + 108);
        v26 = 0;
        v27 = (_QWORD *)((char *)*a2 + 40);
        *v27 = v25;
        if ( v25 )
          *(_QWORD *)(v25 + 48) = v27;
        *((_QWORD *)v23 + 6) = v24;
        *v24 = v23;
        MUTX::Leave((COleScript *)((char *)this + 808));
      }
      else
      {
        v26 = -2147467259;
      }
    }
    else
    {
      *a2 = 0;
      v26 = -2147024882;
    }
    ExecBody::Release(v29);
    return v26;
  }
}

```

## disassembly

```asm
0x1800123dc  push    rbx
0x1800123de  push    rbp
0x1800123df  push    rsi
0x1800123e0  push    rdi
0x1800123e1  push    r12
0x1800123e3  push    r14
0x1800123e5  push    r15
0x1800123e7  sub     rsp, 340h
0x1800123ee  mov     rax, cs:__security_cookie
0x1800123f5  xor     rax, rsp
0x1800123f8  mov     [rsp+378h+var_48], rax
0x180012400  mov     r15, [rsp+378h+arg_20]
0x180012408  mov     eax, r9d
0x18001240b  mov     r12, [rsp+378h+arg_30]
0x180012413  and     eax, 201h
0x180012418  mov     rbp, [rsp+378h+arg_38]
0x180012420  xor     ebx, ebx
0x180012422  mov     [rsp+378h+var_318], 0
0x18001242b  mov     edi, r9d
0x18001242e  mov     r14, rdx
0x180012431  mov     rsi, rcx
0x180012434  cmp     eax, 1
0x180012437  jnz     short loc_180012457
0x180012439  mov     rcx, r8; unsigned __int16 *
0x18001243c  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180012441  mov     rbx, rax
0x180012444  test    rax, rax
0x180012447  jnz     loc_1800125D1
0x18001244d  mov     eax, 8007000Eh
0x180012452  jmp     loc_18001258A
0x180012457  lea     rcx, [rsp+378h+var_308]; this
0x18001245c  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x180012461  mov     rax, [rsp+378h+arg_40]
0x180012469  lea     rdx, [rsp+378h+var_318]; struct ExecBody **
0x18001246e  mov     rcx, [rsp+378h+arg_48]
0x180012476  mov     r9, r8; unsigned __int16 *
0x180012479  mov     [rsp+378h+var_328], rcx; unsigned __int16 *
0x18001247e  mov     r8, rsi; struct COleScript *
0x180012481  mov     [rsp+378h+var_330], rax; unsigned __int16 *
0x180012486  lea     rcx, [rsp+378h+var_308]; this
0x18001248b  mov     eax, [rsp+378h+arg_28]
0x180012492  mov     [rsp+378h+var_338], r12; unsigned __int16 *
0x180012497  mov     [rsp+378h+var_340], rbp; struct CompileScriptException *
0x18001249c  mov     [rsp+378h+var_348], eax; UINT
0x1800124a0  mov     [rsp+378h+var_350], r15; LPCSTR
0x1800124a5  mov     [rsp+378h+var_358], edi; unsigned int
0x1800124a9  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)
0x1800124ae  mov     edi, eax
0x1800124b0  test    rbx, rbx
0x1800124b3  jnz     loc_1800125F2
0x1800124b9  test    edi, edi
0x1800124bb  js      loc_1800125BB
0x1800124c1  lea     rcx, [rsp+378h+var_308]; this
0x1800124c6  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x1800124cb  mov     ecx, 50h ; 'P'; Size
0x1800124d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800124d5  mov     rdx, rax
0x1800124d8  test    rax, rax
0x1800124db  jz      loc_1800125AD
0x1800124e1  mov     rcx, [rsp+378h+var_318]
0x1800124e6  mov     dword ptr [rax], 1
0x1800124ec  mov     qword ptr [rax+8], 0
0x1800124f4  mov     qword ptr [rax+10h], 0
0x1800124fc  mov     qword ptr [rax+18h], 0
0x180012504  mov     [rax+20h], rsi
0x180012508  lock inc dword ptr [rsi+94h]
0x18001250f  mov     qword ptr [rax+28h], 0
0x180012517  mov     qword ptr [rax+30h], 0
0x18001251f  mov     [rax+38h], rcx
0x180012523  lock inc dword ptr [rcx+8]
0x180012527  mov     rax, [rax+38h]
0x18001252b  lea     rdi, [rsi+328h]
0x180012532  mov     rcx, [rax]
0x180012535  mov     [rdx+40h], rcx
0x180012539  mov     [rdx+48h], rcx
0x18001253d  mov     rcx, rdi; this
0x180012540  mov     [r14], rdx
0x180012543  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180012548  test    eax, eax
0x18001254a  jz      loc_180012615
0x180012550  mov     rax, [r14]
0x180012553  lea     rdx, [rsi+360h]
0x18001255a  mov     r8, [rdx]
0x18001255d  xor     ebx, ebx
0x18001255f  lea     r9, [rax+28h]
0x180012563  mov     [r9], r8
0x180012566  test    r8, r8
0x180012569  jnz     loc_18001261F
0x18001256f  mov     [rax+30h], rdx
0x180012573  mov     rcx, rdi; this
0x180012576  mov     [rdx], rax
0x180012579  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18001257e  mov     rcx, [rsp+378h+var_318]; this
0x180012583  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x180012588  mov     eax, ebx
0x18001258a  mov     rcx, [rsp+378h+var_48]
0x180012592  xor     rcx, rsp; StackCookie
0x180012595  call    __security_check_cookie
0x18001259a  add     rsp, 340h
0x1800125a1  pop     r15
0x1800125a3  pop     r14
0x1800125a5  pop     r12
0x1800125a7  pop     rdi
0x1800125a8  pop     rsi
0x1800125a9  pop     rbp
0x1800125aa  pop     rbx
0x1800125ab  retn
0x1800125ad  mov     qword ptr [r14], 0
0x1800125b4  mov     ebx, 8007000Eh
0x1800125b9  jmp     short loc_18001257E
0x1800125bb  cmp     edi, 86664004h
0x1800125c1  jz      short loc_180012606
0x1800125c3  lea     rcx, [rsp+378h+var_308]; this
0x1800125c8  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x1800125cd  mov     eax, edi
0x1800125cf  jmp     short loc_18001258A
0x1800125d1  mov     rcx, rbx; pbstr
0x1800125d4  call    cs:__imp_SysStringLen
0x1800125db  nop     dword ptr [rax+rax+00h]
0x1800125e0  mov     edx, eax; unsigned __int64
0x1800125e2  mov     rcx, rbx; unsigned __int16 *
0x1800125e5  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x1800125ea  mov     r8, rbx
0x1800125ed  jmp     loc_180012457
0x1800125f2  mov     rcx, rbx; bstrString
0x1800125f5  call    cs:__imp_SysFreeString
0x1800125fc  nop     dword ptr [rax+rax+00h]
0x180012601  jmp     loc_1800124B9
0x180012606  cmp     dword ptr [rbp+40h], 0
0x18001260a  jl      short loc_1800125C3
0x18001260c  mov     dword ptr [rbp+40h], 80004005h
0x180012613  jmp     short loc_1800125C3
0x180012615  mov     ebx, 80004005h
0x18001261a  jmp     loc_18001257E
0x18001261f  mov     [r8+30h], r9
0x180012623  jmp     loc_18001256F
```
