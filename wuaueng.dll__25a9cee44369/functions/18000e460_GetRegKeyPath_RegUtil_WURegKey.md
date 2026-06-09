# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x18000e460`
- end: `0x18000e69d`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(int, __int64, __int64, wchar_t **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800064e0`
- `0x18000e460`

## callees

- `0x180001ca8`
- `0x18000ab44`
- `0x18000b0b4`
- `0x18000b198`
- `0x18000e460`
- `0x18000eee0`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e66c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e66c`

## string_xrefs

- `0x18000e589`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x18000e529`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x18000e530`: `WindowsUpdate`
- `0x18000e50a`: `AdapterCacheKeyID`
- `0x18000e5fe`: `SQMClientLink`

## pseudocode

```c
__int64 __fastcall GetRegKeyPath(int a1, __int64 a2, __int64 a3, wchar_t **a4)
{
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v6; // rdi
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  const wchar_t *v12; // rdx
  wchar_t *v13; // rcx
  const wchar_t *v14; // rdx
  wchar_t *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 RegKeyPath; // r9
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  __int64 v24; // rbx
  unsigned __int64 *v26; // [rsp+28h] [rbp-E0h]
  unsigned int v27; // [rsp+30h] [rbp-D8h]
  signed __int64 v28; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+48h] [rbp-C0h] BYREF

  v4 = a1;
  v5 = 0;
  pv = 0;
  v28 = 0;
  v6 = 3 * v4;
  if ( !*(&RegUtil::paths + 3 * v4 + 2) )
  {
    v7 = *((_DWORD *)&RegUtil::paths + 6 * v4 + 1);
    if ( v7 > 6 )
    {
      v20 = v7 - 7;
      if ( !v20 )
      {
        v12 = L"SOFTWARE\\Microsoft\\SQMClient";
        v13 = L"SQMClientLink";
        goto LABEL_31;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v12 = L"Software\\Policies\\Microsoft\\WindowsStore\\Apps";
        v13 = L"EnterpriseModernAppReleaseManagement";
        goto LABEL_31;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v12 = L"Software\\Microsoft\\WindowsSelfHost";
        v13 = L"WindowsSelfhost";
        goto LABEL_31;
      }
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 != 1 )
          goto LABEL_37;
        v14 = L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement";
        v15 = L"FeatureManagement";
        goto LABEL_14;
      }
      v17 = 35;
    }
    else if ( v7 == 6 )
    {
      v17 = 29;
    }
    else
    {
      if ( !v7 )
      {
        v12 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate";
        v13 = L"WUCurrentVersion";
        goto LABEL_31;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 != 1 )
                goto LABEL_37;
              v12 = L"SOFTWARE\\Microsoft\\SIH";
              v13 = L"SIH";
            }
            else
            {
              v12 = L"Software\\Microsoft\\DirectX";
              v13 = L"AdapterCacheKeyID";
            }
          }
          else
          {
            v12 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx";
            v13 = L"AppxRoot";
          }
LABEL_31:
          if ( (int)WUSystemInterfaceHelper::GetPersistedRegistryLocation(
                      (WUSystemInterfaceHelper *)v13,
                      v12,
                      (const wchar_t *)&pv,
                      a4) >= 0 )
          {
            v16 = StringCchCopyExW(Buffer, 0x104u, (const wchar_t *)pv, 0, v26, v27);
            goto LABEL_33;
          }
LABEL_36:
          v5 = pv;
          goto LABEL_37;
        }
        v14 = L"SOFTWARE\\Microsoft\\WindowsUpdate";
        v15 = L"WindowsUpdate";
LABEL_14:
        if ( (int)WUSystemInterfaceHelper::GetPersistedRegistryLocation(
                    (WUSystemInterfaceHelper *)v15,
                    v14,
                    (const wchar_t *)&pv,
                    a4) >= 0 )
        {
          v16 = StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", pv, *(&RegUtil::paths + v6 + 1));
          goto LABEL_33;
        }
        goto LABEL_36;
      }
      v17 = 0;
    }
    v18 = (__int64)*(&RegUtil::paths + 3 * v4 + 1);
    RegKeyPath = GetRegKeyPath(v17);
    v16 = StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", RegKeyPath, v18);
LABEL_33:
    if ( v16 >= 0 && (int)DuplicateString<wchar_t *,wchar_t *>(Buffer, &v28) >= 0 )
      SusFree((void *)(v28
                     & -(__int64)(_InterlockedCompareExchange64(
                                    (volatile signed __int64 *)&RegUtil::paths + v6 + 2,
                                    v28,
                                    0) != 0)));
    goto LABEL_36;
  }
LABEL_37:
  v24 = (__int64)*(&RegUtil::paths + v6 + 2);
  if ( v5 )
    CoTaskMemFree(v5);
  return v24;
}

```

## disassembly

```asm
0x18000e460  mov     rax, rsp
0x18000e463  mov     [rax+10h], rbx
0x18000e467  mov     [rax+18h], rsi
0x18000e46b  mov     [rax+20h], rdi
0x18000e46f  push    rbp
0x18000e470  lea     rbp, [rax-168h]
0x18000e477  sub     rsp, 260h
0x18000e47e  mov     rax, cs:__security_cookie
0x18000e485  xor     rax, rsp
0x18000e488  mov     [rbp+160h+var_10], rax
0x18000e48f  movsxd  rax, ecx
0x18000e492  xor     ecx, ecx
0x18000e494  mov     [rsp+260h+pv], rcx
0x18000e499  mov     [rsp+260h+var_230], rcx
0x18000e49e  lea     rdi, [rax+rax*2]
0x18000e4a2  lea     rsi, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x18000e4a9  cmp     [rsi+rdi*8+10h], rcx
0x18000e4ae  jnz     loc_18000E662
0x18000e4b4  mov     edx, [rsi+rdi*8+4]
0x18000e4b8  cmp     edx, 6
0x18000e4bb  jg      loc_18000E5A0
0x18000e4c1  jz      loc_18000E599
0x18000e4c7  test    edx, edx
0x18000e4c9  jz      loc_18000E589
0x18000e4cf  sub     edx, 1
0x18000e4d2  jz      loc_18000E573
0x18000e4d8  sub     edx, 1
0x18000e4db  jz      short loc_18000E529
0x18000e4dd  sub     edx, 1
0x18000e4e0  jz      short loc_18000E516
0x18000e4e2  sub     edx, 1
0x18000e4e5  jz      short loc_18000E503
0x18000e4e7  cmp     edx, 1
0x18000e4ea  jnz     loc_18000E662
0x18000e4f0  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SIH"
0x18000e4f7  lea     rcx, aSih; "SIH"
0x18000e4fe  jmp     loc_18000E605
0x18000e503  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\DirectX"
0x18000e50a  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x18000e511  jmp     loc_18000E605
0x18000e516  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e51d  lea     rcx, aAppxroot; "AppxRoot"
0x18000e524  jmp     loc_18000E605
0x18000e529  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x18000e530  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18000e537  lea     r8, [rsp+260h+pv]; wchar_t *
0x18000e53c  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x18000e541  test    eax, eax
0x18000e543  js      loc_18000E65D
0x18000e549  mov     rax, [rsi+rdi*8+8]
0x18000e54e  mov     [rsp+260h+var_240], rax
0x18000e553  mov     r9, [rsp+260h+pv]
0x18000e558  lea     r8, aSS; "%s\\%s"
0x18000e55f  mov     edx, 104h; unsigned __int64
0x18000e564  lea     rcx, [rsp+260h+Buffer]; Buffer
0x18000e569  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000e56e  jmp     loc_18000E62A
0x18000e573  xor     ecx, ecx
0x18000e575  mov     rbx, [rsi+rdi*8+8]
0x18000e57a  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18000e57f  mov     [rsp+260h+var_240], rbx
0x18000e584  mov     r9, rax
0x18000e587  jmp     short loc_18000E558
0x18000e589  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e590  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x18000e597  jmp     short loc_18000E605
0x18000e599  mov     ecx, 1Dh
0x18000e59e  jmp     short loc_18000E575
0x18000e5a0  sub     edx, 7
0x18000e5a3  jz      short loc_18000E5F7
0x18000e5a5  sub     edx, 1
0x18000e5a8  jz      short loc_18000E5E7
0x18000e5aa  sub     edx, 1
0x18000e5ad  jz      short loc_18000E5D7
0x18000e5af  sub     edx, 1
0x18000e5b2  jz      short loc_18000E5D0
0x18000e5b4  cmp     edx, 1
0x18000e5b7  jnz     loc_18000E662
0x18000e5bd  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x18000e5c4  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x18000e5cb  jmp     loc_18000E537
0x18000e5d0  mov     ecx, 23h ; '#'
0x18000e5d5  jmp     short loc_18000E575
0x18000e5d7  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\WindowsSelfHost"
0x18000e5de  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x18000e5e5  jmp     short loc_18000E605
0x18000e5e7  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\WindowsS"...
0x18000e5ee  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x18000e5f5  jmp     short loc_18000E605
0x18000e5f7  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\SQMClient"
0x18000e5fe  lea     rcx, aSqmclientlink; "SQMClientLink"
0x18000e605  lea     r8, [rsp+260h+pv]; wchar_t *
0x18000e60a  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x18000e60f  test    eax, eax
0x18000e611  js      short loc_18000E65D
0x18000e613  xor     r9d, r9d; wchar_t **
0x18000e616  mov     r8, [rsp+260h+pv]; wchar_t *
0x18000e61b  mov     edx, 104h; unsigned __int64
0x18000e620  lea     rcx, [rsp+260h+Buffer]; wchar_t *
0x18000e625  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000e62a  test    eax, eax
0x18000e62c  js      short loc_18000E65D
0x18000e62e  lea     rdx, [rsp+260h+var_230]
0x18000e633  lea     rcx, [rsp+260h+Buffer]
0x18000e638  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e63d  test    eax, eax
0x18000e63f  js      short loc_18000E65D
0x18000e641  mov     rdx, [rsp+260h+var_230]
0x18000e646  xor     eax, eax
0x18000e648  lock cmpxchg [rsi+rdi*8+10h], rdx
0x18000e64f  neg     rax
0x18000e652  sbb     rcx, rcx
0x18000e655  and     rcx, rdx; lpMem
0x18000e658  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e65d  mov     rcx, [rsp+260h+pv]; pv
0x18000e662  mov     rbx, [rsi+rdi*8+10h]
0x18000e667  test    rcx, rcx
0x18000e66a  jz      short loc_18000E672
0x18000e66c  call    cs:__imp_CoTaskMemFree
0x18000e672  mov     rax, rbx
0x18000e675  mov     rcx, [rbp+160h+var_10]
0x18000e67c  xor     rcx, rsp; StackCookie
0x18000e67f  call    __security_check_cookie
0x18000e684  lea     r11, [rsp+260h+var_s0]
0x18000e68c  mov     rbx, [r11+18h]
0x18000e690  mov     rsi, [r11+20h]
0x18000e694  mov     rdi, [r11+28h]
0x18000e698  mov     rsp, r11
0x18000e69b  pop     rbp
0x18000e69c  retn
```
