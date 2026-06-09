# HrGetSpecifiedWizardModuleFileName(_GUID const *,tagXW_REGISTRY_SECTION_TYPE,ushort * *)

- ea: `0x18000e140`
- end: `0x18000e405`
- name: `?HrGetSpecifiedWizardModuleFileName@@YAJPEBU_GUID@@W4tagXW_REGISTRY_SECTION_TYPE@@PEAPEAG@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010518`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000e140`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e2c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e2c1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e205`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e205`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e22a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e22a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e36c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e269`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e269`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000e2a0`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000e2a0`

## string_xrefs

- `0x18000e1b7`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetSpecifiedWizardModuleFileName(const GUID *a1, __int64 a2, unsigned __int16 **a3)
{
  __int64 v5; // rsi
  __int64 v6; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  SIZE_T v10; // rcx
  unsigned int v11; // esi
  unsigned __int16 *v12; // rax
  unsigned int LastErrorHRESULT; // eax
  PVOID *v14; // rcx
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
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, &qword_180017630);
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( SubKey[v6] );
  StringFromGUID2(a1, &SubKey[v6], 39);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( !v7 )
  {
    v9 = RegQueryValueExW(hKey, L"File Name", 0, 0, (LPBYTE)Data, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)SubKey,
          v8);
    }
    else if ( ExpandEnvironmentStringsForUserW(0, Data, Dest, 0x105u) )
    {
      do
        ++v5;
      while ( Dest[v5] );
      v10 = 2LL * (unsigned int)(v5 + 1);
      v11 = v5 + 1;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(v10);
      *a3 = v12;
      if ( v12 )
      {
        *v12 = 0;
        StringCchCopyW(*a3, v11, Dest);
      }
      else
      {
        v8 = -2147024882;
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
      v8 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)Data,
          LastErrorHRESULT);
    }
    RegCloseKey(hKey);
    goto LABEL_26;
  }
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
LABEL_27:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
        WPP_SF_D(v14[2], 82, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v8);
      return v8;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v8);
LABEL_26:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  return v8;
}

```

## disassembly

