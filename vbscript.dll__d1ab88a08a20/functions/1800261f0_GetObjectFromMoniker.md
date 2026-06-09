# GetObjectFromMoniker

- ea: `0x1800261f0`
- end: `0x180026379`
- name: `GetObjectFromMoniker`
- size: `393`
- prototype: `HRESULT __fastcall(CSession **this, OLECHAR *szUserName, struct VAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180042d28`

## callees

- `0x18001ad94`
- `0x1800261f0`
- `0x180026570`
- `0x180037330`
- `0x180061148`
- `0x180061388`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180026214`
- `OLEAUT32!__imp_SysStringLen` at `0x180026214`
- `OLE32!CreateBindCtx` at `0x180026254`
- `OLE32!CreateBindCtx` at `0x180026254`
- `OLE32!BindMoniker` at `0x1800262c5`
- `OLE32!BindMoniker` at `0x1800262c5`
- `OLE32!MkParseDisplayName` at `0x180026286`
- `OLE32!MkParseDisplayName` at `0x180026286`

## pseudocode

```c
HRESULT __fastcall GetObjectFromMoniker(CSession **this, OLECHAR *szUserName, struct VAR *a3)
{
  HRESULT result; // eax
  HRESULT v7; // ebx
  const struct _GUID *v8; // rdx
  CSession *v9; // rdi
  ULONG pchEaten; // [rsp+20h] [rbp-60h] BYREF
  LPMONIKER ppmk; // [rsp+28h] [rbp-58h] BYREF
  LPBC ppbc; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppvResult; // [rsp+38h] [rbp-48h] BYREF
  struct tagEXCEPINFO v14; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+B8h] [rbp+38h] BYREF

  if ( !SysStringLen(szUserName) )
    return -2146828283;
  if ( (unsigned int)COleScript::InSafeMode((COleScript *)this, 0) )
    return -2146827859;
  ppbc = 0;
  result = CreateBindCtx(0, &ppbc);
  if ( result >= 0 )
  {
    pchEaten = 0;
    ppmk = 0;
    v7 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v7 >= 0 )
    {
      ppvResult = 0;
      v15 = BindMoniker(ppmk, 0, &IID_IUnknown, &ppvResult);
      v7 = v15;
      if ( v15 < 0 )
      {
        v9 = this[80];
        if ( v9 )
        {
          if ( (unsigned int)FSupportsErrorInfo((struct IUnknown *)ppmk, v8) )
          {
            memset_0(&v14, 0, sizeof(v14));
            if ( !(unsigned int)GetErrorInfo(&v14) )
            {
              v14.wCode = 0;
              v14.scode = v7;
              CSession::RecordExcepInfoAndClear(v9, &v14, &v15);
              v7 = v15;
            }
          }
        }
      }
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
      if ( v7 >= 0 )
      {
        v7 = PrepareObject((struct COleScript *)this, (struct IUnknown *)ppvResult, a3);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvResult + 16LL))(ppvResult);
      }
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800261f0  mov     [rsp-18h+arg_0], rbx
0x1800261f5  mov     [rsp-18h+arg_8], rsi
0x1800261fa  push    rbp
0x1800261fb  push    rdi
0x1800261fc  push    r14
0x1800261fe  mov     rbp, rsp
0x180026201  sub     rsp, 80h
0x180026208  mov     rsi, rcx
0x18002620b  mov     r14, r8
0x18002620e  mov     rcx, rdx; pbstr
0x180026211  mov     rbx, rdx
0x180026214  call    cs:__imp_SysStringLen
0x18002621b  nop     dword ptr [rax+rax+00h]
0x180026220  test    eax, eax
0x180026222  jnz     short loc_18002622E
0x180026224  mov     eax, 800A0005h
0x180026229  jmp     loc_180026360
0x18002622e  xor     edx, edx; struct _GUID *
0x180026230  mov     rcx, rsi; this
0x180026233  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180026238  test    eax, eax
0x18002623a  jz      short loc_180026246
0x18002623c  mov     eax, 800A01ADh
0x180026241  jmp     loc_180026360
0x180026246  lea     rdx, [rbp+ppbc]; ppbc
0x18002624a  mov     [rbp+ppbc], 0
0x180026252  xor     ecx, ecx; reserved
0x180026254  call    cs:__imp_CreateBindCtx
0x18002625b  nop     dword ptr [rax+rax+00h]
0x180026260  test    eax, eax
0x180026262  js      loc_180026360
0x180026268  mov     rcx, [rbp+ppbc]; pbc
0x18002626c  lea     r9, [rbp+ppmk]; ppmk
0x180026270  lea     r8, [rbp+pchEaten]; pchEaten
0x180026274  mov     [rbp+pchEaten], 0
0x18002627b  mov     rdx, rbx; szUserName
0x18002627e  mov     [rbp+ppmk], 0
0x180026286  call    cs:__imp_MkParseDisplayName
0x18002628d  nop     dword ptr [rax+rax+00h]
0x180026292  mov     rcx, [rbp+ppbc]
0x180026296  mov     ebx, eax
0x180026298  mov     rdx, [rcx]
0x18002629b  mov     rax, [rdx+10h]
0x18002629f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a4  test    ebx, ebx
0x1800262a6  js      loc_18002635E
0x1800262ac  mov     rcx, [rbp+ppmk]; pmk
0x1800262b0  lea     r9, [rbp+ppvResult]; ppvResult
0x1800262b4  lea     r8, IID_IUnknown; iidResult
0x1800262bb  mov     [rbp+ppvResult], 0
0x1800262c3  xor     edx, edx; grfOpt
0x1800262c5  call    cs:__imp_BindMoniker
0x1800262cc  nop     dword ptr [rax+rax+00h]
0x1800262d1  mov     [rbp+arg_18], eax
0x1800262d4  mov     ebx, eax
0x1800262d6  test    eax, eax
0x1800262d8  jns     short loc_180026329
0x1800262da  mov     rdi, [rsi+280h]
0x1800262e1  test    rdi, rdi
0x1800262e4  jz      short loc_180026329
0x1800262e6  mov     rcx, [rbp+ppmk]; struct IUnknown *
0x1800262ea  call    ?FSupportsErrorInfo@@YAHPEAUIUnknown@@AEBU_GUID@@@Z; FSupportsErrorInfo(IUnknown *,_GUID const &)
0x1800262ef  test    eax, eax
0x1800262f1  jz      short loc_180026329
0x1800262f3  xor     edx, edx; Val
0x1800262f5  lea     rcx, [rbp+var_40]; void *
0x1800262f9  lea     r8d, [rdx+40h]; Size
0x1800262fd  call    memset_0
0x180026302  lea     rcx, [rbp+var_40]; struct tagEXCEPINFO *
0x180026306  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x18002630b  test    eax, eax
0x18002630d  jnz     short loc_180026329
0x18002630f  lea     r8, [rbp+arg_18]; int *
0x180026313  mov     [rbp+var_40.wCode], ax
0x180026317  lea     rdx, [rbp+var_40]; struct tagEXCEPINFO *
0x18002631b  mov     [rbp+var_40.scode], ebx
0x18002631e  mov     rcx, rdi; this
0x180026321  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x180026326  mov     ebx, [rbp+arg_18]
0x180026329  mov     rcx, [rbp+ppmk]
0x18002632d  mov     rdx, [rcx]
0x180026330  mov     rax, [rdx+10h]
0x180026334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026339  test    ebx, ebx
0x18002633b  js      short loc_18002635E
0x18002633d  mov     rdx, [rbp+ppvResult]; struct IUnknown *
0x180026341  mov     r8, r14; struct VAR *
0x180026344  mov     rcx, rsi; struct COleScript *
0x180026347  call    ?PrepareObject@@YAJPEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(COleScript *,IUnknown *,VAR *)
0x18002634c  mov     rcx, [rbp+ppvResult]
0x180026350  mov     ebx, eax
0x180026352  mov     rdx, [rcx]
0x180026355  mov     rax, [rdx+10h]
0x180026359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002635e  mov     eax, ebx
0x180026360  lea     r11, [rsp+80h+var_s0]
0x180026368  mov     rbx, [r11+20h]
0x18002636c  mov     rsi, [r11+28h]
0x180026370  mov     rsp, r11
0x180026373  pop     r14
0x180026375  pop     rdi
0x180026376  pop     rbp
0x180026377  retn
```
