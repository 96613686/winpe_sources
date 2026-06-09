# ComBreakpointExpression::Start(IDebugExpressionCallBack *)

- ea: `0x18005d6d0`
- end: `0x18005d87b`
- name: `?Start@ComBreakpointExpression@@UEAAJPEAUIDebugExpressionCallBack@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(ComBreakpointExpression *__hidden this, struct IDebugExpressionCallBack *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180046884`
- `0x180051acc`
- `0x180052a70`
- `0x180052e50`
- `0x180053ecc`
- `0x180053f64`
- `0x18005cb84`
- `0x18005cc98`
- `0x18005cdf0`
- `0x18005d6d0`
- `0x180060f68`
- `0x1800615f0`
- `0x1800616c0`
- `0x18007a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005d783`
- `msvcrt!_wcsicmp` at `0x18005d783`

## pseudocode

```c
__int64 __fastcall ComBreakpointExpression::Start(ComBreakpointExpression *this, struct IDebugExpressionCallBack *a2)
{
  __int64 v4; // rdx
  _QWORD *v6; // r14
  COleScript *v7; // r15
  unsigned int v8; // ebx
  __int64 v9; // rax
  const wchar_t *v10; // r8
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // r12
  __int64 v14; // r13
  int v15; // r14d
  struct CScriptBody *v16; // r12
  CCodeContext *v17; // rax
  CCodeContext *v18; // rax
  struct IDebugCodeContext *v19; // rdi
  CActiveScriptError *v20; // rax
  CActiveScriptError *v21; // rax
  struct IActiveScriptError *v22; // rdi
  __int64 v23; // [rsp+60h] [rbp+8h]
  const wchar_t *v24; // [rsp+70h] [rbp+18h]
  char v25; // [rsp+78h] [rbp+20h] BYREF

  v4 = *((_QWORD *)this + 2);
  if ( !v4 )
    return 2147549183LL;
  LockOleScript::LockOleScript((LockOleScript *)&v25, *(struct COleScript **)(v4 + 32));
  v6 = (_QWORD *)*((_QWORD *)this + 2);
  v7 = (COleScript *)v6[4];
  if ( *((_DWORD *)this + 3) == *((_DWORD *)v7 + 214) )
  {
    if ( !*((_QWORD *)this + 4) )
    {
      v9 = v6[8];
      v10 = (const wchar_t *)*((_QWORD *)this + 3);
      v24 = v10;
      v11 = v6[9] + *(int *)(v9 + 16);
      v12 = *(_DWORD *)(v9 + 20);
      v23 = v11;
      while ( --v12 > 0 )
      {
        v13 = v6[9];
        v14 = *(int *)(v11 + 4LL * v12);
        if ( *(_DWORD *)(v13 + v14) )
        {
          if ( !_wcsicmp(v10, (const wchar_t *)(v13 + *(int *)(v13 + v14))) )
          {
            v15 = *(_DWORD *)(v13 + v14 + 16);
            v16 = (struct CScriptBody *)*((_QWORD *)this + 2);
            v17 = (CCodeContext *)operator new(0x28u);
            if ( v17 )
            {
              v18 = CCodeContext::CCodeContext(v17);
              v19 = (struct IDebugCodeContext *)v18;
              if ( v18 )
              {
                if ( (int)CCodeContext::Init(v18, v16, v15) >= 0 )
                  COleScript::DbgCreateBrowserFromCodeContext(
                    v7,
                    v19,
                    *((const unsigned __int16 **)this + 3),
                    (struct IDebugProperty **)this + 4);
                CCodeContext::Release((CCodeContext *)v19);
              }
            }
            goto LABEL_19;
          }
          v11 = v23;
          v10 = v24;
        }
      }
      v20 = (CActiveScriptError *)operator new(0x80u);
      if ( v20 )
      {
        v21 = CActiveScriptError::CActiveScriptError(v20);
        v22 = (struct IActiveScriptError *)v21;
        if ( v21 )
        {
          *((_DWORD *)v21 + 20) = -2146828253;
          ExcepInfoDeferredFillIn();
          COleScript::DbgCreateBrowserFromError(
            v7,
            v22 + 1,
            *((const unsigned __int16 **)this + 3),
            (struct IDebugProperty **)this + 4);
          CActiveScriptError::Release((CActiveScriptError *)v22);
        }
      }
    }
LABEL_19:
    if ( a2 )
      ((void (__fastcall *)(struct IDebugExpressionCallBack *))a2->lpVtbl->onComplete)(a2);
    v8 = 0;
  }
  else
  {
    ComBreakpointExpression::Close(this);
    v8 = -2147418113;
  }
  LockOleScript::~LockOleScript((LockOleScript *)&v25);
  return v8;
}

```

