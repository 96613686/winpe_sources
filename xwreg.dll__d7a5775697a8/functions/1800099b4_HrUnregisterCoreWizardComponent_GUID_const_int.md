# HrUnregisterCoreWizardComponent(_GUID const *,int)

- ea: `0x1800099b4`
- end: `0x180009c98`
- name: `?HrUnregisterCoreWizardComponent@@YAJPEBU_GUID@@H@Z`
- size: `740`
- prototype: `__int64 __fastcall(GUID *rguid, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009ca0`

## callees

- `0x180007820`
- `0x1800099b4`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ada4`
- `0x18000ebc0`
- `0x18000f484`
- `0x18001236c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009a06`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009a06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009abb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009abb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009b02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009b02`

## string_xrefs

- `0x180009b0c`: `xwizards.dll`
- `0x180009a3b`: `Components`

## pseudocode

```c
__int64 __fastcall HrUnregisterCoreWizardComponent(GUID *rguid, int a2)
{
  BOOL v4; // esi
  LSTATUS v5; // eax
  int v6; // edx
  int v7; // r8d
  signed int v8; // ebx
  LSTATUS v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  PVOID *v12; // rcx
  PVOID v13; // rcx
  const char *v14; // r9
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[112]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 Data[264]; // [rsp+180h] [rbp+80h] BYREF

  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(rguid, sz, 40);
  phkResult = 0;
  v4 = 0;
  hKey = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &phkResult);
  v8 = v5;
  if ( !v5 )
  {
    StringCchCatW(SubKey, 0x69u, L"\\");
    StringCchCatW(SubKey, 0x69u, sz);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hKey);
    v8 = v9;
    if ( !v9 )
    {
      cbData = 522;
      if ( !RegQueryValueExW(hKey, L"File Name", 0, 0, (LPBYTE)Data, &cbData) )
        v4 = wcsistr(Data, L"xwizards.dll") != 0;
      RegCloseKey(hKey);
      v8 = HrRegDeleteSubKeyTree(phkResult, sz);
      if ( v8 >= 0 && (v4 || a2) )
        v8 = HrUnregisterCOMServer(sz);
      goto LABEL_19;
    }
    if ( v9 == 2 )
    {
      v8 = 1;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_19;
      v11 = 74;
    }
    else
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_19;
      v11 = 75;
    }
    WPP_SF_SD(v10[2], v11, (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)SubKey, v8);
LABEL_19:
    RegCloseKey(phkResult);
LABEL_25:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( v5 > 0 )
    v8 = (unsigned __int16)v5 | 0x80070000;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
      (unsigned int)SubKey,
      v8);
    goto LABEL_25;
  }
LABEL_26:
  if ( v8 >= 0 )
  {
    if ( v12 == &WPP_GLOBAL_Control )
      return (unsigned int)v8;
    if ( (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      v13 = v12[2];
      v14 = "factory";
      if ( !v4 )
        v14 = "core";
      WPP_SF_sS((_DWORD)v13, v6, v7, (_DWORD)v14, (__int64)sz);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
    WPP_SF_D(v12[2], 78, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800099b4  mov     [rsp-8+arg_8], rbx
0x1800099b9  mov     [rsp-8+arg_10], rsi
0x1800099be  push    rbp
0x1800099bf  push    rdi
0x1800099c0  push    r14
0x1800099c2  lea     rbp, [rsp-2A0h]
0x1800099ca  sub     rsp, 3A0h
0x1800099d1  mov     rax, cs:__security_cookie
0x1800099d8  xor     rax, rsp
0x1800099db  mov     [rbp+2B0h+var_20], rax
0x1800099e2  mov     r14d, edx
0x1800099e5  mov     rbx, rcx
0x1800099e8  xor     edx, edx; Val
0x1800099ea  lea     rcx, [rsp+3B0h+sz]; void *
0x1800099ef  lea     r8d, [rdx+50h]; Size
0x1800099f3  call    memset_0
0x1800099f8  mov     r8d, 28h ; '('; cchMax
0x1800099fe  lea     rdx, [rsp+3B0h+sz]; lpsz
0x180009a03  mov     rcx, rbx; rguid
0x180009a06  call    cs:__imp_StringFromGUID2
0x180009a0c  xor     eax, eax
0x180009a0e  mov     [rsp+3B0h+var_370], 0
0x180009a17  xor     esi, esi
0x180009a19  mov     [rsp+3B0h+hKey], 0
0x180009a22  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009a29  mov     [rbp+2B0h+SubKey], ax
0x180009a2d  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x180009a31  lea     edi, [rsi+69h]
0x180009a34  mov     edx, edi; unsigned __int64
0x180009a36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009a3b  lea     r8, aComponents; "Components"
0x180009a42  mov     edx, edi; unsigned __int64
0x180009a44  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x180009a48  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a4d  lea     rax, [rsp+3B0h+var_370]
0x180009a52  mov     r9d, 20006h; samDesired
0x180009a58  xor     r8d, r8d; ulOptions
0x180009a5b  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180009a60  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x180009a64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009a6b  call    cs:__imp_RegOpenKeyExW
0x180009a71  mov     ebx, eax
0x180009a73  test    eax, eax
0x180009a75  jnz     loc_180009BC7
0x180009a7b  lea     r8, asc_180016A5C; "\\"
0x180009a82  mov     edx, edi; unsigned __int64
0x180009a84  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x180009a88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a8d  lea     r8, [rsp+3B0h+sz]; unsigned __int16 *
0x180009a92  mov     edx, edi; unsigned __int64
0x180009a94  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x180009a98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a9d  lea     rax, [rsp+3B0h+hKey]
0x180009aa2  mov     r9d, 2001Fh; samDesired
0x180009aa8  xor     r8d, r8d; ulOptions
0x180009aab  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180009ab0  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x180009ab4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009abb  call    cs:__imp_RegOpenKeyExW
0x180009ac1  lea     rdi, WPP_GLOBAL_Control
0x180009ac8  mov     ebx, eax
0x180009aca  test    eax, eax
0x180009acc  jnz     loc_180009B5F
0x180009ad2  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180009ad7  lea     rax, [rsp+3B0h+cbData]
0x180009adc  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180009ae1  lea     rdx, aFileName; "File Name"
0x180009ae8  lea     rax, [rbp+2B0h+Data]
0x180009aef  mov     [rsp+3B0h+cbData], 20Ah
0x180009af7  xor     r9d, r9d; lpType
0x180009afa  mov     [rsp+3B0h+phkResult], rax; lpData
0x180009aff  xor     r8d, r8d; lpReserved
0x180009b02  call    cs:__imp_RegQueryValueExW
0x180009b08  test    eax, eax
0x180009b0a  jnz     short loc_180009B28
0x180009b0c  lea     rdx, aXwizardsDll; "xwizards.dll"
0x180009b13  lea     rcx, [rbp+2B0h+Data]; unsigned __int16 *
0x180009b1a  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x180009b1f  test    rax, rax
0x180009b22  lea     ebx, [rsi+1]
0x180009b25  cmovnz  esi, ebx
0x180009b28  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180009b2d  call    cs:__imp_RegCloseKey
0x180009b33  mov     rcx, [rsp+3B0h+var_370]; HKEY
0x180009b38  lea     rdx, [rsp+3B0h+sz]; unsigned __int16 *
0x180009b3d  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x180009b42  mov     ebx, eax
0x180009b44  test    eax, eax
0x180009b46  js      short loc_180009BBA
0x180009b48  test    esi, esi
0x180009b4a  jnz     short loc_180009B51
0x180009b4c  test    r14d, r14d
0x180009b4f  jz      short loc_180009BBA
0x180009b51  lea     rcx, [rsp+3B0h+sz]; unsigned __int16 *
0x180009b56  call    ?HrUnregisterCOMServer@@YAJPEBG@Z; HrUnregisterCOMServer(ushort const *)
0x180009b5b  mov     ebx, eax
0x180009b5d  jmp     short loc_180009BBA
0x180009b5f  cmp     eax, 2
0x180009b62  jnz     short loc_180009B7E
0x180009b64  lea     ebx, [rax-1]
0x180009b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b6e  cmp     rcx, rdi
0x180009b71  jz      short loc_180009BBA
0x180009b73  test    byte ptr [rcx+1Ch], 10h
0x180009b77  jz      short loc_180009BBA
0x180009b79  lea     edx, [rax+48h]
0x180009b7c  jmp     short loc_180009BA2
0x180009b7e  test    eax, eax
0x180009b80  jle     short loc_180009B8B
0x180009b82  movzx   ebx, ax
0x180009b85  or      ebx, 80070000h
0x180009b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b92  cmp     rcx, rdi
0x180009b95  jz      short loc_180009BBA
0x180009b97  test    byte ptr [rcx+1Ch], 4
0x180009b9b  jz      short loc_180009BBA
0x180009b9d  mov     edx, 4Bh ; 'K'
0x180009ba2  mov     rcx, [rcx+10h]
0x180009ba6  lea     r9, [rbp+2B0h+SubKey]
0x180009baa  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009bb1  mov     dword ptr [rsp+3B0h+phkResult], ebx
0x180009bb5  call    WPP_SF_SD
0x180009bba  mov     rcx, [rsp+3B0h+var_370]; hKey
0x180009bbf  call    cs:__imp_RegCloseKey
0x180009bc5  jmp     short loc_180009C08
0x180009bc7  jle     short loc_180009BD2
0x180009bc9  movzx   ebx, ax
0x180009bcc  or      ebx, 80070000h
0x180009bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bd9  lea     rdi, WPP_GLOBAL_Control
0x180009be0  cmp     rcx, rdi
0x180009be3  jz      short loc_180009C0F
0x180009be5  test    byte ptr [rcx+1Ch], 4
0x180009be9  jz      short loc_180009C0F
0x180009beb  mov     rcx, [rcx+10h]
0x180009bef  lea     r9, [rbp+2B0h+SubKey]
0x180009bf3  mov     edx, 4Ch ; 'L'
0x180009bf8  mov     dword ptr [rsp+3B0h+phkResult], ebx
0x180009bfc  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009c03  call    WPP_SF_SD
0x180009c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c0f  test    ebx, ebx
0x180009c11  js      short loc_180009C4C
0x180009c13  cmp     rcx, rdi
0x180009c16  jz      short loc_180009C6F
0x180009c18  test    byte ptr [rcx+1Ch], 8
0x180009c1c  jz      short loc_180009C4C
0x180009c1e  mov     rcx, [rcx+10h]
0x180009c22  lea     rax, aCore; "core"
0x180009c29  test    esi, esi
0x180009c2b  lea     r9, aFactory; "factory"
0x180009c32  cmovz   r9, rax
0x180009c36  lea     rax, [rsp+3B0h+sz]
0x180009c3b  mov     [rsp+3B0h+phkResult], rax
0x180009c40  call    WPP_SF_sS
0x180009c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c4c  cmp     rcx, rdi
0x180009c4f  jz      short loc_180009C6F
0x180009c51  test    byte ptr [rcx+1Ch], 10h
0x180009c55  jz      short loc_180009C6F
0x180009c57  mov     rcx, [rcx+10h]
0x180009c5b  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009c62  mov     edx, 4Eh ; 'N'
0x180009c67  mov     r9d, ebx
0x180009c6a  call    WPP_SF_D
0x180009c6f  mov     eax, ebx
0x180009c71  mov     rcx, [rbp+2B0h+var_20]
0x180009c78  xor     rcx, rsp; StackCookie
0x180009c7b  call    __security_check_cookie
0x180009c80  lea     r11, [rsp+3B0h+var_10]
0x180009c88  mov     rbx, [r11+28h]
0x180009c8c  mov     rsi, [r11+30h]
0x180009c90  mov     rsp, r11
0x180009c93  pop     r14
0x180009c95  pop     rdi
0x180009c96  pop     rbp
0x180009c97  retn
```
