# CThemeFile::GetHighContrast(int *)

- ea: `0x180016dd0`
- end: `0x180017015`
- name: `?GetHighContrast@CThemeFile@@UEAAJPEAH@Z`
- size: `581`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007d20`
- `0x18000b78c`
- `0x180016dd0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016f48`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017009`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016f88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016f88`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016e47`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016e47`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::GetHighContrast(CThemeFile *this, int *a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rcx
  HRESULT v8; // r14d
  __int64 v9; // rcx
  int ppv; // [rsp+20h] [rbp-40h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v13; // [rsp+50h] [rbp-10h]
  LPVOID pv; // [rsp+90h] [rbp+30h] BYREF
  LPCWCH lpString1; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  if ( !*((_QWORD *)this + 4) )
    return (unsigned int)-2147467259;
  v4 = (__int64 *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    v5 = *v4;
    v6 = *((_BYTE *)this + 48) == 0;
    v7 = *((_QWORD *)this + 5);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(v5 + 8))(v7);
      v8 = 0;
      goto LABEL_10;
    }
    (*(void (__fastcall **)(__int64))(v5 + 96))(v7);
  }
  pv = 0;
  v8 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &pv);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv + 24LL))(pv, *((_QWORD *)this + 4), 0x400000);
  if ( v8 < 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    return (unsigned int)v8;
  }
  v9 = *((_QWORD *)this + 5);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v4 = (__int64 *)pv;
  *((_QWORD *)this + 5) = pv;
  (*(void (__fastcall **)(__int64 *))(*v4 + 8))(v4);
  *((_BYTE *)this + 48) = 0;
LABEL_10:
  *(_OWORD *)pvar = 0;
  v13 = 0;
  LOWORD(ppv) = 3;
  if ( (*(int (__fastcall **)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, PROPVARIANT *))(*v4 + 40))(
         v4,
         L"VisualStyles",
         L"HighContrast",
         0,
         ppv,
         pvar) >= 0 )
  {
    *a2 = (int)pvar[1];
    PropVariantClear(pvar);
  }
  else
  {
    *a2 = -1;
  }
  (*(void (__fastcall **)(__int64 *))(*v4 + 16))(v4);
  if ( *a2 == -1 )
  {
    lpString1 = 0;
    pv = 0;
    if ( (*(int (__fastcall **)(CThemeFile *, LPCWCH *))(*(_QWORD *)this + 480LL))(this, &lpString1) >= 0
      && CompareStringOrdinal(lpString1, -1, L"DABJDKT", -1, 1) == 2
      && (int)CThemeFile::_getThemeSetting(
                (CThemeFile *)((char *)this - 16),
                L"VisualStyles",
                L"ColorStyle",
                0,
                (unsigned __int16 **)&pv) >= 0 )
    {
      *a2 = HighContrastNumberFromSchemeName((const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    else
    {
      *a2 = 0;
    }
    SysFreeString((BSTR)lpString1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016dd0  mov     [rsp-28h+arg_10], rbx
0x180016dd5  mov     [rsp-28h+arg_18], rsi
0x180016dda  push    rbp
0x180016ddb  push    rdi
0x180016ddc  push    r12
0x180016dde  push    r14
0x180016de0  push    r15
0x180016de2  mov     rbp, rsp
0x180016de5  sub     rsp, 60h
0x180016de9  mov     rsi, rdx
0x180016dec  mov     rdi, rcx
0x180016def  mov     dword ptr [rdx], 0
0x180016df5  cmp     qword ptr [rcx+20h], 0
0x180016dfa  jz      loc_180016F93
0x180016e00  mov     rbx, [rcx+28h]
0x180016e04  test    rbx, rbx
0x180016e07  jz      short loc_180016E22
0x180016e09  mov     rax, [rbx]
0x180016e0c  cmp     byte ptr [rcx+30h], 0
0x180016e10  mov     rcx, rbx
0x180016e13  jz      loc_180016FBE
0x180016e19  mov     rax, [rax+60h]
0x180016e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e22  mov     [rbp+pv], 0
0x180016e2a  lea     rax, [rbp+pv]
0x180016e2e  mov     [rsp+60h+ppv], rax; ppv
0x180016e33  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180016e3a  xor     edx, edx; pUnkOuter
0x180016e3c  lea     r8d, [rdx+1]; dwClsContext
0x180016e40  lea     rcx, CLSID_PrivateProfile; rclsid
0x180016e47  call    cs:__imp_CoCreateInstance
0x180016e4d  mov     r14d, eax
0x180016e50  test    eax, eax
0x180016e52  js      loc_180016F63
0x180016e58  mov     rcx, [rbp+pv]
0x180016e5c  mov     rax, [rcx]
0x180016e5f  mov     r8d, 400000h
0x180016e65  mov     rdx, [rdi+20h]
0x180016e69  mov     rax, [rax+18h]
0x180016e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e72  mov     r14d, eax
0x180016e75  test    eax, eax
0x180016e77  js      loc_180016F9B
0x180016e7d  mov     rcx, [rdi+28h]
0x180016e81  test    rcx, rcx
0x180016e84  jnz     loc_180016FAD
0x180016e8a  mov     rbx, [rbp+pv]
0x180016e8e  mov     [rdi+28h], rbx
0x180016e92  mov     rax, [rbx]
0x180016e95  mov     rcx, rbx
0x180016e98  mov     rax, [rax+8]
0x180016e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ea1  mov     byte ptr [rdi+30h], 0
0x180016ea5  xorps   xmm0, xmm0
0x180016ea8  xor     eax, eax
0x180016eaa  movups  xmmword ptr [rbp+pvar], xmm0
0x180016eae  mov     [rbp+var_10], rax
0x180016eb2  mov     rax, [rbx]
0x180016eb5  lea     rcx, [rbp+pvar]
0x180016eb9  mov     [rsp+60h+var_38], rcx
0x180016ebe  mov     word ptr [rsp+60h+ppv], 3
0x180016ec5  xor     r9d, r9d
0x180016ec8  lea     r8, aHighcontrast; "HighContrast"
0x180016ecf  lea     rdx, aVisualstyles; "VisualStyles"
0x180016ed6  mov     rcx, rbx
0x180016ed9  mov     rax, [rax+28h]
0x180016edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee2  or      r15d, 0FFFFFFFFh
0x180016ee6  test    eax, eax
0x180016ee8  jns     loc_180016F7F
0x180016eee  mov     [rsi], r15d
0x180016ef1  mov     rax, [rbx]
0x180016ef4  mov     rcx, rbx
0x180016ef7  mov     rax, [rax+10h]
0x180016efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f00  cmp     [rsi], r15d
0x180016f03  jnz     short loc_180016F63
0x180016f05  mov     [rbp+lpString1], 0
0x180016f0d  mov     [rbp+pv], 0
0x180016f15  mov     rax, [rdi]
0x180016f18  lea     rdx, [rbp+lpString1]
0x180016f1c  mov     rcx, rdi
0x180016f1f  mov     rax, [rax+1E0h]
0x180016f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f2b  test    eax, eax
0x180016f2d  js      short loc_180016F53
0x180016f2f  mov     dword ptr [rsp+60h+ppv], 1; bIgnoreCase
0x180016f37  mov     r9d, r15d; cchCount2
0x180016f3a  lea     r8, String2; "DABJDKT"
0x180016f41  mov     edx, r15d; cchCount1
0x180016f44  mov     rcx, [rbp+lpString1]; lpString1
0x180016f48  call    cs:__imp_CompareStringOrdinal
0x180016f4e  cmp     eax, 2
0x180016f51  jz      short loc_180016FCF
0x180016f53  mov     dword ptr [rsi], 0
0x180016f59  mov     rcx, [rbp+lpString1]; bstrString
0x180016f5d  call    cs:__imp_SysFreeString
0x180016f63  mov     eax, r14d
0x180016f66  lea     r11, [rsp+60h+var_s0]
0x180016f6b  mov     rbx, [r11+40h]
0x180016f6f  mov     rsi, [r11+48h]
0x180016f73  mov     rsp, r11
0x180016f76  pop     r15
0x180016f78  pop     r14
0x180016f7a  pop     r12
0x180016f7c  pop     rdi
0x180016f7d  pop     rbp
0x180016f7e  retn
0x180016f7f  mov     eax, dword ptr [rbp+pvar+8]
0x180016f82  mov     [rsi], eax
0x180016f84  lea     rcx, [rbp+pvar]; pvar
0x180016f88  call    cs:__imp_PropVariantClear
0x180016f8e  jmp     loc_180016EF1
0x180016f93  mov     r14d, 80004005h
0x180016f99  jmp     short loc_180016F63
0x180016f9b  mov     rcx, [rbp+pv]
0x180016f9f  mov     rax, [rcx]
0x180016fa2  mov     rax, [rax+10h]
0x180016fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fab  jmp     short loc_180016F63
0x180016fad  mov     rax, [rcx]
0x180016fb0  mov     rax, [rax+10h]
0x180016fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fb9  jmp     loc_180016E8A
0x180016fbe  mov     rax, [rax+8]
0x180016fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc7  xor     r14d, r14d
0x180016fca  jmp     loc_180016EA5
0x180016fcf  lea     rax, [rbp+pv]
0x180016fd3  mov     [rsp+60h+ppv], rax; unsigned __int16 **
0x180016fd8  xor     r9d, r9d; unsigned int
0x180016fdb  lea     r8, aColorstyle; "ColorStyle"
0x180016fe2  lea     rdx, aVisualstyles; "VisualStyles"
0x180016fe9  lea     rcx, [rdi-10h]; this
0x180016fed  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x180016ff2  test    eax, eax
0x180016ff4  js      loc_180016F53
0x180016ffa  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180016ffe  call    ?HighContrastNumberFromSchemeName@@YAHPEBG@Z; HighContrastNumberFromSchemeName(ushort const *)
0x180017003  mov     [rsi], eax
0x180017005  mov     rcx, [rbp+pv]; pv
0x180017009  call    cs:__imp_CoTaskMemFree
0x18001700f  jmp     loc_180016F59
```
