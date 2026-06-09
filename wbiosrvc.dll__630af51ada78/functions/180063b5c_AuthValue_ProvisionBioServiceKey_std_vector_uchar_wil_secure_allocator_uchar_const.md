# AuthValue::ProvisionBioServiceKey(std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x180063b5c`
- end: `0x180063c64`
- name: `?ProvisionBioServiceKey@AuthValue@@QEAAJAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800533f8`

## callees

- `0x180011d90`
- `0x180056358`
- `0x180063b5c`
- `0x180063c6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063c51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063bfe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063bfe`
- `CRYPT32!CryptProtectData` at `0x180063bae`
- `CRYPT32!CryptProtectData` at `0x180063bae`

## string_xrefs

- `0x180063bbd`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063c10`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063bf3`: `BioServiceKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthValue::ProvisionBioServiceKey(__int64 a1, __int64 a2)
{
  BYTE *v3; // r8
  const char *v4; // r9
  void *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // edi
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  DWORD cbData[4]; // [rsp+40h] [rbp-28h] BYREF
  DATA_BLOB v11; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *(BYTE **)a2;
  v11.cbData = *(_DWORD *)(a2 + 8) - *(_QWORD *)a2;
  *(&v11.cbData + 1) = 0;
  v11.pbData = v3;
  *(_OWORD *)cbData = 0;
  if ( !CryptProtectData(&v11, 0, 0, 0, 0, 1u, (DATA_BLOB *)cbData) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x206,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
             v4);
  v6 = *(void **)&cbData[2];
  v7 = RegSetValueExW(*(HKEY *)(a1 + 32), L"BioServiceKey", 0, 3u, *(const BYTE **)&cbData[2], cbData[0]);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x210,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
           (const char *)v7,
           lpData);
    if ( v6 )
      LocalFree(v6);
    return v8;
  }
  else
  {
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(a1 + 40, *(_QWORD *)&cbData[2], cbData[0]);
    if ( v6 )
      LocalFree(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180063b5c  mov     r11, rsp
0x180063b5f  mov     [r11+8], rbx
0x180063b63  push    rdi
0x180063b64  sub     rsp, 60h
0x180063b68  mov     rdi, rcx
0x180063b6b  mov     r8, [rdx]
0x180063b6e  mov     eax, [rdx+8]
0x180063b71  sub     eax, r8d
0x180063b74  mov     [rsp+68h+var_18], eax
0x180063b78  xor     eax, eax
0x180063b7a  mov     [rsp+68h+var_14], eax
0x180063b7e  mov     [r11-10h], r8
0x180063b82  xorps   xmm0, xmm0
0x180063b85  movups  xmmword ptr [rsp+68h+cbData], xmm0
0x180063b8a  lea     rax, [r11-28h]
0x180063b8e  mov     [r11-38h], rax
0x180063b92  mov     [rsp+68h+dwFlags], 1; dwFlags
0x180063b9a  mov     qword ptr [r11-48h], 0
0x180063ba2  xor     r9d, r9d; pvReserved
0x180063ba5  xor     r8d, r8d; pOptionalEntropy
0x180063ba8  xor     edx, edx; szDataDescr
0x180063baa  lea     rcx, [r11-18h]; pDataIn
0x180063bae  call    cs:__imp_CryptProtectData
0x180063bb4  test    eax, eax
0x180063bb6  jnz     short loc_180063BD3
0x180063bb8  mov     rcx, [rsp+68h]; this
0x180063bbd  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063bc4  mov     edx, 206h; void *
0x180063bc9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063bce  jmp     loc_180063C59
0x180063bd3  mov     rbx, qword ptr [rsp+68h+cbData+8]
0x180063bd8  mov     [rsp+68h+arg_8], rbx
0x180063bdd  mov     eax, [rsp+68h+cbData]
0x180063be1  mov     [rsp+68h+dwFlags], eax; cbData
0x180063be5  mov     [rsp+68h+lpData], rbx; unsigned int
0x180063bea  mov     r9d, 3; dwType
0x180063bf0  xor     r8d, r8d; Reserved
0x180063bf3  lea     rdx, aBioservicekey; "BioServiceKey"
0x180063bfa  mov     rcx, [rdi+20h]; hKey
0x180063bfe  call    cs:__imp_RegSetValueExW
0x180063c04  test    eax, eax
0x180063c06  jz      short loc_180063C35
0x180063c08  mov     rcx, [rsp+68h]; this
0x180063c0d  mov     r9d, eax; char *
0x180063c10  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063c17  mov     edx, 210h; void *
0x180063c1c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180063c21  mov     edi, eax
0x180063c23  test    rbx, rbx
0x180063c26  jz      short loc_180063C31
0x180063c28  mov     rcx, rbx; hMem
0x180063c2b  call    cs:__imp_LocalFree
0x180063c31  mov     eax, edi
0x180063c33  jmp     short loc_180063C59
0x180063c35  mov     rdx, qword ptr [rsp+68h+cbData+8]
0x180063c3a  mov     r8d, [rsp+68h+cbData]
0x180063c3f  lea     rcx, [rdi+28h]
0x180063c43  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180063c48  nop
0x180063c49  test    rbx, rbx
0x180063c4c  jz      short loc_180063C57
0x180063c4e  mov     rcx, rbx; hMem
0x180063c51  call    cs:__imp_LocalFree
0x180063c57  xor     eax, eax
0x180063c59  mov     rbx, [rsp+68h+arg_0]
0x180063c5e  add     rsp, 60h
0x180063c62  pop     rdi
0x180063c63  retn
```
