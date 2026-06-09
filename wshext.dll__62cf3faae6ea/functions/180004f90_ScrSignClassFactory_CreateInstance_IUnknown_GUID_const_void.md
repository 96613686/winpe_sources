# ScrSignClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004f90`
- end: `0x1800050e6`
- name: `?CreateInstance@ScrSignClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `342`
- prototype: `__int64 __fastcall(ScrSignClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003200`
- `0x180004f90`
- `0x1800050ec`
- `0x180007fc4`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180005031`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180005031`

## pseudocode

```c
__int64 __fastcall ScrSignClassFactory::CreateInstance(
        ScrSignClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v7; // edi
  CScriptSigningControl *v8; // rsi
  CScriptSigningControl *v9; // rax
  CScriptSigningControl *v10; // rbx
  void *v11; // [rsp+30h] [rbp-28h] BYREF
  ITypeLib *pptlib; // [rsp+78h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  v11 = 0;
  if ( !a2 )
  {
    v7 = -2147467262;
    if ( !(unsigned int)DoGuidsMatch((const struct _GUID *)((char *)this + 12), &CLSID_Signer) )
      goto LABEL_21;
    v8 = 0;
    pptlib = 0;
    v9 = (CScriptSigningControl *)operator new(0x18u);
    if ( v9 )
    {
      v10 = CScriptSigningControl::CScriptSigningControl(v9);
      if ( v10 )
      {
        v7 = LoadRegTypeLib(&LIBID_ScriptSigner, 1u, 0, 0x409u, &pptlib);
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, char *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                 pptlib,
                 &IID_IScriptSigningControl,
                 (char *)v10 + 16);
          if ( v7 >= 0 )
          {
            v8 = v10;
            v10 = 0;
            v7 = 0;
          }
        }
        goto LABEL_13;
      }
    }
    else
    {
      v10 = 0;
    }
    v7 = -2147024882;
LABEL_13:
    if ( pptlib )
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    if ( v10 )
      (*(void (__fastcall **)(CScriptSigningControl *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v7 >= 0 )
      v7 = (**(__int64 (__fastcall ***)(CScriptSigningControl *, const struct _GUID *, void **))v8)(v8, a3, &v11);
    if ( v8 )
      (*(void (__fastcall **)(CScriptSigningControl *))(*(_QWORD *)v8 + 16LL))(v8);
    goto LABEL_21;
  }
  v7 = -2147221232;
LABEL_21:
  *a4 = v11;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004f90  mov     [rsp+arg_0], rbx
0x180004f95  mov     [rsp+arg_8], rbp
0x180004f9a  push    rsi
0x180004f9b  push    rdi
0x180004f9c  push    r14
0x180004f9e  sub     rsp, 40h
0x180004fa2  mov     r14, r9
0x180004fa5  mov     rbp, r8
0x180004fa8  test    r9, r9
0x180004fab  jnz     short loc_180004FB7
0x180004fad  mov     eax, 80004003h
0x180004fb2  jmp     loc_1800050D3
0x180004fb7  mov     [rsp+58h+var_28], 0
0x180004fc0  test    rdx, rdx
0x180004fc3  jz      short loc_180004FCF
0x180004fc5  mov     edi, 80040110h
0x180004fca  jmp     loc_1800050C9
0x180004fcf  add     rcx, 0Ch; struct _GUID *
0x180004fd3  lea     rdx, CLSID_Signer; struct _GUID *
0x180004fda  mov     edi, 80004002h
0x180004fdf  call    ?DoGuidsMatch@@YAHAEBU_GUID@@0@Z; DoGuidsMatch(_GUID const &,_GUID const &)
0x180004fe4  test    eax, eax
0x180004fe6  jz      loc_1800050C9
0x180004fec  xor     esi, esi
0x180004fee  mov     [rsp+58h+arg_18], 0
0x180004ff7  lea     ecx, [rsi+18h]; Size
0x180004ffa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fff  test    rax, rax
0x180005002  jz      short loc_180005068
0x180005004  mov     rcx, rax; this
0x180005007  call    ??0CScriptSigningControl@@AEAA@XZ; CScriptSigningControl::CScriptSigningControl(void)
0x18000500c  mov     rbx, rax
0x18000500f  test    rax, rax
0x180005012  jz      short loc_18000506A
0x180005014  lea     rax, [rsp+58h+arg_18]
0x180005019  xor     r8d, r8d; wVerMinor
0x18000501c  lea     edx, [rsi+1]; wVerMajor
0x18000501f  mov     [rsp+58h+pptlib], rax; pptlib
0x180005024  mov     r9d, 409h; lcid
0x18000502a  lea     rcx, LIBID_ScriptSigner; rguid
0x180005031  call    cs:__imp_LoadRegTypeLib
0x180005037  mov     edi, eax
0x180005039  test    eax, eax
0x18000503b  js      short loc_18000506F
0x18000503d  mov     rcx, [rsp+58h+arg_18]
0x180005042  lea     r8, [rbx+10h]
0x180005046  lea     rdx, IID_IScriptSigningControl
0x18000504d  mov     rax, [rcx]
0x180005050  mov     rax, [rax+30h]
0x180005054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005059  mov     edi, eax
0x18000505b  test    eax, eax
0x18000505d  js      short loc_18000506F
0x18000505f  mov     rsi, rbx
0x180005062  xor     ebx, ebx
0x180005064  xor     edi, edi
0x180005066  jmp     short loc_18000506F
0x180005068  xor     ebx, ebx
0x18000506a  mov     edi, 8007000Eh
0x18000506f  mov     rcx, [rsp+58h+arg_18]
0x180005074  test    rcx, rcx
0x180005077  jz      short loc_180005085
0x180005079  mov     rax, [rcx]
0x18000507c  mov     rax, [rax+10h]
0x180005080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005085  test    rbx, rbx
0x180005088  jz      short loc_180005099
0x18000508a  mov     rax, [rbx]
0x18000508d  mov     rcx, rbx
0x180005090  mov     rax, [rax+10h]
0x180005094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005099  test    edi, edi
0x18000509b  js      short loc_1800050B5
0x18000509d  mov     rax, [rsi]
0x1800050a0  lea     r8, [rsp+58h+var_28]
0x1800050a5  mov     rdx, rbp
0x1800050a8  mov     rcx, rsi
0x1800050ab  mov     rax, [rax]
0x1800050ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b3  mov     edi, eax
0x1800050b5  test    rsi, rsi
0x1800050b8  jz      short loc_1800050C9
0x1800050ba  mov     rax, [rsi]
0x1800050bd  mov     rcx, rsi
0x1800050c0  mov     rax, [rax+10h]
0x1800050c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c9  mov     rax, [rsp+58h+var_28]
0x1800050ce  mov     [r14], rax
0x1800050d1  mov     eax, edi
0x1800050d3  mov     rbx, [rsp+58h+arg_0]
0x1800050d8  mov     rbp, [rsp+58h+arg_8]
0x1800050dd  add     rsp, 40h
0x1800050e1  pop     r14
0x1800050e3  pop     rdi
0x1800050e4  pop     rsi
0x1800050e5  retn
```
