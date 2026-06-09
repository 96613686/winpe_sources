# SHAutoComplete

- ea: `0x180024830`
- end: `0x1800249c7`
- name: `SHAutoComplete`
- size: `407`
- prototype: `HRESULT __stdcall(HWND hwndEdit, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002bb0`
- `0x180010a18`
- `0x180012550`
- `0x180022f58`
- `0x180023940`
- `0x180023ed0`
- `0x180024830`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800248d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800248d9`

## pseudocode

```c
HRESULT __stdcall SHAutoComplete(HWND hwndEdit, DWORD dwFlags)
{
  unsigned int updated; // eax
  char v5; // cl
  unsigned int v6; // r14d
  struct IUnknown *v7; // rbx
  int v9; // edi
  __int64 v10; // rdx
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  unsigned int v13; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v14; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v13 = 0;
  updated = _UpdateAutoCompleteFlags(dwFlags, &v13);
  v5 = 7;
  v6 = updated;
  if ( dwFlags )
    v5 = dwFlags;
  v7 = ACGetLists(v5, v13);
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x346,
      (unsigned int)"shell\\shlwapi\\util.cpp",
      (const char *)0x8007000ELL,
      ppv);
    return -2147024882;
  }
  v14 = 0;
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v14);
  v9 = CoCreateInstance(&CLSID_AutoComplete, 0, 1u, &GUID_eac04bc0_3791_11d2_bb95_0060977b464c, &v14);
  if ( v9 >= 0 )
  {
    if ( SHPinDllOfCLSID((__int64)&CLSID_ACListISF) && SHPinDllOfCLSID((__int64)&CLSID_AutoComplete) )
    {
      ppva = 0;
      v9 = (*(__int64 (__fastcall **)(LPVOID, HWND, struct IUnknown *, _QWORD))(*(_QWORD *)v14 + 24LL))(
             v14,
             hwndEdit,
             v7,
             0);
      if ( v9 >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v14 + 40LL))(v14, v6);
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v14);
        ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
        return 0;
      }
      v10 = 846;
    }
    else
    {
      v9 = -2147467259;
      v10 = 844;
    }
  }
  else
  {
    v10 = 843;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shell\\shlwapi\\util.cpp",
    (const char *)(unsigned int)v9,
    ppva);
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v14);
  ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  return v9;
}

