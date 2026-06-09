# _IsCaCertificate

- ea: `0x180045390`
- end: `0x180045420`
- name: `_IsCaCertificate`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180019888`

## callees

- `0x180045390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004540d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004540d`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800453f9`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800453f9`
- `CRYPT32!CertFindExtension` at `0x1800453b7`
- `CRYPT32!CertFindExtension` at `0x1800453b7`

## pseudocode

```c
__int64 __fastcall IsCaCertificate(__int64 a1)
{
  unsigned int v2; // ebx
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  DWORD v6; // ecx
  DWORD pcbStructInfo; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  Extension = CertFindExtension(
                "2.5.29.19",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( Extension )
  {
    cbData = Extension->Value.cbData;
    pbData = Extension->Value.pbData;
    v6 = *(_DWORD *)a1;
    hMem = 0;
    pcbStructInfo = 0;
    if ( CryptDecodeObjectEx(v6, (LPCSTR)0xF, pbData, cbData, 0x8005u, 0, &hMem, &pcbStructInfo) )
    {
      LOBYTE(v2) = *(_DWORD *)hMem != 0;
      LocalFree(hMem);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180045390  mov     [rsp+arg_10], rbx
0x180045395  push    rdi
0x180045396  sub     rsp, 40h
0x18004539a  mov     rdx, [rcx+18h]
0x18004539e  mov     rdi, rcx
0x1800453a1  lea     rcx, a252919; "2.5.29.19"
0x1800453a8  xor     ebx, ebx
0x1800453aa  mov     r8, [rdx+0C8h]; rgExtensions
0x1800453b1  mov     edx, [rdx+0C0h]; cExtensions
0x1800453b7  call    cs:__imp_CertFindExtension
0x1800453bd  test    rax, rax
0x1800453c0  jz      short loc_180045413
0x1800453c2  mov     r9d, [rax+10h]; cbEncoded
0x1800453c6  lea     rcx, [rsp+48h+arg_0]
0x1800453cb  mov     r8, [rax+18h]; pbEncoded
0x1800453cf  lea     edx, [rbx+0Fh]; lpszStructType
0x1800453d2  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x1800453d7  lea     rcx, [rsp+48h+hMem]
0x1800453dc  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x1800453e1  mov     ecx, [rdi]; dwCertEncodingType
0x1800453e3  mov     [rsp+48h+pDecodePara], rbx; pDecodePara
0x1800453e8  mov     [rsp+48h+dwFlags], 8005h; dwFlags
0x1800453f0  mov     [rsp+48h+hMem], rbx
0x1800453f5  mov     [rsp+48h+arg_0], ebx
0x1800453f9  call    cs:__imp_CryptDecodeObjectEx
0x1800453ff  test    eax, eax
0x180045401  jz      short loc_180045413
0x180045403  mov     rcx, [rsp+48h+hMem]; hMem
0x180045408  cmp     [rcx], ebx
0x18004540a  setnz   bl
0x18004540d  call    cs:__imp_LocalFree
0x180045413  mov     eax, ebx
0x180045415  mov     rbx, [rsp+48h+arg_10]
0x18004541a  add     rsp, 40h
0x18004541e  pop     rdi
0x18004541f  retn
```
