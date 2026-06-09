# _GiveAllowForegroundToShell(ulong)

- ea: `0x1800059a0`
- end: `0x180005b1f`
- name: `?_GiveAllowForegroundToShell@@YAJK@Z`
- size: `383`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800056c8`
- `0x1800297a0`
- `0x1800298d8`

## callees

- `0x1800059a0`
- `0x180005df4`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800059fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800059fb`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800059d9`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800059d9`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180005a81`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180005a81`

## string_xrefs

- `0x180005a4f`: `Session:%d!clsid:%s`
- `0x180005a39`: `Session:Console!clsid:%s`

## pseudocode

```c
__int64 __fastcall _GiveAllowForegroundToShell(unsigned int a1)
{
  HRESULT Object; // ebx
  void (*Release)(void); // rax
  int v4; // eax
  void *ppv; // [rsp+30h] [rbp-188h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-180h] BYREF
  __int64 v8; // [rsp+40h] [rbp-178h] BYREF
  OLECHAR sz; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v10[72]; // [rsp+52h] [rbp-166h] BYREF
  __int16 v11; // [rsp+9Ah] [rbp-11Eh]
  WCHAR pszName[128]; // [rsp+A0h] [rbp-118h] BYREF

  v8 = 0;
  ppbc = 0;
  Object = CreateBindCtx(0, &ppbc);
  if ( Object >= 0 )
  {
    if ( !StringFromGUID2(&CLSID_SetShellForeground, &sz, 39) )
    {
      Object = -2147024774;
      Release = (void (*)(void))ppbc->lpVtbl->Release;
LABEL_12:
      Release();
      return (unsigned int)Object;
    }
    v11 = 0;
    if ( a1 )
      v4 = StringCchPrintfW(pszName, 0x80u, L"Session:%d!clsid:%s", a1, v10);
    else
      v4 = StringCchPrintfW(pszName, 0x80u, L"Session:Console!clsid:%s", v10);
    Object = v4;
    if ( v4 >= 0 )
    {
      ppv = 0;
      Object = CoGetObject(pszName, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
      if ( Object >= 0 )
      {
        Object = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   0,
                   &GUID_bf0d821f_486c_49c4_8a3d_86e990047d65,
                   &v8);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( Object >= 0 )
    {
      Object = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
      Release = *(void (**)(void))(*(_QWORD *)v8 + 16LL);
      goto LABEL_12;
    }
  }
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x1800059a0  mov     [rsp+arg_8], rbx
0x1800059a5  mov     [rsp+arg_10], rsi
0x1800059aa  push    rdi
0x1800059ab  sub     rsp, 1B0h
0x1800059b2  mov     rax, cs:__security_cookie
0x1800059b9  xor     rax, rsp
0x1800059bc  mov     [rsp+1B8h+var_18], rax
0x1800059c4  mov     edi, ecx
0x1800059c6  lea     rdx, [rsp+1B8h+ppbc]; ppbc
0x1800059cb  xor     esi, esi
0x1800059cd  xor     ecx, ecx; reserved
0x1800059cf  mov     [rsp+1B8h+var_178], rsi
0x1800059d4  mov     [rsp+1B8h+ppbc], rsi
0x1800059d9  call    cs:__imp_CreateBindCtx
0x1800059df  mov     ebx, eax
0x1800059e1  test    eax, eax
0x1800059e3  js      loc_180005AF8
0x1800059e9  mov     r8d, 27h ; '''; cchMax
0x1800059ef  lea     rdx, [rsp+1B8h+sz]; lpsz
0x1800059f4  lea     rcx, CLSID_SetShellForeground; rguid
0x1800059fb  call    cs:__imp_StringFromGUID2
0x180005a01  test    eax, eax
0x180005a03  jnz     short loc_180005A1B
0x180005a05  mov     rcx, [rsp+1B8h+ppbc]
0x180005a0a  mov     ebx, 8007007Ah
0x180005a0f  mov     rax, [rcx]
0x180005a12  mov     rax, [rax+10h]
0x180005a16  jmp     loc_180005AF3
0x180005a1b  mov     [rsp+1B8h+var_11E], si
0x180005a23  mov     edx, 80h; unsigned __int64
0x180005a28  lea     rcx, [rsp+1B8h+pszName]; unsigned __int16 *
0x180005a30  test    edi, edi
0x180005a32  jnz     short loc_180005A47
0x180005a34  lea     r9, [rsp+1B8h+var_166]
0x180005a39  lea     r8, aSessionConsole; "Session:Console!clsid:%s"
0x180005a40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a45  jmp     short loc_180005A60
0x180005a47  lea     rax, [rsp+1B8h+var_166]
0x180005a4c  mov     r9d, edi
0x180005a4f  lea     r8, aSessionDClsidS; "Session:%d!clsid:%s"
0x180005a56  mov     [rsp+1B8h+var_198], rax
0x180005a5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a60  mov     ebx, eax
0x180005a62  test    eax, eax
0x180005a64  js      short loc_180005ABF
0x180005a66  lea     r9, [rsp+1B8h+ppv]; ppv
0x180005a6b  mov     [rsp+1B8h+ppv], rsi
0x180005a70  lea     r8, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180005a77  xor     edx, edx; pBindOptions
0x180005a79  lea     rcx, [rsp+1B8h+pszName]; pszName
0x180005a81  call    cs:__imp_CoGetObject
0x180005a87  mov     ebx, eax
0x180005a89  test    eax, eax
0x180005a8b  js      short loc_180005ABF
0x180005a8d  mov     rcx, [rsp+1B8h+ppv]
0x180005a92  lea     r9, [rsp+1B8h+var_178]
0x180005a97  lea     r8, _GUID_bf0d821f_486c_49c4_8a3d_86e990047d65
0x180005a9e  xor     edx, edx
0x180005aa0  mov     rax, [rcx]
0x180005aa3  mov     rax, [rax+18h]
0x180005aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aac  mov     rcx, [rsp+1B8h+ppv]
0x180005ab1  mov     ebx, eax
0x180005ab3  mov     rax, [rcx]
0x180005ab6  mov     rax, [rax+10h]
0x180005aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abf  mov     rcx, [rsp+1B8h+ppbc]
0x180005ac4  mov     rax, [rcx]
0x180005ac7  mov     rax, [rax+10h]
0x180005acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad0  test    ebx, ebx
0x180005ad2  js      short loc_180005AF8
0x180005ad4  mov     rcx, [rsp+1B8h+var_178]
0x180005ad9  mov     rax, [rcx]
0x180005adc  mov     rax, [rax+18h]
0x180005ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae5  mov     rcx, [rsp+1B8h+var_178]
0x180005aea  mov     ebx, eax
0x180005aec  mov     rdx, [rcx]
0x180005aef  mov     rax, [rdx+10h]
0x180005af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af8  mov     eax, ebx
0x180005afa  mov     rcx, [rsp+1B8h+var_18]
0x180005b02  xor     rcx, rsp; StackCookie
0x180005b05  call    __security_check_cookie
0x180005b0a  lea     r11, [rsp+1B8h+var_8]
0x180005b12  mov     rbx, [r11+18h]
0x180005b16  mov     rsi, [r11+20h]
0x180005b1a  mov     rsp, r11
0x180005b1d  pop     rdi
0x180005b1e  retn
```
