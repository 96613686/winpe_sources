# CThemeFile::get_ColorizationColor(ulong *)

- ea: `0x180017ea0`
- end: `0x180018105`
- name: `?get_ColorizationColor@CThemeFile@@UEAAJPEAK@Z`
- size: `613`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000dd60`
- `0x180017ea0`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrToIntExW` at `0x180017ff5`
- `SHLWAPI!StrToIntExW` at `0x180017ff5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001800a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001800a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017f1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017f1a`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_ColorizationColor(CThemeFile *this, unsigned int *a2)
{
  WCHAR *v2; // r15
  __int64 *v5; // rbx
  HRESULT v6; // edi
  __int64 v7; // rcx
  bool v8; // zf
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int piRet[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v17; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[528]; // [rsp+270h] [rbp+170h] BYREF

  v2 = 0;
  v17 = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v6 = -2147467259;
    goto LABEL_13;
  }
  v5 = (__int64 *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    v8 = *((_BYTE *)this + 48) == 0;
    v9 = *((_QWORD *)this + 5);
    v10 = *v5;
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(v10 + 8))(v9);
LABEL_20:
      *(_QWORD *)piRet = 0;
      if ( (int)StringCchPrintfW(v18, 0x104u, L"%s.MUI", L"ColorizationColor") >= 0
        && (*(int (__fastcall **)(__int64 *, const WCHAR *, unsigned __int16 *, _QWORD, int, int *))(*v5 + 48))(
             v5,
             L"VisualStyles",
             v18,
             0,
             1,
             piRet) >= 0
        || (v6 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, const WCHAR *, _QWORD, int, int *))(*v5 + 48))(
                   v5,
                   L"VisualStyles",
                   L"ColorizationColor",
                   0,
                   1,
                   piRet),
            v6 >= 0) )
      {
        memset_0(v19, 0, 0x208u);
        v6 = _AllocString<CTCoAllocPolicy>(v14, v13, *(_QWORD *)piRet, &v17);
        CoTaskMemFree(*(LPVOID *)piRet);
        v2 = v17;
      }
      v11 = *v5;
      goto LABEL_12;
    }
    (*(void (__fastcall **)(__int64))(v10 + 96))(v9);
  }
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v6 < 0 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
         ppv,
         *((_QWORD *)this + 4),
         0x400000);
  if ( v6 >= 0 )
  {
    v7 = *((_QWORD *)this + 5);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v5 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    *((_BYTE *)this + 48) = 0;
    goto LABEL_20;
  }
  v11 = *(_QWORD *)ppv;
LABEL_12:
  (*(void (**)(void))(v11 + 16))();
