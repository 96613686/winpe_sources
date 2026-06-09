# CreateSymmetricKey

- ea: `0x18002d938`
- end: `0x18002db22`
- name: `CreateSymmetricKey`
- size: `490`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002cd38`
- `0x18002d340`
- `0x18002eb94`
- `0x18002f43c`

## callees

- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x18002d938`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002db12`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetKeyParam` at `0x18002daee`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetKeyParam` at `0x18002daee`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x18002da24`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x18002da24`

## pseudocode

```c
__int64 __fastcall CreateSymmetricKey(int a1, unsigned int a2, const void *a3, const BYTE *a4, HCRYPTKEY *phKey)
{
  size_t v7; // rbx
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  DWORD LastError; // eax
  __int64 v12; // rdx
  BYTE pbData[32]; // [rsp+30h] [rbp-68h] BYREF

  v7 = a2;
  memset(pbData, 0, 28);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (unsigned int)v7 > 0x10 )
  {
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_9;
    WPP_SF_(v9[2], 233, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
LABEL_8:
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
    v10 = -1073741595;
    goto LABEL_21;
  }
  *(_DWORD *)pbData = 520;
  *(_DWORD *)&pbData[4] = a1;
  memcpy_0(&pbData[12], a3, v7);
  *(_DWORD *)&pbData[8] = v7;
  if ( !CryptImportKey(g_hCryptProv, pbData, 0x1Cu, 0, 0, phKey) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v12 = 235;
    goto LABEL_14;
  }
  v10 = 0;
  if ( ((a1 - 26113) & 0xFFFFFFF7) != 0 )
  {
LABEL_20:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  if ( a4 )
  {
    if ( !CryptSetKeyParam(*phKey, 1u, a4, 0) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      LastError = GetLastError();
      v12 = 238;
LABEL_14:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, LastError);
      goto LABEL_8;
    }
    goto LABEL_20;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
    goto LABEL_20;
  }
LABEL_21:
  if ( v9 != &WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 )
    WPP_SF_d(v9[2], 239, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002d938  push    rbx
0x18002d93a  push    rbp
0x18002d93b  push    rsi
0x18002d93c  push    rdi
0x18002d93d  push    r12
0x18002d93f  push    r14
0x18002d941  push    r15
0x18002d943  sub     rsp, 60h
0x18002d947  mov     rax, cs:__security_cookie
0x18002d94e  xor     rax, rsp
0x18002d951  mov     [rsp+98h+var_48], rax
0x18002d956  mov     r14, [rsp+98h+arg_20]
0x18002d95e  xorps   xmm0, xmm0
0x18002d961  movups  xmmword ptr [rsp+98h+pbData+1], xmm0
0x18002d966  mov     rdi, r9
0x18002d969  mov     rbp, r8
0x18002d96c  movups  xmmword ptr [rsp+98h+var_5C], xmm0
0x18002d971  mov     ebx, edx
0x18002d973  mov     esi, ecx
0x18002d975  mov     [rsp+98h+pbData], 0
0x18002d97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d981  lea     r15, WPP_GLOBAL_Control
0x18002d988  lea     r12, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18002d98f  cmp     rcx, r15
0x18002d992  jz      short loc_18002D9B2
0x18002d994  test    byte ptr [rcx+1Ch], 80h
0x18002d998  jz      short loc_18002D9B2
0x18002d99a  mov     rcx, [rcx+10h]
0x18002d99e  mov     edx, 0E8h
0x18002d9a3  mov     r8, r12
0x18002d9a6  call    WPP_SF_
0x18002d9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9b2  cmp     ebx, 10h
0x18002d9b5  jbe     short loc_18002D9E4
0x18002d9b7  cmp     rcx, r15
0x18002d9ba  jz      short loc_18002D9DA
0x18002d9bc  test    byte ptr [rcx+1Ch], 1
0x18002d9c0  jz      short loc_18002D9DA
0x18002d9c2  mov     rcx, [rcx+10h]
0x18002d9c6  mov     edx, 0E9h
0x18002d9cb  mov     r8, r12
0x18002d9ce  call    WPP_SF_
0x18002d9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9da  mov     ebx, 0C00000E5h
0x18002d9df  jmp     loc_18002DAA4
0x18002d9e4  mov     r8, rbx; Size
0x18002d9e7  mov     dword ptr [rsp+98h+pbData], 208h
0x18002d9ef  mov     rdx, rbp; Src
0x18002d9f2  mov     [rsp+98h+var_64], esi
0x18002d9f6  lea     rcx, [rsp+98h+var_5C]; void *
0x18002d9fb  call    memcpy_0
0x18002da00  mov     rcx, cs:g_hCryptProv; hProv
0x18002da07  lea     rdx, [rsp+98h+pbData]; pbData
0x18002da0c  xor     r9d, r9d; hPubKey
0x18002da0f  mov     [rsp+98h+phKey], r14; phKey
0x18002da14  mov     [rsp+98h+var_60], ebx
0x18002da18  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18002da20  lea     r8d, [r9+1Ch]; dwDataLen
0x18002da24  call    cs:__imp_CryptImportKey
0x18002da2a  test    eax, eax
0x18002da2c  jnz     short loc_18002DA66
0x18002da2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da35  cmp     rcx, r15
0x18002da38  jz      short loc_18002D9DA
0x18002da3a  test    byte ptr [rcx+1Ch], 1
0x18002da3e  jz      short loc_18002D9DA
0x18002da40  call    cs:__imp_GetLastError
0x18002da46  mov     edx, 0EBh
0x18002da4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da52  mov     r9d, eax
0x18002da55  mov     r8, r12
0x18002da58  mov     rcx, [rcx+10h]
0x18002da5c  call    WPP_SF_d
0x18002da61  jmp     loc_18002D9D3
0x18002da66  xor     ebx, ebx
0x18002da68  lea     eax, [rsi-6601h]
0x18002da6e  test    eax, 0FFFFFFF7h
0x18002da73  jnz     short loc_18002DA9D
0x18002da75  test    rdi, rdi
0x18002da78  jnz     short loc_18002DAE1
0x18002da7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da81  cmp     rcx, r15
0x18002da84  jz      short loc_18002DAC3
0x18002da86  test    byte ptr [rcx+1Ch], 2
0x18002da8a  jz      short loc_18002DAA4
0x18002da8c  mov     rcx, [rcx+10h]
0x18002da90  mov     edx, 0ECh
0x18002da95  mov     r8, r12
0x18002da98  call    WPP_SF_
0x18002da9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daa4  cmp     rcx, r15
0x18002daa7  jz      short loc_18002DAC3
0x18002daa9  test    byte ptr [rcx+1Ch], 80h
0x18002daad  jz      short loc_18002DAC3
0x18002daaf  mov     rcx, [rcx+10h]
0x18002dab3  mov     edx, 0EFh
0x18002dab8  mov     r9d, ebx
0x18002dabb  mov     r8, r12
0x18002dabe  call    WPP_SF_d
0x18002dac3  mov     eax, ebx
0x18002dac5  mov     rcx, [rsp+98h+var_48]
0x18002daca  xor     rcx, rsp; StackCookie
0x18002dacd  call    __security_check_cookie
0x18002dad2  add     rsp, 60h
0x18002dad6  pop     r15
0x18002dad8  pop     r14
0x18002dada  pop     r12
0x18002dadc  pop     rdi
0x18002dadd  pop     rsi
0x18002dade  pop     rbp
0x18002dadf  pop     rbx
0x18002dae0  retn
0x18002dae1  mov     rcx, [r14]; hKey
0x18002dae4  xor     r9d, r9d; dwFlags
0x18002dae7  mov     r8, rdi; pbData
0x18002daea  lea     edx, [r9+1]; dwParam
0x18002daee  call    cs:__imp_CryptSetKeyParam
0x18002daf4  test    eax, eax
0x18002daf6  jnz     short loc_18002DA9D
0x18002daf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daff  cmp     rcx, r15
0x18002db02  jz      loc_18002D9DA
0x18002db08  test    byte ptr [rcx+1Ch], 1
0x18002db0c  jz      loc_18002D9DA
0x18002db12  call    cs:__imp_GetLastError
0x18002db18  mov     edx, 0EEh
0x18002db1d  jmp     loc_18002DA4B
```
