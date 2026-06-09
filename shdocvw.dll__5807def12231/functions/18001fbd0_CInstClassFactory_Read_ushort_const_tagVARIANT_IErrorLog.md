# CInstClassFactory::Read(ushort const *,tagVARIANT *,IErrorLog *)

- ea: `0x18001fbd0`
- end: `0x18001fc69`
- name: `?Read@CInstClassFactory@@UEAAJPEBGPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `153`
- prototype: `int(CInstClassFactory *__hidden this, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001fbd0`
- `0x180029010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18001fbec`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001fc2f`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001fbec`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001fc2f`
- `PROPSYS!InitVariantFromBuffer` at `0x18001fc00`
- `PROPSYS!InitVariantFromBuffer` at `0x18001fc00`

## string_xrefs

- `0x18001fbdf`: `THIS.CLSID`
- `0x18001fc28`: `ShellLinkDataFlags`

## pseudocode

```c
HRESULT __fastcall CInstClassFactory::Read(
        CInstClassFactory *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct IErrorLog *a4)
{
  HRESULT result; // eax
  __int64 v9; // rax

  if ( !StrCmpICW(L"THIS.CLSID", a2) )
    return InitVariantFromBuffer((char *)this + 32, 0x10u, a3);
  v9 = *((_QWORD *)this + 6) - *(_QWORD *)&CLSID_FolderShortcut.Data1;
  if ( !v9 )
    v9 = *((_QWORD *)this + 7) - *(_QWORD *)CLSID_FolderShortcut.Data4;
  if ( v9 )
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             a2,
             a3,
             a4);
  result = StrCmpICW(L"ShellLinkDataFlags", a2);
  if ( result )
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             a2,
             a3,
             a4);
  a3->vt = 19;
  a3->lVal = 0x8000;
  return result;
}

```

## disassembly

```asm
0x18001fbd0  push    rbx
0x18001fbd2  push    rbp
0x18001fbd3  push    rsi
0x18001fbd4  push    rdi
0x18001fbd5  sub     rsp, 38h
0x18001fbd9  mov     rdi, rcx
0x18001fbdc  mov     rbp, r9
0x18001fbdf  lea     rcx, pszStr1; "THIS.CLSID"
0x18001fbe6  mov     rbx, r8
0x18001fbe9  mov     rsi, rdx
0x18001fbec  call    cs:__imp_StrCmpICW
0x18001fbf2  test    eax, eax
0x18001fbf4  jnz     short loc_18001FC08
0x18001fbf6  lea     rcx, [rdi+20h]; pv
0x18001fbfa  mov     r8, rbx; pvar
0x18001fbfd  lea     edx, [rax+10h]; cb
0x18001fc00  call    cs:__imp_InitVariantFromBuffer
0x18001fc06  jmp     short loc_18001FC60
0x18001fc08  mov     rax, [rdi+30h]
0x18001fc0c  sub     rax, qword ptr cs:CLSID_FolderShortcut.Data1
0x18001fc13  jnz     short loc_18001FC20
0x18001fc15  mov     rax, [rdi+38h]
0x18001fc19  sub     rax, qword ptr cs:CLSID_FolderShortcut.Data4
0x18001fc20  test    rax, rax
0x18001fc23  jnz     short loc_18001FC47
0x18001fc25  mov     rdx, rsi; pszStr2
0x18001fc28  lea     rcx, aShelllinkdataf; "ShellLinkDataFlags"
0x18001fc2f  call    cs:__imp_StrCmpICW
0x18001fc35  test    eax, eax
0x18001fc37  jnz     short loc_18001FC47
0x18001fc39  mov     word ptr [rbx], 13h
0x18001fc3e  mov     dword ptr [rbx+8], 8000h
0x18001fc45  jmp     short loc_18001FC60
0x18001fc47  mov     rcx, [rdi+40h]
0x18001fc4b  mov     r9, rbp
0x18001fc4e  mov     r8, rbx
0x18001fc51  mov     rdx, rsi
0x18001fc54  mov     rax, [rcx]
0x18001fc57  mov     rax, [rax+18h]
0x18001fc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc60  add     rsp, 38h
0x18001fc64  pop     rdi
0x18001fc65  pop     rsi
0x18001fc66  pop     rbp
0x18001fc67  pop     rbx
0x18001fc68  retn
```
