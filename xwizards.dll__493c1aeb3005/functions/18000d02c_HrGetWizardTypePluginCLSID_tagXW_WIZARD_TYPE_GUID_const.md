# HrGetWizardTypePluginCLSID(tagXW_WIZARD_TYPE,_GUID * const)

- ea: `0x18000d02c`
- end: `0x18000d244`
- name: `?HrGetWizardTypePluginCLSID@@YAJW4tagXW_WIZARD_TYPE@@QEAU_GUID@@@Z`
- size: `536`
- prototype: `int __high(enum tagXW_WIZARD_TYPE, struct _GUID *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fa50`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000d02c`
- `0x18000e87c`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d148`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d148`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d100`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d100`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d162`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d162`

## string_xrefs

- `0x18000d12e`: `Plug-in Clsid`

## pseudocode

```c
__int64 __fastcall HrGetWizardTypePluginCLSID(__int64 a1, GUID *a2)
{
  __int64 v3; // rax
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[72]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR Data[40]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x47u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x47u, L"Types");
  StringCchCatW(SubKey, 0x47u, &qword_18003C618);
  v3 = -1;
  do
    ++v3;
  while ( SubKey[v3] );
  swprintf_sfn(&SubKey[v3], 71 - v3, L"%#0*.*lx");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    memset_0(Data, 0, sizeof(Data));
    cbData = 80;
    v4 = RegQueryValueExW(hKey, L"Plug-in Clsid", 0, 0, (LPBYTE)Data, &cbData);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)SubKey,
          v5);
    }
    else
    {
      v5 = CLSIDFromString(Data, a2);
    }
    RegCloseKey(hKey);
    goto LABEL_15;
  }
  v5 = -2147467263;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      136,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      1);
