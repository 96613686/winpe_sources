# CInstClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006de0`
- end: `0x180007021`
- name: `?CreateInstance@CInstClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `577`
- prototype: `__int64 __fastcall(CInstClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006de0`
- `0x180008320`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_SHCLSIDFromString` at `0x180006e74`
- `SHELL32!__imp_SHCLSIDFromString` at `0x180006e74`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180006eb2`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x180006eb2`
- `SHLWAPI!SHGetValueW` at `0x180006e42`
- `SHLWAPI!SHGetValueW` at `0x180006e42`
- `SHLWAPI!SHOpenRegStream2W` at `0x180006f88`
- `SHLWAPI!SHOpenRegStream2W` at `0x180006f88`
- `SHLWAPI!__imp_SHLoadFromPropertyBag` at `0x180006f42`
- `SHLWAPI!__imp_SHLoadFromPropertyBag` at `0x180006f42`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x180006f25`
- `SHLWAPI!__imp_SHCreatePropertyBagOnRegKey` at `0x180006f25`

## string_xrefs

- `0x180006e36`: `CLSID`

## pseudocode

```c
__int64 __fastcall CInstClassFactory::CreateInstance(
        CInstClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HKEY *v4; // rsi
  LSTATUS v8; // eax
  int v9; // ebx
  IStream *v10; // rdi
  __int64 v12; // [rsp+30h] [rbp-59h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-51h] BYREF
  __int64 v14; // [rsp+40h] [rbp-49h] BYREF
  __int64 v15; // [rsp+48h] [rbp-41h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp-39h] BYREF
  WCHAR psz[40]; // [rsp+60h] [rbp-29h] BYREF

  *a4 = 0;
  v4 = (HKEY *)((char *)this + 32);
  pcbData = 80;
  v8 = SHGetValueW(*((HKEY *)this + 4), 0, L"CLSID", 0, psz, &pcbData);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    psz[38] = 0;
    pclsid = 0;
    v9 = SHCLSIDFromString(psz, &pclsid);
    if ( v9 >= 0 )
    {
      v12 = 0;
      *(CLSID *)((char *)this + 56) = pclsid;
      v9 = SHExtCoCreateInstance(&pclsid, 0, 1, 1, a3, &v12);
      if ( v9 >= 0 )
      {
        v14 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
               v12,
               &GUID_c2aa8366_6694_47f9_a15b_324d6a75d4cd,
               &v14) >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        v9 = SHCreatePropertyBagOnRegKey(
               *v4,
               L"InitPropertyBag",
               0,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               (char *)this + 72);
        if ( v9 >= 0 )
        {
          v9 = SHLoadFromPropertyBag(v12, ((unsigned __int64)this + 8) & -(__int64)(this != 0));
          if ( v9 >= 0 )
            goto LABEL_15;
        }
        v15 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v12)(
               v12,
               &GUID_00000109_0000_0000_c000_000000000046,
               &v15) >= 0 )
        {
          v10 = SHOpenRegStream2W(*v4, L"InitStream", 0, 0);
          if ( v10 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v15 + 40LL))(v15, v10);
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
          }
          else
          {
            v9 = -2147467259;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v9 >= 0 )
LABEL_15:
            v9 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v12)(v12, a3, a4);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006de0  mov     [rsp-8+arg_8], rbx
