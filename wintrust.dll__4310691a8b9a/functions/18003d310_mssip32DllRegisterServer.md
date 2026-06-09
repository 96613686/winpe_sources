# mssip32DllRegisterServer

- ea: `0x18003d310`
- end: `0x18003d558`
- name: `mssip32DllRegisterServer`
- size: `584`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800358f0`

## callees

- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `CRYPT32!CryptSIPAddProvider` at `0x18003d47d`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d493`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4b7`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4db`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4f4`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d50c`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d524`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d47d`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d493`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4b7`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4db`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d4f4`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d50c`
- `CRYPT32!CryptSIPAddProvider` at `0x18003d524`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d4e9`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d535`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d4e9`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d535`

## string_xrefs

- `0x18003d423`: `WINTRUST.DLL`
- `0x18003d450`: `CryptSIPCreateIndirectData`
- `0x18003d468`: `CryptSIPRemoveSignedDataMsg`

## pseudocode

```c
__int64 mssip32DllRegisterServer()
{
  BOOL v0; // ebx
  int v1; // edi
  int v2; // esi
  int v3; // ebx
  int v4; // edi
  SIP_ADD_NEWPROVIDER psNewProv; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v7[4]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v8[4]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v9[4]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v10[4]; // [rsp+B0h] [rbp-50h] BYREF
  GUID pgProv; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v12[4]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v13[4]; // [rsp+E0h] [rbp-20h] BYREF
  GUID v14; // [rsp+F0h] [rbp-10h] BYREF

  v7[0] = -566945214;
  v7[1] = 298880601;
  v7[2] = -1073723508;
  v7[3] = -292175281;
  v10[0] = -964056392;
  v10[1] = 298880632;
  v10[2] = -1073723508;
  v10[3] = -292175281;
  v9[0] = -964056390;
  v9[1] = 298880632;
  v9[2] = -1073723508;
  v9[3] = -292175281;
  pgProv.Data1 = -964056391;
  *(_DWORD *)&pgProv.Data2 = 298880632;
  *(_DWORD *)pgProv.Data4 = -1073723508;
  *(_DWORD *)&pgProv.Data4[4] = -292175281;
  v12[0] = -566945213;
  v12[1] = 298880601;
  v12[2] = -1073723508;
  v12[3] = -292175281;
  v13[0] = -1683612353;
  v13[1] = 298903354;
  v13[2] = -1073687924;
  v13[3] = -292175281;
  v14.Data1 = -1810093769;
  *(_DWORD *)&v14.Data2 = 298914450;
  *(_DWORD *)v14.Data4 = -1073693051;
  *(_DWORD *)&v14.Data4[4] = -292175281;
  v8[0] = 414433601;
  v8[1] = 1090104845;
  v8[2] = 1122330004;
  v8[3] = -945045073;
  memset_0(&psNewProv, 0, 0x60u);
  psNewProv.cbStruct = 96;
  psNewProv.pwszDLLFileName = (WCHAR *)L"WINTRUST.DLL";
  psNewProv.pwszGetFuncName = L"CryptSIPGetSignedDataMsg";
  psNewProv.pwszPutFuncName = L"CryptSIPPutSignedDataMsg";
  psNewProv.pwszCreateFuncName = L"CryptSIPCreateIndirectData";
  psNewProv.pwszVerifyFuncName = L"CryptSIPVerifyIndirectData";
  psNewProv.pwszRemoveFuncName = L"CryptSIPRemoveSignedDataMsg";
  psNewProv.pgSubject = (GUID *)v7;
  v0 = CryptSIPAddProvider(&psNewProv);
  psNewProv.pgSubject = (GUID *)v8;
  v1 = v0 & CryptSIPAddProvider(&psNewProv);
  psNewProv.pgSubject = (GUID *)v9;
  psNewProv.pwszMagicNumber = L"MSCF";
  v2 = v1 & CryptSIPAddProvider(&psNewProv);
  psNewProv.pgSubject = (GUID *)v10;
  psNewProv.pwszMagicNumber = L"0x00004550";
  v3 = v2 & CryptSIPAddProvider(&psNewProv);
  CryptSIPRemoveProvider(&pgProv);
  LOBYTE(v1) = v3 & CryptSIPAddProvider(&psNewProv);
  psNewProv.pgSubject = (GUID *)v12;
  LOBYTE(v3) = v1 & CryptSIPAddProvider(&psNewProv);
  psNewProv.pgSubject = (GUID *)v13;
  v4 = (unsigned __int8)v3 & CryptSIPAddProvider(&psNewProv) & 1;
  CryptSIPRemoveProvider(&v14);
  return v4 ^ 1u;
}

