# COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,ushort const *)

- ea: `0x1800180dc`
- end: `0x180018609`
- name: `?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@0@Z`
- size: `1325`
- prototype: `__int64 __usercall@<rax>(COleScript *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct SRCINFO *@<r9>, wchar_t *String2, const unsigned __int16 *, struct tagEXCEPINFO *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x180017b40`
- `0x180051f0c`

## callees

- `0x1800180dc`
- `0x180018610`
- `0x180018b50`
- `0x180018c78`
- `0x180018dd4`
- `0x180018e3c`
- `0x1800190bc`
- `0x180020398`
- `0x180022ce0`
- `0x180022e04`
- `0x180022e44`
- `0x180022ea0`
- `0x1800238f4`
- `0x18002bc28`
- `0x18003512c`
- `0x180037f74`
- `0x18003e450`
- `0x180041984`
- `0x180041fa4`
- `0x180045490`
- `0x180053b64`
- `0x180054ccc`
- `0x18005f498`
- `0x18005f970`
- `0x18007672e`
- `0x18007673a`
- `0x180076746`
- `0x1800767a0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018423`
- `OLEAUT32!__imp_SysFreeString` at `0x18001842d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180018529`
- `OLEAUT32!__imp_SysFreeString` at `0x180018423`
- `OLEAUT32!__imp_SysFreeString` at `0x18001842d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800184c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180018529`
- `OLEAUT32!__imp_SysStringLen` at `0x1800181ea`
- `OLEAUT32!__imp_SysStringLen` at `0x1800181ea`

## pseudocode

