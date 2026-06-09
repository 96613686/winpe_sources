# DTLSCookieManager::init(ushort const *)

- ea: `0x180075cf0`
- end: `0x180075dc2`
- name: `?init@DTLSCookieManager@@QEAAJPEBG@Z`
- size: `210`
- prototype: `__int64 __fastcall(DTLSCookieManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180075c30`

## callees

- `0x18000fee0`
- `0x180021eb0`
- `0x180075cf0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180075d74`
- `bcrypt!BCryptGetProperty` at `0x180075d9f`
- `bcrypt!BCryptGetProperty` at `0x180075d74`
- `bcrypt!BCryptGetProperty` at `0x180075d9f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180075d45`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180075d45`

## pseudocode

```c
NTSTATUS __fastcall DTLSCookieManager::init(DTLSCookieManager *this, const unsigned __int16 *a2)
{
  UCHAR *v3; // rax
  NTSTATUS result; // eax
  BCRYPT_HANDLE *v5; // rdi

  v3 = (UCHAR *)SPExternalAlloc(*(unsigned int *)this);
  *((_QWORD *)this + 1) = v3;
  if ( !v3 )
    return -1073741670;
  result = GenerateRandomBits(v3, *(_DWORD *)this);
  if ( result >= 0 )
  {
    v5 = (BCRYPT_HANDLE *)((char *)this + 24);
    result = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 3, L"SHA256", 0, 8u);
    if ( result >= 0 )
    {
      result = BCryptGetProperty(*v5, L"HashDigestLength", (PUCHAR)this + 32, 4u, (ULONG *)this + 9, 0);
      if ( result >= 0 )
      {
        result = BCryptGetProperty(*v5, L"ObjectLength", (PUCHAR)this + 40, 4u, (ULONG *)this + 9, 0);
        if ( result >= 0 )
        {
          *((_DWORD *)this + 4) = 1;
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180075cf0  mov     [rsp+arg_0], rbx
0x180075cf5  mov     [rsp+arg_8], rsi
0x180075cfa  push    rdi
0x180075cfb  sub     rsp, 30h
0x180075cff  mov     rbx, rcx
0x180075d02  mov     ecx, [rcx]; uBytes
0x180075d04  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180075d09  mov     [rbx+8], rax
0x180075d0d  test    rax, rax
0x180075d10  jnz     short loc_180075D1C
0x180075d12  mov     eax, 0C000009Ah
0x180075d17  jmp     loc_180075DB2
0x180075d1c  mov     edx, [rbx]; cbBuffer
0x180075d1e  mov     rcx, rax; pbBuffer
0x180075d21  call    ?GenerateRandomBits@@YAKPEAEK@Z; GenerateRandomBits(uchar *,ulong)
0x180075d26  test    eax, eax
0x180075d28  js      loc_180075DB2
0x180075d2e  lea     rdi, [rbx+18h]
0x180075d32  mov     r9d, 8; dwFlags
0x180075d38  mov     rcx, rdi; phAlgorithm
0x180075d3b  lea     rdx, aSha256_0; "SHA256"
0x180075d42  xor     r8d, r8d; pszImplementation
0x180075d45  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075d4b  test    eax, eax
0x180075d4d  js      short loc_180075DB2
0x180075d4f  mov     rcx, [rdi]; hObject
0x180075d52  lea     rsi, [rbx+24h]
0x180075d56  lea     r8, [rbx+20h]; pbOutput
0x180075d5a  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180075d62  mov     r9d, 4; cbOutput
0x180075d68  mov     [rsp+38h+pcbResult], rsi; pcbResult
0x180075d6d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180075d74  call    cs:__imp_BCryptGetProperty
0x180075d7a  test    eax, eax
0x180075d7c  js      short loc_180075DB2
0x180075d7e  mov     rcx, [rdi]; hObject
0x180075d81  lea     r8, [rbx+28h]; pbOutput
0x180075d85  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180075d8d  lea     rdx, pszProperty; "ObjectLength"
0x180075d94  mov     r9d, 4; cbOutput
0x180075d9a  mov     [rsp+38h+pcbResult], rsi; pcbResult
0x180075d9f  call    cs:__imp_BCryptGetProperty
0x180075da5  test    eax, eax
0x180075da7  js      short loc_180075DB2
0x180075da9  mov     dword ptr [rbx+10h], 1
0x180075db0  xor     eax, eax
0x180075db2  mov     rbx, [rsp+38h+arg_0]
0x180075db7  mov     rsi, [rsp+38h+arg_8]
0x180075dbc  add     rsp, 30h
0x180075dc0  pop     rdi
0x180075dc1  retn
```
