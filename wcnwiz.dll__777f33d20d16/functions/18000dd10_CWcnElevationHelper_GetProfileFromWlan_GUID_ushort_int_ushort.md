# CWcnElevationHelper::GetProfileFromWlan(_GUID,ushort *,int,ushort * *)

- ea: `0x18000dd10`
- end: `0x18000e03c`
- name: `?GetProfileFromWlan@CWcnElevationHelper@@UEAAJU_GUID@@PEAGHPEAPEAG@Z`
- size: `812`
- prototype: `__int64 __fastcall(CWcnElevationHelper *this, struct _GUID *, unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000d630`
- `0x18000dd10`
- `0x18000e044`
- `0x18000e0a0`
- `0x18000e0ec`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18002de1c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000df3c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df3c`
- `wlanapi!WlanCloseHandle` at `0x18000dfa0`
- `wlanapi!WlanCloseHandle` at `0x18000dfa0`
- `wlanapi!WlanOpenHandle` at `0x18000dde8`
- `wlanapi!WlanOpenHandle` at `0x18000dde8`
- `wlanapi!WlanGetProfile` at `0x18000de67`
- `wlanapi!WlanGetProfile` at `0x18000de67`
- `wlanapi!WlanFreeMemory` at `0x18000df88`
- `wlanapi!WlanFreeMemory` at `0x18000df88`

## string_xrefs

- `0x18000ddb1`: `pbstrXmlProfile`
- `0x18000df65`: `*pbstrXmlProfile`

## pseudocode

```c
__int64 __fastcall CWcnElevationHelper::GetProfileFromWlan(
        CWcnElevationHelper *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5)
{
  DWORD v5; // eax
  _QWORD *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  signed int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  _QWORD *v16; // r10
  signed int Profile; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // ebx
  const char *v21; // rax
  __int64 v22; // rdx
  const char *v23; // r9
  int v24; // eax
  unsigned __int16 *v25; // rax
  signed int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // eax
  __int64 v29; // r10
  DWORD pdwFlags; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR psz; // [rsp+48h] [rbp-28h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+50h] [rbp-20h] BYREF
  void *phClientHandle; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-10h] BYREF

  v5 = 0;
  pdwFlags = 0;
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  psz = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 10, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, Indent);
    v5 = pdwFlags;
    v9 = WPP_GLOBAL_Control;
  }
  if ( a5 )
  {
    *a5 = 0;
    if ( a4 )
      pdwFlags = v5 | 4;
    v13 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      else
        v14 = v13;
      v15 = v14 | 0x80000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids,
          (unsigned int)v13,
          v15);
LABEL_38:
        v16 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      Profile = WlanGetProfile(phClientHandle, a2, a3, 0, &psz, &pdwFlags, 0);
      if ( !Profile )
      {
        if ( (pdwFlags & 1) != 0 )
        {
          v15 = -2147024846;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_39;
          v21 = GetIndent(0);
          v22 = 14;
          v23 = v21;
        }
        else
        {
          v24 = StringCchLengthW(psz, 0xA00000u, &v34);
          v15 = v24;
          if ( v24 < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids,
                (unsigned int)v24);
              goto LABEL_38;
            }
            goto LABEL_39;
          }
          v25 = SysAllocString(psz);
          *a5 = v25;
          if ( v25 )
            goto LABEL_38;
          v15 = -2147024882;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_39;
          v22 = 16;
          v23 = "*pbstrXmlProfile";
        }
        WPP_SF_s(v16[2], v22, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, v23);
        goto LABEL_38;
      }
      if ( Profile > 0 )
        v20 = (unsigned __int16)Profile | 0x80070000;
      else
        v20 = Profile;
      v15 = v20 | 0x80000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S_guid_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)psz, (__int64)a2, Profile, v15);
        goto LABEL_38;
      }
    }
