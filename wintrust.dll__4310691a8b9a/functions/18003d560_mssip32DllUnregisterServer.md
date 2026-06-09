# mssip32DllUnregisterServer

- ea: `0x18003d560`
- end: `0x18003d6c3`
- name: `mssip32DllUnregisterServer`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180035930`

## callees

- `0x18004deb0`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d660`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d66a`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d674`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d67e`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d688`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d692`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d69c`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d6a6`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d660`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d66a`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d674`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d67e`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d688`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d692`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d69c`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18003d6a6`

## pseudocode

```c
__int64 mssip32DllUnregisterServer()
{
  GUID pgProv; // [rsp+20h] [rbp-39h] BYREF
  GUID v2; // [rsp+30h] [rbp-29h] BYREF
  GUID v3; // [rsp+40h] [rbp-19h] BYREF
  GUID v4; // [rsp+50h] [rbp-9h] BYREF
  GUID v5; // [rsp+60h] [rbp+7h] BYREF
  GUID v6; // [rsp+70h] [rbp+17h] BYREF
  GUID v7; // [rsp+80h] [rbp+27h] BYREF
  GUID v8; // [rsp+90h] [rbp+37h] BYREF

  pgProv.Data1 = -566945214;
  *(_DWORD *)&pgProv.Data2 = 298880601;
  *(_DWORD *)pgProv.Data4 = -1073723508;
  *(_DWORD *)&pgProv.Data4[4] = -292175281;
  v2.Data1 = -964056392;
  *(_DWORD *)&v2.Data2 = 298880632;
  *(_DWORD *)v2.Data4 = -1073723508;
  *(_DWORD *)&v2.Data4[4] = -292175281;
  v3.Data1 = -964056390;
  *(_DWORD *)&v3.Data2 = 298880632;
  *(_DWORD *)v3.Data4 = -1073723508;
  *(_DWORD *)&v3.Data4[4] = -292175281;
  v4.Data1 = -964056391;
  *(_DWORD *)&v4.Data2 = 298880632;
  *(_DWORD *)v4.Data4 = -1073723508;
  *(_DWORD *)&v4.Data4[4] = -292175281;
  v5.Data1 = -566945213;
  *(_DWORD *)&v5.Data2 = 298880601;
  *(_DWORD *)v5.Data4 = -1073723508;
  *(_DWORD *)&v5.Data4[4] = -292175281;
  v6.Data1 = -1683612353;
  *(_DWORD *)&v6.Data2 = 298903354;
  *(_DWORD *)v6.Data4 = -1073687924;
  *(_DWORD *)&v6.Data4[4] = -292175281;
  v7.Data1 = -1810093769;
  *(_DWORD *)&v7.Data2 = 298914450;
  *(_DWORD *)v7.Data4 = -1073693051;
  *(_DWORD *)&v7.Data4[4] = -292175281;
  v8.Data1 = 414433601;
  *(_DWORD *)&v8.Data2 = 1090104845;
  *(_DWORD *)v8.Data4 = 1122330004;
  *(_DWORD *)&v8.Data4[4] = -945045073;
  CryptSIPRemoveProvider(&pgProv);
  CryptSIPRemoveProvider(&v2);
  CryptSIPRemoveProvider(&v3);
  CryptSIPRemoveProvider(&v4);
  CryptSIPRemoveProvider(&v5);
  CryptSIPRemoveProvider(&v6);
  CryptSIPRemoveProvider(&v7);
  CryptSIPRemoveProvider(&v8);
  return 0;
}

