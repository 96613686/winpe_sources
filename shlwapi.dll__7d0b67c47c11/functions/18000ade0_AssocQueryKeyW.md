# AssocQueryKeyW

- ea: `0x18000ade0`
- end: `0x18000af0e`
- name: `AssocQueryKeyW`
- size: `302`
- prototype: `HRESULT __stdcall(ASSOCF flags, ASSOCKEY key, LPCWSTR pszAssoc, LPCWSTR pszExtra, HKEY *phkeyOut)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020170`

## callees

- `0x18000ade0`
- `0x180012550`
- `0x1800369c5`
- `0x180037010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000ae87`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000ae87`

## pseudocode

```c
HRESULT __stdcall AssocQueryKeyW(ASSOCF flags, ASSOCKEY key, LPCWSTR pszAssoc, LPCWSTR pszExtra, HKEY *phkeyOut)
{
  int v9; // ebx
  GUID Buf1; // [rsp+30h] [rbp-58h] BYREF
  void *ppv; // [rsp+40h] [rbp-48h] BYREF

  ppv = 0;
  *phkeyOut = 0;
  Buf1 = CLSID_QueryAssociations;
  if ( !memcmp_0(&Buf1, &CLSID_QueryAssociations, 0x10u)
    || (v9 = -2147024809, !memcmp_0(&Buf1, &IID_IQueryAssociations, 0x10u)) )
  {
    v9 = SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(void *, _QWORD, LPCWSTR, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
             ppv,
             flags & 0x40F,
             pszAssoc,
             0,
             0);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, LPCWSTR, HKEY *))(*(_QWORD *)ppv + 40LL))(
               ppv,
               flags,
               (unsigned int)key,
               pszExtra,
               phkeyOut);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000ade0  push    rbx
0x18000ade2  push    rbp
0x18000ade3  push    rsi
0x18000ade4  push    rdi
0x18000ade5  push    r14
0x18000ade7  push    r15
0x18000ade9  sub     rsp, 58h
0x18000aded  mov     rax, cs:__security_cookie
0x18000adf4  xor     rax, rsp
0x18000adf7  mov     [rsp+88h+var_40], rax
0x18000adfc  mov     rsi, [rsp+88h+phkeyOut]
0x18000ae04  mov     r15, r8
0x18000ae07  mov     ebp, edx
0x18000ae09  mov     [rsp+88h+var_48], 0
0x18000ae12  mov     edi, ecx
0x18000ae14  lea     rdx, CLSID_QueryAssociations; Buf2
0x18000ae1b  mov     r8d, 10h; Size
0x18000ae21  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18000ae26  mov     qword ptr [rsi], 0
0x18000ae2d  mov     r14, r9
0x18000ae30  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x18000ae37  movdqu  [rsp+88h+Buf1], xmm0
0x18000ae3d  call    memcmp_0
0x18000ae42  test    eax, eax
0x18000ae44  jz      short loc_18000AE6A
0x18000ae46  mov     r8d, 10h; Size
0x18000ae4c  lea     rdx, IID_IQueryAssociations; Buf2
0x18000ae53  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18000ae58  mov     ebx, 80070057h
0x18000ae5d  call    memcmp_0
0x18000ae62  test    eax, eax
0x18000ae64  jnz     loc_18000AEF2
0x18000ae6a  lea     rax, [rsp+88h+var_48]
0x18000ae6f  xor     r8d, r8d; pUnkOuter
0x18000ae72  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000ae79  mov     [rsp+88h+ppv], rax; ppv
0x18000ae7e  lea     rdx, CLSID_QueryAssociations; pclsid
0x18000ae85  xor     ecx, ecx; pszCLSID
0x18000ae87  call    cs:__imp_SHCoCreateInstance
0x18000ae8d  mov     ebx, eax
0x18000ae8f  test    eax, eax
0x18000ae91  js      short loc_18000AEF2
0x18000ae93  mov     rcx, [rsp+88h+var_48]
0x18000ae98  mov     edx, edi
0x18000ae9a  and     edx, 40Fh
0x18000aea0  mov     [rsp+88h+ppv], 0
0x18000aea9  xor     r9d, r9d
0x18000aeac  mov     r8, r15
0x18000aeaf  mov     rax, [rcx]
0x18000aeb2  mov     rax, [rax+18h]
0x18000aeb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebb  mov     ebx, eax
0x18000aebd  test    eax, eax
0x18000aebf  js      short loc_18000AEE1
0x18000aec1  mov     rcx, [rsp+88h+var_48]
0x18000aec6  mov     r9, r14
0x18000aec9  mov     r8d, ebp
0x18000aecc  mov     [rsp+88h+ppv], rsi
0x18000aed1  mov     edx, edi
0x18000aed3  mov     rax, [rcx]
0x18000aed6  mov     rax, [rax+28h]
0x18000aeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aedf  mov     ebx, eax
0x18000aee1  mov     rcx, [rsp+88h+var_48]
0x18000aee6  mov     rax, [rcx]
0x18000aee9  mov     rax, [rax+10h]
0x18000aeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef2  mov     eax, ebx
0x18000aef4  mov     rcx, [rsp+88h+var_40]
0x18000aef9  xor     rcx, rsp; StackCookie
0x18000aefc  call    __security_check_cookie
0x18000af01  add     rsp, 58h
0x18000af05  pop     r15
0x18000af07  pop     r14
0x18000af09  pop     rdi
0x18000af0a  pop     rsi
0x18000af0b  pop     rbp
0x18000af0c  pop     rbx
0x18000af0d  retn
```
