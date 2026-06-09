# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x1400109ec`
- end: `0x140010c3b`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400080bc`
- `0x1400109ec`

## callees

- `0x140002d48`
- `0x14000cae4`
- `0x14000cff8`
- `0x14000d4cc`
- `0x1400109ec`
- `0x140010e78`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010c0a`

## string_xrefs

- `0x140010b16`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x140010ab6`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x140010abd`: `WindowsUpdate`
- `0x140010a97`: `AdapterCacheKeyID`
- `0x140010b8b`: `SQMClientLink`

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
  signed __int64 v26; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+48h] [rbp-C0h] BYREF

  v4 = a1;
  v5 = 0;
  pv = 0;
  v26 = 0;
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
            v16 = StringCchCopyExW(Buffer, 0x104u, (const wchar_t *)pv, 0, 0, 0x100u);
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
    if ( v16 >= 0 && (int)DuplicateString<wchar_t *,wchar_t *>(Buffer, &v26) >= 0 )
      SusFree((void *)(v26
                     & -(__int64)(_InterlockedCompareExchange64(
                                    (volatile signed __int64 *)&RegUtil::paths + v6 + 2,
                                    v26,
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
0x1400109ec  mov     rax, rsp
0x1400109ef  mov     [rax+10h], rbx
0x1400109f3  mov     [rax+18h], rdi
0x1400109f7  mov     [rax+20h], r14
0x1400109fb  push    rbp
0x1400109fc  lea     rbp, [rax-168h]
0x140010a03  sub     rsp, 260h
0x140010a0a  mov     rax, cs:__security_cookie
0x140010a11  xor     rax, rsp
0x140010a14  mov     [rbp+160h+var_10], rax
0x140010a1b  movsxd  rax, ecx
0x140010a1e  xor     ecx, ecx
0x140010a20  mov     [rsp+260h+pv], rcx
0x140010a25  mov     [rsp+260h+var_230], rcx
0x140010a2a  lea     rdi, [rax+rax*2]
0x140010a2e  lea     r14, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x140010a35  cmp     [r14+rdi*8+10h], rcx
0x140010a3a  jnz     loc_140010C00
0x140010a40  mov     edx, [r14+rdi*8+4]
0x140010a45  cmp     edx, 6
0x140010a48  jg      loc_140010B2D
0x140010a4e  jz      loc_140010B26
0x140010a54  test    edx, edx
0x140010a56  jz      loc_140010B16
0x140010a5c  sub     edx, 1
0x140010a5f  jz      loc_140010B00
0x140010a65  sub     edx, 1
0x140010a68  jz      short loc_140010AB6
0x140010a6a  sub     edx, 1
0x140010a6d  jz      short loc_140010AA3
0x140010a6f  sub     edx, 1
0x140010a72  jz      short loc_140010A90
0x140010a74  cmp     edx, 1
0x140010a77  jnz     loc_140010C00
0x140010a7d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SIH"
0x140010a84  lea     rcx, aSih; "SIH"
0x140010a8b  jmp     loc_140010B92
0x140010a90  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\DirectX"
0x140010a97  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x140010a9e  jmp     loc_140010B92
0x140010aa3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140010aaa  lea     rcx, aAppxroot; "AppxRoot"
0x140010ab1  jmp     loc_140010B92
0x140010ab6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x140010abd  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x140010ac4  lea     r8, [rsp+260h+pv]; wchar_t *
0x140010ac9  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x140010ace  test    eax, eax
0x140010ad0  js      loc_140010BFB
0x140010ad6  mov     rax, [r14+rdi*8+8]
0x140010adb  mov     [rsp+260h+var_240], rax
0x140010ae0  mov     r9, [rsp+260h+pv]
0x140010ae5  lea     r8, aSS; "%s\\%s"
0x140010aec  mov     edx, 104h; unsigned __int64
0x140010af1  lea     rcx, [rsp+260h+Buffer]; Buffer
0x140010af6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140010afb  jmp     loc_140010BC8
0x140010b00  xor     ecx, ecx
0x140010b02  mov     rbx, [r14+rdi*8+8]
0x140010b07  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140010b0c  mov     [rsp+260h+var_240], rbx
0x140010b11  mov     r9, rax
0x140010b14  jmp     short loc_140010AE5
0x140010b16  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140010b1d  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x140010b24  jmp     short loc_140010B92
0x140010b26  mov     ecx, 1Dh
0x140010b2b  jmp     short loc_140010B02
0x140010b2d  sub     edx, 7
0x140010b30  jz      short loc_140010B84
0x140010b32  sub     edx, 1
0x140010b35  jz      short loc_140010B74
0x140010b37  sub     edx, 1
0x140010b3a  jz      short loc_140010B64
0x140010b3c  sub     edx, 1
0x140010b3f  jz      short loc_140010B5D
0x140010b41  cmp     edx, 1
0x140010b44  jnz     loc_140010C00
0x140010b4a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x140010b51  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x140010b58  jmp     loc_140010AC4
0x140010b5d  mov     ecx, 23h ; '#'
0x140010b62  jmp     short loc_140010B02
0x140010b64  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\WindowsSelfHost"
0x140010b6b  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x140010b72  jmp     short loc_140010B92
0x140010b74  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\WindowsS"...
0x140010b7b  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x140010b82  jmp     short loc_140010B92
0x140010b84  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\SQMClient"
0x140010b8b  lea     rcx, aSqmclientlink; "SQMClientLink"
0x140010b92  lea     r8, [rsp+260h+pv]; wchar_t *
0x140010b97  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x140010b9c  test    eax, eax
0x140010b9e  js      short loc_140010BFB
0x140010ba0  mov     [rsp+260h+var_238], 100h; unsigned int
0x140010ba8  mov     [rsp+260h+var_240], 0; unsigned __int64 *
0x140010bb1  xor     r9d, r9d; wchar_t **
0x140010bb4  mov     r8, [rsp+260h+pv]; wchar_t *
0x140010bb9  mov     edx, 104h; unsigned __int64
0x140010bbe  lea     rcx, [rsp+260h+Buffer]; pszDest
0x140010bc3  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140010bc8  test    eax, eax
0x140010bca  js      short loc_140010BFB
0x140010bcc  lea     rdx, [rsp+260h+var_230]
0x140010bd1  lea     rcx, [rsp+260h+Buffer]
0x140010bd6  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140010bdb  test    eax, eax
0x140010bdd  js      short loc_140010BFB
0x140010bdf  mov     rdx, [rsp+260h+var_230]
0x140010be4  xor     eax, eax
0x140010be6  lock cmpxchg [r14+rdi*8+10h], rdx
0x140010bed  neg     rax
0x140010bf0  sbb     rcx, rcx
0x140010bf3  and     rcx, rdx; lpMem
0x140010bf6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140010bfb  mov     rcx, [rsp+260h+pv]; pv
0x140010c00  mov     rbx, [r14+rdi*8+10h]
0x140010c05  test    rcx, rcx
0x140010c08  jz      short loc_140010C10
0x140010c0a  call    cs:__imp_CoTaskMemFree
0x140010c10  mov     rax, rbx
0x140010c13  mov     rcx, [rbp+160h+var_10]
0x140010c1a  xor     rcx, rsp; StackCookie
0x140010c1d  call    __security_check_cookie
0x140010c22  lea     r11, [rsp+260h+var_s0]
0x140010c2a  mov     rbx, [r11+18h]
0x140010c2e  mov     rdi, [r11+20h]
0x140010c32  mov     r14, [r11+28h]
0x140010c36  mov     rsp, r11
0x140010c39  pop     rbp
0x140010c3a  retn
```
