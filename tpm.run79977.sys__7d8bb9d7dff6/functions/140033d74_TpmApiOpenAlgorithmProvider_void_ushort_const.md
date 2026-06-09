# TpmApiOpenAlgorithmProvider(void * *,ushort const *)

- ea: `0x140033d74`
- end: `0x140033e12`
- name: `?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z`
- size: `158`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140034148`

## callees

- `0x140032c88`
- `0x140033ce4`
- `0x140033d74`
- `0x140033e18`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x140033db5`
- `cng!BCryptOpenAlgorithmProvider` at `0x140033de8`
- `cng!BCryptOpenAlgorithmProvider` at `0x140033db5`
- `cng!BCryptOpenAlgorithmProvider` at `0x140033de8`

## pseudocode

```c
__int64 __fastcall TpmApiOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *phAlgorithm, const unsigned __int16 *a2)
{
  NTSTATUS v3; // edi
  unsigned int v5; // [rsp+38h] [rbp+10h] BYREF
  int v6; // [rsp+3Ch] [rbp+14h]
  LPCWSTR pszImplementation; // [rsp+40h] [rbp+18h] BYREF

  v6 = HIDWORD(a2);
  pszImplementation = 0;
  v5 = 0;
  TpmApiRegistryGetAlgorithmProvider((unsigned __int16 **)&pszImplementation, &v5);
  v3 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA1", pszImplementation, 0);
  if ( v3 < 0 && pszImplementation && TpmApiDefaultToExistingProviders() )
    v3 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA1", 0, 0);
  TpmApiCallbackFree(0, 0, pszImplementation);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140033d74  mov     rax, rsp
0x140033d77  mov     [rax+8], rsi
0x140033d7b  mov     [rax+10h], rdx
0x140033d7f  push    rdi
0x140033d80  sub     rsp, 20h
0x140033d84  mov     rsi, rcx
0x140033d87  mov     qword ptr [rax+18h], 0
0x140033d8f  lea     rcx, [rax+18h]; unsigned __int16 **
0x140033d93  mov     dword ptr [rax+10h], 0
0x140033d9a  lea     rdx, [rax+10h]; unsigned int *
0x140033d9e  call    ?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z; TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)
0x140033da3  mov     r8, [rsp+28h+pszImplementation]; pszImplementation
0x140033da8  lea     rdx, aSha1; "SHA1"
0x140033daf  xor     r9d, r9d; dwFlags
0x140033db2  mov     rcx, rsi; phAlgorithm
0x140033db5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140033dbc  nop     dword ptr [rax+rax+00h]
0x140033dc1  mov     edi, eax
0x140033dc3  test    eax, eax
0x140033dc5  jns     short loc_140033DF6
0x140033dc7  cmp     [rsp+28h+pszImplementation], 0
0x140033dcd  jz      short loc_140033DF6
0x140033dcf  call    ?TpmApiDefaultToExistingProviders@@YAEXZ; TpmApiDefaultToExistingProviders(void)
0x140033dd4  test    al, al
0x140033dd6  jz      short loc_140033DF6
0x140033dd8  xor     r9d, r9d; dwFlags
0x140033ddb  lea     rdx, aSha1; "SHA1"
0x140033de2  xor     r8d, r8d; pszImplementation
0x140033de5  mov     rcx, rsi; phAlgorithm
0x140033de8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140033def  nop     dword ptr [rax+rax+00h]
0x140033df4  mov     edi, eax
0x140033df6  mov     r8, [rsp+28h+pszImplementation]
0x140033dfb  xor     edx, edx
0x140033dfd  xor     ecx, ecx
0x140033dff  call    TpmApiCallbackFree
0x140033e04  mov     rsi, [rsp+28h+arg_0]
0x140033e09  mov     eax, edi
0x140033e0b  add     rsp, 20h
0x140033e0f  pop     rdi
0x140033e10  retn
```
