# HrUnregisterCOMServer(ushort const *)

- ea: `0x18000f484`
- end: `0x18000f7bc`
- name: `?HrUnregisterCOMServer@@YAJPEBG@Z`
- size: `824`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800099b4`
- `0x18000daac`
- `0x18000ee04`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ebc0`
- `0x18000f484`
- `0x1800107e4`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f53c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f53c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f57b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f5a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f57b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f5a6`

## string_xrefs

- `0x18000f4b9`: `CLSID`

## pseudocode

```c
__int64 __fastcall HrUnregisterCOMServer(const unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // r8
  PVOID *v6; // rcx
  int v7; // eax
  int v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD lpcbData; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR SubKey[48]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v14[2]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE Data[2]; // [rsp+4B0h] [rbp+3B0h] BYREF

  hKey = 0;
  lpcbData = 1026;
  cbData = 1026;
  *(_WORD *)Data = 0;
  *(_WORD *)v14 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x30u, L"CLSID");
  StringCchCatW(SubKey, 0x30u, &qword_180017630);
  StringCchCatW(SubKey, 0x30u, a1);
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
  v3 = v2;
  if ( !v2 )
  {
    RegQueryValueExW(hKey, L"ProgID", 0, 0, Data, &cbData);
    RegQueryValueExW(hKey, L"VersionIndependentProgID", 0, 0, v14, &lpcbData);
    RegCloseKey(hKey);
    v4 = HrRegDeleteSubKeyTree(HKEY_CLASSES_ROOT, SubKey);
    v3 = v4;
    if ( v4 < 0 && (_WORD)v4 != 2 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_8:
        if ( !*(_WORD *)v14 )
          goto LABEL_15;
        v7 = HrRegDeleteSubKeyTree(HKEY_CLASSES_ROOT, (unsigned __int16 *)v14);
        v3 = v7;
        if ( v7 < 0 && (_WORD)v7 != 2 )
        {
          v6 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
LABEL_15:
            if ( *(_WORD *)Data )
            {
              v8 = HrRegDeleteSubKeyTree(HKEY_CLASSES_ROOT, (unsigned __int16 *)Data);
              v3 = v8;
              if ( v8 < 0 && (_WORD)v8 != 2 )
              {
                v6 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  return v3;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                  goto LABEL_22;
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  57,
                  (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
                  (unsigned int)Data,
                  v8);
              }
              v6 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_22:
            if ( v6 == &WPP_GLOBAL_Control )
              return v3;
            if ( (*((_BYTE *)v6 + 28) & 8) == 0 )
              goto LABEL_36;
            WPP_SF_S(v6[2], 58, v5, a1);
            goto LABEL_35;
          }
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)v14,
            v7);
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_15;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)SubKey,
        v4);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  if ( v2 == 2 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)SubKey,
        2);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 1;
    goto LABEL_36;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_36:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_D(v6[2], 61, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v3);
      return v3;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v3);
LABEL_35:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  return v3;
}

