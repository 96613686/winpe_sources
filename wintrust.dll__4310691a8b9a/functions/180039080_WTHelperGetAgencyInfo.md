# WTHelperGetAgencyInfo

- ea: `0x180039080`
- end: `0x180039162`
- name: `WTHelperGetAgencyInfo`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180039080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003914a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003914a`
- `CRYPT32!CertFindExtension` at `0x1800390c5`
- `CRYPT32!CertFindExtension` at `0x1800390c5`
- `CRYPT32!CryptDecodeObject` at `0x1800390fb`
- `CRYPT32!CryptDecodeObject` at `0x180039134`
- `CRYPT32!CryptDecodeObject` at `0x1800390fb`
- `CRYPT32!CryptDecodeObject` at `0x180039134`

## pseudocode

```c
_BOOL8 __fastcall WTHelperGetAgencyInfo(__int64 a1, DWORD *a2, void *a3)
{
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v6; // rdi
  DWORD v7; // ecx

  if ( a1 && a2 )
  {
    *a2 = 0;
    Extension = CertFindExtension(
                  "1.3.6.1.4.1.311.2.1.10",
                  *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                  *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
    v6 = Extension;
    if ( !Extension )
      return 0;
    CryptDecodeObject(1u, (LPCSTR)0x7D0, Extension->Value.pbData, Extension->Value.cbData, 0, 0, a2);
    if ( !*a2 )
      return 0;
    if ( a3 )
      return CryptDecodeObject(1u, (LPCSTR)0x7D0, v6->Value.pbData, v6->Value.cbData, 0, a3, a2);
    v7 = 122;
  }
  else
  {
    v7 = 87;
  }
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x180039080  mov     [rsp+arg_0], rbx
0x180039085  mov     [rsp+arg_8], rsi
0x18003908a  push    rdi
0x18003908b  sub     rsp, 40h
0x18003908f  mov     rsi, r8
0x180039092  mov     rbx, rdx
0x180039095  test    rcx, rcx
0x180039098  jz      loc_180039145
0x18003909e  test    rdx, rdx
0x1800390a1  jz      loc_180039145
0x1800390a7  mov     dword ptr [rdx], 0
0x1800390ad  mov     rdx, [rcx+18h]
0x1800390b1  lea     rcx, a1361413112110; "1.3.6.1.4.1.311.2.1.10"
0x1800390b8  mov     r8, [rdx+0C8h]; rgExtensions
0x1800390bf  mov     edx, [rdx+0C0h]; cExtensions
0x1800390c5  call    cs:__imp_CertFindExtension
0x1800390cb  mov     rdi, rax
0x1800390ce  test    rax, rax
0x1800390d1  jz      short loc_180039150
0x1800390d3  mov     r9d, [rax+10h]; cbEncoded
0x1800390d7  mov     edx, 7D0h; lpszStructType
0x1800390dc  mov     r8, [rax+18h]; pbEncoded
0x1800390e0  mov     ecx, 1; dwCertEncodingType
0x1800390e5  mov     [rsp+48h+pcbStructInfo], rbx; pcbStructInfo
0x1800390ea  mov     [rsp+48h+pvStructInfo], 0; pvStructInfo
0x1800390f3  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800390fb  call    cs:__imp_CryptDecodeObject
0x180039101  cmp     dword ptr [rbx], 0
0x180039104  jz      short loc_180039150
0x180039106  test    rsi, rsi
0x180039109  jnz     short loc_180039110
0x18003910b  lea     ecx, [rsi+7Ah]
0x18003910e  jmp     short loc_18003914A
0x180039110  mov     r9d, [rdi+10h]; cbEncoded
0x180039114  mov     edx, 7D0h; lpszStructType
0x180039119  mov     r8, [rdi+18h]; pbEncoded
0x18003911d  mov     ecx, 1; dwCertEncodingType
0x180039122  mov     [rsp+48h+pcbStructInfo], rbx; pcbStructInfo
0x180039127  mov     [rsp+48h+pvStructInfo], rsi; pvStructInfo
0x18003912c  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180039134  call    cs:__imp_CryptDecodeObject
0x18003913a  xor     ecx, ecx
0x18003913c  test    eax, eax
0x18003913e  setnz   cl
0x180039141  mov     eax, ecx
0x180039143  jmp     short loc_180039152
0x180039145  mov     ecx, 57h ; 'W'; dwErrCode
0x18003914a  call    cs:__imp_SetLastError
0x180039150  xor     eax, eax
0x180039152  mov     rbx, [rsp+48h+arg_0]
0x180039157  mov     rsi, [rsp+48h+arg_8]
0x18003915c  add     rsp, 40h
0x180039160  pop     rdi
0x180039161  retn
```