```asm
0x18000e140  mov     [rsp-8+arg_8], rbx
0x18000e145  mov     [rsp-8+arg_18], rsi
0x18000e14a  push    rbp
0x18000e14b  push    rdi
0x18000e14c  push    r12
0x18000e14e  push    r14
0x18000e150  push    r15
0x18000e152  lea     rbp, [rsp-450h]
0x18000e15a  sub     rsp, 550h
0x18000e161  mov     rax, cs:__security_cookie
0x18000e168  xor     rax, rsp
0x18000e16b  mov     [rbp+470h+var_30], rax
0x18000e172  mov     r14, r8
0x18000e175  mov     rbx, rcx
0x18000e178  mov     edi, 20Ah
0x18000e17d  lea     rcx, [rbp+470h+Data]; void *
0x18000e184  xor     r15d, r15d
0x18000e187  mov     r8d, edi; Size
0x18000e18a  xor     edx, edx; Val
0x18000e18c  mov     [rsp+570h+hKey], r15
0x18000e191  call    memset_0
0x18000e196  mov     [rsp+570h+cbData], edi
0x18000e19a  lea     r8, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e1a1  lea     edi, [r15+69h]
0x18000e1a5  mov     [rsp+570h+SubKey], r15w
0x18000e1ab  mov     edx, edi; unsigned __int64
0x18000e1ad  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000e1b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1b7  lea     r8, aComponents_0; "Components"
0x18000e1be  mov     edx, edi; unsigned __int64
0x18000e1c0  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000e1c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e1ca  lea     r8, qword_180017630; unsigned __int16 *
0x18000e1d1  mov     edx, edi; unsigned __int64
0x18000e1d3  lea     rcx, [rsp+570h+SubKey]; unsigned __int16 *
0x18000e1d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e1dd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e1e1  lea     rcx, [rsp+570h+SubKey]
0x18000e1e6  mov     rax, rsi
0x18000e1e9  inc     rax
0x18000e1ec  cmp     [rcx+rax*2], r15w
0x18000e1f1  jnz     short loc_18000E1E9
0x18000e1f3  lea     rdx, [rsp+570h+SubKey]
0x18000e1f8  mov     r8d, 27h ; '''; cchMax
0x18000e1fe  lea     rdx, [rdx+rax*2]; lpsz
0x18000e202  mov     rcx, rbx; rguid
0x18000e205  call    cs:__imp_StringFromGUID2
0x18000e20b  lea     rax, [rsp+570h+hKey]
0x18000e210  mov     r9d, 20019h; samDesired
0x18000e216  xor     r8d, r8d; ulOptions
0x18000e219  mov     [rsp+570h+phkResult], rax; phkResult
0x18000e21e  lea     rdx, [rsp+570h+SubKey]; lpSubKey
0x18000e223  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e22a  call    cs:__imp_RegOpenKeyExW
0x18000e230  lea     r12, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000e237  mov     ebx, eax
0x18000e239  test    eax, eax
0x18000e23b  jnz     loc_18000E374
0x18000e241  mov     rcx, [rsp+570h+hKey]; hKey
0x18000e246  lea     rax, [rsp+570h+cbData]
0x18000e24b  mov     [rsp+570h+lpcbData], rax; lpcbData
0x18000e250  lea     rdx, aFileName_2; "File Name"
0x18000e257  lea     rax, [rbp+470h+Data]
0x18000e25e  xor     r9d, r9d; lpType
0x18000e261  xor     r8d, r8d; lpReserved
0x18000e264  mov     [rsp+570h+phkResult], rax; lpData
0x18000e269  call    cs:__imp_RegQueryValueExW
0x18000e26f  mov     ebx, eax
0x18000e271  test    eax, eax
0x18000e273  jle     short loc_18000E27E
0x18000e275  movzx   ebx, ax
0x18000e278  or      ebx, 80070000h
0x18000e27e  lea     rdi, WPP_GLOBAL_Control
0x18000e285  test    ebx, ebx
0x18000e287  js      loc_18000E33B
0x18000e28d  mov     r9d, 105h; dwSize
0x18000e293  lea     r8, [rbp+470h+Dest]; lpDest
0x18000e297  lea     rdx, [rbp+470h+Data]; lpSrc
0x18000e29e  xor     ecx, ecx; hToken
0x18000e2a0  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000e2a6  test    eax, eax
0x18000e2a8  jz      short loc_18000E310
0x18000e2aa  lea     rax, [rbp+470h+Dest]
0x18000e2ae  inc     rsi
0x18000e2b1  cmp     [rax+rsi*2], r15w
0x18000e2b6  jnz     short loc_18000E2AE
0x18000e2b8  lea     eax, [rsi+1]
0x18000e2bb  lea     rcx, [rax+rax]; cb
0x18000e2bf  mov     esi, eax
0x18000e2c1  call    cs:__imp_CoTaskMemAlloc
0x18000e2c7  mov     [r14], rax
0x18000e2ca  test    rax, rax
0x18000e2cd  jz      short loc_18000E2E6
0x18000e2cf  mov     [rax], r15w
0x18000e2d3  lea     r8, [rbp+470h+Dest]; unsigned __int16 *
0x18000e2d7  mov     rcx, [r14]; unsigned __int16 *
0x18000e2da  mov     edx, esi; unsigned __int64
0x18000e2dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e2e1  jmp     loc_18000E367
0x18000e2e6  mov     ebx, 8007000Eh
0x18000e2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2f2  cmp     rcx, rdi
0x18000e2f5  jz      short loc_18000E367
0x18000e2f7  test    byte ptr [rcx+1Ch], 4
0x18000e2fb  jz      short loc_18000E367
0x18000e2fd  mov     edx, 4Eh ; 'N'
0x18000e302  mov     dword ptr [rsp+570h+phkResult], 8007000Eh
0x18000e30a  lea     r9, [rbp+470h+Dest]
0x18000e30e  jmp     short loc_18000E35B
0x18000e310  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000e315  mov     ebx, eax
0x18000e317  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e31e  cmp     rcx, rdi
0x18000e321  jz      short loc_18000E367
0x18000e323  test    byte ptr [rcx+1Ch], 4
0x18000e327  jz      short loc_18000E367
0x18000e329  mov     edx, 4Fh ; 'O'
0x18000e32e  mov     dword ptr [rsp+570h+phkResult], eax
0x18000e332  lea     r9, [rbp+470h+Data]
0x18000e339  jmp     short loc_18000E35B
0x18000e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e342  cmp     rcx, rdi
0x18000e345  jz      short loc_18000E367
0x18000e347  test    byte ptr [rcx+1Ch], 4
0x18000e34b  jz      short loc_18000E367
0x18000e34d  mov     edx, 50h ; 'P'
0x18000e352  mov     dword ptr [rsp+570h+phkResult], ebx
0x18000e356  lea     r9, [rsp+570h+SubKey]
0x18000e35b  mov     rcx, [rcx+10h]
0x18000e35f  mov     r8, r12
0x18000e362  call    WPP_SF_SD
0x18000e367  mov     rcx, [rsp+570h+hKey]; hKey
0x18000e36c  call    cs:__imp_RegCloseKey
0x18000e372  jmp     short loc_18000E3B2
0x18000e374  jle     short loc_18000E37F
0x18000e376  movzx   ebx, ax
0x18000e379  or      ebx, 80070000h
0x18000e37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e386  lea     rdi, WPP_GLOBAL_Control
0x18000e38d  cmp     rcx, rdi
0x18000e390  jz      short loc_18000E3D8
0x18000e392  test    byte ptr [rcx+1Ch], 10h
0x18000e396  jz      short loc_18000E3B9
0x18000e398  mov     rcx, [rcx+10h]
0x18000e39c  lea     r9, [rsp+570h+SubKey]
0x18000e3a1  mov     edx, 51h ; 'Q'
0x18000e3a6  mov     dword ptr [rsp+570h+phkResult], ebx
0x18000e3aa  mov     r8, r12
0x18000e3ad  call    WPP_SF_SD
0x18000e3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b9  cmp     rcx, rdi
0x18000e3bc  jz      short loc_18000E3D8
0x18000e3be  test    byte ptr [rcx+1Ch], 10h
0x18000e3c2  jz      short loc_18000E3D8
0x18000e3c4  mov     rcx, [rcx+10h]
0x18000e3c8  mov     edx, 52h ; 'R'
0x18000e3cd  mov     r9d, ebx
0x18000e3d0  mov     r8, r12
0x18000e3d3  call    WPP_SF_D
0x18000e3d8  mov     eax, ebx
0x18000e3da  mov     rcx, [rbp+470h+var_30]
0x18000e3e1  xor     rcx, rsp; StackCookie
0x18000e3e4  call    __security_check_cookie
0x18000e3e9  lea     r11, [rsp+570h+var_20]
0x18000e3f1  mov     rbx, [r11+38h]
0x18000e3f5  mov     rsi, [r11+48h]
0x18000e3f9  mov     rsp, r11
0x18000e3fc  pop     r15
0x18000e3fe  pop     r14
0x18000e400  pop     r12
0x18000e402  pop     rdi
0x18000e403  pop     rbp
0x18000e404  retn
```
