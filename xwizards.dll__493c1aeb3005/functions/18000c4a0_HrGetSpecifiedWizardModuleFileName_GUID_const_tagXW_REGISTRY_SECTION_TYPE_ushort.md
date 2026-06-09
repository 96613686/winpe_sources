# HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)

- ea: `0x18000c4a0`
- end: `0x18000c775`
- name: `?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z`
- size: `725`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c3ac`
- `0x18000de90`
- `0x18000df3c`
- `0x18000f930`
- `0x18000f9f0`

## callees

- `0x180004370`
- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000c4a0`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c5d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c5d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c59a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c59a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c631`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c575`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c575`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c610`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c610`

## string_xrefs

- `0x18000c523`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetSpecifiedWizardModuleFileName(const GUID *a1, int a2, unsigned __int16 **a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  SIZE_T v12; // rcx
  unsigned int v13; // esi
  unsigned __int16 *v14; // rax
  unsigned int LastErrorHRESULT; // eax
  PVOID *v16; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[112]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dest[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Data[264]; // [rsp+330h] [rbp+230h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  v6 = L"Components";
  if ( a2 != 1 )
    v6 = L"Factory";
  StringCchCatW(SubKey, 0x69u, v6);
  StringCchCatW(SubKey, 0x69u, &qword_18003C618);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( SubKey[v8] );
  StringFromGUID2(a1, &SubKey[v8], 39);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v10 = v9;
  if ( !v9 )
  {
    v11 = RegQueryValueExW(hKey, L"File Name", 0, 0, (LPBYTE)Data, &cbData);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)SubKey,
          v10);
    }
    else if ( ExpandEnvironmentStringsForUserW(0, Data, Dest, 0x105u) )
    {
      do
        ++v7;
      while ( Dest[v7] );
      v12 = 2LL * (unsigned int)(v7 + 1);
      v13 = v7 + 1;
      v14 = (unsigned __int16 *)CoTaskMemAlloc(v12);
      *a3 = v14;
      if ( v14 )
      {
        *v14 = 0;
        StringCchCopyW(*a3, v13, Dest);
      }
      else
      {
        v10 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)Dest,
            14);
      }
    }
    else
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      v10 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)Data,
          LastErrorHRESULT);
    }
    RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
LABEL_29:
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x10) != 0 )
        WPP_SF_d(v16[2], 82, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v10);
      return v10;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v10);
LABEL_28:
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  return v10;
}

```

## disassembly