```c
__int64 __fastcall COleScript::CreateScriptBody(
        COleScript *this,
        unsigned __int16 *a2,
        int a3,
        struct SRCINFO *a4,
        wchar_t *String2,
        const unsigned __int16 *a6,
        struct tagEXCEPINFO *a7,
        const unsigned __int16 *a8)
{
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // esi
  OLECHAR *v15; // rax
  unsigned __int16 *v16; // rbx
  UINT v17; // eax
  int v18; // edi
  struct CScriptBody *v19; // rbx
  ExecBody *v20; // rax
  __int64 *v21; // rax
  __int64 v22; // rcx
  int v23; // esi
  struct CScriptBody **v24; // rax
  __int64 v25; // rcx
  int *v26; // rdi
  int v27; // r13d
  size_t v28; // r12
  int v29; // r15d
  struct tagEXCEPINFO *v30; // rax
  unsigned int scode; // ebx
  CActiveScriptError *v33; // rbx
  struct IActiveScriptError *v34; // rdx
  ExecBody *v35; // [rsp+60h] [rbp-A0h] BYREF
  struct CActiveScriptError *Src; // [rsp+68h] [rbp-98h] BYREF
  struct CScriptBody *v37; // [rsp+70h] [rbp-90h]
  struct tagEXCEPINFO *v38; // [rsp+78h] [rbp-88h]
  char v39[8]; // [rsp+80h] [rbp-80h] BYREF
  struct tagEXCEPINFO v40; // [rsp+88h] [rbp-78h] BYREF
  CActiveScriptError *v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  BSTR bstrString; // [rsp+D8h] [rbp-28h]
  BSTR v44; // [rsp+E0h] [rbp-20h]
  _BYTE v45[704]; // [rsp+F0h] [rbp-10h] BYREF

  v38 = a7;
  HIDWORD(Src) = *((_DWORD *)a4 + 6);
  v37 = 0;
  if ( (a3 & 0x60) == 0x60 )
    return 2147942487LL;
  v12 = ComputeGrfscr(String2);
  v13 = 2;
  v14 = v12;
  if ( (a3 & 0x40) != 0 )
    v13 = 3;
  LODWORD(Src) = v13;
  if ( (a3 & 0x80) != 0 )
  {
    v13 |= 8u;
    LODWORD(Src) = v13;
  }
  if ( (a3 & 0x80000020) == 0x80000020 )
  {
    v14 = v12 | 2;
    LODWORD(Src) = v13 | 4;
  }
  if ( (a3 & 0x80) != 0 )
    *((_DWORD *)a4 + 7) |= 1u;
  if ( (a3 & 0x40000000) != 0 )
    *((_DWORD *)a4 + 7) |= 2u;
  memset_0(v39, 0, 0x50u);
  v42 = 0;
  bstrString = 0;
  v44 = 0;
  v35 = 0;
  if ( (v14 & 0x201) == 1 )
  {
    v15 = _SysAllocString(a2);
    v16 = v15;
    if ( !v15 )
    {
      v23 = -2147024882;
      goto LABEL_40;
    }
    v17 = SysStringLen(v15);
    RemoveHTMLCommentSuffix(v16, v17);
    a2 = v16;
  }
  else
  {
    v16 = 0;
  }
  Parser::Parser((Parser *)v45);
  v18 = Parser::ParseSource(
          (Parser *)v45,
          &v35,
          this,
          a2,
          v14,
          (LPCSTR)a4,
          0x20u,
          (struct CompileScriptException *)v39,
          a6,
          0,
          a8);
  if ( v16 )
    SysFreeString(v16);
  if ( v18 < 0 )
  {
    if ( v18 == -2040119292 && v40.scode >= 0 )
      v40.scode = -2147467259;
    Parser::~Parser((Parser *)v45);
    v23 = v18;
    LODWORD(v35) = v18;
  }
  else
  {
    Parser::~Parser((Parser *)v45);
    v19 = (struct CScriptBody *)operator new(0x50u);
    if ( v19 )
    {
      v20 = v35;
      *(_DWORD *)v19 = 1;
      *((_QWORD *)v19 + 1) = 0;
      *((_QWORD *)v19 + 2) = 0;
      *((_QWORD *)v19 + 3) = 0;
      *((_QWORD *)v19 + 4) = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 37);
      *((_QWORD *)v19 + 5) = 0;
      *((_QWORD *)v19 + 6) = 0;
      *((_QWORD *)v19 + 7) = v20;
      _InterlockedIncrement((volatile signed __int32 *)v20 + 2);
      v21 = (__int64 *)*((_QWORD *)v19 + 7);
      v22 = *v21;
      *((_QWORD *)v19 + 8) = *v21;
      *((_QWORD *)v19 + 9) = v22;
    }
    else
    {
      v19 = 0;
    }
    v37 = v19;
    if ( v19 )
    {
      if ( (unsigned int)MUTX::Enter((COleScript *)((char *)this + 808)) )
      {
        v24 = (struct CScriptBody **)((char *)this + 864);
        v23 = 0;
        v25 = *((_QWORD *)this + 108);
        *((_QWORD *)v19 + 5) = v25;
        if ( v25 )
          *(_QWORD *)(v25 + 48) = (char *)v19 + 40;
        *((_QWORD *)v19 + 6) = v24;
        *v24 = v19;
        MUTX::Leave((COleScript *)((char *)this + 808));
      }
      else
      {
        v23 = -2147467259;
      }
    }
    else
    {
      v23 = -2147024882;
    }
    v18 = v23;
    ExecBody::Release(v35);
    LODWORD(v35) = v23;
    if ( v23 >= 0 )
    {
      if ( !(unsigned int)COleScript::DisableInterrupts(this) )
      {
        CompileScriptException::~CompileScriptException((CompileScriptException *)v39);
        return 2147500037LL;
      }
      if ( (unsigned int)COleScript::FDebuggerEnabled(this) )
      {
        v23 = COleScript::DbgRegisterScriptBlock(this, v19);
        if ( v23 < 0 )
          goto LABEL_38;
      }
      v26 = (int *)*((_QWORD *)this + 82);
      if ( !v26 )
      {
        v26 = (int *)operator new(0x20u);
        if ( !v26 )
        {
          *((_QWORD *)this + 82) = 0;
          goto LABEL_66;
        }
        v26[2] = 1;
        *(_QWORD *)v26 = &GL::`vftable';
        v26[3] = 16;
        *((_QWORD *)v26 + 2) = 0;
        *((_QWORD *)v26 + 3) = 0;
        *((_QWORD *)this + 82) = v26;
      }
      v27 = v26[7];
      v28 = v26[3];
      v29 = v28 * (v27 + 1);
      if ( v29 <= v26[6] || (unsigned int)GL::FEnsureSize((GL *)v26, v29) )
      {
        v30 = (struct tagEXCEPINFO *)(v27 * (int)v28 + *((_QWORD *)v26 + 2));
        v38 = v30;
        if ( v27 < v26[7] )
        {
          memmove_0((char *)v30 + v28, v30, v29 - v27 * (int)v28 - (int)v28);
          v30 = v38;
        }
        memcpy_0(v30, &Src, v28);
        ++v26[7];
        _InterlockedIncrement((volatile signed __int32 *)v19);
        goto LABEL_38;
      }
