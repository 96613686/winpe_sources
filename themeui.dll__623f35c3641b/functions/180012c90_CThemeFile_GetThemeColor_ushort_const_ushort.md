# CThemeFile::GetThemeColor(ushort const *,ushort * *)

- ea: `0x180012c90`
- end: `0x180012e94`
- name: `?GetThemeColor@CThemeFile@@UEAAJPEBGPEAPEAG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000dd60`
- `0x180012c90`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012e78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012cfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012cfc`

## pseudocode

```c
__int64 __fastcall CThemeFile::GetThemeColor(CThemeFile *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 *v6; // rdi
  HRESULT v7; // edi
  __int64 v8; // rcx
  bool v9; // zf
  __int64 v10; // rcx
  __int64 v11; // rax
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  LPVOID pv; // [rsp+40h] [rbp-468h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-460h] BYREF
  unsigned __int16 v18[264]; // [rsp+50h] [rbp-458h] BYREF
  _BYTE v19[528]; // [rsp+260h] [rbp-248h] BYREF

  *a3 = 0;
  if ( !*((_QWORD *)this + 4) )
    return (unsigned int)-2147467259;
  v6 = (__int64 *)*((_QWORD *)this + 5);
  if ( !v6 )
  {
LABEL_3:
    ppv = 0;
    v7 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
             ppv,
             *((_QWORD *)this + 4),
             0x400000);
      if ( v7 >= 0 )
      {
        v8 = *((_QWORD *)this + 5);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        v6 = (__int64 *)ppv;
        *((_QWORD *)this + 5) = ppv;
        (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
        *((_BYTE *)this + 48) = 0;
        goto LABEL_14;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    return (unsigned int)v7;
  }
  v9 = *((_BYTE *)this + 48) == 0;
  v10 = *((_QWORD *)this + 5);
  v11 = *v6;
  if ( !v9 )
  {
    (*(void (__fastcall **)(__int64))(v11 + 96))(v10);
    goto LABEL_3;
  }
  (*(void (__fastcall **)(__int64))(v11 + 8))(v10);
LABEL_14:
  pv = 0;
  if ( (int)StringCchPrintfW(v18, 0x104u, L"%s.MUI", a2) >= 0
    && (*(int (__fastcall **)(__int64 *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPVOID *))(*v6 + 48))(
         v6,
         L"Control Panel\\Colors",
         v18,
         0,
         1,
         &pv) >= 0
    || (v13 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, const unsigned __int16 *, _QWORD, int, LPVOID *))(*v6 + 48))(
                v6,
                L"Control Panel\\Colors",
                a2,
                0,
                1,
                &pv),
        v13 >= 0) )
  {
    memset_0(v19, 0, 0x208u);
    v13 = _AllocString<CTCoAllocPolicy>(v15, v14, pv, a3);
    CoTaskMemFree(pv);
  }
  (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012c90  mov     [rsp+arg_18], rbx
0x180012c95  push    rbp
0x180012c96  push    rsi
0x180012c97  push    rdi
0x180012c98  push    r14
0x180012c9a  push    r15
0x180012c9c  sub     rsp, 480h
0x180012ca3  mov     rax, cs:__security_cookie
0x180012caa  xor     rax, rsp
0x180012cad  mov     [rsp+4A8h+var_38], rax
0x180012cb5  xor     r15d, r15d
0x180012cb8  mov     r14, r8
0x180012cbb  mov     [r8], r15
0x180012cbe  mov     rbp, rdx
0x180012cc1  mov     rbx, rcx
0x180012cc4  cmp     [rcx+20h], r15
0x180012cc8  jz      loc_180012D6A
0x180012cce  mov     rdi, [rcx+28h]
0x180012cd2  test    rdi, rdi
0x180012cd5  jnz     short loc_180012D50
0x180012cd7  lea     rax, [rsp+4A8h+var_460]
0x180012cdc  mov     [rsp+4A8h+var_460], r15
0x180012ce1  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180012ce8  mov     [rsp+4A8h+ppv], rax; ppv
0x180012ced  xor     edx, edx; pUnkOuter
0x180012cef  lea     rcx, CLSID_PrivateProfile; rclsid
0x180012cf6  mov     r8d, 1; dwClsContext
0x180012cfc  call    cs:__imp_CoCreateInstance
0x180012d02  mov     edi, eax
0x180012d04  test    eax, eax
0x180012d06  js      short loc_180012D6F
0x180012d08  mov     rcx, [rsp+4A8h+var_460]
0x180012d0d  mov     r8d, 400000h
0x180012d13  mov     rdx, [rbx+20h]
0x180012d17  mov     rax, [rcx]
0x180012d1a  mov     rax, [rax+18h]
0x180012d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d23  mov     edi, eax
0x180012d25  test    eax, eax
0x180012d27  js      short loc_180012D98
0x180012d29  mov     rcx, [rbx+28h]
0x180012d2d  test    rcx, rcx
0x180012d30  jnz     short loc_180012DAB
0x180012d32  mov     rdi, [rsp+4A8h+var_460]
0x180012d37  mov     [rbx+28h], rdi
0x180012d3b  mov     rcx, rdi
0x180012d3e  mov     rax, [rdi]
0x180012d41  mov     rax, [rax+8]
0x180012d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4a  mov     [rbx+30h], r15b
0x180012d4e  jmp     short loc_180012DC5
0x180012d50  cmp     [rcx+30h], r15b
0x180012d54  mov     rcx, rdi
0x180012d57  mov     rax, [rdi]
0x180012d5a  jz      short loc_180012DBC
0x180012d5c  mov     rax, [rax+60h]
0x180012d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d65  jmp     loc_180012CD7
0x180012d6a  mov     edi, 80004005h
0x180012d6f  mov     eax, edi
0x180012d71  mov     rcx, [rsp+4A8h+var_38]
0x180012d79  xor     rcx, rsp; StackCookie
0x180012d7c  call    __security_check_cookie
0x180012d81  mov     rbx, [rsp+4A8h+arg_18]
0x180012d89  add     rsp, 480h
0x180012d90  pop     r15
0x180012d92  pop     r14
0x180012d94  pop     rdi
0x180012d95  pop     rsi
0x180012d96  pop     rbp
0x180012d97  retn
0x180012d98  mov     rcx, [rsp+4A8h+var_460]
0x180012d9d  mov     rdx, [rcx]
0x180012da0  mov     rax, [rdx+10h]
0x180012da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da9  jmp     short loc_180012D6F
0x180012dab  mov     rax, [rcx]
0x180012dae  mov     rax, [rax+10h]
0x180012db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db7  jmp     loc_180012D32
0x180012dbc  mov     rax, [rax+8]
0x180012dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dc5  mov     r9, rbp
0x180012dc8  mov     [rsp+4A8h+pv], r15
0x180012dcd  lea     r8, aSMui; "%s.MUI"
0x180012dd4  mov     edx, 104h; unsigned __int64
0x180012dd9  lea     rcx, [rsp+4A8h+var_458]; unsigned __int16 *
0x180012dde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012de3  test    eax, eax
0x180012de5  js      short loc_180012E1B
0x180012de7  mov     rax, [rdi]
0x180012dea  lea     rcx, [rsp+4A8h+pv]
0x180012def  mov     [rsp+4A8h+var_480], rcx
0x180012df4  lea     r8, [rsp+4A8h+var_458]
0x180012df9  xor     r9d, r9d
0x180012dfc  mov     dword ptr [rsp+4A8h+ppv], 1
0x180012e04  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x180012e0b  mov     rcx, rdi
0x180012e0e  mov     rax, [rax+30h]
0x180012e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e17  test    eax, eax
0x180012e19  jns     short loc_180012E4F
0x180012e1b  mov     rax, [rdi]
0x180012e1e  lea     rcx, [rsp+4A8h+pv]
0x180012e23  mov     [rsp+4A8h+var_480], rcx
0x180012e28  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x180012e2f  xor     r9d, r9d
0x180012e32  mov     dword ptr [rsp+4A8h+ppv], 1
0x180012e3a  mov     r8, rbp
0x180012e3d  mov     rcx, rdi
0x180012e40  mov     rax, [rax+30h]
0x180012e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e49  mov     ebx, eax
0x180012e4b  test    eax, eax
0x180012e4d  js      short loc_180012E7E
0x180012e4f  xor     edx, edx; Val
0x180012e51  lea     rcx, [rsp+4A8h+var_248]; void *
0x180012e59  mov     r8d, 208h; Size
0x180012e5f  call    memset_0
0x180012e64  mov     r8, [rsp+4A8h+pv]
0x180012e69  mov     r9, r14
0x180012e6c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180012e71  mov     rcx, [rsp+4A8h+pv]; pv
0x180012e76  mov     ebx, eax
0x180012e78  call    cs:__imp_CoTaskMemFree
0x180012e7e  mov     rax, [rdi]
0x180012e81  mov     rcx, rdi
0x180012e84  mov     rax, [rax+10h]
0x180012e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e8d  mov     eax, ebx
0x180012e8f  jmp     loc_180012D71
```
