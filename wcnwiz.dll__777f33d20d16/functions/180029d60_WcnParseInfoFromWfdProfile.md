# WcnParseInfoFromWfdProfile

- ea: `0x180029d60`
- end: `0x18002a313`
- name: `WcnParseInfoFromWfdProfile`
- size: `1459`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64, _DWORD *, _DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800296a4`

## callees

- `0x180001820`
- `0x180002294`
- `0x180002981`
- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800132e0`
- `0x180029d60`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WFDFreeMemoryInt` at `0x18002a2a8`
- `wlanapi!WFDFreeMemoryInt` at `0x18002a2a8`
- `wlanapi!WFDGetProfileKeyInfoInt` at `0x18002a132`
- `wlanapi!WFDGetProfileKeyInfoInt` at `0x18002a132`
- `wlanapi!WFDParseProfileXmlInt` at `0x180029eb4`
- `wlanapi!WFDParseProfileXmlInt` at `0x180029eb4`

## string_xrefs

- `0x180029e35`: `pSsid`

## pseudocode

```c
__int64 __fastcall WcnParseInfoFromWfdProfile(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6,
        _QWORD *a7)
{
  _BYTE *v11; // r10
  const char *Indent; // rax
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rdx
  const char *v16; // r9
  int v18; // eax
  unsigned int v19; // ebx
  signed int v20; // ebx
  _QWORD *v21; // r10
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // r10
  char v25; // r11
  int v26; // edx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // eax
  __int64 v34; // rdi
  const char *v35; // rax
  __int64 v36; // r10
  unsigned int v37; // ebx
  const char *v38; // rax
  __int64 v39; // r10
  __int64 v40; // rdx
  __int64 v41; // rdi
  unsigned int v42; // eax
  __int64 v43; // r10
  __int64 v44; // [rsp+30h] [rbp-61h] BYREF
  int v45; // [rsp+38h] [rbp-59h] BYREF
  unsigned int Size; // [rsp+3Ch] [rbp-55h] BYREF
  _BYTE Size_4[64]; // [rsp+40h] [rbp-51h] BYREF

  v44 = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v13 + 16), 10, v14, Indent);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 11;
    v16 = "wszNetworkProfile";
LABEL_24:
    WPP_SF_s(*((_QWORD *)v11 + 2), v15, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v16);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 12;
    v16 = "pSsid";
    goto LABEL_24;
  }
  if ( !a4 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 13;
    v16 = "pWcnAuthType";
    goto LABEL_24;
  }
  if ( !a5 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 14;
    v16 = "pWcnCipherType";
    goto LABEL_24;
  }
  if ( !a6 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 15;
    v16 = "pPassphrase";
    goto LABEL_24;
  }
  v18 = WFDParseProfileXmlInt(a1, &v44, 0);
  if ( v18 )
  {
    if ( v18 > 0 )
      v19 = (unsigned __int16)v18 | 0x80070000;
    else
      v19 = v18;
    v20 = v19 | 0x80000000;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_95;
    v22 = 16;
    goto LABEL_33;
  }
  if ( !*(_DWORD *)(v44 + 136) || *(_DWORD *)(v44 + 148) == 1 )
  {
    *a4 = 1;
  }
  else
  {
    switch ( *(_DWORD *)(v44 + 148) )
    {
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
        v20 = -2147024846;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_95;
        v23 = (unsigned int)GetIndent(0);
        v26 = 17;
        goto LABEL_42;
    }
  }
  if ( *(_DWORD *)(v44 + 144) )
  {
    v27 = *(_DWORD *)(v44 + 152);
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( !v29 )
        {
          *a5 = 4;
          goto LABEL_62;
        }
        v30 = v29 - 2;
        if ( !v30 )
          goto LABEL_58;
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 3;
          if ( v32 )
          {
            if ( v32 != 249 )
            {
              v20 = -2147024846;
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_95;
              v23 = (unsigned int)GetIndent(0);
              v26 = 18;
              goto LABEL_42;
            }
            goto LABEL_60;
          }
LABEL_58:
          *a5 = 8;
          goto LABEL_62;
        }
      }
