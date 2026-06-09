# MatchAgainstAltNames(_CERT_CONTEXT const *,ushort const *,int *)

- ea: `0x18003e2a8`
- end: `0x18003e3e4`
- name: `?MatchAgainstAltNames@@YAJPEBU_CERT_CONTEXT@@PEBGPEAH@Z`
- size: `316`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003e87c`

## callees

- `0x18003e2a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e3a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003e3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e3c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e3c9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003e368`
- `CRYPT32!CryptDecodeObjectEx` at `0x18003e368`
- `CRYPT32!CertFindExtension` at `0x18003e306`
- `CRYPT32!CertFindExtension` at `0x18003e325`
- `CRYPT32!CertFindExtension` at `0x18003e306`
- `CRYPT32!CertFindExtension` at `0x18003e325`

## pseudocode

```c
__int64 __fastcall MatchAgainstAltNames(const struct _CERT_CONTEXT *a1, const unsigned __int16 *a2, int *a3)
{
  PCERT_INFO pCertInfo; // rdi
  unsigned int v7; // ebx
  PCERT_EXTENSION Extension; // rax
  signed int LastError; // eax
  int v10; // esi
  __int64 v11; // rdi
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  pCertInfo = a1->pCertInfo;
  hMem = 0;
  pcbStructInfo = 0;
  *a3 = 0;
  if ( pCertInfo )
  {
    v7 = -2147024894;
    Extension = CertFindExtension("2.5.29.17", pCertInfo->cExtension, pCertInfo->rgExtension);
    if ( Extension || (Extension = CertFindExtension("2.5.29.7", pCertInfo->cExtension, pCertInfo->rgExtension)) != 0 )
    {
      if ( CryptDecodeObjectEx(
             a1->dwCertEncodingType,
             (LPCSTR)0xC,
             Extension->Value.pbData,
             Extension->Value.cbData,
             0x8005u,
             0,
             &hMem,
             &pcbStructInfo) )
      {
        v10 = *(_DWORD *)hMem;
        v11 = *((_QWORD *)hMem + 1);
        while ( v10 )
        {
          if ( *(_DWORD *)v11 == 3 )
          {
            v7 = 0;
            if ( !(unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v11 + 8)) )
            {
              *a3 = 1;
              break;
            }
          }
          --v10;
          v11 += 24;
        }
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x18003e2a8  mov     rax, rsp
0x18003e2ab  mov     [rax+10h], rbx
0x18003e2af  mov     [rax+20h], rbp
0x18003e2b3  push    rsi
0x18003e2b4  push    rdi
0x18003e2b5  push    r14
0x18003e2b7  sub     rsp, 40h
0x18003e2bb  mov     rdi, [rcx+18h]
0x18003e2bf  mov     r14, r8
0x18003e2c2  mov     qword ptr [rax+18h], 0
0x18003e2ca  mov     rbp, rdx
0x18003e2cd  mov     dword ptr [rax+8], 0
0x18003e2d4  mov     rsi, rcx
0x18003e2d7  mov     dword ptr [r8], 0
0x18003e2de  test    rdi, rdi
0x18003e2e1  jnz     short loc_18003E2ED
0x18003e2e3  mov     ebx, 80070057h
0x18003e2e8  jmp     loc_18003E3CF
0x18003e2ed  mov     r8, [rdi+0C8h]; rgExtensions
0x18003e2f4  lea     rcx, pszObjId; "2.5.29.17"
0x18003e2fb  mov     edx, [rdi+0C0h]; cExtensions
0x18003e301  mov     ebx, 80070002h
0x18003e306  call    cs:__imp_CertFindExtension
0x18003e30c  test    rax, rax
0x18003e30f  jnz     short loc_18003E334
0x18003e311  mov     r8, [rdi+0C8h]; rgExtensions
0x18003e318  lea     rcx, a25297; "2.5.29.7"
0x18003e31f  mov     edx, [rdi+0C0h]; cExtensions
0x18003e325  call    cs:__imp_CertFindExtension
0x18003e32b  test    rax, rax
0x18003e32e  jz      loc_18003E3BF
0x18003e334  mov     r9d, [rax+10h]; cbEncoded
0x18003e338  lea     rcx, [rsp+58h+arg_0]
0x18003e33d  mov     r8, [rax+18h]; pbEncoded
0x18003e341  mov     edx, 0Ch; lpszStructType
0x18003e346  mov     [rsp+58h+pcbStructInfo], rcx; pcbStructInfo
0x18003e34b  lea     rcx, [rsp+58h+hMem]
0x18003e350  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x18003e355  mov     ecx, [rsi]; dwCertEncodingType
0x18003e357  mov     [rsp+58h+pDecodePara], 0; pDecodePara
0x18003e360  mov     [rsp+58h+dwFlags], 8005h; dwFlags
0x18003e368  call    cs:__imp_CryptDecodeObjectEx
0x18003e36e  test    eax, eax
0x18003e370  jnz     short loc_18003E389
0x18003e372  call    cs:__imp_GetLastError
0x18003e378  mov     ebx, eax
0x18003e37a  test    eax, eax
0x18003e37c  jle     short loc_18003E3BF
0x18003e37e  movzx   ebx, ax
0x18003e381  or      ebx, 80070000h
0x18003e387  jmp     short loc_18003E3BF
0x18003e389  mov     rax, [rsp+58h+hMem]
0x18003e38e  mov     esi, [rax]
0x18003e390  mov     rdi, [rax+8]
0x18003e394  test    esi, esi
0x18003e396  jz      short loc_18003E3BF
0x18003e398  cmp     dword ptr [rdi], 3
0x18003e39b  jnz     short loc_18003E3B0
0x18003e39d  mov     rdx, [rdi+8]
0x18003e3a1  mov     rcx, rbp
0x18003e3a4  xor     ebx, ebx
0x18003e3a6  call    cs:__imp__o__wcsicmp
0x18003e3ac  test    eax, eax
0x18003e3ae  jz      short loc_18003E3B8
0x18003e3b0  dec     esi
0x18003e3b2  add     rdi, 18h
0x18003e3b6  jmp     short loc_18003E394
0x18003e3b8  mov     dword ptr [r14], 1
0x18003e3bf  mov     rcx, [rsp+58h+hMem]; hMem
0x18003e3c4  test    rcx, rcx
0x18003e3c7  jz      short loc_18003E3CF
0x18003e3c9  call    cs:__imp_LocalFree
0x18003e3cf  mov     rbp, [rsp+58h+arg_18]
0x18003e3d4  mov     eax, ebx
0x18003e3d6  mov     rbx, [rsp+58h+arg_8]
0x18003e3db  add     rsp, 40h
0x18003e3df  pop     r14
0x18003e3e1  pop     rdi
0x18003e3e2  pop     rsi
0x18003e3e3  retn
```
