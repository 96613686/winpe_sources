# IsPrivateKeyPresent

- ea: `0x180007408`
- end: `0x180007449`
- name: `IsPrivateKeyPresent`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003aac`
- `0x180004300`
- `0x180005370`
- `0x180005830`

## callees

- `0x180007408`

## import_xrefs

- `CRYPT32!CertGetCertificateContextProperty` at `0x180007424`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000742e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000742e`

## pseudocode

```c
bool __fastcall IsPrivateKeyPresent(const CERT_CONTEXT *a1)
{
  char v1; // bl
  DWORD pcbData; // [rsp+38h] [rbp+10h] BYREF

  pcbData = 0;
  v1 = 1;
  if ( !CertGetCertificateContextProperty(a1, 2u, 0, &pcbData) )
    return GetLastError() == 234;
  return v1;
}

```

## disassembly

```asm
0x180007408  push    rbx
0x18000740a  sub     rsp, 20h
0x18000740e  xor     r8d, r8d; pvData
0x180007411  mov     [rsp+28h+pcbData], 0
0x180007419  lea     r9, [rsp+28h+pcbData]; pcbData
0x18000741e  mov     bl, 1
0x180007420  lea     edx, [r8+2]; dwPropId
0x180007424  call    cs:__imp_CertGetCertificateContextProperty
0x18000742a  test    eax, eax
0x18000742c  jnz     short loc_180007441
0x18000742e  call    cs:__imp_GetLastError
0x180007434  xor     ecx, ecx
0x180007436  movzx   ebx, bl
0x180007439  cmp     eax, 0EAh
0x18000743e  cmovnz  ebx, ecx
0x180007441  mov     al, bl
0x180007443  add     rsp, 20h
0x180007447  pop     rbx
0x180007448  retn
```