```

## disassembly

```asm
0x18000f484  mov     [rsp-8+arg_8], rbx
0x18000f489  mov     [rsp-8+arg_10], rsi
0x18000f48e  push    rbp
0x18000f48f  push    rdi
0x18000f490  push    r12
0x18000f492  push    r14
0x18000f494  push    r15
0x18000f496  lea     rbp, [rsp-7D0h]
0x18000f49e  sub     rsp, 8D0h
0x18000f4a5  mov     rax, cs:__security_cookie
0x18000f4ac  xor     rax, rsp
0x18000f4af  mov     [rbp+7F0h+var_30], rax
0x18000f4b6  xor     r14d, r14d
0x18000f4b9  lea     r8, aClsid_0; "CLSID"
0x18000f4c0  mov     eax, 402h
0x18000f4c5  mov     [rsp+8F0h+hKey], r14
0x18000f4ca  mov     rsi, rcx
0x18000f4cd  mov     [rsp+8F0h+var_8B4], eax
0x18000f4d1  lea     rcx, [rsp+8F0h+SubKey]; unsigned __int16 *
0x18000f4d6  mov     [rsp+8F0h+cbData], eax
0x18000f4da  lea     ebx, [r14+30h]
0x18000f4de  mov     word ptr [rbp+7F0h+Data], r14w
0x18000f4e6  mov     edx, ebx; unsigned __int64
0x18000f4e8  mov     word ptr [rbp+7F0h+var_850], r14w
0x18000f4ed  mov     [rsp+8F0h+SubKey], r14w
0x18000f4f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f4f8  lea     r8, qword_180017630; unsigned __int16 *
0x18000f4ff  mov     edx, ebx; unsigned __int64
0x18000f501  lea     rcx, [rsp+8F0h+SubKey]; unsigned __int16 *
0x18000f506  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f50b  mov     r8, rsi; unsigned __int16 *
0x18000f50e  lea     rcx, [rsp+8F0h+SubKey]; unsigned __int16 *
0x18000f513  mov     edx, ebx; unsigned __int64
0x18000f515  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f51a  lea     rax, [rsp+8F0h+hKey]
0x18000f51f  mov     r12, 0FFFFFFFF80000000h
0x18000f526  mov     rcx, r12; hKey
0x18000f529  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18000f52e  mov     r9d, 20019h; samDesired
0x18000f534  lea     rdx, [rsp+8F0h+SubKey]; lpSubKey
0x18000f539  xor     r8d, r8d; ulOptions
0x18000f53c  call    cs:__imp_RegOpenKeyExW
0x18000f542  lea     r15, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f549  mov     ebx, eax
0x18000f54b  test    eax, eax
0x18000f54d  jnz     loc_18000F6E1
0x18000f553  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18000f558  lea     rax, [rsp+8F0h+cbData]
0x18000f55d  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x18000f562  lea     rdx, aProgid_0; "ProgID"
0x18000f569  lea     rax, [rbp+7F0h+Data]
0x18000f570  xor     r9d, r9d; lpType
0x18000f573  xor     r8d, r8d; lpReserved
0x18000f576  mov     [rsp+8F0h+phkResult], rax; lpData
0x18000f57b  call    cs:__imp_RegQueryValueExW
0x18000f581  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18000f586  lea     rax, [rsp+8F0h+var_8B4]
0x18000f58b  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x18000f590  lea     rdx, aVersionindepen_0; "VersionIndependentProgID"
0x18000f597  lea     rax, [rbp+7F0h+var_850]
0x18000f59b  xor     r9d, r9d; lpType
0x18000f59e  xor     r8d, r8d; lpReserved
0x18000f5a1  mov     [rsp+8F0h+phkResult], rax; lpData
0x18000f5a6  call    cs:__imp_RegQueryValueExW
0x18000f5ac  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18000f5b1  call    cs:__imp_RegCloseKey
0x18000f5b7  lea     rdx, [rsp+8F0h+SubKey]; unsigned __int16 *
0x18000f5bc  mov     rcx, r12; HKEY
0x18000f5bf  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000f5c4  lea     rdi, WPP_GLOBAL_Control
0x18000f5cb  mov     ebx, eax
0x18000f5cd  test    eax, eax
0x18000f5cf  jns     short loc_18000F602
0x18000f5d1  cmp     ax, 2
0x18000f5d5  jz      short loc_18000F602
0x18000f5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5de  cmp     rcx, rdi
0x18000f5e1  jz      short loc_18000F609
0x18000f5e3  test    byte ptr [rcx+1Ch], 4
0x18000f5e7  jz      short loc_18000F609
0x18000f5e9  mov     rcx, [rcx+10h]
0x18000f5ed  lea     edx, [r14+37h]
0x18000f5f1  lea     r9, [rsp+8F0h+SubKey]
0x18000f5f6  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18000f5fa  mov     r8, r15
0x18000f5fd  call    WPP_SF_SD
0x18000f602  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f609  cmp     word ptr [rbp+7F0h+var_850], r14w
0x18000f60e  jz      short loc_18000F65A
0x18000f610  lea     rdx, [rbp+7F0h+var_850]; unsigned __int16 *
0x18000f614  mov     rcx, r12; HKEY
0x18000f617  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000f61c  mov     ebx, eax
0x18000f61e  test    eax, eax
0x18000f620  jns     short loc_18000F653
0x18000f622  cmp     ax, 2
0x18000f626  jz      short loc_18000F653
0x18000f628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f62f  cmp     rcx, rdi
0x18000f632  jz      short loc_18000F65A
0x18000f634  test    byte ptr [rcx+1Ch], 4
0x18000f638  jz      short loc_18000F65A
0x18000f63a  mov     rcx, [rcx+10h]
0x18000f63e  lea     r9, [rbp+7F0h+var_850]
0x18000f642  mov     edx, 38h ; '8'
0x18000f647  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18000f64b  mov     r8, r15
0x18000f64e  call    WPP_SF_SD
0x18000f653  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f65a  cmp     word ptr [rbp+7F0h+Data], r14w
0x18000f662  jz      short loc_18000F6B8
0x18000f664  lea     rdx, [rbp+7F0h+Data]; unsigned __int16 *
0x18000f66b  mov     rcx, r12; HKEY
0x18000f66e  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000f673  mov     ebx, eax
0x18000f675  test    eax, eax
0x18000f677  jns     short loc_18000F6B1
0x18000f679  cmp     ax, 2
0x18000f67d  jz      short loc_18000F6B1
0x18000f67f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f686  cmp     rcx, rdi
0x18000f689  jz      loc_18000F78F
0x18000f68f  test    byte ptr [rcx+1Ch], 4
0x18000f693  jz      short loc_18000F6B8
0x18000f695  mov     rcx, [rcx+10h]
0x18000f699  lea     r9, [rbp+7F0h+Data]
0x18000f6a0  mov     edx, 39h ; '9'
0x18000f6a5  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18000f6a9  mov     r8, r15
0x18000f6ac  call    WPP_SF_SD
0x18000f6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6b8  cmp     rcx, rdi
0x18000f6bb  jz      loc_18000F78F
0x18000f6c1  test    byte ptr [rcx+1Ch], 8
0x18000f6c5  jz      loc_18000F770
0x18000f6cb  mov     rcx, [rcx+10h]
0x18000f6cf  mov     edx, 3Ah ; ':'
0x18000f6d4  mov     r9, rsi
0x18000f6d7  call    WPP_SF_S
0x18000f6dc  jmp     loc_18000F769
0x18000f6e1  cmp     eax, 2
0x18000f6e4  jnz     short loc_18000F729
0x18000f6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6ed  lea     rdi, WPP_GLOBAL_Control
0x18000f6f4  cmp     rcx, rdi
0x18000f6f7  jz      short loc_18000F722
0x18000f6f9  test    byte ptr [rcx+1Ch], 10h
0x18000f6fd  jz      short loc_18000F722
0x18000f6ff  mov     rcx, [rcx+10h]
0x18000f703  lea     edx, [rax+39h]
0x18000f706  lea     r9, [rsp+8F0h+SubKey]
0x18000f70b  mov     dword ptr [rsp+8F0h+phkResult], 80070002h
0x18000f713  mov     r8, r15
0x18000f716  call    WPP_SF_SD
0x18000f71b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f722  mov     ebx, 1
0x18000f727  jmp     short loc_18000F770
0x18000f729  test    eax, eax
0x18000f72b  jle     short loc_18000F736
0x18000f72d  movzx   ebx, ax
0x18000f730  or      ebx, 80070000h
0x18000f736  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f73d  lea     rdi, WPP_GLOBAL_Control
0x18000f744  cmp     rcx, rdi
0x18000f747  jz      short loc_18000F78F
0x18000f749  test    byte ptr [rcx+1Ch], 4
0x18000f74d  jz      short loc_18000F770
0x18000f74f  mov     rcx, [rcx+10h]
0x18000f753  lea     r9, [rsp+8F0h+SubKey]
0x18000f758  mov     edx, 3Ch ; '<'
0x18000f75d  mov     dword ptr [rsp+8F0h+phkResult], ebx
0x18000f761  mov     r8, r15
0x18000f764  call    WPP_SF_SD
0x18000f769  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f770  cmp     rcx, rdi
0x18000f773  jz      short loc_18000F78F
0x18000f775  test    byte ptr [rcx+1Ch], 10h
0x18000f779  jz      short loc_18000F78F
0x18000f77b  mov     rcx, [rcx+10h]
0x18000f77f  mov     edx, 3Dh ; '='
0x18000f784  mov     r9d, ebx
0x18000f787  mov     r8, r15
0x18000f78a  call    WPP_SF_D
0x18000f78f  mov     eax, ebx
0x18000f791  mov     rcx, [rbp+7F0h+var_30]
0x18000f798  xor     rcx, rsp; StackCookie
0x18000f79b  call    __security_check_cookie
0x18000f7a0  lea     r11, [rsp+8F0h+var_20]
0x18000f7a8  mov     rbx, [r11+38h]
0x18000f7ac  mov     rsi, [r11+40h]
0x18000f7b0  mov     rsp, r11
0x18000f7b3  pop     r15
0x18000f7b5  pop     r14
0x18000f7b7  pop     r12
0x18000f7b9  pop     rdi
0x18000f7ba  pop     rbp
0x18000f7bb  retn
```
