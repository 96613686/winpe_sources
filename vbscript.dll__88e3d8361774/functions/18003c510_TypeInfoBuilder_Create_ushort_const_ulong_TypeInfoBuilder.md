# TypeInfoBuilder::Create(ushort const *,ulong,TypeInfoBuilder * *)

- ea: `0x18003c510`
- end: `0x18003c74a`
- name: `?Create@TypeInfoBuilder@@SAJPEBGKPEAPEAV1@@Z`
- size: `570`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct TypeInfoBuilder **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004ba30`
- `0x18005c380`

## callees

- `0x18003c510`
- `0x180041b70`
- `0x180045490`
- `0x180064d8c`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18003c58a`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18003c58a`

## pseudocode

```c
__int64 __fastcall TypeInfoBuilder::Create(const unsigned __int16 *a1, unsigned int a2, ICreateTypeLib2 ***a3)
{
  ICreateTypeLib2 **v6; // rax
  ICreateTypeLib2 **v7; // rbx
  HRESULT DispatchTypeInfo; // edi
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  struct ITypeInfo *v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v6 = (ICreateTypeLib2 **)operator new(0x18u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    DispatchTypeInfo = GetDispatchTypeInfo(&v13);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v9 = v7 + 2;
    DispatchTypeInfo = CreateTypeLib2(SYS_WIN32, L"VBSDeb.tlb", v7 + 2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 80LL))(*v9, a2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 32LL))(
                         *v9,
                         L"VBScriptTypeLib");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 56LL))(
                         *v9,
                         L"Visual Basic Scripting Type Library");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v9 + 40LL))(*v9, 10, 8);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v9 + 48LL))(*v9, &IID_IScriptTypeLib);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 88LL))(*v9, 0);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v10 = *v9;
    v11 = v7 + 1;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, ICreateTypeLib2 **))(*(_QWORD *)v10 + 24LL))(
                         v10,
                         a1,
                         4,
                         v7 + 1);
    if ( DispatchTypeInfo < 0
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v11 + 40LL))(
                               *v11,
                               L"Visual Basic Scripting Type Info"),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 24LL))(
                               *v11,
                               &IID_IScriptTypeInfo),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v11 + 56LL))(*v11, 10, 8),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, struct ITypeInfo *, unsigned int *))(*(_QWORD *)*v11 + 64LL))(
                               *v11,
                               v13,
                               &v14),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 80LL))(*v11, 0, v14),
          DispatchTypeInfo < 0) )
    {
LABEL_17:
      TypeInfoBuilder::Release((TypeInfoBuilder *)v7);
    }
    else
    {
      DispatchTypeInfo = 0;
      *a3 = v7;
    }
  }
  else
  {
    DispatchTypeInfo = -2147024882;
  }
  if ( v13 )
    ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->Release)(v13);
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x18003c510  mov     rax, rsp
0x18003c513  push    rbx
0x18003c514  push    rbp
0x18003c515  push    rsi
0x18003c516  push    rdi
0x18003c517  push    r14
0x18003c519  push    r15
0x18003c51b  sub     rsp, 48h
0x18003c51f  mov     r15, rcx
0x18003c522  mov     dword ptr [rax+20h], 0
0x18003c529  mov     ecx, 18h; Size
0x18003c52e  mov     qword ptr [rax-48h], 0
0x18003c536  mov     r14, r8
0x18003c539  mov     ebp, edx
0x18003c53b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c540  mov     rbx, rax
0x18003c543  test    rax, rax
0x18003c546  jz      loc_18003C720
0x18003c54c  lea     rcx, [rsp+78h+var_48]; struct ITypeInfo **
0x18003c551  mov     qword ptr [rax], 0
0x18003c558  mov     qword ptr [rax+8], 0
0x18003c560  mov     qword ptr [rax+10h], 0
0x18003c568  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x18003c56d  mov     edi, eax
0x18003c56f  test    eax, eax
0x18003c571  js      loc_18003C716
0x18003c577  lea     rsi, [rbx+10h]
0x18003c57b  mov     ecx, 1; syskind
0x18003c580  mov     r8, rsi; ppctlib
0x18003c583  lea     rdx, szFile; "VBSDeb.tlb"
0x18003c58a  call    cs:__imp_CreateTypeLib2
0x18003c590  mov     edi, eax
0x18003c592  test    eax, eax
0x18003c594  js      loc_18003C716
0x18003c59a  mov     rcx, [rsi]
0x18003c59d  mov     edx, ebp
0x18003c59f  mov     rax, [rcx]
0x18003c5a2  mov     rax, [rax+50h]
0x18003c5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5ab  mov     edi, eax
0x18003c5ad  test    eax, eax
0x18003c5af  js      loc_18003C716
0x18003c5b5  mov     rcx, [rsi]
0x18003c5b8  lea     rdx, aVbscripttypeli; "VBScriptTypeLib"
0x18003c5bf  mov     rax, [rcx]
0x18003c5c2  mov     rax, [rax+20h]
0x18003c5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5cb  mov     edi, eax
0x18003c5cd  test    eax, eax
0x18003c5cf  js      loc_18003C716
0x18003c5d5  mov     rcx, [rsi]
0x18003c5d8  lea     rdx, aVisualBasicScr; "Visual Basic Scripting Type Library"
0x18003c5df  mov     rax, [rcx]
0x18003c5e2  mov     rax, [rax+38h]
0x18003c5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5eb  mov     edi, eax
0x18003c5ed  test    eax, eax
0x18003c5ef  js      loc_18003C716
0x18003c5f5  mov     rcx, [rsi]
0x18003c5f8  mov     ebp, 8
0x18003c5fd  mov     r8d, ebp
0x18003c600  mov     rax, [rcx]
0x18003c603  lea     edx, [rbp+2]
0x18003c606  mov     rax, [rax+28h]
0x18003c60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c60f  mov     edi, eax
0x18003c611  test    eax, eax
0x18003c613  js      loc_18003C716
0x18003c619  mov     rcx, [rsi]
0x18003c61c  lea     rdx, IID_IScriptTypeLib
0x18003c623  mov     rax, [rcx]
0x18003c626  mov     rax, [rax+30h]
0x18003c62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c62f  mov     edi, eax
0x18003c631  test    eax, eax
0x18003c633  js      loc_18003C716
0x18003c639  mov     rcx, [rsi]
0x18003c63c  xor     edx, edx
0x18003c63e  mov     rax, [rcx]
0x18003c641  mov     rax, [rax+58h]
0x18003c645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c64a  mov     edi, eax
0x18003c64c  test    eax, eax
0x18003c64e  js      loc_18003C716
0x18003c654  mov     rcx, [rsi]
0x18003c657  lea     r8d, [rbp-4]
0x18003c65b  lea     rsi, [rbx+8]
0x18003c65f  mov     rdx, r15
0x18003c662  mov     r9, rsi
0x18003c665  mov     rax, [rcx]
0x18003c668  mov     rax, [rax+18h]
0x18003c66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c671  mov     edi, eax
0x18003c673  test    eax, eax
0x18003c675  js      loc_18003C716
0x18003c67b  mov     rcx, [rsi]
0x18003c67e  lea     rdx, aVisualBasicScr_0; "Visual Basic Scripting Type Info"
0x18003c685  mov     rax, [rcx]
0x18003c688  mov     rax, [rax+28h]
0x18003c68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c691  mov     edi, eax
0x18003c693  test    eax, eax
0x18003c695  js      short loc_18003C716
0x18003c697  mov     rcx, [rsi]
0x18003c69a  lea     rdx, IID_IScriptTypeInfo
0x18003c6a1  mov     rax, [rcx]
0x18003c6a4  mov     rax, [rax+18h]
0x18003c6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6ad  mov     edi, eax
0x18003c6af  test    eax, eax
0x18003c6b1  js      short loc_18003C716
0x18003c6b3  mov     rcx, [rsi]
0x18003c6b6  lea     edx, [rbp+2]
0x18003c6b9  mov     r8d, ebp
0x18003c6bc  mov     rax, [rcx]
0x18003c6bf  mov     rax, [rax+38h]
0x18003c6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6c8  mov     edi, eax
0x18003c6ca  test    eax, eax
0x18003c6cc  js      short loc_18003C716
0x18003c6ce  mov     rcx, [rsi]
0x18003c6d1  lea     r8, [rsp+78h+arg_18]
0x18003c6d9  mov     rdx, [rsp+78h+var_48]
0x18003c6de  mov     rax, [rcx]
0x18003c6e1  mov     rax, [rax+40h]
0x18003c6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6ea  mov     edi, eax
0x18003c6ec  test    eax, eax
0x18003c6ee  js      short loc_18003C716
0x18003c6f0  mov     rcx, [rsi]
0x18003c6f3  xor     edx, edx
0x18003c6f5  mov     r8d, [rsp+78h+arg_18]
0x18003c6fd  mov     rax, [rcx]
0x18003c700  mov     rax, [rax+50h]
0x18003c704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c709  mov     edi, eax
0x18003c70b  test    eax, eax
0x18003c70d  js      short loc_18003C716
0x18003c70f  xor     edi, edi
0x18003c711  mov     [r14], rbx
0x18003c714  jmp     short loc_18003C725
0x18003c716  mov     rcx, rbx; this
0x18003c719  call    ?Release@TypeInfoBuilder@@QEAAXXZ; TypeInfoBuilder::Release(void)
0x18003c71e  jmp     short loc_18003C725
0x18003c720  mov     edi, 8007000Eh
0x18003c725  mov     rcx, [rsp+78h+var_48]
0x18003c72a  test    rcx, rcx
0x18003c72d  jz      short loc_18003C73B
0x18003c72f  mov     rax, [rcx]
0x18003c732  mov     rax, [rax+10h]
0x18003c736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c73b  mov     eax, edi
0x18003c73d  add     rsp, 48h
0x18003c741  pop     r15
0x18003c743  pop     r14
0x18003c745  pop     rdi
0x18003c746  pop     rsi
0x18003c747  pop     rbp
0x18003c748  pop     rbx
0x18003c749  retn
```