LABEL_60:
      *a5 = 2;
      goto LABEL_62;
    }
  }
  *a5 = 1;
LABEL_62:
  v33 = StringCchCopyW(a2, 0x100u, (const unsigned __int16 *)(v44 + 4));
  v20 = v33;
  if ( v33 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_95;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
      (unsigned int)v33);
    goto LABEL_94;
  }
  v34 = v44;
  *(_OWORD *)a3 = *(_OWORD *)(v44 + 80);
  *(_OWORD *)(a3 + 16) = *(_OWORD *)(v34 + 96);
  *(_DWORD *)(a3 + 32) = *(_DWORD *)(v34 + 112);
  if ( !*(_DWORD *)(v34 + 164) )
  {
    if ( *(_BYTE *)(v34 + 168) > 0x40u )
    {
      v20 = -2147024846;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_95;
      v23 = (unsigned int)GetIndent(0);
      v26 = 23;
LABEL_42:
      WPP_SF_sd(*(_QWORD *)(v24 + 16), v26, (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v23, v25);
      goto LABEL_94;
    }
    if ( !*(_DWORD *)(v34 + 160) )
    {
      v20 = -2147024846;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_95;
      v38 = GetIndent(0);
      v40 = 24;
LABEL_81:
      WPP_SF_s(*(_QWORD *)(v39 + 16), v40, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v38);
      goto LABEL_94;
    }
    memcpy_0((void *)(a6 + 16), (const void *)(v34 + 169), *(unsigned __int8 *)(v34 + 168));
    v41 = *(unsigned __int8 *)(v34 + 168);
LABEL_92:
    *(_QWORD *)(a6 + 8) = v41;
    *(_BYTE *)a6 = 1;
    if ( a7 )
    {
      *a7 = v44;
      v44 = 0;
    }
    goto LABEL_94;
  }
  v45 = 0;
  memset_0(Size_4, 0, sizeof(Size_4));
  Size = 64;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v35 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v36 + 16), 20, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v35);
  }
  v18 = WFDGetProfileKeyInfoInt(0, v44, &v45, Size_4, &Size);
  if ( !v18 )
  {
    if ( !v45 )
    {
      v20 = -2147024846;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_95;
      v38 = GetIndent(0);
      v40 = 22;
      goto LABEL_81;
    }
    v41 = Size;
    memcpy_0((void *)(a6 + 16), Size_4, Size);
    goto LABEL_92;
  }
  if ( v18 > 0 )
    v37 = (unsigned __int16)v18 | 0x80070000;
  else
    v37 = v18;
  v20 = v37 | 0x80000000;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_95;
  v22 = 21;
LABEL_33:
  WPP_SF_Dd(v21[2], v22, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, (unsigned int)v18, v20);
LABEL_94:
  v21 = WPP_GLOBAL_Control;
LABEL_95:
  if ( v44 )
  {
    WFDFreeMemoryInt(v44);
    v21 = WPP_GLOBAL_Control;
    v44 = 0;
  }
  if ( v21 != &WPP_GLOBAL_Control && (v20 < 0 || *((_BYTE *)v21 + 25) >= 6u) )
  {
    v42 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v43 + 16), 25, (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v42, v20);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180029d60  push    rbp
