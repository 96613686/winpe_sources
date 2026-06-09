# TsCryptCertContainsEnhancedKeyUsage

- ea: `0x180088ae0`
- end: `0x180088be4`
- name: `TsCryptCertContainsEnhancedKeyUsage`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180088e00`

## callees

- `0x180088954`
- `0x180088a28`
- `0x180088ae0`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x180088b34`
- `CRYPT32!CertFindExtension` at `0x180088b34`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180088ba4`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180088ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088bc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088bc9`

## pseudocode

```c
__int64 __fastcall TsCryptCertContainsEnhancedKeyUsage(
        _DWORD *a1,
        const CERT_CONTEXT *a2,
        __int64 a3,
        __int64 a4,
        DWORD pcbUsage)
{
  HLOCAL v5; // rbx
  unsigned int v9; // edi
  PCERT_EXTENSION Extension; // rax
  const char *v11; // rdx
  int v12; // eax
  unsigned int v14; // [rsp+20h] [rbp-38h]
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  hMem = 0;
  v16 = 0;
  *a1 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v9 = 0;
  Extension = CertFindExtension("2.5.29.37", a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
  if ( a3 )
  {
    if ( !Extension )
      return v9;
    v12 = TsCryptDecodeObject(
            a2->dwCertEncodingType,
            v11,
            Extension->Value.pbData,
            Extension->Value.cbData,
            v14,
            &hMem,
            &v16);
    v5 = hMem;
    v9 = v12;
    if ( v12 >= 0 )
    {
      if ( !hMem )
        return v9;
      *a1 = TsCryptEnhancedKeyUsageContainsIds(hMem, a3);
    }
  }
  else
  {
    pcbUsage = 0;
    if ( CertGetEnhancedKeyUsage(a2, 2u, 0, &pcbUsage) || GetLastError() != -2146885628 )
      return v9;
    *a1 = 1;
  }
  if ( v5 )
    LocalFree(v5);
  return v9;
}

```

## disassembly

```asm
0x180088ae0  mov     rax, rsp
0x180088ae3  mov     [rax+10h], rbx
0x180088ae7  mov     [rax+18h], rbp
0x180088aeb  mov     [rax+20h], r9d
0x180088aef  push    rsi
0x180088af0  push    rdi
0x180088af1  push    r14
0x180088af3  sub     rsp, 40h
0x180088af7  xor     ebx, ebx
0x180088af9  mov     rbp, r8
0x180088afc  mov     [rax+8], rbx
0x180088b00  mov     r14, rdx
0x180088b03  mov     [rax+20h], ebx
0x180088b06  mov     rsi, rcx
0x180088b09  mov     [rcx], ebx
0x180088b0b  test    rdx, rdx
0x180088b0e  jnz     short loc_180088B1A
0x180088b10  mov     edi, 80070057h
0x180088b15  jmp     loc_180088BCF
0x180088b1a  mov     rdx, [rdx+18h]
0x180088b1e  lea     rcx, pszObjId; "2.5.29.37"
0x180088b25  xor     edi, edi
0x180088b27  mov     r8, [rdx+0C8h]; rgExtensions
0x180088b2e  mov     edx, [rdx+0C0h]; cExtensions
0x180088b34  call    cs:__imp_CertFindExtension
0x180088b3a  test    rbp, rbp
0x180088b3d  jz      short loc_180088B8B
0x180088b3f  test    rax, rax
0x180088b42  jz      loc_180088BCF
0x180088b48  mov     r9d, [rax+10h]; unsigned int
0x180088b4c  lea     rcx, [rsp+58h+arg_18]
0x180088b51  mov     r8, [rax+18h]; unsigned __int8 *
0x180088b55  mov     [rsp+58h+var_28], rcx; unsigned int *
0x180088b5a  lea     rcx, [rsp+58h+hMem]
0x180088b5f  mov     [rsp+58h+var_30], rcx; void **
0x180088b64  mov     ecx, [r14]; dwCertEncodingType
0x180088b67  call    ?TsCryptDecodeObject@@YAJKPEBDPEBEKKPEAPEAXPEAK@Z; TsCryptDecodeObject(ulong,char const *,uchar const *,ulong,ulong,void * *,ulong *)
0x180088b6c  mov     rbx, [rsp+58h+hMem]
0x180088b71  mov     edi, eax
0x180088b73  test    eax, eax
0x180088b75  js      short loc_180088BC1
0x180088b77  test    rbx, rbx
0x180088b7a  jz      short loc_180088BCF
0x180088b7c  mov     rdx, rbp
0x180088b7f  mov     rcx, rbx
0x180088b82  call    ?TsCryptEnhancedKeyUsageContainsIds@@YAHPEAU_CTL_USAGE@@PEAPEBDKW4EKUSearchOption@@@Z; TsCryptEnhancedKeyUsageContainsIds(_CTL_USAGE *,char const * *,ulong,EKUSearchOption)
0x180088b87  mov     [rsi], eax
0x180088b89  jmp     short loc_180088BC1
0x180088b8b  xor     r8d, r8d; pUsage
0x180088b8e  mov     [rsp+58h+pcbUsage], ebx
0x180088b95  lea     r9, [rsp+58h+pcbUsage]; pcbUsage
0x180088b9d  mov     rcx, r14; pCertContext
0x180088ba0  lea     edx, [r8+2]; dwFlags
0x180088ba4  call    cs:__imp_CertGetEnhancedKeyUsage
0x180088baa  test    eax, eax
0x180088bac  jnz     short loc_180088BCF
0x180088bae  call    cs:__imp_GetLastError
0x180088bb4  cmp     eax, 80092004h
0x180088bb9  jnz     short loc_180088BCF
0x180088bbb  mov     dword ptr [rsi], 1
0x180088bc1  test    rbx, rbx
0x180088bc4  jz      short loc_180088BCF
0x180088bc6  mov     rcx, rbx; hMem
0x180088bc9  call    cs:__imp_LocalFree
0x180088bcf  mov     rbx, [rsp+58h+arg_8]
0x180088bd4  mov     eax, edi
0x180088bd6  mov     rbp, [rsp+58h+arg_10]
0x180088bdb  add     rsp, 40h
0x180088bdf  pop     r14
0x180088be1  pop     rdi
0x180088be2  pop     rsi
0x180088be3  retn
```
