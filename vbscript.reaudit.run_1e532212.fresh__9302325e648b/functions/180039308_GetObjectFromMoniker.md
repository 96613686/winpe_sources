# GetObjectFromMoniker

- ea: `0x180039308`
- end: `0x180039478`
- name: `GetObjectFromMoniker`
- size: `368`
- prototype: `__int64 __fastcall(struct COleScript *, LPCOLESTR szUserName, struct VAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180041370`

## callees

- `0x18001ff14`
- `0x180035dc4`
- `0x180039308`
- `0x180039668`
- `0x18005f4c4`
- `0x18005f708`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18003932c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003932c`
- `OLE32!CreateBindCtx` at `0x180039366`
- `OLE32!CreateBindCtx` at `0x180039366`
- `OLE32!BindMoniker` at `0x1800393cb`
- `OLE32!BindMoniker` at `0x1800393cb`
- `OLE32!MkParseDisplayName` at `0x180039392`
- `OLE32!MkParseDisplayName` at `0x180039392`

## pseudocode

```c
HRESULT __fastcall GetObjectFromMoniker(CSession **a1, OLECHAR *szUserName, struct VAR *a3)
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
  if ( (unsigned int)COleScript::InSafeMode((COleScript *)a1, 0) )
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
        v9 = a1[80];
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
        v7 = PrepareObject((struct COleScript *)a1, (struct IUnknown *)ppvResult, a3);
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
0x180039308  mov     [rsp-18h+arg_0], rbx
0x18003930d  mov     [rsp-18h+arg_8], rsi
0x180039312  push    rbp
0x180039313  push    rdi
0x180039314  push    r14
0x180039316  mov     rbp, rsp
0x180039319  sub     rsp, 80h
0x180039320  mov     rsi, rcx
0x180039323  mov     r14, r8
0x180039326  mov     rcx, rdx; pbstr
0x180039329  mov     rbx, rdx
0x18003932c  call    cs:__imp_SysStringLen
0x180039332  test    eax, eax
0x180039334  jnz     short loc_180039340
0x180039336  mov     eax, 800A0005h
0x18003933b  jmp     loc_180039460
0x180039340  xor     edx, edx; struct _GUID *
0x180039342  mov     rcx, rsi; this
0x180039345  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x18003934a  test    eax, eax
0x18003934c  jz      short loc_180039358
0x18003934e  mov     eax, 800A01ADh
0x180039353  jmp     loc_180039460
0x180039358  lea     rdx, [rbp+ppbc]; ppbc
0x18003935c  mov     [rbp+ppbc], 0
0x180039364  xor     ecx, ecx; reserved
0x180039366  call    cs:__imp_CreateBindCtx
0x18003936c  test    eax, eax
0x18003936e  js      loc_180039460
0x180039374  mov     rcx, [rbp+ppbc]; pbc
0x180039378  lea     r9, [rbp+ppmk]; ppmk
0x18003937c  lea     r8, [rbp+pchEaten]; pchEaten
0x180039380  mov     [rbp+pchEaten], 0
0x180039387  mov     rdx, rbx; szUserName
0x18003938a  mov     [rbp+ppmk], 0
0x180039392  call    cs:__imp_MkParseDisplayName
0x180039398  mov     rcx, [rbp+ppbc]
0x18003939c  mov     ebx, eax
0x18003939e  mov     rdx, [rcx]
0x1800393a1  mov     rax, [rdx+10h]
0x1800393a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393aa  test    ebx, ebx
0x1800393ac  js      loc_18003945E
0x1800393b2  mov     rcx, [rbp+ppmk]; pmk
0x1800393b6  lea     r9, [rbp+ppvResult]; ppvResult
0x1800393ba  lea     r8, IID_IUnknown; iidResult
0x1800393c1  mov     [rbp+ppvResult], 0
0x1800393c9  xor     edx, edx; grfOpt
0x1800393cb  call    cs:__imp_BindMoniker
0x1800393d1  mov     [rbp+arg_18], eax
0x1800393d4  mov     ebx, eax
0x1800393d6  test    eax, eax
0x1800393d8  jns     short loc_180039429
0x1800393da  mov     rdi, [rsi+280h]
0x1800393e1  test    rdi, rdi
0x1800393e4  jz      short loc_180039429
0x1800393e6  mov     rcx, [rbp+ppmk]; struct IUnknown *
0x1800393ea  call    ?FSupportsErrorInfo@@YAHPEAUIUnknown@@AEBU_GUID@@@Z; FSupportsErrorInfo(IUnknown *,_GUID const &)
0x1800393ef  test    eax, eax
0x1800393f1  jz      short loc_180039429
0x1800393f3  xor     edx, edx; Val
0x1800393f5  lea     rcx, [rbp+var_40]; void *
0x1800393f9  lea     r8d, [rdx+40h]; Size
0x1800393fd  call    memset_0
0x180039402  lea     rcx, [rbp+var_40]; struct tagEXCEPINFO *
0x180039406  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x18003940b  test    eax, eax
0x18003940d  jnz     short loc_180039429
0x18003940f  lea     r8, [rbp+arg_18]; int *
0x180039413  mov     [rbp+var_40.wCode], ax
0x180039417  lea     rdx, [rbp+var_40]; struct tagEXCEPINFO *
0x18003941b  mov     [rbp+var_40.scode], ebx
0x18003941e  mov     rcx, rdi; this
0x180039421  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x180039426  mov     ebx, [rbp+arg_18]
0x180039429  mov     rcx, [rbp+ppmk]
0x18003942d  mov     rdx, [rcx]
0x180039430  mov     rax, [rdx+10h]
0x180039434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039439  test    ebx, ebx
0x18003943b  js      short loc_18003945E
0x18003943d  mov     rdx, [rbp+ppvResult]; struct IUnknown *
0x180039441  mov     r8, r14; struct VAR *
0x180039444  mov     rcx, rsi; struct COleScript *
0x180039447  call    ?PrepareObject@@YAJPEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(COleScript *,IUnknown *,VAR *)
0x18003944c  mov     rcx, [rbp+ppvResult]
0x180039450  mov     ebx, eax
0x180039452  mov     rdx, [rcx]
0x180039455  mov     rax, [rdx+10h]
0x180039459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003945e  mov     eax, ebx
0x180039460  lea     r11, [rsp+80h+var_s0]
0x180039468  mov     rbx, [r11+20h]
0x18003946c  mov     rsi, [r11+28h]
0x180039470  mov     rsp, r11
0x180039473  pop     r14
0x180039475  pop     rdi
0x180039476  pop     rbp
0x180039477  retn
```