## disassembly

```asm
0x18005d6d0  mov     [rsp+arg_8], rbx
0x18005d6d5  push    rbp
0x18005d6d6  push    rsi
0x18005d6d7  push    rdi
0x18005d6d8  push    r12
0x18005d6da  push    r13
0x18005d6dc  push    r14
0x18005d6de  push    r15
0x18005d6e0  sub     rsp, 20h
0x18005d6e4  mov     rsi, rdx
0x18005d6e7  mov     rbx, rcx
0x18005d6ea  mov     rdx, [rcx+10h]
0x18005d6ee  test    rdx, rdx
0x18005d6f1  jnz     short loc_18005D6FD
0x18005d6f3  mov     eax, 8000FFFFh
0x18005d6f8  jmp     loc_18005D865
0x18005d6fd  mov     rdx, [rdx+20h]; struct COleScript *
0x18005d701  lea     rcx, [rsp+58h+arg_18]; this
0x18005d706  call    ??0LockOleScript@@QEAA@PEAVCOleScript@@@Z; LockOleScript::LockOleScript(COleScript *)
0x18005d70b  mov     r14, [rbx+10h]
0x18005d70f  mov     r15, [r14+20h]
0x18005d713  mov     eax, [r15+358h]
0x18005d71a  cmp     [rbx+0Ch], eax
0x18005d71d  jz      short loc_18005D731
0x18005d71f  mov     rcx, rbx; this
0x18005d722  call    ?Close@ComBreakpointExpression@@AEAAXXZ; ComBreakpointExpression::Close(void)
0x18005d727  mov     ebx, 8000FFFFh
0x18005d72c  jmp     loc_18005D859
0x18005d731  lea     rbp, [rbx+20h]
0x18005d735  cmp     qword ptr [rbp+0], 0
0x18005d73a  jnz     loc_18005D843
0x18005d740  mov     rax, [r14+40h]
0x18005d744  mov     r8, [rbx+18h]
0x18005d748  mov     [rsp+58h+arg_10], r8
0x18005d74d  movsxd  rcx, dword ptr [rax+10h]
0x18005d751  add     rcx, [r14+48h]
0x18005d755  mov     edi, [rax+14h]
0x18005d758  mov     [rsp+58h+arg_0], rcx
0x18005d75d  dec     edi
0x18005d75f  test    edi, edi
0x18005d761  jle     loc_18005D7F9
0x18005d767  mov     r12, [r14+48h]
0x18005d76b  movsxd  rax, edi
0x18005d76e  movsxd  r13, dword ptr [rcx+rax*4]
0x18005d772  cmp     dword ptr [r12+r13], 0
0x18005d777  jz      short loc_18005D75D
0x18005d779  movsxd  rdx, dword ptr [r12+r13]
0x18005d77d  mov     rcx, r8; String1
0x18005d780  add     rdx, r12; String2
0x18005d783  call    cs:__imp__wcsicmp
0x18005d78a  nop     dword ptr [rax+rax+00h]
0x18005d78f  test    eax, eax
0x18005d791  jz      short loc_18005D79F
0x18005d793  mov     rcx, [rsp+58h+arg_0]
0x18005d798  mov     r8, [rsp+58h+arg_10]
0x18005d79d  jmp     short loc_18005D75D
0x18005d79f  mov     r14d, [r12+r13+10h]
0x18005d7a4  mov     ecx, 28h ; '('; Size
0x18005d7a9  mov     r12, [rbx+10h]
0x18005d7ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005d7b2  test    rax, rax
0x18005d7b5  jz      loc_18005D843
0x18005d7bb  mov     rcx, rax; this
0x18005d7be  call    ??0CCodeContext@@QEAA@XZ; CCodeContext::CCodeContext(void)
0x18005d7c3  mov     rdi, rax
0x18005d7c6  test    rax, rax
0x18005d7c9  jz      short loc_18005D843
0x18005d7cb  mov     r8d, r14d; int
0x18005d7ce  mov     rdx, r12; struct CScriptBody *
0x18005d7d1  mov     rcx, rax; this
0x18005d7d4  call    ?Init@CCodeContext@@QEAAJPEAVCScriptBody@@J@Z; CCodeContext::Init(CScriptBody *,long)
0x18005d7d9  test    eax, eax
0x18005d7db  js      short loc_18005D7EF
0x18005d7dd  mov     r8, [rbx+18h]; unsigned __int16 *
0x18005d7e1  mov     r9, rbp; struct IDebugProperty **
0x18005d7e4  mov     rdx, rdi; struct IDebugCodeContext *
0x18005d7e7  mov     rcx, r15; this
0x18005d7ea  call    ?DbgCreateBrowserFromCodeContext@COleScript@@QEAAJPEAUIDebugCodeContext@@PEBGPEAPEAUIDebugProperty@@@Z; COleScript::DbgCreateBrowserFromCodeContext(IDebugCodeContext *,ushort const *,IDebugProperty * *)
0x18005d7ef  mov     rcx, rdi; this
0x18005d7f2  call    ?Release@CCodeContext@@UEAAKXZ; CCodeContext::Release(void)
0x18005d7f7  jmp     short loc_18005D843
0x18005d7f9  mov     ecx, 80h; Size
0x18005d7fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005d803  test    rax, rax
0x18005d806  jz      short loc_18005D843
0x18005d808  mov     rcx, rax; this
0x18005d80b  call    ??0CActiveScriptError@@QEAA@XZ; CActiveScriptError::CActiveScriptError(void)
0x18005d810  mov     rdi, rax
0x18005d813  test    rax, rax
0x18005d816  jz      short loc_18005D843
0x18005d818  lea     rcx, [rax+18h]
0x18005d81c  mov     dword ptr [rcx+38h], 800A0023h
0x18005d823  call    ExcepInfoDeferredFillIn
0x18005d828  mov     r8, [rbx+18h]; unsigned __int16 *
0x18005d82c  lea     rdx, [rdi+8]; struct IActiveScriptError *
0x18005d830  mov     r9, rbp; struct IDebugProperty **
0x18005d833  mov     rcx, r15; this
0x18005d836  call    ?DbgCreateBrowserFromError@COleScript@@QEAAJPEAUIActiveScriptError@@PEBGPEAPEAUIDebugProperty@@@Z; COleScript::DbgCreateBrowserFromError(IActiveScriptError *,ushort const *,IDebugProperty * *)
0x18005d83b  mov     rcx, rdi; this
0x18005d83e  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x18005d843  test    rsi, rsi
0x18005d846  jz      short loc_18005D857
0x18005d848  mov     rax, [rsi]
0x18005d84b  mov     rcx, rsi
0x18005d84e  mov     rax, [rax+18h]
0x18005d852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d857  xor     ebx, ebx
0x18005d859  lea     rcx, [rsp+58h+arg_18]; this
0x18005d85e  call    ??1LockOleScript@@QEAA@XZ; LockOleScript::~LockOleScript(void)
0x18005d863  mov     eax, ebx
0x18005d865  mov     rbx, [rsp+58h+arg_8]
0x18005d86a  add     rsp, 20h
0x18005d86e  pop     r15
0x18005d870  pop     r14
0x18005d872  pop     r13
0x18005d874  pop     r12
0x18005d876  pop     rdi
0x18005d877  pop     rsi
0x18005d878  pop     rbp
0x18005d879  retn
```
