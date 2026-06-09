# ShellItemFromFileSystemPath(ushort const *,_GUID const &,void * *,IBindCtx *)

- ea: `0x180057fbc`
- end: `0x1800580a5`
- name: `?ShellItemFromFileSystemPath@@YAJPEBGAEBU_GUID@@PEAPEAXPEAUIBindCtx@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(PCWSTR pszPath, const struct _GUID *, void **, struct IBindCtx *)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180057610`
- `0x180059000`
- `0x18005df84`
- `0x180062d2c`
- `0x18006644c`
- `0x180068128`

## callees

- `0x18001367c`
- `0x180031e94`
- `0x180036f50`
- `0x180057ed8`
- `0x180057fbc`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180058079`
- `SHELL32!SHCreateItemFromParsingName` at `0x180058079`
- `ole32!CreateBindCtx` at `0x180058025`
- `ole32!CreateBindCtx` at `0x180058025`

## string_xrefs

- `0x180058055`: `shell\ext\zip\archive\precomp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellItemFromFileSystemPath(PCWSTR pszPath, const struct _GUID *a2, void **a3, struct IBindCtx *a4)
{
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  LPBC v11; // [rsp+20h] [rbp-30h] BYREF
  struct tagVARIANT v12; // [rsp+28h] [rbp-28h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  ppbc = 0;
  if ( a4 )
  {
    ((void (__fastcall *)(struct IBindCtx *, const struct _GUID *))a4->lpVtbl->AddRef)(a4, a2);
    v11 = ppbc;
    ppbc = a4;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
    CreateBindCtx(0, &ppbc);
  }
  v12.vt = 19;
  v12.lVal = 16;
  v8 = wil::ShellBindContextHelper::Set((wil::ShellBindContextHelper *)&ppbc, v7, &v12);
  v9 = v8;
  if ( v8 >= 0 )
    v9 = SHCreateItemFromParsingName(pszPath, ppbc, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a3);
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D5,
      (unsigned int)"shell\\ext\\zip\\archive\\precomp.h",
      (const char *)(unsigned int)v8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  return v9;
}

```

## disassembly

```asm
0x180057fbc  mov     [rsp-18h+arg_8], rbx
0x180057fc1  push    rbp
0x180057fc2  push    rsi
0x180057fc3  push    rdi
0x180057fc4  mov     rbp, rsp
0x180057fc7  sub     rsp, 50h
0x180057fcb  mov     rax, cs:__security_cookie
0x180057fd2  xor     rax, rsp
0x180057fd5  mov     [rbp+var_8], rax
0x180057fd9  mov     rbx, r9
0x180057fdc  mov     rsi, r8
0x180057fdf  mov     rdi, rcx
0x180057fe2  mov     [rbp+ppbc], 0
0x180057fea  test    r9, r9
0x180057fed  jz      short loc_180058016
0x180057fef  mov     rax, [r9]
0x180057ff2  mov     rcx, rbx
0x180057ff5  mov     rax, [rax+8]
0x180057ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ffe  nop
0x180057fff  mov     rax, [rbp+ppbc]
0x180058003  mov     [rbp+var_30], rax
0x180058007  mov     [rbp+ppbc], rbx
0x18005800b  lea     rcx, [rbp+var_30]
0x18005800f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058014  jmp     short loc_18005802B
0x180058016  lea     rcx, [rbp+ppbc]
0x18005801a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005801f  lea     rdx, [rbp+ppbc]; ppbc
0x180058023  xor     ecx, ecx; reserved
0x180058025  call    cs:__imp_CreateBindCtx
0x18005802b  mov     eax, 13h
0x180058030  mov     word ptr [rbp+var_28], ax
0x180058034  mov     dword ptr [rbp+var_28+8], 10h
0x18005803b  lea     r8, [rbp+var_28]; struct tagVARIANT *
0x18005803f  lea     rcx, [rbp+ppbc]; this
0x180058043  call    ?Set@ShellBindContextHelper@wil@@QEAAJPEBGAEBUtagVARIANT@@@Z; wil::ShellBindContextHelper::Set(ushort const *,tagVARIANT const &)
0x180058048  mov     ebx, eax
0x18005804a  test    eax, eax
0x18005804c  jns     short loc_180058068
0x18005804e  mov     rcx, [rbp+18h]
0x180058052  mov     r9d, eax
0x180058055  lea     r8, aShellExtZipArc_4; "shell\\ext\\zip\\archive\\precomp.h"
0x18005805c  mov     edx, 4D5h
0x180058061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058066  jmp     short loc_180058081
0x180058068  mov     r9, rsi; ppv
0x18005806b  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180058072  mov     rdx, [rbp+ppbc]; pbc
0x180058076  mov     rcx, rdi; pszPath
0x180058079  call    cs:__imp_SHCreateItemFromParsingName
0x18005807f  mov     ebx, eax
0x180058081  lea     rcx, [rbp+ppbc]
0x180058085  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005808a  mov     eax, ebx
0x18005808c  mov     rcx, [rbp+var_8]
0x180058090  xor     rcx, rsp; StackCookie
0x180058093  call    __security_check_cookie
0x180058098  mov     rbx, [rsp+50h+arg_8]
0x18005809d  add     rsp, 50h
0x1800580a1  pop     rdi
0x1800580a2  pop     rsi
0x1800580a3  pop     rbp
0x1800580a4  retn
```
