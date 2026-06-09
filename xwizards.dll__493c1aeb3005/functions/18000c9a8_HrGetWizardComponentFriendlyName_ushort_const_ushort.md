# HrGetWizardComponentFriendlyName(ushort * const,ushort * *)

- ea: `0x18000c9a8`
- end: `0x18000cc42`
- name: `?HrGetWizardComponentFriendlyName@@YAJQEAGPEAPEAG@Z`
- size: `666`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f6e0`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000c9a8`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000caab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000caab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cacd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cacd`

## string_xrefs

- `0x18000ca20`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetWizardComponentFriendlyName(unsigned __int16 *const a1, unsigned __int16 **a2)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned __int16 *v7; // rax
  _QWORD *v8; // rcx
  int v9; // edx
  PVOID *v10; // rcx
  char phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[112]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Data[264]; // [rsp+120h] [rbp+20h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  *a2 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, &qword_18003C618);
  StringCchCatW(SubKey, 0x69u, a1);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( !v4 )
  {
    v6 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 != 2 )
      {
        if ( v6 > 0 )
          v5 = (unsigned __int16)v6 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_23;
        v9 = 89;
        phkResult = v5;
        goto LABEL_22;
      }
      v5 = 1;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_23;
      v9 = 88;
    }
    else
    {
      if ( cbData > 2 )
      {
        v7 = (unsigned __int16 *)CoTaskMemAlloc(cbData);
        *a2 = v7;
        if ( v7 )
        {
          *v7 = 0;
          StringCchCopyW(*a2, (unsigned __int64)cbData >> 1, Data);
        }
        else
        {
          v5 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              86,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)Data,
              14);
        }
        goto LABEL_23;
      }
      v5 = 1;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_23:
        RegCloseKey(hKey);
        goto LABEL_29;
      }
      v9 = 87;
    }
    phkResult = 1;
LABEL_22:
    WPP_SF_SD(
      v8[2],
      v9,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      phkResult);
    goto LABEL_23;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_30:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
        WPP_SF_d(v10[2], 91, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v5);
      return v5;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v5);
LABEL_29:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  return v5;
}

```

## disassembly