LABEL_15:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    WPP_SF_d(v6[2], 137, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000d02c  mov     [rsp-8+arg_10], rbx
0x18000d031  mov     [rsp-8+arg_18], rsi
0x18000d036  push    rbp
0x18000d037  push    rdi
0x18000d038  push    r14
0x18000d03a  lea     rbp, [rsp-30h]
0x18000d03f  sub     rsp, 130h
0x18000d046  mov     rax, cs:__security_cookie
0x18000d04d  xor     rax, rsp
0x18000d050  mov     [rbp+40h+var_20], rax
0x18000d054  xor     r14d, r14d
0x18000d057  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d05e  mov     rsi, rdx
0x18000d061  mov     [rsp+140h+hKey], r14
0x18000d066  mov     edi, ecx
0x18000d068  mov     [rsp+140h+SubKey], r14w
0x18000d06e  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000d073  lea     ebx, [r14+47h]
0x18000d077  mov     edx, ebx; unsigned __int64
0x18000d079  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d07e  lea     r8, aTypes; "Types"
0x18000d085  mov     edx, ebx; unsigned __int64
0x18000d087  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000d08c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d091  lea     r8, qword_18003C618; unsigned __int16 *
0x18000d098  mov     edx, ebx; unsigned __int64
0x18000d09a  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000d09f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d0a4  lea     rcx, [rsp+140h+SubKey]
0x18000d0a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d0ad  inc     rax
0x18000d0b0  cmp     [rcx+rax*2], r14w
0x18000d0b5  jnz     short loc_18000D0AD
0x18000d0b7  sub     rbx, rax
0x18000d0ba  mov     dword ptr [rsp+140h+lpcbData], edi
0x18000d0be  mov     r9d, 8
0x18000d0c4  lea     rcx, [rsp+140h+SubKey]
0x18000d0c9  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000d0cd  mov     dword ptr [rsp+140h+phkResult], r9d
0x18000d0d2  mov     rdx, rbx; unsigned __int64
0x18000d0d5  lea     r8, a0Lx; "%#0*.*lx"
0x18000d0dc  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x18000d0e1  lea     rax, [rsp+140h+hKey]
0x18000d0e6  mov     r9d, 20019h; samDesired
0x18000d0ec  xor     r8d, r8d; ulOptions
0x18000d0ef  mov     [rsp+140h+phkResult], rax; phkResult
0x18000d0f4  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x18000d0f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d100  call    cs:__imp_RegOpenKeyExW
0x18000d106  test    eax, eax
0x18000d108  jnz     loc_18000D1B4
0x18000d10e  lea     ebx, [rax+50h]
0x18000d111  xor     edx, edx; Val
0x18000d113  mov     r8d, ebx; Size
0x18000d116  lea     rcx, [rbp+40h+Data]; void *
0x18000d11a  call    memset_0
0x18000d11f  mov     rcx, [rsp+140h+hKey]; hKey
0x18000d124  lea     rax, [rsp+140h+cbData]
0x18000d129  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18000d12e  lea     rdx, aPlugInClsid; "Plug-in Clsid"
0x18000d135  lea     rax, [rbp+40h+Data]
0x18000d139  mov     [rsp+140h+cbData], ebx
0x18000d13d  xor     r9d, r9d; lpType
0x18000d140  mov     [rsp+140h+phkResult], rax; lpData
0x18000d145  xor     r8d, r8d; lpReserved
0x18000d148  call    cs:__imp_RegQueryValueExW
0x18000d14e  lea     rdi, WPP_GLOBAL_Control
0x18000d155  mov     ebx, eax
0x18000d157  test    eax, eax
0x18000d159  jnz     short loc_18000D16C
0x18000d15b  mov     rdx, rsi; pclsid
0x18000d15e  lea     rcx, [rbp+40h+Data]; lpsz
0x18000d162  call    cs:__imp_CLSIDFromString
0x18000d168  mov     ebx, eax
0x18000d16a  jmp     short loc_18000D1A7
0x18000d16c  jle     short loc_18000D177
0x18000d16e  movzx   ebx, ax
0x18000d171  or      ebx, 80070000h
0x18000d177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d17e  cmp     rcx, rdi
0x18000d181  jz      short loc_18000D1A7
0x18000d183  test    byte ptr [rcx+1Ch], 4
0x18000d187  jz      short loc_18000D1A7
0x18000d189  mov     rcx, [rcx+10h]
0x18000d18d  lea     r9, [rsp+140h+SubKey]
0x18000d192  mov     edx, 87h
0x18000d197  mov     dword ptr [rsp+140h+phkResult], ebx
0x18000d19b  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d1a2  call    WPP_SF_SD
0x18000d1a7  mov     rcx, [rsp+140h+hKey]; hKey
0x18000d1ac  call    cs:__imp_RegCloseKey
0x18000d1b2  jmp     short loc_18000D1F4
0x18000d1b4  mov     ebx, 80004001h
0x18000d1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c0  lea     rdi, WPP_GLOBAL_Control
0x18000d1c7  cmp     rcx, rdi
0x18000d1ca  jz      short loc_18000D21E
0x18000d1cc  test    byte ptr [rcx+1Ch], 10h
0x18000d1d0  jz      short loc_18000D1FB
0x18000d1d2  mov     rcx, [rcx+10h]
0x18000d1d6  lea     r9, [rsp+140h+SubKey]
0x18000d1db  mov     edx, 88h
0x18000d1e0  mov     dword ptr [rsp+140h+phkResult], 80004001h
0x18000d1e8  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d1ef  call    WPP_SF_SD
0x18000d1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1fb  cmp     rcx, rdi
0x18000d1fe  jz      short loc_18000D21E
0x18000d200  test    byte ptr [rcx+1Ch], 10h
0x18000d204  jz      short loc_18000D21E
0x18000d206  mov     rcx, [rcx+10h]
0x18000d20a  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d211  mov     edx, 89h
0x18000d216  mov     r9d, ebx
0x18000d219  call    WPP_SF_d
0x18000d21e  mov     eax, ebx
0x18000d220  mov     rcx, [rbp+40h+var_20]
0x18000d224  xor     rcx, rsp; StackCookie
0x18000d227  call    __security_check_cookie
0x18000d22c  lea     r11, [rsp+140h+var_10]
0x18000d234  mov     rbx, [r11+30h]
0x18000d238  mov     rsi, [r11+38h]
0x18000d23c  mov     rsp, r11
0x18000d23f  pop     r14
0x18000d241  pop     rdi
0x18000d242  pop     rbp
0x18000d243  retn
```
