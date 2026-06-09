# COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *,ushort const *,ushort const *)

- ea: `0x18001787c`
- end: `0x180017abb`
- name: `?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@11@Z`
- size: `575`
- prototype: `int(COleScript *__hidden this, struct CScriptBody **, const unsigned __int16 *, unsigned int, void *, int, const unsigned __int16 *, struct CompileScriptException *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180054d74`
- `0x180069914`

## callees

- `0x18001787c`
- `0x180018c78`
- `0x180018dd4`
- `0x180018e3c`
- `0x1800190bc`
- `0x180022ce0`
- `0x1800238f4`
- `0x18003512c`
- `0x18003e450`
- `0x180045490`
- `0x1800767a0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180017a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017a8e`
- `OLEAUT32!__imp_SysStringLen` at `0x180017a73`
- `OLEAUT32!__imp_SysStringLen` at `0x180017a73`

## pseudocode

```c
__int64 __fastcall COleScript::Compile(
        COleScript *this,
        struct CScriptBody **a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        CHAR *a5,
        UINT a6,
        unsigned __int16 *a7,
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
0x18001787c  push    rbx
0x18001787e  push    rbp
0x18001787f  push    rsi
0x180017880  push    rdi
0x180017881  push    r12
0x180017883  push    r14
0x180017885  push    r15
0x180017887  sub     rsp, 340h
0x18001788e  mov     rax, cs:__security_cookie
0x180017895  xor     rax, rsp
0x180017898  mov     [rsp+378h+var_48], rax
0x1800178a0  mov     r15, [rsp+378h+arg_20]
0x1800178a8  mov     eax, r9d
0x1800178ab  mov     r12, [rsp+378h+arg_30]
0x1800178b3  and     eax, 201h
0x1800178b8  mov     rbp, [rsp+378h+arg_38]
0x1800178c0  xor     ebx, ebx
0x1800178c2  mov     [rsp+378h+var_318], 0
0x1800178cb  mov     edi, r9d
0x1800178ce  mov     r14, rdx
0x1800178d1  mov     rsi, rcx
0x1800178d4  cmp     eax, 1
0x1800178d7  jnz     short loc_1800178F7
0x1800178d9  mov     rcx, r8; unsigned __int16 *
0x1800178dc  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x1800178e1  mov     rbx, rax
0x1800178e4  test    rax, rax
0x1800178e7  jnz     loc_180017A70
0x1800178ed  mov     eax, 8007000Eh
0x1800178f2  jmp     loc_180017A2A
0x1800178f7  lea     rcx, [rsp+378h+var_308]; this
0x1800178fc  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x180017901  mov     rax, [rsp+378h+arg_40]
0x180017909  lea     rdx, [rsp+378h+var_318]; struct ExecBody **
0x18001790e  mov     rcx, [rsp+378h+arg_48]
0x180017916  mov     r9, r8; unsigned __int16 *
0x180017919  mov     [rsp+378h+var_328], rcx; unsigned __int16 *
0x18001791e  mov     r8, rsi; struct COleScript *
0x180017921  mov     [rsp+378h+var_330], rax; unsigned __int16 *
0x180017926  lea     rcx, [rsp+378h+var_308]; this
0x18001792b  mov     eax, [rsp+378h+arg_28]
0x180017932  mov     [rsp+378h+var_338], r12; unsigned __int16 *
0x180017937  mov     [rsp+378h+var_340], rbp; struct CompileScriptException *
0x18001793c  mov     [rsp+378h+var_348], eax; UINT
0x180017940  mov     [rsp+378h+var_350], r15; LPCSTR
0x180017945  mov     [rsp+378h+var_358], edi; unsigned int
0x180017949  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)
0x18001794e  mov     edi, eax
0x180017950  test    rbx, rbx
0x180017953  jnz     loc_180017A8B
0x180017959  test    edi, edi
0x18001795b  js      loc_180017A5A
0x180017961  lea     rcx, [rsp+378h+var_308]; this
0x180017966  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001796b  mov     ecx, 50h ; 'P'; Size
0x180017970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017975  mov     rdx, rax
0x180017978  test    rax, rax
0x18001797b  jz      loc_180017A4C
0x180017981  mov     rcx, [rsp+378h+var_318]
0x180017986  mov     dword ptr [rax], 1
0x18001798c  mov     qword ptr [rax+8], 0
0x180017994  mov     qword ptr [rax+10h], 0
0x18001799c  mov     qword ptr [rax+18h], 0
0x1800179a4  mov     [rax+20h], rsi
0x1800179a8  lock inc dword ptr [rsi+94h]
0x1800179af  mov     qword ptr [rax+28h], 0
0x1800179b7  mov     qword ptr [rax+30h], 0
0x1800179bf  mov     [rax+38h], rcx
0x1800179c3  lock inc dword ptr [rcx+8]
0x1800179c7  mov     rax, [rax+38h]
0x1800179cb  lea     rdi, [rsi+328h]
0x1800179d2  mov     rcx, [rax]
0x1800179d5  mov     [rdx+40h], rcx
0x1800179d9  mov     [rdx+48h], rcx
0x1800179dd  mov     rcx, rdi; this
0x1800179e0  mov     [r14], rdx
0x1800179e3  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x1800179e8  test    eax, eax
0x1800179ea  jz      loc_180017AA8
0x1800179f0  mov     rax, [r14]
0x1800179f3  lea     rdx, [rsi+360h]
0x1800179fa  mov     r8, [rdx]
0x1800179fd  xor     ebx, ebx
0x1800179ff  lea     r9, [rax+28h]
0x180017a03  mov     [r9], r8
0x180017a06  test    r8, r8
0x180017a09  jnz     loc_180017AB2
0x180017a0f  mov     [rax+30h], rdx
0x180017a13  mov     rcx, rdi; this
0x180017a16  mov     [rdx], rax
0x180017a19  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180017a1e  mov     rcx, [rsp+378h+var_318]; this
0x180017a23  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x180017a28  mov     eax, ebx
0x180017a2a  mov     rcx, [rsp+378h+var_48]
0x180017a32  xor     rcx, rsp; StackCookie
0x180017a35  call    __security_check_cookie
0x180017a3a  add     rsp, 340h
0x180017a41  pop     r15
0x180017a43  pop     r14
0x180017a45  pop     r12
0x180017a47  pop     rdi
0x180017a48  pop     rsi
0x180017a49  pop     rbp
0x180017a4a  pop     rbx
0x180017a4b  retn
0x180017a4c  mov     qword ptr [r14], 0
0x180017a53  mov     ebx, 8007000Eh
0x180017a58  jmp     short loc_180017A1E
0x180017a5a  cmp     edi, 86664004h
0x180017a60  jz      short loc_180017A99
0x180017a62  lea     rcx, [rsp+378h+var_308]; this
0x180017a67  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x180017a6c  mov     eax, edi
0x180017a6e  jmp     short loc_180017A2A
0x180017a70  mov     rcx, rbx; pbstr
0x180017a73  call    cs:__imp_SysStringLen
0x180017a79  mov     edx, eax; unsigned __int64
0x180017a7b  mov     rcx, rbx; unsigned __int16 *
0x180017a7e  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x180017a83  mov     r8, rbx
0x180017a86  jmp     loc_1800178F7
0x180017a8b  mov     rcx, rbx; bstrString
0x180017a8e  call    cs:__imp_SysFreeString
0x180017a94  jmp     loc_180017959
0x180017a99  cmp     dword ptr [rbp+40h], 0
0x180017a9d  jl      short loc_180017A62
0x180017a9f  mov     dword ptr [rbp+40h], 80004005h
0x180017aa6  jmp     short loc_180017A62
0x180017aa8  mov     ebx, 80004005h
0x180017aad  jmp     loc_180017A1E
0x180017ab2  mov     [r8+30h], r9
0x180017ab6  jmp     loc_180017A0F
```
