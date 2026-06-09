# WcnWlanCreateNetworkSignatureForProfile(_DOT11_SSID const *,ushort const *,bool,_GUID const *,_GUID *)

- ea: `0x1800279ac`
- end: `0x180027ba5`
- name: `?WcnWlanCreateNetworkSignatureForProfile@@YAJPEBU_DOT11_SSID@@PEBG_NPEBU_GUID@@PEAU2@@Z`
- size: `505`
- prototype: `__int64 __fastcall(const struct _DOT11_SSID *, const unsigned __int16 *, bool, const struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800100b0`
- `0x1800165cc`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d630`
- `0x18000e0a0`
- `0x18000e1dc`
- `0x1800279ac`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180027a57`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180027a57`
- `wlanapi!AcmGenerateConnectionIdForNotification` at `0x180027afa`
- `wlanapi!AcmGenerateConnectionIdForNotification` at `0x180027afa`

## pseudocode

```c
__int64 __fastcall WcnWlanCreateNetworkSignatureForProfile(
        const struct _DOT11_SSID *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const struct _GUID *a4,
        struct _GUID *a5)
{
  const char *Indent; // rax
  __int64 v8; // r10
  int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // ebx
  _QWORD *v12; // r10
  __int64 v13; // rdx
  int v14; // eax
  __int128 v15; // xmm1
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // r10
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[512]; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v24; // [rsp+254h] [rbp+154h]
  __int128 v25; // [rsp+264h] [rbp+164h]
  int v26; // [rsp+274h] [rbp+174h]
  int v27; // [rsp+278h] [rbp+178h]
  __int64 v28; // [rsp+27Ch] [rbp+17Ch]

  memset_0(&v22, 0, 0x23Cu);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 31, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, Indent);
  }
  v22 = 0;
  v20 = 256;
  v9 = WlanUtf8SsidToDisplayName(a1, 1, v23, &v20);
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v11 = v10 | 0x80000000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 32;
LABEL_11:
        WPP_SF_Dd(v12[2], v13, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, (unsigned int)v9, v11);
LABEL_20:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      goto LABEL_21;
    }
  }
  else
  {
    v14 = *(_DWORD *)&a1->ucSSID[28];
    v15 = *(_OWORD *)&a1->ucSSID[12];
    v24 = *(_OWORD *)&a1->uSSIDLength;
    v26 = v14;
    v27 = 1;
    v21 = 0;
    v28 = 1;
    v25 = v15;
    v9 = AcmGenerateConnectionIdForNotification(a4, &v22, &v21);
    if ( !v9 )
    {
      v11 = 0;
      *a5 = v21;
      goto LABEL_20;
    }
    if ( v9 > 0 )
      v16 = (unsigned __int16)v9 | 0x80070000;
    else
      v16 = v9;
    v11 = v16 | 0x80000000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 33;
        goto LABEL_11;
      }
LABEL_21:
      if ( v12 != &WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)v12 + 25) >= 6u) )
      {
        v17 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v18 + 16), 34, (unsigned int)WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, v17, v11);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800279ac  mov     [rsp-8+arg_8], rbx
