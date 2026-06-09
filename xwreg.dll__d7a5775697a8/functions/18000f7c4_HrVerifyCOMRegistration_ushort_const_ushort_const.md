# HrVerifyCOMRegistration(ushort * const,ushort * * const)

- ea: `0x18000f7c4`
- end: `0x18000fa78`
- name: `?HrVerifyCOMRegistration@@YAJQEAGQEAPEAG@Z`
- size: `692`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000daac`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000e8bc`
- `0x18000f7c4`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f937`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f891`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f891`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f9e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f9e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8f6`

## string_xrefs

- `0x18000f819`: `CLSID`

## pseudocode

```c
__int64 __fastcall HrVerifyCOMRegistration(unsigned __int16 *const a1, unsigned __int16 **const a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  int FullNonHardCodedPath; // eax
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned __int16 *v9; // rax
  PVOID *v10; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[72]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Data[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  hKey = 0;
  if ( a2 )
    *a2 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x41u, L"CLSID");
  StringCchCatW(SubKey, 0x41u, &qword_180017630);
  StringCchCatW(SubKey, 0x41u, a1);
  StringCchCatW(SubKey, 0x41u, &qword_180017630);
  StringCchCatW(SubKey, 0x41u, L"InprocServer32");
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
  {
    v4 = 0;
    if ( a2 )
    {
      memset_0(Data, 0, 0x20Au);
      cbData = 522;
      v5 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
      v4 = v5;
      if ( v5 )
      {
        if ( v5 > 0 )
          v4 = (unsigned __int16)v5 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v4);
      }
      else
      {
        FullNonHardCodedPath = HrMakeFullNonHardCodedPath(Data, v15);
        v4 = FullNonHardCodedPath;
        if ( FullNonHardCodedPath < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)Data,
              FullNonHardCodedPath);
        }
        else
        {
          v7 = -1;
          do
            ++v7;
          while ( v15[v7] );
          v8 = (unsigned int)(v7 + 1);
          v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
          *a2 = v9;
          if ( v9 )
          {
            *v9 = 0;
            StringCchCopyW(*a2, (unsigned int)v8, v15);
          }
          else
          {
            v4 = -2147024882;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
                (unsigned int)v15,
                14);
          }
        }
      }
    }
    RegCloseKey(hKey);
    goto LABEL_26;
  }
  v4 = 1;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      1);
LABEL_26:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    WPP_SF_D(v10[2], 119, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000f7c4  mov     [rsp-8+arg_10], rbx
0x18000f7c9  mov     [rsp-8+arg_18], rsi
0x18000f7ce  push    rbp
0x18000f7cf  push    rdi
0x18000f7d0  push    r12
0x18000f7d2  push    r14
0x18000f7d4  push    r15
0x18000f7d6  lea     rbp, [rsp-400h]
0x18000f7de  sub     rsp, 500h
0x18000f7e5  mov     rax, cs:__security_cookie
0x18000f7ec  xor     rax, rsp
0x18000f7ef  mov     [rbp+420h+var_30], rax
0x18000f7f6  xor     r15d, r15d
0x18000f7f9  mov     rsi, rdx
0x18000f7fc  mov     [rsp+520h+hKey], r15
0x18000f801  mov     rbx, rcx
0x18000f804  test    rdx, rdx
0x18000f807  jz      short loc_18000F80C
0x18000f809  mov     [rdx], r15
0x18000f80c  mov     edi, 41h ; 'A'
0x18000f811  mov     [rsp+520h+SubKey], r15w
0x18000f817  mov     edx, edi; unsigned __int64
0x18000f819  lea     r8, aClsid_0; "CLSID"
0x18000f820  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000f825  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f82a  lea     r8, qword_180017630; unsigned __int16 *
0x18000f831  mov     edx, edi; unsigned __int64
0x18000f833  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000f838  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f83d  mov     r8, rbx; unsigned __int16 *
0x18000f840  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000f845  mov     edx, edi; unsigned __int64
0x18000f847  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f84c  lea     r8, qword_180017630; unsigned __int16 *
0x18000f853  mov     edx, edi; unsigned __int64
0x18000f855  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000f85a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f85f  lea     r8, aInprocserver32; "InprocServer32"
0x18000f866  mov     edx, edi; unsigned __int64
0x18000f868  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000f86d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f872  lea     rax, [rsp+520h+hKey]
0x18000f877  mov     r9d, 20019h; samDesired
0x18000f87d  xor     r8d, r8d; ulOptions
0x18000f880  mov     [rsp+520h+phkResult], rax; phkResult
0x18000f885  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x18000f88a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000f891  call    cs:__imp_RegOpenKeyExW
0x18000f897  lea     r12, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f89e  test    eax, eax
0x18000f8a0  jnz     loc_18000F9EF
0x18000f8a6  lea     rdi, WPP_GLOBAL_Control
0x18000f8ad  mov     ebx, r15d
0x18000f8b0  test    rsi, rsi
0x18000f8b3  jz      loc_18000F9E2
0x18000f8b9  mov     ebx, 20Ah
0x18000f8be  lea     rcx, [rbp+420h+Data]; void *
0x18000f8c5  mov     r8d, ebx; Size
0x18000f8c8  xor     edx, edx; Val
0x18000f8ca  call    memset_0
0x18000f8cf  mov     rcx, [rsp+520h+hKey]; hKey
0x18000f8d4  lea     rax, [rsp+520h+cbData]
0x18000f8d9  mov     [rsp+520h+lpcbData], rax; lpcbData
0x18000f8de  xor     r9d, r9d; lpType
0x18000f8e1  lea     rax, [rbp+420h+Data]
0x18000f8e8  mov     [rsp+520h+cbData], ebx
0x18000f8ec  xor     r8d, r8d; lpReserved
0x18000f8ef  mov     [rsp+520h+phkResult], rax; lpData
0x18000f8f4  xor     edx, edx; lpValueName
0x18000f8f6  call    cs:__imp_RegQueryValueExW
0x18000f8fc  mov     ebx, eax
0x18000f8fe  test    eax, eax
0x18000f900  jnz     loc_18000F9AB
0x18000f906  lea     rdx, [rbp+420h+var_450]; unsigned __int16 *
0x18000f90a  lea     rcx, [rbp+420h+Data]; lpSrc
0x18000f911  call    ?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z; HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)
0x18000f916  mov     ebx, eax
0x18000f918  test    eax, eax
0x18000f91a  js      short loc_18000F987
0x18000f91c  lea     rcx, [rbp+420h+var_450]
0x18000f920  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f924  inc     rax
0x18000f927  cmp     [rcx+rax*2], r15w
0x18000f92c  jnz     short loc_18000F924
0x18000f92e  inc     eax
0x18000f930  mov     r14d, eax
0x18000f933  lea     rcx, [rax+rax]; cb
0x18000f937  call    cs:__imp_CoTaskMemAlloc
0x18000f93d  mov     [rsi], rax
0x18000f940  test    rax, rax
0x18000f943  jz      short loc_18000F95D
0x18000f945  mov     [rax], r15w
0x18000f949  lea     r8, [rbp+420h+var_450]; unsigned __int16 *
0x18000f94d  mov     rcx, [rsi]; unsigned __int16 *
0x18000f950  mov     edx, r14d; unsigned __int64
0x18000f953  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f958  jmp     loc_18000F9E2
0x18000f95d  mov     ebx, 8007000Eh
0x18000f962  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f969  cmp     rcx, rdi
0x18000f96c  jz      short loc_18000F9E2
0x18000f96e  test    byte ptr [rcx+1Ch], 4
0x18000f972  jz      short loc_18000F9E2
0x18000f974  mov     edx, 73h ; 's'
0x18000f979  mov     dword ptr [rsp+520h+phkResult], 8007000Eh
0x18000f981  lea     r9, [rbp+420h+var_450]
0x18000f985  jmp     short loc_18000F9D6
0x18000f987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f98e  cmp     rcx, rdi
0x18000f991  jz      short loc_18000F9E2
0x18000f993  test    byte ptr [rcx+1Ch], 4
0x18000f997  jz      short loc_18000F9E2
0x18000f999  mov     edx, 74h ; 't'
0x18000f99e  mov     dword ptr [rsp+520h+phkResult], eax
0x18000f9a2  lea     r9, [rbp+420h+Data]
0x18000f9a9  jmp     short loc_18000F9D6
0x18000f9ab  jle     short loc_18000F9B6
0x18000f9ad  movzx   ebx, ax
0x18000f9b0  or      ebx, 80070000h
0x18000f9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9bd  cmp     rcx, rdi
0x18000f9c0  jz      short loc_18000F9E2
0x18000f9c2  test    byte ptr [rcx+1Ch], 4
0x18000f9c6  jz      short loc_18000F9E2
0x18000f9c8  mov     edx, 75h ; 'u'
0x18000f9cd  mov     dword ptr [rsp+520h+phkResult], ebx
0x18000f9d1  lea     r9, [rsp+520h+SubKey]
0x18000f9d6  mov     rcx, [rcx+10h]
0x18000f9da  mov     r8, r12
0x18000f9dd  call    WPP_SF_SD
0x18000f9e2  mov     rcx, [rsp+520h+hKey]; hKey
0x18000f9e7  call    cs:__imp_RegCloseKey
0x18000f9ed  jmp     short loc_18000FA25
0x18000f9ef  mov     ebx, 1
0x18000f9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9fb  lea     rdi, WPP_GLOBAL_Control
0x18000fa02  cmp     rcx, rdi
0x18000fa05  jz      short loc_18000FA4B
0x18000fa07  test    byte ptr [rcx+1Ch], 10h
0x18000fa0b  jz      short loc_18000FA2C
0x18000fa0d  mov     rcx, [rcx+10h]
0x18000fa11  lea     edx, [rbx+75h]
0x18000fa14  lea     r9, [rsp+520h+SubKey]
0x18000fa19  mov     dword ptr [rsp+520h+phkResult], ebx
0x18000fa1d  mov     r8, r12
0x18000fa20  call    WPP_SF_SD
0x18000fa25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa2c  cmp     rcx, rdi
0x18000fa2f  jz      short loc_18000FA4B
0x18000fa31  test    byte ptr [rcx+1Ch], 10h
0x18000fa35  jz      short loc_18000FA4B
0x18000fa37  mov     rcx, [rcx+10h]
0x18000fa3b  mov     edx, 77h ; 'w'
0x18000fa40  mov     r9d, ebx
0x18000fa43  mov     r8, r12
0x18000fa46  call    WPP_SF_D
0x18000fa4b  mov     eax, ebx
0x18000fa4d  mov     rcx, [rbp+420h+var_30]
0x18000fa54  xor     rcx, rsp; StackCookie
0x18000fa57  call    __security_check_cookie
0x18000fa5c  lea     r11, [rsp+520h+var_20]
0x18000fa64  mov     rbx, [r11+40h]
0x18000fa68  mov     rsi, [r11+48h]
0x18000fa6c  mov     rsp, r11
0x18000fa6f  pop     r15
0x18000fa71  pop     r14
0x18000fa73  pop     r12
0x18000fa75  pop     rdi
0x18000fa76  pop     rbp
0x18000fa77  retn
```
