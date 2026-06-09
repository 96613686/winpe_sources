# GetCertName

- ea: `0x180024b6c`
- end: `0x180024c0b`
- name: `GetCertName`
- size: `159`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, DWORD dwFlags, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002498c`

## callees

- `0x180024b6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bf8`
- `ntdll!RtlCreateUnicodeString` at `0x180024bef`
- `ntdll!RtlCreateUnicodeString` at `0x180024bef`
- `CRYPT32!CertGetNameStringW` at `0x180024b9f`
- `CRYPT32!CertGetNameStringW` at `0x180024be3`
- `CRYPT32!CertGetNameStringW` at `0x180024b9f`
- `CRYPT32!CertGetNameStringW` at `0x180024be3`

## pseudocode

```c
__int64 __fastcall GetCertName(PCCERT_CONTEXT pCertContext, DWORD dwFlags, PUNICODE_STRING DestinationString)
{
  DWORD cchNameString; // r14d
  WCHAR *pszNameString; // rax
  WCHAR *v8; // rbx

  cchNameString = (unsigned __int16)CertGetNameStringW(pCertContext, 3u, dwFlags, (void *)"2.5.4.3", 0, 0);
  pszNameString = (WCHAR *)LocalAlloc(0x40u, 2 * cchNameString);
  v8 = pszNameString;
  if ( !pszNameString )
    return 2147942414LL;
  CertGetNameStringW(pCertContext, 3u, dwFlags, (void *)"2.5.4.3", pszNameString, cchNameString);
  RtlCreateUnicodeString(DestinationString, v8);
  LocalFree(v8);
  return 0;
}

```

## disassembly

```asm
0x180024b6c  push    rbx
0x180024b6e  push    rbp
0x180024b6f  push    rsi
0x180024b70  push    rdi
0x180024b71  push    r14
0x180024b73  sub     rsp, 30h
0x180024b77  mov     rbp, r8
0x180024b7a  mov     [rsp+58h+cchNameString], 0; cchNameString
0x180024b82  mov     r8d, edx; dwFlags
0x180024b85  mov     [rsp+58h+pszNameString], 0; pszNameString
0x180024b8e  mov     edi, edx
0x180024b90  lea     r9, pvTypePara; "2.5.4.3"
0x180024b97  mov     edx, 3; dwType
0x180024b9c  mov     rsi, rcx
0x180024b9f  call    cs:__imp_CertGetNameStringW
0x180024ba5  movzx   r14d, ax
0x180024ba9  mov     ecx, 40h ; '@'; uFlags
0x180024bae  lea     edx, [r14+r14]; uBytes
0x180024bb2  call    cs:__imp_LocalAlloc
0x180024bb8  mov     rbx, rax
0x180024bbb  test    rax, rax
0x180024bbe  jnz     short loc_180024BC7
0x180024bc0  mov     eax, 8007000Eh
0x180024bc5  jmp     short loc_180024C00
0x180024bc7  mov     [rsp+58h+cchNameString], r14d; cchNameString
0x180024bcc  lea     r9, pvTypePara; "2.5.4.3"
0x180024bd3  mov     r8d, edi; dwFlags
0x180024bd6  mov     [rsp+58h+pszNameString], rbx; pszNameString
0x180024bdb  mov     edx, 3; dwType
0x180024be0  mov     rcx, rsi; pCertContext
0x180024be3  call    cs:__imp_CertGetNameStringW
0x180024be9  mov     rdx, rbx; SourceString
0x180024bec  mov     rcx, rbp; DestinationString
0x180024bef  call    cs:__imp_RtlCreateUnicodeString
0x180024bf5  mov     rcx, rbx; hMem
0x180024bf8  call    cs:__imp_LocalFree
0x180024bfe  xor     eax, eax
0x180024c00  add     rsp, 30h
0x180024c04  pop     r14
0x180024c06  pop     rdi
0x180024c07  pop     rsi
0x180024c08  pop     rbp
0x180024c09  pop     rbx
0x180024c0a  retn
```
