# CArchiveItemContextMenu::_OpenExploreTempFile(HWND__ *,ushort const *,ushort const *)

- ea: `0x1800278b0`
- end: `0x180027a37`
- name: `?_OpenExploreTempFile@CArchiveItemContextMenu@@AEAAJPEAUHWND__@@PEBG1@Z`
- size: `391`
- prototype: `__int64 __fastcall(CArchiveItemContextMenu *this, HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ea30`

## callees

- `0x1800278b0`
- `0x180027a40`
- `0x180027bf0`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x1800278f2`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800278f2`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x1800279e4`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenu` at `0x1800279e4`

## string_xrefs

- `0x18002793b`: `ReadWriteTempFile`

## pseudocode

```c
__int64 __fastcall CArchiveItemContextMenu::_OpenExploreTempFile(
        CArchiveItemContextMenu *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HRESULT v8; // ebx
  CTempFileNameArray *v9; // rcx
  int v10; // ebx
  void *ppv; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h] BYREF
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-20h] BYREF

  ppv = 0;
  v8 = SHCreateItemFromParsingName(a4, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v8 >= 0 )
  {
    v13 = 0;
    if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           &BHID_AssociationArray,
           &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f,
           &v13) < 0
      || (v10 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 48LL))(
                  v13,
                  17760256,
                  L"ReadWriteTempFile"),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13),
          v10 < 0) )
    {
      CTempFileNameArray::ReferenceTempFile(v9, a3, a4);
    }
    v15 = 0;
    v8 = BindCtx_RegisterUIWindow(v9, a2, &v15);
    if ( v8 >= 0 )
    {
      v14 = 0;
      v8 = (*(__int64 (__fastcall **)(void *, __int64, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             v15,
             &BHID_SFUIObject,
             &GUID_000214e4_0000_0000_c000_000000000046,
             &v14);
      if ( v8 >= 0 )
      {
        v8 = SHInvokeCommandOnContextMenu(a2, *((_QWORD *)this + 1), v14, 0x4000000);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800278b0  push    rbp
0x1800278b2  push    rbx
0x1800278b3  push    rsi
0x1800278b4  push    rdi
0x1800278b5  push    r14
0x1800278b7  push    r15
0x1800278b9  mov     rbp, rsp
0x1800278bc  sub     rsp, 68h
0x1800278c0  mov     rax, cs:__security_cookie
0x1800278c7  xor     rax, rsp
0x1800278ca  mov     [rbp+var_18], rax
0x1800278ce  mov     rsi, r9
0x1800278d1  mov     [rbp+ppv], 0
0x1800278d9  mov     r14, r8
0x1800278dc  lea     r9, [rbp+ppv]; ppv
0x1800278e0  mov     rdi, rdx
0x1800278e3  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800278ea  mov     r15, rcx
0x1800278ed  xor     edx, edx; pbc
0x1800278ef  mov     rcx, rsi; pszPath
0x1800278f2  call    cs:__imp_SHCreateItemFromParsingName
0x1800278f8  mov     ebx, eax
0x1800278fa  test    eax, eax
0x1800278fc  js      loc_180027A1C
0x180027902  mov     rcx, [rbp+ppv]
0x180027906  lea     rdx, [rbp+var_30]
0x18002790a  mov     [rbp+var_30], 0
0x180027912  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x180027919  mov     [rsp+68h+var_48], rdx
0x18002791e  lea     r8, BHID_AssociationArray
0x180027925  xor     edx, edx
0x180027927  mov     rax, [rcx]
0x18002792a  mov     rax, [rax+18h]
0x18002792e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027933  test    eax, eax
0x180027935  js      short loc_18002796C
0x180027937  mov     rcx, [rbp+var_30]
0x18002793b  lea     r8, aReadwritetempf; "ReadWriteTempFile"
0x180027942  mov     edx, 10F0000h
0x180027947  mov     rax, [rcx]
0x18002794a  mov     rax, [rax+30h]
0x18002794e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027953  mov     rdx, [rbp+var_30]
0x180027957  mov     ebx, eax
0x180027959  mov     rcx, [rdx]
0x18002795c  mov     rax, [rcx+10h]
0x180027960  mov     rcx, rdx
0x180027963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027968  test    ebx, ebx
0x18002796a  jns     short loc_180027977
0x18002796c  mov     r8, rsi; unsigned __int16 *
0x18002796f  mov     rdx, r14; unsigned __int16 *
0x180027972  call    ?ReferenceTempFile@CTempFileNameArray@@QEAAXPEBG0@Z; CTempFileNameArray::ReferenceTempFile(ushort const *,ushort const *)
0x180027977  lea     r8, [rbp+var_20]
0x18002797b  mov     [rbp+var_20], 0
0x180027983  mov     rdx, rdi
0x180027986  call    BindCtx_RegisterUIWindow
0x18002798b  mov     ebx, eax
0x18002798d  test    eax, eax
0x18002798f  js      short loc_180027A0C
0x180027991  mov     rcx, [rbp+ppv]
0x180027995  lea     rdx, [rbp+var_28]
0x180027999  mov     [rbp+var_28], 0
0x1800279a1  lea     r9, _GUID_000214e4_0000_0000_c000_000000000046
0x1800279a8  mov     [rsp+68h+var_48], rdx
0x1800279ad  lea     r8, BHID_SFUIObject
0x1800279b4  mov     rdx, [rbp+var_20]
0x1800279b8  mov     rax, [rcx]
0x1800279bb  mov     rax, [rax+18h]
0x1800279bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279c4  mov     ebx, eax
0x1800279c6  test    eax, eax
0x1800279c8  js      short loc_1800279FC
0x1800279ca  mov     r8, [rbp+var_28]
0x1800279ce  mov     r9d, 4000000h
0x1800279d4  mov     rdx, [r15+8]
0x1800279d8  mov     rcx, rdi
0x1800279db  mov     [rsp+68h+var_48], 0
0x1800279e4  call    cs:__imp_SHInvokeCommandOnContextMenu
0x1800279ea  mov     rcx, [rbp+var_28]
0x1800279ee  mov     ebx, eax
0x1800279f0  mov     rax, [rcx]
0x1800279f3  mov     rax, [rax+10h]
0x1800279f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279fc  mov     rcx, [rbp+var_20]
0x180027a00  mov     rax, [rcx]
0x180027a03  mov     rax, [rax+10h]
0x180027a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a0c  mov     rcx, [rbp+ppv]
0x180027a10  mov     rax, [rcx]
0x180027a13  mov     rax, [rax+10h]
0x180027a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a1c  mov     eax, ebx
0x180027a1e  mov     rcx, [rbp+var_18]
0x180027a22  xor     rcx, rsp; StackCookie
0x180027a25  call    __security_check_cookie
0x180027a2a  add     rsp, 68h
0x180027a2e  pop     r15
0x180027a30  pop     r14
0x180027a32  pop     rdi
0x180027a33  pop     rsi
0x180027a34  pop     rbx
0x180027a35  pop     rbp
0x180027a36  retn
```