0x1800279b1  mov     [rsp-8+arg_10], rsi
0x1800279b6  push    rbp
0x1800279b7  push    rdi
0x1800279b8  push    r15
0x1800279ba  lea     rbp, [rsp-1A0h]
0x1800279c2  sub     rsp, 2A0h
0x1800279c9  mov     rax, cs:__security_cookie
0x1800279d0  xor     rax, rsp
0x1800279d3  mov     [rbp+1B0h+var_20], rax
0x1800279da  mov     rdi, [rbp+1B0h+arg_20]
0x1800279e1  mov     rbx, rcx
0x1800279e4  lea     rcx, [rsp+2B0h+var_260]; void *
0x1800279e9  xor     edx, edx; Val
0x1800279eb  mov     r8d, 23Ch; Size
0x1800279f1  mov     rsi, r9
0x1800279f4  call    memset_0
0x1800279f9  mov     r10, cs:WPP_GLOBAL_Control
0x180027a00  lea     r15, WPP_GLOBAL_Control
0x180027a07  cmp     r10, r15
0x180027a0a  jz      short loc_180027A35
0x180027a0c  cmp     byte ptr [r10+19h], 6
0x180027a11  jb      short loc_180027A35
0x180027a13  mov     ecx, 1; int
0x180027a18  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180027a1d  mov     rcx, [r10+10h]
0x180027a21  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027a28  mov     edx, 1Fh
0x180027a2d  mov     r9, rax
0x180027a30  call    WPP_SF_s
0x180027a35  lea     r9, [rsp+2B0h+var_280]
0x180027a3a  mov     [rsp+2B0h+var_260], 0
0x180027a42  lea     r8, [rsp+2B0h+var_25C]
0x180027a47  mov     [rsp+2B0h+var_280], 100h
0x180027a4f  mov     edx, 1
0x180027a54  mov     rcx, rbx
0x180027a57  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180027a5d  test    eax, eax
0x180027a5f  jz      short loc_180027AB2
0x180027a61  jg      short loc_180027A67
0x180027a63  mov     ebx, eax
0x180027a65  jmp     short loc_180027A70
0x180027a67  movzx   ebx, ax
0x180027a6a  or      ebx, 80070000h
0x180027a70  or      ebx, 80000000h
0x180027a76  mov     r10, cs:WPP_GLOBAL_Control
0x180027a7d  cmp     r10, r15
0x180027a80  jz      loc_180027B7C
0x180027a86  cmp     byte ptr [r10+19h], 2
0x180027a8b  jb      loc_180027B48
0x180027a91  mov     edx, 20h ; ' '
0x180027a96  mov     rcx, [r10+10h]
0x180027a9a  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027aa1  mov     r9d, eax
0x180027aa4  mov     [rsp+2B0h+var_290], ebx
0x180027aa8  call    WPP_SF_Dd
0x180027aad  jmp     loc_180027B41
0x180027ab2  movups  xmm0, xmmword ptr [rbx]
0x180027ab5  mov     eax, [rbx+20h]
0x180027ab8  lea     r8, [rsp+2B0h+var_278]
0x180027abd  movups  xmm1, xmmword ptr [rbx+10h]
0x180027ac1  lea     rdx, [rsp+2B0h+var_260]
0x180027ac6  mov     rcx, rsi
0x180027ac9  movups  [rbp+1B0h+var_5C], xmm0
0x180027ad0  mov     [rbp+1B0h+var_3C], eax
0x180027ad6  xorps   xmm0, xmm0
0x180027ad9  mov     [rbp+1B0h+var_38], 1
0x180027ae3  movups  xmmword ptr [rsp+2B0h+var_278.Data1], xmm0
0x180027ae8  mov     [rbp+1B0h+var_34], 1
0x180027af3  movups  [rbp+1B0h+var_4C], xmm1
0x180027afa  call    cs:__imp_AcmGenerateConnectionIdForNotification
0x180027b00  test    eax, eax
0x180027b02  jz      short loc_180027B36
0x180027b04  jg      short loc_180027B0A
0x180027b06  mov     ebx, eax
0x180027b08  jmp     short loc_180027B13
0x180027b0a  movzx   ebx, ax
0x180027b0d  or      ebx, 80070000h
0x180027b13  or      ebx, 80000000h
0x180027b19  mov     r10, cs:WPP_GLOBAL_Control
0x180027b20  cmp     r10, r15
0x180027b23  jz      short loc_180027B7C
0x180027b25  cmp     byte ptr [r10+19h], 2
0x180027b2a  jb      short loc_180027B48
0x180027b2c  mov     edx, 21h ; '!'
0x180027b31  jmp     loc_180027A96
0x180027b36  movups  xmm0, xmmword ptr [rsp+2B0h+var_278.Data1]
0x180027b3b  xor     ebx, ebx
0x180027b3d  movdqu  xmmword ptr [rdi], xmm0
0x180027b41  mov     r10, cs:WPP_GLOBAL_Control
0x180027b48  cmp     r10, r15
0x180027b4b  jz      short loc_180027B7C
0x180027b4d  test    ebx, ebx
0x180027b4f  js      short loc_180027B58
0x180027b51  cmp     byte ptr [r10+19h], 6
0x180027b56  jb      short loc_180027B7C
0x180027b58  or      ecx, 0FFFFFFFFh; int
0x180027b5b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180027b60  mov     rcx, [r10+10h]
0x180027b64  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027b6b  mov     edx, 22h ; '"'
0x180027b70  mov     [rsp+2B0h+var_290], ebx
0x180027b74  mov     r9, rax
0x180027b77  call    WPP_SF_sd
0x180027b7c  mov     eax, ebx
0x180027b7e  mov     rcx, [rbp+1B0h+var_20]
0x180027b85  xor     rcx, rsp; StackCookie
0x180027b88  call    __security_check_cookie
0x180027b8d  lea     r11, [rsp+2B0h+var_10]
0x180027b95  mov     rbx, [r11+28h]
0x180027b99  mov     rsi, [r11+30h]
0x180027b9d  mov     rsp, r11
0x180027ba0  pop     r15
0x180027ba2  pop     rdi
0x180027ba3  pop     rbp
0x180027ba4  retn
```