```

## disassembly

```asm
0x18003d560  push    rbp
0x18003d562  lea     rbp, [rsp-57h]
0x18003d567  sub     rsp, 0B0h
0x18003d56e  mov     rax, cs:__security_cookie
0x18003d575  xor     rax, rsp
0x18003d578  mov     [rbp+57h+var_10], rax
0x18003d57c  lea     rcx, [rbp+57h+pgProv]; pgProv
0x18003d580  mov     [rbp+57h+pgProv.Data1], 0DE351A42h
0x18003d587  mov     dword ptr [rbp+57h+pgProv.Data2], 11D08E59h
0x18003d58e  mov     dword ptr [rbp+57h+pgProv.Data4], 0C000478Ch
0x18003d595  mov     dword ptr [rbp+57h+pgProv.Data4+4], 0EE95C24Fh
0x18003d59c  mov     [rbp+57h+var_80.Data1], 0C689AAB8h
0x18003d5a3  mov     dword ptr [rbp+57h+var_80.Data2], 11D08E78h
0x18003d5aa  mov     dword ptr [rbp+57h+var_80.Data4], 0C000478Ch
0x18003d5b1  mov     dword ptr [rbp+57h+var_80.Data4+4], 0EE95C24Fh
0x18003d5b8  mov     [rbp+57h+var_70.Data1], 0C689AABAh
0x18003d5bf  mov     dword ptr [rbp+57h+var_70.Data2], 11D08E78h
0x18003d5c6  mov     dword ptr [rbp+57h+var_70.Data4], 0C000478Ch
0x18003d5cd  mov     dword ptr [rbp+57h+var_70.Data4+4], 0EE95C24Fh
0x18003d5d4  mov     [rbp+57h+var_60.Data1], 0C689AAB9h
0x18003d5db  mov     dword ptr [rbp+57h+var_60.Data2], 11D08E78h
0x18003d5e2  mov     dword ptr [rbp+57h+var_60.Data4], 0C000478Ch
0x18003d5e9  mov     dword ptr [rbp+57h+var_60.Data4+4], 0EE95C24Fh
0x18003d5f0  mov     [rbp+57h+var_50.Data1], 0DE351A43h
0x18003d5f7  mov     dword ptr [rbp+57h+var_50.Data2], 11D08E59h
0x18003d5fe  mov     dword ptr [rbp+57h+var_50.Data4], 0C000478Ch
0x18003d605  mov     dword ptr [rbp+57h+var_50.Data4+4], 0EE95C24Fh
0x18003d60c  mov     [rbp+57h+var_40.Data1], 9BA61D3Fh
0x18003d613  mov     dword ptr [rbp+57h+var_40.Data2], 11D0E73Ah
0x18003d61a  mov     dword ptr [rbp+57h+var_40.Data4], 0C000D28Ch
0x18003d621  mov     dword ptr [rbp+57h+var_40.Data4+4], 0EE95C24Fh
0x18003d628  mov     [rbp+57h+var_30.Data1], 941C2937h
0x18003d62f  mov     dword ptr [rbp+57h+var_30.Data2], 11D11292h
0x18003d636  mov     dword ptr [rbp+57h+var_30.Data4], 0C000BE85h
0x18003d63d  mov     dword ptr [rbp+57h+var_30.Data4+4], 0EE95C24Fh
0x18003d644  mov     [rbp+57h+var_20.Data1], 18B3C141h
0x18003d64b  mov     dword ptr [rbp+57h+var_20.Data2], 40F9AE0Dh
0x18003d652  mov     dword ptr [rbp+57h+var_20.Data4], 42E56594h
0x18003d659  mov     dword ptr [rbp+57h+var_20.Data4+4], 0C7ABC1AFh
0x18003d660  call    cs:__imp_CryptSIPRemoveProvider
0x18003d666  lea     rcx, [rbp+57h+var_80]; pgProv
0x18003d66a  call    cs:__imp_CryptSIPRemoveProvider
0x18003d670  lea     rcx, [rbp+57h+var_70]; pgProv
0x18003d674  call    cs:__imp_CryptSIPRemoveProvider
0x18003d67a  lea     rcx, [rbp+57h+var_60]; pgProv
0x18003d67e  call    cs:__imp_CryptSIPRemoveProvider
0x18003d684  lea     rcx, [rbp+57h+var_50]; pgProv
0x18003d688  call    cs:__imp_CryptSIPRemoveProvider
0x18003d68e  lea     rcx, [rbp+57h+var_40]; pgProv
0x18003d692  call    cs:__imp_CryptSIPRemoveProvider
0x18003d698  lea     rcx, [rbp+57h+var_30]; pgProv
0x18003d69c  call    cs:__imp_CryptSIPRemoveProvider
0x18003d6a2  lea     rcx, [rbp+57h+var_20]; pgProv
0x18003d6a6  call    cs:__imp_CryptSIPRemoveProvider
0x18003d6ac  xor     eax, eax
0x18003d6ae  mov     rcx, [rbp+57h+var_10]
0x18003d6b2  xor     rcx, rsp; StackCookie
0x18003d6b5  call    __security_check_cookie
0x18003d6ba  add     rsp, 0B0h
0x18003d6c1  pop     rbp
0x18003d6c2  retn
```
