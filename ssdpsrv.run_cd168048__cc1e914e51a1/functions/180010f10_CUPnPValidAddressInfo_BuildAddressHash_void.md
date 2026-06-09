# CUPnPValidAddressInfo::BuildAddressHash(void)

- ea: `0x180010f10`
- end: `0x180011395`
- name: `?BuildAddressHash@CUPnPValidAddressInfo@@AEAAJXZ`
- size: `1157`
- prototype: `__int64 __fastcall(CUPnPValidAddressInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010390`

## callees

- `0x180010f10`
- `0x180011c44`
- `0x1800271fc`
- `0x1800287d0`
- `0x18002fe28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180011371`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180011371`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180011196`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180011196`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180011384`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180011384`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180010fa3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180010fa3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180010f77`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180010f77`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010ff0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010ff0`

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
0x180010f10  mov     r11, rsp
0x180010f13  push    rbp
0x180010f14  push    rbx
0x180010f15  lea     rbp, [r11-8]
0x180010f19  sub     rsp, 118h
0x180010f20  mov     rax, cs:__security_cookie
0x180010f27  xor     rax, rsp
0x180010f2a  mov     [rbp+var_28], rax
0x180010f2e  lea     rax, [rcx+18h]
0x180010f32  mov     [r11-20h], r14
0x180010f36  mov     [rbp+var_60], rax
0x180010f3a  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180010f41  lea     rax, [rcx+28h]
0x180010f45  mov     [r11-28h], r15
0x180010f49  mov     [rbp+var_58], rax
0x180010f4d  mov     r14, rcx
0x180010f50  lea     rax, [rcx+38h]
0x180010f54  mov     [rsp+120h+dwFlags], 0F0000000h; dwFlags
0x180010f5c  xor     r15d, r15d
0x180010f5f  mov     [rbp+var_50], rax
0x180010f63  lea     rcx, [rbp+phProv]; phProv
0x180010f67  mov     [rbp+phProv], r15
0x180010f6b  mov     r9d, 1; dwProvType
0x180010f71  mov     [rbp+phHash], r15
0x180010f75  xor     edx, edx; szContainer
0x180010f77  call    cs:__imp_CryptAcquireContextW
0x180010f7e  nop     dword ptr [rax+rax+00h]
0x180010f83  test    eax, eax
0x180010f85  jz      loc_1800111CB
0x180010f8b  mov     rcx, [rbp+phProv]; hProv
0x180010f8f  lea     rax, [rbp+phHash]
0x180010f93  xor     r9d, r9d; dwFlags
0x180010f96  mov     qword ptr [rsp+120h+dwFlags], rax; phHash
0x180010f9b  xor     r8d, r8d; hKey
0x180010f9e  mov     edx, 8003h; Algid
0x180010fa3  call    cs:__imp_CryptCreateHash
0x180010faa  nop     dword ptr [rax+rax+00h]
0x180010faf  test    eax, eax
0x180010fb1  jz      loc_180011211
0x180010fb7  mov     [rsp+120h+arg_8], rsi
0x180010fbf  mov     esi, r15d
0x180010fc2  mov     [rsp+120h+arg_10], rdi
0x180010fca  cmp     esi, 3
0x180010fcd  jb      loc_180011155
0x180010fd3  mov     rcx, [rbp+phHash]; hHash
0x180010fd7  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180010fdb  lea     r8, [rbp+pbData]; pbData
0x180010fdf  mov     [rbp+pdwDataLen], 10h
0x180010fe6  mov     edx, 2; dwParam
0x180010feb  mov     [rsp+120h+dwFlags], r15d; dwFlags
0x180010ff0  call    cs:__imp_CryptGetHashParam
0x180010ff7  nop     dword ptr [rax+rax+00h]
0x180010ffc  test    eax, eax
0x180010ffe  jz      loc_1800112BD
0x180011004  movzx   ecx, [rbp+var_37]
0x180011008  lea     rax, [r14+48h]
0x18001100c  movzx   edx, [rbp+var_36]
0x180011010  movzx   r8d, [rbp+var_35]
0x180011015  movzx   edi, [rbp+var_31]
0x180011019  movzx   r10d, [rbp+var_34]
0x18001101e  movzx   r11d, [rbp+var_33]
0x180011023  movzx   ebx, [rbp+var_32]
0x180011027  movzx   esi, [rbp+var_30]
0x18001102b  movzx   r14d, [rbp+var_2F]
0x180011030  movzx   r15d, [rbp+var_2E]
0x180011035  movzx   r9d, [rbp+var_29]
0x18001103a  mov     [rbp+var_80], rax
0x18001103e  movzx   eax, [rbp+pbData]
0x180011042  mov     [rsp+90h], eax
0x180011049  movzx   eax, [rbp+var_2B]
0x18001104d  mov     [rsp+120h+var_98], ecx
0x180011054  mov     [rsp+120h+var_A0], edx
0x18001105b  mov     edx, 21h ; '!'; unsigned __int64
0x180011060  mov     [rsp+120h+var_A8], r8d
0x180011065  lea     r8, a02x02x02x02x02_0; "%02x%02x%02x%02x%02x%02x%02x%02x%02x%02"...
0x18001106c  mov     [rsp+120h+var_B0], r10d
0x180011071  mov     [rsp+120h+var_B8], r11d
0x180011076  mov     [rsp+120h+var_C0], ebx
0x18001107a  mov     [rsp+120h+var_C8], edi
0x18001107e  mov     rdi, [rbp+var_80]
0x180011082  mov     [rsp+120h+var_D0], esi
0x180011086  mov     rcx, rdi; char *
0x180011089  mov     [rsp+120h+var_D8], r14d
0x18001108e  mov     [rsp+120h+var_E0], r15d
0x180011093  mov     [rsp+120h+arg_18], r12
0x18001109b  movzx   r12d, [rbp+var_2D]
0x1800110a0  mov     [rsp+120h+var_E8], r12d
0x1800110a5  mov     [rsp+110h], r13
0x1800110ad  movzx   r13d, [rbp+var_2C]
0x1800110b2  mov     [rsp+120h+var_F0], r13d
0x1800110b7  mov     [rsp+120h+var_F8], eax
0x1800110bb  movzx   eax, [rbp+var_2A]
0x1800110bf  mov     [rsp+120h+dwFlags], eax
0x1800110c3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800110c8  mov     r13, [rsp+110h]
0x1800110d0  mov     ebx, eax
0x1800110d2  mov     r12, [rsp+120h+arg_18]
0x1800110da  test    eax, eax
0x1800110dc  js      loc_180011316
0x1800110e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110e9  lea     rax, WPP_GLOBAL_Control
0x1800110f0  cmp     rcx, rax
0x1800110f3  jz      short loc_180011102
0x1800110f5  test    dword ptr [rcx+1Ch], 200h
0x1800110fc  jnz     loc_180011354
0x180011102  mov     rsi, [rsp+120h+arg_8]
0x18001110a  mov     rdi, [rsp+120h+arg_10]
0x180011112  mov     rcx, [rbp+phHash]; hHash
0x180011116  mov     r15, [rsp+120h+var_20]
0x18001111e  mov     r14, [rsp+120h+var_18]
0x180011126  test    rcx, rcx
0x180011129  jnz     loc_180011371
0x18001112f  mov     rcx, [rbp+phProv]; hProv
0x180011133  test    rcx, rcx
0x180011136  jnz     loc_180011382
0x18001113c  mov     eax, ebx
0x18001113e  mov     rcx, [rbp+var_28]
0x180011142  xor     rcx, rsp; StackCookie
0x180011145  call    __security_check_cookie
0x18001114a  add     rsp, 118h
0x180011151  pop     rbx
0x180011152  pop     rbp
0x180011153  retn
0x180011155  mov     eax, esi
0x180011157  mov     rdi, [rbp+rax*8+var_60]
0x18001115c  mov     rbx, [rdi]
0x18001115f  nop
0x180011160  cmp     rbx, rdi
0x180011163  jz      short loc_1800111C4
0x180011165  cmp     word ptr [rbx-0D8h], 17h
0x18001116d  xorps   xmm0, xmm0
0x180011170  movups  xmmword ptr [rbp+var_48], xmm0
0x180011174  mov     dword ptr [rbp+var_80], r15d
0x180011178  jnz     short loc_1800111AF
0x18001117a  movups  xmm0, xmmword ptr [rbx-0D0h]
0x180011181  lea     rdx, [rbp+var_48]; pbData
0x180011185  mov     r8d, 10h; dwDataLen
0x18001118b  movups  xmmword ptr [rbp+var_48], xmm0
0x18001118f  mov     rcx, [rbp+phHash]; hHash
0x180011193  xor     r9d, r9d; dwFlags
0x180011196  call    cs:__imp_CryptHashData
0x18001119d  nop     dword ptr [rax+rax+00h]
0x1800111a2  test    eax, eax
0x1800111a4  jz      loc_180011272
0x1800111aa  mov     rbx, [rbx]
0x1800111ad  jmp     short loc_180011160
0x1800111af  mov     eax, [rbx-0D4h]
0x1800111b5  lea     rdx, [rbp+var_80]
0x1800111b9  mov     dword ptr [rbp+var_80], eax
0x1800111bc  mov     r8d, 4
0x1800111c2  jmp     short loc_18001118F
0x1800111c4  inc     esi
0x1800111c6  jmp     loc_180010FCA
0x1800111cb  call    cs:__imp_GetLastError
0x1800111d2  nop     dword ptr [rax+rax+00h]
0x1800111d7  mov     ebx, eax
0x1800111d9  test    eax, eax
0x1800111db  jg      loc_180011308
0x1800111e1  test    ebx, ebx
0x1800111e3  jz      loc_180011112
0x1800111e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111f0  lea     rax, WPP_GLOBAL_Control
0x1800111f7  cmp     rcx, rax
0x1800111fa  jz      loc_180011112
0x180011200  test    byte ptr [rcx+1Ch], 1
0x180011204  jz      loc_180011112
0x18001120a  mov     edx, 2Bh ; '+'
0x18001120f  jmp     short loc_18001125A
0x180011211  call    cs:__imp_GetLastError
0x180011218  nop     dword ptr [rax+rax+00h]
0x18001121d  mov     ebx, eax
0x18001121f  test    eax, eax
0x180011221  jle     short loc_18001122C
0x180011223  movzx   ebx, ax
0x180011226  or      ebx, 80070000h
0x18001122c  test    ebx, ebx
0x18001122e  jz      loc_180011112
0x180011234  mov     rcx, cs:WPP_GLOBAL_Control
0x18001123b  lea     rax, WPP_GLOBAL_Control
0x180011242  cmp     rcx, rax
0x180011245  jz      loc_180011112
0x18001124b  test    byte ptr [rcx+1Ch], 1
0x18001124f  jz      loc_180011112
0x180011255  mov     edx, 2Ch ; ','
0x18001125a  mov     rcx, [rcx+10h]
0x18001125e  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180011265  mov     r9d, ebx
0x180011268  call    WPP_SF_d
0x18001126d  jmp     loc_180011112
0x180011272  call    cs:__imp_GetLastError
0x180011279  nop     dword ptr [rax+rax+00h]
0x18001127e  mov     ebx, eax
0x180011280  test    eax, eax
0x180011282  jle     short loc_18001128D
0x180011284  movzx   ebx, ax
0x180011287  or      ebx, 80070000h
0x18001128d  test    ebx, ebx
0x18001128f  jz      loc_180011102
0x180011295  mov     rcx, cs:WPP_GLOBAL_Control
0x18001129c  lea     rax, WPP_GLOBAL_Control
0x1800112a3  cmp     rcx, rax
0x1800112a6  jz      loc_180011102
0x1800112ac  test    byte ptr [rcx+1Ch], 1
0x1800112b0  jz      loc_180011102
0x1800112b6  mov     edx, 2Dh ; '-'
0x1800112bb  jmp     short loc_18001133C
0x1800112bd  call    cs:__imp_GetLastError
0x1800112c4  nop     dword ptr [rax+rax+00h]
0x1800112c9  mov     ebx, eax
0x1800112cb  test    eax, eax
0x1800112cd  jle     short loc_1800112D8
0x1800112cf  movzx   ebx, ax
0x1800112d2  or      ebx, 80070000h
0x1800112d8  test    ebx, ebx
0x1800112da  jz      loc_180011102
0x1800112e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112e7  lea     rax, WPP_GLOBAL_Control
0x1800112ee  cmp     rcx, rax
0x1800112f1  jz      loc_180011102
0x1800112f7  test    byte ptr [rcx+1Ch], 1
0x1800112fb  jz      loc_180011102
0x180011301  mov     edx, 2Eh ; '.'
0x180011306  jmp     short loc_18001133C
0x180011308  movzx   ebx, ax
0x18001130b  or      ebx, 80070000h
0x180011311  jmp     loc_1800111E1
0x180011316  mov     rcx, cs:WPP_GLOBAL_Control
0x18001131d  lea     rax, WPP_GLOBAL_Control
0x180011324  cmp     rcx, rax
0x180011327  jz      loc_180011102
0x18001132d  test    byte ptr [rcx+1Ch], 1
0x180011331  jz      loc_180011102
0x180011337  mov     edx, 2Fh ; '/'
0x18001133c  mov     rcx, [rcx+10h]
0x180011340  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180011347  mov     r9d, ebx
0x18001134a  call    WPP_SF_d
0x18001134f  jmp     loc_180011102
0x180011354  mov     rcx, [rcx+10h]
0x180011358  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18001135f  mov     edx, 30h ; '0'
0x180011364  mov     r9, rdi
0x180011367  call    WPP_SF_s
0x18001136c  jmp     loc_180011102
0x180011371  call    cs:__imp_CryptDestroyHash
0x180011378  nop     dword ptr [rax+rax+00h]
0x18001137d  jmp     loc_18001112F
0x180011382  xor     edx, edx; dwFlags
0x180011384  call    cs:__imp_CryptReleaseContext
0x18001138b  nop     dword ptr [rax+rax+00h]
0x180011390  jmp     loc_18001113C
```