LABEL_66:
      v23 = -2147024882;
LABEL_38:
      COleScript::EnableInterrupts(this);
      if ( v19 )
        CScriptBody::Release(v19);
      goto LABEL_40;
    }
  }
  if ( v18 != -2040119292 )
  {
LABEL_40:
    SysFreeString(bstrString);
    SysFreeString(v44);
    FreeExcepInfo(&v40);
    if ( v41 )
      CActiveScriptError::Release(v41);
    return (unsigned int)v23;
  }
  Src = 0;
  if ( (int)CompileScriptException::GetActiveScriptError((CompileScriptException *)v39, &Src) >= 0 )
  {
    v33 = Src;
    v34 = (struct IActiveScriptError *)((char *)Src + 8);
    if ( !Src )
      v34 = 0;
    if ( (unsigned int)COleScript::OnScriptError(this, v34) )
    {
      CompileScriptException::GetError((CompileScriptException *)v39, (int *)&v35, v38);
      v23 = (int)v35;
    }
    else
    {
      ScriptException::DetachActiveScriptError((ScriptException *)v39);
      v23 = -2147352319;
    }
    CActiveScriptError::Release(v33);
    goto LABEL_40;
  }
  scode = v40.scode;
  SysFreeString(bstrString);
  SysFreeString(v44);
  FreeExcepInfo(&v40);
  if ( v41 )
    CActiveScriptError::Release(v41);
  return scode;
}