0x180006de5  push    rbp
0x180006de6  push    rsi
0x180006de7  push    rdi
0x180006de8  push    r14
0x180006dea  push    r15
0x180006dec  lea     rbp, [rsp-37h]
0x180006df1  sub     rsp, 0C0h
0x180006df8  mov     rax, cs:__security_cookie
0x180006dff  xor     rax, rsp
0x180006e02  mov     [rbp+57h+var_30], rax
0x180006e06  mov     qword ptr [r9], 0
0x180006e0d  lea     rax, [rbp+57h+var_A8]
0x180006e11  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180006e16  lea     rsi, [rcx+20h]
0x180006e1a  lea     rax, [rbp+57h+psz]
0x180006e1e  mov     [rbp+57h+var_A8], 50h ; 'P'
0x180006e25  mov     r15, r9
0x180006e28  mov     [rsp+0E0h+pvData], rax; pvData
0x180006e2d  mov     r14, r8
0x180006e30  mov     rdi, rcx
0x180006e33  mov     rcx, [rsi]; hkey
0x180006e36  lea     r8, pszValue; "CLSID"
0x180006e3d  xor     r9d, r9d; pdwType
0x180006e40  xor     edx, edx; pszSubKey
0x180006e42  call    cs:__imp_SHGetValueW
0x180006e48  mov     ebx, eax
0x180006e4a  test    eax, eax
0x180006e4c  jle     short loc_180006E57
0x180006e4e  movzx   ebx, ax
0x180006e51  or      ebx, 80070000h
0x180006e57  test    ebx, ebx
0x180006e59  js      loc_180006FFC
0x180006e5f  xor     eax, eax
0x180006e61  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180006e65  xorps   xmm0, xmm0
0x180006e68  mov     [rbp+57h+var_34], ax
0x180006e6c  lea     rcx, [rbp+57h+psz]; psz
0x180006e70  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180006e74  call    cs:__imp_SHCLSIDFromString
0x180006e7a  mov     ebx, eax
0x180006e7c  test    eax, eax
0x180006e7e  js      loc_180006FFC
0x180006e84  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x180006e88  lea     rax, [rbp+57h+var_B0]
0x180006e8c  mov     [rbp+57h+var_B0], 0
0x180006e94  mov     r8d, 1
0x180006e9a  mov     [rsp+0E0h+pcbData], rax
0x180006e9f  mov     r9d, r8d
0x180006ea2  mov     [rsp+0E0h+pvData], r14
0x180006ea7  xor     edx, edx
0x180006ea9  lea     rcx, [rbp+57h+pclsid]
0x180006ead  movdqu  xmmword ptr [rdi+38h], xmm0
0x180006eb2  call    cs:__imp_SHExtCoCreateInstance
0x180006eb8  mov     ebx, eax
0x180006eba  test    eax, eax
0x180006ebc  js      loc_180006FFC
0x180006ec2  mov     rcx, [rbp+57h+var_B0]
0x180006ec6  lea     r8, [rbp+57h+var_A0]
0x180006eca  mov     [rbp+57h+var_A0], 0
0x180006ed2  lea     rdx, _GUID_c2aa8366_6694_47f9_a15b_324d6a75d4cd
0x180006ed9  mov     rax, [rcx]
0x180006edc  mov     rax, [rax]
0x180006edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee4  test    eax, eax
0x180006ee6  js      short loc_180006F08
0x180006ee8  mov     rcx, [rbp+57h+var_A0]
0x180006eec  mov     rax, [rcx]
0x180006eef  mov     rax, [rax+18h]
0x180006ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef8  mov     rcx, [rbp+57h+var_A0]
0x180006efc  mov     rax, [rcx]
0x180006eff  mov     rax, [rax+10h]
0x180006f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f08  mov     rcx, [rsi]
0x180006f0b  lea     rax, [rdi+48h]
0x180006f0f  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x180006f16  mov     [rsp+0E0h+pvData], rax
0x180006f1b  xor     r8d, r8d
0x180006f1e  lea     rdx, aInitpropertyba; "InitPropertyBag"
0x180006f25  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x180006f2b  mov     ebx, eax
0x180006f2d  test    eax, eax
0x180006f2f  js      short loc_180006F52
0x180006f31  mov     rcx, [rbp+57h+var_B0]
0x180006f35  lea     rax, [rdi+8]
0x180006f39  neg     rdi
0x180006f3c  sbb     rdx, rdx
0x180006f3f  and     rdx, rax
0x180006f42  call    cs:__imp_SHLoadFromPropertyBag
0x180006f48  mov     ebx, eax
0x180006f4a  test    eax, eax
0x180006f4c  jns     loc_180006FD5
0x180006f52  mov     rcx, [rbp+57h+var_B0]
0x180006f56  lea     r8, [rbp+57h+var_98]
0x180006f5a  mov     [rbp+57h+var_98], 0
0x180006f62  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180006f69  mov     rax, [rcx]
0x180006f6c  mov     rax, [rax]
0x180006f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f74  test    eax, eax
0x180006f76  js      short loc_180006FEC
0x180006f78  mov     rcx, [rsi]; hkey
0x180006f7b  lea     rdx, pszSubkey; "InitStream"
0x180006f82  xor     r9d, r9d; grfMode
0x180006f85  xor     r8d, r8d; pszValue
0x180006f88  call    cs:__imp_SHOpenRegStream2W
0x180006f8e  mov     rdi, rax
0x180006f91  test    rax, rax
0x180006f94  jz      short loc_180006FBC
0x180006f96  mov     rcx, [rbp+57h+var_98]
0x180006f9a  mov     rdx, [rcx]
0x180006f9d  mov     rax, [rdx+28h]
0x180006fa1  mov     rdx, rdi
0x180006fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa9  mov     rcx, [rdi]
0x180006fac  mov     ebx, eax
0x180006fae  mov     rax, [rcx+10h]
0x180006fb2  mov     rcx, rdi
0x180006fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fba  jmp     short loc_180006FC1
0x180006fbc  mov     ebx, 80004005h
0x180006fc1  mov     rcx, [rbp+57h+var_98]
0x180006fc5  mov     rax, [rcx]
0x180006fc8  mov     rax, [rax+10h]
0x180006fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd1  test    ebx, ebx
0x180006fd3  js      short loc_180006FEC
0x180006fd5  mov     rcx, [rbp+57h+var_B0]
0x180006fd9  mov     r8, r15
0x180006fdc  mov     rdx, r14
0x180006fdf  mov     rax, [rcx]
0x180006fe2  mov     rax, [rax]
0x180006fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fea  mov     ebx, eax
0x180006fec  mov     rcx, [rbp+57h+var_B0]
0x180006ff0  mov     rax, [rcx]
0x180006ff3  mov     rax, [rax+10h]
0x180006ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffc  mov     eax, ebx
0x180006ffe  mov     rcx, [rbp+57h+var_30]
0x180007002  xor     rcx, rsp; StackCookie
0x180007005  call    __security_check_cookie
0x18000700a  mov     rbx, [rsp+0E0h+arg_8]
0x180007012  add     rsp, 0C0h
0x180007019  pop     r15
0x18000701b  pop     r14
0x18000701d  pop     rdi
0x18000701e  pop     rsi
0x18000701f  pop     rbp
0x180007020  retn
```
