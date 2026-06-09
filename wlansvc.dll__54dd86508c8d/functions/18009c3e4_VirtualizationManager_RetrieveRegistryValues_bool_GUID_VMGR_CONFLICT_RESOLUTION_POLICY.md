# VirtualizationManager::RetrieveRegistryValues(bool &,_GUID &,VMGR_CONFLICT_RESOLUTION_POLICY &)

- ea: `0x18009c3e4`
- end: `0x18009c71d`
- name: `?RetrieveRegistryValues@VirtualizationManager@@AEAAXAEA_NAEAU_GUID@@AEAW4VMGR_CONFLICT_RESOLUTION_POLICY@@@Z`
- size: `825`
- prototype: `void(VirtualizationManager *__hidden this, bool *, struct _GUID *, enum VMGR_CONFLICT_RESOLUTION_POLICY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009c1e4`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18009c3e4`
- `0x180106340`
- `0x1801e6fd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c4bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c4bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c6f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c6f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c547`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c5c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c641`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c547`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c5c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009c641`
- `RPCRT4!UuidFromStringW` at `0x18009c67c`
- `RPCRT4!UuidFromStringW` at `0x18009c67c`

## string_xrefs

- `0x18009c463`: `System\CurrentControlSet\Services\WlanSvc\VirtualizationManager`
- `0x18009c614`: `WindowsPushNotificationPlatformClsid`

## pseudocode

```c
void __fastcall VirtualizationManager::RetrieveRegistryValues(
        VirtualizationManager *this,
        bool *a2,
        struct _GUID *a3,
        enum VMGR_CONFLICT_RESOLUTION_POLICY *a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  PVOID *v11; // r10
  __int64 v12; // rdx
  int pvData; // [rsp+40h] [rbp-69h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-65h] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-61h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 StringUuid[8]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v18; // [rsp+70h] [rbp-39h]
  __int128 v19; // [rsp+80h] [rbp-29h]
  _OWORD v20[2]; // [rsp+90h] [rbp-19h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, &WPP_c178980aa4753e2985c8d771618c8184_Traceguids);
  }
  *(_OWORD *)StringUuid = *(_OWORD *)L"00000000-0000-0000-0000-000000000000";
  v19 = *(_OWORD *)L"00-0000-000000000000";
  hkey = 0;
  v18 = *(_OWORD *)L"-0000-0000-0000-000000000000";
  v20[0] = *(_OWORD *)L"000000000000";
  *(_OWORD *)((char *)v20 + 10) = *(_OWORD *)L"0000000";
  pdwType = 0;
  pcbData = 0;
  pvData = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WlanSvc\\VirtualizationManager",
         0,
         0x20119u,
         &hkey);
  if ( v8 )
  {
    *((_BYTE *)this + 72) = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 66, &WPP_c178980aa4753e2985c8d771618c8184_Traceguids, v8);
    goto LABEL_33;
  }
  pvData = 0;
  pcbData = 4;
  if ( !RegGetValueW(hkey, &word_180243548, L"Disable", 0x18u, &pdwType, &pvData, &pcbData) && pvData )
  {
    *((_BYTE *)this + 72) = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    v12 = 67;
    goto LABEL_32;
  }
  pvData = 0;
  pcbData = 4;
  if ( !RegGetValueW(hkey, &word_180243548, L"DisableNotifications", 0x18u, &pdwType, &pvData, &pcbData) )
  {
    if ( pvData )
    {
      *a2 = 0;
      *(_DWORD *)a4 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 68, &WPP_c178980aa4753e2985c8d771618c8184_Traceguids);
      }
    }
  }
  pcbData = 74;
  if ( RegGetValueW(hkey, &word_180243548, L"WindowsPushNotificationPlatformClsid", 2u, &pdwType, StringUuid, &pcbData) )
  {
    *a2 = 0;
    *(_DWORD *)a4 = 1;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    v12 = 69;
    goto LABEL_32;
  }
  if ( !UuidFromStringW(StringUuid, a3) )
  {
LABEL_33:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  *a2 = 0;
  *(_DWORD *)a4 = 1;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_38;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    v12 = 70;
LABEL_32:
    WPP_SF_(v11[12], v12, &WPP_c178980aa4753e2985c8d771618c8184_Traceguids);
    goto LABEL_33;
  }
LABEL_34:
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) >= 3u && (*((_BYTE *)v11 + 108) & 1) != 0 )
    WPP_SF_llD(v11[12], v9, v10, *((unsigned __int8 *)this + 72), *a2, *(_DWORD *)a4);
LABEL_38:
  if ( hkey )
    RegCloseKey(hkey);
}

```

