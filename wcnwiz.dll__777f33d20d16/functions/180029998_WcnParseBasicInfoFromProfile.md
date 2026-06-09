# WcnParseBasicInfoFromProfile

- ea: `0x180029998`
- end: `0x180029d5a`
- name: `WcnParseBasicInfoFromProfile`
- size: `962`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800296a4`

## callees

- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800132e0`
- `0x180029998`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WlanParseProfileXmlBasicSettings` at `0x180029b14`
- `wlanapi!WlanParseProfileXmlBasicSettings` at `0x180029b14`
- `wlanapi!WlanFreeMemory` at `0x180029cfe`
- `wlanapi!WlanFreeMemory` at `0x180029cfe`

## string_xrefs

- `0x180029a75`: `pSsid`

## pseudocode

```c
__int64 __fastcall WcnParseBasicInfoFromProfile(__int64 a1, unsigned __int16 *a2, __int64 a3, _DWORD *a4, _DWORD *a5)
{
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // rdx
  const char *v14; // r9
  _DWORD *v15; // rbx
  int v17; // eax
  unsigned int v18; // ebx
  signed int v19; // ebx
  _BYTE *v20; // r10
  const char *v21; // rax
  __int64 v22; // r10
  unsigned int v23; // eax
  __int64 v24; // r10
  char v25; // r11
  int v26; // edx
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // r10
  int v30; // [rsp+50h] [rbp-20h] BYREF
  int v31; // [rsp+54h] [rbp-1Ch] BYREF
  int v32; // [rsp+58h] [rbp-18h] BYREF
  int v33; // [rsp+5Ch] [rbp-14h] BYREF
  int v34; // [rsp+60h] [rbp-10h] BYREF
  int v35; // [rsp+64h] [rbp-Ch] BYREF
  PVOID pMemory; // [rsp+68h] [rbp-8h] BYREF
  int v37; // [rsp+A0h] [rbp+30h] BYREF

  pMemory = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v37 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 26, v12, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 27;
    v14 = "wszNetworkProfile";
LABEL_20:
    WPP_SF_s(*((_QWORD *)v9 + 2), v13, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v14);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 28;
    v14 = "pSsid";
    goto LABEL_20;
  }
  if ( !a4 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 29;
    v14 = "pWcnAuthType";
    goto LABEL_20;
  }
  v15 = a5;
  if ( !a5 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = (unsigned int)((_DWORD)a5 + 30);
    v14 = "pWcnCipherType";
    goto LABEL_20;
  }
  v17 = WlanParseProfileXmlBasicSettings(a1, &pMemory, a3, &v35, &v34, &v33, &v32, &v30, &v31, &v37);
  if ( v17 )
  {
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    else
      v18 = v17;
    v19 = v18 | 0x80000000;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_64;
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
      (unsigned int)v17,
      v19);
    goto LABEL_63;
  }
  if ( !v37 )
  {
    switch ( v30 )
    {
      case 1:
        *a4 = 1;
        break;
      case 2:
        *a4 = 4;
        break;
      case 4:
        *a4 = 2;
        break;
      case 7:
        *a4 = 32;
        break;
      default:
        v19 = -2147024846;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_64;
        v23 = (unsigned int)GetIndent(0);
        v26 = 33;
        goto LABEL_40;
    }
    if ( !v31 )
    {
      *v15 = 1;
LABEL_59:
      v27 = StringCchCopyW(a2, 0x100u, (const unsigned __int16 *)pMemory);
      v19 = v27;
      if ( v27 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_64;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
          (unsigned int)v27);
      }
      goto LABEL_63;
    }
    if ( v31 != 1 )
    {
      if ( v31 == 2 )
      {
        *v15 = 4;
        goto LABEL_59;
      }
      if ( v31 == 4 )
        goto LABEL_55;
      if ( v31 != 5 )
      {
        if ( v31 != 8 )
        {
          if ( v31 != 257 )
          {
            v19 = -2147024846;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_64;
            v23 = (unsigned int)GetIndent(0);
            v26 = 34;
LABEL_40:
            WPP_SF_sd(
              *(_QWORD *)(v24 + 16),
              v26,
              (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
              v23,
              v25);
            goto LABEL_63;
          }
          goto LABEL_57;
        }
LABEL_55:
        *v15 = 8;
        goto LABEL_59;
      }
    }
LABEL_57:
    *v15 = 2;
    goto LABEL_59;
  }
  v19 = -2147024846;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_64;
  v21 = GetIndent(0);
  WPP_SF_s(*(_QWORD *)(v22 + 16), 32, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v21);
