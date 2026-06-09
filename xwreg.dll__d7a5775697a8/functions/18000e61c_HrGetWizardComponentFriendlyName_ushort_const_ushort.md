# HrGetWizardComponentFriendlyName(ushort * const,ushort * *)

- ea: `0x18000e61c`
- end: `0x18000e8b6`
- name: `?HrGetWizardComponentFriendlyName@@YAJQEAGPEAPEAG@Z`
- size: `666`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008b4c`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000e61c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e821`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e71f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e71f`

## string_xrefs

- `0x18000e694`: `Components`

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
  StringCchCatW(SubKey, 0x69u, &qword_180017630);
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
        WPP_SF_D(v10[2], 91, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v5);
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
0x18000e61c  mov     [rsp-8+arg_10], rbx
0x18000e621  mov     [rsp-8+arg_18], rsi
0x18000e626  push    rbp
0x18000e627  push    rdi
0x18000e628  push    r14
0x18000e62a  lea     rbp, [rsp-240h]
0x18000e632  sub     rsp, 340h
0x18000e639  mov     rax, cs:__security_cookie
0x18000e640  xor     rax, rsp
0x18000e643  mov     [rbp+250h+var_20], rax
0x18000e64a  mov     rsi, rdx
0x18000e64d  mov     [rsp+350h+hKey], 0
0x18000e656  mov     rbx, rcx
0x18000e659  mov     edi, 20Ah
0x18000e65e  mov     r8d, edi; Size
0x18000e661  lea     rcx, [rbp+250h+Data]; void *
0x18000e665  xor     edx, edx; Val
0x18000e667  call    memset_0
0x18000e66c  xor     eax, eax
0x18000e66e  mov     [rsp+350h+cbData], edi
0x18000e672  lea     r8, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e679  mov     qword ptr [rsi], 0
0x18000e680  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000e685  mov     [rsp+350h+SubKey], ax
0x18000e68a  lea     edi, [rax+69h]
0x18000e68d  mov     edx, edi; unsigned __int64
0x18000e68f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e694  lea     r8, aComponents_0; "Components"
0x18000e69b  mov     edx, edi; unsigned __int64
0x18000e69d  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000e6a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e6a7  lea     r8, qword_180017630; unsigned __int16 *
0x18000e6ae  mov     edx, edi; unsigned __int64
0x18000e6b0  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000e6b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e6ba  mov     r8, rbx; unsigned __int16 *
0x18000e6bd  lea     rcx, [rsp+350h+SubKey]; unsigned __int16 *
0x18000e6c2  mov     edx, edi; unsigned __int64
0x18000e6c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e6c9  lea     rax, [rsp+350h+hKey]
0x18000e6ce  mov     r9d, 20019h; samDesired
0x18000e6d4  xor     r8d, r8d; ulOptions
0x18000e6d7  mov     [rsp+350h+phkResult], rax; phkResult
0x18000e6dc  lea     rdx, [rsp+350h+SubKey]; lpSubKey
0x18000e6e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e6e8  call    cs:__imp_RegOpenKeyExW
0x18000e6ee  lea     r14, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e6f5  mov     ebx, eax
0x18000e6f7  test    eax, eax
0x18000e6f9  jnz     loc_18000E829
0x18000e6ff  mov     rcx, [rsp+350h+hKey]; hKey
0x18000e704  lea     rax, [rsp+350h+cbData]
0x18000e709  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18000e70e  xor     r9d, r9d; lpType
0x18000e711  lea     rax, [rbp+250h+Data]
0x18000e715  xor     r8d, r8d; lpReserved
0x18000e718  xor     edx, edx; lpValueName
0x18000e71a  mov     [rsp+350h+phkResult], rax; lpData
0x18000e71f  call    cs:__imp_RegQueryValueExW
0x18000e725  lea     rdi, WPP_GLOBAL_Control
0x18000e72c  mov     ebx, eax
0x18000e72e  test    eax, eax
0x18000e730  jnz     loc_18000E7C0
0x18000e736  cmp     [rsp+350h+cbData], 2
0x18000e73b  jbe     short loc_18000E79E
0x18000e73d  mov     ecx, [rsp+350h+cbData]; cb
0x18000e741  call    cs:__imp_CoTaskMemAlloc
0x18000e747  mov     [rsi], rax
0x18000e74a  test    rax, rax
0x18000e74d  jz      short loc_18000E76C
0x18000e74f  xor     edx, edx
0x18000e751  lea     r8, [rbp+250h+Data]; unsigned __int16 *
0x18000e755  mov     [rax], dx
0x18000e758  mov     edx, [rsp+350h+cbData]
0x18000e75c  mov     rcx, [rsi]; unsigned __int16 *
0x18000e75f  shr     rdx, 1; unsigned __int64
0x18000e762  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e767  jmp     loc_18000E81C
0x18000e76c  mov     ebx, 8007000Eh
0x18000e771  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e778  cmp     rcx, rdi
0x18000e77b  jz      loc_18000E81C
0x18000e781  test    byte ptr [rcx+1Ch], 4
0x18000e785  jz      loc_18000E81C
0x18000e78b  mov     edx, 56h ; 'V'
0x18000e790  mov     dword ptr [rsp+350h+phkResult], 8007000Eh
0x18000e798  lea     r9, [rbp+250h+Data]
0x18000e79c  jmp     short loc_18000E810
0x18000e79e  mov     eax, 1
0x18000e7a3  mov     ebx, eax
0x18000e7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7ac  cmp     rcx, rdi
0x18000e7af  jz      short loc_18000E81C
0x18000e7b1  test    byte ptr [rcx+1Ch], 10h
0x18000e7b5  jz      short loc_18000E81C
0x18000e7b7  lea     edx, [rax+56h]
0x18000e7ba  mov     dword ptr [rsp+350h+phkResult], eax
0x18000e7be  jmp     short loc_18000E80B
0x18000e7c0  cmp     eax, 2
0x18000e7c3  jnz     short loc_18000E7E3
0x18000e7c5  mov     eax, 1
0x18000e7ca  mov     ebx, eax
0x18000e7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d3  cmp     rcx, rdi
0x18000e7d6  jz      short loc_18000E81C
0x18000e7d8  test    byte ptr [rcx+1Ch], 10h
0x18000e7dc  jz      short loc_18000E81C
0x18000e7de  lea     edx, [rax+57h]
0x18000e7e1  jmp     short loc_18000E7BA
0x18000e7e3  test    eax, eax
0x18000e7e5  jle     short loc_18000E7F0
0x18000e7e7  movzx   ebx, ax
0x18000e7ea  or      ebx, 80070000h
0x18000e7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7f7  cmp     rcx, rdi
0x18000e7fa  jz      short loc_18000E81C
0x18000e7fc  test    byte ptr [rcx+1Ch], 10h
0x18000e800  jz      short loc_18000E81C
0x18000e802  mov     edx, 59h ; 'Y'
0x18000e807  mov     dword ptr [rsp+350h+phkResult], ebx
0x18000e80b  lea     r9, [rsp+350h+SubKey]
0x18000e810  mov     rcx, [rcx+10h]
0x18000e814  mov     r8, r14
0x18000e817  call    WPP_SF_SD
0x18000e81c  mov     rcx, [rsp+350h+hKey]; hKey
0x18000e821  call    cs:__imp_RegCloseKey
0x18000e827  jmp     short loc_18000E867
0x18000e829  jle     short loc_18000E834
0x18000e82b  movzx   ebx, ax
0x18000e82e  or      ebx, 80070000h
0x18000e834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e83b  lea     rdi, WPP_GLOBAL_Control
0x18000e842  cmp     rcx, rdi
0x18000e845  jz      short loc_18000E88D
0x18000e847  test    byte ptr [rcx+1Ch], 4
0x18000e84b  jz      short loc_18000E86E
0x18000e84d  mov     rcx, [rcx+10h]
0x18000e851  lea     r9, [rsp+350h+SubKey]
0x18000e856  mov     edx, 5Ah ; 'Z'
0x18000e85b  mov     dword ptr [rsp+350h+phkResult], ebx
0x18000e85f  mov     r8, r14
0x18000e862  call    WPP_SF_SD
0x18000e867  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e86e  cmp     rcx, rdi
0x18000e871  jz      short loc_18000E88D
0x18000e873  test    byte ptr [rcx+1Ch], 10h
0x18000e877  jz      short loc_18000E88D
0x18000e879  mov     rcx, [rcx+10h]
0x18000e87d  mov     edx, 5Bh ; '['
0x18000e882  mov     r9d, ebx
0x18000e885  mov     r8, r14
0x18000e888  call    WPP_SF_D
0x18000e88d  mov     eax, ebx
0x18000e88f  mov     rcx, [rbp+250h+var_20]
0x18000e896  xor     rcx, rsp; StackCookie
0x18000e899  call    __security_check_cookie
0x18000e89e  lea     r11, [rsp+350h+var_10]
0x18000e8a6  mov     rbx, [r11+30h]
0x18000e8aa  mov     rsi, [r11+38h]
0x18000e8ae  mov     rsp, r11
0x18000e8b1  pop     r14
0x18000e8b3  pop     rdi
0x18000e8b4  pop     rbp
0x18000e8b5  retn
```
