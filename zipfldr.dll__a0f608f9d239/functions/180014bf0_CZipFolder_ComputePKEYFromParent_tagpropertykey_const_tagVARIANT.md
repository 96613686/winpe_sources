# CZipFolder::ComputePKEYFromParent(_tagpropertykey const &,tagVARIANT *)

- ea: `0x180014bf0`
- end: `0x180014d58`
- name: `?ComputePKEYFromParent@CZipFolder@@QEAAJAEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `360`
- prototype: `int(CZipFolder *__hidden this, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e2c0`
- `0x180032270`

## callees

- `0x18001367c`
- `0x180014bf0`
- `0x180014d60`
- `0x180031e94`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180014c42`
- `SHELL32!SHCreateItemFromIDList` at `0x180014c42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014cda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d44`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014cda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014d44`
- `OLEAUT32!__imp_VariantInit` at `0x180014c19`
- `OLEAUT32!__imp_VariantInit` at `0x180014c19`

## pseudocode

```c
__int64 __fastcall CZipFolder::ComputePKEYFromParent(
        LPCITEMIDLIST *this,
        const struct _tagpropertykey *a2,
        struct tagVARIANT *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  void *v8; // rcx
  int v10; // eax
  int v11; // eax
  void *v12; // rcx
  void *ppv; // [rsp+20h] [rbp-30h] BYREF
  PROPVARIANT pvar[3]; // [rsp+28h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  VariantInit(a3);
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v6 = SHCreateItemFromIDList(this[139], &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x576,
      (unsigned int)"shell\\ext\\zip\\shlfldr.cpp",
      (const char *)(unsigned int)v6,
      (int)ppv);
    goto LABEL_3;
  }
  LOWORD(pvar[0]) = 0;
  v10 = (*(__int64 (__fastcall **)(void *, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
          ppv,
          a2,
          pvar);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x578,
      (unsigned int)"shell\\ext\\zip\\shlfldr.cpp",
      (const char *)(unsigned int)v10,
      (int)ppv);
    PropVariantClear(pvar);
LABEL_3:
    v8 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v11 = StealVariantFromPropVariant(pvar, a3);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x579,
      (unsigned int)"shell\\ext\\zip\\shlfldr.cpp",
      (const char *)(unsigned int)v11,
      (int)ppv);
    PropVariantClear(pvar);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    return v7;
  }
  PropVariantClear(pvar);
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180014bf0  mov     [rsp-18h+arg_18], rbx
0x180014bf5  push    rbp
0x180014bf6  push    rsi
0x180014bf7  push    rdi
0x180014bf8  mov     rbp, rsp
0x180014bfb  sub     rsp, 50h
0x180014bff  mov     rax, cs:__security_cookie
0x180014c06  xor     rax, rsp
0x180014c09  mov     [rbp+var_10], rax
0x180014c0d  mov     rbx, rcx
0x180014c10  mov     rdi, r8
0x180014c13  mov     rcx, r8; pvarg
0x180014c16  mov     rsi, rdx
0x180014c19  call    cs:__imp_VariantInit
0x180014c1f  lea     rcx, [rbp+ppv]
0x180014c23  mov     [rbp+ppv], 0
0x180014c2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014c30  mov     rcx, [rbx+458h]; pidl
0x180014c37  lea     r8, [rbp+ppv]; ppv
0x180014c3b  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180014c42  call    cs:__imp_SHCreateItemFromIDList
0x180014c48  mov     ebx, eax
0x180014c4a  test    eax, eax
0x180014c4c  jns     short loc_180014CA1
0x180014c4e  mov     rcx, [rbp+18h]; this
0x180014c52  lea     r8, aShellExtZipShl; "shell\\ext\\zip\\shlfldr.cpp"
0x180014c59  mov     r9d, eax; char *
0x180014c5c  mov     edx, 576h; void *
0x180014c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c66  mov     rcx, [rbp+ppv]
0x180014c6a  test    rcx, rcx
0x180014c6d  jz      short loc_180014C83
0x180014c6f  mov     [rbp+ppv], 0
0x180014c77  mov     rax, [rcx]
0x180014c7a  mov     rax, [rax+10h]
0x180014c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c83  mov     eax, ebx
0x180014c85  mov     rcx, [rbp+var_10]
0x180014c89  xor     rcx, rsp; StackCookie
0x180014c8c  call    __security_check_cookie
0x180014c91  mov     rbx, [rsp+50h+arg_18]
0x180014c99  add     rsp, 50h
0x180014c9d  pop     rdi
0x180014c9e  pop     rsi
0x180014c9f  pop     rbp
0x180014ca0  retn
0x180014ca1  mov     rcx, [rbp+ppv]
0x180014ca5  lea     r8, [rbp+pvar]
0x180014ca9  xor     eax, eax
0x180014cab  mov     rdx, rsi
0x180014cae  mov     word ptr [rbp+pvar], ax
0x180014cb2  mov     rax, [rcx]
0x180014cb5  mov     rax, [rax+68h]
0x180014cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cbe  mov     ebx, eax
0x180014cc0  test    eax, eax
0x180014cc2  js      short loc_180014D01
0x180014cc4  mov     rdx, rdi; pvarg
0x180014cc7  lea     rcx, [rbp+pvar]; pvar
0x180014ccb  call    ?StealVariantFromPropVariant@@YAJPEAUtagPROPVARIANT@@PEAUtagVARIANT@@@Z; StealVariantFromPropVariant(tagPROPVARIANT *,tagVARIANT *)
0x180014cd0  mov     ebx, eax
0x180014cd2  test    eax, eax
0x180014cd4  js      short loc_180014D28
0x180014cd6  lea     rcx, [rbp+pvar]; pvar
0x180014cda  call    cs:__imp_PropVariantClear
0x180014ce0  mov     rcx, [rbp+ppv]
0x180014ce4  test    rcx, rcx
0x180014ce7  jz      short loc_180014CFD
0x180014ce9  mov     [rbp+ppv], 0
0x180014cf1  mov     rax, [rcx]
0x180014cf4  mov     rax, [rax+10h]
0x180014cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cfd  xor     eax, eax
0x180014cff  jmp     short loc_180014C85
0x180014d01  mov     rcx, [rbp+18h]; this
0x180014d05  lea     r8, aShellExtZipShl; "shell\\ext\\zip\\shlfldr.cpp"
0x180014d0c  mov     r9d, ebx; char *
0x180014d0f  mov     edx, 578h; void *
0x180014d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d19  lea     rcx, [rbp+pvar]; pvar
0x180014d1d  call    cs:__imp_PropVariantClear
0x180014d23  jmp     loc_180014C66
0x180014d28  mov     rcx, [rbp+18h]; this
0x180014d2c  lea     r8, aShellExtZipShl; "shell\\ext\\zip\\shlfldr.cpp"
0x180014d33  mov     r9d, ebx; char *
0x180014d36  mov     edx, 579h; void *
0x180014d3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d40  lea     rcx, [rbp+pvar]; pvar
0x180014d44  call    cs:__imp_PropVariantClear
0x180014d4a  lea     rcx, [rbp+ppv]
0x180014d4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d53  jmp     loc_180014C83
```
