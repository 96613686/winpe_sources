# SQLLicense::WriteLicenseInfo(wchar_t *,bool,uchar *,ulong,wchar_t *,ulong,uchar *,ulong,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x100449880`
- end: `0x100449d39`
- name: `?WriteLicenseInfo@SQLLicense@@MEAAJPEA_W_NPEAEK0K2K0K0K@Z`
- size: `1209`
- prototype: `__int64 __fastcall(SQLLicense *__hidden this, wchar_t *, bool, unsigned __int8 *, DWORD cbData, wchar_t *, unsigned int, BYTE *, DWORD, wchar_t *, unsigned int, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1004366d0`

## callees

- `0x100449880`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x100449b32`
- `ADVAPI32!RegDeleteValueW` at `0x100449bd8`
- `ADVAPI32!RegDeleteValueW` at `0x100449b32`
- `ADVAPI32!RegDeleteValueW` at `0x100449bd8`
- `ADVAPI32!RegConnectRegistryW` at `0x1004498d4`
- `ADVAPI32!RegConnectRegistryW` at `0x1004498d4`
- `ADVAPI32!RegSetValueExW` at `0x100449a49`
- `ADVAPI32!RegSetValueExW` at `0x100449ad6`
- `ADVAPI32!RegSetValueExW` at `0x100449b7c`
- `ADVAPI32!RegSetValueExW` at `0x100449c15`
- `ADVAPI32!RegSetValueExW` at `0x100449c9a`
- `ADVAPI32!RegSetValueExW` at `0x100449a49`
- `ADVAPI32!RegSetValueExW` at `0x100449ad6`
- `ADVAPI32!RegSetValueExW` at `0x100449b7c`
- `ADVAPI32!RegSetValueExW` at `0x100449c15`
- `ADVAPI32!RegSetValueExW` at `0x100449c9a`
- `ADVAPI32!RegCreateKeyExW` at `0x1004499cf`
- `ADVAPI32!RegCreateKeyExW` at `0x1004499cf`
- `ADVAPI32!RegFlushKey` at `0x100449cf5`
- `ADVAPI32!RegFlushKey` at `0x100449d19`
- `ADVAPI32!RegFlushKey` at `0x100449cf5`
- `ADVAPI32!RegFlushKey` at `0x100449d19`
- `ADVAPI32!RegCloseKey` at `0x100449d00`
- `ADVAPI32!RegCloseKey` at `0x100449d27`
- `ADVAPI32!RegCloseKey` at `0x100449d00`
- `ADVAPI32!RegCloseKey` at `0x100449d27`
- `ADVAPI32!RegOpenKeyExW` at `0x100449944`
- `ADVAPI32!RegOpenKeyExW` at `0x100449944`

## pseudocode

```c
__int64 __fastcall SQLLicense::WriteLicenseInfo(
        SQLLicense *this,
        wchar_t *a2,
        char a3,
        unsigned __int8 *a4,
        DWORD cbData,
        BYTE *a6,
        unsigned int a7,
        BYTE *a8,
        DWORD a9,
        BYTE *a10,
        unsigned int a11,
        BYTE *a12,
        unsigned int a13)
{
  int v14; // [rsp+50h] [rbp-88h]
  HKEY hKey; // [rsp+58h] [rbp-80h] BYREF
  LSTATUS v16; // [rsp+60h] [rbp-78h]
  LSTATUS v17; // [rsp+68h] [rbp-70h]
  LSTATUS v18; // [rsp+70h] [rbp-68h]
  LSTATUS v19; // [rsp+78h] [rbp-60h]
  LSTATUS v20; // [rsp+80h] [rbp-58h]
  LSTATUS v21; // [rsp+88h] [rbp-50h]
  LSTATUS v22; // [rsp+90h] [rbp-48h]
  LSTATUS v23; // [rsp+98h] [rbp-40h]
  HKEY phkResult; // [rsp+A0h] [rbp-38h] BYREF
  signed int v25; // [rsp+A8h] [rbp-30h]
  unsigned int v26; // [rsp+ACh] [rbp-2Ch]
  unsigned int v27; // [rsp+B0h] [rbp-28h]
  unsigned int v28; // [rsp+B4h] [rbp-24h]
  unsigned int v29; // [rsp+B8h] [rbp-20h]
  unsigned int v30; // [rsp+BCh] [rbp-1Ch]
  unsigned int v31; // [rsp+C0h] [rbp-18h]
  unsigned int v32; // [rsp+C4h] [rbp-14h]
  DWORD dwDisposition[4]; // [rsp+C8h] [rbp-10h] BYREF

  dwDisposition[0] = 0;
  hKey = 0;
  phkResult = 0;
  v16 = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v16 > 0 )
    v25 = (unsigned __int16)v16 | 0x80070000;
  else
    v25 = v16;
  v14 = v25;
  if ( v25 >= 0 )
  {
    v17 = RegOpenKeyExW(phkResult, a2, 0, 0xF003Fu, &hKey);
    if ( v17 > 0 )
      v26 = (unsigned __int16)v17 | 0x80070000;
    else
      v26 = v17;
    if ( v26 )
    {
      v18 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, dwDisposition);
      if ( v18 > 0 )
        v27 = (unsigned __int16)v18 | 0x80070000;
      else
        v27 = v18;
      v14 = v27;
    }
    if ( !v14 )
    {
      v19 = RegSetValueExW(hKey, CheckSumValueName, 0, 3u, a4, cbData);
      if ( v19 > 0 )
        v28 = (unsigned __int16)v19 | 0x80070000;
      else
        v28 = v19;
      v14 = v28;
      if ( v28 || a3 )
      {
        RegDeleteValueW(hKey, ProductIDValueName);
      }
      else
      {
        v20 = RegSetValueExW(hKey, ProductIDValueName, 0, 1u, a6, 2 * a7);
        if ( v20 > 0 )
          v29 = (unsigned __int16)v20 | 0x80070000;
        else
          v29 = v20;
        v14 = v29;
      }
      if ( v14 || a3 )
      {
        RegDeleteValueW(hKey, DigitalProductIDValueName);
      }
      else
      {
        v21 = RegSetValueExW(hKey, DigitalProductIDValueName, 0, 3u, a8, a9);
        if ( v21 > 0 )
          v30 = (unsigned __int16)v21 | 0x80070000;
        else
          v30 = v21;
        v14 = v30;
      }
      if ( v14 >= 0 )
      {
        v22 = RegSetValueExW(hKey, EditionTypeValueName, 0, 1u, a10, 2 * a11);
        if ( v22 > 0 )
          v31 = (unsigned __int16)v22 | 0x80070000;
        else
          v31 = v22;
        v14 = v31;
      }
      if ( v14 >= 0 )
      {
        v23 = RegSetValueExW(hKey, EditionValueName, 0, 1u, a12, 2 * a13);
        if ( v23 > 0 )
          v32 = (unsigned __int16)v23 | 0x80070000;
        else
          v32 = v23;
        v14 = v32;
      }
    }
  }
  if ( hKey )
  {
    RegFlushKey(hKey);
    RegCloseKey(hKey);
  }
  if ( phkResult )
  {
    RegFlushKey(phkResult);
    RegCloseKey(phkResult);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x100449880  mov     [rsp+lpData], r9
0x100449885  mov     [rsp+arg_10], r8b
0x10044988a  mov     [rsp+lpSubKey], rdx
0x10044988f  mov     [rsp+arg_0], rcx
0x100449894  sub     rsp, 0D8h
0x10044989b  mov     [rsp+0D8h+var_88], 0
0x1004498a3  mov     [rsp+0D8h+dwDisposition], 0
0x1004498ae  mov     [rsp+0D8h+hKey], 0
0x1004498b7  mov     [rsp+0D8h+phkResult], 0
0x1004498c3  lea     r8, [rsp+0D8h+phkResult]; phkResult
0x1004498cb  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1004498d2  xor     ecx, ecx; lpMachineName
0x1004498d4  call    cs:__imp_RegConnectRegistryW
0x1004498da  mov     [rsp+0D8h+var_78], eax
0x1004498de  cmp     [rsp+0D8h+var_78], 0
0x1004498e3  jg      short loc_1004498F2
0x1004498e5  mov     eax, [rsp+0D8h+var_78]
0x1004498e9  mov     [rsp+0D8h+var_30], eax
0x1004498f0  jmp     short loc_10044990B
0x1004498f2  mov     eax, [rsp+0D8h+var_78]
0x1004498f6  and     eax, 0FFFFh
0x1004498fb  or      eax, 70000h
0x100449900  bts     eax, 1Fh
0x100449904  mov     [rsp+0D8h+var_30], eax
0x10044990b  mov     eax, [rsp+0D8h+var_30]
0x100449912  mov     [rsp+0D8h+var_88], eax
0x100449916  cmp     [rsp+0D8h+var_88], 0
0x10044991b  jl      loc_100449CE8
0x100449921  lea     rax, [rsp+0D8h+hKey]
0x100449926  mov     [rsp+0D8h+var_B8], rax; phkResult
0x10044992b  mov     r9d, 0F003Fh; samDesired
0x100449931  xor     r8d, r8d; ulOptions
0x100449934  mov     rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x10044993c  mov     rcx, [rsp+0D8h+phkResult]; hKey
0x100449944  call    cs:__imp_RegOpenKeyExW
0x10044994a  mov     [rsp+0D8h+var_70], eax
0x10044994e  cmp     [rsp+0D8h+var_70], 0
0x100449953  jg      short loc_100449962
0x100449955  mov     eax, [rsp+0D8h+var_70]
0x100449959  mov     [rsp+0D8h+var_2C], eax
0x100449960  jmp     short loc_10044997B
0x100449962  mov     eax, [rsp+0D8h+var_70]
0x100449966  and     eax, 0FFFFh
0x10044996b  or      eax, 70000h
0x100449970  bts     eax, 1Fh
0x100449974  mov     [rsp+0D8h+var_2C], eax
0x10044997b  cmp     [rsp+0D8h+var_2C], 0
0x100449983  jz      loc_100449A11
0x100449989  lea     rax, [rsp+0D8h+dwDisposition]
0x100449991  mov     [rsp+0D8h+lpdwDisposition], rax; lpdwDisposition
0x100449996  lea     rax, [rsp+0D8h+hKey]
0x10044999b  mov     [rsp+0D8h+var_A0], rax; phkResult
0x1004499a0  mov     [rsp+0D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1004499a9  mov     [rsp+0D8h+samDesired], 0F003Fh; samDesired
0x1004499b1  mov     dword ptr [rsp+0D8h+var_B8], 0; dwOptions
0x1004499b9  xor     r9d, r9d; lpClass
0x1004499bc  xor     r8d, r8d; Reserved
0x1004499bf  mov     rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x1004499c7  mov     rcx, [rsp+0D8h+phkResult]; hKey
0x1004499cf  call    cs:__imp_RegCreateKeyExW
0x1004499d5  mov     [rsp+0D8h+var_68], eax
0x1004499d9  cmp     [rsp+0D8h+var_68], 0
0x1004499de  jg      short loc_1004499ED
0x1004499e0  mov     eax, [rsp+0D8h+var_68]
0x1004499e4  mov     [rsp+0D8h+var_28], eax
0x1004499eb  jmp     short loc_100449A06
0x1004499ed  mov     eax, [rsp+0D8h+var_68]
0x1004499f1  and     eax, 0FFFFh
0x1004499f6  or      eax, 70000h
0x1004499fb  bts     eax, 1Fh
0x1004499ff  mov     [rsp+0D8h+var_28], eax
0x100449a06  mov     eax, [rsp+0D8h+var_28]
0x100449a0d  mov     [rsp+0D8h+var_88], eax
0x100449a11  cmp     [rsp+0D8h+var_88], 0
0x100449a16  jnz     loc_100449CE8
0x100449a1c  mov     eax, [rsp+0D8h+cbData]
0x100449a23  mov     [rsp+0D8h+samDesired], eax; cbData
0x100449a27  mov     rax, [rsp+0D8h+lpData]
0x100449a2f  mov     [rsp+0D8h+var_B8], rax; lpData
0x100449a34  mov     r9d, 3; dwType
0x100449a3a  xor     r8d, r8d; Reserved
0x100449a3d  mov     rdx, cs:?CheckSumValueName@@3PEB_WEB; lpValueName
0x100449a44  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449a49  call    cs:__imp_RegSetValueExW
0x100449a4f  mov     [rsp+0D8h+var_60], eax
0x100449a53  cmp     [rsp+0D8h+var_60], 0
0x100449a58  jg      short loc_100449A67
0x100449a5a  mov     eax, [rsp+0D8h+var_60]
0x100449a5e  mov     [rsp+0D8h+var_24], eax
0x100449a65  jmp     short loc_100449A80
0x100449a67  mov     eax, [rsp+0D8h+var_60]
0x100449a6b  and     eax, 0FFFFh
0x100449a70  or      eax, 70000h
0x100449a75  bts     eax, 1Fh
0x100449a79  mov     [rsp+0D8h+var_24], eax
0x100449a80  mov     eax, [rsp+0D8h+var_24]
0x100449a87  mov     [rsp+0D8h+var_88], eax
0x100449a8b  cmp     [rsp+0D8h+var_88], 0
0x100449a90  jnz     loc_100449B26
0x100449a96  movzx   eax, [rsp+0D8h+arg_10]
0x100449a9e  test    eax, eax
0x100449aa0  jnz     loc_100449B26
0x100449aa6  mov     eax, [rsp+0D8h+arg_30]
0x100449aad  shl     rax, 1
0x100449ab0  mov     [rsp+0D8h+samDesired], eax; cbData
0x100449ab4  mov     rax, [rsp+0D8h+arg_28]
0x100449abc  mov     [rsp+0D8h+var_B8], rax; lpData
0x100449ac1  mov     r9d, 1; dwType
0x100449ac7  xor     r8d, r8d; Reserved
0x100449aca  mov     rdx, cs:?ProductIDValueName@@3PEB_WEB; lpValueName
0x100449ad1  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449ad6  call    cs:__imp_RegSetValueExW
0x100449adc  mov     [rsp+0D8h+var_58], eax
0x100449ae3  cmp     [rsp+0D8h+var_58], 0
0x100449aeb  jg      short loc_100449AFD
0x100449aed  mov     eax, [rsp+0D8h+var_58]
0x100449af4  mov     [rsp+0D8h+var_20], eax
0x100449afb  jmp     short loc_100449B19
0x100449afd  mov     eax, [rsp+0D8h+var_58]
0x100449b04  and     eax, 0FFFFh
0x100449b09  or      eax, 70000h
0x100449b0e  bts     eax, 1Fh
0x100449b12  mov     [rsp+0D8h+var_20], eax
0x100449b19  mov     eax, [rsp+0D8h+var_20]
0x100449b20  mov     [rsp+0D8h+var_88], eax
0x100449b24  jmp     short loc_100449B38
0x100449b26  mov     rdx, cs:?ProductIDValueName@@3PEB_WEB; lpValueName
0x100449b2d  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449b32  call    cs:__imp_RegDeleteValueW
0x100449b38  cmp     [rsp+0D8h+var_88], 0
0x100449b3d  jnz     loc_100449BCC
0x100449b43  movzx   eax, [rsp+0D8h+arg_10]
0x100449b4b  test    eax, eax
0x100449b4d  jnz     short loc_100449BCC
0x100449b4f  mov     eax, [rsp+0D8h+arg_40]
0x100449b56  mov     [rsp+0D8h+samDesired], eax; cbData
0x100449b5a  mov     rax, [rsp+0D8h+arg_38]
0x100449b62  mov     [rsp+0D8h+var_B8], rax; lpData
0x100449b67  mov     r9d, 3; dwType
0x100449b6d  xor     r8d, r8d; Reserved
0x100449b70  mov     rdx, cs:?DigitalProductIDValueName@@3PEB_WEB; lpValueName
0x100449b77  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449b7c  call    cs:__imp_RegSetValueExW
0x100449b82  mov     [rsp+0D8h+var_50], eax
0x100449b89  cmp     [rsp+0D8h+var_50], 0
0x100449b91  jg      short loc_100449BA3
0x100449b93  mov     eax, [rsp+0D8h+var_50]
0x100449b9a  mov     [rsp+0D8h+var_1C], eax
0x100449ba1  jmp     short loc_100449BBF
0x100449ba3  mov     eax, [rsp+0D8h+var_50]
0x100449baa  and     eax, 0FFFFh
0x100449baf  or      eax, 70000h
0x100449bb4  bts     eax, 1Fh
0x100449bb8  mov     [rsp+0D8h+var_1C], eax
0x100449bbf  mov     eax, [rsp+0D8h+var_1C]
0x100449bc6  mov     [rsp+0D8h+var_88], eax
0x100449bca  jmp     short loc_100449BDE
0x100449bcc  mov     rdx, cs:?DigitalProductIDValueName@@3PEB_WEB; lpValueName
0x100449bd3  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449bd8  call    cs:__imp_RegDeleteValueW
0x100449bde  cmp     [rsp+0D8h+var_88], 0
0x100449be3  jl      short loc_100449C63
0x100449be5  mov     eax, [rsp+0D8h+arg_50]
0x100449bec  shl     rax, 1
0x100449bef  mov     [rsp+0D8h+samDesired], eax; cbData
0x100449bf3  mov     rax, [rsp+0D8h+arg_48]
0x100449bfb  mov     [rsp+0D8h+var_B8], rax; lpData
0x100449c00  mov     r9d, 1; dwType
0x100449c06  xor     r8d, r8d; Reserved
0x100449c09  mov     rdx, cs:?EditionTypeValueName@@3PEB_WEB; lpValueName
0x100449c10  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449c15  call    cs:__imp_RegSetValueExW
0x100449c1b  mov     [rsp+0D8h+var_48], eax
0x100449c22  cmp     [rsp+0D8h+var_48], 0
0x100449c2a  jg      short loc_100449C3C
0x100449c2c  mov     eax, [rsp+0D8h+var_48]
0x100449c33  mov     [rsp+0D8h+var_18], eax
0x100449c3a  jmp     short loc_100449C58
0x100449c3c  mov     eax, [rsp+0D8h+var_48]
0x100449c43  and     eax, 0FFFFh
0x100449c48  or      eax, 70000h
0x100449c4d  bts     eax, 1Fh
0x100449c51  mov     [rsp+0D8h+var_18], eax
0x100449c58  mov     eax, [rsp+0D8h+var_18]
0x100449c5f  mov     [rsp+0D8h+var_88], eax
0x100449c63  cmp     [rsp+0D8h+var_88], 0
0x100449c68  jl      short loc_100449CE8
0x100449c6a  mov     eax, [rsp+0D8h+arg_60]
0x100449c71  shl     rax, 1
0x100449c74  mov     [rsp+0D8h+samDesired], eax; cbData
0x100449c78  mov     rax, [rsp+0D8h+arg_58]
0x100449c80  mov     [rsp+0D8h+var_B8], rax; lpData
0x100449c85  mov     r9d, 1; dwType
0x100449c8b  xor     r8d, r8d; Reserved
0x100449c8e  mov     rdx, cs:?EditionValueName@@3PEB_WEB; lpValueName
0x100449c95  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449c9a  call    cs:__imp_RegSetValueExW
0x100449ca0  mov     [rsp+0D8h+var_40], eax
0x100449ca7  cmp     [rsp+0D8h+var_40], 0
0x100449caf  jg      short loc_100449CC1
0x100449cb1  mov     eax, [rsp+0D8h+var_40]
0x100449cb8  mov     [rsp+0D8h+var_14], eax
0x100449cbf  jmp     short loc_100449CDD
0x100449cc1  mov     eax, [rsp+0D8h+var_40]
0x100449cc8  and     eax, 0FFFFh
0x100449ccd  or      eax, 70000h
0x100449cd2  bts     eax, 1Fh
0x100449cd6  mov     [rsp+0D8h+var_14], eax
0x100449cdd  mov     eax, [rsp+0D8h+var_14]
0x100449ce4  mov     [rsp+0D8h+var_88], eax
0x100449ce8  cmp     [rsp+0D8h+hKey], 0
0x100449cee  jz      short loc_100449D06
0x100449cf0  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449cf5  call    cs:__imp_RegFlushKey
0x100449cfb  mov     rcx, [rsp+0D8h+hKey]; hKey
0x100449d00  call    cs:__imp_RegCloseKey
0x100449d06  cmp     [rsp+0D8h+phkResult], 0
0x100449d0f  jz      short loc_100449D2D
0x100449d11  mov     rcx, [rsp+0D8h+phkResult]; hKey
0x100449d19  call    cs:__imp_RegFlushKey
0x100449d1f  mov     rcx, [rsp+0D8h+phkResult]; hKey
0x100449d27  call    cs:__imp_RegCloseKey
0x100449d2d  mov     eax, [rsp+0D8h+var_88]
0x100449d31  add     rsp, 0D8h
0x100449d38  retn
```
