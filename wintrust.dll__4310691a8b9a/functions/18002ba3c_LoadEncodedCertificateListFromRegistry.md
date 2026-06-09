# LoadEncodedCertificateListFromRegistry

- ea: `0x18002ba3c`
- end: `0x18002bb9a`
- name: `LoadEncodedCertificateListFromRegistry`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041fe0`

## callees

- `0x18002ba3c`
- `0x18002bba0`
- `0x18002c090`
- `0x18002c34c`
- `0x18002c394`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ba8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bb1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ba8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bb1f`

## string_xrefs

- `0x18002bacc`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002bb69`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002ba60`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x18002bb08`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
int __fastcall LoadEncodedCertificateListFromRegistry(void *a1, __int64 a2)
{
  unsigned int ValueW; // eax
  unsigned int v3; // r8d
  PVOID v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  int v8; // edi
  int AuthrootCTL; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PVOID hMem; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbCtlEncoded; // [rsp+58h] [rbp+10h] BYREF
  int v15; // [rsp+5Ch] [rbp+14h]

  v15 = HIDWORD(a2);
  hMem = a1;
  cbCtlEncoded = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
             L"EncodedCtl",
             8u,
             0,
             0,
             &cbCtlEncoded);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x3A1, v3, (const char *)ValueW, pdwType);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, cbCtlEncoded);
  v5 = hMem;
  if ( !hMem )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A5,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    return -2147024882;
  }
  v6 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
         L"EncodedCtl",
         8u,
         0,
         hMem,
         &cbCtlEncoded);
  if ( v6 )
  {
    v8 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x3AE, v7, (const char *)v6, pdwTypea);
LABEL_7:
    if ( v5 )
      LocalFree(v5);
    return v8;
  }
  AuthrootCTL = LoadAuthrootCTL((BYTE *)v5, cbCtlEncoded);
  v8 = AuthrootCTL;
  if ( AuthrootCTL < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)(unsigned int)AuthrootCTL,
      pdwTypea);
    goto LABEL_7;
  }
  if ( v5 )
    LocalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x18002ba3c  mov     r11, rsp
0x18002ba3f  mov     [r11+18h], rbx
0x18002ba43  mov     [r11+10h], rdx
0x18002ba47  mov     [r11+8], rcx
0x18002ba4b  push    rdi
0x18002ba4c  sub     rsp, 40h
0x18002ba50  lea     rax, [r11+10h]
0x18002ba54  mov     [rsp+48h+cbCtlEncoded], 0
0x18002ba5c  mov     [r11-18h], rax
0x18002ba60  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\SystemCertificates"...
0x18002ba67  mov     rdi, r8
0x18002ba6a  mov     qword ptr [r11-20h], 0
0x18002ba72  mov     r9d, 8; dwFlags
0x18002ba78  mov     qword ptr [r11-28h], 0
0x18002ba80  lea     r8, aEncodedctl; "EncodedCtl"
0x18002ba87  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002ba8e  call    cs:__imp_RegGetValueW
0x18002ba94  test    eax, eax
0x18002ba96  jz      short loc_18002BAAF
0x18002ba98  mov     rcx, [rsp+48h]; this
0x18002ba9d  mov     r9d, eax; char *
0x18002baa0  mov     edx, 3A1h; void *
0x18002baa5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002baaa  jmp     loc_18002BB8F
0x18002baaf  mov     edx, [rsp+48h+cbCtlEncoded]
0x18002bab3  lea     rcx, [rsp+48h+hMem]
0x18002bab8  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002babd  mov     rbx, [rsp+48h+hMem]
0x18002bac2  test    rbx, rbx
0x18002bac5  jnz     short loc_18002BAEC
0x18002bac7  mov     rcx, [rsp+48h]; this
0x18002bacc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bad3  mov     ebx, 8007000Eh
0x18002bad8  mov     edx, 3A5h; void *
0x18002badd  mov     r9d, ebx; char *
0x18002bae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bae5  mov     eax, ebx
0x18002bae7  jmp     loc_18002BB8F
0x18002baec  lea     rax, [rsp+48h+cbCtlEncoded]
0x18002baf1  mov     r9d, 8; dwFlags
0x18002baf7  mov     [rsp+48h+pcbData], rax; pcbData
0x18002bafc  lea     r8, aEncodedctl; "EncodedCtl"
0x18002bb03  mov     [rsp+48h+pvData], rbx; pvData
0x18002bb08  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\SystemCertificates"...
0x18002bb0f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002bb16  mov     [rsp+48h+pdwType], 0; int
0x18002bb1f  call    cs:__imp_RegGetValueW
0x18002bb25  test    eax, eax
0x18002bb27  jz      short loc_18002BB4F
0x18002bb29  mov     rcx, [rsp+48h]; this
0x18002bb2e  mov     r9d, eax; char *
0x18002bb31  mov     edx, 3AEh; void *
0x18002bb36  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bb3b  mov     edi, eax
0x18002bb3d  test    rbx, rbx
0x18002bb40  jz      short loc_18002BB4B
0x18002bb42  mov     rcx, rbx; hMem
0x18002bb45  call    cs:__imp_LocalFree
0x18002bb4b  mov     eax, edi
0x18002bb4d  jmp     short loc_18002BB8F
0x18002bb4f  mov     edx, [rsp+48h+cbCtlEncoded]; cbCtlEncoded
0x18002bb53  mov     r8, rdi
0x18002bb56  mov     rcx, rbx; pbCtlEncoded
0x18002bb59  call    LoadAuthrootCTL
0x18002bb5e  mov     edi, eax
0x18002bb60  test    eax, eax
0x18002bb62  jns     short loc_18002BB7F
0x18002bb64  mov     rcx, [rsp+48h]; this
0x18002bb69  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002bb70  mov     r9d, eax; char *
0x18002bb73  mov     edx, 3B2h; void *
0x18002bb78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb7d  jmp     short loc_18002BB3D
0x18002bb7f  test    rbx, rbx
0x18002bb82  jz      short loc_18002BB8D
0x18002bb84  mov     rcx, rbx; hMem
0x18002bb87  call    cs:__imp_LocalFree
0x18002bb8d  xor     eax, eax
0x18002bb8f  mov     rbx, [rsp+48h+arg_10]
0x18002bb94  add     rsp, 40h
0x18002bb98  pop     rdi
0x18002bb99  retn
```
