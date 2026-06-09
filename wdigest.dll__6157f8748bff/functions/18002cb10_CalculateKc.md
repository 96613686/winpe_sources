# CalculateKc

- ea: `0x18002cb10`
- end: `0x18002cd30`
- name: `CalculateKc`
- size: `544`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002eb94`
- `0x18002f43c`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x18002cb10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc92`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cbe8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cc26`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cbe8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cc26`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002cb8d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002cb8d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cca9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cced`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cca9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cced`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002cc6e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002cc6e`

## pseudocode

```c
__int64 __fastcall CalculateKc(BYTE *pbData, unsigned __int16 a2, const BYTE **a3, BYTE *a4)
{
  DWORD v4; // esi
  PVOID *v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  DWORD pdwDataLen; // [rsp+30h] [rbp-18h] BYREF
  HCRYPTHASH hHash[2]; // [rsp+38h] [rbp-10h] BYREF

  v4 = a2;
  hHash[0] = 0;
  pdwDataLen = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 301, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  *(_OWORD *)a4 = 0;
  if ( !CryptCreateHash(g_hCryptProv, 0x8003u, 0, 0, hHash) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v10 = 305;
LABEL_8:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, LastError);
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
    v11 = -1073741174;
    goto LABEL_26;
  }
  if ( !CryptHashData(hHash[0], pbData, v4, 0) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v10 = 306;
    goto LABEL_8;
  }
  if ( *(_WORD *)a3 && !CryptHashData(hHash[0], a3[1], *(unsigned __int16 *)a3, 0) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v10 = 307;
    goto LABEL_8;
  }
  pdwDataLen = 16;
  if ( !CryptGetHashParam(hHash[0], 2u, a4, &pdwDataLen, 0) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v10 = 308;
    goto LABEL_8;
  }
  v11 = 0;
  CryptDestroyHash(hHash[0]);
  hHash[0] = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, pdwDataLen);
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
    if ( hHash[0] )
    {
      CryptDestroyHash(hHash[0]);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      hHash[0] = 0;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && *((char *)v8 + 28) < 0 )
    WPP_SF_d(v8[2], 311, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002cb10  push    rbp
0x18002cb12  push    rbx
0x18002cb13  push    rsi
0x18002cb14  push    rdi
0x18002cb15  push    r12
0x18002cb17  push    r13
0x18002cb19  push    r14
0x18002cb1b  push    r15
0x18002cb1d  mov     rbp, rsp
0x18002cb20  sub     rsp, 48h
0x18002cb24  xor     r15d, r15d
0x18002cb27  movzx   esi, dx
0x18002cb2a  mov     [rbp+hHash], r15
0x18002cb2e  mov     rdi, r9
0x18002cb31  mov     [rbp+pdwDataLen], r15d
0x18002cb35  mov     rbx, r8
0x18002cb38  mov     r14, rcx
0x18002cb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb42  lea     r12, WPP_GLOBAL_Control
0x18002cb49  lea     r13, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002cb50  cmp     rcx, r12
0x18002cb53  jz      short loc_18002CB6C
0x18002cb55  test    byte ptr [rcx+1Ch], 80h
0x18002cb59  jz      short loc_18002CB6C
0x18002cb5b  mov     rcx, [rcx+10h]
0x18002cb5f  mov     edx, 12Dh
0x18002cb64  mov     r8, r13
0x18002cb67  call    WPP_SF_
0x18002cb6c  xorps   xmm0, xmm0
0x18002cb6f  lea     rax, [rbp+hHash]
0x18002cb73  movups  xmmword ptr [rdi], xmm0
0x18002cb76  mov     rcx, cs:g_hCryptProv; hProv
0x18002cb7d  xor     r9d, r9d; dwFlags
0x18002cb80  xor     r8d, r8d; hKey
0x18002cb83  mov     [rsp+48h+phHash], rax; phHash
0x18002cb88  mov     edx, 8003h; Algid
0x18002cb8d  call    cs:__imp_CryptCreateHash
0x18002cb93  test    eax, eax
0x18002cb95  jnz     short loc_18002CBDB
0x18002cb97  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb9e  cmp     rcx, r12
0x18002cba1  jz      short loc_18002CBD1
0x18002cba3  test    byte ptr [rcx+1Ch], 1
0x18002cba7  jz      short loc_18002CBD1
0x18002cba9  call    cs:__imp_GetLastError
0x18002cbaf  mov     edx, 131h
0x18002cbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbbb  mov     r9d, eax
0x18002cbbe  mov     r8, r13
0x18002cbc1  mov     rcx, [rcx+10h]
0x18002cbc5  call    WPP_SF_d
0x18002cbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbd1  mov     ebx, 0C000028Ah
0x18002cbd6  jmp     loc_18002CCE1
0x18002cbdb  mov     rcx, [rbp+hHash]; hHash
0x18002cbdf  mov     r8d, esi; dwDataLen
0x18002cbe2  xor     r9d, r9d; dwFlags
0x18002cbe5  mov     rdx, r14; pbData
0x18002cbe8  call    cs:__imp_CryptHashData
0x18002cbee  test    eax, eax
0x18002cbf0  jnz     short loc_18002CC11
0x18002cbf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbf9  cmp     rcx, r12
0x18002cbfc  jz      short loc_18002CBD1
0x18002cbfe  test    byte ptr [rcx+1Ch], 1
0x18002cc02  jz      short loc_18002CBD1
0x18002cc04  call    cs:__imp_GetLastError
0x18002cc0a  mov     edx, 132h
0x18002cc0f  jmp     short loc_18002CBB4
0x18002cc11  cmp     [rbx], r15w
0x18002cc15  jz      short loc_18002CC52
0x18002cc17  movzx   r8d, word ptr [rbx]; dwDataLen
0x18002cc1b  xor     r9d, r9d; dwFlags
0x18002cc1e  mov     rdx, [rbx+8]; pbData
0x18002cc22  mov     rcx, [rbp+hHash]; hHash
0x18002cc26  call    cs:__imp_CryptHashData
0x18002cc2c  test    eax, eax
0x18002cc2e  jnz     short loc_18002CC52
0x18002cc30  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc37  cmp     rcx, r12
0x18002cc3a  jz      short loc_18002CBD1
0x18002cc3c  test    byte ptr [rcx+1Ch], 1
0x18002cc40  jz      short loc_18002CBD1
0x18002cc42  call    cs:__imp_GetLastError
0x18002cc48  mov     edx, 133h
0x18002cc4d  jmp     loc_18002CBB4
0x18002cc52  mov     rcx, [rbp+hHash]; hHash
0x18002cc56  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002cc5a  mov     r8, rdi; pbData
0x18002cc5d  mov     [rbp+pdwDataLen], 10h
0x18002cc64  mov     edx, 2; dwParam
0x18002cc69  mov     dword ptr [rsp+48h+phHash], r15d; dwFlags
0x18002cc6e  call    cs:__imp_CryptGetHashParam
0x18002cc74  test    eax, eax
0x18002cc76  jnz     short loc_18002CCA2
0x18002cc78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc7f  cmp     rcx, r12
0x18002cc82  jz      loc_18002CBD1
0x18002cc88  test    byte ptr [rcx+1Ch], 1
0x18002cc8c  jz      loc_18002CBD1
0x18002cc92  call    cs:__imp_GetLastError
0x18002cc98  mov     edx, 134h
0x18002cc9d  jmp     loc_18002CBB4
0x18002cca2  mov     rcx, [rbp+hHash]; hHash
0x18002cca6  mov     ebx, r15d
0x18002cca9  call    cs:__imp_CryptDestroyHash
0x18002ccaf  mov     [rbp+hHash], r15
0x18002ccb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccba  cmp     rcx, r12
0x18002ccbd  jz      short loc_18002CD1D
0x18002ccbf  test    byte ptr [rcx+1Ch], 4
0x18002ccc3  jz      short loc_18002CCFE
0x18002ccc5  mov     r9d, [rbp+pdwDataLen]
0x18002ccc9  mov     edx, 135h
0x18002ccce  mov     rcx, [rcx+10h]
0x18002ccd2  mov     r8, r13
0x18002ccd5  call    WPP_SF_d
0x18002ccda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cce1  mov     rax, [rbp+hHash]
0x18002cce5  test    rax, rax
0x18002cce8  jz      short loc_18002CCFE
0x18002ccea  mov     rcx, rax; hHash
0x18002cced  call    cs:__imp_CryptDestroyHash
0x18002ccf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccfa  mov     [rbp+hHash], r15
0x18002ccfe  cmp     rcx, r12
0x18002cd01  jz      short loc_18002CD1D
0x18002cd03  test    byte ptr [rcx+1Ch], 80h
0x18002cd07  jz      short loc_18002CD1D
0x18002cd09  mov     rcx, [rcx+10h]
0x18002cd0d  mov     edx, 137h
0x18002cd12  mov     r9d, ebx
0x18002cd15  mov     r8, r13
0x18002cd18  call    WPP_SF_d
0x18002cd1d  mov     eax, ebx
0x18002cd1f  add     rsp, 48h
0x18002cd23  pop     r15
0x18002cd25  pop     r14
0x18002cd27  pop     r13
0x18002cd29  pop     r12
0x18002cd2b  pop     rdi
0x18002cd2c  pop     rsi
0x18002cd2d  pop     rbx
0x18002cd2e  pop     rbp
0x18002cd2f  retn
```
