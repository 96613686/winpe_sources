# Autoplay::CThreadTaskCreateAndCallEventHandler::_DoStuff(void)

- ea: `0x180005b30`
- end: `0x180005ded`
- name: `?_DoStuff@CThreadTaskCreateAndCallEventHandler@Autoplay@@MEAAJXZ`
- size: `701`
- prototype: `__int64 __fastcall(Autoplay::CThreadTaskCreateAndCallEventHandler *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005b30`
- `0x180005df4`
- `0x180018a74`
- `0x180028a28`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005b70`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005bf7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005b70`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180005bf7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005d87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005d87`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005b9a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005b9a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005bd5`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005bd5`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180005c6c`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180005c6c`

## string_xrefs

- `0x180005c3e`: `Session:%d!clsid:%s`
- `0x180005c28`: `Session:Console!clsid:%s`

## pseudocode

```c
__int64 __fastcall Autoplay::CThreadTaskCreateAndCallEventHandler::_DoStuff(
        Autoplay::CThreadTaskCreateAndCallEventHandler *this)
{
  __int64 v2; // rcx
  int v3; // ecx
  HRESULT Object; // ebx
  int v5; // r8d
  unsigned int v6; // r14d
  LPBC v7; // rcx
  int v8; // eax
  IBindCtx *v9; // rbx
  IBindCtx *v11; // [rsp+38h] [rbp-D0h] BYREF
  void *ppv; // [rsp+40h] [rbp-C8h] BYREF
  LPBC ppbc; // [rsp+48h] [rbp-C0h] BYREF
  OLECHAR v14; // [rsp+58h] [rbp-B0h] BYREF
  _WORD v15[39]; // [rsp+5Ah] [rbp-AEh] BYREF
  OLECHAR sz[40]; // [rsp+A8h] [rbp-60h] BYREF
  WCHAR pszName[128]; // [rsp+F8h] [rbp-10h] BYREF

  StringFromGUID2((const GUID *const)((char *)this + 1244), sz, 39);
  if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
    McTemplateU0zz_EtwEventWriteTransfer(v2, ShellTraceId_HDSrv_NonVolume_NotifyShell_Start, sz, (char *)this + 40);
  Object = CoInitializeEx(0, 4u);
  if ( Object >= 0 )
  {
    v6 = *((_DWORD *)this + 310);
    v11 = 0;
    ppbc = 0;
    Object = CreateBindCtx(0, &ppbc);
    if ( Object >= 0 )
    {
      if ( StringFromGUID2((const GUID *const)this + 76, &v14, 39) )
      {
        v15[36] = 0;
        if ( v6 )
          v8 = StringCchPrintfW(pszName, 0x80u, L"Session:%d!clsid:%s", v6, v15);
        else
          v8 = StringCchPrintfW(pszName, 0x80u, L"Session:Console!clsid:%s", v15);
        Object = v8;
        if ( v8 >= 0 )
        {
          ppv = 0;
          Object = CoGetObject(pszName, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
          if ( Object >= 0 )
          {
            Object = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, IBindCtx **))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       0,
                       &GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1,
                       &v11);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
        if ( Object < 0 )
          goto LABEL_22;
        Object = ((__int64 (__fastcall *)(IBindCtx *, _QWORD))v11->lpVtbl->RegisterObjectBound)(
                   v11,
                   *((_QWORD *)this + 154));
        if ( Object >= 0 )
        {
          ppbc = 0;
          if ( ((__int64 (__fastcall *)(IBindCtx *, GUID *, LPBC *))v11->lpVtbl->QueryInterface)(
                 v11,
                 &GUID_ed7cc9ee_2c17_4912_8fa0_e3ce911e225d,
                 &ppbc) >= 0 )
            ((void (__fastcall *)(LPBC, char *))ppbc->lpVtbl->SetBindOptions)(ppbc, (char *)this + 1244);
          if ( ppbc )
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          v9 = v11;
          ((void (__fastcall *)(IBindCtx *))v11->lpVtbl->AddRef)(v11);
          *((_QWORD *)this + 70) = v9;
          Object = ((__int64 (__fastcall *)(IBindCtx *, char *, char *, char *))v9->lpVtbl->RevokeObjectBound)(
                     v9,
                     (char *)this + 40,
                     (char *)this + 568,
                     (char *)this + 1088);
        }
        v7 = v11;
      }
      else
      {
        v7 = ppbc;
        Object = -2147024774;
      }
      ((void (__fastcall *)(LPBC))v7->lpVtbl->Release)(v7);
    }
LABEL_22:
    CoUninitialize();
  }
  if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v3,
      (unsigned int)ShellTraceId_HDSrv_NonVolume_NotifyShell_Stop,
      v5,
      1,
      (__int64)&ppbc);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180005b30  mov     r11, rsp
