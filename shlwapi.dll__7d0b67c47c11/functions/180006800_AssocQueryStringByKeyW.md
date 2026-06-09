# AssocQueryStringByKeyW

- ea: `0x180006800`
- end: `0x18000693b`
- name: `AssocQueryStringByKeyW`
- size: `315`
- prototype: `HRESULT __stdcall(ASSOCF flags, ASSOCSTR str, HKEY hkAssoc, LPCWSTR pszExtra, LPWSTR pszOut, DWORD *pcchOut)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800203e0`

## callees

- `0x180006800`
- `0x180012550`
- `0x1800369c5`
- `0x180037010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000688a`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000688a`

## pseudocode

```c
HRESULT __stdcall AssocQueryStringByKeyW(
        ASSOCF flags,
        ASSOCSTR str,
        HKEY hkAssoc,
        LPCWSTR pszExtra,
        LPWSTR pszOut,
        DWORD *pcchOut)
{
  int v10; // ebx
  GUID Buf1; // [rsp+40h] [rbp-68h] BYREF
  void *ppv; // [rsp+50h] [rbp-58h] BYREF

  Buf1 = CLSID_QueryAssociations;
  ppv = 0;
  if ( !memcmp_0(&Buf1, &CLSID_QueryAssociations, 0x10u)
    || (v10 = -2147024809, !memcmp_0(&Buf1, &IID_IQueryAssociations, 0x10u)) )
  {
    v10 = SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, HKEY, _QWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              flags & 0x40F,
              0,
              hkAssoc,
              0);
      if ( v10 >= 0 )
        v10 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, LPCWSTR, LPWSTR, DWORD *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                flags,
                (unsigned int)str,
                pszExtra,
                pszOut,
                pcchOut);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180006800  push    rbx
0x180006802  push    rbp
0x180006803  push    rsi
0x180006804  push    rdi
0x180006805  push    r12
0x180006807  push    r13
0x180006809  push    r14
0x18000680b  push    r15
0x18000680d  sub     rsp, 68h
0x180006811  mov     rax, cs:__security_cookie
0x180006818  xor     rax, rsp
0x18000681b  mov     [rsp+0A8h+var_50], rax
0x180006820  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180006827  mov     r15, [rsp+0A8h+pszOut]
0x18000682f  mov     rsi, r8
0x180006832  mov     r12, [rsp+0A8h+pcchOut]
0x18000683a  mov     ebp, edx
0x18000683c  mov     edi, ecx
0x18000683e  movaps  [rsp+0A8h+Buf1], xmm0
0x180006843  xor     r13d, r13d
0x180006846  lea     rdx, CLSID_QueryAssociations; Buf2
0x18000684d  mov     r8d, 10h; Size
0x180006853  mov     [rsp+0A8h+var_58], r13
0x180006858  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x18000685d  mov     r14, r9
0x180006860  call    memcmp_0
0x180006865  test    eax, eax
0x180006867  jnz     loc_180006916
0x18000686d  lea     rax, [rsp+0A8h+var_58]
0x180006872  xor     r8d, r8d; pUnkOuter
0x180006875  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000687c  mov     [rsp+0A8h+ppv], rax; ppv
0x180006881  lea     rdx, CLSID_QueryAssociations; pclsid
0x180006888  xor     ecx, ecx; pszCLSID
0x18000688a  call    cs:__imp_SHCoCreateInstance
0x180006890  mov     ebx, eax
0x180006892  test    eax, eax
0x180006894  js      short loc_1800068F6
0x180006896  mov     rcx, [rsp+0A8h+var_58]
0x18000689b  mov     edx, edi
0x18000689d  and     edx, 40Fh
0x1800068a3  mov     [rsp+0A8h+ppv], r13
0x1800068a8  mov     r9, rsi
0x1800068ab  xor     r8d, r8d
0x1800068ae  mov     rax, [rcx]
0x1800068b1  mov     rax, [rax+18h]
0x1800068b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ba  mov     ebx, eax
0x1800068bc  test    eax, eax
0x1800068be  js      short loc_1800068E5
0x1800068c0  mov     rcx, [rsp+0A8h+var_58]
0x1800068c5  mov     r9, r14
0x1800068c8  mov     [rsp+0A8h+var_80], r12
0x1800068cd  mov     r8d, ebp
0x1800068d0  mov     edx, edi
0x1800068d2  mov     [rsp+0A8h+ppv], r15
0x1800068d7  mov     rax, [rcx]
0x1800068da  mov     rax, [rax+20h]
0x1800068de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e3  mov     ebx, eax
0x1800068e5  mov     rcx, [rsp+0A8h+var_58]
0x1800068ea  mov     rax, [rcx]
0x1800068ed  mov     rax, [rax+10h]
0x1800068f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f6  mov     eax, ebx
0x1800068f8  mov     rcx, [rsp+0A8h+var_50]
0x1800068fd  xor     rcx, rsp; StackCookie
0x180006900  call    __security_check_cookie
0x180006905  add     rsp, 68h
0x180006909  pop     r15
0x18000690b  pop     r14
0x18000690d  pop     r13
0x18000690f  pop     r12
0x180006911  pop     rdi
0x180006912  pop     rsi
0x180006913  pop     rbp
0x180006914  pop     rbx
0x180006915  retn
0x180006916  mov     r8d, 10h; Size
0x18000691c  lea     rdx, IID_IQueryAssociations; Buf2
0x180006923  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x180006928  mov     ebx, 80070057h
0x18000692d  call    memcmp_0
0x180006932  test    eax, eax
0x180006934  jnz     short loc_1800068F6
0x180006936  jmp     loc_18000686D
```