```

## disassembly

```asm
0x1800180dc  mov     [rsp-8+arg_10], rbx
0x1800180e1  push    rbp
0x1800180e2  push    rsi
0x1800180e3  push    rdi
0x1800180e4  push    r12
0x1800180e6  push    r13
0x1800180e8  push    r14
0x1800180ea  push    r15
0x1800180ec  lea     rbp, [rsp-2C0h]
0x1800180f4  sub     rsp, 3C0h
0x1800180fb  mov     rax, cs:__security_cookie
0x180018102  xor     rax, rsp
0x180018105  mov     [rbp+2F0h+var_40], rax
0x18001810c  mov     rax, [rbp+2F0h+arg_30]
0x180018113  mov     r14, rcx
0x180018116  mov     rcx, [rbp+2F0h+String2]; String2
0x18001811d  mov     rdi, r9
0x180018120  mov     r12, [rbp+2F0h+arg_28]
0x180018127  mov     ebx, r8d
0x18001812a  mov     r13, [rbp+2F0h+arg_38]
0x180018131  mov     r15, rdx
0x180018134  mov     [rsp+3F0h+var_378], rax
0x180018139  mov     eax, [r9+18h]
0x18001813d  mov     dword ptr [rsp+3F0h+Src+4], eax
0x180018141  mov     eax, r8d
0x180018144  and     eax, 60h
0x180018147  mov     [rsp+3F0h+var_380], 0
0x180018150  cmp     al, 60h ; '`'
0x180018152  jz      loc_1800184EF
0x180018158  call    ?ComputeGrfscr@@YAKPEBG@Z; ComputeGrfscr(ushort const *)
0x18001815d  mov     ecx, 2
0x180018162  test    bl, 40h
0x180018165  mov     esi, eax
0x180018167  mov     edx, ebx
0x180018169  lea     eax, [rcx+1]
0x18001816c  cmovnz  ecx, eax
0x18001816f  mov     dword ptr [rsp+3F0h+Src], ecx
0x180018173  and     edx, 80h
0x180018179  jnz     loc_1800184F9
0x18001817f  mov     r8d, 80000020h
0x180018185  mov     eax, ebx
0x180018187  and     eax, r8d
0x18001818a  cmp     eax, r8d
0x18001818d  jz      loc_180018505
0x180018193  test    edx, edx
0x180018195  jnz     loc_180018514
0x18001819b  bt      ebx, 1Eh
0x18001819f  jb      loc_18001851D
0x1800181a5  xor     edx, edx; Val
0x1800181a7  lea     rcx, [rbp+2F0h+var_370]; void *
0x1800181ab  lea     r8d, [rdx+50h]; Size
0x1800181af  call    memset_0
0x1800181b4  xor     ecx, ecx
0x1800181b6  mov     eax, esi
0x1800181b8  and     eax, 201h
0x1800181bd  mov     [rbp+2F0h+var_320], rcx
0x1800181c1  mov     [rbp+2F0h+bstrString], rcx
0x1800181c5  mov     [rbp+2F0h+var_310], rcx
0x1800181c9  mov     [rsp+3F0h+var_390], rcx
0x1800181ce  cmp     eax, 1
0x1800181d1  jnz     short loc_1800181FF
0x1800181d3  mov     rcx, r15; unsigned __int16 *
0x1800181d6  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x1800181db  mov     rbx, rax
0x1800181de  test    rax, rax
0x1800181e1  jz      loc_1800184E5
0x1800181e7  mov     rcx, rax; pbstr
0x1800181ea  call    cs:__imp_SysStringLen
0x1800181f0  mov     edx, eax; unsigned __int64
0x1800181f2  mov     rcx, rbx; unsigned __int16 *
0x1800181f5  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x1800181fa  mov     r15, rbx
0x1800181fd  jmp     short loc_180018202
0x1800181ff  mov     rbx, rcx
0x180018202  lea     rcx, [rbp+2F0h+var_300]; this
0x180018206  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x18001820b  mov     [rsp+3F0h+var_3A0], r13; unsigned __int16 *
0x180018210  lea     rax, [rbp+2F0h+var_370]
0x180018214  xor     r13d, r13d
0x180018217  lea     rdx, [rsp+3F0h+var_390]; struct ExecBody **
0x18001821c  mov     [rsp+3F0h+var_3A8], r13; unsigned __int16 *
0x180018221  lea     rcx, [rbp+2F0h+var_300]; this
0x180018225  mov     [rsp+3F0h+var_3B0], r12; unsigned __int16 *
0x18001822a  mov     r9, r15; unsigned __int16 *
0x18001822d  mov     [rsp+3F0h+var_3B8], rax; struct CompileScriptException *
0x180018232  mov     r8, r14; struct COleScript *
0x180018235  lea     r12d, [r13+20h]
0x180018239  mov     [rsp+3F0h+var_3C0], r12d; UINT
0x18001823e  mov     [rsp+3F0h+var_3C8], rdi; LPCSTR
0x180018243  mov     [rsp+3F0h+var_3D0], esi; unsigned int
0x180018247  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)
0x18001824c  mov     edi, eax
0x18001824e  test    rbx, rbx
0x180018251  jnz     loc_180018526
0x180018257  mov     r15d, 86664004h
0x18001825d  test    edi, edi
0x18001825f  js      loc_18001847D
0x180018265  lea     rcx, [rbp+2F0h+var_300]; this
0x180018269  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001826e  mov     ecx, 50h ; 'P'; Size
0x180018273  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018278  mov     rbx, rax
0x18001827b  test    rax, rax
0x18001827e  jz      loc_180018475
0x180018284  mov     rax, [rsp+3F0h+var_390]
0x180018289  mov     dword ptr [rbx], 1
0x18001828f  mov     [rbx+8], r13
0x180018293  mov     [rbx+10h], r13
0x180018297  mov     [rbx+18h], r13
0x18001829b  mov     [rbx+20h], r14
0x18001829f  lock inc dword ptr [r14+94h]
0x1800182a7  mov     [rbx+28h], r13
0x1800182ab  mov     [rbx+30h], r13
0x1800182af  mov     [rbx+38h], rax
0x1800182b3  lock inc dword ptr [rax+8]
0x1800182b7  mov     rax, [rbx+38h]
0x1800182bb  mov     rcx, [rax]
0x1800182be  mov     [rbx+40h], rcx
0x1800182c2  mov     [rbx+48h], rcx
0x1800182c6  mov     [rsp+3F0h+var_380], rbx
0x1800182cb  test    rbx, rbx
0x1800182ce  jnz     short loc_1800182D7
0x1800182d0  mov     esi, 8007000Eh
0x1800182d5  jmp     short loc_18001831A
0x1800182d7  lea     rdi, [r14+328h]
0x1800182de  mov     rcx, rdi; this
0x1800182e1  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x1800182e6  test    eax, eax
0x1800182e8  jz      loc_18001854A
0x1800182ee  lea     rax, [r14+360h]
0x1800182f5  mov     esi, r13d
0x1800182f8  mov     rcx, [rax]
0x1800182fb  lea     rdx, [rbx+28h]
0x1800182ff  mov     [rdx], rcx
0x180018302  test    rcx, rcx
0x180018305  jnz     loc_180018554
0x18001830b  mov     [rbx+30h], rax
0x18001830f  mov     rcx, rdi; this
0x180018312  mov     [rax], rbx
0x180018315  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18001831a  mov     rcx, [rsp+3F0h+var_390]; this
0x18001831f  mov     edi, esi
0x180018321  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x180018326  mov     dword ptr [rsp+3F0h+var_390], esi
0x18001832a  test    esi, esi
0x18001832c  js      loc_180018495
0x180018332  mov     rcx, r14; this
0x180018335  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001833a  test    eax, eax
0x18001833c  jz      loc_1800185B4
0x180018342  mov     rcx, r14; this
0x180018345  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x18001834a  test    eax, eax
0x18001834c  jnz     loc_1800185C7
0x180018352  mov     rdi, [r14+290h]
0x180018359  test    rdi, rdi
0x18001835c  jnz     short loc_180018399
0x18001835e  mov     rcx, r12; Size
0x180018361  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018366  mov     rdi, rax
0x180018369  test    rax, rax
0x18001836c  jz      loc_1800185E1
0x180018372  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x180018379  mov     dword ptr [rdi+8], 1
0x180018380  mov     [rdi], rax
0x180018383  mov     dword ptr [rdi+0Ch], 10h
0x18001838a  mov     [rdi+10h], r13
0x18001838e  mov     [rdi+18h], r13
0x180018392  mov     [r14+290h], rdi
0x180018399  mov     r13d, [rdi+1Ch]
0x18001839d  movsxd  r12, dword ptr [rdi+0Ch]
0x1800183a1  lea     r15d, [r13+1]
0x1800183a5  imul    r15d, r12d
0x1800183a9  cmp     r15d, [rdi+18h]
0x1800183ad  jle     short loc_1800183C2
0x1800183af  mov     edx, r15d; int
0x1800183b2  mov     rcx, rdi; this
0x1800183b5  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x1800183ba  test    eax, eax
0x1800183bc  jz      loc_1800185E8
0x1800183c2  mov     rax, [rdi+10h]
0x1800183c6  mov     edx, r12d
0x1800183c9  imul    edx, r13d
0x1800183cd  movsxd  rcx, edx
0x1800183d0  add     rax, rcx
0x1800183d3  mov     [rsp+3F0h+var_378], rax
0x1800183d8  cmp     r13d, [rdi+1Ch]
0x1800183dc  jge     short loc_1800183F8
0x1800183de  sub     r15d, edx
0x1800183e1  lea     rcx, [rax+r12]; void *
0x1800183e5  sub     r15d, r12d
0x1800183e8  mov     rdx, rax; Src
0x1800183eb  movsxd  r8, r15d; Size
0x1800183ee  call    memmove_0
0x1800183f3  mov     rax, [rsp+3F0h+var_378]
0x1800183f8  mov     r8, r12; Size
0x1800183fb  lea     rdx, [rsp+3F0h+Src]; Src
0x180018400  mov     rcx, rax; void *
0x180018403  call    memcpy_0
0x180018408  inc     dword ptr [rdi+1Ch]
0x18001840b  lock inc dword ptr [rbx]
0x18001840e  mov     rcx, r14; this
0x180018411  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180018416  test    rbx, rbx
0x180018419  jnz     loc_1800185F2
0x18001841f  mov     rcx, [rbp+2F0h+bstrString]; bstrString
0x180018423  call    cs:__imp_SysFreeString
0x180018429  mov     rcx, [rbp+2F0h+var_310]; bstrString
0x18001842d  call    cs:__imp_SysFreeString
0x180018433  lea     rcx, [rbp+2F0h+var_368]; struct tagEXCEPINFO *
0x180018437  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18001843c  mov     rcx, [rbp+2F0h+var_328]; this
0x180018440  test    rcx, rcx
0x180018443  jnz     loc_1800185FF
0x180018449  mov     eax, esi
0x18001844b  mov     rcx, [rbp+2F0h+var_40]
0x180018452  xor     rcx, rsp; StackCookie
0x180018455  call    __security_check_cookie
0x18001845a  mov     rbx, [rsp+3F0h+arg_10]
0x180018462  add     rsp, 3C0h
0x180018469  pop     r15
0x18001846b  pop     r14
0x18001846d  pop     r13
0x18001846f  pop     r12
0x180018471  pop     rdi
0x180018472  pop     rsi
0x180018473  pop     rbp
0x180018474  retn
0x180018475  mov     rbx, r13
0x180018478  jmp     loc_1800182C6
0x18001847d  cmp     edi, r15d
0x180018480  jz      loc_180018534
0x180018486  lea     rcx, [rbp+2F0h+var_300]; this
0x18001848a  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001848f  mov     esi, edi
0x180018491  mov     dword ptr [rsp+3F0h+var_390], edi
0x180018495  cmp     edi, r15d
0x180018498  jnz     short loc_18001841F
0x18001849a  lea     rdx, [rsp+3F0h+Src]; struct CActiveScriptError **
0x18001849f  mov     [rsp+3F0h+Src], r13
0x1800184a4  lea     rcx, [rbp+2F0h+var_370]; this
0x1800184a8  call    ?GetActiveScriptError@CompileScriptException@@QEAAJPEAPEAVCActiveScriptError@@@Z; CompileScriptException::GetActiveScriptError(CActiveScriptError * *)
0x1800184ad  test    eax, eax
0x1800184af  jns     loc_180018567
0x1800184b5  mov     rcx, [rbp+2F0h+bstrString]; bstrString
0x1800184b9  mov     ebx, [rbp+2F0h+var_368.scode]
0x1800184bc  call    cs:__imp_SysFreeString
0x1800184c2  mov     rcx, [rbp+2F0h+var_310]; bstrString
0x1800184c6  call    cs:__imp_SysFreeString
0x1800184cc  lea     rcx, [rbp+2F0h+var_368]; struct tagEXCEPINFO *
0x1800184d0  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x1800184d5  mov     rcx, [rbp+2F0h+var_328]; this
0x1800184d9  test    rcx, rcx
0x1800184dc  jnz     short loc_18001855D
0x1800184de  mov     eax, ebx
0x1800184e0  jmp     loc_18001844B
0x1800184e5  mov     esi, 8007000Eh
0x1800184ea  jmp     loc_18001841F
0x1800184ef  mov     eax, 80070057h
0x1800184f4  jmp     loc_18001844B
0x1800184f9  or      ecx, 8
0x1800184fc  mov     dword ptr [rsp+3F0h+Src], ecx
0x180018500  jmp     loc_18001817F
0x180018505  or      esi, 2
0x180018508  or      ecx, 4
0x18001850b  mov     dword ptr [rsp+3F0h+Src], ecx
0x18001850f  jmp     loc_180018193
0x180018514  or      dword ptr [rdi+1Ch], 1
0x180018518  jmp     loc_18001819B
0x18001851d  or      dword ptr [rdi+1Ch], 2
0x180018521  jmp     loc_1800181A5
0x180018526  mov     rcx, rbx; bstrString
0x180018529  call    cs:__imp_SysFreeString
0x18001852f  jmp     loc_180018257
0x180018534  cmp     [rbp+2F0h+var_368.scode], r13d
0x180018538  jl      loc_180018486
0x18001853e  mov     [rbp+2F0h+var_368.scode], 80004005h
0x180018545  jmp     loc_180018486
0x18001854a  mov     esi, 80004005h
0x18001854f  jmp     loc_18001831A
0x180018554  mov     [rcx+30h], rdx
0x180018558  jmp     loc_18001830B
0x18001855d  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x180018562  jmp     loc_1800184DE
0x180018567  mov     rbx, [rsp+3F0h+Src]
0x18001856c  lea     rdx, [rbx+8]
0x180018570  test    rbx, rbx
0x180018573  jnz     short loc_180018578
0x180018575  mov     rdx, r13; struct IActiveScriptError *
0x180018578  mov     rcx, r14; this
0x18001857b  call    ?OnScriptError@COleScript@@QEAAJPEAUIActiveScriptError@@@Z; COleScript::OnScriptError(IActiveScriptError *)
0x180018580  lea     rcx, [rbp+2F0h+var_370]; this
0x180018584  test    eax, eax
0x180018586  jnz     short loc_180018594
0x180018588  call    ?DetachActiveScriptError@ScriptException@@QEAAXXZ; ScriptException::DetachActiveScriptError(void)
0x18001858d  mov     esi, 80020101h
0x180018592  jmp     short loc_1800185A7
0x180018594  mov     r8, [rsp+3F0h+var_378]; struct tagEXCEPINFO *
0x180018599  lea     rdx, [rsp+3F0h+var_390]; int *
0x18001859e  call    ?GetError@CompileScriptException@@QEAAXPEAJPEAUtagEXCEPINFO@@@Z; CompileScriptException::GetError(long *,tagEXCEPINFO *)
  ... truncated ...
```
