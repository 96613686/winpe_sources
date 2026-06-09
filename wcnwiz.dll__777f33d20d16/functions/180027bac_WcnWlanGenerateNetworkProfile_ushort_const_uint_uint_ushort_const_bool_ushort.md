# WcnWlanGenerateNetworkProfile(ushort const *,uint,uint,ushort const *,bool,ushort * *)

- ea: `0x180027bac`
- end: `0x180027eb9`
- name: `?WcnWlanGenerateNetworkProfile@@YAJPEBGII0_NPEAPEAG@Z`
- size: `781`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014da0`

## callees

- `0x180001820`
- `0x180001c60`
- `0x18000d630`
- `0x18000e044`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800132e0`
- `0x180026360`
- `0x180026390`
- `0x180027bac`
- `0x1800287dc`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WlanStringToSsid` at `0x180027c80`
- `wlanapi!WlanStringToSsid` at `0x180027c80`
- `wlanapi!WlanFreeMemory` at `0x180027e56`
- `wlanapi!WlanFreeMemory` at `0x180027e56`
- `wlanapi!WlanGenerateProfileXmlBasicSettings` at `0x180027d3b`
- `wlanapi!WlanGenerateProfileXmlBasicSettings` at `0x180027d3b`

## string_xrefs

- `0x180027c57`: `ppProfileXml`

## pseudocode

```c
__int64 __fastcall WcnWlanGenerateNetworkProfile(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        bool a5,
        unsigned __int16 **a6)
{
  _QWORD *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // ebx
  _QWORD *v16; // r10
  __int64 v17; // rdx
  unsigned int WlanCipherFromWcnCipher; // eax
  unsigned int WlanAuthFromWcnAuth; // eax
  int v20; // edx
  __int64 v21; // r10
  int v22; // r11d
  unsigned int v23; // ebx
  int v24; // eax
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // rax
  unsigned __int16 *v27; // rax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  __int64 v32; // r10
  __int64 v33; // rax
  unsigned __int64 v34; // [rsp+50h] [rbp-88h] BYREF
  PVOID pMemory; // [rsp+58h] [rbp-80h] BYREF
  std::bad_alloc *v36; // [rsp+60h] [rbp-78h] BYREF
  _OWORD v37[2]; // [rsp+68h] [rbp-70h] BYREF
  int v38; // [rsp+88h] [rbp-50h]

  memset(v37, 0, sizeof(v37));
  v38 = 0;
  pMemory = 0;
  v34 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 19, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_s(v9[2], 20, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, "ppProfileXml");
    return 2147500035LL;
  }
  v13 = WlanStringToSsid(a1, v37);
  if ( v13 )
  {
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    else
      v14 = v13;
    v15 = v14 | 0x80000000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_36;
    v17 = 21;
    goto LABEL_16;
  }
  WlanCipherFromWcnCipher = GetWlanCipherFromWcnCipher(a3);
  WlanAuthFromWcnAuth = GetWlanAuthFromWcnAuth(a2, WlanCipherFromWcnCipher);
  v13 = WlanGenerateProfileXmlBasicSettings(a1, v37, 1, WlanAuthFromWcnAuth, v20, 0, v21, v22, 0, &pMemory);
  if ( v13 )
  {
    if ( v13 > 0 )
      v23 = (unsigned __int16)v13 | 0x80070000;
    else
      v23 = v13;
    v15 = v23 | 0x80000000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_36;
    v17 = 22;
LABEL_16:
    WPP_SF_Dd(v16[2], v17, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, (unsigned int)v13, v15);
LABEL_35:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  v24 = StringCchLengthW((const unsigned __int16 *)pMemory, 0x1000u, &v34);
  v15 = v24;
  if ( v24 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_36;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_b21d8b9d621e39ee23229db12d609292_Traceguids,
      (unsigned int)v24);
    goto LABEL_35;
  }
  v25 = v34 + 1;
  v26 = 2 * (v34 + 1);
  if ( !is_mul_ok(v34 + 1, 2u) )
    v26 = -1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v27 = (unsigned __int16 *)operator new[](v26);
    *a6 = v27;
    v28 = StringCchCopyW(v27, v25, (const unsigned __int16 *)pMemory);
    v15 = v28;
    if ( v28 >= 0 )
      goto LABEL_34;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v30, (unsigned int)v28, v28);
LABEL_34:
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v36) )
    {
      LODWORD(v34) = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v36 + 8LL))(v36);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, v33);
      }
      v15 = v34;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180027E36);
      goto LABEL_35;
    }
  }
LABEL_36:
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v16 = WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (v15 < 0 || *((_BYTE *)v16 + 25) >= 6u) )
  {
    v31 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v32 + 16), 26, (unsigned int)WPP_b21d8b9d621e39ee23229db12d609292_Traceguids, v31, v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180027bac  mov     r11, rsp
