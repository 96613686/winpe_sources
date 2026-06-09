# md5_ulong(uchar *,ulong)

- ea: `0x18002d1c4`
- end: `0x18002d33f`
- name: `?md5_ulong@@YAKPEAEK@Z`
- size: `379`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027a3c`
- `0x180028c3c`
- `0x180028cd4`

## callees

- `0x180004c4c`
- `0x18002d198`
- `0x18002d1c4`
- `0x18002d80e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2f9`
- `CRYPTSP!CryptCreateHash` at `0x18002d231`
- `CRYPTSP!CryptCreateHash` at `0x18002d231`
- `CRYPTSP!CryptReleaseContext` at `0x18002d29a`
- `CRYPTSP!CryptReleaseContext` at `0x18002d321`
- `CRYPTSP!CryptReleaseContext` at `0x18002d29a`
- `CRYPTSP!CryptReleaseContext` at `0x18002d321`
- `CRYPTSP!CryptGetHashParam` at `0x18002d25c`
- `CRYPTSP!CryptGetHashParam` at `0x18002d2e5`
- `CRYPTSP!CryptGetHashParam` at `0x18002d25c`
- `CRYPTSP!CryptGetHashParam` at `0x18002d2e5`
- `CRYPTSP!CryptDestroyHash` at `0x18002d285`
- `CRYPTSP!CryptDestroyHash` at `0x18002d308`
- `CRYPTSP!CryptDestroyHash` at `0x18002d285`
- `CRYPTSP!CryptDestroyHash` at `0x18002d308`
- `CRYPTSP!CryptAcquireContextW` at `0x18002d20a`
- `CRYPTSP!CryptAcquireContextW` at `0x18002d20a`

## pseudocode

```c
__int64 __fastcall md5_ulong(unsigned __int8 *a1, unsigned int a2)
{
  BYTE *v4; // rax
  BYTE *v5; // rbx
  unsigned int v7; // r9d
  unsigned int v8; // edi
  HCRYPTHASH phHash; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-8h] BYREF
  DWORD pbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD pdwDataLen; // [rsp+78h] [rbp+38h] BYREF

  pbData = 0;
  phProv = 0;
  phHash = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000040) )
    ATL::AtlHresultFromLastError();
  if ( !CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
    ATL::AtlHresultFromLastError();
  pdwDataLen = 4;
  if ( !CryptGetHashParam(phHash, 4u, (BYTE *)&pbData, &pdwDataLen, 0) )
    ATL::AtlHresultFromLastError();
  v4 = (BYTE *)CoTaskMemAlloc(pbData);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, pbData);
    ATL::CCryptHash::AddData((ATL::CCryptHash *)&phHash, a1, a2, v7);
    if ( !CryptGetHashParam(phHash, 2u, v5, &pbData, 0) )
      ATL::AtlHresultFromLastError();
    v8 = *(_DWORD *)v5;
    CoTaskMemFree(v5);
    if ( phHash )
    {
      CryptDestroyHash(phHash);
      phHash = 0;
    }
    if ( phProv && !CryptReleaseContext(phProv, 0) )
      ATL::AtlHresultFromLastError();
    return v8;
  }
  else
  {
    if ( phHash )
    {
      CryptDestroyHash(phHash);
      phHash = 0;
    }
    if ( phProv )
    {
      if ( !CryptReleaseContext(phProv, 0) )
        ATL::AtlHresultFromLastError();
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002d1c4  mov     [rsp-18h+arg_0], rbx
0x18002d1c9  push    rbp
0x18002d1ca  push    rsi
0x18002d1cb  push    rdi
0x18002d1cc  mov     rbp, rsp
0x18002d1cf  sub     rsp, 40h
0x18002d1d3  mov     edi, edx
0x18002d1d5  mov     [rbp+pbData], 0
0x18002d1dc  mov     rsi, rcx
0x18002d1df  mov     [rbp+phProv], 0
0x18002d1e7  xor     edx, edx; szContainer
0x18002d1e9  mov     [rbp+phHash], 0
0x18002d1f1  lea     rcx, [rbp+phProv]; phProv
0x18002d1f5  mov     [rsp+40h+dwFlags], 0F0000040h; dwFlags
0x18002d1fd  mov     r9d, 1; dwProvType
0x18002d203  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18002d20a  call    cs:__imp_CryptAcquireContextW
0x18002d210  test    eax, eax
0x18002d212  jnz     short loc_18002D219
0x18002d214  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d219  mov     rcx, [rbp+phProv]; hProv
0x18002d21d  lea     rax, [rbp+phHash]
0x18002d221  xor     r9d, r9d; dwFlags
0x18002d224  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x18002d229  xor     r8d, r8d; hKey
0x18002d22c  mov     edx, 8004h; Algid
0x18002d231  call    cs:__imp_CryptCreateHash
0x18002d237  test    eax, eax
0x18002d239  jnz     short loc_18002D240
0x18002d23b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d240  mov     rcx, [rbp+phHash]; hHash
0x18002d244  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002d248  mov     edx, 4; dwParam
0x18002d24d  mov     [rsp+40h+dwFlags], 0; dwFlags
0x18002d255  lea     r8, [rbp+pbData]; pbData
0x18002d259  mov     [rbp+pdwDataLen], edx
0x18002d25c  call    cs:__imp_CryptGetHashParam
0x18002d262  test    eax, eax
0x18002d264  jnz     short loc_18002D26B
0x18002d266  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d26b  mov     ecx, [rbp+pbData]; cb
0x18002d26e  call    cs:__imp_CoTaskMemAlloc
0x18002d274  mov     rbx, rax
0x18002d277  test    rax, rax
0x18002d27a  jnz     short loc_18002D2B0
0x18002d27c  mov     rcx, [rbp+phHash]; hHash
0x18002d280  test    rcx, rcx
0x18002d283  jz      short loc_18002D28F
0x18002d285  call    cs:__imp_CryptDestroyHash
0x18002d28b  mov     [rbp+phHash], rbx
0x18002d28f  mov     rcx, [rbp+phProv]; hProv
0x18002d293  test    rcx, rcx
0x18002d296  jz      short loc_18002D2A9
0x18002d298  xor     edx, edx; dwFlags
0x18002d29a  call    cs:__imp_CryptReleaseContext
0x18002d2a0  test    eax, eax
0x18002d2a2  jnz     short loc_18002D2A9
0x18002d2a4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d2a9  xor     eax, eax
0x18002d2ab  jmp     loc_18002D332
0x18002d2b0  mov     r8d, [rbp+pbData]; Size
0x18002d2b4  xor     edx, edx; Val
0x18002d2b6  mov     rcx, rbx; void *
0x18002d2b9  call    memset_0
0x18002d2be  mov     r8d, edi; unsigned int
0x18002d2c1  lea     rcx, [rbp+phHash]; this
0x18002d2c5  mov     rdx, rsi; unsigned __int8 *
0x18002d2c8  call    ?AddData@CCryptHash@ATL@@QEAAJPEBEKK@Z; ATL::CCryptHash::AddData(uchar const *,ulong,ulong)
0x18002d2cd  mov     rcx, [rbp+phHash]; hHash
0x18002d2d1  lea     r9, [rbp+pbData]; pdwDataLen
0x18002d2d5  mov     r8, rbx; pbData
0x18002d2d8  mov     [rsp+40h+dwFlags], 0; dwFlags
0x18002d2e0  mov     edx, 2; dwParam
0x18002d2e5  call    cs:__imp_CryptGetHashParam
0x18002d2eb  test    eax, eax
0x18002d2ed  jnz     short loc_18002D2F4
0x18002d2ef  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d2f4  mov     edi, [rbx]
0x18002d2f6  mov     rcx, rbx; pv
0x18002d2f9  call    cs:__imp_CoTaskMemFree
0x18002d2ff  mov     rcx, [rbp+phHash]; hHash
0x18002d303  test    rcx, rcx
0x18002d306  jz      short loc_18002D316
0x18002d308  call    cs:__imp_CryptDestroyHash
0x18002d30e  mov     [rbp+phHash], 0
0x18002d316  mov     rcx, [rbp+phProv]; hProv
0x18002d31a  test    rcx, rcx
0x18002d31d  jz      short loc_18002D330
0x18002d31f  xor     edx, edx; dwFlags
0x18002d321  call    cs:__imp_CryptReleaseContext
0x18002d327  test    eax, eax
0x18002d329  jnz     short loc_18002D330
0x18002d32b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002d330  mov     eax, edi
0x18002d332  mov     rbx, [rsp+40h+arg_0]
0x18002d337  add     rsp, 40h
0x18002d33b  pop     rdi
0x18002d33c  pop     rsi
0x18002d33d  pop     rbp
0x18002d33e  retn
```
