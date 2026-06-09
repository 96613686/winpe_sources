# RdVhd::Uvhd::CProfileHelper::CreateUserProfileKey(ushort const *,void *,ushort const *)

- ea: `0x1800558bc`
- end: `0x180055c9a`
- name: `?CreateUserProfileKey@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGPEAX0@Z`
- size: `990`
- prototype: `int(RdVhd::Uvhd::CProfileHelper *__hidden this, const unsigned __int16 *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180055ca0`

## callees

- `0x1800488e4`
- `0x180048b28`
- `0x1800558bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055a62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055af4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055b89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055c0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055a62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055af4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055b89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055c0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800559d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800559d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055be6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055be6`

## string_xrefs

- `0x180055a4d`: `ProfileImagePath`
- `0x18005590c`: `szUserProfileDirectory`
- `0x180055954`: `pUserSid`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::CreateUserProfileKey(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2,
        void *a3,
        const BYTE *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // r9
  signed int v9; // ebx
  __int64 v10; // rdi
  LSTATUS v11; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v12; // rcx
  __int64 v13; // rdx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  DWORD LengthSid; // eax
  LSTATUS v18; // eax
  RdVhd::Uvhd::CProfileHelper *Data; // [rsp+80h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  Data = this;
  hKey = 0;
  if ( !a4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 71;
    v8 = L"szUserProfileDirectory";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v6 + 2), v7, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v8);
LABEL_7:
    v9 = -2147024809;
    goto LABEL_71;
  }
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 72;
    v8 = L"pUserSid";
    goto LABEL_6;
  }
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 73;
    v8 = L"szUserProfileKey";
    goto LABEL_6;
  }
  v9 = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)&a4[2 * v10] );
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( !v11 )
    goto LABEL_30;
  v9 = v11;
  if ( (v11 & 0xFFFF0000) == 0 )
  {
    if ( v11 > 0 )
      v9 = v11 | 0x80070000;
    v9 = v9 & 0x8000FFFF | 0x502F0000;
  }
  if ( v9 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 74;
LABEL_70:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, (unsigned int)v9);
    }
  }
  else
  {
LABEL_30:
    v14 = RegSetValueExW(hKey, L"ProfileImagePath", 0, 2u, a4, 2 * v10 + 2);
    if ( !v14 )
      goto LABEL_40;
    v9 = v14;
    if ( (v14 & 0xFFFF0000) == 0 )
    {
      if ( v14 > 0 )
        v9 = v14 | 0x80070000;
      v9 = v9 & 0x8000FFFF | 0x50300000;
    }
    if ( v9 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 75;
        goto LABEL_70;
      }
    }
    else
    {
LABEL_40:
      LODWORD(Data) = 0;
      v15 = RegSetValueExW(hKey, L"Flags", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v15 )
        goto LABEL_50;
      v9 = v15;
      if ( (v15 & 0xFFFF0000) == 0 )
      {
        if ( v15 > 0 )
          v9 = v15 | 0x80070000;
        v9 = v9 & 0x8000FFFF | 0x50310000;
      }
      if ( v9 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 76;
          goto LABEL_70;
        }
      }
      else
      {
LABEL_50:
        LODWORD(Data) = 4;
        v16 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v16 )
          goto LABEL_60;
        v9 = v16;
        if ( (v16 & 0xFFFF0000) == 0 )
        {
          if ( v16 > 0 )
            v9 = v16 | 0x80070000;
          v9 = v9 & 0x8000FFFF | 0x50320000;
        }
        if ( v9 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 77;
            goto LABEL_70;
          }
        }
        else
        {
LABEL_60:
          LengthSid = GetLengthSid(a3);
          v18 = RegSetValueExW(hKey, L"Sid", 0, 3u, (const BYTE *)a3, LengthSid);
          if ( v18 )
          {
            v9 = v18;
            if ( (v18 & 0xFFFF0000) == 0 )
            {
              if ( v18 > 0 )
                v9 = v18 | 0x80070000;
              v9 = v9 & 0x8000FFFF | 0x503C0000;
            }
            if ( v9 < 0 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = 78;
                goto LABEL_70;
              }
            }
          }
        }
      }
    }
  }