LABEL_63:
  v20 = WPP_GLOBAL_Control;
LABEL_64:
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v20 = WPP_GLOBAL_Control;
  }
  if ( v20 != (_BYTE *)&WPP_GLOBAL_Control && (v19 < 0 || v20[25] >= 6u) )
  {
    v28 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v29 + 16), 36, (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v28, v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180029998  mov     [rsp-28h+arg_8], rbx
0x18002999d  mov     [rsp-28h+arg_10], rsi
0x1800299a2  push    rbp
0x1800299a3  push    rdi
0x1800299a4  push    r13
0x1800299a6  push    r14
0x1800299a8  push    r15
0x1800299aa  mov     rbp, rsp
0x1800299ad  sub     rsp, 70h
0x1800299b1  mov     rdi, r9
0x1800299b4  mov     [rbp+pMemory], 0
0x1800299bc  mov     rsi, r8
0x1800299bf  mov     [rbp+var_C], 0
0x1800299c6  mov     r15, rdx
0x1800299c9  mov     [rbp+var_10], 0
0x1800299d0  mov     r14, rcx
0x1800299d3  mov     [rbp+var_14], 0
0x1800299da  mov     [rbp+var_18], 0
0x1800299e1  mov     [rbp+var_20], 0
0x1800299e8  mov     [rbp+var_1C], 0
0x1800299ef  mov     [rbp+arg_0], 0
0x1800299f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800299fd  lea     r13, WPP_GLOBAL_Control
0x180029a04  lea     r11, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029a0b  cmp     r10, r13
0x180029a0e  jz      short loc_180029A43
0x180029a10  cmp     byte ptr [r10+19h], 6
0x180029a15  jb      short loc_180029A43
0x180029a17  mov     ecx, 1; int
0x180029a1c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029a21  mov     rcx, [r10+10h]
0x180029a25  mov     edx, 1Ah
0x180029a2a  mov     r9, rax
0x180029a2d  mov     r8, r11
0x180029a30  call    WPP_SF_s
0x180029a35  mov     r10, cs:WPP_GLOBAL_Control
0x180029a3c  lea     r11, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029a43  test    r14, r14
0x180029a46  jnz     short loc_180029A61
0x180029a48  cmp     r10, r13
0x180029a4b  jz      short loc_180029AC6
0x180029a4d  cmp     byte ptr [r10+19h], 2
0x180029a52  jb      short loc_180029AC6
0x180029a54  lea     edx, [r14+1Bh]
0x180029a58  lea     r9, aWsznetworkprof; "wszNetworkProfile"
0x180029a5f  jmp     short loc_180029ABA
0x180029a61  test    rsi, rsi
0x180029a64  jnz     short loc_180029A7E
0x180029a66  cmp     r10, r13
0x180029a69  jz      short loc_180029AC6
0x180029a6b  cmp     byte ptr [r10+19h], 2
0x180029a70  jb      short loc_180029AC6
0x180029a72  lea     edx, [rsi+1Ch]
0x180029a75  lea     r9, aPssid; "pSsid"
0x180029a7c  jmp     short loc_180029ABA
0x180029a7e  test    rdi, rdi
0x180029a81  jnz     short loc_180029A9B
0x180029a83  cmp     r10, r13
0x180029a86  jz      short loc_180029AC6
0x180029a88  cmp     byte ptr [r10+19h], 2
0x180029a8d  jb      short loc_180029AC6
0x180029a8f  lea     edx, [rdi+1Dh]
0x180029a92  lea     r9, aPwcnauthtype; "pWcnAuthType"
0x180029a99  jmp     short loc_180029ABA
0x180029a9b  mov     rbx, [rbp+arg_20]
0x180029a9f  test    rbx, rbx
0x180029aa2  jnz     short loc_180029AD0
0x180029aa4  cmp     r10, r13
0x180029aa7  jz      short loc_180029AC6
0x180029aa9  cmp     byte ptr [r10+19h], 2
0x180029aae  jb      short loc_180029AC6
0x180029ab0  lea     edx, [rbx+1Eh]
0x180029ab3  lea     r9, aPwcnciphertype; "pWcnCipherType"
0x180029aba  mov     rcx, [r10+10h]
0x180029abe  mov     r8, r11
0x180029ac1  call    WPP_SF_s
0x180029ac6  mov     eax, 80004003h
0x180029acb  jmp     loc_180029D41
0x180029ad0  lea     rax, [rbp+arg_0]
0x180029ad4  mov     r8, rsi
0x180029ad7  mov     [rsp+70h+var_28], rax
0x180029adc  lea     r9, [rbp+var_C]
0x180029ae0  lea     rax, [rbp+var_1C]
0x180029ae4  mov     rcx, r14
0x180029ae7  mov     [rsp+70h+var_30], rax
0x180029aec  lea     rdx, [rbp+pMemory]
0x180029af0  lea     rax, [rbp+var_20]
0x180029af4  mov     [rsp+70h+var_38], rax
0x180029af9  lea     rax, [rbp+var_18]
0x180029afd  mov     [rsp+70h+var_40], rax
0x180029b02  lea     rax, [rbp+var_14]
0x180029b06  mov     [rsp+70h+var_48], rax
0x180029b0b  lea     rax, [rbp+var_10]
0x180029b0f  mov     [rsp+70h+var_50], rax
0x180029b14  call    cs:__imp_WlanParseProfileXmlBasicSettings
0x180029b1a  test    eax, eax
0x180029b1c  jz      short loc_180029B6F
0x180029b1e  jg      short loc_180029B24
0x180029b20  mov     ebx, eax
0x180029b22  jmp     short loc_180029B2D
0x180029b24  movzx   ebx, ax
0x180029b27  or      ebx, 80070000h
0x180029b2d  or      ebx, 80000000h
0x180029b33  mov     r10, cs:WPP_GLOBAL_Control
0x180029b3a  cmp     r10, r13
0x180029b3d  jz      loc_180029CF5
0x180029b43  cmp     byte ptr [r10+19h], 2
0x180029b48  jb      loc_180029CF5
0x180029b4e  mov     rcx, [r10+10h]
0x180029b52  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029b59  mov     edx, 1Fh
0x180029b5e  mov     dword ptr [rsp+70h+var_50], ebx
0x180029b62  mov     r9d, eax
0x180029b65  call    WPP_SF_Dd
0x180029b6a  jmp     loc_180029CEE
0x180029b6f  cmp     [rbp+arg_0], 0
0x180029b73  jz      short loc_180029BB9
0x180029b75  mov     ebx, 80070032h
0x180029b7a  mov     r10, cs:WPP_GLOBAL_Control
0x180029b81  cmp     r10, r13
0x180029b84  jz      loc_180029CF5
0x180029b8a  cmp     byte ptr [r10+19h], 2
0x180029b8f  jb      loc_180029CF5
0x180029b95  xor     ecx, ecx; int
0x180029b97  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029b9c  mov     rcx, [r10+10h]
0x180029ba0  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029ba7  mov     edx, 20h ; ' '
0x180029bac  mov     r9, rax
0x180029baf  call    WPP_SF_s
0x180029bb4  jmp     loc_180029CEE
0x180029bb9  mov     r11d, [rbp+var_20]
0x180029bbd  mov     edx, 4
0x180029bc2  mov     ecx, r11d
0x180029bc5  sub     ecx, 1
0x180029bc8  jz      short loc_180029C36
0x180029bca  sub     ecx, 1
0x180029bcd  jz      short loc_180029C32
0x180029bcf  sub     ecx, 2
0x180029bd2  jz      short loc_180029C2A
0x180029bd4  cmp     ecx, 3
0x180029bd7  jz      short loc_180029C22
0x180029bd9  mov     ebx, 80070032h
0x180029bde  mov     r10, cs:WPP_GLOBAL_Control
0x180029be5  cmp     r10, r13
0x180029be8  jz      loc_180029CF5
0x180029bee  cmp     byte ptr [r10+19h], 2
0x180029bf3  jb      loc_180029CF5
0x180029bf9  xor     ecx, ecx; int
0x180029bfb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029c00  mov     edx, 21h ; '!'
0x180029c05  mov     rcx, [r10+10h]
0x180029c09  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029c10  mov     r9, rax
0x180029c13  mov     dword ptr [rsp+70h+var_50], r11d
0x180029c18  call    WPP_SF_sd
0x180029c1d  jmp     loc_180029CEE
0x180029c22  mov     dword ptr [rdi], 20h ; ' '
0x180029c28  jmp     short loc_180029C3C
0x180029c2a  mov     dword ptr [rdi], 2
0x180029c30  jmp     short loc_180029C3C
0x180029c32  mov     [rdi], edx
0x180029c34  jmp     short loc_180029C3C
0x180029c36  mov     dword ptr [rdi], 1
0x180029c3c  mov     r11d, [rbp+var_1C]
0x180029c40  mov     ecx, r11d
0x180029c43  test    r11d, r11d
0x180029c46  jz      short loc_180029CA6
0x180029c48  sub     ecx, 1
0x180029c4b  jz      short loc_180029C9E
0x180029c4d  sub     ecx, 1
0x180029c50  jz      short loc_180029C9A
0x180029c52  sub     ecx, 2
0x180029c55  jz      short loc_180029C92
0x180029c57  sub     ecx, 1
0x180029c5a  jz      short loc_180029C9E
0x180029c5c  sub     ecx, 3
0x180029c5f  jz      short loc_180029C92
0x180029c61  cmp     ecx, 0F9h
0x180029c67  jz      short loc_180029C9E
0x180029c69  mov     ebx, 80070032h
0x180029c6e  mov     r10, cs:WPP_GLOBAL_Control
0x180029c75  cmp     r10, r13
0x180029c78  jz      short loc_180029CF5
0x180029c7a  cmp     byte ptr [r10+19h], 2
0x180029c7f  jb      short loc_180029CF5
0x180029c81  xor     ecx, ecx; int
0x180029c83  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029c88  mov     edx, 22h ; '"'
0x180029c8d  jmp     loc_180029C05
0x180029c92  mov     dword ptr [rbx], 8
0x180029c98  jmp     short loc_180029CAC
0x180029c9a  mov     [rbx], edx
0x180029c9c  jmp     short loc_180029CAC
0x180029c9e  mov     dword ptr [rbx], 2
0x180029ca4  jmp     short loc_180029CAC
0x180029ca6  mov     dword ptr [rbx], 1
0x180029cac  mov     r8, [rbp+pMemory]; unsigned __int16 *
0x180029cb0  mov     edx, 100h; unsigned __int64
0x180029cb5  mov     rcx, r15; unsigned __int16 *
0x180029cb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029cbd  mov     ebx, eax
0x180029cbf  test    eax, eax
0x180029cc1  jns     short loc_180029CEE
0x180029cc3  mov     r10, cs:WPP_GLOBAL_Control
0x180029cca  cmp     r10, r13
0x180029ccd  jz      short loc_180029CF5
0x180029ccf  cmp     byte ptr [r10+19h], 2
0x180029cd4  jb      short loc_180029CF5
0x180029cd6  mov     rcx, [r10+10h]
0x180029cda  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029ce1  mov     edx, 23h ; '#'
0x180029ce6  mov     r9d, eax
0x180029ce9  call    WPP_SF_d
0x180029cee  mov     r10, cs:WPP_GLOBAL_Control
0x180029cf5  mov     rcx, [rbp+pMemory]; pMemory
0x180029cf9  test    rcx, rcx
0x180029cfc  jz      short loc_180029D0B
0x180029cfe  call    cs:__imp_WlanFreeMemory
0x180029d04  mov     r10, cs:WPP_GLOBAL_Control
0x180029d0b  cmp     r10, r13
0x180029d0e  jz      short loc_180029D3F
0x180029d10  test    ebx, ebx
0x180029d12  js      short loc_180029D1B
0x180029d14  cmp     byte ptr [r10+19h], 6
0x180029d19  jb      short loc_180029D3F
0x180029d1b  or      ecx, 0FFFFFFFFh; int
0x180029d1e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029d23  mov     rcx, [r10+10h]
0x180029d27  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029d2e  mov     edx, 24h ; '$'
0x180029d33  mov     dword ptr [rsp+70h+var_50], ebx
0x180029d37  mov     r9, rax
0x180029d3a  call    WPP_SF_sd
0x180029d3f  mov     eax, ebx
0x180029d41  lea     r11, [rsp+70h+var_s0]
0x180029d46  mov     rbx, [r11+38h]
0x180029d4a  mov     rsi, [r11+40h]
0x180029d4e  mov     rsp, r11
0x180029d51  pop     r15
0x180029d53  pop     r14
0x180029d55  pop     r13
0x180029d57  pop     rdi
0x180029d58  pop     rbp
0x180029d59  retn
```