```

## disassembly

```asm
0x180024830  mov     [rsp-18h+arg_10], rbx
0x180024835  mov     [rsp-18h+arg_18], rsi
0x18002483a  push    rbp
0x18002483b  push    rdi
0x18002483c  push    r14
0x18002483e  mov     rbp, rsp
0x180024841  sub     rsp, 50h
0x180024845  mov     rax, cs:__security_cookie
0x18002484c  xor     rax, rsp
0x18002484f  mov     [rbp+var_10], rax
0x180024853  mov     ebx, edx
0x180024855  mov     [rbp+var_20], 0
0x18002485c  mov     rsi, rcx
0x18002485f  lea     rdx, [rbp+var_20]; unsigned int *
0x180024863  mov     ecx, ebx; unsigned int
0x180024865  call    ?_UpdateAutoCompleteFlags@@YAKKPEAK@Z; _UpdateAutoCompleteFlags(ulong,ulong *)
0x18002486a  mov     edx, [rbp+var_20]; unsigned int
0x18002486d  mov     ecx, 7
0x180024872  test    ebx, ebx
0x180024874  mov     r14d, eax
0x180024877  cmovnz  ecx, ebx; unsigned int
0x18002487a  call    ?ACGetLists@@YAPEAUIUnknown@@KK@Z; ACGetLists(ulong,ulong)
0x18002487f  mov     rbx, rax
0x180024882  test    rax, rax
0x180024885  jnz     short loc_1800248AB
0x180024887  mov     rcx, [rbp+18h]; this
0x18002488b  lea     r8, aShellShlwapiUt; "shell\\shlwapi\\util.cpp"
0x180024892  mov     ebx, 8007000Eh
0x180024897  mov     edx, 346h; void *
0x18002489c  mov     r9d, ebx; char *
0x18002489f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248a4  mov     eax, ebx
0x1800248a6  jmp     loc_1800249A6
0x1800248ab  lea     rcx, [rbp+var_18]
0x1800248af  mov     [rbp+var_18], 0
0x1800248b7  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x1800248bc  xor     edx, edx; pUnkOuter
0x1800248be  lea     rax, [rbp+var_18]
0x1800248c2  lea     r9, _GUID_eac04bc0_3791_11d2_bb95_0060977b464c; riid
0x1800248c9  mov     qword ptr [rsp+50h+ppv], rax; int
0x1800248ce  lea     rcx, CLSID_AutoComplete; rclsid
0x1800248d5  lea     r8d, [rdx+1]; dwClsContext
0x1800248d9  call    cs:__imp_CoCreateInstance
0x1800248df  mov     edi, eax
0x1800248e1  test    eax, eax
0x1800248e3  jns     short loc_1800248EF
0x1800248e5  mov     edx, 34Bh
0x1800248ea  jmp     loc_180024979
0x1800248ef  lea     rcx, CLSID_ACListISF
0x1800248f6  call    SHPinDllOfCLSID
0x1800248fb  test    rax, rax
0x1800248fe  jz      short loc_18002496F
0x180024900  lea     rcx, CLSID_AutoComplete
0x180024907  call    SHPinDllOfCLSID
0x18002490c  test    rax, rax
0x18002490f  jz      short loc_18002496F
0x180024911  mov     rcx, [rbp+var_18]
0x180024915  xor     r9d, r9d
0x180024918  mov     r8, rbx
0x18002491b  mov     qword ptr [rsp+50h+ppv], 0
0x180024924  mov     rdx, rsi
0x180024927  mov     rax, [rcx]
0x18002492a  mov     rax, [rax+18h]
0x18002492e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024933  mov     edi, eax
0x180024935  test    eax, eax
0x180024937  jns     short loc_180024940
0x180024939  mov     edx, 34Eh
0x18002493e  jmp     short loc_180024979
0x180024940  mov     rcx, [rbp+var_18]
0x180024944  mov     edx, r14d
0x180024947  mov     rax, [rcx]
0x18002494a  mov     rax, [rax+28h]
0x18002494e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024953  lea     rcx, [rbp+var_18]
0x180024957  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18002495c  mov     rax, [rbx]
0x18002495f  mov     rcx, rbx
0x180024962  mov     rax, [rax+10h]
0x180024966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002496b  xor     eax, eax
0x18002496d  jmp     short loc_1800249A6
0x18002496f  mov     edi, 80004005h
0x180024974  mov     edx, 34Ch; void *
0x180024979  mov     rcx, [rbp+18h]; this
0x18002497d  lea     r8, aShellShlwapiUt; "shell\\shlwapi\\util.cpp"
0x180024984  mov     r9d, edi; char *
0x180024987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002498c  lea     rcx, [rbp+var_18]
0x180024990  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180024995  mov     rcx, [rbx]
0x180024998  mov     rax, [rcx+10h]
0x18002499c  mov     rcx, rbx
0x18002499f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a4  mov     eax, edi
0x1800249a6  mov     rcx, [rbp+var_10]
0x1800249aa  xor     rcx, rsp; StackCookie
0x1800249ad  call    __security_check_cookie
0x1800249b2  lea     r11, [rsp+50h+var_s0]
0x1800249b7  mov     rbx, [r11+30h]
0x1800249bb  mov     rsi, [r11+38h]
0x1800249bf  mov     rsp, r11
0x1800249c2  pop     r14
0x1800249c4  pop     rdi
0x1800249c5  pop     rbp
0x1800249c6  retn
```