0x180005b33  push    rbp
0x180005b34  push    rbx
0x180005b35  lea     rbp, [r11-118h]
0x180005b3c  sub     rsp, 208h
0x180005b43  mov     rax, cs:__security_cookie
0x180005b4a  xor     rax, rsp
0x180005b4d  mov     [rbp+110h+var_20], rax
0x180005b54  mov     [r11+10h], rsi
0x180005b58  lea     rdx, [rbp+110h+sz]; lpsz
0x180005b5c  mov     [r11+18h], rdi
0x180005b60  mov     r8d, 27h ; '''; cchMax
0x180005b66  mov     rdi, rcx
0x180005b69  add     rcx, 4DCh; rguid
0x180005b70  call    cs:__imp_StringFromGUID2
0x180005b76  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x180005b7d  jz      short loc_180005B93
0x180005b7f  lea     r9, [rdi+28h]
0x180005b83  lea     r8, [rbp+110h+sz]
0x180005b87  lea     rdx, ShellTraceId_HDSrv_NonVolume_NotifyShell_Start
0x180005b8e  call    McTemplateU0zz_EtwEventWriteTransfer
0x180005b93  mov     edx, 4; dwCoInit
0x180005b98  xor     ecx, ecx; pvReserved
0x180005b9a  call    cs:__imp_CoInitializeEx
0x180005ba0  mov     ebx, eax
0x180005ba2  test    eax, eax
0x180005ba4  js      loc_180005D9D
0x180005baa  mov     [rsp+210h+arg_18], r14
0x180005bb2  lea     rdx, [rsp+210h+ppbc]; ppbc
0x180005bb7  mov     r14d, [rdi+4D8h]
0x180005bbe  xor     ecx, ecx; reserved
0x180005bc0  mov     [rsp+200h], r15
0x180005bc8  xor     r15d, r15d
0x180005bcb  mov     [rsp+210h+var_1E0], r15
0x180005bd0  mov     [rsp+210h+ppbc], r15
0x180005bd5  call    cs:__imp_CreateBindCtx
0x180005bdb  mov     ebx, eax
0x180005bdd  test    eax, eax
0x180005bdf  js      loc_180005D87
0x180005be5  lea     rcx, [rdi+4C0h]; rguid
0x180005bec  mov     r8d, 27h ; '''; cchMax
0x180005bf2  lea     rdx, [rsp+210h+var_1C0]; lpsz
0x180005bf7  call    cs:__imp_StringFromGUID2
0x180005bfd  test    eax, eax
0x180005bff  jnz     short loc_180005C10
0x180005c01  mov     rcx, [rsp+210h+ppbc]
0x180005c06  mov     ebx, 8007007Ah
0x180005c0b  jmp     loc_180005D7B
0x180005c10  mov     [rbp+110h+var_176], r15w
0x180005c15  mov     edx, 80h; unsigned __int64
0x180005c1a  lea     rcx, [rbp+110h+pszName]; unsigned __int16 *
0x180005c1e  test    r14d, r14d
0x180005c21  jnz     short loc_180005C36
0x180005c23  lea     r9, [rsp+52h]
0x180005c28  lea     r8, aSessionConsole; "Session:Console!clsid:%s"
0x180005c2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c34  jmp     short loc_180005C4F
0x180005c36  lea     rax, [rsp+52h]
0x180005c3b  mov     r9d, r14d
0x180005c3e  lea     r8, aSessionDClsidS; "Session:%d!clsid:%s"
0x180005c45  mov     [rsp+20h], rax
0x180005c4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c4f  mov     ebx, eax
0x180005c51  test    eax, eax
0x180005c53  js      short loc_180005CAA
0x180005c55  lea     r9, [rsp+210h+ppv]; ppv
0x180005c5a  mov     [rsp+210h+ppv], r15
0x180005c5f  lea     r8, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180005c66  xor     edx, edx; pBindOptions
0x180005c68  lea     rcx, [rbp+110h+pszName]; pszName
0x180005c6c  call    cs:__imp_CoGetObject
0x180005c72  mov     ebx, eax
0x180005c74  test    eax, eax
0x180005c76  js      short loc_180005CAA
0x180005c78  mov     rcx, [rsp+210h+ppv]
0x180005c7d  lea     r9, [rsp+210h+var_1E0]
0x180005c82  lea     r8, _GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1
0x180005c89  xor     edx, edx
0x180005c8b  mov     rax, [rcx]
0x180005c8e  mov     rax, [rax+18h]
0x180005c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c97  mov     rcx, [rsp+210h+ppv]
0x180005c9c  mov     ebx, eax
0x180005c9e  mov     rax, [rcx]
0x180005ca1  mov     rax, [rax+10h]
0x180005ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005caa  mov     rcx, [rsp+210h+ppbc]
0x180005caf  mov     rax, [rcx]
0x180005cb2  mov     rax, [rax+10h]
0x180005cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cbb  test    ebx, ebx
0x180005cbd  js      loc_180005D87
0x180005cc3  mov     rcx, [rsp+210h+var_1E0]
0x180005cc8  mov     rdx, [rdi+4D0h]
0x180005ccf  mov     rax, [rcx]
0x180005cd2  mov     rax, [rax+18h]
0x180005cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cdb  mov     ebx, eax
0x180005cdd  test    eax, eax
0x180005cdf  js      loc_180005D76
0x180005ce5  mov     rcx, [rsp+210h+var_1E0]
0x180005cea  lea     r8, [rsp+210h+ppbc]
0x180005cef  mov     [rsp+210h+ppbc], r15
0x180005cf4  lea     rdx, _GUID_ed7cc9ee_2c17_4912_8fa0_e3ce911e225d
0x180005cfb  mov     rax, [rcx]
0x180005cfe  mov     rax, [rax]
0x180005d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d06  test    eax, eax
0x180005d08  js      short loc_180005D22
0x180005d0a  mov     rcx, [rsp+210h+ppbc]
0x180005d0f  lea     rdx, [rdi+4DCh]
0x180005d16  mov     rax, [rcx]
0x180005d19  mov     rax, [rax+30h]
0x180005d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d22  mov     rcx, [rsp+210h+ppbc]
0x180005d27  test    rcx, rcx
0x180005d2a  jz      short loc_180005D38
0x180005d2c  mov     rax, [rcx]
0x180005d2f  mov     rax, [rax+10h]
0x180005d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d38  mov     rbx, [rsp+210h+var_1E0]
0x180005d3d  mov     rcx, rbx
0x180005d40  mov     rax, [rbx]
0x180005d43  mov     rax, [rax+8]
0x180005d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4c  mov     [rdi+230h], rbx
0x180005d53  lea     r9, [rdi+440h]
0x180005d5a  mov     rax, [rbx]
0x180005d5d  lea     r8, [rdi+238h]
0x180005d64  lea     rdx, [rdi+28h]
0x180005d68  mov     rcx, rbx
0x180005d6b  mov     rax, [rax+20h]
0x180005d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d74  mov     ebx, eax
0x180005d76  mov     rcx, [rsp+210h+var_1E0]
0x180005d7b  mov     rax, [rcx]
0x180005d7e  mov     rax, [rax+10h]
0x180005d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d87  call    cs:__imp_CoUninitialize
0x180005d8d  mov     r15, [rsp+200h]
0x180005d95  mov     r14, [rsp+210h+arg_18]
0x180005d9d  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x180005da4  mov     rdi, [rsp+210h+arg_10]
0x180005dac  mov     rsi, [rsp+210h+arg_8]
0x180005db4  jz      short loc_180005DD2
0x180005db6  lea     rax, [rsp+210h+ppbc]
0x180005dbb  mov     r9d, 1
0x180005dc1  lea     rdx, ShellTraceId_HDSrv_NonVolume_NotifyShell_Stop
0x180005dc8  mov     [rsp+20h], rax
0x180005dcd  call    McGenEventWrite_EtwEventWriteTransfer
0x180005dd2  mov     eax, ebx
0x180005dd4  mov     rcx, [rbp+110h+var_20]
0x180005ddb  xor     rcx, rsp; StackCookie
0x180005dde  call    __security_check_cookie
0x180005de3  add     rsp, 208h
0x180005dea  pop     rbx
0x180005deb  pop     rbp
0x180005dec  retn
```