## disassembly

```asm
0x18009c3e4  push    rbp
0x18009c3e6  push    rbx
0x18009c3e7  push    rsi
0x18009c3e8  push    rdi
0x18009c3e9  push    r12
0x18009c3eb  push    r13
0x18009c3ed  push    r14
0x18009c3ef  push    r15
0x18009c3f1  lea     rbp, [rsp-1Fh]
0x18009c3f6  sub     rsp, 0C8h
0x18009c3fd  mov     rax, cs:__security_cookie
0x18009c404  xor     rax, rsp
0x18009c407  mov     [rbp+57h+var_50], rax
0x18009c40b  mov     rdi, r9
0x18009c40e  mov     r14, r8
0x18009c411  mov     rbx, rdx
0x18009c414  mov     rsi, rcx
0x18009c417  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c41e  lea     r13, WPP_GLOBAL_Control
0x18009c425  mov     r12d, 1
0x18009c42b  cmp     rcx, r13
0x18009c42e  jz      short loc_18009C451
0x18009c430  cmp     byte ptr [rcx+69h], 3
0x18009c434  jb      short loc_18009C451
0x18009c436  test    [rcx+6Ch], r12b
0x18009c43a  jz      short loc_18009C451
0x18009c43c  mov     rcx, [rcx+60h]
0x18009c440  lea     edx, [r12+40h]
0x18009c445  lea     r8, WPP_c178980aa4753e2985c8d771618c8184_Traceguids
0x18009c44c  call    WPP_SF_
0x18009c451  movaps  xmm0, xmmword ptr cs:a00000000000000; "00000000-0000-0000-0000-000000000000"
0x18009c458  lea     rax, [rbp+57h+hkey]
0x18009c45c  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "-0000-0000-0000-000000000000"
0x18009c463  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Wl"...
0x18009c46a  xor     r15d, r15d
0x18009c46d  movaps  xmmword ptr [rbp+57h+StringUuid], xmm0
0x18009c471  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "00-0000-000000000000"
0x18009c478  mov     r9d, 20119h; samDesired
0x18009c47e  movaps  [rbp+57h+var_80], xmm0
0x18009c482  xor     r8d, r8d; ulOptions
0x18009c485  movups  xmm0, xmmword ptr cs:a00000000000000+3Ah; "0000000"
0x18009c48c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c493  mov     [rbp+57h+hkey], r15
0x18009c497  movaps  [rbp+57h+var_90], xmm1
0x18009c49b  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "000000000000"
0x18009c4a2  movaps  xmmword ptr [rbp+57h+var_70], xmm1
0x18009c4a6  movups  xmmword ptr [rbp+57h+var_70+0Ah], xmm0
0x18009c4aa  mov     [rbp+57h+pdwType], r15d
0x18009c4ae  mov     [rbp+57h+var_BC], r15d
0x18009c4b2  mov     [rbp+57h+var_C0], r15d
0x18009c4b6  mov     [rsp+100h+phkResult], rax; phkResult
0x18009c4bb  call    cs:__imp_RegOpenKeyExW
0x18009c4c1  test    eax, eax
0x18009c4c3  jz      short loc_18009C509
0x18009c4c5  mov     [rsi+48h], r15b
0x18009c4c9  mov     r10, cs:WPP_GLOBAL_Control
0x18009c4d0  cmp     r10, r13
0x18009c4d3  jz      loc_18009C6EE
0x18009c4d9  cmp     [r10+69h], r12b
0x18009c4dd  jb      loc_18009C6C1
0x18009c4e3  test    [r10+6Ch], r12b
0x18009c4e7  jz      loc_18009C6C1
0x18009c4ed  mov     rcx, [r10+60h]
0x18009c4f1  lea     edx, [r15+42h]
0x18009c4f5  mov     r9d, eax
0x18009c4f8  lea     r8, WPP_c178980aa4753e2985c8d771618c8184_Traceguids
0x18009c4ff  call    WPP_SF_d
0x18009c504  jmp     loc_18009C6BA
0x18009c509  mov     rcx, [rbp+57h+hkey]; hkey
0x18009c50d  lea     rax, [rbp+57h+var_BC]
0x18009c511  mov     [rsp+100h+pcbData], rax; pcbData
0x18009c516  lea     r8, aDisable_0; "Disable"
0x18009c51d  lea     rax, [rbp+57h+var_C0]
0x18009c521  mov     [rbp+57h+var_C0], r15d
0x18009c525  mov     [rsp+100h+pvData], rax; pvData
0x18009c52a  lea     rdx, word_180243548; lpSubKey
0x18009c531  lea     rax, [rbp+57h+pdwType]
0x18009c535  mov     [rbp+57h+var_BC], 4
0x18009c53c  mov     r9d, 18h; dwFlags
0x18009c542  mov     [rsp+100h+phkResult], rax; pdwType
0x18009c547  call    cs:__imp_RegGetValueW
0x18009c54d  test    eax, eax
0x18009c54f  jnz     short loc_18009C588
0x18009c551  cmp     [rbp+57h+var_C0], r15d
0x18009c555  jbe     short loc_18009C588
0x18009c557  mov     [rsi+48h], r15b
0x18009c55b  mov     r10, cs:WPP_GLOBAL_Control
0x18009c562  cmp     r10, r13
0x18009c565  jz      loc_18009C6EE
0x18009c56b  cmp     byte ptr [r10+69h], 2
0x18009c570  jb      loc_18009C6C1
0x18009c576  test    [r10+6Ch], r12b
0x18009c57a  jz      loc_18009C6C1
0x18009c580  lea     edx, [rax+43h]
0x18009c583  jmp     loc_18009C6AA
0x18009c588  mov     rcx, [rbp+57h+hkey]; hkey
0x18009c58c  lea     rax, [rbp+57h+var_BC]
0x18009c590  mov     [rsp+100h+pcbData], rax; pcbData
0x18009c595  lea     r8, aDisablenotific; "DisableNotifications"
0x18009c59c  lea     rax, [rbp+57h+var_C0]
0x18009c5a0  mov     [rbp+57h+var_C0], r15d
0x18009c5a4  mov     [rsp+100h+pvData], rax; pvData
0x18009c5a9  lea     rdx, word_180243548; lpSubKey
0x18009c5b0  lea     rax, [rbp+57h+pdwType]
0x18009c5b4  mov     [rbp+57h+var_BC], 4
0x18009c5bb  mov     r9d, 18h; dwFlags
0x18009c5c1  mov     [rsp+100h+phkResult], rax; pdwType
0x18009c5c6  call    cs:__imp_RegGetValueW
0x18009c5cc  test    eax, eax
0x18009c5ce  jnz     short loc_18009C607
0x18009c5d0  cmp     [rbp+57h+var_C0], r15d
0x18009c5d4  jbe     short loc_18009C607
0x18009c5d6  mov     [rbx], r15b
0x18009c5d9  mov     [rdi], r12d
0x18009c5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c5e3  cmp     rcx, r13
0x18009c5e6  jz      short loc_18009C607
0x18009c5e8  cmp     byte ptr [rcx+69h], 2
0x18009c5ec  jb      short loc_18009C607
0x18009c5ee  test    [rcx+6Ch], r12b
0x18009c5f2  jz      short loc_18009C607
0x18009c5f4  mov     rcx, [rcx+60h]
0x18009c5f8  lea     edx, [rax+44h]
0x18009c5fb  lea     r8, WPP_c178980aa4753e2985c8d771618c8184_Traceguids
0x18009c602  call    WPP_SF_
0x18009c607  mov     rcx, [rbp+57h+hkey]; hkey
0x18009c60b  lea     rax, [rbp+57h+var_BC]
0x18009c60f  mov     [rsp+100h+pcbData], rax; pcbData
0x18009c614  lea     r8, aWindowspushnot; "WindowsPushNotificationPlatformClsid"
0x18009c61b  lea     rax, [rbp+57h+StringUuid]
0x18009c61f  mov     [rbp+57h+var_BC], 4Ah ; 'J'
0x18009c626  mov     [rsp+100h+pvData], rax; pvData
0x18009c62b  lea     rdx, word_180243548; lpSubKey
0x18009c632  lea     rax, [rbp+57h+pdwType]
0x18009c636  mov     r9d, 2; dwFlags
0x18009c63c  mov     [rsp+100h+phkResult], rax; pdwType
0x18009c641  call    cs:__imp_RegGetValueW
0x18009c647  test    eax, eax
0x18009c649  jz      short loc_18009C675
0x18009c64b  mov     [rbx], r15b
0x18009c64e  mov     [rdi], r12d
0x18009c651  mov     r10, cs:WPP_GLOBAL_Control
0x18009c658  cmp     r10, r13
0x18009c65b  jz      loc_18009C6EE
0x18009c661  cmp     byte ptr [r10+69h], 2
0x18009c666  jb      short loc_18009C6C1
0x18009c668  test    [r10+6Ch], r12b
0x18009c66c  jz      short loc_18009C6C1
0x18009c66e  mov     edx, 45h ; 'E'
0x18009c673  jmp     short loc_18009C6AA
0x18009c675  mov     rdx, r14; Uuid
0x18009c678  lea     rcx, [rbp+57h+StringUuid]; StringUuid
0x18009c67c  call    cs:__imp_UuidFromStringW
0x18009c682  test    eax, eax
0x18009c684  jz      short loc_18009C6BA
0x18009c686  mov     [rbx], r15b
0x18009c689  mov     [rdi], r12d
0x18009c68c  mov     r10, cs:WPP_GLOBAL_Control
0x18009c693  cmp     r10, r13
0x18009c696  jz      short loc_18009C6EE
0x18009c698  cmp     byte ptr [r10+69h], 2
0x18009c69d  jb      short loc_18009C6C1
0x18009c69f  test    [r10+6Ch], r12b
0x18009c6a3  jz      short loc_18009C6C1
0x18009c6a5  mov     edx, 46h ; 'F'
0x18009c6aa  mov     rcx, [r10+60h]
0x18009c6ae  lea     r8, WPP_c178980aa4753e2985c8d771618c8184_Traceguids
0x18009c6b5  call    WPP_SF_
0x18009c6ba  mov     r10, cs:WPP_GLOBAL_Control
0x18009c6c1  cmp     r10, r13
0x18009c6c4  jz      short loc_18009C6EE
0x18009c6c6  cmp     byte ptr [r10+69h], 3
0x18009c6cb  jb      short loc_18009C6EE
0x18009c6cd  test    [r10+6Ch], r12b
0x18009c6d1  jz      short loc_18009C6EE
0x18009c6d3  movzx   ecx, byte ptr [rbx]
0x18009c6d6  mov     eax, [rdi]
0x18009c6d8  movzx   r9d, byte ptr [rsi+48h]
0x18009c6dd  mov     dword ptr [rsp+100h+pvData], eax
0x18009c6e1  mov     dword ptr [rsp+100h+phkResult], ecx
0x18009c6e5  mov     rcx, [r10+60h]
0x18009c6e9  call    WPP_SF_llD
0x18009c6ee  mov     rcx, [rbp+57h+hkey]; hKey
0x18009c6f2  test    rcx, rcx
0x18009c6f5  jz      short loc_18009C6FD
0x18009c6f7  call    cs:__imp_RegCloseKey
0x18009c6fd  mov     rcx, [rbp+57h+var_50]
0x18009c701  xor     rcx, rsp; StackCookie
0x18009c704  call    __security_check_cookie
0x18009c709  add     rsp, 0C8h
0x18009c710  pop     r15
0x18009c712  pop     r14
0x18009c714  pop     r13
0x18009c716  pop     r12
0x18009c718  pop     rdi
0x18009c719  pop     rsi
0x18009c71a  pop     rbx
0x18009c71b  pop     rbp
0x18009c71c  retn
```
