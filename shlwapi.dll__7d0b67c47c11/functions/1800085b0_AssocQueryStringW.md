# AssocQueryStringW

- ea: `0x1800085b0`
- end: `0x1800086eb`
- name: `AssocQueryStringW`
- size: `315`
- prototype: `HRESULT __stdcall(ASSOCF flags, ASSOCSTR str, LPCWSTR pszAssoc, LPCWSTR pszExtra, LPWSTR pszOut, DWORD *pcchOut)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fa90`
- `0x180020250`
- `0x180020b20`

## callees

- `0x1800085b0`
- `0x180012550`
- `0x1800369c5`
- `0x180037010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000863a`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000863a`

## pseudocode

```c
HRESULT __stdcall AssocQueryStringW(
        ASSOCF flags,
        ASSOCSTR str,
        LPCWSTR pszAssoc,
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
      v10 = (*(__int64 (__fastcall **)(void *, _QWORD, LPCWSTR, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              flags & 0x40F,
              pszAssoc,
              0,
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
0x1800085b0  push    rbx
0x1800085b2  push    rbp
0x1800085b3  push    rsi
0x1800085b4  push    rdi
0x1800085b5  push    r12
0x1800085b7  push    r13
0x1800085b9  push    r14
0x1800085bb  push    r15
0x1800085bd  sub     rsp, 68h
0x1800085c1  mov     rax, cs:__security_cookie
0x1800085c8  xor     rax, rsp
0x1800085cb  mov     [rsp+0A8h+var_50], rax
0x1800085d0  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x1800085d7  mov     r15, [rsp+0A8h+pszOut]
0x1800085df  mov     rsi, r8
0x1800085e2  mov     r12, [rsp+0A8h+pcchOut]
0x1800085ea  mov     ebp, edx
0x1800085ec  mov     edi, ecx
0x1800085ee  movaps  [rsp+0A8h+Buf1], xmm0
0x1800085f3  xor     r13d, r13d
0x1800085f6  lea     rdx, CLSID_QueryAssociations; Buf2
0x1800085fd  mov     r8d, 10h; Size
0x180008603  mov     [rsp+0A8h+var_58], r13
0x180008608  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x18000860d  mov     r14, r9
0x180008610  call    memcmp_0
0x180008615  test    eax, eax
0x180008617  jnz     loc_1800086C6
0x18000861d  lea     rax, [rsp+0A8h+var_58]
0x180008622  xor     r8d, r8d; pUnkOuter
0x180008625  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000862c  mov     [rsp+0A8h+ppv], rax; ppv
0x180008631  lea     rdx, CLSID_QueryAssociations; pclsid
0x180008638  xor     ecx, ecx; pszCLSID
0x18000863a  call    cs:__imp_SHCoCreateInstance
0x180008640  mov     ebx, eax
0x180008642  test    eax, eax
0x180008644  js      short loc_1800086A6
0x180008646  mov     rcx, [rsp+0A8h+var_58]
0x18000864b  mov     edx, edi
0x18000864d  and     edx, 40Fh
0x180008653  mov     [rsp+0A8h+ppv], r13
0x180008658  xor     r9d, r9d
0x18000865b  mov     r8, rsi
0x18000865e  mov     rax, [rcx]
0x180008661  mov     rax, [rax+18h]
0x180008665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866a  mov     ebx, eax
0x18000866c  test    eax, eax
0x18000866e  js      short loc_180008695
0x180008670  mov     rcx, [rsp+0A8h+var_58]
0x180008675  mov     r9, r14
0x180008678  mov     [rsp+0A8h+var_80], r12
0x18000867d  mov     r8d, ebp
0x180008680  mov     edx, edi
0x180008682  mov     [rsp+0A8h+ppv], r15
0x180008687  mov     rax, [rcx]
0x18000868a  mov     rax, [rax+20h]
0x18000868e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008693  mov     ebx, eax
0x180008695  mov     rcx, [rsp+0A8h+var_58]
0x18000869a  mov     rax, [rcx]
0x18000869d  mov     rax, [rax+10h]
0x1800086a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a6  mov     eax, ebx
0x1800086a8  mov     rcx, [rsp+0A8h+var_50]
0x1800086ad  xor     rcx, rsp; StackCookie
0x1800086b0  call    __security_check_cookie
0x1800086b5  add     rsp, 68h
0x1800086b9  pop     r15
0x1800086bb  pop     r14
0x1800086bd  pop     r13
0x1800086bf  pop     r12
0x1800086c1  pop     rdi
0x1800086c2  pop     rsi
0x1800086c3  pop     rbp
0x1800086c4  pop     rbx
0x1800086c5  retn
0x1800086c6  mov     r8d, 10h; Size
0x1800086cc  lea     rdx, IID_IQueryAssociations; Buf2
0x1800086d3  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x1800086d8  mov     ebx, 80070057h
0x1800086dd  call    memcmp_0
0x1800086e2  test    eax, eax
0x1800086e4  jnz     short loc_1800086A6
0x1800086e6  jmp     loc_18000861D
```
