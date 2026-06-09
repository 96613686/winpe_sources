# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x18000e3ec`
- end: `0x18000e629`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180007d00`
- `0x18000e3ec`

## callees

- `0x180001ca8`
- `0x18000ab98`
- `0x18000b108`
- `0x18000b1ec`
- `0x18000e3ec`
- `0x18000ef30`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5f8`

## string_xrefs

- `0x18000e515`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x18000e4b5`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x18000e4bc`: `WindowsUpdate`
- `0x18000e496`: `AdapterCacheKeyID`
- `0x18000e58a`: `SQMClientLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000e3ec  mov     rax, rsp
0x18000e3ef  mov     [rax+10h], rbx
0x18000e3f3  mov     [rax+18h], rsi
0x18000e3f7  mov     [rax+20h], rdi
0x18000e3fb  push    rbp
0x18000e3fc  lea     rbp, [rax-168h]
0x18000e403  sub     rsp, 260h
0x18000e40a  mov     rax, cs:__security_cookie
0x18000e411  xor     rax, rsp
0x18000e414  mov     [rbp+160h+var_10], rax
0x18000e41b  movsxd  rax, ecx
0x18000e41e  xor     ecx, ecx
0x18000e420  mov     [rsp+260h+pv], rcx
0x18000e425  mov     [rsp+260h+var_230], rcx
0x18000e42a  lea     rdi, [rax+rax*2]
0x18000e42e  lea     rsi, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x18000e435  cmp     [rsi+rdi*8+10h], rcx
0x18000e43a  jnz     loc_18000E5EE
0x18000e440  mov     edx, [rsi+rdi*8+4]
0x18000e444  cmp     edx, 6
0x18000e447  jg      loc_18000E52C
0x18000e44d  jz      loc_18000E525
0x18000e453  test    edx, edx
0x18000e455  jz      loc_18000E515
0x18000e45b  sub     edx, 1
0x18000e45e  jz      loc_18000E4FF
0x18000e464  sub     edx, 1
0x18000e467  jz      short loc_18000E4B5
0x18000e469  sub     edx, 1
0x18000e46c  jz      short loc_18000E4A2
0x18000e46e  sub     edx, 1
0x18000e471  jz      short loc_18000E48F
0x18000e473  cmp     edx, 1
0x18000e476  jnz     loc_18000E5EE
0x18000e47c  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SIH"
0x18000e483  lea     rcx, aSih; "SIH"
0x18000e48a  jmp     loc_18000E591
0x18000e48f  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\DirectX"
0x18000e496  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x18000e49d  jmp     loc_18000E591
0x18000e4a2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e4a9  lea     rcx, aAppxroot; "AppxRoot"
0x18000e4b0  jmp     loc_18000E591
0x18000e4b5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x18000e4bc  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18000e4c3  lea     r8, [rsp+260h+pv]; wchar_t *
0x18000e4c8  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x18000e4cd  test    eax, eax
0x18000e4cf  js      loc_18000E5E9
0x18000e4d5  mov     rax, [rsi+rdi*8+8]
0x18000e4da  mov     [rsp+260h+var_240], rax
0x18000e4df  mov     r9, [rsp+260h+pv]
0x18000e4e4  lea     r8, aSS; "%s\\%s"
0x18000e4eb  mov     edx, 104h; unsigned __int64
0x18000e4f0  lea     rcx, [rsp+260h+Buffer]; Buffer
0x18000e4f5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000e4fa  jmp     loc_18000E5B6
0x18000e4ff  xor     ecx, ecx
0x18000e501  mov     rbx, [rsi+rdi*8+8]
0x18000e506  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18000e50b  mov     [rsp+260h+var_240], rbx
0x18000e510  mov     r9, rax
0x18000e513  jmp     short loc_18000E4E4
0x18000e515  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e51c  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x18000e523  jmp     short loc_18000E591
0x18000e525  mov     ecx, 1Dh
0x18000e52a  jmp     short loc_18000E501
0x18000e52c  sub     edx, 7
0x18000e52f  jz      short loc_18000E583
0x18000e531  sub     edx, 1
0x18000e534  jz      short loc_18000E573
0x18000e536  sub     edx, 1
0x18000e539  jz      short loc_18000E563
0x18000e53b  sub     edx, 1
0x18000e53e  jz      short loc_18000E55C
0x18000e540  cmp     edx, 1
0x18000e543  jnz     loc_18000E5EE
0x18000e549  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x18000e550  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x18000e557  jmp     loc_18000E4C3
0x18000e55c  mov     ecx, 23h ; '#'
0x18000e561  jmp     short loc_18000E501
0x18000e563  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\WindowsSelfHost"
0x18000e56a  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x18000e571  jmp     short loc_18000E591
0x18000e573  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\WindowsS"...
0x18000e57a  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x18000e581  jmp     short loc_18000E591
0x18000e583  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\SQMClient"
0x18000e58a  lea     rcx, aSqmclientlink; "SQMClientLink"
0x18000e591  lea     r8, [rsp+260h+pv]; wchar_t *
0x18000e596  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x18000e59b  test    eax, eax
0x18000e59d  js      short loc_18000E5E9
0x18000e59f  xor     r9d, r9d; wchar_t **
0x18000e5a2  mov     r8, [rsp+260h+pv]; wchar_t *
0x18000e5a7  mov     edx, 104h; unsigned __int64
0x18000e5ac  lea     rcx, [rsp+260h+Buffer]; wchar_t *
0x18000e5b1  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000e5b6  test    eax, eax
0x18000e5b8  js      short loc_18000E5E9
0x18000e5ba  lea     rdx, [rsp+260h+var_230]
0x18000e5bf  lea     rcx, [rsp+260h+Buffer]
0x18000e5c4  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e5c9  test    eax, eax
0x18000e5cb  js      short loc_18000E5E9
0x18000e5cd  mov     rdx, [rsp+260h+var_230]
0x18000e5d2  xor     eax, eax
0x18000e5d4  lock cmpxchg [rsi+rdi*8+10h], rdx
0x18000e5db  neg     rax
0x18000e5de  sbb     rcx, rcx
0x18000e5e1  and     rcx, rdx; lpMem
0x18000e5e4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e5e9  mov     rcx, [rsp+260h+pv]; pv
0x18000e5ee  mov     rbx, [rsi+rdi*8+10h]
0x18000e5f3  test    rcx, rcx
0x18000e5f6  jz      short loc_18000E5FE
0x18000e5f8  call    cs:__imp_CoTaskMemFree
0x18000e5fe  mov     rax, rbx
0x18000e601  mov     rcx, [rbp+160h+var_10]
0x18000e608  xor     rcx, rsp; StackCookie
0x18000e60b  call    __security_check_cookie
0x18000e610  lea     r11, [rsp+260h+var_s0]
0x18000e618  mov     rbx, [r11+18h]
0x18000e61c  mov     rsi, [r11+20h]
0x18000e620  mov     rdi, [r11+28h]
0x18000e624  mov     rsp, r11
0x18000e627  pop     rbp
0x18000e628  retn
```