LABEL_39:
    if ( psz )
    {
      WlanFreeMemory(psz);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !phClientHandle )
      goto LABEL_50;
    v26 = WlanCloseHandle(phClientHandle, 0);
    if ( v26 )
    {
      if ( v26 > 0 )
        v27 = (unsigned __int16)v26 | 0x80070000;
      else
        v27 = v26;
      v15 = v27 | 0x80000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v15;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_50:
        if ( v16 != &WPP_GLOBAL_Control && ((v15 & 0x80000000) != 0 || *((_BYTE *)v16 + 25) >= 6u) )
        {
          v28 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v29 + 16), 18, (unsigned int)WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, v28, v15);
        }
        return v15;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids,
        (unsigned int)v26,
        v15);
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 2u )
    WPP_SF_s(v9[2], 11, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, "pbstrXmlProfile");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000dd10  mov     [rsp-28h+arg_0], rbx
0x18000dd15  mov     [rsp-28h+arg_18], rsi
0x18000dd1a  push    rbp
0x18000dd1b  push    rdi
0x18000dd1c  push    r12
0x18000dd1e  push    r13
0x18000dd20  push    r14
0x18000dd22  mov     rbp, rsp
0x18000dd25  sub     rsp, 70h
0x18000dd29  mov     rdi, [rbp+arg_20]
0x18000dd2d  xor     eax, eax
0x18000dd2f  mov     [rbp+var_30], eax
0x18000dd32  mov     ebx, r9d
0x18000dd35  mov     r14, r8
0x18000dd38  mov     [rbp+phClientHandle], 0
0x18000dd40  mov     rsi, rdx
0x18000dd43  mov     [rbp+pdwNegotiatedVersion], 0
0x18000dd4a  mov     [rbp+psz], 0
0x18000dd52  mov     r10, cs:WPP_GLOBAL_Control
0x18000dd59  lea     r12, WPP_GLOBAL_Control
0x18000dd60  lea     r13, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids
0x18000dd67  cmp     r10, r12
0x18000dd6a  jz      short loc_18000DD99
0x18000dd6c  cmp     byte ptr [r10+19h], 6
0x18000dd71  jb      short loc_18000DD99
0x18000dd73  lea     ecx, [rax+1]; int
0x18000dd76  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dd7b  mov     rcx, [r10+10h]
0x18000dd7f  mov     edx, 0Ah
0x18000dd84  mov     r9, rax
0x18000dd87  mov     r8, r13
0x18000dd8a  call    WPP_SF_s
0x18000dd8f  mov     eax, [rbp+var_30]
0x18000dd92  mov     r10, cs:WPP_GLOBAL_Control
0x18000dd99  test    rdi, rdi
0x18000dd9c  jnz     short loc_18000DDCA
0x18000dd9e  cmp     r10, r12
0x18000dda1  jz      short loc_18000DDC0
0x18000dda3  cmp     byte ptr [r10+19h], 2
0x18000dda8  jb      short loc_18000DDC0
0x18000ddaa  mov     rcx, [r10+10h]
0x18000ddae  lea     edx, [rdi+0Bh]
0x18000ddb1  lea     r9, aPbstrxmlprofil_0; "pbstrXmlProfile"
0x18000ddb8  mov     r8, r13
0x18000ddbb  call    WPP_SF_s
0x18000ddc0  mov     eax, 80004003h
0x18000ddc5  jmp     loc_18000E023
0x18000ddca  mov     qword ptr [rdi], 0
0x18000ddd1  test    ebx, ebx
0x18000ddd3  jz      short loc_18000DDDB
0x18000ddd5  or      eax, 4
0x18000ddd8  mov     [rbp+var_30], eax
0x18000dddb  xor     edx, edx; pReserved
0x18000dddd  lea     r9, [rbp+phClientHandle]; phClientHandle
0x18000dde1  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000dde5  lea     ecx, [rdx+2]; dwClientVersion
0x18000dde8  call    cs:__imp_WlanOpenHandle
0x18000ddee  test    eax, eax
0x18000ddf0  jz      short loc_18000DE3F
0x18000ddf2  jg      short loc_18000DDF8
0x18000ddf4  mov     ebx, eax
0x18000ddf6  jmp     short loc_18000DE01
0x18000ddf8  movzx   ebx, ax
0x18000ddfb  or      ebx, 80070000h
0x18000de01  or      ebx, 80000000h
0x18000de07  mov     r10, cs:WPP_GLOBAL_Control
0x18000de0e  cmp     r10, r12
0x18000de11  jz      loc_18000DF7F
0x18000de17  cmp     byte ptr [r10+19h], 2
0x18000de1c  jb      loc_18000DF7F
0x18000de22  mov     rcx, [r10+10h]
0x18000de26  mov     edx, 0Ch
0x18000de2b  mov     r9d, eax
0x18000de2e  mov     dword ptr [rsp+70h+pstrProfileXml], ebx
0x18000de32  mov     r8, r13
0x18000de35  call    WPP_SF_Dd
0x18000de3a  jmp     loc_18000DF78
0x18000de3f  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18000de43  lea     rax, [rbp+var_30]
0x18000de47  mov     [rsp+70h+pdwGrantedAccess], 0; pdwGrantedAccess
0x18000de50  xor     r9d, r9d; pReserved
0x18000de53  mov     [rsp+70h+pdwFlags], rax; pdwFlags
0x18000de58  mov     r8, r14; strProfileName
0x18000de5b  lea     rax, [rbp+psz]
0x18000de5f  mov     rdx, rsi; pInterfaceGuid
0x18000de62  mov     [rsp+70h+pstrProfileXml], rax; pstrProfileXml
0x18000de67  call    cs:__imp_WlanGetProfile
0x18000de6d  test    eax, eax
0x18000de6f  jz      short loc_18000DEC0
0x18000de71  jg      short loc_18000DE77
0x18000de73  mov     ebx, eax
0x18000de75  jmp     short loc_18000DE80
0x18000de77  movzx   ebx, ax
0x18000de7a  or      ebx, 80070000h
0x18000de80  or      ebx, 80000000h
0x18000de86  mov     r10, cs:WPP_GLOBAL_Control
0x18000de8d  cmp     r10, r12
0x18000de90  jz      loc_18000DF7F
0x18000de96  cmp     byte ptr [r10+19h], 2
0x18000de9b  jb      loc_18000DF7F
0x18000dea1  mov     r9, [rbp+psz]
0x18000dea5  mov     rcx, [r10+10h]
0x18000dea9  mov     dword ptr [rsp+70h+pdwGrantedAccess], ebx
0x18000dead  mov     dword ptr [rsp+70h+pdwFlags], eax
0x18000deb1  mov     [rsp+70h+pstrProfileXml], rsi
0x18000deb6  call    WPP_SF_S_guid_Dd
0x18000debb  jmp     loc_18000DF78
0x18000dec0  test    byte ptr [rbp+var_30], 1
0x18000dec4  jz      short loc_18000DEF7
0x18000dec6  mov     ebx, 80070032h
0x18000decb  mov     r10, cs:WPP_GLOBAL_Control
0x18000ded2  cmp     r10, r12
0x18000ded5  jz      loc_18000DF7F
0x18000dedb  cmp     byte ptr [r10+19h], 2
0x18000dee0  jb      loc_18000DF7F
0x18000dee6  xor     ecx, ecx; int
0x18000dee8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000deed  mov     edx, 0Eh
0x18000def2  mov     r9, rax
0x18000def5  jmp     short loc_18000DF6C
0x18000def7  mov     rcx, [rbp+psz]; unsigned __int16 *
0x18000defb  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18000deff  mov     edx, 0A00000h; unsigned __int64
0x18000df04  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000df09  mov     ebx, eax
0x18000df0b  test    eax, eax
0x18000df0d  jns     short loc_18000DF38
0x18000df0f  mov     r10, cs:WPP_GLOBAL_Control
0x18000df16  cmp     r10, r12
0x18000df19  jz      short loc_18000DF7F
0x18000df1b  cmp     byte ptr [r10+19h], 2
0x18000df20  jb      short loc_18000DF7F
0x18000df22  mov     rcx, [r10+10h]
0x18000df26  mov     edx, 0Fh
0x18000df2b  mov     r9d, eax
0x18000df2e  mov     r8, r13
0x18000df31  call    WPP_SF_d
0x18000df36  jmp     short loc_18000DF78
0x18000df38  mov     rcx, [rbp+psz]; psz
0x18000df3c  call    cs:__imp_SysAllocString
0x18000df42  mov     [rdi], rax
0x18000df45  test    rax, rax
0x18000df48  jnz     short loc_18000DF78
0x18000df4a  mov     ebx, 8007000Eh
0x18000df4f  mov     r10, cs:WPP_GLOBAL_Control
0x18000df56  cmp     r10, r12
0x18000df59  jz      short loc_18000DF7F
0x18000df5b  cmp     byte ptr [r10+19h], 2
0x18000df60  jb      short loc_18000DF7F
0x18000df62  lea     edx, [rax+10h]
0x18000df65  lea     r9, aPbstrxmlprofil; "*pbstrXmlProfile"
0x18000df6c  mov     rcx, [r10+10h]
0x18000df70  mov     r8, r13
0x18000df73  call    WPP_SF_s
0x18000df78  mov     r10, cs:WPP_GLOBAL_Control
0x18000df7f  mov     rcx, [rbp+psz]; pMemory
0x18000df83  test    rcx, rcx
0x18000df86  jz      short loc_18000DF95
0x18000df88  call    cs:__imp_WlanFreeMemory
0x18000df8e  mov     r10, cs:WPP_GLOBAL_Control
0x18000df95  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18000df99  test    rcx, rcx
0x18000df9c  jz      short loc_18000DFF1
0x18000df9e  xor     edx, edx; pReserved
0x18000dfa0  call    cs:__imp_WlanCloseHandle
0x18000dfa6  test    eax, eax
0x18000dfa8  jz      short loc_18000DFEA
0x18000dfaa  jg      short loc_18000DFB0
0x18000dfac  mov     ebx, eax
0x18000dfae  jmp     short loc_18000DFB9
0x18000dfb0  movzx   ebx, ax
0x18000dfb3  or      ebx, 80070000h
0x18000dfb9  or      ebx, 80000000h
0x18000dfbf  mov     r10, cs:WPP_GLOBAL_Control
0x18000dfc6  cmp     r10, r12
0x18000dfc9  jz      short loc_18000E021
0x18000dfcb  cmp     byte ptr [r10+19h], 3
0x18000dfd0  jb      short loc_18000DFF1
0x18000dfd2  mov     rcx, [r10+10h]
0x18000dfd6  mov     edx, 11h
0x18000dfdb  mov     r9d, eax
0x18000dfde  mov     dword ptr [rsp+70h+pstrProfileXml], ebx
0x18000dfe2  mov     r8, r13
0x18000dfe5  call    WPP_SF_Dd
0x18000dfea  mov     r10, cs:WPP_GLOBAL_Control
0x18000dff1  cmp     r10, r12
0x18000dff4  jz      short loc_18000E021
0x18000dff6  test    ebx, ebx
0x18000dff8  js      short loc_18000E001
0x18000dffa  cmp     byte ptr [r10+19h], 6
0x18000dfff  jb      short loc_18000E021
0x18000e001  or      ecx, 0FFFFFFFFh; int
0x18000e004  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e009  mov     rcx, [r10+10h]
0x18000e00d  mov     edx, 12h
0x18000e012  mov     r9, rax
0x18000e015  mov     dword ptr [rsp+70h+pstrProfileXml], ebx
0x18000e019  mov     r8, r13
0x18000e01c  call    WPP_SF_sd
0x18000e021  mov     eax, ebx
0x18000e023  lea     r11, [rsp+70h+var_s0]
0x18000e028  mov     rbx, [r11+30h]
0x18000e02c  mov     rsi, [r11+48h]
0x18000e030  mov     rsp, r11
0x18000e033  pop     r14
0x18000e035  pop     r13
0x18000e037  pop     r12
0x18000e039  pop     rdi
0x18000e03a  pop     rbp
0x18000e03b  retn
```
