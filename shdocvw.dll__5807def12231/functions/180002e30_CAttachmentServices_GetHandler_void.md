# CAttachmentServices::_GetHandler(void)

- ea: `0x180002e30`
- end: `0x180003019`
- name: `?_GetHandler@CAttachmentServices@@AEAAHXZ`
- size: `489`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010e3c`

## callees

- `0x180002e30`
- `0x180003020`
- `0x180003c10`
- `0x180008320`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_PathIsExe` at `0x180002e8a`
- `SHELL32!__imp_PathIsExe` at `0x180002e8a`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180002eba`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180002eba`
- `SHLWAPI!PathFindExtensionW` at `0x180002e81`
- `SHLWAPI!PathFindExtensionW` at `0x180002ef4`
- `SHLWAPI!PathFindExtensionW` at `0x180002e81`
- `SHLWAPI!PathFindExtensionW` at `0x180002ef4`
- `SHLWAPI!PathFindFileNameW` at `0x180002e72`
- `SHLWAPI!PathFindFileNameW` at `0x180002ee5`
- `SHLWAPI!PathFindFileNameW` at `0x180002e72`
- `SHLWAPI!PathFindFileNameW` at `0x180002ee5`

## pseudocode

```c
_BOOL8 __fastcall CAttachmentServices::_GetHandler(CAttachmentServices *this)
{
  _QWORD *v1; // rbx
  const WCHAR *v3; // rcx
  const WCHAR *v4; // rax
  const WCHAR *ExtensionW; // rax
  int (__fastcall *v6)(void *, __int64, LPWSTR, _QWORD, _QWORD); // rbp
  const WCHAR *v7; // rcx
  const WCHAR *FileNameW; // rax
  LPWSTR v9; // rax
  int v10; // eax
  void *ppv; // [rsp+40h] [rbp-248h] BYREF
  int v13; // [rsp+48h] [rbp-240h] BYREF
  WCHAR psz[264]; // [rsp+50h] [rbp-238h] BYREF

  v1 = (_QWORD *)((char *)this + 104);
  if ( !*((_QWORD *)this + 13) )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 5);
    v4 = v3 ? PathFindFileNameW(v3) : (const WCHAR *)*((_QWORD *)this + 4);
    ExtensionW = PathFindExtensionW(v4);
    if ( !PathIsExe(ExtensionW) )
    {
      ppv = 0;
      if ( SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv) >= 0 )
      {
        v6 = *(int (__fastcall **)(void *, __int64, LPWSTR, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL);
        v7 = (const WCHAR *)*((_QWORD *)this + 5);
        if ( v7 )
          FileNameW = PathFindFileNameW(v7);
        else
          FileNameW = (const WCHAR *)*((_QWORD *)this + 4);
        v9 = PathFindExtensionW(FileNameW);
        if ( v6(ppv, 4, v9, 0, 0) < 0 )
          goto LABEL_16;
        v13 = 260;
        v10 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, _QWORD, WCHAR *, int *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                0,
                2,
                0,
                psz,
                &v13);
        if ( v10 == -2147023741 )
          v10 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, _QWORD, WCHAR *, int *))(*(_QWORD *)ppv + 32LL))(
                  ppv,
                  0,
                  21,
                  0,
                  psz,
                  &v13);
        if ( v10 < 0
          || (Str_SetPtrW((LPWSTR *)this + 12, psz), !*((_QWORD *)this + 12))
          || (*(int (__fastcall **)(void *, _QWORD, __int64, _QWORD, _QWORD *))(*(_QWORD *)ppv + 40LL))(
               ppv,
               0,
               1,
               0,
               v1) < 0 )
        {
LABEL_16:
          CAttachmentServices::_FreeHandler(this);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  return *v1 != 0;
}

```

## disassembly

