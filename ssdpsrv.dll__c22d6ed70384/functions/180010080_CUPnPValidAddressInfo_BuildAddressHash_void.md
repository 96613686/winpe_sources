# CUPnPValidAddressInfo::BuildAddressHash(void)

- ea: `0x180010080`
- end: `0x1800104cb`
- name: `?BuildAddressHash@CUPnPValidAddressInfo@@AEAAJXZ`
- size: `1099`
- prototype: `__int64 __fastcall(CUPnPValidAddressInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eec0`

## callees

- `0x180010080`
- `0x180010654`
- `0x1800255a8`
- `0x180026a30`
- `0x18002dcf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010405`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800104b3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800104b3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800102f6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800102f6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800104c0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800104c0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001010d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001010d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800100e7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800100e7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010154`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010154`

## pseudocode

```c
__int64 __fastcall CUPnPValidAddressInfo::BuildAddressHash(CUPnPValidAddressInfo *this)
{
  unsigned int v2; // esi
  unsigned int v3; // ebx
  _QWORD **v5; // rdi
  _QWORD *i; // rbx
  bool v7; // zf
  const BYTE *v8; // rdx
  DWORD v9; // r8d
  signed int LastError; // eax
  LPCSTR v11; // rcx
  __int64 v12; // rdx
  signed int v13; // eax
  signed int v14; // eax
  LPCSTR v15; // rcx
  __int64 v16; // rdx
  signed int v17; // eax
  char *v18; // [rsp+A8h] [rbp-80h] BYREF
  HCRYPTHASH phHash; // [rsp+B0h] [rbp-78h] BYREF
  DWORD pdwDataLen; // [rsp+B8h] [rbp-70h] BYREF
  HCRYPTPROV phProv; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD v22[3]; // [rsp+C8h] [rbp-60h]
  BYTE v23[16]; // [rsp+E0h] [rbp-48h] BYREF
  BYTE pbData[16]; // [rsp+F0h] [rbp-38h] BYREF

  v22[0] = (char *)this + 24;
  v22[1] = (char *)this + 40;
  v22[2] = (char *)this + 56;
  phProv = 0;
  phHash = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( !v3 )
      goto LABEL_10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_10;
    v12 = 43;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v3);
    goto LABEL_10;
  }
  if ( !CryptCreateHash(phProv, 0x8003u, 0, 0, &phHash) )
  {
    v13 = GetLastError();
    v3 = v13;
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    if ( !v3 )
      goto LABEL_10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_10;
    v12 = 44;
    goto LABEL_35;
  }
  v2 = 0;
LABEL_4:
  if ( v2 < 3 )
  {
    v5 = (_QWORD **)v22[v2];
    for ( i = *v5; ; i = (_QWORD *)*i )
    {
      if ( i == v5 )
      {
        ++v2;
        goto LABEL_4;
      }
      v7 = *((_WORD *)i - 108) == 23;
      *(_OWORD *)v23 = 0;
      LODWORD(v18) = 0;
      if ( v7 )
      {
        v8 = v23;
        v9 = 16;
        *(_OWORD *)v23 = *((_OWORD *)i - 13);
      }
      else
      {
        v8 = (const BYTE *)&v18;
        LODWORD(v18) = *((_DWORD *)i - 53);
        v9 = 4;
      }
      if ( !CryptHashData(phHash, v8, v9, 0) )
        break;
    }
    v14 = GetLastError();
    v3 = v14;
    if ( v14 > 0 )
      v3 = (unsigned __int16)v14 | 0x80070000;
    if ( v3 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v16 = 45;
        goto LABEL_51;
      }
    }
  }
  else
  {
    pdwDataLen = 16;
    if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
    {
      v18 = (char *)this + 72;
      v3 = StringCchPrintfA(
             (char *)this + 72,
             0x21u,
             "%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x%02x",
             pbData[15],
             pbData[14],
             pbData[13],
             pbData[12],
             pbData[11],
             pbData[10],
             pbData[9],
             pbData[8],
             pbData[7],
             pbData[6],
             pbData[5],
             pbData[4],
             pbData[3],
             pbData[2],
             pbData[1],
             pbData[0]);
      if ( (v3 & 0x80000000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
            (char *)this + 72);
        goto LABEL_10;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_10;
      v16 = 47;
LABEL_51:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v3);
      goto LABEL_10;
    }
    v17 = GetLastError();
    v3 = v17;
    if ( v17 > 0 )
      v3 = (unsigned __int16)v17 | 0x80070000;
    if ( v3 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v16 = 46;
        goto LABEL_51;
      }
    }
  }
LABEL_10:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v3;
}

```

