# ASNRegisterServer(ushort const *)

- ea: `0x180035998`
- end: `0x180035a43`
- name: `?ASNRegisterServer@@YAJPEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035970`

## callees

- `0x180035998`
- `0x180035afc`

## import_xrefs

- `CRYPT32!CryptRegisterOIDFunction` at `0x1800359de`
- `CRYPT32!CryptRegisterOIDFunction` at `0x180035a28`
- `CRYPT32!CryptRegisterOIDFunction` at `0x1800359de`
- `CRYPT32!CryptRegisterOIDFunction` at `0x180035a28`

## string_xrefs

- `0x1800359b3`: `WINTRUST.DLL`
- `0x1800359fd`: `WINTRUST.DLL`
- `0x1800359bd`: `CryptDllEncodeObject`
- `0x180035a07`: `CryptDllDecodeObject`

## pseudocode

```c
__int64 __fastcall ASNRegisterServer(const unsigned __int16 *a1)
{
  unsigned int i; // ebx
  unsigned int j; // ebx

  for ( i = 0; i < 0x22; ++i )
  {
    if ( !CryptRegisterOIDFunction(
            1u,
            "CryptDllEncodeObject",
            off_180052CC0[2 * (int)i],
            L"WINTRUST.DLL",
            (&off_180052CC8)[2 * (int)i]) )
      return HError();
  }
  for ( j = 0; j < 0x22; ++j )
  {
    if ( !CryptRegisterOIDFunction(
            1u,
            "CryptDllDecodeObject",
            off_180052A90[2 * (int)j],
            L"WINTRUST.DLL",
            (&off_180052A98)[2 * (int)j]) )
      return HError();
  }
  return 0;
}

```

## disassembly

```asm
0x180035998  mov     [rsp+arg_0], rbx
0x18003599d  push    rsi
0x18003599e  sub     rsp, 30h
0x1800359a2  xor     ebx, ebx
0x1800359a4  lea     rsi, __ImageBase
0x1800359ab  cmp     ebx, 22h ; '"'
0x1800359ae  jnb     short loc_1800359F3
0x1800359b0  movsxd  r8, ebx
0x1800359b3  lea     r9, aWintrustDll_0; "WINTRUST.DLL"
0x1800359ba  add     r8, r8
0x1800359bd  lea     rdx, pszFuncName; "CryptDllEncodeObject"
0x1800359c4  mov     ecx, 1; dwEncodingType
0x1800359c9  mov     rax, ds:rva off_180052CC8[rsi+r8*8]; "WVTAsn1SpcPeImageDataEncode" ...
0x1800359d1  mov     r8, ds:rva off_180052CC0[rsi+r8*8]; pszOID
0x1800359d9  mov     [rsp+38h+pszOverrideFuncName], rax; pszOverrideFuncName
0x1800359de  call    cs:__imp_CryptRegisterOIDFunction
0x1800359e4  test    eax, eax
0x1800359e6  jz      short loc_1800359EC
0x1800359e8  inc     ebx
0x1800359ea  jmp     short loc_1800359AB
0x1800359ec  call    ?HError@@YAJXZ; HError(void)
0x1800359f1  jmp     short loc_180035A38
0x1800359f3  xor     ebx, ebx
0x1800359f5  cmp     ebx, 22h ; '"'
0x1800359f8  jnb     short loc_180035A36
0x1800359fa  movsxd  r8, ebx
0x1800359fd  lea     r9, aWintrustDll_0; "WINTRUST.DLL"
0x180035a04  add     r8, r8
0x180035a07  lea     rdx, aCryptdlldecode; "CryptDllDecodeObject"
0x180035a0e  mov     ecx, 1; dwEncodingType
0x180035a13  mov     rax, ds:rva off_180052A98[rsi+r8*8]; "WVTAsn1SpcPeImageDataDecode" ...
0x180035a1b  mov     r8, ds:rva off_180052A90[rsi+r8*8]; pszOID
0x180035a23  mov     [rsp+38h+pszOverrideFuncName], rax; pszOverrideFuncName
0x180035a28  call    cs:__imp_CryptRegisterOIDFunction
0x180035a2e  test    eax, eax
0x180035a30  jz      short loc_1800359EC
0x180035a32  inc     ebx
0x180035a34  jmp     short loc_1800359F5
0x180035a36  xor     eax, eax
0x180035a38  mov     rbx, [rsp+38h+arg_0]
0x180035a3d  add     rsp, 30h
0x180035a41  pop     rsi
0x180035a42  retn
```