```asm
0x180002e30  push    rbx
0x180002e32  push    rsi
0x180002e33  push    r14
0x180002e35  sub     rsp, 270h
0x180002e3c  mov     rax, cs:__security_cookie
0x180002e43  xor     rax, rsp
0x180002e46  mov     [rsp+288h+var_28], rax
0x180002e4e  lea     rbx, [rcx+68h]
0x180002e52  xor     r14d, r14d
0x180002e55  mov     rsi, rcx
0x180002e58  cmp     [rbx], r14
0x180002e5b  jnz     loc_180002FF4
0x180002e61  mov     rcx, [rcx+28h]; pszPath
0x180002e65  mov     [rsp+288h+arg_10], rdi
0x180002e6d  test    rcx, rcx
0x180002e70  jz      short loc_180002E7A
0x180002e72  call    cs:__imp_PathFindFileNameW
0x180002e78  jmp     short loc_180002E7E
0x180002e7a  mov     rax, [rsi+20h]
0x180002e7e  mov     rcx, rax; pszPath
0x180002e81  call    cs:__imp_PathFindExtensionW
0x180002e87  mov     rcx, rax; pszPath
0x180002e8a  call    cs:__imp_PathIsExe
0x180002e90  test    eax, eax
0x180002e92  jnz     loc_180002FEC
0x180002e98  lea     rax, [rsp+288h+var_248]
0x180002e9d  mov     [rsp+288h+var_248], r14
0x180002ea2  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x180002ea9  mov     [rsp+288h+ppv], rax; ppv
0x180002eae  xor     r8d, r8d; pUnkOuter
0x180002eb1  lea     rdx, CLSID_QueryAssociations; pclsid
0x180002eb8  xor     ecx, ecx; pszCLSID
0x180002eba  call    cs:__imp_SHCoCreateInstance
0x180002ec0  test    eax, eax
0x180002ec2  js      loc_180002FEC
0x180002ec8  mov     rax, [rsp+288h+var_248]
0x180002ecd  mov     [rsp+288h+arg_8], rbp
0x180002ed5  mov     rcx, [rax]
0x180002ed8  mov     rbp, [rcx+18h]
0x180002edc  mov     rcx, [rsi+28h]; pszPath
0x180002ee0  test    rcx, rcx
0x180002ee3  jz      short loc_180002EED
0x180002ee5  call    cs:__imp_PathFindFileNameW
0x180002eeb  jmp     short loc_180002EF1
0x180002eed  mov     rax, [rsi+20h]
0x180002ef1  mov     rcx, rax; pszPath
0x180002ef4  call    cs:__imp_PathFindExtensionW
0x180002efa  mov     rcx, [rsp+288h+var_248]
0x180002eff  xor     r9d, r9d
0x180002f02  mov     r8, rax
0x180002f05  mov     [rsp+288h+ppv], r14
0x180002f0a  mov     rax, rbp
0x180002f0d  mov     edx, 4
0x180002f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f17  mov     rbp, [rsp+288h+arg_8]
0x180002f1f  test    eax, eax
0x180002f21  js      loc_180002FD3
0x180002f27  mov     rcx, [rsp+288h+var_248]
0x180002f2c  lea     rdx, [rsp+288h+var_240]
0x180002f31  mov     [rsp+288h+var_260], rdx
0x180002f36  xor     r9d, r9d
0x180002f39  lea     rdx, [rsp+288h+psz]
0x180002f3e  mov     [rsp+288h+var_240], 104h
0x180002f46  mov     [rsp+288h+ppv], rdx
0x180002f4b  mov     r8d, 2
0x180002f51  mov     rax, [rcx]
0x180002f54  xor     edx, edx
0x180002f56  mov     rax, [rax+20h]
0x180002f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5f  cmp     eax, 80070483h
0x180002f64  jnz     short loc_180002F96
0x180002f66  mov     rcx, [rsp+288h+var_248]
0x180002f6b  lea     rdx, [rsp+288h+var_240]
0x180002f70  mov     [rsp+288h+var_260], rdx
0x180002f75  xor     r9d, r9d
0x180002f78  lea     rdx, [rsp+288h+psz]
0x180002f7d  mov     r8d, 15h
0x180002f83  mov     [rsp+288h+ppv], rdx
0x180002f88  xor     edx, edx
0x180002f8a  mov     rax, [rcx]
0x180002f8d  mov     rax, [rax+20h]
0x180002f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f96  test    eax, eax
0x180002f98  js      short loc_180002FD3
0x180002f9a  lea     rdx, [rsp+288h+psz]; psz
0x180002f9f  lea     rcx, [rsi+60h]; ppsz
0x180002fa3  call    Str_SetPtrW
0x180002fa8  cmp     [rsi+60h], r14
0x180002fac  jz      short loc_180002FD3
0x180002fae  mov     rcx, [rsp+288h+var_248]
0x180002fb3  xor     r9d, r9d
0x180002fb6  xor     edx, edx
0x180002fb8  mov     [rsp+288h+ppv], rbx
0x180002fbd  mov     r8d, 1
0x180002fc3  mov     rax, [rcx]
0x180002fc6  mov     rax, [rax+28h]
0x180002fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fcf  test    eax, eax
0x180002fd1  jns     short loc_180002FDB
0x180002fd3  mov     rcx, rsi; this
0x180002fd6  call    ?_FreeHandler@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_FreeHandler(void)
0x180002fdb  mov     rcx, [rsp+288h+var_248]
0x180002fe0  mov     rax, [rcx]
0x180002fe3  mov     rax, [rax+10h]
0x180002fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fec  mov     rdi, [rsp+288h+arg_10]
0x180002ff4  mov     eax, r14d
0x180002ff7  cmp     [rbx], rax
0x180002ffa  setnz   al
0x180002ffd  mov     rcx, [rsp+288h+var_28]
0x180003005  xor     rcx, rsp; StackCookie
0x180003008  call    __security_check_cookie
0x18000300d  add     rsp, 270h
0x180003014  pop     r14
0x180003016  pop     rsi
0x180003017  pop     rbx
0x180003018  retn
```