```

## disassembly

```asm
0x18003d310  push    rbp
0x18003d312  push    rbx
0x18003d313  push    rsi
0x18003d314  push    rdi
0x18003d315  lea     rbp, [rsp-18h]
0x18003d31a  sub     rsp, 118h
0x18003d321  mov     rax, cs:__security_cookie
0x18003d328  xor     rax, rsp
0x18003d32b  mov     [rbp+30h+var_30], rax
0x18003d32f  mov     ebx, 60h ; '`'
0x18003d334  mov     [rbp+30h+var_B0], 0DE351A42h
0x18003d33b  mov     r8d, ebx; Size
0x18003d33e  mov     [rbp+30h+var_AC], 11D08E59h
0x18003d345  xor     edx, edx; Val
0x18003d347  mov     [rbp+30h+var_A8], 0C000478Ch
0x18003d34e  lea     rcx, [rsp+130h+psNewProv]; void *
0x18003d353  mov     [rbp+30h+var_A4], 0EE95C24Fh
0x18003d35a  mov     [rbp+30h+var_80], 0C689AAB8h
0x18003d361  mov     [rbp+30h+var_7C], 11D08E78h
0x18003d368  mov     [rbp+30h+var_78], 0C000478Ch
0x18003d36f  mov     [rbp+30h+var_74], 0EE95C24Fh
0x18003d376  mov     [rbp+30h+var_90], 0C689AABAh
0x18003d37d  mov     [rbp+30h+var_8C], 11D08E78h
0x18003d384  mov     [rbp+30h+var_88], 0C000478Ch
0x18003d38b  mov     [rbp+30h+var_84], 0EE95C24Fh
0x18003d392  mov     [rbp+30h+pgProv.Data1], 0C689AAB9h
0x18003d399  mov     dword ptr [rbp+30h+pgProv.Data2], 11D08E78h
0x18003d3a0  mov     dword ptr [rbp+30h+pgProv.Data4], 0C000478Ch
0x18003d3a7  mov     dword ptr [rbp+30h+pgProv.Data4+4], 0EE95C24Fh
0x18003d3ae  mov     [rbp+30h+var_60], 0DE351A43h
0x18003d3b5  mov     [rbp+30h+var_5C], 11D08E59h
0x18003d3bc  mov     [rbp+30h+var_58], 0C000478Ch
0x18003d3c3  mov     [rbp+30h+var_54], 0EE95C24Fh
0x18003d3ca  mov     [rbp+30h+var_50], 9BA61D3Fh
0x18003d3d1  mov     [rbp+30h+var_4C], 11D0E73Ah
0x18003d3d8  mov     [rbp+30h+var_48], 0C000D28Ch
0x18003d3df  mov     [rbp+30h+var_44], 0EE95C24Fh
0x18003d3e6  mov     [rbp+30h+var_40.Data1], 941C2937h
0x18003d3ed  mov     dword ptr [rbp+30h+var_40.Data2], 11D11292h
0x18003d3f4  mov     dword ptr [rbp+30h+var_40.Data4], 0C000BE85h
0x18003d3fb  mov     dword ptr [rbp+30h+var_40.Data4+4], 0EE95C24Fh
0x18003d402  mov     [rbp+30h+var_A0], 18B3C141h
0x18003d409  mov     [rbp+30h+var_9C], 40F9AE0Dh
0x18003d410  mov     [rbp+30h+var_98], 42E56594h
0x18003d417  mov     [rbp+30h+var_94], 0C7ABC1AFh
0x18003d41e  call    memset_0
0x18003d423  lea     rax, aWintrustDll_0; "WINTRUST.DLL"
0x18003d42a  mov     [rsp+130h+psNewProv.cbStruct], ebx
0x18003d42e  mov     [rsp+130h+psNewProv.pwszDLLFileName], rax
0x18003d433  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d438  lea     rax, aCryptsipgetsig_0; "CryptSIPGetSignedDataMsg"
0x18003d43f  mov     [rsp+130h+psNewProv.pwszGetFuncName], rax
0x18003d444  lea     rax, aCryptsipputsig_0; "CryptSIPPutSignedDataMsg"
0x18003d44b  mov     [rsp+130h+psNewProv.pwszPutFuncName], rax
0x18003d450  lea     rax, aCryptsipcreate_0; "CryptSIPCreateIndirectData"
0x18003d457  mov     [rsp+130h+psNewProv.pwszCreateFuncName], rax
0x18003d45c  lea     rax, aCryptsipverify_0; "CryptSIPVerifyIndirectData"
0x18003d463  mov     [rsp+130h+psNewProv.pwszVerifyFuncName], rax
0x18003d468  lea     rax, aCryptsipremove_1; "CryptSIPRemoveSignedDataMsg"
0x18003d46f  mov     [rsp+130h+psNewProv.pwszRemoveFuncName], rax
0x18003d474  lea     rax, [rbp+30h+var_B0]
0x18003d478  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d47d  call    cs:__imp_CryptSIPAddProvider
0x18003d483  mov     ebx, eax
0x18003d485  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d48a  lea     rax, [rbp+30h+var_A0]
0x18003d48e  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d493  call    cs:__imp_CryptSIPAddProvider
0x18003d499  mov     edi, eax
0x18003d49b  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d4a0  lea     rax, [rbp+30h+var_90]
0x18003d4a4  and     edi, ebx
0x18003d4a6  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d4ab  lea     rax, aMscf; "MSCF"
0x18003d4b2  mov     [rsp+130h+psNewProv.pwszMagicNumber], rax
0x18003d4b7  call    cs:__imp_CryptSIPAddProvider
0x18003d4bd  mov     esi, eax
0x18003d4bf  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d4c4  lea     rax, [rbp+30h+var_80]
0x18003d4c8  and     esi, edi
0x18003d4ca  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d4cf  lea     rax, a0x00004550; "0x00004550"
0x18003d4d6  mov     [rsp+130h+psNewProv.pwszMagicNumber], rax
0x18003d4db  call    cs:__imp_CryptSIPAddProvider
0x18003d4e1  mov     ebx, eax
0x18003d4e3  lea     rcx, [rbp+30h+pgProv]; pgProv
0x18003d4e7  and     ebx, esi
0x18003d4e9  call    cs:__imp_CryptSIPRemoveProvider
0x18003d4ef  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d4f4  call    cs:__imp_CryptSIPAddProvider
0x18003d4fa  mov     edi, eax
0x18003d4fc  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d501  lea     rax, [rbp+30h+var_60]
0x18003d505  and     edi, ebx
0x18003d507  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d50c  call    cs:__imp_CryptSIPAddProvider
0x18003d512  mov     ebx, eax
0x18003d514  lea     rcx, [rsp+130h+psNewProv]; psNewProv
0x18003d519  lea     rax, [rbp+30h+var_50]
0x18003d51d  and     ebx, edi
0x18003d51f  mov     [rsp+130h+psNewProv.pgSubject], rax
0x18003d524  call    cs:__imp_CryptSIPAddProvider
0x18003d52a  mov     edi, eax
0x18003d52c  lea     rcx, [rbp+30h+var_40]; pgProv
0x18003d530  and     edi, ebx
0x18003d532  and     edi, 1
0x18003d535  call    cs:__imp_CryptSIPRemoveProvider
0x18003d53b  xor     edi, 1
0x18003d53e  mov     eax, edi
0x18003d540  mov     rcx, [rbp+30h+var_30]
0x18003d544  xor     rcx, rsp; StackCookie
0x18003d547  call    __security_check_cookie
0x18003d54c  add     rsp, 118h
0x18003d553  pop     rdi
0x18003d554  pop     rsi
0x18003d555  pop     rbx
0x18003d556  pop     rbp
0x18003d557  retn
```
