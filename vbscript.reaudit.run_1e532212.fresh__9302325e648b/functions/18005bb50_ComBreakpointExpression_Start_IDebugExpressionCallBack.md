# ComBreakpointExpression::Start(IDebugExpressionCallBack *)

- ea: `0x18005bb50`
- end: `0x18005bcf4`
- name: `?Start@ComBreakpointExpression@@UEAAJPEAUIDebugExpressionCallBack@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(ComBreakpointExpression *__hidden this, struct IDebugExpressionCallBack *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180045490`
- `0x18005030c`
- `0x180051290`
- `0x180051660`
- `0x180052678`
- `0x180052710`
- `0x18005b064`
- `0x18005b174`
- `0x18005b2bc`
- `0x18005bb50`
- `0x18005f300`
- `0x18005f970`
- `0x18005fa40`
- `0x180077010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005bc03`
- `msvcrt!_wcsicmp` at `0x18005bc03`

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
0x18005bb50  mov     [rsp+arg_8], rbx
0x18005bb55  push    rbp
0x18005bb56  push    rsi
0x18005bb57  push    rdi
0x18005bb58  push    r12
0x18005bb5a  push    r13
0x18005bb5c  push    r14
0x18005bb5e  push    r15
0x18005bb60  sub     rsp, 20h
0x18005bb64  mov     rsi, rdx
0x18005bb67  mov     rbx, rcx
0x18005bb6a  mov     rdx, [rcx+10h]
0x18005bb6e  test    rdx, rdx
0x18005bb71  jnz     short loc_18005BB7D
0x18005bb73  mov     eax, 8000FFFFh
0x18005bb78  jmp     loc_18005BCDF
0x18005bb7d  mov     rdx, [rdx+20h]; struct COleScript *
0x18005bb81  lea     rcx, [rsp+58h+arg_18]; this
0x18005bb86  call    ??0LockOleScript@@QEAA@PEAVCOleScript@@@Z; LockOleScript::LockOleScript(COleScript *)
0x18005bb8b  mov     r14, [rbx+10h]
0x18005bb8f  mov     r15, [r14+20h]
0x18005bb93  mov     eax, [r15+358h]
0x18005bb9a  cmp     [rbx+0Ch], eax
0x18005bb9d  jz      short loc_18005BBB1
0x18005bb9f  mov     rcx, rbx; this
0x18005bba2  call    ?Close@ComBreakpointExpression@@AEAAXXZ; ComBreakpointExpression::Close(void)
0x18005bba7  mov     ebx, 8000FFFFh
0x18005bbac  jmp     loc_18005BCD3
0x18005bbb1  lea     rbp, [rbx+20h]
0x18005bbb5  cmp     qword ptr [rbp+0], 0
0x18005bbba  jnz     loc_18005BCBD
0x18005bbc0  mov     rax, [r14+40h]
0x18005bbc4  mov     r8, [rbx+18h]
0x18005bbc8  mov     [rsp+58h+arg_10], r8
0x18005bbcd  movsxd  rcx, dword ptr [rax+10h]
0x18005bbd1  add     rcx, [r14+48h]
0x18005bbd5  mov     edi, [rax+14h]
0x18005bbd8  mov     [rsp+58h+arg_0], rcx
0x18005bbdd  dec     edi
0x18005bbdf  test    edi, edi
0x18005bbe1  jle     loc_18005BC73
0x18005bbe7  mov     r12, [r14+48h]
0x18005bbeb  movsxd  rax, edi
0x18005bbee  movsxd  r13, dword ptr [rcx+rax*4]
0x18005bbf2  cmp     dword ptr [r12+r13], 0
0x18005bbf7  jz      short loc_18005BBDD
0x18005bbf9  movsxd  rdx, dword ptr [r12+r13]
0x18005bbfd  mov     rcx, r8; String1
0x18005bc00  add     rdx, r12; String2
0x18005bc03  call    cs:__imp__wcsicmp
0x18005bc09  test    eax, eax
0x18005bc0b  jz      short loc_18005BC19
0x18005bc0d  mov     rcx, [rsp+58h+arg_0]
0x18005bc12  mov     r8, [rsp+58h+arg_10]
0x18005bc17  jmp     short loc_18005BBDD
0x18005bc19  mov     r14d, [r12+r13+10h]
0x18005bc1e  mov     ecx, 28h ; '('; Size
0x18005bc23  mov     r12, [rbx+10h]
0x18005bc27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bc2c  test    rax, rax
0x18005bc2f  jz      loc_18005BCBD
0x18005bc35  mov     rcx, rax; this
0x18005bc38  call    ??0CCodeContext@@QEAA@XZ; CCodeContext::CCodeContext(void)
0x18005bc3d  mov     rdi, rax
0x18005bc40  test    rax, rax
0x18005bc43  jz      short loc_18005BCBD
0x18005bc45  mov     r8d, r14d; int
0x18005bc48  mov     rdx, r12; struct CScriptBody *
0x18005bc4b  mov     rcx, rax; this
0x18005bc4e  call    ?Init@CCodeContext@@QEAAJPEAVCScriptBody@@J@Z; CCodeContext::Init(CScriptBody *,long)
0x18005bc53  test    eax, eax
0x18005bc55  js      short loc_18005BC69
0x18005bc57  mov     r8, [rbx+18h]; unsigned __int16 *
0x18005bc5b  mov     r9, rbp; struct IDebugProperty **
0x18005bc5e  mov     rdx, rdi; struct IDebugCodeContext *
0x18005bc61  mov     rcx, r15; this
0x18005bc64  call    ?DbgCreateBrowserFromCodeContext@COleScript@@QEAAJPEAUIDebugCodeContext@@PEBGPEAPEAUIDebugProperty@@@Z; COleScript::DbgCreateBrowserFromCodeContext(IDebugCodeContext *,ushort const *,IDebugProperty * *)
0x18005bc69  mov     rcx, rdi; this
0x18005bc6c  call    ?Release@CCodeContext@@UEAAKXZ; CCodeContext::Release(void)
0x18005bc71  jmp     short loc_18005BCBD
0x18005bc73  mov     ecx, 80h; Size
0x18005bc78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bc7d  test    rax, rax
0x18005bc80  jz      short loc_18005BCBD
0x18005bc82  mov     rcx, rax; this
0x18005bc85  call    ??0CActiveScriptError@@QEAA@XZ; CActiveScriptError::CActiveScriptError(void)
0x18005bc8a  mov     rdi, rax
0x18005bc8d  test    rax, rax
0x18005bc90  jz      short loc_18005BCBD
0x18005bc92  lea     rcx, [rax+18h]
0x18005bc96  mov     dword ptr [rcx+38h], 800A0023h
0x18005bc9d  call    ExcepInfoDeferredFillIn
0x18005bca2  mov     r8, [rbx+18h]; unsigned __int16 *
0x18005bca6  lea     rdx, [rdi+8]; struct IActiveScriptError *
0x18005bcaa  mov     r9, rbp; struct IDebugProperty **
0x18005bcad  mov     rcx, r15; this
0x18005bcb0  call    ?DbgCreateBrowserFromError@COleScript@@QEAAJPEAUIActiveScriptError@@PEBGPEAPEAUIDebugProperty@@@Z; COleScript::DbgCreateBrowserFromError(IActiveScriptError *,ushort const *,IDebugProperty * *)
0x18005bcb5  mov     rcx, rdi; this
0x18005bcb8  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x18005bcbd  test    rsi, rsi
0x18005bcc0  jz      short loc_18005BCD1
0x18005bcc2  mov     rax, [rsi]
0x18005bcc5  mov     rcx, rsi
0x18005bcc8  mov     rax, [rax+18h]
0x18005bccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcd1  xor     ebx, ebx
0x18005bcd3  lea     rcx, [rsp+58h+arg_18]; this
0x18005bcd8  call    ??1LockOleScript@@QEAA@XZ; LockOleScript::~LockOleScript(void)
0x18005bcdd  mov     eax, ebx
0x18005bcdf  mov     rbx, [rsp+58h+arg_8]
0x18005bce4  add     rsp, 20h
0x18005bce8  pop     r15
0x18005bcea  pop     r14
0x18005bcec  pop     r13
0x18005bcee  pop     r12
0x18005bcf0  pop     rdi
0x18005bcf1  pop     rsi
0x18005bcf2  pop     rbp
0x18005bcf3  retn
```