LABEL_71:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800558bc  mov     rax, rsp
0x1800558bf  mov     [rax+10h], rbx
0x1800558c3  mov     [rax+18h], rbp
0x1800558c7  mov     [rax+8], rcx
0x1800558cb  push    rsi
0x1800558cc  push    rdi
0x1800558cd  push    r12
0x1800558cf  push    r14
0x1800558d1  push    r15
0x1800558d3  sub     rsp, 50h
0x1800558d7  xor     r14d, r14d
0x1800558da  mov     rsi, r9
0x1800558dd  mov     [rax+20h], r14
0x1800558e1  mov     rbp, r8
0x1800558e4  test    r9, r9
0x1800558e7  jnz     short loc_18005592D
0x1800558e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800558f0  lea     rax, WPP_GLOBAL_Control
0x1800558f7  cmp     rcx, rax
0x1800558fa  jz      short loc_180055923
0x1800558fc  test    byte ptr [rcx+1Ch], 4
0x180055900  jz      short loc_180055923
0x180055902  cmp     byte ptr [rcx+19h], 2
0x180055906  jb      short loc_180055923
0x180055908  lea     edx, [r9+47h]
0x18005590c  lea     r9, aSzuserprofiled; "szUserProfileDirectory"
0x180055913  mov     rcx, [rcx+10h]
0x180055917  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x18005591e  call    WPP_SF_S
0x180055923  mov     ebx, 80070057h
0x180055928  jmp     loc_180055C6C
0x18005592d  test    rbp, rbp
0x180055930  jnz     short loc_18005595D
0x180055932  mov     rcx, cs:WPP_GLOBAL_Control
0x180055939  lea     rax, WPP_GLOBAL_Control
0x180055940  cmp     rcx, rax
0x180055943  jz      short loc_180055923
0x180055945  test    byte ptr [rcx+1Ch], 4
0x180055949  jz      short loc_180055923
0x18005594b  cmp     byte ptr [rcx+19h], 2
0x18005594f  jb      short loc_180055923
0x180055951  lea     edx, [rbp+48h]
0x180055954  lea     r9, aPusersid; "pUserSid"
0x18005595b  jmp     short loc_180055913
0x18005595d  test    rdx, rdx
0x180055960  jnz     short loc_18005598F
0x180055962  mov     rcx, cs:WPP_GLOBAL_Control
0x180055969  lea     rax, WPP_GLOBAL_Control
0x180055970  cmp     rcx, rax
0x180055973  jz      short loc_180055923
0x180055975  test    byte ptr [rcx+1Ch], 4
0x180055979  jz      short loc_180055923
0x18005597b  cmp     byte ptr [rcx+19h], 2
0x18005597f  jb      short loc_180055923
0x180055981  mov     edx, 49h ; 'I'; lpSubKey
0x180055986  lea     r9, aSzuserprofilek; "szUserProfileKey"
0x18005598d  jmp     short loc_180055913
0x18005598f  mov     ebx, r14d
0x180055992  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055996  inc     rdi
0x180055999  cmp     [r9+rdi*2], r14w
0x18005599e  jnz     short loc_180055996
0x1800559a0  mov     [rsp+78h+lpdwDisposition], r14; lpdwDisposition
0x1800559a5  lea     rax, [rsp+78h+hKey]
0x1800559ad  mov     [rsp+78h+phkResult], rax; phkResult
0x1800559b2  xor     r9d, r9d; lpClass
0x1800559b5  mov     [rsp+78h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800559ba  xor     r8d, r8d; Reserved
0x1800559bd  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800559c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800559cc  mov     [rsp+78h+dwOptions], r14d; dwOptions
0x1800559d1  call    cs:__imp_RegCreateKeyExW
0x1800559d7  mov     r15d, 0FFFF0000h
0x1800559dd  mov     r12d, 80070000h
0x1800559e3  test    eax, eax
0x1800559e5  jz      short loc_180055A3A
0x1800559e7  mov     ebx, eax
0x1800559e9  test    r15d, eax
0x1800559ec  jnz     short loc_180055A01
0x1800559ee  test    eax, eax
0x1800559f0  jle     short loc_1800559F5
0x1800559f2  or      ebx, r12d
0x1800559f5  and     ebx, 0D02FFFFFh
0x1800559fb  or      ebx, 502F0000h
0x180055a01  test    ebx, ebx
0x180055a03  jns     short loc_180055A3A
0x180055a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a0c  lea     rax, WPP_GLOBAL_Control
0x180055a13  cmp     rcx, rax
0x180055a16  jz      loc_180055C6C
0x180055a1c  test    byte ptr [rcx+1Ch], 4
0x180055a20  jz      loc_180055C6C
0x180055a26  cmp     byte ptr [rcx+19h], 2
0x180055a2a  jb      loc_180055C6C
0x180055a30  mov     edx, 4Ah ; 'J'
0x180055a35  jmp     loc_180055C59
0x180055a3a  mov     rcx, [rsp+78h+hKey]; hKey
0x180055a42  lea     eax, ds:2[rdi*2]
0x180055a49  mov     [rsp+78h+samDesired], eax; cbData
0x180055a4d  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x180055a54  mov     r9d, 2; dwType
0x180055a5a  mov     qword ptr [rsp+78h+dwOptions], rsi; lpData
0x180055a5f  xor     r8d, r8d; Reserved
0x180055a62  call    cs:__imp_RegSetValueExW
0x180055a68  test    eax, eax
0x180055a6a  jz      short loc_180055ABF
0x180055a6c  mov     ebx, eax
0x180055a6e  test    r15d, eax
0x180055a71  jnz     short loc_180055A86
0x180055a73  test    eax, eax
0x180055a75  jle     short loc_180055A7A
0x180055a77  or      ebx, r12d
0x180055a7a  and     ebx, 0D030FFFFh
0x180055a80  or      ebx, 50300000h
0x180055a86  test    ebx, ebx
0x180055a88  jns     short loc_180055ABF
0x180055a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a91  lea     rax, WPP_GLOBAL_Control
0x180055a98  cmp     rcx, rax
0x180055a9b  jz      loc_180055C6C
0x180055aa1  test    byte ptr [rcx+1Ch], 4
0x180055aa5  jz      loc_180055C6C
0x180055aab  cmp     byte ptr [rcx+19h], 2
0x180055aaf  jb      loc_180055C6C
0x180055ab5  mov     edx, 4Bh ; 'K'
0x180055aba  jmp     loc_180055C59
0x180055abf  mov     rcx, [rsp+78h+hKey]; hKey
0x180055ac7  lea     rax, [rsp+78h+Data]
0x180055acf  mov     [rsp+78h+samDesired], 4; cbData
0x180055ad7  lea     rdx, aFlags; "Flags"
0x180055ade  mov     r9d, 4; dwType
0x180055ae4  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180055ae9  xor     r8d, r8d; Reserved
0x180055aec  mov     dword ptr [rsp+78h+Data], r14d
0x180055af4  call    cs:__imp_RegSetValueExW
0x180055afa  test    eax, eax
0x180055afc  jz      short loc_180055B51
0x180055afe  mov     ebx, eax
0x180055b00  test    r15d, eax
0x180055b03  jnz     short loc_180055B18
0x180055b05  test    eax, eax
0x180055b07  jle     short loc_180055B0C
0x180055b09  or      ebx, r12d
0x180055b0c  and     ebx, 0D031FFFFh
0x180055b12  or      ebx, 50310000h
0x180055b18  test    ebx, ebx
0x180055b1a  jns     short loc_180055B51
0x180055b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b23  lea     rax, WPP_GLOBAL_Control
0x180055b2a  cmp     rcx, rax
0x180055b2d  jz      loc_180055C6C
0x180055b33  test    byte ptr [rcx+1Ch], 4
0x180055b37  jz      loc_180055C6C
0x180055b3d  cmp     byte ptr [rcx+19h], 2
0x180055b41  jb      loc_180055C6C
0x180055b47  mov     edx, 4Ch ; 'L'
0x180055b4c  jmp     loc_180055C59
0x180055b51  mov     rcx, [rsp+78h+hKey]; hKey
0x180055b59  lea     rax, [rsp+78h+Data]
0x180055b61  mov     [rsp+78h+samDesired], 4; cbData
0x180055b69  lea     rdx, aState; "State"
0x180055b70  mov     r9d, 4; dwType
0x180055b76  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180055b7b  xor     r8d, r8d; Reserved
0x180055b7e  mov     dword ptr [rsp+78h+Data], 4
0x180055b89  call    cs:__imp_RegSetValueExW
0x180055b8f  test    eax, eax
0x180055b91  jz      short loc_180055BE3
0x180055b93  mov     ebx, eax
0x180055b95  test    r15d, eax
0x180055b98  jnz     short loc_180055BAD
0x180055b9a  test    eax, eax
0x180055b9c  jle     short loc_180055BA1
0x180055b9e  or      ebx, r12d
0x180055ba1  and     ebx, 0D032FFFFh
0x180055ba7  or      ebx, 50320000h
0x180055bad  test    ebx, ebx
0x180055baf  jns     short loc_180055BE3
0x180055bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180055bb8  lea     rax, WPP_GLOBAL_Control
0x180055bbf  cmp     rcx, rax
0x180055bc2  jz      loc_180055C6C
0x180055bc8  test    byte ptr [rcx+1Ch], 4
0x180055bcc  jz      loc_180055C6C
0x180055bd2  cmp     byte ptr [rcx+19h], 2
0x180055bd6  jb      loc_180055C6C
0x180055bdc  mov     edx, 4Dh ; 'M'
0x180055be1  jmp     short loc_180055C59
0x180055be3  mov     rcx, rbp; pSid
0x180055be6  call    cs:__imp_GetLengthSid
0x180055bec  mov     rcx, [rsp+78h+hKey]; hKey
0x180055bf4  lea     rdx, aSid; "Sid"
0x180055bfb  mov     [rsp+78h+samDesired], eax; cbData
0x180055bff  mov     r9d, 3; dwType
0x180055c05  xor     r8d, r8d; Reserved
0x180055c08  mov     qword ptr [rsp+78h+dwOptions], rbp; lpData
0x180055c0d  call    cs:__imp_RegSetValueExW
0x180055c13  test    eax, eax
0x180055c15  jz      short loc_180055C6C
0x180055c17  mov     ebx, eax
0x180055c19  test    r15d, eax
0x180055c1c  jnz     short loc_180055C31
0x180055c1e  test    eax, eax
0x180055c20  jle     short loc_180055C25
0x180055c22  or      ebx, r12d
0x180055c25  and     ebx, 0D03CFFFFh
0x180055c2b  or      ebx, 503C0000h
0x180055c31  test    ebx, ebx
0x180055c33  jns     short loc_180055C6C
0x180055c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c3c  lea     rax, WPP_GLOBAL_Control
0x180055c43  cmp     rcx, rax
0x180055c46  jz      short loc_180055C6C
0x180055c48  test    byte ptr [rcx+1Ch], 4
0x180055c4c  jz      short loc_180055C6C
0x180055c4e  cmp     byte ptr [rcx+19h], 2
0x180055c52  jb      short loc_180055C6C
0x180055c54  mov     edx, 4Eh ; 'N'
0x180055c59  mov     rcx, [rcx+10h]
0x180055c5d  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180055c64  mov     r9d, ebx
0x180055c67  call    WPP_SF_d
0x180055c6c  mov     rcx, [rsp+78h+hKey]; hKey
0x180055c74  test    rcx, rcx
0x180055c77  jz      short loc_180055C7F
0x180055c79  call    cs:__imp_RegCloseKey
0x180055c7f  lea     r11, [rsp+78h+var_28]
0x180055c84  mov     eax, ebx
0x180055c86  mov     rbx, [r11+38h]
0x180055c8a  mov     rbp, [r11+40h]
0x180055c8e  mov     rsp, r11
0x180055c91  pop     r15
0x180055c93  pop     r14
0x180055c95  pop     r12
0x180055c97  pop     rdi
0x180055c98  pop     rsi
0x180055c99  retn
```
