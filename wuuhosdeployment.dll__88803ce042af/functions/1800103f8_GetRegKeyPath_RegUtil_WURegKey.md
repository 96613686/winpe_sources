# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x1800103f8`
- end: `0x180010647`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006600`
- `0x1800103f8`

## callees

- `0x180001e8c`
- `0x180005f64`
- `0x180009c1c`
- `0x18000af44`
- `0x1800103f8`
- `0x180026810`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010616`

## string_xrefs

- `0x180010522`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x1800104c2`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x1800104c9`: `WindowsUpdate`
- `0x1800104a3`: `AdapterCacheKeyID`
- `0x180010597`: `SQMClientLink`

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
      CSusBaseAllocTag<942762101>::operator delete((void *)(v26
                                                          & -(__int64)(_InterlockedCompareExchange64(
                                                                         (volatile signed __int64 *)&RegUtil::paths
                                                                       + v6
                                                                       + 2,
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
0x1800103f8  mov     rax, rsp
0x1800103fb  mov     [rax+10h], rbx
0x1800103ff  mov     [rax+18h], rdi
0x180010403  mov     [rax+20h], r14
0x180010407  push    rbp
0x180010408  lea     rbp, [rax-168h]
0x18001040f  sub     rsp, 260h
0x180010416  mov     rax, cs:__security_cookie
0x18001041d  xor     rax, rsp
0x180010420  mov     [rbp+160h+var_10], rax
0x180010427  movsxd  rax, ecx
0x18001042a  xor     ecx, ecx
0x18001042c  mov     [rsp+260h+pv], rcx
0x180010431  mov     [rsp+260h+var_230], rcx
0x180010436  lea     rdi, [rax+rax*2]
0x18001043a  lea     r14, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x180010441  cmp     [r14+rdi*8+10h], rcx
0x180010446  jnz     loc_18001060C
0x18001044c  mov     edx, [r14+rdi*8+4]
0x180010451  cmp     edx, 6
0x180010454  jg      loc_180010539
0x18001045a  jz      loc_180010532
0x180010460  test    edx, edx
0x180010462  jz      loc_180010522
0x180010468  sub     edx, 1
0x18001046b  jz      loc_18001050C
0x180010471  sub     edx, 1
0x180010474  jz      short loc_1800104C2
0x180010476  sub     edx, 1
0x180010479  jz      short loc_1800104AF
0x18001047b  sub     edx, 1
0x18001047e  jz      short loc_18001049C
0x180010480  cmp     edx, 1
0x180010483  jnz     loc_18001060C
0x180010489  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\SIH"
0x180010490  lea     rcx, aSih; "SIH"
0x180010497  jmp     loc_18001059E
0x18001049c  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\DirectX"
0x1800104a3  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x1800104aa  jmp     loc_18001059E
0x1800104af  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800104b6  lea     rcx, aAppxroot; "AppxRoot"
0x1800104bd  jmp     loc_18001059E
0x1800104c2  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x1800104c9  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x1800104d0  lea     r8, [rsp+260h+pv]; wchar_t *
0x1800104d5  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800104da  test    eax, eax
0x1800104dc  js      loc_180010607
0x1800104e2  mov     rax, [r14+rdi*8+8]
0x1800104e7  mov     [rsp+260h+var_240], rax
0x1800104ec  mov     r9, [rsp+260h+pv]
0x1800104f1  lea     r8, aSS; "%s\\%s"
0x1800104f8  mov     edx, 104h; unsigned __int64
0x1800104fd  lea     rcx, [rsp+260h+Buffer]; Buffer
0x180010502  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180010507  jmp     loc_1800105D4
0x18001050c  xor     ecx, ecx
0x18001050e  mov     rbx, [r14+rdi*8+8]
0x180010513  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180010518  mov     [rsp+260h+var_240], rbx
0x18001051d  mov     r9, rax
0x180010520  jmp     short loc_1800104F1
0x180010522  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010529  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x180010530  jmp     short loc_18001059E
0x180010532  mov     ecx, 1Dh
0x180010537  jmp     short loc_18001050E
0x180010539  sub     edx, 7
0x18001053c  jz      short loc_180010590
0x18001053e  sub     edx, 1
0x180010541  jz      short loc_180010580
0x180010543  sub     edx, 1
0x180010546  jz      short loc_180010570
0x180010548  sub     edx, 1
0x18001054b  jz      short loc_180010569
0x18001054d  cmp     edx, 1
0x180010550  jnz     loc_18001060C
0x180010556  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x18001055d  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x180010564  jmp     loc_1800104D0
0x180010569  mov     ecx, 23h ; '#'
0x18001056e  jmp     short loc_18001050E
0x180010570  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WindowsSelfHost"
0x180010577  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x18001057e  jmp     short loc_18001059E
0x180010580  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\WindowsS"...
0x180010587  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x18001058e  jmp     short loc_18001059E
0x180010590  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SQMClient"
0x180010597  lea     rcx, aSqmclientlink; "SQMClientLink"
0x18001059e  lea     r8, [rsp+260h+pv]; wchar_t *
0x1800105a3  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800105a8  test    eax, eax
0x1800105aa  js      short loc_180010607
0x1800105ac  mov     [rsp+260h+var_238], 100h; unsigned int
0x1800105b4  mov     [rsp+260h+var_240], 0; unsigned __int64 *
0x1800105bd  xor     r9d, r9d; wchar_t **
0x1800105c0  mov     r8, [rsp+260h+pv]; wchar_t *
0x1800105c5  mov     edx, 104h; unsigned __int64
0x1800105ca  lea     rcx, [rsp+260h+Buffer]; pszDest
0x1800105cf  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800105d4  test    eax, eax
0x1800105d6  js      short loc_180010607
0x1800105d8  lea     rdx, [rsp+260h+var_230]
0x1800105dd  lea     rcx, [rsp+260h+Buffer]
0x1800105e2  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1800105e7  test    eax, eax
0x1800105e9  js      short loc_180010607
0x1800105eb  mov     rdx, [rsp+260h+var_230]
0x1800105f0  xor     eax, eax
0x1800105f2  lock cmpxchg [r14+rdi*8+10h], rdx
0x1800105f9  neg     rax
0x1800105fc  sbb     rcx, rcx
0x1800105ff  and     rcx, rdx; lpMem
0x180010602  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180010607  mov     rcx, [rsp+260h+pv]; pv
0x18001060c  mov     rbx, [r14+rdi*8+10h]
0x180010611  test    rcx, rcx
0x180010614  jz      short loc_18001061C
0x180010616  call    cs:__imp_CoTaskMemFree
0x18001061c  mov     rax, rbx
0x18001061f  mov     rcx, [rbp+160h+var_10]
0x180010626  xor     rcx, rsp; StackCookie
0x180010629  call    __security_check_cookie
0x18001062e  lea     r11, [rsp+260h+var_s0]
0x180010636  mov     rbx, [r11+18h]
0x18001063a  mov     rdi, [r11+20h]
0x18001063e  mov     r14, [r11+28h]
0x180010642  mov     rsp, r11
0x180010645  pop     rbp
0x180010646  retn
```