LABEL_13:
  if ( v6 >= 0 )
  {
    piRet[0] = 0;
    if ( StrToIntExW(v2, 1, piRet) )
      *a2 = piRet[0];
    else
      v6 = -2147467259;
    CoTaskMemFree(v2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017ea0  mov     [rsp-8+arg_10], rbx
0x180017ea5  mov     [rsp-8+arg_18], rsi
0x180017eaa  push    rbp
0x180017eab  push    rdi
0x180017eac  push    r12
0x180017eae  push    r14
0x180017eb0  push    r15
0x180017eb2  lea     rbp, [rsp-390h]
0x180017eba  sub     rsp, 490h
0x180017ec1  mov     rax, cs:__security_cookie
0x180017ec8  xor     rax, rsp
0x180017ecb  mov     [rbp+3B0h+var_30], rax
0x180017ed2  xor     r15d, r15d
0x180017ed5  mov     r12, rdx
0x180017ed8  mov     rsi, rcx
0x180017edb  mov     [rsp+4B0h+var_460], r15
0x180017ee0  cmp     [rcx+20h], r15
0x180017ee4  jz      loc_180017F97
0x180017eea  mov     rbx, [rcx+28h]
0x180017eee  test    rbx, rbx
0x180017ef1  jnz     loc_180017F79
0x180017ef7  xor     edx, edx; pUnkOuter
0x180017ef9  mov     [rsp+4B0h+var_468], r15
0x180017efe  lea     rax, [rsp+4B0h+var_468]
0x180017f03  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180017f0a  mov     [rsp+4B0h+ppv], rax; ppv
0x180017f0f  lea     rcx, CLSID_PrivateProfile; rclsid
0x180017f16  lea     r8d, [rdx+1]; dwClsContext
0x180017f1a  call    cs:__imp_CoCreateInstance
0x180017f20  mov     edi, eax
0x180017f22  test    eax, eax
0x180017f24  js      loc_180017FAF
0x180017f2a  mov     rcx, [rsp+4B0h+var_468]
0x180017f2f  mov     r8d, 400000h
0x180017f35  mov     rdx, [rsi+20h]
0x180017f39  mov     rax, [rcx]
0x180017f3c  mov     rax, [rax+18h]
0x180017f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f45  mov     edi, eax
0x180017f47  test    eax, eax
0x180017f49  js      short loc_180017F9E
0x180017f4b  mov     rcx, [rsi+28h]
0x180017f4f  test    rcx, rcx
0x180017f52  jnz     loc_180018019
0x180017f58  mov     rbx, [rsp+4B0h+var_468]
0x180017f5d  mov     [rsi+28h], rbx
0x180017f61  mov     rcx, rbx
0x180017f64  mov     rax, [rbx]
0x180017f67  mov     rax, [rax+8]
0x180017f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f70  mov     [rsi+30h], r15b
0x180017f74  jmp     loc_180018033
0x180017f79  cmp     [rcx+30h], r15b
0x180017f7d  mov     rcx, rbx
0x180017f80  mov     rax, [rbx]
0x180017f83  jz      loc_18001802A
0x180017f89  mov     rax, [rax+60h]
0x180017f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f92  jmp     loc_180017EF7
0x180017f97  mov     edi, 80004005h
0x180017f9c  jmp     short loc_180017FAF
0x180017f9e  mov     rcx, [rsp+4B0h+var_468]
0x180017fa3  mov     rax, [rcx]
0x180017fa6  mov     rax, [rax+10h]
0x180017faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017faf  test    edi, edi
0x180017fb1  jns     short loc_180017FE0
0x180017fb3  mov     eax, edi
0x180017fb5  mov     rcx, [rbp+3B0h+var_30]
0x180017fbc  xor     rcx, rsp; StackCookie
0x180017fbf  call    __security_check_cookie
0x180017fc4  lea     r11, [rsp+4B0h+var_20]
0x180017fcc  mov     rbx, [r11+40h]
0x180017fd0  mov     rsi, [r11+48h]
0x180017fd4  mov     rsp, r11
0x180017fd7  pop     r15
0x180017fd9  pop     r14
0x180017fdb  pop     r12
0x180017fdd  pop     rdi
0x180017fde  pop     rbp
0x180017fdf  retn
0x180017fe0  lea     r8, [rsp+4B0h+piRet]; piRet
0x180017fe5  mov     [rsp+4B0h+piRet], 0
0x180017fed  mov     edx, 1; dwFlags
0x180017ff2  mov     rcx, r15; pszString
0x180017ff5  call    cs:__imp_StrToIntExW
0x180017ffb  test    eax, eax
0x180017ffd  jz      short loc_180018012
0x180017fff  mov     eax, [rsp+4B0h+piRet]
0x180018003  mov     [r12], eax
0x180018007  mov     rcx, r15; pv
0x18001800a  call    cs:__imp_CoTaskMemFree
0x180018010  jmp     short loc_180017FB3
0x180018012  mov     edi, 80004005h
0x180018017  jmp     short loc_180018007
0x180018019  mov     rax, [rcx]
0x18001801c  mov     rax, [rax+10h]
0x180018020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018025  jmp     loc_180017F58
0x18001802a  mov     rax, [rax+8]
0x18001802e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018033  lea     r9, aColorizationco; "ColorizationColor"
0x18001803a  mov     qword ptr [rsp+4B0h+piRet], r15
0x18001803f  lea     r8, aSMui; "%s.MUI"
0x180018046  mov     edx, 104h; unsigned __int64
0x18001804b  lea     rcx, [rsp+4B0h+var_450]; unsigned __int16 *
0x180018050  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018055  test    eax, eax
0x180018057  js      short loc_18001808D
0x180018059  mov     rax, [rbx]
0x18001805c  lea     rcx, [rsp+4B0h+piRet]
0x180018061  mov     [rsp+4B0h+var_488], rcx
0x180018066  lea     r8, [rsp+4B0h+var_450]
0x18001806b  xor     r9d, r9d
0x18001806e  mov     dword ptr [rsp+4B0h+ppv], 1
0x180018076  lea     rdx, aVisualstyles; "VisualStyles"
0x18001807d  mov     rcx, rbx
0x180018080  mov     rax, [rax+30h]
0x180018084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018089  test    eax, eax
0x18001808b  jns     short loc_1800180C5
0x18001808d  mov     rax, [rbx]
0x180018090  lea     rcx, [rsp+4B0h+piRet]
0x180018095  mov     [rsp+4B0h+var_488], rcx
0x18001809a  lea     r8, aColorizationco; "ColorizationColor"
0x1800180a1  xor     r9d, r9d
0x1800180a4  mov     dword ptr [rsp+4B0h+ppv], 1
0x1800180ac  lea     rdx, aVisualstyles; "VisualStyles"
0x1800180b3  mov     rcx, rbx
0x1800180b6  mov     rax, [rax+30h]
0x1800180ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180bf  mov     edi, eax
0x1800180c1  test    eax, eax
0x1800180c3  js      short loc_1800180FA
0x1800180c5  xor     edx, edx; Val
0x1800180c7  lea     rcx, [rbp+3B0h+var_240]; void *
0x1800180ce  mov     r8d, 208h; Size
0x1800180d4  call    memset_0
0x1800180d9  mov     r8, qword ptr [rsp+4B0h+piRet]
0x1800180de  lea     r9, [rsp+4B0h+var_460]
0x1800180e3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800180e8  mov     rcx, qword ptr [rsp+4B0h+piRet]; pv
0x1800180ed  mov     edi, eax
0x1800180ef  call    cs:__imp_CoTaskMemFree
0x1800180f5  mov     r15, [rsp+4B0h+var_460]
0x1800180fa  mov     rax, [rbx]
0x1800180fd  mov     rcx, rbx
0x180018100  jmp     loc_180017FA6
```
