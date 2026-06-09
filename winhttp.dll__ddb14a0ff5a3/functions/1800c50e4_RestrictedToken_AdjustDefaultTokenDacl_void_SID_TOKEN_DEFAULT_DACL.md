# RestrictedToken::AdjustDefaultTokenDacl(void *,_SID *,_TOKEN_DEFAULT_DACL * *)

- ea: `0x1800c50e4`
- end: `0x1800c542b`
- name: `?AdjustDefaultTokenDacl@RestrictedToken@@AEAAJPEAXPEAU_SID@@PEAPEAU_TOKEN_DEFAULT_DACL@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(RestrictedToken *this, void *, struct _SID *, struct _TOKEN_DEFAULT_DACL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c551c`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c50e4`
- `0x1800da694`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5170`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c5170`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c51a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5266`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c51a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5266`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c51fc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c51fc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800c5347`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800c5347`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800c52fa`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800c52fa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c52ba`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c52ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c51bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c52c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c53a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c51bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c52c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c53a4`

## pseudocode

```c
__int64 __fastcall RestrictedToken::AdjustDefaultTokenDacl(
        RestrictedToken *this,
        void *a2,
        struct _SID *a3,
        struct _TOKEN_DEFAULT_DACL **a4)
{
  struct _TOKEN_DEFAULT_DACL *v4; // rbx
  unsigned int v8; // edi
  signed int LastError; // eax
  DWORD LengthSid; // eax
  DWORD v11; // edi
  __int64 v12; // rcx
  struct _TOKEN_DEFAULT_DACL *Heap; // rax
  struct _TOKEN_DEFAULT_DACL *v14; // r14
  signed int v15; // eax
  struct _TOKEN_DEFAULT_DACL v16; // rcx
  DWORD AceCount; // r14d
  signed int v18; // eax
  signed int v19; // eax
  DWORD v20; // r13d
  DWORD i; // esi
  __int64 v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  signed int v25; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-40h]
  struct _TOKEN_DEFAULT_DACL *v28; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-20h] BYREF
  DWORD v30; // [rsp+48h] [rbp-18h] BYREF

  v4 = 0;
  v28 = 0;
  pAce = 0;
  v30 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 26, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids);
  if ( a4 )
    *a4 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    goto LABEL_52;
  }
  if ( !IsValidSid(a3) )
  {
    v8 = -2147024809;
    goto LABEL_52;
  }
  if ( GetTokenInformation(a2, TokenDefaultDacl, 0, 0, &v30) )
  {
    v8 = -2147418113;
    goto LABEL_52;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError == 122 )
    goto LABEL_17;
  if ( !LastError )
  {
    v8 = -2147418113;
    goto LABEL_52;
  }
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
LABEL_17:
    LengthSid = GetLengthSid(a3);
    v11 = LengthSid + v30 + 8;
    Heap = (struct _TOKEN_DEFAULT_DACL *)WxAllocateHeapEx(v12, v11);
    v14 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, v11);
      v4 = v14;
      v28 = v14;
      if ( GetTokenInformation(a2, TokenDefaultDacl, v14, v11, &v30) )
      {
        v16.DefaultDacl = v14->DefaultDacl;
        AceCount = v14->DefaultDacl->AceCount;
        v16.DefaultDacl->AclSize = v11 - 8;
        if ( AddAccessAllowedAce(v4->DefaultDacl, 2u, 0x20018u, a3) )
        {
          if ( SetTokenInformation(a2, TokenDefaultDacl, v4, v11) )
          {
            v8 = 0;
            v20 = AceCount;
            for ( i = 0; ; ++i )
            {
              if ( i >= v20 )
              {
                *a4 = v4;
                v4 = 0;
                v28 = 0;
                goto LABEL_52;
              }
              if ( !GetAce(v4->DefaultDacl, i, &pAce) )
                break;
              v24 = pAce;
              v8 = 0;
              if ( !*(_BYTE *)pAce )
              {
                if ( (xmmword_180107A60 & 0x20) != 0 )
                {
                  LODWORD(ReturnLength) = *((_DWORD *)pAce + 1);
                  WPP_SF__sid_D(v22, 27, v23, (char *)pAce + 8);
                }
                v24[1] = 1183745;
                if ( (xmmword_180107A60 & 0x20) != 0 )
                {
                  LODWORD(ReturnLength) = 1183745;
                  WPP_SF__sid_D(v22, 28, v23, v24 + 2);
                }
              }
            }
            v25 = GetLastError();
            if ( v25 > 0 )
              v25 = (unsigned __int16)v25 | 0x80070000;
            if ( v25 >= 0 )
              v25 = -2147418113;
            v8 = v25;
          }
          else
          {
            v19 = GetLastError();
            if ( v19 > 0 )
              v19 = (unsigned __int16)v19 | 0x80070000;
            if ( v19 >= 0 )
              v19 = -2147418113;
            v8 = v19;
          }
        }
        else
        {
          v18 = GetLastError();
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          if ( v18 >= 0 )
            v18 = -2147418113;
          v8 = v18;
        }
      }
      else
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        if ( v15 >= 0 )
          v15 = -2147418113;
        v8 = v15;
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
LABEL_52:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 29, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, v8, ReturnLength);
  if ( v4 )
    WxFreeHeapEx(&v28);
  return v8;
}

```

