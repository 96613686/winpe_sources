# ClearCertHash

- ea: `0x180002474`
- end: `0x180002511`
- name: `ClearCertHash`
- size: `157`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e70`

## callees

- `0x180002474`
- `0x18000a014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024c8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024c8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800024d8`

## string_xrefs

- `0x1800024ce`: `isHashConfiguredByAdmin`

## pseudocode

```c
__int64 __fastcall ClearCertHash(HKEY hKey)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52);
  RegDeleteValueW(hKey, L"SHA256CertificateHash");
  RegDeleteValueW(hKey, L"SHA1CertificateHash");
  RegDeleteValueW(hKey, L"isHashConfiguredByAdmin");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53);
  return 0;
}

```

## disassembly

```asm
0x180002474  mov     [rsp+arg_0], rbx
0x180002479  push    rsi
0x18000247a  sub     rsp, 20h
0x18000247e  mov     rbx, rcx
0x180002481  mov     rcx, cs:WPP_GLOBAL_Control
0x180002488  lea     rsi, WPP_GLOBAL_Control
0x18000248f  cmp     rcx, rsi
0x180002492  jz      short loc_1800024AE
0x180002494  mov     eax, [rcx+1Ch]
0x180002497  and     eax, 0C0h
0x18000249c  cmp     al, 0C0h
0x18000249e  jnz     short loc_1800024AE
0x1800024a0  mov     rcx, [rcx+10h]
0x1800024a4  mov     edx, 34h ; '4'
0x1800024a9  call    WPP_SF_
0x1800024ae  lea     rdx, aSha256certific; "SHA256CertificateHash"
0x1800024b5  mov     rcx, rbx; hKey
0x1800024b8  call    cs:__imp_RegDeleteValueW
0x1800024be  lea     rdx, aSha1certificat; "SHA1CertificateHash"
0x1800024c5  mov     rcx, rbx; hKey
0x1800024c8  call    cs:__imp_RegDeleteValueW
0x1800024ce  lea     rdx, aIshashconfigur; "isHashConfiguredByAdmin"
0x1800024d5  mov     rcx, rbx; hKey
0x1800024d8  call    cs:__imp_RegDeleteValueW
0x1800024de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024e5  cmp     rcx, rsi
0x1800024e8  jz      short loc_180002504
0x1800024ea  mov     eax, [rcx+1Ch]
0x1800024ed  and     eax, 0C0h
0x1800024f2  cmp     al, 0C0h
0x1800024f4  jnz     short loc_180002504
0x1800024f6  mov     rcx, [rcx+10h]
0x1800024fa  mov     edx, 35h ; '5'
0x1800024ff  call    WPP_SF_
0x180002504  mov     rbx, [rsp+28h+arg_0]
0x180002509  xor     eax, eax
0x18000250b  add     rsp, 20h
0x18000250f  pop     rsi
0x180002510  retn
```