```asm
0x18000c4a0  mov     [rsp-8+arg_8], rbx
0x18000c4a5  mov     [rsp-8+arg_18], rsi
0x18000c4aa  push    rbp
0x18000c4ab  push    rdi
0x18000c4ac  push    r12
0x18000c4ae  push    r14
0x18000c4b0  push    r15
0x18000c4b2  lea     rbp, [rsp-450h]
0x18000c4ba  sub     rsp, 550h
0x18000c4c1  mov     rax, cs:__security_cookie
0x18000c4c8  xor     rax, rsp
0x18000c4cb  mov     [rbp+470h+var_30], rax
0x18000c4d2  mov     r14, r8
0x18000c4d5  mov     ebx, edx
0x18000c4d7  mov     rdi, rcx
0x18000c4da  mov     esi, 20Ah
0x18000c4df  xor     r15d, r15d
0x18000c4e2  lea     rcx, [rbp+470h+Data]; void *
0x18000c4e9  mov     r8d, esi; Size
0x18000c4ec  mov     [rsp+570h+hKey], r15
0x18000c4f1  xor     edx, edx; Val
0x18000c4f3  call    memset_0
0x18000c4f8  mov     [rsp+570h+cbData], esi
0x18000c4fc  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c503  lea     esi, [r15+69h]
0x18000c507  mov     [rsp+570h+SubKey], r15w
0x18000c50d  mov     edx, esi; unsigned __int64
0x18000c50f  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000c514  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c519  lea     rax, aFactory_0; "Factory"
0x18000c520  cmp     ebx, 1
0x18000c523  lea     r8, aComponents; "Components"
0x18000c52a  mov     edx, esi; unsigned __int64
0x18000c52c  cmovnz  r8, rax; unsigned __int16 *
0x18000c530  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000c535  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c53a  lea     r8, qword_18003C618; unsigned __int16 *
0x18000c541  mov     edx, esi; unsigned __int64
0x18000c543  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000c548  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c54d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c551  lea     rcx, [rsp+570h+SubKey]
0x18000c556  mov     rax, rsi
0x18000c559  inc     rax
0x18000c55c  cmp     [rcx+rax*2], r15w
0x18000c561  jnz     short loc_18000C559
0x18000c563  lea     rdx, [rsp+570h+SubKey]
0x18000c568  mov     r8d, 27h ; '''; cchMax
0x18000c56e  lea     rdx, [rdx+rax*2]; lpsz
0x18000c572  mov     rcx, rdi; rguid
0x18000c575  call    cs:__imp_StringFromGUID2
0x18000c57b  lea     rax, [rsp+570h+hKey]
0x18000c580  mov     r9d, 20019h; samDesired
0x18000c586  xor     r8d, r8d; ulOptions
0x18000c589  mov     [rsp+570h+phkResult], rax; phkResult
0x18000c58e  lea     rdx, [rsp+570h+SubKey]; lpSubKey
0x18000c593  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c59a  call    cs:__imp_RegOpenKeyExW
0x18000c5a0  lea     r12, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000c5a7  mov     ebx, eax
0x18000c5a9  test    eax, eax
0x18000c5ab  jnz     loc_18000C6E4
0x18000c5b1  mov     rcx, [rsp+570h+hKey]; hKey
0x18000c5b6  lea     rax, [rsp+570h+cbData]
0x18000c5bb  mov     [rsp+570h+lpcbData], rax; lpcbData
0x18000c5c0  lea     rdx, aFileName; "File Name"
0x18000c5c7  lea     rax, [rbp+470h+Data]
0x18000c5ce  xor     r9d, r9d; lpType
0x18000c5d1  xor     r8d, r8d; lpReserved
0x18000c5d4  mov     [rsp+570h+phkResult], rax; lpData
0x18000c5d9  call    cs:__imp_RegQueryValueExW
0x18000c5df  mov     ebx, eax
0x18000c5e1  test    eax, eax
0x18000c5e3  jle     short loc_18000C5EE
0x18000c5e5  movzx   ebx, ax
0x18000c5e8  or      ebx, 80070000h
0x18000c5ee  lea     rdi, WPP_GLOBAL_Control
0x18000c5f5  test    ebx, ebx
0x18000c5f7  js      loc_18000C6AB
0x18000c5fd  mov     r9d, 105h; dwSize
0x18000c603  lea     r8, [rbp+470h+Dest]; lpDest
0x18000c607  lea     rdx, [rbp+470h+Data]; lpSrc
0x18000c60e  xor     ecx, ecx; hToken
0x18000c610  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000c616  test    eax, eax
0x18000c618  jz      short loc_18000C680
0x18000c61a  lea     rax, [rbp+470h+Dest]
0x18000c61e  inc     rsi
0x18000c621  cmp     [rax+rsi*2], r15w
0x18000c626  jnz     short loc_18000C61E
0x18000c628  lea     eax, [rsi+1]
0x18000c62b  lea     rcx, [rax+rax]; cb
0x18000c62f  mov     esi, eax
0x18000c631  call    cs:__imp_CoTaskMemAlloc
0x18000c637  mov     [r14], rax
0x18000c63a  test    rax, rax
0x18000c63d  jz      short loc_18000C656
0x18000c63f  mov     [rax], r15w
0x18000c643  lea     r8, [rbp+470h+Dest]; unsigned __int16 *
0x18000c647  mov     rcx, [r14]; unsigned __int16 *
0x18000c64a  mov     edx, esi; unsigned __int64
0x18000c64c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c651  jmp     loc_18000C6D7
0x18000c656  mov     ebx, 8007000Eh
0x18000c65b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c662  cmp     rcx, rdi
0x18000c665  jz      short loc_18000C6D7
0x18000c667  test    byte ptr [rcx+1Ch], 4
0x18000c66b  jz      short loc_18000C6D7
0x18000c66d  mov     edx, 4Eh ; 'N'
0x18000c672  mov     dword ptr [rsp+570h+phkResult], 8007000Eh
0x18000c67a  lea     r9, [rbp+470h+Dest]
0x18000c67e  jmp     short loc_18000C6CB
0x18000c680  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000c685  mov     ebx, eax
0x18000c687  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c68e  cmp     rcx, rdi
0x18000c691  jz      short loc_18000C6D7
0x18000c693  test    byte ptr [rcx+1Ch], 4
0x18000c697  jz      short loc_18000C6D7
0x18000c699  mov     edx, 4Fh ; 'O'
0x18000c69e  mov     dword ptr [rsp+570h+phkResult], eax
0x18000c6a2  lea     r9, [rbp+470h+Data]
0x18000c6a9  jmp     short loc_18000C6CB
0x18000c6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6b2  cmp     rcx, rdi
0x18000c6b5  jz      short loc_18000C6D7
0x18000c6b7  test    byte ptr [rcx+1Ch], 4
0x18000c6bb  jz      short loc_18000C6D7
0x18000c6bd  mov     edx, 50h ; 'P'
0x18000c6c2  mov     dword ptr [rsp+570h+phkResult], ebx
0x18000c6c6  lea     r9, [rsp+570h+SubKey]
0x18000c6cb  mov     rcx, [rcx+10h]
0x18000c6cf  mov     r8, r12
0x18000c6d2  call    WPP_SF_SD
0x18000c6d7  mov     rcx, [rsp+570h+hKey]; hKey
0x18000c6dc  call    cs:__imp_RegCloseKey
0x18000c6e2  jmp     short loc_18000C722
0x18000c6e4  jle     short loc_18000C6EF
0x18000c6e6  movzx   ebx, ax
0x18000c6e9  or      ebx, 80070000h
0x18000c6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6f6  lea     rdi, WPP_GLOBAL_Control
0x18000c6fd  cmp     rcx, rdi
0x18000c700  jz      short loc_18000C748
0x18000c702  test    byte ptr [rcx+1Ch], 10h
0x18000c706  jz      short loc_18000C729
0x18000c708  mov     rcx, [rcx+10h]
0x18000c70c  lea     r9, [rsp+570h+SubKey]
0x18000c711  mov     edx, 51h ; 'Q'
0x18000c716  mov     dword ptr [rsp+570h+phkResult], ebx
0x18000c71a  mov     r8, r12
0x18000c71d  call    WPP_SF_SD
0x18000c722  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c729  cmp     rcx, rdi
0x18000c72c  jz      short loc_18000C748
0x18000c72e  test    byte ptr [rcx+1Ch], 10h
0x18000c732  jz      short loc_18000C748
0x18000c734  mov     rcx, [rcx+10h]
0x18000c738  mov     edx, 52h ; 'R'
0x18000c73d  mov     r9d, ebx
0x18000c740  mov     r8, r12
0x18000c743  call    WPP_SF_d
0x18000c748  mov     eax, ebx
0x18000c74a  mov     rcx, [rbp+470h+var_30]
0x18000c751  xor     rcx, rsp; StackCookie
0x18000c754  call    __security_check_cookie
0x18000c759  lea     r11, [rsp+570h+var_20]
0x18000c761  mov     rbx, [r11+38h]
0x18000c765  mov     rsi, [r11+48h]
0x18000c769  mov     rsp, r11
0x18000c76c  pop     r15
0x18000c76e  pop     r14
0x18000c770  pop     r12
0x18000c772  pop     rdi
0x18000c773  pop     rbp
0x18000c774  retn
```
