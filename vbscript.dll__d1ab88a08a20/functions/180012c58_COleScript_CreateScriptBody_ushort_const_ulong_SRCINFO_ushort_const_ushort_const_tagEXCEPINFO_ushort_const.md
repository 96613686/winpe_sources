# COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,ushort const *)

- ea: `0x180012c58`
- end: `0x1800131b2`
- name: `?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@0@Z`
- size: `1370`
- prototype: `__int64 __fastcall(COleScript *this, unsigned __int16 *, int, struct SRCINFO *, wchar_t *String2, const unsigned __int16 *, struct tagEXCEPINFO *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1800126a0`
- `0x18005370c`

## callees

- `0x18001176c`
- `0x18001199c`
- `0x180011a58`
- `0x180012c58`
- `0x1800131b8`
- `0x180013708`
- `0x180013840`
- `0x1800139b4`
- `0x180013a1c`
- `0x180013cb8`
- `0x18001b588`
- `0x18001cb34`
- `0x18001e2e4`
- `0x18001e32c`
- `0x18001e390`
- `0x18001eef0`
- `0x180039b0c`
- `0x180042fe0`
- `0x1800435f4`
- `0x180046884`
- `0x180055414`
- `0x18005660c`
- `0x18006111c`
- `0x1800615f0`
- `0x18007941e`
- `0x18007942a`
- `0x180079436`
- `0x180079490`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180012fa5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001304f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001305f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800130cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fa5`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001304f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001305f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800130cc`
- `OLEAUT32!__imp_SysStringLen` at `0x180012d66`
- `OLEAUT32!__imp_SysStringLen` at `0x180012d66`

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
0x180012c58  mov     [rsp-8+arg_10], rbx
0x180012c5d  push    rbp
0x180012c5e  push    rsi
0x180012c5f  push    rdi
0x180012c60  push    r12
0x180012c62  push    r13
0x180012c64  push    r14
0x180012c66  push    r15
0x180012c68  lea     rbp, [rsp-2C0h]
0x180012c70  sub     rsp, 3C0h
0x180012c77  mov     rax, cs:__security_cookie
0x180012c7e  xor     rax, rsp
0x180012c81  mov     [rbp+2F0h+var_40], rax
0x180012c88  mov     rax, [rbp+2F0h+arg_30]
0x180012c8f  mov     r14, rcx
0x180012c92  mov     rcx, [rbp+2F0h+String2]; String2
0x180012c99  mov     rdi, r9
0x180012c9c  mov     r12, [rbp+2F0h+arg_28]
0x180012ca3  mov     ebx, r8d
0x180012ca6  mov     r13, [rbp+2F0h+arg_38]
0x180012cad  mov     r15, rdx
0x180012cb0  mov     [rsp+3F0h+var_378], rax
0x180012cb5  mov     eax, [r9+18h]
0x180012cb9  mov     dword ptr [rsp+3F0h+Src+4], eax
0x180012cbd  mov     eax, r8d
0x180012cc0  and     eax, 60h
0x180012cc3  mov     [rsp+3F0h+var_380], 0
0x180012ccc  cmp     al, 60h ; '`'
0x180012cce  jz      loc_180013092
0x180012cd4  call    ?ComputeGrfscr@@YAKPEBG@Z; ComputeGrfscr(ushort const *)
0x180012cd9  mov     ecx, 2
0x180012cde  test    bl, 40h
0x180012ce1  mov     esi, eax
0x180012ce3  mov     edx, ebx
0x180012ce5  lea     eax, [rcx+1]
0x180012ce8  cmovnz  ecx, eax
0x180012ceb  mov     dword ptr [rsp+3F0h+Src], ecx
0x180012cef  and     edx, 80h
0x180012cf5  jnz     loc_18001309C
0x180012cfb  mov     r8d, 80000020h
0x180012d01  mov     eax, ebx
0x180012d03  and     eax, r8d
0x180012d06  cmp     eax, r8d
0x180012d09  jz      loc_1800130A8
0x180012d0f  test    edx, edx
0x180012d11  jnz     loc_1800130B7
0x180012d17  bt      ebx, 1Eh
0x180012d1b  jb      loc_1800130C0
0x180012d21  xor     edx, edx; Val
0x180012d23  lea     rcx, [rbp+2F0h+var_370]; void *
0x180012d27  lea     r8d, [rdx+50h]; Size
0x180012d2b  call    memset_0
0x180012d30  xor     ecx, ecx
0x180012d32  mov     eax, esi
0x180012d34  and     eax, 201h
0x180012d39  mov     [rbp+2F0h+var_320], rcx
0x180012d3d  mov     [rbp+2F0h+bstrString], rcx
0x180012d41  mov     [rbp+2F0h+var_310], rcx
0x180012d45  mov     [rsp+3F0h+var_390], rcx
0x180012d4a  cmp     eax, 1
0x180012d4d  jnz     short loc_180012D81
0x180012d4f  mov     rcx, r15; unsigned __int16 *
0x180012d52  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180012d57  mov     rbx, rax
0x180012d5a  test    rax, rax
0x180012d5d  jz      loc_180013088
0x180012d63  mov     rcx, rax; pbstr
0x180012d66  call    cs:__imp_SysStringLen
0x180012d6d  nop     dword ptr [rax+rax+00h]
0x180012d72  mov     edx, eax; unsigned __int64
0x180012d74  mov     rcx, rbx; unsigned __int16 *
0x180012d77  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x180012d7c  mov     r15, rbx
0x180012d7f  jmp     short loc_180012D84
0x180012d81  mov     rbx, rcx
0x180012d84  lea     rcx, [rbp+2F0h+var_300]; this
0x180012d88  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x180012d8d  mov     [rsp+3F0h+var_3A0], r13; unsigned __int16 *
0x180012d92  lea     rax, [rbp+2F0h+var_370]
0x180012d96  xor     r13d, r13d
0x180012d99  lea     rdx, [rsp+3F0h+var_390]; struct ExecBody **
0x180012d9e  mov     [rsp+3F0h+var_3A8], r13; unsigned __int16 *
0x180012da3  lea     rcx, [rbp+2F0h+var_300]; this
0x180012da7  mov     [rsp+3F0h+var_3B0], r12; unsigned __int16 *
0x180012dac  mov     r9, r15; unsigned __int16 *
0x180012daf  mov     [rsp+3F0h+var_3B8], rax; struct CompileScriptException *
0x180012db4  mov     r8, r14; struct COleScript *
0x180012db7  lea     r12d, [r13+20h]
0x180012dbb  mov     [rsp+3F0h+var_3C0], r12d; UINT
0x180012dc0  mov     [rsp+3F0h+var_3C8], rdi; LPCSTR
0x180012dc5  mov     [rsp+3F0h+var_3D0], esi; unsigned int
0x180012dc9  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@222@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,ushort const *,ushort const *)
0x180012dce  mov     edi, eax
0x180012dd0  test    rbx, rbx
0x180012dd3  jnz     loc_1800130C9
0x180012dd9  mov     r15d, 86664004h
0x180012ddf  test    edi, edi
0x180012de1  js      loc_18001300C
0x180012de7  lea     rcx, [rbp+2F0h+var_300]; this
0x180012deb  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x180012df0  mov     ecx, 50h ; 'P'; Size
0x180012df5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012dfa  mov     rbx, rax
0x180012dfd  test    rax, rax
0x180012e00  jz      loc_180013004
0x180012e06  mov     rax, [rsp+3F0h+var_390]
0x180012e0b  mov     dword ptr [rbx], 1
0x180012e11  mov     [rbx+8], r13
0x180012e15  mov     [rbx+10h], r13
0x180012e19  mov     [rbx+18h], r13
0x180012e1d  mov     [rbx+20h], r14
0x180012e21  lock inc dword ptr [r14+94h]
0x180012e29  mov     [rbx+28h], r13
0x180012e2d  mov     [rbx+30h], r13
0x180012e31  mov     [rbx+38h], rax
0x180012e35  lock inc dword ptr [rax+8]
0x180012e39  mov     rax, [rbx+38h]
0x180012e3d  mov     rcx, [rax]
0x180012e40  mov     [rbx+40h], rcx
0x180012e44  mov     [rbx+48h], rcx
0x180012e48  mov     [rsp+3F0h+var_380], rbx
0x180012e4d  test    rbx, rbx
0x180012e50  jnz     short loc_180012E59
0x180012e52  mov     esi, 8007000Eh
0x180012e57  jmp     short loc_180012E9C
0x180012e59  lea     rdi, [r14+328h]
0x180012e60  mov     rcx, rdi; this
0x180012e63  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180012e68  test    eax, eax
0x180012e6a  jz      loc_1800130F3
0x180012e70  lea     rax, [r14+360h]
0x180012e77  mov     esi, r13d
0x180012e7a  mov     rcx, [rax]
0x180012e7d  lea     rdx, [rbx+28h]
0x180012e81  mov     [rdx], rcx
0x180012e84  test    rcx, rcx
0x180012e87  jnz     loc_1800130FD
0x180012e8d  mov     [rbx+30h], rax
0x180012e91  mov     rcx, rdi; this
0x180012e94  mov     [rax], rbx
0x180012e97  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180012e9c  mov     rcx, [rsp+3F0h+var_390]; this
0x180012ea1  mov     edi, esi
0x180012ea3  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x180012ea8  mov     dword ptr [rsp+3F0h+var_390], esi
0x180012eac  test    esi, esi
0x180012eae  js      loc_180013024
0x180012eb4  mov     rcx, r14; this
0x180012eb7  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180012ebc  test    eax, eax
0x180012ebe  jz      loc_18001315D
0x180012ec4  mov     rcx, r14; this
0x180012ec7  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180012ecc  test    eax, eax
0x180012ece  jnz     loc_180013170
0x180012ed4  mov     rdi, [r14+290h]
0x180012edb  test    rdi, rdi
0x180012ede  jnz     short loc_180012F1B
0x180012ee0  mov     rcx, r12; Size
0x180012ee3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012ee8  mov     rdi, rax
0x180012eeb  test    rax, rax
0x180012eee  jz      loc_18001318A
0x180012ef4  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x180012efb  mov     dword ptr [rdi+8], 1
0x180012f02  mov     [rdi], rax
0x180012f05  mov     dword ptr [rdi+0Ch], 10h
0x180012f0c  mov     [rdi+10h], r13
0x180012f10  mov     [rdi+18h], r13
0x180012f14  mov     [r14+290h], rdi
0x180012f1b  mov     r13d, [rdi+1Ch]
0x180012f1f  movsxd  r12, dword ptr [rdi+0Ch]
0x180012f23  lea     r15d, [r13+1]
0x180012f27  imul    r15d, r12d
0x180012f2b  cmp     r15d, [rdi+18h]
0x180012f2f  jle     short loc_180012F44
0x180012f31  mov     edx, r15d; int
0x180012f34  mov     rcx, rdi; this
0x180012f37  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180012f3c  test    eax, eax
0x180012f3e  jz      loc_180013191
0x180012f44  mov     rax, [rdi+10h]
0x180012f48  mov     edx, r12d
0x180012f4b  imul    edx, r13d
0x180012f4f  movsxd  rcx, edx
0x180012f52  add     rax, rcx
0x180012f55  mov     [rsp+3F0h+var_378], rax
0x180012f5a  cmp     r13d, [rdi+1Ch]
0x180012f5e  jge     short loc_180012F7A
0x180012f60  sub     r15d, edx
0x180012f63  lea     rcx, [rax+r12]; void *
0x180012f67  sub     r15d, r12d
0x180012f6a  mov     rdx, rax; Src
0x180012f6d  movsxd  r8, r15d; Size
0x180012f70  call    memmove_0
0x180012f75  mov     rax, [rsp+3F0h+var_378]
0x180012f7a  mov     r8, r12; Size
0x180012f7d  lea     rdx, [rsp+3F0h+Src]; Src
0x180012f82  mov     rcx, rax; void *
0x180012f85  call    memcpy_0
0x180012f8a  inc     dword ptr [rdi+1Ch]
0x180012f8d  lock inc dword ptr [rbx]
0x180012f90  mov     rcx, r14; this
0x180012f93  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180012f98  test    rbx, rbx
0x180012f9b  jnz     loc_18001319B
0x180012fa1  mov     rcx, [rbp+2F0h+bstrString]; bstrString
0x180012fa5  call    cs:__imp_SysFreeString
0x180012fac  nop     dword ptr [rax+rax+00h]
0x180012fb1  mov     rcx, [rbp+2F0h+var_310]; bstrString
0x180012fb5  call    cs:__imp_SysFreeString
0x180012fbc  nop     dword ptr [rax+rax+00h]
0x180012fc1  lea     rcx, [rbp+2F0h+var_368]; struct tagEXCEPINFO *
0x180012fc5  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180012fca  mov     rcx, [rbp+2F0h+var_328]; this
0x180012fce  test    rcx, rcx
0x180012fd1  jnz     loc_1800131A8
0x180012fd7  mov     eax, esi
0x180012fd9  mov     rcx, [rbp+2F0h+var_40]
0x180012fe0  xor     rcx, rsp; StackCookie
0x180012fe3  call    __security_check_cookie
0x180012fe8  mov     rbx, [rsp+3F0h+arg_10]
0x180012ff0  add     rsp, 3C0h
0x180012ff7  pop     r15
0x180012ff9  pop     r14
0x180012ffb  pop     r13
0x180012ffd  pop     r12
0x180012fff  pop     rdi
0x180013000  pop     rsi
0x180013001  pop     rbp
0x180013002  retn
0x180013004  mov     rbx, r13
0x180013007  jmp     loc_180012E48
0x18001300c  cmp     edi, r15d
0x18001300f  jz      loc_1800130DD
0x180013015  lea     rcx, [rbp+2F0h+var_300]; this
0x180013019  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001301e  mov     esi, edi
0x180013020  mov     dword ptr [rsp+3F0h+var_390], edi
0x180013024  cmp     edi, r15d
0x180013027  jnz     loc_180012FA1
0x18001302d  lea     rdx, [rsp+3F0h+Src]; struct CActiveScriptError **
0x180013032  mov     [rsp+3F0h+Src], r13
0x180013037  lea     rcx, [rbp+2F0h+var_370]; this
0x18001303b  call    ?GetActiveScriptError@CompileScriptException@@QEAAJPEAPEAVCActiveScriptError@@@Z; CompileScriptException::GetActiveScriptError(CActiveScriptError * *)
0x180013040  test    eax, eax
0x180013042  jns     loc_180013110
0x180013048  mov     rcx, [rbp+2F0h+bstrString]; bstrString
0x18001304c  mov     ebx, [rbp+2F0h+var_368.scode]
0x18001304f  call    cs:__imp_SysFreeString
0x180013056  nop     dword ptr [rax+rax+00h]
0x18001305b  mov     rcx, [rbp+2F0h+var_310]; bstrString
0x18001305f  call    cs:__imp_SysFreeString
0x180013066  nop     dword ptr [rax+rax+00h]
0x18001306b  lea     rcx, [rbp+2F0h+var_368]; struct tagEXCEPINFO *
0x18001306f  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180013074  mov     rcx, [rbp+2F0h+var_328]; this
0x180013078  test    rcx, rcx
0x18001307b  jnz     loc_180013106
0x180013081  mov     eax, ebx
0x180013083  jmp     loc_180012FD9
0x180013088  mov     esi, 8007000Eh
0x18001308d  jmp     loc_180012FA1
0x180013092  mov     eax, 80070057h
0x180013097  jmp     loc_180012FD9
0x18001309c  or      ecx, 8
0x18001309f  mov     dword ptr [rsp+3F0h+Src], ecx
0x1800130a3  jmp     loc_180012CFB
0x1800130a8  or      esi, 2
0x1800130ab  or      ecx, 4
0x1800130ae  mov     dword ptr [rsp+3F0h+Src], ecx
0x1800130b2  jmp     loc_180012D0F
0x1800130b7  or      dword ptr [rdi+1Ch], 1
0x1800130bb  jmp     loc_180012D17
0x1800130c0  or      dword ptr [rdi+1Ch], 2
0x1800130c4  jmp     loc_180012D21
0x1800130c9  mov     rcx, rbx; bstrString
0x1800130cc  call    cs:__imp_SysFreeString
0x1800130d3  nop     dword ptr [rax+rax+00h]
0x1800130d8  jmp     loc_180012DD9
0x1800130dd  cmp     [rbp+2F0h+var_368.scode], r13d
0x1800130e1  jl      loc_180013015
0x1800130e7  mov     [rbp+2F0h+var_368.scode], 80004005h
0x1800130ee  jmp     loc_180013015
0x1800130f3  mov     esi, 80004005h
0x1800130f8  jmp     loc_180012E9C
0x1800130fd  mov     [rcx+30h], rdx
0x180013101  jmp     loc_180012E8D
0x180013106  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x18001310b  jmp     loc_180013081
0x180013110  mov     rbx, [rsp+3F0h+Src]
0x180013115  lea     rdx, [rbx+8]
0x180013119  test    rbx, rbx
0x18001311c  jnz     short loc_180013121
0x18001311e  mov     rdx, r13; struct IActiveScriptError *
0x180013121  mov     rcx, r14; this
0x180013124  call    ?OnScriptError@COleScript@@QEAAJPEAUIActiveScriptError@@@Z; COleScript::OnScriptError(IActiveScriptError *)
0x180013129  lea     rcx, [rbp+2F0h+var_370]; this
0x18001312d  test    eax, eax
0x18001312f  jnz     short loc_18001313D
  ... truncated ...
```