0x180027baf  push    rbx
0x180027bb0  push    rsi
0x180027bb1  push    rdi
0x180027bb2  push    r12
0x180027bb4  push    r14
0x180027bb6  push    r15
0x180027bb8  sub     rsp, 0A8h
0x180027bbf  mov     rax, cs:__security_cookie
0x180027bc6  xor     rax, rsp
0x180027bc9  mov     [rsp+0D8h+var_48], rax
0x180027bd1  mov     rsi, r9
0x180027bd4  mov     r12d, r8d
0x180027bd7  mov     r15d, edx
0x180027bda  mov     rbx, rcx
0x180027bdd  mov     r14, [rsp+0D8h+arg_28]
0x180027be5  xorps   xmm0, xmm0
0x180027be8  xor     eax, eax
0x180027bea  movups  [rsp+0D8h+var_70], xmm0
0x180027bef  movups  [rsp+0D8h+var_60], xmm0
0x180027bf4  mov     [r11-50h], eax
0x180027bf8  mov     [r11-80h], rax
0x180027bfc  mov     [rsp+0D8h+var_88], rax
0x180027c01  lea     rdi, WPP_GLOBAL_Control
0x180027c08  mov     r10, cs:WPP_GLOBAL_Control
0x180027c0f  cmp     r10, rdi
0x180027c12  jz      short loc_180027C42
0x180027c14  cmp     byte ptr [r10+19h], 6
0x180027c19  jb      short loc_180027C42
0x180027c1b  lea     ecx, [rax+1]; int
0x180027c1e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180027c23  mov     edx, 13h
0x180027c28  mov     r9, rax
0x180027c2b  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027c32  mov     rcx, [r10+10h]
0x180027c36  call    WPP_SF_s
0x180027c3b  mov     r10, cs:WPP_GLOBAL_Control
0x180027c42  test    r14, r14
0x180027c45  jnz     short loc_180027C78
0x180027c47  cmp     r10, rdi
0x180027c4a  jz      short loc_180027C6E
0x180027c4c  cmp     byte ptr [r10+19h], 2
0x180027c51  jb      short loc_180027C6E
0x180027c53  lea     edx, [r14+14h]
0x180027c57  lea     r9, aPpprofilexml; "ppProfileXml"
0x180027c5e  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027c65  mov     rcx, [r10+10h]
0x180027c69  call    WPP_SF_s
0x180027c6e  mov     eax, 80004003h
0x180027c73  jmp     loc_180027E98
0x180027c78  lea     rdx, [rsp+0D8h+var_70]
0x180027c7d  mov     rcx, rbx
0x180027c80  call    cs:__imp_WlanStringToSsid
0x180027c86  test    eax, eax
0x180027c88  jz      short loc_180027CDB
0x180027c8a  jg      short loc_180027C90
0x180027c8c  mov     ebx, eax
0x180027c8e  jmp     short loc_180027C99
0x180027c90  movzx   ebx, ax
0x180027c93  or      ebx, 80070000h
0x180027c99  or      ebx, 80000000h
0x180027c9f  mov     r10, cs:WPP_GLOBAL_Control
0x180027ca6  cmp     r10, rdi
0x180027ca9  jz      loc_180027E48
0x180027caf  cmp     byte ptr [r10+19h], 2
0x180027cb4  jb      loc_180027E48
0x180027cba  mov     edx, 15h
0x180027cbf  mov     [rsp+0D8h+var_B8], ebx
0x180027cc3  mov     r9d, eax
0x180027cc6  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027ccd  mov     rcx, [r10+10h]
0x180027cd1  call    WPP_SF_Dd
0x180027cd6  jmp     loc_180027E41
0x180027cdb  movzx   r11d, [rsp+0D8h+arg_20]
0x180027ce4  movzx   eax, word ptr [rsi]
0x180027ce7  neg     ax
0x180027cea  sbb     r10, r10
0x180027ced  and     r10, rsi
0x180027cf0  mov     ecx, r12d
0x180027cf3  call    GetWlanCipherFromWcnCipher
0x180027cf8  mov     edx, eax
0x180027cfa  mov     ecx, r15d
0x180027cfd  call    GetWlanAuthFromWcnAuth
0x180027d02  mov     r9d, eax
0x180027d05  lea     rax, [rsp+0D8h+pMemory]
0x180027d0a  mov     [rsp+0D8h+var_90], rax
0x180027d0f  mov     [rsp+0D8h+var_98], 0
0x180027d17  mov     [rsp+0D8h+var_A0], r11d
0x180027d1c  mov     [rsp+0D8h+var_A8], r10
0x180027d21  mov     [rsp+0D8h+var_B0], 0
0x180027d29  mov     [rsp+0D8h+var_B8], edx
0x180027d2d  mov     r8d, 1
0x180027d33  lea     rdx, [rsp+0D8h+var_70]
0x180027d38  mov     rcx, rbx
0x180027d3b  call    cs:__imp_WlanGenerateProfileXmlBasicSettings
0x180027d41  test    eax, eax
0x180027d43  jz      short loc_180027D7F
0x180027d45  jg      short loc_180027D4B
0x180027d47  mov     ebx, eax
0x180027d49  jmp     short loc_180027D54
0x180027d4b  movzx   ebx, ax
0x180027d4e  or      ebx, 80070000h
0x180027d54  or      ebx, 80000000h
0x180027d5a  mov     r10, cs:WPP_GLOBAL_Control
0x180027d61  cmp     r10, rdi
0x180027d64  jz      loc_180027E48
0x180027d6a  cmp     byte ptr [r10+19h], 2
0x180027d6f  jb      loc_180027E48
0x180027d75  mov     edx, 16h
0x180027d7a  jmp     loc_180027CBF
0x180027d7f  lea     r8, [rsp+0D8h+var_88]; unsigned __int64 *
0x180027d84  mov     edx, 1000h; unsigned __int64
0x180027d89  mov     rcx, [rsp+0D8h+pMemory]; unsigned __int16 *
0x180027d8e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180027d93  mov     ebx, eax
0x180027d95  test    eax, eax
0x180027d97  jns     short loc_180027DCE
0x180027d99  mov     r10, cs:WPP_GLOBAL_Control
0x180027da0  cmp     r10, rdi
0x180027da3  jz      loc_180027E48
0x180027da9  cmp     byte ptr [r10+19h], 2
0x180027dae  jb      loc_180027E48
0x180027db4  mov     edx, 17h
0x180027db9  mov     r9d, eax
0x180027dbc  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027dc3  mov     rcx, [r10+10h]
0x180027dc7  call    WPP_SF_d
0x180027dcc  jmp     short loc_180027E41
0x180027dce  mov     rbx, [rsp+0D8h+var_88]
0x180027dd3  inc     rbx
0x180027dd6  mov     eax, 2
0x180027ddb  mul     rbx
0x180027dde  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180027de5  cmovb   rax, rsi
0x180027de9  mov     rcx, rax; unsigned __int64
0x180027dec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027df1  mov     [r14], rax
0x180027df4  mov     r8, [rsp+0D8h+pMemory]; unsigned __int16 *
0x180027df9  mov     rdx, rbx; unsigned __int64
0x180027dfc  mov     rcx, rax; unsigned __int16 *
0x180027dff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027e04  mov     ebx, eax
0x180027e06  test    eax, eax
0x180027e08  jns     short loc_180027E2D
0x180027e0a  mov     r10, cs:WPP_GLOBAL_Control
0x180027e11  cmp     r10, rdi
0x180027e14  jz      short loc_180027E4C
0x180027e16  cmp     byte ptr [r10+19h], 2
0x180027e1b  jb      short loc_180027E4C
0x180027e1d  mov     [rsp+0D8h+var_B8], eax
0x180027e21  mov     r9d, eax
0x180027e24  mov     rcx, [r10+10h]
0x180027e28  call    WPP_SF_dd
0x180027e2d  mov     r10, cs:WPP_GLOBAL_Control
0x180027e34  jmp     short loc_180027E4C
0x180027e36  lea     rdi, WPP_GLOBAL_Control
0x180027e3d  mov     ebx, dword ptr [rsp+0D8h+var_88]
0x180027e41  mov     r10, cs:WPP_GLOBAL_Control
0x180027e48  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027e4c  mov     rcx, [rsp+0D8h+pMemory]; pMemory
0x180027e51  test    rcx, rcx
0x180027e54  jz      short loc_180027E63
0x180027e56  call    cs:__imp_WlanFreeMemory
0x180027e5c  mov     r10, cs:WPP_GLOBAL_Control
0x180027e63  cmp     r10, rdi
0x180027e66  jz      short loc_180027E96
0x180027e68  test    ebx, ebx
0x180027e6a  js      short loc_180027E73
0x180027e6c  cmp     byte ptr [r10+19h], 6
0x180027e71  jb      short loc_180027E96
0x180027e73  mov     ecx, esi; int
0x180027e75  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180027e7a  mov     edx, 1Ah
0x180027e7f  mov     [rsp+0D8h+var_B8], ebx
0x180027e83  mov     r9, rax
0x180027e86  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180027e8d  mov     rcx, [r10+10h]
0x180027e91  call    WPP_SF_sd
0x180027e96  mov     eax, ebx
0x180027e98  mov     rcx, [rsp+0D8h+var_48]
0x180027ea0  xor     rcx, rsp; StackCookie
0x180027ea3  call    __security_check_cookie
0x180027ea8  add     rsp, 0A8h
0x180027eaf  pop     r15
0x180027eb1  pop     r14
0x180027eb3  pop     r12
0x180027eb5  pop     rdi
0x180027eb6  pop     rsi
0x180027eb7  pop     rbx
0x180027eb8  retn
```
