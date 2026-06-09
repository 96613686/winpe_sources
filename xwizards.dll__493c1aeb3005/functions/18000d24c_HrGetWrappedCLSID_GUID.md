# HrGetWrappedCLSID(_GUID *)

- ea: `0x18000d24c`
- end: `0x18000d434`
- name: `?HrGetWrappedCLSID@@YAJPEAU_GUID@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000fab0`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000d24c`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d337`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d301`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d301`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d352`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000d352`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000d2cd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000d2cd`

## string_xrefs

- `0x18000d320`: `Wrapped CLSID`
- `0x18000d29d`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetWrappedCLSID(LPCLSID pclsid)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  PVOID *v5; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[112]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  cbData = 80;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, &qword_18003C618);
  StringFromGUID2(pclsid, sz, 40);
  StringCchCatW(SubKey, 0x69u, sz);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v3 = v2;
  if ( !v2 )
  {
    v4 = RegQueryValueExW(hKey, L"Wrapped CLSID", 0, 0, (LPBYTE)sz, &cbData);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        v3 = 1;
      }
      else
      {
        if ( v4 > 0 )
          v3 = (unsigned __int16)v4 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v3);
      }
    }
    else
    {
      v3 = CLSIDFromString(sz, pclsid);
    }
    RegCloseKey(hKey);
    goto LABEL_17;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_18:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
        WPP_SF_d(v5[2], 142, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v3);
      return v3;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v3);
LABEL_17:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  return v3;
}

```

## disassembly

```asm
0x18000d24c  push    rbp
0x18000d24e  push    rbx
0x18000d24f  push    rsi
0x18000d250  push    rdi
0x18000d251  lea     rbp, [rsp-88h]
0x18000d259  sub     rsp, 188h
0x18000d260  mov     rax, cs:__security_cookie
0x18000d267  xor     rax, rsp
0x18000d26a  mov     [rbp+0A0h+var_30], rax
0x18000d26e  xor     eax, eax
0x18000d270  mov     [rsp+1A0h+hKey], 0
0x18000d279  mov     rsi, rcx
0x18000d27c  mov     [rsp+1A0h+cbData], 50h ; 'P'
0x18000d284  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d28b  mov     [rbp+0A0h+SubKey], ax
0x18000d28f  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000d293  lea     ebx, [rax+69h]
0x18000d296  mov     edx, ebx; unsigned __int64
0x18000d298  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d29d  lea     r8, aComponents; "Components"
0x18000d2a4  mov     edx, ebx; unsigned __int64
0x18000d2a6  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000d2aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d2af  lea     r8, qword_18003C618; unsigned __int16 *
0x18000d2b6  mov     edx, ebx; unsigned __int64
0x18000d2b8  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000d2bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d2c1  lea     r8d, [rbx-41h]; cchMax
0x18000d2c5  mov     rcx, rsi; rguid
0x18000d2c8  lea     rdx, [rsp+1A0h+sz]; lpsz
0x18000d2cd  call    cs:__imp_StringFromGUID2
0x18000d2d3  lea     r8, [rsp+1A0h+sz]; unsigned __int16 *
0x18000d2d8  mov     edx, ebx; unsigned __int64
0x18000d2da  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000d2de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d2e3  lea     rax, [rsp+1A0h+hKey]
0x18000d2e8  mov     r9d, 20019h; samDesired
0x18000d2ee  xor     r8d, r8d; ulOptions
0x18000d2f1  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18000d2f6  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x18000d2fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d301  call    cs:__imp_RegOpenKeyExW
0x18000d307  mov     ebx, eax
0x18000d309  test    eax, eax
0x18000d30b  jnz     loc_18000D3AF
0x18000d311  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000d316  lea     rax, [rsp+1A0h+cbData]
0x18000d31b  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18000d320  lea     rdx, aWrappedClsid; "Wrapped CLSID"
0x18000d327  lea     rax, [rsp+1A0h+sz]
0x18000d32c  xor     r9d, r9d; lpType
0x18000d32f  xor     r8d, r8d; lpReserved
0x18000d332  mov     [rsp+1A0h+phkResult], rax; lpData
0x18000d337  call    cs:__imp_RegQueryValueExW
0x18000d33d  lea     rdi, WPP_GLOBAL_Control
0x18000d344  mov     ebx, eax
0x18000d346  test    eax, eax
0x18000d348  jnz     short loc_18000D35C
0x18000d34a  mov     rdx, rsi; pclsid
0x18000d34d  lea     rcx, [rsp+1A0h+sz]; lpsz
0x18000d352  call    cs:__imp_CLSIDFromString
0x18000d358  mov     ebx, eax
0x18000d35a  jmp     short loc_18000D3A2
0x18000d35c  cmp     eax, 2
0x18000d35f  jnz     short loc_18000D366
0x18000d361  lea     ebx, [rax-1]
0x18000d364  jmp     short loc_18000D3A2
0x18000d366  test    eax, eax
0x18000d368  jle     short loc_18000D373
0x18000d36a  movzx   ebx, ax
0x18000d36d  or      ebx, 80070000h
0x18000d373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d37a  cmp     rcx, rdi
0x18000d37d  jz      short loc_18000D3A2
0x18000d37f  test    byte ptr [rcx+1Ch], 4
0x18000d383  jz      short loc_18000D3A2
0x18000d385  mov     rcx, [rcx+10h]
0x18000d389  lea     r9, [rbp+0A0h+SubKey]
0x18000d38d  mov     edx, 8Ch
0x18000d392  mov     dword ptr [rsp+1A0h+phkResult], ebx
0x18000d396  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d39d  call    WPP_SF_SD
0x18000d3a2  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000d3a7  call    cs:__imp_RegCloseKey
0x18000d3ad  jmp     short loc_18000D3F0
0x18000d3af  jle     short loc_18000D3BA
0x18000d3b1  movzx   ebx, ax
0x18000d3b4  or      ebx, 80070000h
0x18000d3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3c1  lea     rdi, WPP_GLOBAL_Control
0x18000d3c8  cmp     rcx, rdi
0x18000d3cb  jz      short loc_18000D41A
0x18000d3cd  test    byte ptr [rcx+1Ch], 4
0x18000d3d1  jz      short loc_18000D3F7
0x18000d3d3  mov     rcx, [rcx+10h]
0x18000d3d7  lea     r9, [rbp+0A0h+SubKey]
0x18000d3db  mov     edx, 8Dh
0x18000d3e0  mov     dword ptr [rsp+1A0h+phkResult], ebx
0x18000d3e4  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d3eb  call    WPP_SF_SD
0x18000d3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3f7  cmp     rcx, rdi
0x18000d3fa  jz      short loc_18000D41A
0x18000d3fc  test    byte ptr [rcx+1Ch], 10h
0x18000d400  jz      short loc_18000D41A
0x18000d402  mov     rcx, [rcx+10h]
0x18000d406  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d40d  mov     edx, 8Eh
0x18000d412  mov     r9d, ebx
0x18000d415  call    WPP_SF_d
0x18000d41a  mov     eax, ebx
0x18000d41c  mov     rcx, [rbp+0A0h+var_30]
0x18000d420  xor     rcx, rsp; StackCookie
0x18000d423  call    __security_check_cookie
0x18000d428  add     rsp, 188h
0x18000d42f  pop     rdi
0x18000d430  pop     rsi
0x18000d431  pop     rbx
0x18000d432  pop     rbp
0x18000d433  retn
```