## disassembly

```asm
0x180010080  mov     r11, rsp
0x180010083  push    rbp
0x180010084  push    rbx
0x180010085  lea     rbp, [r11-8]
0x180010089  sub     rsp, 118h
0x180010090  mov     rax, cs:__security_cookie
0x180010097  xor     rax, rsp
0x18001009a  mov     [rbp+var_28], rax
0x18001009e  lea     rax, [rcx+18h]
0x1800100a2  mov     [r11-20h], r14
0x1800100a6  mov     [rbp+var_60], rax
0x1800100aa  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x1800100b1  lea     rax, [rcx+28h]
0x1800100b5  mov     [r11-28h], r15
0x1800100b9  mov     [rbp+var_58], rax
0x1800100bd  mov     r14, rcx
0x1800100c0  lea     rax, [rcx+38h]
0x1800100c4  mov     [rsp+120h+dwFlags], 0F0000000h; dwFlags
0x1800100cc  xor     r15d, r15d
0x1800100cf  mov     [rbp+var_50], rax
0x1800100d3  lea     rcx, [rbp+phProv]; phProv
0x1800100d7  mov     [rbp+phProv], r15
0x1800100db  mov     r9d, 1; dwProvType
0x1800100e1  mov     [rbp+phHash], r15
0x1800100e5  xor     edx, edx; szContainer
0x1800100e7  call    cs:__imp_CryptAcquireContextW
0x1800100ed  test    eax, eax
0x1800100ef  jz      loc_180010325
0x1800100f5  mov     rcx, [rbp+phProv]; hProv
0x1800100f9  lea     rax, [rbp+phHash]
0x1800100fd  xor     r9d, r9d; dwFlags
0x180010100  mov     qword ptr [rsp+120h+dwFlags], rax; phHash
0x180010105  xor     r8d, r8d; hKey
0x180010108  mov     edx, 8003h; Algid
0x18001010d  call    cs:__imp_CryptCreateHash
0x180010113  test    eax, eax
0x180010115  jz      loc_180010365
0x18001011b  mov     [rsp+120h+arg_8], rsi
0x180010123  mov     esi, r15d
0x180010126  mov     [rsp+120h+arg_10], rdi
0x18001012e  cmp     esi, 3
0x180010131  jb      loc_1800102B2
0x180010137  mov     rcx, [rbp+phHash]; hHash
0x18001013b  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18001013f  lea     r8, [rbp+pbData]; pbData
0x180010143  mov     [rbp+pdwDataLen], 10h
0x18001014a  mov     edx, 2; dwParam
0x18001014f  mov     [rsp+120h+dwFlags], r15d; dwFlags
0x180010154  call    cs:__imp_CryptGetHashParam
0x18001015a  test    eax, eax
0x18001015c  jz      loc_180010405
0x180010162  movzx   ecx, [rbp+var_37]
0x180010166  lea     rax, [r14+48h]
0x18001016a  movzx   edx, [rbp+var_36]
0x18001016e  movzx   r8d, [rbp+var_35]
0x180010173  movzx   edi, [rbp+var_31]
0x180010177  movzx   r10d, [rbp+var_34]
0x18001017c  movzx   r11d, [rbp+var_33]
0x180010181  movzx   ebx, [rbp+var_32]
0x180010185  movzx   esi, [rbp+var_30]
0x180010189  movzx   r14d, [rbp+var_2F]
0x18001018e  movzx   r15d, [rbp+var_2E]
0x180010193  movzx   r9d, [rbp+var_29]
0x180010198  mov     [rbp+var_80], rax
0x18001019c  movzx   eax, [rbp+pbData]
0x1800101a0  mov     [rsp+90h], eax
0x1800101a7  movzx   eax, [rbp+var_2B]
0x1800101ab  mov     [rsp+120h+var_98], ecx
0x1800101b2  mov     [rsp+120h+var_A0], edx
0x1800101b9  mov     edx, 21h ; '!'; unsigned __int64
0x1800101be  mov     [rsp+120h+var_A8], r8d
0x1800101c3  lea     r8, a02x02x02x02x02_0; "%02x%02x%02x%02x%02x%02x%02x%02x%02x%02"...
0x1800101ca  mov     [rsp+120h+var_B0], r10d
0x1800101cf  mov     [rsp+120h+var_B8], r11d
0x1800101d4  mov     [rsp+120h+var_C0], ebx
0x1800101d8  mov     [rsp+120h+var_C8], edi
0x1800101dc  mov     rdi, [rbp+var_80]
0x1800101e0  mov     [rsp+120h+var_D0], esi
0x1800101e4  mov     rcx, rdi; char *
0x1800101e7  mov     [rsp+120h+var_D8], r14d
0x1800101ec  mov     [rsp+120h+var_E0], r15d
0x1800101f1  mov     [rsp+120h+arg_18], r12
0x1800101f9  movzx   r12d, [rbp+var_2D]
0x1800101fe  mov     [rsp+120h+var_E8], r12d
0x180010203  mov     [rsp+110h], r13
0x18001020b  movzx   r13d, [rbp+var_2C]
0x180010210  mov     [rsp+120h+var_F0], r13d
0x180010215  mov     [rsp+120h+var_F8], eax
0x180010219  movzx   eax, [rbp+var_2A]
0x18001021d  mov     [rsp+120h+dwFlags], eax
0x180010221  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010226  mov     r13, [rsp+110h]
0x18001022e  mov     ebx, eax
0x180010230  mov     r12, [rsp+120h+arg_18]
0x180010238  test    eax, eax
0x18001023a  js      loc_180010458
0x180010240  mov     rcx, cs:WPP_GLOBAL_Control
0x180010247  lea     rax, WPP_GLOBAL_Control
0x18001024e  cmp     rcx, rax
0x180010251  jz      short loc_180010260
0x180010253  test    dword ptr [rcx+1Ch], 200h
0x18001025a  jnz     loc_180010496
0x180010260  mov     rsi, [rsp+120h+arg_8]
0x180010268  mov     rdi, [rsp+120h+arg_10]
0x180010270  mov     rcx, [rbp+phHash]; hHash
0x180010274  mov     r15, [rsp+120h+var_20]
0x18001027c  mov     r14, [rsp+120h+var_18]
0x180010284  test    rcx, rcx
0x180010287  jnz     loc_1800104B3
0x18001028d  mov     rcx, [rbp+phProv]; hProv
0x180010291  test    rcx, rcx
0x180010294  jnz     loc_1800104BE
0x18001029a  mov     eax, ebx
0x18001029c  mov     rcx, [rbp+var_28]
0x1800102a0  xor     rcx, rsp; StackCookie
0x1800102a3  call    __security_check_cookie
0x1800102a8  add     rsp, 118h
0x1800102af  pop     rbx
0x1800102b0  pop     rbp
0x1800102b1  retn
0x1800102b2  mov     eax, esi
0x1800102b4  mov     rdi, [rbp+rax*8+var_60]
0x1800102b9  mov     rbx, [rdi]
0x1800102bc  nop     dword ptr [rax+00h]
0x1800102c0  cmp     rbx, rdi
0x1800102c3  jz      short loc_18001031E
0x1800102c5  cmp     word ptr [rbx-0D8h], 17h
0x1800102cd  xorps   xmm0, xmm0
0x1800102d0  movups  xmmword ptr [rbp+var_48], xmm0
0x1800102d4  mov     dword ptr [rbp+var_80], r15d
0x1800102d8  jnz     short loc_180010309
0x1800102da  movups  xmm0, xmmword ptr [rbx-0D0h]
0x1800102e1  lea     rdx, [rbp+var_48]; pbData
0x1800102e5  mov     r8d, 10h; dwDataLen
0x1800102eb  movups  xmmword ptr [rbp+var_48], xmm0
0x1800102ef  mov     rcx, [rbp+phHash]; hHash
0x1800102f3  xor     r9d, r9d; dwFlags
0x1800102f6  call    cs:__imp_CryptHashData
0x1800102fc  test    eax, eax
0x1800102fe  jz      loc_1800103C0
0x180010304  mov     rbx, [rbx]
0x180010307  jmp     short loc_1800102C0
0x180010309  mov     eax, [rbx-0D4h]
0x18001030f  lea     rdx, [rbp+var_80]
0x180010313  mov     dword ptr [rbp+var_80], eax
0x180010316  mov     r8d, 4
0x18001031c  jmp     short loc_1800102EF
0x18001031e  inc     esi
0x180010320  jmp     loc_18001012E
0x180010325  call    cs:__imp_GetLastError
0x18001032b  mov     ebx, eax
0x18001032d  test    eax, eax
0x18001032f  jg      loc_18001044A
0x180010335  test    ebx, ebx
0x180010337  jz      loc_180010270
0x18001033d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010344  lea     rax, WPP_GLOBAL_Control
0x18001034b  cmp     rcx, rax
0x18001034e  jz      loc_180010270
0x180010354  test    byte ptr [rcx+1Ch], 1
0x180010358  jz      loc_180010270
0x18001035e  mov     edx, 2Bh ; '+'
0x180010363  jmp     short loc_1800103A8
0x180010365  call    cs:__imp_GetLastError
0x18001036b  mov     ebx, eax
0x18001036d  test    eax, eax
0x18001036f  jle     short loc_18001037A
0x180010371  movzx   ebx, ax
0x180010374  or      ebx, 80070000h
0x18001037a  test    ebx, ebx
0x18001037c  jz      loc_180010270
0x180010382  mov     rcx, cs:WPP_GLOBAL_Control
0x180010389  lea     rax, WPP_GLOBAL_Control
0x180010390  cmp     rcx, rax
0x180010393  jz      loc_180010270
0x180010399  test    byte ptr [rcx+1Ch], 1
0x18001039d  jz      loc_180010270
0x1800103a3  mov     edx, 2Ch ; ','
0x1800103a8  mov     rcx, [rcx+10h]
0x1800103ac  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x1800103b3  mov     r9d, ebx
0x1800103b6  call    WPP_SF_d
0x1800103bb  jmp     loc_180010270
0x1800103c0  call    cs:__imp_GetLastError
0x1800103c6  mov     ebx, eax
0x1800103c8  test    eax, eax
0x1800103ca  jle     short loc_1800103D5
0x1800103cc  movzx   ebx, ax
0x1800103cf  or      ebx, 80070000h
0x1800103d5  test    ebx, ebx
0x1800103d7  jz      loc_180010260
0x1800103dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103e4  lea     rax, WPP_GLOBAL_Control
0x1800103eb  cmp     rcx, rax
0x1800103ee  jz      loc_180010260
0x1800103f4  test    byte ptr [rcx+1Ch], 1
0x1800103f8  jz      loc_180010260
0x1800103fe  mov     edx, 2Dh ; '-'
0x180010403  jmp     short loc_18001047E
0x180010405  call    cs:__imp_GetLastError
0x18001040b  mov     ebx, eax
0x18001040d  test    eax, eax
0x18001040f  jle     short loc_18001041A
0x180010411  movzx   ebx, ax
0x180010414  or      ebx, 80070000h
0x18001041a  test    ebx, ebx
0x18001041c  jz      loc_180010260
0x180010422  mov     rcx, cs:WPP_GLOBAL_Control
0x180010429  lea     rax, WPP_GLOBAL_Control
0x180010430  cmp     rcx, rax
0x180010433  jz      loc_180010260
0x180010439  test    byte ptr [rcx+1Ch], 1
0x18001043d  jz      loc_180010260
0x180010443  mov     edx, 2Eh ; '.'
0x180010448  jmp     short loc_18001047E
0x18001044a  movzx   ebx, ax
0x18001044d  or      ebx, 80070000h
0x180010453  jmp     loc_180010335
0x180010458  mov     rcx, cs:WPP_GLOBAL_Control
0x18001045f  lea     rax, WPP_GLOBAL_Control
0x180010466  cmp     rcx, rax
0x180010469  jz      loc_180010260
0x18001046f  test    byte ptr [rcx+1Ch], 1
0x180010473  jz      loc_180010260
0x180010479  mov     edx, 2Fh ; '/'
0x18001047e  mov     rcx, [rcx+10h]
0x180010482  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180010489  mov     r9d, ebx
0x18001048c  call    WPP_SF_d
0x180010491  jmp     loc_180010260
0x180010496  mov     rcx, [rcx+10h]
0x18001049a  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x1800104a1  mov     edx, 30h ; '0'
0x1800104a6  mov     r9, rdi
0x1800104a9  call    WPP_SF_s
0x1800104ae  jmp     loc_180010260
0x1800104b3  call    cs:__imp_CryptDestroyHash
0x1800104b9  jmp     loc_18001028D
0x1800104be  xor     edx, edx; dwFlags
0x1800104c0  call    cs:__imp_CryptReleaseContext
0x1800104c6  jmp     loc_18001029A
```