## disassembly

```asm
0x1800c50e4  mov     [rsp-38h+arg_0], rbx
0x1800c50e9  push    rbp
0x1800c50ea  push    rsi
0x1800c50eb  push    rdi
0x1800c50ec  push    r12
0x1800c50ee  push    r13
0x1800c50f0  push    r14
0x1800c50f2  push    r15
0x1800c50f4  mov     rbp, rsp
0x1800c50f7  sub     rsp, 60h
0x1800c50fb  mov     rax, cs:__security_cookie
0x1800c5102  xor     rax, rsp
0x1800c5105  mov     [rbp+var_10], rax
0x1800c5109  xor     ebx, ebx
0x1800c510b  mov     [rbp+var_2C], 0
0x1800c5112  mov     [rbp+var_28], rbx
0x1800c5116  mov     r12, r9
0x1800c5119  mov     [rbp+pAce], rbx
0x1800c511d  mov     rsi, r8
0x1800c5120  mov     r13, rdx
0x1800c5123  mov     [rbp+var_18], 0
0x1800c512a  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5131  jz      short loc_1800C514E
0x1800c5133  lea     edx, [rbx+1Ah]
0x1800c5136  mov     ecx, 405h
0x1800c513b  lea     r9, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; RestrictedToken PacWorkerClient::s_RestrictedToken
0x1800c5142  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c5149  call    WPP_SF_q
0x1800c514e  test    r12, r12
0x1800c5151  jz      short loc_1800C5157
0x1800c5153  mov     [r12], rbx
0x1800c5157  test    rsi, rsi
0x1800c515a  jnz     short loc_1800C516D
0x1800c515c  mov     edi, 80070057h
0x1800c5161  mov     [rbp+var_2C], 23Eh
0x1800c5168  jmp     loc_1800C53D5
0x1800c516d  mov     rcx, rsi; pSid
0x1800c5170  call    cs:__imp_IsValidSid
0x1800c5176  test    eax, eax
0x1800c5178  jnz     short loc_1800C518B
0x1800c517a  mov     edi, 80070057h
0x1800c517f  mov     [rbp+var_2C], 240h
0x1800c5186  jmp     loc_1800C53D5
0x1800c518b  xor     r9d, r9d; TokenInformationLength
0x1800c518e  lea     rax, [rbp+var_18]
0x1800c5192  xor     r8d, r8d; TokenInformation
0x1800c5195  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800c519a  mov     rcx, r13; TokenHandle
0x1800c519d  lea     edx, [r9+6]; TokenInformationClass
0x1800c51a1  call    cs:__imp_GetTokenInformation
0x1800c51a7  test    eax, eax
0x1800c51a9  jz      short loc_1800C51BC
0x1800c51ab  mov     edi, 8000FFFFh
0x1800c51b0  mov     [rbp+var_2C], 24Ah
0x1800c51b7  jmp     loc_1800C53D5
0x1800c51bc  call    cs:__imp_GetLastError
0x1800c51c2  mov     edi, eax
0x1800c51c4  cmp     eax, 7Ah ; 'z'
0x1800c51c7  jz      short loc_1800C51F9
0x1800c51c9  test    eax, eax
0x1800c51cb  jnz     short loc_1800C51DE
0x1800c51cd  mov     edi, 8000FFFFh
0x1800c51d2  mov     [rbp+var_2C], 24Fh
0x1800c51d9  jmp     loc_1800C53D5
0x1800c51de  jle     short loc_1800C51E9
0x1800c51e0  movzx   edi, ax
0x1800c51e3  or      edi, 80070000h
0x1800c51e9  test    edi, edi
0x1800c51eb  jns     short loc_1800C51F9
0x1800c51ed  mov     [rbp+var_2C], 250h
0x1800c51f4  jmp     loc_1800C53D5
0x1800c51f9  mov     rcx, rsi; pSid
0x1800c51fc  call    cs:__imp_GetLengthSid
0x1800c5202  mov     edi, [rbp+var_18]
0x1800c5205  add     edi, 8
0x1800c5208  mov     [rbp+var_2C], ebx
0x1800c520b  add     edi, eax
0x1800c520d  mov     edx, edi
0x1800c520f  mov     r15d, edi
0x1800c5212  call    WxAllocateHeapEx
0x1800c5217  mov     r14, rax
0x1800c521a  test    rax, rax
0x1800c521d  jnz     short loc_1800C5237
0x1800c521f  mov     [rbp+var_2C], 4Ch ; 'L'
0x1800c5226  mov     edi, 8007000Eh
0x1800c522b  mov     [rbp+var_2C], 25Ch
0x1800c5232  jmp     loc_1800C53D5
0x1800c5237  mov     r8, r15; Size
0x1800c523a  xor     edx, edx; Val
0x1800c523c  mov     rcx, r14; void *
0x1800c523f  call    memset_0
0x1800c5244  mov     rbx, r14
0x1800c5247  mov     [rbp+var_28], rbx
0x1800c524b  lea     rax, [rbp+var_18]
0x1800c524f  mov     r15d, 6
0x1800c5255  mov     edx, r15d; TokenInformationClass
0x1800c5258  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800c525d  mov     r9d, edi; TokenInformationLength
0x1800c5260  mov     r8, r14; TokenInformation
0x1800c5263  mov     rcx, r13; TokenHandle
0x1800c5266  call    cs:__imp_GetTokenInformation
0x1800c526c  test    eax, eax
0x1800c526e  jnz     short loc_1800C529A
0x1800c5270  call    cs:__imp_GetLastError
0x1800c5276  test    eax, eax
0x1800c5278  jle     short loc_1800C5282
0x1800c527a  movzx   eax, ax
0x1800c527d  or      eax, 80070000h
0x1800c5282  mov     edi, 8000FFFFh
0x1800c5287  mov     [rbp+var_2C], 262h
0x1800c528e  test    eax, eax
0x1800c5290  cmovns  eax, edi
0x1800c5293  mov     edi, eax
0x1800c5295  jmp     loc_1800C53D5
0x1800c529a  mov     rcx, [r14]
0x1800c529d  lea     eax, [rdi-8]
0x1800c52a0  mov     r9, rsi; pSid
0x1800c52a3  mov     edx, 2; dwAceRevision
0x1800c52a8  mov     r8d, 20018h; AccessMask
0x1800c52ae  movzx   r14d, word ptr [rcx+4]
0x1800c52b3  mov     [rcx+2], ax
0x1800c52b7  mov     rcx, [rbx]; pAcl
0x1800c52ba  call    cs:__imp_AddAccessAllowedAce
0x1800c52c0  test    eax, eax
0x1800c52c2  jnz     short loc_1800C52EE
0x1800c52c4  call    cs:__imp_GetLastError
0x1800c52ca  test    eax, eax
0x1800c52cc  jle     short loc_1800C52D6
0x1800c52ce  movzx   eax, ax
0x1800c52d1  or      eax, 80070000h
0x1800c52d6  mov     edi, 8000FFFFh
0x1800c52db  mov     [rbp+var_2C], 277h
0x1800c52e2  test    eax, eax
0x1800c52e4  cmovns  eax, edi
0x1800c52e7  mov     edi, eax
0x1800c52e9  jmp     loc_1800C53D5
0x1800c52ee  mov     r9d, edi; TokenInformationLength
0x1800c52f1  mov     r8, rbx; TokenInformation
0x1800c52f4  mov     edx, r15d; TokenInformationClass
0x1800c52f7  mov     rcx, r13; TokenHandle
0x1800c52fa  call    cs:__imp_SetTokenInformation
0x1800c5300  test    eax, eax
0x1800c5302  jnz     short loc_1800C532E
0x1800c5304  call    cs:__imp_GetLastError
0x1800c530a  test    eax, eax
0x1800c530c  jle     short loc_1800C5316
0x1800c530e  movzx   eax, ax
0x1800c5311  or      eax, 80070000h
0x1800c5316  mov     edi, 8000FFFFh
0x1800c531b  mov     [rbp+var_2C], 27Ch
0x1800c5322  test    eax, eax
0x1800c5324  cmovns  eax, edi
0x1800c5327  mov     edi, eax
0x1800c5329  jmp     loc_1800C53D5
0x1800c532e  xor     edi, edi
0x1800c5330  mov     r13d, r14d
0x1800c5333  xor     esi, esi
0x1800c5335  cmp     esi, r13d
0x1800c5338  jnb     loc_1800C53CB
0x1800c533e  mov     rcx, [rbx]; pAcl
0x1800c5341  lea     r8, [rbp+pAce]; pAce
0x1800c5345  mov     edx, esi; dwAceIndex
0x1800c5347  call    cs:__imp_GetAce
0x1800c534d  test    eax, eax
0x1800c534f  jz      short loc_1800C53A4
0x1800c5351  mov     r14, [rbp+pAce]
0x1800c5355  xor     edi, edi
0x1800c5357  cmp     [r14], dil
0x1800c535a  jnz     short loc_1800C53A0
0x1800c535c  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5363  jz      short loc_1800C5379
0x1800c5365  mov     eax, [r14+4]
0x1800c5369  lea     edx, [rdi+1Bh]
0x1800c536c  lea     r9, [r14+8]
0x1800c5370  mov     dword ptr [rsp+60h+ReturnLength], eax
0x1800c5374  call    WPP_SF__sid_D
0x1800c5379  mov     dword ptr [r14+4], 121001h
0x1800c5381  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5388  jz      short loc_1800C53A0
0x1800c538a  mov     edx, 1Ch
0x1800c538f  mov     dword ptr [rsp+60h+ReturnLength], 121001h
0x1800c5397  lea     r9, [r14+8]
0x1800c539b  call    WPP_SF__sid_D
0x1800c53a0  inc     esi
0x1800c53a2  jmp     short loc_1800C5335
0x1800c53a4  call    cs:__imp_GetLastError
0x1800c53aa  test    eax, eax
0x1800c53ac  jle     short loc_1800C53B6
0x1800c53ae  movzx   eax, ax
0x1800c53b1  or      eax, 80070000h
0x1800c53b6  mov     edi, 8000FFFFh
0x1800c53bb  mov     [rbp+var_2C], 286h
0x1800c53c2  test    eax, eax
0x1800c53c4  cmovns  eax, edi
0x1800c53c7  mov     edi, eax
0x1800c53c9  jmp     short loc_1800C53D5
0x1800c53cb  mov     [r12], rbx
0x1800c53cf  xor     ebx, ebx
0x1800c53d1  mov     [rbp+var_28], rbx
0x1800c53d5  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c53dc  jz      short loc_1800C53F7
0x1800c53de  mov     edx, 1Dh
0x1800c53e3  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c53ea  mov     ecx, 405h
0x1800c53ef  mov     r9d, edi
0x1800c53f2  call    WPP_SF_d
0x1800c53f7  test    rbx, rbx
0x1800c53fa  jz      short loc_1800C5405
0x1800c53fc  lea     rcx, [rbp+var_28]
0x1800c5400  call    WxFreeHeapEx
0x1800c5405  mov     eax, edi
0x1800c5407  mov     rcx, [rbp+var_10]
0x1800c540b  xor     rcx, rsp; StackCookie
0x1800c540e  call    __security_check_cookie
0x1800c5413  mov     rbx, [rsp+60h+arg_0]
0x1800c541b  add     rsp, 60h
0x1800c541f  pop     r15
0x1800c5421  pop     r14
0x1800c5423  pop     r13
0x1800c5425  pop     r12
0x1800c5427  pop     rdi
0x1800c5428  pop     rsi
0x1800c5429  pop     rbp
0x1800c542a  retn
```