0x180029d62  push    rbx
0x180029d63  push    rsi
0x180029d64  push    rdi
0x180029d65  push    r12
0x180029d67  push    r13
0x180029d69  push    r14
0x180029d6b  push    r15
0x180029d6d  lea     rbp, [rsp-7]
0x180029d72  sub     rsp, 98h
0x180029d79  mov     rax, cs:__security_cookie
0x180029d80  xor     rax, rsp
0x180029d83  mov     [rbp+3Fh+var_50], rax
0x180029d87  mov     r14, [rbp+3Fh+arg_28]
0x180029d8b  mov     rbx, r9
0x180029d8e  mov     rsi, [rbp+3Fh+arg_20]
0x180029d92  mov     r15, r8
0x180029d95  mov     r12, [rbp+3Fh+arg_30]
0x180029d99  mov     r13, rdx
0x180029d9c  mov     rdi, rcx
0x180029d9f  mov     [rbp+3Fh+var_A0], 0
0x180029da7  mov     r10, cs:WPP_GLOBAL_Control
0x180029dae  lea     rax, WPP_GLOBAL_Control
0x180029db5  lea     r11, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029dbc  cmp     r10, rax
0x180029dbf  jz      short loc_180029DFB
0x180029dc1  cmp     byte ptr [r10+19h], 6
0x180029dc6  jb      short loc_180029DFB
0x180029dc8  mov     ecx, 1; int
0x180029dcd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029dd2  mov     rcx, [r10+10h]
0x180029dd6  mov     edx, 0Ah
0x180029ddb  mov     r9, rax
0x180029dde  mov     r8, r11
0x180029de1  call    WPP_SF_s
0x180029de6  mov     r10, cs:WPP_GLOBAL_Control
0x180029ded  lea     rax, WPP_GLOBAL_Control
0x180029df4  lea     r11, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029dfb  test    rdi, rdi
0x180029dfe  jnz     short loc_180029E20
0x180029e00  cmp     r10, rax
0x180029e03  jz      loc_180029EA0
0x180029e09  cmp     byte ptr [r10+19h], 2
0x180029e0e  jb      loc_180029EA0
0x180029e14  lea     edx, [rdi+0Bh]
0x180029e17  lea     r9, aWsznetworkprof; "wszNetworkProfile"
0x180029e1e  jmp     short loc_180029E94
0x180029e20  test    r15, r15
0x180029e23  jnz     short loc_180029E3E
0x180029e25  cmp     r10, rax
0x180029e28  jz      short loc_180029EA0
0x180029e2a  cmp     byte ptr [r10+19h], 2
0x180029e2f  jb      short loc_180029EA0
0x180029e31  lea     edx, [r15+0Ch]
0x180029e35  lea     r9, aPssid; "pSsid"
0x180029e3c  jmp     short loc_180029E94
0x180029e3e  test    rbx, rbx
0x180029e41  jnz     short loc_180029E5B
0x180029e43  cmp     r10, rax
0x180029e46  jz      short loc_180029EA0
0x180029e48  cmp     byte ptr [r10+19h], 2
0x180029e4d  jb      short loc_180029EA0
0x180029e4f  lea     edx, [rbx+0Dh]
0x180029e52  lea     r9, aPwcnauthtype; "pWcnAuthType"
0x180029e59  jmp     short loc_180029E94
0x180029e5b  test    rsi, rsi
0x180029e5e  jnz     short loc_180029E78
0x180029e60  cmp     r10, rax
0x180029e63  jz      short loc_180029EA0
0x180029e65  cmp     byte ptr [r10+19h], 2
0x180029e6a  jb      short loc_180029EA0
0x180029e6c  lea     edx, [rsi+0Eh]
0x180029e6f  lea     r9, aPwcnciphertype; "pWcnCipherType"
0x180029e76  jmp     short loc_180029E94
0x180029e78  test    r14, r14
0x180029e7b  jnz     short loc_180029EAA
0x180029e7d  cmp     r10, rax
0x180029e80  jz      short loc_180029EA0
0x180029e82  cmp     byte ptr [r10+19h], 2
0x180029e87  jb      short loc_180029EA0
0x180029e89  lea     edx, [r14+0Fh]
0x180029e8d  lea     r9, aPpassphrase; "pPassphrase"
0x180029e94  mov     rcx, [r10+10h]
0x180029e98  mov     r8, r11
0x180029e9b  call    WPP_SF_s
0x180029ea0  mov     eax, 80004003h
0x180029ea5  jmp     loc_18002A2F3
0x180029eaa  xor     r8d, r8d
0x180029ead  lea     rdx, [rbp+3Fh+var_A0]
0x180029eb1  mov     rcx, rdi
0x180029eb4  call    cs:__imp_WFDParseProfileXmlInt
0x180029eba  test    eax, eax
0x180029ebc  jz      short loc_180029F16
0x180029ebe  jg      short loc_180029EC4
0x180029ec0  mov     ebx, eax
0x180029ec2  jmp     short loc_180029ECD
0x180029ec4  movzx   ebx, ax
0x180029ec7  or      ebx, 80070000h
0x180029ecd  or      ebx, 80000000h
0x180029ed3  mov     r10, cs:WPP_GLOBAL_Control
0x180029eda  lea     rsi, WPP_GLOBAL_Control
0x180029ee1  cmp     r10, rsi
0x180029ee4  jz      loc_18002A29C
0x180029eea  cmp     byte ptr [r10+19h], 2
0x180029eef  jb      loc_18002A29C
0x180029ef5  mov     edx, 10h
0x180029efa  mov     rcx, [r10+10h]
0x180029efe  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029f05  mov     r9d, eax
0x180029f08  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180029f0c  call    WPP_SF_Dd
0x180029f11  jmp     loc_18002A295
0x180029f16  mov     rdi, [rbp+3Fh+var_A0]
0x180029f1a  mov     edx, 4
0x180029f1f  cmp     dword ptr [rdi+88h], 0
0x180029f26  jz      loc_180029FAE
0x180029f2c  mov     r11d, [rdi+94h]
0x180029f33  mov     ecx, r11d
0x180029f36  sub     ecx, 1
0x180029f39  jz      short loc_180029FAE
0x180029f3b  sub     ecx, 1
0x180029f3e  jz      short loc_180029FAA
0x180029f40  sub     ecx, 2
0x180029f43  jz      short loc_180029FA2
0x180029f45  cmp     ecx, 3
0x180029f48  jz      short loc_180029F9A
0x180029f4a  mov     ebx, 80070032h
0x180029f4f  mov     r10, cs:WPP_GLOBAL_Control
0x180029f56  lea     rsi, WPP_GLOBAL_Control
0x180029f5d  cmp     r10, rsi
0x180029f60  jz      loc_18002A29C
0x180029f66  cmp     byte ptr [r10+19h], 2
0x180029f6b  jb      loc_18002A29C
0x180029f71  xor     ecx, ecx; int
0x180029f73  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029f78  mov     edx, 11h
0x180029f7d  mov     rcx, [r10+10h]
0x180029f81  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029f88  mov     r9, rax
0x180029f8b  mov     dword ptr [rsp+0D0h+var_B0], r11d
0x180029f90  call    WPP_SF_sd
0x180029f95  jmp     loc_18002A295
0x180029f9a  mov     dword ptr [rbx], 20h ; ' '
0x180029fa0  jmp     short loc_180029FB4
0x180029fa2  mov     dword ptr [rbx], 2
0x180029fa8  jmp     short loc_180029FB4
0x180029faa  mov     [rbx], edx
0x180029fac  jmp     short loc_180029FB4
0x180029fae  mov     dword ptr [rbx], 1
0x180029fb4  mov     rdi, [rbp+3Fh+var_A0]
0x180029fb8  cmp     dword ptr [rdi+90h], 0
0x180029fbf  jz      short loc_18002A03D
0x180029fc1  mov     r11d, [rdi+98h]
0x180029fc8  mov     ecx, r11d
0x180029fcb  test    r11d, r11d
0x180029fce  jz      short loc_18002A03D
0x180029fd0  sub     ecx, 1
0x180029fd3  jz      short loc_18002A035
0x180029fd5  sub     ecx, 1
0x180029fd8  jz      short loc_18002A031
0x180029fda  sub     ecx, 2
0x180029fdd  jz      short loc_18002A029
0x180029fdf  sub     ecx, 1
0x180029fe2  jz      short loc_18002A035
0x180029fe4  sub     ecx, 3
0x180029fe7  jz      short loc_18002A029
0x180029fe9  cmp     ecx, 0F9h
0x180029fef  jz      short loc_18002A035
0x180029ff1  mov     ebx, 80070032h
0x180029ff6  mov     r10, cs:WPP_GLOBAL_Control
0x180029ffd  lea     rsi, WPP_GLOBAL_Control
0x18002a004  cmp     r10, rsi
0x18002a007  jz      loc_18002A29C
0x18002a00d  cmp     byte ptr [r10+19h], 2
0x18002a012  jb      loc_18002A29C
0x18002a018  xor     ecx, ecx; int
0x18002a01a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a01f  mov     edx, 12h
0x18002a024  jmp     loc_180029F7D
0x18002a029  mov     dword ptr [rsi], 8
0x18002a02f  jmp     short loc_18002A043
0x18002a031  mov     [rsi], edx
0x18002a033  jmp     short loc_18002A043
0x18002a035  mov     dword ptr [rsi], 2
0x18002a03b  jmp     short loc_18002A043
0x18002a03d  mov     dword ptr [rsi], 1
0x18002a043  mov     r8, [rbp+3Fh+var_A0]
0x18002a047  mov     rcx, r13; unsigned __int16 *
0x18002a04a  add     r8, rdx; unsigned __int16 *
0x18002a04d  mov     edx, 100h; unsigned __int64
0x18002a052  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a057  mov     ebx, eax
0x18002a059  test    eax, eax
0x18002a05b  jns     short loc_18002A09C
0x18002a05d  mov     r10, cs:WPP_GLOBAL_Control
0x18002a064  lea     rsi, WPP_GLOBAL_Control
0x18002a06b  cmp     r10, rsi
0x18002a06e  jz      loc_18002A29C
0x18002a074  cmp     byte ptr [r10+19h], 2
0x18002a079  jb      loc_18002A29C
0x18002a07f  mov     rcx, [r10+10h]
0x18002a083  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a08a  mov     edx, 13h
0x18002a08f  mov     r9d, eax
0x18002a092  call    WPP_SF_d
0x18002a097  jmp     loc_18002A295
0x18002a09c  mov     rdi, [rbp+3Fh+var_A0]
0x18002a0a0  movups  xmm0, xmmword ptr [rdi+50h]
0x18002a0a4  movups  xmmword ptr [r15], xmm0
0x18002a0a8  movups  xmm1, xmmword ptr [rdi+60h]
0x18002a0ac  movups  xmmword ptr [r15+10h], xmm1
0x18002a0b1  mov     eax, [rdi+70h]
0x18002a0b4  mov     [r15+20h], eax
0x18002a0b8  cmp     dword ptr [rdi+0A4h], 0
0x18002a0bf  jz      loc_18002A1D8
0x18002a0c5  xor     edx, edx; Val
0x18002a0c7  mov     [rbp+3Fh+var_98], 0
0x18002a0ce  lea     rcx, [rbp+3Fh+Size+4]; void *
0x18002a0d2  lea     r8d, [rdx+40h]; Size
0x18002a0d6  call    memset_0
0x18002a0db  mov     dword ptr [rbp+3Fh+Size], 40h ; '@'
0x18002a0e2  mov     r10, cs:WPP_GLOBAL_Control
0x18002a0e9  lea     rsi, WPP_GLOBAL_Control
0x18002a0f0  cmp     r10, rsi
0x18002a0f3  jz      short loc_18002A11B
0x18002a0f5  cmp     byte ptr [r10+19h], 4
0x18002a0fa  jb      short loc_18002A11B
0x18002a0fc  xor     ecx, ecx; int
0x18002a0fe  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a103  mov     rcx, [r10+10h]
0x18002a107  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a10e  mov     edx, 14h
0x18002a113  mov     r9, rax
0x18002a116  call    WPP_SF_s
0x18002a11b  mov     rdx, [rbp+3Fh+var_A0]
0x18002a11f  lea     rax, [rbp+3Fh+Size]
0x18002a123  lea     r9, [rbp+3Fh+Size+4]
0x18002a127  mov     [rsp+0D0h+var_B0], rax
0x18002a12c  lea     r8, [rbp+3Fh+var_98]
0x18002a130  xor     ecx, ecx
0x18002a132  call    cs:__imp_WFDGetProfileKeyInfoInt
0x18002a138  test    eax, eax
0x18002a13a  jz      short loc_18002A176
0x18002a13c  jg      short loc_18002A142
0x18002a13e  mov     ebx, eax
0x18002a140  jmp     short loc_18002A14B
0x18002a142  movzx   ebx, ax
0x18002a145  or      ebx, 80070000h
0x18002a14b  or      ebx, 80000000h
0x18002a151  mov     r10, cs:WPP_GLOBAL_Control
0x18002a158  cmp     r10, rsi
0x18002a15b  jz      loc_18002A29C
0x18002a161  cmp     byte ptr [r10+19h], 2
0x18002a166  jb      loc_18002A29C
0x18002a16c  mov     edx, 15h
0x18002a171  jmp     loc_180029EFA
0x18002a176  cmp     [rbp+3Fh+var_98], 0
0x18002a17a  jnz     short loc_18002A1C0
0x18002a17c  mov     ebx, 80070032h
0x18002a181  mov     r10, cs:WPP_GLOBAL_Control
0x18002a188  cmp     r10, rsi
0x18002a18b  jz      loc_18002A29C
0x18002a191  cmp     byte ptr [r10+19h], 3
0x18002a196  jb      loc_18002A29C
0x18002a19c  xor     ecx, ecx; int
0x18002a19e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a1a3  mov     edx, 16h
0x18002a1a8  mov     rcx, [r10+10h]
0x18002a1ac  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a1b3  mov     r9, rax
0x18002a1b6  call    WPP_SF_s
0x18002a1bb  jmp     loc_18002A295
0x18002a1c0  mov     edi, dword ptr [rbp+3Fh+Size]
0x18002a1c3  lea     rcx, [r14+10h]; void *
0x18002a1c7  mov     r8d, edi; Size
0x18002a1ca  lea     rdx, [rbp+3Fh+Size+4]; Src
0x18002a1ce  call    memcpy_0
0x18002a1d3  jmp     loc_18002A278
0x18002a1d8  movzx   r11d, byte ptr [rdi+0A8h]
0x18002a1e0  cmp     r11b, 40h ; '@'
0x18002a1e4  jbe     short loc_18002A21E
0x18002a1e6  mov     ebx, 80070032h
0x18002a1eb  mov     r10, cs:WPP_GLOBAL_Control
0x18002a1f2  lea     rsi, WPP_GLOBAL_Control
0x18002a1f9  cmp     r10, rsi
0x18002a1fc  jz      loc_18002A29C
0x18002a202  cmp     byte ptr [r10+19h], 2
0x18002a207  jb      loc_18002A29C
0x18002a20d  xor     ecx, ecx; int
0x18002a20f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a214  mov     edx, 17h
0x18002a219  jmp     loc_180029F7D
0x18002a21e  cmp     dword ptr [rdi+0A0h], 0
0x18002a225  jnz     short loc_18002A257
0x18002a227  mov     ebx, 80070032h
0x18002a22c  mov     r10, cs:WPP_GLOBAL_Control
0x18002a233  lea     rsi, WPP_GLOBAL_Control
0x18002a23a  cmp     r10, rsi
0x18002a23d  jz      short loc_18002A29C
0x18002a23f  cmp     byte ptr [r10+19h], 3
  ... truncated ...
```