```asm
0x18000c9a8  mov     [rsp-8+arg_10], rbx
0x18000c9ad  mov     [rsp-8+arg_18], rsi
0x18000c9b2  push    rbp
0x18000c9b3  push    rdi
0x18000c9b4  push    r14
0x18000c9b6  lea     rbp, [rsp-240h]
0x18000c9be  sub     rsp, 340h
0x18000c9c5  mov     rax, cs:__security_cookie
0x18000c9cc  xor     rax, rsp
0x18000c9cf  mov     [rbp+250h+var_20], rax
0x18000c9d6  mov     rsi, rdx
0x18000c9d9  mov     [rsp+350h+hKey], 0
0x18000c9e2  mov     rbx, rcx
0x18000c9e5  mov     edi, 20Ah
0x18000c9ea  mov     r8d, edi; Size
0x18000c9ed  lea     rcx, [rbp+250h+Data]; void *
0x18000c9f1  xor     edx, edx; Val
0x18000c9f3  call    memset_0
0x18000c9f8  xor     eax, eax
0x18000c9fa  mov     [rsp+350h+cbData], edi
0x18000c9fe  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ca05  mov     qword ptr [rsi], 0
0x18000ca0c  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000ca11  mov     [rsp+350h+SubKey], ax
0x18000ca16  lea     edi, [rax+69h]
0x18000ca19  mov     edx, edi; unsigned __int64
0x18000ca1b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ca20  lea     r8, aComponents; "Components"
0x18000ca27  mov     edx, edi; unsigned __int64
0x18000ca29  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000ca2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ca33  lea     r8, qword_18003C618; unsigned __int16 *
0x18000ca3a  mov     edx, edi; unsigned __int64
0x18000ca3c  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000ca41  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ca46  mov     r8, rbx; unsigned __int16 *
0x18000ca49  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000ca4e  mov     edx, edi; unsigned __int64
0x18000ca50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ca55  lea     rax, [rsp+350h+hKey]
0x18000ca5a  mov     r9d, 20019h; samDesired
0x18000ca60  xor     r8d, r8d; ulOptions
0x18000ca63  mov     [rsp+350h+phkResult], rax; phkResult
0x18000ca68  lea     rdx, [rsp+350h+SubKey]; lpSubKey
0x18000ca6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ca74  call    cs:__imp_RegOpenKeyExW
0x18000ca7a  lea     r14, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ca81  mov     ebx, eax
0x18000ca83  test    eax, eax
0x18000ca85  jnz     loc_18000CBB5
0x18000ca8b  mov     rcx, [rsp+350h+hKey]; hKey
0x18000ca90  lea     rax, [rsp+350h+cbData]
0x18000ca95  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18000ca9a  xor     r9d, r9d; lpType
0x18000ca9d  lea     rax, [rbp+250h+Data]
0x18000caa1  xor     r8d, r8d; lpReserved
0x18000caa4  xor     edx, edx; lpValueName
0x18000caa6  mov     [rsp+350h+phkResult], rax; lpData
0x18000caab  call    cs:__imp_RegQueryValueExW
0x18000cab1  lea     rdi, WPP_GLOBAL_Control
0x18000cab8  mov     ebx, eax
0x18000caba  test    eax, eax
0x18000cabc  jnz     loc_18000CB4C
0x18000cac2  cmp     [rsp+350h+cbData], 2
0x18000cac7  jbe     short loc_18000CB2A
0x18000cac9  mov     ecx, [rsp+350h+cbData]; cb
0x18000cacd  call    cs:__imp_CoTaskMemAlloc
0x18000cad3  mov     [rsi], rax
0x18000cad6  test    rax, rax
0x18000cad9  jz      short loc_18000CAF8
0x18000cadb  xor     edx, edx
0x18000cadd  lea     r8, [rbp+250h+Data]; unsigned __int16 *
0x18000cae1  mov     [rax], dx
0x18000cae4  mov     edx, [rsp+350h+cbData]
0x18000cae8  mov     rcx, [rsi]; unsigned __int16 *
0x18000caeb  shr     rdx, 1; unsigned __int64
0x18000caee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000caf3  jmp     loc_18000CBA8
0x18000caf8  mov     ebx, 8007000Eh
0x18000cafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb04  cmp     rcx, rdi
0x18000cb07  jz      loc_18000CBA8
0x18000cb0d  test    byte ptr [rcx+1Ch], 4
0x18000cb11  jz      loc_18000CBA8
0x18000cb17  mov     edx, 56h ; 'V'
0x18000cb1c  mov     dword ptr [rsp+350h+phkResult], 8007000Eh
0x18000cb24  lea     r9, [rbp+250h+Data]
0x18000cb28  jmp     short loc_18000CB9C
0x18000cb2a  mov     eax, 1
0x18000cb2f  mov     ebx, eax
0x18000cb31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb38  cmp     rcx, rdi
0x18000cb3b  jz      short loc_18000CBA8
0x18000cb3d  test    byte ptr [rcx+1Ch], 10h
0x18000cb41  jz      short loc_18000CBA8
0x18000cb43  lea     edx, [rax+56h]
0x18000cb46  mov     dword ptr [rsp+350h+phkResult], eax
0x18000cb4a  jmp     short loc_18000CB97
0x18000cb4c  cmp     eax, 2
0x18000cb4f  jnz     short loc_18000CB6F
0x18000cb51  mov     eax, 1
0x18000cb56  mov     ebx, eax
0x18000cb58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb5f  cmp     rcx, rdi
0x18000cb62  jz      short loc_18000CBA8
0x18000cb64  test    byte ptr [rcx+1Ch], 10h
0x18000cb68  jz      short loc_18000CBA8
0x18000cb6a  lea     edx, [rax+57h]
0x18000cb6d  jmp     short loc_18000CB46
0x18000cb6f  test    eax, eax
0x18000cb71  jle     short loc_18000CB7C
0x18000cb73  movzx   ebx, ax
0x18000cb76  or      ebx, 80070000h
0x18000cb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb83  cmp     rcx, rdi
0x18000cb86  jz      short loc_18000CBA8
0x18000cb88  test    byte ptr [rcx+1Ch], 10h
0x18000cb8c  jz      short loc_18000CBA8
0x18000cb8e  mov     edx, 59h ; 'Y'
0x18000cb93  mov     dword ptr [rsp+350h+phkResult], ebx
0x18000cb97  lea     r9, [rsp+350h+SubKey]
0x18000cb9c  mov     rcx, [rcx+10h]
0x18000cba0  mov     r8, r14
0x18000cba3  call    WPP_SF_SD
0x18000cba8  mov     rcx, [rsp+350h+hKey]; hKey
0x18000cbad  call    cs:__imp_RegCloseKey
0x18000cbb3  jmp     short loc_18000CBF3
0x18000cbb5  jle     short loc_18000CBC0
0x18000cbb7  movzx   ebx, ax
0x18000cbba  or      ebx, 80070000h
0x18000cbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbc7  lea     rdi, WPP_GLOBAL_Control
0x18000cbce  cmp     rcx, rdi
0x18000cbd1  jz      short loc_18000CC19
0x18000cbd3  test    byte ptr [rcx+1Ch], 4
0x18000cbd7  jz      short loc_18000CBFA
0x18000cbd9  mov     rcx, [rcx+10h]
0x18000cbdd  lea     r9, [rsp+350h+SubKey]
0x18000cbe2  mov     edx, 5Ah ; 'Z'
0x18000cbe7  mov     dword ptr [rsp+350h+phkResult], ebx
0x18000cbeb  mov     r8, r14
0x18000cbee  call    WPP_SF_SD
0x18000cbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbfa  cmp     rcx, rdi
0x18000cbfd  jz      short loc_18000CC19
0x18000cbff  test    byte ptr [rcx+1Ch], 10h
0x18000cc03  jz      short loc_18000CC19
0x18000cc05  mov     rcx, [rcx+10h]
0x18000cc09  mov     edx, 5Bh ; '['
0x18000cc0e  mov     r9d, ebx
0x18000cc11  mov     r8, r14
0x18000cc14  call    WPP_SF_d
0x18000cc19  mov     eax, ebx
0x18000cc1b  mov     rcx, [rbp+250h+var_20]
0x18000cc22  xor     rcx, rsp; StackCookie
0x18000cc25  call    __security_check_cookie
0x18000cc2a  lea     r11, [rsp+350h+var_10]
0x18000cc32  mov     rbx, [r11+30h]
0x18000cc36  mov     rsi, [r11+38h]
0x18000cc3a  mov     rsp, r11
0x18000cc3d  pop     r14
0x18000cc3f  pop     rdi
0x18000cc40  pop     rbp
0x18000cc41  retn
```
